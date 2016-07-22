###border-box
The width and height properties include the padding and border, but not the margin
###content-box
This is the initial and default value as specified by the CSS standard. The width and height properties are measured including only the content, but not the padding, border or margin.

Normally, when an element’s size is set, the width and height properties determine the width and height of the element’s content box. Any padding added to the element will increase the total computed width and/or height of the element—this is how the default box model works in regards to sizing the element. The box-sizing property allows you to control how the sizing of an element’s dimensions works. More specifically, using the box-sizing property, you can tell the browser to include the padding width and/or border width in the width of the element, without increasing that width. This is useful for many use cases, but mostly so for when you’re building grid systems in CSS

###PageX/Y && ClientX/Y
```pageX/Y``` coordinates are relative to the top left corner of the whole rendered page (including parts hidden by scrolling),
while ```clientX/Y``` coordinates are relative to the top left corner of the visible part of the page, "seen" through browser window.

- ```pageX/Y``` gives the coordinates relative to the <html> element in CSS pixels.
- ```clientX/Y``` gives the coordinates relative to the viewport in CSS pixels.
- ```screenX/Y``` gives the coordinates relative to the screen in device pixels.

###Target && currentTarget
```target``` is the element that triggered the event (e.g., the user clicked on)
```currentTarget``` is the element that the event listener is attached to.


###Declaration Order in Css class/id

```
.declaration-order {
  /* Positioning */
  position: absolute;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
  z-index: 100;

  /* Box-model */
  display: block;
  float: right;
  width: 100px;
  height: 100px;

  /* Typography */
  font: normal 13px "Helvetica Neue", sans-serif;
  line-height: 1.5;
  color: #333;
  text-align: center;

  /* Visual */
  background-color: #f5f5f5;
  border: 1px solid #e5e5e5;
  border-radius: 3px;

  /* Misc */
  opacity: 1;
}
```
###BEM css styling

```
site-search {} /* Block */
.site-search__field {} /* Element */
.site-search--full {} /* Modifier */
.person {}
.person__hand {}
.person--female {}
.person--female__hand {}
.person__hand--left {}
```

The CSS box model is rather complicated, particularly when it comes to scrolling content. While the browser uses the values from your CSS to draw boxes, determining all the dimensions using JS is not straight-forward if you only have the CSS.

That's why each element has six DOM properties for your convenience: offsetWidth, offsetHeight, clientWidth, clientHeight, scrollWidth and scrollHeight. These are read-only attributes representing the current visual layout, and all of them are integers (thus possibly subject to rounding errors).

![](http://i.stack.imgur.com/5AAyW.png)

- ```offsetWidth```, ```offsetHeight```: The size of the visual box incuding all borders. Can be calculated by adding width/height and paddings and borders, if the element has display: block
- ```clientWidth```, ```clientHeight```: The visual portion of the box content, not including borders or scroll bars , but includes padding . Can not be calculated directly from CSS, depends on the system's scroll bar size.
- ```scrollWidth```, ```scrollHeight```: The size of all of the box's content, including the parts that are currently hidden outside the scrolling area. Can not be calculated directly from CSS, depends on the content.
