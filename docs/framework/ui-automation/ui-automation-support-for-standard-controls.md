---
title: UI 自动化对标准控件的支持
ms.date: 03/30/2017
helpviewer_keywords:
- controls, UI Automation support for
- UI Automation, support for standard controls
ms.assetid: 3770ea8a-2655-4add-9c59-fe0610ad5084
ms.openlocfilehash: 36028d589e98177f6a0e83092edd656860b1a8d4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179855"
---
# <a name="ui-automation-support-for-standard-controls"></a><span data-ttu-id="8a6e2-102">UI 自动化对标准控件的支持</span><span class="sxs-lookup"><span data-stu-id="8a6e2-102">UI Automation Support for Standard Controls</span></span>
> [!NOTE]
> <span data-ttu-id="8a6e2-103">本文档适用于想要使用 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 命名空间中定义的托管 <xref:System.Windows.Automation> 类的 .NET Framework 开发人员。</span><span class="sxs-lookup"><span data-stu-id="8a6e2-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="8a6e2-104">有关 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]的最新信息，请参阅 [Windows 自动化 API：UI 自动化](/windows/win32/winauto/entry-uiauto-win32)。</span><span class="sxs-lookup"><span data-stu-id="8a6e2-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="8a6e2-105">本主题包含有关支持为[!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)][!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)]Win32 和 Windows 窗体框架开发的应用程序中的标准控件的信息。</span><span class="sxs-lookup"><span data-stu-id="8a6e2-105">This topic contains information about [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] support for standard controls in applications developed for the [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)], Win32, and Windows Forms frameworks.</span></span>  
  
<a name="Windows_Presentation_Foundation_Controls"></a>
## <a name="windows-presentation-foundation-controls"></a><span data-ttu-id="8a6e2-106">Windows Presentation Foundation 控件</span><span class="sxs-lookup"><span data-stu-id="8a6e2-106">Windows Presentation Foundation Controls</span></span>  
 <span data-ttu-id="8a6e2-107">为用户交互提供信息或支持的所有 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 控件元素均具有对 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]的完整本机支持。</span><span class="sxs-lookup"><span data-stu-id="8a6e2-107">All [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] control elements that provide information or support for user interaction have full native support for [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span> <span data-ttu-id="8a6e2-108">面板等其他元素对 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]不可见。</span><span class="sxs-lookup"><span data-stu-id="8a6e2-108">Other elements, such as panels, are not visible to [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span>  
  
<a name="Win32_Controls"></a>
## <a name="win32-controls"></a><span data-ttu-id="8a6e2-109">Win32 控件</span><span class="sxs-lookup"><span data-stu-id="8a6e2-109">Win32 Controls</span></span>  
 <span data-ttu-id="8a6e2-110">大多数 Win32 控件[!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)]通过 UIAutomationClientside 提供程序.dll 中的客户端提供程序公开。</span><span class="sxs-lookup"><span data-stu-id="8a6e2-110">Most Win32 controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] through client-side providers in UIAutomationClientsideProviders.dll.</span></span> <span data-ttu-id="8a6e2-111">此程序集将自动注册，以用于 UI 自动化客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="8a6e2-111">This assembly is automatically registered for use with UI Automation client applications.</span></span>  
  
 <span data-ttu-id="8a6e2-112">完全支持仅为*ComCtrl32.dll*版本 6 中的控件提供。</span><span class="sxs-lookup"><span data-stu-id="8a6e2-112">Full support is provided only for controls from version 6 of *ComCtrl32.dll*.</span></span>  
  
 <span data-ttu-id="8a6e2-113">支持以下控件。</span><span class="sxs-lookup"><span data-stu-id="8a6e2-113">The following controls are supported.</span></span>  
  
