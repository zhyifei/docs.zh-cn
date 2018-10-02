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
ms.openlocfilehash: d948ff2f71ff7d4335cacc0fa3815dd75af4ad45
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/26/2018
ms.locfileid: "47231371"
---
# <a name="get-supported-ui-automation-control-patterns"></a>获取受支持的 UI 自动化控件模式
> [!NOTE]
>  本文档适用于想要使用 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 命名空间中定义的托管 <xref:System.Windows.Automation> 类的 .NET Framework 开发人员。 有关最新信息[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]，请参阅[Windows 自动化 API: UI 自动化](https://go.microsoft.com/fwlink/?LinkID=156746)。  
  
 本主题演示如何检索控件模式对象从[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]元素。  
  
### <a name="obtain-all-control-patterns"></a>获取所有控件模式  
  
1.  获取<xref:System.Windows.Automation.AutomationElement>您对其控件模式感兴趣。  
  
2.  调用<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>若要从元素中获取所有控件模式。  
  
> [!CAUTION]
>  强烈建议客户端不使用<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>。 因为此方法调用，性能会受到严重影响<xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A>在内部为每个现有的控件模式。 如果可能，应调用客户端<xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A>感兴趣的关键模式。  
  
### <a name="obtain-a-specific-control-pattern"></a>获取特定的控件模式  
  
1.  获取<xref:System.Windows.Automation.AutomationElement>您对其控件模式感兴趣。  
  
2.  调用<xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A>或<xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A>特定模式的查询。 这些方法非常相似，但是，如果找不到模式，<xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A>引发异常，并<xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A>返回`false`。  
  
## <a name="example"></a>示例  
 下面的示例检索<xref:System.Windows.Automation.AutomationElement>列表项，并获取<xref:System.Windows.Automation.SelectionItemPattern>从该元素。  
  
 [!code-csharp[UIAClient_snip#103](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#103)]
 [!code-vb[UIAClient_snip#103](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#103)]  
  
## <a name="see-also"></a>请参阅  
 [客户端的 UI 自动化控件模式](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)
