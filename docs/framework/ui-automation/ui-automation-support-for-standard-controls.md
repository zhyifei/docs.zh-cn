---
title: UI 自动化对标准控件的支持
ms.date: 03/30/2017
helpviewer_keywords:
- controls, UI Automation support for
- UI Automation, support for standard controls
ms.assetid: 3770ea8a-2655-4add-9c59-fe0610ad5084
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: cbfb640a068a2c1178d321480ee3a112db07b6ac
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2018
ms.locfileid: "43463887"
---
# <a name="ui-automation-support-for-standard-controls"></a><span data-ttu-id="7aa10-102">UI 自动化对标准控件的支持</span><span class="sxs-lookup"><span data-stu-id="7aa10-102">UI Automation Support for Standard Controls</span></span>
> [!NOTE]
>  <span data-ttu-id="7aa10-103">本文档适用于想要使用 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 命名空间中定义的托管 <xref:System.Windows.Automation> 类的 .NET Framework 开发人员。</span><span class="sxs-lookup"><span data-stu-id="7aa10-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="7aa10-104">有关最新信息[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]，请参阅[Windows 自动化 API: UI 自动化](https://go.microsoft.com/fwlink/?LinkID=156746)。</span><span class="sxs-lookup"><span data-stu-id="7aa10-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="7aa10-105">本主题包含有关对为 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] 、 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)]和 [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)]框架所开发的应用程序中标准控件的 [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)] 支持的信息。</span><span class="sxs-lookup"><span data-stu-id="7aa10-105">This topic contains information about [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] support for standard controls in applications developed for the [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)], [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)], and [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)] frameworks.</span></span>  
  
