# proposal-guide
STSI guide to writing, editing, managing proposals

In pretty form at: [stsilabs.github.io/proposal-guide](http://stsilabs.github.io/proposal-guide/) 

## Organization of Content

The basic model is as follows:

* __Topics__: A topic is the higher-level item, corresponding to one larger guide, rendered as a single long page.

* __Sections__: Each topic is comprised of multiple sections, each rendered under a heading.

## Editing

To make edits, add or update files in the `_sections` directory. Note: the formatting is based on [markdown](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet) syntax. 

Sections will be ordered by the alpha sort of the file name. Therefore, by prefixing file names with a number, we can control the order.

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
