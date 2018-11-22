# heartofclojure

Heart of Clojure site (GH pages) [link](https://heartofclojure.eu)

## Building locally

When making changes it's a good idea to check on your own computer what the result looks like.

This site uses Jekyll, which is written in Ruby, so make sure you have Ruby and Bundler (Ruby's package manager) installed.

In a terminal, clone this repository, `cd` into it, and run `bundle install`. You only need to `bundle install` once.

After that run `bundle exec jekyll serve`. You can now access the site at [http://localhost:4000](http://localhost:4000). Changes will automatically be picked up (you do need to refresh your browser).

## Markdown vs HTML

Pages are generally written in Markdown. They need a "preamble" for Jekyll to pick them up though. For instance you can create a file named `tickets.md`, which will result in the page `https://heartofclojure.eu/tickets`. You don't need to add `.html` to the URL, and you should not use `.html` in links.

```
---
layout: default
title: Tickets
permalink: /tickets
---

## Tickets

...
```

Jekyll is configured to allow mixing HTML and markdown, so you can do this:

```
<div class="article">

## Tickets

Please buy many tickets

</div class="article">
```

Watch out though because lines that start with four or more spaces are considered as code snippets in markdown. Say you do this


```
<div>
  <ul>
    <li>a list item</li>
  </ul>
<div>
```

Then the `<li>` element will be considered a code snippet, and rendered as plain text.

In general limit the HTML to simple blocks at the top level without indentation (as the `class="article"` example above), or simple inline elements like using a `<span>` to add a class.

You can turn the markdown-inside-html behavior on or off with `markdown="0"` / `markdow="1"`, e.g.


```
<form ... markdown="0">
  ...  complicated form with lots of indentation ...
</form>
```

So this way you can write any HTML you like.
