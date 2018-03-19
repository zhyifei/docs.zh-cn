---
title: ".NET Framework 中辅助功能的新增功能"
ms.custom: updateeachrelease
ms.date: 10/13/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- what's new [.NET Framework]
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 5f17550bc0cc4919f00dc93c8e92d258b38c4f76
ms.sourcegitcommit: 1c0b0f082b3f300e54b4d069b317ac724c88ddc3
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/16/2018
---
# <a name="whats-new-in-accessibility-in-the-net-framework"></a>.NET Framework 中辅助功能的新增功能

.NET Framework 旨在让用户更轻松地使用应用程序。 辅助功能使应用程序能够为辅助技术用户提供最佳体验。 从 .NET Framework 4.7.1 开始，.NET Framework 包括大量辅助功能改进，使开发人员能够创建易于访问的应用程序。 

对于面向 .NET Framework 4.7.1 或更高版本的应用程序，新的辅助功能默认情况下处于启用状态。 此外，对于面向 .NET Framework 早期版本，但在 .NET Framework 4.7.1 或更高版本上运行的应用程序，可通过将以下开关添加到应用程序配置文件 [`<runtime>`](~/docs/framework/configure-apps/file-schema/runtime/index.md) 部分中的 [`<AppContextSwitchOverrides>`](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) 元素来选择取消旧辅助功能行为（因而选择使用 .NET Framework 4.7.1 中的辅助功能改进）。 

```xml
<runtime>
    <!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true|false;key2=true|false  -->
    <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false" />
</runtime>
```

同样，对于面向 .NET Framework 4.7.1 或更高版本的应用程序，可通过将以下开关添加到应用程序配置文件 [`<runtime>`](~/docs/framework/configure-apps/file-schema/runtime/index.md) 部分中的 [`<AppContextSwitchOverrides>`](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) 来禁用辅助功能。 

```xml
<runtime>
    <!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true|false;key2=true|false  -->
    <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=true" />
</runtime>
```

## <a name="whats-new-in-accessibility-in-the-net-framework-471"></a>.NET Framework 4.7.1 中辅助功能的新增功能

.NET Framework 4.7.1 在以下几个领域新增了辅助功能：

