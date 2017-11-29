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
# <a name="ui-automation-control-types-overview"></a>UI 自动化控件类型概述
> [!NOTE]
>  本文档适用于想要使用 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 命名空间中定义的托管 <xref:System.Windows.Automation> 类的 .NET Framework 开发人员。 有关 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]的最新信息，请参阅 [Windows 自动化 API：UI 自动化](http://go.microsoft.com/fwlink/?LinkID=156746)。  
  
 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] 控件类型是已知的标识符，可用于指示特定元素显示的控件类型，例如组合框或按钮。  
  
 具有已知标识符便于辅助技术设备确定 [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] 中可用的控件的类型以及和控件交互的方式。  
  
<a name="UI_Automation_Control_Type_Requisites"></a>   
## <a name="ui-automation-control-type-requisites"></a>UI 自动化控件类型必备条件  
 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] 控件类型提供一组提供程序必须满足的条件。 满足这些条件时，控件可以使用特定的控件类型名称。 每个控件类型对以下内容设有条件：  
  
-   [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 控件模式 — 必须支持哪些控件模式、哪个控件模式是可选的以及控件不得支持哪些控件模式。  
  
-   [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 属性值 — 支持哪些属性值。  
  
-   [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 树结构 — 控件必需的 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 树结构。  
  
 当控件满足特定控件类型的条件时， <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.ControlType%2A> 属性值将指示该控件类型。  
  
<a name="Current_UI_Automation_Control_Types"></a>   
## <a name="current-ui-automation-control-types"></a>当前的 UI 自动化控件类型  
 以下列表包含当前 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] 控制类型集：  
  
-   [Button 控件类型的 UI 自动化支持](../../../docs/framework/ui-automation/ui-automation-support-for-the-button-control-type.md)  
  
-   [Calendar 控件类型的 UI 自动化支持](../../../docs/framework/ui-automation/ui-automation-support-for-the-calendar-control-type.md)  
  
-   [对 CheckBox 控件类型的 UI 自动化支持](../../../docs/framework/ui-automation/ui-automation-support-for-the-checkbox-control-type.md)  
  
-   [对 ComboBox 控件类型的 UI 自动化支持](../../../docs/framework/ui-automation/ui-automation-support-for-the-combobox-control-type.md)  
  
-   [DataGrid 控件类型的 UI 自动化支持](../../../docs/framework/ui-automation/ui-automation-support-for-the-datagrid-control-type.md)  
  
-   [对 DataItem 控件类型的 UI 自动化支持](../../../docs/framework/ui-automation/ui-automation-support-for-the-dataitem-control-type.md)  
  
-   [UI 自动化对 Document 控件类型的支持](../../../docs/framework/ui-automation/ui-automation-support-for-the-document-control-type.md)  
  
-   [Edit 控件类型的 UI 自动化支持](../../../docs/framework/ui-automation/ui-automation-support-for-the-edit-control-type.md)  
  
-   [Group 控件类型的 UI 自动化支持](../../../docs/framework/ui-automation/ui-automation-support-for-the-group-control-type.md)  
  
-   [标头控件类型的 UI 自动化支持](../../../docs/framework/ui-automation/ui-automation-support-for-the-header-control-type.md)  
  
-   [UI 自动化对 HeaderItem 控件类型的支持](../../../docs/framework/ui-automation/ui-automation-support-for-the-headeritem-control-type.md)  
  
-   [Hyperlink 控件类型的 UI 自动化支持](../../../docs/framework/ui-automation/ui-automation-support-for-the-hyperlink-control-type.md)  
  
-   [图像控件类型的 UI 自动化支持](../../../docs/framework/ui-automation/ui-automation-support-for-the-image-control-type.md)  
  
-   [List 控件类型的 UI 自动化支持](../../../docs/framework/ui-automation/ui-automation-support-for-the-list-control-type.md)  
  
-   [对 ListItem 控件类型的 UI 自动化支持](../../../docs/framework/ui-automation/ui-automation-support-for-the-listitem-control-type.md)  
  
-   [Menu 控件类型的 UI 自动化支持](../../../docs/framework/ui-automation/ui-automation-support-for-the-menu-control-type.md)  
  
-   [对 MenuBar 控件类型的 UI 自动化支持](../../../docs/framework/ui-automation/ui-automation-support-for-the-menubar-control-type.md)  
  
-   [对 MenuItem 控件类型的 UI 自动化支持](../../../docs/framework/ui-automation/ui-automation-support-for-the-menuitem-control-type.md)  
  
-   [窗格控件类型的 UI 自动化支持](../../../docs/framework/ui-automation/ui-automation-support-for-the-pane-control-type.md)  
  
-   [UI 自动化对 ProgressBar 控件类型的支持](../../../docs/framework/ui-automation/ui-automation-support-for-the-progressbar-control-type.md)  
  
-   [对 RadioButton 控件类型的 UI 自动化支持](../../../docs/framework/ui-automation/ui-automation-support-for-the-radiobutton-control-type.md)  
  
-   [对 ScrollBar 控件类型的 UI 自动化支持](../../../docs/framework/ui-automation/ui-automation-support-for-the-scrollbar-control-type.md)  
  
-   [Separator 控件类型的 UI 自动化支持](../../../docs/framework/ui-automation/ui-automation-support-for-the-separator-control-type.md)  
  
-   [Slider 控件类型的 UI 自动化支持](../../../docs/framework/ui-automation/ui-automation-support-for-the-slider-control-type.md)  
  
-   [微调控件类型的 UI 自动化支持](../../../docs/framework/ui-automation/ui-automation-support-for-the-spinner-control-type.md)  
  
-   [对 SplitButton 控件类型的 UI 自动化支持](../../../docs/framework/ui-automation/ui-automation-support-for-the-splitbutton-control-type.md)  
  
-   [对 StatusBar 控件类型的 UI 自动化支持](../../../docs/framework/ui-automation/ui-automation-support-for-the-statusbar-control-type.md)  
  
-   [Tab 控件类型的 UI 自动化支持](../../../docs/framework/ui-automation/ui-automation-support-for-the-tab-control-type.md)  
  
-   [对 TabItem 控件类型的 UI 自动化支持](../../../docs/framework/ui-automation/ui-automation-support-for-the-tabitem-control-type.md)  
  
-   [Table 控件类型的 UI 自动化支持](../../../docs/framework/ui-automation/ui-automation-support-for-the-table-control-type.md)  
  
-   [Text 控件类型的 UI 自动化支持](../../../docs/framework/ui-automation/ui-automation-support-for-the-text-control-type.md)  
  
-   [Thumb 控件类型的 UI 自动化支持](../../../docs/framework/ui-automation/ui-automation-support-for-the-thumb-control-type.md)  
  
-   [对 TitleBar 控件类型的 UI 自动化支持](../../../docs/framework/ui-automation/ui-automation-support-for-the-titlebar-control-type.md)  
  
-   [工具栏控件类型的 UI 自动化支持](../../../docs/framework/ui-automation/ui-automation-support-for-the-toolbar-control-type.md)  
  
-   [ToolTip 控件类型的 UI 自动化支持](../../../docs/framework/ui-automation/ui-automation-support-for-the-tooltip-control-type.md)  
  
-   [Tree 控件类型的 UI 自动化支持](../../../docs/framework/ui-automation/ui-automation-support-for-the-tree-control-type.md)  
  
-   [对 TreeItem 控件类型的 UI 自动化支持](../../../docs/framework/ui-automation/ui-automation-support-for-the-treeitem-control-type.md)  
  
-   [UI 自动化 Window 控件类型的支持](../../../docs/framework/ui-automation/ui-automation-support-for-the-window-control-type.md)  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Windows.Automation.ControlType>
