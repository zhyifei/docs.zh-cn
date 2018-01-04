---
title: "如何：以编程方式更改 TextWrapping 属性"
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
- documents [WPF], changing TextWrapping property programmatically
- TextWrapping property [WPF], changing programmatically
ms.assetid: 30d25554-4c82-4df9-a8d6-35683a4a13bb
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ca87d651f66edba00280a57ca1468af33657a329
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-change-the-textwrapping-property-programmatically"></a><span data-ttu-id="667e5-102">如何：以编程方式更改 TextWrapping 属性</span><span class="sxs-lookup"><span data-stu-id="667e5-102">How to: Change the TextWrapping Property Programmatically</span></span>
## <a name="example"></a><span data-ttu-id="667e5-103">示例</span><span class="sxs-lookup"><span data-stu-id="667e5-103">Example</span></span>  
 <span data-ttu-id="667e5-104">下面的代码示例演示如何更改的值<xref:System.Windows.Controls.TextBlock.TextWrapping%2A>属性以编程方式。</span><span class="sxs-lookup"><span data-stu-id="667e5-104">The following code example shows how to change the value of the <xref:System.Windows.Controls.TextBlock.TextWrapping%2A> property programmatically.</span></span>  
  
 <span data-ttu-id="667e5-105">三个<xref:System.Windows.Controls.Button>元素放在<xref:System.Windows.Controls.StackPanel>中的元素[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="667e5-105">Three <xref:System.Windows.Controls.Button> elements are placed within a <xref:System.Windows.Controls.StackPanel> element in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span></span> <span data-ttu-id="667e5-106">每个<xref:System.Windows.Controls.Primitives.ButtonBase.Click>事件<xref:System.Windows.Controls.Button>对应与一个事件处理程序代码中。</span><span class="sxs-lookup"><span data-stu-id="667e5-106">Each <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event for a <xref:System.Windows.Controls.Button> corresponds with an event handler in the code.</span></span> <span data-ttu-id="667e5-107">事件处理程序使用相同的名称作为<xref:System.Windows.Controls.TextBlock.TextWrapping%2A>值它们将应用于`txt2`时单击该按钮。</span><span class="sxs-lookup"><span data-stu-id="667e5-107">The event handlers use the same name as the <xref:System.Windows.Controls.TextBlock.TextWrapping%2A> value they will apply to `txt2` when the button is clicked.</span></span> <span data-ttu-id="667e5-108">此外中的文本`txt1`(<xref:System.Windows.Controls.TextBlock>中不会显示[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]) 更新以反映在属性中的更改。</span><span class="sxs-lookup"><span data-stu-id="667e5-108">Also, the text in `txt1` (a <xref:System.Windows.Controls.TextBlock> not shown in the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]) is updated to reflect the change in the property.</span></span>  
  
 [!code-xaml[TextWrapProperty#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextWrapProperty/VisualBasic/Pane1.xaml#1)]  
  
 [!code-csharp[TextWrapProperty#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextWrapProperty/CSharp/Window1.xaml.cs#2)]
 [!code-vb[TextWrapProperty#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextWrapProperty/VisualBasic/Pane1.xaml.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="667e5-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="667e5-109">See Also</span></span>  
 <xref:System.Windows.Controls.TextBlock.TextWrapping%2A>  
 <xref:System.Windows.TextWrapping>
