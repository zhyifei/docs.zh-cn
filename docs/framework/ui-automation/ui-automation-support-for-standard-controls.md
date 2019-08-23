---
title: UI 自动化对标准控件的支持
ms.date: 03/30/2017
helpviewer_keywords:
- controls, UI Automation support for
- UI Automation, support for standard controls
ms.assetid: 3770ea8a-2655-4add-9c59-fe0610ad5084
ms.openlocfilehash: d83713a81e7675a68482890c2401f1a0a6803abc
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69914232"
---
# <a name="ui-automation-support-for-standard-controls"></a><span data-ttu-id="af296-102">UI 自动化对标准控件的支持</span><span class="sxs-lookup"><span data-stu-id="af296-102">UI Automation Support for Standard Controls</span></span>
> [!NOTE]
> <span data-ttu-id="af296-103">本文档适用于想要使用 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 命名空间中定义的托管 <xref:System.Windows.Automation> 类的 .NET Framework 开发人员。</span><span class="sxs-lookup"><span data-stu-id="af296-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="af296-104">有关的最新信息[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], 请[参阅 Windows 自动化 API:UI 自动化](https://go.microsoft.com/fwlink/?LinkID=156746)。</span><span class="sxs-lookup"><span data-stu-id="af296-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="af296-105">本主题包含有关对为 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] 、 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)]和 [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)]框架所开发的应用程序中标准控件的 [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)] 支持的信息。</span><span class="sxs-lookup"><span data-stu-id="af296-105">This topic contains information about [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] support for standard controls in applications developed for the [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)], [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)], and [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)] frameworks.</span></span>  
  
