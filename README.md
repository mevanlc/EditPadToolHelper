# EditPadToolHelper

EditPadToolHelper is a tool wrapper that works around EditPad's behavior of appending a final DOS end-of-file byte `^Z` (hex `0x1A`) to the data it pipes to an external tool. Many modern programs misinterpret this extra byte, so the helper removes it before passing the data along. A carefully considered goal is for the program to be transparent: wrapping your program with this program should behave exactly as if launching your program directly, except for the aforementioned `0x1A` fix.

## Usage

Configure EditPad to call EditPadToolHelper instead of calling your tool directly:

```console
EditPadToolHelper.exe <path-to-your-tool-exe> [optional arguments to your tool]
```

EditPadToolHelper will:
1. Run your specified executable (along with supplied arguments, if any)
2. Carefully shuttle data back and forth between EditPad 
  - This includes stdout, stderr, and stdin
3. Exits with the same exit code code as the wrapped program. 
4. Any errors encountered are shown in a GUI message box.

## Configuration options

EditPadToolHelper has no configurable behaviors at this time.
