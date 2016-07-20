#### JavaScript Object Reference
In JavaScript objects are always passed by copy-reference (also called call-by-sharing) i.e copy of the reference of object will be passed not the object itself which means that any changes made to the object will be visible after the function is done executing. 
```
var obj = { a: "hello" };
function modify(o){
    o.a += " world";
}

modify(obj);
alert(obj.a);  //alerts "hello world"

```

As only copy of the reference is passed, if the object inside the function is re-assigned, this will not be visible outside of the function as it was only a copy of the reference that is change as shown below

```
var obj = { a: "hello" };
function modify(o){
    o = { a: "hello world" };
}

modify(obj);
alert(obj.a);  //alerts just "hello"

```
Another scenario 

```
function changeStuff(a, b, c) {
  a = a * 10;
  b.item = "changed";
  c = {item: "changed"};
}

var num = 10;
var obj1 = {item: "unchanged"};
var obj2 = {item: "unchanged"};

changeStuff(num, obj1, obj2);

console.log(num); //10
console.log(obj1.item); //changed   
console.log(obj2.item); //unchaged

```

The reason is that within changeStuff, num, obj1, and obj2 are references. When you change the item property of the object referenced by obj1, you are changing the value of the item property that was originally set to "unchanged". When you assign obj2 a value of {item: "changed"} you are changing the reference to a new object (which immediately goes out of scope when the function exits).

It's always pass by value, but for objects the value of the variable is a reference. Because of this, when you pass an object and change its members, those changes persist outside of the function. This makes it look like pass by reference. But if you actually change the value of the object variable you will see that the change does not persist, proving it's really pass by value.

####Few important points 
- Javascript is always pass by value, but when a variable refers to an object (including arrays), the "value" is a - reference to the object.
- Changing the value of a variable never changes the underlying primitive or object, it just points the variable to a new primitive or object.
- However, changing a property of an object referenced by a variable does change the underlying object.

###Export Default
Using default means that this ```export``` is the primary export of this file. It's more than just a formality though, using the ```default``` syntax also makes importing easier. With the ```WidgetList``` example from below, we are exporting ```WidgetList``` by default. This means that when we ```import``` WidgetList, we will get the exact same thing that was exported:

```
import React from 'react';

const WidgetList = React.createClass({
  render: function() {
    return (
      <ul className="widget-list">
        <li>Widget 1</li>
        <li>Widget 2</li>
        <li>Widget 3</li>
      </ul>
    );
  }
});

export default WidgetList;
```

###Debounce V Throttle 

```Debounce``` returns a function, that, as long as it continues to be invoked, will not be triggered. The function will be called after it stops being called for N milliseconds. If `immediate` is passed, trigger the function on the leading edge, instead of the trailing.

```Throttle``` the maximum number of times a function can be called in certain time.

###CORS
The Cross-Origin Resource Sharing standard works by adding new HTTP headers that allow servers to describe the set of origins that are permitted to read that information using a web browser. Additionally, for HTTP request methods that can cause side-effects on user data (in particular, for HTTP methods other than GET, or for POST usage with certain MIME types), the specification mandates that browsers "preflight" the request, soliciting supported methods from the server with an HTTP OPTIONS request header, and then, upon "approval" from the server, sending the actual request with the actual HTTP request method. Servers can also notify clients whether "credentials" (including Cookies and HTTP Authentication data) should be sent with requests.

```Stack``` is LIFO (Last In First Out) and 
```Queue``` is FIFO (First In First Out)
