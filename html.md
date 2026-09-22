HTML stands for Hyper Text Markup Language
HTML is the standard markup language for creating Web pages
HTML describes the structure of a Web page

<!DOCTYPE html> declaration defines that this document is an HTML5 document
<html> element is the root element of an HTML page
<head> element contains meta information about the HTML page
<title> element specifies a title for the HTML page
<body> element defines the document's body, and is a container for all the visible contents, such as headings, paragraphs, images, hyperlinks, tables, lists, etc.

lang="en"
This specifies the primary language of the page.

<meta charset="UTF-8">
UTF-8 supports almost every language and symbol, including:

<meta name="viewport" content="width=device-width, initial-scale=1.0">

width=device-width
Sets the page width equal to the device's screen width.

initial-scale=1.0
Sets the initial zoom level to 100%.



## Different browsers use different engines
Browser	       Rendering        Engine
Google           Chrome	         Blink
Microsoft         Edge	         Blink
Mozilla           Firefox	     Gecko
Apple             Safari	     WebKit

# HTML Headings Tag
HTML headings are defined with the <h1> to <h6> tags.


# HTML Paragraphs
HTML paragraphs are defined with the <p> tag:
 
HTML <div> Tag

The <div> (Division) tag is a block-level container used to group HTML elements together. It has no visual effect by itself, but it is commonly used with CSS for styling and JavaScript for manipulating groups of elements

# HTML Lists
HTML provides three main types of lists:

# Ordered List (<ol>) – Numbered list
<ol> <li>HTML</li> </ol>

# Unordered List (<ul>) – Bulleted list
<ul> <li>Apple</li> </ul>

# Description List (<dl>) – Terms and descriptions
Lists help organize information in a structured and readable format.
<dl> → Description List
<dt> → Description Term
<dd> → Description Details

<dl>
    <dt>HTML</dt>
    <dd>HyperText Markup Language</dd>
</dl>


<hr> — horizontal divider line
<br> — line break
<b> — bold (visual only)
<strong> —  important
<i> — italic (visual only)
<em> — italic + semantically emphasized
<mark> — highlighted (yellow background)
<small> — smaller font size
<del> — strikethrough (removed text)
<ins> — underline (added text)
<sub> — subscript (e.g., H₂O)
<sup> — superscript (e.g., x²)

# HTML Links
The Anchor (<a>) tag is used to create hyperlinks in HTML. Hyperlinks allow users to navigate between web pages, websites, email addresses, phone numbers, or different sections of the same page.

<a href="https://www.google.com">Visit Google</a>

# Types of Links

1. External Link
Links to another website.
<a href="https://www.github.com">GitHub</a>

Internal Link
Links to another page within the same website.
<a href="contact.html">Contact Us</a>

# Email Link
Opens the user's email application.
<a href="mailto:info@example.com">Email Us</a>

# Phone Link
Useful for mobile devices.
<a href="tel:+911234567890">Call Us</a>

# Download Link
Downloads a file instead of opening it.
<a href="resume.pdf" download>Download Resume</a>

# Absolute Path
An absolute path contains the complete URL.
<a href="https://react.dev">React Official Website</a>

# target Attribute
Open in Same Tab
<a href="about.html" target="_self">About</a>

Open in New Tab
<a href="https://react.dev" target="_blank">
    React Website
</a>


# Navigation Menu

A navigation menu helps users move between pages.
Basic Navigation
<nav>
    <a href="index.html">Home</a> |
    <a href="about.html">About</a> |
    <a href="services.html">Services</a> |
    <a href="contact.html">Contact</a>
</nav>


# Image Tag (<img>)
The <img> tag is used to display images on a webpage.
HTML images are defined with the <img> tag.
The source file (src), alternative text (alt), width, and height are provided as attributes:
 
<img src="images/logo.png" alt="Company Logo">


# HTML Tables

