---
title: 'Academic Pages'
date: 2022-01-19
permalink: /posts/2022/01/Academic-Pages/
tags:
  - Academic Pages
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
 - Tags...
---
```
