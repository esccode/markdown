---
title: "awk"
author: Jacek Wieteska
description: 'copy from man Ubuntu 20.04.5 LTS'
date: January 22, 2023
output: markdown
---

## NAME
gawk - pattern scanning and processing language

---
## SYNOPSIS
gawk [ POSIX or GNU style options ] `-f` program-file [ -- ]..
gawk [ POSIX or GNU style options ] [ .. ] program-text file ...

---
## DESCRIPTION
Gawk is the GNU Project's implementation of the AWK programming language. It conform to the definition of the language in the POSIX 1003.1 standard. This version in turn is based on the description in *The AWK Programming Language*, by Aho, Kerninghan, and Weinberger. GAwk provides the additional features found in the current version of Brain Kerninghan's *awk* and numerous GNU-specific extensions.

The command line consists of options to gawk itself, the AWK program text (if not supplied  via the -f or `--incude` options), and values to be made available in the ARGC and ARGV pre-defined AWK variables.

When *gawk* is invoked with the `--profile` option, it starts gathering profiling statistics from the execution of the program. *Gawk* runs more slowly in this mode, and automatically produces an execution profile in the file awkprof.out when done. See the `--profile` options, below.

*Gawk* also has an integrated debugger. An interactive debugging session can be started by supplying the `--debug` option to the command line. In this mode of execution, *gawk* loads the AWK source code and then prompts for debugging commands. *Gawk* can only debug AWK program source provided with the `-f` and `--include` options. The debugger is documented in *GAWK*: *Effective AWK Programming*.

---
## OPTION FORMAT
*Gawk* options may be either traditional POSIX-style one letter options, or GNU-style long option, or GNU-style long option. POSIX options start with a single `"-"`, while long options start with `"--"`. Long options are provided for both GNU-specific features and for POSIX-mandated features.

*Gawk*-specific options are typically used in long-options form. Arguments to long options are either joined with the options by an = sign, with no intervening space, or they may be provided in the next command line argument. Long options may be abbreviated, as long as abbreviation remains unique.

Additionally, every long options has a corresponding short options, so that the option's functionality may be used from within `#!` executable csripts.

---

## OPTIONS

*Gawk* accepts the following options. Standard options are listed first, followed by options for *gawk* extensions, listed alphabetically by short options.

`-f` *program-file*  
`--file` *program-file*
>Read the AWK program source from the file *program-file*, instead of from the first command line argument. Multiple `-f` (or `--file`) options may be used. Files read with `-f` are treated as if they begin with an implicit `@namespace "awk"` statement.

`-F` *fs*  
`--field-separator` *fs*
>Use *fs* for the input field separator (the value of the *FS* predefined variable).

`-v` *var=val*  
`--assign` *var=val*
>Assign the value *val*, before execution of the program begins. Such variable values are available to the *BEGIN* rule of an *AWK* program.

`-b`  
`--characters-as-bytes`
>Treat all input data as single-byte characters. In other words, don't pay any attention to the local information when attempting to process strings as multibyte charcters. The `--posix` option overrides this one.

`-c`  
`--traditional`  
>Run in *compatibility* mode. In compatibility mode, *gawk* behaves identically to Brian Kernighan's *awk*; none of the GNU-specific extensions are recognized. See GNU EXTENSIONS, below, for more information.

