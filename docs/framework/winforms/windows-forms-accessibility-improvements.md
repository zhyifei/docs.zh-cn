---
title: Windows 窗体辅助功能改进
description: 了解 .NET 核心 Windows 窗体尝试与 .NET 框架 Windows 窗体相比提高可访问性的方式。
ms.date: 04/20/2020
helpviewer_keywords:
- Windows Forms accessibility
- accessibility
author: M-Lipin
ms.openlocfilehash: 30eb8b3bd0aaf646ea23f4f036e822f9bba78dc4
ms.sourcegitcommit: 465547886a1224a5435c3ac349c805e39ce77706
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2020
ms.locfileid: "81739762"
---
# <a name="accessibility-improvements-in-windows-forms-controls-for-net-core-30"></a>.NET Core 3.0 的 Windows 窗体控件中的辅助功能改进

Windows 窗体正在继续改进其使用辅助功能技术的方式，以便更好地支持 Windows 窗体客户。 这些改进包括以下更改：

- 与辅助功能客户端应用程序（包括讲述人）交互的各个领域的更改。
- 辅助功能层次结构中的更改（通过 UI 自动化树改进导航）。
- 键盘导航中的更改。

> [!IMPORTANT]
> 在 .NET 框架 4.7.1 到 .NET 框架 4.8 中所做的辅助功能更改包含在 .NET Core 3.0 及以上，默认情况下已启用。 . NET 框架支持兼容换机，允许应用程序选择退出新的辅助功能行为。 另一方面，.NET Core 不支持这些设置，并且不允许应用程序选择退出辅助功能行为。
  
从 .NET Core 3.0 开始，Windows 窗体应用程序将受益于所有新的辅助功能（在 .NET 框架 4.7.1 - 4.8 中介绍），无需其他配置。

## <a name="listbox-accessibility-support"></a>列表框辅助功能支持

以下更改适用于<xref:System.Windows.Forms.ListBox>控件：

- 启用了用于`ListBox`控制的 UI 自动化支持。
- 通过将`ListBox`添加到<xref:System.Windows.Automation.ScrollItemPattern>`ListBox`项以及通过增强辅助功能事件筹集和处理以及通过项目进行讲述人导航（上限锁定导航不正确，并且不会无意中将导航扔到控件之外），从而改进了辅助功能支持。

## <a name="checkedlistbox-accessibility-support"></a>选中列表框辅助功能支持

以下更改适用于<xref:System.Windows.Forms.CheckedListBox>控件：

- 由条目`CheckedListBox`的辅助功能属性提供的更正边界。
- 改进了`ListBox`整体`CheckedListBox`和可访问性：更正了属性值和事件模型。

## <a name="combobox-accessibility-support"></a>组合盒辅助功能支持

以下更改适用于<xref:System.Windows.Forms.ComboBox>控件：

- 更新了获取`ComboBox`项的辅助对象以启用为项目生成 I 而不是从项获取哈希代码的过程，如果函数被覆盖，<xref:System.Object.GetHashCode%2A>这可能不安全。

## <a name="datagridview-accessibility-support"></a>数据网格视图辅助功能支持

以下更改适用于<xref:System.Windows.Forms.DataGridView>控件：

- 由列`DataGridView.Bounds`、行、单元格和相应标头的辅助功能属性更正，提高了边界矩形计算的性能。 考虑到整个控件的边界及其视口，将正确表示所有可访问边界。
- 为可`Value.IsReadOnly`访问的客户端应用程序提供更正的属性值。 该属性现在显示单元格`IsReadOnly`的正确状态。
- 修复了第一次<xref:System.Windows.Forms.DataGridView.CellParsing>单元格更改的事件引发问题。 单元格值可以更改，没有任何问题，包括第一`DataGridView`个控制交互。
- 使用`DataGridView`Windows 高对比度主题时，改进了背景颜色对比度。 使用`DataGridView`HC#1、HC+2 和 HC 黑色主题时更改默认回颜色。

