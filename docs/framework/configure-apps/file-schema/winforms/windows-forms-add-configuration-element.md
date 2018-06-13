---
title: Windows 窗体添加配置元素
ms.date: 04/07/2017
helpviewer_keywords:
- Windows Forms Add configuration element
- configuring Windows Forms applications
ms.assetid: 3e3e04de-99d1-4658-b716-44cb669d9589
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 529dbccd5ddb4dd1f1456fb9a6043f3c5f7b378d
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
ms.locfileid: "32759655"
---
# <a name="windows-forms-add-configuration-element"></a>Windows 窗体添加配置元素

`<add>`元素将添加指定 Windows 窗体应用程序是否支持添加到.NET Framework 4.7 或更高版本的 Windows 窗体应用的功能的预定义的键。

## <a name="syntax"></a>语法

```xml
<System.Windows.Forms.ApplicationConfigurationSection>
  <add key="key-name" value="key-value" />
</System.Windows.Forms.ApplicationConfigurationSection>
```

## <a name="attributes-and-elements"></a>特性和元素

下列各节描述了特性、子元素和父元素。

### <a name="attributes"></a>特性

| 特性 | 描述 |
| --------- | ----------- |
| `key`     | 必需的特性。 预定义的密钥名称对应于特定的 Windows 窗体可自定义功能。 |
| `value`   | 必需的特性。 要赋给 `key` 的值。 |

### <a name="key-attribute-names-and-associated-values"></a>`key` 特性名称和关联的值

| `key` 名称 | 值 | 描述 |
| ---------- | ------ | ----------- |
| "AnchorLayout.DisableSinglePassControlScaling" | "true"&#124;"false" | 指示是否已锚定的控件调整单个传递中。 "true"以禁用单个传递缩放;否则为 false。 请参阅中的"单通过缩放"一节[备注](#Remarks)有关详细信息。 |
| "DpiAwareness" | "PerMonitorV2"&#124;"false" | 指示是否 DPI 感知应用程序。 设置为"PerMonitorV2"，以支持 Dpi 感知; 密钥否则，将其设置为"false"。 DPI 感知是一项可以选择使用的功能;若要充分利用 Windows 窗体的高 DPI 支持，应设置为"PerMonitorV2"其值。 请参阅[备注](#remarks)部分以了解更多信息。 |
| "CheckedListBox.DisableHighDpiImprovements" | "true"&#124;"false" | 指示是否<xref:System.Windows.Forms.CheckedListBox>控制所采用的.NET Framework 4.7 中引入的缩放和布局改进的优点。 "true"来选择退出 caling 和布局改进;否则为"false"。 |
| "DataGridView.DisableHighDpiImprovements" | "true"&#124;"false" | 指示是否<xref:System.Windows.Forms.DataGridView>控制.NET Framework 4.7 中引入的缩放和布局改进。 "true"来选择退出 DPI 感知;"false"否则为。 |
| "DisableDpiChangedMessageHandling" | "true"&#124;"false" | "true"来选择退出接收与 DPI 缩放更改; 相关的消息"false"否则为。 请参阅[备注](#remarks)部分以了解更多信息。 |
| "EnableWindowsFormsHighDpiAutoResizing" | "true"&#124;"false" | 指示是否自动调整 Windows 窗体应用程序大小由于 DPI 缩放更改。 "true"以启用自动调整大小;否则为 false。 |
| "Form.DisableSinglePassControlScaling" | "true"&#124;"false" | 指示是否<xref:System.Windows.Forms.Form>扩展单个传递中。 "true"以禁用次传递缩放;否则为 false。 请参阅中的"单通过缩放"一节[备注](#Remarks)有关详细信息。 |
| "MonthCalendar.DisableSinglePassControlScaling" | "true"&#124;"false" | 指示是否<xref:System.Windows.Forms.MonthCalendar>单个传递中缩放控件。 "true"以禁用次传递缩放;否则为 false。 请参阅中的"单通过缩放"一节[备注](#Remarks)有关详细信息。 |
| "Toolstrip.DisableHighDpiImprovements" | "true"&#124;"false" | 指示是否<xref:System.Windows.Forms.ToolStrip>控制所采用的.NET Framework 4.7 中引入的缩放和布局改进的优点。 "true"来选择退出 DPI 感知;"false"否则为。 |

### <a name="child-elements"></a>子元素

无。

### <a name="parent-elements"></a>父元素

| 元素 | 描述 |
| ------- | ----------- |
| [`<System.Windows.Forms.ApplicationConfigurationSection>`](../../../../../docs/framework/configure-apps/file-schema/winforms/index.md) | 配置对新 Windows 窗体应用程序功能的支持。 |

## <a name="a-nameremarks--remarks"></a><a name="remarks" /> 备注

