# Applied Accessibility

**"Accessibility"** generally means having web content and a user interface that can be understood, navigated, and interacted with by a broad audience. This includes people with visual, auditory, mobility, or cognitive disabilities.

Here are three general concepts this section will explore throughout the following documentation:

1. have well-organized code that uses appropriate markup
1. ensure text alternatives exist for non-text and visual content
1. create an easily-navigated page that's keyboard-friendly

A great resource for projects going forward is the _**W3 Consortium's Web Content Accessibility Guidelines**_ (WCAG). They set the international standard for accessibility and provide a number of criteria you can use to check your work.

#### Official ARIA documentation

[Here is the link](https://www.w3.org/TR/wai-aria-practices-1.1/)

### 1. Add a Text Alternative to Images for Visually Impaired Accessibility

_**Alt**_ text describes the <ins>content of the image and provides a text-alternative for it.</ins> This helps in cases where the image fails to load or can't be seen by a user. It's also used by search engines to understand what an image contains to include it in search results. Here's an example:

`<img src="importantLogo.jpeg" alt="Company logo">`

You should <ins>always</ins> include an _**alt**_ attribute on your image. Per HTML5 specification, this is now considered mandatory.

### 2. Know When Alt Text Should be Left Blank

In situations when an image is already explained with text content, or does not add meaning to a page, the _**img**_ still needs an alt attribute, but it can be set to an <ins>empty string.</ins> Here's an example:

`<img src="visualDecoration.jpeg" alt="">`

For images with a caption, you may still want to include _**alt**_ text, since it helps search engines catalog the content of the image.

### 3. Use Headings to Show Hierarchical Relationships of ContentPassed

Each page should always have <ins>**one (and only one)</ins> h1** element, which is the main subject of your content. This and the other headings are used in part by search engines to understand the <ins>topic of the page.</ins>

```
<h1>How to Become a Ninja</h1>
<main>
  <h2>Learn the Art of Moving Stealthily</h2>
  <h3>How to Hide in Plain Sight</h3>
  <h3>How to Climb a Wall</h3>
</main>
```

### 3.Jump Straight to the Content Using the main Element

The _**main**_ element is used to wrap <ins>the main content</ins>, and there should be <ins>**only one per page.**</ins> It's meant to surround the information that's related to the central topic of your page.
It's not meant to include items that repeat across pages, like navigation links or banners.

The _**main**_ tag also has an <ins>embedded landmark feature</ins> that assistive technology can use to quickly navigate to the main content.

```
<header>
  <h1>Weapons of the Ninja</h1>
</header>
  <main>
  </main>

<footer></footer>
```

### 4. Wrap Content in the article Element

_**article**_ is another one of the new HTML5 elements that adds semantic meaning to your markup. _**article**_ is a sectioning element, and is used <ins>to wrap independent, self-contained content.</ins> The tag works well with blog entries, forum posts, or news articles.

#### Note about section and div

The _**section**_ element is also new with HTML5, and has a slightly different semantic meaning than _**article**_. An _**article**_ is for <ins>standalone content</ins>, and a _**section**_ is for <ins>grouping thematically related content.</ins> They can be used within each other, as needed. For example, if a book is the _**article**_, then each chapter is a _**section**_. When there's no relationship between groups of content, then use a _**div**_.

```
<div> - groups content
<section> - groups related content
<article> - groups independent, self-contained content
```

```
<h1>Deep Thoughts with Master Camper Cat</h1>
<main>
  <article>
    <h2>The Garfield Files: Lasagna as Training Fuel?</h2>
    <p>The internet is littered with varying opinions on nutritional paradigms,...</p>
  </article>
```

### 5. Make Screen Reader Navigation Easier with the header Landmark

_**header**_ tag it's used to wrap introductory information or navigation links for its parent tag and works well around content that's repeated at the top on multiple pages.

#### Note

The _**header**_ is meant for use in the _**body**_ tag of your HTML document. This is different than the <ins>**_head_**</ins> element, which contains the page's title, meta information, etc.

```
<header>
    <h1>Training with Camper Cat</h1>
  </header>
```

### 6. Make Screen Reader Navigation Easier with the nav Landmark

The _**nav**_ element is another HTML5 item with the embedded landmark feature for easy screen reader navigation. This tag is meant to wrap around <ins>the main navigation links in your page.</ins>

```
<nav>
      <ul>
        <li><a href="#stealth">Stealth &amp; Agility
        </a></li>
        <li><a href="#combat">Combat</a></li>
        <li><a href="#weapons">Weapons</a></li>
      </ul>
</nav>
```

### 7. Make Screen Reader Navigation Easier with the footer Landmark

Similar to _**header**_ and _**nav**_, the _**footer**_ element has a built-in landmark feature that allows assistive devices to quickly navigate to it. It's primarily used to contain **copyright information** or **links** to related documents that usually sit at the <ins>bottom</ins> of a page.

`<footer>&copy; 2018 Camper Cat</footer>`

### 8. Improve Accessibility of Audio Content with the audio Element

HTML5's _**audio**_ element gives semantic meaning when it wraps sound or audio stream content in your markup. <ins>Audio content also needs a text alternative</ins> to be accessible to people who are deaf or hard of hearing. This can be done with nearby text on the page or a link to a transcript.

The _**audio**_ tag supports the _**controls**_ attribute. This shows the browser default play, pause, and other controls, and supports keyboard functionality. This is a <ins>boolean attribute</ins>, meaning it doesn't need a value, its presence on the tag turns the setting on.

Here's an example:

```
<audio id="meowClip" controls>
  <source src="audio/meow.mp3" type="audio/mpeg" />
  <source src="audio/meow.ogg" type="audio/ogg" />
</audio>
```

### 9. Improve Chart Accessibility with the figure Element

HTML5 introduced the _**figure**_ element, along with the related _**figcaption**_. Used together, these items wrap a <ins>visual representation</ins> (like an image, diagram, or chart) along with its caption.

Here's an example - note that the _**figcaption**_ goes inside the _**figure**_ tags and can be combined with other elements:

```
<figure>
  <img src="roundhouseDestruction.jpeg" alt="Photo of Camper Cat executing a roundhouse kick">
  <br>
  <figcaption>
    Master Camper Cat demonstrates proper form of a roundhouse kick.
  </figcaption>
</figure>
```

### 10. Improve Form Field Accessibility with the label Element

The _**label**_ tag wraps the <ins>text for a specific form control item</ins>, usually the name or label for a choice. This ties meaning to the item and makes the form more readable. The _**for**_ attribute on a _**label**_ tag explicitly associates that _**label**_ with the form control and is used by screen readers.

The value of the _**for**_ attribute must be the same as the value of the _**id**_ attribute of the _**form**_ control. Here's an example:

```
<form>
  <label for="name">Name:</label>
  <input type="text" id="name" name="name">
</form>
```

### 11. Wrap Radio Buttons in a fieldset Element for Better Accessibility

The next form topic covers accessibility of <ins>radio buttons</ins>. Each choice is given a _**label**_ with a _**for**_ attribute tying to the _**id**_ of the corresponding. Since radio buttons often come in a group where the user must choose one, there's a way to semantically show the choices are part of a set.

The _**fieldset**_ tag surrounds the entire grouping of radio buttons to achieve this. It often uses a _**legend**_ tag to provide a <ins>description for the grouping</ins>, which is read by screen readers for each choice in the _**fieldset**_ element.

The _**fieldset**_ wrapper and _**legend**_ tag are <ins>not necessary when the choices are self-explanatory, like a gender selection</ins>. Using a _**label**_ with the _**for**_ attribute for each radio button is sufficient.

Here's an example:

```
<form>
  <fieldset>
    <legend>Choose one of these three items:</legend>
    <input id="one" type="radio" name="items" value="one">
    <label for="one">Choice One</label><br>
    <input id="two" type="radio" name="items" value="two">
    <label for="two">Choice Two</label><br>
    <input id="three" type="radio" name="items" value="three">
    <label for="three">Choice Three</label>
  </fieldset>
</form>
```

### 12. Add an Accessible Date Picker

Forms often include the _**input**_ field, which can be used to <ins>create several different form controls</ins>. The _**type**_ attribute on this element indicates <ins>what kind of input</ins> will be created.

Depending on browser support, a date picker shows up in the _**input**_ field when it's in focus, which makes filling in a form easier for all users.

For older browsers, the type will default to _**text**_, so it helps to show users the expected date format in the label or as placeholder text just in case.

Here's an example:

```
<label for="input1">Enter a date:</label>
<input type="date" id="input1" name="input1">
```

### 13. Standardize Times with the HTML5 datetime Attribute

Continuing with the date theme, HTML5 also introduced the _**time**_ element along with a _**datetime**_ attribute to standardize times. This is an <ins>inline element that can wrap a date or time on a page</ins>.

A valid format of that date is held by the _**datetime**_ attribute. This is the value accessed by assistive devices. It helps avoid confusion by stating a standardized version of a time, even if it's written in an informal or colloquial manner in the text.

Here's an example:

```
<p>
    Master Camper Cat officiated the cage match between Goro and Scorpion
    <time datetime="2013-02-13">
    last Wednesday
    </time>
    , which ended in a draw.
</p>
```

### 14. Make Elements Only Visible to a Screen Reader by Using Custom CSS

CSS's magic can also improve accessibility on your page when you want to <ins>visually hide content meant only for screen readers</ins>. This happens when information is in a visual format (like a chart), but screen reader users need an alternative presentation (like a table) to access the data. CSS is used to position the screen reader-only elements off the visual area of the browser window.

Here's an example of the CSS rules that accomplish this:

```
.sr-only {
  position: absolute;
  left: -10000px;
  width: 1px;
  height: 1px;
  top: auto;
  overflow: hidden;
}
```

- _**display: none;**_ or _**visibility: hidden;**_ hides content for everyone, including screen reader users
- Zero values for pixel sizes, such as _**width:0px; height: 0px;**_ removes that element from the flow of your document, meaning screen readers will ignore it

### 15. Improve Readability with High Contrast Text

The _**Web Content Accessibility Guidelines**_ (WCAG) recommend at least a **4.5** to **1** contrast ratio for normal text. The ratio is calculated by comparing the <ins>relative luminance</ins> values of two colors. This ranges from **1:1** for the same color, or no contrast, to **21:1** for white against black, the strongest contrast.

### 16. Avoid Colorblindness Issues by Using Sufficient Contrast

Color is a large part of visual design, but its use introduces two accessibility issues:

- color alone should not be used as the only way to convey important information because <ins>screen reader users won't see it</ins>;
- foreground and background colors need sufficient <ins>contrast</ins> so colorblind users can distinguish them.

In practice, the **4.5:1** contrast ratio can be reached by <ins>shading</ins> (adding black to) the darker color and <ins>tinting</ins> (adding white to) the lighter color. **Darker shades** on the color wheel are considered to be shades of blues, violets, magentas, and reds, whereas **lighter tinted** colors are oranges, yellows, greens, and blue-greens.

### 17. Avoid Colorblindness Issues by Carefully Choosing Colors that Convey Information

If two similar green colors are the <ins>foreground and background color</ins> of your content, a colorblind user may not be able to distinguish them. Close colors can be thought of as neighbors on the color wheel, and <ins>those combinations should be avoided when conveying important information</ins>.

**Note:** Some online color picking tools include visual simulations of how colors appear for different types of colorblindness. These are great resources in addition to online contrast checking calculators:

[Color Oracle](http://www.colororacle.org/) is a free color blindness simulator for Windows, Mac and Linux. It takes the guesswork out of designing for color blindness by showing you in real time what people with common color vision impairments will see.

[Chroma.js](https://gka.github.io/palettes/#/9|s|00429d,96ffea,ffffe0|ffffe0,ff005e,93003a|1|1) tool is also useful for optimizing your diverging color palettes. It can help you take two or more colors and generate a full scale of in-between values.

[I want Hue](http://medialab.github.io/iwanthue/)
**Colors for data scientists**. Generate and refine palettes of optimally distinct colors.

### 18. Give Links Meaning by Using Descriptive Link Text

Screen reader users have different options for what type of content their device reads. This includes **skipping to (or over)** landmark elements, **jumping** to the main content, or **getting a page summary from the headings**. Another option is to only <ins>hear</ins> the links available on a page.

Screen readers do this by reading the link text, or what's between the anchor **(a)** tags. Having a list of **"click here"** or **"read more"** links isn't helpful. Instead, you should use <ins>brief but descriptive text within the a tags</ins> to provide more meaning for these users.

```
<p>... Click here for <a href="">information about batteries</a></p>
```

### 19. Make Links Navigable with HTML Access Keys

HTML offers the _**accesskey**_ attribute to specify a shortcut key to <ins>activate or bring focus to an element</ins>. This can make navigation more efficient for keyboard-only users.

HTML5 allows this attribute to be used on any element, but it's particularly useful when it's used with **interactive** ones. This includes links, buttons, and form controls.

Here's an example:

`<button accesskey="b">Important Button</button>`

### 20. Use tabindex to Add Keyboard Focus to an Element

The HTML _**tabindex**_ attribute has three distinct functions relating to an element's keyboard focus. When it's on a **tag**, it indicates that element can be focused on. The value (an integer that's positive, negative, or zero) determines the behavior.

Certain elements, such as links and form controls, automatically receive keyboard focus when a user tabs through a page. It's in the same order as the elements come in the HTML source markup. This same functionality can be given to other elements, such as _**div**_, _**span**_, and _**p**_, by placing a _**tabindex="0"**_ attribute on them. Here's an example:

`<div tabindex="0">I need keyboard focus!</div>`

### 21. Use tabindex to Specify the Order of Keyboard Focus for Several Elements

The _**tabindex**_ attribute also specifies the <ins>exact tab order of elements</ins>. This is achieved when the **value** of the attribute is set to a positive number of **1 or higher**.

Setting a _**tabindex="1"**_ will bring keyboard focus to that element first. Then it cycles through the sequence of specified _**tabindex values (2, 3, etc.)**_, before moving to default and _**tabindex="0"**_ items.

It's **important** to note that when the tab order is set this way, it <ins>overrides the default order</ins>(which uses the HTML source). This may confuse users who are expecting to start navigation from the top of the page. This technique may be necessary in some circumstances, but in terms of accessibility, take care before applying it.

Here's an example:

```
<div tabindex="1">I get keyboard focus, and I get it first!</div>

<div tabindex="2">I get keyboard focus, and I get it second!</div>
```

Thank you [freeCodeCamp](https://www.freecodecamp.org/learn)
