---
title: "Windows 窗体添加配置元素"
ms.custom: 
ms.date: 04/07/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Forms Add configuration element
- configuring Windows Forms applications
ms.assetid: 3e3e04de-99d1-4658-b716-44cb669d9589
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 331b2238ae87776938422484d34bb68b4653a56e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="windows-forms-add-configuration-element"></a><span data-ttu-id="ac95c-102">Windows 窗体添加配置元素</span><span class="sxs-lookup"><span data-stu-id="ac95c-102">Windows Forms Add Configuration Element</span></span>

<span data-ttu-id="ac95c-103">`<add>`元素将添加指定 Windows 窗体应用程序是否支持添加到.NET Framework 4.7 或更高版本的 Windows 窗体应用的功能的预定义的键。</span><span class="sxs-lookup"><span data-stu-id="ac95c-103">The `<add>` element adds a predefined key that specifies whether your Windows Form app supports features added to Windows Forms apps in the .NET Framework 4.7 or later.</span></span>

## <a name="syntax"></a><span data-ttu-id="ac95c-104">语法</span><span class="sxs-lookup"><span data-stu-id="ac95c-104">Syntax</span></span>

```xml
<System.Windows.Forms.ApplicationConfigurationSection>
  <add key="key-name" value="key-value" />
</System.Windows.Forms.ApplicationConfigurationSection>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="ac95c-105">特性和元素</span><span class="sxs-lookup"><span data-stu-id="ac95c-105">Attributes and elements</span></span>

<span data-ttu-id="ac95c-106">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="ac95c-106">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="ac95c-107">特性</span><span class="sxs-lookup"><span data-stu-id="ac95c-107">Attributes</span></span>

| <span data-ttu-id="ac95c-108">特性</span><span class="sxs-lookup"><span data-stu-id="ac95c-108">Attribute</span></span> | <span data-ttu-id="ac95c-109">描述</span><span class="sxs-lookup"><span data-stu-id="ac95c-109">Description</span></span> |
| --------- | ----------- |
| `key`     | <span data-ttu-id="ac95c-110">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="ac95c-110">Required attribute.</span></span> <span data-ttu-id="ac95c-111">预定义的密钥名称对应于特定的 Windows 窗体可自定义功能。</span><span class="sxs-lookup"><span data-stu-id="ac95c-111">A predefined key name that corresponds to a particular Windows Forms customizable feature.</span></span> |
| `value`   | <span data-ttu-id="ac95c-112">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="ac95c-112">Required attribute.</span></span> <span data-ttu-id="ac95c-113">要赋给 `key` 的值。</span><span class="sxs-lookup"><span data-stu-id="ac95c-113">The value to assign to `key`.</span></span> |

### <a name="key-attribute-names-and-associated-values"></a><span data-ttu-id="ac95c-114">`key`特性名称和关联的值</span><span class="sxs-lookup"><span data-stu-id="ac95c-114">`key` attribute names and associated values</span></span>

| <span data-ttu-id="ac95c-115">`key` 名称</span><span class="sxs-lookup"><span data-stu-id="ac95c-115">`key` name</span></span> | <span data-ttu-id="ac95c-116">值</span><span class="sxs-lookup"><span data-stu-id="ac95c-116">Values</span></span> | <span data-ttu-id="ac95c-117">描述</span><span class="sxs-lookup"><span data-stu-id="ac95c-117">Description</span></span> |
| ---------- | ------ | ----------- |
| <span data-ttu-id="ac95c-118">"AnchorLayout.DisableSinglePassControlScaling"</span><span class="sxs-lookup"><span data-stu-id="ac95c-118">"AnchorLayout.DisableSinglePassControlScaling"</span></span> | <span data-ttu-id="ac95c-119">"true"&#124;"false"</span><span class="sxs-lookup"><span data-stu-id="ac95c-119">"true"&#124;"false"</span></span> | <span data-ttu-id="ac95c-120">指示是否已锚定的控件调整单个传递中。</span><span class="sxs-lookup"><span data-stu-id="ac95c-120">Indicates whether anchored controls are scaled in a single pass.</span></span> <span data-ttu-id="ac95c-121">"true"以禁用单个传递缩放;否则为 false。</span><span class="sxs-lookup"><span data-stu-id="ac95c-121">"true" to disable single pass scaling; otherwise, false.</span></span> <span data-ttu-id="ac95c-122">请参阅中的"单通过缩放"一节[备注](#Remarks)有关详细信息。</span><span class="sxs-lookup"><span data-stu-id="ac95c-122">See the "Single pass scaling" section in the [Remarks](#Remarks) for more information.</span></span> |
| <span data-ttu-id="ac95c-123">"DpiAwareness"</span><span class="sxs-lookup"><span data-stu-id="ac95c-123">"DpiAwareness"</span></span> | <span data-ttu-id="ac95c-124">"PerMonitorV2"&#124;"false"</span><span class="sxs-lookup"><span data-stu-id="ac95c-124">"PerMonitorV2"&#124;"false"</span></span> | <span data-ttu-id="ac95c-125">指示是否 DPI 感知应用程序。</span><span class="sxs-lookup"><span data-stu-id="ac95c-125">Indicates whether an application is DPI-aware.</span></span> <span data-ttu-id="ac95c-126">设置为"PerMonitorV2"，以支持 Dpi 感知; 密钥否则，将其设置为"false"。</span><span class="sxs-lookup"><span data-stu-id="ac95c-126">Set the key to "PerMonitorV2" to support Dpi awareness; otherwise, set it to "false".</span></span> <span data-ttu-id="ac95c-127">DPI 感知是一项可以选择使用的功能;若要充分利用 Windows 窗体的高 DPI 支持，应设置为"PerMonitorV2"其值。</span><span class="sxs-lookup"><span data-stu-id="ac95c-127">DPI awareness is an opt-in feature; to take advantage of Windows Forms' high DPI support, you should set its value to "PerMonitorV2".</span></span> <span data-ttu-id="ac95c-128">请参阅[备注](#remarks)部分以了解更多信息。</span><span class="sxs-lookup"><span data-stu-id="ac95c-128">See the [Remarks](#remarks) section for more information.</span></span> |
| <span data-ttu-id="ac95c-129">"CheckedListBox.DisableHighDpiImprovements"</span><span class="sxs-lookup"><span data-stu-id="ac95c-129">"CheckedListBox.DisableHighDpiImprovements"</span></span> | <span data-ttu-id="ac95c-130">"true"&#124;"false"</span><span class="sxs-lookup"><span data-stu-id="ac95c-130">"true"&#124;"false"</span></span> | <span data-ttu-id="ac95c-131">指示是否<xref:System.Windows.Forms.CheckedListBox>控制所采用的.NET Framework 4.7 中引入的缩放和布局改进的优点。</span><span class="sxs-lookup"><span data-stu-id="ac95c-131">Indicates whether the <xref:System.Windows.Forms.CheckedListBox> control takes advantage of scaling and layout improvements introduced in the .NET Framework 4.7.</span></span> <span data-ttu-id="ac95c-132">"true"来选择退出 caling 和布局改进;否则为"false"。</span><span class="sxs-lookup"><span data-stu-id="ac95c-132">"true" to opt out of caling and layout improvements; otherwise, "false".</span></span> |
| <span data-ttu-id="ac95c-133">"DataGridView.DisableHighDpiImprovements"</span><span class="sxs-lookup"><span data-stu-id="ac95c-133">"DataGridView.DisableHighDpiImprovements"</span></span> | <span data-ttu-id="ac95c-134">"true"&#124;"false"</span><span class="sxs-lookup"><span data-stu-id="ac95c-134">"true"&#124;"false"</span></span> | <span data-ttu-id="ac95c-135">指示是否<xref:System.Windows.Forms.DataGridView>控制.NET Framework 4.7 中引入的缩放和布局改进。</span><span class="sxs-lookup"><span data-stu-id="ac95c-135">Indicates whether the <xref:System.Windows.Forms.DataGridView> control scaling and layout improvements introduced in the .NET Framework 4.7.</span></span> <span data-ttu-id="ac95c-136">"true"来选择退出 DPI 感知;"false"否则为。</span><span class="sxs-lookup"><span data-stu-id="ac95c-136">"true" to opt out of DPI awareness; "false" otherwise.</span></span> |
| <span data-ttu-id="ac95c-137">"DisableDpiChangedMessageHandling"</span><span class="sxs-lookup"><span data-stu-id="ac95c-137">"DisableDpiChangedMessageHandling"</span></span> | <span data-ttu-id="ac95c-138">"true"&#124;"false"</span><span class="sxs-lookup"><span data-stu-id="ac95c-138">"true"&#124;"false"</span></span> | <span data-ttu-id="ac95c-139">"true"来选择退出接收与 DPI 缩放更改; 相关的消息"false"否则为。</span><span class="sxs-lookup"><span data-stu-id="ac95c-139">"true" to opt out of receiving messages related to DPI scaling changes; "false" otherwise.</span></span> <span data-ttu-id="ac95c-140">请参阅[备注](#remarks)部分以了解更多信息。</span><span class="sxs-lookup"><span data-stu-id="ac95c-140">See the [Remarks](#remarks) section for more information.</span></span> |
| <span data-ttu-id="ac95c-141">"EnableWindowsFormsHighDpiAutoResizing"</span><span class="sxs-lookup"><span data-stu-id="ac95c-141">"EnableWindowsFormsHighDpiAutoResizing"</span></span> | <span data-ttu-id="ac95c-142">"true"&#124;"false"</span><span class="sxs-lookup"><span data-stu-id="ac95c-142">"true"&#124;"false"</span></span> | <span data-ttu-id="ac95c-143">指示是否自动调整 Windows 窗体应用程序大小由于 DPI 缩放更改。</span><span class="sxs-lookup"><span data-stu-id="ac95c-143">Indicates whether a Windows Forms application is automatically resized due to DPI scaling changes.</span></span> <span data-ttu-id="ac95c-144">"true"以启用自动调整大小;否则为 false。</span><span class="sxs-lookup"><span data-stu-id="ac95c-144">"true" to enable automatic resizing; otherwise, false.</span></span> |
| <span data-ttu-id="ac95c-145">"Form.DisableSinglePassControlScaling"</span><span class="sxs-lookup"><span data-stu-id="ac95c-145">"Form.DisableSinglePassControlScaling"</span></span> | <span data-ttu-id="ac95c-146">"true"&#124;"false"</span><span class="sxs-lookup"><span data-stu-id="ac95c-146">"true"&#124;"false"</span></span> | <span data-ttu-id="ac95c-147">指示是否<xref:System.Windows.Forms.Form>扩展单个传递中。</span><span class="sxs-lookup"><span data-stu-id="ac95c-147">Indicates whether the <xref:System.Windows.Forms.Form> is scaled in a single pass.</span></span> <span data-ttu-id="ac95c-148">"true"以禁用次传递缩放;否则为 false。</span><span class="sxs-lookup"><span data-stu-id="ac95c-148">"true" to disable single-pass scaling; otherwise, false.</span></span> <span data-ttu-id="ac95c-149">请参阅中的"单通过缩放"一节[备注](#Remarks)有关详细信息。</span><span class="sxs-lookup"><span data-stu-id="ac95c-149">See the "Single pass scaling" section in the [Remarks](#Remarks) for more information.</span></span> |
| <span data-ttu-id="ac95c-150">"MonthCalendar.DisableSinglePassControlScaling"</span><span class="sxs-lookup"><span data-stu-id="ac95c-150">"MonthCalendar.DisableSinglePassControlScaling"</span></span> | <span data-ttu-id="ac95c-151">"true"&#124;"false"</span><span class="sxs-lookup"><span data-stu-id="ac95c-151">"true"&#124;"false"</span></span> | <span data-ttu-id="ac95c-152">指示是否<xref:System.Windows.Forms.MonthCalendar>单个传递中缩放控件。</span><span class="sxs-lookup"><span data-stu-id="ac95c-152">Indicates whether the <xref:System.Windows.Forms.MonthCalendar> control is scaled in a single pass.</span></span> <span data-ttu-id="ac95c-153">"true"以禁用次传递缩放;否则为 false。</span><span class="sxs-lookup"><span data-stu-id="ac95c-153">"true" to disable single-pass scaling; otherwise, false.</span></span> <span data-ttu-id="ac95c-154">请参阅中的"单通过缩放"一节[备注](#Remarks)有关详细信息。</span><span class="sxs-lookup"><span data-stu-id="ac95c-154">See the "Single pass scaling" section in the [Remarks](#Remarks) for more information.</span></span> |
| <span data-ttu-id="ac95c-155">"Toolstrip.DisableHighDpiImprovements"</span><span class="sxs-lookup"><span data-stu-id="ac95c-155">"Toolstrip.DisableHighDpiImprovements"</span></span> | <span data-ttu-id="ac95c-156">"true"&#124;"false"</span><span class="sxs-lookup"><span data-stu-id="ac95c-156">"true"&#124;"false"</span></span> | <span data-ttu-id="ac95c-157">指示是否<xref:System.Windows.Forms.ToolStrip>控制所采用的.NET Framework 4.7 中引入的缩放和布局改进的优点。</span><span class="sxs-lookup"><span data-stu-id="ac95c-157">Indicates whether the <xref:System.Windows.Forms.ToolStrip> control takes advantage of scaling and layout improvements introduced in the .NET Framework 4.7.</span></span> <span data-ttu-id="ac95c-158">"true"来选择退出 DPI 感知;"false"否则为。</span><span class="sxs-lookup"><span data-stu-id="ac95c-158">"true" to opt out of DPI awareness; "false" otherwise.</span></span> |

### <a name="child-elements"></a><span data-ttu-id="ac95c-159">子元素</span><span class="sxs-lookup"><span data-stu-id="ac95c-159">Child elements</span></span>

<span data-ttu-id="ac95c-160">无。</span><span class="sxs-lookup"><span data-stu-id="ac95c-160">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="ac95c-161">父元素</span><span class="sxs-lookup"><span data-stu-id="ac95c-161">Parent elements</span></span>

| <span data-ttu-id="ac95c-162">元素</span><span class="sxs-lookup"><span data-stu-id="ac95c-162">Element</span></span> | <span data-ttu-id="ac95c-163">描述</span><span class="sxs-lookup"><span data-stu-id="ac95c-163">Description</span></span> |
| ------- | ----------- |
| [`<System.Windows.Forms.ApplicationConfigurationSection>`](../../../../../docs/framework/configure-apps/file-schema/winforms/index.md) | <span data-ttu-id="ac95c-164">配置对新 Windows 窗体应用程序功能的支持。</span><span class="sxs-lookup"><span data-stu-id="ac95c-164">Configures support for new Windows Forms application features.</span></span> |

## <a name="a-nameremarks--remarks"></a><span data-ttu-id="ac95c-165"><a name="remarks" />备注</span><span class="sxs-lookup"><span data-stu-id="ac95c-165"><a name="remarks" /> Remarks</span></span>

<span data-ttu-id="ac95c-166">从 .NET Framework 4.7 开始，`<System.Windows.Forms.ApplicationConfigurationSection>` 元素允许配置 Windows 窗体应用程序，以利用最新版本的 .NET Framework 中添加的功能。</span><span class="sxs-lookup"><span data-stu-id="ac95c-166">Starting with the .NET Framework 4.7, the `<System.Windows.Forms.ApplicationConfigurationSection>` element allows you to configure Windows Forms applications to take advantage of features added in recent releases of the .NET Framework.</span></span> 

<span data-ttu-id="ac95c-167">`<System.Windows.Forms.ApplicationConfigurationSection>`元素，你可以添加一个或多个子`<add>`元素，其中每个定义特定配置设置。</span><span class="sxs-lookup"><span data-stu-id="ac95c-167">The `<System.Windows.Forms.ApplicationConfigurationSection>` element allows you to add one or more child `<add>` elements, each of which defines a specific configuration setting.</span></span>  

<span data-ttu-id="ac95c-168">Windows 窗体高 DPI 支持的概述，请参阅[高 DPI 支持 Windows 窗体中](../../../../../docs/framework/winforms/high-dpi-support-in-windows-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="ac95c-168">For an overview of Windows Forms High DPI support, see [High DPI Support in Windows Forms](../../../../../docs/framework/winforms/high-dpi-support-in-windows-forms.md).</span></span>

### <a name="dpiawareness"></a><span data-ttu-id="ac95c-169">DpiAwareness</span><span class="sxs-lookup"><span data-stu-id="ac95c-169">DpiAwareness</span></span>

<span data-ttu-id="ac95c-170">可以配置从.NET Framework 4.7 开始开始的 Windows 10 创建者版本和.NET Framework 目标版本的 Windows 版本下运行的 Windows 窗体应用程序以利用.NET Framework 中引入的高 DPI 改进4.7。</span><span class="sxs-lookup"><span data-stu-id="ac95c-170">Windows Forms apps that run under Windows versions starting with Windows 10 Creators Edition and target versions of the .NET Framework starting with the .NET Framework 4.7 can be configured to take advantage of high DPI improvements introduced in the .NET Framework 4.7.</span></span> <span data-ttu-id="ac95c-171">这些方法包括：</span><span class="sxs-lookup"><span data-stu-id="ac95c-171">These include:</span></span>

- <span data-ttu-id="ac95c-172">动态 Windows 窗体应用程序已启动后用户更改的 DPI 或缩放系数的 DPI 方案的支持。</span><span class="sxs-lookup"><span data-stu-id="ac95c-172">Support for dynamic DPI scenarios in which the user changes the DPI or scale factor after a Windows Forms application has been launched.</span></span>

- <span data-ttu-id="ac95c-173">缩放和多个 Windows 窗体的布局中的改进控件，如<xref:System.Windows.Forms.MonthCalendar>控件和<xref:System.Windows.Forms.CheckedListBox>控件。</span><span class="sxs-lookup"><span data-stu-id="ac95c-173">Improvements in the scaling and layout of a number of Windows Forms controls, such as the <xref:System.Windows.Forms.MonthCalendar> control and the <xref:System.Windows.Forms.CheckedListBox> control.</span></span> 

<span data-ttu-id="ac95c-174">高 DPI 感知是一项可以选择使用的功能;默认情况下，值`DpiAwareness`是`false`。</span><span class="sxs-lookup"><span data-stu-id="ac95c-174">High DPI awareness is an opt-in feature; by default, the value of `DpiAwareness` is `false`.</span></span> <span data-ttu-id="ac95c-175">你可以选择加入 Windows 窗体支持为了 DPI 感知通过此密钥来将值设置`PerMonitorV2`应用程序配置文件中。</span><span class="sxs-lookup"><span data-stu-id="ac95c-175">You can opt into Windows Forms' support for DPI awareness by setting the value of this key to `PerMonitorV2` in the application configuration file.</span></span> <span data-ttu-id="ac95c-176">如果启用了 DPI 感知，还将启用所有各项 DPI 功能。</span><span class="sxs-lookup"><span data-stu-id="ac95c-176">If DPI awareness is enabled, all individual DPI features are also enabled.</span></span> <span data-ttu-id="ac95c-177">这些方法包括：</span><span class="sxs-lookup"><span data-stu-id="ac95c-177">These include:</span></span>

- <span data-ttu-id="ac95c-178">DPI 更改消息不同，后者由控制`DisableDpiChangedMessageHandling`密钥。</span><span class="sxs-lookup"><span data-stu-id="ac95c-178">DPI changed messages, which are controlled by the `DisableDpiChangedMessageHandling` key.</span></span>

- <span data-ttu-id="ac95c-179">动态 DPI 支持，它由控制`EnableWindowsFormsHighDpiAutoResizing`密钥。</span><span class="sxs-lookup"><span data-stu-id="ac95c-179">Dynamic DPI support, which is controlled by the `EnableWindowsFormsHighDpiAutoResizing` key.</span></span>

- <span data-ttu-id="ac95c-180">单个传递控件缩放，这由控制`Form.DisableSinglePassControlScaling`个人<xref:System.Windows.Forms.Form>控件，通过`AnchorLayout.DisableSinglePassControlScaling`针对锚定控件，并按密钥`MonthCalendar.DisableSinglePassControlScaling`键<xref:System.Windows.Forms.MonthCalendar>控件</span><span class="sxs-lookup"><span data-stu-id="ac95c-180">Single-pass control scaling, which is controlled by the `Form.DisableSinglePassControlScaling` for individual <xref:System.Windows.Forms.Form> controls, by the `AnchorLayout.DisableSinglePassControlScaling` key for anchored controls, and by the `MonthCalendar.DisableSinglePassControlScaling` key for the <xref:System.Windows.Forms.MonthCalendar> control</span></span> 

- <span data-ttu-id="ac95c-181">高 DPI 缩放和布局改进，其由控制`CheckListBox.DisableHighDpiImprovements`键<xref:System.Windows.Forms.CheckedListBox>控制，请通过`DataGridView.DisableHighDpiImprovements`键<xref:System.Windows.Forms.DataGridView>控件，并通过`Toolstrip.DisableHighDpiImprovements`键<xref:System.Windows.Forms.ToolStrip>控件。</span><span class="sxs-lookup"><span data-stu-id="ac95c-181">High DPI scaling and layout improvements, which is controlled by the `CheckListBox.DisableHighDpiImprovements` key for the <xref:System.Windows.Forms.CheckedListBox> control, by the `DataGridView.DisableHighDpiImprovements` key for the <xref:System.Windows.Forms.DataGridView> control, and by the `Toolstrip.DisableHighDpiImprovements` key for the <xref:System.Windows.Forms.ToolStrip> control.</span></span>  

<span data-ttu-id="ac95c-182">通过设置提供选择加入设置一个默认`DpiAwareness`到`PerMonitorV2`通常足以满足新的 Windows 窗体应用程序。</span><span class="sxs-lookup"><span data-stu-id="ac95c-182">The single default opt-in setting provided by setting `DpiAwareness` to `PerMonitorV2` is generally adequate for new Windows Forms applications.</span></span> <span data-ttu-id="ac95c-183">但是，你可以然后选择退出各个高 DPI 改进将相应的项添加到应用程序配置文件。</span><span class="sxs-lookup"><span data-stu-id="ac95c-183">However, You can then opt out of individual high DPI improvements by adding the corresponding key to the application configuration file.</span></span> <span data-ttu-id="ac95c-184">例如，若要利用动态 DPI 支持除外的所有新 DPI featuers，要到你的应用程序配置文件添加以下：</span><span class="sxs-lookup"><span data-stu-id="ac95c-184">For example, to take advantage of all the new DPI featuers except for dynamic DPI support, you would add the following to your application configuration file:</span></span>

```xml
<System.Windows.Forms.ApplicationConfigurationSection>
   <add key="DpiAwareness" value="PerMonitorV2" />
   <--! Disable dynamic DPI support -->
   <add key="EnableWindowsFormsHighDpiAutoResizing" value="false" />
