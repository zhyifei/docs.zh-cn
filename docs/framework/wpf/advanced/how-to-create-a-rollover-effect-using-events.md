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
ms.openlocfilehash: ccdc8aeb26b538814b2f9020e1e3a5b311fa5a99
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460157"
---
# <a name="how-to-create-a-rollover-effect-using-events"></a>如何：使用事件创建翻转效果
此示例演示如何在鼠标指针进入和离开元素占用的区域时更改元素的颜色。  
  
 此示例由一个 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 文件和一个代码隐藏文件组成。  
  
> [!NOTE]
> 此示例演示如何使用事件，但建议的方法是在样式中使用 <xref:System.Windows.Trigger>。 有关详细信息，请参阅[样式设置和模板化](../../../desktop-wpf/fundamentals/styles-templates-overview.md)。  
  
## <a name="example"></a>示例  
 以下 XAML 创建用户界面，该用户界面由围绕 <xref:System.Windows.Controls.TextBlock><xref:System.Windows.Controls.Border>，并将 <xref:System.Windows.Input.Mouse.MouseEnter> 和 <xref:System.Windows.UIElement.MouseLeave> 事件处理程序附加到 <xref:System.Windows.Controls.Border>。  
  
 [!code-xaml[mouseenterMouseleave#MouseEnterLeaveSampleXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/mouseenterMouseleave/CSharp/Window1.xaml#mouseenterleavesamplexaml)]  
  
 下面的代码将创建 <xref:System.Windows.UIElement.MouseEnter> 和 <xref:System.Windows.UIElement.MouseLeave> 事件处理程序。  当鼠标指针进入 <xref:System.Windows.Controls.Border>时，<xref:System.Windows.Controls.Border> 的背景更改为红色。  当鼠标指针离开 <xref:System.Windows.Controls.Border>时，<xref:System.Windows.Controls.Border> 的背景会改回为白色。  
  
 [!code-csharp[mouseenterMouseleave#MouseEnterLeaveSampleEventHandlers](~/samples/snippets/csharp/VS_Snippets_Wpf/mouseenterMouseleave/CSharp/Window1.xaml.cs#mouseenterleavesampleeventhandlers)]
 [!code-vb[mouseenterMouseleave#MouseEnterLeaveSampleEventHandlers](~/samples/snippets/visualbasic/VS_Snippets_Wpf/mouseenterMouseleave/VisualBasic/Window1.xaml.vb#mouseenterleavesampleeventhandlers)]
