# HTML Complete Notes

## 1. What is HTML?

**HTML** stands for **HyperText Markup Language**.

HTML is the standard markup language used to create and structure web pages.

HTML is **not a programming language**. It is a markup language because it uses elements and tags to describe the structure and meaning of content.

### What can HTML do?

HTML is used to create:

- Headings
- Paragraphs
- Links
- Images
- Lists
- Tables
- Forms
- Buttons
- Audio
- Video
- Navigation menus
- Semantic page layouts

### HTML, CSS, and JavaScript

A modern web page commonly uses three technologies:

| Technology | Main Purpose |
|---|---|
| HTML | Structure and content |
| CSS | Styling and visual appearance |
| JavaScript | Behavior and interactivity |

For example:

```html
<h1>Welcome</h1>
```

HTML creates the heading structure.

```css
h1 {
    color: blue;
}
```

CSS controls the appearance.

```javascript
alert("Welcome!");
```

JavaScript adds behavior.

---

# 2. HTML Elements and Tags

An HTML **tag** is written using angle brackets.

```html
<p>
```

An HTML **element** usually contains an opening tag, content, and a closing tag.

```html
<p>Hello World</p>
```

Here:

- `<p>` = opening tag
- `Hello World` = content
- `</p>` = closing tag
- Complete `<p>Hello World</p>` = element

Some HTML elements are **void elements**, meaning they do not require a closing tag.

Examples:

```html
<br>
<hr>
<img>
<input>
<meta>
```

---

# 3. Basic HTML Document Structure

A basic HTML5 document looks like this:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My Web Page</title>
</head>
<body>

    <h1>Hello World</h1>
    <p>Welcome to my website.</p>

</body>
</html>
```

## Explanation

### `<!DOCTYPE html>`

The `<!DOCTYPE html>` declaration tells the browser that the document uses the HTML5 standard.

It is a declaration, not a normal HTML element.

---

### `<html>`

The `<html>` element is the root element of an HTML document.

All other HTML elements are normally placed inside it.

```html
<html>
    ...
</html>
```

---

### `lang="en"`

The `lang` attribute specifies the primary language of the document.

```html
<html lang="en">
```

`en` means English.

Examples:

```html
<html lang="hi">
```

Hindi

```html
<html lang="fr">
```

French

The language attribute helps browsers, screen readers, search engines, and accessibility tools understand the document language.

---

### `<head>`

The `<head>` element contains information about the document that is generally not displayed as page content.

It commonly contains:

- `<title>`
- `<meta>`
- `<link>`
- `<style>`
- `<script>`

Example:

```html
<head>
    <meta charset="UTF-8">
    <title>My Website</title>
</head>
```

---

### `<title>`

The `<title>` element defines the title of the document.

The title is usually displayed in the browser tab.

```html
<title>Student Registration</title>
```

---

### `<body>`

The `<body>` element contains the visible content of the web page.

Examples:

- Headings
- Paragraphs
- Images
- Links
- Tables
- Forms
- Lists
- Videos

```html
<body>
    <h1>Welcome</h1>
    <p>This content is visible on the page.</p>
</body>
```

---

# 4. Meta Charset

```html
<meta charset="UTF-8">
```

UTF-8 is a character encoding that supports a very large range of characters, symbols, and writing systems.

It helps browsers correctly display text such as:

```text
Hello
नमस्ते
こんにちは
你好
€ ₹ © ✓
```

It is recommended to include this declaration in the `<head>`.

---

# 5. Viewport Meta Tag

```html
<meta name="viewport" content="width=device-width, initial-scale=1.0">
```

This is important for responsive web pages.

### `width=device-width`

Sets the page width to the device's screen width.

### `initial-scale=1.0`

Sets the initial zoom level to 100%.

This helps the page display correctly on:

- Mobile phones
- Tablets
- Laptops
- Desktop computers

---

# 6. HTML Comments

Comments are notes written in HTML code that are not displayed as normal page content.

```html
<!-- This is an HTML comment -->
```

Comments can be used to:

- Explain code
- Organize sections
- Temporarily disable code

Example:

```html
<!-- Student Information -->
<h2>Student Details</h2>
```

---

# 7. Different Browsers Use Different Rendering Engines

Browsers use rendering engines to interpret HTML and CSS and display web pages.

| Browser | Rendering Engine |
|---|---|
| Google Chrome | Blink |
| Microsoft Edge | Blink |
| Mozilla Firefox | Gecko |
| Apple Safari | WebKit |

The rendering engine is responsible for converting web document information into what the user sees on the screen.

---

# 8. HTML Headings

HTML provides six heading levels:

```html
<h1>Heading 1</h1>
<h2>Heading 2</h2>
<h3>Heading 3</h3>
<h4>Heading 4</h4>
<h5>Heading 5</h5>
<h6>Heading 6</h6>
```

## Heading hierarchy

`<h1>` is the highest-level heading.

`<h6>` is the lowest-level heading.

Example:

```html
<h1>Web Development</h1>

