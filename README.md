vimv
====

vimv renames files using a text editor.
It generates a shell script to rename files and opens the text editor.
Once the editor is closed, it executes the script.

Example
-------


    $ touch a b c
    $ vimv a b c

The text editor opens with the following script:

`````sh
#!/bin/bash

mv="mv -v --"

$mv a  a
$mv b  b
$mv c  c
`````

Edit the script to look like this:

`````sh
#!/bin/bash

mv="mv -v --"

$mv a  first
$mv b  second
$mv c  third
`````

Save the script and close the editor. The files get renamed:

`````
renamed 'a' -> 'first'
renamed 'b' -> 'second'
renamed 'c' -> 'third'
`````

