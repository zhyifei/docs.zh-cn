---
title: 获取 UI 自动化元素的属性
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- properties, retrieving
- UI Automation, retrieving properties of elements
ms.assetid: 09576b1a-291f-435c-980e-dee32d899ae1
ms.openlocfilehash: e3b3b118c3db95f55c67c2b27149734efc8cbea8
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69968966"
---
# <a name="get-ui-automation-element-properties"></a>获取 UI 自动化元素的属性
> [!NOTE]
> 本文档适用于想要使用 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 命名空间中定义的托管 <xref:System.Windows.Automation> 类的 .NET Framework 开发人员。 有关的最新信息[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], 请[参阅 Windows 自动化 API:UI 自动化](https://go.microsoft.com/fwlink/?LinkID=156746)。  
  
 本主题说明如何检索[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]元素的属性。  
  
### <a name="get-a-current-property-value"></a>获取当前属性值  
  
1. 获取要<xref:System.Windows.Automation.AutomationElement>获取其属性的。  
  
2. 调用<xref:System.Windows.Automation.AutomationElement.GetCurrentPropertyValue%2A>或<xref:System.Windows.Automation.AutomationElement.Current%2A>检索属性结构, 并从其成员之一获取值。  
  
### <a name="get-a-cached-property-value"></a>获取缓存的属性值  
  
1. 获取要<xref:System.Windows.Automation.AutomationElement>获取其属性的。 必须已在中<xref:System.Windows.Automation.CacheRequest>指定了属性。  
  
2. 调用<xref:System.Windows.Automation.AutomationElement.GetCachedPropertyValue%2A>或<xref:System.Windows.Automation.AutomationElement.Cached%2A>检索属性结构, 并从其成员之一获取值。  
  
## <a name="example"></a>示例  
 下面的示例演示了检索的当前属性的<xref:System.Windows.Automation.AutomationElement>各种方法。  
  
 [!code-csharp[UIAClient_snip#170](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#170)]
 [!code-vb[UIAClient_snip#170](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#170)]  
  
## <a name="see-also"></a>请参阅

- [客户端的 UI 自动化属性](../../../docs/framework/ui-automation/ui-automation-properties-for-clients.md)
- [在 UI 自动化中使用缓存](../../../docs/framework/ui-automation/use-caching-in-ui-automation.md)
- [在 UI 自动化客户端中缓存](../../../docs/framework/ui-automation/caching-in-ui-automation-clients.md)
