---
title: "使用 UI 自动化向文本框添加内容"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- adding content to text boxes
- text boxes, adding content
- UI Automation, adding content to text boxes
ms.assetid: 8bdd1a73-1ecb-4a05-a891-a7827ebb767f
caps.latest.revision: "13"
author: Xansky
ms.author: mhopkins
manager: markl
ms.workload: dotnet
ms.openlocfilehash: be0081bc830a2995f7cba9f2a080c6ee33dcc79a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="add-content-to-a-text-box-using-ui-automation"></a><span data-ttu-id="6698c-102">使用 UI 自动化向文本框添加内容</span><span class="sxs-lookup"><span data-stu-id="6698c-102">Add Content to a Text Box Using UI Automation</span></span>
> [!NOTE]
>  <span data-ttu-id="6698c-103">本文档适用于想要使用 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 命名空间中定义的托管 <xref:System.Windows.Automation> 类的 .NET Framework 开发人员。</span><span class="sxs-lookup"><span data-stu-id="6698c-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="6698c-104">有关 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]的最新信息，请参阅 [Windows 自动化 API：UI 自动化](http://go.microsoft.com/fwlink/?LinkID=156746)。</span><span class="sxs-lookup"><span data-stu-id="6698c-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](http://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="6698c-105">本主题包含演示如何使用的示例代码[!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)]单行文本框中插入文本。</span><span class="sxs-lookup"><span data-stu-id="6698c-105">This topic contains example code that demonstrates how to use [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] to insert text into a single-line text box.</span></span> <span data-ttu-id="6698c-106">为多行和多格式文本控件提供一种替代方法其中[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]不适用。</span><span class="sxs-lookup"><span data-stu-id="6698c-106">An alternate method is provided for multi-line and rich text controls where [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] is not applicable.</span></span> <span data-ttu-id="6698c-107">为了进行比较，该示例还演示如何使用 Win32 方法来达到相同的结果。</span><span class="sxs-lookup"><span data-stu-id="6698c-107">For comparison purposes, the example also demonstrates how to use Win32 methods to accomplish the same results.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6698c-108">示例</span><span class="sxs-lookup"><span data-stu-id="6698c-108">Example</span></span>  
 <span data-ttu-id="6698c-109">以下示例步骤通过一系列中的目标应用程序中的文本控件。</span><span class="sxs-lookup"><span data-stu-id="6698c-109">The following example steps through a sequence of text controls in a target application.</span></span> <span data-ttu-id="6698c-110">每个文本控件进行测试以查看是否<xref:System.Windows.Automation.ValuePattern>对象可以通过使用其<xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="6698c-110">Each text control is tested to see if a <xref:System.Windows.Automation.ValuePattern> object can be obtained from it using the <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> method.</span></span> <span data-ttu-id="6698c-111">如果文本控件不支持<xref:System.Windows.Automation.ValuePattern>、<xref:System.Windows.Automation.ValuePattern.SetValue%2A>方法用于插入文本控件是用户定义的字符串。</span><span class="sxs-lookup"><span data-stu-id="6698c-111">If the text control does support <xref:System.Windows.Automation.ValuePattern>, the <xref:System.Windows.Automation.ValuePattern.SetValue%2A> method is used to insert a user-defined string into the text control.</span></span> <span data-ttu-id="6698c-112">否则为<xref:System.Windows.Forms.SendKeys.SendWait%2A?displayProperty=nameWithType>使用方法。</span><span class="sxs-lookup"><span data-stu-id="6698c-112">Otherwise, the <xref:System.Windows.Forms.SendKeys.SendWait%2A?displayProperty=nameWithType> method is used.</span></span>  
  
 [!code-csharp[InsertText#InsertText](../../../samples/snippets/csharp/VS_Snippets_Wpf/InsertText/CSharp/Window1.xaml.cs#inserttext)]
 [!code-vb[InsertText#InsertText](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InsertText/VisualBasic/Window1.xaml.vb#inserttext)]  
  
## <a name="see-also"></a><span data-ttu-id="6698c-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="6698c-113">See Also</span></span>  
 [<span data-ttu-id="6698c-114">TextPattern 插入文本示例</span><span class="sxs-lookup"><span data-stu-id="6698c-114">TextPattern Insert Text Sample</span></span>](http://msdn.microsoft.com/en-us/67353f93-7ee2-42f2-ab76-5c078cf6ca16)
