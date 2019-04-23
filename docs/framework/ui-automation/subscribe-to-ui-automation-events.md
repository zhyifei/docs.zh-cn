---
title: 订阅 UI 自动化事件
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- UI Automation, subscribing to events
- subscribing to UI Automation events
- events, subscribing to
- listening for events
ms.assetid: b688effa-b3e8-4b05-944d-05ed89a245aa
ms.openlocfilehash: 9c5308192ca122e9c25fa8e845f2b8f89345dda8
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59168462"
---
# <a name="subscribe-to-ui-automation-events"></a><span data-ttu-id="0eb1d-102">订阅 UI 自动化事件</span><span class="sxs-lookup"><span data-stu-id="0eb1d-102">Subscribe to UI Automation Events</span></span>
> [!NOTE]
>  <span data-ttu-id="0eb1d-103">本文档适用于想要使用 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 命名空间中定义的托管 <xref:System.Windows.Automation> 类的 .NET Framework 开发人员。</span><span class="sxs-lookup"><span data-stu-id="0eb1d-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="0eb1d-104">有关最新信息[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]，请参阅[Windows 自动化 API:UI 自动化](https://go.microsoft.com/fwlink/?LinkID=156746)。</span><span class="sxs-lookup"><span data-stu-id="0eb1d-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="0eb1d-105">本主题演示如何订阅 UI 自动化提供程序引发的事件。</span><span class="sxs-lookup"><span data-stu-id="0eb1d-105">This topic shows how to subscribe to events raised by UI Automation providers.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0eb1d-106">示例</span><span class="sxs-lookup"><span data-stu-id="0eb1d-106">Example</span></span>  
 <span data-ttu-id="0eb1d-107">下面的代码示例为调用控件（如按钮）时引发的事件注册事件处理程序，并在应用程序窗体关闭时删除该事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="0eb1d-107">The following example code registers an event handler for the event that is raised when a control such as a button is invoked, and removes it when the application form closes.</span></span> <span data-ttu-id="0eb1d-108">事件由作为参数传递到 <xref:System.Windows.Automation.Automation.AddAutomationEventHandler%2A> 的 <xref:System.Windows.Automation.AutomationEvent> 标识。</span><span class="sxs-lookup"><span data-stu-id="0eb1d-108">The event is identified by an <xref:System.Windows.Automation.AutomationEvent> passed as a parameter to <xref:System.Windows.Automation.Automation.AddAutomationEventHandler%2A>.</span></span>  
  
 [!code-csharp[UIAClient_snip#101](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#101)]
 [!code-vb[UIAClient_snip#101](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#101)]  
  
## <a name="example"></a><span data-ttu-id="0eb1d-109">示例</span><span class="sxs-lookup"><span data-stu-id="0eb1d-109">Example</span></span>  
 <span data-ttu-id="0eb1d-110">下面的示例演示如何使用 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] 来订阅当焦点更改时引发的事件。</span><span class="sxs-lookup"><span data-stu-id="0eb1d-110">The following example shows how to use [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] to subscribe to an event that is raised when the focus changes.</span></span> <span data-ttu-id="0eb1d-111">事件处理程序将在可在应用程序关闭时调用的方法中注销，或在不再需要 UI 事件通知时注销。</span><span class="sxs-lookup"><span data-stu-id="0eb1d-111">The event handler is unregistered in a method that could be called on application shutdown, or when notification of UI events is no longer required.</span></span>  
  
 [!code-csharp[UIAClient_snip#102](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#102)]
 [!code-vb[UIAClient_snip#102](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#102)]  
  
## <a name="see-also"></a><span data-ttu-id="0eb1d-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="0eb1d-112">See also</span></span>

- <xref:System.Windows.Automation.Automation.AddAutomationEventHandler%2A>
- <xref:System.Windows.Automation.Automation.RemoveAllEventHandlers%2A>
- <xref:System.Windows.Automation.Automation.RemoveAutomationEventHandler%2A>
- [<span data-ttu-id="0eb1d-113">UI 自动化事件概述</span><span class="sxs-lookup"><span data-stu-id="0eb1d-113">UI Automation Events Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-events-overview.md)
