---
title: "UI 自动化控件类型概述"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- UI Automation, control types
- control types, UI Automation
ms.assetid: 75159ef8-bd43-4d13-acb7-1f1fe9253160
caps.latest.revision: "22"
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: c1a424f05f2d57f773e8367e102f553d69b7dc22
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="ui-automation-control-types-overview"></a><span data-ttu-id="90960-102">UI 自动化控件类型概述</span><span class="sxs-lookup"><span data-stu-id="90960-102">UI Automation Control Types Overview</span></span>
> [!NOTE]
>  <span data-ttu-id="90960-103">本文档适用于想要使用 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 命名空间中定义的托管 <xref:System.Windows.Automation> 类的 .NET Framework 开发人员。</span><span class="sxs-lookup"><span data-stu-id="90960-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="90960-104">有关 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]的最新信息，请参阅 [Windows 自动化 API：UI 自动化](http://go.microsoft.com/fwlink/?LinkID=156746)。</span><span class="sxs-lookup"><span data-stu-id="90960-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](http://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)]<span data-ttu-id="90960-105"> 控件类型是已知的标识符，可用于指示特定元素显示的控件类型，例如组合框或按钮。</span><span class="sxs-lookup"><span data-stu-id="90960-105"> control types are well-known identifiers that can be used to indicate what kind of control a particular element represents, such as a combo box or a button.</span></span>  
  
 <span data-ttu-id="90960-106">具有已知标识符便于辅助技术设备确定 [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] 中可用的控件的类型以及和控件交互的方式。</span><span class="sxs-lookup"><span data-stu-id="90960-106">Having a well-known identifier makes it easier for assistive technology devices to determine what types of controls are available in the [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] and how to interact with the controls.</span></span>  
  
<a name="UI_Automation_Control_Type_Requisites"></a>   
## <a name="ui-automation-control-type-requisites"></a><span data-ttu-id="90960-107">UI 自动化控件类型必备条件</span><span class="sxs-lookup"><span data-stu-id="90960-107">UI Automation Control Type Requisites</span></span>  
 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)]<span data-ttu-id="90960-108"> 控件类型提供一组提供程序必须满足的条件。</span><span class="sxs-lookup"><span data-stu-id="90960-108"> control types provide a set of conditions that providers must meet.</span></span> <span data-ttu-id="90960-109">满足这些条件时，控件可以使用特定的控件类型名称。</span><span class="sxs-lookup"><span data-stu-id="90960-109">When these conditions are met, the control can use the specific control type name.</span></span> <span data-ttu-id="90960-110">每个控件类型对以下内容设有条件：</span><span class="sxs-lookup"><span data-stu-id="90960-110">Each control type has conditions for the following:</span></span>  
  
-   [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]<span data-ttu-id="90960-111"> 控件模式 — 必须支持哪些控件模式、哪个控件模式是可选的以及控件不得支持哪些控件模式。</span><span class="sxs-lookup"><span data-stu-id="90960-111"> control patterns—which control patterns must be supported, which control patterns are optional, and which control patterns must not be supported by the control.</span></span>  
  
-   [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]<span data-ttu-id="90960-112"> 属性值 — 支持哪些属性值。</span><span class="sxs-lookup"><span data-stu-id="90960-112"> property values—which property values are supported.</span></span>  
  
-   [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]<span data-ttu-id="90960-113"> 树结构 — 控件必需的 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 树结构。</span><span class="sxs-lookup"><span data-stu-id="90960-113"> tree structure—the required [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] tree structure for the control.</span></span>  
  
 <span data-ttu-id="90960-114">当控件满足特定控件类型的条件时， <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.ControlType%2A> 属性值将指示该控件类型。</span><span class="sxs-lookup"><span data-stu-id="90960-114">When a control meets the conditions for a particular control type, the <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.ControlType%2A> property value will indicate that control type.</span></span>  
  
<a name="Current_UI_Automation_Control_Types"></a>   
## <a name="current-ui-automation-control-types"></a><span data-ttu-id="90960-115">当前的 UI 自动化控件类型</span><span class="sxs-lookup"><span data-stu-id="90960-115">Current UI Automation Control Types</span></span>  
 <span data-ttu-id="90960-116">以下列表包含当前 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] 控制类型集：</span><span class="sxs-lookup"><span data-stu-id="90960-116">The following list contains the current set of [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] control types:</span></span>  
  
-   [<span data-ttu-id="90960-117">Button 控件类型的 UI 自动化支持</span><span class="sxs-lookup"><span data-stu-id="90960-117">UI Automation Support for the Button Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-button-control-type.md)  
  
