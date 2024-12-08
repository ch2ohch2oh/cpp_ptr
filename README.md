## `nullptr` vs `NULL`

`NULL` is defined as integer 0 as a C Macro. It could cause confusion when `NULL`
is passed to an overloaded function which can take both `int` and pointer type as parameter.

```cpp
void foo(int i);        // 1
void foo(char *s);      // 2

foo(NULL);      // Calls 1 or 2??
foo(nullptr);   // Calls 2
```

## Array parameters

All three below are the same.

```cpp
void f(int *x);
void f(int x[]);
void f(int x[10]);
```

## `const`

```cpp
// Pointer to a const: cannot do *p=...
const T *p;
T const *p;

// Const pointer: cannot do p=...
T *const p;

// Const pointer to const
const T *const p;
T const *const p;
```

## Learning material

- [Back to Basics: Pointers and Memory - Ben Saks - CppCon 2020][1] covers pointer,
*not* smart pointers.

[1]: https://www.youtube.com/watch?v=rqVWj0aVSxg