# GCVideo HDL 项目

此目录包含 GCVideo 电路板上 FPGA 的 HDL 项目。目前有三个项目子目录：

* gcvideo_lite

    此目录包含 GCVideo Lite 硬件（使用 XO2-640）的 HDL 源代码和用于构建它的 Lattice Diamond 项目。

* gcvideo_lite_n64

    此目录包含将 GCVideo Lite 硬件用作任天堂64的 DAC 的 HDL 源代码和 Diamond 项目。

* gcvideo_dvi

    此目录包含 GCVideo 的 DVI 输出版本的 HDL 源代码和 Xilinx ISE 项目。它目前可以在 Pluto IIx HDMI 电路板以及其他几种电路板上运行。
    更多详细信息，请参阅其中的 [README.md](gcvideo_dvi/README.md) 文件。