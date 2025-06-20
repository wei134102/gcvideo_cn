# GCVideo #

GCVideo 是一系列小型 FPGA 板和 VHDL 项目，能够将 GameCube 的数字视频端口信号转换为标准视频信号，而无需使用原装分量视频线中的定制芯片。目前有针对多个 FPGA 板的 VHDL 项目，包括用于 KNJN Pluto IIx-HDMI 的 Gamecube-to-DVI 版本，以及名为 GCVideo Lite 的 Gamecube-to-Component/RGB 版本（也在本仓库中记录）。GCVideo Lite 还被适配用作任天堂64的 RGB DAC。

原理图和布局在 [Hardware](Hardware) 目录中，HDL 项目在 [HDL](HDL) 目录中。每个目录都应包含 README.md 文件，提供更多信息。


## 迷你常见问题 ##

1. 我想要一个，多少钱？  
    我不销售任何硬件。由于这是一个开源项目，其他人可能会提供现成的板卡或改装服务。

    GCVideo-DVI 基于一个现成的商用 FPGA 开发板，所以你可以直接购买它，刷写并自行安装（或找人帮你做）。

1. 但为什么不直接销售呢？  
    制造用于销售的硬件需要大量工作，需要很多时间，我宁愿把这些时间用在更有趣的事情上。此外，当地法律要求销售自制的电子设备需要大量文书工作和投资，我不想处理这些。

1. 你说你的原型来自 OSHPark，所以你至少有三块板子。能卖我一块吗？  
    不行，它们都已经有主了。

1. 为什么使用那个奇怪的视频 DAC，它在 Digikey 上不是常规库存零件！<br>
    几个月前我设计这块板子时它还是常规库存零件...当时它是最便宜的24位视频DAC。只要DAC有24位并行输入和单泵时钟，应该不难将设计适配到不同的DAC。对于YPbPr输出，DAC还需要能够在Y线上产生一个小偏移，以便在消隐电平下生成同步信号。

1. 呃，原理图上写着XO2-256，但BOM上是XO2-640。哪个是正确的？  
    原计划使用XO2-256，但添加RGB输出的色彩空间转换使设计变得太大。在原理图中保留为XO2-256是为了确保只使用该芯片上可用的引脚，因此可以构建一个稍微便宜些的仅分量版本。

1. 关于行倍频呢？  
    GCVideo Lite（模拟版本）使用了能容纳所有需求的最小FPGA，但这个芯片没有足够的BlockRAM来生成行倍频图像。可以通过使用更大的、引脚兼容的FPGA来更新，但由于480i/576i在分量输入上支持良好，而240p/288p在Gamecube游戏中很少使用，所以目前还没有尝试。

    GCVideo DVI 完全支持行倍频，如果需要还可以在行倍频图像上叠加扫描线。



# 许可证 #

<pre>
版权所有 (C) 2014-2021, Ingo Korb &lt;ingo@akana.de&gt;
保留所有权利。

在满足以下条件的情况下，允许以源代码和二进制形式重新分发和使用（无论是否修改）：
1. 源代码的重新分发必须保留上述版权声明、本条件列表和以下免责声明。
2. 二进制形式的重新分发必须在分发时提供的文档和/或其他材料中复制上述版权声明、本条件列表和以下免责声明。

本软件按"原样"提供，不提供任何明示或暗示的担保，包括但不限于对适销性和特定用途适用性的暗示担保。在任何情况下，版权持有人或贡献者均不对任何直接、间接、附带、特殊、示范性或后果性损害（包括但不限于替代商品或服务的采购、使用损失、数据或利润损失或业务中断）承担责任，无论是因合同、严格责任或侵权行为（包括疏忽或其他）引起的，即使已被告知此类损害的可能性。
</pre>