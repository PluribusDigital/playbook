---
title: Dependency Management
---

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
