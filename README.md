# Lua

A Lua 5.5.0 iOS framework built with Xcode, packaging the official Lua scripting language as a native Apple framework.

## Overview

This project wraps the [Lua 5.5.0](http://www.lua.org) scripting language into an iOS framework (`com.github.zhkl0228.Lua`), making it easy to embed Lua scripting capabilities into iOS applications.

The official [lua/lua](https://github.com/lua/lua) repository is integrated as a git submodule pinned to tag `v5.5.0`.

## Getting Started

Clone the repository with submodules:

```bash
git clone --recurse-submodules git@github.com:zhkl0228/Lua.git
```

Or if already cloned:

```bash
git submodule update --init
```

## Build

```bash
xcodebuild -project Lua.xcodeproj -target Lua -configuration Release -sdk iphoneos
```

## Requirements

- Xcode
- iOS 12.0+

## Notes

- `loslib.c` is compiled with `-DLUA_USE_IOS` to disable `os.execute()`, which relies on `system()` — unavailable on iOS.
- `lbitlib.c` was removed in Lua 5.5.0 as bitwise operators are now part of the core language.

## License

Lua is free software distributed under the terms of the [MIT license](http://www.lua.org/license.html).
