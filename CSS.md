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
