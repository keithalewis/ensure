# ensure

Use `ensure` to throw an exception or break in the debugger instead of [`assert`](https://en.cppreference.com/w/cpp/error/assert)
which calls [`abort`](https://en.cppreference.com/w/cpp/utility/program/abort).

While developing code `#define DEBUG_BREAK` to have the debugger plop you exactly 
where what you thought should work didn't work. 
Have a look at the relevant runtime values and fix your code.

If you don't define `DEBUG_BREAK` then a `std::runtime_exception` will be thrown 
with an error string containg the file, line, and expression that failed.
Exceptions have termination semantics in C++.

Pro tip: use `ensure(e || !"helpful static string message")` to communicate 
"helpful static string message" to a human being that might be able to fix the code
you wrote after you have moved on.
