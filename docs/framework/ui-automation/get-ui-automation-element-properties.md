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
ms.openlocfilehash: 1b82302ff89d2e8407871cbfba6c10e8322ac4e7
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74435496"
---
# <a name="get-ui-automation-element-properties"></a>获取 UI 自动化元素的属性
> [!NOTE]
> 本文档适用于想要使用 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 命名空间中定义的托管 <xref:System.Windows.Automation> 类的 .NET Framework 开发人员。 有关 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]的最新信息，请参阅 [Windows 自动化 API：UI 自动化](/windows/win32/winauto/entry-uiauto-win32)。  
  
 本主题演示如何检索 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 元素的属性。  
  
### <a name="get-a-current-property-value"></a>获取当前属性值  
  
1. 获取要获取其属性的 <xref:System.Windows.Automation.AutomationElement>。  
  
2. 调用 <xref:System.Windows.Automation.AutomationElement.GetCurrentPropertyValue%2A>，或检索 <xref:System.Windows.Automation.AutomationElement.Current%2A> 属性结构并从其成员之一获取值。  
  
### <a name="get-a-cached-property-value"></a>获取缓存的属性值  
  
1. 获取要获取其属性的 <xref:System.Windows.Automation.AutomationElement>。 必须已在 <xref:System.Windows.Automation.CacheRequest>中指定了属性。  
  
2. 调用 <xref:System.Windows.Automation.AutomationElement.GetCachedPropertyValue%2A>，或检索 <xref:System.Windows.Automation.AutomationElement.Cached%2A> 属性结构并从其成员之一获取值。  
  
## <a name="example"></a>示例  
 下面的示例演示了检索 <xref:System.Windows.Automation.AutomationElement>的当前属性的各种方法。  
  
 [!code-csharp[UIAClient_snip#170](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#170)]
 [!code-vb[UIAClient_snip#170](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#170)]  
  
## <a name="see-also"></a>另请参阅

- [UI Automation Properties for Clients](ui-automation-properties-for-clients.md)
- [在 UI 自动化中使用缓存](use-caching-in-ui-automation.md)
- [Caching in UI Automation Clients](caching-in-ui-automation-clients.md)
