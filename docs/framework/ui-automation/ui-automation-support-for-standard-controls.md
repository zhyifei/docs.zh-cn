---
title: UI 自动化对标准控件的支持
ms.date: 03/30/2017
helpviewer_keywords:
- controls, UI Automation support for
- UI Automation, support for standard controls
ms.assetid: 3770ea8a-2655-4add-9c59-fe0610ad5084
ms.openlocfilehash: c59352f908c5f4a1fd2ca6dd631d26bb5d69f09a
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74441222"
---
# <a name="ui-automation-support-for-standard-controls"></a>UI 自动化对标准控件的支持
> [!NOTE]
> 本文档适用于想要使用 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 命名空间中定义的托管 <xref:System.Windows.Automation> 类的 .NET Framework 开发人员。 有关 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]的最新信息，请参阅 [Windows 自动化 API：UI 自动化](/windows/win32/winauto/entry-uiauto-win32)。  
  
 本主题包含有关对为 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] 、 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)]和 [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)]框架所开发的应用程序中标准控件的 [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)] 支持的信息。  
  
<a name="Windows_Presentation_Foundation_Controls"></a>   
## <a name="windows-presentation-foundation-controls"></a>Windows Presentation Foundation 控件  
 为用户交互提供信息或支持的所有 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 控件元素均具有对 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]的完整本机支持。 面板等其他元素对 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]不可见。  
  
<a name="Win32_Controls"></a>   
## <a name="win32-controls"></a>Win32 控件  
 大多数 [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] 控件都通过 UIAutomationClientsideProviders.dll 中的客户端提供程序向 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] 公开。 此程序集将自动注册，以用于 UI 自动化客户端应用程序。  
  
 仅对 ComCtrl32.dll 版本 6（随 [!INCLUDE[TLA#tla_winxp](../../../includes/tlasharptla-winxp-md.md)] 和更高版本提供）中的控件提供完全支持。  
  
 支持以下控件。  
  
|类名称|控件类型|  
|----------------|------------------|  
|按钮|按钮|  
|按钮|RadioButton|  
|按钮|组|  
|按钮|CheckBox|  
|按钮|超链接|  
|按钮|SplitButton|  
|按钮|CheckBox|  
|ComboBoxEx32|组合框|  
|组合框|组合框|  
|编辑|文档|  
|编辑|编辑|  
|SysLink|超链接|  
|静态|文本|  
|静态|映像|  
|SysIPAddress32|自定义|  
|SysHeader32|Header/HeaderItem|  
|SysListView32|DataGrid|  
|SysListView32|列表|  
|ListBox|列表|  
|ListBox|ListItem|  
|#32768|菜单|  
|#32768|MenuItem|  
|msctls_progress32|进度条|  
|RichEdit|Document。 请参阅注释。|  
|RichEdit20A|文档|  
|RichEdit20W|文档|  
|RichEdit50W|文档|  
|ScrollBar|滑块|  
|msctls_trackbar32|滑块|  
|msctls_updown32|Spinner|  
|msctls_statusbar32|StatusBar|  
|SysTabControl32|Tab|  
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
  
 **注意**只有 Windows Vista 附带的版本（在 Riched20.dll 版本3.1 及更高版本以及 Msftedit.dll 版本4.1 及更高版本）支持 RichEdit 控件。  
  
 不支持以下控件。  
  
|类名称|控件类型|  
|----------------|------------------|  
|SysAnimate32|映像|  
|SysPager|Spinner|  
|SysDateTimePick32|自定义|  
|SysMonthCal32|Calendar|  
|MS_WINNOTE|工具提示|  
|VBBubble|工具提示|  
|ScrollBar（在用作独立控件时）|滑块|  
|SuperGrid|自定义|  
  
<a name="Windows_Forms_Controls"></a>   
## <a name="windows-forms-controls"></a>Windows 窗体控件  
 通过 Uiautomationclientsideproviders.dll 中的客户端提供程序 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] 公开 Windows 窗体控件。 此程序集将自动注册，以用于 UI 自动化客户端应用程序。  
  
 通常，[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]支持作为 [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] 公共控件的托管包装的 Windows 窗体控件。 支持以下控件。  
  
|类名称|  
|----------------|  
|按钮|  
|CheckBox|  
|CheckedListBox|  
|ColorDialog|  
|组合框|  
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
|进度条|  
|RadioButton|  
|RichTextBox|  
|SaveFileDialog|  
|ScrollableControl|  
|SoundPlayer|  
|StatusBar|  
|TabControl/TabPage|  
|文本框|  
|计时器|  
|工具栏|  
|ToolTip|  
|TrackBar|  
|TreeView|  
|VscrollBar|  
|Web 浏览器|  
  
 以下控件仅通过其对 Microsoft Active Accessibility 的支持公开给 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)]。 某些功能可能不可用。  
  
|控件名称|  
|------------------|  
|BindingSource|  
|DataGrid|  
|DataGridView|  
|DataNavigator|  
|DomainUpDown|  
|ErrorProvider|  
|FlowLayoutPanel|  
|窗体|  
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
|拆分器|  
|RaftingContainer|  
|StatusStrip|  
  
## <a name="see-also"></a>另请参阅

- [UI Automation Control Types](ui-automation-control-types.md)
