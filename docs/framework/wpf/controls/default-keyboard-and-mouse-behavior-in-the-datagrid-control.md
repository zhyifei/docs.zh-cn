---
title: DataGrid 控件中的默认键盘和鼠标行为
ms.date: 03/30/2017
helpviewer_keywords:
- DataGrid [WPF], keyboard behavior
- DataGrid [WPF], mouse behavior
- keyboard behavior [WPF], DataGrid
- mouse behavior [WPF], DataGrid
ms.assetid: 563b8854-ca39-4d97-8235-17eaa0f93c8d
ms.openlocfilehash: 559b84d3e6b5ece6c71f17e6766cac4ec14824cb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="default-keyboard-and-mouse-behavior-in-the-datagrid-control"></a>DataGrid 控件中的默认键盘和鼠标行为
本主题介绍用户如何与交互<xref:System.Windows.Controls.DataGrid>通过使用键盘和鼠标的控件。  
  
 与典型交互<xref:System.Windows.Controls.DataGrid>包括导航、 选择和编辑。 选择行为受<xref:System.Windows.Controls.DataGrid.SelectionMode%2A>和<xref:System.Windows.Controls.DataGrid.SelectionUnit%2A>属性。 本主题中导致所述的行为的默认值是<xref:System.Windows.Controls.DataGridSelectionMode.Extended?displayProperty=nameWithType>和<xref:System.Windows.Controls.DataGridSelectionUnit.FullRow?displayProperty=nameWithType>。 更改这些值可能会导致不同于所描述的行为。 编辑控件时的单元格处于编辑模式，可能会重写的标准键盘行为<xref:System.Windows.Controls.DataGrid>。  
  
## <a name="default-keyboard-behavior"></a>默认键盘行为  
 下表列出的默认键盘行为<xref:System.Windows.Controls.DataGrid>。  
  
|键或键组合|描述|  
|----------------------------|-----------------|  
|向下键|将焦点移到当前单元格的正下方的单元格。 如果最后一行中有焦点，按向下箭头没有任何影响。|  
|向上键|将焦点移到当前单元格上方直接的单元格。 如果第一行中有焦点，则按向上键没有任何影响。|  
|向左键|将焦点移到上一个单元格的行中。 如果焦点位于行中的第一个单元格，按向左键会执行任何操作。|  
|向右键|将焦点移到行中的下一个单元。 如果焦点位于行中的最后一个单元格，按右箭头没有任何影响。|  
|Home|将焦点移到当前行中的第一个单元。|  
|End|将焦点移到当前行中的最后一个单元。|  
|PAGE DOWN|如果行不分组，控件向下滚动完全显示的行数。 将焦点移到完全显示的最后一行中，而无需更改列。<br /><br /> 如果行分组，将焦点移到中的最后一行<xref:System.Windows.Controls.DataGrid>而无需更改列。|  
|PAGE UP|如果行不分组，按照完全显示的行数向上滚动控件。 将焦点移到而无需更改列显示的第一行。<br /><br /> 如果行分组，将焦点移到中的第一行<xref:System.Windows.Controls.DataGrid>而无需更改列。|  
|Tab|将焦点移到当前行中的下一个单元。 焦点位于该行的最后一个单元格，如果将焦点移到下一行中的第一个单元格。 如果焦点在控件中的最后一个单元中，将焦点移到下一个控件的父容器的 tab 键顺序。<br /><br /> 如果当前单元格处于编辑模式并按 tab 键引起焦点将从当前行移开，对行进行了任何更改提交之前更改焦点。|  
|Shift+Tab|将焦点移到当前行中上一个单元格。 如果焦点的行的第一个单元中已存在，请将焦点移到前一行中的最后一个单元。 如果焦点在控件中的第一个单元中，将焦点移到上一个控件的父容器的 tab 键顺序。<br /><br /> 如果当前单元格处于编辑模式并按 tab 键引起焦点将从当前行移开，对行进行了任何更改提交之前更改焦点。|  
|Ctrl+向下键|将焦点移到当前的列中的最后一个单元格。|  
|Ctrl+向上键|将焦点移到当前的列中的第一个单元格。|  
|Ctrl+向右键|将焦点移到当前行中的最后一个单元。|  
|Ctrl+向左键|将焦点移到当前行中的第一个单元。|  
|CTRL + HOME|将焦点移到控件中的第一个单元。|  
|CTRL + END|将焦点移到控件中的最后一个单元。|  
|Ctrl+Page Down|向下翻页相同。|  
|Ctrl+Page Up|PAGE UP 相同。|  
|F2|如果<xref:System.Windows.Controls.DataGrid.IsReadOnly%2A?displayProperty=nameWithType>属性是`false`和<xref:System.Windows.Controls.DataGridColumn.IsReadOnly%2A?displayProperty=nameWithType>属性是`false`对于当前的列中，将当前的单元格进入单元格的编辑模式。|  
|Enter|提交对当前单元格和行所有更改并将焦点移动到当前单元格的正下方的单元格。 如果最后一行中有焦点，而无需移动焦点提交任何更改。|  
|Esc|如果控件处于编辑模式中，取消编辑，并将恢复该控件中所做的任何更改。 如果基础数据源实现<xref:System.ComponentModel.IEditableObject>，第二次按 esc 键取消整个行的编辑模式。|  
|退格符|编辑单元格时，请删除光标位置前的字符。|  
|DELETE|编辑单元格时，光标位置后删除的字符。|  
|Ctrl+Enter|提交到当前单元格的任何更改，而无需移动焦点。|  
|Ctrl+A|如果<xref:System.Windows.Controls.DataGrid.SelectionMode%2A>设置为<xref:System.Windows.Controls.DataGridSelectionMode.Extended>，选择中的所有行<xref:System.Windows.Controls.DataGrid>。|  
  
