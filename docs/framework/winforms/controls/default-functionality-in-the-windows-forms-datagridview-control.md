---
title: Windows 窗体 DataGridView 控件中的默认功能
ms.date: 03/30/2017
helpviewer_keywords:
- data grids [Windows Forms], default functionality in DataGridView control
- DataGridView control [Windows Forms], default functionality
ms.assetid: 4405f697-cad1-4839-9bcd-8ddb09d9f00e
ms.openlocfilehash: a475d8bce388860c88571fbf638d206bfe01223d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33526622"
---
# <a name="default-functionality-in-the-windows-forms-datagridview-control"></a>Windows 窗体 DataGridView 控件中的默认功能
Windows 窗体<xref:System.Windows.Forms.DataGridView>控件向用户提供大量的默认功能。  
  
## <a name="default-functionality"></a>默认功能  
 默认情况下，<xref:System.Windows.Forms.DataGridView>控件：  
  
-   自动显示列标题和垂直滚动表时保持可见的行标题。  
  
-   具有行标头，其中包含当前行的选择指示器。  
  
-   已选择矩形中的第一个单元。  
  
-   具有当用户双击列分隔线可以自动调整的列。  
  
-   自动支持在 Windows XP 和 Windows Server 2003 系列上的视觉样式时<xref:System.Windows.Forms.Application.EnableVisualStyles%2A>从应用程序的调用方法`Main`方法。  
  
 此外，内容<xref:System.Windows.Forms.DataGridView>控件可以编辑默认情况下：  
  
-   如果用户双击或按下 F2 在单元格中，该控件将自动将单元格置于编辑模式，并更新的用户类型作为单元格的内容。  
  
-   如果用户滚动到网格的结尾时，用户将看到用于添加新记录行是否存在。 当用户单击此行时，将新行添加到<xref:System.Windows.Forms.DataGridView>控件，使用默认值。 当用户按 ESC 时，此新行将会消失。  
  
-   如果用户单击行标题，则选择整个行。  
  
 当绑定<xref:System.Windows.Forms.DataGridView>控件添加到数据源通过设置其<xref:System.Windows.Forms.DataGridView.DataSource%2A>属性、 控件：  
  
-   自动使用数据源的列的名称作为列标题文本。  
  
-   使用数据源的内容填充。 <xref:System.Windows.Forms.DataGridView> 为数据源中的每一列自动创建列。  
  
-   表中创建每个可见行的行。  
  
-   自动对基于基础数据，当用户单击列标题行进行排序。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Forms.DataGridView>  
 [DataGridView 控件](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)
