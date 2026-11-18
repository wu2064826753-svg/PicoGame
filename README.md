# PicoGame

PicoGame 是面向 PICO 头显的 Unreal Engine 5.6 VR 游戏项目，使用 `PICOOpenXR` 插件。当前仓库包含工程描述和团队共享配置，游戏默认地图使用引擎自带的 `/Engine/Maps/Templates/OpenWorld`。

## 首次打开工程

1. 安装 Unreal Engine 5.6，并为该引擎安装兼容的 PICO OpenXR 插件。工程已启用 `PICOOpenXR`，团队成员需在各自的开发机上安装插件。
2. 克隆仓库，在 Windows PowerShell 中执行以下命令打开工程。

   ```powershell
   git clone https://github.com/wu2064826753-svg/PicoGame.git
   cd PicoGame
   Start-Process .\PicoGame.uproject
   ```

3. 等待编辑器完成首次资源初始化。如果提示缺少 `PICOOpenXR`，检查插件是否安装到了打开工程所用的 UE 5.6 实例。

## 资源与版本控制

| 路径 | 用途与提交方式 |
| --- | --- |
| `PicoGame.uproject` | 工程入口，记录引擎版本和启用的插件。 |
| `Config/` | 团队共享的渲染、输入、平台等设置，修改后随功能提交。 |
| `Content/` | 存放蓝图、材质、模型和关卡。保存资源后，将对应的 `.uasset`、`.umap` 和新增依赖一起提交。Git 只跟踪文件，空目录在克隆后不会出现。 |
| `DerivedDataCache/`、`Intermediate/`、`Saved/` | 引擎在本机生成的缓存、中间文件和运行数据，已由 `.gitignore` 排除。 |

## 多人协作

- 从最新的 `main` 创建任务分支，完成后提 Pull Request，在描述中写明改动内容和测试方法。
- 开始修改共享蓝图或关卡前，先与队友确认资源路径。多人同时编辑同一份二进制资源时，Git 很难自动合并改动。
- 移动或重命名资源时使用 UE 内容浏览器，并在提交前打开相关关卡，检查材质、蓝图和对象引用。
