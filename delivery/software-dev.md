# Software Development Guide

This guide allows STSI staff and teaming partners to be synced on what to expect when building web applications together. It is also a useful resource for tech resources in getting up to speed. This guide serves two types of readers:

1. **Expert Developers**: This guide serves as a reference of STSI norms of preferences in order to be consistent with other team members.

2. **Still-learning Developers**: You need an introduction to concepts, then a path to gain proficiency. Some concepts you might understand, while others are new. This guide points you in the direction of how to learn the concepts and related practices.

## Team Coordination

A team means you have to work with people, which requires communication and coordination.

### Key Concepts

#### Work Tracking

We have to track the stuff we're all doing, so that we know what each team member is working on, and what comes next. New system capabilities can be represented as user stories. We generally start with a very short description ("As a ... I want the ability to do ... so that I can ..."), and then build out more information.

Teams can use a physical board (i.e. post-it notes on the wall), or more commonly a work tracking software. Popular specialized software includes JIRA and GitHub Issues. Other general purpose tools like Trello can also work. Any tool allows us to track key elements including:

 * Title
 * Size/points
 * Acceptance criteria
 * Notes/comments/discussion

#### Meetings

**Standup Meeting:** Short, daily [standup meetings](https://www.martinfowler.com/articles/itsNotJustStandingUp.html) help team members understand what is going on across the team. The meeting is meant to be very short - just enough to raise key coordination questions. It shouldn't rehash what is already on the board, and should open up opportunities for serendipity and opportunities to solve problems.

**Retrospective:** At the end of each iteration, we reflect on what worked well, and what can improve. The format can vary a bit, but certainly include versions of "What went well" and "It would be even better if...". Some include other questions like "What still puzzles me?" The point is to encourage open, honest reflection. We read the [Retrospective Prime Directive](http://retrospectivewiki.org/index.php?title=The_Prime_Directive) aloud at the start of a retro.

#### Technical Documentation

A lot of open source software is written by people who don't work in the same office or timezone.
Over the years, they have developed some conventions so that anyone starting to work on a project can orient themselves.
Look for these files in any new project to get an idea of how to get started.

`README.md` - At a minimum, most projects will have one of these files in the root.  Typically, it explains the project's purpose and how to use it.
It may also contain information about how to install or configure your project.

`CONTRIBUTING.md` - This file describes how to contribute to a project.  It usually explains how issues are tracked, how pull requests are approved and any other code quality details like code coverage or linting.

`INSTALL.md` - Some projects will have a separate file for installation instuctions.  The separate file will usually indicate a more involved build process or signal that the project has many more users than authors. 

### The STSI Way

* Work Tracking: Any method works, so long as it is equally accessible to all team members (if any team member is remote, do it electronically).
* Standups: Find a time and cadence that fits the team's work pattern, with <= 15 minutes in the morning as the norm.
* Retrospective: Once per iteration, but certainly no less than once every month. Read the [Retrospective Prime Directive](http://retrospectivewiki.org/index.php?title=The_Prime_Directive) aloud at the start.
* Documentation: At a minimum, the project should have a `README.md` file that explains how to install, build and run the project. We would prefer a README/CONTRIBUTING/INSTALL set as [outlined here](https://github.com/LappleApple/feedmereadmes/blob/master/README-maturity-model.md#level-three-basic-readme).

## Source Control

Source control allows us to work together on writing a shared codebase (really just a bunch of text files). It helps us do a few key things:

 * Get a copy of the latest code
 * Track changes to the code
 * Save ("commit") a version of the codebase
 * Share those changes with others
 * Merge in changes from others
 * Roll back changes when things go wrong
 * Store the code in a central location

### Key Concepts

#### Git vs. GitHub

Git allows you to track sets of changes to code. All of this happens on your local computer first. Git also has the concept of a remote. GitHub is an incredibly popular service that hosts git remote repositories. There are many other tools and hosted tools (Microsoft TFS, AWS CodeCommit, GitLab, etc.) that do something similar.

#### Branching

When you want to make a set of changes, you create a branch. We follow the [gitflow](https://www.atlassian.com/git/tutorials/comparing-workflows/gitflow-workflow) workflow to apply a consistent approach to branching (and later merging). You checkout a "feature branch" in order to make a set of changes - kind of like saving off your version of the code. By branching, you won't create conflicts in the codebase while you and others are all working on changes concurrently. 

#### When & How to Commit, Push

**Commit**: With Git, you create commits to capture a save-point of the code base. This allows you to get to that version of the code, or even pull out a single file within the codebase as of that snapshot. Commit each time you create an incremental step forward - you added something without breaking anything. In general (but not always) your tests should pass before a commit. You should commit often - generally a few times per day.

**Push**: Commits happen on your local computer. That isn't part of the shared repo (e.g. GitHub.com) until you push the code to the remote repo. When you are working on a feature branch, it is generally best to push with each commit. This allows others to be able to see (or merge in) the most recent working increment of your code as needed.

#### Managing Secrets

"Secrets" refers to things that the running application needs to know, but are generally sensitive. We don't want to share secrets widely. For example, sharing AWS credentials on a public repo could [allow a bitcoin miners to hijack your account](https://readwrite.com/2014/04/15/amazon-web-services-hack-bitcoin-miners-github/). This is not good. Instead, we inject such secrets as environment variables (a.k.a. ENV).

### The STSI Way

 * **Git**: We use Git whenever possible. It is by far the dominant industry standard.
 * **Git Flow**: We use the [gitflow](https://www.atlassian.com/git/tutorials/comparing-workflows/gitflow-workflow) workflow approach to branching/merging/pull requests whenever possible.
 * **GitHub**: We use [GitHub](https://github.com/STSILABS/) by default for any repos owned by STSI, but often work with client-provided repositories.
 * **DotEnv**: By default, we use a "dotenv" approach. The libraries differ by language, but all use a local file (e.g. `/.env`) that is also in the `.gitignore`. A `/.env.example` file shows developers what values need to be filled in. In development envirionments, the contents of the file are loaded as environment variables. In production, the same environment variables are set via other means.
 
### Learning Checklist/Resources
 
  * Read Git docs [Getting started](https://git-scm.com/book/en/v1/Getting-Started) 
  * Practice using proper hygiene on real or for-fun projects
  * [Git Flight Rules](https://github.com/k88hudson/git-flight-rules#i-want-to-start-a-local-repository) walks you through common scenarios and the corresponding git commands


## Local Tools

To work with your code you need several tools on your workstation (unless you are using something like AWS Cloud9). This section has a starter list.

### Key Concepts

**Editor:** You need a way to browse and edit the codebase. Atom or VSCode are capable, free editors. Some use terminal-based tools such as Vim.

**Terminal:** You need to be able to run commands to build or run the app locally. This is done from the command line. Most operating systems have built-in terminals, but you can also install others (iterm2 for Mac, git bash for Windows, etc.).

### The STSI Way

Local developer tools are generally a matter of preference. There is no standard.

 * Some tools have configuration or data files (e.g. `.idea`). If so, make sure these are in the `.gitignore` file to avoid cluttering the repo with those files.

## Dependency Management

We never start from scratch. There are zillions of code libraries we can borrow and build upon. Package management tools do the legwork for us to find and download the right versions of the libraries and keep it all in sync when those get updated.

### Key Concepts

* __Dependency Jargon__: The terms 'dependency' or 'package' get thrown about, as do 'libraries'. Your application probably has depenedencies on other people's code. These code libraries are (hopefully) packaged into something like a node module, ruby gem, python egg, etc. Packaged libraries can be dealt with by a package manager, saving lots of headache.
* __Package Repository__: Packaged libraries are usually available through a central package repository on the public internet such as [maven central](https://search.maven.org/), [rubygems](https://rubygems.org/), [PyPI](https://pypi.org/) or [npm](https://www.npmjs.com/). These tend to be the default, but organizations can also have private package repositories for the purpose of keeping code confidential or secure. 
* __Manifest__: Best practice is to use a manifest file (package.json, Gemfile, requirements.txt, etc.) that describes the dependencies required by your project. This allows others who download your code to let the package manager software go out and get the right versions of everything. 
* __Dependency Resolution__: Package managers also resolve dependencies, because your dependencies have dependencies, and those might conflict. 
* __Updates__: Packages are a great accelerator at first. You get to plug in other people's code. It becomes a maintenance pain to update packages, and particularly to do so promptly when a [vulnerability](https://en.wikipedia.org/wiki/Common_Vulnerabilities_and_Exposures) is found. You also have to make sure your dependencies are maintained and don't grow stale.

### The STSI Way

* Only introduce dependencies via a manifest and package manager, unless there is no other way
* Perform due dilligence to investigate a new package, including update frequency, github stars/forks, code investigation, etc.
* Bringing in a library carries a cost. If you can replace it with 10 lines of custom code, the latter is probably better.

## Testing

We write code to test our code. It sounds like double-work but saves a ton of time. We know instantly when something breaks.

### Key Concepts
* _Types of testing:_ [There are many different ways to test software](https://en.wikipedia.org/wiki/Software_testing), but developers typically mean unit tests.  These tests focus on a single function or class.  When many classes or functions are tested together, this is known as integration testing.  Another popular type of testing is behavior testing, which tests the application as a whole and can use special tooling to help automate these tests.
* _Test coverage:_ Even a simple function will have if statements, so multiple tests will be needed to make sure all code paths in a function are exercised.  Test coverage is used to show how much of the code is being tested and which parts are not covered.
* _Testing provides early warnings:_  Sometimes changes in one part of the application will accidently break other parts.  With tests, these side effects are surfaced immediately and can be addressed in the same pull request.  Without tests, the bugs are passed along and will be found at a much later time which can be costly and time consuming.
* _Testing improves Maintainability:_ Write tests not so much for yourself, but for the dozens of other developers that will read and maintain your code over many years.  Oftentimes, a test acts as a secondary means of communicating the purpose of a block of code.  If the maintainer cannot understand the original code, the tests exercising it may provide additional insight.

### The STSI Way
* _Coverage:_ We believe that your code should have tests that cover at least 80% of your code base, with special attention given to key functions or modules.
* _Passing Tests:_ We believe that code is not ready for review until all the tests are passing
* _Testing as a start:_ A great way to familiarize yourself with an existing project is to run the tests and add missing coverage.  This will give you experience building, running and understanding the code while contributing to the overall health of the project.

## Build Process & Tools

There's app code, then there's code that helps us write the code. Some languages are compiled, but many interpreted (not compiled) languages are still not run directly from your source code. These build tools handle all kinds of grunt work to help us work faster and handle the needs of different environments. 

### Key Concepts

 * _Environment Config:_ The build process can adapt the code for different environments, such as which database you connect to or many other things.
 * _Transpiling:_ In Javascript, code is often not written in Javascript. It is written in Typescript, JSX, CoffeeScript, or some other variant. Transpiling translates the source code to vanilla Javascript. This allows you to write code in a preferred language, but still have the code run in environments (like web browsers) that only support certain languages/versions.
 * _Source maps:_ Transpiled code can be hard to debug, since you wrote it in one style, but it gets run in another - and this throws off line number references for errors. Source maps basically provide for friendly error messages to show you where in the original source the error originated - as opposed to where in the transpiled code the error materialized. 
 * _Minification:_ Frontend in-browser apps are typically minified. This is the process of basically compressing the code to get rid of white space, long variable names, etc. It makes the code fairly unreadable to humans, but quicker to download for the browser. 
 * _Tree shaking:_ You may load lots of libraries, but only use small bits of each. Tree shaking is a process to prune the codebase to only what you are using so that less is sent to the browser, and less has to be dealt with by the machine running it. 


### The STSI Way

 * __Convention__: Unless there is a great reason otherwise, stick to the dominant convention of the framework you use. For example, React.js apps tend to use webpack and babel. Better yet, use react-scripts/create-react-app in that case.
 
## Continuous Integration 

A Continuous Integration (CI) process looks for changes in the code (i.e. new commits being pushed or merged), then automatically tries to build, run, test, analyze, and deploy the code.


### Key Concepts
* _Source of truth:_ Sometimes, you may write code that works on your machine, only to discover that it doesn't work on other machines. There may be a forgotton configuation or pre-condition that prevents it from running smoothly or at all. A CI server can act as an impartial judge of whether the code base works by building, installing and testing each change.  Unless it works on the CI server, it doesn't _work_.
* _Automated build:_ Having a server rebuild the codebase after every change means that the entire build process has to be scripted.  While this requires that the development team has to gain some fluency with operational concepts like environment configuration and bash scripts, it makes sure that the build process is well-understood, consistent and version-controlled.
* _Dependency security audit_: Dependencies (borrowed libraries of code) are a primary vector for the introduction of security vulnerabilities in your app. Well-maintained libraries release patch-level versions to fix vulnerabilities. Tools like `npm audit` and capabilities of tools like Artifactory and Nexus allow the audit of depenecies to find such inherited vulnerabilities. 
* _Automated tests:_ Once the codebase is built, the server should be able to run a suite of tests to validate the functionality and verify nothing has broken.  Again, this will rely on scripts to initialize the environment and execute the tests.
* _Capture Metrics:_ If the test suite ran successfully, the CI server can use other tools to measure code coverage, code complexity, compliance with style and a host of other metrics that can be tracked to show how the code has changed, and hopefully, improved over time.
* _Validate pull requests:_ A CI server can be used as the first step in a PR review process.  Before other developers get a chance to review the code, it can be automatically built, tested and measured.  This frees up the development team to perform high-quality review tasks only after the low-level checks have succeeded.

### The STSI Way
* _Use a CI server:_ There are several free CI servers available.  We use [Travis](https://travis-ci.org/STSILABS) or [CircleCI](https://circleci.com/gh/STSILABS) for open source projects, and those or others for customer work.  These should be configured to build and test every pull request.
* _Metrics:_ Depending on the application, it may be important to use analyzers to check code quality.  In the past we have used [Code Climate](https://codeclimate.com/) to perform static analysis and [Coveralls](https://coveralls.io/github/STSILABS) to track code coverage.  Both of these tools should be integrated with the CI server during PR builds.
* _Perform security scans_: Static code analysis products like the above code quality tools, or standalone security scan solutions, should be used to find potentially unsecure code (i.e. of the code that we write).
* _Enforce security audits_: Dependency audit results of high severity should "break the build", and not allow the app to progress to deployment. This is generally a quick fix (updating the library to the latest patch version), but could occasionally result in replacing a library that is not well maintained enough to issue fixes.


## Deployment

The app has to run somewhere, generally some virtual server on the cloud.

### Key Concepts

* _Multiple Environments_: An app will typically have several environments to which to deploy. 
  * Production: the environment that is live to end users.
  * Staging: a production-equivalent environment for any final testing and validation. Deploying to this environment is a good test that the deployment process will be smooth in production.
  * Development: a frequently-changing environment that is similar to staging, but has the latest changes from developers. Changes may not be truly ready for production. This provides a way for developers to see changes running live, share them with stakeholders for a preview and feedback, etc.
  * (Ad Hoc): Modern cloud platforms allow us to spin up new environments (app server, database, etc.) that might be useful to demo a specific feature, test a configuration, etc.
* _Deployment Scripts_: Apps typically require various tasks to be run on deployment. For example, it may have to kick off a background worker, run database migrations, etc.

### The STSI Way

* _Automate_ deployment as part of CI. For example, a change to the master branch could trigger a deployment to the production environment. This is why a good CI process that you can trust with your life is important. 
