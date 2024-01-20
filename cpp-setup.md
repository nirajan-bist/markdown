# CPP Installation
- Install `sudo apt-get g++ gdb`
- Check `g++ --version`
- Note: `g++` is compiler and `gdb` is a debugger.

# CPP setup in VS code.
- Install `C/C++ Extension Pack`;
- Terminal > Configure Default Build Task
- Add `-Wall` option to the `args`.
- Note: `Ctrl + Shift + B` to build.
- To run the program create a `launch.json` file in `.vscode` folder
```json
{
    "version": "0.2.0",
    "configurations": [
      {
        "name": "C/C++: g++ build and debug active file",
        "type": "cppdbg",
        "request": "launch",
        "program": "${fileDirname}/${fileBasenameNoExtension}",
        "args": [],
        "stopAtEntry": false,
        "cwd": "${workspaceFolder}",
        "environment": [],
        "externalConsole": false,
        "MIMode": "gdb",
        "miDebuggerPath": "/usr/bin/gdb",
        "setupCommands": [
          {
            "description": "Enable pretty-printing for gdb",
            "text": "-enable-pretty-printing",
            "ignoreFailures": true
          }
        ],
        "preLaunchTask": "C/C++: g++ build active file"
      }
    ]
  }
```
- Note: Press `F5` to build and run.