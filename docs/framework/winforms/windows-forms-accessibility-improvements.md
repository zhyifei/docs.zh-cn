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
# <a name="accessibility-improvements-in-windows-forms-controls-for-net-core-30"></a><span data-ttu-id="d9b06-103">.NET Core 3.0 的 Windows 窗体控件中的辅助功能改进</span><span class="sxs-lookup"><span data-stu-id="d9b06-103">Accessibility improvements in Windows Forms controls for .NET Core 3.0</span></span>

<span data-ttu-id="d9b06-104">Windows 窗体正在继续改进其使用辅助功能技术的方式，以便更好地支持 Windows 窗体客户。</span><span class="sxs-lookup"><span data-stu-id="d9b06-104">Windows Forms is continuing to improve how it works with accessibility technologies to better support Windows Forms customers.</span></span> <span data-ttu-id="d9b06-105">这些改进包括以下更改：</span><span class="sxs-lookup"><span data-stu-id="d9b06-105">These improvements include the following changes:</span></span>

- <span data-ttu-id="d9b06-106">与辅助功能客户端应用程序（包括讲述人）交互的各个领域的更改。</span><span class="sxs-lookup"><span data-stu-id="d9b06-106">Changes in various areas of interaction with accessibility client applications, including Narrator.</span></span>
- <span data-ttu-id="d9b06-107">辅助功能层次结构中的更改（通过 UI 自动化树改进导航）。</span><span class="sxs-lookup"><span data-stu-id="d9b06-107">Changes in the Accessible hierarchy (improving navigation through the UI Automation tree).</span></span>
- <span data-ttu-id="d9b06-108">键盘导航中的更改。</span><span class="sxs-lookup"><span data-stu-id="d9b06-108">Changes in keyboard navigation.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d9b06-109">在 .NET 框架 4.7.1 到 .NET 框架 4.8 中所做的辅助功能更改包含在 .NET Core 3.0 及以上，默认情况下已启用。</span><span class="sxs-lookup"><span data-stu-id="d9b06-109">Accessibility changes made in .NET Framework 4.7.1 through .NET Framework 4.8 are included in .NET Core 3.0 and above, and are enabled by default.</span></span> <span data-ttu-id="d9b06-110">. NET 框架支持兼容换机，允许应用程序选择退出新的辅助功能行为。</span><span class="sxs-lookup"><span data-stu-id="d9b06-110">The .NET Framework supported compatibility switches that allowed applications to opt out of the new accessibility behavior.</span></span> <span data-ttu-id="d9b06-111">另一方面，.NET Core 不支持这些设置，并且不允许应用程序选择退出辅助功能行为。</span><span class="sxs-lookup"><span data-stu-id="d9b06-111">On the other hand, .NET Core doesn't support these settings and doesn't allow applications to opt out of accessibility behavior.</span></span>
  
<span data-ttu-id="d9b06-112">从 .NET Core 3.0 开始，Windows 窗体应用程序将受益于所有新的辅助功能（在 .NET 框架 4.7.1 - 4.8 中介绍），无需其他配置。</span><span class="sxs-lookup"><span data-stu-id="d9b06-112">Starting with .NET Core 3.0, Windows Forms applications benefit from all the new accessibility features (introduced in .NET Framework 4.7.1 - 4.8) without additional configuration.</span></span>

## <a name="listbox-accessibility-support"></a><span data-ttu-id="d9b06-113">列表框辅助功能支持</span><span class="sxs-lookup"><span data-stu-id="d9b06-113">ListBox Accessibility support</span></span>

<span data-ttu-id="d9b06-114">以下更改适用于<xref:System.Windows.Forms.ListBox>控件：</span><span class="sxs-lookup"><span data-stu-id="d9b06-114">The following changes apply to the <xref:System.Windows.Forms.ListBox> control:</span></span>