<h2>Frontend Development</h2>
<h3>HTML</h3>
<h3>CSS</h3>
<h3>JavaScript</h3>

<h2>Backend Development</h2>
<h3>Node.js</h3>
<h3>Express.js</h3>
```

### Best Practice

Use headings according to the logical structure of the page rather than choosing a heading only because it looks larger or smaller.

---

# 9. HTML Paragraphs

The `<p>` element defines a paragraph.

```html
<p>
    HTML is used to create the structure of web pages.
</p>
```

Multiple paragraphs can be written separately:

```html
<p>HTML creates page structure.</p>
<p>CSS controls presentation.</p>
<p>JavaScript adds interactivity.</p>
```

---

# 10. The `<div>` Element

The `<div>` element is a generic block-level container.

It is commonly used to group related elements.

```html
<div>
    <h2>Student Details</h2>
    <p>Name: Rohit</p>
    <p>City: Jaipur</p>
</div>
```

A `<div>` has no special semantic meaning by itself.

It is frequently used with:

- CSS
- JavaScript
- Layout systems

Example:

```html
<div class="card">
    <h2>Product</h2>
    <p>Price: ₹999</p>
</div>
```

---

# 11. HTML Lists

HTML provides three main types of lists:

1. Ordered list
2. Unordered list
3. Description list

---

## 11.1 Ordered List `<ol>`

An ordered list normally displays items in a numbered sequence.

```html
<ol>
    <li>HTML</li>
    <li>CSS</li>
    <li>JavaScript</li>
</ol>
```

Output conceptually:

```text
1. HTML
2. CSS
3. JavaScript
```

---

## 11.2 Unordered List `<ul>`

An unordered list normally displays bullet points.

```html
<ul>
    <li>Apple</li>
    <li>Banana</li>
    <li>Mango</li>
</ul>
```

---

## 11.3 Description List `<dl>`

A description list represents terms and their descriptions.

- `<dl>` = Description List
- `<dt>` = Description Term
- `<dd>` = Description Details

Example:

```html
<dl>
    <dt>HTML</dt>
    <dd>HyperText Markup Language</dd>

    <dt>CSS</dt>
    <dd>Cascading Style Sheets</dd>

    <dt>JS</dt>
    <dd>JavaScript</dd>
</dl>
```

Description lists are useful for:

- Glossaries
- Definitions
- Terms and explanations
- Metadata-like information

---

# 12. HTML Text Formatting

HTML provides elements that communicate formatting or semantic meaning.

## `<b>` — Bold

Used for stylistically bold text without adding special importance.

```html
<p>This is <b>bold</b> text.</p>
```

---

## `<strong>` — Important Text

Indicates that the content has strong importance.

```html
<p>Please read the <strong>important notice</strong>.</p>
```

`<strong>` is semantic, whereas `<b>` is primarily stylistic.

---

## `<i>` — Italic

Used for text that is stylistically offset.

```html
<p>This is <i>italic</i> text.</p>
```

---

## `<em>` — Emphasized Text

Represents semantic emphasis.

```html
<p>This is <em>important</em> information.</p>
```

---

## `<mark>` — Highlight

Highlights text.

```html
<p>This is <mark>important</mark> text.</p>
```

---

## `<small>` — Smaller Text

Represents smaller side comments or text.

```html
<p><small>Terms and conditions apply.</small></p>
```

---

## `<del>` — Deleted Text

Represents content that has been deleted.

```html
<p>Price: <del>₹1000</del> ₹799</p>
```

---

## `<ins>` — Inserted Text

Represents content that has been added.

```html
<p>This is <ins>new content</ins>.</p>
```

---

## `<sub>` — Subscript

Displays text below the normal baseline.

Example:

```html
<p>H<sub>2</sub>O</p>
```

Output:

```text
H₂O
```

---

## `<sup>` — Superscript

Displays text above the normal baseline.

Example:

```html
<p>x<sup>2</sup></p>
```

Output:

```text
x²
```

---

# 13. Line Break and Horizontal Rule

## `<br>`

Creates a line break.

```html
<p>
    Hello<br>
    Welcome to HTML
</p>
```

---

## `<hr>`

Represents a thematic break between sections.

```html
<h2>Introduction</h2>
<p>HTML is a markup language.</p>

<hr>

<h2>CSS</h2>
<p>CSS is used for styling.</p>
```

---

# 14. HTML Links

The `<a>` element creates hyperlinks.

Basic syntax:

```html
<a href="URL">Link Text</a>
```

Example:

```html
<a href="https://www.google.com">Visit Google</a>
```

The `href` attribute specifies the destination.

---

# 15. Types of HTML Links

## 15.1 External Link

An external link points to another website.

```html
<a href="https://github.com">
    GitHub
</a>
```

---

## 15.2 Internal Link

An internal link points to another page in the same website.

```html
<a href="contact.html">
    Contact Us
