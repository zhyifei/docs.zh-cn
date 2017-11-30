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
# <a name="whats-new-in-accessibility-in-the-net-framework"></a><span data-ttu-id="98d7f-102">.NET Framework 中的辅助功能的新增功能</span><span class="sxs-lookup"><span data-stu-id="98d7f-102">What's new in accessibility in the .NET Framework</span></span>

<span data-ttu-id="98d7f-103">.NET Framework 的目的是使多个 accessibile 为你的用户的应用程序。</span><span class="sxs-lookup"><span data-stu-id="98d7f-103">The .NET Framework aims at making applications more accessibile for your users.</span></span> <span data-ttu-id="98d7f-104">辅助功能允许应用程序的辅助技术的用户提供的适当的体验。</span><span class="sxs-lookup"><span data-stu-id="98d7f-104">Accessibility features allow an application to provide an appropriate experience for users of Assistive Technology.</span></span> <span data-ttu-id="98d7f-105">从.NET Framework 4.7.1 开始，.NET Framework 包括大量的可访问性改进功能的允许开发人员创建可访问应用程序。</span><span class="sxs-lookup"><span data-stu-id="98d7f-105">Starting with the .NET Framework 4.7.1, the .NET Framework includes a large number of accessibility improvements that allow developers to create accessible applications.</span></span> 

<span data-ttu-id="98d7f-106">新的辅助功能已启用默认情况下，对于面向.NET Framework 4.7.1 的应用程序或更高版本。</span><span class="sxs-lookup"><span data-stu-id="98d7f-106">The new accessibility features are enabled by default for applications that target the .NET Framework 4.7.1 or later.</span></span> <span data-ttu-id="98d7f-107">此外，面向.NET Framework 的早期版本，但在.NET Framework 4.7.1 上运行或更高版本可以选择的应用程序的旧的可访问性行为 （和从而参与到.NET Framework 4.7.1 中的可访问性改进） 通过添加以下切换到[ `<AppContextSwitchOverrides>` ](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md)中的元素[ `<runtime>` ](~/docs/framework/configure-apps/file-schema/runtime/index.md)应用程序的配置文件节。</span><span class="sxs-lookup"><span data-stu-id="98d7f-107">In addition, applications that target an earlier version of the .NET Framework but are running on the .NET Framework 4.7.1 or later can opt out of legacy accessibility behaviors (and thereby opt in to the accessibility improvements in the .NET Framework 4.7.1) by adding the following switch to the [`<AppContextSwitchOverrides>`](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) element in the [`<runtime>`](~/docs/framework/configure-apps/file-schema/runtime/index.md) section of the application's configuration file.</span></span> 

```xml
<runtime>
    <!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true|false;key2=true|false  -->
    <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false" />
</runtime>
```

<span data-ttu-id="98d7f-108">同样，开头 4.7.1.NET Framework 目标版本的应用程序可禁用辅助功能，通过添加以下切换到[ `<AppContextSwitchOverrides>` ](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md)中的元素[ `<runtime>` ](~/docs/framework/configure-apps/file-schema/runtime/index.md)应用程序的配置文件节。</span><span class="sxs-lookup"><span data-stu-id="98d7f-108">Similarly, applications that target versions of the .NET Framework starting with 4.7.1 can disable accessibility features by adding the following switch to the [`<AppContextSwitchOverrides>`](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) element in the [`<runtime>`](~/docs/framework/configure-apps/file-schema/runtime/index.md) section of the application's configuration file.</span></span> 

```xml
<runtime>
    <!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true|false;key2=true|false  -->
    <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=true" />
</runtime>
```

## <a name="whats-new-in-accessibility-in-the-net-framework-471"></a><span data-ttu-id="98d7f-109">.NET Framework 4.7.1 中的辅助功能的新增功能</span><span class="sxs-lookup"><span data-stu-id="98d7f-109">What's new in accessibility in the .NET Framework 4.7.1</span></span>

<span data-ttu-id="98d7f-110">.NET Framework 4.7.1 包括以下区域中的新辅助功能：</span><span class="sxs-lookup"><span data-stu-id="98d7f-110">The .NET Framework 4.7.1 includes new accessibility features in the following areas:</span></span>

