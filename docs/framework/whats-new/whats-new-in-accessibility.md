---
title: ".NET Framework 中的辅助功能的新增功能"
ms.custom: updateeachrelease
ms.date: 10/13/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: what's new [.NET Framework]
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4886dad94d3a67e78525241a1538c06b9fe4b0be
ms.sourcegitcommit: 6f49c973f62855ffd6c4a322903e7dd50c5c1b50
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2017
---
# <a name="whats-new-in-accessibility-in-the-net-framework"></a>.NET Framework 中的辅助功能的新增功能

.NET Framework 的目的是使多个 accessibile 为你的用户的应用程序。 辅助功能允许应用程序的辅助技术的用户提供的适当的体验。 从.NET Framework 4.7.1 开始，.NET Framework 包括大量的可访问性改进功能的允许开发人员创建可访问应用程序。 

新的辅助功能已启用默认情况下，对于面向.NET Framework 4.7.1 的应用程序或更高版本。 此外，面向.NET Framework 的早期版本，但在.NET Framework 4.7.1 上运行或更高版本可以选择的应用程序的旧的可访问性行为 （和从而参与到.NET Framework 4.7.1 中的可访问性改进） 通过添加以下切换到[ `<AppContextSwitchOverrides>` ](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md)中的元素[ `<runtime>` ](~/docs/framework/configure-apps/file-schema/runtime/index.md)应用程序的配置文件节。 

```xml
<runtime>
    <!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true|false;key2=true|false  -->
    <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false" />
</runtime>
```

同样，开头 4.7.1.NET Framework 目标版本的应用程序可禁用辅助功能，通过添加以下切换到[ `<AppContextSwitchOverrides>` ](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md)中的元素[ `<runtime>` ](~/docs/framework/configure-apps/file-schema/runtime/index.md)应用程序的配置文件节。 

```xml
<runtime>
    <!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true|false;key2=true|false  -->
    <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=true" />
</runtime>
```

## <a name="whats-new-in-accessibility-in-the-net-framework-471"></a>.NET Framework 4.7.1 中的辅助功能的新增功能

.NET Framework 4.7.1 包括以下区域中的新辅助功能：

