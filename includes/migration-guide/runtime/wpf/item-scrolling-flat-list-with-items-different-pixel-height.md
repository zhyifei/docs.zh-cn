---
ms.openlocfilehash: 088ebad0f822f791d05a8a8dafb0f7fd74f5581a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59774126"
---
### <a name="item-scrolling-a-flat-list-with-items-of-different-pixel-height"></a>项滚动包含不同像素高度的项的平面列表

|   |   |
|---|---|
|详细信息|当 <xref:System.Windows.Controls.ItemsControl?displayProperty=name> 使用虚拟化 (<code>IsVirtualizing=true</code>) 和项滚动 (<code>ScrollUnit=Item</code>) 显示集合时，以及控件滚动显示像素高度不同于其相邻项的项时，<xref:System.Windows.Controls.VirtualizingStackPanel?displayProperty=name> 将循环访问集合中的所有项。 UI 在迭代期间无响应，如果集合很大，可以将此视为挂起。即使在之前的 .NET Framework 版本中，其他情况下也会发生迭代。 例如，在以下情况下会出现上述情形：遇到像素高度不同的项时进行像素滚动 (<code>ScrollUnit=Pixel</code>)，以及遇到子项数量不同于其相邻项的项时进行项滚动分层数据（例如，<xref:System.Windows.Controls.TreeView?displayProperty=name> 或已启用分组的 <xref:System.Windows.Controls.ItemsControl?displayProperty=name>）。对于项滚动和不同像素高度的情况，.NET Framework 4.6.1 中引入了迭代以修复分层数据布局中的 bug。  如果数据采用平面结构（没有层次结构），则不需要迭代，.NET Framework 4.6.2 在这种情况下也不会执行该操作。|
|建议|如果迭代发生在 .NET Framework 4.6.1 中，但在以前版本中并未发生 - 也就是说，如果 <xref:System.Windows.Controls.ItemsControl?displayProperty=name> 项滚动含有像素高度不同的项的平面列表 - 可采用以下两种补救措施：<ol><li>安装 .NET Framework 4.6.2。</li><li>安装适用于 .NET Framework 4.6.1 的修补程序 HR 1605。</li></ol>|
|范围|次要|
|版本|4.6.1|
|类型|运行时|
|受影响的 API|<ul><li><xref:System.Windows.Controls.VirtualizingStackPanel?displayProperty=nameWithType></li></ul>|
