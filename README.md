# ext-parser

Navigating the ext-fs data-structures.
This project rewritten based on TheCodeArtist's [ext2-parser](https://github.com/TheCodeArtist/ext2-parser/tree/b42065a07d8b06894f3cf88139a8d7808cd791d0). Thanks to the awesome [ext2-parser](https://github.com/TheCodeArtist/ext2-parser)!
##  1. Introduction 
This project aims to prepare a basic program capable of navigating the ext-fs filesystem with the knowledge of its internal data-structures.

The headers are borrowed from project ext2reader.
http://www.cs.washington.edu/education/courses/cse451/09sp/projects.html

## 2. Building

```sh
$ make         # Build binary (ext-shell).
$ make clean   # Delete all generated files.
```

## 3. Running
###  3.1 Running ext-shell
`$ ./ext-shell <ext-file.img>`

- Ext-shell is an interactive shell to handle ext filesystems. The above command loads the img file in RD_ONLY mode. It will parse the superblock and inode-table and print basic info about the filesystem contained in the img file. It then displays the ext-shell prompt and waits for user input.

### 3.2 Supported cmds
The following is a list of cmds support by the ext-shell. These can be typed in at the ext-shell prompt to performs the corresponding functions.
```sh
    ls      		- list contents of the present directory.
        	    	  Default ext-shell starts with '/' i.e. root of img.

    cd <dirname> 	- switch to directory 'dirname'

    cp <filename>	- copy file 'filename' onto the host system.

    q   		- quit ext-shell
```

- NOTE: The current version supports single-level dirname and filename i.e. to access a file/directory one must cd into it one level at a time. cp can be performed only on the files contained in the present directory.

## 4. Coding Style
`$ astyle --style=kr <fliename>`

## 5. References
- Reference material in references directory, copyright of respective owners.


## 6. Version History
v0.2
- Unified interactive-shell binary 'ext-shell'
- supported cmds: ls cd cp q

v0.1
- ext.c to parse and list directory structure.
  Syntax: ./ext <img-file> [inode-num]
- cp.c to copy the contents of file out of the img file.
  Syntax: ./cp <img-file> <src-inode-num> <dst-filename>

