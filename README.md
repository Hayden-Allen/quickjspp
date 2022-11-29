# QuickJS Javascript Engine - Cmake Version

Date: November 29th, 2022
Maintainer: Robin Rowe robin.rowe@cinepaint.org
Platforms: Windows, Linux, MacOS, FreeBSD
Language: C
Build System: cmake
Dependencies: libunistd (needed for Windows only)

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
    
## Open Source License

/*
 * C utilities
 * 
 * Copyright (c) 2017 Fabrice Bellard
 * Copyright (c) 2018 Charlie Gordon
 *
 * Permission is hereby granted, free of charge, to any person obtaining a copy
 * of this software and associated documentation files (the "Software"), to deal
 * in the Software without restriction, including without limitation the rights
 * to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
 * copies of the Software, and to permit persons to whom the Software is
 * furnished to do so, subject to the following conditions:
 *
 * The above copyright notice and this permission notice shall be included in
 * all copies or substantial portions of the Software.
 *
 * THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
 * IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
 * FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL
 * THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
 * LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
 * OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
 * THE SOFTWARE.
 */

