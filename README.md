# ATS2 emacs mode + snippets

## Description
Major mode for editing [ATS2](http://www.ats-lang.org/) source files (.dats, .sats, .hats).

## Optional Dependencies 
Optional packages available on MELPA, enables pseudo-IDE features.
- flycheck
- smart-compile
- yasnippet

## Configure
Load the major mode.
``` emacs-lisp
(load! "ats2-mode.el")
```

Yasnippet can be integrated with company-mode to provide pseudo-autocompletion.
```emacs-lisp
(setq! yas-indent-line nil)
(defvar company-mode/enable-yas t
  "Enable yasnippet for all backends.")
(defun company-mode/backend-with-yas (backend)
  (if (or (not company-mode/enable-yas) (and (listp backend) (member 'company-yasnippet backend)))
      backend
    (append (if (consp backend) backend (list backend))
            '(:with company-yasnippet))))
(setq company-backends (mapcar #'company-mode/backend-with-yas company-backends))
```

## Usage

Typecheck buffer using keychord
```
C-c C-c
```

Optionally, if flycheck and smart-compile are installed, buffers can be typechecked automatically after saving.

## Extending
If you have any features/snippets that wish to be added, feel free to open a pull request!
