---
title: UI 自动化对标准控件的支持
ms.date: 03/30/2017
helpviewer_keywords:
- controls, UI Automation support for
- UI Automation, support for standard controls
ms.assetid: 3770ea8a-2655-4add-9c59-fe0610ad5084
ms.openlocfilehash: 314526c1164f70e6b261df1a6f11ddce2b5fa240
ms.sourcegitcommit: 42ed59871db1f29a32b3d8e7abeb20e6eceeda7c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2019
ms.locfileid: "74960077"
---
# <a name="ui-automation-support-for-standard-controls"></a><span data-ttu-id="bdfbb-102">UI 自动化对标准控件的支持</span><span class="sxs-lookup"><span data-stu-id="bdfbb-102">UI Automation Support for Standard Controls</span></span>
> [!NOTE]
> <span data-ttu-id="bdfbb-103">本文档适用于想要使用 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 命名空间中定义的托管 <xref:System.Windows.Automation> 类的 .NET Framework 开发人员。</span><span class="sxs-lookup"><span data-stu-id="bdfbb-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="bdfbb-104">有关 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]的最新信息，请参阅 [Windows 自动化 API：UI 自动化](/windows/win32/winauto/entry-uiauto-win32)。</span><span class="sxs-lookup"><span data-stu-id="bdfbb-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="bdfbb-105">本主题包含有关对为 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] 、 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)]和 [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)]框架所开发的应用程序中标准控件的 [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)] 支持的信息。</span><span class="sxs-lookup"><span data-stu-id="bdfbb-105">This topic contains information about [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] support for standard controls in applications developed for the [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)], [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)], and [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)] frameworks.</span></span>  
  
<a name="Windows_Presentation_Foundation_Controls"></a>   
## <a name="windows-presentation-foundation-controls"></a><span data-ttu-id="bdfbb-106">Windows Presentation Foundation 控件</span><span class="sxs-lookup"><span data-stu-id="bdfbb-106">Windows Presentation Foundation Controls</span></span>  
 <span data-ttu-id="bdfbb-107">为用户交互提供信息或支持的所有 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 控件元素均具有对 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]的完整本机支持。</span><span class="sxs-lookup"><span data-stu-id="bdfbb-107">All [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] control elements that provide information or support for user interaction have full native support for [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span> <span data-ttu-id="bdfbb-108">面板等其他元素对 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]不可见。</span><span class="sxs-lookup"><span data-stu-id="bdfbb-108">Other elements, such as panels, are not visible to [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span>  
  
<a name="Win32_Controls"></a>   
## <a name="win32-controls"></a><span data-ttu-id="bdfbb-109">Win32 控件</span><span class="sxs-lookup"><span data-stu-id="bdfbb-109">Win32 Controls</span></span>  
 <span data-ttu-id="bdfbb-110">大多数 [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] 控件都通过 UIAutomationClientsideProviders.dll 中的客户端提供程序向 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] 公开。</span><span class="sxs-lookup"><span data-stu-id="bdfbb-110">Most [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] through client-side providers in UIAutomationClientsideProviders.dll.</span></span> <span data-ttu-id="bdfbb-111">此程序集将自动注册，以用于 UI 自动化客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="bdfbb-111">This assembly is automatically registered for use with UI Automation client applications.</span></span>  
  
 <span data-ttu-id="bdfbb-112">仅为*对 comctrl32.dll*版本6中的控件提供完全支持。</span><span class="sxs-lookup"><span data-stu-id="bdfbb-112">Full support is provided only for controls from version 6 of *ComCtrl32.dll*.</span></span>  
  
 <span data-ttu-id="bdfbb-113">支持以下控件。</span><span class="sxs-lookup"><span data-stu-id="bdfbb-113">The following controls are supported.</span></span>  
  
