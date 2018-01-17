---
title: "Windows 窗体 DataGridView 控件中的默认键盘和鼠标处理"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- data grids [Windows Forms], mouse handling
- DataGridView control [Windows Forms], navigation keys
- keyboards [Windows Forms], default handling in DataGridView control
- DataGridView control [Windows Forms], keyboard handling
- mouse [Windows Forms], default handling in DataGridView control
- DataGridView control [Windows Forms], mouse handling
- navigation keys [Windows Forms], DataGridView control
ms.assetid: 4519b928-bfc8-4e8b-bb9c-b1e76a0ca552
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 627784f3d68ddf03f1f6c94975405dded3163c06
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="default-keyboard-and-mouse-handling-in-the-windows-forms-datagridview-control"></a>Windows 窗体 DataGridView 控件中的默认键盘和鼠标处理
下表描述用户如何与交互<xref:System.Windows.Forms.DataGridView>控制通过键盘和鼠标。  
  
> [!NOTE]
>  若要自定义键盘行为，可以处理标准键盘事件，如<xref:System.Windows.Forms.Control.KeyDown>。 但是，在编辑模式下，在托管的编辑控件接收键盘输入和键盘事件将不会对<xref:System.Windows.Forms.DataGridView>控件。 若要处理编辑的控件事件，请将您的处理程序附加到中的编辑控件<xref:System.Windows.Forms.DataGridView.EditingControlShowing>事件处理程序。 或者，你可以自定义中的键盘行为<xref:System.Windows.Forms.DataGridView>通过重写子类<xref:System.Windows.Forms.DataGridView.ProcessDialogKey%2A>和<xref:System.Windows.Forms.DataGridView.ProcessDataGridViewKey%2A>方法。  
  
## <a name="default-keyboard-handling"></a>默认键盘处理  
  
### <a name="basic-navigation-and-entry-keys"></a>基本导航和输入键  
  
|键或键组合|描述|  
|----------------------------|-----------------|  
|向下键|将焦点移到当前单元格的正下方的单元格。 如果最后一行中有焦点，则没有任何影响。|  
|向左键|将焦点移到上一个单元格的行中。 焦点位于行中的第一个单元格，如果没有任何影响。|  
|向右键|将焦点移到行中的下一个单元。 焦点位于行中的最后一个单元格，如果没有任何影响。|  
|向上键|将焦点移到当前单元格上方直接的单元格。 如果第一行中有焦点，则没有任何影响。|  
|Home|将焦点移到当前行中的第一个单元。|  
|End|将焦点移到当前行中的最后一个单元。|  
|PAGE DOWN|控件向下滚动完全显示的行数。 将焦点移到完全显示的最后一行中，而无需更改列。|  
|PAGE UP|按照完全显示的行数向上滚动控件。 将焦点移到而无需更改列显示的第一行。|  
|Tab|如果<xref:System.Windows.Forms.DataGridView.StandardTab%2A>属性值是`false`，将焦点移到当前行中的下一个单元。 如果焦点的行的最后一个单元中已存在，请将焦点移到下一行中的第一个单元格。 如果焦点在控件中的最后一个单元中，将焦点移到下一个控件的父容器的 tab 键顺序。<br /><br /> 如果<xref:System.Windows.Forms.DataGridView.StandardTab%2A>属性值是`true`，将焦点移到下一个控件的父容器的 tab 键顺序。|  
|Shift+Tab|如果<xref:System.Windows.Forms.DataGridView.StandardTab%2A>属性值是`false`，将焦点移到当前行中上一个单元格。 如果焦点的行的第一个单元中已存在，请将焦点移到前一行中的最后一个单元。 如果焦点在控件中的第一个单元中，将焦点移到上一个控件的父容器的 tab 键顺序。<br /><br /> 如果<xref:System.Windows.Forms.DataGridView.StandardTab%2A>属性值是`true`，将焦点移到上一个控件的父容器的 tab 键顺序。|  
|Ctrl+Tab|如果<xref:System.Windows.Forms.DataGridView.StandardTab%2A>属性值是`false`，将焦点移到下一个控件的父容器的 tab 键顺序。<br /><br /> 如果<xref:System.Windows.Forms.DataGridView.StandardTab%2A>属性值是`true`，将焦点移到当前行中的下一个单元。 如果焦点的行的最后一个单元中已存在，请将焦点移到下一行中的第一个单元格。 如果焦点在控件中的最后一个单元中，将焦点移到下一个控件的父容器的 tab 键顺序。|  
|Ctrl+Shift+Tab|如果<xref:System.Windows.Forms.DataGridView.StandardTab%2A>属性值是`false`，将焦点移到上一个控件的父容器的 tab 键顺序。<br /><br /> 如果<xref:System.Windows.Forms.DataGridView.StandardTab%2A>属性值是`true`，将焦点移到当前行中上一个单元格。 如果焦点的行的第一个单元中已存在，请将焦点移到前一行中的最后一个单元。 如果焦点在控件中的第一个单元中，将焦点移到上一个控件的父容器的 tab 键顺序。|  
|按 CTRL + 箭头|将焦点移到的最远的单元格箭头的方向。|  
|CTRL + HOME|将焦点移到控件中的第一个单元。|  
|CTRL + END|将焦点移到控件中的最后一个单元。|  
|CTRL + PAGE 下移/上|向下翻页或向上翻页相同。|  
|F2|将当前单元格置于单元格编辑模式，如果<xref:System.Windows.Forms.DataGridView.EditMode%2A>属性值是<xref:System.Windows.Forms.DataGridViewEditMode.EditOnF2>或<xref:System.Windows.Forms.DataGridViewEditMode.EditOnKeystrokeOrF2>。|  
|F4|如果当前单元格是<xref:System.Windows.Forms.DataGridViewComboBoxCell>、 将单元格置于编辑模式和显示的下拉列表。|  
|ALT + 向上/向下键|如果当前单元格是<xref:System.Windows.Forms.DataGridViewComboBoxCell>、 将单元格置于编辑模式和显示的下拉列表。|  
|空格键|如果当前单元格是<xref:System.Windows.Forms.DataGridViewButtonCell>， <xref:System.Windows.Forms.DataGridViewLinkCell>，或<xref:System.Windows.Forms.DataGridViewCheckBoxCell>，引发<xref:System.Windows.Forms.DataGridView.CellClick>和<xref:System.Windows.Forms.DataGridView.CellContentClick>事件。 如果当前单元格是<xref:System.Windows.Forms.DataGridViewButtonCell>，还会按下按钮。 如果当前单元格是<xref:System.Windows.Forms.DataGridViewCheckBoxCell>，也会更改的复选状态。|  
|Enter|提交对当前单元格和行所有更改并将焦点移动到当前单元格的正下方的单元格。 如果最后一行中有焦点，而无需移动焦点提交任何更改。|  
|Esc|如果控件处于编辑模式，则取消编辑。 如果控件不处于编辑模式中，将恢复如果该控件绑定到支持编辑数据源已对当前行进行任何更改，或已经行级提交作用域以实现虚拟模式。|  
|退格符|编辑单元格时，请删除该插入点之前的字符。|  
|DELETE|编辑单元格时，请在插入点后删除的字符。|  
|Ctrl+Enter|提交到当前单元格的任何更改，而无需移动焦点。 此外提交对当前行，如果该控件绑定到数据源支持编辑或虚拟模式的任何更改已与实现行级提交作用域。|  
|Ctrl+0|进入<xref:System.DBNull.Value?displayProperty=nameWithType>时可以编辑的单元格的当前单元格中的值。 默认情况下，显示值为<xref:System.DBNull>单元格的值是值<xref:System.Windows.Forms.DataGridViewCellStyle.NullValue%2A>属性<xref:System.Windows.Forms.DataGridViewCellStyle>对当前单元格生效。|  
  