- [Windows Presentation Foundation (WPF)](#windows-presentation-foundation-wpf)

- [Windows 窗体](#windows-forms-accessibility-improvements)

### <a name="windows-presentation-foundation-wpf"></a>Windows Presentation Foundation (WPF)

**屏幕阅读器改进**

如果启用了辅助功能改进，.NET Framework 4.7.1 包括以下可影响屏幕读阅读的增强功能：

- 在 .NET Framework 4.7 及更低版本中，<xref:System.Windows.Controls.Expander> 控件由屏幕阅读器宣称为按钮。 从 .NET Framework 4.7.1 开始，它们被正确地称为可展开/可折叠组。

- 在 .NET Framework 4.7 及更低版本中，<xref:System.Windows.Controls.DataGridCell> 控件由屏幕阅读器宣称为“自定义”。 从 .NET Framework 4.7.1 开始，它们被正确地称为数据网格单元格（已本地化）。
 
- 从 .NET Framework 4.7.1 开始，屏幕阅读器读出可编辑 <xref:System.Windows.Controls.ComboBox> 的名称。

- 在 .NET Framework 4.7 及更低版本中，<xref:System.Windows.Controls.PasswordBox> 控件被宣称为“视图中没有任何项”或有其他错误行为。 此问题已在 .NET Framework 4.7.1 及更高版本中解决。     

**UIAutomation LiveRegion 支持**

屏幕阅读器（如讲述人）可帮助用户阅读应用程序的 UI 内容，通常通过具有焦点的 UI 内容的文本到语音转换输出实现。 但是，如果 UI 元素更改，并且不具有焦点，则用户可能不会收到通知，并且可能会错过重要信息。 活动区域旨在解决此问题。 开发人员可使用它们来通知屏幕阅读器或任何其他 UIAutomation 客户端 UI 元素有重要更改。 然后，屏幕阅读器可确定向用户通知此更改的方式和时间。 

为了支持活动区域，向 WPF 添加了以下 API：

- <xref:System.Windows.Automation.AutomationElementIdentifiers.LiveSettingProperty?displayProperty=nameWithType> 和 <xref:System.Windows.Automation.AutomationElementIdentifiers.LiveRegionChangedEvent?displayProperty=nameWithType> 字段，用于标识 LiveSetting 属性和 LiveRegionChanged 事件。 可通过使用 XAML 来进行设置。

- AutomationProperties.LiveSetting 附加属性，用于向屏幕阅读器通知 UI 更改对用户的重要性。

- <xref:System.Windows.Automation.AutomationProperties.LiveSettingProperty?displayProperty=nameWithType> 属性，用于标识 AutomationProperties.LiveSetting 附加属性。
 
- <xref:System.Windows.Automation.Peers.AutomationPeer.GetLiveSettingCore%2A?displayProperty=nameWithType> 方法，可替代该方法以提供 LiveSetting 值。

- <xref:System.Windows.Automation.AutomationProperties.GetLiveSetting%2A?displayProperty=nameWithType> 和 <xref:System.Windows.Automation.AutomationProperties.SetLiveSetting%2A?displayProperty=nameWithType> 方法，用于获取和设置 LiveSetting 值。
 
- <xref:System.Windows.Automation.AutomationLiveSetting?displayProperty=nameWithType> 枚举，用于定义以下可能的 LiveSetting 值：

   - <xref:System.Windows.Automation.AutomationLiveSetting.Off?displayProperty=nameWithType>。 如果活动区域的内容已更改，则该元素不会发送通知。   
   - <xref:System.Windows.Automation.AutomationLiveSetting.Polite?displayProperty=nameWithType>。 如果活动区域的内容已更改，则该元素将发送非中断通知。   

  - <xref:System.Windows.Automation.AutomationLiveSetting.Assertive?displayProperty=nameWithType>。 如果活动区域的内容已更改，则该元素将发送中断通知。   

可通过对相关元素设置 AutomationProperties.LiveSetting 属性来创建 LiveRegion，如以下示例所示：   

```xaml
<TextBlock Name="myTextBlock" AutomationProperties.LiveSetting="Assertive">announcement</TextBlock>
```

活动区域中的数据发生更改，并且需要通知屏幕阅读器时，可显式引发事件，如以下示例所示。

```csharp
var peer = FrameworkElementAutomationPeer.FromElement(myTextBlock);

peer.RaiseAutomationEvent(AutomationEvents.LiveRegionChanged);
```
```vb
Dim peer = FrameworkElementAutomationPeer.FromElement(myTextBlock)
peer.RaiseAutomationEvent(AutomationEvents.LiveRegionChanged)

```

**高对比度**

从 .NET Framework 4.7.1 开始，对多种 WPF 控件进行了高对比度改进。 可在设置 <xref:System.Windows.SystemParameters.HighContrast%2A> 主题后看到这些改进。 这些方法包括：

- <xref:System.Windows.Controls.Expander> 控件

    <xref:System.Windows.Controls.Expander> 控件的焦点视觉对象现在可见。 <xref:System.Windows.Controls.ComboBox>、<xref:System.Windows.Controls.ListBox> 和 <xref:System.Windows.Controls.RadioButton> 控件的键盘视觉对象也可见。 例如:

    在此之前: 
    
    ![辅助功能改进前具有焦点的 Expander 控件](media/expander-before.png)

    之后： 

    ![辅助功能改进后具有焦点的 Expander 控件](media/expander-after.png)

- <xref:System.Windows.Controls.CheckBox> 和 <xref:System.Windows.Controls.RadioButton> 控件
 
    在高对比度主题下选中时，<xref:System.Windows.Controls.CheckBox> 和 <xref:System.Windows.Controls.RadioButton> 控件中的文本更易于查看。 例如:

    在此之前: 

    ![辅助功能改进前具有焦点的高对比度单选按钮](media/radio-button-before.png)
    
    之后： 

    ![辅助功能改进后具有焦点的高对比度单选按钮](media/radio-button-after.png)

- <xref:System.Windows.Controls.ComboBox> 控件
 
    从 .NET Framework 4.7.1 开始，已禁用的 <xref:System.Windows.Controls.ComboBox> 控件的边框与禁用的文本颜色相同。 例如:
    
    在此之前: 

     ![辅助功能改进前禁用的 ComboBox 边框和文本](media/combo-disabled-before.png)

    之后：   

     ![辅助功能改进后禁用的 ComboBox 边框和文本](media/combo-disabled-after.png)

    此外，已禁用的按钮和具有焦点的按钮使用正确的主题颜色。

    在此之前:

    ![辅助功能改进前的按钮主题颜色](media/button-themes-before.png) 
    
    之后： 

    ![辅助功能改进后的按钮主题颜色](media/button-themes-after.png) 

    最后，在 .NET Framework 4.7 及更低版本中，将 <xref:System.Windows.Controls.ComboBox> 控件的样式设置为 `Toolbar.ComboBoxStyleKey` 会导致下拉箭头不可见。 此问题已在 .NET Framework 4.7.1 及更高版本中解决。 例如:

    在此之前: 

    ![辅助功能改进前的 Toolbar.ComboBoxStyleKey](media/comboboxstylekey-before.png) 
    
    之后： 

    ![辅助功能改进后的 Toolbar.ComboBoxStyleKey](media/comboboxstylekey-after.png) 

- <xref:System.Windows.Controls.DataGrid> 控件

    从 .NET Framework 4.7.1 开始，<xref:System.Windows.Controls.DataGrid> 控件中的排序指示符箭头现在使用正确的主题颜色。 例如:

    在此之前: 

    ![辅助功能改进前的排序指示符箭头](media/sort-indicator-before.png) 
    
    之后：   
 
    ![辅助功能改进后的排序指示符箭头](media/sort-indicator-after.png) 
    
    此外，在 .NET Framework 4.7 及更低版本中，在高对比度模式下，默认链接样式在鼠标悬停在其上时更改为不正确的颜色。 此问题已在 .NET Framework 4.7.1 及更高版本中解决。 同样，从 .NET Framework 4.7.1 开始，<xref:System.Windows.Controls.DataGrid> 复选框列对键盘焦点反馈使用预期的颜色。

    在此之前: 

    ![辅助功能改进前的 DataGrid 默认链接样式](media/default-link-style-before.png) 
 
    之后：    
  
    ![辅助功能改进后的 DataGrid 默认链接样式](media/default-link-style-after.png)  

有关 .NET Framework 4.7.1 中 WPF 辅助功能改进的详细信息，请参阅 [WPF 辅助功能改进](../migration-guide/retargeting/4.7-4.7.1.md#accessibility-improvements-in-wpf)。

## <a name="windows-forms-accessibility-improvements"></a>Windows 窗体辅助功能改进

在 .NET Framework 4.7.1 中，Windows 窗体 (WinForms) 包括以下几个方面的辅助功能改进。

**改进了高对比度模式下的显示**

从 .NET Framework 4.7.1 开始，多种 WinForms 控件改进了高对比度模式下在操作系统中的呈现方式。 Windows 10 更改了一些高对比度系统颜色的值，而 Windows 窗体基于 Windows 10 Win32 框架。 为获得最佳体验，请运行最新版本的 Windows，并通过在测试应用程序中添加 app.manifest 文件选择使用最新的 OS 更改，同时取消注释 Windows 10 支持的 OS 行，最终结果如下所示：

```xml
<!-- Windows 10 -->
<supportedOS Id=”{8e0f7a12-bfb3-4fe8-b9a5-48fd50a15a9a}” />
```
高对比度更改的一些示例包括：

- <xref:System.Windows.Forms.MenuStrip> 项中的复选标记更易于查看。

- 选中后，禁用的 <xref:System.Windows.Forms.MenuStrip> 项更易于查看。

- 所选 <xref:System.Windows.Forms.Button> 控件中的文本与选中颜色形成鲜明对比。

- 禁用的文本更易于阅读。 例如:

    在此之前:

    ![辅助功能改进前禁用的文本](media/wf-disabled-before.png) 

    之后：

    ![辅助功能改进后禁用的文本](media/wf-disabled-after.png) 

- “线程异常”对话框中的高对比度改进。

**改进了讲述人支持**

.NET Framework 4.7.1 中的 Windows 窗体对讲述人进行了以下辅助功改进：

- 讲述人以及其他 UI 自动化工具可访问 <xref:System.Windows.Forms.MonthCalendar> 控件。

- 当某个项的选中状态更改时，<xref:System.Windows.Forms.CheckedListBox> 控件会通知讲述人，因此用户可获知更改了列表项的值。
 
- <xref:System.Windows.Forms.DataGridViewCell> 控件向讲述人报告正确的只读状态。
 
- 讲述人现在可以阅读已禁用的 <xref:System.Windows.Forms.ToolStripMenuItem> 文本，而以前它会跳过禁用的菜单项。

**增强了对 UIAutomation 辅助功能模式的支持**

从 .NET Framework 4.7.1 开始，辅助功能技术工具的开发人员可以利用常见的 API 辅助功能模式和多个 WinForms 控件的属性。 这些辅助功能改进包括：

- <xref:System.Windows.Forms.ComboBox> 和 <xref:System.Windows.Forms.ToolStripSplitButton> 现在支持[展开/折叠模式](../ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md)。
 
- <xref:System.Windows.Forms.DataGridViewCheckBoxCell> 现在支持[切换模式](../ui-automation/implementing-the-ui-automation-toggle-control-pattern.md)。
 
- <xref:System.Windows.Forms.ToolStripItem> 控件支持 <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.Name> 属性和[展开/折叠模式](../ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md)。

- <xref:System.Windows.Forms.NumericUpDown> 和 <xref:System.Windows.Forms.DomainUpDown> 控件支持 <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.Name> 属性。

**改进了属性浏览器体验**

从 .NET Framework 4.7.1 开始，Windows 窗体包括以下改进：

- 更好地通过各种下拉选择窗口使用键盘导航。
- 减少不必要的制表位。
- 更好地报告控件类型。
- 改进了讲述人行为。
 
## <a name="see-also"></a>请参阅
[.NET Framework 的新增功能](whats-new.md)   
 