- [Windows Presentation Foundation (WPF)](#windows-presentation-foundation-wpf)

- [Windows 窗体](#windows-forms-accessibility-improvements)

### <a name="windows-presentation-foundation-wpf"></a>Windows Presentation Foundation (WPF)

**屏幕读取器改进**

如果启用了可访问性改进，.NET Framework 4.7.1 包括影响屏幕读取器的以下增强功能：

- 在.NET Framework 4.7 和早期版本中，<xref:System.Windows.Controls.Expander>控件已宣布为按钮的屏幕读取器。 从.NET Framework 4.7.1 开始，正确上公布它们作为可展开/折叠组。

- 在.NET Framework 4.7 和早期版本中，<xref:System.Windows.Controls.DataGridCell>控件已宣布屏幕读取器，为"custom"。 从.NET Framework 4.7.1 开始，现在正确上公布它们与数据网格单元格 （本地化）。
 
- 从.NET Framework 4.7.1 开始，屏幕阅读器宣告的可编辑名称<xref:System.Windows.Controls.ComboBox>。

- 在.NET Framework 4.7 和早期版本中，<xref:System.Windows.Controls.PasswordBox>控件已宣布为"视图中没有项"或具有否则为不正确的行为。 从.NET Framework 4.7.1 开始修复此问题。     

**UIAutomation LiveRegion 支持**

如讲述人帮助人员屏幕读取器读取应用程序的 UI 内容通常具有焦点的 UI 内容的文本到语音转换输出。 但是，如果 UI 元素更改，并且不具有焦点，则用户可能不会收到通知，并且可能会丢失重要信息。 在解决此问题的目标是实时的区域。 开发人员可以将其用作屏幕阅读器或对 UI 元素进行了重要更改任何其他 UIAutomation 客户端。 屏幕读取器然后可决定何时以及如何通知用户此更改。 

若要支持实时区域，以下 Api 已添加到 WPF:

- <xref:System.Windows.Automation.AutomationElementIdentifiers.LiveSettingProperty?displayProperty=nameWithType>和<xref:System.Windows.Automation.AutomationElementIdentifiers.LiveRegionChangedEvent?displayProperty=nameWithType>字段，标识**LiveSetting**属性和**LiveRegionChanged**事件。 它们可以通过使用 XAML 设置。

- **AutomationProperties.LiveSetting**附加属性，用于通知的重要性对用户的用户界面更改屏幕读取器。

- <xref:System.Windows.Automation.AutomationProperties.LiveSettingProperty?displayProperty=nameWithType>属性，它标识**AutomationProperties.LiveSetting**附加属性。
 
- <xref:System.Windows.Automation.Peers.AutomationPeer.GetLiveSettingCore%2A?displayProperty=nameWithType>方法，可以重写以提供**LiveSetting**值。

- <xref:System.Windows.Automation.AutomationProperties.GetLiveSetting%2A?displayProperty=nameWithType>和<xref:System.Windows.Automation.AutomationProperties.SetLiveSetting%2A?displayProperty=nameWithType>的 get 和 set 方法**LiveSetting**值。
 
- <xref:System.Windows.Automation.AutomationLiveSetting?displayProperty=nameWithType>枚举，它定义了以下可能**LiveSetting**值：

   - <xref:System.Windows.Automation.AutomationLiveSetting.Off?displayProperty=nameWithType>。 如果实时区域的内容已更改，该元素不会发送通知。   
   - <xref:System.Windows.Automation.AutomationLiveSetting.Polite?displayProperty=nameWithType>。 如果活动区域的内容已更改，则该元素将发送非中断通知。   

  - <xref:System.Windows.Automation.AutomationLiveSetting.Assertive?displayProperty=nameWithType>。 如果活动区域的内容已更改，则该元素将发送中断通知。   

你可以通过设置创建 LiveRegion **AutomationProperties.LiveSetting**感兴趣，如下面的示例中所示的元素的属性上：   

```xaml
<TextBlock Name="myTextBlock" AutomationProperties.LiveSetting="Assertive">announcement</TextBlock>
```

实时区域中的数据更改，你需要告知屏幕读取器时你显式引发事件，如下面的示例中所示。

```csharp
var peer = FrameworkElementAutomationPeer.FromElement(myTextBlock);

peer.RaiseAutomationEvent(AutomationEvents.LiveRegionChanged);
```
```vb
Dim peer = FrameworkElementAutomationPeer.FromElement(myTextBlock)
peer.RaiseAutomationEvent(AutomationEvents.LiveRegionChanged)

```

**高对比度**

从.NET Framework 4.7.1 开始，在高对比度已得到改进各种 WPF 控件。 它们现在是可见时<xref:System.Windows.SystemParameters.HighContrast%2A>设置主题。 这些方法包括：

- <xref:System.Windows.Controls.Expander> 控件

    焦点视觉<xref:System.Windows.Controls.Expander>控件现在是否可见。 键盘视觉对象以<xref:System.Windows.Controls.ComboBox>，<xref:System.Windows.Controls.ListBox>，和<xref:System.Windows.Controls.RadioButton>控件也可见。 例如: 

    在此之前: 
    
    ![具有焦点之前可访问性改进的扩展器控件](media/expander-before.png)

    在此之后： 

    ![扩展器具有可访问性改进后的焦点的控件](media/expander-after.png)

- <xref:System.Windows.Controls.CheckBox>和<xref:System.Windows.Controls.RadioButton>控件
 
    中的文本<xref:System.Windows.Controls.CheckBox>和<xref:System.Windows.Controls.RadioButton>控件现在是更轻松地查看在高对比度主题中选择。 例如: 

    在此之前: 

    ![具有焦点之前可访问性改进的高对比度单选按钮](media/radio-button-before.png)
    
    在此之后： 

    ![具有可访问性改进后的焦点的高对比度单选按钮](media/radio-button-after.png)

- <xref:System.Windows.Controls.ComboBox> 控件
 
    从.NET Framework 4.7.1，已禁用的边框开始<xref:System.Windows.Controls.ComboBox>控件是禁用的文本与相同的颜色。 例如: 
    
    在此之前: 

     ![组合框禁用边框和可访问性改进前的文本](media/combo-disabled-before.png)

    在此之后：   

     ![组合框可访问性改进后禁用边框和文本](media/combo-disabled-after.png)

    此外，已禁用的专注于按钮将使用正确的主题颜色。

    在此之前:

    ![按钮可访问性改进之前的主题颜色](media/button-themes-before.png) 
    
    在此之后： 

    ![按钮可访问性改进后的主题颜色](media/button-themes-after.png) 

    最后，在.NET Framework 4.7 和早期版本中，设置<xref:System.Windows.Controls.ComboBox>控件的样式应用到`Toolbar.ComboBoxStyleKey`导致不可见的下拉箭头。 从.NET Framework 4.7.1 开始修复此问题。 例如: 

    在此之前: 

    ![Toolbar.ComboBoxStyleKey 之前可访问性改进](media/comboboxstylekey-before.png) 
    
    在此之后： 

    ![Toolbar.ComboBoxStyleKey 后可访问性改进](media/comboboxstylekey-after.png) 

- <xref:System.Windows.Controls.DataGrid> 控件

    从.NET Framework 4.7.1 中的排序指示器箭头开始<xref:System.Windows.Controls.DataGrid>控制现在使用更正主题颜色。 例如: 

    在此之前: 

    ![排序指示器箭头之前可访问性改进](media/sort-indicator-before.png) 
    
    在此之后：   
 
    ![排在可访问性改进指示器箭头](media/sort-indicator-after.png) 
    
    此外，在.NET Framework 4.7 和早期版本中，默认链接样式更改为鼠标上不正确的颜色在高对比度模式。 此问题解决从.NET Framework 4.7.1 开始。 同样，<xref:System.Windows.Controls.DataGrid>复选框列的键盘焦点反馈从.NET Framework 4.7.1 开始使用预期的颜色。

    在此之前: 

    ![DataGrid 默认链接样式之前可访问性改进](media/default-link-style-before.png) 
 
    在此之后：    
  
    ![可访问性改进后的 DataGrid 默认链接样式](media/default-link-style-after.png)  

有关在.NET Framework 4.7.1 WPF 可访问性改进的详细信息，请参阅[WPF 中的可访问性改进](../migration-guide/retargeting/4.7-4.7.1.md#accessibility-improvements-in-wpf)。

## <a name="windows-forms-accessibility-improvements"></a>Windows 窗体可访问性改进

在.NET Framework 4.7.1 中，Windows 窗体 (WinForms) 包括以下几个方面的可访问性更改。

**在高对比度模式中的改进的显示**

从.NET Framework 4.7.1 开始，各种 WinForms 控件提供改进的呈现在操作系统中可用的高对比度模式。 Windows 窗体根据 Windows 10 Win32 framework 和 Windows 10 已更改的一些高对比度的系统颜色的值。 为获得最佳体验，最新版本的 Windows 上运行并通过添加测试应用程序并取消注释 Windows 10 中的应用程序清单文件支持 OS 行，这样它看起来就以下参与到最新的操作系统更改：

```xml
<!– Windows 10 –>
<supportedOS Id=”{8e0f7a12-bfb3-4fe8-b9a5-48fd50a15a9a}” />
```
高对比度更改的一些示例包括：

- 中的复选标记<xref:System.Windows.Forms.MenuStrip>项更易于查看。

- 当选中时，禁用<xref:System.Windows.Forms.MenuStrip>项更易于查看。

- 在所选的文本<xref:System.Windows.Forms.Button>控制所选的颜色与之相对的。

- 已禁用的文本更容易读取。 例如: 

    在此之前:

    ![已禁用的文本之前可访问性改进](media/wf-disabled-before.png) 

    在此之后：

    ![之后可访问性改进的禁用的文本](media/wf-disabled-after.png) 

- 在异常对话框中的线程的高对比度改进。

**讲述人的增强的支持**

.NET Framework 4.7.1 中的 Windows 窗体包含讲述人的以下可访问性改进：

- <xref:System.Windows.Forms.MonthCalendar>控件可以由讲述人，以及其他 UI 自动化工具进行访问。

- <xref:System.Windows.Forms.CheckedListBox>控件时，在项的复选状态已经更改，因此它们已更改的列表项的值会通知用户通知讲述人。
 
- <xref:System.Windows.Forms.DataGridViewCell>控件到讲述人报告正确的只读状态。
 
- 讲述人现在可以读取已禁用<xref:System.Windows.Forms.ToolStripMenuItem>文本，而以前它将跳过禁用的菜单项。

**增强了对 UIAutomation 可访问性模式支持**

从.NET Framework 4.7.1 开始，辅助功能技术工具的开发人员可以利用常见的 API 可访问性模式和多个 WinForms 控件的属性。 这些辅助功能改进包括：

- <xref:System.Windows.Forms.ComboBox>和<xref:System.Windows.Forms.ToolStripSplitButton>现在支持[展开/折叠模式](../ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md)。
 
- <xref:System.Windows.Forms.DataGridViewCheckBoxCell>现在支持[toggle 模式](../ui-automation/implementing-the-ui-automation-toggle-control-pattern.md)。
 
- <xref:System.Windows.Forms.ToolStripItem>控件支持<xref:System.Windows.Automation.AutomationElement.Name>属性和[展开/折叠模式](../ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md)。

- <xref:System.Windows.Forms.NumericUpDown>和<xref:System.Windows.Forms.DomainUpDown>控件支持<xref:System.Windows.Automation.automationElement.Name>属性。

**改进的属性浏览器体验**

从.NET Framework 4.7.1 开始，Windows 窗体包括：

- 更好地键盘通过不同的下拉列表选择窗口的导航。
- 减少不必要的制表位。
- 更好的控件类型的报告。
- 改进了讲述人行为。
 
## <a name="see-also"></a>另请参阅
[什么是.NET Framework 中的新增功能](whats-new.md)   
 