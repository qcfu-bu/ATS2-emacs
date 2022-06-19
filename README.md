# ATS2 emacs mode

## Description
Major mode for editing [ATS2](http://www.ats-lang.org/) source files (.dats, .sats, .hats).

## Optional Dependencies 
- flycheck

## Configure
Load the major mode.
``` emacs-lisp
(load! "ats2-mode.el")
```

## Usage

Typecheck buffer using keychord
```
C-c C-c
```

Optionally, if flycheck is installed, buffers can be typechecked automatically after saving.
