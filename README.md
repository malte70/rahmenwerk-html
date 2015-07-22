# maltes-boilerplate

A small boilerplate for HTML5 websites.

## Components

- Server configuration files
	- sane defaults for Apache HTTPd and Lighttpd
- Website (frontend) template
	- HTML 5 page template and error pages (for HTTP errors 403, 404 and 500)
	- The page template contains:
		- OpenGraph meta data
		- a Google+ Authorship link
		- a link to your [humans.txt](http://humanstxt.org) file
		- a basic document stricture for a blog including [schema.org microdata](http://schema.org/)
	- A basic CSS framework (written in SCSS for best extensibility)

## The CSS Framework

The CSS framework included in Malte's Boilerplate is composed of the following components, described in detail below:

- [normalize.css](git.io/normalize) by Nicolas Gallagher
- [colors](https://github.com/mrmrs/colors) by Adam Morse
- A variable definition, defining basic settings like font faces and colors, and the grid size.
- The grid framework (description below)
- some basic styling like link colors, setting the configured font, helper classes for aligned text, and a small responsive image hack using max-width.

## The Grid

The grid framework is a very basic grid framework, but it's all you need (I'm currently building a rather complex commercial website using this grid). It is inspired by the class names of many big frameworks like [Twitters' Bootstrap](http://getbootstrap.com/), so if you previously used one of them, switching should not be so hard.

The main elements of the grid are **rows**, **columns** and the **wrapper**.

### Rows

A row contains all elements that should appear next to each other in full-width layout. (Hint: The width of a row is defined in \_variables.scss, as mentioned above). A row always contains 12 columns, although on smaller screens, they might be displayed below each other (the grid is fully responsive)

### Columns

A single column with the width *1* is one twelfth of a row in full width layout, one sixth of a row in tablet/landscape layout, one third in smartphone layout, or the full width in tiny screen layout.

You can use from one to all twelve parts of a row as one column, as you can see in the example below:

```html
<div class="row">
	<div class="col-1">
		<p>A small column</p>
	</div>
	<div class="col-8">
		<p>A large column</p>
	</div>
	<div class="col-3">
		<p>Another column, three times the first one in width.</p>
	</div>
</div>
<div class="row">
	<div class="col-12">
		<p>A second row with only one huge column.</p>
	</div>
</div>
```

If you need to, you can force a different column width on a specific screen size, using helper classes/prefixes:

```html
<div class="row">
	<div class="col-6 medium-col-3">
		<p>This column behaves like it was only three units wide on medium-sized screens. On small or tiny screens, it has full width.</p>
	</div>
	<div class="col-6">
		<p>Empty space</p>
	</div>
</div>
<div class="row">
	<div class="col-4 medium-col-2 small-col-1">
		<p>This columns is always one third of the full width.</p>
	</div>
	<div class="col-8 medium-col-4 small-col-2">
		<p>Ans this one is always two third of the full width.</p>
	</div>
</div>
```

### Wrapper

As you can see, I always talk about *full width* instead of *screen width*. Since you might want to have your website centered in the browser window if it is too large, you can put your rows inside a wrapper:

```html
<div class="wrapper">
	<div class="row">
		[…]
	</div>
	[…]
</div>
```

The maximum width of the wrapper is defined in `_variables.scss`; the default is 850 pixels.