|<span data-ttu-id="bdfbb-114">类名</span><span class="sxs-lookup"><span data-stu-id="bdfbb-114">Class name</span></span>|<span data-ttu-id="bdfbb-115">控件类型</span><span class="sxs-lookup"><span data-stu-id="bdfbb-115">Control Type</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="bdfbb-116">Button</span><span class="sxs-lookup"><span data-stu-id="bdfbb-116">Button</span></span>|<span data-ttu-id="bdfbb-117">Button</span><span class="sxs-lookup"><span data-stu-id="bdfbb-117">Button</span></span>|  
|<span data-ttu-id="bdfbb-118">Button</span><span class="sxs-lookup"><span data-stu-id="bdfbb-118">Button</span></span>|<span data-ttu-id="bdfbb-119">RadioButton</span><span class="sxs-lookup"><span data-stu-id="bdfbb-119">RadioButton</span></span>|  
|<span data-ttu-id="bdfbb-120">Button</span><span class="sxs-lookup"><span data-stu-id="bdfbb-120">Button</span></span>|<span data-ttu-id="bdfbb-121">组</span><span class="sxs-lookup"><span data-stu-id="bdfbb-121">Group</span></span>|  
|<span data-ttu-id="bdfbb-122">Button</span><span class="sxs-lookup"><span data-stu-id="bdfbb-122">Button</span></span>|<span data-ttu-id="bdfbb-123">CheckBox</span><span class="sxs-lookup"><span data-stu-id="bdfbb-123">CheckBox</span></span>|  
|<span data-ttu-id="bdfbb-124">Button</span><span class="sxs-lookup"><span data-stu-id="bdfbb-124">Button</span></span>|<span data-ttu-id="bdfbb-125">超链接</span><span class="sxs-lookup"><span data-stu-id="bdfbb-125">Hyperlink</span></span>|  
|<span data-ttu-id="bdfbb-126">Button</span><span class="sxs-lookup"><span data-stu-id="bdfbb-126">Button</span></span>|<span data-ttu-id="bdfbb-127">SplitButton</span><span class="sxs-lookup"><span data-stu-id="bdfbb-127">SplitButton</span></span>|  
|<span data-ttu-id="bdfbb-128">Button</span><span class="sxs-lookup"><span data-stu-id="bdfbb-128">Button</span></span>|<span data-ttu-id="bdfbb-129">CheckBox</span><span class="sxs-lookup"><span data-stu-id="bdfbb-129">CheckBox</span></span>|  
|<span data-ttu-id="bdfbb-130">ComboBoxEx32</span><span class="sxs-lookup"><span data-stu-id="bdfbb-130">ComboBoxEx32</span></span>|<span data-ttu-id="bdfbb-131">组合框</span><span class="sxs-lookup"><span data-stu-id="bdfbb-131">ComboBox</span></span>|  
|<span data-ttu-id="bdfbb-132">组合框</span><span class="sxs-lookup"><span data-stu-id="bdfbb-132">ComboBox</span></span>|<span data-ttu-id="bdfbb-133">组合框</span><span class="sxs-lookup"><span data-stu-id="bdfbb-133">ComboBox</span></span>|  
|<span data-ttu-id="bdfbb-134">Edit</span><span class="sxs-lookup"><span data-stu-id="bdfbb-134">Edit</span></span>|<span data-ttu-id="bdfbb-135">Document</span><span class="sxs-lookup"><span data-stu-id="bdfbb-135">Document</span></span>|  
|<span data-ttu-id="bdfbb-136">Edit</span><span class="sxs-lookup"><span data-stu-id="bdfbb-136">Edit</span></span>|<span data-ttu-id="bdfbb-137">Edit</span><span class="sxs-lookup"><span data-stu-id="bdfbb-137">Edit</span></span>|  
|<span data-ttu-id="bdfbb-138">SysLink</span><span class="sxs-lookup"><span data-stu-id="bdfbb-138">SysLink</span></span>|<span data-ttu-id="bdfbb-139">超链接</span><span class="sxs-lookup"><span data-stu-id="bdfbb-139">Hyperlink</span></span>|  
|<span data-ttu-id="bdfbb-140">Static</span><span class="sxs-lookup"><span data-stu-id="bdfbb-140">Static</span></span>|<span data-ttu-id="bdfbb-141">文本</span><span class="sxs-lookup"><span data-stu-id="bdfbb-141">Text</span></span>|  
|<span data-ttu-id="bdfbb-142">Static</span><span class="sxs-lookup"><span data-stu-id="bdfbb-142">Static</span></span>|<span data-ttu-id="bdfbb-143">Image</span><span class="sxs-lookup"><span data-stu-id="bdfbb-143">Image</span></span>|  
|<span data-ttu-id="bdfbb-144">SysIPAddress32</span><span class="sxs-lookup"><span data-stu-id="bdfbb-144">SysIPAddress32</span></span>|<span data-ttu-id="bdfbb-145">“自定义”</span><span class="sxs-lookup"><span data-stu-id="bdfbb-145">Custom</span></span>|  
|<span data-ttu-id="bdfbb-146">SysHeader32</span><span class="sxs-lookup"><span data-stu-id="bdfbb-146">SysHeader32</span></span>|<span data-ttu-id="bdfbb-147">Header/HeaderItem</span><span class="sxs-lookup"><span data-stu-id="bdfbb-147">Header/HeaderItem</span></span>|  
|<span data-ttu-id="bdfbb-148">SysListView32</span><span class="sxs-lookup"><span data-stu-id="bdfbb-148">SysListView32</span></span>|<span data-ttu-id="bdfbb-149">DataGrid</span><span class="sxs-lookup"><span data-stu-id="bdfbb-149">DataGrid</span></span>|  
|<span data-ttu-id="bdfbb-150">SysListView32</span><span class="sxs-lookup"><span data-stu-id="bdfbb-150">SysListView32</span></span>|<span data-ttu-id="bdfbb-151">列表</span><span class="sxs-lookup"><span data-stu-id="bdfbb-151">List</span></span>|  
|<span data-ttu-id="bdfbb-152">ListBox</span><span class="sxs-lookup"><span data-stu-id="bdfbb-152">ListBox</span></span>|<span data-ttu-id="bdfbb-153">列表</span><span class="sxs-lookup"><span data-stu-id="bdfbb-153">List</span></span>|  
|<span data-ttu-id="bdfbb-154">ListBox</span><span class="sxs-lookup"><span data-stu-id="bdfbb-154">ListBox</span></span>|<span data-ttu-id="bdfbb-155">ListItem</span><span class="sxs-lookup"><span data-stu-id="bdfbb-155">ListItem</span></span>|  
|<span data-ttu-id="bdfbb-156">#32768</span><span class="sxs-lookup"><span data-stu-id="bdfbb-156">#32768</span></span>|<span data-ttu-id="bdfbb-157">菜单</span><span class="sxs-lookup"><span data-stu-id="bdfbb-157">Menu</span></span>|  
|<span data-ttu-id="bdfbb-158">#32768</span><span class="sxs-lookup"><span data-stu-id="bdfbb-158">#32768</span></span>|<span data-ttu-id="bdfbb-159">MenuItem</span><span class="sxs-lookup"><span data-stu-id="bdfbb-159">MenuItem</span></span>|  
|<span data-ttu-id="bdfbb-160">msctls_progress32</span><span class="sxs-lookup"><span data-stu-id="bdfbb-160">msctls_progress32</span></span>|<span data-ttu-id="bdfbb-161">进度条</span><span class="sxs-lookup"><span data-stu-id="bdfbb-161">ProgressBar</span></span>|  
|<span data-ttu-id="bdfbb-162">RichEdit</span><span class="sxs-lookup"><span data-stu-id="bdfbb-162">RichEdit</span></span>|<span data-ttu-id="bdfbb-163">Document。</span><span class="sxs-lookup"><span data-stu-id="bdfbb-163">Document.</span></span> <span data-ttu-id="bdfbb-164">请参阅注释。</span><span class="sxs-lookup"><span data-stu-id="bdfbb-164">See note.</span></span>|  
|<span data-ttu-id="bdfbb-165">RichEdit20A</span><span class="sxs-lookup"><span data-stu-id="bdfbb-165">RichEdit20A</span></span>|<span data-ttu-id="bdfbb-166">Document</span><span class="sxs-lookup"><span data-stu-id="bdfbb-166">Document</span></span>|  
|<span data-ttu-id="bdfbb-167">RichEdit20W</span><span class="sxs-lookup"><span data-stu-id="bdfbb-167">RichEdit20W</span></span>|<span data-ttu-id="bdfbb-168">Document</span><span class="sxs-lookup"><span data-stu-id="bdfbb-168">Document</span></span>|  
|<span data-ttu-id="bdfbb-169">RichEdit50W</span><span class="sxs-lookup"><span data-stu-id="bdfbb-169">RichEdit50W</span></span>|<span data-ttu-id="bdfbb-170">Document</span><span class="sxs-lookup"><span data-stu-id="bdfbb-170">Document</span></span>|  
|<span data-ttu-id="bdfbb-171">ScrollBar</span><span class="sxs-lookup"><span data-stu-id="bdfbb-171">ScrollBar</span></span>|<span data-ttu-id="bdfbb-172">Slider</span><span class="sxs-lookup"><span data-stu-id="bdfbb-172">Slider</span></span>|  
|<span data-ttu-id="bdfbb-173">msctls_trackbar32</span><span class="sxs-lookup"><span data-stu-id="bdfbb-173">msctls_trackbar32</span></span>|<span data-ttu-id="bdfbb-174">Slider</span><span class="sxs-lookup"><span data-stu-id="bdfbb-174">Slider</span></span>|  
|<span data-ttu-id="bdfbb-175">msctls_updown32</span><span class="sxs-lookup"><span data-stu-id="bdfbb-175">msctls_updown32</span></span>|<span data-ttu-id="bdfbb-176">Spinner</span><span class="sxs-lookup"><span data-stu-id="bdfbb-176">Spinner</span></span>|  
|<span data-ttu-id="bdfbb-177">msctls_statusbar32</span><span class="sxs-lookup"><span data-stu-id="bdfbb-177">msctls_statusbar32</span></span>|<span data-ttu-id="bdfbb-178">StatusBar</span><span class="sxs-lookup"><span data-stu-id="bdfbb-178">StatusBar</span></span>|  
|<span data-ttu-id="bdfbb-179">SysTabControl32</span><span class="sxs-lookup"><span data-stu-id="bdfbb-179">SysTabControl32</span></span>|<span data-ttu-id="bdfbb-180">选项卡</span><span class="sxs-lookup"><span data-stu-id="bdfbb-180">Tab</span></span>|  
|<span data-ttu-id="bdfbb-181">SysTabControl32</span><span class="sxs-lookup"><span data-stu-id="bdfbb-181">SysTabControl32</span></span>|<span data-ttu-id="bdfbb-182">TabItem</span><span class="sxs-lookup"><span data-stu-id="bdfbb-182">TabItem</span></span>|  
|<span data-ttu-id="bdfbb-183">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="bdfbb-183">ToolbarWindow32</span></span>|<span data-ttu-id="bdfbb-184">ToolBar</span><span class="sxs-lookup"><span data-stu-id="bdfbb-184">ToolBar</span></span>|  
|<span data-ttu-id="bdfbb-185">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="bdfbb-185">ToolbarWindow32</span></span>|<span data-ttu-id="bdfbb-186">MenuItem</span><span class="sxs-lookup"><span data-stu-id="bdfbb-186">MenuItem</span></span>|  
|<span data-ttu-id="bdfbb-187">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="bdfbb-187">ToolbarWindow32</span></span>|<span data-ttu-id="bdfbb-188">Button</span><span class="sxs-lookup"><span data-stu-id="bdfbb-188">Button</span></span>|  
|<span data-ttu-id="bdfbb-189">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="bdfbb-189">ToolbarWindow32</span></span>|<span data-ttu-id="bdfbb-190">CheckBox</span><span class="sxs-lookup"><span data-stu-id="bdfbb-190">CheckBox</span></span>|  
|<span data-ttu-id="bdfbb-191">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="bdfbb-191">ToolbarWindow32</span></span>|<span data-ttu-id="bdfbb-192">RadioButton</span><span class="sxs-lookup"><span data-stu-id="bdfbb-192">RadioButton</span></span>|  
|<span data-ttu-id="bdfbb-193">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="bdfbb-193">ToolbarWindow32</span></span>|<span data-ttu-id="bdfbb-194">Separator</span><span class="sxs-lookup"><span data-stu-id="bdfbb-194">Separator</span></span>|  
|<span data-ttu-id="bdfbb-195">tooltips_class32</span><span class="sxs-lookup"><span data-stu-id="bdfbb-195">tooltips_class32</span></span>|<span data-ttu-id="bdfbb-196">工具提示</span><span class="sxs-lookup"><span data-stu-id="bdfbb-196">ToolTip</span></span>|  
|<span data-ttu-id="bdfbb-197">#32774</span><span class="sxs-lookup"><span data-stu-id="bdfbb-197">#32774</span></span>|<span data-ttu-id="bdfbb-198">工具提示</span><span class="sxs-lookup"><span data-stu-id="bdfbb-198">ToolTip</span></span>|  
|<span data-ttu-id="bdfbb-199">ReBarWindow32</span><span class="sxs-lookup"><span data-stu-id="bdfbb-199">ReBarWindow32</span></span>|<span data-ttu-id="bdfbb-200">Toolbar</span><span class="sxs-lookup"><span data-stu-id="bdfbb-200">Toolbar</span></span>|  
|<span data-ttu-id="bdfbb-201">SysTreeView32</span><span class="sxs-lookup"><span data-stu-id="bdfbb-201">SysTreeView32</span></span>|<span data-ttu-id="bdfbb-202">树</span><span class="sxs-lookup"><span data-stu-id="bdfbb-202">Tree</span></span>|  
|<span data-ttu-id="bdfbb-203">SysTreeView32</span><span class="sxs-lookup"><span data-stu-id="bdfbb-203">SysTreeView32</span></span>|<span data-ttu-id="bdfbb-204">TreeItem</span><span class="sxs-lookup"><span data-stu-id="bdfbb-204">TreeItem</span></span>|  
  
 <span data-ttu-id="bdfbb-205">**注意**只有 Windows Vista 附带的版本（在 Riched20.dll 版本3.1 及更高版本以及 Msftedit.dll 版本4.1 及更高版本）支持 RichEdit 控件。</span><span class="sxs-lookup"><span data-stu-id="bdfbb-205">**Note** The RichEdit control is supported only for versions shipped with Windows Vista (in RichEd20.dll version 3.1 and later, and MsftEdit.dll version 4.1 and later).</span></span>  
  
 <span data-ttu-id="bdfbb-206">不支持以下控件。</span><span class="sxs-lookup"><span data-stu-id="bdfbb-206">The following controls are not supported.</span></span>  
  
