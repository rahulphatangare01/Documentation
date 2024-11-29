# CSS interview Questions

### Basic Questions

<details>
<summary>
1.<b> What is CSS?</b>
</summary>

CSS stands for **Cascading Style Sheets**. CSS is used to define styles for web pages, including the design, layout and variations in display for different devices and screen sizes. CSS was intended to allow web professionals to separate the content and structure of a website's code from the visual design.

CSS can be used for document text styling — for example changing the color and size of headings and links. It can be used to create layout — for example turning a single column of text into a layout with a main content area and a sidebar for related information. It can even be used for effects such as animation.

```jsx harmony

h1 {
  color: red;
  font-size: 5em;
}

p {
  color: black;
}
```

</details>

<details>
<summary>
2.<b> What is the use of css ruleset?</b>
</summary>

**CSS** is a rule or set of rules that describe the formatting (change of appearance) of individual elements on a web page. The rule consists of two parts: the selector and the next declaration block. The image below shows the structure (syntax) of the rule:

```jsx harmony
div {
  color: blue;
  text-align: justify;
}

```

- The first is always the **selector**, it tells the browser which element or elements of the web page will be styled.
- Next is the **declaration block**, which begins with the opening curly brace { and ends with the closing }, between the curly braces are specified formatting commands (declarations), which are used by the browser to stylize the selected selector element.
- Each **declaration** consists of two parts: the property and its value. The declaration must always end with a semicolon (;). You can omit the ; only at the end of the last declaration before the closing curly brace.
- A **property** is a formatting command that defines a specific style effect for an element. Each property has its own predefined set of values. After the property name, a colon is specified, which separates the property name from the valid value.

</details>

<details>
<summary>
3.<b> What are the possible ways to apply CSS styles to a web page? </b>
</summary>

There are three ways to apply CSS to HTML: Inline, internal, and external.

1. **Inline CSS**:

Inline CSS is specified directly in the opening tag of the element you want it to apply to. It is entered into the style attribute within HTML. This allows CSS properties on a "per tag" basis.

Example:

```jsx harmony
<p style="font-weight:bold;">Bold Font</p>
```

This CSS type is not really recommended, as each HTML tag needs to be styled individually. However, inline CSS in HTML can be useful in some situations. For example, in cases where you don't have access to CSS files or need to apply styles for a single element only.

2. **Internal CSS**:

Internal or Embedded, styles are used for the whole page. Inside the head element, the style tags surround all of the styles for the page.

Example:

````jsx harmony

<!DOCTYPE html>
<html>
  <head>
    <title>Internal CSS Example</title>
  <style>
    p {
        color: red;
    }

    a {
        color: blue;
    }
</style>
```

This CSS style is an effective method of styling a single page. However,
using this style for multiple pages is time-consuming as you need to put CSS rules to every page of your website


3. **External CSS**:
In external CSS rules are stored in a separate file. To refer to that file from the HTML page, add the link element (and its closing element within XHTML) to the head element. This CSS type is a more efficient method, especially for styling a large website. By editing one .css file, you can change your entire site at once.

style.css:

```jsx harmony
  p {
      color: red;
  }

  a {
      color: blue;
  }
````

```jsx harmony
<!DOCTYPE html>
<html>
<head>
    <title>External CSS Example</title>
    <link rel="stylesheet" type="text/css" href="style.css">
```

The link element in the example has three attributes. The first, rel, tells the browser the type of the target of the link. The second, type, tells the browser what type of stylesheet it is. And the third, href, tells the browser under which URL to find the stylesheet.

</details>

<details>
<summary>
4.<b> What are CSS filters?</b>
</summary>

The CSS filter property provides access to effects like blur or color shifting on an element's rendering before the element is displayed.

`filter: blur(20px) grayscale(20%) (example of multiple filters being used)`
`filter: sepia(1)`
`filter: saturate(8)`
`filter: hue-rotate(90deg)`
`filter: invert(.8)`
`filter: opacity(.2)`
`filter: brightness(3)`
`filter: contrast(4)`

</details>

<details>
<summary>
5.<b> What are CSS transformations?</b>
</summary>

The CSS transform property allows you to visually manipulate element, literally transforming their appearance.

