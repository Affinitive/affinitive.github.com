---
title: Bootstrap 3 Grid Components
layout: post
published: true
author: rmarscher
tags: ["Bootstrap", "CSS"]
---

One of the major changes in Bootstrap 3 is an update to the grid. It makes the grid always responsive and is simpler and more straight-forward than earlier versions of Bootstrap. The grid consists of three main components: containers, rows, and columns.

Containers
----------

The container defines the max-width for the site for different viewports, centers the content, and applies a clearfix to make sure all floated elements stay inside the container.

LESS code: `.container;`

SASS code: `@extend .container;`

Rows
----

Use rows when you have columns of layout. These cannot be the same html element as a container. It must be inside the container, but you don't necessarily have to have a container in your markup at all for rows to still work.

A row uses negative margins since each column has a "gutter" margin applied to the right and left of it. The negative margin for the row makes sure the first column is aligned with the left end of the container.

Note that these negative margins mess up the iframe size for Facebook apps if the row is up against the edge of the frame. You should give the container a `max-width: 810px` with `overflow-x: hidden` or enough padding or margin so the negative half-gutter margin of the row doesn't spill outside the frame.

A row also uses clearfix to make sure the columns stay contained in the row.

LESS code: `.make-row();`

SASS code: `@include make-row();`


Columns
-------

Bootstrap 3 changes make-column() to variants for different screen sizes which determine when the columns will become full screen width instead of the specified percentage. There are no fixed widths. It's always percentage based (hurrah!).

`@include make-md-column()` is basically equivalent to `make-column()` in lower versions of Bootstrap. But you can now also include `make-sm-column()` if you want the column to still exist on tablet and `make-xs-column()` for mobile screen sizes.  There's also `make-lg-column()` for large desktops.

The media queries for each of the column mixins use min-width so you only need to specify the lowest setting if they are all the same on larger screen sizes. For example,

If you want to nest columns inside other columns, you'll need to put a row element inside first and then your columns inside that. You can't just add more columns directly inside another column.

Just because you have multiple elements in the same row in your design doesn't mean you always need to use a row and columns. The columns make sure things align together to a grid, but your design might simply call for inline-block or floated elements with fixed widths or custom percentages. There should be a discussion with the designer to identify what was designed to the grid and what wasn't.

LESS code: `.make-md-column();`

SASS code: `@include make-md-column();`


Summary
-------

* Containers are optional.
* Rows cannot be the same element as containers.
* Columns cannot be the same element as containers or rows. Columns must be placed inside rows.







