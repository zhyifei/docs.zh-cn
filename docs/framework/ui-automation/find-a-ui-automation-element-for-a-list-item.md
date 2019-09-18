---
title: 查找列表项的 UI 自动化元素
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- list items, finding elements for
- elements, finding for list items
- UI Automation, finding elements for List items
ms.assetid: c326ad2b-2144-4f64-ae4c-d850c74f95c5
ms.openlocfilehash: 2b9fb1ffe4b20074de66afe6d418a7cf5d39be0c
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/17/2019
ms.locfileid: "71043717"
---
# <a name="find-a-ui-automation-element-for-a-list-item"></a>查找列表项的 UI 自动化元素
> [!NOTE]
> 本文档适用于想要使用 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 命名空间中定义的托管 <xref:System.Windows.Automation> 类的 .NET Framework 开发人员。 有关的最新信息[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], 请[参阅 Windows 自动化 API:UI 自动化](https://go.microsoft.com/fwlink/?LinkID=156746)。  
  
 本主题演示如何在已知项<xref:System.Windows.Automation.AutomationElement>的索引时检索列表中的项。  
  
## <a name="example"></a>示例  
 下面的示例演示了两种方法，用于从列表中检索指定的项<xref:System.Windows.Automation.TreeWalker> ，一个使用， <xref:System.Windows.Automation.AutomationElement.FindAll%2A>另一个使用。  
  
 第一种方法倾向于控件的[!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)]速度更快，但第二种方法更快 Windows Presentation Foundation （WPF）控件。  
  
 [!code-csharp[UIAClient_snip#184](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#184)]
 [!code-vb[UIAClient_snip#184](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#184)]  
  
## <a name="see-also"></a>请参阅

- [获取 UI 自动化元素](obtaining-ui-automation-elements.md)
