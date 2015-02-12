<div id="table-of-contents">
<h2>Table of Contents</h2>
<div id="text-table-of-contents">
<ul>
<li><a href="#sec-1">1. What is Semantic Refactor?</a></li>
<li><a href="#sec-2">2. Features</a></li>
<li><a href="#sec-3">3. Usage</a></li>
<li><a href="#sec-4">4. TODOS</a></li>
</ul>
</div>
</div>

# What is Semantic Refactor?<a id="sec-1" name="sec-1"></a>

Semantic Refactor is a refactoring tool based on Semantic parser
framework.

[Semantic](https://www.gnu.org/software/emacs/manual/html_node/semantic/index.html#Top) is a package that provides a framework for writing parsers.
Parsing is a process of analyzing source code based on programming
language syntax. relies on Semantic for analyzing source code and uses
its results to perform smart code refactoring that based on code
structure of the analyzed language, instead of plain text structure.

# Features<a id="sec-2" name="sec-2"></a>

This package includes the following features:

-   Context-sensitive menu

-   Generate class implementation.

-   Generate class getters and setters

-   Generate function implementation

-   Generate function prototype

-   Convert function to function pointer

-   Convert function to function parameter

-   Move semantic units

-   Extract function with type information

[More info and demo](srefactor-demos/demos.md)

# Usage<a id="sec-3" name="sec-3"></a>

To use this package, a user only needs to use this single command:
`srefactor-refactor-at-point` and `semanti-mode` activated. Based on
the context at point, appropriate menu items are offered.

Configuration:

    (semantic-mode 1)
    (define-key c-mode-map (kbd "M-RET") 'srefactor-refactor-at-point)
    (define-key c++-mode-map (kbd "M-RET") 'srefactor-refactor-at-point)

# TODOS<a id="sec-4" name="sec-4"></a>

-   Add local variable rename
-   Add function prototype/implementation generation from lambda
-   Insert function pointer if there is a lambda as local variable in
    extracted region.
-   Convert function pointer parameter -> function
-   Macro extraction
    -   Magic number extraction: replace a number with a macro and replace
        all its occurrences with the macro.
    -   Turn a region into a macro and parameterize string inside the
        region into macro parameter. [Use case](https://github.com/torvalds/linux/blob/9a3c4145af32125c5ee39c0272662b47307a8323/drivers/edac/i7core_edac.c#L802).
-   Smart tag diff and sync between function declarations and function
    implementations
-   Make use of SemanticDB and GNU Global to fine correct definition for
    function extraction
-   Create a tree that transparently display tags across buffers