- <span data-ttu-id="d9b06-115">启用了用于`ListBox`控制的 UI 自动化支持。</span><span class="sxs-lookup"><span data-stu-id="d9b06-115">Enabled UI Automation support for `ListBox` control.</span></span>
- <span data-ttu-id="d9b06-116">通过将`ListBox`添加到<xref:System.Windows.Automation.ScrollItemPattern>`ListBox`项以及通过增强辅助功能事件筹集和处理以及通过项目进行讲述人导航（上限锁定导航不正确，并且不会无意中将导航扔到控件之外），从而改进了辅助功能支持。</span><span class="sxs-lookup"><span data-stu-id="d9b06-116">Improved `ListBox` accessibility support by adding the <xref:System.Windows.Automation.ScrollItemPattern> to `ListBox` items and by enhancing the accessibility event raising and handling and Narrator navigation through the items (caps lock navigation isn't correct and doesn't throw the navigation outside the control unintentionally).</span></span>

## <a name="checkedlistbox-accessibility-support"></a><span data-ttu-id="d9b06-117">选中列表框辅助功能支持</span><span class="sxs-lookup"><span data-stu-id="d9b06-117">CheckedListBox Accessibility support</span></span>

<span data-ttu-id="d9b06-118">以下更改适用于<xref:System.Windows.Forms.CheckedListBox>控件：</span><span class="sxs-lookup"><span data-stu-id="d9b06-118">The following changes apply to the <xref:System.Windows.Forms.CheckedListBox> control:</span></span>

- <span data-ttu-id="d9b06-119">由条目`CheckedListBox`的辅助功能属性提供的更正边界。</span><span class="sxs-lookup"><span data-stu-id="d9b06-119">Corrected `CheckedListBox` Bounds provided by accessibility properties for entries.</span></span>
- <span data-ttu-id="d9b06-120">改进了`ListBox`整体`CheckedListBox`和可访问性：更正了属性值和事件模型。</span><span class="sxs-lookup"><span data-stu-id="d9b06-120">Improved overall `ListBox` and `CheckedListBox` accessibility: corrected property values and event model.</span></span>

## <a name="combobox-accessibility-support"></a><span data-ttu-id="d9b06-121">组合盒辅助功能支持</span><span class="sxs-lookup"><span data-stu-id="d9b06-121">ComboBox Accessibility support</span></span>

<span data-ttu-id="d9b06-122">以下更改适用于<xref:System.Windows.Forms.ComboBox>控件：</span><span class="sxs-lookup"><span data-stu-id="d9b06-122">The following changes apply to the <xref:System.Windows.Forms.ComboBox> control:</span></span>

- <span data-ttu-id="d9b06-123">更新了获取`ComboBox`项的辅助对象以启用为项目生成 I 而不是从项获取哈希代码的过程，如果函数被覆盖，<xref:System.Object.GetHashCode%2A>这可能不安全。</span><span class="sxs-lookup"><span data-stu-id="d9b06-123">Updated the process of getting `ComboBox` items' accessibility objects to enable generating IDs for items instead of getting hash codes from items, which may be unsafe in case the <xref:System.Object.GetHashCode%2A> function is overridden.</span></span>

## <a name="datagridview-accessibility-support"></a><span data-ttu-id="d9b06-124">数据网格视图辅助功能支持</span><span class="sxs-lookup"><span data-stu-id="d9b06-124">DataGridView Accessibility support</span></span>

<span data-ttu-id="d9b06-125">以下更改适用于<xref:System.Windows.Forms.DataGridView>控件：</span><span class="sxs-lookup"><span data-stu-id="d9b06-125">The following changes apply to the <xref:System.Windows.Forms.DataGridView> control:</span></span>

