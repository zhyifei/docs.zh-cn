---
ms.openlocfilehash: 1545c807e3bef675e63e14d01ab82c1131600f39
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235196"
---
### <a name="itemsclear-does-not-remove-duplicates-from-selecteditems"></a>Items.Clear 不会从 SelectedItems 删除重复项

|   |   |
|---|---|
|详细信息|假设选择器（已启用多个选择）在其 <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=name> 集合中有多个重复项（出现不止一次的相同项）。  从数据源删除这些项（例如通过调用 Items.Clear）不会从 <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=name> 删除它们；仅删除第一个实例。 此外，随后使用 <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=name>（例如 SelectedItems.Clear()）可能会遇到 <xref:System.ArgumentException?displayProperty=name> 等问题，这是因为 <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=name> 包含不再出现在数据源中的项。|
|建议|如果可能请升级到 .NET Framework 4.6.2。|
|范围|次要|
|版本|4.5|
|类型|运行时|
|受影响的 API|<ul><li><xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=nameWithType></li></ul>|
