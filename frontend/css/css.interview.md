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
6.<b></b>
</summary>
</details>

<details>
<summary>
7.<b></b>
</summary>
</details>

<details>
<summary>
8.<b></b>
</summary>
</details>

<details>
<summary>
9.<b></b>
</summary>
</details>

<details>
<summary>
10.<b></b>
</summary>
</details>

<details>
<summary>
11.<b></b>
</summary>
</details>

<details>
<summary>
12.<b></b>
</summary>
</details>

<details>
<summary>
13.<b></b>
</summary>
</details>

<details>
<summary>
14.<b></b>
</summary>
</details>

<details>
<summary>
15.<b></b>
</summary>
</details>

<details>
<summary>
16.<b></b>
</summary>
</details>

<details>
<summary>
17.<b></b>
</summary>
</details>

<details>
<summary>
18.<b></b>
</summary>
</details>

<details>
<summary>
19.<b></b>
</summary>
</details>

<details>
<summary>
20.<b></b>
</summary>
</details>

<details>
<summary>
21.<b></b>
</summary>
</details>

<details>
<summary>
22.<b></b>
</summary>
</details>

<details>
<summary>
23.<b></b>
</summary>
</details>

<details>
<summary>
24.<b></b>
</summary>
</details>

<details>
<summary>
25.<b></b>
</summary>
</details>

<details>
<summary>
26.<b></b>
</summary>
</details>

<details>
<summary>
27.<b></b>
</summary>
</details>

<details>
<summary>
28.<b></b>
</summary>
</details>

<details>
<summary>
29.<b></b>
</summary>
</details>

<details>
<summary>
30.<b></b>
</summary>
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