</a>
```

---

## 15.3 Email Link

Uses the `mailto:` URL scheme.

```html
<a href="mailto:info@example.com">
    Email Us
</a>
```

---

## 15.4 Phone Link

Uses the `tel:` URL scheme.

```html
<a href="tel:+911234567890">
    Call Us
</a>
```

---

## 15.5 Download Link

The `download` attribute can tell the browser that the linked resource is intended to be downloaded.

```html
<a href="resume.pdf" download>
    Download Resume
</a>
```

---

# 16. Absolute and Relative URLs

## Absolute URL

An absolute URL contains the complete web address.

```html
<a href="https://react.dev">
    React Official Website
</a>
```

## Relative URL

A relative URL points to a resource relative to the current document.

```html
<a href="about.html">
    About
</a>
```

Another example:

```html
<a href="pages/contact.html">
    Contact
</a>
```

---

# 17. Target Attribute

The `target` attribute controls where a linked document is opened.

## `_self`

Opens the link in the current browsing context.

```html
<a href="about.html" target="_self">
    About
</a>
```

## `_blank`

Opens the link in a new browsing context, commonly a new tab.

```html
<a href="https://react.dev" target="_blank" rel="noopener noreferrer">
    React Website
</a>
```

For external links using `_blank`, `rel="noopener noreferrer"` is a useful security and privacy practice.

---

# 18. Navigation Menu

The `<nav>` element represents a section containing navigation links.

```html
<nav>
    <a href="index.html">Home</a>
    <a href="about.html">About</a>
    <a href="services.html">Services</a>
    <a href="contact.html">Contact</a>
</nav>
```

A navigation menu can also use lists:

```html
<nav>
    <ul>
        <li><a href="index.html">Home</a></li>
        <li><a href="about.html">About</a></li>
        <li><a href="services.html">Services</a></li>
        <li><a href="contact.html">Contact</a></li>
    </ul>
</nav>
```

---

# 19. Images

The `<img>` element embeds an image.

Basic syntax:

```html
<img src="images/logo.png" alt="Company Logo">
```

## Important attributes

### `src`

Specifies the image source.

```html
<img src="logo.png">
```

### `alt`

Provides alternative text describing the image.

```html
<img src="logo.png" alt="Company Logo">
```

The `alt` attribute is important for accessibility and is useful when the image cannot be displayed.

### `width`

Specifies the displayed width.

```html
<img src="logo.png" alt="Logo" width="300">
```

### `height`

Specifies the displayed height.

```html
<img src="logo.png" alt="Logo" width="300" height="150">
```

---

# 20. HTML Tables

Tables are used to represent data in rows and columns.

A table commonly contains:

- `<table>`
- `<thead>`
- `<tbody>`
- `<tfoot>`
- `<tr>`
- `<th>`
- `<td>`

## Basic Table

```html
<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Age</th>
            <th>City</th>
        </tr>
    </thead>

    <tbody>
        <tr>
            <td>Rohit</td>
            <td>25</td>
            <td>Jaipur</td>
        </tr>

        <tr>
            <td>Aman</td>
            <td>24</td>
            <td>Delhi</td>
        </tr>
    </tbody>
</table>
```

---

# 21. Table Elements

## `<table>`

Creates the table.

```html
<table>
    ...
</table>
```

## `<tr>`

Creates a table row.

```html
<tr>
    ...
</tr>
```

## `<th>`

Defines a header cell.

```html
<th>Name</th>
```

## `<td>`

Defines a data cell.

```html
<td>Rohit</td>
```

## `<thead>`

Groups table header rows.

## `<tbody>`

Groups the main table data.

## `<tfoot>`

Groups table footer rows.

---

# 22. `colspan`

`colspan` allows one cell to span multiple columns.

```html
<table border="1">
    <tr>
        <th>Name</th>
        <th>Age</th>
        <th>City</th>
    </tr>

    <tr>
        <td colspan="3">Student Information</td>
    </tr>
</table>
```

Here the cell spans three columns.

---

# 23. `rowspan`

`rowspan` allows one cell to span multiple rows.

```html
<table border="1">
    <tr>
        <th>Name</th>
        <th>Subject</th>
    </tr>

    <tr>
        <td rowspan="2">Rohit</td>
        <td>HTML</td>
    </tr>

    <tr>
        <td>CSS</td>
    </tr>
</table>
```

---

# 24. Complete Table Example

```html
<table border="1">
    <thead>
        <tr>
            <th>Name</th>
            <th>Age</th>
            <th>City</th>
        </tr>
    </thead>

    <tbody>
        <tr>
            <td>Rohit</td>
            <td>25</td>
            <td>Jaipur</td>
        </tr>

        <tr>
            <td>Aman</td>
            <td>24</td>
            <td>Delhi</td>
        </tr>
    </tbody>

    <tfoot>
        <tr>
            <td colspan="3">Total Students: 2</td>
        </tr>
    </tfoot>
