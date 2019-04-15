---
ms.openlocfilehash: 4eac93d5cfea19cb83c66cd3fe35c1b0703c0cc0
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59233928"
---
### <a name="wpf-focusvisual-for-radiobutton-and-checkbox-now-displays-correctly-when-the-controls-have-no-content"></a>RadioButton 和 CheckBox 的 WPF FocusVisual 现可在控件无内容时正确显示

|   |   |
|---|---|
|详细信息|在 .NET Framework 4.7.1 和更早版本中，WPF <xref:System.Windows.Controls.CheckBox?displayProperty=nameWIthType> 和 <xref:System.Windows.Controls.RadioButton?displayProperty=nameWIthType> 不一致且在经典和高对比度主题中具有不正确的焦点视觉对象。  控件没有内容集时会出现这些问题。  这会使得主题间的转换变得混乱且难以看到焦点视觉对象。 现在，在 .NET Framework 4.7.2 中，主题间的这些视觉对象更加一致，并且在经典和高对比度主题中更轻松可见。|
|建议|如果开发人员面向 .NET Framework 4.7.2，但要还原到 .NET 4.7.1 行为，则需要设置以下 AppContext 标记。<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.UseLegacyAccessibilityFeatures.2=true;&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>如果开发人员面向 .NET 4.7.2 以下的框架版本，但想要利用此更改，则必须设置以下 AppContext 标记。请注意，必须正确设置所有标记，并且安装的 .NET Framework 版本必须是 4.7.2 或更高版本。WPF 应用程序需选择启用所有的早期辅助功能改进，才能获取最新改进。 若要执行此操作，请确保将“Switch.UseLegacyAccessibilityFeatures”和“Switch.UseLegacyAccessibilityFeatures.2”这两个 AppContext 开关设置为 false。<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.UseLegacyAccessibilityFeatures=false;Switch.UseLegacyAccessibilityFeatures.2=false;&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>|
|范围|边缘|
|版本|4.7.2|
|类型|重定目标|
