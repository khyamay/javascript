#### JavaScript Object Reference
In JavaScript objects are always passed by copy-reference (also called call by sharing) i.e copy of the reference of object will be passed not the object itself which means that any changes made to the object will be visible after the function is done executing. 
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
