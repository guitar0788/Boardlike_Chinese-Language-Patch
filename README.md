前言：我非常喜欢这种类型的游戏，在steam上也没有找到比这更好玩的游戏（如果盒友有更好的游戏可以推荐给我）。虽然Boardlike支持简体中文，但是本地化像一坨屎：漏翻译、翻译不准确，甚至还有本地化系统找不到对应翻译问题比比皆是。所以做了个汉化补丁给自己使用。

补丁基本覆盖了所有未能成功本地化和本地化之后仍然狗屁不通的句子，安装之后第一次进入游戏初始化会短暂存在英文。

补丁使用 BepInEx。安装包声称已包含所需组件，通常不必另外下载 BepInEx；不过如果插件加载失败，请按下面的方法检查文件是否齐全。

## 安装说明（Windows / Steam）

**重要：不是把解压后的 `Boardlike_Chinese_Patch_Release` 整个文件夹放进游戏目录。必须把里面的内容放到 `Boardlike.exe` 同级。** Windows 的“全部解压”选项可能自动创建一层同名文件夹，压缩包内部也可能存在同名目录，请逐层打开后再操作。

1. 下载仓库里的 `Boardlike_Chinese_Patch_Release.zip`。
2. Steam 游戏库 → 右键 Boardlike →「管理」→「浏览本地文件」，确认该目录里能直接看到 `Boardlike.exe`。
3. 将 ZIP 解压到一个临时位置。打开解压产生的文件夹；如果又看到同名的 `Boardlike_Chinese_Patch_Release` 文件夹，请继续打开，直到能看到 `BepInEx` 目录和压缩包附带的其他文件。
4. **选中这一层里面的文件和文件夹**，复制到第 2 步找到的 `Boardlike.exe` 所在目录；不要复制外层包装文件夹。若弹出文件合并提示，请确认目标目录正确。
5. 启动游戏，在游戏设置中选择「简体中文」。补丁只针对简体中文本地化做了修改。

正确位置示例（只展示必要的相对关系，其他加载器文件以安装包实际内容为准）：

```text
Boardlike/
├── Boardlike.exe
├── Boardlike_Data/
└── BepInEx/
    └── plugins/
        └── BoardlikeChinese/
```

**常见错误：**

```text
Boardlike/
├── Boardlike.exe
└── Boardlike_Chinese_Patch_Release/
    └── Boardlike_Chinese_Patch_Release/
        └── BepInEx/
            └── plugins/
```

以上嵌套结构不会让游戏根目录中的 BepInEx 正常加载该补丁。

## 安装后没有汉化？

1. 先确认 `BepInEx` 与 `Boardlike.exe` 是同级目录，不是在 `Boardlike_Chinese_Patch_Release` 文件夹中。
2. 启动一次游戏并退出，查看 `BepInEx/LogOutput.log` 是否存在（不同版本的加载器可能采用不同日志路径）。
3. 如果没有日志，优先排查 BepInEx 启动文件缺失或放错位置；如果有日志，检查其中是否提到 `BoardlikeChinese`、加载失败或异常。
4. 若仍不生效，请提供游戏根目录、`BepInEx/plugins` 目录截图及日志，以便确认是安装包问题、游戏版本兼容问题，还是翻译插件自身的问题。

**说明：** 本次文档修订用于澄清安装路径，不能替代对现有 ZIP 包内部结构和游戏实际运行效果的验证；在确认之前，不应宣称现有发布包已修复。