</table>
```

> For production websites, CSS is generally preferred over the obsolete `border` attribute for table styling.

---

# 25. HTML Forms

The `<form>` element represents a section containing interactive controls for submitting information.

Example:

```html
<form>
    <label for="name">Name:</label>
    <input type="text" id="name" name="name">

    <button type="submit">Submit</button>
</form>
```

Forms are commonly used for:

- Registration
- Login
- Search
- Contact forms
- Feedback
- Checkout
- Applications

---

# 26. Input Element

The `<input>` element collects user input.

Example:

```html
<input type="text">
```

---

# 27. Common Input Attributes

## `placeholder`

Displays hint text.

```html
<input
    type="text"
    placeholder="Enter your name">
```

---

## `maxlength`

Specifies the maximum number of characters allowed.

```html
<input
    type="text"
    maxlength="20">
```

---

## `minlength`

Specifies the minimum number of characters required.

```html
<input
    type="text"
    minlength="3">
```

---

## `required`

Makes the field required.

```html
<input
    type="email"
    required>
```

---

## `readonly`

Prevents the user from editing the field.

```html
<input
    type="text"
    value="Jaipur"
    readonly>
```

A readonly field can generally still be submitted with the form.

---

## `disabled`

Disables the control.

```html
<input
    type="text"
    value="Not Available"
    disabled>
```

A disabled form control is not submitted as a successful form control.

---

# 28. HTML Input Types

HTML provides many specialized input types.

| Input Type | Purpose |
|---|---|
| `text` | Single-line text |
| `password` | Password input |
| `email` | Email address |
| `number` | Numeric input |
| `tel` | Telephone number |
| `url` | URL input |
| `search` | Search input |
| `date` | Date picker |
| `time` | Time picker |
| `datetime-local` | Local date and time |
| `month` | Month and year |
| `week` | Week selection |
| `color` | Color picker |
| `range` | Slider |
| `checkbox` | Multiple selections |
| `radio` | One selection from a group |
| `file` | File upload |
| `hidden` | Hidden form value |
| `image` | Image submit control |
| `submit` | Submit button |
| `reset` | Reset form |
| `button` | Generic button |

---

# 29. Text Input

```html
<label for="username">Username</label>

<input
    type="text"
    id="username"
    name="username"
    placeholder="Enter username">
```

---

# 30. Password Input

```html
<label for="password">Password</label>

<input
    type="password"
    id="password"
    name="password"
    placeholder="Enter password">
```

The browser normally masks the characters.

---

# 31. Email Input

```html
<label for="email">Email</label>

<input
    type="email"
    id="email"
    name="email"
    placeholder="Enter email"
    required>
```

Browsers can perform basic email-format validation.

---

# 32. Number Input

```html
<label for="age">Age</label>

<input
    type="number"
    id="age"
    name="age"
    min="1"
    max="100">
```

---

# 33. Telephone Input

```html
<label for="phone">Phone</label>

<input
    type="tel"
    id="phone"
    name="phone"
    placeholder="Enter phone number">
```

---

# 34. URL Input

```html
<label for="website">Website</label>

<input
    type="url"
    id="website"
    name="website"
    placeholder="https://example.com">
```

---

# 35. Search Input

```html
<label for="search">Search</label>

<input
    type="search"
    id="search"
    name="search"
    placeholder="Search products">
```

---

# 36. Date Input

```html
<label for="dob">Date of Birth</label>

<input
    type="date"
    id="dob"
    name="dob">
```

---

# 37. Time Input

```html
<label for="time">Time</label>

<input
    type="time"
    id="time"
    name="time">
```

---

# 38. Date and Time Input

```html
<label for="meeting">Meeting</label>

<input
    type="datetime-local"
    id="meeting"
    name="meeting">
```

---

# 39. Month Input

```html
<input
    type="month"
    name="month">
```

Allows selection of a month and year.

---

# 40. Week Input

```html
<input
    type="week"
    name="week">
```

Allows selection of a week and year.

---

# 41. Color Input

```html
<label for="color">Choose Color</label>

<input
    type="color"
    id="color"
    name="color">
```

---

# 42. Range Input

```html
<label for="volume">Volume</label>

<input
    type="range"
    id="volume"
    name="volume"
    min="0"
    max="100"
    value="50">
```

---

# 43. Checkbox

A checkbox allows the user to select zero, one, or multiple options.

```html
<h3>Select Your Skills</h3>

<input
    type="checkbox"
    id="html"
    name="skills"
    value="HTML">

<label for="html">HTML</label>

<br>

<input
    type="checkbox"
    id="css"
    name="skills"
    value="CSS">

<label for="css">CSS</label>

<br>

<input
    type="checkbox"
    id="js"
    name="skills"
    value="JavaScript">

<label for="js">JavaScript</label>
```

The `id` connects the input with its `<label>`.

---

# 44. Radio Button

Radio buttons are normally used when the user must choose one option from a group.

The radio buttons should share the same `name`.

```html
<h3>Select Gender</h3>

