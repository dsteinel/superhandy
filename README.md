# superhandy
This is a nice helper belt for bugfixing websites and finding stupid mistakes

- - -

### Shitty horizontal scrollbar
find overflowing content

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