- <span data-ttu-id="d9b06-126">由列`DataGridView.Bounds`、行、单元格和相应标头的辅助功能属性更正，提高了边界矩形计算的性能。</span><span class="sxs-lookup"><span data-stu-id="d9b06-126">Corrected `DataGridView.Bounds` provided by accessibility properties for columns, rows, cells and corresponding headers, improved performance of bounding rectangle calculation.</span></span> <span data-ttu-id="d9b06-127">考虑到整个控件的边界及其视口，将正确表示所有可访问边界。</span><span class="sxs-lookup"><span data-stu-id="d9b06-127">All accessibility bounds are represented correctly taking into account the bounds of entire control, along with its viewport.</span></span>
- <span data-ttu-id="d9b06-128">为可`Value.IsReadOnly`访问的客户端应用程序提供更正的属性值。</span><span class="sxs-lookup"><span data-stu-id="d9b06-128">Corrected `Value.IsReadOnly` property value providing for accessible client applications.</span></span> <span data-ttu-id="d9b06-129">该属性现在显示单元格`IsReadOnly`的正确状态。</span><span class="sxs-lookup"><span data-stu-id="d9b06-129">The property now shows correct `IsReadOnly` status for cells.</span></span>
- <span data-ttu-id="d9b06-130">修复了第一次<xref:System.Windows.Forms.DataGridView.CellParsing>单元格更改的事件引发问题。</span><span class="sxs-lookup"><span data-stu-id="d9b06-130">Fixed the issue with <xref:System.Windows.Forms.DataGridView.CellParsing> event raising for the first cell change.</span></span> <span data-ttu-id="d9b06-131">单元格值可以更改，没有任何问题，包括第一`DataGridView`个控制交互。</span><span class="sxs-lookup"><span data-stu-id="d9b06-131">Cell value can be changed without any issues including the first `DataGridView` control interaction.</span></span>
- <span data-ttu-id="d9b06-132">使用`DataGridView`Windows 高对比度主题时，改进了背景颜色对比度。</span><span class="sxs-lookup"><span data-stu-id="d9b06-132">Improved `DataGridView` background color contrast when using Windows High Contrast themes.</span></span> <span data-ttu-id="d9b06-133">使用`DataGridView`HC#1、HC+2 和 HC 黑色主题时更改默认回颜色。</span><span class="sxs-lookup"><span data-stu-id="d9b06-133">Changed `DataGridView` default back color when using HC#1, HC#2, and HC Black themes.</span></span>

## <a name="propertygrid-accessibility-support"></a><span data-ttu-id="d9b06-134">属性网格辅助功能支持</span><span class="sxs-lookup"><span data-stu-id="d9b06-134">PropertyGrid Accessibility support</span></span>

<span data-ttu-id="d9b06-135">以下更改适用于<xref:System.Windows.Forms.PropertyGrid>控件：</span><span class="sxs-lookup"><span data-stu-id="d9b06-135">The following changes apply to the <xref:System.Windows.Forms.PropertyGrid> control:</span></span>

- <span data-ttu-id="d9b06-136">网格`PropertyGrid.Bounds`条目的辅助功能属性已更正，提高了边界矩形计算的性能。</span><span class="sxs-lookup"><span data-stu-id="d9b06-136">Corrected `PropertyGrid.Bounds` provided by accessibility properties for grid entries, improved performance of bounding rectangle calculation.</span></span> <span data-ttu-id="d9b06-137">现在，考虑到整个控件的边界及其视口，所有可访问性边界都正确表示。</span><span class="sxs-lookup"><span data-stu-id="d9b06-137">For now all accessibility bounds are represented correctly taking into account the bounds of entire control, along with its viewport.</span></span>
- <span data-ttu-id="d9b06-138">更正了辅助控件的可访问名称和说明，以不包含控件类型名称，并避免对控件类型名称进行双重通知。</span><span class="sxs-lookup"><span data-stu-id="d9b06-138">Corrected accessible names and descriptions of subcontrols to not include control type names and to avoid double announcement for control type names.</span></span>

## <a name="toolstrip-accessibility-support"></a><span data-ttu-id="d9b06-139">工具条辅助功能支持</span><span class="sxs-lookup"><span data-stu-id="d9b06-139">ToolStrip Accessibility support</span></span>

<span data-ttu-id="d9b06-140">以下更改适用于<xref:System.Windows.Forms.ToolStrip>控件：</span><span class="sxs-lookup"><span data-stu-id="d9b06-140">The following changes apply to the <xref:System.Windows.Forms.ToolStrip> control:</span></span>

