# EditPadToolHelper

EditPadToolHelper is a command line tool wrapper that works around EditPad's behavior of appending the DOS end-of-file character `^Z` (hex `0x1A`) when piping text to an external tool. Many programs misinterpret this extra byte, so the helper removes it before passing the data along.

## Usage

Run the helper followed by the program you want EditPad to call:

```console
EditPadToolHelper.exe <path-to-tool-exe> [tool arguments]
```

The helper launches the specified tool, shuttles data between EditPad and that tool while stripping the injected `^Z`, and exits with the same code. Any errors encountered are shown in a message box.

## Configuration options

There are no options to configure at this time. Future versions may introduce customizable behavior.
