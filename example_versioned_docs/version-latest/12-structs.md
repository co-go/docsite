---
title: Structs
id: structs
slug: /structs
sidebar_label: 12. Structs
description: Using arrays with Wing
keywords: [Wing language, example]
image: /img/wing-by-example.png
---

Structs are custom data types you can define to store structured information. They're loosely modeled after typed JSON literals in JavaScript.

```js playground example title="main.w"
// Define a simple structure called `Example`
struct Example {
  a: str;    
  b: num;    
  c: bool?;  
}

// Define another structure called `MyData` that includes composition
struct MyData {
  a: str;       
  b: num?;      
  c: Example;   
}

// Creating an instance of `MyData` with some fields initialized
let data = MyData {
  a: "hello",      
  c: {     
    a: "world",    
    b: 42,         
  }
};

log(data.a);        
log(data.c.a);      
log(data.c.b);      
```

```bash title="Wing console output"
# Run locally with wing console
wing it

hello
world
42
```