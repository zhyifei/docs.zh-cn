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
ms.openlocfilehash: e6a6759ae285f2dd101bddf71ea8e5ca792e87df
ms.sourcegitcommit: 957c696f25e39f923a827fc3ad5e8ab72768838c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/13/2018
---
# <a name="whats-new-in-accessibility-in-the-net-framework"></a><span data-ttu-id="61edb-102">.NET Framework 中辅助功能的新增功能</span><span class="sxs-lookup"><span data-stu-id="61edb-102">What's new in accessibility in the .NET Framework</span></span>

<span data-ttu-id="61edb-103">.NET Framework 旨在让用户更轻松地使用应用程序。</span><span class="sxs-lookup"><span data-stu-id="61edb-103">The .NET Framework aims at making applications more accessibile for your users.</span></span> <span data-ttu-id="61edb-104">辅助功能使应用程序能够为辅助技术用户提供最佳体验。</span><span class="sxs-lookup"><span data-stu-id="61edb-104">Accessibility features allow an application to provide an appropriate experience for users of Assistive Technology.</span></span> <span data-ttu-id="61edb-105">从 .NET Framework 4.7.1 开始，.NET Framework 包括大量辅助功能改进，使开发人员能够创建易于访问的应用程序。</span><span class="sxs-lookup"><span data-stu-id="61edb-105">Starting with the .NET Framework 4.7.1, the .NET Framework includes a large number of accessibility improvements that allow developers to create accessible applications.</span></span> 

<span data-ttu-id="61edb-106">对于面向 .NET Framework 4.7.1 或更高版本的应用程序，新的辅助功能默认情况下处于启用状态。</span><span class="sxs-lookup"><span data-stu-id="61edb-106">The new accessibility features are enabled by default for applications that target the .NET Framework 4.7.1 or later.</span></span> <span data-ttu-id="61edb-107">此外，对于面向 .NET Framework 早期版本，但在 .NET Framework 4.7.1 或更高版本上运行的应用程序，可通过将以下开关添加到应用程序配置文件 [`<runtime>`](~/docs/framework/configure-apps/file-schema/runtime/index.md) 部分中的 [`<AppContextSwitchOverrides>`](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) 元素来选择取消旧辅助功能行为（因而选择使用 .NET Framework 4.7.1 中的辅助功能改进）。</span><span class="sxs-lookup"><span data-stu-id="61edb-107">In addition, applications that target an earlier version of the .NET Framework but are running on the .NET Framework 4.7.1 or later can opt out of legacy accessibility behaviors (and thereby opt in to the accessibility improvements in the .NET Framework 4.7.1) by adding the following switch to the [`<AppContextSwitchOverrides>`](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) element in the [`<runtime>`](~/docs/framework/configure-apps/file-schema/runtime/index.md) section of the application's configuration file.</span></span> 

```xml
<runtime>
    <!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true|false;key2=true|false  -->
    <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false" />
</runtime>
```

<span data-ttu-id="61edb-108">同样，对于面向 .NET Framework 4.7.1 或更高版本的应用程序，可通过将以下开关添加到应用程序配置文件 [`<runtime>`](~/docs/framework/configure-apps/file-schema/runtime/index.md) 部分中的 [`<AppContextSwitchOverrides>`](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) 来禁用辅助功能。</span><span class="sxs-lookup"><span data-stu-id="61edb-108">Similarly, applications that target versions of the .NET Framework starting with 4.7.1 can disable accessibility features by adding the following switch to the [`<AppContextSwitchOverrides>`](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) element in the [`<runtime>`](~/docs/framework/configure-apps/file-schema/runtime/index.md) section of the application's configuration file.</span></span> 

```xml
<runtime>
    <!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true|false;key2=true|false  -->
    <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=true" />
</runtime>
```

## <a name="whats-new-in-accessibility-in-the-net-framework-471"></a><span data-ttu-id="61edb-109">.NET Framework 4.7.1 中辅助功能的新增功能</span><span class="sxs-lookup"><span data-stu-id="61edb-109">What's new in accessibility in the .NET Framework 4.7.1</span></span>

<span data-ttu-id="61edb-110">.NET Framework 4.7.1 在以下几个领域新增了辅助功能：</span><span class="sxs-lookup"><span data-stu-id="61edb-110">The .NET Framework 4.7.1 includes new accessibility features in the following areas:</span></span>

