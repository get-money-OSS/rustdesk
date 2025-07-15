衍生自 https://github.com/quadrupleslap/scrap

# scrap

Scrap 录制你的屏幕！至少在 Windows、macOS 或 Linux 上可以。

## 使用方法

```toml
[dependencies]
scrap = "0.5"
```

它的 API 非常简单！

```rust
struct Display; /// 一个屏幕。
struct Frame; /// 屏幕上像素的数组。
struct Capturer; /// 一个录制实例。

impl Capturer {
    /// 开始录制。
    pub fn new(display: Display) -> io::Result<Capturer>;

    /// 尝试获取一帧。
    /// 如果还没准备好则返回 WouldBlock。
    pub fn frame<'a>(&'a mut self) -> io::Result<Frame<'a>>;

    pub fn width(&self) -> usize;
    pub fn height(&self) -> usize;
}

impl Display {
    /// 主屏幕。
    pub fn primary() -> io::Result<Display>;

    /// 所有屏幕。
    pub fn all() -> io::Result<Vec<Display>>;

    pub fn width(&self) -> usize;
    pub fn height(&self) -> usize;
}

impl<'a> ops::Deref for Frame<'a> {
    /// 一帧就是一个字节数组。
    type Target = [u8];
}
```

## 帧格式

- 帧格式保证是 **打包的 BGRA**。
- 宽度和高度保证保持不变。
- 步长可能大于宽度，也可能在帧之间变化。

## 系统要求

操作系统      | 最低要求
--------|---------------------
macOS   | macOS 10.8
Linux   | XCB + SHM + RandR
Windows | DirectX 11.1
