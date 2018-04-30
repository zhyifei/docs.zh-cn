---
title: 查找列表项的 UI 自动化元素
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-bcl
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- list items, finding elements for
- elements, finding for list items
- UI Automation, finding elements for List items
ms.assetid: c326ad2b-2144-4f64-ae4c-d850c74f95c5
caps.latest.revision: 5
author: Xansky
ms.author: mhopkins
manager: markl
ms.workload:
- dotnet
ms.openlocfilehash: 727610b910cecbfa2b4c2eb1064fc357be822d42
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/30/2018
---
# <a name="find-a-ui-automation-element-for-a-list-item"></a>查找列表项的 UI 自动化元素
> [!NOTE]
>  本文档适用于想要使用 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 命名空间中定义的托管 <xref:System.Windows.Automation> 类的 .NET Framework 开发人员。 有关 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]的最新信息，请参阅 [Windows 自动化 API：UI 自动化](http://go.microsoft.com/fwlink/?LinkID=156746)。  
  
 本主题演示如何检索<xref:System.Windows.Automation.AutomationElement>为列表时已知的项的索引中的项。  
  
## <a name="example"></a>示例  
 下面的示例演示两种方法检索指定的项从列表中，一个使用<xref:System.Windows.Automation.TreeWalker>和其他使用<xref:System.Windows.Automation.AutomationElement.FindAll%2A>。  
  
 第一种方法往往是更快[!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)]控件，但第二个速度更快的 Windows Presentation Foundation (WPF) 控件。  
  
 [!code-csharp[UIAClient_snip#184](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#184)]
 [!code-vb[UIAClient_snip#184](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#184)]  
  
## <a name="see-also"></a>请参阅  
 [获取 UI 自动化元素](../../../docs/framework/ui-automation/obtaining-ui-automation-elements.md)