|<span data-ttu-id="bdfbb-207">类名</span><span class="sxs-lookup"><span data-stu-id="bdfbb-207">Class name</span></span>|<span data-ttu-id="bdfbb-208">控件类型</span><span class="sxs-lookup"><span data-stu-id="bdfbb-208">Control type</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="bdfbb-209">SysAnimate32</span><span class="sxs-lookup"><span data-stu-id="bdfbb-209">SysAnimate32</span></span>|<span data-ttu-id="bdfbb-210">Image</span><span class="sxs-lookup"><span data-stu-id="bdfbb-210">Image</span></span>|  
|<span data-ttu-id="bdfbb-211">SysPager</span><span class="sxs-lookup"><span data-stu-id="bdfbb-211">SysPager</span></span>|<span data-ttu-id="bdfbb-212">Spinner</span><span class="sxs-lookup"><span data-stu-id="bdfbb-212">Spinner</span></span>|  
|<span data-ttu-id="bdfbb-213">SysDateTimePick32</span><span class="sxs-lookup"><span data-stu-id="bdfbb-213">SysDateTimePick32</span></span>|<span data-ttu-id="bdfbb-214">“自定义”</span><span class="sxs-lookup"><span data-stu-id="bdfbb-214">Custom</span></span>|  
|<span data-ttu-id="bdfbb-215">SysMonthCal32</span><span class="sxs-lookup"><span data-stu-id="bdfbb-215">SysMonthCal32</span></span>|<span data-ttu-id="bdfbb-216">Calendar</span><span class="sxs-lookup"><span data-stu-id="bdfbb-216">Calendar</span></span>|  
|<span data-ttu-id="bdfbb-217">MS_WINNOTE</span><span class="sxs-lookup"><span data-stu-id="bdfbb-217">MS_WINNOTE</span></span>|<span data-ttu-id="bdfbb-218">ToolTip</span><span class="sxs-lookup"><span data-stu-id="bdfbb-218">Tooltip</span></span>|  
|<span data-ttu-id="bdfbb-219">VBBubble</span><span class="sxs-lookup"><span data-stu-id="bdfbb-219">VBBubble</span></span>|<span data-ttu-id="bdfbb-220">ToolTip</span><span class="sxs-lookup"><span data-stu-id="bdfbb-220">Tooltip</span></span>|  
|<span data-ttu-id="bdfbb-221">ScrollBar（在用作独立控件时）</span><span class="sxs-lookup"><span data-stu-id="bdfbb-221">ScrollBar (when used as a standalone control)</span></span>|<span data-ttu-id="bdfbb-222">Slider</span><span class="sxs-lookup"><span data-stu-id="bdfbb-222">Slider</span></span>|  
|<span data-ttu-id="bdfbb-223">SuperGrid</span><span class="sxs-lookup"><span data-stu-id="bdfbb-223">SuperGrid</span></span>|<span data-ttu-id="bdfbb-224">“自定义”</span><span class="sxs-lookup"><span data-stu-id="bdfbb-224">Custom</span></span>|  
  
