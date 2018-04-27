---
title: UI 自动化对标准控件的支持
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-bcl
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- controls, UI Automation support for
- UI Automation, support for standard controls
ms.assetid: 3770ea8a-2655-4add-9c59-fe0610ad5084
caps.latest.revision: 11
author: Xansky
ms.author: mhopkins
manager: markl
ms.workload:
- dotnet
ms.openlocfilehash: af46a984f1b4c2577daee120752590ff18b9d1d8
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/27/2018
---
# <a name="ui-automation-support-for-standard-controls"></a><span data-ttu-id="5443c-102">UI 自动化对标准控件的支持</span><span class="sxs-lookup"><span data-stu-id="5443c-102">UI Automation Support for Standard Controls</span></span>
> [!NOTE]
>  <span data-ttu-id="5443c-103">本文档适用于想要使用 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 命名空间中定义的托管 <xref:System.Windows.Automation> 类的 .NET Framework 开发人员。</span><span class="sxs-lookup"><span data-stu-id="5443c-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="5443c-104">有关 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]的最新信息，请参阅 [Windows 自动化 API：UI 自动化](http://go.microsoft.com/fwlink/?LinkID=156746)。</span><span class="sxs-lookup"><span data-stu-id="5443c-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](http://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="5443c-105">本主题包含有关对为 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] 、 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)]和 [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)]框架所开发的应用程序中标准控件的 [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)] 支持的信息。</span><span class="sxs-lookup"><span data-stu-id="5443c-105">This topic contains information about [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] support for standard controls in applications developed for the [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)], [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)], and [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)] frameworks.</span></span>  
  
<a name="Windows_Presentation_Foundation_Controls"></a>   
## <a name="windows-presentation-foundation-controls"></a><span data-ttu-id="5443c-106">Windows Presentation Foundation 控件</span><span class="sxs-lookup"><span data-stu-id="5443c-106">Windows Presentation Foundation Controls</span></span>  
 <span data-ttu-id="5443c-107">为用户交互提供信息或支持的所有 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 控件元素均具有对 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]的完整本机支持。</span><span class="sxs-lookup"><span data-stu-id="5443c-107">All [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] control elements that provide information or support for user interaction have full native support for [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span> <span data-ttu-id="5443c-108">面板等其他元素对 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]不可见。</span><span class="sxs-lookup"><span data-stu-id="5443c-108">Other elements, such as panels, are not visible to [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span>  
  
<a name="Win32_Controls"></a>   
## <a name="win32-controls"></a><span data-ttu-id="5443c-109">Win32 控件</span><span class="sxs-lookup"><span data-stu-id="5443c-109">Win32 Controls</span></span>  
 <span data-ttu-id="5443c-110">大多数 [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] 控件都通过 UIAutomationClientsideProviders.dll 中的客户端提供程序向 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] 公开。</span><span class="sxs-lookup"><span data-stu-id="5443c-110">Most [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] through client-side providers in UIAutomationClientsideProviders.dll.</span></span> <span data-ttu-id="5443c-111">此程序集将自动注册，以用于 UI 自动化客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="5443c-111">This assembly is automatically registered for use with UI Automation client applications.</span></span>  
  
 <span data-ttu-id="5443c-112">仅对 ComCtrl32.dll 版本 6（随 [!INCLUDE[TLA#tla_winxp](../../../includes/tlasharptla-winxp-md.md)] 和更高版本提供）中的控件提供完全支持。</span><span class="sxs-lookup"><span data-stu-id="5443c-112">Full support is provided only for controls from version 6 of ComCtrl32.dll (available with [!INCLUDE[TLA#tla_winxp](../../../includes/tlasharptla-winxp-md.md)] and later).</span></span>  
  
 <span data-ttu-id="5443c-113">支持以下控件。</span><span class="sxs-lookup"><span data-stu-id="5443c-113">The following controls are supported.</span></span>  
  
|<span data-ttu-id="5443c-114">类名</span><span class="sxs-lookup"><span data-stu-id="5443c-114">Class name</span></span>|<span data-ttu-id="5443c-115">控件类型</span><span class="sxs-lookup"><span data-stu-id="5443c-115">Control Type</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="5443c-116">Button</span><span class="sxs-lookup"><span data-stu-id="5443c-116">Button</span></span>|<span data-ttu-id="5443c-117">Button</span><span class="sxs-lookup"><span data-stu-id="5443c-117">Button</span></span>|  
|<span data-ttu-id="5443c-118">Button</span><span class="sxs-lookup"><span data-stu-id="5443c-118">Button</span></span>|<span data-ttu-id="5443c-119">RadioButton</span><span class="sxs-lookup"><span data-stu-id="5443c-119">RadioButton</span></span>|  
|<span data-ttu-id="5443c-120">Button</span><span class="sxs-lookup"><span data-stu-id="5443c-120">Button</span></span>|<span data-ttu-id="5443c-121">Group</span><span class="sxs-lookup"><span data-stu-id="5443c-121">Group</span></span>|  
|<span data-ttu-id="5443c-122">Button</span><span class="sxs-lookup"><span data-stu-id="5443c-122">Button</span></span>|<span data-ttu-id="5443c-123">CheckBox</span><span class="sxs-lookup"><span data-stu-id="5443c-123">CheckBox</span></span>|  
|<span data-ttu-id="5443c-124">Button</span><span class="sxs-lookup"><span data-stu-id="5443c-124">Button</span></span>|<span data-ttu-id="5443c-125">超链接</span><span class="sxs-lookup"><span data-stu-id="5443c-125">Hyperlink</span></span>|  
|<span data-ttu-id="5443c-126">Button</span><span class="sxs-lookup"><span data-stu-id="5443c-126">Button</span></span>|<span data-ttu-id="5443c-127">SplitButton</span><span class="sxs-lookup"><span data-stu-id="5443c-127">SplitButton</span></span>|  
|<span data-ttu-id="5443c-128">Button</span><span class="sxs-lookup"><span data-stu-id="5443c-128">Button</span></span>|<span data-ttu-id="5443c-129">CheckBox</span><span class="sxs-lookup"><span data-stu-id="5443c-129">CheckBox</span></span>|  
|<span data-ttu-id="5443c-130">ComboBoxEx32</span><span class="sxs-lookup"><span data-stu-id="5443c-130">ComboBoxEx32</span></span>|<span data-ttu-id="5443c-131">组合框</span><span class="sxs-lookup"><span data-stu-id="5443c-131">ComboBox</span></span>|  
|<span data-ttu-id="5443c-132">组合框</span><span class="sxs-lookup"><span data-stu-id="5443c-132">ComboBox</span></span>|<span data-ttu-id="5443c-133">组合框</span><span class="sxs-lookup"><span data-stu-id="5443c-133">ComboBox</span></span>|  
|<span data-ttu-id="5443c-134">Edit</span><span class="sxs-lookup"><span data-stu-id="5443c-134">Edit</span></span>|<span data-ttu-id="5443c-135">Document</span><span class="sxs-lookup"><span data-stu-id="5443c-135">Document</span></span>|  
|<span data-ttu-id="5443c-136">Edit</span><span class="sxs-lookup"><span data-stu-id="5443c-136">Edit</span></span>|<span data-ttu-id="5443c-137">Edit</span><span class="sxs-lookup"><span data-stu-id="5443c-137">Edit</span></span>|  
|<span data-ttu-id="5443c-138">SysLink</span><span class="sxs-lookup"><span data-stu-id="5443c-138">SysLink</span></span>|<span data-ttu-id="5443c-139">超链接</span><span class="sxs-lookup"><span data-stu-id="5443c-139">Hyperlink</span></span>|  
|<span data-ttu-id="5443c-140">Static</span><span class="sxs-lookup"><span data-stu-id="5443c-140">Static</span></span>|<span data-ttu-id="5443c-141">Text</span><span class="sxs-lookup"><span data-stu-id="5443c-141">Text</span></span>|  
|<span data-ttu-id="5443c-142">Static</span><span class="sxs-lookup"><span data-stu-id="5443c-142">Static</span></span>|<span data-ttu-id="5443c-143">图像</span><span class="sxs-lookup"><span data-stu-id="5443c-143">Image</span></span>|  
|<span data-ttu-id="5443c-144">SysIPAddress32</span><span class="sxs-lookup"><span data-stu-id="5443c-144">SysIPAddress32</span></span>|<span data-ttu-id="5443c-145">自定义</span><span class="sxs-lookup"><span data-stu-id="5443c-145">Custom</span></span>|  
|<span data-ttu-id="5443c-146">SysHeader32</span><span class="sxs-lookup"><span data-stu-id="5443c-146">SysHeader32</span></span>|<span data-ttu-id="5443c-147">Header/HeaderItem</span><span class="sxs-lookup"><span data-stu-id="5443c-147">Header/HeaderItem</span></span>|  
|<span data-ttu-id="5443c-148">SysListView32</span><span class="sxs-lookup"><span data-stu-id="5443c-148">SysListView32</span></span>|<span data-ttu-id="5443c-149">DataGrid</span><span class="sxs-lookup"><span data-stu-id="5443c-149">DataGrid</span></span>|  
|<span data-ttu-id="5443c-150">SysListView32</span><span class="sxs-lookup"><span data-stu-id="5443c-150">SysListView32</span></span>|<span data-ttu-id="5443c-151">列表</span><span class="sxs-lookup"><span data-stu-id="5443c-151">List</span></span>|  
|<span data-ttu-id="5443c-152">ListBox</span><span class="sxs-lookup"><span data-stu-id="5443c-152">ListBox</span></span>|<span data-ttu-id="5443c-153">列表</span><span class="sxs-lookup"><span data-stu-id="5443c-153">List</span></span>|  
|<span data-ttu-id="5443c-154">ListBox</span><span class="sxs-lookup"><span data-stu-id="5443c-154">ListBox</span></span>|<span data-ttu-id="5443c-155">ListItem</span><span class="sxs-lookup"><span data-stu-id="5443c-155">ListItem</span></span>|  
|<span data-ttu-id="5443c-156">#32768</span><span class="sxs-lookup"><span data-stu-id="5443c-156">#32768</span></span>|<span data-ttu-id="5443c-157">菜单</span><span class="sxs-lookup"><span data-stu-id="5443c-157">Menu</span></span>|  
|<span data-ttu-id="5443c-158">#32768</span><span class="sxs-lookup"><span data-stu-id="5443c-158">#32768</span></span>|<span data-ttu-id="5443c-159">MenuItem</span><span class="sxs-lookup"><span data-stu-id="5443c-159">MenuItem</span></span>|  
|<span data-ttu-id="5443c-160">msctls_progress32</span><span class="sxs-lookup"><span data-stu-id="5443c-160">msctls_progress32</span></span>|<span data-ttu-id="5443c-161">ProgressBar</span><span class="sxs-lookup"><span data-stu-id="5443c-161">ProgressBar</span></span>|  
|<span data-ttu-id="5443c-162">RichEdit</span><span class="sxs-lookup"><span data-stu-id="5443c-162">RichEdit</span></span>|<span data-ttu-id="5443c-163">Document。</span><span class="sxs-lookup"><span data-stu-id="5443c-163">Document.</span></span> <span data-ttu-id="5443c-164">请参阅注释。</span><span class="sxs-lookup"><span data-stu-id="5443c-164">See note.</span></span>|  
|<span data-ttu-id="5443c-165">RichEdit20A</span><span class="sxs-lookup"><span data-stu-id="5443c-165">RichEdit20A</span></span>|<span data-ttu-id="5443c-166">Document</span><span class="sxs-lookup"><span data-stu-id="5443c-166">Document</span></span>|  
|<span data-ttu-id="5443c-167">RichEdit20W</span><span class="sxs-lookup"><span data-stu-id="5443c-167">RichEdit20W</span></span>|<span data-ttu-id="5443c-168">Document</span><span class="sxs-lookup"><span data-stu-id="5443c-168">Document</span></span>|  
|<span data-ttu-id="5443c-169">RichEdit50W</span><span class="sxs-lookup"><span data-stu-id="5443c-169">RichEdit50W</span></span>|<span data-ttu-id="5443c-170">Document</span><span class="sxs-lookup"><span data-stu-id="5443c-170">Document</span></span>|  
|<span data-ttu-id="5443c-171">ScrollBar</span><span class="sxs-lookup"><span data-stu-id="5443c-171">ScrollBar</span></span>|<span data-ttu-id="5443c-172">Slider</span><span class="sxs-lookup"><span data-stu-id="5443c-172">Slider</span></span>|  
|<span data-ttu-id="5443c-173">msctls_trackbar32</span><span class="sxs-lookup"><span data-stu-id="5443c-173">msctls_trackbar32</span></span>|<span data-ttu-id="5443c-174">Slider</span><span class="sxs-lookup"><span data-stu-id="5443c-174">Slider</span></span>|  
|<span data-ttu-id="5443c-175">msctls_updown32</span><span class="sxs-lookup"><span data-stu-id="5443c-175">msctls_updown32</span></span>|<span data-ttu-id="5443c-176">Spinner</span><span class="sxs-lookup"><span data-stu-id="5443c-176">Spinner</span></span>|  
|<span data-ttu-id="5443c-177">msctls_statusbar32</span><span class="sxs-lookup"><span data-stu-id="5443c-177">msctls_statusbar32</span></span>|<span data-ttu-id="5443c-178">StatusBar</span><span class="sxs-lookup"><span data-stu-id="5443c-178">StatusBar</span></span>|  
|<span data-ttu-id="5443c-179">SysTabControl32</span><span class="sxs-lookup"><span data-stu-id="5443c-179">SysTabControl32</span></span>|<span data-ttu-id="5443c-180">Tab</span><span class="sxs-lookup"><span data-stu-id="5443c-180">Tab</span></span>|  
|<span data-ttu-id="5443c-181">SysTabControl32</span><span class="sxs-lookup"><span data-stu-id="5443c-181">SysTabControl32</span></span>|<span data-ttu-id="5443c-182">TabItem</span><span class="sxs-lookup"><span data-stu-id="5443c-182">TabItem</span></span>|  
|<span data-ttu-id="5443c-183">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="5443c-183">ToolbarWindow32</span></span>|<span data-ttu-id="5443c-184">ToolBar</span><span class="sxs-lookup"><span data-stu-id="5443c-184">ToolBar</span></span>|  
|<span data-ttu-id="5443c-185">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="5443c-185">ToolbarWindow32</span></span>|<span data-ttu-id="5443c-186">MenuItem</span><span class="sxs-lookup"><span data-stu-id="5443c-186">MenuItem</span></span>|  
|<span data-ttu-id="5443c-187">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="5443c-187">ToolbarWindow32</span></span>|<span data-ttu-id="5443c-188">Button</span><span class="sxs-lookup"><span data-stu-id="5443c-188">Button</span></span>|  
|<span data-ttu-id="5443c-189">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="5443c-189">ToolbarWindow32</span></span>|<span data-ttu-id="5443c-190">CheckBox</span><span class="sxs-lookup"><span data-stu-id="5443c-190">CheckBox</span></span>|  
|<span data-ttu-id="5443c-191">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="5443c-191">ToolbarWindow32</span></span>|<span data-ttu-id="5443c-192">RadioButton</span><span class="sxs-lookup"><span data-stu-id="5443c-192">RadioButton</span></span>|  
|<span data-ttu-id="5443c-193">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="5443c-193">ToolbarWindow32</span></span>|<span data-ttu-id="5443c-194">Separator</span><span class="sxs-lookup"><span data-stu-id="5443c-194">Separator</span></span>|  
|<span data-ttu-id="5443c-195">tooltips_class32</span><span class="sxs-lookup"><span data-stu-id="5443c-195">tooltips_class32</span></span>|<span data-ttu-id="5443c-196">ToolTip</span><span class="sxs-lookup"><span data-stu-id="5443c-196">ToolTip</span></span>|  
|<span data-ttu-id="5443c-197">#32774</span><span class="sxs-lookup"><span data-stu-id="5443c-197">#32774</span></span>|<span data-ttu-id="5443c-198">ToolTip</span><span class="sxs-lookup"><span data-stu-id="5443c-198">ToolTip</span></span>|  
|<span data-ttu-id="5443c-199">ReBarWindow32</span><span class="sxs-lookup"><span data-stu-id="5443c-199">ReBarWindow32</span></span>|<span data-ttu-id="5443c-200">Toolbar</span><span class="sxs-lookup"><span data-stu-id="5443c-200">Toolbar</span></span>|  
|<span data-ttu-id="5443c-201">SysTreeView32</span><span class="sxs-lookup"><span data-stu-id="5443c-201">SysTreeView32</span></span>|<span data-ttu-id="5443c-202">树</span><span class="sxs-lookup"><span data-stu-id="5443c-202">Tree</span></span>|  
|<span data-ttu-id="5443c-203">SysTreeView32</span><span class="sxs-lookup"><span data-stu-id="5443c-203">SysTreeView32</span></span>|<span data-ttu-id="5443c-204">TreeItem</span><span class="sxs-lookup"><span data-stu-id="5443c-204">TreeItem</span></span>|  
  
 <span data-ttu-id="5443c-205">**注意** 仅在随 [!INCLUDE[TLA#tla_winvista](../../../includes/tlasharptla-winvista-md.md)] 一起提供的版本中（在 RichEd20.dll 中为版本 3.1 和更高版本，在 MsftEdit.dll 中为版本 4.1 和更高版本）支持 RichEdit 控件。</span><span class="sxs-lookup"><span data-stu-id="5443c-205">**Note** The RichEdit control is supported only for versions shipped with [!INCLUDE[TLA#tla_winvista](../../../includes/tlasharptla-winvista-md.md)] (in RichEd20.dll version 3.1 and later, and MsftEdit.dll version 4.1 and later).</span></span>  
  
 <span data-ttu-id="5443c-206">不支持以下控件。</span><span class="sxs-lookup"><span data-stu-id="5443c-206">The following controls are not supported.</span></span>  
  
|<span data-ttu-id="5443c-207">类名</span><span class="sxs-lookup"><span data-stu-id="5443c-207">Class name</span></span>|<span data-ttu-id="5443c-208">控件类型</span><span class="sxs-lookup"><span data-stu-id="5443c-208">Control type</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="5443c-209">SysAnimate32</span><span class="sxs-lookup"><span data-stu-id="5443c-209">SysAnimate32</span></span>|<span data-ttu-id="5443c-210">图像</span><span class="sxs-lookup"><span data-stu-id="5443c-210">Image</span></span>|  
|<span data-ttu-id="5443c-211">SysPager</span><span class="sxs-lookup"><span data-stu-id="5443c-211">SysPager</span></span>|<span data-ttu-id="5443c-212">Spinner</span><span class="sxs-lookup"><span data-stu-id="5443c-212">Spinner</span></span>|  
|<span data-ttu-id="5443c-213">SysDateTimePick32</span><span class="sxs-lookup"><span data-stu-id="5443c-213">SysDateTimePick32</span></span>|<span data-ttu-id="5443c-214">自定义</span><span class="sxs-lookup"><span data-stu-id="5443c-214">Custom</span></span>|  
|<span data-ttu-id="5443c-215">SysMonthCal32</span><span class="sxs-lookup"><span data-stu-id="5443c-215">SysMonthCal32</span></span>|<span data-ttu-id="5443c-216">Calendar</span><span class="sxs-lookup"><span data-stu-id="5443c-216">Calendar</span></span>|  
|<span data-ttu-id="5443c-217">MS_WINNOTE</span><span class="sxs-lookup"><span data-stu-id="5443c-217">MS_WINNOTE</span></span>|<span data-ttu-id="5443c-218">ToolTip</span><span class="sxs-lookup"><span data-stu-id="5443c-218">Tooltip</span></span>|  
|<span data-ttu-id="5443c-219">VBBubble</span><span class="sxs-lookup"><span data-stu-id="5443c-219">VBBubble</span></span>|<span data-ttu-id="5443c-220">ToolTip</span><span class="sxs-lookup"><span data-stu-id="5443c-220">Tooltip</span></span>|  
|<span data-ttu-id="5443c-221">ScrollBar（在用作独立控件时）</span><span class="sxs-lookup"><span data-stu-id="5443c-221">ScrollBar (when used as a standalone control)</span></span>|<span data-ttu-id="5443c-222">Slider</span><span class="sxs-lookup"><span data-stu-id="5443c-222">Slider</span></span>|  
|<span data-ttu-id="5443c-223">SuperGrid</span><span class="sxs-lookup"><span data-stu-id="5443c-223">SuperGrid</span></span>|<span data-ttu-id="5443c-224">自定义</span><span class="sxs-lookup"><span data-stu-id="5443c-224">Custom</span></span>|  
  
<a name="Windows_Forms_Controls"></a>   
## <a name="windows-forms-controls"></a><span data-ttu-id="5443c-225">Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="5443c-225">Windows Forms Controls</span></span>  
 <span data-ttu-id="5443c-226">Windows 窗体控件公开给[!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)]通过 UIAutomationClientsideProviders.dll 中的客户端提供程序。</span><span class="sxs-lookup"><span data-stu-id="5443c-226">Windows Forms controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] through client-side providers in UIAutomationClientsideProviders.dll.</span></span> <span data-ttu-id="5443c-227">此程序集将自动注册，以用于 UI 自动化客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="5443c-227">This assembly is automatically registered for use with UI Automation client applications.</span></span>  
  
 <span data-ttu-id="5443c-228">通常情况下，Windows 窗体控件的托管包装[!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)]公共控件支持的[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="5443c-228">Typically, Windows Forms controls that are managed wrappers for [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] common controls are supported by [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span> <span data-ttu-id="5443c-229">支持以下控件。</span><span class="sxs-lookup"><span data-stu-id="5443c-229">The following controls are supported.</span></span>  
  
|<span data-ttu-id="5443c-230">类名</span><span class="sxs-lookup"><span data-stu-id="5443c-230">Class Name</span></span>|  
|----------------|  
|<span data-ttu-id="5443c-231">Button</span><span class="sxs-lookup"><span data-stu-id="5443c-231">Button</span></span>|  
|<span data-ttu-id="5443c-232">CheckBox</span><span class="sxs-lookup"><span data-stu-id="5443c-232">CheckBox</span></span>|  
|<span data-ttu-id="5443c-233">CheckedListBox</span><span class="sxs-lookup"><span data-stu-id="5443c-233">CheckedListBox</span></span>|  
|<span data-ttu-id="5443c-234">ColorDialog</span><span class="sxs-lookup"><span data-stu-id="5443c-234">ColorDialog</span></span>|  
|<span data-ttu-id="5443c-235">组合框</span><span class="sxs-lookup"><span data-stu-id="5443c-235">ComboBox</span></span>|  
|<span data-ttu-id="5443c-236">FolderBrowser</span><span class="sxs-lookup"><span data-stu-id="5443c-236">FolderBrowser</span></span>|  
|<span data-ttu-id="5443c-237">FontDialog</span><span class="sxs-lookup"><span data-stu-id="5443c-237">FontDialog</span></span>|  
|<span data-ttu-id="5443c-238">GroupBox</span><span class="sxs-lookup"><span data-stu-id="5443c-238">GroupBox</span></span>|  
|<span data-ttu-id="5443c-239">HscrollBar</span><span class="sxs-lookup"><span data-stu-id="5443c-239">HscrollBar</span></span>|  
|<span data-ttu-id="5443c-240">ImageList</span><span class="sxs-lookup"><span data-stu-id="5443c-240">ImageList</span></span>|  
|<span data-ttu-id="5443c-241">Label</span><span class="sxs-lookup"><span data-stu-id="5443c-241">Label</span></span>|  
|<span data-ttu-id="5443c-242">ListBox</span><span class="sxs-lookup"><span data-stu-id="5443c-242">ListBox</span></span>|  
|<span data-ttu-id="5443c-243">ListView</span><span class="sxs-lookup"><span data-stu-id="5443c-243">ListView</span></span>|  
|<span data-ttu-id="5443c-244">MainMenu/ContextMenu</span><span class="sxs-lookup"><span data-stu-id="5443c-244">MainMenu/ContextMenu</span></span>|  
|<span data-ttu-id="5443c-245">MonthCalendar</span><span class="sxs-lookup"><span data-stu-id="5443c-245">MonthCalendar</span></span>|  
|<span data-ttu-id="5443c-246">NotifyIcon</span><span class="sxs-lookup"><span data-stu-id="5443c-246">NotifyIcon</span></span>|  
|<span data-ttu-id="5443c-247">OpenFileDialog</span><span class="sxs-lookup"><span data-stu-id="5443c-247">OpenFileDialog</span></span>|  
|<span data-ttu-id="5443c-248">PageSetupDialog</span><span class="sxs-lookup"><span data-stu-id="5443c-248">PageSetupDialog</span></span>|  
|<span data-ttu-id="5443c-249">PrintDialog</span><span class="sxs-lookup"><span data-stu-id="5443c-249">PrintDialog</span></span>|  
|<span data-ttu-id="5443c-250">ProgressBar</span><span class="sxs-lookup"><span data-stu-id="5443c-250">ProgressBar</span></span>|  
|<span data-ttu-id="5443c-251">RadioButton</span><span class="sxs-lookup"><span data-stu-id="5443c-251">RadioButton</span></span>|  
|<span data-ttu-id="5443c-252">RichTextBox</span><span class="sxs-lookup"><span data-stu-id="5443c-252">RichTextBox</span></span>|  
|<span data-ttu-id="5443c-253">SaveFileDialog</span><span class="sxs-lookup"><span data-stu-id="5443c-253">SaveFileDialog</span></span>|  
|<span data-ttu-id="5443c-254">ScrollableControl</span><span class="sxs-lookup"><span data-stu-id="5443c-254">ScrollableControl</span></span>|  
|<span data-ttu-id="5443c-255">SoundPlayer</span><span class="sxs-lookup"><span data-stu-id="5443c-255">SoundPlayer</span></span>|  
|<span data-ttu-id="5443c-256">StatusBar</span><span class="sxs-lookup"><span data-stu-id="5443c-256">StatusBar</span></span>|  
|<span data-ttu-id="5443c-257">TabControl/TabPage</span><span class="sxs-lookup"><span data-stu-id="5443c-257">TabControl/TabPage</span></span>|  
|<span data-ttu-id="5443c-258">文本框</span><span class="sxs-lookup"><span data-stu-id="5443c-258">TextBox</span></span>|  
|<span data-ttu-id="5443c-259">计时器</span><span class="sxs-lookup"><span data-stu-id="5443c-259">Timer</span></span>|  
|<span data-ttu-id="5443c-260">ToolBar</span><span class="sxs-lookup"><span data-stu-id="5443c-260">Toolbar</span></span>|  
|<span data-ttu-id="5443c-261">ToolTip</span><span class="sxs-lookup"><span data-stu-id="5443c-261">ToolTip</span></span>|  
|<span data-ttu-id="5443c-262">TrackBar</span><span class="sxs-lookup"><span data-stu-id="5443c-262">TrackBar</span></span>|  
|<span data-ttu-id="5443c-263">TreeView</span><span class="sxs-lookup"><span data-stu-id="5443c-263">TreeView</span></span>|  
|<span data-ttu-id="5443c-264">VscrollBar</span><span class="sxs-lookup"><span data-stu-id="5443c-264">VscrollBar</span></span>|  
|<span data-ttu-id="5443c-265">Web 浏览器</span><span class="sxs-lookup"><span data-stu-id="5443c-265">WebBrowser</span></span>|  
  
 <span data-ttu-id="5443c-266">以下控件仅通过其对 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] 的支持向 [!INCLUDE[TLA#tla_aa](../../../includes/tlasharptla-aa-md.md)]公开。</span><span class="sxs-lookup"><span data-stu-id="5443c-266">The following controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] only through their support for [!INCLUDE[TLA#tla_aa](../../../includes/tlasharptla-aa-md.md)].</span></span> <span data-ttu-id="5443c-267">某些功能可能不可用。</span><span class="sxs-lookup"><span data-stu-id="5443c-267">Some functionality may not be available.</span></span>  
  
|<span data-ttu-id="5443c-268">控件名称</span><span class="sxs-lookup"><span data-stu-id="5443c-268">Control Name</span></span>|  
|------------------|  
|<span data-ttu-id="5443c-269">BindingSource</span><span class="sxs-lookup"><span data-stu-id="5443c-269">BindingSource</span></span>|  
|<span data-ttu-id="5443c-270">DataGrid</span><span class="sxs-lookup"><span data-stu-id="5443c-270">DataGrid</span></span>|  
|<span data-ttu-id="5443c-271">DataGridView</span><span class="sxs-lookup"><span data-stu-id="5443c-271">DataGridView</span></span>|  
|<span data-ttu-id="5443c-272">DataNavigator</span><span class="sxs-lookup"><span data-stu-id="5443c-272">DataNavigator</span></span>|  
|<span data-ttu-id="5443c-273">DomainUpDown</span><span class="sxs-lookup"><span data-stu-id="5443c-273">DomainUpDown</span></span>|  
|<span data-ttu-id="5443c-274">ErrorProvider</span><span class="sxs-lookup"><span data-stu-id="5443c-274">ErrorProvider</span></span>|  
|<span data-ttu-id="5443c-275">FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="5443c-275">FlowLayoutPanel</span></span>|  
|<span data-ttu-id="5443c-276">窗体</span><span class="sxs-lookup"><span data-stu-id="5443c-276">Form</span></span>|  
|<span data-ttu-id="5443c-277">LinkLabel</span><span class="sxs-lookup"><span data-stu-id="5443c-277">LinkLabel</span></span>|  
|<span data-ttu-id="5443c-278">HelpProvider</span><span class="sxs-lookup"><span data-stu-id="5443c-278">HelpProvider</span></span>|  
|<span data-ttu-id="5443c-279">MaskedTextBox</span><span class="sxs-lookup"><span data-stu-id="5443c-279">MaskedTextBox</span></span>|  
|<span data-ttu-id="5443c-280">MenuStrip/ContextMenuStrip</span><span class="sxs-lookup"><span data-stu-id="5443c-280">MenuStrip/ContextMenuStrip</span></span>|  
|<span data-ttu-id="5443c-281">NumericUpDown</span><span class="sxs-lookup"><span data-stu-id="5443c-281">NumericUpDown</span></span>|  
|<span data-ttu-id="5443c-282">Panel</span><span class="sxs-lookup"><span data-stu-id="5443c-282">Panel</span></span>|  
|<span data-ttu-id="5443c-283">PictureBox</span><span class="sxs-lookup"><span data-stu-id="5443c-283">PictureBox</span></span>|  
|<span data-ttu-id="5443c-284">PrintDocument</span><span class="sxs-lookup"><span data-stu-id="5443c-284">PrintDocument</span></span>|  
|<span data-ttu-id="5443c-285">PrintPreview-Control</span><span class="sxs-lookup"><span data-stu-id="5443c-285">PrintPreview-Control</span></span>|  
|<span data-ttu-id="5443c-286">PrintPreview-Dialog</span><span class="sxs-lookup"><span data-stu-id="5443c-286">PrintPreview-Dialog</span></span>|  
|<span data-ttu-id="5443c-287">PropertyGrid</span><span class="sxs-lookup"><span data-stu-id="5443c-287">PropertyGrid</span></span>|  
|<span data-ttu-id="5443c-288">用户控件</span><span class="sxs-lookup"><span data-stu-id="5443c-288">UserControl</span></span>|  
|<span data-ttu-id="5443c-289">ToolStrip</span><span class="sxs-lookup"><span data-stu-id="5443c-289">ToolStrip</span></span>|  
|<span data-ttu-id="5443c-290">TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="5443c-290">TableLayoutPanel</span></span>|  
|<span data-ttu-id="5443c-291">SplitContainer/SplitterPanel</span><span class="sxs-lookup"><span data-stu-id="5443c-291">SplitContainer/SplitterPanel</span></span>|  
|<span data-ttu-id="5443c-292">Splitter</span><span class="sxs-lookup"><span data-stu-id="5443c-292">Splitter</span></span>|  
|<span data-ttu-id="5443c-293">RaftingContainer</span><span class="sxs-lookup"><span data-stu-id="5443c-293">RaftingContainer</span></span>|  
|<span data-ttu-id="5443c-294">StatusStrip</span><span class="sxs-lookup"><span data-stu-id="5443c-294">StatusStrip</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5443c-295">请参阅</span><span class="sxs-lookup"><span data-stu-id="5443c-295">See Also</span></span>  
 [<span data-ttu-id="5443c-296">UI 自动化控件类型</span><span class="sxs-lookup"><span data-stu-id="5443c-296">UI Automation Control Types</span></span>](../../../docs/framework/ui-automation/ui-automation-control-types.md)