<input
    type="radio"
    id="male"
    name="gender"
    value="Male">

<label for="male">Male</label>

<br>

<input
    type="radio"
    id="female"
    name="gender"
    value="Female">

<label for="female">Female</label>
```

Because both inputs use:

```html
name="gender"
```

the browser treats them as one radio group.

---

# 45. Select Dropdown

The `<select>` element creates a dropdown.

```html
<label for="city">Select City</label>

<select id="city" name="city">
    <option value="">--Choose City--</option>
    <option value="Jaipur">Jaipur</option>
    <option value="Delhi">Delhi</option>
    <option value="Mumbai">Mumbai</option>
    <option value="Bangalore">Bangalore</option>
</select>
```

---

# 46. Textarea

The `<textarea>` element is used for multi-line text.

```html
<label for="message">Message</label>

<textarea
    id="message"
    name="message"
    rows="4"
    cols="40"
    maxlength="200"
    placeholder="Write your feedback...">
</textarea>
```

### Important attributes

| Attribute | Purpose |
|---|---|
| `rows` | Visible number of rows |
| `cols` | Approximate visible width |
| `maxlength` | Maximum characters |
| `placeholder` | Hint text |
| `required` | Makes input mandatory |

---

# 47. Label Element

The `<label>` element provides a text label for a form control.

```html
<label for="email">Email</label>

<input
    type="email"
    id="email">
```

The `for` value should match the input's `id`.

This improves usability and accessibility.

---

# 48. Buttons

HTML provides different button types.

```html
<button type="submit">Submit</button>

<button type="reset">Reset</button>

<button type="button">Click Me</button>
```

## Submit

Submits the form.

```html
<button type="submit">Submit</button>
```

## Reset

Resets form controls to their initial values.

```html
<button type="reset">Reset</button>
```

## Button

A generic button that does not submit a form by itself.

```html
<button type="button">Click Me</button>
```

---

# 49. Form Example

```html
<form action="/register" method="post">

    <label for="name">Name:</label>

    <input
        type="text"
        id="name"
        name="name"
        required>

    <br><br>

    <label for="email">Email:</label>

    <input
        type="email"
        id="email"
        name="email"
        required>

    <br><br>

    <label for="password">Password:</label>

    <input
        type="password"
        id="password"
        name="password"
        minlength="8"
        required>

    <br><br>

    <label for="city">City:</label>

    <select
        id="city"
        name="city"
        required>

        <option value="">Choose City</option>
        <option value="Jaipur">Jaipur</option>
        <option value="Delhi">Delhi</option>
        <option value="Mumbai">Mumbai</option>

    </select>

    <br><br>

    <button type="submit">Register</button>
    <button type="reset">Reset</button>

</form>
```

---

# 50. Semantic HTML

Semantic HTML uses elements that clearly describe their purpose.

Semantic elements improve:

- Code readability
- Accessibility
- Document structure
- Search engine understanding
- Maintainability

Common semantic elements:

| Element | Purpose |
|---|---|
| `<header>` | Introductory/header content |
| `<nav>` | Navigation links |
| `<main>` | Main page content |
| `<section>` | Thematic grouping |
| `<article>` | Independent content |
| `<aside>` | Related/sidebar content |
| `<footer>` | Footer content |

---

# 51. `<header>`

The `<header>` element represents introductory content for a page or section.

```html
<header>
    <h1>My Website</h1>
    <p>Learn Web Development</p>
</header>
```

A page can contain more than one header when sections have their own introductory content.

---

# 52. `<nav>`

The `<nav>` element represents a major navigation section.

```html
<nav>
    <a href="/">Home</a>
    <a href="/about">About</a>
    <a href="/contact">Contact</a>
</nav>
```

---

# 53. `<main>`

The `<main>` element contains the primary content of the document.

```html
<main>
    <h1>HTML Course</h1>
    <p>Learn HTML step by step.</p>
</main>
```

A document should normally have one main content area.

---

# 54. `<section>`

The `<section>` element groups related content.

```html
<section>
    <h2>HTML Basics</h2>
    <p>Learn HTML fundamentals.</p>
</section>
```

Sections usually have a heading.

---

# 55. `<article>`

The `<article>` element represents independent content that could stand on its own.

Examples:

- Blog post
- News article
- Forum post
- Product review

```html
<article>
    <h2>What is HTML?</h2>
    <p>
        HTML is the standard markup language for web pages.
    </p>
</article>
```

---

# 56. `<aside>`

The `<aside>` element contains related content that is not the main content.

Examples:

- Sidebar
- Related articles
- Recent posts
- Advertisements
- Additional information

```html
<aside>
    <h3>Recent Posts</h3>
    <ul>
        <li>HTML Basics</li>
        <li>CSS Basics</li>
    </ul>
