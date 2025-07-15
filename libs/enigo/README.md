[![Build Status](https://travis-ci.org/enigo-rs/enigo.svg?branch=master)](https://travis-ci.org/enigo-rs/enigo)
[![Build status](https://ci.appveyor.com/api/projects/status/6cd00pajx4tvvl3e?svg=true)](https://ci.appveyor.com/project/pythoneer/enigo-85xiy)
[![Dependency Status](https://dependencyci.com/github/pythoneer/enigo/badge)](https://dependencyci.com/github/pythoneer/enigo)
[![Docs](https://docs.rs/enigo/badge.svg)](https://docs.rs/enigo)
[![Crates.io](https://img.shields.io/crates/v/enigo.svg)](https://crates.io/crates/enigo)
[![Discord chat](https://img.shields.io/discord/315925376486342657.svg)](https://discord.gg/Eb8CsnN)
[![Gitter chat](https://badges.gitter.im/gitterHQ/gitter.png)](https://gitter.im/enigo-rs/Lobby)


# enigo
Rust 中的跨平台输入模拟！

- [x] Linux (X11) 鼠标
- [x] Linux (X11) 文本
- [ ] Linux (Wayland) 鼠标
- [ ] Linux (Wayland) 文本
- [x] MacOS 鼠标
- [x] MacOS 文本
- [x] Win 鼠标
- [x] Win 文本
- [x] 自定义解析器


```Rust
let mut enigo = Enigo::new();

enigo.mouse_move_to(500, 200);
enigo.mouse_click(MouseButton::Left);
enigo.key_sequence_parse("{+CTRL}a{-CTRL}{+SHIFT}Hello World{-SHIFT}");
```

更多示例请查看 examples

运行时依赖
--------------------

Linux 用户可能需要安装 libxdo-dev。例如，在 Ubuntu 上：

```Bash
apt install libxdo-dev
```
在 Arch 上：

```Bash
pacman -S xdotool
```
