---
ms.openlocfilehash: e2d63d85adce64db6e00b62ec17f55ae71ce3052
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59803343"
---
### <a name="calling-datagridcommitedit-from-a-celleditending-handler-drops-focus"></a>从 CellEditEnding 处理程序调用 DataGrid.CommitEdit 将丢失焦点

|   |   |
|---|---|
|详细信息|从 <xref:System.Windows.Controls.DataGrid?displayProperty=name> 的一个 <xref:System.Windows.Controls.DataGrid.CellEditEnding?displayProperty=name> 事件处理程序中调用 <xref:System.Windows.Controls.DataGrid.CommitEdit> 导致 <xref:System.Windows.Controls.DataGrid?displayProperty=name> 失去焦点。|
|建议|此 bug 已在 .NET Framework 4.5.2 中得到修复，因此升级 .NET Framework 可避免出现此问题。 或者，可通过在调用 <xref:System.Windows.Controls.DataGrid.CommitEdit?displayProperty=name> 后显式重新选择 <xref:System.Windows.Controls.DataGrid?displayProperty=name> 避免出现此问题。|
|范围|边缘|
|版本|4.5|
|类型|运行时|
|受影响的 API|<ul><li><xref:System.Windows.Controls.DataGrid.CommitEdit?displayProperty=nameWithType></li><li><xref:System.Windows.Controls.DataGrid.CommitEdit(System.Windows.Controls.DataGridEditingUnit,System.Boolean)?displayProperty=nameWithType></li></ul>|
