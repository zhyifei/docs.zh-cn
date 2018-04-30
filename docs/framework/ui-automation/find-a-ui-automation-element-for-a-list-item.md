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
# <a name="find-a-ui-automation-element-for-a-list-item"></a><span data-ttu-id="7ca51-102">查找列表项的 UI 自动化元素</span><span class="sxs-lookup"><span data-stu-id="7ca51-102">Find a UI Automation Element for a List Item</span></span>
> [!NOTE]
>  <span data-ttu-id="7ca51-103">本文档适用于想要使用 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 命名空间中定义的托管 <xref:System.Windows.Automation> 类的 .NET Framework 开发人员。</span><span class="sxs-lookup"><span data-stu-id="7ca51-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="7ca51-104">有关 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]的最新信息，请参阅 [Windows 自动化 API：UI 自动化](http://go.microsoft.com/fwlink/?LinkID=156746)。</span><span class="sxs-lookup"><span data-stu-id="7ca51-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](http://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="7ca51-105">本主题演示如何检索<xref:System.Windows.Automation.AutomationElement>为列表时已知的项的索引中的项。</span><span class="sxs-lookup"><span data-stu-id="7ca51-105">This topic shows how to retrieve an <xref:System.Windows.Automation.AutomationElement> for an item within a list when the index of the item is known.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7ca51-106">示例</span><span class="sxs-lookup"><span data-stu-id="7ca51-106">Example</span></span>  
 <span data-ttu-id="7ca51-107">下面的示例演示两种方法检索指定的项从列表中，一个使用<xref:System.Windows.Automation.TreeWalker>和其他使用<xref:System.Windows.Automation.AutomationElement.FindAll%2A>。</span><span class="sxs-lookup"><span data-stu-id="7ca51-107">The following example shows two ways of retrieving a specified item from a list, one using <xref:System.Windows.Automation.TreeWalker> and the other using <xref:System.Windows.Automation.AutomationElement.FindAll%2A>.</span></span>  
  
 <span data-ttu-id="7ca51-108">第一种方法往往是更快[!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)]控件，但第二个速度更快的 Windows Presentation Foundation (WPF) 控件。</span><span class="sxs-lookup"><span data-stu-id="7ca51-108">The first technique tends to be faster for [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] controls, but the second is faster for Windows Presentation Foundation (WPF) controls.</span></span>  
  
 [!code-csharp[UIAClient_snip#184](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#184)]
 [!code-vb[UIAClient_snip#184](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#184)]  
  
## <a name="see-also"></a><span data-ttu-id="7ca51-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="7ca51-109">See Also</span></span>  
 [<span data-ttu-id="7ca51-110">获取 UI 自动化元素</span><span class="sxs-lookup"><span data-stu-id="7ca51-110">Obtaining UI Automation Elements</span></span>](../../../docs/framework/ui-automation/obtaining-ui-automation-elements.md)
