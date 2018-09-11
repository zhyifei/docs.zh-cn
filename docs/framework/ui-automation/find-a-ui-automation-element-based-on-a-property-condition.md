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
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: 4c4f14f79960b98618a4f6a3450b1e1a2c05f731
ms.sourcegitcommit: 67de6cb5dd66a19f2180ba7e4d7aecc697f8a963
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2018
ms.locfileid: "44339404"
---
# <a name="find-a-ui-automation-element-based-on-a-property-condition"></a><span data-ttu-id="ff9b2-102">基于属性条件查找 UI 自动化元素</span><span class="sxs-lookup"><span data-stu-id="ff9b2-102">Find a UI Automation Element Based on a Property Condition</span></span>
> [!NOTE]
>  <span data-ttu-id="ff9b2-103">本文档适用于想要使用 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 命名空间中定义的托管 <xref:System.Windows.Automation> 类的 .NET Framework 开发人员。</span><span class="sxs-lookup"><span data-stu-id="ff9b2-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="ff9b2-104">有关最新信息[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]，请参阅[Windows 自动化 API: UI 自动化](https://go.microsoft.com/fwlink/?LinkID=156746)。</span><span class="sxs-lookup"><span data-stu-id="ff9b2-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="ff9b2-105">本主题包含代码示例演示如何查找中的某个元素[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]基于树的特定属性或属性。</span><span class="sxs-lookup"><span data-stu-id="ff9b2-105">This topic contains example code that shows how to locate an element within the [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] tree based on a specific property or properties.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ff9b2-106">示例</span><span class="sxs-lookup"><span data-stu-id="ff9b2-106">Example</span></span>  
 <span data-ttu-id="ff9b2-107">在以下示例中，一系列属性条件，用于标识感兴趣的某些元素 （或元素） 中指定<xref:System.Windows.Automation.AutomationElement>树。</span><span class="sxs-lookup"><span data-stu-id="ff9b2-107">In the following example, a set of property conditions are specified that identify a certain element (or elements) of interest in the <xref:System.Windows.Automation.AutomationElement> tree.</span></span> <span data-ttu-id="ff9b2-108">然后执行搜索的所有匹配的元素<xref:System.Windows.Automation.AutomationElement.FindAll%2A>方法，其中包含一系列<xref:System.Windows.Automation.AndCondition>布尔运算以限制匹配的元素数。</span><span class="sxs-lookup"><span data-stu-id="ff9b2-108">A search for all matching elements is then performed with the <xref:System.Windows.Automation.AutomationElement.FindAll%2A> method that incorporates a series of <xref:System.Windows.Automation.AndCondition> boolean operations to limit the number of matching elements.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ff9b2-109">从搜索时<xref:System.Windows.Automation.AutomationElement.RootElement%2A>，应尝试仅获取直接子级。</span><span class="sxs-lookup"><span data-stu-id="ff9b2-109">When searching from the <xref:System.Windows.Automation.AutomationElement.RootElement%2A>, you should try to obtain only direct children.</span></span> <span data-ttu-id="ff9b2-110">对后代的搜索可能循环访问数百个甚至数千个元素，从而可能会导致堆栈溢出。</span><span class="sxs-lookup"><span data-stu-id="ff9b2-110">A search for descendants might iterate through hundreds or even thousands of elements, possibly resulting in a stack overflow.</span></span> <span data-ttu-id="ff9b2-111">如果尝试在较低级别上获取特定元素，应该从应用程序窗口或者从较低级别的容器中开始搜索。</span><span class="sxs-lookup"><span data-stu-id="ff9b2-111">If you are attempting to obtain a specific element at a lower level, you should start your search from the application window or from a container at a lower level.</span></span>  
  
 [!code-csharp[InvokePatternApp#1100](../../../samples/snippets/csharp/VS_Snippets_Wpf/InvokePatternApp/CSharp/InvokePatternApp.cs#1100)]
 [!code-vb[InvokePatternApp#1100](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InvokePatternApp/VisualBasic/Client.vb#1100)]  
  
## <a name="see-also"></a><span data-ttu-id="ff9b2-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="ff9b2-112">See Also</span></span>  
 [<span data-ttu-id="ff9b2-113">InvokePattern 和 ExpandCollapsePattern 菜单项示例</span><span class="sxs-lookup"><span data-stu-id="ff9b2-113">InvokePattern and ExpandCollapsePattern Menu Item Sample</span></span>](https://msdn.microsoft.com/library/b7fa141c-e2d1-4da2-a27f-81a7d1172210)  
 [<span data-ttu-id="ff9b2-114">获取 UI 自动化元素</span><span class="sxs-lookup"><span data-stu-id="ff9b2-114">Obtaining UI Automation Elements</span></span>](../../../docs/framework/ui-automation/obtaining-ui-automation-elements.md)  
 [<span data-ttu-id="ff9b2-115">使用 AutomationID 属性</span><span class="sxs-lookup"><span data-stu-id="ff9b2-115">Use the AutomationID Property</span></span>](../../../docs/framework/ui-automation/use-the-automationid-property.md)