## <a name="selection-keys"></a>选择键  
 如果<xref:System.Windows.Controls.DataGrid.SelectionMode%2A>属性设置为<xref:System.Windows.Controls.DataGridSelectionMode.Extended>、 导航行为不会更改，但是使用键盘导航按住 SHIFT （包括 CTRL + SHIFT） 的同时会修改多行选择。 导航开始之前，控件将当前行标记为定位行。 当你导航在按住 SHIFT 的同时，所选内容将包括定位行和当前行之间的所有行。  
  
 以下的选择项修改多行选择。  
  
-   Shift+向下键  
  
-   Shift+向上键  
  
-   Shift+Page Down  
  
-   Shift+Page Up  
  
-   Ctrl+Shift+向下键  
  
-   Ctrl+Shift+向上键  
  
-   CTRL + SHIFT + HOME  
  
-   CTRL + SHIFT + END  
  
## <a name="default-mouse-behavior"></a>默认鼠标行为  
 下表列出的默认鼠标行为<xref:System.Windows.Controls.DataGrid>。  
  
|鼠标操作|描述|  
|------------------|-----------------|  
|单击未选定的行|将当前行中，并单击的单元格的当前单元格包含被单击的行。|  
|单击当前单元格|将当前单元格置于编辑模式。|  
|拖动列标题单元格|如果<xref:System.Windows.Controls.DataGrid.CanUserReorderColumns%2A?displayProperty=nameWithType>属性是`true`和<xref:System.Windows.Controls.DataGridColumn.CanUserReorder%2A?displayProperty=nameWithType>属性是`true`对于当前的列中，移动所列，因此它可以放入新的位置。|  
|拖动列标题分隔符|如果<xref:System.Windows.Controls.DataGrid.CanUserResizeColumns%2A?displayProperty=nameWithType>属性是`true`和<xref:System.Windows.Controls.DataGridColumn.CanUserResize%2A?displayProperty=nameWithType>属性是`true`对于当前的列，调整列大小。|  
|双击列标题分隔符|如果<xref:System.Windows.Controls.DataGrid.CanUserResizeColumns%2A?displayProperty=nameWithType>属性是`true`和<xref:System.Windows.Controls.DataGridColumn.CanUserResize%2A?displayProperty=nameWithType>属性是`true`当前的列中，自动大小的列使用<xref:System.Windows.Controls.DataGridLength.Auto%2A>大小调整模式。|  
|单击列标题单元格|如果<xref:System.Windows.Controls.DataGrid.CanUserSortColumns%2A?displayProperty=nameWithType>属性是`true`和<xref:System.Windows.Controls.DataGridColumn.CanUserSort%2A?displayProperty=nameWithType>属性是`true`对于当前的列中，对列进行排序。<br /><br /> 单击已排序的列标题将反向该列的排序方向。<br /><br /> 在单击多个列标题将按多个列中单击的顺序进行排序，请按住 SHIFT 键。|  
|CTRL + 单击的行|如果<xref:System.Windows.Controls.DataGrid.SelectionMode%2A>设置为<xref:System.Windows.Controls.DataGridSelectionMode.Extended>，修改非连续的多行选择。<br /><br /> 如果已选择行，则取消选择该行。|  
|按住 SHIFT 的同时单击的行|如果<xref:System.Windows.Controls.DataGrid.SelectionMode%2A>设置为<xref:System.Windows.Controls.DataGridSelectionMode.Extended>，修改连续的多行选择。|  
|单击行组头|展开或折叠组。|  
|单击左上角的全选按钮 <xref:System.Windows.Controls.DataGrid>|如果<xref:System.Windows.Controls.DataGrid.SelectionMode%2A>设置为<xref:System.Windows.Controls.DataGridSelectionMode.Extended>，选择中的所有行<xref:System.Windows.Controls.DataGrid>。|  
  
## <a name="mouse-selection"></a>鼠标选择  
 如果<xref:System.Windows.Controls.DataGrid.SelectionMode%2A>属性设置为<xref:System.Windows.Controls.DataGridSelectionMode.Extended>，按住 CTRL 或 SHIFT 的同时单击行将修改多行选择。  
  
 按住 CTRL 的同时单击某一行，该行将所选内容将其状态更改而所有其他行保持其当前的选择状态。 这样做来选择非相邻的行。  
  
 按住 SHIFT 的同时单击某一行，所选内容将包括当前行和当前行之前单击的位置定位行之间的所有行。 随后按下 shift 键的同时单击更改当前行中，而不是定位行。 这样做来选择相邻的行的范围。  
  
 CTRL + SHIFT 可结合使用来选择非相邻的范围的相邻的行。 若要执行此操作，通过使用 SHIFT 选择第一个范围 + 单击如前面所述。 选择的行的第一个范围后，使用 CTRL + 单击以选择在下一步的范围中的第一行，然后按住 CTRL + SHIFT 的同时单击下一步的范围中的最后一行。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Controls.DataGrid>  
 <xref:System.Windows.Controls.DataGrid.SelectionMode%2A>
