# CoffeeScript coding conventions
<a name="module_imports"/>
## Module Imports

If using a module system (CommonJS Modules, AMD, etc.), `require` statements should be placed on separate lines.

```coffeescript
require 'lib/setup'
Backbone = require 'backbone'
```
These statements should be grouped in the following order:

1. Standard library imports _(if a standard library exists)_
2. Third party library imports
3. Local imports _(imports specific to this application or library)_

<a name="whitespace"/>
## Whitespace in Expressions and Statements

Avoid extraneous whitespace in the following situations:

- Immediately inside parentheses, brackets or braces

    ```coffeescript
       ($ 'body') # Yes
       ( $ 'body' ) # No
    ```

- Immediately before a comma

    ```coffeescript
       console.log x, y # Yes
       console.log x , y # No
    ```

Additional recommendations:

- Always surround these binary operators with a **single space** on either side

    - assignment: `=`

        - _Note that this also applies when indicating default parameter value(s) in a function declaration_

           ```coffeescript
           test: (param = null) -> # Yes
           test: (param=null) -> # No
           ```

    - augmented assignment: `+=`, `-=`, etc.
    - comparisons: `==`, `<`, `>`, `<=`, `>=`, `unless`, etc.
    - arithmetic operators: `+`, `-`, `*`, `/`, etc.

    - _(Do not use more than one space around these operators)_

        ```coffeescript
           # Yes
           x = 1
           y = 1
           fooBar = 3

           # No
           x      = 1
           y      = 1
           fooBar = 3
        ```