-   [<span data-ttu-id="90960-118">Calendar 控件类型的 UI 自动化支持</span><span class="sxs-lookup"><span data-stu-id="90960-118">UI Automation Support for the Calendar Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-calendar-control-type.md)  
  
-   [<span data-ttu-id="90960-119">对 CheckBox 控件类型的 UI 自动化支持</span><span class="sxs-lookup"><span data-stu-id="90960-119">UI Automation Support for the CheckBox Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-checkbox-control-type.md)  
  
-   [<span data-ttu-id="90960-120">对 ComboBox 控件类型的 UI 自动化支持</span><span class="sxs-lookup"><span data-stu-id="90960-120">UI Automation Support for the ComboBox Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-combobox-control-type.md)  
  
-   [<span data-ttu-id="90960-121">DataGrid 控件类型的 UI 自动化支持</span><span class="sxs-lookup"><span data-stu-id="90960-121">UI Automation Support for the DataGrid Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-datagrid-control-type.md)  
  
-   [<span data-ttu-id="90960-122">对 DataItem 控件类型的 UI 自动化支持</span><span class="sxs-lookup"><span data-stu-id="90960-122">UI Automation Support for the DataItem Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-dataitem-control-type.md)  
  
-   [<span data-ttu-id="90960-123">UI 自动化对 Document 控件类型的支持</span><span class="sxs-lookup"><span data-stu-id="90960-123">UI Automation Support for the Document Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-document-control-type.md)  
  
-   [<span data-ttu-id="90960-124">Edit 控件类型的 UI 自动化支持</span><span class="sxs-lookup"><span data-stu-id="90960-124">UI Automation Support for the Edit Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-edit-control-type.md)  
  
-   [<span data-ttu-id="90960-125">Group 控件类型的 UI 自动化支持</span><span class="sxs-lookup"><span data-stu-id="90960-125">UI Automation Support for the Group Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-group-control-type.md)  
  
-   [<span data-ttu-id="90960-126">标头控件类型的 UI 自动化支持</span><span class="sxs-lookup"><span data-stu-id="90960-126">UI Automation Support for the Header Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-header-control-type.md)  
  
-   [<span data-ttu-id="90960-127">UI 自动化对 HeaderItem 控件类型的支持</span><span class="sxs-lookup"><span data-stu-id="90960-127">UI Automation Support for the HeaderItem Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-headeritem-control-type.md)  
  
-   [<span data-ttu-id="90960-128">Hyperlink 控件类型的 UI 自动化支持</span><span class="sxs-lookup"><span data-stu-id="90960-128">UI Automation Support for the Hyperlink Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-hyperlink-control-type.md)  
  
-   [<span data-ttu-id="90960-129">图像控件类型的 UI 自动化支持</span><span class="sxs-lookup"><span data-stu-id="90960-129">UI Automation Support for the Image Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-image-control-type.md)  
  
-   [<span data-ttu-id="90960-130">List 控件类型的 UI 自动化支持</span><span class="sxs-lookup"><span data-stu-id="90960-130">UI Automation Support for the List Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-list-control-type.md)  
  
-   [<span data-ttu-id="90960-131">对 ListItem 控件类型的 UI 自动化支持</span><span class="sxs-lookup"><span data-stu-id="90960-131">UI Automation Support for the ListItem Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-listitem-control-type.md)  
  
-   [<span data-ttu-id="90960-132">Menu 控件类型的 UI 自动化支持</span><span class="sxs-lookup"><span data-stu-id="90960-132">UI Automation Support for the Menu Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-menu-control-type.md)  
  
-   [<span data-ttu-id="90960-133">对 MenuBar 控件类型的 UI 自动化支持</span><span class="sxs-lookup"><span data-stu-id="90960-133">UI Automation Support for the MenuBar Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-menubar-control-type.md)  
  
-   [<span data-ttu-id="90960-134">对 MenuItem 控件类型的 UI 自动化支持</span><span class="sxs-lookup"><span data-stu-id="90960-134">UI Automation Support for the MenuItem Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-menuitem-control-type.md)  
  
-   [<span data-ttu-id="90960-135">窗格控件类型的 UI 自动化支持</span><span class="sxs-lookup"><span data-stu-id="90960-135">UI Automation Support for the Pane Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-pane-control-type.md)  
  
-   [<span data-ttu-id="90960-136">UI 自动化对 ProgressBar 控件类型的支持</span><span class="sxs-lookup"><span data-stu-id="90960-136">UI Automation Support for the ProgressBar Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-progressbar-control-type.md)  
  
