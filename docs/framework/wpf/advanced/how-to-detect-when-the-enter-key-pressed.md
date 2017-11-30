---
title: "如何：检测何时按下 Enter 键"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Enter key [WPF], detecting
- keys [WPF], Enter
ms.assetid: a66f39d2-ef4a-43a5-b454-a4ea0fe88655
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8311083b4b82d4ab4827e8d0a2cf958c67347014
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-detect-when-the-enter-key-pressed"></a><span data-ttu-id="3f03d-102">如何：检测何时按下 Enter 键</span><span class="sxs-lookup"><span data-stu-id="3f03d-102">How to: Detect When the Enter Key Pressed</span></span>
<span data-ttu-id="3f03d-103">此示例演示如何检测何时<xref:System.Windows.Input.Key.Enter>键盘上按下键。</span><span class="sxs-lookup"><span data-stu-id="3f03d-103">This example shows how to detect when the <xref:System.Windows.Input.Key.Enter> key is pressed on the keyboard.</span></span>  
  
 <span data-ttu-id="3f03d-104">此示例组成[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]文件和代码隐藏文件。</span><span class="sxs-lookup"><span data-stu-id="3f03d-104">This example consists of a [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file and a code-behind file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3f03d-105">示例</span><span class="sxs-lookup"><span data-stu-id="3f03d-105">Example</span></span>  
 <span data-ttu-id="3f03d-106">当用户按<xref:System.Windows.Input.Key.Enter>中的键<xref:System.Windows.Controls.TextBox>，在文本框中输入将出现在另一个区域的[!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="3f03d-106">When the user presses the <xref:System.Windows.Input.Key.Enter> key in the <xref:System.Windows.Controls.TextBox>, the input in the text box appears in another area of the [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)].</span></span>  
  
 <span data-ttu-id="3f03d-107">以下[!INCLUDE[TLA2#tla_titlexaml](../../../../includes/tla2sharptla-titlexaml-md.md)]创建用户界面，其中包括<xref:System.Windows.Controls.StackPanel>、 <xref:System.Windows.Controls.TextBlock>，和一个<xref:System.Windows.Controls.TextBox>。</span><span class="sxs-lookup"><span data-stu-id="3f03d-107">The following [!INCLUDE[TLA2#tla_titlexaml](../../../../includes/tla2sharptla-titlexaml-md.md)] creates the user interface, which consists of a <xref:System.Windows.Controls.StackPanel>, a <xref:System.Windows.Controls.TextBlock>, and a <xref:System.Windows.Controls.TextBox>.</span></span>  
  
 [!code-xaml[keydown#KeyDownUI](../../../../samples/snippets/csharp/VS_Snippets_Wpf/KeyDown/CSharp/Window1.xaml#keydownui)]  
  
 <span data-ttu-id="3f03d-108">下面的代码隐藏创建<xref:System.Windows.UIElement.KeyDown>事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="3f03d-108">The following code behind creates the <xref:System.Windows.UIElement.KeyDown> event handler.</span></span>  <span data-ttu-id="3f03d-109">如果按下的键是<xref:System.Windows.Input.Key.Enter>密钥，显示一条消息是在<xref:System.Windows.Controls.TextBlock>。</span><span class="sxs-lookup"><span data-stu-id="3f03d-109">If the key that is pressed is the <xref:System.Windows.Input.Key.Enter> key, a message is displayed in the <xref:System.Windows.Controls.TextBlock>.</span></span>  
  
 [!code-csharp[keydown#KeyDownSample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/KeyDown/CSharp/Window1.xaml.cs#keydownsample)]
 [!code-vb[keydown#KeyDownSample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/KeyDown/VisualBasic/Window1.xaml.vb#keydownsample)]  
  
## <a name="see-also"></a><span data-ttu-id="3f03d-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3f03d-110">See Also</span></span>  
 [<span data-ttu-id="3f03d-111">输入概述</span><span class="sxs-lookup"><span data-stu-id="3f03d-111">Input Overview</span></span>](../../../../docs/framework/wpf/advanced/input-overview.md)  
 [<span data-ttu-id="3f03d-112">路由事件概述</span><span class="sxs-lookup"><span data-stu-id="3f03d-112">Routed Events Overview</span></span>](../../../../docs/framework/wpf/advanced/routed-events-overview.md)
