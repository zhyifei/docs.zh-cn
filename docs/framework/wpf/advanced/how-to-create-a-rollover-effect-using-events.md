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
ms.openlocfilehash: 806056397200fa5c567e83227499ba721544f523
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005175"
---
# <a name="how-to-create-a-rollover-effect-using-events"></a>如何：使用事件创建翻转效果
此示例演示如何在鼠标指针进入和离开元素占用的区域时更改元素的颜色。  
  
 此示例由一个 @no__t 0 文件和一个代码隐藏文件组成。  
  
> [!NOTE]
> 此示例演示如何使用事件，但实现此相同效果的建议方法是在样式中使用 @no__t 0。 有关详细信息，请参阅[样式设置和模板化](../controls/styling-and-templating.md)。  
  
## <a name="example"></a>示例  
 下面的 XAML 创建用户界面，该用户界面由 <xref:System.Windows.Controls.Border> 围绕 <xref:System.Windows.Controls.TextBlock>，并将 @no__t 和 @no__t 事件处理程序附加到 @no__t。  
  
 [!code-xaml[mouseenterMouseleave#MouseEnterLeaveSampleXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/mouseenterMouseleave/CSharp/Window1.xaml#mouseenterleavesamplexaml)]  
  
 下面的代码将创建 @no__t 0 和 @no__t 事件处理程序。  当鼠标指针进入 <xref:System.Windows.Controls.Border> 时，@no__t 的背景更改为红色。  当鼠标指针离开 <xref:System.Windows.Controls.Border> 时，@no__t 的背景会改回为白色。  
  
 [!code-csharp[mouseenterMouseleave#MouseEnterLeaveSampleEventHandlers](~/samples/snippets/csharp/VS_Snippets_Wpf/mouseenterMouseleave/CSharp/Window1.xaml.cs#mouseenterleavesampleeventhandlers)]
 [!code-vb[mouseenterMouseleave#MouseEnterLeaveSampleEventHandlers](~/samples/snippets/visualbasic/VS_Snippets_Wpf/mouseenterMouseleave/VisualBasic/Window1.xaml.vb#mouseenterleavesampleeventhandlers)]