</aside>
```

---

# 57. `<footer>`

The `<footer>` element represents footer information for a page or section.

```html
<footer>
    <p>&copy; 2026 My Website</p>
</footer>
```

---

# 58. Complete Semantic Page

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta
        name="viewport"
        content="width=device-width, initial-scale=1.0">
    <title>Semantic HTML Page</title>
</head>

<body>

    <header>
        <h1>My Website</h1>

        <nav>
            <a href="#home">Home</a>
            <a href="#courses">Courses</a>
            <a href="#contact">Contact</a>
        </nav>
    </header>

    <main>

        <section id="home">
            <h2>Welcome</h2>
            <p>
                Welcome to our web development course.
            </p>
        </section>

        <section id="courses">

            <h2>Courses</h2>

            <article>
                <h3>HTML</h3>
                <p>
                    Learn how to structure web pages.
                </p>
            </article>

            <article>
                <h3>CSS</h3>
                <p>
                    Learn how to style web pages.
                </p>
            </article>

        </section>

        <aside>
            <h3>Latest Updates</h3>
            <p>New HTML course available.</p>
        </aside>

    </main>

    <footer id="contact">
        <p>&copy; 2026 My Website</p>
    </footer>

</body>
</html>
```

---

# 59. HTML Video

The `<video>` element embeds video content.

```html
<video
    width="600"
    controls>

    <source
        src="react-course.mp4"
        type="video/mp4">

    Your browser does not support video.
</video>
```

## Common video attributes

### `controls`

Displays browser-provided playback controls.

```html
<video controls>
```

### `autoplay`

Requests automatic playback.

```html
<video autoplay>
```

Autoplay may be restricted by browsers, especially when audio is enabled.

### `muted`

Starts the video muted.

```html
<video autoplay muted>
```

### `loop`

Repeats the video.

```html
<video controls loop>
```

### `poster`

Displays an image before playback.

```html
<video
    controls
    poster="thumbnail.jpg">
```

---

# 60. HTML Audio

The `<audio>` element embeds audio content.

```html
<audio controls>

    <source
        src="podcast.mp3"
        type="audio/mpeg">

    Your browser does not support audio.

</audio>
```

Common attributes:

- `controls`
- `autoplay`
- `muted`
- `loop`

Example:

```html
<audio controls loop>
    <source
        src="music.mp3"
        type="audio/mpeg">
</audio>
```

---

# 61. Multiple Media Sources

A browser may support one media format but not another.

Multiple `<source>` elements can be provided.

```html
<video controls>

    <source
        src="video.mp4"
        type="video/mp4">

    <source
        src="video.webm"
        type="video/webm">

    Your browser does not support video.
</video>
```

The browser can choose a compatible source.

---

# 62. HTML Accessibility Basics

Accessibility means making websites usable by as many people as possible, including people who use assistive technologies.

Important practices include:

### Use meaningful `alt` text

```html
<img
    src="student.jpg"
    alt="Student working on a laptop">
```

If an image is purely decorative, an empty `alt` can be appropriate:

```html
<img src="decoration.png" alt="">
```

### Use labels for form controls

```html
<label for="email">Email</label>
<input type="email" id="email">
```

### Use semantic HTML

Prefer:

```html
<header>
<nav>
<main>
<section>
<article>
<aside>
<footer>
```

when their meanings match the content.

### Use headings logically

```html
<h1>Web Development</h1>
<h2>HTML</h2>
<h2>CSS</h2>
<h2>JavaScript</h2>
```

---

# 63. HTML Global Attributes

Global attributes can be used on many HTML elements.

## `id`

Provides a unique identifier.

```html
<p id="intro">Welcome to HTML.</p>
```

An `id` can be used for:

- CSS
- JavaScript
- Fragment links

Example:

```html
<a href="#intro">Go to Introduction</a>
```

---

## `class`

Provides one or more class names.

```html
<p class="highlight">Important information.</p>
```

Classes are commonly used by CSS and JavaScript.

---

## `title`

Provides additional advisory information.

```html
<p title="This is additional information">
    Hover over this text.
</p>
```

---

## `style`

Adds inline CSS.

```html
<p style="color: blue;">
    Blue text
</p>
```

Inline CSS should generally be used sparingly in maintainable applications.

---

# 64. HTML Entities

HTML entities are used to represent reserved characters and special symbols.

Examples:

| Entity | Result |
|---|---|
| `&lt;` | `<` |
| `&gt;` | `>` |
| `&amp;` | `&` |
| `&quot;` | `"` |
| `&apos;` | `'` |
| `&copy;` | © |
| `&nbsp;` | Non-breaking space |

Example:

```html
<p>5 &lt; 10</p>
<p>&copy; 2026 My Website</p>
```

---

# 65. HTML File and Folder Structure

A simple HTML project can have this structure:

```text
my-website/
│
├── index.html
├── about.html
├── contact.html
│
├── images/
│   ├── logo.png
│   └── banner.jpg
│
├── css/
│   └── style.css
│
└── js/
    └── script.js
```