HTML tables are used to display data in rows and columns.
A table consists of:
<table> → Creates the table
<thead> → Table header
<tbody> → Table body
<tfoot> → Table footer
<tr> → Table row
<th> → Table header cell
<td> → Table data cell
colspan	Merges multiple columns into one cell
rowspan	Merges multiple rows into one cell

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

    <tfoot>
        <tr>
            <td colspan="3">Total Students: 2</td>
        </tr>
    </tfoot>
</table>

# HTML Input Types
The <input> element is used inside an HTML <form> to collect data from users.
HTML5 provides many input types, each designed for a specific kind of data.

placeholder	Shows hint text
maxlength	Maximum number of characters
minlength	Minimum number of characters
required	Makes the field mandatory
readonly	Prevents editing
disabled	Disables the field
<input
    type="text"
    placeholder="Username"
    maxlength="20"
    required>
<input type="radio" name="gender" value="Male"> Male
<input type="radio" name="gender" value="Female"> Female

text	Single-line text input
password	Password field (hidden characters)
email	Email address
number	Numeric input
tel	Telephone number
url	Website URL
search	Search box
date	Date picker
time	Time picker
datetime-local	Date and time picker
month	Month and year picker
week	Week picker
color	Color picker
range	Slider control
checkbox	Multiple selections
radio	Single selection from a group
file	File upload
hidden	Hidden value sent with form
image	Image as submit button
submit	Submit form
reset	Reset form
button	Generic clickable button



# HTML Form Controls: Checkboxes, Radio Buttons, Select Dropdowns, and Textarea
HTML provides different form controls to collect user input.
In this lesson, we'll cover:

Checkbox (<input type="checkbox">)
Radio Button (<input type="radio">)
Select Dropdown (<select>)
Textarea (<textarea>)

# Checkbox (type="checkbox")
A checkbox allows users to select one or more options.

<h3>Select Your Skills</h3>

<input type="checkbox" id="html" name="skills" value="HTML">
<label for="html">HTML</label>

<br>

<input type="checkbox" id="css" name="skills" value="CSS">
<label for="css">CSS</label>

<br>

<input type="checkbox" id="js" name="skills" value="JavaScript">
<label for="js">JavaScript</label>



# Radio Button (type="radio")
A radio button allows users to select only one option from a group.
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


<label for="city">Select City</label>

<select id="city" name="city">

    <option value="">--Choose City--</option>

    <option value="Jaipur">Jaipur</option>

    <option value="Delhi">Delhi</option>

    <option value="Mumbai">Mumbai</option>

    <option value="Bangalore">Bangalore</option>

</select>

# Select Dropdown (<select>)
The <select> element creates a dropdown list

<label for="city">Select City</label>
<select id="city" name="city">

    <option value="">--Choose City--</option>

    <option value="Jaipur">Jaipur</option>

    <option value="Delhi">Delhi</option>

    <option value="Mumbai">Mumbai</option>

    <option value="Bangalore">Bangalore</option>

</select>

# Textarea Attributes
<textarea
    rows="4"
    cols="40"
    maxlength="200"
    placeholder="Write your feedback...">
</textarea>


# HTML Semantic Elements

Semantic elements clearly describe the meaning and purpose of different parts of a web page. They make code easier to read, improve accessibility, and help search engines understand the page structure.
Common semantic elements include:

<header>	Contains the website title and introductory content
<nav>	Holds the navigation menu links
<main>	Contains the primary content of the page
<section>	Groups related blog articles
<article>	Represents an individual blog post
<aside>	Displays sidebar content such as recent posts and categories
<footer>	Contains copyright and footer information



# Video Tag (<video>)
The <video> tag embeds videos in HTML.
<video
    width="600"
    controls>

    <source src="react-course.mp4" type="video/mp4">

    Your browser does not support video.
</video>

# Audio Tag (<audio>)

The <audio> tag plays sound files.
<audio controls>

    <source
        src="podcast.mp3"
        type="audio/mpeg">

    Your browser does not support audio.

</audio>

