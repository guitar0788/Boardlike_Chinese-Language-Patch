# Boardlike 中文汉化补丁

《Boardlike》原版虽然支持简体中文，但有漏翻、错译和部分文本未正确显示的问题。我做了这个补丁，主要修正这些问题。

**这是包含 BepInEx 的整合包，不需要另外下载或安装 BepInEx。** 适用于 Windows 版 Steam 游戏。进入游戏后仍须选择「简体中文」，补丁是在原版简体中文基础上修正的。

> **2026-11-03 安装包修正：** 之前的 ZIP 内部多包了一层 `Boardlike_Chinese_Patch_Release` 目录。玩家使用 Windows「全部解压」后可能再出现一层同名文件夹，导致 BepInEx 不在游戏根目录，汉化无法加载。新的整合包已经把安装文件直接放到 ZIP 根目录，并保留了先前的汉化插件和译文。旧版压缩包已备份在 `archive/`，供追溯使用。

## 下载

**[下载完整整合包：Boardlike_Chinese_Patch_Release.zip](./Boardlike_Chinese_Patch_Release.zip)**

也可以下载同内容、名称更明确的 **[Boardlike_Chinese_Integrated_Fixed_2026-11-03.zip](./Boardlike_Chinese_Integrated_Fixed_2026-11-03.zip)**。两者任选其一即可，**不要两个一起装**。

安装包包含：
- BepInEx 5.4.23.6 运行组件（含 `BepInEx/core`）；
- 启动加载文件 `winhttp.dll`、`doorstop_config.ini`、`.doorstop_version`；
- `BepInEx/plugins/BoardlikeChinese/BoardlikeChinese.dll`；
- `translations.tsv`、`locale_bridge.tsv`；
- `README_INSTALL_CN.txt` 简明说明。

**不用单独安装 BepInEx，也不用将补丁文件夹放进 `Boardlike_Data`。**

## 安装步骤（Windows / Steam）

1. **退出游戏。** 如果 Boardlike 正在运行，先完全关闭。
2. 在 Steam 游戏库中右键 **Boardlike** → **管理** → **浏览本地文件**。打开的目录应当能直接看到 `Boardlike.exe`，例如 `D:\STEAM\steamapps\common\Boardlike\`。
3. 下载上面的 ZIP 压缩包，**打开压缩包，选中里面的文件和文件夹**（包括 `BepInEx`、`winhttp.dll`、`doorstop_config.ini` 和 `.doorstop_version`），直接复制或解压到 `Boardlike.exe` 所在目录。不要把整个 `Boardlike_Chinese_Patch_Release` 外层文件夹放进去。
4. 如果使用 Windows 的「全部解压」，发现系统自动生成了一层以 ZIP 命名的文件夹，**打开这一层，复制里面的内容**，而不是移动整个外层文件夹。
5. 通过 Steam 启动 Boardlike。在游戏设置中选择 **简体中文**。

正常安装后应是这样（只列出关键文件）：

```text
Boardlike/
├── Boardlike.exe
├── Boardlike_Data/
├── .doorstop_version
├── doorstop_config.ini
├── winhttp.dll
├── BepInEx/
│   ├── core/
│   │   └── BepInEx.dll
│   └── plugins/
│       └── BoardlikeChinese/
│           ├── BoardlikeChinese.dll
│           ├── translations.tsv
│           └── locale_bridge.tsv
└── README_INSTALL_CN.txt
```

**错误示例：**

```text
Boardlike/
├── Boardlike.exe
└── Boardlike_Chinese_Patch_Release/
    └── BepInEx/
        └── plugins/
```

只要 `BepInEx` 不与 `Boardlike.exe` 同级，就属于放错位置。

## 没有汉化时怎么检查

- 先确认语言选择了**简体中文**。
- 检查是否能在 `Boardlike.exe` 同级看到 `winhttp.dll`、`doorstop_config.ini`、`BepInEx`。
- 启动游戏一次并退出，查找 `Boardlike/BepInEx/LogOutput.log`（具体日志位置以 BepInEx 版本及配置为准）。没有日志时先排查加载器是否运行；有日志时查找 `BoardlikeChinese` 或异常信息。
- 如果之前已经安装过其他 BepInEx 版本或修改过加载器文件，先确认兼容性，不要随意覆盖其他 Mod 的配置。
- 仍不生效，请附上游戏根目录截图、`BepInEx/plugins` 目录截图及日志，以便排查。不要反复重装多个版本。

首次启动时，部分文本可能在初始化阶段暂时显示英文。

## 版本说明与验证状态

- 本次仅调整**安装包层级和发布说明**，复用之前公开版本的 BepInEx 组件、汉化插件和翻译资源；没有重新编译汉化 DLL，也没有修改游戏原始文件。
- 对当前 GitHub 原包中的 **24 个文件**进行了路径、文件长度和 CRC32 对照；修正版 ZIP 根目录结构、关键文件和压缩包索引检查已通过。
- **尚未完成在新的 Windows 游戏安装环境中的实际启动验收。** 因此，安装结构问题已修复，但不能据此断言所有游戏版本都能正常汉化。
- 历史包保留在 `archive/Boardlike_Chinese_Patch_Release_legacy_nested.zip` 中，不建议新玩家下载它。

如果你喜欢这类游戏，欢迎推荐。
