---
title: UI 自动化对标准控件的支持
ms.date: 03/30/2017
helpviewer_keywords:
- controls, UI Automation support for
- UI Automation, support for standard controls
ms.assetid: 3770ea8a-2655-4add-9c59-fe0610ad5084
ms.openlocfilehash: 49277073706444fd611ae41e762442388ac50b71
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789607"
---
# <a name="ui-automation-support-for-standard-controls"></a><span data-ttu-id="18cbd-102">UI 自动化对标准控件的支持</span><span class="sxs-lookup"><span data-stu-id="18cbd-102">UI Automation Support for Standard Controls</span></span>
> [!NOTE]
> <span data-ttu-id="18cbd-103">本文档适用于想要使用 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 命名空间中定义的托管 <xref:System.Windows.Automation> 类的 .NET Framework 开发人员。</span><span class="sxs-lookup"><span data-stu-id="18cbd-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="18cbd-104">有关 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]的最新信息，请参阅 [Windows 自动化 API：UI 自动化](/windows/win32/winauto/entry-uiauto-win32)。</span><span class="sxs-lookup"><span data-stu-id="18cbd-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="18cbd-105">本主题包含有关为 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)]、Win32 和 Windows 窗体框架开发的应用程序中的标准控件 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] 支持的信息。</span><span class="sxs-lookup"><span data-stu-id="18cbd-105">This topic contains information about [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] support for standard controls in applications developed for the [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)], Win32, and Windows Forms frameworks.</span></span>  
  
<a name="Windows_Presentation_Foundation_Controls"></a>   
## <a name="windows-presentation-foundation-controls"></a><span data-ttu-id="18cbd-106">Windows Presentation Foundation 控件</span><span class="sxs-lookup"><span data-stu-id="18cbd-106">Windows Presentation Foundation Controls</span></span>  
 <span data-ttu-id="18cbd-107">为用户交互提供信息或支持的所有 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 控件元素均具有对 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]的完整本机支持。</span><span class="sxs-lookup"><span data-stu-id="18cbd-107">All [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] control elements that provide information or support for user interaction have full native support for [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span> <span data-ttu-id="18cbd-108">面板等其他元素对 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]不可见。</span><span class="sxs-lookup"><span data-stu-id="18cbd-108">Other elements, such as panels, are not visible to [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span>  
  
<a name="Win32_Controls"></a>   
## <a name="win32-controls"></a><span data-ttu-id="18cbd-109">Win32 控件</span><span class="sxs-lookup"><span data-stu-id="18cbd-109">Win32 Controls</span></span>  
 <span data-ttu-id="18cbd-110">大多数 Win32 控件都通过 Uiautomationclientsideproviders.dll 中的客户端提供程序公开 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="18cbd-110">Most Win32 controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] through client-side providers in UIAutomationClientsideProviders.dll.</span></span> <span data-ttu-id="18cbd-111">此程序集将自动注册，以用于 UI 自动化客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="18cbd-111">This assembly is automatically registered for use with UI Automation client applications.</span></span>  
  
 <span data-ttu-id="18cbd-112">仅为*对 comctrl32.dll*版本6中的控件提供完全支持。</span><span class="sxs-lookup"><span data-stu-id="18cbd-112">Full support is provided only for controls from version 6 of *ComCtrl32.dll*.</span></span>  
  
 <span data-ttu-id="18cbd-113">支持以下控件。</span><span class="sxs-lookup"><span data-stu-id="18cbd-113">The following controls are supported.</span></span>  
  
