# STSI Playbooks

Documentation on how we do things - the "source code" for our organization.

In pretty form at: [playbook.stsiinc.com](http://playbook.stsiinc.com/)

## Making Changes

The steps to make a change are to:

1. Create a GitHub issue, using the correct issue template and tags, to document what needs to be updated and why
2. Fork the repository or create a branch
3. Make the edits
4. Create a pull request into the `gh-pages` branch

To make edits, add or update files in the `_sections` directory. Note: the formatting is based on [markdown](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet) syntax. 

Sections will be ordered by the alpha sort of the file name. Therefore, by prefixing file names with a number, we can control the order.

## Organization of Content

The basic model is as follows:

* __Topics__: A topic is the higher-level item, corresponding to one larger guide, rendered as a single long page.

* __Sections__: Each topic is comprised of multiple sections, each rendered under a heading.

## Adding Topics

To add a topic:

* The corresponding file must be added in the `_topics` directory. 
* The `_config.yml` file must be edited to add a value under `defaults` -> `scope`. See other examples to map the directory in `_sections` to the topic.

## Running Locally

Content can be edited directly in GitHub. To do more complex work such as changing templates, styles, etc. you can run locally on the desktop.

See [jekyll docs](https://jekyllrb.com/) for more detail, but the TLDR is:

* [Install ruby](https://www.ruby-lang.org/en/documentation/installation/) if not present
* `gem install jekyll bundler`
* `bundle install`
* `jekyll serve`
