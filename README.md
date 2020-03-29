# Weblog

My personal weblog based on [eleventy-base-blog](https://github.com/11ty/eleventy).

[![Build Status](https://travis-ci.org/abhineet97/weblog.svg?branch=master)](https://travis-ci.org/abhineet97/weblog)

## Setup

Install Node.js and then run:

```
npm install
```

To build the site, run:

```
npx eleventy
```

To server the site for local development, run:

```
npx eleventy --serve
```

To run in debug mode:

```
DEBUG=* npx eleventy
```

### Notes

- `.eleventy.js` contains Eleventy configuations.
- `_data/metadata.json` contains blog configuations.
- `posts/` contains blog posts but posts can live in any directory. They just need the `post` tag to be added to this collection.
- Add the `nav` tag to add a template to the top level site navigation.
- Content can be any template format (blog posts needn’t be markdown, for example). Configure your supported templates in `.eleventy.js` -> `templateFormats`. \* Because `css` and `png` are listed in `templateFormats` but are not supported template types, any files with these extensions will be copied without modification to the output (while keeping the same directory structure).
- The blog post feed template is in `feed/feed.njk`. .
- Layouts used:
  - `_includes/layouts/base.njk`: the top level HTML structure
  - `_includes/layouts/home.njk`: the home page template (wrapped into `base.njk`)
  - `_includes/layouts/post.njk`: the blog post template (wrapped into `base.njk`)
- `_includes/postlist.njk` is a Nunjucks include and is a reusable component used to display a list of all the posts. `index.njk` has an example of how to use it.
