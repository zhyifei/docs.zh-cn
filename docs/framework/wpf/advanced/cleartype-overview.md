---
title: ClearType 概述
ms.date: 03/30/2017
helpviewer_keywords:
- typography [WPF], ClearType technology
- ClearType [WPF], technology
ms.assetid: 7e2392e0-75dc-463d-a716-908772782431
ms.openlocfilehash: b76c0cb04e5de498374cbf28c8813fe5c95d41ae
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186153"
---
# <a name="cleartype-overview"></a>ClearType 概述
本主题概述了 中的 Microsoft ClearType 技术[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]。  

<a name="overview"></a>
## <a name="technology-overview"></a>技术概述  
 ClearType 是 Microsoft 开发的一种软件技术，可提高现有 LCD（液晶显示器）文本的可读性，例如笔记本电脑屏幕、袖珍 PC 屏幕和平板显示器。  ClearType 的工作原理是访问 LCD 屏幕每个像素中的单个垂直颜色条纹元素。 在 ClearType 之前，计算机可以显示的最小详细级别是单个像素，但随着 ClearType 在 LCD 监视器上运行，我们现在可以显示文本的宽度小到一小部分的文本特征。 超高的分辨率增加了文本显示中细节的清晰度，使其更便于长时间阅读。  
  
 中[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]提供的 ClearType 是最新一代的 ClearType，与 Microsoft Windows 图形设备接口 （GDI） 中的版本有若干改进。  
  
<a name="sub-pixel_positioning"></a>
## <a name="sub-pixel-positioning"></a>子像素定位  
 与早期版本的 ClearType 相比，一个显著改进是使用子像素定位。 与 GDI 中的 ClearType 实现不同，中找到的[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]ClearType 允许字形在像素内开始，而不仅仅是像素的起始边界。 由于在定位字形时的这种超高的分辨率，字形的间距和比例更加精确和一致。  
  
 以下两个示例演示了使用子像素定位时，字形如何从任意子像素边界处开始。 左侧的示例使用早期版本的 ClearType 渲染器呈现，该版本不使用子像素定位。 右侧的示例使用新版本的 ClearType 渲染器使用子像素定位进行呈现。 请注意右侧图像中的每个 **e** 和 **l** 的呈现方式稍有不同，因为每一个字母都开始于一个不同的子像素。 在屏幕上以正常尺寸查看文本时，由于字形图像的高对比度，这种差异并不明显。 这只有在 ClearType 中包含复杂的颜色滤波时才可能实现。  
  
 ![使用两个版本的 ClearType 显示的文本](./media/wcpsdk-mmgraphics-text-cleartype-overview-01.png "wcpsdk_mmgraphics_text_cleartype_overview_01")  
使用较早和较晚版本的 ClearType 显示的文本  
  
 以下两个示例将早期 ClearType 渲染器的输出与新版本的 ClearType 渲染器的输出进行比较。 右侧显示的子像素定位显著改善了屏幕上的字体间距，尤其是在较小尺寸处，子像素与整个像素之间的差异在很大程度上代表了字形宽度。 请注意，第二张图中字母之间的间距更均匀。 子像素定位对文本屏幕整体外观的累积效益大大提高，代表了ClearType技术的一个重大进步。  
  
 ![使用较早的 ClearType 版本显示的文本](./media/wcpsdk-mmgraphics-text-cleartype-overview-02.png "wcpsdk_mmgraphics_text_cleartype_overview_02")  
使用较早和较晚版本的 ClearType 显示的文本  
  
<a name="y-direction_antialiasing"></a>
## <a name="y-direction-antialiasing"></a>Y 方向抗锯齿功能  
 ClearType 的另[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]一个改进是 y 方向反锯齿。 没有 y 方向抗锯齿的 GDI 中的 ClearType 可在 x 轴上提供更好的分辨率，但不包括 y 轴。 在平缓曲线的顶部和底部，锯齿状边缘会降低其可读性。  
  
 以下示例演示了没有 y 方向抗锯齿功能的效果。 在这个示例中，字母顶部和底部的锯齿状边缘非常明显。  
  
 ![平缓曲线上有粗糙边缘的文本](./media/wcpsdk-mmgraphics-text-cleartype-overview-03.png "wcpsdk_mmgraphics_text_cleartype_overview_03")  
平缓曲线上有粗糙边缘的文本  
  
 ClearType[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]在 y 方向级别提供抗锯齿，以平滑任何锯齿边缘。 这对于提高东亚语言的可读性特别重要，在东亚语言中，表意文字的水平和垂直平缓曲线几乎同样多。  
  
 以下示例演示了 y 方向抗锯齿功能的效果。 在这个示例中，字母顶部和底部对曲线较为平滑。  
  
 ![采用 ClearType y 向抗锯齿的文本](./media/wcpsdk-mmgraphics-text-cleartype-overview-04.png "wcpsdk_mmgraphics_text_cleartype_overview_04")  
采用 ClearType y 向抗锯齿的文本  
  
<a name="hardware_acceleration"></a>
## <a name="hardware-acceleration"></a>硬件加速  
 ClearType[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]可以利用硬件加速来提高性能，并降低 CPU 负载和系统内存要求。 通过使用图形卡的像素底片和视频内存，ClearType 提供了更快的文本渲染速度，尤其是在使用动画时。  
  
 清除类型[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]不会修改系统范围的清除类型设置。 在 Windows 中禁用[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]ClearType 会将反锯齿模式设置为灰度模式。 此外，ClearType 不会[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]修改[ClearType 调谐器 PowerToy 的](https://www.microsoft.com/typography/ClearTypePowerToy.mspx)设置。  
  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 体系结构设计决策之一是让不依赖于分辨率的布局更好地支持较高分辨率的 DPI 显示器，这种显示器正在日益普及。 此决策的后果是 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 不支持某些东亚字体中抗锯齿的文本呈现或位图，因为它们都依赖于分辨率。  
  
<a name="further_information"></a>
## <a name="further-information"></a>其他信息  
 [ClearType 信息](https://www.microsoft.com/typography/ClearTypeInfo.mspx)  
  
 [ClearType 调谐器 PowerToy](https://www.microsoft.com/typography/ClearTypePowerToy.mspx)  
  
## <a name="see-also"></a>另请参阅

- [ClearType 注册表设置](cleartype-registry-settings.md)
