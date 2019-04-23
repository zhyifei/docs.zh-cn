---
ms.openlocfilehash: edd194fef27d97976f1ff45daec1cd56382bbb55
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59803340"
---
### <a name="new-enum-values-in-wpfs-pagerangeselection"></a>WPF PageRangeSelection 中的新枚举值

|   |   |
|---|---|
|详细信息|两个新成员（<xref:System.Windows.Controls.PageRangeSelection.CurrentPage?displayProperty=name> 和 <xref:System.Windows.Controls.PageRangeSelection.SelectedPages?displayProperty=name>）已添加到 <xref:System.Windows.Controls.PageRangeSelection?displayProperty=name> 枚举。|
|建议|大多数情况下，这些更改不会影响用户代码。 但是，应该修改依赖于对 <xref:System.Windows.Controls.PageRangeSelection?displayProperty=name> 类型的 <xref:System.Enum.GetNames(System.Type)> 或 <xref:System.Enum.GetValues(System.Type)> 调用中所存在特定数量元素的代码。|
|范围|边缘|
|版本|4.5|
|类型|运行时|
|受影响的 API|<ul><li><xref:System.Windows.Controls.PageRangeSelection?displayProperty=nameWithType></li></ul>|