|<span data-ttu-id="18cbd-114">类名</span><span class="sxs-lookup"><span data-stu-id="18cbd-114">Class name</span></span>|<span data-ttu-id="18cbd-115">控件类型</span><span class="sxs-lookup"><span data-stu-id="18cbd-115">Control Type</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="18cbd-116">Button</span><span class="sxs-lookup"><span data-stu-id="18cbd-116">Button</span></span>|<span data-ttu-id="18cbd-117">Button</span><span class="sxs-lookup"><span data-stu-id="18cbd-117">Button</span></span>|  
|<span data-ttu-id="18cbd-118">Button</span><span class="sxs-lookup"><span data-stu-id="18cbd-118">Button</span></span>|<span data-ttu-id="18cbd-119">RadioButton</span><span class="sxs-lookup"><span data-stu-id="18cbd-119">RadioButton</span></span>|  
|<span data-ttu-id="18cbd-120">Button</span><span class="sxs-lookup"><span data-stu-id="18cbd-120">Button</span></span>|<span data-ttu-id="18cbd-121">组</span><span class="sxs-lookup"><span data-stu-id="18cbd-121">Group</span></span>|  
|<span data-ttu-id="18cbd-122">Button</span><span class="sxs-lookup"><span data-stu-id="18cbd-122">Button</span></span>|<span data-ttu-id="18cbd-123">CheckBox</span><span class="sxs-lookup"><span data-stu-id="18cbd-123">CheckBox</span></span>|  
|<span data-ttu-id="18cbd-124">Button</span><span class="sxs-lookup"><span data-stu-id="18cbd-124">Button</span></span>|<span data-ttu-id="18cbd-125">超链接</span><span class="sxs-lookup"><span data-stu-id="18cbd-125">Hyperlink</span></span>|  
|<span data-ttu-id="18cbd-126">Button</span><span class="sxs-lookup"><span data-stu-id="18cbd-126">Button</span></span>|<span data-ttu-id="18cbd-127">SplitButton</span><span class="sxs-lookup"><span data-stu-id="18cbd-127">SplitButton</span></span>|  
|<span data-ttu-id="18cbd-128">Button</span><span class="sxs-lookup"><span data-stu-id="18cbd-128">Button</span></span>|<span data-ttu-id="18cbd-129">CheckBox</span><span class="sxs-lookup"><span data-stu-id="18cbd-129">CheckBox</span></span>|  
|<span data-ttu-id="18cbd-130">ComboBoxEx32</span><span class="sxs-lookup"><span data-stu-id="18cbd-130">ComboBoxEx32</span></span>|<span data-ttu-id="18cbd-131">组合框</span><span class="sxs-lookup"><span data-stu-id="18cbd-131">ComboBox</span></span>|  
|<span data-ttu-id="18cbd-132">组合框</span><span class="sxs-lookup"><span data-stu-id="18cbd-132">ComboBox</span></span>|<span data-ttu-id="18cbd-133">组合框</span><span class="sxs-lookup"><span data-stu-id="18cbd-133">ComboBox</span></span>|  
|<span data-ttu-id="18cbd-134">Edit</span><span class="sxs-lookup"><span data-stu-id="18cbd-134">Edit</span></span>|<span data-ttu-id="18cbd-135">文档</span><span class="sxs-lookup"><span data-stu-id="18cbd-135">Document</span></span>|  
|<span data-ttu-id="18cbd-136">Edit</span><span class="sxs-lookup"><span data-stu-id="18cbd-136">Edit</span></span>|<span data-ttu-id="18cbd-137">Edit</span><span class="sxs-lookup"><span data-stu-id="18cbd-137">Edit</span></span>|  
|<span data-ttu-id="18cbd-138">SysLink</span><span class="sxs-lookup"><span data-stu-id="18cbd-138">SysLink</span></span>|<span data-ttu-id="18cbd-139">超链接</span><span class="sxs-lookup"><span data-stu-id="18cbd-139">Hyperlink</span></span>|  
|<span data-ttu-id="18cbd-140">Static</span><span class="sxs-lookup"><span data-stu-id="18cbd-140">Static</span></span>|<span data-ttu-id="18cbd-141">文本</span><span class="sxs-lookup"><span data-stu-id="18cbd-141">Text</span></span>|  
|<span data-ttu-id="18cbd-142">Static</span><span class="sxs-lookup"><span data-stu-id="18cbd-142">Static</span></span>|<span data-ttu-id="18cbd-143">Image</span><span class="sxs-lookup"><span data-stu-id="18cbd-143">Image</span></span>|  
|<span data-ttu-id="18cbd-144">SysIPAddress32</span><span class="sxs-lookup"><span data-stu-id="18cbd-144">SysIPAddress32</span></span>|<span data-ttu-id="18cbd-145">“自定义”</span><span class="sxs-lookup"><span data-stu-id="18cbd-145">Custom</span></span>|  
|<span data-ttu-id="18cbd-146">SysHeader32</span><span class="sxs-lookup"><span data-stu-id="18cbd-146">SysHeader32</span></span>|<span data-ttu-id="18cbd-147">Header/HeaderItem</span><span class="sxs-lookup"><span data-stu-id="18cbd-147">Header/HeaderItem</span></span>|  
|<span data-ttu-id="18cbd-148">SysListView32</span><span class="sxs-lookup"><span data-stu-id="18cbd-148">SysListView32</span></span>|<span data-ttu-id="18cbd-149">DataGrid</span><span class="sxs-lookup"><span data-stu-id="18cbd-149">DataGrid</span></span>|  
|<span data-ttu-id="18cbd-150">SysListView32</span><span class="sxs-lookup"><span data-stu-id="18cbd-150">SysListView32</span></span>|<span data-ttu-id="18cbd-151">列表</span><span class="sxs-lookup"><span data-stu-id="18cbd-151">List</span></span>|  
|<span data-ttu-id="18cbd-152">ListBox</span><span class="sxs-lookup"><span data-stu-id="18cbd-152">ListBox</span></span>|<span data-ttu-id="18cbd-153">列表</span><span class="sxs-lookup"><span data-stu-id="18cbd-153">List</span></span>|  
|<span data-ttu-id="18cbd-154">ListBox</span><span class="sxs-lookup"><span data-stu-id="18cbd-154">ListBox</span></span>|<span data-ttu-id="18cbd-155">ListItem</span><span class="sxs-lookup"><span data-stu-id="18cbd-155">ListItem</span></span>|  
|<span data-ttu-id="18cbd-156">#32768</span><span class="sxs-lookup"><span data-stu-id="18cbd-156">#32768</span></span>|<span data-ttu-id="18cbd-157">菜单</span><span class="sxs-lookup"><span data-stu-id="18cbd-157">Menu</span></span>|  
|<span data-ttu-id="18cbd-158">#32768</span><span class="sxs-lookup"><span data-stu-id="18cbd-158">#32768</span></span>|<span data-ttu-id="18cbd-159">MenuItem</span><span class="sxs-lookup"><span data-stu-id="18cbd-159">MenuItem</span></span>|  
|<span data-ttu-id="18cbd-160">msctls_progress32</span><span class="sxs-lookup"><span data-stu-id="18cbd-160">msctls_progress32</span></span>|<span data-ttu-id="18cbd-161">进度条</span><span class="sxs-lookup"><span data-stu-id="18cbd-161">ProgressBar</span></span>|  
|<span data-ttu-id="18cbd-162">RichEdit</span><span class="sxs-lookup"><span data-stu-id="18cbd-162">RichEdit</span></span>|<span data-ttu-id="18cbd-163">Document。</span><span class="sxs-lookup"><span data-stu-id="18cbd-163">Document.</span></span> <span data-ttu-id="18cbd-164">请参阅注释。</span><span class="sxs-lookup"><span data-stu-id="18cbd-164">See note.</span></span>|  
|<span data-ttu-id="18cbd-165">RichEdit20A</span><span class="sxs-lookup"><span data-stu-id="18cbd-165">RichEdit20A</span></span>|<span data-ttu-id="18cbd-166">文档</span><span class="sxs-lookup"><span data-stu-id="18cbd-166">Document</span></span>|  
|<span data-ttu-id="18cbd-167">RichEdit20W</span><span class="sxs-lookup"><span data-stu-id="18cbd-167">RichEdit20W</span></span>|<span data-ttu-id="18cbd-168">文档</span><span class="sxs-lookup"><span data-stu-id="18cbd-168">Document</span></span>|  
|<span data-ttu-id="18cbd-169">RichEdit50W</span><span class="sxs-lookup"><span data-stu-id="18cbd-169">RichEdit50W</span></span>|<span data-ttu-id="18cbd-170">文档</span><span class="sxs-lookup"><span data-stu-id="18cbd-170">Document</span></span>|  
|<span data-ttu-id="18cbd-171">ScrollBar</span><span class="sxs-lookup"><span data-stu-id="18cbd-171">ScrollBar</span></span>|<span data-ttu-id="18cbd-172">Slider</span><span class="sxs-lookup"><span data-stu-id="18cbd-172">Slider</span></span>|  
|<span data-ttu-id="18cbd-173">msctls_trackbar32</span><span class="sxs-lookup"><span data-stu-id="18cbd-173">msctls_trackbar32</span></span>|<span data-ttu-id="18cbd-174">Slider</span><span class="sxs-lookup"><span data-stu-id="18cbd-174">Slider</span></span>|  
|<span data-ttu-id="18cbd-175">msctls_updown32</span><span class="sxs-lookup"><span data-stu-id="18cbd-175">msctls_updown32</span></span>|<span data-ttu-id="18cbd-176">Spinner</span><span class="sxs-lookup"><span data-stu-id="18cbd-176">Spinner</span></span>|  
|<span data-ttu-id="18cbd-177">msctls_statusbar32</span><span class="sxs-lookup"><span data-stu-id="18cbd-177">msctls_statusbar32</span></span>|<span data-ttu-id="18cbd-178">StatusBar</span><span class="sxs-lookup"><span data-stu-id="18cbd-178">StatusBar</span></span>|  
|<span data-ttu-id="18cbd-179">SysTabControl32</span><span class="sxs-lookup"><span data-stu-id="18cbd-179">SysTabControl32</span></span>|<span data-ttu-id="18cbd-180">Tab</span><span class="sxs-lookup"><span data-stu-id="18cbd-180">Tab</span></span>|  
|<span data-ttu-id="18cbd-181">SysTabControl32</span><span class="sxs-lookup"><span data-stu-id="18cbd-181">SysTabControl32</span></span>|<span data-ttu-id="18cbd-182">TabItem</span><span class="sxs-lookup"><span data-stu-id="18cbd-182">TabItem</span></span>|  
|<span data-ttu-id="18cbd-183">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="18cbd-183">ToolbarWindow32</span></span>|<span data-ttu-id="18cbd-184">ToolBar</span><span class="sxs-lookup"><span data-stu-id="18cbd-184">ToolBar</span></span>|  
|<span data-ttu-id="18cbd-185">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="18cbd-185">ToolbarWindow32</span></span>|<span data-ttu-id="18cbd-186">MenuItem</span><span class="sxs-lookup"><span data-stu-id="18cbd-186">MenuItem</span></span>|  
|<span data-ttu-id="18cbd-187">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="18cbd-187">ToolbarWindow32</span></span>|<span data-ttu-id="18cbd-188">Button</span><span class="sxs-lookup"><span data-stu-id="18cbd-188">Button</span></span>|  
|<span data-ttu-id="18cbd-189">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="18cbd-189">ToolbarWindow32</span></span>|<span data-ttu-id="18cbd-190">CheckBox</span><span class="sxs-lookup"><span data-stu-id="18cbd-190">CheckBox</span></span>|  
|<span data-ttu-id="18cbd-191">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="18cbd-191">ToolbarWindow32</span></span>|<span data-ttu-id="18cbd-192">RadioButton</span><span class="sxs-lookup"><span data-stu-id="18cbd-192">RadioButton</span></span>|  
|<span data-ttu-id="18cbd-193">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="18cbd-193">ToolbarWindow32</span></span>|<span data-ttu-id="18cbd-194">Separator</span><span class="sxs-lookup"><span data-stu-id="18cbd-194">Separator</span></span>|  
|<span data-ttu-id="18cbd-195">tooltips_class32</span><span class="sxs-lookup"><span data-stu-id="18cbd-195">tooltips_class32</span></span>|<span data-ttu-id="18cbd-196">工具提示</span><span class="sxs-lookup"><span data-stu-id="18cbd-196">ToolTip</span></span>|  
|<span data-ttu-id="18cbd-197">#32774</span><span class="sxs-lookup"><span data-stu-id="18cbd-197">#32774</span></span>|<span data-ttu-id="18cbd-198">工具提示</span><span class="sxs-lookup"><span data-stu-id="18cbd-198">ToolTip</span></span>|  
|<span data-ttu-id="18cbd-199">ReBarWindow32</span><span class="sxs-lookup"><span data-stu-id="18cbd-199">ReBarWindow32</span></span>|<span data-ttu-id="18cbd-200">ToolBar</span><span class="sxs-lookup"><span data-stu-id="18cbd-200">Toolbar</span></span>|  
|<span data-ttu-id="18cbd-201">SysTreeView32</span><span class="sxs-lookup"><span data-stu-id="18cbd-201">SysTreeView32</span></span>|<span data-ttu-id="18cbd-202">树</span><span class="sxs-lookup"><span data-stu-id="18cbd-202">Tree</span></span>|  
|<span data-ttu-id="18cbd-203">SysTreeView32</span><span class="sxs-lookup"><span data-stu-id="18cbd-203">SysTreeView32</span></span>|<span data-ttu-id="18cbd-204">TreeItem</span><span class="sxs-lookup"><span data-stu-id="18cbd-204">TreeItem</span></span>|  
  
 <span data-ttu-id="18cbd-205">**注意**只有 Windows Vista 附带的版本（在 Riched20.dll 版本3.1 及更高版本以及 Msftedit.dll 版本4.1 及更高版本）支持 RichEdit 控件。</span><span class="sxs-lookup"><span data-stu-id="18cbd-205">**Note** The RichEdit control is supported only for versions shipped with Windows Vista (in RichEd20.dll version 3.1 and later, and MsftEdit.dll version 4.1 and later).</span></span>  
  
 <span data-ttu-id="18cbd-206">不支持以下控件。</span><span class="sxs-lookup"><span data-stu-id="18cbd-206">The following controls are not supported.</span></span>  
  