</System.Windows.Forms.ApplicationConfigurationSection>
```
<span data-ttu-id="ac95c-185">通常情况下，你选择退出特定功能因为您已选择以编程方式处理。</span><span class="sxs-lookup"><span data-stu-id="ac95c-185">Typically, you opt out of a particular feature because you've chosen to handle it programmatically.</span></span>

<span data-ttu-id="ac95c-186">利用 Windows 窗体应用程序中的高 DPI 支持的详细信息，请参阅[高 DPI 支持 Windows 窗体中](../../../../../docs/framework/winforms/high-dpi-support-in-windows-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="ac95c-186">For more information on taking advantage of High DPI support in Windows Forms applications, see [High DPI Support in Windows Forms](../../../../../docs/framework/winforms/high-dpi-support-in-windows-forms.md).</span></span>
 
### <a name="disabledpichangedmessagehandling"></a><span data-ttu-id="ac95c-187">DisableDpiChangedMessageHandling</span><span class="sxs-lookup"><span data-stu-id="ac95c-187">DisableDpiChangedMessageHandling</span></span>

<span data-ttu-id="ac95c-188">从.NET Framework 4.7 开始，Windows 窗体控件引发与 DPI 缩放更改相关的事件数。</span><span class="sxs-lookup"><span data-stu-id="ac95c-188">Starting with the .NET Framework 4.7, Windows Forms controls raise a number of events related to changes in DPI scaling.</span></span> <span data-ttu-id="ac95c-189">其中包括<xref:System.Windows.Forms.Control.DpiChangedAfterParent>， <xref:System.Windows.Forms.Control.DpiChangedBeforeParent>，和<xref:System.Windows.Forms.Form.DpiChanged>事件。</span><span class="sxs-lookup"><span data-stu-id="ac95c-189">These include the <xref:System.Windows.Forms.Control.DpiChangedAfterParent>, <xref:System.Windows.Forms.Control.DpiChangedBeforeParent>, and <xref:System.Windows.Forms.Form.DpiChanged> events.</span></span> <span data-ttu-id="ac95c-190">值`DisableDpiChangedMessageHandling`键决定是否在 Windows 窗体应用程序会引发这些事件。</span><span class="sxs-lookup"><span data-stu-id="ac95c-190">The value of the `DisableDpiChangedMessageHandling` key determines whether these events are raised in a Windows Forms application.</span></span> 

### <a name="single-pass-scaling"></a><span data-ttu-id="ac95c-191">单个传递缩放</span><span class="sxs-lookup"><span data-stu-id="ac95c-191">Single-pass scaling</span></span>

<span data-ttu-id="ac95c-192">单个或多传递缩放影响的用户界面的感知响应能力和用户界面元素的可视外观，因为它们缩放。</span><span class="sxs-lookup"><span data-stu-id="ac95c-192">Single or multi-pass scaling influences the perceived responsiveness of the user interface and the visual appearance of user interface elements as they are scaled.</span></span> <span data-ttu-id="ac95c-193">从.NET Framework 4.7 开始，使用单个传递缩放 Windows 窗体。</span><span class="sxs-lookup"><span data-stu-id="ac95c-193">Starting with the .NET Framework 4.7, Windows Forms uses single pass scaling.</span></span> <span data-ttu-id="ac95c-194">在以前版本的.NET Framework 中，通过多个通过，这导致某些控件可按比例超过时需要执行缩放。</span><span class="sxs-lookup"><span data-stu-id="ac95c-194">In previous versions of the .NET Framework, scaling was performed through multiple passes, which caused some controls to be scaled more than was necessary.</span></span> <span data-ttu-id="ac95c-195">如果你的应用程序依赖于这一旧行为应仅禁用单个传递缩放。</span><span class="sxs-lookup"><span data-stu-id="ac95c-195">Single-pass scaling should only be disabled if your app depends on the old behavior.</span></span>  

## <a name="see-also"></a><span data-ttu-id="ac95c-196">请参阅</span><span class="sxs-lookup"><span data-stu-id="ac95c-196">See also</span></span>
 
<span data-ttu-id="ac95c-197">[Windows 窗体配置节](../../../../../docs/framework/configure-apps/file-schema/winforms/index.md) </span><span class="sxs-lookup"><span data-stu-id="ac95c-197">[Windows Forms Configuration Section](../../../../../docs/framework/configure-apps/file-schema/winforms/index.md) </span></span>  
[<span data-ttu-id="ac95c-198">Windows 窗体中的高 DPI 支持</span><span class="sxs-lookup"><span data-stu-id="ac95c-198">High DPI Support in Windows Forms</span></span>](../../../../../docs/framework/winforms/high-dpi-support-in-windows-forms.md)
