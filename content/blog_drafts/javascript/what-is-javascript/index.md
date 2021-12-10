---
title: What is JavaScript?
date: "2021-11-04T10:22:03.284Z"
description: 'What is JavaScript?'
inHome: false
---

JavaScript is a scripting language used to add custom behaviors to HTML content on websites.

Nowadays JavaScript is also used for server-side development (Read node.js), among many other usage applications.

#### What can I do with Javascript?

- You can perform client side validation.
- You can give dynamic behavior to static HTML pages.
- Show animations on web pages.
- You can update partial portion of pages using HTTP requests.
- Develop Server side applications using frameworks like Node.js.

#### Javascript is interpreted language

Javascript is interpreted language, write once and attach it to HTML page. No further compilation is required.

#### Is there any relation between JavaScript and Java?

Absolutely there is no relation between JavaScript and Java.

#### What is ECMAScript?

ECMAScript is a standard, JavaScript is the language that
implement ECMAScript standard.

#### Is JavaScript supports Unicode?

JavaScript programs are written in Unicode. ECMAScript 5 standard supports Unicode 3.

#### Is JavaScript case-sensitive?

Yes JavaScript is a case sensitive language.

#### Is it compulsory to end statement using ;?
Many languages like Java, C, C++ use ; as statement terminator.
Usage of ; is optional in JavaScript, but I always prefer to use ; to maintain consistency.

#### Is JavaScript support automatic garbage collection?

Yes, JavaScript support automatic garbage collection, whenever JavaScript interpreter finds an unreachable object (or) variable, it frees the memory allocated for that variable (or) object.

#### Is JavaScript an object oriented language?

Yes, JavaScript is an object-oriented language, but the kind of inheritance it provides is different from the inheritance provided by languages like Java and C++. JavaScript supports Prototype inheritance.

## Hello world program

Create a `helloWorld.html` file with the following content and open it in your web browser

```html
<!DOCTYPE html>
<html>
    <head>
        <title>Hello world</title>
    </head>
    <body>
        <script type="text/javascript">
            document.write("Hello World");
        </script>
    </body>
</html>
```

The `document.write("Hello World");`  statement gives instruction to the browser to write "Hello World". JavaScript is embedded between <script></script> tags in a HTML document.

We can also enter the following line in the web browser console:

```javascript
console.log("Hello World");
```

And we will observe the following output:

```
Hello World
```

From here we will analyze the examples in this way, looking at the JavaScript code and avoiding specifying HTML code every time.