|<span data-ttu-id="8a6e2-114">类名称</span><span class="sxs-lookup"><span data-stu-id="8a6e2-114">Class name</span></span>|<span data-ttu-id="8a6e2-115">控件类型</span><span class="sxs-lookup"><span data-stu-id="8a6e2-115">Control Type</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="8a6e2-116">按钮</span><span class="sxs-lookup"><span data-stu-id="8a6e2-116">Button</span></span>|<span data-ttu-id="8a6e2-117">按钮</span><span class="sxs-lookup"><span data-stu-id="8a6e2-117">Button</span></span>|  
|<span data-ttu-id="8a6e2-118">按钮</span><span class="sxs-lookup"><span data-stu-id="8a6e2-118">Button</span></span>|<span data-ttu-id="8a6e2-119">RadioButton</span><span class="sxs-lookup"><span data-stu-id="8a6e2-119">RadioButton</span></span>|  
|<span data-ttu-id="8a6e2-120">按钮</span><span class="sxs-lookup"><span data-stu-id="8a6e2-120">Button</span></span>|<span data-ttu-id="8a6e2-121">组</span><span class="sxs-lookup"><span data-stu-id="8a6e2-121">Group</span></span>|  
|<span data-ttu-id="8a6e2-122">按钮</span><span class="sxs-lookup"><span data-stu-id="8a6e2-122">Button</span></span>|<span data-ttu-id="8a6e2-123">CheckBox</span><span class="sxs-lookup"><span data-stu-id="8a6e2-123">CheckBox</span></span>|  
|<span data-ttu-id="8a6e2-124">按钮</span><span class="sxs-lookup"><span data-stu-id="8a6e2-124">Button</span></span>|<span data-ttu-id="8a6e2-125">Hyperlink</span><span class="sxs-lookup"><span data-stu-id="8a6e2-125">Hyperlink</span></span>|  
|<span data-ttu-id="8a6e2-126">按钮</span><span class="sxs-lookup"><span data-stu-id="8a6e2-126">Button</span></span>|<span data-ttu-id="8a6e2-127">SplitButton</span><span class="sxs-lookup"><span data-stu-id="8a6e2-127">SplitButton</span></span>|  
|<span data-ttu-id="8a6e2-128">按钮</span><span class="sxs-lookup"><span data-stu-id="8a6e2-128">Button</span></span>|<span data-ttu-id="8a6e2-129">CheckBox</span><span class="sxs-lookup"><span data-stu-id="8a6e2-129">CheckBox</span></span>|  
|<span data-ttu-id="8a6e2-130">ComboBoxEx32</span><span class="sxs-lookup"><span data-stu-id="8a6e2-130">ComboBoxEx32</span></span>|<span data-ttu-id="8a6e2-131">ComboBox</span><span class="sxs-lookup"><span data-stu-id="8a6e2-131">ComboBox</span></span>|  
|<span data-ttu-id="8a6e2-132">ComboBox</span><span class="sxs-lookup"><span data-stu-id="8a6e2-132">ComboBox</span></span>|<span data-ttu-id="8a6e2-133">ComboBox</span><span class="sxs-lookup"><span data-stu-id="8a6e2-133">ComboBox</span></span>|  
|<span data-ttu-id="8a6e2-134">编辑</span><span class="sxs-lookup"><span data-stu-id="8a6e2-134">Edit</span></span>|<span data-ttu-id="8a6e2-135">Document</span><span class="sxs-lookup"><span data-stu-id="8a6e2-135">Document</span></span>|  
|<span data-ttu-id="8a6e2-136">编辑</span><span class="sxs-lookup"><span data-stu-id="8a6e2-136">Edit</span></span>|<span data-ttu-id="8a6e2-137">编辑</span><span class="sxs-lookup"><span data-stu-id="8a6e2-137">Edit</span></span>|  
|<span data-ttu-id="8a6e2-138">SysLink</span><span class="sxs-lookup"><span data-stu-id="8a6e2-138">SysLink</span></span>|<span data-ttu-id="8a6e2-139">Hyperlink</span><span class="sxs-lookup"><span data-stu-id="8a6e2-139">Hyperlink</span></span>|  
|<span data-ttu-id="8a6e2-140">静态</span><span class="sxs-lookup"><span data-stu-id="8a6e2-140">Static</span></span>|<span data-ttu-id="8a6e2-141">文本</span><span class="sxs-lookup"><span data-stu-id="8a6e2-141">Text</span></span>|  
|<span data-ttu-id="8a6e2-142">静态</span><span class="sxs-lookup"><span data-stu-id="8a6e2-142">Static</span></span>|<span data-ttu-id="8a6e2-143">映像</span><span class="sxs-lookup"><span data-stu-id="8a6e2-143">Image</span></span>|  
|<span data-ttu-id="8a6e2-144">SysIPAddress32</span><span class="sxs-lookup"><span data-stu-id="8a6e2-144">SysIPAddress32</span></span>|<span data-ttu-id="8a6e2-145">自定义</span><span class="sxs-lookup"><span data-stu-id="8a6e2-145">Custom</span></span>|  
|<span data-ttu-id="8a6e2-146">SysHeader32</span><span class="sxs-lookup"><span data-stu-id="8a6e2-146">SysHeader32</span></span>|<span data-ttu-id="8a6e2-147">Header/HeaderItem</span><span class="sxs-lookup"><span data-stu-id="8a6e2-147">Header/HeaderItem</span></span>|  
|<span data-ttu-id="8a6e2-148">SysListView32</span><span class="sxs-lookup"><span data-stu-id="8a6e2-148">SysListView32</span></span>|<span data-ttu-id="8a6e2-149">DataGrid</span><span class="sxs-lookup"><span data-stu-id="8a6e2-149">DataGrid</span></span>|  
|<span data-ttu-id="8a6e2-150">SysListView32</span><span class="sxs-lookup"><span data-stu-id="8a6e2-150">SysListView32</span></span>|<span data-ttu-id="8a6e2-151">列出</span><span class="sxs-lookup"><span data-stu-id="8a6e2-151">List</span></span>|  
|<span data-ttu-id="8a6e2-152">ListBox</span><span class="sxs-lookup"><span data-stu-id="8a6e2-152">ListBox</span></span>|<span data-ttu-id="8a6e2-153">列出</span><span class="sxs-lookup"><span data-stu-id="8a6e2-153">List</span></span>|  
|<span data-ttu-id="8a6e2-154">ListBox</span><span class="sxs-lookup"><span data-stu-id="8a6e2-154">ListBox</span></span>|<span data-ttu-id="8a6e2-155">ListItem</span><span class="sxs-lookup"><span data-stu-id="8a6e2-155">ListItem</span></span>|  
|<span data-ttu-id="8a6e2-156">#32768</span><span class="sxs-lookup"><span data-stu-id="8a6e2-156">#32768</span></span>|<span data-ttu-id="8a6e2-157">菜单</span><span class="sxs-lookup"><span data-stu-id="8a6e2-157">Menu</span></span>|  
|<span data-ttu-id="8a6e2-158">#32768</span><span class="sxs-lookup"><span data-stu-id="8a6e2-158">#32768</span></span>|<span data-ttu-id="8a6e2-159">MenuItem</span><span class="sxs-lookup"><span data-stu-id="8a6e2-159">MenuItem</span></span>|  
|<span data-ttu-id="8a6e2-160">msctls_progress32</span><span class="sxs-lookup"><span data-stu-id="8a6e2-160">msctls_progress32</span></span>|<span data-ttu-id="8a6e2-161">ProgressBar</span><span class="sxs-lookup"><span data-stu-id="8a6e2-161">ProgressBar</span></span>|  
|<span data-ttu-id="8a6e2-162">RichEdit</span><span class="sxs-lookup"><span data-stu-id="8a6e2-162">RichEdit</span></span>|<span data-ttu-id="8a6e2-163">Document。</span><span class="sxs-lookup"><span data-stu-id="8a6e2-163">Document.</span></span> <span data-ttu-id="8a6e2-164">请参阅注释。</span><span class="sxs-lookup"><span data-stu-id="8a6e2-164">See note.</span></span>|  
|<span data-ttu-id="8a6e2-165">RichEdit20A</span><span class="sxs-lookup"><span data-stu-id="8a6e2-165">RichEdit20A</span></span>|<span data-ttu-id="8a6e2-166">Document</span><span class="sxs-lookup"><span data-stu-id="8a6e2-166">Document</span></span>|  
|<span data-ttu-id="8a6e2-167">RichEdit20W</span><span class="sxs-lookup"><span data-stu-id="8a6e2-167">RichEdit20W</span></span>|<span data-ttu-id="8a6e2-168">Document</span><span class="sxs-lookup"><span data-stu-id="8a6e2-168">Document</span></span>|  
|<span data-ttu-id="8a6e2-169">RichEdit50W</span><span class="sxs-lookup"><span data-stu-id="8a6e2-169">RichEdit50W</span></span>|<span data-ttu-id="8a6e2-170">Document</span><span class="sxs-lookup"><span data-stu-id="8a6e2-170">Document</span></span>|  
|<span data-ttu-id="8a6e2-171">ScrollBar</span><span class="sxs-lookup"><span data-stu-id="8a6e2-171">ScrollBar</span></span>|<span data-ttu-id="8a6e2-172">滑块</span><span class="sxs-lookup"><span data-stu-id="8a6e2-172">Slider</span></span>|  
|<span data-ttu-id="8a6e2-173">msctls_trackbar32</span><span class="sxs-lookup"><span data-stu-id="8a6e2-173">msctls_trackbar32</span></span>|<span data-ttu-id="8a6e2-174">滑块</span><span class="sxs-lookup"><span data-stu-id="8a6e2-174">Slider</span></span>|  
|<span data-ttu-id="8a6e2-175">msctls_updown32</span><span class="sxs-lookup"><span data-stu-id="8a6e2-175">msctls_updown32</span></span>|<span data-ttu-id="8a6e2-176">Spinner</span><span class="sxs-lookup"><span data-stu-id="8a6e2-176">Spinner</span></span>|  
|<span data-ttu-id="8a6e2-177">msctls_statusbar32</span><span class="sxs-lookup"><span data-stu-id="8a6e2-177">msctls_statusbar32</span></span>|<span data-ttu-id="8a6e2-178">StatusBar</span><span class="sxs-lookup"><span data-stu-id="8a6e2-178">StatusBar</span></span>|  
|<span data-ttu-id="8a6e2-179">SysTabControl32</span><span class="sxs-lookup"><span data-stu-id="8a6e2-179">SysTabControl32</span></span>|<span data-ttu-id="8a6e2-180">选项卡</span><span class="sxs-lookup"><span data-stu-id="8a6e2-180">Tab</span></span>|  
|<span data-ttu-id="8a6e2-181">SysTabControl32</span><span class="sxs-lookup"><span data-stu-id="8a6e2-181">SysTabControl32</span></span>|<span data-ttu-id="8a6e2-182">TabItem</span><span class="sxs-lookup"><span data-stu-id="8a6e2-182">TabItem</span></span>|  
|<span data-ttu-id="8a6e2-183">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="8a6e2-183">ToolbarWindow32</span></span>|<span data-ttu-id="8a6e2-184">ToolBar</span><span class="sxs-lookup"><span data-stu-id="8a6e2-184">ToolBar</span></span>|  
|<span data-ttu-id="8a6e2-185">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="8a6e2-185">ToolbarWindow32</span></span>|<span data-ttu-id="8a6e2-186">MenuItem</span><span class="sxs-lookup"><span data-stu-id="8a6e2-186">MenuItem</span></span>|  
|<span data-ttu-id="8a6e2-187">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="8a6e2-187">ToolbarWindow32</span></span>|<span data-ttu-id="8a6e2-188">按钮</span><span class="sxs-lookup"><span data-stu-id="8a6e2-188">Button</span></span>|  
|<span data-ttu-id="8a6e2-189">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="8a6e2-189">ToolbarWindow32</span></span>|<span data-ttu-id="8a6e2-190">CheckBox</span><span class="sxs-lookup"><span data-stu-id="8a6e2-190">CheckBox</span></span>|  
|<span data-ttu-id="8a6e2-191">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="8a6e2-191">ToolbarWindow32</span></span>|<span data-ttu-id="8a6e2-192">RadioButton</span><span class="sxs-lookup"><span data-stu-id="8a6e2-192">RadioButton</span></span>|  
|<span data-ttu-id="8a6e2-193">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="8a6e2-193">ToolbarWindow32</span></span>|<span data-ttu-id="8a6e2-194">分隔符</span><span class="sxs-lookup"><span data-stu-id="8a6e2-194">Separator</span></span>|  
|<span data-ttu-id="8a6e2-195">tooltips_class32</span><span class="sxs-lookup"><span data-stu-id="8a6e2-195">tooltips_class32</span></span>|<span data-ttu-id="8a6e2-196">ToolTip</span><span class="sxs-lookup"><span data-stu-id="8a6e2-196">ToolTip</span></span>|  
|<span data-ttu-id="8a6e2-197">#32774</span><span class="sxs-lookup"><span data-stu-id="8a6e2-197">#32774</span></span>|<span data-ttu-id="8a6e2-198">ToolTip</span><span class="sxs-lookup"><span data-stu-id="8a6e2-198">ToolTip</span></span>|  
|<span data-ttu-id="8a6e2-199">ReBarWindow32</span><span class="sxs-lookup"><span data-stu-id="8a6e2-199">ReBarWindow32</span></span>|<span data-ttu-id="8a6e2-200">工具栏</span><span class="sxs-lookup"><span data-stu-id="8a6e2-200">Toolbar</span></span>|  
|<span data-ttu-id="8a6e2-201">SysTreeView32</span><span class="sxs-lookup"><span data-stu-id="8a6e2-201">SysTreeView32</span></span>|<span data-ttu-id="8a6e2-202">树</span><span class="sxs-lookup"><span data-stu-id="8a6e2-202">Tree</span></span>|  
|<span data-ttu-id="8a6e2-203">SysTreeView32</span><span class="sxs-lookup"><span data-stu-id="8a6e2-203">SysTreeView32</span></span>|<span data-ttu-id="8a6e2-204">TreeItem</span><span class="sxs-lookup"><span data-stu-id="8a6e2-204">TreeItem</span></span>|  
  
 <span data-ttu-id="8a6e2-205">**注意**仅支持与 Windows Vista 一起附带的版本（在 RichEd20.dll 版本 3.1 及更高版本以及 MsftEdit.dll 版本 4.1 及更高版本）中支持 RichEdit 控件。</span><span class="sxs-lookup"><span data-stu-id="8a6e2-205">**Note** The RichEdit control is supported only for versions shipped with Windows Vista (in RichEd20.dll version 3.1 and later, and MsftEdit.dll version 4.1 and later).</span></span>  
  
 <span data-ttu-id="8a6e2-206">不支持以下控件。</span><span class="sxs-lookup"><span data-stu-id="8a6e2-206">The following controls are not supported.</span></span>  
  
