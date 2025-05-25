# GCVideo DVI 固件更新器 #

此目录包含用于更新基于 GCVideo 3.x 设备固件的控制台应用程序。它基本上只是一个图像查看器，通过 HDL 目录中的 `build-updater.pl` 脚本注入固件数据。

要构建它，你需要在系统上安装 devkitPro，包含 devkitPPC 工具链以及 Gamecube 和/或 Wii 的库。包含的 Makefile 假设已设置通常的环境变量，指向 devkitPro 的目录。

要为 GameCube 构建更新器，使用 `make TARGET=gc`，要为 Wii 构建，使用 `make TARGET=wii`。为方便起见，仓库中包含预编译的二进制文件。