### <a name="selection-keys"></a>选择键  
 如果<xref:System.Windows.Forms.DataGridView.MultiSelect%2A>属性设置为`false`和<xref:System.Windows.Forms.DataGridView.SelectionMode%2A>属性设置为<xref:System.Windows.Forms.DataGridViewSelectionMode.CellSelect>，通过使用导航键来更改当前单元格更改为新的单元格的所选内容。 SHIFT、 CTRL 和 ALT 键不会影响此行为。  
  
 如果<xref:System.Windows.Forms.DataGridView.SelectionMode%2A>设置为<xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect>或<xref:System.Windows.Forms.DataGridViewSelectionMode.ColumnHeaderSelect>，相同的行为发生但添加了以下内容。  
  
|键或键组合|描述|  
|----------------------------|-----------------|  
|SHIFT + 空格键|选择整行或列 （与单击行或列标题相同）。|  
|导航键 （箭头键，页向上/向下，主页，结束）|如果选择整行或列，则更改为新行或列的当前单元格将所选内容移动到完整的新行或列 （具体取决于所选内容模式中）。|  
  
 如果<xref:System.Windows.Forms.DataGridView.MultiSelect%2A>设置为`false`和<xref:System.Windows.Forms.DataGridView.SelectionMode%2A>设置为<xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect>或<xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect>，通过使用键盘更改为新行或列的当前单元格将所选项移到完整的新行或列。 SHIFT、 CTRL 和 ALT 键不会影响此行为。  
  
 如果<xref:System.Windows.Forms.DataGridView.MultiSelect%2A>设置为`true`、 导航行为不会更改，但是使用键盘导航按住 SHIFT （包括 CTRL + SHIFT） 的同时会修改多单元格选择。 导航开始之前，该控件会将当前单元格标记为定位单元格。 当你导航在按住 SHIFT 的同时，所选内容将包括的定位单元格和当前单元格之间的所有单元格。 如果已选择它们，但如果键盘导航临时将其置于当前单元格的定位单元格之间则会取消选定，则将保持所选控件中的其他单元格。  
  
 如果<xref:System.Windows.Forms.DataGridView.MultiSelect%2A>设置为`true`和<xref:System.Windows.Forms.DataGridView.SelectionMode%2A>设置为<xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect>或<xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect>、 定位单元格和当前单元格的行为相同，但仅完整行或列成为选中或取消选中。  
  
