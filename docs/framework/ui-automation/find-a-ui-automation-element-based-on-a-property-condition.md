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
ms.openlocfilehash: da455b10425c9e0b20a644679358dde469ed92e5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="find-a-ui-automation-element-based-on-a-property-condition"></a>基于属性条件查找 UI 自动化元素
> [!NOTE]
>  本文档适用于想要使用 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 命名空间中定义的托管 <xref:System.Windows.Automation> 类的 .NET Framework 开发人员。 有关 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]的最新信息，请参阅 [Windows 自动化 API：UI 自动化](http://go.microsoft.com/fwlink/?LinkID=156746)。  
  
 本主题包含的代码示例演示如何查找中的某个元素[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]树基于特定属性或属性。  
  
## <a name="example"></a>示例  
 在下面的示例中，指定一组属性条件是，它们可标识感兴趣的某些元素 （或元素） 中<xref:System.Windows.Automation.AutomationElement>树。 然后，搜索所有匹配的元素执行与<xref:System.Windows.Automation.AutomationElement.FindAll%2A>方法包含一系列<xref:System.Windows.Automation.AndCondition>布尔运算以限制匹配元素的数目。  
  
> [!NOTE]
>  从搜索时<xref:System.Windows.Automation.AutomationElement.RootElement%2A>，你应该尝试来仅获取直接子级。 对后代的搜索可能循环访问数百个甚至数千个元素，可能会导致堆栈溢出。 如果尝试在较低级别上获取特定元素，应该从应用程序窗口或者从较低级别的容器中开始搜索。  
  
 [!code-csharp[InvokePatternApp#1100](../../../samples/snippets/csharp/VS_Snippets_Wpf/InvokePatternApp/CSharp/InvokePatternApp.cs#1100)]
 [!code-vb[InvokePatternApp#1100](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InvokePatternApp/VisualBasic/Client.vb#1100)]  
  
## <a name="see-also"></a>请参阅  
 [InvokePattern 和 ExpandCollapsePattern 菜单项示例](http://msdn.microsoft.com/library/b7fa141c-e2d1-4da2-a27f-81a7d1172210)  
 [获取 UI 自动化元素](../../../docs/framework/ui-automation/obtaining-ui-automation-elements.md)  
 [使用 AutomationID 属性](../../../docs/framework/ui-automation/use-the-automationid-property.md)