`transform: translate(50px, 100px)` (there's also `translateX() and translateY()`)
`transform: rotate(20deg)`
`transform: scale(2, 3)` (there's also `scaleX() and scaleY()`)
`transform: skew(20deg, 10deg)` (there's also `skewX()` and `skewY()`)
`transform: matrix(1, -0.3, 0, 1, 0, 0)` (combines all the 2D transform methods into one)
These just made 2D transformations, but there are also 3D transformation methods:

`transform: rotateX(150deg)` (rotates an element around its X-axis at a given degree)
`transform: rotateY(130deg)` (rotates an element around its Y-axis at a given degree)
`transform: rotateX(90deg)` (rotates an element around its Z-axis at a given degree)

</details>

<details>
<summary>
6.<b> Who maintains the CSS specifications? What do you understand by W3C?</b>
</summary>

**W3C** stands for **World Wide Web Consortium**. The mission of the W3C is to lead the Web to its full potential by developing relevant protocols and guidelines.This is achieved primarily by creating and publishing Web standards. By adopting the Web standards created by the W3C, hardware manufacturers and software developers can ensure their equipment and programs work with the latest Web technologies. For example, most Web browsers incorporate several W3C standards, which allows them to interpret the latest versions of HTML and CSS code. When browsers conform to the W3C standards, it also helps Web pages appear consistent across different browsers.

</details>

<details>
<summary>
7.<b> Explain the difference between visibility: hidden; and display: none;? What are the pros and cons of using display:none?</b>
</summary>

- **visibility**: hidden simply hides the element but it will occupy space and affect the layout of the document.

- **display**: none removes the element from the normal layout flow (causes DOM reflow). It will not affect the layout of the document nor occupy space.
</details>

<details>
<summary>
8.<b> What is the purpose of the z-index and how is it used?</b>
</summary>

The `z-index` helps specify the stack order of positioned elements that may overlap one another. The `z-index` default value is zero, and can take on either a positive or negative number.

An element with a higher `z-index` is always stacked above than a lower index.

`z-index` can take the following values:

1. **Auto**: Sets the stack order equal to its parents.
2. **Number**: Orders the stack order.
3. **Initial**: Sets this property to its default value (0).
4. **Inherit**: Inherits this property from its parent element.

</details>

<details>
<summary>
9.<b> How does z-index relate to positioning? Describe z-index and how stacking context is formed?</b>
</summary>

The `z-index` property specifies the stack order of elements. An element with a higher `z-index` stack order is always rendered in front of an element with a lower z-index stack order on the screen. `z-index` only works on positioned elements `position: absolute`, p`osition: relative`, or `position: fixed`. The default stack order of non-positioned elements is their order in the document.

</details>

<details>
<summary>
10.<b> Which one would you prefer among px, em % or pt and why?</b>
</summary>

it depends on what you are trying to do.

- **px** gives fine grained control and maintains alignment because 1 px or multiple of 1 px is guaranteed to look sharp. px is not cascade, this means if parent font-size is 20px and child 16px. child would be 16px.

- **em** maintains relative size. you can have responsive fonts. em is the width of the letter 'm' in the selected typeface. However, this concept is tricky. 1em is equal to the current font-size of the element or the browser default. if u sent font-size to 16px then 1em = 16px. The common practice is to set default body font-size to 62.5% (equal to 10px). em is cascade

- **%** sets font-size relative to the font size of the body. Hence, you have to set font-size of the body to a reasonable size. this is easy to use and does cascade. for example, if parent font-size is 20px and child font-size is 50%. child would be 10px.

- **pt**(points) are traditionally used in print. 1pt = 1/72 inch and it is fixed-size unit.

</details>

<details>
<summary>
11.<b> What are CSS transitions?</b>
</summary>

They allow elements to change values over a specified duration, animating the property changes, rather than having them occur immediately.

```jsx harmony

div {
  transition: background-color 0.5s ease;
  background-color: orange;
}

div:hover {
  background-color: green;
}
```

Here's an overview of the syntax:

```jsx harmony
/* Apply to 1 property */
/* property name | duration */
transition: margin-left 4s;

/* property name | duration | delay */
transition: margin-left 4s 1s;

/* property name | duration | timing function | delay */
transition: margin-left 4s ease-in-out 1s;

/* Apply to 2 properties */
transition: margin-left 4s, color 1s;

/* Apply to all changed properties */
transition: all 0.5s ease-out;
```

Most common timing functions are ease, linear, ease-in, ease-out, ease-in-out, step-start, step-end. Check out this link for more info on timing functions.

</details>

<details>
<summary>
12.<b> What is specificity? How do you calculate specificity?</b>
</summary>

The different weight of selectors is usually the reason why your CSS rules don't apply to some elements, although you think they should have. I

- There are four distinct categories which define the specificity level of a given selector: inline styles, IDs, classes+attributes and elements.
- When selectors have an equal specificity value, the latest rule is the one that counts.
- Rules with more specific selectors have a greater specificity.
- The last rule defined overrides any previous, conflicting rules.
- You should always try to use IDs to increase the specificity.
- A class selector beats any number of element selectors.
</details>

<details>
<summary>
13.<b> What are the main display values an element can take?</b>
</summary>

- **Inline**
  **display**: inline is the default value for all elements. Think of elements like span, em, or b and how wrapping text in those elements within a string of text doesn't break the flow of the text. An inline element will accept margin and padding, but the element still sits inline as you might expect. Margin and padding will only push other elements horizontally away, not vertically. An inline element will not accept height and width, it will just ignore them.

**Inline Block**
**An element set to display**: inline-block is very similar to inline in that it will set inline with the natural flow of text (on the "baseline"). The difference is that you are now able to set a width and height which will be respected.

**Block**
A block-level element (display: block) starts on a new line and stretches out to the left and right as far as it can (just like a div or p do).

</details>

<details>
<summary>
14.<b> What are the different position values an element can take?</b>
</summary>

**Static**
`position: static` is the default value. An element with position: static is not positioned in any special way.

**Relative**
`position: relative` behaves the same as static unless you add some extra properties. Setting the `top`, `right`, `bottom` and `left` properties of a relatively-positioned element will cause it to be adjusted away from its normal position. This means that the new position (determined by `top`, `right`, `bottom`, `left`) is relative to the original (static) position.

```jsx harmony
#something {
  position: relative; /* i'm gonna move this element from its original spot */
  top: -10px; /* push this 10px up to the top */
  left: 20px; /* push this 20px to the right */
}

```

**Fixed**
A fixed element is positioned relative to the viewport, which means it always stays in the same place even if the page is scrolled (think of a modal window). As with relative, the `top`, `right`, `bottom`, and `left` properties are used.

**Absolute**
`position: absolute` behaves like fixed except relative to the nearest positioned ancestor instead of relative to the viewport. If an absolutely-positioned element has no positioned ancestors, it uses the document body, and still moves along with page scrolling. Remember, a "positioned" element is one whose position is anything except static.

</details>

<details>
<summary>
15.<b> How does z-index work?</b>
</summary>

The z-index property in CSS controls the vertical stacking order of elements that overlap. As in, which one appears as if it is physically closer to you. `z-index` only effects elements that have a position value other than static (the default).

Elements can overlap for a variety of reasons, for instance relative positioning has nudged it over something else. Negative margin has pulled the element over another. Absolutely positioned elements overlap each other. All sorts of reasons. Without any z-index value, elements stack in the order that they appear in the DOM (the lowest one down at the same hierarchy level appears on top). Elements with non-static positioning will always appear on top of elements with default static positioning.

</details>

<details>
<summary>
16.<b> What does margin: auto do?</b>
</summary>

ou can set the `left` and `right` margins to `auto` to horizontally center an element within its container.

</details>

<details>
<summary>
17.<b> How does floating elements work?</b>
</summary>

Our HTML is bound by some rules, in particular, the normal flow. In the normal flow, each block element (`div`, `p`, `h1`, etc.) stacks on top of each other vertically, from the top of the viewport down. Floated elements are first laid out according to the normal flow, then taken out of the normal flow and sent as far to the right or left (depending on which value is applied) of the parent element. In other words, they go from stacking on top of each other to sitting next to each other, given that there is enough room in the parent element for each floated element to sit.

Notice that depending on the size of the container (parent), the floated (children) elements will drop to a second row when there is not enough room for all of them to sit side by side.

</details>

<details>
<summary>
18.<b> What does the clear property do?</b>
</summary>

The clear property has five values available: `left`, `right`, `both`, `inherit`, and `none`.

- Assigning a value of `left` says the top edge of this element must sit below any element that has the `float: left` property applied to it.
- The same concept applies for the `right` value: the element must sit beneath any element that has the `float: right` property applied to it.
- Using the both value tells our element that its top edge must sit below any element floated either left or right. The inherit value takes on the clear property from its parent element, while the default value none behaves as you would expect.

This is an immensely powerful property; as you can see, it helps bring our non-floated elements back into the normal flow, a behavior that we tend to expect by default.

</details>

<details>
<summary>
19.<b> Why is the float property important? What other alternative do we have for bulding grid layouts?</b>
</summary>

The CSS float property allows you to incorporate table-like columns in an HTML layout without the use of tables. If it were not for the CSS float property, CSS layouts would not be possible except using absolute and relative positioning — which would be messy and would make the layout unmaintainable.

</details>

<details>
<summary>
20.<b> How to fix the collapsed parent effect?</b>
</summary>

One of the most common symptoms of float-heavy layouts is the "collapsing parent". This is demonstrated in the example below:

Notice that the bottom of the floated image appears outside its parent. The parent does not fully expand to hold the floated image. This is caused because the floated element is out of the flow in relation to other block elements, so all block elements will render as if the floated element is not even there. This is not a CSS bug, it's in fact in line with CSS specifications.

The easiest way to fix this problem is to float the containing parent element. Now the container expands to fit all the child elements. But unfortunately this fix will only work in a limited number of circumstances, since floating the parent may have undesirable effects on your layout.

Another solution would be to simply add an extra element at the very bottom and "clear" it.

```jsx harmony
<div id="container">
  <img src="lifesaver.jpg" alt="Lifesaver" />
  <p>Pellentesque habitant morbi tristique senectus...</p>
  <div class="clearfix"></div>
</div>
```

```jsx harmony
.clearfix {
  clear: both;
}
```

By far the best, and easiest solution to resolve the collapsing parent issue is to add either overflow: hidden or overflow: auto to the parent element. This is clean, easy to maintain, works in almost all browsers (but IE6) and does not add extra markup.

</details>

### Advanced Questions

<details>
<summary>
21.<b> How do you include CSS in your HTML document?</b>
</summary>

There are `four primary methods` to incorporate CSS in an HTML document, each presenting unique advantages and use cases.

**Methods of CSS Integration**

1. **Inline Style**: Directly insert CSS rules within HTML tags.
2. **Embedded Style**: Encompass CSS within the HTML document's <head> section.
3. **External Style Sheet**: Create a standalone .css file to be referenced in the HTML.
4. **Imported Style Sheet**: Employ @import within a <style> tag or a CSS file to bring in other CSS files.

   **Key Considerations**

   **Specificity**: The degree of influence a selector has over others.
   **Reuse**: The potential to apply the same CSS rules across multiple elements.
   **Maintainability**: The ease with which one can update and manage the CSS.

   **Best Practices**
   **Ideally, Choose a Single Method**: Mixing techniques can complicate maintenance and understanding.
   **Inline Styles for Quick Changes**: Useful when rapid style modifications are necessary.

   `HTML Code Example: Methods Northwind.CSS`
   Here is the HTML code:

```jsx harmony
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link rel="stylesheet" href="mystyle.css">
    <title>Document</title>
</head>
    <style>
        h1, h2, p {
            color: green;
        }

        div {
            border: 1px solid black;
        }
    </style>
<body>
    <h1>My Header</h1>
    <p>Hello, World!</p>
</body>
</html>
```

</details>

<details>
<summary>
22.<b> Can you explain the difference between class and ID selectors?</b>
</summary>

**Class** and **ID** selectors in CSS serve distinct roles and have limitations in their applicability.

**Selectivity and Applicability**
**Class Selector** (`.classname{...}`): Matches multiple elements that share the same class attribute. These elements can belong to various HTML tags (e.g., <div>, <p>).

**ID Selector** (#idName{...}): Identifies a single unique element based on its unique ID attribute. While it's still possible to style multiple elements with the same ID, best practices mandate unique IDs for effective CSS usage.

**Efficiency and Performance**

**Class Selector**: Generally faster to compute than ID selectors in modern browsers, particularly when applied to a large number of elements.

**ID Selector**: Formerly superior in terms of speed, contemporary browsers mitigate this difference.

**Common Use Cases**

**Class Selector**: Ideal for styling groups of elements based on shared attributes or type.

**ID Selector**: Typically reserved for unique elements that require highly specific styling or JavaScript manipulation. While it's valid to use an ID for styling, as stated in the HTML5 specification, it's generally more maintainable to reserve the use of IDs for uniquely identifiable elements and use classes for styling.

**Code Example: Class and ID Selectors**
Here is the HTML code:

```jsx harmony
<html>
  <head>
    <link rel="stylesheet" type="text/css" href="styles.css" />
  </head>
  <body>
    <div class="content">Content 1</div>
    <div class="content">Content 2</div>
    <div class="content" id="uniqueContent">
      Special Content
    </div>
  </body>
</html>
```

Here is the CSS code:

```jsx harmony
/* Styles applied using class selectors */
.content { color: blue; }

/* Styles applied using ID selector */
#uniqueContent { color: red; }
```

</details>

<details>
<summary>
23.<b> What are pseudo-classes in CSS?</b>
</summary>

`Pseudo-classes` are special keywords in CSS that allow you to apply styles to elements based not only on their state or position in the document tree but also on user interaction.

**Categories of Pseudo-Classes**

**Dynamic Pseudo-classes**: These appear as the user interacts with an element. For instance, :hover is activated when the user hovers the cursor over an element.

**User-action Pseudo-classes**: These capture actions taken by the user, such as :checked for input elements that are selected.

**Relationship Pseudo-classes**: These pertain to the document tree's hierarchical structure, like :first-child for an element that's the first child within its parent.

**Language Pseudo-Classes**: These cater to elements displayed in specific languages, for example :dir().

**Input Control Pseudo-Classes**: Designed specifically for interactive elements, these pseudo-classes style form controls like buttons, inputs, and text areas. Some examples are :default, :valid, :invalid, and :optional.

**Enabled and Disabled Pseudo-classes**: These are self-explanatory; they alter the style of elements based on whether they're enabled or disabled. Examples include :enabled and :disabled.

</details>

<details>
<summary>
24.<b> Describe how to implement a CSS reset and why it is useful.</b>
</summary>

A `CSS reset` is a set of styles intended to reduce browser inconsistencies in elements such as margins, paddings, and various typical style defaults.

**Benefits of CSS Reset**

**Consistent Starting Point**: Eliminates default styling differences across browsers, making the design process more predictable.
**Consistent Box Model**: Ensures uniform calculations of element sizing (e.g., widths and heights) to prevent unexpected layout shifts.
**Want Only Custom Styles**: It's especially useful if you intend to start from a blank slate and apply your own bespoke styles.

**The Code**
For HTML:

```jsx harmony
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <link href="styles.css" rel="stylesheet">
  <title>Document</title>
</head>
<body>
  <h1>Hello, CSS Reset!</h1>
</body>
</html>
```

And for CSS, here is a simple normalize.css-based reset:

```jsx harmony
/* reset.css */
/*! normalize.css v8.0.1 | MIT License | github.com/necolas/normalize.css */
h1 {
    font-size: 2em;
    margin: 0.67em 0;
}
```

</details>

<details>
<summary>
25.<b> How do you select elements by attribute in CSS?</b>
</summary>

While programming in CSS, you can leverage `attribute selectors` to define rules based on the presence or value of specific HTML attributes.

**Benefits**

Using attribute selectors has multiple advantages, such as:

**Versatility**: They cater to a wide range of scenarios.
**Simplicity**: They are easy to use.
**Consistency**: They're a part of a standard set of CSS selectors.

**Variations**

You can utilize attribute selectors in three distinct ways:

**Exact Match**: [] selects an exact attribute value.
**Value Starts With**: [^] targets attributes with specified starting values.
**Case Insensitive**: Selectors are usually case-sensitive, but by using i, you can make them case-insensitive.
Here is the CSS code snippet:

```jsx harmony
/* Exact Match */
[class="important"] {
  color: red;
}

/* Value Starts With */
[href^="https"] {
  color: green;
}

/* Case Insensitive */
[alt="home" i] {
  background: url('home-icon.png');
}
```

In the example above,

- `[class="important"]` selects all elements with the exact class attribute set to "important".
- `[href^="https"]` will style all anchor links with an href attribute that starts with "https".
- `[alt="home" i]` targets the alt attribute with a value of "home" in a case-insensitive manner.

</details>

<details>
<summary>
26.<b> What is a pseudo-element, and what are they used for?</b>
</summary>

`Pseudo-elements` are virtual elements that give developers the power to style parts of an HTML document that don't correspond to actual HTML elements. Essentially, they let you apply styles to specific parts of an element without the need for extra HTML markup.

Commonly used `pseudo-elements` include `::before` and `::after` which let developers insert content before or after an element, respectively.

**Key Features**

- **Automatic Insertion**: These pseudo-elements can add content continuously without requiring manual code changes.
- **Dynamic Content**: With generated content and styles, pseudo-elements can adapt based on the specific conditions.
- **Custom Styling**: Pseudo-elements enable developers to style parts of an element differently than the rest.

**Practical Applications**

1. **Indicating External Links**
   **Link**: Indicating content that opens an external website.
   **Implementation**: Visual or textual cues like arrows or "External Link" next to anchor elements.

2. **Specialized Numbers and Letters**
   **Link**: Styling a single letter or number within a text block.
   **Implementation**: Especially useful in design, for instance, highlighting the first letter of a paragraph with a larger font size.

3. **Responsive Backgrounds**
   **Link**: Apply background images or colors specific to certain parts of an element for various screen sizes.
   **Implementation**: Use media queries within the pseudo-element for specific screen sizes.
4. **Code Blocks and Blockquotes**
   **Link**: Add decorative elements preceding and following code blocks and blockquote elements.
   **Implementation**: Help highlight code samples or visually delineate long blockquote sections.

5. **Custom Radio Buttons and Checkboxes**
   **Link**: Rework default styling for radio buttons and checkboxes for a more customized look.
   **Implementation**: Use ::before or ::after with content property to replace default appearance.
6. **Clear Floats**
   **Link**: Overcome challenges in parent containers not respecting the height of floated child elements and collapsing.
   **Implementation**: Create an element with ::after pseudo-element where the content clears the floats.
7. **Hacks for Older Browsers**
   **Link**: Sometimes, especially with prior versions of Internet Explorer, using pseudo-elements proves crucial for achieving desired stylings.
   **Implementation**: Useful for applying specifically crafted styles that wouldn't work properly on older browsers without this technique.

</details>

<details>
<summary>
27.<b> Explain the difference between the child combinator and the descendant combinator.</b>
</summary>

The `child combinator` (>) and the` descendant combinator` (~) both serve to target HTML elements with CSS. However, they `operate` in different ways.

**Distinct Characteristics**

- Child Combinator >: Selects an HTML element that is a direct child of another element.
- Descendant Combinator ~: Matches an HTML element that is a descendant (direct or indirect child) of another specified element.

Code Example
Here is the CSS:

```jsx harmony
/* target direct children of the parent element */
nav > ul > li {
  color: red;
}

/* target any descendant list items under nav */
nav li {
  color: blue;
}
```

Here is the HTML:

```jsx harmony
<nav>
  <ul>
    <li>Direct Child</li> <!-- This is red -->
    <li>
      Nested Child <!-- This is blue -->
      <ul>
        <li>Nested List Item</li> <!-- This is blue -->
      </ul>
    </li>
  </ul>
</nav>
```

**Best Practices for Combinator Use**

1. **Specificity of Selection**: Implement the child combinator > when you want to target a specific, direct child of an element.

2. **Minimize Global Targeting**: Utilize the descendant combinator cautiously as it has the potential for global targeting. It's often a good habit to opt for more specific selectors.
3. **Balance Styling and Performance**: As a rule of thumb, more specific selectors could improve rendering speed. Use combinators with a balanced approach keeping in mind both specificity and performance needs.

</details>

<details>
<summary>
28.<b> How would you select all direct children elements of a particular type?</b>
</summary>

To **select all direct children** of a specific type in CSS, you can use the > child selector combined with the desired element to build the selector.

For example, to select all the direct children that are `<li>` elements within an `<ul>` element, you would use the following CSS:

```jsx harmony
ul > li {
  /* Styles here */
}
```

</details>

<details>
<summary>
29.<b>  What are the universal selector and the sibling combinator, and when would you use them?</b>
</summary>

The `Universal Selector` (the asterisk, \*) is a powerful tool that enables you to target every element within a specified container. While it's a straightforward selector, its implications can be broad.

**When to Use**: You might want to normalize or reset specific CSS properties (resetting padding, margin, etc.) across all elements within a container or the entire document. The Universal Selector effectively achieves this.

**Best Practices**: Overuse of the Universal Selector can lead to performance issues and unexpected style side effects. Keep its use concise and well-defined.

**When To Use Sibling Combinator**
The Sibling Combinator (+) in CSS targets elements that are immediately preceded by a specified element. Unlike child (>) or descendant (whitespace) selectors, the sibling combinator allows direct sibling targeting.

**When to Use**: For DOM structures where direct sibling relationships are key, such as tabbed content or multi-step forms.

**Best Practices**: While direct sibling targeting is useful, ensure it's the most efficient method for your objective. Overreliance can lead to inflexible CSS and HTML structures.

`Code Example: Universal Selector`
Here is the CSS:

```jsx harmony
/* Remove margins, paddings on all elements within the container */
.containers > * {
    margin: 0;
    padding: 0;
}
```

The HTML:

```jsx harmony
<div class="container">
  <p>Paragraph 1</p>
  <ul>
    <li>Item 1</li>
    <li>Item 2</li>
  </ul>
</div>
```

`Code Example: Sibling Combinator`
Here is the CSS:

```jsx harmony
/* Style the direct sibling anchor tag when a list item is hovered */
ul li:hover + a {
    color: red;
}
```

The HTML:

```jsx harmony
<ul>
  <li>Item 1</li>
  <li>Item 2</li>
  <li>
    <a href="#">Link</a>
  </li>
</ul>
```

**Case Study: Practical Applications**
Let us take a real-world example.

**Resetting Margins and Paddings**
In this scenario, you have a parent container and you want to remove the default margins and paddings from all its child elements.

The `Universal Selector` can accomplish this:

Here is the CSS:

```jsx harmony
.container > * {
    margin: 0;
    padding: 0;
}
```

The HTML:

```jsx harmony
<div class="container">
  <p>Paragraph 1</p>
  <p>Paragraph 2</p>
</div>
```

</details>

<details>
<summary>
30.<b>What is the CSS Box Model?</b>
</summary>

The Box Model is the foundational concept in CSS that describes the structure of an HTML element. It encompasses four key components: content, padding, border, and margin.

**Box Model Components**
**Content**: The actual element content, such as text, images, or other visual or interactive elements.
**Padding**: Clears an area around the element's content, inside the border. The padding is transparent and doesn't have a background color or border.
**Border**: A solid line that defines the boundary of the padding area.
**Margin**: Clears an area around the element's border, outside any defined background or border.
Visual Representation

**Key Attributes**
**Height & Width**: Element dimensions are determined by the sum of content width/height, and any padding, border, or margin added to it.
**Border**: Specifies the size, style, and color of the border surrounding the content and padding.
**Margin**: Defines the clearance between adjacent elements.

Code Example: Box Model
Here is the HTML code:

```jsx harmony
<div id="boxModelExample">This is an example of text within the Box Model.</div>
```

Here is the CSS code:

```jsx harmony

#boxModelExample {
    border: 5px solid red;
    padding: 20px;
    margin: 20px;
}
```

**Margins**

`Auto Margins`
When the surrounding container has a defined width, horizontal margins set to "auto" equally distribute the remaining horizontal space on both sides of the element, centering it within the container.

```jsx harmony

#autoMarginExample {
    width: 50%;
    margin-left: auto;
    margin-right: auto;
}
```

**Parent and Child Element Interplay**

Box Sizing
By default, the width of an element does not include padding or border. CSS can alter this behavior using the box-sizing property:

**Content-Box** (default): The element's specified width and height are calculated excluding padding and border. When you change the width or height of an element using CSS, this is the model being used.
**Border-Box**: The width and height comprise the content, padding, and border, avoiding the expansion of the box when adding padding or border to an element.
This distinction aids in layout control and ensures uniformity.

```jsx harmony
#borderBoxExample {
    box-sizing: border-box;
}
```

</details>

<details>
<summary>
31.<b></b>
</summary>
</details>

<details>
<summary>
32.<b></b>
</summary>
</details>

<details>
<summary>
33.<b></b>
</summary>
</details>

<details>
<summary>
34.<b></b>
</summary>
</details>

<details>
<summary>
35.<b></b>
</summary>
</details>

<details>
<summary>
36.<b></b>
</summary>
</details>

<details>
<summary>
37.<b></b>
</summary>
</details>

<details>
<summary>
38.<b></b>
</summary>
</details>

<details>
<summary>
39.<b></b>
</summary>
</details>

<details>
<summary>
40.<b></b>
</summary>
</details>

<details>
<summary>
41.<b></b>
</summary>
</details>

<details>
<summary>
42.<b></b>
</summary>
</details>

<details>
<summary>
43.<b></b>
</summary>
</details>

<details>
<summary>
44.<b></b>
</summary>
</details>

<details>
<summary>
45.<b></b>
</summary>
</details>

<details>
<summary>
46.<b></b>
</summary>
</details>

<details>
<summary>
47.<b></b>
</summary>
</details>

<details>
<summary>
48.<b></b>
</summary>
</details>

<details>
<summary>
49.<b></b>
</summary>
</details>

<details>
<summary>
50.<b></b>
</summary>
</details>

<details>
<summary>
51.<b></b>
</summary>
</details>

<details>
<summary>
52.<b></b>
</summary>
</details>

<details>
<summary>
53.<b></b>
</summary>
</details>

<details>
<summary>
54.<b></b>
</summary>
</details>

<details>
<summary>
55.<b></b>
</summary>
</details>

<details>
<summary>
56.<b></b>
</summary>
</details>

<details>
<summary>
57.<b></b>
</summary>
</details>

<details>
<summary>
58.<b></b>
</summary>
</details>

<details>
<summary>
59.<b></b>
</summary>
</details>

<details>
<summary>
60.<b></b>
</summary>
</details>

<details>
<summary>
61.<b></b>
</summary>
</details>

<details>
<summary>
62.<b></b>
</summary>
</details>

<details>
<summary>
63.<b></b>
</summary>
</details>

<details>
<summary>
64.<b></b>
</summary>
</details>

<details>
<summary>
65.<b></b>
</summary>
</details>

<details>
<summary>
66.<b></b>
</summary>
</details>

<details>
<summary>
67.<b></b>
</summary>
</details>

<details>
<summary>
68.<b></b>
</summary>
</details>

<details>
<summary>
69.<b></b>
</summary>
</details>

<details>
<summary>
70.<b></b>
</summary>
</details>

<details>
<summary>
71.<b></b>
</summary>
</details>

<details>
<summary>
72.<b></b>
</summary>
</details>

<details>
<summary>
73.<b></b>
</summary>
</details>

<details>
<summary>
74.<b></b>
</summary>
</details>

<details>
<summary>
75.<b></b>
</summary>
</details>

<details>
<summary>
76.<b></b>
</summary>
</details>

<details>
<summary>
77.<b></b>
</summary>
</details>

<details>
<summary>
78.<b></b>
</summary>
</details>

<details>
<summary>
79.<b></b>
</summary>
</details>

<details>
<summary>
80.<b></b>
</summary>
</details>

<details>
<summary>
81.<b></b>
</summary>
</details>

<details>
<summary>
82.<b></b>
</summary>
</details>

<details>
<summary>
83.<b></b>
</summary>
</details>

<details>
<summary>
84.<b></b>
</summary>
</details>

<details>
<summary>
85.<b></b>
</summary>
</details>

<details>
<summary>
86.<b></b>
</summary>
</details>

<details>
<summary>
87.<b></b>
</summary>
</details>

<details>
<summary>
88.<b></b>
</summary>
</details>

<details>
<summary>
89.<b></b>
</summary>
</details>

<details>
<summary>
90.<b></b>
</summary>
</details>

<details>
<summary>
91.<b></b>
</summary>
</details>

<details>
<summary>
92.<b></b>
</summary>
</details>

<details>
<summary>
93.<b></b>
</summary>
</details>

<details>
<summary>
94.<b></b>
</summary>
</details>

<details>
<summary>
95.<b></b>
</summary>
</details>

<details>
<summary>
96.<b></b>
</summary>
</details>

<details>
<summary>
97.<b></b>
</summary>
</details>

<details>
<summary>
98.<b></b>
</summary>
</details>

<details>
<summary>
99.<b></b>
</summary>
</details>

<details>
<summary>
100.<b></b>
</summary>
</details>
```