### `index.html`

Usually acts as the main page.

### `css/style.css`

Contains CSS styling.

### `js/script.js`

Contains JavaScript behavior.

### `images/`

Contains image assets.

---

# 66. Complete HTML Form Example

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta
        name="viewport"
        content="width=device-width, initial-scale=1.0">

    <title>Student Registration</title>
</head>

<body>

    <h1>Student Registration Form</h1>

    <form action="/register" method="post">

        <label for="name">Full Name:</label>

        <input
            type="text"
            id="name"
            name="name"
            placeholder="Enter your full name"
            minlength="3"
            maxlength="50"
            required>

        <br><br>

        <label for="email">Email:</label>

        <input
            type="email"
            id="email"
            name="email"
            placeholder="Enter your email"
            required>

        <br><br>

        <label for="password">Password:</label>

        <input
            type="password"
            id="password"
            name="password"
            minlength="8"
            required>

        <br><br>

        <label for="phone">Phone:</label>

        <input
            type="tel"
            id="phone"
            name="phone"
            placeholder="Enter phone number">

        <br><br>

        <label for="dob">Date of Birth:</label>

        <input
            type="date"
            id="dob"
            name="dob">

        <br><br>

        <p>Select Gender:</p>

        <input
            type="radio"
            id="male"
            name="gender"
            value="Male">

        <label for="male">Male</label>

        <input
            type="radio"
            id="female"
            name="gender"
            value="Female">

        <label for="female">Female</label>

        <br><br>

        <p>Select Skills:</p>

        <input
            type="checkbox"
            id="html"
            name="skills"
            value="HTML">

        <label for="html">HTML</label>

        <input
            type="checkbox"
            id="css"
            name="skills"
            value="CSS">

        <label for="css">CSS</label>

        <input
            type="checkbox"
            id="javascript"
            name="skills"
            value="JavaScript">

        <label for="javascript">JavaScript</label>

        <br><br>

        <label for="city">City:</label>

        <select id="city" name="city" required>
            <option value="">Choose City</option>
            <option value="Jaipur">Jaipur</option>
            <option value="Delhi">Delhi</option>
            <option value="Mumbai">Mumbai</option>
            <option value="Bangalore">Bangalore</option>
        </select>

        <br><br>

        <label for="message">Address:</label>

        <br>

        <textarea
            id="message"
            name="message"
            rows="5"
            cols="40"
            placeholder="Enter your address"
            maxlength="200"></textarea>

        <br><br>

        <label for="resume">Upload Resume:</label>

        <input
            type="file"
            id="resume"
            name="resume">

        <br><br>

        <button type="submit">
            Register
        </button>

        <button type="reset">
            Reset
        </button>

    </form>

</body>
</html>
```

---

# 67. Complete HTML Revision Table

| Topic | Important Elements/Attributes |
|---|---|
| Document | `<!DOCTYPE html>`, `<html>`, `<head>`, `<body>` |
| Metadata | `<meta>`, `<title>` |
| Headings | `<h1>` to `<h6>` |
| Paragraph | `<p>` |
| Container | `<div>` |
| Lists | `<ol>`, `<ul>`, `<dl>`, `<dt>`, `<dd>` |
| Formatting | `<b>`, `<strong>`, `<i>`, `<em>`, `<mark>` |
| Text | `<small>`, `<del>`, `<ins>`, `<sub>`, `<sup>` |
| Breaks | `<br>`, `<hr>` |
| Links | `<a>`, `href`, `target`, `download` |
| Images | `<img>`, `src`, `alt`, `width`, `height` |
| Tables | `<table>`, `<tr>`, `<th>`, `<td>` |
| Table Sections | `<thead>`, `<tbody>`, `<tfoot>` |
| Table Merge | `colspan`, `rowspan` |
| Forms | `<form>`, `<input>`, `<label>` |
| Selection | `<select>`, `<option>` |
| Text Area | `<textarea>` |
| Buttons | `<button>` |
| Semantic | `<header>`, `<nav>`, `<main>`, `<section>`, `<article>`, `<aside>`, `<footer>` |
| Media | `<video>`, `<audio>`, `<source>` |
| Global | `id`, `class`, `title`, `style` |

---

# 68. Important HTML Interview Questions

## 1. What is HTML?

HTML is the standard markup language used to structure content on web pages.

## 2. Is HTML a programming language?

No. HTML is a markup language, not a programming language.

## 3. What is HTML5?

HTML5 is the modern version of HTML that provides elements and APIs for modern web applications, including semantic elements and native media support.

## 4. What is `<!DOCTYPE html>`?

It tells the browser that the document should be interpreted using the HTML standard and, for HTML5 documents, uses the HTML5 doctype.

## 5. What is the difference between `<head>` and `<body>`?

`<head>` contains document metadata and resources, while `<body>` contains the page content intended for users.

## 6. What is the difference between `<div>` and semantic elements?

`<div>` is a generic container with no semantic meaning. Semantic elements such as `<article>` and `<nav>` communicate the purpose of their content.

## 7. What is the difference between `<b>` and `<strong>`?

`<b>` is primarily a stylistic offset, while `<strong>` indicates strong importance.

## 8. What is the difference between `<i>` and `<em>`?

`<i>` represents text stylistically offset from normal prose, while `<em>` represents semantic emphasis.

## 9. What is the purpose of `alt` in an image?

It provides alternative text for an image, which helps accessibility and is useful when the image cannot be displayed.

## 10. What is the difference between checkbox and radio button?

Checkboxes allow multiple selections. Radio buttons are normally used to select one option from a group.

## 11. Why is the same `name` used for radio buttons?

Radio buttons with the same `name` belong to the same group, allowing the user to select one option from that group.

## 12. What is `colspan`?

`colspan` allows a table cell to span multiple columns.

## 13. What is `rowspan`?

`rowspan` allows a table cell to span multiple rows.

## 14. What is the viewport meta tag?

It controls the viewport dimensions and initial scaling used by the browser, which is important for responsive layouts.

## 15. What is semantic HTML?

Semantic HTML uses elements that describe the meaning and purpose of content, such as `<header>`, `<nav>`, `<main>`, and `<article>`.

---

# 69. HTML Best Practices

1. Always use `<!DOCTYPE html>`.
2. Specify the document language with `lang`.
3. Use UTF-8 character encoding.
4. Include the viewport meta tag for responsive pages.
5. Use semantic HTML where appropriate.
6. Use meaningful heading hierarchy.
7. Use `alt` text for meaningful images.
8. Associate form controls with `<label>`.
9. Use descriptive link text.
10. Use valid nesting of elements.
11. Keep HTML structure readable and properly indented.
12. Separate structure, styling, and behavior into HTML, CSS, and JavaScript where practical.
13. Use `button` for actions and links for navigation.
14. Avoid using tables for page layout.
15. Prefer CSS for presentation instead of obsolete HTML presentation attributes.

---

# 70. Final HTML Learning Roadmap

A beginner can learn HTML in this order:

```text
1. HTML Introduction
       ↓
