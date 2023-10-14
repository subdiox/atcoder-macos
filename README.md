# AtCoder Environment on VSCode for macOS

## Tested Environment

- macOS Sonoma 14.0
- Xcode 15.0
- Homebrew 4.1.15
- online-judge-tools 11.5.1
- atcoder-cli 2.2.0

## How to setup

### Install GCC

```
brew install gcc
```

### Setup a symbolic link

```
ln -s /opt/homebrew/Cellar/gcc/13.2.0/bin/gcc-13 /opt/homebrew/bin/gcc
ln -s /opt/homebrew/Cellar/gcc/13.2.0/bin/g++-13 /opt/homebrew/bin/gcc
```

(The version might differ in your environment)

### Setup settings.json in VSCode

```json:settings.json
{
  "C_Cpp.default.cStandard": "c23",
  "C_Cpp.default.cppStandard": "c++23",
  "C_Cpp.default.includePath": [
    "${workspaceFolder}/**",
    "/opt/homebrew/include/**",
    "/usr/local/include/**",
  ],
}
```

### Setup keybindings.json in VSCode

```json:~/Library/Application Support/Code/User/keybindings.json
[
  {
    "key": "ctrl+t",
    "command": "workbench.action.tasks.runTask",
    "when": "editorTextFocus",
    "args": "CheckTestCase"
  },
  {
    "key": "ctrl+s",
    "command": "workbench.action.tasks.runTask",
    "when": "editorTextFocus",
    "args": "SubmitCode"
  }
]
```
