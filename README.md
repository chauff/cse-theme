# cse-theme

This Jekyll theme is built on top of [Minima](https://github.com/jekyll/minima), Jekyll's default theme. Only the necessary files were kept, the rest was stripped from the repo.

For this theme to work, the course information, lectures and practicals need to reside in specific folders/files (see below). Apart from those prerequisites, it should be possible to develop the lecture materials entirely in markdown, without regard for the `cse-theme`.

![cse-theme preview](/screenshot.png)

# Course content

## Course information

The course information (overview, instructors, grading, etc.) should all be contained in `index.md`.

## Adding a lecture

Place the lectures (each one in a separate markdown file) in the `_lectures` folder and add the [YAML front matter](https://jekyllrb.com/docs/front-matter/) at the top of each file, separated by tripple dashes:

```
---
layout: default
permalink: /http/
linkname: HTTP
ordering: 4
---

OTHER CONTENT
```

The `layout` variable is always `default` in our case (other Jekyll themes may have different types of pages depending on the content type). The `permalink` variable beautifies the URL and the `linkname` variable determines how the link appears in the navigation bar. As lectures are typically in a specific order, the `ordering` variable (just use integers, ascending order) determines the order of the lectures. Without this explicit ordering, the links would show up in alphabetic order.

Note: all content appearing after the front matter is pushed into the `content` attribute, accessed as `{{content}}` in `default.html`.


## Adding practicals

Practicals (assignments, exercises, old exams, etc.) are added to the `_practicals` folder. The front matter is the same as for the lectures.

# Layout

The CSS is split across files:

- `/assets/css/personalizable.css` contains the colors (and a few other bits and pieces) to personalize the skin.
- `/assets/css/skin.css` contains the CSS for the layout of the entire page (CSS grid) and the header, navbar and footer.
- `/assets/css/github-markdown.css` contains the CSS for the layout of the lectures/exercises, etc. The CSS comes from [sindresorhus](https://github.com/sindresorhus/github-markdown-css) (with slight adaptations).


## Installation

This theme repo was designed for the [CSE1500 course materials](https://github.io/chauff/Web-Teaching/). It does not have to be forked, cloned or anything else. It can be used as [remote theme](https://github.blog/2017-11-29-use-any-theme-with-github-pages/). All that is needed in the repository to apply the theme to is a file `_config.yml` that contains just two lines:

```
baseurl: "/Web-Teaching"
remote_theme: chauff/cse-theme
```

The `baseurl` is used to set the root of the website (minus the hostname). The `remote_theme` has the format `GITHUBUSERNAME/REPO`. That's it. Once the `_config.yml` file is added to the repository of choice this theme will apply to it.