## <a name="propertygrid-accessibility-support"></a>属性网格辅助功能支持

以下更改适用于<xref:System.Windows.Forms.PropertyGrid>控件：

- 网格`PropertyGrid.Bounds`条目的辅助功能属性已更正，提高了边界矩形计算的性能。 现在，考虑到整个控件的边界及其视口，所有可访问性边界都正确表示。
- 更正了辅助控件的可访问名称和说明，以不包含控件类型名称，并避免对控件类型名称进行双重通知。

## <a name="toolstrip-accessibility-support"></a>工具条辅助功能支持

以下更改适用于<xref:System.Windows.Forms.ToolStrip>控件：

- 改进了通过`ToolStrip``MenuStrip`和`StatusStrip`和 项的导航。 更正`ToolStrip`和`MenuStrip`移位选项卡导航，在按下移位选项卡上箭头时回循环菜单项，该箭头将导航到底部菜单元素。
- 改进`MenuStrip`了可访问导航、更正的菜单可访问控制类型，可为子菜单制作类型为"菜单"而不是"菜单项目"的子菜单。

## <a name="printpreviewcontrol-and-printpreviewdialog-accessibility-support"></a>打印预览控制和打印预览对话辅助功能支持

以下更改适用于打印控件：

- 通过菜单项改进了可访问导航（包括讲述人导航）。
- 改进了高对比度主题支持，使控制元素更加对比。

## <a name="stringcollectioneditor-accessibility-support"></a>字符串收集编辑器辅助功能支持

Windows 窗体设计器现在使用具有改进的辅助功能支持的字符串集合编辑器。

## <a name="monthcalendar-accessibility-support-available-in-net-core-31"></a>月历辅助功能支持（在 .NET 核心 3.1 中提供）

以下更改适用于<xref:System.Windows.Forms.MonthCalendar>控件：

- 添加了 UI 自动化服务器提供程序`MonthCalendar`来控制、添加了 UI 自动化网格模式和表模式提供程序。
- 更改_的表_可访问控件类型到_日历_可访问`MonthCalendar`控件类型，除非控件具有定义`MonthCalendar`控件可访问名称的上述标签控件的情况，在此特定情况下，可访问控件类型将成为_表_。
- 改进了所选控制日期的`MonthCalendar`公告。
- 改进`MonthCalendar`了对屏幕阅读器和其他辅助功能工具的控制支持。 此时，用户可以导航控件元素并使用仅键盘输入与这些元素进行交互。 使用"讲述人"，使用 CAPS + 箭头键通过控制元素导航，然后使用 CAPS = 输入以调用元素默认操作。
- 使用对焦矩形改进`MonthCalendar`了子元素的箭头键导航：讲述人的蓝色焦点矩形。
- 改进了控件元素命中测试操作`MonthCalendar`的可访问性，`MonthCalendar`以便通过提供的坐标获取子可访问元素。

## <a name="tooltips-accessibility-available-in-net-core-31"></a>工具提示辅助功能（在 .NET 核心 3.1 中提供）

- 增加了通过屏幕阅读器应用程序（如 NVDA 和讲述人）宣布工具提示文本的能力。 屏幕阅读器应用程序现在可以宣布任何 Windows 窗体控件的键盘或鼠标工具提示的文本，该控件配置为显示工具提示。

## <a name="ui-automation-support-for-datagridview-propertygrid-listbox-combobox-toolstrip-and-other-controls"></a>对 DataGridView、属性网格、列表框、组合盒、工具条和其他控件的 UI 自动化支持

在运行时为控件启用 UI 自动化支持，但在设计期间不使用。 有关 UI 自动化的概述，请参阅 [UI 自动化概述](https://docs.microsoft.com/dotnet/framework/ui-automation/ui-automation-overview)。

## <a name="see-also"></a>另请参阅

- [辅助功能最佳实践](../ui-automation/accessibility-best-practices.md)。
