---
ms.openlocfilehash: e04134ec731c5e7bede3388621078c6518805ec2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2020
ms.locfileid: "67803533"
---
### <a name="add-selectiontextbrush-public-property-to-textboxpasswordbox-non-adorner-selection"></a>将 SelectionTextBrush 公共属性添加到 TextBox/PasswordBox 非装饰器选择功能

|   |   |
|---|---|
|详细信息|在使用 [ 和 ](https://github.com/Microsoft/dotnet/blob/master/Documentation/compatibility/wpf-TextBox-PasswordBox-text-selection-does-not-follow-system-colors.md) 的<xref:System.Windows.Controls.TextBox>基于非装饰器的文本选择功能<xref:System.Windows.Controls.PasswordBox>的 WPF 应用程序中，开发人员现在可以设置新添加的 SelectionTextBrush 属性，以便更改所选文本的呈现。  默认情况下，通过 <xref:System.Windows.SystemColors.HighlightTextBrushKey> 更改此颜色。  如果未启用基于非修饰器的文本选择功能，则此属性不执行任何操作。|
|建议|启用基于非装饰器的文本选择功能后，可以使用 <xref:System.Windows.Controls.PasswordBox.SelectionTextBrush?displayProperty=nameWithType> 和 <xref:System.Windows.Controls.Primitives.TextBoxBase.SelectionTextBrush> 属性更改所选文本的外观。 可以使用 XAML 实现此操作：<pre><code class="lang-xaml">&lt;TextBox SelectionBrush=&quot;Red&quot; SelectionTextBrush=&quot;White&quot;  SelectionOpacity=&quot;0.5&quot;&#13;&#10;Foreground=&quot;Blue&quot; CaretBrush=&quot;Blue&quot;&gt;&#13;&#10;This is some text.&#13;&#10;&lt;/TextBox&gt;&#13;&#10;</code></pre>|
|范围|主要|
|Version|4.8|
|类型|重定目标|
|受影响的 API|<ul><li><xref:System.Windows.Controls.Primitives.TextBoxBase.SelectionTextBrushProperty?displayProperty=nameWithType></li><li><xref:System.Windows.Controls.Primitives.TextBoxBase.SelectionTextBrush?displayProperty=nameWithType></li><li>[System.Windows.Controls.TextBox](xref:System.Windows.Controls.TextBox)</li><li>[System.Windows.Controls.PasswordBox](xref:System.Windows.Controls.PasswordBox)</li></ul>|
