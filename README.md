# TidalCycles for VSCode

Support for the TidalCycles in vscode. You can learn more about
TidalCycles at [TidalCycles](https://tidalcycles.org).

## Features

This VSCode extension for TidalCycles is inspired by the commands from the popular Atom package:

- `Shift+Enter` to evalulate a single line
- `Ctrl+Enter` to evaluate multiple lines
- `Ctrl+Alt+H` to hush

### A "flood" function

A custom `flood` function is defined in the bootup of this package. Use `flood` to fill the
post window with some text:

`flood "hello from tidal "`

## Syntax Highlighting

In order to get syntax highlighting in `.tidal` files you must do
two things:

- Install the [Haskell Syntax Highlighting](https://marketplace.visualstudio.com/items?itemName=justusadam.language-haskell) extension
- Associate `.tidal` files to the Haskell language by adding the following 
settings in `settings.json`:

```
"files.associations": {
    "*.tidal": "haskell"
}
```

## Prerequisites

You will need to have TidalCycles (a Haskell package) installed before
using this extension. If you want to produce sound, you'll also
need to have SuperDirt running. You can find instructions to install
TidalCycles and SuperDirt at [TidalCycles](https://tidalcycles.org).

## Extension Settings

* `tidalcycles.ghci` - path to `ghci.exe`
* `tidalcycles.feedbackColor` - the color to use for the "eval flash", 
    in the format `rgba([red],[green],[blue],[opacity])` (e.g. `rgba(100,200,100,0.25)`).
* `tidalcycles.bootTidalPath` - path to a file that contains line-by-line commands to boot the TidalCycles Haskell package.
* `tidalcycles.showOutputInConsoleChannel` - if `true`, will show REPL output in a console window. *NOTE: VSCode does not yet support auto-scrolling in console channels, so this feature doesn't work perfectly yet.*

These settings can all be specified in the VS Code settings file like so:

```
"tidalcycles": {
        "feedbackColor": "rgba(100,250,100,0.5)",
        "ghciPath": "c:\\path\\to\\ghci.exe",
        "showOutputInConsoleChannel": false,
        "tidalBootPath": "c:\\path\\to\\file.hs"
    }
```

## Known Issues

- The `Eval and Copy` and `Eval Multi Line and Copy` commands from the Atom package are not supported.