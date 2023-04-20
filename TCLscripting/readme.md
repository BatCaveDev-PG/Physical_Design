# TCL Scipting - Quick start 
The basic understanding of TCL scripting for VLSI purpose is demonstrated here

## General scenarios
 use `echo "type to print"` to print a line.
 
 `pwd` - current working directory. Use `set my_work_dir = 'pwd' ` 

 use # for comments

**1. Not provided .csv file as input**

`$argv[1]` and `$argv[2]` are two arg variables

`$#argv` gives number of arguments

```php
    if ($#arg != 1) then
        echo "Info: provide a csv file"
        exit 1
    endif
```
**2. The .csv file which doesn't exist | "-help" to find out usage | Entering the correct file**
```php
    if (! -f $argv[1] || $arv[1] == "-help") then
        if ($argv[1] != "-help") then
            echo "Error: Cannot find csv file. Exiting..."
            exit 1
        else
            echo "your usage message" 
            exit 1
        endif
    else
        tclsh synth.tcl $argv[1]
    endif   
```