从 .NET Framework 4.7 开始，`<System.Windows.Forms.ApplicationConfigurationSection>` 元素允许配置 Windows 窗体应用程序，以利用最新版本的 .NET Framework 中添加的功能。 

`<System.Windows.Forms.ApplicationConfigurationSection>`元素，你可以添加一个或多个子`<add>`元素，其中每个定义特定配置设置。  

Windows 窗体高 DPI 支持的概述，请参阅[高 DPI 支持 Windows 窗体中](../../../../../docs/framework/winforms/high-dpi-support-in-windows-forms.md)。

### <a name="dpiawareness"></a>DpiAwareness

可以配置从.NET Framework 4.7 开始开始的 Windows 10 创建者版本和.NET Framework 目标版本的 Windows 版本下运行的 Windows 窗体应用程序以利用.NET Framework 中引入的高 DPI 改进4.7。 这些方法包括：

- 动态 Windows 窗体应用程序已启动后用户更改的 DPI 或缩放系数的 DPI 方案的支持。

- 缩放和多个 Windows 窗体的布局中的改进控件，如<xref:System.Windows.Forms.MonthCalendar>控件和<xref:System.Windows.Forms.CheckedListBox>控件。 

高 DPI 感知是一项可以选择使用的功能;默认情况下，值`DpiAwareness`是`false`。 你可以选择加入 Windows 窗体支持为了 DPI 感知通过此密钥来将值设置`PerMonitorV2`应用程序配置文件中。 如果启用了 DPI 感知，还将启用所有各项 DPI 功能。 这些方法包括：

- DPI 更改消息不同，后者由控制`DisableDpiChangedMessageHandling`密钥。

- 动态 DPI 支持，它由控制`EnableWindowsFormsHighDpiAutoResizing`密钥。

- 单个传递控件缩放，这由控制`Form.DisableSinglePassControlScaling`个人<xref:System.Windows.Forms.Form>控件，通过`AnchorLayout.DisableSinglePassControlScaling`针对锚定控件，并按密钥`MonthCalendar.DisableSinglePassControlScaling`键<xref:System.Windows.Forms.MonthCalendar>控件 

- 高 DPI 缩放和布局改进，其由控制`CheckListBox.DisableHighDpiImprovements`键<xref:System.Windows.Forms.CheckedListBox>控制，请通过`DataGridView.DisableHighDpiImprovements`键<xref:System.Windows.Forms.DataGridView>控件，并通过`Toolstrip.DisableHighDpiImprovements`键<xref:System.Windows.Forms.ToolStrip>控件。  

通过设置提供选择加入设置一个默认`DpiAwareness`到`PerMonitorV2`通常足以满足新的 Windows 窗体应用程序。 但是，你可以然后选择退出各个高 DPI 改进将相应的项添加到应用程序配置文件。 例如，若要利用动态 DPI 支持除外的所有新 DPI featuers，要到你的应用程序配置文件添加以下：

```xml
<System.Windows.Forms.ApplicationConfigurationSection>
   <add key="DpiAwareness" value="PerMonitorV2" />
   <--! Disable dynamic DPI support -->
   <add key="EnableWindowsFormsHighDpiAutoResizing" value="false" />
</System.Windows.Forms.ApplicationConfigurationSection>
```
通常情况下，你选择退出特定功能因为您已选择以编程方式处理。

利用 Windows 窗体应用程序中的高 DPI 支持的详细信息，请参阅[高 DPI 支持 Windows 窗体中](../../../../../docs/framework/winforms/high-dpi-support-in-windows-forms.md)。
 
### <a name="disabledpichangedmessagehandling"></a>DisableDpiChangedMessageHandling

从.NET Framework 4.7 开始，Windows 窗体控件引发与 DPI 缩放更改相关的事件数。 其中包括<xref:System.Windows.Forms.Control.DpiChangedAfterParent>， <xref:System.Windows.Forms.Control.DpiChangedBeforeParent>，和<xref:System.Windows.Forms.Form.DpiChanged>事件。 值`DisableDpiChangedMessageHandling`键决定是否在 Windows 窗体应用程序会引发这些事件。 

### <a name="single-pass-scaling"></a>单个传递缩放

单个或多传递缩放影响的用户界面的感知响应能力和用户界面元素的可视外观，因为它们缩放。 从.NET Framework 4.7 开始，使用单个传递缩放 Windows 窗体。 在以前版本的.NET Framework 中，通过多个通过，这导致某些控件可按比例超过时需要执行缩放。 如果你的应用程序依赖于这一旧行为应仅禁用单个传递缩放。  

## <a name="see-also"></a>请参阅
 
[Windows 窗体配置节](../../../../../docs/framework/configure-apps/file-schema/winforms/index.md)   
[Windows 窗体中的高 DPI 支持](../../../../../docs/framework/winforms/high-dpi-support-in-windows-forms.md)
