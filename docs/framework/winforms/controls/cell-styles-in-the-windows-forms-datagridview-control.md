---
title: "Windows 窗体 DataGridView 控件中的单元格样式"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- DataGridView control [Windows Forms], cell styles
- cells [Windows Forms], styles
- data grids [Windows Forms], cell styles
ms.assetid: dbb75ed6-8804-4232-8382-f9920c2e380c
caps.latest.revision: "33"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 915aba380b6fe35299de94720f216cda5ab66721
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="cell-styles-in-the-windows-forms-datagridview-control"></a>Windows 窗体 DataGridView 控件中的单元格样式
中的每个单元格<xref:System.Windows.Forms.DataGridView>控件可以具有其自己的样式，例如文本格式、 背景色、 前景颜色和字体。 但是，通常情况下，多个单元格将具有特定样式特征。  
  
 用于共享样式的单元格的组可能包括在特定行或列、 包含特定值的所有单元格或所有单元格的所有单元格控件中。 因为这些组重叠，则每个单元格可能从多个位置中获取其样式信息。 例如，你可能需要在中的每个单元格<xref:System.Windows.Forms.DataGridView>控件使用带有负数的字体相同，但仅在要使用货币格式的货币列中的单元格和仅货币单元格，才能使用红色前景色。  
  
## <a name="the-datagridviewcellstyle-class"></a>DataGridViewCellStyle 类  
 <xref:System.Windows.Forms.DataGridViewCellStyle>类包含与视觉样式相关的以下属性：  
  
-   <xref:System.Windows.Forms.DataGridViewCellStyle.BackColor%2A> 和 <xref:System.Windows.Forms.DataGridViewCellStyle.ForeColor%2A>  
  
-   <xref:System.Windows.Forms.DataGridViewCellStyle.SelectionBackColor%2A> 和 <xref:System.Windows.Forms.DataGridViewCellStyle.SelectionForeColor%2A>  
  
-   <xref:System.Windows.Forms.DataGridViewCellStyle.Font%2A>  
  
 此类还包含与格式设置相关的以下属性：  
  
-   <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> 和 <xref:System.Windows.Forms.DataGridViewCellStyle.FormatProvider%2A>  
  
-   <xref:System.Windows.Forms.DataGridViewCellStyle.NullValue%2A> 和 <xref:System.Windows.Forms.DataGridViewCellStyle.DataSourceNullValue%2A>  
  
-   <xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A>  
  
-   <xref:System.Windows.Forms.DataGridViewCellStyle.Alignment%2A>  
  
-   <xref:System.Windows.Forms.DataGridViewCellStyle.Padding%2A>  
  
 有关这些属性和其他单元格样式属性的详细信息，请参阅<xref:System.Windows.Forms.DataGridViewCellStyle>下面的另请参阅部分中列出的参考文档和主题。  
  
## <a name="using-datagridviewcellstyle-objects"></a>使用 DataGridViewCellStyle 对象  
 你可以检索<xref:System.Windows.Forms.DataGridViewCellStyle>对象的各种属性从<xref:System.Windows.Forms.DataGridView>， <xref:System.Windows.Forms.DataGridViewColumn>， <xref:System.Windows.Forms.DataGridViewRow>，和<xref:System.Windows.Forms.DataGridViewCell>类和它们的派生的类。 如果其中一个属性尚未尚未设置，检索其值将创建一个新<xref:System.Windows.Forms.DataGridViewCellStyle>对象。 你还可以实例化自己<xref:System.Windows.Forms.DataGridViewCellStyle>对象，并将它们分配给这些属性。  
  
 你可以通过共享来避免不必要的样式信息的重复<xref:System.Windows.Forms.DataGridViewCellStyle>多个对象<xref:System.Windows.Forms.DataGridView>元素。 由于样式设置在控件、 列和行级别筛选器向下的通过每个级别向单元格级别，还可以通过在每个以上级别不同的级别设置仅这些样式属性来避免样式重复。 遵循样式继承一部分更详细地对此进行了描述。  
  
 下表列出的主属性用于获取或设置<xref:System.Windows.Forms.DataGridViewCellStyle>对象。  
  
