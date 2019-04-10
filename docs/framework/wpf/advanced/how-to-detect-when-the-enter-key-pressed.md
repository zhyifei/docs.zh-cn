---
title: 如何：检测何时按下 Enter 键
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Enter key [WPF], detecting
- keys [WPF], Enter
ms.assetid: a66f39d2-ef4a-43a5-b454-a4ea0fe88655
ms.openlocfilehash: a99da5804bbc31897198b9b6d9e21da9f17dfe26
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59204609"
---
# <a name="how-to-detect-when-the-enter-key-pressed"></a><span data-ttu-id="8fb9b-102">如何：检测何时按下 Enter 键</span><span class="sxs-lookup"><span data-stu-id="8fb9b-102">How to: Detect When the Enter Key Pressed</span></span>
<span data-ttu-id="8fb9b-103">此示例演示如何检测何时<xref:System.Windows.Input.Key.Enter>键盘上按下键。</span><span class="sxs-lookup"><span data-stu-id="8fb9b-103">This example shows how to detect when the <xref:System.Windows.Input.Key.Enter> key is pressed on the keyboard.</span></span>  
  
 <span data-ttu-id="8fb9b-104">此示例中包含的[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]文件和代码隐藏文件。</span><span class="sxs-lookup"><span data-stu-id="8fb9b-104">This example consists of a [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file and a code-behind file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8fb9b-105">示例</span><span class="sxs-lookup"><span data-stu-id="8fb9b-105">Example</span></span>  
 <span data-ttu-id="8fb9b-106">当用户按<xref:System.Windows.Input.Key.Enter>中的键<xref:System.Windows.Controls.TextBox>，在文本框中输入将出现在另一个区域的[!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="8fb9b-106">When the user presses the <xref:System.Windows.Input.Key.Enter> key in the <xref:System.Windows.Controls.TextBox>, the input in the text box appears in another area of the [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)].</span></span>  
  
 <span data-ttu-id="8fb9b-107">以下[!INCLUDE[TLA2#tla_titlexaml](../../../../includes/tla2sharptla-titlexaml-md.md)]创建用户界面，其中包括<xref:System.Windows.Controls.StackPanel>即<xref:System.Windows.Controls.TextBlock>，和一个<xref:System.Windows.Controls.TextBox>。</span><span class="sxs-lookup"><span data-stu-id="8fb9b-107">The following [!INCLUDE[TLA2#tla_titlexaml](../../../../includes/tla2sharptla-titlexaml-md.md)] creates the user interface, which consists of a <xref:System.Windows.Controls.StackPanel>, a <xref:System.Windows.Controls.TextBlock>, and a <xref:System.Windows.Controls.TextBox>.</span></span>  
  
 [!code-xaml[keydown#KeyDownUI](~/samples/snippets/csharp/VS_Snippets_Wpf/KeyDown/CSharp/Window1.xaml#keydownui)]  
  
 <span data-ttu-id="8fb9b-108">下面的代码隐藏创建<xref:System.Windows.UIElement.KeyDown>事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="8fb9b-108">The following code behind creates the <xref:System.Windows.UIElement.KeyDown> event handler.</span></span>  <span data-ttu-id="8fb9b-109">如果按下的键是<xref:System.Windows.Input.Key.Enter>键，显示一条消息是在<xref:System.Windows.Controls.TextBlock>。</span><span class="sxs-lookup"><span data-stu-id="8fb9b-109">If the key that is pressed is the <xref:System.Windows.Input.Key.Enter> key, a message is displayed in the <xref:System.Windows.Controls.TextBlock>.</span></span>  
  
 [!code-csharp[keydown#KeyDownSample](~/samples/snippets/csharp/VS_Snippets_Wpf/KeyDown/CSharp/Window1.xaml.cs#keydownsample)]
 [!code-vb[keydown#KeyDownSample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/KeyDown/VisualBasic/Window1.xaml.vb#keydownsample)]  
  
## <a name="see-also"></a><span data-ttu-id="8fb9b-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="8fb9b-110">See also</span></span>

- [<span data-ttu-id="8fb9b-111">输入概述</span><span class="sxs-lookup"><span data-stu-id="8fb9b-111">Input Overview</span></span>](input-overview.md)
- [<span data-ttu-id="8fb9b-112">路由事件概述</span><span class="sxs-lookup"><span data-stu-id="8fb9b-112">Routed Events Overview</span></span>](routed-events-overview.md)
