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
