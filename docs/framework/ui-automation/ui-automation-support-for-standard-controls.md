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
# <a name="ui-automation-support-for-standard-controls"></a>UI 自动化对标准控件的支持
> [!NOTE]
> 本文档适用于想要使用 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 命名空间中定义的托管 <xref:System.Windows.Automation> 类的 .NET Framework 开发人员。 有关 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]的最新信息，请参阅 [Windows 自动化 API：UI 自动化](/windows/win32/winauto/entry-uiauto-win32)。  
  
 本主题包含有关支持为[!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)][!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)]Win32 和 Windows 窗体框架开发的应用程序中的标准控件的信息。  
  
<a name="Windows_Presentation_Foundation_Controls"></a>
## <a name="windows-presentation-foundation-controls"></a>Windows Presentation Foundation 控件  
 为用户交互提供信息或支持的所有 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 控件元素均具有对 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]的完整本机支持。 面板等其他元素对 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]不可见。  
  
<a name="Win32_Controls"></a>
## <a name="win32-controls"></a>Win32 控件  
 大多数 Win32 控件[!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)]通过 UIAutomationClientside 提供程序.dll 中的客户端提供程序公开。 此程序集将自动注册，以用于 UI 自动化客户端应用程序。  
  
 完全支持仅为*ComCtrl32.dll*版本 6 中的控件提供。  
  
 支持以下控件。  
  
|类名称|控件类型|  
|----------------|------------------|  
|按钮|按钮|  
|按钮|RadioButton|  
|按钮|组|  
|按钮|CheckBox|  
|按钮|Hyperlink|  
|按钮|SplitButton|  
|按钮|CheckBox|  
|ComboBoxEx32|ComboBox|  
|ComboBox|ComboBox|  
|编辑|Document|  
|编辑|编辑|  
|SysLink|Hyperlink|  
|静态|文本|  
|静态|映像|  
|SysIPAddress32|自定义|  
|SysHeader32|Header/HeaderItem|  
|SysListView32|DataGrid|  
|SysListView32|列出|  
|ListBox|列出|  
|ListBox|ListItem|  
|#32768|菜单|  
|#32768|MenuItem|  
|msctls_progress32|ProgressBar|  
|RichEdit|Document。 请参阅注释。|  
|RichEdit20A|Document|  
|RichEdit20W|Document|  
|RichEdit50W|Document|  
|ScrollBar|滑块|  
|msctls_trackbar32|滑块|  
|msctls_updown32|Spinner|  
|msctls_statusbar32|StatusBar|  
|SysTabControl32|选项卡|  
|SysTabControl32|TabItem|  
|ToolbarWindow32|ToolBar|  
|ToolbarWindow32|MenuItem|  
|ToolbarWindow32|按钮|  
|ToolbarWindow32|CheckBox|  
|ToolbarWindow32|RadioButton|  
|ToolbarWindow32|分隔符|  
|tooltips_class32|ToolTip|  
|#32774|ToolTip|  
|ReBarWindow32|工具栏|  
|SysTreeView32|树|  
|SysTreeView32|TreeItem|  
  
 **注意**仅支持与 Windows Vista 一起附带的版本（在 RichEd20.dll 版本 3.1 及更高版本以及 MsftEdit.dll 版本 4.1 及更高版本）中支持 RichEdit 控件。  
  
 不支持以下控件。  
  
|类名称|控件类型|  
|----------------|------------------|  
|SysAnimate32|映像|  
|SysPager|Spinner|  
|SysDateTimePick32|自定义|  
|SysMonthCal32|日历|  
|MS_WINNOTE|工具提示|  
|VBBubble|工具提示|  
|ScrollBar（在用作独立控件时）|滑块|  
|SuperGrid|自定义|  
  
<a name="Windows_Forms_Controls"></a>
## <a name="windows-forms-controls"></a>Windows 窗体控件  
 Windows 窗体控件通过[!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)]UIAutomationClientside 提供程序.dll 中的客户端提供程序公开。 此程序集将自动注册，以用于 UI 自动化客户端应用程序。  
  
 通常，Win32 公共控件的托管包装器的 Windows 窗体控件受[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]支持。 支持以下控件。  
  
|类名|  
|----------------|  
|按钮|  
|CheckBox|  
|CheckedListBox|  
|ColorDialog|  
|ComboBox|  
|FolderBrowser|  
|FontDialog|  
|GroupBox|  
|HscrollBar|  
|ImageList|  
|Label|  
|ListBox|  
|ListView|  
|MainMenu/ContextMenu|  
|MonthCalendar|  
|NotifyIcon|  
|OpenFileDialog|  
|PageSetupDialog|  
|PrintDialog|  
|ProgressBar|  
|RadioButton|  
|RichTextBox|  
|SaveFileDialog|  
|ScrollableControl|  
|SoundPlayer|  
|StatusBar|  
|TabControl/TabPage|  
|TextBox|  
|Timer|  
|工具栏|  
|ToolTip|  
|TrackBar|  
|TreeView|  
|VscrollBar|  
|Web 浏览器|  
  
 以下控件[!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)]仅通过支持 Microsoft 活动辅助功能而公开。 某些功能可能不可用。  
  
|控件名称|  
|------------------|  
|BindingSource|  
|DataGrid|  
|DataGridView|  
|DataNavigator|  
|DomainUpDown|  
|ErrorProvider|  
|FlowLayoutPanel|  
|Form|  
|LinkLabel|  
|HelpProvider|  
|MaskedTextBox|  
|MenuStrip/ContextMenuStrip|  
|NumericUpDown|  
|Panel|  
|PictureBox|  
|PrintDocument|  
|PrintPreview-Control|  
|PrintPreview-Dialog|  
|PropertyGrid|  
|用户控件|  
|ToolStrip|  
|TableLayoutPanel|  
|SplitContainer/SplitterPanel|  
|Splitter|  
|RaftingContainer|  
|StatusStrip|  
  
## <a name="see-also"></a>另请参阅

- [UI Automation Control Types](ui-automation-control-types.md)
