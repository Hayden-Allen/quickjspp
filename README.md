# QuickJS Javascript Engine - Cmake Version

Maintainer: Robin Rowe 2022/11/29

Robin's fork builds with cmake. Platforms: Windows, Linux, MacOS, FreeBSD.

## 2.2 Quick start

qjs is the command line interpreter (Read-Eval-Print Loop) and/or expressions as arguments to execute them:

    ./qjs examples/hello.js

qjsc is the command line compiler, generates a hello executable with no external dependency:

./qjsc -o hello examples/hello.js
    ./hello

Documentation in doc/quickjs.pdf or [doc/quickjs.html](doc/quickjs.html).

## QuickJS Javascript Engine - Premake Windows Previous Version

Authors: Fabrice Bellard and Charlie Gordon

Ported from https://bellard.org/quickjs/ and its official GitHub mirror https://github.com/bellard/quickjs

By Andrew Fedoniouk (a.k.a. c-smile)

This version is 

* Microsoft Visual C++ compatible/compileable
* Is used in Sciter.JS
* It contains extras: 
  * [JSX](doc/jsx.md) - built-in [facebook::JSX](https://facebook.github.io/jsx/) support with Sciter specific extras.
  * Built-in [Persistence](storage/doc/README.md) - you can think of it as local MongoDB (NoSQL) DB embedded into the language. Pretty small, adds just 70kb into binary.
    Persistence is based on [DyBASE of Konstantin Knizhnik](http://garret.ru/)

