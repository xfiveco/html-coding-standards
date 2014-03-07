HTML Coding Standards
=====================

HTML Coding Standards you must conform to when writing HTML in XHTMLized projects.

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

