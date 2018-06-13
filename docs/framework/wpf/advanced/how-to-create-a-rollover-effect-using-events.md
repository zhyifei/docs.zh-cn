---
title: 如何：使用事件创建翻转效果
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- colors of elements [WPF], changing
- rollover effect [WPF]
- element colors [WPF], changing
ms.assetid: 3b20d028-6f1c-4b25-95d2-fa68cefbdb4c
ms.openlocfilehash: d458d87586614093b35fcd73969dea04fe620351
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33543005"
---
# <a name="how-to-create-a-rollover-effect-using-events"></a>如何：使用事件创建翻转效果
此示例演示如何根据鼠标指针进入和离开元素占用的区域更改元素的颜色。  
  
 此示例组成[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]文件和代码隐藏文件。  
  
> [!NOTE]
>  此示例演示如何使用事件，但获得相同的效果的推荐的方式是使用<xref:System.Windows.Trigger>样式。 有关详细信息，请参阅[样式设置和模板化](../../../../docs/framework/wpf/controls/styling-and-templating.md)。  
  
## <a name="example"></a>示例  
 以下[!INCLUDE[TLA2#tla_titlexaml](../../../../includes/tla2sharptla-titlexaml-md.md)]创建用户界面，其中包括<xref:System.Windows.Controls.Border>围绕<xref:System.Windows.Controls.TextBlock>，并将其附加<xref:System.Windows.Input.Mouse.MouseEnter>和<xref:System.Windows.UIElement.MouseLeave>到事件处理程序<xref:System.Windows.Controls.Border>。  
  
 [!code-xaml[mouseenterMouseleave#MouseEnterLeaveSampleXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/mouseenterMouseleave/CSharp/Window1.xaml#mouseenterleavesamplexaml)]  
  
 下面的代码隐藏创建<xref:System.Windows.UIElement.MouseEnter>和<xref:System.Windows.UIElement.MouseLeave>事件处理程序。  当鼠标指针进入<xref:System.Windows.Controls.Border>，背景的<xref:System.Windows.Controls.Border>将变为红色。  当鼠标指针离开<xref:System.Windows.Controls.Border>，背景的<xref:System.Windows.Controls.Border>将变回为空白。  
  
 [!code-csharp[mouseenterMouseleave#MouseEnterLeaveSampleEventHandlers](../../../../samples/snippets/csharp/VS_Snippets_Wpf/mouseenterMouseleave/CSharp/Window1.xaml.cs#mouseenterleavesampleeventhandlers)]
 [!code-vb[mouseenterMouseleave#MouseEnterLeaveSampleEventHandlers](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/mouseenterMouseleave/VisualBasic/Window1.xaml.vb#mouseenterleavesampleeventhandlers)]
