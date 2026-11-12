# SIMulacrum 简体中文版

SIMulacrum 是一款在本机运行的《魔兽世界》装备模拟工具。粘贴 SimulationCraft 插件导出的角色数据后，它会使用 SimulationCraft 比较装备、宝石、消耗品和天赋方案，并按 DPS 排名。

本 Fork 在保留上游模拟逻辑的基础上，增加了简体中文界面和中英文切换。默认语言为简体中文，语言选择保存在本机浏览器中。

## 功能

- **装备比较：** 遍历当前装备和背包物品的有效组合；戒指、饰品会尝试不同栏位组合，并避免重复使用唯一装备。
- **装备升级与化生：** 根据角色导出数据中的纹章数量、化生充能和装备升级路线生成可行方案。
- **宝石：** 比较宝石插槽组合及棱彩钻石搭配。
- **消耗品：** 比较食物、合剂、药水、武器油和增益符文。
- **天赋方案：** 模拟导出数据中保存的天赋配置。
- **智能模拟：** 先快速筛选，再以完整精度重新模拟领先组合和统计上接近的组合。
- **结果分析：** 查看装备组合排名、伤害构成、增益覆盖率和完整 SimulationCraft 报告。
- **更多模拟：** 属性权重、Pawn 字符串、纹章升级规划、宏伟宝库奖励、饰品升级图表和战斗场景比较。
- **DPS 历史：** 在本机保存每次主要模拟记录。

## Windows 使用方法

1. 从本仓库的 Releases 下载 `SIMulacrum-windows.zip`。
2. 解压 ZIP，进入 `SIMulacrum` 文件夹。
3. 双击 `SIMulacrum.exe`，浏览器会自动打开本地页面。
4. 页面顶部语言选项默认是“简体中文”，也可以随时切换到 English。
5. 使用期间保持黑色命令窗口运行；关闭窗口即可退出程序。

如果 Windows 显示“已保护你的电脑”，点击“更多信息”，然后选择“仍要运行”。程序未必经过代码签名，因此 Windows 可能显示此提示。

## 导入角色数据

1. 安装游戏内 SimulationCraft 插件（CurseForge 或 Wago）。
2. 登录要模拟的角色，在聊天框输入 `/simc` 并按回车。
3. 在弹出的窗口中按 `Ctrl+A` 全选，再按 `Ctrl+C` 复制全部内容。请包含背包装备。
4. 将文本粘贴到 SIMulacrum 页面。
5. 勾选要比较的装备、宝石、消耗品或天赋方案，设置战斗场景和精度，然后点击“开始模拟”。
6. 点击结果列表中的任意组合，可查看详细伤害构成和完整报告。

属性权重、纹章规划、宏伟宝库、饰品图表和战斗场景等功能位于“更多模拟”区域。战斗场景比较需要先运行一次“最高 DPS”。

## SimulationCraft 引擎更新

魔兽世界补丁或热修复后，点击页面底部的“检查更新”，按提示更新模拟引擎。不要在模拟任务运行时更新引擎。

此项目会保留原始 SimulationCraft 参数、物品 ID、角色导入格式和模拟算法；汉化只作用于界面展示，不会翻译传给 SimulationCraft 的机器参数。

## 从源码运行和构建

需要 Windows、Node.js 22 和 npm。安装依赖后可运行：

```powershell
npm ci
npm test
npm start
```

浏览器打开 `http://127.0.0.1:8787`。

如果已有 SimulationCraft 可执行文件，可将其传给打包脚本：

```powershell
npm run package -- --simc simc\\simc.exe
```

生成的 Windows 文件位于 `dist/SIMulacrum`。压缩整个文件夹即可分发。上游 Release workflow 也会在 Windows runner 上构建 SimulationCraft 和独立 EXE。

## 项目与许可证

- 本地化 Fork： https://github.com/siwon-fr/wow-gear-sim
- 上游项目： https://github.com/ktmsft/wow-gear-sim
- SimulationCraft： https://github.com/simulationcraft/simc

本项目遵循 MIT 许可证。随包提供的 SimulationCraft 引擎遵循 GPL-3.0；其许可证及源码链接应随发行包提供。字体遵循 SIL Open Font License。