|<span data-ttu-id="8a6e2-207">类名称</span><span class="sxs-lookup"><span data-stu-id="8a6e2-207">Class name</span></span>|<span data-ttu-id="8a6e2-208">控件类型</span><span class="sxs-lookup"><span data-stu-id="8a6e2-208">Control type</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="8a6e2-209">SysAnimate32</span><span class="sxs-lookup"><span data-stu-id="8a6e2-209">SysAnimate32</span></span>|<span data-ttu-id="8a6e2-210">映像</span><span class="sxs-lookup"><span data-stu-id="8a6e2-210">Image</span></span>|  
|<span data-ttu-id="8a6e2-211">SysPager</span><span class="sxs-lookup"><span data-stu-id="8a6e2-211">SysPager</span></span>|<span data-ttu-id="8a6e2-212">Spinner</span><span class="sxs-lookup"><span data-stu-id="8a6e2-212">Spinner</span></span>|  
|<span data-ttu-id="8a6e2-213">SysDateTimePick32</span><span class="sxs-lookup"><span data-stu-id="8a6e2-213">SysDateTimePick32</span></span>|<span data-ttu-id="8a6e2-214">自定义</span><span class="sxs-lookup"><span data-stu-id="8a6e2-214">Custom</span></span>|  
|<span data-ttu-id="8a6e2-215">SysMonthCal32</span><span class="sxs-lookup"><span data-stu-id="8a6e2-215">SysMonthCal32</span></span>|<span data-ttu-id="8a6e2-216">日历</span><span class="sxs-lookup"><span data-stu-id="8a6e2-216">Calendar</span></span>|  
|<span data-ttu-id="8a6e2-217">MS_WINNOTE</span><span class="sxs-lookup"><span data-stu-id="8a6e2-217">MS_WINNOTE</span></span>|<span data-ttu-id="8a6e2-218">工具提示</span><span class="sxs-lookup"><span data-stu-id="8a6e2-218">Tooltip</span></span>|  
|<span data-ttu-id="8a6e2-219">VBBubble</span><span class="sxs-lookup"><span data-stu-id="8a6e2-219">VBBubble</span></span>|<span data-ttu-id="8a6e2-220">工具提示</span><span class="sxs-lookup"><span data-stu-id="8a6e2-220">Tooltip</span></span>|  
|<span data-ttu-id="8a6e2-221">ScrollBar（在用作独立控件时）</span><span class="sxs-lookup"><span data-stu-id="8a6e2-221">ScrollBar (when used as a standalone control)</span></span>|<span data-ttu-id="8a6e2-222">滑块</span><span class="sxs-lookup"><span data-stu-id="8a6e2-222">Slider</span></span>|  
|<span data-ttu-id="8a6e2-223">SuperGrid</span><span class="sxs-lookup"><span data-stu-id="8a6e2-223">SuperGrid</span></span>|<span data-ttu-id="8a6e2-224">自定义</span><span class="sxs-lookup"><span data-stu-id="8a6e2-224">Custom</span></span>|  
  
