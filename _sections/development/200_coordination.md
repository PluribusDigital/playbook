---
title: Team Coordination
---

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

**README.md:**

At a minimum, most projects will have one of these files in the root.  Typically, it explains the project's purpose and how to use it.
It may also contain information about how to install or configure your project.

**CONTRIBUTING.md:**

This file describes how to contribute to a project.  It usually explains how issues are tracked, how pull requests are approved and any other code quality details like code coverage or linting.

**INSTALL.md:**

Some projects will have a separate file for installation instuctions.  The separate file will usually indicate a more involved build process or signal that the project has many more users than authors. 

### The STSI Way

* Work Tracking: Any method works, so long as it is equally accessible to all team members (if any team member is remote, do it electronically).
* Standups: Find a time and cadence that fits the team's work pattern, with <= 15 minutes in the morning as the norm.
* Retrospective: Once per iteration, but certainly no less than once every month. Read the [Retrospective Prime Directive](http://retrospectivewiki.org/index.php?title=The_Prime_Directive) aloud at the start.
* Documentation: At a minimum, the project should have a `README.md` file that explains how to install, build and run the project. We would prefer a README/CONTRIBUTING/INSTALL set as [outlined here](https://github.com/LappleApple/feedmereadmes/blob/master/README-maturity-model.md#level-three-basic-readme).
