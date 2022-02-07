---
title: 'Academic Pages'
date: 2022-01-19
permalink: /posts/2022/01/Academic-Pages/
tags:
  - Academic Pages
  - tutorials
---

Notes on modifying the [Academic Pages](https://academicpages.github.io/) template to fit my personal website needs.

## Making it personal - The sidebar
Modify the settings within `_config.yml` to configure the sidebar image, name, description, social/professional links, etc.

## Changing the header
Add, remove, or comment out sections of `_data/navigation.yml` to change which pages will appear in the header

The title of the sections within this file must match some filename within `_pages`

## Blog posts
Write blog posts by creating a file with the naming convention 'YYYY-MM-DD-Title.md'

Within this file, include the following header section at the top of the file with details replaced

```
---
title: 'Title'
date: YYYY-MM-DD
permalink: /posts/YYYY/MM/Title/
tags:
 - Tag1
 - Tag2
 - ...
---
```

## Markdown
Use the [Markdown Guide "Markdown Cheat](https://www.markdownguide.org/cheat-sheet/) Sheet" for quick reference.

Most useful notes:
* Comment with `<!--` to begin commment and `-->` to close.
* Place a horizontal rule with `***`, `---`, or `___`
* Bold font with `**` before and after the text
* Italicize with `_` before and after the text

## Adding a 'Favicon' - Browser tab image
Add the following to the `head` of `default.html`
```
<link rel="icon" href="/images/filename.extension">
```
where `filename` and `extension` are replaced by the corresponding fields of the image for the favicon. The `/` before `images/filename.extension` is important. Without this, the favicon will only be applied to the home page

## Adding an image to a blog post
Place an image on a post with `![Image caption](/images/filename.extension)`
