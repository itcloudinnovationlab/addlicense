# addlicense

The program ensures source code files have copyright license headers
by scanning directory patterns recursively.

It modifies all source files in place and avoids adding a license header
to any file that already has one.

addlicense requires go 1.16 or later.

## install

    go install github.com/itcloudinnovationlab/addlicense@latest

## usage

    addlicense [flags] pattern [pattern ...]

    -c      copyright holder (default "Google LLC")
    -check  check only mode: verify presence of license headers and exit with non-zero code if missing
    -f      license file
    -pgv    Packeage version
    -gap    Gap version
    -sctd   Solicitud version
    -date   Date version
    -own    Owner change
    -desc   Description change
    -ignore file patterns to ignore, for example: -ignore **/*.go -ignore vendor/**
    -l      license type: apache, bsd, mit, mpl (default "apache")
    -s      Include SPDX identifier in license header. Set -s=only to only include SPDX identifier.
    -v      verbose mode: print the name of the files that are modified
    -y      copyright year(s) (default is the current year)

The pattern argument can be provided multiple times, and may also refer
to single files.  Directories are processed recursively.

For example, to run addlicense across everything in the current directory and
all subdirectories:

    addlicense . -l ITC -c Itc Soluciones LLC -y 2024-20242001v -pfv 0001 -gap 0001 -sctd 0001 -date 07022024 -own theoverlord -desc Entrega Version inicial

The `-ignore` flag can use any pattern [supported by
doublestar](https://github.com/bmatcuk/doublestar#patterns).


## license

Apache 2.0

This is not an official Google product.