-   [<span data-ttu-id="90960-137">对 RadioButton 控件类型的 UI 自动化支持</span><span class="sxs-lookup"><span data-stu-id="90960-137">UI Automation Support for the RadioButton Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-radiobutton-control-type.md)  
  
-   [<span data-ttu-id="90960-138">对 ScrollBar 控件类型的 UI 自动化支持</span><span class="sxs-lookup"><span data-stu-id="90960-138">UI Automation Support for the ScrollBar Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-scrollbar-control-type.md)  
  
-   [<span data-ttu-id="90960-139">Separator 控件类型的 UI 自动化支持</span><span class="sxs-lookup"><span data-stu-id="90960-139">UI Automation Support for the Separator Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-separator-control-type.md)  
  
-   [<span data-ttu-id="90960-140">Slider 控件类型的 UI 自动化支持</span><span class="sxs-lookup"><span data-stu-id="90960-140">UI Automation Support for the Slider Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-slider-control-type.md)  
  
-   [<span data-ttu-id="90960-141">微调控件类型的 UI 自动化支持</span><span class="sxs-lookup"><span data-stu-id="90960-141">UI Automation Support for the Spinner Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-spinner-control-type.md)  
  
-   [<span data-ttu-id="90960-142">对 SplitButton 控件类型的 UI 自动化支持</span><span class="sxs-lookup"><span data-stu-id="90960-142">UI Automation Support for the SplitButton Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-splitbutton-control-type.md)  
  
-   [<span data-ttu-id="90960-143">对 StatusBar 控件类型的 UI 自动化支持</span><span class="sxs-lookup"><span data-stu-id="90960-143">UI Automation Support for the StatusBar Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-statusbar-control-type.md)  
  
-   [<span data-ttu-id="90960-144">Tab 控件类型的 UI 自动化支持</span><span class="sxs-lookup"><span data-stu-id="90960-144">UI Automation Support for the Tab Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-tab-control-type.md)  
  
-   [<span data-ttu-id="90960-145">对 TabItem 控件类型的 UI 自动化支持</span><span class="sxs-lookup"><span data-stu-id="90960-145">UI Automation Support for the TabItem Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-tabitem-control-type.md)  
  
-   [<span data-ttu-id="90960-146">Table 控件类型的 UI 自动化支持</span><span class="sxs-lookup"><span data-stu-id="90960-146">UI Automation Support for the Table Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-table-control-type.md)  
  
-   [<span data-ttu-id="90960-147">Text 控件类型的 UI 自动化支持</span><span class="sxs-lookup"><span data-stu-id="90960-147">UI Automation Support for the Text Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-text-control-type.md)  
  
-   [<span data-ttu-id="90960-148">Thumb 控件类型的 UI 自动化支持</span><span class="sxs-lookup"><span data-stu-id="90960-148">UI Automation Support for the Thumb Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-thumb-control-type.md)  
  
-   [<span data-ttu-id="90960-149">对 TitleBar 控件类型的 UI 自动化支持</span><span class="sxs-lookup"><span data-stu-id="90960-149">UI Automation Support for the TitleBar Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-titlebar-control-type.md)  
  
-   [<span data-ttu-id="90960-150">工具栏控件类型的 UI 自动化支持</span><span class="sxs-lookup"><span data-stu-id="90960-150">UI Automation Support for the ToolBar Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-toolbar-control-type.md)  
  
-   [<span data-ttu-id="90960-151">ToolTip 控件类型的 UI 自动化支持</span><span class="sxs-lookup"><span data-stu-id="90960-151">UI Automation Support for the ToolTip Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-tooltip-control-type.md)  
  
-   [<span data-ttu-id="90960-152">Tree 控件类型的 UI 自动化支持</span><span class="sxs-lookup"><span data-stu-id="90960-152">UI Automation Support for the Tree Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-tree-control-type.md)  
  
-   [<span data-ttu-id="90960-153">对 TreeItem 控件类型的 UI 自动化支持</span><span class="sxs-lookup"><span data-stu-id="90960-153">UI Automation Support for the TreeItem Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-treeitem-control-type.md)  
  
-   [<span data-ttu-id="90960-154">UI 自动化 Window 控件类型的支持</span><span class="sxs-lookup"><span data-stu-id="90960-154">UI Automation Support for the Window Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-window-control-type.md)  
  
## <a name="see-also"></a><span data-ttu-id="90960-155">另请参阅</span><span class="sxs-lookup"><span data-stu-id="90960-155">See Also</span></span>  
 <xref:System.Windows.Automation.ControlType>
