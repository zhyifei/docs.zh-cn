---
title: 如何：自定义滑块上的刻度
ms.date: 03/30/2017
helpviewer_keywords:
- TickBar [WPF]
- Slider control [WPF], creating with TickBar
ms.assetid: 4fa694f2-a620-4b15-be78-5f4286f89361
ms.openlocfilehash: 3b32bbedb5f654ce75e90a827eb0c4dba1d4d345
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61910684"
---
# <a name="how-to-customize-the-ticks-on-a-slider"></a>如何：自定义滑块上的刻度
此示例演示如何创建<xref:System.Windows.Controls.Slider>带有刻度的控件。  
  
## <a name="example"></a>示例  
 <xref:System.Windows.Controls.Primitives.TickBar>设置时将显示<xref:System.Windows.Controls.Slider.TickPlacement%2A>属性的值以外的其他<xref:System.Windows.Controls.Primitives.TickPlacement.None>，这是默认值。  
  
 下面的示例演示如何创建<xref:System.Windows.Controls.Slider>与<xref:System.Windows.Controls.Primitives.TickBar>显示刻度。 <xref:System.Windows.Controls.Slider.TickPlacement%2A>和<xref:System.Windows.Controls.Slider.TickFrequency%2A>属性定义刻度线和它们之间的间隔的位置。 当您移动<xref:System.Windows.Controls.Primitives.Thumb>，工具提示显示的值<xref:System.Windows.Controls.Slider>。 <xref:System.Windows.Controls.Slider.AutoToolTipPlacement%2A>属性定义工具提示的出现。 <xref:System.Windows.Controls.Primitives.Thumb>移动对应于刻度线的位置，因为<xref:System.Windows.Controls.Slider.IsSnapToTickEnabled%2A>设置为`true`。  
  
 下面的示例演示如何使用<xref:System.Windows.Controls.Slider.Ticks%2A>属性来创建刻度线沿<xref:System.Windows.Controls.Slider>不规则间隔。  
  
 [!code-xaml[Slider#4](~/samples/snippets/xaml/VS_Snippets_Wpf/Slider/xaml/window1.xaml#4)]  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Controls.Slider>
- <xref:System.Windows.Controls.Primitives.TickBar>
- <xref:System.Windows.Controls.Slider.TickPlacement%2A>
- [如何：将滑块绑定到属性值](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms788716(v=vs.90))
