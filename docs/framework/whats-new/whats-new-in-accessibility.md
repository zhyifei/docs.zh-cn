---
title: .NET Framework 中辅助功能的新增功能
ms.custom: updateeachrelease
ms.date: 04/10/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- what's new [.NET Framework]
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 59fe1a5492b34d2aef88e81b86307498e3a5dc2c
ms.sourcegitcommit: 438919211260bb415fc8f96ca3eabc33cf2d681d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2019
ms.locfileid: "59612285"
---
# <a name="whats-new-in-accessibility-in-the-net-framework"></a><span data-ttu-id="efaba-102">.NET Framework 中辅助功能的新增功能</span><span class="sxs-lookup"><span data-stu-id="efaba-102">What's new in accessibility in the .NET Framework</span></span>

<span data-ttu-id="efaba-103">.NET Framework 旨在让用户更轻松地使用应用程序。</span><span class="sxs-lookup"><span data-stu-id="efaba-103">The .NET Framework aims at making applications more accessible for your users.</span></span> <span data-ttu-id="efaba-104">辅助功能使应用程序能够为辅助技术用户提供最佳体验。</span><span class="sxs-lookup"><span data-stu-id="efaba-104">Accessibility features allow an application to provide an appropriate experience for users of Assistive Technology.</span></span> <span data-ttu-id="efaba-105">从 .NET Framework 4.7.1 开始，.NET Framework 包括大量辅助功能改进，使开发人员能够创建易于访问的应用程序。</span><span class="sxs-lookup"><span data-stu-id="efaba-105">Starting with the .NET Framework 4.7.1, the .NET Framework includes a large number of accessibility improvements that allow developers to create accessible applications.</span></span>

## <a name="accessibility-switches"></a><span data-ttu-id="efaba-106">辅助功能开关</span><span class="sxs-lookup"><span data-stu-id="efaba-106">Accessibility switches</span></span>

<span data-ttu-id="efaba-107">如果应用面向 .NET Framework 4.7 或更低版本，但是在 .NET Framework 4.7.1 或更高版本上运行，可以将应用配置为选择使用辅助功能。</span><span class="sxs-lookup"><span data-stu-id="efaba-107">You can configure your app to opt into accessibility features if it targets the .NET Framework 4.7 or an earlier version but is running on the .NET Framework 4.7.1 or later.</span></span> <span data-ttu-id="efaba-108">如果应用面向 .NET Framework 4.7.1 或更高版本，还可以将应用配置为使用旧版功能（且不使用辅助功能）。</span><span class="sxs-lookup"><span data-stu-id="efaba-108">You can also configure your app to use legacy features (and not take advantage of accessibility features) if it targets the .NET Framework 4.7.1 or later.</span></span> <span data-ttu-id="efaba-109">包括辅助功能的每个 .NET Framework 版本都有一个特定于版本的辅助开关，请将它添加到应用程序配置文件 [`<runtime>`](~/docs/framework/configure-apps/file-schema/runtime/index.md) 部分中的 [`<AppContextSwitchOverrides>`](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) 元素。</span><span class="sxs-lookup"><span data-stu-id="efaba-109">Each version of the .NET Framework that includes accessibility features has a version-specific accessibility switch, which you add to the [`<AppContextSwitchOverrides>`](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) element in the [`<runtime>`](~/docs/framework/configure-apps/file-schema/runtime/index.md) section of the application's configuration file.</span></span> <span data-ttu-id="efaba-110">以下是受支持的开关：</span><span class="sxs-lookup"><span data-stu-id="efaba-110">The following are the supported switches:</span></span>

|<span data-ttu-id="efaba-111">Version</span><span class="sxs-lookup"><span data-stu-id="efaba-111">Version</span></span>|<span data-ttu-id="efaba-112">开关</span><span class="sxs-lookup"><span data-stu-id="efaba-112">Switch</span></span>|
|---|---|
|<span data-ttu-id="efaba-113">.NET Framework 4.7.1</span><span class="sxs-lookup"><span data-stu-id="efaba-113">.NET Framework 4.7.1</span></span>|<span data-ttu-id="efaba-114">"Switch.UseLegacyAccessibilityFeatures"</span><span class="sxs-lookup"><span data-stu-id="efaba-114">"Switch.UseLegacyAccessibilityFeatures"</span></span>|
|<span data-ttu-id="efaba-115">.NET Framework 4.7.2</span><span class="sxs-lookup"><span data-stu-id="efaba-115">.NET Framework 4.7.2</span></span>|<span data-ttu-id="efaba-116">"Switch.UseLegacyAccessibilityFeatures.2"</span><span class="sxs-lookup"><span data-stu-id="efaba-116">"Switch.UseLegacyAccessibilityFeatures.2"</span></span>|

### <a name="taking-advantage-of-accessibility-enhancements"></a><span data-ttu-id="efaba-117">利用辅助功能改进</span><span class="sxs-lookup"><span data-stu-id="efaba-117">Taking advantage of accessibility enhancements</span></span>

<span data-ttu-id="efaba-118">对于面向 .NET Framework 4.7.1 或更高版本的应用程序，新的辅助功能默认情况下处于启用状态。</span><span class="sxs-lookup"><span data-stu-id="efaba-118">The new accessibility features are enabled by default for applications that target the .NET Framework 4.7.1 or later.</span></span> <span data-ttu-id="efaba-119">此外，对于面向 .NET Framework 早期版本，但在 .NET Framework 4.7.1 或更高版本上运行的应用程序，可通过将开关添加到应用程序配置文件 [`<runtime>`](~/docs/framework/configure-apps/file-schema/runtime/index.md) 部分中的 [`<AppContextSwitchOverrides>`](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) 元素并将其值设为 `false` 来选择弃用旧辅助功能行为（因而利用辅助功能改进）。</span><span class="sxs-lookup"><span data-stu-id="efaba-119">In addition, applications that target an earlier version of the .NET Framework but are running on the .NET Framework 4.7.1 or later can opt out of legacy accessibility behaviors (and thereby take advantage of accessibility improvements) by adding switches to the [`<AppContextSwitchOverrides>`](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) element in the [`<runtime>`](~/docs/framework/configure-apps/file-schema/runtime/index.md) section of the application's configuration file and setting their value to `false`.</span></span> <span data-ttu-id="efaba-120">以下代码演示如何选择使用 .NET Framework 4.7.1 中引入的辅助功能改进：</span><span class="sxs-lookup"><span data-stu-id="efaba-120">The following shows how to opt in to accessibility enhancements introduced in the .NET Framework 4.7.1:</span></span>

```xml
<runtime>
    <!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true|false;key2=true|false  -->
    <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false" />
</runtime>
```

<span data-ttu-id="efaba-121">如果选择使用更高的 .NET Framework 版本中的辅助功能，还必须显式选择使用更低 .NET Framework 版本的功能。</span><span class="sxs-lookup"><span data-stu-id="efaba-121">If you choose to opt in to accessibility features in a later version of the .NET Framework, you must also explicitly opt in to the features from earlier versions of the .NET Framework.</span></span> <span data-ttu-id="efaba-122">将应用配置为利用 .NET Framework 4.7.1 和 4.7.2 中的辅助功能改进需要以下 [`<AppContextSwitchOverrides>`](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) 元素：</span><span class="sxs-lookup"><span data-stu-id="efaba-122">Configuring your app to take advantage of accessibility improvements in both the .NET Framework 4.7.1 and 4.7.2 requires the following [`<AppContextSwitchOverrides>`](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) element:</span></span>

```xml
<runtime>
    <!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true|false;key2=true|false  -->
    <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false;Switch.UseLegacyAccessibilityFeatures.2=false" />
</runtime>
```

### <a name="restoring-legacy-behavior"></a><span data-ttu-id="efaba-123">还原旧行为</span><span class="sxs-lookup"><span data-stu-id="efaba-123">Restoring legacy behavior</span></span>

<span data-ttu-id="efaba-124">对于面向 .NET Framework 4.7.1 或更高版本的应用程序，可通过将开关添加到应用程序配置文件 [`<runtime>`](~/docs/framework/configure-apps/file-schema/runtime/index.md) 部分中的 [`<AppContextSwitchOverrides>`](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) 元素并将其值设为 `true` 来禁用辅助功能。</span><span class="sxs-lookup"><span data-stu-id="efaba-124">Applications that target versions of the .NET Framework starting with 4.7.1 can disable accessibility features by adding switches to the [`<AppContextSwitchOverrides>`](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) element in the [`<runtime>`](~/docs/framework/configure-apps/file-schema/runtime/index.md) section of the application's configuration file and setting their value to `true`.</span></span> <span data-ttu-id="efaba-125">例如，以下配置选择弃用 .NET Framework 4.7.2 中引入的辅助功能：</span><span class="sxs-lookup"><span data-stu-id="efaba-125">For example, the following configuration opts out of accessibility features introduced in .NET Framework 4.7.2:</span></span>

```xml
<runtime>
    <!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true|false;key2=true|false  -->
    <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures.2=true" />
</runtime>
```

## <a name="whats-new-in-accessibility-in-the-net-framework-472"></a><span data-ttu-id="efaba-126">.NET Framework 4.7.2 中辅助功能的新增功能</span><span class="sxs-lookup"><span data-stu-id="efaba-126">What's new in accessibility in the .NET Framework 4.7.2</span></span>

