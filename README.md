# esbonio.el

Emacs package for integrating the [esbonio](https://github.com/swyddfa/esbonio) language server into Emacs, providing the necessary glue code for both `eglot` and `lsp-mode`

It also exposes the functionality provided by the language server that falls outside the LSP specification including live previews and syncronised scrolling

Requires Emacs 30.1

## Setup (eglot)

Install the esbonio language server if you haven't already

```
pipx install --pre esbonio
```

Add the following configuration to your ``init.el``

```elisp
(use-package esbonio
  :vc (esbonio :url "https://github.com/swyddfa/esbonio.el")
  :hook ((rst-mode . esbonio-eglot-ensure)))
```

## Setup (lsp-mode)

Install the esbonio language server if you haven't already

```
pipx install --pre esbonio
```

Add the following configuration to your `init.el`

```elisp
(use-package esbonio
  :vc (esbonio :url "https://github.com/swyddfa/esbonio.el")
  :hook ((rst-mode . esbonio-lsp-deferred)))  ;; or `esbonio-lsp'
```

## Usage

See the upstream project's [documentation](https://docs.esbon.io/en/latest/) on using esbonio itself.

In addition to registering esbonio with the various lsp client packages, this package provides the following

- `esbonio-preview-file`: Function to open a preview for the current file
- `esbonio-sync-scroll-mode`: Global minor mode that synhronises the scroll state between Emacs and the documentation preview.
