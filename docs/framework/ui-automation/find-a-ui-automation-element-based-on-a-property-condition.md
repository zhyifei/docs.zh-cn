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
ms.openlocfilehash: 3ca609551955b32ad8b63296975ce10f097d9c30
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74433589"
---
# <a name="find-a-ui-automation-element-based-on-a-property-condition"></a>基于属性条件查找 UI 自动化元素
> [!NOTE]
> 本文档适用于想要使用 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 命名空间中定义的托管 <xref:System.Windows.Automation> 类的 .NET Framework 开发人员。 有关 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]的最新信息，请参阅 [Windows 自动化 API：UI 自动化](/windows/win32/winauto/entry-uiauto-win32)。  
  
 本主题包含示例代码，该代码演示如何基于特定属性在 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 树中查找元素。  
  
## <a name="example"></a>示例  
 在下面的示例中，指定了一组属性条件，这些条件标识在 <xref:System.Windows.Automation.AutomationElement> 树中感兴趣的某个元素（或元素）。 然后，将使用 <xref:System.Windows.Automation.AutomationElement.FindAll%2A> 方法对所有匹配元素执行搜索，该方法包含一系列 <xref:System.Windows.Automation.AndCondition> 布尔运算来限制匹配元素的数目。  
  
> [!NOTE]
> 从 <xref:System.Windows.Automation.AutomationElement.RootElement%2A>搜索时，应尝试仅获取直接子级。 对后代的搜索可能循环访问数百个甚至数千个元素，这可能导致堆栈溢出。 如果尝试在较低级别上获取特定元素，应该从应用程序窗口或者从较低级别的容器中开始搜索。  
  
 [!code-csharp[InvokePatternApp#1100](../../../samples/snippets/csharp/VS_Snippets_Wpf/InvokePatternApp/CSharp/InvokePatternApp.cs#1100)]
 [!code-vb[InvokePatternApp#1100](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InvokePatternApp/VisualBasic/Client.vb#1100)]  
  
## <a name="see-also"></a>另请参阅

- [InvokePattern 和 ExpandCollapsePattern 菜单项示例](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms771636(v=vs.90))
- [Obtaining UI Automation Elements](obtaining-ui-automation-elements.md)
- [使用 AutomationID 属性](use-the-automationid-property.md)
