---
title: 如何：按下 Enter 键时进行检测
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Enter key [WPF], detecting
- keys [WPF], Enter
ms.assetid: a66f39d2-ef4a-43a5-b454-a4ea0fe88655
ms.openlocfilehash: e2337826077c836696937f91541d6d261f1270aa
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004819"
---
# <a name="how-to-detect-when-the-enter-key-pressed"></a>如何：按下 Enter 键时进行检测
此示例演示如何检测在键盘上按 @no__t 0 键的时间。  
  
 此示例由一个 @no__t 0 文件和一个代码隐藏文件组成。  
  
## <a name="example"></a>示例  
 当用户按 @no__t 中的 @no__t 0 键时，文本框中的输入将显示在 @no__t 的另一区域中。  
  
 下面的 XAML 创建用户界面，该用户界面由 <xref:System.Windows.Controls.StackPanel>、<xref:System.Windows.Controls.TextBlock> 和 <xref:System.Windows.Controls.TextBox> 组成。  
  
 [!code-xaml[keydown#KeyDownUI](~/samples/snippets/csharp/VS_Snippets_Wpf/KeyDown/CSharp/Window1.xaml#keydownui)]  
  
 下面的代码将创建 <xref:System.Windows.UIElement.KeyDown> 事件处理程序。  如果按下的键是 <xref:System.Windows.Input.Key.Enter> 键，则会在 <xref:System.Windows.Controls.TextBlock> 中显示一条消息。  
  
 [!code-csharp[keydown#KeyDownSample](~/samples/snippets/csharp/VS_Snippets_Wpf/KeyDown/CSharp/Window1.xaml.cs#keydownsample)]
 [!code-vb[keydown#KeyDownSample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/KeyDown/VisualBasic/Window1.xaml.vb#keydownsample)]  
  
## <a name="see-also"></a>请参阅

- [输入概述](input-overview.md)
- [路由事件概述](routed-events-overview.md)
