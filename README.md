# C盘缓存清理 v1.2

Windows 单文件缓存清理工具（C# WinForms，.NET Framework 4.8，无需额外运行时）。

左侧按分组勾选要清理的项目，右侧显示说明与风险等级；扫描后节点直接显示体积。

## 特性

- 22 个清理项 / 6 组：临时文件、浏览器、WebView2 应用、系统日志与更新、豆包、其他软件缓存
- 高级组（着色器缓存、EA 反作弊、Package Cache、回收站）默认不勾，可手动勾选，高风险项二次确认
- 勾选状态记忆（%LOCALAPPDATA%\\C盘缓存清理\\selection.txt）
- 分类汇总 + 最大 10 项 + 历史记录（累计释放）
- 占用检测：豆包 / Edge / Steam 等运行时提示「删了空间不会立即归还」
- 命令行模式：`--scan` / `--clean`

## 保留策略

着色器缓存（D3DSCache、NVIDIA DXCache/ComputeCache、游戏 PSO）、EA 反作弊、Package Cache、WinSxS、Saved Games、个人文件默认不清理。

## 编译

```
csc /target:winexe /win32icon:app.ico /win32manifest:app.manifest ^
    /r:System.Windows.Forms.dll /r:System.Drawing.dll CleanCache.cs
```

源码必须保持单组 UTF-8 BOM。
