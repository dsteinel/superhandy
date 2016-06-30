# superhandy
This is a nice helper belt for bugfixing websites and finding stupid mistakes

- - -

### Shitty horizontal scrollbar
find an overflowing content on website. Just put this in your browser and find the honkey element

```javascript
var d = document.documentElement.offsetWidth;

[].forEach.call(
  document.querySelectorAll('*'),
  function(el) {
    if (el.offsetWidth > d) {
      console.log(el);
    }
  }
);
```


### Offset anchorlink
Jump to a specific location on a page with an anchor link. If you have a fixed navigation at the top, you will find yourself on a bad place on the page after clicking the anchor. By default the anchorlink will be placed at the top of your view.

```css
  .anchor {
    display: block;
    visibility: hidden;
    position: relative;
    top: -220px;
    height: 0;
  }
```


### Center Backgroundvideo
http://alancrissey.com/articles/stupid-css-tricks/

```css
  .video {
    display: block;
    position: absolute;
    z-index: 0;
    width: 100%;
    height: auto;
    top: 0;
    right: 0;
    bottom: 0;
    left: 50%;
    transform: translateX(-50%);
    margin: auto;
  
    @media screen and (max-aspect-ratio: 239/100) {
      width: auto;
      height: 100%;
    }
  }
```
