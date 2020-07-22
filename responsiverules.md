### 1. Make an Image Responsive

Making images responsive with CSS is actually very simple. You just need to add these properties to an image:

```
img {
  max-width: 100%;
  height: auto;
}
```

The _**max-width**_ of **100%** will make sure the image is never wider than the container it is in, and the _**height**_ of _**auto**_ will make the image keep its original aspect ratio.

### 2. Use a Retina Image for Higher Resolution Displays

The simplest way to make your images properly appear on High-Resolution Displays, such as the MacBook Pros "retina display" is to define their _**width**_ and _**height**_ values as only half of what the original file is. Here is an example of an image that is only using half of the original height and width:

```
<style>
  img { height: 250px; width: 250px; }
</style>
<img src="coolPic500x500" alt="A most excellent picture">
```

### 3. Make Typography Responsive

Instead of using _**em**_ or _**px**_ to size text, you can use **viewport units** for responsive typography.

The four different viewport units are:

- _**vw**_ (viewport width): _**10vw**_ would be 10% of the viewport's width.
- _**vh**_ (viewport height): _**3vh**_ would be 3% of the viewport's height.
- _**vmin**_ (viewport minimum): _**70vmin**_ would be 70% of the viewport's smaller dimension (height or width).
- _**vmax**_ (viewport maximum): _**100vmax**_ would be 100% of the viewport's bigger dimension (height or width).

Here is an example that sets a body tag to 30% of the viewport's width.

`body { width: 30vw; }`

### 4. Create a Media Query

Media Queries consist of a media type, and if that media type matches the type of device the document is displayed on, the styles are applied. _You can have as many selectors and styles inside your media query as you want._

Here's an example of a media query that returns the content when the device's width is less than or equal to 100px:

`@media (max-width: 100px) { /* CSS Rules */ }`

and the following media query returns the content when the device's height is more than or equal to 350px:

`@media (min-height: 350px) { /* CSS Rules */ }`

**Note:** CSS inside the media query is applied only if the media type matches that of the device being used.