<a name="Windows_Forms_Controls"></a>
## <a name="windows-forms-controls"></a><span data-ttu-id="8a6e2-225">Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="8a6e2-225">Windows Forms Controls</span></span>  
 <span data-ttu-id="8a6e2-226">Windows 窗体控件通过[!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)]UIAutomationClientside 提供程序.dll 中的客户端提供程序公开。</span><span class="sxs-lookup"><span data-stu-id="8a6e2-226">Windows Forms controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] through client-side providers in UIAutomationClientsideProviders.dll.</span></span> <span data-ttu-id="8a6e2-227">此程序集将自动注册，以用于 UI 自动化客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="8a6e2-227">This assembly is automatically registered for use with UI Automation client applications.</span></span>  
  
 <span data-ttu-id="8a6e2-228">通常，Win32 公共控件的托管包装器的 Windows 窗体控件受[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]支持。</span><span class="sxs-lookup"><span data-stu-id="8a6e2-228">Typically, Windows Forms controls that are managed wrappers for Win32 common controls are supported by [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span> <span data-ttu-id="8a6e2-229">支持以下控件。</span><span class="sxs-lookup"><span data-stu-id="8a6e2-229">The following controls are supported.</span></span>  
  
|<span data-ttu-id="8a6e2-230">类名</span><span class="sxs-lookup"><span data-stu-id="8a6e2-230">Class Name</span></span>|  
|----------------|  
|<span data-ttu-id="8a6e2-231">按钮</span><span class="sxs-lookup"><span data-stu-id="8a6e2-231">Button</span></span>|  
|<span data-ttu-id="8a6e2-232">CheckBox</span><span class="sxs-lookup"><span data-stu-id="8a6e2-232">CheckBox</span></span>|  
|<span data-ttu-id="8a6e2-233">CheckedListBox</span><span class="sxs-lookup"><span data-stu-id="8a6e2-233">CheckedListBox</span></span>|  
|<span data-ttu-id="8a6e2-234">ColorDialog</span><span class="sxs-lookup"><span data-stu-id="8a6e2-234">ColorDialog</span></span>|  
|<span data-ttu-id="8a6e2-235">ComboBox</span><span class="sxs-lookup"><span data-stu-id="8a6e2-235">ComboBox</span></span>|  
|<span data-ttu-id="8a6e2-236">FolderBrowser</span><span class="sxs-lookup"><span data-stu-id="8a6e2-236">FolderBrowser</span></span>|  
|<span data-ttu-id="8a6e2-237">FontDialog</span><span class="sxs-lookup"><span data-stu-id="8a6e2-237">FontDialog</span></span>|  
|<span data-ttu-id="8a6e2-238">GroupBox</span><span class="sxs-lookup"><span data-stu-id="8a6e2-238">GroupBox</span></span>|  
|<span data-ttu-id="8a6e2-239">HscrollBar</span><span class="sxs-lookup"><span data-stu-id="8a6e2-239">HscrollBar</span></span>|  
|<span data-ttu-id="8a6e2-240">ImageList</span><span class="sxs-lookup"><span data-stu-id="8a6e2-240">ImageList</span></span>|  
|<span data-ttu-id="8a6e2-241">Label</span><span class="sxs-lookup"><span data-stu-id="8a6e2-241">Label</span></span>|  
|<span data-ttu-id="8a6e2-242">ListBox</span><span class="sxs-lookup"><span data-stu-id="8a6e2-242">ListBox</span></span>|  
|<span data-ttu-id="8a6e2-243">ListView</span><span class="sxs-lookup"><span data-stu-id="8a6e2-243">ListView</span></span>|  
|<span data-ttu-id="8a6e2-244">MainMenu/ContextMenu</span><span class="sxs-lookup"><span data-stu-id="8a6e2-244">MainMenu/ContextMenu</span></span>|  
|<span data-ttu-id="8a6e2-245">MonthCalendar</span><span class="sxs-lookup"><span data-stu-id="8a6e2-245">MonthCalendar</span></span>|  
|<span data-ttu-id="8a6e2-246">NotifyIcon</span><span class="sxs-lookup"><span data-stu-id="8a6e2-246">NotifyIcon</span></span>|  
|<span data-ttu-id="8a6e2-247">OpenFileDialog</span><span class="sxs-lookup"><span data-stu-id="8a6e2-247">OpenFileDialog</span></span>|  
|<span data-ttu-id="8a6e2-248">PageSetupDialog</span><span class="sxs-lookup"><span data-stu-id="8a6e2-248">PageSetupDialog</span></span>|  
|<span data-ttu-id="8a6e2-249">PrintDialog</span><span class="sxs-lookup"><span data-stu-id="8a6e2-249">PrintDialog</span></span>|  
|<span data-ttu-id="8a6e2-250">ProgressBar</span><span class="sxs-lookup"><span data-stu-id="8a6e2-250">ProgressBar</span></span>|  
|<span data-ttu-id="8a6e2-251">RadioButton</span><span class="sxs-lookup"><span data-stu-id="8a6e2-251">RadioButton</span></span>|  
|<span data-ttu-id="8a6e2-252">RichTextBox</span><span class="sxs-lookup"><span data-stu-id="8a6e2-252">RichTextBox</span></span>|  
|<span data-ttu-id="8a6e2-253">SaveFileDialog</span><span class="sxs-lookup"><span data-stu-id="8a6e2-253">SaveFileDialog</span></span>|  
|<span data-ttu-id="8a6e2-254">ScrollableControl</span><span class="sxs-lookup"><span data-stu-id="8a6e2-254">ScrollableControl</span></span>|  
|<span data-ttu-id="8a6e2-255">SoundPlayer</span><span class="sxs-lookup"><span data-stu-id="8a6e2-255">SoundPlayer</span></span>|  
|<span data-ttu-id="8a6e2-256">StatusBar</span><span class="sxs-lookup"><span data-stu-id="8a6e2-256">StatusBar</span></span>|  
|<span data-ttu-id="8a6e2-257">TabControl/TabPage</span><span class="sxs-lookup"><span data-stu-id="8a6e2-257">TabControl/TabPage</span></span>|  
|<span data-ttu-id="8a6e2-258">TextBox</span><span class="sxs-lookup"><span data-stu-id="8a6e2-258">TextBox</span></span>|  
|<span data-ttu-id="8a6e2-259">Timer</span><span class="sxs-lookup"><span data-stu-id="8a6e2-259">Timer</span></span>|  
|<span data-ttu-id="8a6e2-260">工具栏</span><span class="sxs-lookup"><span data-stu-id="8a6e2-260">Toolbar</span></span>|  
|<span data-ttu-id="8a6e2-261">ToolTip</span><span class="sxs-lookup"><span data-stu-id="8a6e2-261">ToolTip</span></span>|  
|<span data-ttu-id="8a6e2-262">TrackBar</span><span class="sxs-lookup"><span data-stu-id="8a6e2-262">TrackBar</span></span>|  
|<span data-ttu-id="8a6e2-263">TreeView</span><span class="sxs-lookup"><span data-stu-id="8a6e2-263">TreeView</span></span>|  
|<span data-ttu-id="8a6e2-264">VscrollBar</span><span class="sxs-lookup"><span data-stu-id="8a6e2-264">VscrollBar</span></span>|  
|<span data-ttu-id="8a6e2-265">Web 浏览器</span><span class="sxs-lookup"><span data-stu-id="8a6e2-265">WebBrowser</span></span>|  
  
 <span data-ttu-id="8a6e2-266">以下控件[!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)]仅通过支持 Microsoft 活动辅助功能而公开。</span><span class="sxs-lookup"><span data-stu-id="8a6e2-266">The following controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] only through their support for Microsoft Active Accessibility.</span></span> <span data-ttu-id="8a6e2-267">某些功能可能不可用。</span><span class="sxs-lookup"><span data-stu-id="8a6e2-267">Some functionality may not be available.</span></span>  
  