<span data-ttu-id="efaba-127">.NET Framework 4.7.2 在以下几个领域新增了辅助功能：</span><span class="sxs-lookup"><span data-stu-id="efaba-127">The .NET Framework 4.7.2 includes new accessibility features in the following areas:</span></span>

- [<span data-ttu-id="efaba-128">Windows 窗体</span><span class="sxs-lookup"><span data-stu-id="efaba-128">Windows Forms</span></span>](#winforms472)

- [<span data-ttu-id="efaba-129">Windows Presentation Foundation (WPF)</span><span class="sxs-lookup"><span data-stu-id="efaba-129">Windows Presentation Foundation (WPF)</span></span>](#wpf472)

<a name="winforms472"></a>

### <a name="windows-forms"></a><span data-ttu-id="efaba-130">Windows 窗体</span><span class="sxs-lookup"><span data-stu-id="efaba-130">Windows Forms</span></span>

<span data-ttu-id="efaba-131">**高对比度主题中的 OS 定义的颜色**</span><span class="sxs-lookup"><span data-stu-id="efaba-131">**OS-defined colors in High Contrast themes**</span></span>

<span data-ttu-id="efaba-132">自 .NET Framework 4.7.2 起，Windows 窗体使用高对比度主题中的操作系统定义的颜色。</span><span class="sxs-lookup"><span data-stu-id="efaba-132">Starting with .NET Framework 4.7.2, Windows Forms uses colors defined by the operating system in High Contrast themes.</span></span> <span data-ttu-id="efaba-133">这会影响以下控件：</span><span class="sxs-lookup"><span data-stu-id="efaba-133">This affects the following controls:</span></span>

- <span data-ttu-id="efaba-134"><xref:System.Windows.Forms.ToolStripDropDownButton> 控件的下拉箭头。</span><span class="sxs-lookup"><span data-stu-id="efaba-134">The drop-down arrow of the <xref:System.Windows.Forms.ToolStripDropDownButton> control.</span></span>

- <span data-ttu-id="efaba-135"><xref:System.Windows.Forms.ButtonBase.FlatStyle> 设为 <xref:System.Windows.Forms.FlatStyle.Flat?displayProperty=nameWithType> 或 <xref:System.Windows.Forms.FlatStyle.Popup?displayProperty=nameWithType> 的 <xref:System.Windows.Forms.Button>、<xref:System.Windows.Forms.RadioButton> 和 <xref:System.Windows.Forms.CheckBox> 控件。</span><span class="sxs-lookup"><span data-stu-id="efaba-135">The <xref:System.Windows.Forms.Button>, <xref:System.Windows.Forms.RadioButton> and <xref:System.Windows.Forms.CheckBox> controls with <xref:System.Windows.Forms.ButtonBase.FlatStyle> set to <xref:System.Windows.Forms.FlatStyle.Flat?displayProperty=nameWithType> or <xref:System.Windows.Forms.FlatStyle.Popup?displayProperty=nameWithType>.</span></span> <span data-ttu-id="efaba-136">以前，所选文本和背景颜色对比度低，难以阅读。</span><span class="sxs-lookup"><span data-stu-id="efaba-136">Previously, selected text and background colors were not contrasting and were hard to read.</span></span>

- <span data-ttu-id="efaba-137"><xref:System.Windows.Forms.Control.Enabled> 属性设为 `false` 的 <xref:System.Windows.Forms.GroupBox> 中所包含的控件。</span><span class="sxs-lookup"><span data-stu-id="efaba-137">Controls contained within a <xref:System.Windows.Forms.GroupBox> that has its <xref:System.Windows.Forms.Control.Enabled> property set to `false`.</span></span>

- <span data-ttu-id="efaba-138">在高对比度模式下，<xref:System.Windows.Forms.ToolStripButton>、<xref:System.Windows.Forms.ToolStripComboBox> 和 <xref:System.Windows.Forms.ToolStripDropDownButton> 控件的亮度对比度提高。</span><span class="sxs-lookup"><span data-stu-id="efaba-138">The <xref:System.Windows.Forms.ToolStripButton>, <xref:System.Windows.Forms.ToolStripComboBox>, and <xref:System.Windows.Forms.ToolStripDropDownButton> controls, which have an increased luminosity contrast ratio in High Contrast Mode.</span></span>

- <span data-ttu-id="efaba-139"><xref:System.Windows.Forms.DataGridViewLinkCell> 的 <xref:System.Windows.Forms.DataGridViewLinkCell.LinkColor> 属性。</span><span class="sxs-lookup"><span data-stu-id="efaba-139">The <xref:System.Windows.Forms.DataGridViewLinkCell.LinkColor> property of the <xref:System.Windows.Forms.DataGridViewLinkCell>.</span></span>

<span data-ttu-id="efaba-140">**讲述人改进**</span><span class="sxs-lookup"><span data-stu-id="efaba-140">**Narrator improvements**</span></span>

<span data-ttu-id="efaba-141">自 .NET Framework 4.7.2 起，讲述人支持在以下几个方面改进：</span><span class="sxs-lookup"><span data-stu-id="efaba-141">Starting with the .NET Framework 4.7.2, Narrator support is enhanced as follows:</span></span>

- <span data-ttu-id="efaba-142">它在公布 <xref:System.Windows.Forms.ToolStripMenuItem> 的文本时会公布 <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys?displayProperty=nameWithType> 属性的值。</span><span class="sxs-lookup"><span data-stu-id="efaba-142">It announces the value of the <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys?displayProperty=nameWithType> property when announcing the text of a <xref:System.Windows.Forms.ToolStripMenuItem>.</span></span>

- <span data-ttu-id="efaba-143">当 <xref:System.Windows.Forms.ToolStripMenuItem> 的 <xref:System.Windows.Forms.Control.Enabled> 属性设置为 `false` 时，它会有所指示。</span><span class="sxs-lookup"><span data-stu-id="efaba-143">It indicates when a <xref:System.Windows.Forms.ToolStripMenuItem> has its <xref:System.Windows.Forms.Control.Enabled> property set to `false`.</span></span>

- <span data-ttu-id="efaba-144">当 <xref:System.Windows.Forms.ListView.CheckBoxes?displayProperty=nameWithType> 属性设置为 `true` 时，它会针对复选框的状态给出反馈。</span><span class="sxs-lookup"><span data-stu-id="efaba-144">It gives feedback on the state of a check box when the <xref:System.Windows.Forms.ListView.CheckBoxes?displayProperty=nameWithType> property is set to `true`.</span></span>

- <span data-ttu-id="efaba-145">讲述人扫描模式焦点顺序与 ClickOnce 下载对话框窗口中控件的视觉顺序一致。</span><span class="sxs-lookup"><span data-stu-id="efaba-145">Narrator's Scan Mode focus order is consistent with the visual order of the controls on the ClickOnce download dialog window.</span></span>

<span data-ttu-id="efaba-146">**DataGridView 改进**</span><span class="sxs-lookup"><span data-stu-id="efaba-146">**DataGridView improvements**</span></span>

<span data-ttu-id="efaba-147">自 .NET Framework 4.7.2 起，<xref:System.Windows.Forms.DataGridView> 控件引入了以下辅助功能改进：</span><span class="sxs-lookup"><span data-stu-id="efaba-147">Starting with the .NET Framework 4.7.2, the <xref:System.Windows.Forms.DataGridView> control has introduced the following accessibility improvements:</span></span>

- <span data-ttu-id="efaba-148">可以使用键盘对行进行排序。</span><span class="sxs-lookup"><span data-stu-id="efaba-148">Rows can be sorted using the keyboard.</span></span> <span data-ttu-id="efaba-149">用户可使用 F3 按当前列排序。</span><span class="sxs-lookup"><span data-stu-id="efaba-149">A user can use the F3 key in order to sort by the current column.</span></span>

- <span data-ttu-id="efaba-150">若 <xref:System.Windows.Forms.DataGridView.SelectionMode?displayProperty=nameWithType> 设置为 <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect?displayProperty=nameWithType>，当用户按 Tab 键遍历当前行中的单元格时，列标题将更改颜色来指示当前列。</span><span class="sxs-lookup"><span data-stu-id="efaba-150">When the <xref:System.Windows.Forms.DataGridView.SelectionMode?displayProperty=nameWithType> is set to <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect?displayProperty=nameWithType>, the column header changes color to indicate the current column as the user tabs through the cells in the current row.</span></span>

- <span data-ttu-id="efaba-151"><xref:System.Windows.Forms.DataGridViewLinkCell.DataGridViewLinkCellAccessibleObject?displayProperty=nameWithType> 的 <xref:System.Windows.Forms.AccessibleObject.Parent?displayProperty=nameWithType> 属性返回正确的父控件。</span><span class="sxs-lookup"><span data-stu-id="efaba-151">The <xref:System.Windows.Forms.AccessibleObject.Parent?displayProperty=nameWithType> property of a  <xref:System.Windows.Forms.DataGridViewLinkCell.DataGridViewLinkCellAccessibleObject?displayProperty=nameWithType> returns the correct parent control.</span></span>

<span data-ttu-id="efaba-152">**改进了视觉提示**</span><span class="sxs-lookup"><span data-stu-id="efaba-152">**Improved visual cues**</span></span>

- <span data-ttu-id="efaba-153">具有空 <xref:System.Windows.Forms.ButtonBase.Text> 属性的 <xref:System.Windows.Forms.RadioButton> 和 <xref:System.Windows.Forms.CheckBox> 控件在接收到焦点时会显示焦点指示器。</span><span class="sxs-lookup"><span data-stu-id="efaba-153">The <xref:System.Windows.Forms.RadioButton> and <xref:System.Windows.Forms.CheckBox> controls with an empty <xref:System.Windows.Forms.ButtonBase.Text> property  display a focus indicator when they receive the focus.</span></span>

<span data-ttu-id="efaba-154">**改进了属性网格支持**</span><span class="sxs-lookup"><span data-stu-id="efaba-154">**Improved Property Grid Support**</span></span>

- <span data-ttu-id="efaba-155">现在，仅在 PropertyGrid 元素启用时，<xref:System.Windows.Forms.PropertyGrid> 控件子元素才会为 <xref:System.Windows.Automation.ValuePattern.IsReadOnlyProperty> 属性返回 `true`。</span><span class="sxs-lookup"><span data-stu-id="efaba-155">The <xref:System.Windows.Forms.PropertyGrid> control child elements now return a `true` for the  <xref:System.Windows.Automation.ValuePattern.IsReadOnlyProperty> property only when a PropertyGrid element is enabled.</span></span>

- <span data-ttu-id="efaba-156">仅在用户可更改 PropertyGrid 元素时，<xref:System.Windows.Forms.PropertyGrid> 控件子元素才会为 <xref:System.Windows.Automation.AutomationElement.IsEnabledProperty> 属性返回 `false`。</span><span class="sxs-lookup"><span data-stu-id="efaba-156">The <xref:System.Windows.Forms.PropertyGrid> control child elements return a `false` for the <xref:System.Windows.Automation.AutomationElement.IsEnabledProperty> property only when a PropertyGrid element can be changed by the user.</span></span>

<span data-ttu-id="efaba-157">**改进了的键盘导航**</span><span class="sxs-lookup"><span data-stu-id="efaba-157">**Improved keyboard navigation**</span></span>

- <span data-ttu-id="efaba-158"><xref:System.Windows.Forms.ToolStripButton> 控件允许在焦点包含在 <xref:System.Windows.Forms.ToolStripPanel>（其 <xref:System.Windows.Forms.ToolStripPanel.TabStop> 属性设置为 `true`）中时进行聚焦</span><span class="sxs-lookup"><span data-stu-id="efaba-158">The <xref:System.Windows.Forms.ToolStripButton> control allows focus when contained within a <xref:System.Windows.Forms.ToolStripPanel> that has the <xref:System.Windows.Forms.ToolStripPanel.TabStop> property set to `true`</span></span>

<a name="wpf472"></a>

### <a name="windows-presentation-foundation-wpf"></a><span data-ttu-id="efaba-159">Windows Presentation Foundation (WPF)</span><span class="sxs-lookup"><span data-stu-id="efaba-159">Windows Presentation Foundation (WPF)</span></span>

<span data-ttu-id="efaba-160">**对复选框和单选按钮控件的更改**</span><span class="sxs-lookup"><span data-stu-id="efaba-160">**Changes to the CheckBox and RadioButton controls**</span></span>

<span data-ttu-id="efaba-161">在 .NET Framework 4.7.1 和更低版本中，WPF <xref:System.Windows.Controls.CheckBox?displayProperty=nameWIthType> 和 <xref:System.Windows.Controls.RadioButton?displayProperty=nameWIthType> 控件不一致且在经典和高对比度主题中具有不正确的焦点视觉对象。</span><span class="sxs-lookup"><span data-stu-id="efaba-161">In the .NET Framework 4.7.1 and earlier versions, the WPF <xref:System.Windows.Controls.CheckBox?displayProperty=nameWIthType> and <xref:System.Windows.Controls.RadioButton?displayProperty=nameWIthType> controls have inconsistent and, in Classic and High Contrast themes, incorrect focus visuals.</span></span>  <span data-ttu-id="efaba-162">控件没有内容集时会出现这些问题。</span><span class="sxs-lookup"><span data-stu-id="efaba-162">These issues occur in cases where the controls do not have any content set.</span></span>  <span data-ttu-id="efaba-163">这会使得主题间的转换变得混乱且难以看到焦点视觉对象。</span><span class="sxs-lookup"><span data-stu-id="efaba-163">This can make the transition between themes confusing and the focus visual hard to see.</span></span>

<span data-ttu-id="efaba-164">现在，在 .NET Framework 4.7.2 中，主题间的这些视觉对象更加一致，并且在经典和高对比度主题中更轻松可见。</span><span class="sxs-lookup"><span data-stu-id="efaba-164">In the .NET Framework 4.7.2, these visuals are now more consistent across themes and more easily visible in Classic and High Contrast themes.</span></span>

<span data-ttu-id="efaba-165">**在 WPF 应用程序中托管的 WinForms 控件**</span><span class="sxs-lookup"><span data-stu-id="efaba-165">**WinForms controls hosted in a WPF application**</span></span>

<span data-ttu-id="efaba-166">对于 .NET Framework 4.7.1 和更低版本中的 WPF 应用程序托管的 WinForms 控件，如果该层中的第一个或最后一个控件是 WPF <xref:System.Windows.Forms.Integration.ElementHost> 控件，那么用户不能按 Tab 退出 WinForms 层。</span><span class="sxs-lookup"><span data-stu-id="efaba-166">For WinForms control hosted in a WPF application in the .NET Framework 4.7.1 and earlier versions, users couldn't tab out of the WinForms layer if the first or last control in that layer is the WPF <xref:System.Windows.Forms.Integration.ElementHost> control.</span></span> <span data-ttu-id="efaba-167">现在，在 .NET Framework 4.7.2 中，用户能够按 Tab 退出 WinForms 层。</span><span class="sxs-lookup"><span data-stu-id="efaba-167">In the .NET Framework 4.7.2, users are now able to tab out of the WinForms layer.</span></span>

<span data-ttu-id="efaba-168">但是，依赖于永不转义 WinForms 层的焦点的自动化应用程序不再会按预期工作。</span><span class="sxs-lookup"><span data-stu-id="efaba-168">However, automated applications that rely on focus never escaping the WinForms layer may no longer work as expected.</span></span>

## <a name="whats-new-in-accessibility-in-the-net-framework-471"></a><span data-ttu-id="efaba-169">.NET Framework 4.7.1 中辅助功能的新增功能</span><span class="sxs-lookup"><span data-stu-id="efaba-169">What's new in accessibility in the .NET Framework 4.7.1</span></span>

<span data-ttu-id="efaba-170">.NET Framework 4.7.1 在以下几个领域新增了辅助功能：</span><span class="sxs-lookup"><span data-stu-id="efaba-170">The .NET Framework 4.7.1 includes new accessibility features in the following areas:</span></span>

- [<span data-ttu-id="efaba-171">Windows Presentation Foundation (WPF)</span><span class="sxs-lookup"><span data-stu-id="efaba-171">Windows Presentation Foundation (WPF)</span></span>](#wpf471)

- [<span data-ttu-id="efaba-172">Windows 窗体</span><span class="sxs-lookup"><span data-stu-id="efaba-172">Windows Forms</span></span>](#winforms471)

- [<span data-ttu-id="efaba-173">ASP.NET Web 控件</span><span class="sxs-lookup"><span data-stu-id="efaba-173">ASP.NET web controls</span></span>](#aspnet471)

- [<span data-ttu-id="efaba-174">.NET SDK 工具</span><span class="sxs-lookup"><span data-stu-id="efaba-174">.NET SDK Tools</span></span>](#tools471)

- [<span data-ttu-id="efaba-175">Windows Workflow Foundation (WF) 工作流设计器</span><span class="sxs-lookup"><span data-stu-id="efaba-175">Windows Workflow Foundation (WF) Workflow Designer</span></span>](#wf471)

<a name="wpf471"></a>

### <a name="windows-presentation-foundation-wpf"></a><span data-ttu-id="efaba-176">Windows Presentation Foundation (WPF)</span><span class="sxs-lookup"><span data-stu-id="efaba-176">Windows Presentation Foundation (WPF)</span></span>

<span data-ttu-id="efaba-177">**屏幕阅读器改进**</span><span class="sxs-lookup"><span data-stu-id="efaba-177">**Screen reader improvements**</span></span>

<span data-ttu-id="efaba-178">如果启用了辅助功能改进，.NET Framework 4.7.1 包括以下可影响屏幕读阅读的增强功能：</span><span class="sxs-lookup"><span data-stu-id="efaba-178">If accessibility improvements are enabled, the .NET Framework 4.7.1 includes the following enhancements that affect screen readers:</span></span>

- <span data-ttu-id="efaba-179">在 .NET Framework 4.7 及更低版本中，<xref:System.Windows.Controls.Expander> 控件由屏幕阅读器宣称为按钮。</span><span class="sxs-lookup"><span data-stu-id="efaba-179">In the .NET Framework 4.7 and earlier versions, <xref:System.Windows.Controls.Expander> controls were announced by screen readers as buttons.</span></span> <span data-ttu-id="efaba-180">从 .NET Framework 4.7.1 开始，它们被正确地称为可展开/可折叠组。</span><span class="sxs-lookup"><span data-stu-id="efaba-180">Starting with the .NET Framework 4.7.1, they are correctly announced as expandable/collapsible groups.</span></span>

- <span data-ttu-id="efaba-181">在 .NET Framework 4.7 及更低版本中，<xref:System.Windows.Controls.DataGridCell> 控件由屏幕阅读器宣称为“自定义”。</span><span class="sxs-lookup"><span data-stu-id="efaba-181">In the .NET Framework 4.7 and earlier versions, <xref:System.Windows.Controls.DataGridCell> controls were announced by screen readers as “custom.”</span></span> <span data-ttu-id="efaba-182">从 .NET Framework 4.7.1 开始，它们被正确地称为数据网格单元格（已本地化）。</span><span class="sxs-lookup"><span data-stu-id="efaba-182">Starting with the .NET Framework 4.7.1, they are now correctly announced as data grid cell (localized).</span></span>

- <span data-ttu-id="efaba-183">从 .NET Framework 4.7.1 开始，屏幕阅读器读出可编辑 <xref:System.Windows.Controls.ComboBox> 的名称。</span><span class="sxs-lookup"><span data-stu-id="efaba-183">Starting with the .NET Framework 4.7.1, screen readers announce the name of an editable <xref:System.Windows.Controls.ComboBox>.</span></span>

- <span data-ttu-id="efaba-184">在 .NET Framework 4.7 及更低版本中，<xref:System.Windows.Controls.PasswordBox> 控件被宣称为“视图中没有任何项”或有其他错误行为。</span><span class="sxs-lookup"><span data-stu-id="efaba-184">In the .NET Framework 4.7 and earlier versions, <xref:System.Windows.Controls.PasswordBox> controls were announced as “no item in view” or had otherwise incorrect behavior.</span></span> <span data-ttu-id="efaba-185">此问题已在 .NET Framework 4.7.1 及更高版本中解决。</span><span class="sxs-lookup"><span data-stu-id="efaba-185">This issue is fixed starting with the .NET Framework 4.7.1.</span></span>

<span data-ttu-id="efaba-186">**UIAutomation LiveRegion 支持**</span><span class="sxs-lookup"><span data-stu-id="efaba-186">**UIAutomation LiveRegion support**</span></span>

<span data-ttu-id="efaba-187">屏幕阅读器（如讲述人）可帮助用户阅读应用程序的 UI 内容，通常通过具有焦点的 UI 内容的文本到语音转换输出实现。</span><span class="sxs-lookup"><span data-stu-id="efaba-187">Screen readers such as Narrator help people read the UI contents of an application, usually by text-to-speech output of the UI content that has the focus.</span></span> <span data-ttu-id="efaba-188">但是，如果 UI 元素更改，并且不具有焦点，则用户可能不会收到通知，并且可能会错过重要信息。</span><span class="sxs-lookup"><span data-stu-id="efaba-188">However, if a UI element changes and does not have the focus, the user may not be notified and may miss important information.</span></span> <span data-ttu-id="efaba-189">活动区域旨在解决此问题。</span><span class="sxs-lookup"><span data-stu-id="efaba-189">Live regions aim at solving this problem.</span></span> <span data-ttu-id="efaba-190">开发人员可使用它们来通知屏幕阅读器或任何其他 UIAutomation 客户端 UI 元素有重要更改。</span><span class="sxs-lookup"><span data-stu-id="efaba-190">A developer can use them to inform the screen reader or any other UIAutomation client that an important change has been made to a UI element.</span></span> <span data-ttu-id="efaba-191">然后，屏幕阅读器可确定向用户通知此更改的方式和时间。</span><span class="sxs-lookup"><span data-stu-id="efaba-191">The screen reader can then decide how and when to inform the user of this change.</span></span>

<span data-ttu-id="efaba-192">为了支持活动区域，向 WPF 添加了以下 API：</span><span class="sxs-lookup"><span data-stu-id="efaba-192">To support live regions, the following APIs have been added to WPF:</span></span>

- <span data-ttu-id="efaba-193"><xref:System.Windows.Automation.AutomationElementIdentifiers.LiveSettingProperty?displayProperty=nameWithType> 和 <xref:System.Windows.Automation.AutomationElementIdentifiers.LiveRegionChangedEvent?displayProperty=nameWithType> 字段，用于标识 LiveSetting 属性和 LiveRegionChanged 事件。</span><span class="sxs-lookup"><span data-stu-id="efaba-193">The <xref:System.Windows.Automation.AutomationElementIdentifiers.LiveSettingProperty?displayProperty=nameWithType> and <xref:System.Windows.Automation.AutomationElementIdentifiers.LiveRegionChangedEvent?displayProperty=nameWithType> fields, which identify the **LiveSetting** property and the **LiveRegionChanged** event.</span></span> <span data-ttu-id="efaba-194">可通过使用 XAML 来进行设置。</span><span class="sxs-lookup"><span data-stu-id="efaba-194">They can be set by using XAML.</span></span>

- <span data-ttu-id="efaba-195">AutomationProperties.LiveSetting 附加属性，用于向屏幕阅读器通知 UI 更改对用户的重要性。</span><span class="sxs-lookup"><span data-stu-id="efaba-195">The **AutomationProperties.LiveSetting** attached property, which informs the screen reader of the importance of the UI change to the user.</span></span>

- <span data-ttu-id="efaba-196"><xref:System.Windows.Automation.AutomationProperties.LiveSettingProperty?displayProperty=nameWithType> 属性，用于标识 AutomationProperties.LiveSetting 附加属性。</span><span class="sxs-lookup"><span data-stu-id="efaba-196">The <xref:System.Windows.Automation.AutomationProperties.LiveSettingProperty?displayProperty=nameWithType> property, which identifies the **AutomationProperties.LiveSetting** attached property.</span></span>

- <span data-ttu-id="efaba-197"><xref:System.Windows.Automation.Peers.AutomationPeer.GetLiveSettingCore%2A?displayProperty=nameWithType> 方法，可替代该方法以提供 LiveSetting 值。</span><span class="sxs-lookup"><span data-stu-id="efaba-197">The <xref:System.Windows.Automation.Peers.AutomationPeer.GetLiveSettingCore%2A?displayProperty=nameWithType> method, which can be overridden to provide a **LiveSetting** value.</span></span>

- <span data-ttu-id="efaba-198"><xref:System.Windows.Automation.AutomationProperties.GetLiveSetting%2A?displayProperty=nameWithType> 和 <xref:System.Windows.Automation.AutomationProperties.SetLiveSetting%2A?displayProperty=nameWithType> 方法，用于获取和设置 LiveSetting 值。</span><span class="sxs-lookup"><span data-stu-id="efaba-198">The <xref:System.Windows.Automation.AutomationProperties.GetLiveSetting%2A?displayProperty=nameWithType> and <xref:System.Windows.Automation.AutomationProperties.SetLiveSetting%2A?displayProperty=nameWithType> methods, which get and set a **LiveSetting** value.</span></span>

- <span data-ttu-id="efaba-199"><xref:System.Windows.Automation.AutomationLiveSetting?displayProperty=nameWithType> 枚举，用于定义以下可能的 LiveSetting 值：</span><span class="sxs-lookup"><span data-stu-id="efaba-199">The <xref:System.Windows.Automation.AutomationLiveSetting?displayProperty=nameWithType> enumeration, which defines the following possible **LiveSetting** values:</span></span>

   - <span data-ttu-id="efaba-200"><xref:System.Windows.Automation.AutomationLiveSetting.Off?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="efaba-200"><xref:System.Windows.Automation.AutomationLiveSetting.Off?displayProperty=nameWithType>.</span></span> <span data-ttu-id="efaba-201">如果活动区域的内容已更改，则该元素不会发送通知。</span><span class="sxs-lookup"><span data-stu-id="efaba-201">The element does not send notifications if the content of the live region has changed.</span></span>
   - <span data-ttu-id="efaba-202"><xref:System.Windows.Automation.AutomationLiveSetting.Polite?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="efaba-202"><xref:System.Windows.Automation.AutomationLiveSetting.Polite?displayProperty=nameWithType>.</span></span> <span data-ttu-id="efaba-203">如果活动区域的内容已更改，则该元素将发送非中断通知。</span><span class="sxs-lookup"><span data-stu-id="efaba-203">The element sends non-interruptive notifications if the content of the live region has changed.</span></span>

   - <span data-ttu-id="efaba-204"><xref:System.Windows.Automation.AutomationLiveSetting.Assertive?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="efaba-204"><xref:System.Windows.Automation.AutomationLiveSetting.Assertive?displayProperty=nameWithType>.</span></span> <span data-ttu-id="efaba-205">如果活动区域的内容已更改，则该元素将发送中断通知。</span><span class="sxs-lookup"><span data-stu-id="efaba-205">The element sends interruptive notifications if the content of the live region has changed.</span></span>

<span data-ttu-id="efaba-206">可通过对相关元素设置 AutomationProperties.LiveSetting 属性来创建 LiveRegion，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="efaba-206">You can create a LiveRegion by setting the **AutomationProperties.LiveSetting** property on the element of interest, as shown in the following example:</span></span>

```xaml
<TextBlock Name="myTextBlock" AutomationProperties.LiveSetting="Assertive">announcement</TextBlock>
```

<span data-ttu-id="efaba-207">活动区域中的数据发生更改，并且需要通知屏幕阅读器时，可显式引发事件，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="efaba-207">When the data in the live region changes and you need to inform a screen reader, you explicitly raise an event, as shown in the following sample.</span></span>

```csharp
var peer = FrameworkElementAutomationPeer.FromElement(myTextBlock);

peer.RaiseAutomationEvent(AutomationEvents.LiveRegionChanged);
```

```vb
Dim peer = FrameworkElementAutomationPeer.FromElement(myTextBlock)
peer.RaiseAutomationEvent(AutomationEvents.LiveRegionChanged)

```

<span data-ttu-id="efaba-208">**高对比度**</span><span class="sxs-lookup"><span data-stu-id="efaba-208">**High contrast**</span></span>

<span data-ttu-id="efaba-209">从 .NET Framework 4.7.1 开始，对多种 WPF 控件进行了高对比度改进。</span><span class="sxs-lookup"><span data-stu-id="efaba-209">Starting with the .NET Framework 4.7.1, improvements in high contrast have been made to various WPF controls.</span></span> <span data-ttu-id="efaba-210">可在设置 <xref:System.Windows.SystemParameters.HighContrast%2A> 主题后看到这些改进。</span><span class="sxs-lookup"><span data-stu-id="efaba-210">They are now visible when the <xref:System.Windows.SystemParameters.HighContrast%2A> theme is set.</span></span> <span data-ttu-id="efaba-211">这些方法包括：</span><span class="sxs-lookup"><span data-stu-id="efaba-211">These include:</span></span>

- <span data-ttu-id="efaba-212"><xref:System.Windows.Controls.Expander> 控件</span><span class="sxs-lookup"><span data-stu-id="efaba-212"><xref:System.Windows.Controls.Expander> control</span></span>

    <span data-ttu-id="efaba-213"><xref:System.Windows.Controls.Expander> 控件的焦点视觉对象现在可见。</span><span class="sxs-lookup"><span data-stu-id="efaba-213">The focus visual for the  <xref:System.Windows.Controls.Expander> control is now visible.</span></span> <span data-ttu-id="efaba-214"><xref:System.Windows.Controls.ComboBox>、<xref:System.Windows.Controls.ListBox> 和 <xref:System.Windows.Controls.RadioButton> 控件的键盘视觉对象也可见。</span><span class="sxs-lookup"><span data-stu-id="efaba-214">The keyboard visuals for <xref:System.Windows.Controls.ComboBox>,<xref:System.Windows.Controls.ListBox>, and <xref:System.Windows.Controls.RadioButton> controls are visible as well.</span></span> <span data-ttu-id="efaba-215">例如:</span><span class="sxs-lookup"><span data-stu-id="efaba-215">For example:</span></span>

    <span data-ttu-id="efaba-216">在此之前:</span><span class="sxs-lookup"><span data-stu-id="efaba-216">Before:</span></span> 

    ![辅助功能改进前具有焦点的 Expander 控件](media/expander-before.png)

    <span data-ttu-id="efaba-218">之后：</span><span class="sxs-lookup"><span data-stu-id="efaba-218">After:</span></span> 

    ![辅助功能改进后具有焦点的 Expander 控件](media/expander-after.png)

- <span data-ttu-id="efaba-220"><xref:System.Windows.Controls.CheckBox> 和 <xref:System.Windows.Controls.RadioButton> 控件</span><span class="sxs-lookup"><span data-stu-id="efaba-220"><xref:System.Windows.Controls.CheckBox> and <xref:System.Windows.Controls.RadioButton> controls</span></span>

    <span data-ttu-id="efaba-221">在高对比度主题下选中时，<xref:System.Windows.Controls.CheckBox> 和 <xref:System.Windows.Controls.RadioButton> 控件中的文本更易于查看。</span><span class="sxs-lookup"><span data-stu-id="efaba-221">The text in the <xref:System.Windows.Controls.CheckBox> and <xref:System.Windows.Controls.RadioButton> controls is now easier to see when selected in high contrast themes.</span></span> <span data-ttu-id="efaba-222">例如:</span><span class="sxs-lookup"><span data-stu-id="efaba-222">For example:</span></span>

    <span data-ttu-id="efaba-223">在此之前:</span><span class="sxs-lookup"><span data-stu-id="efaba-223">Before:</span></span> 

    ![辅助功能改进前具有焦点的高对比度单选按钮](media/radio-button-before.png)

    <span data-ttu-id="efaba-225">之后：</span><span class="sxs-lookup"><span data-stu-id="efaba-225">After:</span></span> 

    ![辅助功能改进后具有焦点的高对比度单选按钮](media/radio-button-after.png)

- <span data-ttu-id="efaba-227"><xref:System.Windows.Controls.ComboBox> 控件</span><span class="sxs-lookup"><span data-stu-id="efaba-227"><xref:System.Windows.Controls.ComboBox> control</span></span>

    <span data-ttu-id="efaba-228">从 .NET Framework 4.7.1 开始，已禁用的 <xref:System.Windows.Controls.ComboBox> 控件的边框与禁用的文本颜色相同。</span><span class="sxs-lookup"><span data-stu-id="efaba-228">Starting with the .NET Framework 4.7.1, the border of a disabled <xref:System.Windows.Controls.ComboBox> control is the same color as disabled text.</span></span> <span data-ttu-id="efaba-229">例如:</span><span class="sxs-lookup"><span data-stu-id="efaba-229">For example:</span></span>

    <span data-ttu-id="efaba-230">在此之前:</span><span class="sxs-lookup"><span data-stu-id="efaba-230">Before:</span></span> 

     ![辅助功能改进前禁用的 ComboBox 边框和文本](media/combo-disabled-before.png)

    <span data-ttu-id="efaba-232">之后：</span><span class="sxs-lookup"><span data-stu-id="efaba-232">After:</span></span>   

     ![辅助功能改进后禁用的 ComboBox 边框和文本](media/combo-disabled-after.png)

    <span data-ttu-id="efaba-234">此外，已禁用的按钮和具有焦点的按钮使用正确的主题颜色。</span><span class="sxs-lookup"><span data-stu-id="efaba-234">In addition, disabled and focused buttons use the correct theme color.</span></span>

    <span data-ttu-id="efaba-235">在此之前:</span><span class="sxs-lookup"><span data-stu-id="efaba-235">Before:</span></span>

    ![辅助功能改进前的按钮主题颜色](media/button-themes-before.png) 

    <span data-ttu-id="efaba-237">之后：</span><span class="sxs-lookup"><span data-stu-id="efaba-237">After:</span></span> 

    ![辅助功能改进后的按钮主题颜色](media/button-themes-after.png) 

    <span data-ttu-id="efaba-239">最后，在 .NET Framework 4.7 及更低版本中，将 <xref:System.Windows.Controls.ComboBox> 控件的样式设置为 `Toolbar.ComboBoxStyleKey` 会导致下拉箭头不可见。</span><span class="sxs-lookup"><span data-stu-id="efaba-239">Finally, in the .NET Framework 4.7 and earlier versions, setting a <xref:System.Windows.Controls.ComboBox> control’s style to `Toolbar.ComboBoxStyleKey` caused the drop-down arrow to be invisible.</span></span> <span data-ttu-id="efaba-240">此问题已在 .NET Framework 4.7.1 及更高版本中解决。</span><span class="sxs-lookup"><span data-stu-id="efaba-240">This issue is fixed starting with the .NET Framework 4.7.1.</span></span> <span data-ttu-id="efaba-241">例如:</span><span class="sxs-lookup"><span data-stu-id="efaba-241">For example:</span></span>

    <span data-ttu-id="efaba-242">在此之前:</span><span class="sxs-lookup"><span data-stu-id="efaba-242">Before:</span></span> 

    ![辅助功能改进前的 Toolbar.ComboBoxStyleKey](media/comboboxstylekey-before.png) 

    <span data-ttu-id="efaba-244">之后：</span><span class="sxs-lookup"><span data-stu-id="efaba-244">After:</span></span> 

    ![辅助功能改进后的 Toolbar.ComboBoxStyleKey](media/comboboxstylekey-after.png) 

- <span data-ttu-id="efaba-246"><xref:System.Windows.Controls.DataGrid> 控件</span><span class="sxs-lookup"><span data-stu-id="efaba-246"><xref:System.Windows.Controls.DataGrid> control</span></span>

    <span data-ttu-id="efaba-247">从 .NET Framework 4.7.1 开始，<xref:System.Windows.Controls.DataGrid> 控件中的排序指示符箭头现在使用正确的主题颜色。</span><span class="sxs-lookup"><span data-stu-id="efaba-247">Starting with the .NET Framework 4.7.1, the sort indicator arrow in <xref:System.Windows.Controls.DataGrid> controls now uses correct theme colors.</span></span> <span data-ttu-id="efaba-248">例如:</span><span class="sxs-lookup"><span data-stu-id="efaba-248">For example:</span></span>

    <span data-ttu-id="efaba-249">在此之前:</span><span class="sxs-lookup"><span data-stu-id="efaba-249">Before:</span></span> 

    ![辅助功能改进前的排序指示符箭头](media/sort-indicator-before.png) 

    <span data-ttu-id="efaba-251">之后：</span><span class="sxs-lookup"><span data-stu-id="efaba-251">After:</span></span>   

    ![辅助功能改进后的排序指示符箭头](media/sort-indicator-after.png) 

    <span data-ttu-id="efaba-253">此外，在 .NET Framework 4.7 及更低版本中，在高对比度模式下，默认链接样式在鼠标悬停在其上时更改为不正确的颜色。</span><span class="sxs-lookup"><span data-stu-id="efaba-253">In addition, in the .NET Framework 4.7 and earlier versions, the default link style changed to an incorrect color on mouse over in high contrast modes.</span></span> <span data-ttu-id="efaba-254">此问题已在 .NET Framework 4.7.1 及更高版本中解决。</span><span class="sxs-lookup"><span data-stu-id="efaba-254">This is resolved starting with the .NET Framework 4.7.1.</span></span> <span data-ttu-id="efaba-255">同样，从 .NET Framework 4.7.1 开始，<xref:System.Windows.Controls.DataGrid> 复选框列对键盘焦点反馈使用预期的颜色。</span><span class="sxs-lookup"><span data-stu-id="efaba-255">Similarly, <xref:System.Windows.Controls.DataGrid> checkbox columns uses the expected colors for keyboard focus feedback starting with the .NET Framework 4.7.1.</span></span>

    <span data-ttu-id="efaba-256">在此之前:</span><span class="sxs-lookup"><span data-stu-id="efaba-256">Before:</span></span> 

    ![辅助功能改进前的 DataGrid 默认链接样式](media/default-link-style-before.png) 

    <span data-ttu-id="efaba-258">之后：</span><span class="sxs-lookup"><span data-stu-id="efaba-258">After:</span></span>    

    ![辅助功能改进后的 DataGrid 默认链接样式](media/default-link-style-after.png) 

<span data-ttu-id="efaba-260">有关 .NET Framework 4.7.1 中 WPF 辅助功能改进的详细信息，请参阅 [WPF 辅助功能改进](../migration-guide/retargeting/4.7-4.7.1.md#accessibility-improvements-in-wpf)。</span><span class="sxs-lookup"><span data-stu-id="efaba-260">For more information on WPF accessibility improvements in the .NET Framework 4.7.1, see [Accessibility improvements in WPF](../migration-guide/retargeting/4.7-4.7.1.md#accessibility-improvements-in-wpf).</span></span>

<a name="winforms471"></a>

### <a name="windows-forms-accessibility-improvements"></a><span data-ttu-id="efaba-261">Windows 窗体辅助功能改进</span><span class="sxs-lookup"><span data-stu-id="efaba-261">Windows Forms accessibility improvements</span></span>

<span data-ttu-id="efaba-262">在 .NET Framework 4.7.1 中，Windows 窗体 (WinForms) 包括以下几个方面的辅助功能改进。</span><span class="sxs-lookup"><span data-stu-id="efaba-262">In the .NET Framework 4.7.1, Windows Forms (WinForms) includes accessibility changes in the following areas.</span></span>

<span data-ttu-id="efaba-263">**改进了高对比度模式下的显示**</span><span class="sxs-lookup"><span data-stu-id="efaba-263">**Improved display in High Contrast mode**</span></span>

<span data-ttu-id="efaba-264">从 .NET Framework 4.7.1 开始，多种 WinForms 控件改进了高对比度模式下在操作系统中的呈现方式。</span><span class="sxs-lookup"><span data-stu-id="efaba-264">Starting with the .NET Framework 4.7.1, various WinForms controls offer improved rendering in the HighContrast modes available in the operating system.</span></span> <span data-ttu-id="efaba-265">Windows 10 更改了一些高对比度系统颜色的值，而 Windows 窗体基于 Windows 10 Win32 框架。</span><span class="sxs-lookup"><span data-stu-id="efaba-265">Windows 10 has changed the values for some high contrast system colors, and Windows Forms is based on the Windows 10 Win32 framework.</span></span> <span data-ttu-id="efaba-266">为获得最佳体验，请运行最新版本的 Windows，并通过在测试应用程序中添加 app.manifest 文件选择使用最新的 OS 更改，同时取消注释 Windows 10 支持的 OS 行，最终结果如下所示：</span><span class="sxs-lookup"><span data-stu-id="efaba-266">For the best experience, run on the latest version of Windows and opt in to the latest OS changes by adding an app.manifest file in a test application and un-comment the Windows 10 supported OS  line so that it looks the following:</span></span>

```xml
<!-- Windows 10 -->
<supportedOS Id=”{8e0f7a12-bfb3-4fe8-b9a5-48fd50a15a9a}” />
```

<span data-ttu-id="efaba-267">高对比度更改的一些示例包括：</span><span class="sxs-lookup"><span data-stu-id="efaba-267">Some examples of high contrast changes include:</span></span>

- <span data-ttu-id="efaba-268"><xref:System.Windows.Forms.MenuStrip> 项中的复选标记更易于查看。</span><span class="sxs-lookup"><span data-stu-id="efaba-268">Checkmarks in <xref:System.Windows.Forms.MenuStrip> items are easier to view.</span></span>

- <span data-ttu-id="efaba-269">选中后，禁用的 <xref:System.Windows.Forms.MenuStrip> 项更易于查看。</span><span class="sxs-lookup"><span data-stu-id="efaba-269">When selected, disabled <xref:System.Windows.Forms.MenuStrip> items are easier to view.</span></span>

- <span data-ttu-id="efaba-270">所选 <xref:System.Windows.Forms.Button> 控件中的文本与选中颜色形成鲜明对比。</span><span class="sxs-lookup"><span data-stu-id="efaba-270">Text in a selected <xref:System.Windows.Forms.Button> control contrasts with the selection color.</span></span>

- <span data-ttu-id="efaba-271">禁用的文本更易于阅读。</span><span class="sxs-lookup"><span data-stu-id="efaba-271">Disabled text is easier to read.</span></span> <span data-ttu-id="efaba-272">例如:</span><span class="sxs-lookup"><span data-stu-id="efaba-272">For example:</span></span>

    <span data-ttu-id="efaba-273">在此之前:</span><span class="sxs-lookup"><span data-stu-id="efaba-273">Before:</span></span>

    ![辅助功能改进前禁用的文本](media/wf-disabled-before.png) 

    <span data-ttu-id="efaba-275">之后：</span><span class="sxs-lookup"><span data-stu-id="efaba-275">After:</span></span>

    ![辅助功能改进后禁用的文本](media/wf-disabled-after.png) 

- <span data-ttu-id="efaba-277">“线程异常”对话框中的高对比度改进。</span><span class="sxs-lookup"><span data-stu-id="efaba-277">High contrast improvements in the Thread Exception Dialog.</span></span>

<span data-ttu-id="efaba-278">**改进了讲述人支持**</span><span class="sxs-lookup"><span data-stu-id="efaba-278">**Improved Narrator support**</span></span>

<span data-ttu-id="efaba-279">.NET Framework 4.7.1 中的 Windows 窗体对讲述人进行了以下辅助功改进：</span><span class="sxs-lookup"><span data-stu-id="efaba-279">Windows Forms in the .NET Framework 4.7.1 includes the following accessibility improvements for the Narrator:</span></span>

- <span data-ttu-id="efaba-280">讲述人以及其他 UI 自动化工具可访问 <xref:System.Windows.Forms.MonthCalendar> 控件。</span><span class="sxs-lookup"><span data-stu-id="efaba-280">The <xref:System.Windows.Forms.MonthCalendar> control can be accessed by the Narrator, as well as by other UI automation tools.</span></span>

- <span data-ttu-id="efaba-281">当某个项的选中状态更改时，<xref:System.Windows.Forms.CheckedListBox> 控件会通知讲述人，因此用户可获知更改了列表项的值。</span><span class="sxs-lookup"><span data-stu-id="efaba-281">The <xref:System.Windows.Forms.CheckedListBox> control notifies Narrator when an item's check state has changed so the user is notified that they’ve changed the value of a list item.</span></span>

- <span data-ttu-id="efaba-282"><xref:System.Windows.Forms.DataGridViewCell> 控件向讲述人报告正确的只读状态。</span><span class="sxs-lookup"><span data-stu-id="efaba-282">The <xref:System.Windows.Forms.DataGridViewCell> control reports the correct read-only status to Narrator.</span></span>

- <span data-ttu-id="efaba-283">讲述人现在可以阅读已禁用的 <xref:System.Windows.Forms.ToolStripMenuItem> 文本，而以前它会跳过禁用的菜单项。</span><span class="sxs-lookup"><span data-stu-id="efaba-283">Narrator can now read disabled <xref:System.Windows.Forms.ToolStripMenuItem> text, whereas previously it would skip over disabled menu items.</span></span>

<span data-ttu-id="efaba-284">**增强了对 UIAutomation 辅助功能模式的支持**</span><span class="sxs-lookup"><span data-stu-id="efaba-284">**Enhanced support for UIAutomation accessibility patterns**</span></span>

<span data-ttu-id="efaba-285">从 .NET Framework 4.7.1 开始，辅助功能技术工具的开发人员可以利用常见的 API 辅助功能模式和多个 WinForms 控件的属性。</span><span class="sxs-lookup"><span data-stu-id="efaba-285">Starting with the .NET Framework 4.7.1, developers of accessibility technology tools can leverage common API accessibility patterns and properties for several WinForms controls.</span></span> <span data-ttu-id="efaba-286">这些辅助功能改进包括：</span><span class="sxs-lookup"><span data-stu-id="efaba-286">These accessibility improvements include:</span></span>

- <span data-ttu-id="efaba-287"><xref:System.Windows.Forms.ComboBox> 和 <xref:System.Windows.Forms.ToolStripSplitButton> 现在支持[展开/折叠模式](../ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md)。</span><span class="sxs-lookup"><span data-stu-id="efaba-287">The <xref:System.Windows.Forms.ComboBox> and <xref:System.Windows.Forms.ToolStripSplitButton> now support the [expand/collapse pattern](../ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md).</span></span>

- <span data-ttu-id="efaba-288"><xref:System.Windows.Forms.DataGridViewCheckBoxCell> 现在支持[切换模式](../ui-automation/implementing-the-ui-automation-toggle-control-pattern.md)。</span><span class="sxs-lookup"><span data-stu-id="efaba-288">The <xref:System.Windows.Forms.DataGridViewCheckBoxCell> now supports the [toggle pattern](../ui-automation/implementing-the-ui-automation-toggle-control-pattern.md).</span></span>

- <span data-ttu-id="efaba-289"><xref:System.Windows.Forms.ToolStripItem> 控件支持 <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.Name> 属性和[展开/折叠模式](../ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md)。</span><span class="sxs-lookup"><span data-stu-id="efaba-289">The <xref:System.Windows.Forms.ToolStripItem> control supports the <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.Name> property and the [expand/collapse pattern](../ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md).</span></span>

- <span data-ttu-id="efaba-290"><xref:System.Windows.Forms.NumericUpDown> 和 <xref:System.Windows.Forms.DomainUpDown> 控件支持 <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.Name> 属性。</span><span class="sxs-lookup"><span data-stu-id="efaba-290">The <xref:System.Windows.Forms.NumericUpDown> and <xref:System.Windows.Forms.DomainUpDown> controls support the <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.Name> property.</span></span>

<span data-ttu-id="efaba-291">**改进了属性浏览器体验**</span><span class="sxs-lookup"><span data-stu-id="efaba-291">**Improved property browser experience**</span></span>

<span data-ttu-id="efaba-292">从 .NET Framework 4.7.1 开始，Windows 窗体包括以下改进：</span><span class="sxs-lookup"><span data-stu-id="efaba-292">Starting with the .NET Framework 4.7.1, Windows Forms includes:</span></span>

- <span data-ttu-id="efaba-293">更好地通过各种下拉选择窗口使用键盘导航。</span><span class="sxs-lookup"><span data-stu-id="efaba-293">Better keyboard navigation through the various drop-down selection windows.</span></span>
- <span data-ttu-id="efaba-294">减少不必要的制表位。</span><span class="sxs-lookup"><span data-stu-id="efaba-294">A reduction of unnecessary tab stops.</span></span>
- <span data-ttu-id="efaba-295">更好地报告控件类型。</span><span class="sxs-lookup"><span data-stu-id="efaba-295">Better reporting of control types.</span></span>
- <span data-ttu-id="efaba-296">改进了讲述人行为。</span><span class="sxs-lookup"><span data-stu-id="efaba-296">Improved narrator behavior.</span></span>

<a name="aspnet471"></a>

### <a name="aspnet-web-controls"></a><span data-ttu-id="efaba-297">ASP.NET Web 控件</span><span class="sxs-lookup"><span data-stu-id="efaba-297">ASP.NET web controls</span></span>

<span data-ttu-id="efaba-298">自 .NET Framework 4.7.1 和 Visual Studio 2017 15.3 起，ASP.NET 改进了 ASP.NET Web 控件与 Visual Studio 中的辅助功能技术配合使用的方式。</span><span class="sxs-lookup"><span data-stu-id="efaba-298">Starting with the .NET Framework 4.7.1 and Visual Studio 2017 15.3, ASP.NET improves how ASP.NET web controls work with accessibility technology in Visual Studio.</span></span> <span data-ttu-id="efaba-299">包括以下更改：</span><span class="sxs-lookup"><span data-stu-id="efaba-299">Changes include the following:</span></span>

- <span data-ttu-id="efaba-300">在以下控件中实现缺失 UI 的辅助功能模式：例如“详细信息视图”向导中的“添加字段”对话框或“ListView”向导的“配置 ListView”对话框。</span><span class="sxs-lookup"><span data-stu-id="efaba-300">Changes to implement missing UI accessibility patterns in controls, like the **Add Field** dialog in the **Details View** wizard, or the **Configure ListView** dialog of the **ListView** wizard.</span></span>

- <span data-ttu-id="efaba-301">改善在高对比度模式下（如“数据页导航字段编辑器”）的显示。</span><span class="sxs-lookup"><span data-stu-id="efaba-301">Changes to improve the display in High Contrast mode, like the **Data Pager Fields Editor**.</span></span>

- <span data-ttu-id="efaba-302">改善以下控件的键盘导航体验：例如 DataPager 控件的“编辑页导航字段”向导中的“字段”对话框、“配置 ObjectContext”对话框或“配置数据源”向导的“配置数据选择”对话框。</span><span class="sxs-lookup"><span data-stu-id="efaba-302">Changes to improve the keyboard navigation experiences for controls, like the **Fields** dialog in the **Edit Pager Fields** wizard of the DataPager control, the **Configure ObjectContext** dialog, or the **Configure Data Selection** dialog of the **Configure Data Source** wizard.</span></span>

<a name="tools471"></a>

### <a name="net-sdk-tools"></a><span data-ttu-id="efaba-303">.NET SDK 工具</span><span class="sxs-lookup"><span data-stu-id="efaba-303">.NET SDK Tools</span></span>

<span data-ttu-id="efaba-304">[配置编辑器工具 (SvcConfigEditor.exe)](../wcf/configuration-editor-tool-svcconfigeditor-exe.md) 和[服务跟踪查看器工具 (SvcTraceViewer.exe)](../wcf/service-trace-viewer-tool-svctraceviewer-exe.md) 通过修复各种辅助功能问题得到改进。</span><span class="sxs-lookup"><span data-stu-id="efaba-304">The [Configuration Editor Tool (SvcConfigEditor.exe)](../wcf/configuration-editor-tool-svcconfigeditor-exe.md) and [Service Trace Viewer Tool (SvcTraceViewer.exe)](../wcf/service-trace-viewer-tool-svctraceviewer-exe.md) have been improved by fixing varied accessibility issues.</span></span> <span data-ttu-id="efaba-305">其中大多数都是一些小问题，如未定义名称或未正确实现某些 UI 自动化模式。</span><span class="sxs-lookup"><span data-stu-id="efaba-305">Most of these were small issues, like a name not being defined or certain UI automation patterns not being implemented correctly.</span></span> <span data-ttu-id="efaba-306">虽然许多用户不会意识到这些小问题的重要性，但使用屏幕阅读器等辅助技术的客户会发现这些 SDK 工具更易于访问。</span><span class="sxs-lookup"><span data-stu-id="efaba-306">While many users won’t be aware of these incorrect values, customers who use assistive technologies like screen readers will find these SDK tools more accessible.</span></span>

<span data-ttu-id="efaba-307">这些改进更改了某些旧行为，例如键盘焦点顺序。</span><span class="sxs-lookup"><span data-stu-id="efaba-307">These enhancements change some previous behaviors, such as keyboard focus order.</span></span>

<a name="wf471"></a>

### <a name="windows-workflow-foundation-wf-workflow-designer"></a><span data-ttu-id="efaba-308">Windows Workflow Foundation (WF) 工作流设计器</span><span class="sxs-lookup"><span data-stu-id="efaba-308">Windows Workflow Foundation (WF) Workflow Designer</span></span>

<span data-ttu-id="efaba-309">工作流设计器中的辅助功能更改包括：</span><span class="sxs-lookup"><span data-stu-id="efaba-309">Accessibility changes in the Workflow Designer include the following:</span></span>

- <span data-ttu-id="efaba-310">某些控件中 Tab 键顺序更改为从左到右以及从上到下：</span><span class="sxs-lookup"><span data-stu-id="efaba-310">The tab order changes to left to right and top to bottom in some controls:</span></span>

  - <span data-ttu-id="efaba-311">设置 <xref:System.ServiceModel.Activities.InitializeCorrelation> 活动相关数据的初始化相关窗口。</span><span class="sxs-lookup"><span data-stu-id="efaba-311">The initialize correlation window for setting correlation data for the <xref:System.ServiceModel.Activities.InitializeCorrelation> activity.</span></span>

  - <span data-ttu-id="efaba-312"><xref:System.ServiceModel.Activities.Receive>、<xref:System.ServiceModel.Activities.Send>、<xref:System.ServiceModel.Activities.SendReply> 和 <xref:System.ServiceModel.Activities.ReceiveReply> 活动的内容定义窗口。</span><span class="sxs-lookup"><span data-stu-id="efaba-312">The content definition window for the <xref:System.ServiceModel.Activities.Receive>, <xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.SendReply>, and <xref:System.ServiceModel.Activities.ReceiveReply> activities.</span></span>

- <span data-ttu-id="efaba-313">通过键盘可以使用更多功能：</span><span class="sxs-lookup"><span data-stu-id="efaba-313">More functions are available via the keyboard:</span></span>

  - <span data-ttu-id="efaba-314">编辑活动的属性时，属性组在第一次聚焦时可以通过键盘折叠。</span><span class="sxs-lookup"><span data-stu-id="efaba-314">When editing the properties of an activity, property groups can be collapsed by keyboard the first time they are focused.</span></span>

  - <span data-ttu-id="efaba-315">警告图标可以通过键盘访问。</span><span class="sxs-lookup"><span data-stu-id="efaba-315">Warning icons are accessible by keyboard.</span></span>

  - <span data-ttu-id="efaba-316">“属性”窗口的“更多属性”按钮可以通过键盘访问。</span><span class="sxs-lookup"><span data-stu-id="efaba-316">The **More Properties** button in the **Properties** window is accessible by keyboard.</span></span>

  - <span data-ttu-id="efaba-317">键盘用户可以访问工作流设计器“参数”和“变量”窗格的标题项。</span><span class="sxs-lookup"><span data-stu-id="efaba-317">Keyboard users can access the header items in the **Arguments** and **Variables** panes of the Workflow Designer.</span></span>

- <span data-ttu-id="efaba-318">提升了聚焦项的可见性，例如当：</span><span class="sxs-lookup"><span data-stu-id="efaba-318">Improved visibility of items with focus, such as when:</span></span>

  - <span data-ttu-id="efaba-319">将行添加到工作流设计器和活动设计器使用的数据网格。</span><span class="sxs-lookup"><span data-stu-id="efaba-319">Adding rows to data grids used by the Workflow Designer and activity designers.</span></span>

  - <span data-ttu-id="efaba-320">在 <xref:System.ServiceModel.Activities.ReceiveReply> 和 <xref:System.ServiceModel.Activities.SendReply> 活动中按 Tab 键切换字段。</span><span class="sxs-lookup"><span data-stu-id="efaba-320">Tabbing through fields in the <xref:System.ServiceModel.Activities.ReceiveReply> and <xref:System.ServiceModel.Activities.SendReply> activities.</span></span>

  - <span data-ttu-id="efaba-321">设置变量或自变量的默认值</span><span class="sxs-lookup"><span data-stu-id="efaba-321">Setting default values for variables or arguments</span></span>

- <span data-ttu-id="efaba-322">屏幕读取器现在可以正确识别：</span><span class="sxs-lookup"><span data-stu-id="efaba-322">Screen readers can now correctly recognize:</span></span>

  - <span data-ttu-id="efaba-323">工作流设计器中设置的断点。</span><span class="sxs-lookup"><span data-stu-id="efaba-323">Breakpoints set in the workflow designer.</span></span>

  - <span data-ttu-id="efaba-324"><xref:System.Activities.Statements.FlowSwitch%601>、<xref:System.Activities.Statements.FlowDecision> 和 <xref:System.ServiceModel.Activities.CorrelationScope> 活动。</span><span class="sxs-lookup"><span data-stu-id="efaba-324">The <xref:System.Activities.Statements.FlowSwitch%601>, <xref:System.Activities.Statements.FlowDecision>, and <xref:System.ServiceModel.Activities.CorrelationScope> activities.</span></span>
  - <span data-ttu-id="efaba-325"><xref:System.ServiceModel.Activities.Receive> 活动的内容。</span><span class="sxs-lookup"><span data-stu-id="efaba-325">The contents of the <xref:System.ServiceModel.Activities.Receive> activity.</span></span>

  - <span data-ttu-id="efaba-326"><xref:System.Activities.Statements.InvokeMethod> 活动的目标类型。</span><span class="sxs-lookup"><span data-stu-id="efaba-326">The Target Type for the <xref:System.Activities.Statements.InvokeMethod> activity.</span></span>

  - <span data-ttu-id="efaba-327"><xref:System.Activities.Statements.TryCatch> 活动中的“异常”组合框和“最终”部分。</span><span class="sxs-lookup"><span data-stu-id="efaba-327">The Exception combo box and the Finally section in the <xref:System.Activities.Statements.TryCatch> activity.</span></span>

  - <span data-ttu-id="efaba-328">消息传递活动（<xref:System.ServiceModel.Activities.Receive>、<xref:System.ServiceModel.Activities.Send>、<xref:System.ServiceModel.Activities.SendReply> 和 <xref:System.ServiceModel.Activities.ReceiveReply>）中的“消息类型”组合框、“添加相关初始化表达式”窗口中的拆分器、“内容定义”窗口和“CorrelatesOn 定义”窗口。</span><span class="sxs-lookup"><span data-stu-id="efaba-328">The Message Type combo box, the splitter in the Add Correlation Initializers window, the Content Definition window, and the CorrelatesOn Definition window in the messaging activities (<xref:System.ServiceModel.Activities.Receive>, <xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.SendReply>, and <xref:System.ServiceModel.Activities.ReceiveReply>).</span></span>

  - <span data-ttu-id="efaba-329">状态机转换和转换目标。</span><span class="sxs-lookup"><span data-stu-id="efaba-329">State machine transitions and transitions destinations.</span></span>

  - <span data-ttu-id="efaba-330"><xref:System.Activities.Statements.FlowDecision> 活动上的注释和连接器。</span><span class="sxs-lookup"><span data-stu-id="efaba-330">Annotations and connectors on <xref:System.Activities.Statements.FlowDecision> activities.</span></span>

  - <span data-ttu-id="efaba-331">活动的上下文（右键单击）菜单。</span><span class="sxs-lookup"><span data-stu-id="efaba-331">The context (right-click) menus for activities.</span></span>

  - <span data-ttu-id="efaba-332">属性值编辑器、“清除搜索”按钮、“按类别”和“按字母顺序”排序按钮以及属性网格中的“表达式编辑器”对话框。</span><span class="sxs-lookup"><span data-stu-id="efaba-332">The property value editors, the Clear Search button, the By Category and Alphabetical sort buttons, and the Expression Editor dialog in the properties grid.</span></span>

  - <span data-ttu-id="efaba-333">工作流设计器中的缩放百分比。</span><span class="sxs-lookup"><span data-stu-id="efaba-333">The zoom percentage in the Workflow Designer.</span></span>

  - <span data-ttu-id="efaba-334"><xref:System.Activities.Statements.Parallel> 和 <xref:System.Activities.Statements.Pick> 活动中的分隔符。</span><span class="sxs-lookup"><span data-stu-id="efaba-334">The separator in <xref:System.Activities.Statements.Parallel> and <xref:System.Activities.Statements.Pick> activities.</span></span>

  - <span data-ttu-id="efaba-335"><xref:System.Activities.Statements.InvokeDelegate> 活动。</span><span class="sxs-lookup"><span data-stu-id="efaba-335">The <xref:System.Activities.Statements.InvokeDelegate> activity.</span></span>

  - <span data-ttu-id="efaba-336">字典活动（`Microsoft.Activities.AddToDictionary<TKey,TValue>`、`Microsoft.Activities.RemoveFromDictionary<TKey,TValue>` 等）的“选择类型”窗口。</span><span class="sxs-lookup"><span data-stu-id="efaba-336">The Select Types window for dictionary activities (`Microsoft.Activities.AddToDictionary<TKey,TValue>`, `Microsoft.Activities.RemoveFromDictionary<TKey,TValue>`, etc.).</span></span>

  - <span data-ttu-id="efaba-337">“浏览和选择 .NET 类型”窗口。</span><span class="sxs-lookup"><span data-stu-id="efaba-337">The Browse and Select .NET Type window.</span></span>

  - <span data-ttu-id="efaba-338">工作流设计器中的痕迹导航。</span><span class="sxs-lookup"><span data-stu-id="efaba-338">Breadcrumbs in the Workflow Designer.</span></span>

- <span data-ttu-id="efaba-339">选择高对比度主题的用户将看到工作流设计器及其控件可见性的许多改进，例如元素间更好的对比度和焦点元素更明显的选择框。</span><span class="sxs-lookup"><span data-stu-id="efaba-339">Users who choose High Contrast themes will see many improvements in the visibility of the Workflow Designer and its controls, like better contrast ratios between elements and more noticeable selection boxes used for focus elements.</span></span>

## <a name="see-also"></a><span data-ttu-id="efaba-340">请参阅</span><span class="sxs-lookup"><span data-stu-id="efaba-340">See also</span></span>

- [<span data-ttu-id="efaba-341">.NET Framework 的新增功能</span><span class="sxs-lookup"><span data-stu-id="efaba-341">What's new in the .NET Framework</span></span>](whats-new.md)
