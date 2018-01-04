---
title: "如何：使用设计器设置 Windows 窗体 DataGrid 控件的格式"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- columns [Windows Forms], DataGrid controls
- colors [Windows Forms], applying to DataGrid controls
- DataGrid control [Windows Forms], formatting
- DataGrid control [Windows Forms], default styles
- tables [Windows Forms], formatting in DataGrid control
- formatting [Windows Forms]
ms.assetid: 533b9814-6124-49dc-9fda-085f1502609f
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9c9c82044e7136f05d64a20fb24ee0b209742caf
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-format-the-windows-forms-datagrid-control-using-the-designer"></a>如何：使用设计器设置 Windows 窗体 DataGrid 控件的格式
> [!NOTE]
>  <xref:System.Windows.Forms.DataGridView> 控件取代了 <xref:System.Windows.Forms.DataGrid> 控件并添加了功能；但是，可以选择保留 <xref:System.Windows.Forms.DataGrid> 控件以实现向后兼容并供将来使用。 有关详细信息，请参阅 [Windows 窗体 DataGridView 控件与 DataGrid 控件之间的区别](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)。  
  
 将不同的颜色应用于各个部分的<xref:System.Windows.Forms.DataGrid>控件可以帮助将在其中的信息以易于读取和解释。 颜色可以应用于行和列。 行和列可以还显示或隐藏根据你的判断。  
  
 有三个基本方面的格式设置<xref:System.Windows.Forms.DataGrid>控件：  
  
-   你可以设置属性以建立数据显示为默认样式。  
  
-   以此为基础，你可以然后自定义在运行时显示某些表的方式。  
  
