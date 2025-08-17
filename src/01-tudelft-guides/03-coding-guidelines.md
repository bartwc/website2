# Coding Guidelines

*Reference - [SerenityOS](https://github.com/SerenityOS/serenity/blob/master/CONTRIBUTING.md)*

## 📋 Table of Contents

1. [Human Language Policy](#human-language-policy)
2. [Code and Submission](#code-and-submission)
3. [C++ Coding Style](#c-coding-style)
   - [Indenting](#indenting)
   - [Braces](#braces)
   - [Parentheses](#parentheses)
   - [Null, False and 0](#null-false-and-0)
   - [Names](#names)
4. [Modern C++ Features (C++20/23)](#modern-c-features-c2023)
5. [Doxygen Comments](#doxygen-comments)
6. [Security Best Practices](#security-best-practices)
7. [Source Code Standards](#source-code-standards)
   - [Code Quality Principles](#code-quality-principles)
   - [Compilation and Warnings](#compilation-and-warnings)
   - [Naming and Documentation](#naming-and-documentation)
8. [Version Management (Git)](#version-management-git)
   - [Why Use Version Management](#why-use-version-management)
   - [Git Best Practices](#git-best-practices)

## Human Language Policy

* The official documentation language is English with ISO 8601 dates and metric units.
* Use proper spelling, grammar, and punctuation. Please use tooling (spell checkers, etc) to catch simple mistakes.
* Write in an authoritative and technical tone.

## Code and submission

### Do:

* Conform to the coding style found below. Use clang-format (version 16 or later) to automatically format C++ files.
* Choose expressive variable, function and class names. Make it easy to understand the logic flow of the code.
* Split your changes into separate, atomic commits (i.e. A commit per feature or fix, where the build, tests and the system are all functioning).
* Capitalise the subject line with a maximum of 72 characters.
* Use the body in a commit section to explain what and why, and not how.
* Make sure your commits are rebased on the main branch.
* Squash your commits when making revisions after a patch review.

### Don't:

* Use the repository as a backup
* Iterate excessively on your design across multiple commits.
* Use imprecise words like "refactor" or "fix" to avoid explaining what's being changed.
* End commit message subject lines with a period.
* Include commented-out code.
* Write in C. (Instead, take advantage of C++'s amenities, and don't limit yourself to the standard C library.) Use C++ 20 or later
* Move code around without quantifiable benefit.

# C++ coding style

*Shamelessly stolen from [WebKit](https://webkit.org/blog/25/webkit-coding-style-guidelines/)*

## Indenting

* Use spaces to indent. Tabs should not appear in code files (with the exception of files that require them e.g. Makefiles).
* The indent size is 4 spaces.
* Code editors should be configured to expand tabs that you type to 4 spaces.

## Braces

* Function definitions – open and close braces should be on lines by themselves. Do not put the open brace on the same line as the function signature. For example:

Right:

```
    void foo()
    {
        // do stuff
    }
```

### Wrong:

```
    void foo() {
        // do stuff
    }
```

* Loop control structures, including for, while and do statements – the open brace should go on the same line as the as the control structure.

### Right:

```
    for (int i = 0; i < 10; i++) {
        // do stuff
    }
```

### Wrong:

```
    for (int i = 0; i < 10; i++) 
    {
        // do stuff
    }
```

* If/else statements - as above, but if there is an else clause, the close brace should go on the same line as the else. Also, one-line if or else clauses should not get braces.

### Right:

```
    if (timeToGetCoffee) {
        buyCoffee(&coffee);
        chugIt(coffee);
    } else if (timeToGoHome)
        // comment on else case
        outtaHere = true;
```

### Wrong:

```
    if (timeToGetCoffee)
    {
        buyCoffee(&coffee);
        chugIt(coffee);
    // comment on else case
    } else if (timeToGoHome) 
    {
        outtaHere = true;
    }
            
    if (timeToGetCoffee) {
    } 
    else

    // comment on else case

    if (timeToGoHome) 
        outtaHere = true;
```

## Parentheses

* Function declarations and calls – do not use any spaces between the name and the open paren, inside the parentheses, or before commas that separate arguments. Do use a single space after commas that separate arguments.

### Right:

```
    int myFunction(int arg1, float arg2);

    void noArgFunction(); // for C++ 

    void noArgFunction(void); // for C
```

### Wrong:

```
    int myFunction (int arg1, float arg2);

    int myFunction( int arg1 , float arg2 );

    void noArgFunction ();
```

* Control structures, such as if, while, do and switch – use a single space before the open paren, but no spaces inside the parentheses.

## Null, false and 0

* In C++, the null pointer value should be written as `nullptr`. In C it should be written as `NULL`.
* True and false values of type bool (common in C and C++), or just generic true/false values, should be written as true and false.
* Tests for null pointers, false values and 0 values should all be done diretly, not through an inqueality or equality comparison.

### Right:

```
    // test for true
    if (foo->isSomething()) {
        // code
    }

    // test for false
    if (!foo->isSomething()) {
        // code
    }

    // test for non-null
    if (ptr) {
       // code
    }

    // test for null
    if (!ptr) {
       // code
    }

    // test for nonzero
    if (count) {
        // code
    }

    // test for zero
    if (!count) {
        // code
    }
```

### Wrong:

```
    if (foo->isSomething() == true) {
        // code
    }

    if (foo->isSomething() != false) {
        // code
    }

    if (p == NULL) {
        // code
    }

    if (nil != p) {
        // code
    }

    if (count == 0) {
        // code
    }
```

## Names

* General Rule: With very few exceptions, prefer embedded capitals instead of underscores for class, function and variable names.
* C++ classes, interfaces and protocols, and other type names – these names should start with a capital letter and use InterCaps.

### Right:

```
    class MyImportantClass;
```

### Wrong:

```
    class My_important_class;

    class myImportantClass;
```

* Local variables should use interCaps, but the first word should start with a lowercase letter, like this:

### Right:

```
    int myInt;
```

### Wrong:

```
    int MyInt;

    int my_int;
```

* Free function names in C++ should follow the same naming conventions as local variables. Most functions should be named to sound like verb phrases, like “openDoor” or “walkAroundTheBlock”. (getters, setters, predicates?)
* C++ data members should be named like local variables, but with a prefix of m_.
* C++ member functions should follow the same naming convention as free functions.
* Pointer and reference types – pointer types should be written with a space between the type name and the \* (so the \* is adjacent to the following identifier if any). For reference types, the & goes next to the type name.
* Enum members should user InterCaps with an initial capital letter.
* #defined constants should use all uppercase names with words separated by underscores.
* Macros that expand to function calls or other non-constant computation: these should be (1) avoided if possible, (2) named like functions, and (3) should have parentheses at the end, even if they take no arguments. Note that usually it is preferrable to use an inline function in such cases instead of a macro.

### Right:

```
    #define WBStopButtonTitle()  lookupString("Stop", "Go/Stop button title")
```

### Wrong:

```
    #define WB_STOP_BUTTON_TITLE  lookupString("Stop", "Go/Stop button title")

    #define WBStopButtontitle  lookupString("Stop", "Go/Stop button title")
```

* Acronyms in names: If an identifier includes an acronym, make the acronym all-uppercase or all-lowercase, depending on whether a word in that position would be capitalized or not.

### Right:

```
    urlVariable
    myURLAccessor:
```

### Wrong:

```
    uRLVariable
    myUrlAccessor:
```

## Modern C++ Features (C++20/23)

### Preferred Features

* **Use `auto` for type deduction** when the type is obvious from context
* **Prefer `std::unique_ptr` and `std::shared_ptr`** over raw pointers
* **Use range-based for loops** instead of traditional for loops when possible
* **Use `nullptr`** instead of `0` for null pointers
* **Use `constexpr`** for compile-time computations
* **Use `std::string_view`** for read-only string parameters
* **Use structured bindings** for cleaner tuple/struct unpacking

### Example:

```cpp
// Modern C++ approach
auto processData(const std::string_view& data) -> std::unique_ptr<Result> {
    auto [success, value] = parseInput(data);
    if (!success) {
        return nullptr;
    }
    return std::make_unique<Result>(value);
}
```

## Doxygen comments

* Each class, struct, enum and function should be documented with a Doxygen comment.
* Comments in general, and doxygen comments in particlar, should be written to explain the function and purpose of the code. If comments are needed to explain the internal logic of a special algorithm, do it in comments inside the function, just above the piece of code in question.
* A Doxygen comment block should be defined by a comment block with three forward slashes (`///`) at the beginning of each line.
* Parameters in the documentation block are identified by a `@`.

### Right:

```
    /// Calculate surface area of rectangle
    ///
    /// @x The horizontal dimension in metres
    /// @y The vertical dimension in metres
```

### Wrong:

```
    /** 
     * Calculate surface area of rectangle
     *
     * \x The horizontal dimension in metres
     * \y The vertical dimension in metres
     **/
```

## Security Best Practices

* **Validate all inputs** - Never trust external data
* **Use secure string handling** - Avoid buffer overflows with `std::string` and `std::string_view`
* **Sanitize user input** - Remove or escape potentially dangerous characters
* **Use RAII** - Resource Acquisition Is Initialization for automatic cleanup
* **Avoid raw pointers** - Use smart pointers to prevent memory leaks
* **Check return values** - Always verify function return codes
* **Use const correctness** - Mark parameters and methods as `const` when possible

# Additional Notes

## Source Code Standards

### Code Quality Principles

**Maintainability:**
- Write clean, structured code
- Use consistent indentation, capitalization, commenting
- Code has long lifetime and will be read by many people
- Write simple, understandable code

**Testing Requirements:**
- No program is finished until comprehensively tested
- Testing means demonstrating correct operation for all inputs
- Not just finding one input that seems to work

## **Compilation and Warnings**

**Compiler Settings:**
- Compile with strictest options: `-Wall -ansi` for C/C++
- All warnings must be resolved
- Code should compile without warnings or not compile at all

**Assertions:**
- Insert assertions to check properties that should hold
- In C/C++: at start and end of functions
- In VHDL: in entity declaration or architectures

## **Naming and Documentation**

**Naming Conventions:**
- Use descriptive English names for all identifiers
- Even when English is not your native language
- Variables, functions, methods, classes, files

**Build Systems:**
- Use makefiles where possible
- Document compilation parameters
- Ease installation and reproduction for others

## **Version Management (Git)**

### Why Use Version Management

1. **Backup and Recovery**: Return to previous versions
2. **Change Tracking**: Trace what changed between versions
3. **Multi-location Work**: Work from different computers
4. **Collaboration**: Multiple people can work on same files
5. **Remote Backups**: Multiple repositories act as backups
6. **Experimental Changes**: Make speculative changes safely

### Git Best Practices

**What to Version Control:**
- All source code
- All papers, technical notes, reports
- Microsoft Word documents (use Track Changes and Comments)

**Commit Strategy:**
- Commit frequently to minimize work loss
- Commit whenever you have a working version (even after 5 minutes)
- Use short but useful descriptions in commit messages
- Each commit should be a self-contained change (one feature or bug fix)

**File Management:**
- Only check in source files (not generated files)
- For LaTeX: avoid very long lines to improve change tracking
- Each sentence should start on a new line when possible
- Use hard line breaks at column 70-80 for intermediate results

**Branching:**
- Branches are cheap - use them for experiments
- Delete branches if experiments don't work out
- Merge successful experiments into main branch
