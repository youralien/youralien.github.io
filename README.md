# youralien personal website

## Local Development

### Running
```
bundle exec jekyll serve
```

### Reminders about folder structure

Important main files
- `index.html` has the home page
- `_config.yml` for site wide variables, if you will?

For styling/CSS, there are a few places these are located 
- `assets/css/style-v...`
- `_sass/` folder has separate `*.scss` files for each of the pages. For example, `_home.scss` is linked to the home page `index.html`. Similarly, `_publication.scss` was used for the separate publication page

### Adding new content

#### Publications
Adding new publications is pretty simple. They are defined as simple html files. View the examples in `_publications`

For featured publications there's a bit more work.
1. Create a new papericon in the `/papericons/` folder.
2. Make sure when creating your `{publications}.html` that you also include the `highlight: true` and `papericon: /papericons/affinder.png` lines.
3. This should be reflected on the home page.  See [this code line](https://github.com/youralien/youralien.github.io/blob/master/index.html#L77) in the home page `index.html` for exact code where it only looks for the highlights.

#### Posts (Blog posts)
Adding new posts are pretty easy as well. Look in the `_posts` folder.

Here's one example from paperairplane, below. Notice that some key metadata is defined such as title, cover image, date. The categories are also used.
```
---
layout: post

#event information
title:  "Robot Street Signs"
cover: "img/yellow-sign-detector.gif"
date:   2015-10-26
start_time: "10:00"
categories: [projects]

#event organiser details
organiser: "Ryan Louie"
---
```

The post.categories metadata is used for filtering which blog posts to show in the active_projects.html file. Specifically, it filters posts to include only those with the "projects" category. This is done by the line {% assign project-posts = site.posts | where: "categories", "projects" %} which assigns to project-posts only those posts that have "projects" in their categories.

Relevant code excerpt from active_projects.html:
```
{% assign project-posts = site.posts | where: "categories", "projects" %}
{% for post in project-posts %}
```

## License

The MIT License (MIT)

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.


