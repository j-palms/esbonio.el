# esbonio.el

Emacs package for integrating the [esbonio](https://github.com/swyddfa/esbonio) language server into Emacs

## Setup (eglot)

Install the esbonio language server if you haven't already

```
pipx install --pre esbonio
```

Clone this repository to a location of your choosing

```
git clone https://github.com/swyddfa/esbonio.el
```

Add the following minimal configuration to your ``init.el``

```elisp
;; Ensure that eglot is loaded before esbonio
(use-package eglot)

(use-package esbonio
  :load-path "path/to/esbonio.el"
  :demand
  :hook ((rst-mode . eglot-ensure)))
```

## Setup (lsp-mode)

Coming soon<sup>TM</sup>

## Usage

See the upstream project's [documentation](https://docs.esbon.io/en/latest/) on using esbonio itself.

In addition to registering esbonio with the various lsp client packages, this package provides the following

- `esbonio-preview-file`: Function to open a preview for the current file
- `esbonio-sync-scroll-mode`: Global minor mode that synhronises the scroll state between Emacs and the documentation preview.
