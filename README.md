# EditPadToolHelper

EditPadToolHelper is a command line wrapper that works around EditPad's habit of appending the DOS end-of-file character `^Z` (hex `0x1A`) when piping text to an external tool. Many programs misinterpret this extra byte, so the helper removes it before passing the data along.

## Usage

Run the helper followed by the program you want EditPad to call:

```console
EditPadToolHelper.exe <path-to-tool-exe> [tool arguments]
```

The helper launches the specified tool, shuttles data between EditPad and that tool while stripping the injected `^Z`, and exits with the same code. Any errors encountered are shown in a message box.

## Configuring EditPad

1. Open **Configure Tools** from EditPad's **Tools** menu.
2. Add a new tool entry.
3. Set **Command line** to something like:
   ```
   C:\path\to\EditPadToolHelper.exe C:\path\to\your-tool.exe [args]
   ```
4. Save your changes and invoke the tool from EditPad as usual.

## Configuration options

There are no options to configure at this time. Future versions may introduce customizable behavior.
