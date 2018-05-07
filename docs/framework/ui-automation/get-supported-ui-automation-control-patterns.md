---
title: 获取受支持的 UI 自动化控件模式
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- control patterns, getting
- UI Automation, getting control patterns
- getting, control patterns
ms.assetid: 006c54c9-50bf-48d9-a855-9d62eb95603a
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: fe492aa322f005e3bd118031e97e3837e3314093
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="get-supported-ui-automation-control-patterns"></a>获取受支持的 UI 自动化控件模式
> [!NOTE]
>  本文档适用于想要使用 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 命名空间中定义的托管 <xref:System.Windows.Automation> 类的 .NET Framework 开发人员。 有关 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]的最新信息，请参阅 [Windows 自动化 API：UI 自动化](http://go.microsoft.com/fwlink/?LinkID=156746)。  
  
 本主题演示如何检索控件模式对象从[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]元素。  
  
### <a name="obtain-all-control-patterns"></a>获取所有控件模式  
  
1.  获取<xref:System.Windows.Automation.AutomationElement>你对其控件模式感兴趣。  
  
2.  调用<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>若要从该元素获取所有控件模式。  
  
> [!CAUTION]
>  强烈建议客户端不使用<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>。 与此方法调用，性能会受到严重影响<xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A>内部的每个现有的控件模式。 如果可能，应调用客户端<xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A>针对感兴趣的关键模式。  
  
### <a name="obtain-a-specific-control-pattern"></a>获取特定的控件模式  
  
1.  获取<xref:System.Windows.Automation.AutomationElement>你对其控件模式感兴趣。  
  
2.  调用<xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A>或<xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A>以查询特定模式。 这些方法非常相似，但是，如果未找到该模式，<xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A>引发异常，和<xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A>返回`false`。  
  
## <a name="example"></a>示例  
 下面的示例检索<xref:System.Windows.Automation.AutomationElement>的列表项，并获取<xref:System.Windows.Automation.SelectionItemPattern>从该元素。  
  
 [!code-csharp[UIAClient_snip#103](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#103)]
 [!code-vb[UIAClient_snip#103](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#103)]  
  
## <a name="see-also"></a>请参阅  
 [客户端的 UI 自动化控件模式](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)
