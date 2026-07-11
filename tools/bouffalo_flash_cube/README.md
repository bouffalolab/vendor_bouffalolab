# bouffalo_flash_cube

本目录是从当前 Bouffalo SDK 同步的 FlashCube CLI 最小运行集，用于
BL616CL whole image 离线拼包和显式 UART 烧录入口。未包含 GUI、JLink、
OpenOCD 和其他芯片资源。

## 来源

- SDK 版本：`2.3.28-25-g5c976f45`
- SDK commit：`5c976f45d2632043cc160c8659775e021652b79f`
- 原始路径：`tools/bflb_tools/bouffalo_flash_cube/`
- FlashCube 版本：1.4.2
- 同步日期：2026-07-11

同步文件 SHA-256：

```text
575a245511ffecbcfbcd60d367e1d93b0b20e5dd89daffc6c2a8dbf9792e6f5a  BLFlashCommand-ubuntu
d9d3459da53357d19aaedb1d9aad1857a855d20066bdde0db68cda4653e863da  BLFlashCommand-macos
329517ce5220a2807f4e24e3fc745a4e249818914a7ac93da727d7566f36fc67  BLFlashCommand.exe
b93af5edcaabe0f65bc779749141151b27638679dfbed4951863643c1f0dc8c2  version_info.txt
8ef579af982b617296e6f1f39667e9f01301268c160136f027d21c5c8496a183  chips/bl616cl/eflash_loader/eflash_loader_cfg.conf
5ddb1696dfa75e502dac0d65d37b23ff9ad2c729d43c1ccf10bb9682be38571b  chips/bl616cl/efuse_bootheader/efuse_bootheader_cfg.conf
002c41f38bb652bdaf89136183aaef70ae11abbf85f554a59d7242748f32e1e0  chips/bl616cl/efuse_bootheader/flash_para.bin
```

FlashCube 会修改芯片运行目录并生成 `img_create/`、`log/`。postbuild 和
flash shell 均先复制到临时目录运行，不应直接在本目录执行官方 binary。