<a name="Windows_Forms_Controls"></a>   
## <a name="windows-forms-controls"></a><span data-ttu-id="bdfbb-225">Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="bdfbb-225">Windows Forms Controls</span></span>  
 <span data-ttu-id="bdfbb-226">通过 Uiautomationclientsideproviders.dll 中的客户端提供程序 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] 公开 Windows 窗体控件。</span><span class="sxs-lookup"><span data-stu-id="bdfbb-226">Windows Forms controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] through client-side providers in UIAutomationClientsideProviders.dll.</span></span> <span data-ttu-id="bdfbb-227">此程序集将自动注册，以用于 UI 自动化客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="bdfbb-227">This assembly is automatically registered for use with UI Automation client applications.</span></span>  
  
 <span data-ttu-id="bdfbb-228">通常，[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]支持作为 [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] 公共控件的托管包装的 Windows 窗体控件。</span><span class="sxs-lookup"><span data-stu-id="bdfbb-228">Typically, Windows Forms controls that are managed wrappers for [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] common controls are supported by [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span> <span data-ttu-id="bdfbb-229">支持以下控件。</span><span class="sxs-lookup"><span data-stu-id="bdfbb-229">The following controls are supported.</span></span>  
  
|<span data-ttu-id="bdfbb-230">类名称</span><span class="sxs-lookup"><span data-stu-id="bdfbb-230">Class Name</span></span>|  
|----------------|  
|<span data-ttu-id="bdfbb-231">Button</span><span class="sxs-lookup"><span data-stu-id="bdfbb-231">Button</span></span>|  
|<span data-ttu-id="bdfbb-232">CheckBox</span><span class="sxs-lookup"><span data-stu-id="bdfbb-232">CheckBox</span></span>|  
|<span data-ttu-id="bdfbb-233">CheckedListBox</span><span class="sxs-lookup"><span data-stu-id="bdfbb-233">CheckedListBox</span></span>|  
|<span data-ttu-id="bdfbb-234">ColorDialog</span><span class="sxs-lookup"><span data-stu-id="bdfbb-234">ColorDialog</span></span>|  
|<span data-ttu-id="bdfbb-235">组合框</span><span class="sxs-lookup"><span data-stu-id="bdfbb-235">ComboBox</span></span>|  
|<span data-ttu-id="bdfbb-236">FolderBrowser</span><span class="sxs-lookup"><span data-stu-id="bdfbb-236">FolderBrowser</span></span>|  
|<span data-ttu-id="bdfbb-237">FontDialog</span><span class="sxs-lookup"><span data-stu-id="bdfbb-237">FontDialog</span></span>|  
|<span data-ttu-id="bdfbb-238">GroupBox</span><span class="sxs-lookup"><span data-stu-id="bdfbb-238">GroupBox</span></span>|  
|<span data-ttu-id="bdfbb-239">HscrollBar</span><span class="sxs-lookup"><span data-stu-id="bdfbb-239">HscrollBar</span></span>|  
|<span data-ttu-id="bdfbb-240">ImageList</span><span class="sxs-lookup"><span data-stu-id="bdfbb-240">ImageList</span></span>|  
|<span data-ttu-id="bdfbb-241">Label</span><span class="sxs-lookup"><span data-stu-id="bdfbb-241">Label</span></span>|  
|<span data-ttu-id="bdfbb-242">ListBox</span><span class="sxs-lookup"><span data-stu-id="bdfbb-242">ListBox</span></span>|  
|<span data-ttu-id="bdfbb-243">ListView</span><span class="sxs-lookup"><span data-stu-id="bdfbb-243">ListView</span></span>|  
|<span data-ttu-id="bdfbb-244">MainMenu/ContextMenu</span><span class="sxs-lookup"><span data-stu-id="bdfbb-244">MainMenu/ContextMenu</span></span>|  
|<span data-ttu-id="bdfbb-245">MonthCalendar</span><span class="sxs-lookup"><span data-stu-id="bdfbb-245">MonthCalendar</span></span>|  
|<span data-ttu-id="bdfbb-246">NotifyIcon</span><span class="sxs-lookup"><span data-stu-id="bdfbb-246">NotifyIcon</span></span>|  
|<span data-ttu-id="bdfbb-247">OpenFileDialog</span><span class="sxs-lookup"><span data-stu-id="bdfbb-247">OpenFileDialog</span></span>|  
|<span data-ttu-id="bdfbb-248">PageSetupDialog</span><span class="sxs-lookup"><span data-stu-id="bdfbb-248">PageSetupDialog</span></span>|  
|<span data-ttu-id="bdfbb-249">PrintDialog</span><span class="sxs-lookup"><span data-stu-id="bdfbb-249">PrintDialog</span></span>|  
|<span data-ttu-id="bdfbb-250">进度条</span><span class="sxs-lookup"><span data-stu-id="bdfbb-250">ProgressBar</span></span>|  
|<span data-ttu-id="bdfbb-251">RadioButton</span><span class="sxs-lookup"><span data-stu-id="bdfbb-251">RadioButton</span></span>|  
|<span data-ttu-id="bdfbb-252">RichTextBox</span><span class="sxs-lookup"><span data-stu-id="bdfbb-252">RichTextBox</span></span>|  
|<span data-ttu-id="bdfbb-253">SaveFileDialog</span><span class="sxs-lookup"><span data-stu-id="bdfbb-253">SaveFileDialog</span></span>|  
|<span data-ttu-id="bdfbb-254">ScrollableControl</span><span class="sxs-lookup"><span data-stu-id="bdfbb-254">ScrollableControl</span></span>|  
|<span data-ttu-id="bdfbb-255">SoundPlayer</span><span class="sxs-lookup"><span data-stu-id="bdfbb-255">SoundPlayer</span></span>|  
|<span data-ttu-id="bdfbb-256">StatusBar</span><span class="sxs-lookup"><span data-stu-id="bdfbb-256">StatusBar</span></span>|  
|<span data-ttu-id="bdfbb-257">TabControl/TabPage</span><span class="sxs-lookup"><span data-stu-id="bdfbb-257">TabControl/TabPage</span></span>|  
|<span data-ttu-id="bdfbb-258">文本框</span><span class="sxs-lookup"><span data-stu-id="bdfbb-258">TextBox</span></span>|  
|<span data-ttu-id="bdfbb-259">计时器</span><span class="sxs-lookup"><span data-stu-id="bdfbb-259">Timer</span></span>|  
|<span data-ttu-id="bdfbb-260">Toolbar</span><span class="sxs-lookup"><span data-stu-id="bdfbb-260">Toolbar</span></span>|  
|<span data-ttu-id="bdfbb-261">工具提示</span><span class="sxs-lookup"><span data-stu-id="bdfbb-261">ToolTip</span></span>|  
|<span data-ttu-id="bdfbb-262">TrackBar</span><span class="sxs-lookup"><span data-stu-id="bdfbb-262">TrackBar</span></span>|  
|<span data-ttu-id="bdfbb-263">TreeView</span><span class="sxs-lookup"><span data-stu-id="bdfbb-263">TreeView</span></span>|  
|<span data-ttu-id="bdfbb-264">VscrollBar</span><span class="sxs-lookup"><span data-stu-id="bdfbb-264">VscrollBar</span></span>|  
|<span data-ttu-id="bdfbb-265">Web 浏览器</span><span class="sxs-lookup"><span data-stu-id="bdfbb-265">WebBrowser</span></span>|  
  
 <span data-ttu-id="bdfbb-266">以下控件仅通过其对 Microsoft Active Accessibility 的支持公开给 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="bdfbb-266">The following controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] only through their support for Microsoft Active Accessibility.</span></span> <span data-ttu-id="bdfbb-267">某些功能可能不可用。</span><span class="sxs-lookup"><span data-stu-id="bdfbb-267">Some functionality may not be available.</span></span>  
  
