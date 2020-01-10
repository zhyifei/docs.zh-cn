---
title: UI 自动化对标准控件的支持
ms.date: 03/30/2017
helpviewer_keywords:
- controls, UI Automation support for
- UI Automation, support for standard controls
ms.assetid: 3770ea8a-2655-4add-9c59-fe0610ad5084
ms.openlocfilehash: ed5e4f6ab23fe9ae77c94616a668da8accb46d4b
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2020
ms.locfileid: "75741702"
---
# <a name="ui-automation-support-for-standard-controls"></a>UI 自动化对标准控件的支持
> [!NOTE]
> 本文档适用于想要使用 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 命名空间中定义的托管 <xref:System.Windows.Automation> 类的 .NET Framework 开发人员。 有关 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]的最新信息，请参阅 [Windows 自动化 API：UI 自动化](/windows/win32/winauto/entry-uiauto-win32)。  
  
 本主题包含有关为 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)]、Win32 和 [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)] 框架开发的应用程序中的标准控件 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] 支持的信息。  
  
<a name="Windows_Presentation_Foundation_Controls"></a>   
## <a name="windows-presentation-foundation-controls"></a>Windows Presentation Foundation 控件  
 为用户交互提供信息或支持的所有 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 控件元素均具有对 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]的完整本机支持。 面板等其他元素对 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]不可见。  
  
<a name="Win32_Controls"></a>   
## <a name="win32-controls"></a>Win32 控件  
 大多数 Win32 控件都通过 Uiautomationclientsideproviders.dll 中的客户端提供程序公开 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)]。 此程序集将自动注册，以用于 UI 自动化客户端应用程序。  
  
 仅为*对 comctrl32.dll*版本6中的控件提供完全支持。  
  
 支持以下控件。  
  
|类名|控件类型|  
|----------------|------------------|  
|Button|Button|  
|Button|RadioButton|  
|Button|组|  
|Button|CheckBox|  
|Button|超链接|  
|Button|SplitButton|  
|Button|CheckBox|  
|ComboBoxEx32|组合框|  
|组合框|组合框|  
|Edit|文档|  
|Edit|Edit|  
|SysLink|超链接|  
|Static|文本|  
|Static|Image|  
|SysIPAddress32|“自定义”|  
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
|ScrollBar|Slider|  
|msctls_trackbar32|Slider|  
|msctls_updown32|Spinner|  
|msctls_statusbar32|StatusBar|  
|SysTabControl32|Tab|  
|SysTabControl32|TabItem|  
|ToolbarWindow32|ToolBar|  
|ToolbarWindow32|MenuItem|  
|ToolbarWindow32|Button|  
|ToolbarWindow32|CheckBox|  
|ToolbarWindow32|RadioButton|  
|ToolbarWindow32|Separator|  
|tooltips_class32|工具提示|  
|#32774|工具提示|  
|ReBarWindow32|ToolBar|  
|SysTreeView32|树|  
|SysTreeView32|TreeItem|  
  
 **注意**只有 Windows Vista 附带的版本（在 Riched20.dll 版本3.1 及更高版本以及 Msftedit.dll 版本4.1 及更高版本）支持 RichEdit 控件。  
  
 不支持以下控件。  
  
|类名|控件类型|  
|----------------|------------------|  
|SysAnimate32|Image|  
|SysPager|Spinner|  
|SysDateTimePick32|“自定义”|  
|SysMonthCal32|Calendar|  
|MS_WINNOTE|ToolTip|  
|VBBubble|ToolTip|  
|ScrollBar（在用作独立控件时）|Slider|  
|SuperGrid|“自定义”|  
  
<a name="Windows_Forms_Controls"></a>   
## <a name="windows-forms-controls"></a>Windows 窗体控件  
 通过 Uiautomationclientsideproviders.dll 中的客户端提供程序 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] 公开 Windows 窗体控件。 此程序集将自动注册，以用于 UI 自动化客户端应用程序。  
  
 通常，[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]支持作为 Win32 公共控件的托管包装 Windows 窗体控件。 支持以下控件。  
  
|类名称|  
|----------------|  
|Button|  
|CheckBox|  
|CheckedListBox|  
|ColorDialog|  
|组合框|  
|FolderBrowser|  
|FontDialog|  
|GroupBox|  
|HscrollBar|  
|ImageList|  
|标签|  
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
|ToolBar|  
|工具提示|  
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
