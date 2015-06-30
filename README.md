# jquery-swipe
A jQuery plugin that adds swipe events to elements.

## Arguments

```javascript
$.swipe(onSwipe, minDx, minDy)
```
* *callback* **onSwipe**(*Event* evt, *int* dx, *int* dy) - The event handler for the swipe event.
  * *Event* **evt** - The event object.
  * *int* **dx** - The distance swiped in the X direction.
  * *int* **dy** - The distance swiped in the Y direction.
* *int* **minDx** - (optional) Minimum distance in pixels required to trigger a swipe in the X direction. Default: 30
* *int* **minDy** - (optional) Minimum distance in pixels required to trigger a swipe in the Y direction. Default: 30

## Examples

### Initialize with event handler
```javascript
$('#swipe-box').swipe(function (evt, dx, dy) {
  if (Math.abs(dx) > 30) {
    alert('Swipe X!');
  }
  if (Math.abs(dy) > 30) {
    alert('Swipe Y!');
  }
});
```

### Bind event handler
```javascript
$('#swipe-box').swipe();
$('#swipe-box').bind('swipe', function (evt, dx, dy) {
  if (Math.abs(dx) > 30) {
    alert('Swipe X!');
  }
  if (Math.abs(dy) > 30) {
    alert('Swipe Y!');
  }
});
```

### Putting it all together
```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <title>jQuery Swipe</title>
    <script src="https://code.jquery.com/jquery-2.1.4.min.js"></script>
    <script src="jquery-swipe.js"></script>
    <script>
    // <![CDATA[
    jQuery(function ($) {
      $('#swipe-box').swipe(function (evt, dx, dy) {
        if (Math.abs(dx) > 30) {
          alert('Swipe X!');
        }
        if (Math.abs(dy) > 30) {
          alert('Swipe Y!');
        }
      });
    });
    // ]]>
    </script>
  </head>
  <body>
    <div id="swipe-box"><h1>Swipe me!</h1></div>
  </body>
</html>
```

## Copyright and License
Copyright (c) 2015 Jonathan Baltazar

Code released under the [MIT license](http://www.opensource.org/licenses/mit-license.php).
