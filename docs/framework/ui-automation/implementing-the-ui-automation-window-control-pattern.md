---
title: 实现 UI 自动化 Window 控件模式
ms.date: 03/30/2017
helpviewer_keywords:
- control patterns, Window
- UI Automation, Window control pattern
- Window control pattern
ms.assetid: a28cb286-296e-4a62-b4cb-55ad636ebccc
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: 73a484ea6165b4e38901630730c7ba985a5608ba
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="implementing-the-ui-automation-window-control-pattern"></a><span data-ttu-id="5bcef-102">实现 UI 自动化 Window 控件模式</span><span class="sxs-lookup"><span data-stu-id="5bcef-102">Implementing the UI Automation Window Control Pattern</span></span>
> [!NOTE]
>  <span data-ttu-id="5bcef-103">本文档适用于想要使用 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 命名空间中定义的托管 <xref:System.Windows.Automation> 类的 .NET Framework 开发人员。</span><span class="sxs-lookup"><span data-stu-id="5bcef-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="5bcef-104">有关 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]的最新信息，请参阅 [Windows 自动化 API：UI 自动化](http://go.microsoft.com/fwlink/?LinkID=156746)。</span><span class="sxs-lookup"><span data-stu-id="5bcef-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](http://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="5bcef-105">本主题介绍实现 <xref:System.Windows.Automation.Provider.IWindowProvider>的准则和约定，包括有关 <xref:System.Windows.Automation.WindowPattern> 属性、方法和事件的信息。</span><span class="sxs-lookup"><span data-stu-id="5bcef-105">This topic introduces guidelines and conventions for implementing <xref:System.Windows.Automation.Provider.IWindowProvider>, including information about <xref:System.Windows.Automation.WindowPattern> properties, methods, and events.</span></span> <span data-ttu-id="5bcef-106">本主题的结尾列出了指向其他参考资料的链接。</span><span class="sxs-lookup"><span data-stu-id="5bcef-106">Links to additional references are listed at the end of the topic.</span></span>  
  
 <span data-ttu-id="5bcef-107"><xref:System.Windows.Automation.WindowPattern> 控件模式用于支持在传统的 [!INCLUDE[TLA#tla_gui](../../../includes/tlasharptla-gui-md.md)]内提供基于基本窗口的功能的控件。</span><span class="sxs-lookup"><span data-stu-id="5bcef-107">The <xref:System.Windows.Automation.WindowPattern> control pattern is used to support controls that provide fundamental window-based functionality within a traditional [!INCLUDE[TLA#tla_gui](../../../includes/tlasharptla-gui-md.md)].</span></span> <span data-ttu-id="5bcef-108">必须实现此控件模式的控件示例包括顶级应用程序窗口、 [!INCLUDE[TLA#tla_mdi](../../../includes/tlasharptla-mdi-md.md)] 子窗口、大小可调的拆分窗格控件、模式对话框和气球状帮助窗口。</span><span class="sxs-lookup"><span data-stu-id="5bcef-108">Examples of controls that must implement this control pattern include top-level application windows, [!INCLUDE[TLA#tla_mdi](../../../includes/tlasharptla-mdi-md.md)] child windows, resizable split pane controls, modal dialogs and balloon help windows.</span></span>  
  
<a name="Implementation_Guidelines_and_Conventions"></a>   
## <a name="implementation-guidelines-and-conventions"></a><span data-ttu-id="5bcef-109">实现准则和约定</span><span class="sxs-lookup"><span data-stu-id="5bcef-109">Implementation Guidelines and Conventions</span></span>  
 <span data-ttu-id="5bcef-110">在实现 Window 控件模式时，请注意以下准则和约定：</span><span class="sxs-lookup"><span data-stu-id="5bcef-110">When implementing the Window control pattern, note the following guidelines and conventions:</span></span>  
  
-   <span data-ttu-id="5bcef-111">为了能够使用 UI 自动化同时修改窗口大小和屏幕位置，除了 <xref:System.Windows.Automation.Provider.ITransformProvider> 外，控件还必须实现 <xref:System.Windows.Automation.Provider.IWindowProvider>。</span><span class="sxs-lookup"><span data-stu-id="5bcef-111">To support the ability to modify both window size and screen position using UI Automation, a control must implement <xref:System.Windows.Automation.Provider.ITransformProvider> in addition to <xref:System.Windows.Automation.Provider.IWindowProvider>.</span></span>  
  
-   <span data-ttu-id="5bcef-112">包含标题栏和标题栏元素（使控件能够移动、调整大小、最大化、最小化或关闭）的控件通常需要实现 <xref:System.Windows.Automation.Provider.IWindowProvider>。</span><span class="sxs-lookup"><span data-stu-id="5bcef-112">Controls that contain title bars and title bar elements that enable the control to be moved, resized, maximized, minimized, or closed are typically required to implement <xref:System.Windows.Automation.Provider.IWindowProvider>.</span></span>  
  
-   <span data-ttu-id="5bcef-113">诸如工具提示弹出窗口以及组合框或下拉菜单之类的控件通常不实现 <xref:System.Windows.Automation.Provider.IWindowProvider>。</span><span class="sxs-lookup"><span data-stu-id="5bcef-113">Controls such as tooltip pop-ups and combo box or menu drop-downs do not typically implement <xref:System.Windows.Automation.Provider.IWindowProvider>.</span></span>  
  
-   <span data-ttu-id="5bcef-114">气球状帮助窗口和基本工具提示弹出窗口的区别在于是否提供了像窗口一样的“关闭”按钮。</span><span class="sxs-lookup"><span data-stu-id="5bcef-114">Balloon help windows are differentiated from basic tooltip pop-ups by the provision of a window-like Close button.</span></span>  
  
-   <span data-ttu-id="5bcef-115">IWindowProvider 不支持全屏模式，因为它是特定于应用程序的功能，而不是典型的窗口行为。</span><span class="sxs-lookup"><span data-stu-id="5bcef-115">Full-screen mode is not supported by IWindowProvider as it is feature-specific to an application and is not typical window behavior.</span></span>  
  
<a name="Required_Members_for_IWindowProvider"></a>   
## <a name="required-members-for-iwindowprovider"></a><span data-ttu-id="5bcef-116">IWindowProvider 必需的成员</span><span class="sxs-lookup"><span data-stu-id="5bcef-116">Required Members for IWindowProvider</span></span>  
 <span data-ttu-id="5bcef-117">IWindowProvider 接口需要以下属性、方法和事件。</span><span class="sxs-lookup"><span data-stu-id="5bcef-117">The following properties, methods, and events are required for the IWindowProvider interface.</span></span>  
  
|<span data-ttu-id="5bcef-118">必需的成员</span><span class="sxs-lookup"><span data-stu-id="5bcef-118">Required member</span></span>|<span data-ttu-id="5bcef-119">成员类型</span><span class="sxs-lookup"><span data-stu-id="5bcef-119">Member type</span></span>|<span data-ttu-id="5bcef-120">说明</span><span class="sxs-lookup"><span data-stu-id="5bcef-120">Notes</span></span>|  
|---------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.InteractionState%2A>|<span data-ttu-id="5bcef-121">属性</span><span class="sxs-lookup"><span data-stu-id="5bcef-121">Property</span></span>|<span data-ttu-id="5bcef-122">无</span><span class="sxs-lookup"><span data-stu-id="5bcef-122">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.IsModal%2A>|<span data-ttu-id="5bcef-123">属性</span><span class="sxs-lookup"><span data-stu-id="5bcef-123">Property</span></span>|<span data-ttu-id="5bcef-124">无</span><span class="sxs-lookup"><span data-stu-id="5bcef-124">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.IsTopmost%2A>|<span data-ttu-id="5bcef-125">属性</span><span class="sxs-lookup"><span data-stu-id="5bcef-125">Property</span></span>|<span data-ttu-id="5bcef-126">无</span><span class="sxs-lookup"><span data-stu-id="5bcef-126">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.Maximizable%2A>|<span data-ttu-id="5bcef-127">属性</span><span class="sxs-lookup"><span data-stu-id="5bcef-127">Property</span></span>|<span data-ttu-id="5bcef-128">无</span><span class="sxs-lookup"><span data-stu-id="5bcef-128">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.Minimizable%2A>|<span data-ttu-id="5bcef-129">属性</span><span class="sxs-lookup"><span data-stu-id="5bcef-129">Property</span></span>|<span data-ttu-id="5bcef-130">无</span><span class="sxs-lookup"><span data-stu-id="5bcef-130">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.VisualState%2A>|<span data-ttu-id="5bcef-131">属性</span><span class="sxs-lookup"><span data-stu-id="5bcef-131">Property</span></span>|<span data-ttu-id="5bcef-132">无</span><span class="sxs-lookup"><span data-stu-id="5bcef-132">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.Close%2A>|<span data-ttu-id="5bcef-133">方法</span><span class="sxs-lookup"><span data-stu-id="5bcef-133">Method</span></span>|<span data-ttu-id="5bcef-134">无</span><span class="sxs-lookup"><span data-stu-id="5bcef-134">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.SetVisualState%2A>|<span data-ttu-id="5bcef-135">方法</span><span class="sxs-lookup"><span data-stu-id="5bcef-135">Method</span></span>|<span data-ttu-id="5bcef-136">无</span><span class="sxs-lookup"><span data-stu-id="5bcef-136">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.WaitForInputIdle%2A>|<span data-ttu-id="5bcef-137">方法</span><span class="sxs-lookup"><span data-stu-id="5bcef-137">Method</span></span>|<span data-ttu-id="5bcef-138">无</span><span class="sxs-lookup"><span data-stu-id="5bcef-138">None</span></span>|  
|<xref:System.Windows.Automation.WindowPattern.WindowClosedEvent>|<span data-ttu-id="5bcef-139">事件</span><span class="sxs-lookup"><span data-stu-id="5bcef-139">Event</span></span>|<span data-ttu-id="5bcef-140">无</span><span class="sxs-lookup"><span data-stu-id="5bcef-140">None</span></span>|  
|<xref:System.Windows.Automation.WindowPattern.WindowOpenedEvent>|<span data-ttu-id="5bcef-141">事件</span><span class="sxs-lookup"><span data-stu-id="5bcef-141">Event</span></span>|<span data-ttu-id="5bcef-142">无</span><span class="sxs-lookup"><span data-stu-id="5bcef-142">None</span></span>|  
|<xref:System.Windows.Automation.WindowInteractionState>|<span data-ttu-id="5bcef-143">事件</span><span class="sxs-lookup"><span data-stu-id="5bcef-143">Event</span></span>|<span data-ttu-id="5bcef-144">不保证为 <xref:System.Windows.Automation.WindowInteractionState.ReadyForUserInteraction></span><span class="sxs-lookup"><span data-stu-id="5bcef-144">Is not guaranteed to be <xref:System.Windows.Automation.WindowInteractionState.ReadyForUserInteraction></span></span>|  
  
<a name="Exceptions"></a>   
## <a name="exceptions"></a><span data-ttu-id="5bcef-145">异常</span><span class="sxs-lookup"><span data-stu-id="5bcef-145">Exceptions</span></span>  
 <span data-ttu-id="5bcef-146">提供程序必须引发以下异常。</span><span class="sxs-lookup"><span data-stu-id="5bcef-146">Providers must throw the following exceptions.</span></span>  
  
|<span data-ttu-id="5bcef-147">异常类型</span><span class="sxs-lookup"><span data-stu-id="5bcef-147">Exception type</span></span>|<span data-ttu-id="5bcef-148">条件</span><span class="sxs-lookup"><span data-stu-id="5bcef-148">Condition</span></span>|  
|--------------------|---------------|  
|<xref:System.InvalidOperationException>|<xref:System.Windows.Automation.Provider.IWindowProvider.SetVisualState%2A><br /><br /> <span data-ttu-id="5bcef-149">-如果控件不支持请求的行为。</span><span class="sxs-lookup"><span data-stu-id="5bcef-149">-   When a control does not support a requested behavior.</span></span>|  
|<xref:System.ArgumentOutOfRangeException>|<xref:System.Windows.Automation.Provider.IWindowProvider.WaitForInputIdle%2A><br /><br /> <span data-ttu-id="5bcef-150">-如果参数不是有效的数字。</span><span class="sxs-lookup"><span data-stu-id="5bcef-150">-   When the parameter is not a valid number.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5bcef-151">请参阅</span><span class="sxs-lookup"><span data-stu-id="5bcef-151">See Also</span></span>  
 [<span data-ttu-id="5bcef-152">UI 自动化控件模式概述</span><span class="sxs-lookup"><span data-stu-id="5bcef-152">UI Automation Control Patterns Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)  
 [<span data-ttu-id="5bcef-153">在 UI 自动化提供程序中支持控件模式</span><span class="sxs-lookup"><span data-stu-id="5bcef-153">Support Control Patterns in a UI Automation Provider</span></span>](../../../docs/framework/ui-automation/support-control-patterns-in-a-ui-automation-provider.md)  
 [<span data-ttu-id="5bcef-154">客户端的 UI 自动化控件模式</span><span class="sxs-lookup"><span data-stu-id="5bcef-154">UI Automation Control Patterns for Clients</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)  
 [<span data-ttu-id="5bcef-155">UI 自动化树概述</span><span class="sxs-lookup"><span data-stu-id="5bcef-155">UI Automation Tree Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-tree-overview.md)  
 [<span data-ttu-id="5bcef-156">在 UI 自动化中使用缓存</span><span class="sxs-lookup"><span data-stu-id="5bcef-156">Use Caching in UI Automation</span></span>](../../../docs/framework/ui-automation/use-caching-in-ui-automation.md)