|属性|类|描述|  
|--------------|-------------|-----------------|  
|`DefaultCellStyle`|<xref:System.Windows.Forms.DataGridView><xref:System.Windows.Forms.DataGridViewColumn>， <xref:System.Windows.Forms.DataGridViewRow>，和派生类|获取或设置使用的整个控件 （包括标题单元格），在列中，或在行中的所有单元格的默认样式。|  
|<xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A>|<xref:System.Windows.Forms.DataGridView>|获取或设置控件中的所有行都使用的默认单元格样式。 这不包括标题单元格。|  
|<xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A>|<xref:System.Windows.Forms.DataGridView>|获取或设置交替行控件中的使用的默认单元格样式。 用于创建类似帐目的效果。|  
|<xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A>|<xref:System.Windows.Forms.DataGridView>|获取或设置使用的控件的行标题的默认单元格样式。 如果启用了可视样式，替代当前主题。|  
|<xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A>|<xref:System.Windows.Forms.DataGridView>|获取或设置使用的控件的列标题的默认单元格样式。 如果启用了可视样式，替代当前主题。|  
|<xref:System.Windows.Forms.DataGridViewCell.Style%2A>|<xref:System.Windows.Forms.DataGridViewCell>和派生的类|获取或设置在单元格级别指定的样式。 这些样式会覆盖继承从较高级别。|  
|`InheritedStyle`|<xref:System.Windows.Forms.DataGridViewCell><xref:System.Windows.Forms.DataGridViewRow>， <xref:System.Windows.Forms.DataGridViewColumn>，和派生类|获取当前应用到单元格、 行或列，包括从较高级别继承的样式的所有样式。|  
  
 如上所述，自动获取样式属性的值的实例化一个新<xref:System.Windows.Forms.DataGridViewCellStyle>对象如果属性尚未以前设置。 若要避免不必要地创建这些对象，行和列类具有<xref:System.Windows.Forms.DataGridViewBand.HasDefaultCellStyle%2A>属性，可以检查以确定是否<xref:System.Windows.Forms.DataGridViewBand.DefaultCellStyle%2A>设置属性。 同样，单元格类具有<xref:System.Windows.Forms.DataGridViewCell.HasStyle%2A>属性，该值指示是否<xref:System.Windows.Forms.DataGridViewCell.Style%2A>设置属性。  
  
 每个样式属性都具有对应的*PropertyName* `Changed`上的事件<xref:System.Windows.Forms.DataGridView>控件。 有关行、 列和单元属性，该事件的名称开头"`Row`"，"`Column`"，或"`Cell`"(例如， <xref:System.Windows.Forms.DataGridView.RowDefaultCellStyleChanged>)。 每个事件发生时相应的样式属性设置为另一种<xref:System.Windows.Forms.DataGridViewCellStyle>对象。 当你检索时不会发生这些事件<xref:System.Windows.Forms.DataGridViewCellStyle>对象的样式属性和修改其属性值。 若要对更改作出响应的单元格样式对象本身，处理<xref:System.Windows.Forms.DataGridView.CellStyleContentChanged>事件。  
  
## <a name="style-inheritance"></a>样式继承  
 每个<xref:System.Windows.Forms.DataGridViewCell>获取从其外观其<xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A>属性。 <xref:System.Windows.Forms.DataGridViewCellStyle>此属性返回的对象类型的属性层次结构中继承其值<xref:System.Windows.Forms.DataGridViewCellStyle>。 这些属性列在下面中的顺序<xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A>为非标题单元格获取其值。  
  
1.  <xref:System.Windows.Forms.DataGridViewCell.Style%2A?displayProperty=nameWithType>  
  
2.  <xref:System.Windows.Forms.DataGridViewRow.DefaultCellStyle%2A?displayProperty=nameWithType>  
  
