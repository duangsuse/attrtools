# attrtools
Small command-line app for reading 'i/a' attribute and changing file 'immutable' attribute

## Usage

```plain
Attrtools Usage:
  ./attrtools +i <path> ; Set Immutable
  ./attrtools -i <path> ; Unset Immutable
  ./attrtools <path> ; Is Immutable?
```

+ attrtools __+i__ _\<path\>_ to add 'immutable' flag for file
+ attrtools __-i__ _\<path\>_ to remove 'immutable' flag for file
+ attrtools _\<path\>_ to query file flags
  
## Examples

> sudo __./attrtools +i libe2.o__

`File: libe2.o`

> __./attrtools libe2.o__

```plain
File: libe2.o
16
+i
+a
```

> sudo __./attrtools -i libe2.o__

`File: libe2.o`

> sudo __./attrtools +i libe2__

`Cannot stat: libe2: No such file or directory`

> __./attrtools -i libe2.o__

```plain
File: libe2.o
Failed to chattr -i: Operation not permitted
```

## Exit code

Exit __1__ if __command line/file stat__ fails

Exit __2__ if __chattr/lsattr__ fails

## `stdout` or `stderr`

+ __"informations"__ are printed to stdout
+ __"results"__ are printed to stderr
+ __"errors"__ are printed to stderr

## NDK Compiling

Execute this in project dir:

```bash
ndk-build NDK_PROJECT_PATH=`pwd` NDK_APPLICATION_MK=./Application.mk
```

## Android front-end

https://github.com/duangsuse/ChangeAttr
