# VideoExport ReShade Fix

## ENG
Fixes corrupted VideoExport output with ReShade at ultrawide or certain resolutions. Uses the actual capture size instead of Unity's screen size.

Tested in Koikatsu Sunshine CharaStudio. Close the game, back up your DLL, then replace `BepInEx/plugins/VideoExport.dll` with [VideoExport.dll](VideoExport.dll). Use even dimensions; do not change resolution while recording.

## 中文
修复了 ultrawide（超宽屏）或特定分辨率下，VideoExport 配合 ReShade 导出产物花屏的问题，改为读取实际捕获尺寸。

已在 Koikatsu Sunshine CharaStudio 实测正常。退出游戏并备份旧 DLL，将上方 DLL 替换至 `BepInEx/plugins/VideoExport.dll`。使用偶数分辨率，录制中不要改变分辨率。

Based on [IllusionMods/HSPlugins](https://github.com/IllusionMods/HSPlugins). Unofficial patch / 非官方补丁。MIT License. [Build details / 构建说明](BUILD.md).