3.  <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A?displayProperty=nameWithType>（仅适用于具有奇数索引号的行中的单元格）  
  
4.  <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A?displayProperty=nameWithType>  
  
5.  <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A?displayProperty=nameWithType>  
  
6.  <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>  
  
 为行和列标题单元格<xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A>用从以下列表中所提供的顺序的源属性的值填充属性。  
  
1.  <xref:System.Windows.Forms.DataGridViewCell.Style%2A?displayProperty=nameWithType>  
  
2.  <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A?displayProperty=nameWithType> 或 <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A?displayProperty=nameWithType>  
  
3.  <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>  
  
 下图说明了此过程。  
  
 ![类型 DataGridViewCellStyle 的](../../../../docs/framework/winforms/controls/media/datagridviewcells1.gif "DataGridViewCells1")  
  
 你还可以访问继承的特定行和列样式。 列<xref:System.Windows.Forms.DataGridViewColumn.InheritedStyle%2A>属性继承其属性值从下列属性。  
  
1.  <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A?displayProperty=nameWithType>  
  
2.  <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>  
  
 行<xref:System.Windows.Forms.DataGridViewRow.InheritedStyle%2A>属性继承其属性值从下列属性。  
  
1.  <xref:System.Windows.Forms.DataGridViewRow.DefaultCellStyle%2A?displayProperty=nameWithType>  
  
2.  <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A?displayProperty=nameWithType>（仅适用于具有奇数索引号的行中的单元格）  
  
3.  <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A?displayProperty=nameWithType>  
  
4.  <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>  
  
 中每个属性<xref:System.Windows.Forms.DataGridViewCellStyle>返回对象`InheritedStyle`属性值获取从相应的列表具有对应的属性设置为值以外的第一个单元格样式属性，<xref:System.Windows.Forms.DataGridViewCellStyle>类默认值。  
  
 下表说明了如何<xref:System.Windows.Forms.DataGridViewCellStyle.ForeColor%2A>示例单元格的属性值继承自其包含的列。  
  