- <span data-ttu-id="d9b06-141">改进了通过`ToolStrip``MenuStrip`和`StatusStrip`和 项的导航。</span><span class="sxs-lookup"><span data-stu-id="d9b06-141">Improved navigation through `ToolStrip`, `MenuStrip`, and `StatusStrip` items.</span></span> <span data-ttu-id="d9b06-142">更正`ToolStrip`和`MenuStrip`移位选项卡导航，在按下移位选项卡上箭头时回循环菜单项，该箭头将导航到底部菜单元素。</span><span class="sxs-lookup"><span data-stu-id="d9b06-142">Corrected `ToolStrip` and `MenuStrip` shift-tab navigation, back-looping the menu items when shift-tab up-arrow is pressed, which navigates to the bottom menu element.</span></span>
- <span data-ttu-id="d9b06-143">改进`MenuStrip`了可访问导航、更正的菜单可访问控制类型，可为子菜单制作类型为"菜单"而不是"菜单项目"的子菜单。</span><span class="sxs-lookup"><span data-stu-id="d9b06-143">Improved `MenuStrip` accessible navigation, corrected menu accessible control types for submenus to make submenus of type 'Menu' instead of 'MenuItem'.</span></span>

## <a name="printpreviewcontrol-and-printpreviewdialog-accessibility-support"></a><span data-ttu-id="d9b06-144">打印预览控制和打印预览对话辅助功能支持</span><span class="sxs-lookup"><span data-stu-id="d9b06-144">PrintPreviewControl and PrintPreviewDialog Accessibility support</span></span>

<span data-ttu-id="d9b06-145">以下更改适用于打印控件：</span><span class="sxs-lookup"><span data-stu-id="d9b06-145">The following changes apply to the print controls:</span></span>

- <span data-ttu-id="d9b06-146">通过菜单项改进了可访问导航（包括讲述人导航）。</span><span class="sxs-lookup"><span data-stu-id="d9b06-146">Improved accessible navigation (including Narrator navigation) through menu items.</span></span>
- <span data-ttu-id="d9b06-147">改进了高对比度主题支持，使控制元素更加对比。</span><span class="sxs-lookup"><span data-stu-id="d9b06-147">Improved High Contrast themes support and made the control element more contrasted.</span></span>

## <a name="stringcollectioneditor-accessibility-support"></a><span data-ttu-id="d9b06-148">字符串收集编辑器辅助功能支持</span><span class="sxs-lookup"><span data-stu-id="d9b06-148">StringCollectionEditor Accessibility support</span></span>

<span data-ttu-id="d9b06-149">Windows 窗体设计器现在使用具有改进的辅助功能支持的字符串集合编辑器。</span><span class="sxs-lookup"><span data-stu-id="d9b06-149">Windows Forms designer now uses the string collection editor with improved accessibility support.</span></span>

## <a name="monthcalendar-accessibility-support-available-in-net-core-31"></a><span data-ttu-id="d9b06-150">月历辅助功能支持（在 .NET 核心 3.1 中提供）</span><span class="sxs-lookup"><span data-stu-id="d9b06-150">MonthCalendar Accessibility support (available in .NET Core 3.1)</span></span>

<span data-ttu-id="d9b06-151">以下更改适用于<xref:System.Windows.Forms.MonthCalendar>控件：</span><span class="sxs-lookup"><span data-stu-id="d9b06-151">The following changes apply to the <xref:System.Windows.Forms.MonthCalendar> control:</span></span>