- [<span data-ttu-id="61edb-111">Windows Presentation Foundation (WPF)</span><span class="sxs-lookup"><span data-stu-id="61edb-111">Windows Presentation Foundation (WPF)</span></span>](#windows-presentation-foundation-wpf)

- [<span data-ttu-id="61edb-112">Windows 窗体</span><span class="sxs-lookup"><span data-stu-id="61edb-112">Windows Forms</span></span>](#windows-forms-accessibility-improvements)

### <a name="windows-presentation-foundation-wpf"></a><span data-ttu-id="61edb-113">Windows Presentation Foundation (WPF)</span><span class="sxs-lookup"><span data-stu-id="61edb-113">Windows Presentation Foundation (WPF)</span></span>

<span data-ttu-id="61edb-114">**屏幕阅读器改进**</span><span class="sxs-lookup"><span data-stu-id="61edb-114">**Screen reader improvements**</span></span>

<span data-ttu-id="61edb-115">如果启用了辅助功能改进，.NET Framework 4.7.1 包括以下可影响屏幕读阅读的增强功能：</span><span class="sxs-lookup"><span data-stu-id="61edb-115">If accessibility improvements are enabled, the .NET Framework 4.7.1 includes the following enhancements that affect screen readers:</span></span>

- <span data-ttu-id="61edb-116">在 .NET Framework 4.7 及更低版本中，<xref:System.Windows.Controls.Expander> 控件由屏幕阅读器宣称为按钮。</span><span class="sxs-lookup"><span data-stu-id="61edb-116">In the .NET Framework 4.7 and earlier versions, <xref:System.Windows.Controls.Expander> controls were announced by screen readers as buttons.</span></span> <span data-ttu-id="61edb-117">从 .NET Framework 4.7.1 开始，它们被正确地称为可展开/可折叠组。</span><span class="sxs-lookup"><span data-stu-id="61edb-117">Starting with the .NET Framework 4.7.1, they are correctly announced as expandable/collapsible groups.</span></span>

- <span data-ttu-id="61edb-118">在 .NET Framework 4.7 及更低版本中，<xref:System.Windows.Controls.DataGridCell> 控件由屏幕阅读器宣称为“自定义”。</span><span class="sxs-lookup"><span data-stu-id="61edb-118">In the .NET Framework 4.7 and earlier versions, <xref:System.Windows.Controls.DataGridCell> controls were announced by screen readers as “custom.”</span></span> <span data-ttu-id="61edb-119">从 .NET Framework 4.7.1 开始，它们被正确地称为数据网格单元格（已本地化）。</span><span class="sxs-lookup"><span data-stu-id="61edb-119">Starting with the .NET Framework 4.7.1, they are now correctly announced as data grid cell (localized).</span></span>
 
- <span data-ttu-id="61edb-120">从 .NET Framework 4.7.1 开始，屏幕阅读器读出可编辑 <xref:System.Windows.Controls.ComboBox> 的名称。</span><span class="sxs-lookup"><span data-stu-id="61edb-120">Starting with the .NET Framework 4.7.1, screen readers announce the name of an editable <xref:System.Windows.Controls.ComboBox>.</span></span>

- <span data-ttu-id="61edb-121">在 .NET Framework 4.7 及更低版本中，<xref:System.Windows.Controls.PasswordBox> 控件被宣称为“视图中没有任何项”或有其他错误行为。</span><span class="sxs-lookup"><span data-stu-id="61edb-121">In the .NET Framework 4.7 and earlier versions, <xref:System.Windows.Controls.PasswordBox> controls were announced as “no item in view” or had otherwise incorrect behavior.</span></span> <span data-ttu-id="61edb-122">此问题已在 .NET Framework 4.7.1 及更高版本中解决。</span><span class="sxs-lookup"><span data-stu-id="61edb-122">This issue is fixed starting with the .NET Framework 4.7.1.</span></span>     

<span data-ttu-id="61edb-123">**UIAutomation LiveRegion 支持**</span><span class="sxs-lookup"><span data-stu-id="61edb-123">**UIAutomation LiveRegion support**</span></span>

<span data-ttu-id="61edb-124">屏幕阅读器（如讲述人）可帮助用户阅读应用程序的 UI 内容，通常通过具有焦点的 UI 内容的文本到语音转换输出实现。</span><span class="sxs-lookup"><span data-stu-id="61edb-124">Screen readers such as Narrator help people read the UI contents of an application, usually by text-to-speech output of the UI content that has the focus.</span></span> <span data-ttu-id="61edb-125">但是，如果 UI 元素更改，并且不具有焦点，则用户可能不会收到通知，并且可能会错过重要信息。</span><span class="sxs-lookup"><span data-stu-id="61edb-125">However, if a UI element changes and does not have the focus, the user may not be notified and may miss important information.</span></span> <span data-ttu-id="61edb-126">活动区域旨在解决此问题。</span><span class="sxs-lookup"><span data-stu-id="61edb-126">Live regions aim at solving this problem.</span></span> <span data-ttu-id="61edb-127">开发人员可使用它们来通知屏幕阅读器或任何其他 UIAutomation 客户端 UI 元素有重要更改。</span><span class="sxs-lookup"><span data-stu-id="61edb-127">A developer can use them to inform the screen reader or any other UIAutomation client that an important change has been made to a UI element.</span></span> <span data-ttu-id="61edb-128">然后，屏幕阅读器可确定向用户通知此更改的方式和时间。</span><span class="sxs-lookup"><span data-stu-id="61edb-128">The screen reader can then decide how and when to inform the user of this change.</span></span> 

<span data-ttu-id="61edb-129">为了支持活动区域，向 WPF 添加了以下 API：</span><span class="sxs-lookup"><span data-stu-id="61edb-129">To support live regions, the following APIs have been added to WPF:</span></span>

- <span data-ttu-id="61edb-130"><xref:System.Windows.Automation.AutomationElementIdentifiers.LiveSettingProperty?displayProperty=nameWithType> 和 <xref:System.Windows.Automation.AutomationElementIdentifiers.LiveRegionChangedEvent?displayProperty=nameWithType> 字段，用于标识 LiveSetting 属性和 LiveRegionChanged 事件。</span><span class="sxs-lookup"><span data-stu-id="61edb-130">The <xref:System.Windows.Automation.AutomationElementIdentifiers.LiveSettingProperty?displayProperty=nameWithType> and <xref:System.Windows.Automation.AutomationElementIdentifiers.LiveRegionChangedEvent?displayProperty=nameWithType> fields, which identify the **LiveSetting** property and the **LiveRegionChanged** event.</span></span> <span data-ttu-id="61edb-131">可通过使用 XAML 来进行设置。</span><span class="sxs-lookup"><span data-stu-id="61edb-131">They can be set by using XAML.</span></span>

- <span data-ttu-id="61edb-132">AutomationProperties.LiveSetting 附加属性，用于向屏幕阅读器通知 UI 更改对用户的重要性。</span><span class="sxs-lookup"><span data-stu-id="61edb-132">The **AutomationProperties.LiveSetting** attached property, which informs the screen reader of the importance of the UI change to the user.</span></span>

- <span data-ttu-id="61edb-133"><xref:System.Windows.Automation.AutomationProperties.LiveSettingProperty?displayProperty=nameWithType> 属性，用于标识 AutomationProperties.LiveSetting 附加属性。</span><span class="sxs-lookup"><span data-stu-id="61edb-133">The <xref:System.Windows.Automation.AutomationProperties.LiveSettingProperty?displayProperty=nameWithType> property, which identifies the **AutomationProperties.LiveSetting** attached property.</span></span>
 
- <span data-ttu-id="61edb-134"><xref:System.Windows.Automation.Peers.AutomationPeer.GetLiveSettingCore%2A?displayProperty=nameWithType> 方法，可替代该方法以提供 LiveSetting 值。</span><span class="sxs-lookup"><span data-stu-id="61edb-134">The <xref:System.Windows.Automation.Peers.AutomationPeer.GetLiveSettingCore%2A?displayProperty=nameWithType> method, which can be overridden to provide a **LiveSetting** value.</span></span>

- <span data-ttu-id="61edb-135"><xref:System.Windows.Automation.AutomationProperties.GetLiveSetting%2A?displayProperty=nameWithType> 和 <xref:System.Windows.Automation.AutomationProperties.SetLiveSetting%2A?displayProperty=nameWithType> 方法，用于获取和设置 LiveSetting 值。</span><span class="sxs-lookup"><span data-stu-id="61edb-135">The <xref:System.Windows.Automation.AutomationProperties.GetLiveSetting%2A?displayProperty=nameWithType> and <xref:System.Windows.Automation.AutomationProperties.SetLiveSetting%2A?displayProperty=nameWithType> methods, which get and set a **LiveSetting** value.</span></span>
 
- <span data-ttu-id="61edb-136"><xref:System.Windows.Automation.AutomationLiveSetting?displayProperty=nameWithType> 枚举，用于定义以下可能的 LiveSetting 值：</span><span class="sxs-lookup"><span data-stu-id="61edb-136">The <xref:System.Windows.Automation.AutomationLiveSetting?displayProperty=nameWithType> enumeration, which defines the following possible **LiveSetting** values:</span></span>

   - <span data-ttu-id="61edb-137"><xref:System.Windows.Automation.AutomationLiveSetting.Off?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="61edb-137"><xref:System.Windows.Automation.AutomationLiveSetting.Off?displayProperty=nameWithType>.</span></span> <span data-ttu-id="61edb-138">如果活动区域的内容已更改，则该元素不会发送通知。</span><span class="sxs-lookup"><span data-stu-id="61edb-138">The element does not send notifications if the content of the live region has changed.</span></span>   
   - <span data-ttu-id="61edb-139"><xref:System.Windows.Automation.AutomationLiveSetting.Polite?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="61edb-139"><xref:System.Windows.Automation.AutomationLiveSetting.Polite?displayProperty=nameWithType>.</span></span> <span data-ttu-id="61edb-140">如果活动区域的内容已更改，则该元素将发送非中断通知。</span><span class="sxs-lookup"><span data-stu-id="61edb-140">The element sends non-interruptive notifications if the content of the live region has changed.</span></span>   

  - <span data-ttu-id="61edb-141"><xref:System.Windows.Automation.AutomationLiveSetting.Assertive?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="61edb-141"><xref:System.Windows.Automation.AutomationLiveSetting.Assertive?displayProperty=nameWithType>.</span></span> <span data-ttu-id="61edb-142">如果活动区域的内容已更改，则该元素将发送中断通知。</span><span class="sxs-lookup"><span data-stu-id="61edb-142">The element sends interruptive notifications if the content of the live region has changed.</span></span>   

<span data-ttu-id="61edb-143">可通过对相关元素设置 AutomationProperties.LiveSetting 属性来创建 LiveRegion，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="61edb-143">You can create a LiveRegion by setting the **AutomationProperties.LiveSetting** property on the element of interest, as shown in the following example:</span></span>   

```xaml
<TextBlock Name="myTextBlock" AutomationProperties.LiveSetting="Assertive">announcement</TextBlock>
```

<span data-ttu-id="61edb-144">活动区域中的数据发生更改，并且需要通知屏幕阅读器时，可显式引发事件，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="61edb-144">When the data in the live region changes and you need to inform a screen reader, you explicitly raise an event, as shown in the following sample.</span></span>

```csharp
var peer = FrameworkElementAutomationPeer.FromElement(myTextBlock);

peer.RaiseAutomationEvent(AutomationEvents.LiveRegionChanged);
```
```vb
Dim peer = FrameworkElementAutomationPeer.FromElement(myTextBlock)
peer.RaiseAutomationEvent(AutomationEvents.LiveRegionChanged)

```

<span data-ttu-id="61edb-145">**高对比度**</span><span class="sxs-lookup"><span data-stu-id="61edb-145">**High contrast**</span></span>

<span data-ttu-id="61edb-146">从 .NET Framework 4.7.1 开始，对多种 WPF 控件进行了高对比度改进。</span><span class="sxs-lookup"><span data-stu-id="61edb-146">Starting with the .NET Framework 4.7.1, improvements in high contrast have been made to various WPF controls.</span></span> <span data-ttu-id="61edb-147">可在设置 <xref:System.Windows.SystemParameters.HighContrast%2A> 主题后看到这些改进。</span><span class="sxs-lookup"><span data-stu-id="61edb-147">They are now visible when the <xref:System.Windows.SystemParameters.HighContrast%2A> theme is set.</span></span> <span data-ttu-id="61edb-148">这些方法包括：</span><span class="sxs-lookup"><span data-stu-id="61edb-148">These include:</span></span>

- <span data-ttu-id="61edb-149"><xref:System.Windows.Controls.Expander> 控件</span><span class="sxs-lookup"><span data-stu-id="61edb-149"><xref:System.Windows.Controls.Expander> control</span></span>

    <span data-ttu-id="61edb-150"><xref:System.Windows.Controls.Expander> 控件的焦点视觉对象现在可见。</span><span class="sxs-lookup"><span data-stu-id="61edb-150">The focus visual for the  <xref:System.Windows.Controls.Expander> control is now visible.</span></span> <span data-ttu-id="61edb-151"><xref:System.Windows.Controls.ComboBox>、<xref:System.Windows.Controls.ListBox> 和 <xref:System.Windows.Controls.RadioButton> 控件的键盘视觉对象也可见。</span><span class="sxs-lookup"><span data-stu-id="61edb-151">The keyboard visuals for <xref:System.Windows.Controls.ComboBox>,<xref:System.Windows.Controls.ListBox>, and <xref:System.Windows.Controls.RadioButton> controls are visible as well.</span></span> <span data-ttu-id="61edb-152">例如:</span><span class="sxs-lookup"><span data-stu-id="61edb-152">For example:</span></span>

    <span data-ttu-id="61edb-153">在此之前:</span><span class="sxs-lookup"><span data-stu-id="61edb-153">Before:</span></span> 
    
    ![辅助功能改进前具有焦点的 Expander 控件](media/expander-before.png)

    <span data-ttu-id="61edb-155">之后：</span><span class="sxs-lookup"><span data-stu-id="61edb-155">After:</span></span> 

    ![辅助功能改进后具有焦点的 Expander 控件](media/expander-after.png)

- <span data-ttu-id="61edb-157"><xref:System.Windows.Controls.CheckBox> 和 <xref:System.Windows.Controls.RadioButton> 控件</span><span class="sxs-lookup"><span data-stu-id="61edb-157"><xref:System.Windows.Controls.CheckBox> and <xref:System.Windows.Controls.RadioButton> controls</span></span>
 
    <span data-ttu-id="61edb-158">在高对比度主题下选中时，<xref:System.Windows.Controls.CheckBox> 和 <xref:System.Windows.Controls.RadioButton> 控件中的文本更易于查看。</span><span class="sxs-lookup"><span data-stu-id="61edb-158">The text in the <xref:System.Windows.Controls.CheckBox> and <xref:System.Windows.Controls.RadioButton> controls is now easier to see when selected in high contrast themes.</span></span> <span data-ttu-id="61edb-159">例如:</span><span class="sxs-lookup"><span data-stu-id="61edb-159">For example:</span></span>

    <span data-ttu-id="61edb-160">在此之前:</span><span class="sxs-lookup"><span data-stu-id="61edb-160">Before:</span></span> 

    ![辅助功能改进前具有焦点的高对比度单选按钮](media/radio-button-before.png)
    
    <span data-ttu-id="61edb-162">之后：</span><span class="sxs-lookup"><span data-stu-id="61edb-162">After:</span></span> 

    ![辅助功能改进后具有焦点的高对比度单选按钮](media/radio-button-after.png)

- <span data-ttu-id="61edb-164"><xref:System.Windows.Controls.ComboBox> 控件</span><span class="sxs-lookup"><span data-stu-id="61edb-164"><xref:System.Windows.Controls.ComboBox> control</span></span>
 
    <span data-ttu-id="61edb-165">从 .NET Framework 4.7.1 开始，已禁用的 <xref:System.Windows.Controls.ComboBox> 控件的边框与禁用的文本颜色相同。</span><span class="sxs-lookup"><span data-stu-id="61edb-165">Starting with the .NET Framework 4.7.1, the border of a disabled <xref:System.Windows.Controls.ComboBox> control is the same color as disabled text.</span></span> <span data-ttu-id="61edb-166">例如:</span><span class="sxs-lookup"><span data-stu-id="61edb-166">For example:</span></span>
    
    <span data-ttu-id="61edb-167">在此之前:</span><span class="sxs-lookup"><span data-stu-id="61edb-167">Before:</span></span> 

     ![辅助功能改进前禁用的 ComboBox 边框和文本](media/combo-disabled-before.png)

    <span data-ttu-id="61edb-169">之后：</span><span class="sxs-lookup"><span data-stu-id="61edb-169">After:</span></span>   

     ![辅助功能改进后禁用的 ComboBox 边框和文本](media/combo-disabled-after.png)

    <span data-ttu-id="61edb-171">此外，已禁用的按钮和具有焦点的按钮使用正确的主题颜色。</span><span class="sxs-lookup"><span data-stu-id="61edb-171">In addition, disabled and focused buttons use the correct theme color.</span></span>

    <span data-ttu-id="61edb-172">在此之前:</span><span class="sxs-lookup"><span data-stu-id="61edb-172">Before:</span></span>

    ![辅助功能改进前的按钮主题颜色](media/button-themes-before.png) 
    
    <span data-ttu-id="61edb-174">之后：</span><span class="sxs-lookup"><span data-stu-id="61edb-174">After:</span></span> 

    ![辅助功能改进后的按钮主题颜色](media/button-themes-after.png) 

    <span data-ttu-id="61edb-176">最后，在 .NET Framework 4.7 及更低版本中，将 <xref:System.Windows.Controls.ComboBox> 控件的样式设置为 `Toolbar.ComboBoxStyleKey` 会导致下拉箭头不可见。</span><span class="sxs-lookup"><span data-stu-id="61edb-176">Finally, in the .NET Framework 4.7 and earlier versions, setting a <xref:System.Windows.Controls.ComboBox> control’s style to `Toolbar.ComboBoxStyleKey` caused the drop-down arrow to be invisible.</span></span> <span data-ttu-id="61edb-177">此问题已在 .NET Framework 4.7.1 及更高版本中解决。</span><span class="sxs-lookup"><span data-stu-id="61edb-177">This issue is fixed starting with the .NET Framework 4.7.1.</span></span> <span data-ttu-id="61edb-178">例如:</span><span class="sxs-lookup"><span data-stu-id="61edb-178">For example:</span></span>

    <span data-ttu-id="61edb-179">在此之前:</span><span class="sxs-lookup"><span data-stu-id="61edb-179">Before:</span></span> 

    ![辅助功能改进前的 Toolbar.ComboBoxStyleKey](media/comboboxstylekey-before.png) 
    
    <span data-ttu-id="61edb-181">之后：</span><span class="sxs-lookup"><span data-stu-id="61edb-181">After:</span></span> 

    ![辅助功能改进后的 Toolbar.ComboBoxStyleKey](media/comboboxstylekey-after.png) 

- <span data-ttu-id="61edb-183"><xref:System.Windows.Controls.DataGrid> 控件</span><span class="sxs-lookup"><span data-stu-id="61edb-183"><xref:System.Windows.Controls.DataGrid> control</span></span>

    <span data-ttu-id="61edb-184">从 .NET Framework 4.7.1 开始，<xref:System.Windows.Controls.DataGrid> 控件中的排序指示符箭头现在使用正确的主题颜色。</span><span class="sxs-lookup"><span data-stu-id="61edb-184">Starting with the .NET Framework 4.7.1, the sort indicator arrow in <xref:System.Windows.Controls.DataGrid> controls now uses correct theme colors.</span></span> <span data-ttu-id="61edb-185">例如:</span><span class="sxs-lookup"><span data-stu-id="61edb-185">For example:</span></span>

    <span data-ttu-id="61edb-186">在此之前:</span><span class="sxs-lookup"><span data-stu-id="61edb-186">Before:</span></span> 

    ![辅助功能改进前的排序指示符箭头](media/sort-indicator-before.png) 
    
    <span data-ttu-id="61edb-188">之后：</span><span class="sxs-lookup"><span data-stu-id="61edb-188">After:</span></span>   
 
    ![辅助功能改进后的排序指示符箭头](media/sort-indicator-after.png) 
    
    <span data-ttu-id="61edb-190">此外，在 .NET Framework 4.7 及更低版本中，在高对比度模式下，默认链接样式在鼠标悬停在其上时更改为不正确的颜色。</span><span class="sxs-lookup"><span data-stu-id="61edb-190">In addition, in the .NET Framework 4.7 and earlier versions, the default link style changed to an incorrect color on mouse over in high contrast modes.</span></span> <span data-ttu-id="61edb-191">此问题已在 .NET Framework 4.7.1 及更高版本中解决。</span><span class="sxs-lookup"><span data-stu-id="61edb-191">This is resolved starting with the .NET Framework 4.7.1.</span></span> <span data-ttu-id="61edb-192">同样，从 .NET Framework 4.7.1 开始，<xref:System.Windows.Controls.DataGrid> 复选框列对键盘焦点反馈使用预期的颜色。</span><span class="sxs-lookup"><span data-stu-id="61edb-192">Similarly, <xref:System.Windows.Controls.DataGrid> checkbox columns uses the expected colors for keyboard focus feedback starting with the .NET Framework 4.7.1.</span></span>

    <span data-ttu-id="61edb-193">在此之前:</span><span class="sxs-lookup"><span data-stu-id="61edb-193">Before:</span></span> 

    ![辅助功能改进前的 DataGrid 默认链接样式](media/default-link-style-before.png) 
 
    <span data-ttu-id="61edb-195">之后：</span><span class="sxs-lookup"><span data-stu-id="61edb-195">After:</span></span>    
  
    ![辅助功能改进后的 DataGrid 默认链接样式](media/default-link-style-after.png)  

<span data-ttu-id="61edb-197">有关 .NET Framework 4.7.1 中 WPF 辅助功能改进的详细信息，请参阅 [WPF 辅助功能改进](../migration-guide/retargeting/4.7-4.7.1.md#accessibility-improvements-in-wpf)。</span><span class="sxs-lookup"><span data-stu-id="61edb-197">For more information on WPF accessibility improvements in the .NET Framework 4.7.1, see [Accessibility improvements in WPF](../migration-guide/retargeting/4.7-4.7.1.md#accessibility-improvements-in-wpf).</span></span>

## <a name="windows-forms-accessibility-improvements"></a><span data-ttu-id="61edb-198">Windows 窗体辅助功能改进</span><span class="sxs-lookup"><span data-stu-id="61edb-198">Windows Forms accessibility improvements</span></span>

<span data-ttu-id="61edb-199">在 .NET Framework 4.7.1 中，Windows 窗体 (WinForms) 包括以下几个方面的辅助功能改进。</span><span class="sxs-lookup"><span data-stu-id="61edb-199">In the .NET Framework 4.7.1, Windows Forms (WinForms) includes accessibility changes in the following areas.</span></span>

<span data-ttu-id="61edb-200">**改进了高对比度模式下的显示**</span><span class="sxs-lookup"><span data-stu-id="61edb-200">**Improved display in High Contrast mode**</span></span>

<span data-ttu-id="61edb-201">从 .NET Framework 4.7.1 开始，多种 WinForms 控件改进了高对比度模式下在操作系统中的呈现方式。</span><span class="sxs-lookup"><span data-stu-id="61edb-201">Starting with the .NET Framework 4.7.1, various WinForms controls offer improved rendering in the HighContrast modes available in the operating system.</span></span> <span data-ttu-id="61edb-202">Windows 10 更改了一些高对比度系统颜色的值，而 Windows 窗体基于 Windows 10 Win32 框架。</span><span class="sxs-lookup"><span data-stu-id="61edb-202">Windows 10 has changed the values for some high contrast system colors, and Windows Forms is based on the Windows 10 Win32 framework.</span></span> <span data-ttu-id="61edb-203">为获得最佳体验，请运行最新版本的 Windows，并通过在测试应用程序中添加 app.manifest 文件选择使用最新的 OS 更改，同时取消注释 Windows 10 支持的 OS 行，最终结果如下所示：</span><span class="sxs-lookup"><span data-stu-id="61edb-203">For the best experience, run on the latest version of Windows and opt in to the latest OS changes by adding an app.manifest file in a test application and un-comment the Windows 10 supported OS  line so that it looks the following:</span></span>

```xml
<!– Windows 10 –>
<supportedOS Id=”{8e0f7a12-bfb3-4fe8-b9a5-48fd50a15a9a}” />
```
<span data-ttu-id="61edb-204">高对比度更改的一些示例包括：</span><span class="sxs-lookup"><span data-stu-id="61edb-204">Some examples of high contrast changes include:</span></span>

- <span data-ttu-id="61edb-205"><xref:System.Windows.Forms.MenuStrip> 项中的复选标记更易于查看。</span><span class="sxs-lookup"><span data-stu-id="61edb-205">Checkmarks in <xref:System.Windows.Forms.MenuStrip> items are easier to view.</span></span>

- <span data-ttu-id="61edb-206">选中后，禁用的 <xref:System.Windows.Forms.MenuStrip> 项更易于查看。</span><span class="sxs-lookup"><span data-stu-id="61edb-206">When selected, disabled <xref:System.Windows.Forms.MenuStrip> items are easier to view.</span></span>

- <span data-ttu-id="61edb-207">所选 <xref:System.Windows.Forms.Button> 控件中的文本与选中颜色形成鲜明对比。</span><span class="sxs-lookup"><span data-stu-id="61edb-207">Text in a selected <xref:System.Windows.Forms.Button> control contrasts with the selection color.</span></span>

- <span data-ttu-id="61edb-208">禁用的文本更易于阅读。</span><span class="sxs-lookup"><span data-stu-id="61edb-208">Disabled text is easier to read.</span></span> <span data-ttu-id="61edb-209">例如:</span><span class="sxs-lookup"><span data-stu-id="61edb-209">For example:</span></span>

    <span data-ttu-id="61edb-210">在此之前:</span><span class="sxs-lookup"><span data-stu-id="61edb-210">Before:</span></span>

    ![辅助功能改进前禁用的文本](media/wf-disabled-before.png) 

    <span data-ttu-id="61edb-212">之后：</span><span class="sxs-lookup"><span data-stu-id="61edb-212">After:</span></span>

    ![辅助功能改进后禁用的文本](media/wf-disabled-after.png) 

- <span data-ttu-id="61edb-214">“线程异常”对话框中的高对比度改进。</span><span class="sxs-lookup"><span data-stu-id="61edb-214">High contrast improvements in the Thread Exception Dialog.</span></span>

<span data-ttu-id="61edb-215">**改进了讲述人支持**</span><span class="sxs-lookup"><span data-stu-id="61edb-215">**Improved Narrator support**</span></span>

<span data-ttu-id="61edb-216">.NET Framework 4.7.1 中的 Windows 窗体对讲述人进行了以下辅助功改进：</span><span class="sxs-lookup"><span data-stu-id="61edb-216">Windows Forms in the .NET Framework 4.7.1 includes the following accessibility improvements for the Narrator:</span></span>

- <span data-ttu-id="61edb-217">讲述人以及其他 UI 自动化工具可访问 <xref:System.Windows.Forms.MonthCalendar> 控件。</span><span class="sxs-lookup"><span data-stu-id="61edb-217">The <xref:System.Windows.Forms.MonthCalendar> control can be accessed by the Narrator, as well as by other UI automation tools.</span></span>

- <span data-ttu-id="61edb-218">当某个项的选中状态更改时，<xref:System.Windows.Forms.CheckedListBox> 控件会通知讲述人，因此用户可获知更改了列表项的值。</span><span class="sxs-lookup"><span data-stu-id="61edb-218">The <xref:System.Windows.Forms.CheckedListBox> control notifies Narrator when an item's check state has changed so the user is notified that they’ve changed the value of a list item.</span></span>
 
- <span data-ttu-id="61edb-219"><xref:System.Windows.Forms.DataGridViewCell> 控件向讲述人报告正确的只读状态。</span><span class="sxs-lookup"><span data-stu-id="61edb-219">The <xref:System.Windows.Forms.DataGridViewCell> control reports the correct read-only status to Narrator.</span></span>
 
- <span data-ttu-id="61edb-220">讲述人现在可以阅读已禁用的 <xref:System.Windows.Forms.ToolStripMenuItem> 文本，而以前它会跳过禁用的菜单项。</span><span class="sxs-lookup"><span data-stu-id="61edb-220">Narrator can now read disabled <xref:System.Windows.Forms.ToolStripMenuItem> text, whereas previously it would skip over disabled menu items.</span></span>

<span data-ttu-id="61edb-221">**增强了对 UIAutomation 辅助功能模式的支持**</span><span class="sxs-lookup"><span data-stu-id="61edb-221">**Enhanced support for UIAutomation accessibility patterns**</span></span>

<span data-ttu-id="61edb-222">从 .NET Framework 4.7.1 开始，辅助功能技术工具的开发人员可以利用常见的 API 辅助功能模式和多个 WinForms 控件的属性。</span><span class="sxs-lookup"><span data-stu-id="61edb-222">Starting with the .NET Framework 4.7.1, developers of accessibility technology tools can leverage common API accessibility patterns and properties for several WinForms controls.</span></span> <span data-ttu-id="61edb-223">这些辅助功能改进包括：</span><span class="sxs-lookup"><span data-stu-id="61edb-223">These accessibility improvements include:</span></span>

- <span data-ttu-id="61edb-224"><xref:System.Windows.Forms.ComboBox> 和 <xref:System.Windows.Forms.ToolStripSplitButton> 现在支持[展开/折叠模式](../ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md)。</span><span class="sxs-lookup"><span data-stu-id="61edb-224">The <xref:System.Windows.Forms.ComboBox> and <xref:System.Windows.Forms.ToolStripSplitButton> now support the [expand/collapse pattern](../ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md).</span></span>
 
- <span data-ttu-id="61edb-225"><xref:System.Windows.Forms.DataGridViewCheckBoxCell> 现在支持[切换模式](../ui-automation/implementing-the-ui-automation-toggle-control-pattern.md)。</span><span class="sxs-lookup"><span data-stu-id="61edb-225">The <xref:System.Windows.Forms.DataGridViewCheckBoxCell> now supports the [toggle pattern](../ui-automation/implementing-the-ui-automation-toggle-control-pattern.md).</span></span>
 
- <span data-ttu-id="61edb-226"><xref:System.Windows.Forms.ToolStripItem> 控件支持 <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.Name> 属性和[展开/折叠模式](../ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md)。</span><span class="sxs-lookup"><span data-stu-id="61edb-226">The <xref:System.Windows.Forms.ToolStripItem> control supports the <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.Name> property and the [expand/collapse pattern](../ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md).</span></span>

- <span data-ttu-id="61edb-227"><xref:System.Windows.Forms.NumericUpDown> 和 <xref:System.Windows.Forms.DomainUpDown> 控件支持 <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.Name> 属性。</span><span class="sxs-lookup"><span data-stu-id="61edb-227">The <xref:System.Windows.Forms.NumericUpDown> and <xref:System.Windows.Forms.DomainUpDown> controls support the <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.Name> property.</span></span>

<span data-ttu-id="61edb-228">**改进了属性浏览器体验**</span><span class="sxs-lookup"><span data-stu-id="61edb-228">**Improved property browser experience**</span></span>

<span data-ttu-id="61edb-229">从 .NET Framework 4.7.1 开始，Windows 窗体包括以下改进：</span><span class="sxs-lookup"><span data-stu-id="61edb-229">Starting with the .NET Framework 4.7.1, Windows Forms includes:</span></span>

- <span data-ttu-id="61edb-230">更好地通过各种下拉选择窗口使用键盘导航。</span><span class="sxs-lookup"><span data-stu-id="61edb-230">Better keyboard navigation through the various drop-down selection windows.</span></span>
- <span data-ttu-id="61edb-231">减少不必要的制表位。</span><span class="sxs-lookup"><span data-stu-id="61edb-231">A reduction of unnecessary tab stops.</span></span>
- <span data-ttu-id="61edb-232">更好地报告控件类型。</span><span class="sxs-lookup"><span data-stu-id="61edb-232">Better reporting of control types.</span></span>
- <span data-ttu-id="61edb-233">改进了讲述人行为。</span><span class="sxs-lookup"><span data-stu-id="61edb-233">Improved narrator behavior.</span></span>
 
## <a name="see-also"></a><span data-ttu-id="61edb-234">请参阅</span><span class="sxs-lookup"><span data-stu-id="61edb-234">See Also</span></span>
[<span data-ttu-id="61edb-235">.NET Framework 的新增功能</span><span class="sxs-lookup"><span data-stu-id="61edb-235">What's new in the .NET Framework</span></span>](whats-new.md)   
 