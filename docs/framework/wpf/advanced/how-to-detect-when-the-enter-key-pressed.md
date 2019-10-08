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
# <a name="how-to-detect-when-the-enter-key-pressed"></a><span data-ttu-id="59017-102">如何：按下 Enter 键时进行检测</span><span class="sxs-lookup"><span data-stu-id="59017-102">How to: Detect When the Enter Key Pressed</span></span>
<span data-ttu-id="59017-103">此示例演示如何检测在键盘上按 @no__t 0 键的时间。</span><span class="sxs-lookup"><span data-stu-id="59017-103">This example shows how to detect when the <xref:System.Windows.Input.Key.Enter> key is pressed on the keyboard.</span></span>  
  
 <span data-ttu-id="59017-104">此示例由一个 @no__t 0 文件和一个代码隐藏文件组成。</span><span class="sxs-lookup"><span data-stu-id="59017-104">This example consists of a [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file and a code-behind file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="59017-105">示例</span><span class="sxs-lookup"><span data-stu-id="59017-105">Example</span></span>  
 <span data-ttu-id="59017-106">当用户按 @no__t 中的 @no__t 0 键时，文本框中的输入将显示在 @no__t 的另一区域中。</span><span class="sxs-lookup"><span data-stu-id="59017-106">When the user presses the <xref:System.Windows.Input.Key.Enter> key in the <xref:System.Windows.Controls.TextBox>, the input in the text box appears in another area of the [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)].</span></span>  
  
 <span data-ttu-id="59017-107">下面的 XAML 创建用户界面，该用户界面由 <xref:System.Windows.Controls.StackPanel>、<xref:System.Windows.Controls.TextBlock> 和 <xref:System.Windows.Controls.TextBox> 组成。</span><span class="sxs-lookup"><span data-stu-id="59017-107">The following XAML creates the user interface, which consists of a <xref:System.Windows.Controls.StackPanel>, a <xref:System.Windows.Controls.TextBlock>, and a <xref:System.Windows.Controls.TextBox>.</span></span>  
  
 [!code-xaml[keydown#KeyDownUI](~/samples/snippets/csharp/VS_Snippets_Wpf/KeyDown/CSharp/Window1.xaml#keydownui)]  
  
 <span data-ttu-id="59017-108">下面的代码将创建 <xref:System.Windows.UIElement.KeyDown> 事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="59017-108">The following code behind creates the <xref:System.Windows.UIElement.KeyDown> event handler.</span></span>  <span data-ttu-id="59017-109">如果按下的键是 <xref:System.Windows.Input.Key.Enter> 键，则会在 <xref:System.Windows.Controls.TextBlock> 中显示一条消息。</span><span class="sxs-lookup"><span data-stu-id="59017-109">If the key that is pressed is the <xref:System.Windows.Input.Key.Enter> key, a message is displayed in the <xref:System.Windows.Controls.TextBlock>.</span></span>  
  
 [!code-csharp[keydown#KeyDownSample](~/samples/snippets/csharp/VS_Snippets_Wpf/KeyDown/CSharp/Window1.xaml.cs#keydownsample)]
 [!code-vb[keydown#KeyDownSample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/KeyDown/VisualBasic/Window1.xaml.vb#keydownsample)]  
  
## <a name="see-also"></a><span data-ttu-id="59017-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="59017-110">See also</span></span>

- [<span data-ttu-id="59017-111">输入概述</span><span class="sxs-lookup"><span data-stu-id="59017-111">Input Overview</span></span>](input-overview.md)
- [<span data-ttu-id="59017-112">路由事件概述</span><span class="sxs-lookup"><span data-stu-id="59017-112">Routed Events Overview</span></span>](routed-events-overview.md)
