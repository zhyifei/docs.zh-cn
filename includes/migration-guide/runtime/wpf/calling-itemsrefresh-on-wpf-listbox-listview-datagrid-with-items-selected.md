---
ms.openlocfilehash: de73145273ad5aa5c19de55525417cfc3305b86d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59803315"
---
### <a name="calling-itemsrefresh-on-a-wpf-listbox-listview-or-datagrid-with-items-selected-can-cause-duplicate-items-to-appear-in-the-element"></a>在选定项目的 WPF ListBox、ListView 或 DataGrid 上调用 Items.Refresh 可能会导致元素中出现重复项目

|   |   |
|---|---|
|详细信息|在 .NET Framework 4.5 中，在项目已在 <xref:System.Windows.Controls.ListBox?displayProperty=name> 中选定的同时从代码中调用 ListBox.Items.Refresh 可能会导致选定项目在列表中重复。 <xref:System.Windows.Controls.ListView?displayProperty=name> 和 <xref:System.Windows.Controls.DataGrid?displayProperty=name> 会出现类似问题。 此问题已在 .NET Framework 4.6 中解决。|
|建议|在调用 <xref:System.Windows.Data.CollectionView.Refresh?displayProperty=name> 前以编程方式取消选择项，然后在调用完成后重新选择它们，可以解决此问题。 此外，此问题已在 .NET Framework 4.6 中解决，因此升级到该版本的 .NET Framework 即可解决该问题。|
|范围|次要|
|版本|4.5|
|类型|运行时|
|受影响的 API|<ul><li><xref:System.Windows.Data.CollectionView.Refresh?displayProperty=nameWithType></li></ul>|