2. Document Structure
       ↓
3. Tags and Elements
       ↓
4. Headings and Paragraphs
       ↓
5. Text Formatting
       ↓
6. Lists
       ↓
7. Links
       ↓
8. Images
       ↓
9. Tables
       ↓
10. Forms
       ↓
11. Input Types
       ↓
12. Checkbox / Radio / Select / Textarea
       ↓
13. Semantic HTML
       ↓
14. Audio and Video
       ↓
15. Accessibility Basics
       ↓
16. Build HTML Projects
```

## Practice Projects

After completing these notes, practice with:

1. Personal Profile Page
2. Student Registration Form
3. Restaurant Menu Page
4. School Information Website
5. Portfolio Website
6. Product Table
7. Contact Us Page
8. Blog Article Page
9. Resume/CV Page
10. Course Landing Page

---

# 71. One-Page HTML Cheat Sheet

```html
<!DOCTYPE html>

<html lang="en">

<head>
    <meta charset="UTF-8">

    <meta
        name="viewport"
        content="width=device-width, initial-scale=1.0">

    <title>Page Title</title>
</head>

<body>

    <!-- Headings -->
    <h1>Heading</h1>
    <h2>Heading</h2>

    <!-- Paragraph -->
    <p>Paragraph</p>

    <!-- Link -->
    <a href="https://example.com">Visit</a>

    <!-- Image -->
    <img src="image.jpg" alt="Description">

    <!-- Lists -->
    <ul>
        <li>Item</li>
    </ul>

    <ol>
        <li>Item</li>
    </ol>

    <!-- Table -->
    <table>
        <thead>
            <tr>
                <th>Name</th>
            </tr>
        </thead>

        <tbody>
            <tr>
                <td>Rohit</td>
            </tr>
        </tbody>
    </table>

    <!-- Form -->
    <form>

        <label for="name">Name</label>

        <input
            type="text"
            id="name"
            name="name"
            required>

        <button type="submit">
            Submit
        </button>

    </form>

    <!-- Semantic Structure -->
    <header>Header</header>
    <nav>Navigation</nav>

    <main>

        <section>
            <article>
                Article Content
            </article>
        </section>

        <aside>
            Sidebar
        </aside>

    </main>

    <footer>Footer</footer>

</body>
</html>
```

---

# Conclusion

HTML is the foundation of web development. It defines the structure and meaning of web content.

The most important concepts to master are:

- HTML document structure
- Elements and attributes
- Headings and paragraphs
- Lists
- Links
- Images
- Tables
- Forms
- Input types
- Semantic HTML
- Audio and video
- Accessibility
- Good HTML structure and best practices

Once HTML fundamentals are strong, the next step is **CSS** for styling and then **JavaScript** for behavior and interactivity.
