HTML Coding Standards
=====================

HTML Coding Standards you must conform to when writing HTML in XHTMLized projects.

## Table of contents

- [Write valid HTML](#write-valid-html)
- [Indentation](#indentation)
- [Line endings](#line-endings)
- [Encoding and charset](#encoding-and-charset)
- [Special characters](#special-characters)
- [Images](#images)
- [Images prefixes](#images-prefixes)
- [HTML anchors](#html-anchors)
- [Comments](#comments)
- [Accessibility](#accessibility)
- [Attaching CSS and JavaScript files](#attaching-css-and-javascript-files)
- [License](#license)

## Write valid HTML

All HTML code must be valid and well formed. You must validate it against the HTML specification pertaining to the project you are working on. Unless another specification is requested or needed, use HTML5 Document Type Definition:

```html
<!DOCTYPE HTML>
```

### Lowercase names

Element and attribute names must be in all lower case:


```html
<!-- Correct -->
<input name="name" type="text" />

<!-- Wrong -->
<input name="name" TYPE="text" />
```

### Closing tags

Non-empty elements must have corresponding closing tags.

```html
<h1>My title</h1>
<p>Some text</p>
```

Empty elements must be followed by a corresponding closing tag:

```html
<span></span>
```

Elements with a single tag, such as HR, BR, INPUT, IMG must end with `>`:

```html
<br>
<hr>
<img src="john.jpg" alt="John Doe" width="200" height="100">
```

### Nested elements

Nested elements must be nested appropriately - for example:

```html
<!-- Correct -->
<div>
  <p>Some text</p>
</div>
```

The `<p>` tag and its corresponding closing tag, `</p>`, are both nested inside the `<div>` and `</div>` tags.

If elements overlap they are not properly nested. This is illustrated in the following code:

```html
<!-- Wrong -->
<div>
  <p>Some text</div>
</p>
```

### Attribute values

Attribute values, even numeric attributes should be quoted—for example:

```html
<!-- Correct -->
<input name="age" type="text" size="3" />

<!-- Wrong -->
<input name=age type=text size=3 />
```

## Indentation

Use soft tabs with 2 spaces for code indentation.

Use indentation consistently to enhance the readability of the code.

When elements carry over more than one line of code, indent the contents of elements between the start tag and the end tag. This will make it easy to see where the element begins and ends.

Example:

```html
<div class="container">
  <header class="header">
    <h1>Site Name<span></span></h1>
  </header>
  <!-- / header -->
  <hr>
  <nav class="navigation">
  	<ul>
      <li><a href="#">Link</a></li>
      <li><a href="#">Link</a></li>
      <li><a href="#">Link</a></li>
      <li><a href="#">Link</a></li>
      <li><a href="#">Link</a></li>
  	</ul>
  </nav>
  <!-- / navigation -->
</div>
<!-- / container -->
```

## Line endings

Format files with \n as the line ending (Unix line endings). Do not use \r\n (Windows line endings) or \r (Apple OS's). 

## Encoding and charset

Set encoding of HTML document and its charset to UTF-8 Normalization Form C (NFC):

```html
<meta charset="utf-8" />
```

## Special characters

Encode special characters, for examle:

```html
&amp;
&copy;
&raquo;
&gt;
```

## Images

Always define width and height of the inline HTML images. It speeds up page loading. You can scale the images by leaving out either width or height attribute though this isn't recommended in usual situations.

```html	
<img src="john.jpg" alt="John Doe" width="200" height="100">
```

Check Accessibility section for the correct use of alt attribute.

## Images prefixes

For repeating elements use prefix naming (i.e bg_body.png):

- sprite = images used as CSS sprites
- bg = images used for backgrounds
- border = border graphic, including corners
- logo = images with the clients logo
- nav = images used for navigation items
- bullet = images used for the background of an li-element
- btn = images used for form buttons or links that act as buttons
- ico = images that are icons, as part of a user interface (UI)
- label = images used for labels such as form field labels
- misc = images that cannot reasonably be classified into any group
- seal = images used for security seals for SSL, VISA, MC, AMEX, etc.
- adv = advertising images
- txt = for image replacement for text
- pic = for placeholder images (place in /_media/)

For images that are part of the main elements (Header, Sidebar, Footer), use suffix naming. Eg. use sidebar_bottom, sidebar_top, sidebar_bg, etc.

## HTML anchors

When you need to link to the section inside a HTML document use ID attribute:

```html
<a href="#section">link</a>
<div id="section"></div>
```

If it isn't possible to use IDs (for example because of ASP.NET platform), use a named anchor:

```html
<a href="#section">link</a>
<a name="section"></a>
```

## Comments

Insert ending comment after closing tag of the HTML section in this format:

```html
<!-- / name-of-class-or-id -->
```

Do not use starting comment.

Examples:

```html
<ol class="accessibility-nav">
  <li><a href="#navigation">Skip to navigation</a></li>
  <li><a href="#content">Skip to content</a></li>
  <li><a href="#sidebar">Skip to sidebar</a></li>
</ol>
<!-- / accessibility-nav -->
 
<p>
  <a href="#" title="Go to homepage"><em>Home</em></a>
</p>
<!-- / breadcrumb -->
```

## Accessibility

Adhere to basic accessibility principles when writing HTML.

### General

- Use h1 - h6 to identify headings - [Read more &raquo;](http://www.w3.org/TR/2008/NOTE-WCAG20-TECHS-20081211/html.html#H4)
- Use structural elements to group links - [Read more &raquo;](http://www.w3.org/TR/2008/NOTE-WCAG20-TECHS-20081211/html.html#H50)
- Provide definitions for abbreviations by using the abbr and acronym elements - [Read more &raquo;](http://www.w3.org/TR/2008/NOTE-WCAG20-TECHS-20081211/html.html#H28)
- Use language attributes on html element to identify the default language of a document - [Read more &raquo;](http://www.w3.org/TR/2008/NOTE-WCAG20-TECHS-20081211/html.html#H57)


### Tables

- Use table markup to present tabular information - [Read more &raquo;](http://www.w3.org/TR/2008/NOTE-WCAG20-TECHS-20081211/html.html#H51)
- Use the scope attribute to associate header cells and data cells in data tables - [Read more &raquo;](http://www.w3.org/TR/2008/NOTE-WCAG20-TECHS-20081211/html.html#H63)
- Use the summary attribute of the table element to give an overview of data tables - [Read more &raquo;](http://www.w3.org/TR/2008/NOTE-WCAG20-TECHS-20081211/html.html#H73)

### Forms

- Provide submit buttons - [Read more &raquo;](http://www.w3.org/TR/2008/NOTE-WCAG20-TECHS-20081211/html.html#H32)
- Use alt attributes on images used as submit buttons - [Read more &raquo;](http://www.w3.org/TR/2008/NOTE-WCAG20-TECHS-20081211/html.html#H36)
- Use label elements to associate text labels with form controls - [Read more &raquo;](http://www.w3.org/TR/2008/NOTE-WCAG20-TECHS-20081211/html.html#H44)
- Use the title attribute to identify form controls when the label element cannot be used - [Read more &raquo;](http://www.w3.org/TR/2008/NOTE-WCAG20-TECHS-20081211/html.html#H65)
- Indicate required form controls - [Read more &raquo;](http://www.w3.org/TR/2008/NOTE-WCAG20-TECHS-20081211/html.html#H90)

### Images

- Use alt attributes on img elements - [Read more &raquo;](http://www.w3.org/TR/2008/NOTE-WCAG20-TECHS-20081211/html.html#H37)
- Use null alt text and no title attribute on img elements for images that Assistive Technology should ignore - [Read more &raquo;](http://www.w3.org/TR/2008/NOTE-WCAG20-TECHS-20081211/html.html#H67)

## Attaching CSS and JavaScript files

If necessary attach styleesheets in `head` using a `link` element, for example:

```html	
<link rel="stylesheet" media="all" href="_ui/css/main.css" />
```

If necessary attach JavaScript files at the end of document before `</body>` tag, for example:

```html	
<script src="_ui/js/jquery.jcarousel.min.js"></script>
<script src="_ui/js/main.js"></script>
</body>
</html>
```

## License

[![](http://i.creativecommons.org/l/by/4.0/88x31.png)](http://creativecommons.org/licenses/by/4.0/)

This work is licensed under a [Creative Commons Attribution 4.0 International License](http://creativecommons.org/licenses/by/4.0/).
