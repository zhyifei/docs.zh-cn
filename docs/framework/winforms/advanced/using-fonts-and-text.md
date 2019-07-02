---
title: 使用字体和文本
ms.date: 03/30/2017
helpviewer_keywords:
- GDI [Windows Forms], drawing text [Windows Forms]
- text [Windows Forms], drawing in Windows Forms
- examples [Windows Forms], fonts and text
- fonts [Windows Forms], using in Windows Forms
- strings [Windows Forms], drawing in Windows Forms
ms.assetid: d43640f3-da94-4df2-a29d-a9d021a1c069
ms.openlocfilehash: 73a4af5fe7367e777fcb83af8c84c09be91e5b1e
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/02/2019
ms.locfileid: "67505117"
---
# <a name="using-fonts-and-text"></a>使用字体和文本
还有几个类为在 Windows 窗体上绘制文本提供通过 GDI + 和 GDI。 GDI +<xref:System.Drawing.Graphics>类具有多个<xref:System.Drawing.Graphics.DrawString%2A>，可以指定的文本，例如位置、 边框矩形、 字体和格式的各种功能的方法。 此外，可以绘制和度量的文本值与使用静态的 GDI<xref:System.Windows.Forms.TextRenderer.DrawText%2A>并<xref:System.Windows.Forms.TextRenderer.MeasureText%2A>方法提供的`TextRenderer`类。 GDI 方法还允许您指定位置、 字体和格式。 你可为文本呈现; 选择 GDI 或 GDI +但是，GDI 通常提供更好的性能，并且正在测量更准确的文本。 涉及文本呈现其他类包括`FontFamily`， `Font`， <xref:System.Drawing.StringFormat>，和`TextFormatFlags`。  
  
## <a name="in-this-section"></a>本节内容  
 [如何：构造字体系列和字体](how-to-construct-font-families-and-fonts.md)  
 演示如何创建`Font`和`FontFamily`对象。  
  
 [如何：在指定位置绘制文本](how-to-draw-text-at-a-specified-location.md)  
 介绍如何在某个位置使用 GDI + 和 GDI 绘制文本。  
  
 [如何：在矩形中绘制换行文本](how-to-draw-wrapped-text-in-a-rectangle.md)  
 介绍如何在使用 GDI + 和 GDI 的矩形中绘制文本。  
  
 [如何：用 GDI 绘制文本](how-to-draw-text-with-gdi.md)  
 演示如何使用 GDI 绘制文本。  
  
 [如何：对齐绘制的文本](how-to-align-drawn-text.md)  
 演示如何设置 GDI + 和 GDI 文本的格式。  
  
 [如何：创建垂直文本](how-to-create-vertical-text.md)  
 描述如何绘制使用 GDI + 的垂直对齐的文本。  
  
 [如何：在绘制的文本中设置制表位](how-to-set-tab-stops-in-drawn-text.md)  
 显示了如何绘制使用 GDI + 选项卡停止使用的文本。  
  
 [如何：枚举已安装的字体](how-to-enumerate-installed-fonts.md)  
 说明如何列出已安装的字体的名称。  
  
 [如何：创建专用的字体集合](how-to-create-a-private-font-collection.md)  
 介绍如何创建<xref:System.Drawing.Text.PrivateFontCollection>对象。  
  
 [如何：获取字体规格](how-to-obtain-font-metrics.md)  
 演示如何获取字体规格如单元格上升和下降。  
  
 [如何：对文本使用抗锯齿效果](how-to-use-antialiasing-with-text.md)  
 说明如何绘制文本时使用抗锯齿效果。  
  
## <a name="reference"></a>参考  
 <xref:System.Drawing.Font>  
 介绍此类并包含指向其所有成员。  
  
 <xref:System.Drawing.FontFamily>  
 介绍此类并包含指向其所有成员。  
  
 <xref:System.Drawing.Text.PrivateFontCollection>  
 介绍此类并包含指向其所有成员。  
  
 <xref:System.Windows.Forms.TextRenderer>  
 介绍此类并包含指向其所有成员。  
  
 <xref:System.Windows.Forms.TextFormatFlags>  
 介绍此类并包含指向其所有成员。