|<span data-ttu-id="bdfbb-268">控件名称</span><span class="sxs-lookup"><span data-stu-id="bdfbb-268">Control Name</span></span>|  
|------------------|  
|<span data-ttu-id="bdfbb-269">BindingSource</span><span class="sxs-lookup"><span data-stu-id="bdfbb-269">BindingSource</span></span>|  
|<span data-ttu-id="bdfbb-270">DataGrid</span><span class="sxs-lookup"><span data-stu-id="bdfbb-270">DataGrid</span></span>|  
|<span data-ttu-id="bdfbb-271">DataGridView</span><span class="sxs-lookup"><span data-stu-id="bdfbb-271">DataGridView</span></span>|  
|<span data-ttu-id="bdfbb-272">DataNavigator</span><span class="sxs-lookup"><span data-stu-id="bdfbb-272">DataNavigator</span></span>|  
|<span data-ttu-id="bdfbb-273">DomainUpDown</span><span class="sxs-lookup"><span data-stu-id="bdfbb-273">DomainUpDown</span></span>|  
|<span data-ttu-id="bdfbb-274">ErrorProvider</span><span class="sxs-lookup"><span data-stu-id="bdfbb-274">ErrorProvider</span></span>|  
|<span data-ttu-id="bdfbb-275">FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="bdfbb-275">FlowLayoutPanel</span></span>|  
|<span data-ttu-id="bdfbb-276">窗体</span><span class="sxs-lookup"><span data-stu-id="bdfbb-276">Form</span></span>|  
|<span data-ttu-id="bdfbb-277">LinkLabel</span><span class="sxs-lookup"><span data-stu-id="bdfbb-277">LinkLabel</span></span>|  
|<span data-ttu-id="bdfbb-278">HelpProvider</span><span class="sxs-lookup"><span data-stu-id="bdfbb-278">HelpProvider</span></span>|  
|<span data-ttu-id="bdfbb-279">MaskedTextBox</span><span class="sxs-lookup"><span data-stu-id="bdfbb-279">MaskedTextBox</span></span>|  
|<span data-ttu-id="bdfbb-280">MenuStrip/ContextMenuStrip</span><span class="sxs-lookup"><span data-stu-id="bdfbb-280">MenuStrip/ContextMenuStrip</span></span>|  
|<span data-ttu-id="bdfbb-281">NumericUpDown</span><span class="sxs-lookup"><span data-stu-id="bdfbb-281">NumericUpDown</span></span>|  
|<span data-ttu-id="bdfbb-282">Panel</span><span class="sxs-lookup"><span data-stu-id="bdfbb-282">Panel</span></span>|  
|<span data-ttu-id="bdfbb-283">PictureBox</span><span class="sxs-lookup"><span data-stu-id="bdfbb-283">PictureBox</span></span>|  
|<span data-ttu-id="bdfbb-284">PrintDocument</span><span class="sxs-lookup"><span data-stu-id="bdfbb-284">PrintDocument</span></span>|  
|<span data-ttu-id="bdfbb-285">PrintPreview-Control</span><span class="sxs-lookup"><span data-stu-id="bdfbb-285">PrintPreview-Control</span></span>|  
|<span data-ttu-id="bdfbb-286">PrintPreview-Dialog</span><span class="sxs-lookup"><span data-stu-id="bdfbb-286">PrintPreview-Dialog</span></span>|  
|<span data-ttu-id="bdfbb-287">PropertyGrid</span><span class="sxs-lookup"><span data-stu-id="bdfbb-287">PropertyGrid</span></span>|  
|<span data-ttu-id="bdfbb-288">用户控件</span><span class="sxs-lookup"><span data-stu-id="bdfbb-288">UserControl</span></span>|  
|<span data-ttu-id="bdfbb-289">ToolStrip</span><span class="sxs-lookup"><span data-stu-id="bdfbb-289">ToolStrip</span></span>|  
|<span data-ttu-id="bdfbb-290">TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="bdfbb-290">TableLayoutPanel</span></span>|  
|<span data-ttu-id="bdfbb-291">SplitContainer/SplitterPanel</span><span class="sxs-lookup"><span data-stu-id="bdfbb-291">SplitContainer/SplitterPanel</span></span>|  
|<span data-ttu-id="bdfbb-292">拆分器</span><span class="sxs-lookup"><span data-stu-id="bdfbb-292">Splitter</span></span>|  
|<span data-ttu-id="bdfbb-293">RaftingContainer</span><span class="sxs-lookup"><span data-stu-id="bdfbb-293">RaftingContainer</span></span>|  
|<span data-ttu-id="bdfbb-294">StatusStrip</span><span class="sxs-lookup"><span data-stu-id="bdfbb-294">StatusStrip</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bdfbb-295">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bdfbb-295">See also</span></span>

- [<span data-ttu-id="bdfbb-296">UI 自动化控件类型</span><span class="sxs-lookup"><span data-stu-id="bdfbb-296">UI Automation Control Types</span></span>](ui-automation-control-types.md)