|<span data-ttu-id="8a6e2-268">控件名称</span><span class="sxs-lookup"><span data-stu-id="8a6e2-268">Control Name</span></span>|  
|------------------|  
|<span data-ttu-id="8a6e2-269">BindingSource</span><span class="sxs-lookup"><span data-stu-id="8a6e2-269">BindingSource</span></span>|  
|<span data-ttu-id="8a6e2-270">DataGrid</span><span class="sxs-lookup"><span data-stu-id="8a6e2-270">DataGrid</span></span>|  
|<span data-ttu-id="8a6e2-271">DataGridView</span><span class="sxs-lookup"><span data-stu-id="8a6e2-271">DataGridView</span></span>|  
|<span data-ttu-id="8a6e2-272">DataNavigator</span><span class="sxs-lookup"><span data-stu-id="8a6e2-272">DataNavigator</span></span>|  
|<span data-ttu-id="8a6e2-273">DomainUpDown</span><span class="sxs-lookup"><span data-stu-id="8a6e2-273">DomainUpDown</span></span>|  
|<span data-ttu-id="8a6e2-274">ErrorProvider</span><span class="sxs-lookup"><span data-stu-id="8a6e2-274">ErrorProvider</span></span>|  
|<span data-ttu-id="8a6e2-275">FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="8a6e2-275">FlowLayoutPanel</span></span>|  
|<span data-ttu-id="8a6e2-276">Form</span><span class="sxs-lookup"><span data-stu-id="8a6e2-276">Form</span></span>|  
|<span data-ttu-id="8a6e2-277">LinkLabel</span><span class="sxs-lookup"><span data-stu-id="8a6e2-277">LinkLabel</span></span>|  
|<span data-ttu-id="8a6e2-278">HelpProvider</span><span class="sxs-lookup"><span data-stu-id="8a6e2-278">HelpProvider</span></span>|  
|<span data-ttu-id="8a6e2-279">MaskedTextBox</span><span class="sxs-lookup"><span data-stu-id="8a6e2-279">MaskedTextBox</span></span>|  
|<span data-ttu-id="8a6e2-280">MenuStrip/ContextMenuStrip</span><span class="sxs-lookup"><span data-stu-id="8a6e2-280">MenuStrip/ContextMenuStrip</span></span>|  
|<span data-ttu-id="8a6e2-281">NumericUpDown</span><span class="sxs-lookup"><span data-stu-id="8a6e2-281">NumericUpDown</span></span>|  
|<span data-ttu-id="8a6e2-282">Panel</span><span class="sxs-lookup"><span data-stu-id="8a6e2-282">Panel</span></span>|  
|<span data-ttu-id="8a6e2-283">PictureBox</span><span class="sxs-lookup"><span data-stu-id="8a6e2-283">PictureBox</span></span>|  
|<span data-ttu-id="8a6e2-284">PrintDocument</span><span class="sxs-lookup"><span data-stu-id="8a6e2-284">PrintDocument</span></span>|  
|<span data-ttu-id="8a6e2-285">PrintPreview-Control</span><span class="sxs-lookup"><span data-stu-id="8a6e2-285">PrintPreview-Control</span></span>|  
|<span data-ttu-id="8a6e2-286">PrintPreview-Dialog</span><span class="sxs-lookup"><span data-stu-id="8a6e2-286">PrintPreview-Dialog</span></span>|  
|<span data-ttu-id="8a6e2-287">PropertyGrid</span><span class="sxs-lookup"><span data-stu-id="8a6e2-287">PropertyGrid</span></span>|  
|<span data-ttu-id="8a6e2-288">用户控件</span><span class="sxs-lookup"><span data-stu-id="8a6e2-288">UserControl</span></span>|  
|<span data-ttu-id="8a6e2-289">ToolStrip</span><span class="sxs-lookup"><span data-stu-id="8a6e2-289">ToolStrip</span></span>|  
|<span data-ttu-id="8a6e2-290">TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="8a6e2-290">TableLayoutPanel</span></span>|  
|<span data-ttu-id="8a6e2-291">SplitContainer/SplitterPanel</span><span class="sxs-lookup"><span data-stu-id="8a6e2-291">SplitContainer/SplitterPanel</span></span>|  
|<span data-ttu-id="8a6e2-292">Splitter</span><span class="sxs-lookup"><span data-stu-id="8a6e2-292">Splitter</span></span>|  
|<span data-ttu-id="8a6e2-293">RaftingContainer</span><span class="sxs-lookup"><span data-stu-id="8a6e2-293">RaftingContainer</span></span>|  
|<span data-ttu-id="8a6e2-294">StatusStrip</span><span class="sxs-lookup"><span data-stu-id="8a6e2-294">StatusStrip</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8a6e2-295">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8a6e2-295">See also</span></span>

- [<span data-ttu-id="8a6e2-296">UI Automation Control Types</span><span class="sxs-lookup"><span data-stu-id="8a6e2-296">UI Automation Control Types</span></span>](ui-automation-control-types.md)
