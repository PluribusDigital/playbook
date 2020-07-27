# Database Change Management

Many apps run on databases, often relational databases. In developing software, we have to manage changes to the database including:

* Changes to the database schema (tables, columns, etc.)
* Changes to configuration (indices, etc.)
* Updates to reference data
* Population of seed development/demo data

Any of the above could be done via manual effort - accessing the database via a console or admin tool to make changes. This is simple and can work, but has drawbacks:

* That now has to be replicated in other environments (another developer's machine, upper environments as code is promoted, etc.)
* The information on the change is not part of source control.
* The change can't be rolled back or re-applied easily.

## Automation

By automating this process, we gain some nice features:

* Changes can be easily, reliably applied in any environment.
* The schema is tied into source control, so the database can maintain parity with any branch/commit.

### How the Automation Works

See [Flyway documentation](https://flywaydb.org/getstarted/how) for a more robust explanation of how it works. (Other tools are similar.)

* Developer writes migration scripts for each change (new table, new column, rename, etc.)
* Developer runs a command to apply migrations
* The tool checks it's own schema reference table (stores information about which changes have been applied in this database)
* The tool applies any new migrations in order, and skips any that have already been done.

### Examples of Migration Scripts

Initially create a table.
```SQL
CREATE TABLE Appointment (
  id INT NOT NULL,
  department_Name VARCHAR(100) NOT NULL,
  appointment_Date VARCHAR(8) NOT NULL,
  PRIMARY KEY(id)
);
```

Now we realized we need to change the id to be auto-incremented.
```SQL
ALTER TABLE Appointment 
  MODIFY COLUMN id INT NOT NULL AUTO_INCREMENT;
```

Let's add a column for a new feature. Since this app is already in production, we'll also want to set a default value for old records, but only for a certain department.

```SQL
ALTER TABLE Appointment 
  ADD COLUMN Status VARCHAR(16) NOT NULL;
UPDATE Appointment 
  SET Status='Completed' 
  WHERE Status<>'Completed' 
  AND department_Name='Department of Redundance Department' ;
```

### Benefits of Automation

Automation enables some helpful scenarios in real-world development:

* __Streamlined Deployments__: Schema changes are automated. A deployment to any given environment doesn't require a DBA or developer to kick off a special script.
* __Rollback__: If a change needs to be rolled back, it can be via script.
* __Development Flexibility__: A developer can be in the middle of working on a given branch, check out a different feature branch with code and DB changes, and switch back to their original branch - all the while having the database be appropriately matched to the given branch.
* __Repeatability__: The entire application and DB schema can be built from the source code.

## What to Look Out For

This doesn't remove all pain and risk from making changes to databases. Complex migrations, particularly those that will change a production database, still require careful consideration.

For example, updating a column and changing the datatype may require analysis of the existing data values. The good news is that the migration scripts can include logic to deal with special scenarios - but that still requires smart developers doing the appopriate planning.

## Specific Software Packages

A non-exhaustive list of some tools includes:

* [Flyway](https://flywaydb.org/) for the Java ecosystem
* [Sequelize](https://sequelize.org/v5/manual/migrations.html) for the JavaScript ecosystem
* [ActiveRecord](https://guides.rubyonrails.org/active_record_basics.html) for the Ruby ecosystem
