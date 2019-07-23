---
title: Source Control
---

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
