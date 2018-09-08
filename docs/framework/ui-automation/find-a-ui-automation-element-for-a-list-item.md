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
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: b569b43d83e8a7f1b0fa82b79bc1fc40977b72ba
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/08/2018
ms.locfileid: "44210008"
---
# <a name="find-a-ui-automation-element-for-a-list-item"></a>查找列表项的 UI 自动化元素
> [!NOTE]
>  本文档适用于想要使用 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 命名空间中定义的托管 <xref:System.Windows.Automation> 类的 .NET Framework 开发人员。 有关最新信息[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]，请参阅[Windows 自动化 API: UI 自动化](https://go.microsoft.com/fwlink/?LinkID=156746)。  
  
 本主题演示如何检索<xref:System.Windows.Automation.AutomationElement>列表时已知的项的索引中的项。  
  
## <a name="example"></a>示例  
 下面的示例演示两种方法来检索从列表中，一个使用指定的项<xref:System.Windows.Automation.TreeWalker>和其他使用<xref:System.Windows.Automation.AutomationElement.FindAll%2A>。  
  
 第一种方法往往能更快地[!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)]控件，但第二个是更快地为 Windows Presentation Foundation (WPF) 控件。  
  
 [!code-csharp[UIAClient_snip#184](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#184)]
 [!code-vb[UIAClient_snip#184](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#184)]  
  
## <a name="see-also"></a>请参阅  
 [获取 UI 自动化元素](../../../docs/framework/ui-automation/obtaining-ui-automation-elements.md)
