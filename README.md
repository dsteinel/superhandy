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

### Event Mixin
A little helper for using not just one event. Better accessibility.
```css
@mixin on-event($self: false) {
	@if $self {
		&,
		&:hover,
		&:active,
		&:focus {
			@content;
		}

	} @else {
		&:hover,
		&:active,
		&:focus {
			@content;
		}
	}
}
```
#### usage: 
```css
a {
  color: black;
  
  @include on-event() {
    color: red;
  }
```


### Nice Bullet List
Lets style a normal bullet list a little bit nicer. Without any svg or similar.

```css
@mixin nice-bullet-list($color) {
	list-style-type: none;
	position: relative;
	margin-left: 1em;
	padding-left: 0;

	li:before {
		content: "\2022"; // round bubble
		position: absolute;
		left: -1em;
		margin-right: 5px;
		color: $color;
		font-size: 3rem;
		line-height: 0.5;
	}
}
```