|类型的属性`DataGridViewCellStyle`|示例`ForeColor`检索到的对象的值|  
|----------------------------------------------|----------------------------------------------------|  
|<xref:System.Windows.Forms.DataGridViewCell.Style%2A?displayProperty=nameWithType>|<xref:System.Drawing.Color.Empty?displayProperty=nameWithType>|  
|<xref:System.Windows.Forms.DataGridViewRow.DefaultCellStyle%2A?displayProperty=nameWithType>|<xref:System.Drawing.Color.Red%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A?displayProperty=nameWithType>|<xref:System.Drawing.Color.Empty?displayProperty=nameWithType>|  
|<xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A?displayProperty=nameWithType>|<xref:System.Drawing.Color.Empty?displayProperty=nameWithType>|  
|<xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A?displayProperty=nameWithType>|<xref:System.Drawing.Color.DarkBlue%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>|<xref:System.Drawing.Color.Black%2A?displayProperty=nameWithType>|  
  
 在这种情况下，<xref:System.Drawing.Color.Red%2A?displayProperty=nameWithType>从单元格的行的值是列表上的第一个实际值。 该名称将成为<xref:System.Windows.Forms.DataGridViewCellStyle.ForeColor%2A>属性值的单元格的<xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A>。  
  
 下图说明了如何不同<xref:System.Windows.Forms.DataGridViewCellStyle>属性继承其属性值从不同的位置。  
  
 ![DataGridView 属性 &#45; 值继承](../../../../docs/framework/winforms/controls/media/datagridviewcells2.gif "DataGridViewCells2")  
  
 通过利用样式继承，可以为整个控件提供适当的样式，而无需在多个位置指定相同的信息。  
  
 尽管标题单元格参与样式继承，如所述，返回的对象<xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A>和<xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A>属性<xref:System.Windows.Forms.DataGridView>控件具有重写返回的对象的属性值的初始属性值<xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A>属性。 如果你想为返回的对象设置的属性<xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A>属性要应用于行和列标题，你必须设置返回的对象的相应属性<xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A>和<xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A>为默认值的属性指示有关<xref:System.Windows.Forms.DataGridViewCellStyle>类。  
  
> [!NOTE]
>  如果启用了可视样式，行和列标题 (除<xref:System.Windows.Forms.DataGridView.TopLeftHeaderCell%2A>) 样式将自动由当前的主题，重写任何两个属性中指定的样式。  
  
 <xref:System.Windows.Forms.DataGridViewButtonColumn>， <xref:System.Windows.Forms.DataGridViewImageColumn>，和<xref:System.Windows.Forms.DataGridViewCheckBoxColumn>类型还初始化的列返回的对象的某些值<xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A>属性。 有关详细信息，请参阅这些类型的参考文档。  
  
## <a name="setting-styles-dynamically"></a>动态设置样式  
 若要自定义的具有特定值的单元格的样式，实现的处理程序<xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType>事件。 此事件处理程序接收的自变量<xref:System.Windows.Forms.DataGridViewCellFormattingEventArgs>类型。 此对象包含使你能够确定其位置以及正在格式化的单元格的值的属性<xref:System.Windows.Forms.DataGridView>控件。 此对象还包含<xref:System.Windows.Forms.DataGridViewCellFormattingEventArgs.CellStyle%2A>初始化为的值的属性<xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A>正在格式化的单元格的属性。 你可以修改的单元格样式属性来指定相应的单元格的值和位置的样式信息。  
  
> [!NOTE]
>  <xref:System.Windows.Forms.DataGridView.RowPrePaint>和<xref:System.Windows.Forms.DataGridView.RowPostPaint>事件还会收到<xref:System.Windows.Forms.DataGridViewCellStyle>对象在事件数据，但在其大小写，它是行的副本<xref:System.Windows.Forms.DataGridViewRow.InheritedStyle%2A>属性为只读的目的，并对它的更改不会影响该控件。  
  
 你还可以动态修改以响应事件的各个单元格的样式如<xref:System.Windows.Forms.DataGridView.CellMouseEnter?displayProperty=nameWithType>和<xref:System.Windows.Forms.DataGridView.CellMouseLeave>事件。 例如，在处理程序<xref:System.Windows.Forms.DataGridView.CellMouseEnter>事件，无法存储单元格背景色的当前值 (通过该单元格的检索<xref:System.Windows.Forms.DataGridViewCell.Style%2A>属性)，然后将其设置为在鼠标悬停在其上时将突出显示该单元格的一种新颜色。 中的处理程序<xref:System.Windows.Forms.DataGridView.CellMouseLeave>事件，然后可以将背景色还原到原始值。  
  
> [!NOTE]
>  缓存存储在该单元格的值<xref:System.Windows.Forms.DataGridViewCell.Style%2A>属性是而不考虑是否设置了特定样式值非常重要。 如果您暂时替换样式设置，将其还原到"未设置"的原始状态可确保，则该单元格将返回到从较高级别继承的样式设置。 如果你需要确定无论是否继承样式的单元格有效的实际样式，使用该单元格的<xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A>属性。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridViewCellStyle>  
 <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewBand.InheritedStyle%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewRow.InheritedStyle%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewColumn.InheritedStyle%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewBand.DefaultCellStyle%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewCell.Style%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.CellStyleContentChanged?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.RowPrePaint?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.RowPostPaint?displayProperty=nameWithType>  
 [Windows 窗体 DataGridView 控件中的基本格式和样式设置](../../../../docs/framework/winforms/controls/basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)  
 [如何：设置 Windows 窗体 DataGridView 控件的默认单元格样式](../../../../docs/framework/winforms/controls/how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md)  
 [Windows 窗体 DataGridView 控件中的数据格式设置](../../../../docs/framework/winforms/controls/data-formatting-in-the-windows-forms-datagridview-control.md)