|<span data-ttu-id="18cbd-207">类名</span><span class="sxs-lookup"><span data-stu-id="18cbd-207">Class name</span></span>|<span data-ttu-id="18cbd-208">控件类型</span><span class="sxs-lookup"><span data-stu-id="18cbd-208">Control type</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="18cbd-209">SysAnimate32</span><span class="sxs-lookup"><span data-stu-id="18cbd-209">SysAnimate32</span></span>|<span data-ttu-id="18cbd-210">Image</span><span class="sxs-lookup"><span data-stu-id="18cbd-210">Image</span></span>|  
|<span data-ttu-id="18cbd-211">SysPager</span><span class="sxs-lookup"><span data-stu-id="18cbd-211">SysPager</span></span>|<span data-ttu-id="18cbd-212">Spinner</span><span class="sxs-lookup"><span data-stu-id="18cbd-212">Spinner</span></span>|  
|<span data-ttu-id="18cbd-213">SysDateTimePick32</span><span class="sxs-lookup"><span data-stu-id="18cbd-213">SysDateTimePick32</span></span>|<span data-ttu-id="18cbd-214">“自定义”</span><span class="sxs-lookup"><span data-stu-id="18cbd-214">Custom</span></span>|  
|<span data-ttu-id="18cbd-215">SysMonthCal32</span><span class="sxs-lookup"><span data-stu-id="18cbd-215">SysMonthCal32</span></span>|<span data-ttu-id="18cbd-216">Calendar</span><span class="sxs-lookup"><span data-stu-id="18cbd-216">Calendar</span></span>|  
|<span data-ttu-id="18cbd-217">MS_WINNOTE</span><span class="sxs-lookup"><span data-stu-id="18cbd-217">MS_WINNOTE</span></span>|<span data-ttu-id="18cbd-218">ToolTip</span><span class="sxs-lookup"><span data-stu-id="18cbd-218">Tooltip</span></span>|  
|<span data-ttu-id="18cbd-219">VBBubble</span><span class="sxs-lookup"><span data-stu-id="18cbd-219">VBBubble</span></span>|<span data-ttu-id="18cbd-220">ToolTip</span><span class="sxs-lookup"><span data-stu-id="18cbd-220">Tooltip</span></span>|  
|<span data-ttu-id="18cbd-221">ScrollBar（在用作独立控件时）</span><span class="sxs-lookup"><span data-stu-id="18cbd-221">ScrollBar (when used as a standalone control)</span></span>|<span data-ttu-id="18cbd-222">Slider</span><span class="sxs-lookup"><span data-stu-id="18cbd-222">Slider</span></span>|  
|<span data-ttu-id="18cbd-223">SuperGrid</span><span class="sxs-lookup"><span data-stu-id="18cbd-223">SuperGrid</span></span>|<span data-ttu-id="18cbd-224">“自定义”</span><span class="sxs-lookup"><span data-stu-id="18cbd-224">Custom</span></span>|  
  
