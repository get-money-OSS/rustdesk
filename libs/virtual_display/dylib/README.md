# 虚拟显示器

虚拟显示器可用于没有显示器的计算机。

[开发参考](https://github.com/pavlobu/deskreen/discussions/86)

## Windows

### Win10

Win10 提供了 [间接显示驱动模型](https://msdn.microsoft.com/en-us/library/windows/hardware/mt761968(v=vs.85).aspx)。

此库使用 [这个项目](https://github.com/rustdesk-org/RustDeskIddDriver) 作为驱动程序。


**注意**：Win10 1607 之前的版本。尝试遵循 [这个方法](https://github.com/fanxiushu/xdisp_virt/tree/master/indirect_display)。


#### 测试过的平台

- [x] 19041
- [x] 19043

### Win7

待办事项

[WDDM](https://docs.microsoft.com/en-us/windows-hardware/drivers/display/windows-vista-display-driver-model-design-guide)。

## X11

## OSX
