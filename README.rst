My configuration files for clang format and tidy utilites
=========================================================

My taste, nothing personal.

Resulting file: .clang-format

Styles directory contains predefined styles
(Chromium, GNU, Google, LLVM, Microsoft, Mozilla, WebKit)
by llvm version (18, 19, etc.).

For option description, see: https://clang.llvm.org/docs/ClangFormatStyleOptions.html

Versions
--------

There are differences in versions.

To be precise, currently I've got:

.. code-block:: console
   :caption: My current llvm/clang version

    $ clang-format --version
    clang-format version 19.1.7

ColumnLimit
-----------

The prevalence of widescreen monitors makes
the original justification for the 80-column limit
(fitting multiple windows side-by-side) less compelling.

I think, there should be a limit.

120 columns is increasingly common and accepted,
especially in modern, private, or enterprise codebases.

Predefined styles
+++++++++++++++++


79:
    GNU

80:
    Chromium, Google, LLVM, Mozilla

120:
    Microsoft

No limit:
    WebKit

IndentWidth
-----------

4 spaces: It provides good visual separation
and makes the code structure quite clear.
Many older style guides and projects still use 4 spaces.

2 spaces: Too short for indent, I think.

Predefined styles
+++++++++++++++++

4 spaces
    Microsoft and WebKit

2 spaces
    Chromium, GNU, Google, LLVM, Mozilla

InsertNewlineAtEOF
------------------

An empty line (newline character)
at the end of a source code file
is considered a best practice.
It addresses practical issues related to tooling,
version control, and consistency.

It costs nothing
(1 file - 1 symbol).

Many standard Unix/Linux tools
(like cat, wc, diff, patch, git)
are designed around this definition
and work best or most predictably
with files that end with a newline.
Some tools might issue warnings
(e.g., \ No newline at end of file)
or behave slightly differently
if the final newline is missing.

Predefined styles
+++++++++++++++++

All of them in all versions have ``InsertNewlineAtEOF: false``.

Other utilities
---------------

#. https://uncrustify.sourceforge.net/
#. https://github.com/danmar/cppcheck
#. https://astyle.sourceforge.net/