<a name="Windows_Forms_Controls"></a>   
## <a name="windows-forms-controls"></a><span data-ttu-id="18cbd-225">Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="18cbd-225">Windows Forms Controls</span></span>  
 <span data-ttu-id="18cbd-226">通过 Uiautomationclientsideproviders.dll 中的客户端提供程序 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] 公开 Windows 窗体控件。</span><span class="sxs-lookup"><span data-stu-id="18cbd-226">Windows Forms controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] through client-side providers in UIAutomationClientsideProviders.dll.</span></span> <span data-ttu-id="18cbd-227">此程序集将自动注册，以用于 UI 自动化客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="18cbd-227">This assembly is automatically registered for use with UI Automation client applications.</span></span>  
  
 <span data-ttu-id="18cbd-228">通常，[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]支持作为 Win32 公共控件的托管包装 Windows 窗体控件。</span><span class="sxs-lookup"><span data-stu-id="18cbd-228">Typically, Windows Forms controls that are managed wrappers for Win32 common controls are supported by [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span> <span data-ttu-id="18cbd-229">支持以下控件。</span><span class="sxs-lookup"><span data-stu-id="18cbd-229">The following controls are supported.</span></span>  
  
|<span data-ttu-id="18cbd-230">类名称</span><span class="sxs-lookup"><span data-stu-id="18cbd-230">Class Name</span></span>|  
|----------------|  
|<span data-ttu-id="18cbd-231">Button</span><span class="sxs-lookup"><span data-stu-id="18cbd-231">Button</span></span>|  
|<span data-ttu-id="18cbd-232">CheckBox</span><span class="sxs-lookup"><span data-stu-id="18cbd-232">CheckBox</span></span>|  
|<span data-ttu-id="18cbd-233">CheckedListBox</span><span class="sxs-lookup"><span data-stu-id="18cbd-233">CheckedListBox</span></span>|  
|<span data-ttu-id="18cbd-234">ColorDialog</span><span class="sxs-lookup"><span data-stu-id="18cbd-234">ColorDialog</span></span>|  
|<span data-ttu-id="18cbd-235">组合框</span><span class="sxs-lookup"><span data-stu-id="18cbd-235">ComboBox</span></span>|  
|<span data-ttu-id="18cbd-236">FolderBrowser</span><span class="sxs-lookup"><span data-stu-id="18cbd-236">FolderBrowser</span></span>|  
|<span data-ttu-id="18cbd-237">FontDialog</span><span class="sxs-lookup"><span data-stu-id="18cbd-237">FontDialog</span></span>|  
|<span data-ttu-id="18cbd-238">GroupBox</span><span class="sxs-lookup"><span data-stu-id="18cbd-238">GroupBox</span></span>|  
|<span data-ttu-id="18cbd-239">HscrollBar</span><span class="sxs-lookup"><span data-stu-id="18cbd-239">HscrollBar</span></span>|  
|<span data-ttu-id="18cbd-240">ImageList</span><span class="sxs-lookup"><span data-stu-id="18cbd-240">ImageList</span></span>|  
|<span data-ttu-id="18cbd-241">标签</span><span class="sxs-lookup"><span data-stu-id="18cbd-241">Label</span></span>|  
|<span data-ttu-id="18cbd-242">ListBox</span><span class="sxs-lookup"><span data-stu-id="18cbd-242">ListBox</span></span>|  
|<span data-ttu-id="18cbd-243">ListView</span><span class="sxs-lookup"><span data-stu-id="18cbd-243">ListView</span></span>|  
|<span data-ttu-id="18cbd-244">MainMenu/ContextMenu</span><span class="sxs-lookup"><span data-stu-id="18cbd-244">MainMenu/ContextMenu</span></span>|  
|<span data-ttu-id="18cbd-245">MonthCalendar</span><span class="sxs-lookup"><span data-stu-id="18cbd-245">MonthCalendar</span></span>|  
|<span data-ttu-id="18cbd-246">NotifyIcon</span><span class="sxs-lookup"><span data-stu-id="18cbd-246">NotifyIcon</span></span>|  
|<span data-ttu-id="18cbd-247">OpenFileDialog</span><span class="sxs-lookup"><span data-stu-id="18cbd-247">OpenFileDialog</span></span>|  
|<span data-ttu-id="18cbd-248">PageSetupDialog</span><span class="sxs-lookup"><span data-stu-id="18cbd-248">PageSetupDialog</span></span>|  
|<span data-ttu-id="18cbd-249">PrintDialog</span><span class="sxs-lookup"><span data-stu-id="18cbd-249">PrintDialog</span></span>|  
|<span data-ttu-id="18cbd-250">进度条</span><span class="sxs-lookup"><span data-stu-id="18cbd-250">ProgressBar</span></span>|  
|<span data-ttu-id="18cbd-251">RadioButton</span><span class="sxs-lookup"><span data-stu-id="18cbd-251">RadioButton</span></span>|  
|<span data-ttu-id="18cbd-252">RichTextBox</span><span class="sxs-lookup"><span data-stu-id="18cbd-252">RichTextBox</span></span>|  
|<span data-ttu-id="18cbd-253">SaveFileDialog</span><span class="sxs-lookup"><span data-stu-id="18cbd-253">SaveFileDialog</span></span>|  
|<span data-ttu-id="18cbd-254">ScrollableControl</span><span class="sxs-lookup"><span data-stu-id="18cbd-254">ScrollableControl</span></span>|  
|<span data-ttu-id="18cbd-255">SoundPlayer</span><span class="sxs-lookup"><span data-stu-id="18cbd-255">SoundPlayer</span></span>|  
|<span data-ttu-id="18cbd-256">StatusBar</span><span class="sxs-lookup"><span data-stu-id="18cbd-256">StatusBar</span></span>|  
|<span data-ttu-id="18cbd-257">TabControl/TabPage</span><span class="sxs-lookup"><span data-stu-id="18cbd-257">TabControl/TabPage</span></span>|  
|<span data-ttu-id="18cbd-258">文本框</span><span class="sxs-lookup"><span data-stu-id="18cbd-258">TextBox</span></span>|  
|<span data-ttu-id="18cbd-259">计时器</span><span class="sxs-lookup"><span data-stu-id="18cbd-259">Timer</span></span>|  
|<span data-ttu-id="18cbd-260">ToolBar</span><span class="sxs-lookup"><span data-stu-id="18cbd-260">Toolbar</span></span>|  
|<span data-ttu-id="18cbd-261">工具提示</span><span class="sxs-lookup"><span data-stu-id="18cbd-261">ToolTip</span></span>|  
|<span data-ttu-id="18cbd-262">TrackBar</span><span class="sxs-lookup"><span data-stu-id="18cbd-262">TrackBar</span></span>|  
|<span data-ttu-id="18cbd-263">TreeView</span><span class="sxs-lookup"><span data-stu-id="18cbd-263">TreeView</span></span>|  
|<span data-ttu-id="18cbd-264">VscrollBar</span><span class="sxs-lookup"><span data-stu-id="18cbd-264">VscrollBar</span></span>|  
|<span data-ttu-id="18cbd-265">Web 浏览器</span><span class="sxs-lookup"><span data-stu-id="18cbd-265">WebBrowser</span></span>|  
  
 <span data-ttu-id="18cbd-266">以下控件仅通过其对 Microsoft Active Accessibility 的支持公开给 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="18cbd-266">The following controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] only through their support for Microsoft Active Accessibility.</span></span> <span data-ttu-id="18cbd-267">某些功能可能不可用。</span><span class="sxs-lookup"><span data-stu-id="18cbd-267">Some functionality may not be available.</span></span>  
  