- [<span data-ttu-id="98d7f-111">Windows Presentation Foundation (WPF)</span><span class="sxs-lookup"><span data-stu-id="98d7f-111">Windows Presentation Foundation (WPF)</span></span>](#windows-presentation-foundation-wpf)

- [<span data-ttu-id="98d7f-112">Windows 窗体</span><span class="sxs-lookup"><span data-stu-id="98d7f-112">Windows Forms</span></span>](#windows-forms-accessibility-improvements)

### <a name="windows-presentation-foundation-wpf"></a><span data-ttu-id="98d7f-113">Windows Presentation Foundation (WPF)</span><span class="sxs-lookup"><span data-stu-id="98d7f-113">Windows Presentation Foundation (WPF)</span></span>

<span data-ttu-id="98d7f-114">**屏幕读取器改进**</span><span class="sxs-lookup"><span data-stu-id="98d7f-114">**Screen reader improvements**</span></span>

<span data-ttu-id="98d7f-115">如果启用了可访问性改进，.NET Framework 4.7.1 包括影响屏幕读取器的以下增强功能：</span><span class="sxs-lookup"><span data-stu-id="98d7f-115">If accessibility improvements are enabled, the .NET Framework 4.7.1 includes the following enhancements that affect screen readers:</span></span>

- <span data-ttu-id="98d7f-116">在.NET Framework 4.7 和早期版本中，<xref:System.Windows.Controls.Expander>控件已宣布为按钮的屏幕读取器。</span><span class="sxs-lookup"><span data-stu-id="98d7f-116">In the .NET Framework 4.7 and earlier versions, <xref:System.Windows.Controls.Expander> controls were announced by screen readers as buttons.</span></span> <span data-ttu-id="98d7f-117">从.NET Framework 4.7.1 开始，正确上公布它们作为可展开/折叠组。</span><span class="sxs-lookup"><span data-stu-id="98d7f-117">Starting with the .NET Framework 4.7.1, they are correctly announced as expandable/collapsible groups.</span></span>

- <span data-ttu-id="98d7f-118">在.NET Framework 4.7 和早期版本中，<xref:System.Windows.Controls.DataGridCell>控件已宣布屏幕读取器，为"custom"。</span><span class="sxs-lookup"><span data-stu-id="98d7f-118">In the .NET Framework 4.7 and earlier versions, <xref:System.Windows.Controls.DataGridCell> controls were announced by screen readers as “custom.”</span></span> <span data-ttu-id="98d7f-119">从.NET Framework 4.7.1 开始，现在正确上公布它们与数据网格单元格 （本地化）。</span><span class="sxs-lookup"><span data-stu-id="98d7f-119">Starting with the .NET Framework 4.7.1, they are now correctly announced as data grid cell (localized).</span></span>
 
- <span data-ttu-id="98d7f-120">从.NET Framework 4.7.1 开始，屏幕阅读器宣告的可编辑名称<xref:System.Windows.Controls.ComboBox>。</span><span class="sxs-lookup"><span data-stu-id="98d7f-120">Starting with the .NET Framework 4.7.1, screen readers announce the name of an editable <xref:System.Windows.Controls.ComboBox>.</span></span>

- <span data-ttu-id="98d7f-121">在.NET Framework 4.7 和早期版本中，<xref:System.Windows.Controls.PasswordBox>控件已宣布为"视图中没有项"或具有否则为不正确的行为。</span><span class="sxs-lookup"><span data-stu-id="98d7f-121">In the .NET Framework 4.7 and earlier versions, <xref:System.Windows.Controls.PasswordBox> controls were announced as “no item in view” or had otherwise incorrect behavior.</span></span> <span data-ttu-id="98d7f-122">从.NET Framework 4.7.1 开始修复此问题。</span><span class="sxs-lookup"><span data-stu-id="98d7f-122">This issue is fixed starting with the .NET Framework 4.7.1.</span></span>     

<span data-ttu-id="98d7f-123">**UIAutomation LiveRegion 支持**</span><span class="sxs-lookup"><span data-stu-id="98d7f-123">**UIAutomation LiveRegion support**</span></span>

<span data-ttu-id="98d7f-124">如讲述人帮助人员屏幕读取器读取应用程序的 UI 内容通常具有焦点的 UI 内容的文本到语音转换输出。</span><span class="sxs-lookup"><span data-stu-id="98d7f-124">Screen readers such as Narrator help people read the UI contents of an application, usually by text-to-speech output of the UI content that has the focus.</span></span> <span data-ttu-id="98d7f-125">但是，如果 UI 元素更改，并且不具有焦点，则用户可能不会收到通知，并且可能会丢失重要信息。</span><span class="sxs-lookup"><span data-stu-id="98d7f-125">However, if a UI element changes and does not have the focus, the user may not be notified and may miss important information.</span></span> <span data-ttu-id="98d7f-126">在解决此问题的目标是实时的区域。</span><span class="sxs-lookup"><span data-stu-id="98d7f-126">Live regions aim at solving this problem.</span></span> <span data-ttu-id="98d7f-127">开发人员可以将其用作屏幕阅读器或对 UI 元素进行了重要更改任何其他 UIAutomation 客户端。</span><span class="sxs-lookup"><span data-stu-id="98d7f-127">A developer can use them to inform the screen reader or any other UIAutomation client that an important change has been made to a UI element.</span></span> <span data-ttu-id="98d7f-128">屏幕读取器然后可决定何时以及如何通知用户此更改。</span><span class="sxs-lookup"><span data-stu-id="98d7f-128">The screen reader can then decide how and when to inform the user of this change.</span></span> 

<span data-ttu-id="98d7f-129">若要支持实时区域，以下 Api 已添加到 WPF:</span><span class="sxs-lookup"><span data-stu-id="98d7f-129">To support live regions, the following APIs have been added to WPF:</span></span>

- <span data-ttu-id="98d7f-130"><xref:System.Windows.Automation.AutomationElementIdentifiers.LiveSettingProperty?displayProperty=nameWithType>和<xref:System.Windows.Automation.AutomationElementIdentifiers.LiveRegionChangedEvent?displayProperty=nameWithType>字段，标识**LiveSetting**属性和**LiveRegionChanged**事件。</span><span class="sxs-lookup"><span data-stu-id="98d7f-130">The <xref:System.Windows.Automation.AutomationElementIdentifiers.LiveSettingProperty?displayProperty=nameWithType> and <xref:System.Windows.Automation.AutomationElementIdentifiers.LiveRegionChangedEvent?displayProperty=nameWithType> fields, which identify the **LiveSetting** property and the **LiveRegionChanged** event.</span></span> <span data-ttu-id="98d7f-131">它们可以通过使用 XAML 设置。</span><span class="sxs-lookup"><span data-stu-id="98d7f-131">They can be set by using XAML.</span></span>

- <span data-ttu-id="98d7f-132">**AutomationProperties.LiveSetting**附加属性，用于通知的重要性对用户的用户界面更改屏幕读取器。</span><span class="sxs-lookup"><span data-stu-id="98d7f-132">The **AutomationProperties.LiveSetting** attached property, which informs the screen reader of the importance of the UI change to the user.</span></span>

- <span data-ttu-id="98d7f-133"><xref:System.Windows.Automation.AutomationProperties.LiveSettingProperty?displayProperty=nameWithType>属性，它标识**AutomationProperties.LiveSetting**附加属性。</span><span class="sxs-lookup"><span data-stu-id="98d7f-133">The <xref:System.Windows.Automation.AutomationProperties.LiveSettingProperty?displayProperty=nameWithType> property, which identifies the **AutomationProperties.LiveSetting** attached property.</span></span>
 
- <span data-ttu-id="98d7f-134"><xref:System.Windows.Automation.Peers.AutomationPeer.GetLiveSettingCore%2A?displayProperty=nameWithType>方法，可以重写以提供**LiveSetting**值。</span><span class="sxs-lookup"><span data-stu-id="98d7f-134">The <xref:System.Windows.Automation.Peers.AutomationPeer.GetLiveSettingCore%2A?displayProperty=nameWithType> method, which can be overridden to provide a **LiveSetting** value.</span></span>

- <span data-ttu-id="98d7f-135"><xref:System.Windows.Automation.AutomationProperties.GetLiveSetting%2A?displayProperty=nameWithType>和<xref:System.Windows.Automation.AutomationProperties.SetLiveSetting%2A?displayProperty=nameWithType>的 get 和 set 方法**LiveSetting**值。</span><span class="sxs-lookup"><span data-stu-id="98d7f-135">The <xref:System.Windows.Automation.AutomationProperties.GetLiveSetting%2A?displayProperty=nameWithType> and <xref:System.Windows.Automation.AutomationProperties.SetLiveSetting%2A?displayProperty=nameWithType> methods, which get and set a **LiveSetting** value.</span></span>
 
- <span data-ttu-id="98d7f-136"><xref:System.Windows.Automation.AutomationLiveSetting?displayProperty=nameWithType>枚举，它定义了以下可能**LiveSetting**值：</span><span class="sxs-lookup"><span data-stu-id="98d7f-136">The <xref:System.Windows.Automation.AutomationLiveSetting?displayProperty=nameWithType> enumeration, which defines the following possible **LiveSetting** values:</span></span>

   - <span data-ttu-id="98d7f-137"><xref:System.Windows.Automation.AutomationLiveSetting.Off?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="98d7f-137"><xref:System.Windows.Automation.AutomationLiveSetting.Off?displayProperty=nameWithType>.</span></span> <span data-ttu-id="98d7f-138">如果实时区域的内容已更改，该元素不会发送通知。</span><span class="sxs-lookup"><span data-stu-id="98d7f-138">The element does not send notifications if the content of the live region has changed.</span></span>   
   - <span data-ttu-id="98d7f-139"><xref:System.Windows.Automation.AutomationLiveSetting.Polite?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="98d7f-139"><xref:System.Windows.Automation.AutomationLiveSetting.Polite?displayProperty=nameWithType>.</span></span> <span data-ttu-id="98d7f-140">如果活动区域的内容已更改，则该元素将发送非中断通知。</span><span class="sxs-lookup"><span data-stu-id="98d7f-140">The element sends non-interruptive notifications if the content of the live region has changed.</span></span>   

  - <span data-ttu-id="98d7f-141"><xref:System.Windows.Automation.AutomationLiveSetting.Assertive?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="98d7f-141"><xref:System.Windows.Automation.AutomationLiveSetting.Assertive?displayProperty=nameWithType>.</span></span> <span data-ttu-id="98d7f-142">如果活动区域的内容已更改，则该元素将发送中断通知。</span><span class="sxs-lookup"><span data-stu-id="98d7f-142">The element sends interruptive notifications if the content of the live region has changed.</span></span>   

<span data-ttu-id="98d7f-143">你可以通过设置创建 LiveRegion **AutomationProperties.LiveSetting**感兴趣，如下面的示例中所示的元素的属性上：</span><span class="sxs-lookup"><span data-stu-id="98d7f-143">You can create a LiveRegion by setting the **AutomationProperties.LiveSetting** property on the element of interest, as shown in the following example:</span></span>   

```xaml
<TextBlock Name="myTextBlock" AutomationProperties.LiveSetting="Assertive">announcement</TextBlock>
```

<span data-ttu-id="98d7f-144">实时区域中的数据更改，你需要告知屏幕读取器时你显式引发事件，如下面的示例中所示。</span><span class="sxs-lookup"><span data-stu-id="98d7f-144">When the data in the live region changes and you need to inform a screen reader, you explicitly raise an event, as shown in the following sample.</span></span>

```csharp
var peer = FrameworkElementAutomationPeer.FromElement(myTextBlock);

peer.RaiseAutomationEvent(AutomationEvents.LiveRegionChanged);
```
```vb
Dim peer = FrameworkElementAutomationPeer.FromElement(myTextBlock)
peer.RaiseAutomationEvent(AutomationEvents.LiveRegionChanged)

```

<span data-ttu-id="98d7f-145">**高对比度**</span><span class="sxs-lookup"><span data-stu-id="98d7f-145">**High contrast**</span></span>

<span data-ttu-id="98d7f-146">从.NET Framework 4.7.1 开始，在高对比度已得到改进各种 WPF 控件。</span><span class="sxs-lookup"><span data-stu-id="98d7f-146">Starting with the .NET Framework 4.7.1, improvements in high contrast have been made to various WPF controls.</span></span> <span data-ttu-id="98d7f-147">它们现在是可见时<xref:System.Windows.SystemParameters.HighContrast%2A>设置主题。</span><span class="sxs-lookup"><span data-stu-id="98d7f-147">They are now visible when the <xref:System.Windows.SystemParameters.HighContrast%2A> theme is set.</span></span> <span data-ttu-id="98d7f-148">这些方法包括：</span><span class="sxs-lookup"><span data-stu-id="98d7f-148">These include:</span></span>

- <span data-ttu-id="98d7f-149"><xref:System.Windows.Controls.Expander> 控件</span><span class="sxs-lookup"><span data-stu-id="98d7f-149"><xref:System.Windows.Controls.Expander> control</span></span>

    <span data-ttu-id="98d7f-150">焦点视觉<xref:System.Windows.Controls.Expander>控件现在是否可见。</span><span class="sxs-lookup"><span data-stu-id="98d7f-150">The focus visual for the  <xref:System.Windows.Controls.Expander> control is now visible.</span></span> <span data-ttu-id="98d7f-151">键盘视觉对象以<xref:System.Windows.Controls.ComboBox>，<xref:System.Windows.Controls.ListBox>，和<xref:System.Windows.Controls.RadioButton>控件也可见。</span><span class="sxs-lookup"><span data-stu-id="98d7f-151">The keyboard visuals for <xref:System.Windows.Controls.ComboBox>,<xref:System.Windows.Controls.ListBox>, and <xref:System.Windows.Controls.RadioButton> controls are visible as well.</span></span> <span data-ttu-id="98d7f-152">例如: </span><span class="sxs-lookup"><span data-stu-id="98d7f-152">For example:</span></span>

    <span data-ttu-id="98d7f-153">在此之前:</span><span class="sxs-lookup"><span data-stu-id="98d7f-153">Before:</span></span> 
    
    ![具有焦点之前可访问性改进的扩展器控件](media/expander-before.png)

    <span data-ttu-id="98d7f-155">在此之后：</span><span class="sxs-lookup"><span data-stu-id="98d7f-155">After:</span></span> 

    ![扩展器具有可访问性改进后的焦点的控件](media/expander-after.png)

- <span data-ttu-id="98d7f-157"><xref:System.Windows.Controls.CheckBox>和<xref:System.Windows.Controls.RadioButton>控件</span><span class="sxs-lookup"><span data-stu-id="98d7f-157"><xref:System.Windows.Controls.CheckBox> and <xref:System.Windows.Controls.RadioButton> controls</span></span>
 
    <span data-ttu-id="98d7f-158">中的文本<xref:System.Windows.Controls.CheckBox>和<xref:System.Windows.Controls.RadioButton>控件现在是更轻松地查看在高对比度主题中选择。</span><span class="sxs-lookup"><span data-stu-id="98d7f-158">The text in the <xref:System.Windows.Controls.CheckBox> and <xref:System.Windows.Controls.RadioButton> controls is now easier to see when selected in high contrast themes.</span></span> <span data-ttu-id="98d7f-159">例如: </span><span class="sxs-lookup"><span data-stu-id="98d7f-159">For example:</span></span>

    <span data-ttu-id="98d7f-160">在此之前:</span><span class="sxs-lookup"><span data-stu-id="98d7f-160">Before:</span></span> 

    ![具有焦点之前可访问性改进的高对比度单选按钮](media/radio-button-before.png)
    
    <span data-ttu-id="98d7f-162">在此之后：</span><span class="sxs-lookup"><span data-stu-id="98d7f-162">After:</span></span> 

    ![具有可访问性改进后的焦点的高对比度单选按钮](media/radio-button-after.png)

- <span data-ttu-id="98d7f-164"><xref:System.Windows.Controls.ComboBox> 控件</span><span class="sxs-lookup"><span data-stu-id="98d7f-164"><xref:System.Windows.Controls.ComboBox> control</span></span>
 
    <span data-ttu-id="98d7f-165">从.NET Framework 4.7.1，已禁用的边框开始<xref:System.Windows.Controls.ComboBox>控件是禁用的文本与相同的颜色。</span><span class="sxs-lookup"><span data-stu-id="98d7f-165">Starting with the .NET Framework 4.7.1, the border of a disabled <xref:System.Windows.Controls.ComboBox> control is the same color as disabled text.</span></span> <span data-ttu-id="98d7f-166">例如: </span><span class="sxs-lookup"><span data-stu-id="98d7f-166">For example:</span></span>
    
    <span data-ttu-id="98d7f-167">在此之前:</span><span class="sxs-lookup"><span data-stu-id="98d7f-167">Before:</span></span> 

     ![组合框禁用边框和可访问性改进前的文本](media/combo-disabled-before.png)

    <span data-ttu-id="98d7f-169">在此之后：</span><span class="sxs-lookup"><span data-stu-id="98d7f-169">After:</span></span>   

     ![组合框可访问性改进后禁用边框和文本](media/combo-disabled-after.png)

    <span data-ttu-id="98d7f-171">此外，已禁用的专注于按钮将使用正确的主题颜色。</span><span class="sxs-lookup"><span data-stu-id="98d7f-171">In addition, disabled and focused buttons use the correct theme color.</span></span>

    <span data-ttu-id="98d7f-172">在此之前:</span><span class="sxs-lookup"><span data-stu-id="98d7f-172">Before:</span></span>

    ![按钮可访问性改进之前的主题颜色](media/button-themes-before.png) 
    
    <span data-ttu-id="98d7f-174">在此之后：</span><span class="sxs-lookup"><span data-stu-id="98d7f-174">After:</span></span> 

    ![按钮可访问性改进后的主题颜色](media/button-themes-after.png) 

    <span data-ttu-id="98d7f-176">最后，在.NET Framework 4.7 和早期版本中，设置<xref:System.Windows.Controls.ComboBox>控件的样式应用到`Toolbar.ComboBoxStyleKey`导致不可见的下拉箭头。</span><span class="sxs-lookup"><span data-stu-id="98d7f-176">Finally, in the .NET Framework 4.7 and earlier versions, setting a <xref:System.Windows.Controls.ComboBox> control’s style to `Toolbar.ComboBoxStyleKey` caused the drop-down arrow to be invisible.</span></span> <span data-ttu-id="98d7f-177">从.NET Framework 4.7.1 开始修复此问题。</span><span class="sxs-lookup"><span data-stu-id="98d7f-177">This issue is fixed starting with the .NET Framework 4.7.1.</span></span> <span data-ttu-id="98d7f-178">例如: </span><span class="sxs-lookup"><span data-stu-id="98d7f-178">For example:</span></span>

    <span data-ttu-id="98d7f-179">在此之前:</span><span class="sxs-lookup"><span data-stu-id="98d7f-179">Before:</span></span> 

    ![Toolbar.ComboBoxStyleKey 之前可访问性改进](media/comboboxstylekey-before.png) 
    
    <span data-ttu-id="98d7f-181">在此之后：</span><span class="sxs-lookup"><span data-stu-id="98d7f-181">After:</span></span> 

    ![Toolbar.ComboBoxStyleKey 后可访问性改进](media/comboboxstylekey-after.png) 

- <span data-ttu-id="98d7f-183"><xref:System.Windows.Controls.DataGrid> 控件</span><span class="sxs-lookup"><span data-stu-id="98d7f-183"><xref:System.Windows.Controls.DataGrid> control</span></span>

    <span data-ttu-id="98d7f-184">从.NET Framework 4.7.1 中的排序指示器箭头开始<xref:System.Windows.Controls.DataGrid>控制现在使用更正主题颜色。</span><span class="sxs-lookup"><span data-stu-id="98d7f-184">Starting with the .NET Framework 4.7.1, the sort indicator arrow in <xref:System.Windows.Controls.DataGrid> controls now uses correct theme colors.</span></span> <span data-ttu-id="98d7f-185">例如: </span><span class="sxs-lookup"><span data-stu-id="98d7f-185">For example:</span></span>

    <span data-ttu-id="98d7f-186">在此之前:</span><span class="sxs-lookup"><span data-stu-id="98d7f-186">Before:</span></span> 

    ![排序指示器箭头之前可访问性改进](media/sort-indicator-before.png) 
    
    <span data-ttu-id="98d7f-188">在此之后：</span><span class="sxs-lookup"><span data-stu-id="98d7f-188">After:</span></span>   
 
    ![排在可访问性改进指示器箭头](media/sort-indicator-after.png) 
    
    <span data-ttu-id="98d7f-190">此外，在.NET Framework 4.7 和早期版本中，默认链接样式更改为鼠标上不正确的颜色在高对比度模式。</span><span class="sxs-lookup"><span data-stu-id="98d7f-190">In addition, in the .NET Framework 4.7 and earlier versions, the default link style changed to an incorrect color on mouse over in high contrast modes.</span></span> <span data-ttu-id="98d7f-191">此问题解决从.NET Framework 4.7.1 开始。</span><span class="sxs-lookup"><span data-stu-id="98d7f-191">This is resolved starting with the .NET Framework 4.7.1.</span></span> <span data-ttu-id="98d7f-192">同样，<xref:System.Windows.Controls.DataGrid>复选框列的键盘焦点反馈从.NET Framework 4.7.1 开始使用预期的颜色。</span><span class="sxs-lookup"><span data-stu-id="98d7f-192">Similarly, <xref:System.Windows.Controls.DataGrid> checkbox columns uses the expected colors for keyboard focus feedback starting with the .NET Framework 4.7.1.</span></span>

    <span data-ttu-id="98d7f-193">在此之前:</span><span class="sxs-lookup"><span data-stu-id="98d7f-193">Before:</span></span> 

    ![DataGrid 默认链接样式之前可访问性改进](media/default-link-style-before.png) 
 
    <span data-ttu-id="98d7f-195">在此之后：</span><span class="sxs-lookup"><span data-stu-id="98d7f-195">After:</span></span>    
  
    ![可访问性改进后的 DataGrid 默认链接样式](media/default-link-style-after.png)  

<span data-ttu-id="98d7f-197">有关在.NET Framework 4.7.1 WPF 可访问性改进的详细信息，请参阅[WPF 中的可访问性改进](../migration-guide/retargeting/4.7-4.7.1.md#accessibility-improvements-in-wpf)。</span><span class="sxs-lookup"><span data-stu-id="98d7f-197">For more information on WPF accessibility improvements in the .NET Framework 4.7.1, see [Accessibility improvements in WPF](../migration-guide/retargeting/4.7-4.7.1.md#accessibility-improvements-in-wpf).</span></span>

## <a name="windows-forms-accessibility-improvements"></a><span data-ttu-id="98d7f-198">Windows 窗体可访问性改进</span><span class="sxs-lookup"><span data-stu-id="98d7f-198">Windows Forms accessibility improvements</span></span>

<span data-ttu-id="98d7f-199">在.NET Framework 4.7.1 中，Windows 窗体 (WinForms) 包括以下几个方面的可访问性更改。</span><span class="sxs-lookup"><span data-stu-id="98d7f-199">In the .NET Framework 4.7.1, Windows Forms (WinForms) includes accessibility changes in the following areas.</span></span>

<span data-ttu-id="98d7f-200">**在高对比度模式中的改进的显示**</span><span class="sxs-lookup"><span data-stu-id="98d7f-200">**Improved display in High Contrast mode**</span></span>

<span data-ttu-id="98d7f-201">从.NET Framework 4.7.1 开始，各种 WinForms 控件提供改进的呈现在操作系统中可用的高对比度模式。</span><span class="sxs-lookup"><span data-stu-id="98d7f-201">Starting with the .NET Framework 4.7.1, various WinForms controls offer improved rendering in the HighContrast modes available in the operating system.</span></span> <span data-ttu-id="98d7f-202">Windows 窗体根据 Windows 10 Win32 framework 和 Windows 10 已更改的一些高对比度的系统颜色的值。</span><span class="sxs-lookup"><span data-stu-id="98d7f-202">Windows 10 has changed the values for some high contrast system colors, and Windows Forms is based on the Windows 10 Win32 framework.</span></span> <span data-ttu-id="98d7f-203">为获得最佳体验，最新版本的 Windows 上运行并通过添加测试应用程序并取消注释 Windows 10 中的应用程序清单文件支持 OS 行，这样它看起来就以下参与到最新的操作系统更改：</span><span class="sxs-lookup"><span data-stu-id="98d7f-203">For the best experience, run on the latest version of Windows and opt in to the latest OS changes by adding an app.manifest file in a test application and un-comment the Windows 10 supported OS  line so that it looks the following:</span></span>

```xml
<!– Windows 10 –>
<supportedOS Id=”{8e0f7a12-bfb3-4fe8-b9a5-48fd50a15a9a}” />
```
<span data-ttu-id="98d7f-204">高对比度更改的一些示例包括：</span><span class="sxs-lookup"><span data-stu-id="98d7f-204">Some examples of high contrast changes include:</span></span>

- <span data-ttu-id="98d7f-205">中的复选标记<xref:System.Windows.Forms.MenuStrip>项更易于查看。</span><span class="sxs-lookup"><span data-stu-id="98d7f-205">Checkmarks in <xref:System.Windows.Forms.MenuStrip> items are easier to view.</span></span>

- <span data-ttu-id="98d7f-206">当选中时，禁用<xref:System.Windows.Forms.MenuStrip>项更易于查看。</span><span class="sxs-lookup"><span data-stu-id="98d7f-206">When selected, disabled <xref:System.Windows.Forms.MenuStrip> items are easier to view.</span></span>

- <span data-ttu-id="98d7f-207">在所选的文本<xref:System.Windows.Forms.Button>控制所选的颜色与之相对的。</span><span class="sxs-lookup"><span data-stu-id="98d7f-207">Text in a selected <xref:System.Windows.Forms.Button> control contrasts with the selection color.</span></span>

- <span data-ttu-id="98d7f-208">已禁用的文本更容易读取。</span><span class="sxs-lookup"><span data-stu-id="98d7f-208">Disabled text is easier to read.</span></span> <span data-ttu-id="98d7f-209">例如: </span><span class="sxs-lookup"><span data-stu-id="98d7f-209">For example:</span></span>

    <span data-ttu-id="98d7f-210">在此之前:</span><span class="sxs-lookup"><span data-stu-id="98d7f-210">Before:</span></span>

    ![已禁用的文本之前可访问性改进](media/wf-disabled-before.png) 

    <span data-ttu-id="98d7f-212">在此之后：</span><span class="sxs-lookup"><span data-stu-id="98d7f-212">After:</span></span>

    ![之后可访问性改进的禁用的文本](media/wf-disabled-after.png) 

- <span data-ttu-id="98d7f-214">在异常对话框中的线程的高对比度改进。</span><span class="sxs-lookup"><span data-stu-id="98d7f-214">High contrast improvements in the Thread Exception Dialog.</span></span>

<span data-ttu-id="98d7f-215">**讲述人的增强的支持**</span><span class="sxs-lookup"><span data-stu-id="98d7f-215">**Improved Narrator support**</span></span>

<span data-ttu-id="98d7f-216">.NET Framework 4.7.1 中的 Windows 窗体包含讲述人的以下可访问性改进：</span><span class="sxs-lookup"><span data-stu-id="98d7f-216">Windows Forms in the .NET Framework 4.7.1 includes the following accessibility improvements for the Narrator:</span></span>

- <span data-ttu-id="98d7f-217"><xref:System.Windows.Forms.MonthCalendar>控件可以由讲述人，以及其他 UI 自动化工具进行访问。</span><span class="sxs-lookup"><span data-stu-id="98d7f-217">The <xref:System.Windows.Forms.MonthCalendar> control can be accessed by the Narrator, as well as by other UI automation tools.</span></span>

- <span data-ttu-id="98d7f-218"><xref:System.Windows.Forms.CheckedListBox>控件时，在项的复选状态已经更改，因此它们已更改的列表项的值会通知用户通知讲述人。</span><span class="sxs-lookup"><span data-stu-id="98d7f-218">The <xref:System.Windows.Forms.CheckedListBox> control notifies Narrator when an item's check state has changed so the user is notified that they’ve changed the value of a list item.</span></span>
 
- <span data-ttu-id="98d7f-219"><xref:System.Windows.Forms.DataGridViewCell>控件到讲述人报告正确的只读状态。</span><span class="sxs-lookup"><span data-stu-id="98d7f-219">The <xref:System.Windows.Forms.DataGridViewCell> control reports the correct read-only status to Narrator.</span></span>
 
- <span data-ttu-id="98d7f-220">讲述人现在可以读取已禁用<xref:System.Windows.Forms.ToolStripMenuItem>文本，而以前它将跳过禁用的菜单项。</span><span class="sxs-lookup"><span data-stu-id="98d7f-220">Narrator can now read disabled <xref:System.Windows.Forms.ToolStripMenuItem> text, whereas previously it would skip over disabled menu items.</span></span>

<span data-ttu-id="98d7f-221">**增强了对 UIAutomation 可访问性模式支持**</span><span class="sxs-lookup"><span data-stu-id="98d7f-221">**Enhanced support for UIAutomation accessibility patterns**</span></span>

<span data-ttu-id="98d7f-222">从.NET Framework 4.7.1 开始，辅助功能技术工具的开发人员可以利用常见的 API 可访问性模式和多个 WinForms 控件的属性。</span><span class="sxs-lookup"><span data-stu-id="98d7f-222">Starting with the .NET Framework 4.7.1, developers of accessibility technology tools can leverage common API accessibility patterns and properties for several WinForms controls.</span></span> <span data-ttu-id="98d7f-223">这些辅助功能改进包括：</span><span class="sxs-lookup"><span data-stu-id="98d7f-223">These accessibility improvements include:</span></span>

- <span data-ttu-id="98d7f-224"><xref:System.Windows.Forms.ComboBox>和<xref:System.Windows.Forms.ToolStripSplitButton>现在支持[展开/折叠模式](../ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md)。</span><span class="sxs-lookup"><span data-stu-id="98d7f-224">The <xref:System.Windows.Forms.ComboBox> and <xref:System.Windows.Forms.ToolStripSplitButton> now support the [expand/collapse pattern](../ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md).</span></span>
 
- <span data-ttu-id="98d7f-225"><xref:System.Windows.Forms.DataGridViewCheckBoxCell>现在支持[toggle 模式](../ui-automation/implementing-the-ui-automation-toggle-control-pattern.md)。</span><span class="sxs-lookup"><span data-stu-id="98d7f-225">The <xref:System.Windows.Forms.DataGridViewCheckBoxCell> now supports the [toggle pattern](../ui-automation/implementing-the-ui-automation-toggle-control-pattern.md).</span></span>
 
- <span data-ttu-id="98d7f-226"><xref:System.Windows.Forms.ToolStripItem>控件支持<xref:System.Windows.Automation.AutomationElement.Name>属性和[展开/折叠模式](../ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md)。</span><span class="sxs-lookup"><span data-stu-id="98d7f-226">The <xref:System.Windows.Forms.ToolStripItem> control supports the <xref:System.Windows.Automation.AutomationElement.Name> property and the [expand/collapse pattern](../ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md).</span></span>

- <span data-ttu-id="98d7f-227"><xref:System.Windows.Forms.NumericUpDown>和<xref:System.Windows.Forms.DomainUpDown>控件支持<xref:System.Windows.Automation.automationElement.Name>属性。</span><span class="sxs-lookup"><span data-stu-id="98d7f-227">The <xref:System.Windows.Forms.NumericUpDown> and <xref:System.Windows.Forms.DomainUpDown> controls support the <xref:System.Windows.Automation.automationElement.Name> property.</span></span>

<span data-ttu-id="98d7f-228">**改进的属性浏览器体验**</span><span class="sxs-lookup"><span data-stu-id="98d7f-228">**Improved property browser experience**</span></span>

<span data-ttu-id="98d7f-229">从.NET Framework 4.7.1 开始，Windows 窗体包括：</span><span class="sxs-lookup"><span data-stu-id="98d7f-229">Starting with the .NET Framework 4.7.1, Windows Forms includes:</span></span>

- <span data-ttu-id="98d7f-230">更好地键盘通过不同的下拉列表选择窗口的导航。</span><span class="sxs-lookup"><span data-stu-id="98d7f-230">Better keyboard navigation through the various drop-down selection windows.</span></span>
- <span data-ttu-id="98d7f-231">减少不必要的制表位。</span><span class="sxs-lookup"><span data-stu-id="98d7f-231">A reduction of unnecessary tab stops.</span></span>
- <span data-ttu-id="98d7f-232">更好的控件类型的报告。</span><span class="sxs-lookup"><span data-stu-id="98d7f-232">Better reporting of control types.</span></span>
- <span data-ttu-id="98d7f-233">改进了讲述人行为。</span><span class="sxs-lookup"><span data-stu-id="98d7f-233">Improved narrator behavior.</span></span>
 
## <a name="see-also"></a><span data-ttu-id="98d7f-234">另请参阅</span><span class="sxs-lookup"><span data-stu-id="98d7f-234">See Also</span></span>
[<span data-ttu-id="98d7f-235">什么是.NET Framework 中的新增功能</span><span class="sxs-lookup"><span data-stu-id="98d7f-235">What's new in the .NET Framework</span></span>](whats-new.md)   
 