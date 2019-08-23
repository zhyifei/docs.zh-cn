---
title: 使用 UI 自动化向文本框添加内容
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- adding content to text boxes
- text boxes, adding content
- UI Automation, adding content to text boxes
ms.assetid: 8bdd1a73-1ecb-4a05-a891-a7827ebb767f
ms.openlocfilehash: fdc52d0b94ce500b6560b60419d409f5cbd73b55
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69932642"
---
# <a name="add-content-to-a-text-box-using-ui-automation"></a><span data-ttu-id="8b463-102">使用 UI 自动化向文本框添加内容</span><span class="sxs-lookup"><span data-stu-id="8b463-102">Add Content to a Text Box Using UI Automation</span></span>
> [!NOTE]
> <span data-ttu-id="8b463-103">本文档适用于想要使用 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 命名空间中定义的托管 <xref:System.Windows.Automation> 类的 .NET Framework 开发人员。</span><span class="sxs-lookup"><span data-stu-id="8b463-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="8b463-104">有关的最新信息[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], 请[参阅 Windows 自动化 API:UI 自动化](https://go.microsoft.com/fwlink/?LinkID=156746)。</span><span class="sxs-lookup"><span data-stu-id="8b463-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="8b463-105">本主题包含演示如何使用[!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)]将文本插入单行文本框的示例代码。</span><span class="sxs-lookup"><span data-stu-id="8b463-105">This topic contains example code that demonstrates how to use [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] to insert text into a single-line text box.</span></span> <span data-ttu-id="8b463-106">为多行控件和丰富文本控件提供了一个替代方法, [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]这些控件不适用。</span><span class="sxs-lookup"><span data-stu-id="8b463-106">An alternate method is provided for multi-line and rich text controls where [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] is not applicable.</span></span> <span data-ttu-id="8b463-107">出于比较目的, 此示例还演示了如何使用 Win32 方法来实现相同的结果。</span><span class="sxs-lookup"><span data-stu-id="8b463-107">For comparison purposes, the example also demonstrates how to use Win32 methods to accomplish the same results.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8b463-108">示例</span><span class="sxs-lookup"><span data-stu-id="8b463-108">Example</span></span>  
 <span data-ttu-id="8b463-109">下面的示例逐步介绍目标应用程序中的一系列文本控件。</span><span class="sxs-lookup"><span data-stu-id="8b463-109">The following example steps through a sequence of text controls in a target application.</span></span> <span data-ttu-id="8b463-110">对每个文本控件进行测试, 以<xref:System.Windows.Automation.ValuePattern>查看是否可以<xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A>使用方法从对象获取对象。</span><span class="sxs-lookup"><span data-stu-id="8b463-110">Each text control is tested to see if a <xref:System.Windows.Automation.ValuePattern> object can be obtained from it using the <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> method.</span></span> <span data-ttu-id="8b463-111">如果文本控件支持<xref:System.Windows.Automation.ValuePattern> <xref:System.Windows.Automation.ValuePattern.SetValue%2A> , 则使用方法将用户定义的字符串插入到文本控件中。</span><span class="sxs-lookup"><span data-stu-id="8b463-111">If the text control does support <xref:System.Windows.Automation.ValuePattern>, the <xref:System.Windows.Automation.ValuePattern.SetValue%2A> method is used to insert a user-defined string into the text control.</span></span> <span data-ttu-id="8b463-112">否则, <xref:System.Windows.Forms.SendKeys.SendWait%2A?displayProperty=nameWithType>使用方法。</span><span class="sxs-lookup"><span data-stu-id="8b463-112">Otherwise, the <xref:System.Windows.Forms.SendKeys.SendWait%2A?displayProperty=nameWithType> method is used.</span></span>  
  
 [!code-csharp[InsertText#InsertText](../../../samples/snippets/csharp/VS_Snippets_Wpf/InsertText/CSharp/Window1.xaml.cs#inserttext)]
 [!code-vb[InsertText#InsertText](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InsertText/VisualBasic/Window1.xaml.vb#inserttext)]  
  
## <a name="see-also"></a><span data-ttu-id="8b463-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="8b463-113">See also</span></span>

- <span data-ttu-id="8b463-114">[TextPattern 插入文本示例](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms771478(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="8b463-114">[TextPattern Insert Text Sample](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms771478(v=vs.90))</span></span>