-   最后，您可以修改哪些列显示在数据网格以及颜色和其他格式显示。  
  
 在格式设置数据网格中执行初始步骤，你可以设置的属性<xref:System.Windows.Forms.DataGrid>本身。 这些颜色和格式选项的窗体的基从中然后可以根据的数据表和显示的列的更改。  
  
 下面的过程需要**Windows 应用程序**具有一个窗体包含项目<xref:System.Windows.Forms.DataGrid>控件。 有关设置此类项目的信息，请参阅[如何： 创建 Windows 应用程序项目](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa)和[如何： 向 Windows 窗体添加控件](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)。 在[!INCLUDE[vsprvslong](../../../../includes/vsprvslong-md.md)]、<xref:System.Windows.Forms.DataGrid>控件将不处于**工具箱**默认情况下。 有关详细信息，请参阅[如何： 将项添加到工具箱](http://msdn.microsoft.com/en-us/458e119e-17fe-450b-b889-e31c128bd7e0)。  
  
> [!NOTE]
>  显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。 若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。 有关详细信息，请参阅 [在 Visual Studio 中自定义开发设置](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3)。  
  
### <a name="to-establish-a-default-style-for-the-datagrid-control"></a>若要建立的 DataGrid 控件的默认样式  
  
1.  选择 <xref:System.Windows.Forms.DataGrid> 控件。  
  
2.  在**属性**窗口中，根据需要设置以下属性。  
  
    |属性|描述|  
    |--------------|-----------------|  
    |<xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A>|`BackColor`属性定义的网格中偶数行的颜色。 当你将设置<xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A>为不同的颜色的属性，所有其他行设置为此新的颜色 （行 1、 3、 5 和等等）。|  
    |<xref:System.Windows.Forms.DataGrid.BackColor%2A>|网格中偶数行的背景色 （行 0、 2、 4、 6 和等等）。|  
    |<xref:System.Windows.Forms.DataGrid.BackgroundColor%2A>|而<xref:System.Windows.Forms.DataGrid.BackColor%2A>和<xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A>属性确定在网格中，行的颜色<xref:System.Windows.Forms.DataGrid.BackgroundColor%2A>属性确定行区域，该网格滚动到底部，或如果只有少量的行才可见区域以外的区域的颜色包含在网格中。|  
    |<xref:System.Windows.Forms.DataGrid.BorderStyle%2A>|网格的边框样式，之一<xref:System.Windows.Forms.BorderStyle>枚举值。|  
    |<xref:System.Windows.Forms.DataGrid.CaptionBackColor%2A>|正上方网格的网格窗口标题的背景色。|  
    |<xref:System.Windows.Forms.DataGrid.CaptionFont%2A>|在顶部网格标题的字体。|  
    |<xref:System.Windows.Forms.DataGrid.CaptionForeColor%2A>|网格的窗口标题的背景色。|  
    |<xref:System.Windows.Forms.Control.Font%2A>|用于在网格中显示文本的字体。|  
    |<xref:System.Windows.Forms.DataGrid.ForeColor%2A>|数据网格行中的数据显示字体的颜色。|  
    |<xref:System.Windows.Forms.DataGrid.GridLineColor%2A>|数据网格的网格线的颜色。|  
    |<xref:System.Windows.Forms.DataGrid.GridLineStyle%2A>|网格，其中一个单元格进行分隔线的样式<xref:System.Windows.Forms.DataGridLineStyle>枚举值。|  
    |<xref:System.Windows.Forms.DataGrid.HeaderBackColor%2A>|行和列标题的背景色。|  
    |<xref:System.Windows.Forms.DataGrid.HeaderFont%2A>|用于列标题的字体。|  
    |<xref:System.Windows.Forms.DataGrid.HeaderForeColor%2A>|显示网格的列标题，包括列标题文本的加号 （+） 和减号 （-） 展开和折叠行，多个相关表时的标志符号的前景色。|  
    |<xref:System.Windows.Forms.DataGrid.LinkColor%2A>|在数据网格中，包括指向子表、 关系名称和等等的所有链接的文本的颜色。|  
    |<xref:System.Windows.Forms.DataGrid.ParentRowsBackColor%2A>|在子表中，这是父行的背景色。|  
    |<xref:System.Windows.Forms.DataGrid.ParentRowsForeColor%2A>|在子表中，这是父行的前景色。|  
    |<xref:System.Windows.Forms.DataGrid.ParentRowsLabelStyle%2A>|确定是否表和列名称显示在父行中，通过<xref:System.Windows.Forms.DataGridParentRowsLabelStyle>枚举。|  
    |<xref:System.Windows.Forms.DataGrid.PreferredColumnWidth%2A>|网格中列的默认宽度（以像素为单位）。 重置之前设置此属性<xref:System.Windows.Forms.DataGrid.DataSource%2A>和<xref:System.Windows.Forms.DataGrid.DataMember%2A>属性 (或者单独，或通过<xref:System.Windows.Forms.DataGrid.SetDataBinding%2A>方法)，或者该属性将产生任何效果。<br /><br /> 属性不能设置为小于 0 的值。|  
    |<xref:System.Windows.Forms.DataGrid.PreferredRowHeight%2A>|行的高度 （以像素为单位） 的网格中的行。 重置之前设置此属性<xref:System.Windows.Forms.DataGrid.DataSource%2A>和<xref:System.Windows.Forms.DataGrid.DataMember%2A>属性 (或者单独，或通过<xref:System.Windows.Forms.DataGrid.SetDataBinding%2A>方法)，或者该属性将产生任何效果。<br /><br /> 属性不能设置为小于 0 的值。|  
    |<xref:System.Windows.Forms.DataGrid.RowHeaderWidth%2A>|网格的行标题的宽度。|  
    |<xref:System.Windows.Forms.DataGrid.SelectionBackColor%2A>|选择行或单元格时，这是背景色。|  
    |<xref:System.Windows.Forms.DataGrid.SelectionForeColor%2A>|选择行或单元格时，这是的前景色。|  
  
    > [!NOTE]
    >  当您要自定义控件的颜色时，则可以使控件不佳的颜色选择 （例如，红色和绿色） 不可访问。 使用提供的颜色**系统颜色**调色板，若要避免此问题。  
  
     下面的过程需要<xref:System.Windows.Forms.DataGrid>控件绑定到数据表。 有关详细信息，请参阅[如何： 将 Windows 窗体 DataGrid 控件绑定到数据源](../../../../docs/framework/winforms/controls/how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)。  
  
### <a name="to-set-the-table-and-column-style-of-a-data-table-at-design-time"></a>若要在设计时设置的数据表的表和列样式  
  
1.  选择<xref:System.Windows.Forms.DataGrid>窗体上的控件。  
  
2.  在**属性**窗口中，选择<xref:System.Windows.Forms.DataGrid.TableStyles%2A>属性，然后单击**省略号**(![VisualStudioEllipsesButton 屏幕快照](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) 按钮。  
  
3.  在**DataGridTableStyle 集合编辑器**对话框中，单击**添加**若要将表样式添加到集合。  
  
     与**DataGridTableStyle 集合编辑器**，可以添加和删除表样式、 设置显示和布局属性和组的表样式名称映射。  
  
4.  设置<xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A>为每个表样式的映射名称的属性。  
  
     映射名称用于指定哪些表样式应使用哪种表。  
  
5.  在**DataGridTableStyle 集合编辑器**，选择<xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A>属性，然后单击省略号按钮 (![VisualStudioEllipsesButton 屏幕快照](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")).  
  
6.  在**DataGridColumnStyle 集合编辑器**对话框框中，将列样式添加到你创建的表样式。  
  
     与**DataGridColumnStyle 集合编辑器**、 可以添加和删除列样式，设置显示和布局属性，以及设置映射名称和格式设置字符串的数据列。  
  
    > [!NOTE]
    >  有关格式设置字符串的详细信息，请参阅[格式化类型](../../../../docs/standard/base-types/formatting-types.md)。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Forms.GridTableStylesCollection>  
 <xref:System.Windows.Forms.GridColumnStylesCollection>  
 <xref:System.Windows.Forms.DataGrid>  
 [如何：在 Windows 窗体 DataGrid 控件中删除或隐藏列](../../../../docs/framework/winforms/controls/how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)  
 [DataGrid 控件](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)
