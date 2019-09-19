---
title: 基于属性条件查找 UI 自动化元素
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- elements, finding by property conditions
- UI Automation, finding elements by property conditions
ms.assetid: 3acaee5a-6ce8-4c3e-81c8-67e59eb74477
ms.openlocfilehash: 536a71532f02782f9e84bb2bd086af212a77c0da
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/17/2019
ms.locfileid: "71043668"
---
# <a name="find-a-ui-automation-element-based-on-a-property-condition"></a><span data-ttu-id="4ce11-102">基于属性条件查找 UI 自动化元素</span><span class="sxs-lookup"><span data-stu-id="4ce11-102">Find a UI Automation Element Based on a Property Condition</span></span>
> [!NOTE]
> <span data-ttu-id="4ce11-103">本文档适用于想要使用 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 命名空间中定义的托管 <xref:System.Windows.Automation> 类的 .NET Framework 开发人员。</span><span class="sxs-lookup"><span data-stu-id="4ce11-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="4ce11-104">有关的最新信息[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], 请[参阅 Windows 自动化 API:UI 自动化](https://go.microsoft.com/fwlink/?LinkID=156746)。</span><span class="sxs-lookup"><span data-stu-id="4ce11-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="4ce11-105">本主题包含示例代码，该代码演示如何基于特定属性在[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]树中查找元素。</span><span class="sxs-lookup"><span data-stu-id="4ce11-105">This topic contains example code that shows how to locate an element within the [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] tree based on a specific property or properties.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4ce11-106">示例</span><span class="sxs-lookup"><span data-stu-id="4ce11-106">Example</span></span>  
 <span data-ttu-id="4ce11-107">在下面的示例中，指定了一组属性条件，这些条件标识<xref:System.Windows.Automation.AutomationElement>树中感兴趣的某个元素（或元素）。</span><span class="sxs-lookup"><span data-stu-id="4ce11-107">In the following example, a set of property conditions are specified that identify a certain element (or elements) of interest in the <xref:System.Windows.Automation.AutomationElement> tree.</span></span> <span data-ttu-id="4ce11-108">然后，将使用<xref:System.Windows.Automation.AutomationElement.FindAll%2A>合并一<xref:System.Windows.Automation.AndCondition>系列布尔操作的方法对所有匹配元素执行搜索，以限制匹配元素的数目。</span><span class="sxs-lookup"><span data-stu-id="4ce11-108">A search for all matching elements is then performed with the <xref:System.Windows.Automation.AutomationElement.FindAll%2A> method that incorporates a series of <xref:System.Windows.Automation.AndCondition> boolean operations to limit the number of matching elements.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4ce11-109">在从<xref:System.Windows.Automation.AutomationElement.RootElement%2A>中搜索时，应尝试仅获取直接子级。</span><span class="sxs-lookup"><span data-stu-id="4ce11-109">When searching from the <xref:System.Windows.Automation.AutomationElement.RootElement%2A>, you should try to obtain only direct children.</span></span> <span data-ttu-id="4ce11-110">对后代的搜索可能循环访问数百个甚至数千个元素，这可能导致堆栈溢出。</span><span class="sxs-lookup"><span data-stu-id="4ce11-110">A search for descendants might iterate through hundreds or even thousands of elements, possibly resulting in a stack overflow.</span></span> <span data-ttu-id="4ce11-111">如果尝试在较低级别上获取特定元素，应该从应用程序窗口或者从较低级别的容器中开始搜索。</span><span class="sxs-lookup"><span data-stu-id="4ce11-111">If you are attempting to obtain a specific element at a lower level, you should start your search from the application window or from a container at a lower level.</span></span>  
  
 [!code-csharp[InvokePatternApp#1100](../../../samples/snippets/csharp/VS_Snippets_Wpf/InvokePatternApp/CSharp/InvokePatternApp.cs#1100)]
 [!code-vb[InvokePatternApp#1100](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InvokePatternApp/VisualBasic/Client.vb#1100)]  
  
## <a name="see-also"></a><span data-ttu-id="4ce11-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="4ce11-112">See also</span></span>

- <span data-ttu-id="4ce11-113">[InvokePattern 和 ExpandCollapsePattern 菜单项示例](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms771636(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="4ce11-113">[InvokePattern and ExpandCollapsePattern Menu Item Sample](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms771636(v=vs.90))</span></span>
- [<span data-ttu-id="4ce11-114">获取 UI 自动化元素</span><span class="sxs-lookup"><span data-stu-id="4ce11-114">Obtaining UI Automation Elements</span></span>](obtaining-ui-automation-elements.md)
- [<span data-ttu-id="4ce11-115">使用 AutomationID 属性</span><span class="sxs-lookup"><span data-stu-id="4ce11-115">Use the AutomationID Property</span></span>](use-the-automationid-property.md)
