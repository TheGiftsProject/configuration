# General coding conventions

## Table of Contents

* [The CoffeeScript Style Guide](#guide)
    * [Code Layout](#code_layout)
        * [Tabs or Spaces?](#tabs_or_spaces)
        * [Line endings](#line_endings)
        * [Maximum Line Length](#maximum_line_length)
        * [Blank Lines](#blank_lines)
        * [Trailing Whitespace](#trailing_whitespace)
        * [Encoding](#encoding)
    * [Comments](#comments)
        * [Block Comments](#block_comments)
        * [Inline Comments](#inline_comments)
    * [Exceptions](#exceptions)
    * [Annotations](#annotations)
    * [Miscellaneous](#miscellaneous)

<a name="code_layout"/>
## Code layout

<a name="tabs_or_spaces"/>
### Tabs or spaces

Use **spaces only**, with **2 spaces** per indentation level. Never mix tabs and spaces.

<a name="line_endings"/>
### Line endings
* Use Unix-style line endings. (*BSD/Solaris/Linux/OSX users are covered by default,
  Windows users have to be extra careful.)
    * If you're using Git you might want to add the following
    configuration setting to protect your project from Windows line
    endings creeping in:

        ```$ git config --global core.autocrlf true```

<a name="maximum_line_length"/>
### Maximum Line Length

Limit all lines to a maximum of 100 characters.

<a name="blank_lines"/>
### Blank Lines

Separate top-level function and class definitions with a single blank line.

Separate method definitions inside of a class with a single blank line.

Use a single blank line within the bodies of methods or functions in cases where this improves
readability (e.g., for the purpose of delineating logical sections).

<a name="trailing_whitespace"/>
### Trailing Whitespace

Do not include trailing whitespace on any lines.

<a name="encoding"/>
### Encoding

UTF-8 is the preferred source file encoding.

<a name="comments"/>
## Comments

* Use [TomDoc](http://tomdoc.org/) for all documentation.
* Write self-documenting code and ignore the rest of this section. Seriously!
* If modifying code that is described by an existing comment, update the comment such that it
  accurately reflects the new code. (Ideally, improve the code to obviate the need for the comment,
  and delete the comment entirely.)
* The first word of the comment should be capitalized, unless the first word is an identifier
  that begins with a lower-case letter.
* If a comment is short, the period at the end can be omitted.
* Keep existing comments up-to-date. An outdated is worse than no comment at all.
* Avoid writing comments to explain bad code. Refactor the code to
  make it self-explanatory. (Do or do not - there is no try.)

<a name="block_comments"/>
### Block Comments

Block comments apply to the block of code that follows them.

Each line should be indented at the same level of the code that it describes.

<a name="inline_comments"/>
### Inline Comments

Inline comments are placed on the line immediately above the statement that they are describing.
If the inline comment is sufficiently short, it can be placed on the same line as the statement
(separated by a single space from the end of the statement).

The use of inline comments should be limited, because their existence is typically a sign of a code smell.

Do not use inline comments when they state the obvious:

However, inline comments can be useful in certain scenarios:

<a name="exceptions"/>
## Exceptions

Do not suppress exceptions.

<a name="annotations"/>
## Annotations

Try and avoid annotations as much as possible and use the project task system to document
the needed task.
If needed though, use annotations to describe a specific action that must be taken against the
indicated block of code.

**All annotations should point to a story in the task tracking system**

Write the annotation on the line immediately above the code that the annotation is describing.

The annotation keyword should be followed by a colon and a space, and a descriptive note.

```coffeescript
  # FIXME: The client's current state should *not* affect payload processing.
  resetClientState()
  processPayload()
```

If multiple lines are required by the description, indent subsequent lines with two spaces:

```coffeescript
  # TODO: Ensure that the value returned by this call falls within a certain
  #   range, or throw an exception.
  analyze()
```

Annotation types:

- `TODO`: describe missing functionality that should be added at a later date
- `FIXME`: describe broken code that must be fixed
- `OPTIMIZE`: describe code that is inefficient and may become a bottleneck
- `HACK`: describe the use of a questionable (or ingenious) coding practice
- `REVIEW`: describe code that should be reviewed to confirm implementation

<a name="miscellaneous"/>
## Miscellaneous

`and` is preferred over `&&`.

`or` is preferred over `||`.

`is` is preferred over `==`.

`not` is preferred over `!`.

Avoid `return` where not required, unless the explicit return increases clarity.
