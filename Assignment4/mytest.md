CPSC-402 Assignment 4

Anthony Walujono

About: This assignment is about building a compiler for a C++ program

Commands:
To compile: stack build
To run (used various files listed): stack run mytest/mytest.cc
To display on command line: more a.wat
To convert a.wat to a.wasm: wat2wasm a.wat -o a.wasm


Validate Program by Reading It:
node test/wat2wasm.js a.wat
node test/run.js a.wasm

Bugs:
Whenever I run wat2wasm a.wat -o a.wasm, I always get an error when "return" is present on a.wat, so I have to delete return everytime. For example, I have to delete "return" between (call $printInt) and (i32.const 0), shown below.
(func $main (result i32) (i32.const 2) (i32.const 3) i32.mul (call $printInt) return (i32.const 0))