|<span data-ttu-id="18cbd-268">控件名称</span><span class="sxs-lookup"><span data-stu-id="18cbd-268">Control Name</span></span>|  
|------------------|  
|<span data-ttu-id="18cbd-269">BindingSource</span><span class="sxs-lookup"><span data-stu-id="18cbd-269">BindingSource</span></span>|  
|<span data-ttu-id="18cbd-270">DataGrid</span><span class="sxs-lookup"><span data-stu-id="18cbd-270">DataGrid</span></span>|  
|<span data-ttu-id="18cbd-271">DataGridView</span><span class="sxs-lookup"><span data-stu-id="18cbd-271">DataGridView</span></span>|  
|<span data-ttu-id="18cbd-272">DataNavigator</span><span class="sxs-lookup"><span data-stu-id="18cbd-272">DataNavigator</span></span>|  
|<span data-ttu-id="18cbd-273">DomainUpDown</span><span class="sxs-lookup"><span data-stu-id="18cbd-273">DomainUpDown</span></span>|  
|<span data-ttu-id="18cbd-274">ErrorProvider</span><span class="sxs-lookup"><span data-stu-id="18cbd-274">ErrorProvider</span></span>|  
|<span data-ttu-id="18cbd-275">FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="18cbd-275">FlowLayoutPanel</span></span>|  
|<span data-ttu-id="18cbd-276">窗体</span><span class="sxs-lookup"><span data-stu-id="18cbd-276">Form</span></span>|  
|<span data-ttu-id="18cbd-277">LinkLabel</span><span class="sxs-lookup"><span data-stu-id="18cbd-277">LinkLabel</span></span>|  
|<span data-ttu-id="18cbd-278">HelpProvider</span><span class="sxs-lookup"><span data-stu-id="18cbd-278">HelpProvider</span></span>|  
|<span data-ttu-id="18cbd-279">MaskedTextBox</span><span class="sxs-lookup"><span data-stu-id="18cbd-279">MaskedTextBox</span></span>|  
|<span data-ttu-id="18cbd-280">MenuStrip/ContextMenuStrip</span><span class="sxs-lookup"><span data-stu-id="18cbd-280">MenuStrip/ContextMenuStrip</span></span>|  
|<span data-ttu-id="18cbd-281">NumericUpDown</span><span class="sxs-lookup"><span data-stu-id="18cbd-281">NumericUpDown</span></span>|  
|<span data-ttu-id="18cbd-282">Panel</span><span class="sxs-lookup"><span data-stu-id="18cbd-282">Panel</span></span>|  
|<span data-ttu-id="18cbd-283">PictureBox</span><span class="sxs-lookup"><span data-stu-id="18cbd-283">PictureBox</span></span>|  
|<span data-ttu-id="18cbd-284">PrintDocument</span><span class="sxs-lookup"><span data-stu-id="18cbd-284">PrintDocument</span></span>|  
|<span data-ttu-id="18cbd-285">PrintPreview-Control</span><span class="sxs-lookup"><span data-stu-id="18cbd-285">PrintPreview-Control</span></span>|  
|<span data-ttu-id="18cbd-286">PrintPreview-Dialog</span><span class="sxs-lookup"><span data-stu-id="18cbd-286">PrintPreview-Dialog</span></span>|  
|<span data-ttu-id="18cbd-287">PropertyGrid</span><span class="sxs-lookup"><span data-stu-id="18cbd-287">PropertyGrid</span></span>|  
|<span data-ttu-id="18cbd-288">用户控件</span><span class="sxs-lookup"><span data-stu-id="18cbd-288">UserControl</span></span>|  
|<span data-ttu-id="18cbd-289">ToolStrip</span><span class="sxs-lookup"><span data-stu-id="18cbd-289">ToolStrip</span></span>|  
|<span data-ttu-id="18cbd-290">TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="18cbd-290">TableLayoutPanel</span></span>|  
|<span data-ttu-id="18cbd-291">SplitContainer/SplitterPanel</span><span class="sxs-lookup"><span data-stu-id="18cbd-291">SplitContainer/SplitterPanel</span></span>|  
|<span data-ttu-id="18cbd-292">拆分器</span><span class="sxs-lookup"><span data-stu-id="18cbd-292">Splitter</span></span>|  
|<span data-ttu-id="18cbd-293">RaftingContainer</span><span class="sxs-lookup"><span data-stu-id="18cbd-293">RaftingContainer</span></span>|  
|<span data-ttu-id="18cbd-294">StatusStrip</span><span class="sxs-lookup"><span data-stu-id="18cbd-294">StatusStrip</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="18cbd-295">另请参阅</span><span class="sxs-lookup"><span data-stu-id="18cbd-295">See also</span></span>

- [<span data-ttu-id="18cbd-296">UI Automation Control Types</span><span class="sxs-lookup"><span data-stu-id="18cbd-296">UI Automation Control Types</span></span>](ui-automation-control-types.md)
