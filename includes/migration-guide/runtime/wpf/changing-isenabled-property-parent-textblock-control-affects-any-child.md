---
ms.openlocfilehash: 735278848cb7399e414a128afc650a0a1f882337
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2020
ms.locfileid: "67857557"
---
### <a name="changing-the-isenabled-property-of-the-parent-of-a-textblock-control-affects-any-child-controls"></a>更改 TextBlock 控件父级的 IsEnabled 属性会影响任何子控件

|   |   |
|---|---|
|详细信息|自 .NET Framework 4.6.2 起，更改 <xref:System.Windows.Controls.TextBlock?displayProperty=name> 控件父级的 <xref:System.Windows.UIElement.IsEnabled?displayProperty=name> 属性会影响 <xref:System.Windows.Controls.TextBlock?displayProperty=name> 控件的任意子控件（例如超链接和按钮）。在 .NET Framework 4.6.1 和更早版本中，<xref:System.Windows.Controls.TextBlock?displayProperty=name> 中的控件并非始终反映 <xref:System.Windows.Controls.TextBlock?displayProperty=name> 父级的 <xref:System.Windows.UIElement.IsEnabled?displayProperty=name> 属性状态。|
|建议|无。 此更改符合 <xref:System.Windows.Controls.TextBlock?displayProperty=name> 控件中各控件的预期行为。|
|范围|次要|
|Version|4.6.2|
|类型|运行时|
|受影响的 API|<ul><li><xref:System.Windows.UIElement.IsEnabled?displayProperty=nameWithType></li></ul>|