## <a name="default-mouse-handling"></a>默认鼠标处理  
  
### <a name="basic-mouse-handling"></a>基本鼠标处理  
  
> [!NOTE]
>  单击包含鼠标左键的单元格始终将更改当前单元格。 单击鼠标右键按钮包含的单元格会打开快捷菜单上，如果可用。  
  
|鼠标操作|描述|  
|------------------|-----------------|  
|按下鼠标左键|使被单击的单元格成为当前单元格，并引发<xref:System.Windows.Forms.DataGridView.CellMouseDown?displayProperty=nameWithType>事件。|  
|释放鼠标左键|引发 <xref:System.Windows.Forms.DataGridView.CellMouseUp?displayProperty=nameWithType> 事件|  
|鼠标左键单击|引发<xref:System.Windows.Forms.DataGridView.CellClick?displayProperty=nameWithType>和<xref:System.Windows.Forms.DataGridView.CellMouseClick?displayProperty=nameWithType>事件|  
|向下鼠标左键并拖动列标题单元格上|如果<xref:System.Windows.Forms.DataGridView.AllowUserToOrderColumns%2A?displayProperty=nameWithType>属性是`true`，移动所列，以便它可以放入新的位置。|  
  
### <a name="mouse-selection"></a>鼠标选择  
 没有选择行为是与鼠标中键或鼠标滚轮相关联。  
  
 如果<xref:System.Windows.Forms.DataGridView.MultiSelect%2A>属性设置为`false`和<xref:System.Windows.Forms.DataGridView.SelectionMode%2A>属性设置为<xref:System.Windows.Forms.DataGridViewSelectionMode.CellSelect>，会出现下列行为。  
  
|鼠标操作|描述|  
|------------------|-----------------|  
|单击鼠标左键|如果用户单击单元格，则选择仅对当前单元格。 如果用户单击行或列标题没有选择行为。|  
|单击鼠标右键按钮|如果有的话，则显示快捷菜单。|  
  
 相同的行为发生时<xref:System.Windows.Forms.DataGridView.SelectionMode%2A>设置为<xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect>或<xref:System.Windows.Forms.DataGridViewSelectionMode.ColumnHeaderSelect>，只不过，具体取决于所选内容模式中，单击行或列标题将选择整行或列并设置当前单元格的行或列中的第一个单元格。  
  
 如果<xref:System.Windows.Forms.DataGridView.SelectionMode%2A>设置为<xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect>或<xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect>，单击行或列中的任何单元格将选择整行或列。  
  
 如果<xref:System.Windows.Forms.DataGridView.MultiSelect%2A>设置为`true`，按住 CTRL 或 SHIFT 的同时单击单元格将修改多单元格选择。  
  
 按住 CTRL 的同时单击单元格时，该单元格将更改其所选内容状态，而所有其他单元格保持其当前的选择状态。  
  
 按住 SHIFT 的同时单击一个单元格或一系列单元格，所选内容将包括当前单元格位于第一次单击之前对当前单元格的位置定位单元格之间的所有单元格。 单击并拖动指针跨多个单元格的定位单元格时，单击在拖动操作开始处的单元格。 随后按下 shift 键的同时单击更改当前单元格，但不是定位单元格。 如果已选择它们，但如果鼠标导航临时将其置于当前单元格的定位单元格之间则会取消选定，则将保持所选控件中的其他单元格。  
  
 如果<xref:System.Windows.Forms.DataGridView.MultiSelect%2A>设置为`true`和<xref:System.Windows.Forms.DataGridView.SelectionMode%2A>设置为<xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect>或<xref:System.Windows.Forms.DataGridViewSelectionMode.ColumnHeaderSelect>，在按住 SHIFT 的同时单击行或列标题 （具体取决于所选内容模式中） 将修改的完整行或列的现有选择，如果此类所选内容存在。 否则为将清除所选内容并开始新选择的完整行或列。 按住 CTRL 的同时单击行或列标题，但是，将添加或从当前所选内容中删除被单击的行或列，不会以其他方式修改当前所选内容。  
  
 如果<xref:System.Windows.Forms.DataGridView.MultiSelect%2A>设置为`true`和<xref:System.Windows.Forms.DataGridView.SelectionMode%2A>设置为<xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect>或<xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect>、 按住 SHIFT 或 CTRL 的同时单击单元格的行为相同的方式，除非该只能使用完整的行和列会受到影响。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Forms.DataGridView>  
 [DataGridView 控件](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)
