# macOS 上的文件粘贴

macOS 无法使用 `fuse`，因为 [macfuse 默认不支持](https://github.com/macfuse/macfuse/wiki/Getting-Started#enabling-support-for-third-party-kernel-extensions-apple-silicon-macs)。

1. 使用临时文件 `/tmp/rustdesk_<uuid>` 作为粘贴板中的占位符。
2. 使用 `fsevent` 观察文件粘贴操作。然后执行粘贴文件。

## 文件

### `pasteboard_context.rs`

粘贴操作的上下文管理器。

### `item_data_provider.rs`

1. 设置粘贴板项目。
2. 在 `/tmp/.rustdesk_*` 中创建临时文件。

### `paste_observer.rs`

使用 `fsevent` 观察源文件 `/tmp/.rustdesk_*` 的粘贴操作。

### `paste_task.rs`

执行粘贴。