<a name="Windows_Presentation_Foundation_Controls"></a>   
## <a name="windows-presentation-foundation-controls"></a><span data-ttu-id="7aa10-106">Windows Presentation Foundation 控件</span><span class="sxs-lookup"><span data-stu-id="7aa10-106">Windows Presentation Foundation Controls</span></span>  
 <span data-ttu-id="7aa10-107">为用户交互提供信息或支持的所有 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 控件元素均具有对 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]的完整本机支持。</span><span class="sxs-lookup"><span data-stu-id="7aa10-107">All [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] control elements that provide information or support for user interaction have full native support for [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span> <span data-ttu-id="7aa10-108">面板等其他元素对 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]不可见。</span><span class="sxs-lookup"><span data-stu-id="7aa10-108">Other elements, such as panels, are not visible to [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span>  
  
<a name="Win32_Controls"></a>   
## <a name="win32-controls"></a><span data-ttu-id="7aa10-109">Win32 控件</span><span class="sxs-lookup"><span data-stu-id="7aa10-109">Win32 Controls</span></span>  
 <span data-ttu-id="7aa10-110">大多数 [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] 控件都通过 UIAutomationClientsideProviders.dll 中的客户端提供程序向 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] 公开。</span><span class="sxs-lookup"><span data-stu-id="7aa10-110">Most [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] through client-side providers in UIAutomationClientsideProviders.dll.</span></span> <span data-ttu-id="7aa10-111">此程序集将自动注册，以用于 UI 自动化客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="7aa10-111">This assembly is automatically registered for use with UI Automation client applications.</span></span>  
  
 <span data-ttu-id="7aa10-112">仅对 ComCtrl32.dll 版本 6（随 [!INCLUDE[TLA#tla_winxp](../../../includes/tlasharptla-winxp-md.md)] 和更高版本提供）中的控件提供完全支持。</span><span class="sxs-lookup"><span data-stu-id="7aa10-112">Full support is provided only for controls from version 6 of ComCtrl32.dll (available with [!INCLUDE[TLA#tla_winxp](../../../includes/tlasharptla-winxp-md.md)] and later).</span></span>  
  
 <span data-ttu-id="7aa10-113">支持以下控件。</span><span class="sxs-lookup"><span data-stu-id="7aa10-113">The following controls are supported.</span></span>  
  
|<span data-ttu-id="7aa10-114">类名</span><span class="sxs-lookup"><span data-stu-id="7aa10-114">Class name</span></span>|<span data-ttu-id="7aa10-115">控件类型</span><span class="sxs-lookup"><span data-stu-id="7aa10-115">Control Type</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="7aa10-116">Button</span><span class="sxs-lookup"><span data-stu-id="7aa10-116">Button</span></span>|<span data-ttu-id="7aa10-117">Button</span><span class="sxs-lookup"><span data-stu-id="7aa10-117">Button</span></span>|  
|<span data-ttu-id="7aa10-118">Button</span><span class="sxs-lookup"><span data-stu-id="7aa10-118">Button</span></span>|<span data-ttu-id="7aa10-119">RadioButton</span><span class="sxs-lookup"><span data-stu-id="7aa10-119">RadioButton</span></span>|  
|<span data-ttu-id="7aa10-120">Button</span><span class="sxs-lookup"><span data-stu-id="7aa10-120">Button</span></span>|<span data-ttu-id="7aa10-121">Group</span><span class="sxs-lookup"><span data-stu-id="7aa10-121">Group</span></span>|  
|<span data-ttu-id="7aa10-122">Button</span><span class="sxs-lookup"><span data-stu-id="7aa10-122">Button</span></span>|<span data-ttu-id="7aa10-123">CheckBox</span><span class="sxs-lookup"><span data-stu-id="7aa10-123">CheckBox</span></span>|  
|<span data-ttu-id="7aa10-124">Button</span><span class="sxs-lookup"><span data-stu-id="7aa10-124">Button</span></span>|<span data-ttu-id="7aa10-125">超链接</span><span class="sxs-lookup"><span data-stu-id="7aa10-125">Hyperlink</span></span>|  
|<span data-ttu-id="7aa10-126">Button</span><span class="sxs-lookup"><span data-stu-id="7aa10-126">Button</span></span>|<span data-ttu-id="7aa10-127">SplitButton</span><span class="sxs-lookup"><span data-stu-id="7aa10-127">SplitButton</span></span>|  
|<span data-ttu-id="7aa10-128">Button</span><span class="sxs-lookup"><span data-stu-id="7aa10-128">Button</span></span>|<span data-ttu-id="7aa10-129">CheckBox</span><span class="sxs-lookup"><span data-stu-id="7aa10-129">CheckBox</span></span>|  
|<span data-ttu-id="7aa10-130">ComboBoxEx32</span><span class="sxs-lookup"><span data-stu-id="7aa10-130">ComboBoxEx32</span></span>|<span data-ttu-id="7aa10-131">组合框</span><span class="sxs-lookup"><span data-stu-id="7aa10-131">ComboBox</span></span>|  
|<span data-ttu-id="7aa10-132">组合框</span><span class="sxs-lookup"><span data-stu-id="7aa10-132">ComboBox</span></span>|<span data-ttu-id="7aa10-133">组合框</span><span class="sxs-lookup"><span data-stu-id="7aa10-133">ComboBox</span></span>|  
|<span data-ttu-id="7aa10-134">Edit</span><span class="sxs-lookup"><span data-stu-id="7aa10-134">Edit</span></span>|<span data-ttu-id="7aa10-135">Document</span><span class="sxs-lookup"><span data-stu-id="7aa10-135">Document</span></span>|  
|<span data-ttu-id="7aa10-136">Edit</span><span class="sxs-lookup"><span data-stu-id="7aa10-136">Edit</span></span>|<span data-ttu-id="7aa10-137">Edit</span><span class="sxs-lookup"><span data-stu-id="7aa10-137">Edit</span></span>|  
|<span data-ttu-id="7aa10-138">SysLink</span><span class="sxs-lookup"><span data-stu-id="7aa10-138">SysLink</span></span>|<span data-ttu-id="7aa10-139">超链接</span><span class="sxs-lookup"><span data-stu-id="7aa10-139">Hyperlink</span></span>|  
|<span data-ttu-id="7aa10-140">Static</span><span class="sxs-lookup"><span data-stu-id="7aa10-140">Static</span></span>|<span data-ttu-id="7aa10-141">Text</span><span class="sxs-lookup"><span data-stu-id="7aa10-141">Text</span></span>|  
|<span data-ttu-id="7aa10-142">Static</span><span class="sxs-lookup"><span data-stu-id="7aa10-142">Static</span></span>|<span data-ttu-id="7aa10-143">图像</span><span class="sxs-lookup"><span data-stu-id="7aa10-143">Image</span></span>|  
|<span data-ttu-id="7aa10-144">SysIPAddress32</span><span class="sxs-lookup"><span data-stu-id="7aa10-144">SysIPAddress32</span></span>|<span data-ttu-id="7aa10-145">自定义</span><span class="sxs-lookup"><span data-stu-id="7aa10-145">Custom</span></span>|  
|<span data-ttu-id="7aa10-146">SysHeader32</span><span class="sxs-lookup"><span data-stu-id="7aa10-146">SysHeader32</span></span>|<span data-ttu-id="7aa10-147">Header/HeaderItem</span><span class="sxs-lookup"><span data-stu-id="7aa10-147">Header/HeaderItem</span></span>|  
|<span data-ttu-id="7aa10-148">SysListView32</span><span class="sxs-lookup"><span data-stu-id="7aa10-148">SysListView32</span></span>|<span data-ttu-id="7aa10-149">DataGrid</span><span class="sxs-lookup"><span data-stu-id="7aa10-149">DataGrid</span></span>|  
|<span data-ttu-id="7aa10-150">SysListView32</span><span class="sxs-lookup"><span data-stu-id="7aa10-150">SysListView32</span></span>|<span data-ttu-id="7aa10-151">列表</span><span class="sxs-lookup"><span data-stu-id="7aa10-151">List</span></span>|  
|<span data-ttu-id="7aa10-152">ListBox</span><span class="sxs-lookup"><span data-stu-id="7aa10-152">ListBox</span></span>|<span data-ttu-id="7aa10-153">列表</span><span class="sxs-lookup"><span data-stu-id="7aa10-153">List</span></span>|  
|<span data-ttu-id="7aa10-154">ListBox</span><span class="sxs-lookup"><span data-stu-id="7aa10-154">ListBox</span></span>|<span data-ttu-id="7aa10-155">ListItem</span><span class="sxs-lookup"><span data-stu-id="7aa10-155">ListItem</span></span>|  
|<span data-ttu-id="7aa10-156">#32768</span><span class="sxs-lookup"><span data-stu-id="7aa10-156">#32768</span></span>|<span data-ttu-id="7aa10-157">菜单</span><span class="sxs-lookup"><span data-stu-id="7aa10-157">Menu</span></span>|  
|<span data-ttu-id="7aa10-158">#32768</span><span class="sxs-lookup"><span data-stu-id="7aa10-158">#32768</span></span>|<span data-ttu-id="7aa10-159">MenuItem</span><span class="sxs-lookup"><span data-stu-id="7aa10-159">MenuItem</span></span>|  
|<span data-ttu-id="7aa10-160">msctls_progress32</span><span class="sxs-lookup"><span data-stu-id="7aa10-160">msctls_progress32</span></span>|<span data-ttu-id="7aa10-161">ProgressBar</span><span class="sxs-lookup"><span data-stu-id="7aa10-161">ProgressBar</span></span>|  
|<span data-ttu-id="7aa10-162">RichEdit</span><span class="sxs-lookup"><span data-stu-id="7aa10-162">RichEdit</span></span>|<span data-ttu-id="7aa10-163">Document。</span><span class="sxs-lookup"><span data-stu-id="7aa10-163">Document.</span></span> <span data-ttu-id="7aa10-164">请参阅注释。</span><span class="sxs-lookup"><span data-stu-id="7aa10-164">See note.</span></span>|  
|<span data-ttu-id="7aa10-165">RichEdit20A</span><span class="sxs-lookup"><span data-stu-id="7aa10-165">RichEdit20A</span></span>|<span data-ttu-id="7aa10-166">Document</span><span class="sxs-lookup"><span data-stu-id="7aa10-166">Document</span></span>|  
|<span data-ttu-id="7aa10-167">RichEdit20W</span><span class="sxs-lookup"><span data-stu-id="7aa10-167">RichEdit20W</span></span>|<span data-ttu-id="7aa10-168">Document</span><span class="sxs-lookup"><span data-stu-id="7aa10-168">Document</span></span>|  
|<span data-ttu-id="7aa10-169">RichEdit50W</span><span class="sxs-lookup"><span data-stu-id="7aa10-169">RichEdit50W</span></span>|<span data-ttu-id="7aa10-170">Document</span><span class="sxs-lookup"><span data-stu-id="7aa10-170">Document</span></span>|  
|<span data-ttu-id="7aa10-171">ScrollBar</span><span class="sxs-lookup"><span data-stu-id="7aa10-171">ScrollBar</span></span>|<span data-ttu-id="7aa10-172">Slider</span><span class="sxs-lookup"><span data-stu-id="7aa10-172">Slider</span></span>|  
|<span data-ttu-id="7aa10-173">msctls_trackbar32</span><span class="sxs-lookup"><span data-stu-id="7aa10-173">msctls_trackbar32</span></span>|<span data-ttu-id="7aa10-174">Slider</span><span class="sxs-lookup"><span data-stu-id="7aa10-174">Slider</span></span>|  
|<span data-ttu-id="7aa10-175">msctls_updown32</span><span class="sxs-lookup"><span data-stu-id="7aa10-175">msctls_updown32</span></span>|<span data-ttu-id="7aa10-176">Spinner</span><span class="sxs-lookup"><span data-stu-id="7aa10-176">Spinner</span></span>|  
|<span data-ttu-id="7aa10-177">msctls_statusbar32</span><span class="sxs-lookup"><span data-stu-id="7aa10-177">msctls_statusbar32</span></span>|<span data-ttu-id="7aa10-178">StatusBar</span><span class="sxs-lookup"><span data-stu-id="7aa10-178">StatusBar</span></span>|  
|<span data-ttu-id="7aa10-179">SysTabControl32</span><span class="sxs-lookup"><span data-stu-id="7aa10-179">SysTabControl32</span></span>|<span data-ttu-id="7aa10-180">Tab</span><span class="sxs-lookup"><span data-stu-id="7aa10-180">Tab</span></span>|  
|<span data-ttu-id="7aa10-181">SysTabControl32</span><span class="sxs-lookup"><span data-stu-id="7aa10-181">SysTabControl32</span></span>|<span data-ttu-id="7aa10-182">TabItem</span><span class="sxs-lookup"><span data-stu-id="7aa10-182">TabItem</span></span>|  
|<span data-ttu-id="7aa10-183">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="7aa10-183">ToolbarWindow32</span></span>|<span data-ttu-id="7aa10-184">ToolBar</span><span class="sxs-lookup"><span data-stu-id="7aa10-184">ToolBar</span></span>|  
|<span data-ttu-id="7aa10-185">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="7aa10-185">ToolbarWindow32</span></span>|<span data-ttu-id="7aa10-186">MenuItem</span><span class="sxs-lookup"><span data-stu-id="7aa10-186">MenuItem</span></span>|  
|<span data-ttu-id="7aa10-187">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="7aa10-187">ToolbarWindow32</span></span>|<span data-ttu-id="7aa10-188">Button</span><span class="sxs-lookup"><span data-stu-id="7aa10-188">Button</span></span>|  
|<span data-ttu-id="7aa10-189">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="7aa10-189">ToolbarWindow32</span></span>|<span data-ttu-id="7aa10-190">CheckBox</span><span class="sxs-lookup"><span data-stu-id="7aa10-190">CheckBox</span></span>|  
|<span data-ttu-id="7aa10-191">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="7aa10-191">ToolbarWindow32</span></span>|<span data-ttu-id="7aa10-192">RadioButton</span><span class="sxs-lookup"><span data-stu-id="7aa10-192">RadioButton</span></span>|  
|<span data-ttu-id="7aa10-193">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="7aa10-193">ToolbarWindow32</span></span>|<span data-ttu-id="7aa10-194">Separator</span><span class="sxs-lookup"><span data-stu-id="7aa10-194">Separator</span></span>|  
|<span data-ttu-id="7aa10-195">tooltips_class32</span><span class="sxs-lookup"><span data-stu-id="7aa10-195">tooltips_class32</span></span>|<span data-ttu-id="7aa10-196">ToolTip</span><span class="sxs-lookup"><span data-stu-id="7aa10-196">ToolTip</span></span>|  
|<span data-ttu-id="7aa10-197">#32774</span><span class="sxs-lookup"><span data-stu-id="7aa10-197">#32774</span></span>|<span data-ttu-id="7aa10-198">ToolTip</span><span class="sxs-lookup"><span data-stu-id="7aa10-198">ToolTip</span></span>|  
|<span data-ttu-id="7aa10-199">ReBarWindow32</span><span class="sxs-lookup"><span data-stu-id="7aa10-199">ReBarWindow32</span></span>|<span data-ttu-id="7aa10-200">Toolbar</span><span class="sxs-lookup"><span data-stu-id="7aa10-200">Toolbar</span></span>|  
|<span data-ttu-id="7aa10-201">SysTreeView32</span><span class="sxs-lookup"><span data-stu-id="7aa10-201">SysTreeView32</span></span>|<span data-ttu-id="7aa10-202">树</span><span class="sxs-lookup"><span data-stu-id="7aa10-202">Tree</span></span>|  
|<span data-ttu-id="7aa10-203">SysTreeView32</span><span class="sxs-lookup"><span data-stu-id="7aa10-203">SysTreeView32</span></span>|<span data-ttu-id="7aa10-204">TreeItem</span><span class="sxs-lookup"><span data-stu-id="7aa10-204">TreeItem</span></span>|  
  
 <span data-ttu-id="7aa10-205">**注意** 仅在随 [!INCLUDE[TLA#tla_winvista](../../../includes/tlasharptla-winvista-md.md)] 一起提供的版本中（在 RichEd20.dll 中为版本 3.1 和更高版本，在 MsftEdit.dll 中为版本 4.1 和更高版本）支持 RichEdit 控件。</span><span class="sxs-lookup"><span data-stu-id="7aa10-205">**Note** The RichEdit control is supported only for versions shipped with [!INCLUDE[TLA#tla_winvista](../../../includes/tlasharptla-winvista-md.md)] (in RichEd20.dll version 3.1 and later, and MsftEdit.dll version 4.1 and later).</span></span>  
  
 <span data-ttu-id="7aa10-206">不支持以下控件。</span><span class="sxs-lookup"><span data-stu-id="7aa10-206">The following controls are not supported.</span></span>  
  
|<span data-ttu-id="7aa10-207">类名</span><span class="sxs-lookup"><span data-stu-id="7aa10-207">Class name</span></span>|<span data-ttu-id="7aa10-208">控件类型</span><span class="sxs-lookup"><span data-stu-id="7aa10-208">Control type</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="7aa10-209">SysAnimate32</span><span class="sxs-lookup"><span data-stu-id="7aa10-209">SysAnimate32</span></span>|<span data-ttu-id="7aa10-210">图像</span><span class="sxs-lookup"><span data-stu-id="7aa10-210">Image</span></span>|  
|<span data-ttu-id="7aa10-211">SysPager</span><span class="sxs-lookup"><span data-stu-id="7aa10-211">SysPager</span></span>|<span data-ttu-id="7aa10-212">Spinner</span><span class="sxs-lookup"><span data-stu-id="7aa10-212">Spinner</span></span>|  
|<span data-ttu-id="7aa10-213">SysDateTimePick32</span><span class="sxs-lookup"><span data-stu-id="7aa10-213">SysDateTimePick32</span></span>|<span data-ttu-id="7aa10-214">自定义</span><span class="sxs-lookup"><span data-stu-id="7aa10-214">Custom</span></span>|  
|<span data-ttu-id="7aa10-215">SysMonthCal32</span><span class="sxs-lookup"><span data-stu-id="7aa10-215">SysMonthCal32</span></span>|<span data-ttu-id="7aa10-216">Calendar</span><span class="sxs-lookup"><span data-stu-id="7aa10-216">Calendar</span></span>|  
|<span data-ttu-id="7aa10-217">MS_WINNOTE</span><span class="sxs-lookup"><span data-stu-id="7aa10-217">MS_WINNOTE</span></span>|<span data-ttu-id="7aa10-218">ToolTip</span><span class="sxs-lookup"><span data-stu-id="7aa10-218">Tooltip</span></span>|  
|<span data-ttu-id="7aa10-219">VBBubble</span><span class="sxs-lookup"><span data-stu-id="7aa10-219">VBBubble</span></span>|<span data-ttu-id="7aa10-220">ToolTip</span><span class="sxs-lookup"><span data-stu-id="7aa10-220">Tooltip</span></span>|  
|<span data-ttu-id="7aa10-221">ScrollBar（在用作独立控件时）</span><span class="sxs-lookup"><span data-stu-id="7aa10-221">ScrollBar (when used as a standalone control)</span></span>|<span data-ttu-id="7aa10-222">Slider</span><span class="sxs-lookup"><span data-stu-id="7aa10-222">Slider</span></span>|  
|<span data-ttu-id="7aa10-223">SuperGrid</span><span class="sxs-lookup"><span data-stu-id="7aa10-223">SuperGrid</span></span>|<span data-ttu-id="7aa10-224">自定义</span><span class="sxs-lookup"><span data-stu-id="7aa10-224">Custom</span></span>|  
  
<a name="Windows_Forms_Controls"></a>   
## <a name="windows-forms-controls"></a><span data-ttu-id="7aa10-225">Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="7aa10-225">Windows Forms Controls</span></span>  
 <span data-ttu-id="7aa10-226">Windows 窗体控件公开给[!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)]通过 UIAutomationClientsideProviders.dll 中的客户端提供程序。</span><span class="sxs-lookup"><span data-stu-id="7aa10-226">Windows Forms controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] through client-side providers in UIAutomationClientsideProviders.dll.</span></span> <span data-ttu-id="7aa10-227">此程序集将自动注册，以用于 UI 自动化客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="7aa10-227">This assembly is automatically registered for use with UI Automation client applications.</span></span>  
  
 <span data-ttu-id="7aa10-228">通常情况下，Windows 窗体控件的托管包装[!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)]公共控件支持的[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="7aa10-228">Typically, Windows Forms controls that are managed wrappers for [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] common controls are supported by [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span> <span data-ttu-id="7aa10-229">支持以下控件。</span><span class="sxs-lookup"><span data-stu-id="7aa10-229">The following controls are supported.</span></span>  
  
|<span data-ttu-id="7aa10-230">类名</span><span class="sxs-lookup"><span data-stu-id="7aa10-230">Class Name</span></span>|  
|----------------|  
|<span data-ttu-id="7aa10-231">Button</span><span class="sxs-lookup"><span data-stu-id="7aa10-231">Button</span></span>|  
|<span data-ttu-id="7aa10-232">CheckBox</span><span class="sxs-lookup"><span data-stu-id="7aa10-232">CheckBox</span></span>|  
|<span data-ttu-id="7aa10-233">CheckedListBox</span><span class="sxs-lookup"><span data-stu-id="7aa10-233">CheckedListBox</span></span>|  
|<span data-ttu-id="7aa10-234">ColorDialog</span><span class="sxs-lookup"><span data-stu-id="7aa10-234">ColorDialog</span></span>|  
|<span data-ttu-id="7aa10-235">组合框</span><span class="sxs-lookup"><span data-stu-id="7aa10-235">ComboBox</span></span>|  
|<span data-ttu-id="7aa10-236">FolderBrowser</span><span class="sxs-lookup"><span data-stu-id="7aa10-236">FolderBrowser</span></span>|  
|<span data-ttu-id="7aa10-237">FontDialog</span><span class="sxs-lookup"><span data-stu-id="7aa10-237">FontDialog</span></span>|  
|<span data-ttu-id="7aa10-238">GroupBox</span><span class="sxs-lookup"><span data-stu-id="7aa10-238">GroupBox</span></span>|  
|<span data-ttu-id="7aa10-239">HscrollBar</span><span class="sxs-lookup"><span data-stu-id="7aa10-239">HscrollBar</span></span>|  
|<span data-ttu-id="7aa10-240">ImageList</span><span class="sxs-lookup"><span data-stu-id="7aa10-240">ImageList</span></span>|  
|<span data-ttu-id="7aa10-241">Label</span><span class="sxs-lookup"><span data-stu-id="7aa10-241">Label</span></span>|  
|<span data-ttu-id="7aa10-242">ListBox</span><span class="sxs-lookup"><span data-stu-id="7aa10-242">ListBox</span></span>|  
|<span data-ttu-id="7aa10-243">ListView</span><span class="sxs-lookup"><span data-stu-id="7aa10-243">ListView</span></span>|  
|<span data-ttu-id="7aa10-244">MainMenu/ContextMenu</span><span class="sxs-lookup"><span data-stu-id="7aa10-244">MainMenu/ContextMenu</span></span>|  
|<span data-ttu-id="7aa10-245">MonthCalendar</span><span class="sxs-lookup"><span data-stu-id="7aa10-245">MonthCalendar</span></span>|  
|<span data-ttu-id="7aa10-246">NotifyIcon</span><span class="sxs-lookup"><span data-stu-id="7aa10-246">NotifyIcon</span></span>|  
|<span data-ttu-id="7aa10-247">OpenFileDialog</span><span class="sxs-lookup"><span data-stu-id="7aa10-247">OpenFileDialog</span></span>|  
|<span data-ttu-id="7aa10-248">PageSetupDialog</span><span class="sxs-lookup"><span data-stu-id="7aa10-248">PageSetupDialog</span></span>|  
|<span data-ttu-id="7aa10-249">PrintDialog</span><span class="sxs-lookup"><span data-stu-id="7aa10-249">PrintDialog</span></span>|  
|<span data-ttu-id="7aa10-250">ProgressBar</span><span class="sxs-lookup"><span data-stu-id="7aa10-250">ProgressBar</span></span>|  
|<span data-ttu-id="7aa10-251">RadioButton</span><span class="sxs-lookup"><span data-stu-id="7aa10-251">RadioButton</span></span>|  
|<span data-ttu-id="7aa10-252">RichTextBox</span><span class="sxs-lookup"><span data-stu-id="7aa10-252">RichTextBox</span></span>|  
|<span data-ttu-id="7aa10-253">SaveFileDialog</span><span class="sxs-lookup"><span data-stu-id="7aa10-253">SaveFileDialog</span></span>|  
|<span data-ttu-id="7aa10-254">ScrollableControl</span><span class="sxs-lookup"><span data-stu-id="7aa10-254">ScrollableControl</span></span>|  
|<span data-ttu-id="7aa10-255">SoundPlayer</span><span class="sxs-lookup"><span data-stu-id="7aa10-255">SoundPlayer</span></span>|  
|<span data-ttu-id="7aa10-256">StatusBar</span><span class="sxs-lookup"><span data-stu-id="7aa10-256">StatusBar</span></span>|  
|<span data-ttu-id="7aa10-257">TabControl/TabPage</span><span class="sxs-lookup"><span data-stu-id="7aa10-257">TabControl/TabPage</span></span>|  
|<span data-ttu-id="7aa10-258">文本框</span><span class="sxs-lookup"><span data-stu-id="7aa10-258">TextBox</span></span>|  
|<span data-ttu-id="7aa10-259">计时器</span><span class="sxs-lookup"><span data-stu-id="7aa10-259">Timer</span></span>|  
|<span data-ttu-id="7aa10-260">ToolBar</span><span class="sxs-lookup"><span data-stu-id="7aa10-260">Toolbar</span></span>|  
|<span data-ttu-id="7aa10-261">ToolTip</span><span class="sxs-lookup"><span data-stu-id="7aa10-261">ToolTip</span></span>|  
|<span data-ttu-id="7aa10-262">TrackBar</span><span class="sxs-lookup"><span data-stu-id="7aa10-262">TrackBar</span></span>|  
|<span data-ttu-id="7aa10-263">TreeView</span><span class="sxs-lookup"><span data-stu-id="7aa10-263">TreeView</span></span>|  
|<span data-ttu-id="7aa10-264">VscrollBar</span><span class="sxs-lookup"><span data-stu-id="7aa10-264">VscrollBar</span></span>|  
|<span data-ttu-id="7aa10-265">Web 浏览器</span><span class="sxs-lookup"><span data-stu-id="7aa10-265">WebBrowser</span></span>|  
  
 <span data-ttu-id="7aa10-266">以下控件仅通过其对 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] 的支持向 [!INCLUDE[TLA#tla_aa](../../../includes/tlasharptla-aa-md.md)]公开。</span><span class="sxs-lookup"><span data-stu-id="7aa10-266">The following controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] only through their support for [!INCLUDE[TLA#tla_aa](../../../includes/tlasharptla-aa-md.md)].</span></span> <span data-ttu-id="7aa10-267">某些功能可能不可用。</span><span class="sxs-lookup"><span data-stu-id="7aa10-267">Some functionality may not be available.</span></span>  
  
|<span data-ttu-id="7aa10-268">控件名称</span><span class="sxs-lookup"><span data-stu-id="7aa10-268">Control Name</span></span>|  
|------------------|  
|<span data-ttu-id="7aa10-269">BindingSource</span><span class="sxs-lookup"><span data-stu-id="7aa10-269">BindingSource</span></span>|  
|<span data-ttu-id="7aa10-270">DataGrid</span><span class="sxs-lookup"><span data-stu-id="7aa10-270">DataGrid</span></span>|  
|<span data-ttu-id="7aa10-271">DataGridView</span><span class="sxs-lookup"><span data-stu-id="7aa10-271">DataGridView</span></span>|  
|<span data-ttu-id="7aa10-272">DataNavigator</span><span class="sxs-lookup"><span data-stu-id="7aa10-272">DataNavigator</span></span>|  
|<span data-ttu-id="7aa10-273">DomainUpDown</span><span class="sxs-lookup"><span data-stu-id="7aa10-273">DomainUpDown</span></span>|  
|<span data-ttu-id="7aa10-274">ErrorProvider</span><span class="sxs-lookup"><span data-stu-id="7aa10-274">ErrorProvider</span></span>|  
|<span data-ttu-id="7aa10-275">FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="7aa10-275">FlowLayoutPanel</span></span>|  
|<span data-ttu-id="7aa10-276">窗体</span><span class="sxs-lookup"><span data-stu-id="7aa10-276">Form</span></span>|  
|<span data-ttu-id="7aa10-277">LinkLabel</span><span class="sxs-lookup"><span data-stu-id="7aa10-277">LinkLabel</span></span>|  
|<span data-ttu-id="7aa10-278">HelpProvider</span><span class="sxs-lookup"><span data-stu-id="7aa10-278">HelpProvider</span></span>|  
|<span data-ttu-id="7aa10-279">MaskedTextBox</span><span class="sxs-lookup"><span data-stu-id="7aa10-279">MaskedTextBox</span></span>|  
|<span data-ttu-id="7aa10-280">MenuStrip/ContextMenuStrip</span><span class="sxs-lookup"><span data-stu-id="7aa10-280">MenuStrip/ContextMenuStrip</span></span>|  
|<span data-ttu-id="7aa10-281">NumericUpDown</span><span class="sxs-lookup"><span data-stu-id="7aa10-281">NumericUpDown</span></span>|  
|<span data-ttu-id="7aa10-282">Panel</span><span class="sxs-lookup"><span data-stu-id="7aa10-282">Panel</span></span>|  
|<span data-ttu-id="7aa10-283">PictureBox</span><span class="sxs-lookup"><span data-stu-id="7aa10-283">PictureBox</span></span>|  
|<span data-ttu-id="7aa10-284">PrintDocument</span><span class="sxs-lookup"><span data-stu-id="7aa10-284">PrintDocument</span></span>|  
|<span data-ttu-id="7aa10-285">PrintPreview-Control</span><span class="sxs-lookup"><span data-stu-id="7aa10-285">PrintPreview-Control</span></span>|  
|<span data-ttu-id="7aa10-286">PrintPreview-Dialog</span><span class="sxs-lookup"><span data-stu-id="7aa10-286">PrintPreview-Dialog</span></span>|  
|<span data-ttu-id="7aa10-287">PropertyGrid</span><span class="sxs-lookup"><span data-stu-id="7aa10-287">PropertyGrid</span></span>|  
|<span data-ttu-id="7aa10-288">用户控件</span><span class="sxs-lookup"><span data-stu-id="7aa10-288">UserControl</span></span>|  
|<span data-ttu-id="7aa10-289">ToolStrip</span><span class="sxs-lookup"><span data-stu-id="7aa10-289">ToolStrip</span></span>|  
|<span data-ttu-id="7aa10-290">TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="7aa10-290">TableLayoutPanel</span></span>|  
|<span data-ttu-id="7aa10-291">SplitContainer/SplitterPanel</span><span class="sxs-lookup"><span data-stu-id="7aa10-291">SplitContainer/SplitterPanel</span></span>|  
|<span data-ttu-id="7aa10-292">Splitter</span><span class="sxs-lookup"><span data-stu-id="7aa10-292">Splitter</span></span>|  
|<span data-ttu-id="7aa10-293">RaftingContainer</span><span class="sxs-lookup"><span data-stu-id="7aa10-293">RaftingContainer</span></span>|  
|<span data-ttu-id="7aa10-294">StatusStrip</span><span class="sxs-lookup"><span data-stu-id="7aa10-294">StatusStrip</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7aa10-295">请参阅</span><span class="sxs-lookup"><span data-stu-id="7aa10-295">See Also</span></span>  
 [<span data-ttu-id="7aa10-296">UI 自动化控件类型</span><span class="sxs-lookup"><span data-stu-id="7aa10-296">UI Automation Control Types</span></span>](../../../docs/framework/ui-automation/ui-automation-control-types.md)
