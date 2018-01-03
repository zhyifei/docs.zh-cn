---
title: "订阅 UI 自动化事件"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- UI Automation, subscribing to events
- subscribing to UI Automation events
- events, subscribing to
- listening for events
ms.assetid: b688effa-b3e8-4b05-944d-05ed89a245aa
caps.latest.revision: "16"
author: Xansky
ms.author: mhopkins
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 688ec0ba33b018eaba2f7293127c3869fcf5df48
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="subscribe-to-ui-automation-events"></a><span data-ttu-id="b1dbb-102">订阅 UI 自动化事件</span><span class="sxs-lookup"><span data-stu-id="b1dbb-102">Subscribe to UI Automation Events</span></span>
> [!NOTE]
>  <span data-ttu-id="b1dbb-103">本文档适用于想要使用 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 命名空间中定义的托管 <xref:System.Windows.Automation> 类的 .NET Framework 开发人员。</span><span class="sxs-lookup"><span data-stu-id="b1dbb-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="b1dbb-104">有关 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]的最新信息，请参阅 [Windows 自动化 API：UI 自动化](http://go.microsoft.com/fwlink/?LinkID=156746)。</span><span class="sxs-lookup"><span data-stu-id="b1dbb-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](http://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="b1dbb-105">本主题演示如何订阅 UI 自动化提供程序引发的事件。</span><span class="sxs-lookup"><span data-stu-id="b1dbb-105">This topic shows how to subscribe to events raised by UI Automation providers.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b1dbb-106">示例</span><span class="sxs-lookup"><span data-stu-id="b1dbb-106">Example</span></span>  
 <span data-ttu-id="b1dbb-107">下面的代码示例为调用控件（如按钮）时引发的事件注册事件处理程序，并在应用程序窗体关闭时删除该事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="b1dbb-107">The following example code registers an event handler for the event that is raised when a control such as a button is invoked, and removes it when the application form closes.</span></span> <span data-ttu-id="b1dbb-108">事件由<xref:System.Windows.Automation.AutomationEvent>传递作为参数传递给<xref:System.Windows.Automation.Automation.AddAutomationEventHandler%2A>。</span><span class="sxs-lookup"><span data-stu-id="b1dbb-108">The event is identified by an <xref:System.Windows.Automation.AutomationEvent> passed as a parameter to <xref:System.Windows.Automation.Automation.AddAutomationEventHandler%2A>.</span></span>  
  
 [!code-csharp[UIAClient_snip#101](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#101)]
 [!code-vb[UIAClient_snip#101](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#101)]  
  
## <a name="example"></a><span data-ttu-id="b1dbb-109">示例</span><span class="sxs-lookup"><span data-stu-id="b1dbb-109">Example</span></span>  
 <span data-ttu-id="b1dbb-110">下面的示例演示如何使用[!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)]来订阅当焦点更改时引发事件。</span><span class="sxs-lookup"><span data-stu-id="b1dbb-110">The following example shows how to use [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] to subscribe to an event that is raised when the focus changes.</span></span> <span data-ttu-id="b1dbb-111">事件处理程序将在可在应用程序关闭时调用的方法中注销，或在不再需要 UI 事件通知时注销。</span><span class="sxs-lookup"><span data-stu-id="b1dbb-111">The event handler is unregistered in a method that could be called on application shutdown, or when notification of UI events is no longer required.</span></span>  
  
 [!code-csharp[UIAClient_snip#102](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#102)]
 [!code-vb[UIAClient_snip#102](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#102)]  
  
## <a name="see-also"></a><span data-ttu-id="b1dbb-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="b1dbb-112">See Also</span></span>  
 <xref:System.Windows.Automation.Automation.AddAutomationEventHandler%2A>  
 <xref:System.Windows.Automation.Automation.RemoveAllEventHandlers%2A>  
 <xref:System.Windows.Automation.Automation.RemoveAutomationEventHandler%2A>  
 [<span data-ttu-id="b1dbb-113">UI 自动化事件概述</span><span class="sxs-lookup"><span data-stu-id="b1dbb-113">UI Automation Events Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-events-overview.md)