<a name="Windows_Presentation_Foundation_Controls"></a>   
## <a name="windows-presentation-foundation-controls"></a><span data-ttu-id="af296-106">Windows Presentation Foundation 控件</span><span class="sxs-lookup"><span data-stu-id="af296-106">Windows Presentation Foundation Controls</span></span>  
 <span data-ttu-id="af296-107">为用户交互提供信息或支持的所有 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 控件元素均具有对 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]的完整本机支持。</span><span class="sxs-lookup"><span data-stu-id="af296-107">All [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] control elements that provide information or support for user interaction have full native support for [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span> <span data-ttu-id="af296-108">面板等其他元素对 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]不可见。</span><span class="sxs-lookup"><span data-stu-id="af296-108">Other elements, such as panels, are not visible to [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span>  
  
<a name="Win32_Controls"></a>   
## <a name="win32-controls"></a><span data-ttu-id="af296-109">Win32 控件</span><span class="sxs-lookup"><span data-stu-id="af296-109">Win32 Controls</span></span>  
 <span data-ttu-id="af296-110">大多数 [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] 控件都通过 UIAutomationClientsideProviders.dll 中的客户端提供程序向 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] 公开。</span><span class="sxs-lookup"><span data-stu-id="af296-110">Most [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] through client-side providers in UIAutomationClientsideProviders.dll.</span></span> <span data-ttu-id="af296-111">此程序集将自动注册，以用于 UI 自动化客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="af296-111">This assembly is automatically registered for use with UI Automation client applications.</span></span>  
  
 <span data-ttu-id="af296-112">仅对 ComCtrl32.dll 版本 6（随 [!INCLUDE[TLA#tla_winxp](../../../includes/tlasharptla-winxp-md.md)] 和更高版本提供）中的控件提供完全支持。</span><span class="sxs-lookup"><span data-stu-id="af296-112">Full support is provided only for controls from version 6 of ComCtrl32.dll (available with [!INCLUDE[TLA#tla_winxp](../../../includes/tlasharptla-winxp-md.md)] and later).</span></span>  
  
 <span data-ttu-id="af296-113">支持以下控件。</span><span class="sxs-lookup"><span data-stu-id="af296-113">The following controls are supported.</span></span>  
  
|<span data-ttu-id="af296-114">类名</span><span class="sxs-lookup"><span data-stu-id="af296-114">Class name</span></span>|<span data-ttu-id="af296-115">控件类型</span><span class="sxs-lookup"><span data-stu-id="af296-115">Control Type</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="af296-116">Button</span><span class="sxs-lookup"><span data-stu-id="af296-116">Button</span></span>|<span data-ttu-id="af296-117">Button</span><span class="sxs-lookup"><span data-stu-id="af296-117">Button</span></span>|  
|<span data-ttu-id="af296-118">Button</span><span class="sxs-lookup"><span data-stu-id="af296-118">Button</span></span>|<span data-ttu-id="af296-119">RadioButton</span><span class="sxs-lookup"><span data-stu-id="af296-119">RadioButton</span></span>|  
|<span data-ttu-id="af296-120">Button</span><span class="sxs-lookup"><span data-stu-id="af296-120">Button</span></span>|<span data-ttu-id="af296-121">Group</span><span class="sxs-lookup"><span data-stu-id="af296-121">Group</span></span>|  
|<span data-ttu-id="af296-122">Button</span><span class="sxs-lookup"><span data-stu-id="af296-122">Button</span></span>|<span data-ttu-id="af296-123">CheckBox</span><span class="sxs-lookup"><span data-stu-id="af296-123">CheckBox</span></span>|  
|<span data-ttu-id="af296-124">Button</span><span class="sxs-lookup"><span data-stu-id="af296-124">Button</span></span>|<span data-ttu-id="af296-125">超链接</span><span class="sxs-lookup"><span data-stu-id="af296-125">Hyperlink</span></span>|  
|<span data-ttu-id="af296-126">Button</span><span class="sxs-lookup"><span data-stu-id="af296-126">Button</span></span>|<span data-ttu-id="af296-127">SplitButton</span><span class="sxs-lookup"><span data-stu-id="af296-127">SplitButton</span></span>|  
|<span data-ttu-id="af296-128">Button</span><span class="sxs-lookup"><span data-stu-id="af296-128">Button</span></span>|<span data-ttu-id="af296-129">CheckBox</span><span class="sxs-lookup"><span data-stu-id="af296-129">CheckBox</span></span>|  
|<span data-ttu-id="af296-130">ComboBoxEx32</span><span class="sxs-lookup"><span data-stu-id="af296-130">ComboBoxEx32</span></span>|<span data-ttu-id="af296-131">组合框</span><span class="sxs-lookup"><span data-stu-id="af296-131">ComboBox</span></span>|  
|<span data-ttu-id="af296-132">组合框</span><span class="sxs-lookup"><span data-stu-id="af296-132">ComboBox</span></span>|<span data-ttu-id="af296-133">组合框</span><span class="sxs-lookup"><span data-stu-id="af296-133">ComboBox</span></span>|  
|<span data-ttu-id="af296-134">Edit</span><span class="sxs-lookup"><span data-stu-id="af296-134">Edit</span></span>|<span data-ttu-id="af296-135">Document</span><span class="sxs-lookup"><span data-stu-id="af296-135">Document</span></span>|  
|<span data-ttu-id="af296-136">Edit</span><span class="sxs-lookup"><span data-stu-id="af296-136">Edit</span></span>|<span data-ttu-id="af296-137">Edit</span><span class="sxs-lookup"><span data-stu-id="af296-137">Edit</span></span>|  
|<span data-ttu-id="af296-138">SysLink</span><span class="sxs-lookup"><span data-stu-id="af296-138">SysLink</span></span>|<span data-ttu-id="af296-139">超链接</span><span class="sxs-lookup"><span data-stu-id="af296-139">Hyperlink</span></span>|  
|<span data-ttu-id="af296-140">Static</span><span class="sxs-lookup"><span data-stu-id="af296-140">Static</span></span>|<span data-ttu-id="af296-141">文本</span><span class="sxs-lookup"><span data-stu-id="af296-141">Text</span></span>|  
|<span data-ttu-id="af296-142">Static</span><span class="sxs-lookup"><span data-stu-id="af296-142">Static</span></span>|<span data-ttu-id="af296-143">图像</span><span class="sxs-lookup"><span data-stu-id="af296-143">Image</span></span>|  
|<span data-ttu-id="af296-144">SysIPAddress32</span><span class="sxs-lookup"><span data-stu-id="af296-144">SysIPAddress32</span></span>|<span data-ttu-id="af296-145">自定义</span><span class="sxs-lookup"><span data-stu-id="af296-145">Custom</span></span>|  
|<span data-ttu-id="af296-146">SysHeader32</span><span class="sxs-lookup"><span data-stu-id="af296-146">SysHeader32</span></span>|<span data-ttu-id="af296-147">Header/HeaderItem</span><span class="sxs-lookup"><span data-stu-id="af296-147">Header/HeaderItem</span></span>|  
|<span data-ttu-id="af296-148">SysListView32</span><span class="sxs-lookup"><span data-stu-id="af296-148">SysListView32</span></span>|<span data-ttu-id="af296-149">DataGrid</span><span class="sxs-lookup"><span data-stu-id="af296-149">DataGrid</span></span>|  
|<span data-ttu-id="af296-150">SysListView32</span><span class="sxs-lookup"><span data-stu-id="af296-150">SysListView32</span></span>|<span data-ttu-id="af296-151">列表</span><span class="sxs-lookup"><span data-stu-id="af296-151">List</span></span>|  
|<span data-ttu-id="af296-152">ListBox</span><span class="sxs-lookup"><span data-stu-id="af296-152">ListBox</span></span>|<span data-ttu-id="af296-153">列表</span><span class="sxs-lookup"><span data-stu-id="af296-153">List</span></span>|  
|<span data-ttu-id="af296-154">ListBox</span><span class="sxs-lookup"><span data-stu-id="af296-154">ListBox</span></span>|<span data-ttu-id="af296-155">ListItem</span><span class="sxs-lookup"><span data-stu-id="af296-155">ListItem</span></span>|  
|<span data-ttu-id="af296-156">#32768</span><span class="sxs-lookup"><span data-stu-id="af296-156">#32768</span></span>|<span data-ttu-id="af296-157">菜单</span><span class="sxs-lookup"><span data-stu-id="af296-157">Menu</span></span>|  
|<span data-ttu-id="af296-158">#32768</span><span class="sxs-lookup"><span data-stu-id="af296-158">#32768</span></span>|<span data-ttu-id="af296-159">MenuItem</span><span class="sxs-lookup"><span data-stu-id="af296-159">MenuItem</span></span>|  
|<span data-ttu-id="af296-160">msctls_progress32</span><span class="sxs-lookup"><span data-stu-id="af296-160">msctls_progress32</span></span>|<span data-ttu-id="af296-161">ProgressBar</span><span class="sxs-lookup"><span data-stu-id="af296-161">ProgressBar</span></span>|  
|<span data-ttu-id="af296-162">RichEdit</span><span class="sxs-lookup"><span data-stu-id="af296-162">RichEdit</span></span>|<span data-ttu-id="af296-163">Document。</span><span class="sxs-lookup"><span data-stu-id="af296-163">Document.</span></span> <span data-ttu-id="af296-164">请参阅注释。</span><span class="sxs-lookup"><span data-stu-id="af296-164">See note.</span></span>|  
|<span data-ttu-id="af296-165">RichEdit20A</span><span class="sxs-lookup"><span data-stu-id="af296-165">RichEdit20A</span></span>|<span data-ttu-id="af296-166">Document</span><span class="sxs-lookup"><span data-stu-id="af296-166">Document</span></span>|  
|<span data-ttu-id="af296-167">RichEdit20W</span><span class="sxs-lookup"><span data-stu-id="af296-167">RichEdit20W</span></span>|<span data-ttu-id="af296-168">Document</span><span class="sxs-lookup"><span data-stu-id="af296-168">Document</span></span>|  
|<span data-ttu-id="af296-169">RichEdit50W</span><span class="sxs-lookup"><span data-stu-id="af296-169">RichEdit50W</span></span>|<span data-ttu-id="af296-170">Document</span><span class="sxs-lookup"><span data-stu-id="af296-170">Document</span></span>|  
|<span data-ttu-id="af296-171">ScrollBar</span><span class="sxs-lookup"><span data-stu-id="af296-171">ScrollBar</span></span>|<span data-ttu-id="af296-172">Slider</span><span class="sxs-lookup"><span data-stu-id="af296-172">Slider</span></span>|  
|<span data-ttu-id="af296-173">msctls_trackbar32</span><span class="sxs-lookup"><span data-stu-id="af296-173">msctls_trackbar32</span></span>|<span data-ttu-id="af296-174">Slider</span><span class="sxs-lookup"><span data-stu-id="af296-174">Slider</span></span>|  
|<span data-ttu-id="af296-175">msctls_updown32</span><span class="sxs-lookup"><span data-stu-id="af296-175">msctls_updown32</span></span>|<span data-ttu-id="af296-176">Spinner</span><span class="sxs-lookup"><span data-stu-id="af296-176">Spinner</span></span>|  
|<span data-ttu-id="af296-177">msctls_statusbar32</span><span class="sxs-lookup"><span data-stu-id="af296-177">msctls_statusbar32</span></span>|<span data-ttu-id="af296-178">StatusBar</span><span class="sxs-lookup"><span data-stu-id="af296-178">StatusBar</span></span>|  
|<span data-ttu-id="af296-179">SysTabControl32</span><span class="sxs-lookup"><span data-stu-id="af296-179">SysTabControl32</span></span>|<span data-ttu-id="af296-180">Tab</span><span class="sxs-lookup"><span data-stu-id="af296-180">Tab</span></span>|  
|<span data-ttu-id="af296-181">SysTabControl32</span><span class="sxs-lookup"><span data-stu-id="af296-181">SysTabControl32</span></span>|<span data-ttu-id="af296-182">TabItem</span><span class="sxs-lookup"><span data-stu-id="af296-182">TabItem</span></span>|  
|<span data-ttu-id="af296-183">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="af296-183">ToolbarWindow32</span></span>|<span data-ttu-id="af296-184">ToolBar</span><span class="sxs-lookup"><span data-stu-id="af296-184">ToolBar</span></span>|  
|<span data-ttu-id="af296-185">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="af296-185">ToolbarWindow32</span></span>|<span data-ttu-id="af296-186">MenuItem</span><span class="sxs-lookup"><span data-stu-id="af296-186">MenuItem</span></span>|  
|<span data-ttu-id="af296-187">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="af296-187">ToolbarWindow32</span></span>|<span data-ttu-id="af296-188">Button</span><span class="sxs-lookup"><span data-stu-id="af296-188">Button</span></span>|  
|<span data-ttu-id="af296-189">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="af296-189">ToolbarWindow32</span></span>|<span data-ttu-id="af296-190">CheckBox</span><span class="sxs-lookup"><span data-stu-id="af296-190">CheckBox</span></span>|  
|<span data-ttu-id="af296-191">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="af296-191">ToolbarWindow32</span></span>|<span data-ttu-id="af296-192">RadioButton</span><span class="sxs-lookup"><span data-stu-id="af296-192">RadioButton</span></span>|  
|<span data-ttu-id="af296-193">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="af296-193">ToolbarWindow32</span></span>|<span data-ttu-id="af296-194">Separator</span><span class="sxs-lookup"><span data-stu-id="af296-194">Separator</span></span>|  
|<span data-ttu-id="af296-195">tooltips_class32</span><span class="sxs-lookup"><span data-stu-id="af296-195">tooltips_class32</span></span>|<span data-ttu-id="af296-196">ToolTip</span><span class="sxs-lookup"><span data-stu-id="af296-196">ToolTip</span></span>|  
|<span data-ttu-id="af296-197">#32774</span><span class="sxs-lookup"><span data-stu-id="af296-197">#32774</span></span>|<span data-ttu-id="af296-198">ToolTip</span><span class="sxs-lookup"><span data-stu-id="af296-198">ToolTip</span></span>|  
|<span data-ttu-id="af296-199">ReBarWindow32</span><span class="sxs-lookup"><span data-stu-id="af296-199">ReBarWindow32</span></span>|<span data-ttu-id="af296-200">Toolbar</span><span class="sxs-lookup"><span data-stu-id="af296-200">Toolbar</span></span>|  
|<span data-ttu-id="af296-201">SysTreeView32</span><span class="sxs-lookup"><span data-stu-id="af296-201">SysTreeView32</span></span>|<span data-ttu-id="af296-202">树</span><span class="sxs-lookup"><span data-stu-id="af296-202">Tree</span></span>|  
|<span data-ttu-id="af296-203">SysTreeView32</span><span class="sxs-lookup"><span data-stu-id="af296-203">SysTreeView32</span></span>|<span data-ttu-id="af296-204">TreeItem</span><span class="sxs-lookup"><span data-stu-id="af296-204">TreeItem</span></span>|  
  
 <span data-ttu-id="af296-205">**注意** 仅在随 [!INCLUDE[TLA#tla_winvista](../../../includes/tlasharptla-winvista-md.md)] 一起提供的版本中（在 RichEd20.dll 中为版本 3.1 和更高版本，在 MsftEdit.dll 中为版本 4.1 和更高版本）支持 RichEdit 控件。</span><span class="sxs-lookup"><span data-stu-id="af296-205">**Note** The RichEdit control is supported only for versions shipped with [!INCLUDE[TLA#tla_winvista](../../../includes/tlasharptla-winvista-md.md)] (in RichEd20.dll version 3.1 and later, and MsftEdit.dll version 4.1 and later).</span></span>  
  
 <span data-ttu-id="af296-206">不支持以下控件。</span><span class="sxs-lookup"><span data-stu-id="af296-206">The following controls are not supported.</span></span>  
  
|<span data-ttu-id="af296-207">类名</span><span class="sxs-lookup"><span data-stu-id="af296-207">Class name</span></span>|<span data-ttu-id="af296-208">控件类型</span><span class="sxs-lookup"><span data-stu-id="af296-208">Control type</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="af296-209">SysAnimate32</span><span class="sxs-lookup"><span data-stu-id="af296-209">SysAnimate32</span></span>|<span data-ttu-id="af296-210">图像</span><span class="sxs-lookup"><span data-stu-id="af296-210">Image</span></span>|  
|<span data-ttu-id="af296-211">SysPager</span><span class="sxs-lookup"><span data-stu-id="af296-211">SysPager</span></span>|<span data-ttu-id="af296-212">Spinner</span><span class="sxs-lookup"><span data-stu-id="af296-212">Spinner</span></span>|  
|<span data-ttu-id="af296-213">SysDateTimePick32</span><span class="sxs-lookup"><span data-stu-id="af296-213">SysDateTimePick32</span></span>|<span data-ttu-id="af296-214">自定义</span><span class="sxs-lookup"><span data-stu-id="af296-214">Custom</span></span>|  
|<span data-ttu-id="af296-215">SysMonthCal32</span><span class="sxs-lookup"><span data-stu-id="af296-215">SysMonthCal32</span></span>|<span data-ttu-id="af296-216">Calendar</span><span class="sxs-lookup"><span data-stu-id="af296-216">Calendar</span></span>|  
|<span data-ttu-id="af296-217">MS_WINNOTE</span><span class="sxs-lookup"><span data-stu-id="af296-217">MS_WINNOTE</span></span>|<span data-ttu-id="af296-218">ToolTip</span><span class="sxs-lookup"><span data-stu-id="af296-218">Tooltip</span></span>|  
|<span data-ttu-id="af296-219">VBBubble</span><span class="sxs-lookup"><span data-stu-id="af296-219">VBBubble</span></span>|<span data-ttu-id="af296-220">ToolTip</span><span class="sxs-lookup"><span data-stu-id="af296-220">Tooltip</span></span>|  
|<span data-ttu-id="af296-221">ScrollBar（在用作独立控件时）</span><span class="sxs-lookup"><span data-stu-id="af296-221">ScrollBar (when used as a standalone control)</span></span>|<span data-ttu-id="af296-222">Slider</span><span class="sxs-lookup"><span data-stu-id="af296-222">Slider</span></span>|  
|<span data-ttu-id="af296-223">SuperGrid</span><span class="sxs-lookup"><span data-stu-id="af296-223">SuperGrid</span></span>|<span data-ttu-id="af296-224">自定义</span><span class="sxs-lookup"><span data-stu-id="af296-224">Custom</span></span>|  
  
<a name="Windows_Forms_Controls"></a>   
## <a name="windows-forms-controls"></a><span data-ttu-id="af296-225">Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="af296-225">Windows Forms Controls</span></span>  
 <span data-ttu-id="af296-226">通过 uiautomationclientsideproviders.dll 中的客户[!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)]端提供程序向 Windows 窗体控件公开。</span><span class="sxs-lookup"><span data-stu-id="af296-226">Windows Forms controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] through client-side providers in UIAutomationClientsideProviders.dll.</span></span> <span data-ttu-id="af296-227">此程序集将自动注册，以用于 UI 自动化客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="af296-227">This assembly is automatically registered for use with UI Automation client applications.</span></span>  
  
 <span data-ttu-id="af296-228">通常, [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]支持作为公共控件的托管包装器 Windows 窗体控件。</span><span class="sxs-lookup"><span data-stu-id="af296-228">Typically, Windows Forms controls that are managed wrappers for [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] common controls are supported by [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span> <span data-ttu-id="af296-229">支持以下控件。</span><span class="sxs-lookup"><span data-stu-id="af296-229">The following controls are supported.</span></span>  
  
|<span data-ttu-id="af296-230">类名</span><span class="sxs-lookup"><span data-stu-id="af296-230">Class Name</span></span>|  
|----------------|  
|<span data-ttu-id="af296-231">Button</span><span class="sxs-lookup"><span data-stu-id="af296-231">Button</span></span>|  
|<span data-ttu-id="af296-232">CheckBox</span><span class="sxs-lookup"><span data-stu-id="af296-232">CheckBox</span></span>|  
|<span data-ttu-id="af296-233">CheckedListBox</span><span class="sxs-lookup"><span data-stu-id="af296-233">CheckedListBox</span></span>|  
|<span data-ttu-id="af296-234">ColorDialog</span><span class="sxs-lookup"><span data-stu-id="af296-234">ColorDialog</span></span>|  
|<span data-ttu-id="af296-235">组合框</span><span class="sxs-lookup"><span data-stu-id="af296-235">ComboBox</span></span>|  
|<span data-ttu-id="af296-236">FolderBrowser</span><span class="sxs-lookup"><span data-stu-id="af296-236">FolderBrowser</span></span>|  
|<span data-ttu-id="af296-237">FontDialog</span><span class="sxs-lookup"><span data-stu-id="af296-237">FontDialog</span></span>|  
|<span data-ttu-id="af296-238">GroupBox</span><span class="sxs-lookup"><span data-stu-id="af296-238">GroupBox</span></span>|  
|<span data-ttu-id="af296-239">HscrollBar</span><span class="sxs-lookup"><span data-stu-id="af296-239">HscrollBar</span></span>|  
|<span data-ttu-id="af296-240">ImageList</span><span class="sxs-lookup"><span data-stu-id="af296-240">ImageList</span></span>|  
|<span data-ttu-id="af296-241">Label</span><span class="sxs-lookup"><span data-stu-id="af296-241">Label</span></span>|  
|<span data-ttu-id="af296-242">ListBox</span><span class="sxs-lookup"><span data-stu-id="af296-242">ListBox</span></span>|  
|<span data-ttu-id="af296-243">ListView</span><span class="sxs-lookup"><span data-stu-id="af296-243">ListView</span></span>|  
|<span data-ttu-id="af296-244">MainMenu/ContextMenu</span><span class="sxs-lookup"><span data-stu-id="af296-244">MainMenu/ContextMenu</span></span>|  
|<span data-ttu-id="af296-245">MonthCalendar</span><span class="sxs-lookup"><span data-stu-id="af296-245">MonthCalendar</span></span>|  
|<span data-ttu-id="af296-246">NotifyIcon</span><span class="sxs-lookup"><span data-stu-id="af296-246">NotifyIcon</span></span>|  
|<span data-ttu-id="af296-247">OpenFileDialog</span><span class="sxs-lookup"><span data-stu-id="af296-247">OpenFileDialog</span></span>|  
|<span data-ttu-id="af296-248">PageSetupDialog</span><span class="sxs-lookup"><span data-stu-id="af296-248">PageSetupDialog</span></span>|  
|<span data-ttu-id="af296-249">PrintDialog</span><span class="sxs-lookup"><span data-stu-id="af296-249">PrintDialog</span></span>|  
|<span data-ttu-id="af296-250">ProgressBar</span><span class="sxs-lookup"><span data-stu-id="af296-250">ProgressBar</span></span>|  
|<span data-ttu-id="af296-251">RadioButton</span><span class="sxs-lookup"><span data-stu-id="af296-251">RadioButton</span></span>|  
|<span data-ttu-id="af296-252">RichTextBox</span><span class="sxs-lookup"><span data-stu-id="af296-252">RichTextBox</span></span>|  
|<span data-ttu-id="af296-253">SaveFileDialog</span><span class="sxs-lookup"><span data-stu-id="af296-253">SaveFileDialog</span></span>|  
|<span data-ttu-id="af296-254">ScrollableControl</span><span class="sxs-lookup"><span data-stu-id="af296-254">ScrollableControl</span></span>|  
|<span data-ttu-id="af296-255">SoundPlayer</span><span class="sxs-lookup"><span data-stu-id="af296-255">SoundPlayer</span></span>|  
|<span data-ttu-id="af296-256">StatusBar</span><span class="sxs-lookup"><span data-stu-id="af296-256">StatusBar</span></span>|  
|<span data-ttu-id="af296-257">TabControl/TabPage</span><span class="sxs-lookup"><span data-stu-id="af296-257">TabControl/TabPage</span></span>|  
|<span data-ttu-id="af296-258">文本框</span><span class="sxs-lookup"><span data-stu-id="af296-258">TextBox</span></span>|  
|<span data-ttu-id="af296-259">计时器</span><span class="sxs-lookup"><span data-stu-id="af296-259">Timer</span></span>|  
|<span data-ttu-id="af296-260">ToolBar</span><span class="sxs-lookup"><span data-stu-id="af296-260">Toolbar</span></span>|  
|<span data-ttu-id="af296-261">ToolTip</span><span class="sxs-lookup"><span data-stu-id="af296-261">ToolTip</span></span>|  
|<span data-ttu-id="af296-262">TrackBar</span><span class="sxs-lookup"><span data-stu-id="af296-262">TrackBar</span></span>|  
|<span data-ttu-id="af296-263">TreeView</span><span class="sxs-lookup"><span data-stu-id="af296-263">TreeView</span></span>|  
|<span data-ttu-id="af296-264">VscrollBar</span><span class="sxs-lookup"><span data-stu-id="af296-264">VscrollBar</span></span>|  
|<span data-ttu-id="af296-265">Web 浏览器</span><span class="sxs-lookup"><span data-stu-id="af296-265">WebBrowser</span></span>|  
  
 <span data-ttu-id="af296-266">以下控件[!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)]仅通过其对 Microsoft Active Accessibility 的支持公开。</span><span class="sxs-lookup"><span data-stu-id="af296-266">The following controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] only through their support for Microsoft Active Accessibility.</span></span> <span data-ttu-id="af296-267">某些功能可能不可用。</span><span class="sxs-lookup"><span data-stu-id="af296-267">Some functionality may not be available.</span></span>  
  
|<span data-ttu-id="af296-268">控件名称</span><span class="sxs-lookup"><span data-stu-id="af296-268">Control Name</span></span>|  
|------------------|  
|<span data-ttu-id="af296-269">BindingSource</span><span class="sxs-lookup"><span data-stu-id="af296-269">BindingSource</span></span>|  
|<span data-ttu-id="af296-270">DataGrid</span><span class="sxs-lookup"><span data-stu-id="af296-270">DataGrid</span></span>|  
|<span data-ttu-id="af296-271">DataGridView</span><span class="sxs-lookup"><span data-stu-id="af296-271">DataGridView</span></span>|  
|<span data-ttu-id="af296-272">DataNavigator</span><span class="sxs-lookup"><span data-stu-id="af296-272">DataNavigator</span></span>|  
|<span data-ttu-id="af296-273">DomainUpDown</span><span class="sxs-lookup"><span data-stu-id="af296-273">DomainUpDown</span></span>|  
|<span data-ttu-id="af296-274">ErrorProvider</span><span class="sxs-lookup"><span data-stu-id="af296-274">ErrorProvider</span></span>|  
|<span data-ttu-id="af296-275">FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="af296-275">FlowLayoutPanel</span></span>|  
|<span data-ttu-id="af296-276">窗体</span><span class="sxs-lookup"><span data-stu-id="af296-276">Form</span></span>|  
|<span data-ttu-id="af296-277">LinkLabel</span><span class="sxs-lookup"><span data-stu-id="af296-277">LinkLabel</span></span>|  
|<span data-ttu-id="af296-278">HelpProvider</span><span class="sxs-lookup"><span data-stu-id="af296-278">HelpProvider</span></span>|  
|<span data-ttu-id="af296-279">MaskedTextBox</span><span class="sxs-lookup"><span data-stu-id="af296-279">MaskedTextBox</span></span>|  
|<span data-ttu-id="af296-280">MenuStrip/ContextMenuStrip</span><span class="sxs-lookup"><span data-stu-id="af296-280">MenuStrip/ContextMenuStrip</span></span>|  
|<span data-ttu-id="af296-281">NumericUpDown</span><span class="sxs-lookup"><span data-stu-id="af296-281">NumericUpDown</span></span>|  
|<span data-ttu-id="af296-282">Panel</span><span class="sxs-lookup"><span data-stu-id="af296-282">Panel</span></span>|  
|<span data-ttu-id="af296-283">PictureBox</span><span class="sxs-lookup"><span data-stu-id="af296-283">PictureBox</span></span>|  
|<span data-ttu-id="af296-284">PrintDocument</span><span class="sxs-lookup"><span data-stu-id="af296-284">PrintDocument</span></span>|  
|<span data-ttu-id="af296-285">PrintPreview-Control</span><span class="sxs-lookup"><span data-stu-id="af296-285">PrintPreview-Control</span></span>|  
|<span data-ttu-id="af296-286">PrintPreview-Dialog</span><span class="sxs-lookup"><span data-stu-id="af296-286">PrintPreview-Dialog</span></span>|  
|<span data-ttu-id="af296-287">PropertyGrid</span><span class="sxs-lookup"><span data-stu-id="af296-287">PropertyGrid</span></span>|  
|<span data-ttu-id="af296-288">用户控件</span><span class="sxs-lookup"><span data-stu-id="af296-288">UserControl</span></span>|  
|<span data-ttu-id="af296-289">ToolStrip</span><span class="sxs-lookup"><span data-stu-id="af296-289">ToolStrip</span></span>|  
|<span data-ttu-id="af296-290">TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="af296-290">TableLayoutPanel</span></span>|  
|<span data-ttu-id="af296-291">SplitContainer/SplitterPanel</span><span class="sxs-lookup"><span data-stu-id="af296-291">SplitContainer/SplitterPanel</span></span>|  
|<span data-ttu-id="af296-292">Splitter</span><span class="sxs-lookup"><span data-stu-id="af296-292">Splitter</span></span>|  
|<span data-ttu-id="af296-293">RaftingContainer</span><span class="sxs-lookup"><span data-stu-id="af296-293">RaftingContainer</span></span>|  
|<span data-ttu-id="af296-294">StatusStrip</span><span class="sxs-lookup"><span data-stu-id="af296-294">StatusStrip</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="af296-295">请参阅</span><span class="sxs-lookup"><span data-stu-id="af296-295">See also</span></span>

- [<span data-ttu-id="af296-296">UI 自动化控件类型</span><span class="sxs-lookup"><span data-stu-id="af296-296">UI Automation Control Types</span></span>](../../../docs/framework/ui-automation/ui-automation-control-types.md)