- <span data-ttu-id="d9b06-152">添加了 UI 自动化服务器提供程序`MonthCalendar`来控制、添加了 UI 自动化网格模式和表模式提供程序。</span><span class="sxs-lookup"><span data-stu-id="d9b06-152">Added UI Automation server providers to `MonthCalendar` control, added UI Automation Grid pattern and Table pattern providers.</span></span>
- <span data-ttu-id="d9b06-153">更改_的表_可访问控件类型到_日历_可访问`MonthCalendar`控件类型，除非控件具有定义`MonthCalendar`控件可访问名称的上述标签控件的情况，在此特定情况下，可访问控件类型将成为_表_。</span><span class="sxs-lookup"><span data-stu-id="d9b06-153">Changed _table_ accessible control type to _calendar_ accessible control type for `MonthCalendar` except the case when the control has a preceding label control that defines `MonthCalendar` control accessible name, in this specific case accessible control type becomes _table_.</span></span>
- <span data-ttu-id="d9b06-154">改进了所选控制日期的`MonthCalendar`公告。</span><span class="sxs-lookup"><span data-stu-id="d9b06-154">Improved announcement of selected date for `MonthCalendar` control.</span></span>
- <span data-ttu-id="d9b06-155">改进`MonthCalendar`了对屏幕阅读器和其他辅助功能工具的控制支持。</span><span class="sxs-lookup"><span data-stu-id="d9b06-155">Improved `MonthCalendar` control support for screen readers and other accessibility tools.</span></span> <span data-ttu-id="d9b06-156">此时，用户可以导航控件元素并使用仅键盘输入与这些元素进行交互。</span><span class="sxs-lookup"><span data-stu-id="d9b06-156">At this moment, users can navigate the control elements and interact with these elements using keyboard-only input.</span></span> <span data-ttu-id="d9b06-157">使用"讲述人"，使用 CAPS + 箭头键通过控制元素导航，然后使用 CAPS = 输入以调用元素默认操作。</span><span class="sxs-lookup"><span data-stu-id="d9b06-157">With Narrator, use CAPS + arrow keys to navigation through the control elements and CAPS + Enter to invoke element default action.</span></span>
- <span data-ttu-id="d9b06-158">使用对焦矩形改进`MonthCalendar`了子元素的箭头键导航：讲述人的蓝色焦点矩形。</span><span class="sxs-lookup"><span data-stu-id="d9b06-158">Improved arrow key navigation across `MonthCalendar` child elements with a focusing rectangle: blue focus rectangle for Narrator.</span></span>
- <span data-ttu-id="d9b06-159">改进了控件元素命中测试操作`MonthCalendar`的可访问性，`MonthCalendar`以便通过提供的坐标获取子可访问元素。</span><span class="sxs-lookup"><span data-stu-id="d9b06-159">Improved accessibility for hit test action for `MonthCalendar` control elements to allow getting `MonthCalendar` child accessible element by provided coordinates.</span></span>

## <a name="tooltips-accessibility-available-in-net-core-31"></a><span data-ttu-id="d9b06-160">工具提示辅助功能（在 .NET 核心 3.1 中提供）</span><span class="sxs-lookup"><span data-stu-id="d9b06-160">ToolTips accessibility (available in .NET Core 3.1)</span></span>

- <span data-ttu-id="d9b06-161">增加了通过屏幕阅读器应用程序（如 NVDA 和讲述人）宣布工具提示文本的能力。</span><span class="sxs-lookup"><span data-stu-id="d9b06-161">Added ability to announce a tooltip text by screen reader applications such as NVDA and Narrator.</span></span> <span data-ttu-id="d9b06-162">屏幕阅读器应用程序现在可以宣布任何 Windows 窗体控件的键盘或鼠标工具提示的文本，该控件配置为显示工具提示。</span><span class="sxs-lookup"><span data-stu-id="d9b06-162">Screen reader application can now announce the text of keyboard or mouse tooltip of any Windows Forms control that configured to show tooltips.</span></span>

## <a name="ui-automation-support-for-datagridview-propertygrid-listbox-combobox-toolstrip-and-other-controls"></a><span data-ttu-id="d9b06-163">对 DataGridView、属性网格、列表框、组合盒、工具条和其他控件的 UI 自动化支持</span><span class="sxs-lookup"><span data-stu-id="d9b06-163">UI automation support for DataGridView, PropertyGrid, ListBox, ComboBox, ToolStrip, and other controls</span></span>

<span data-ttu-id="d9b06-164">在运行时为控件启用 UI 自动化支持，但在设计期间不使用。</span><span class="sxs-lookup"><span data-stu-id="d9b06-164">UI Automation support is enabled for controls at runtime but isn't used during design time.</span></span> <span data-ttu-id="d9b06-165">有关 UI 自动化的概述，请参阅 [UI 自动化概述](https://docs.microsoft.com/dotnet/framework/ui-automation/ui-automation-overview)。</span><span class="sxs-lookup"><span data-stu-id="d9b06-165">For an overview of UI automation, see the [UI Automation Overview](https://docs.microsoft.com/dotnet/framework/ui-automation/ui-automation-overview).</span></span>

## <a name="see-also"></a><span data-ttu-id="d9b06-166">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d9b06-166">See also</span></span>

- <span data-ttu-id="d9b06-167">[辅助功能最佳实践](../ui-automation/accessibility-best-practices.md)。</span><span class="sxs-lookup"><span data-stu-id="d9b06-167">[Accessibility Best Practices](../ui-automation/accessibility-best-practices.md).</span></span>
