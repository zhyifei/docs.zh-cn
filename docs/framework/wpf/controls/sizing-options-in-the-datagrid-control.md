---
title: DataGrid 控件中的调整大小选项
ms.date: 03/30/2017
helpviewer_keywords:
- DataGrid control [WPF], sizing
- size [WPF], DataGrid
- automatically size DataGrid [WPF]
ms.assetid: 96a0e47e-b010-4302-98ef-2daac446d8db
ms.openlocfilehash: 0019ac9ad82301506d2da279094b2c96e022e915
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="sizing-options-in-the-datagrid-control"></a>DataGrid 控件中的调整大小选项
很多选项可控制如何<xref:System.Windows.Controls.DataGrid>调整自身大小。 <xref:System.Windows.Controls.DataGrid>，以及单个行和列中的<xref:System.Windows.Controls.DataGrid>、 可以设置为其内容自动调整大小或可以将设置为特定值。 默认情况下，<xref:System.Windows.Controls.DataGrid>将增加和缩小以适应其内容的大小。  
  
## <a name="sizing-the-datagrid"></a>大小调整数据网格  
  
### <a name="cautions-when-using-automatic-sizing"></a>使用自动调整大小时的注意事项  
 默认情况下，<xref:System.Windows.FrameworkElement.Height%2A>和<xref:System.Windows.FrameworkElement.Width%2A>属性<xref:System.Windows.Controls.DataGrid>设置为<xref:System.Double.NaN?displayProperty=nameWithType>("`Auto`"在 XAML 中)，和<xref:System.Windows.Controls.DataGrid>会调整为其内容的大小调整。  
  
 当放置在一个容器，它不限制的大小及其子级，例如内部<xref:System.Windows.Controls.Canvas>或<xref:System.Windows.Controls.StackPanel>、<xref:System.Windows.Controls.DataGrid>将拉伸到容器的可见边界超过并且不会显示滚动条。 这种情况具有可用性和性能的影响。  
  
 如果当绑定到数据集，<xref:System.Windows.FrameworkElement.Height%2A>的<xref:System.Windows.Controls.DataGrid>是不受限制，它将继续添加绑定的数据集合中的每个数据项的行。 这可能会导致<xref:System.Windows.Controls.DataGrid>添加行时增长的应用程序可见的边界之外。 <xref:System.Windows.Controls.DataGrid>将不显示滚动条在这种情况下由于其<xref:System.Windows.FrameworkElement.Height%2A>将继续增大以容纳新行。  
  
 中的每一行创建一个对象<xref:System.Windows.Controls.DataGrid>。 如果你正在使用大型数据集，并且你允许<xref:System.Windows.Controls.DataGrid>以自动调整自身大小，创建大量对象可能会影响你的应用程序的性能。  
  
 若要避免这些问题，当您使用大型数据集时，建议您专门设置<xref:System.Windows.FrameworkElement.Height%2A>的<xref:System.Windows.Controls.DataGrid>或将其放置在一个容器，它将限制其<xref:System.Windows.FrameworkElement.Height%2A>，如<xref:System.Windows.Controls.Grid>。 时<xref:System.Windows.FrameworkElement.Height%2A>受到限制，<xref:System.Windows.Controls.DataGrid>只能创建适合其指定的行<xref:System.Windows.FrameworkElement.Height%2A>，并根据需要以显示新的数据将回收这些行。  
  
### <a name="setting-the-datagrid-size"></a>设置 DataGrid 大小  
 <xref:System.Windows.Controls.DataGrid>可以将设置为自动指定边界内的大小或<xref:System.Windows.Controls.DataGrid>可以设置为特定大小。 下表显示可以设置到控件的属性<xref:System.Windows.Controls.DataGrid>大小。  
  
|属性|描述|  
|--------------|-----------------|  
|<xref:System.Windows.FrameworkElement.Height%2A>|设置为特定高度<xref:System.Windows.Controls.DataGrid>。|  
|<xref:System.Windows.FrameworkElement.MaxHeight%2A>|设置上限的高度<xref:System.Windows.Controls.DataGrid>。 <xref:System.Windows.Controls.DataGrid>将垂直增长，直到其达到此高度。|  
|<xref:System.Windows.FrameworkElement.MinHeight%2A>|设置的高度下限<xref:System.Windows.Controls.DataGrid>。 <xref:System.Windows.Controls.DataGrid>将垂直收缩，直到其达到此高度。|  
|<xref:System.Windows.FrameworkElement.Width%2A>|设置特定宽度<xref:System.Windows.Controls.DataGrid>。|  
|<xref:System.Windows.FrameworkElement.MaxWidth%2A>|设置上限的宽度<xref:System.Windows.Controls.DataGrid>。 <xref:System.Windows.Controls.DataGrid>将水平增大，直到其达到此宽度。|  
|<xref:System.Windows.FrameworkElement.MinWidth%2A>|设置的宽度下限<xref:System.Windows.Controls.DataGrid>。 <xref:System.Windows.Controls.DataGrid>将水平收缩，直到其达到此宽度。|  
  
## <a name="sizing-rows-and-row-headers"></a>调整行和行标题  
  
### <a name="datagrid-rows"></a>DataGrid 行  
 默认情况下，<xref:System.Windows.Controls.DataGrid>行的<xref:System.Windows.FrameworkElement.Height%2A>属性设置为<xref:System.Double.NaN?displayProperty=nameWithType>("`Auto`"在 XAML 中)，并且行高度将扩展到其内容的大小。 中的所有行的高度<xref:System.Windows.Controls.DataGrid>可以通过将设置指定<xref:System.Windows.Controls.DataGrid.RowHeight%2A?displayProperty=nameWithType>属性。 用户可以通过拖动行标题分隔符更改行高度。  
  
### <a name="datagrid-row-headers"></a>DataGrid 行标题  
 若要显示行标题<xref:System.Windows.Controls.DataGrid.HeadersVisibility%2A>属性必须设置为<xref:System.Windows.Controls.DataGridHeadersVisibility.Row?displayProperty=nameWithType>或<xref:System.Windows.Controls.DataGridHeadersVisibility.All?displayProperty=nameWithType>。 默认情况下，显示行标题和它们自动调整大小以适应其内容。 行标题可以通过设置指定特定宽度<xref:System.Windows.Controls.DataGrid.RowHeaderWidth%2A?displayProperty=nameWithType>属性。  
  
## <a name="sizing-columns-and-column-headers"></a>大小调整列和列标题  
  
### <a name="datagrid-columns"></a>数据网格列  
 <xref:System.Windows.Controls.DataGrid>使用值<xref:System.Windows.Controls.DataGridLength>和<xref:System.Windows.Controls.DataGridLengthUnitType>结构，以指定绝对或自动调整大小模式。  
  
 下表显示由提供的值<xref:System.Windows.Controls.DataGridLengthUnitType>结构。  
  
|名称|描述|  
|----------|-----------------|  
|<xref:System.Windows.Controls.DataGridLengthUnitType.Auto>|默认自动调整大小模式大小<xref:System.Windows.Controls.DataGrid>列基于单元格和列标题的内容。|  
|<xref:System.Windows.Controls.DataGridLengthUnitType.SizeToCells>|基于单元格的自动调整大小模式大小<xref:System.Windows.Controls.DataGrid>列基于在列中，不包括列标题单元格的内容。|  
|<xref:System.Windows.Controls.DataGridLengthUnitType.SizeToHeader>|标头基于自动调整大小模式大小<xref:System.Windows.Controls.DataGrid>列基于列标头的内容。|  
|<xref:System.Windows.Controls.DataGridLengthUnitType.Pixel>|基于像素的大小调整模式大小<xref:System.Windows.Controls.DataGrid>列基于提供的数字值。|  
|<xref:System.Windows.Controls.DataGridLengthUnitType.Star>|星型大小调整模式用于根据加权比例分配可用空间。<br /><br /> 在 XAML 中，星号值表示为 n * 其中 n 表示的数字值。 1\*等效于\*。 例如，如果两个中的列<xref:System.Windows.Controls.DataGrid>的宽度为\*和第 2\*，第一列将接收的可用空间的一部分中，第二列会收到的可用空间的两个部分。|  
  
 <xref:System.Windows.Controls.DataGridLengthConverter>类可以用于将数字或字符串值之间的数据转换和<xref:System.Windows.Controls.DataGridLength>值。  
  
 默认情况下，<xref:System.Windows.Controls.DataGrid.ColumnWidth%2A?displayProperty=nameWithType>属性设置为<xref:System.Windows.Controls.DataGridLength.SizeToHeader%2A>，和<xref:System.Windows.Controls.DataGridColumn.Width%2A?displayProperty=nameWithType>属性设置为<xref:System.Windows.Controls.DataGridLength.Auto%2A>。 当大小调整模式设置为<xref:System.Windows.Controls.DataGridLength.Auto%2A>或<xref:System.Windows.Controls.DataGridLength.SizeToCells%2A>，列将增大到其广泛的可见内容的宽度。 当滚动时，这些大小调整模式将导致列展开如果内容大于当前的列大小滚动到视图。 内容滚动到视图后，不会缩小列。  
  
 中的列<xref:System.Windows.Controls.DataGrid>还可以设置为自动调整大小仅在指定边界内或列可以设置为特定大小。 下表显示可以用来控制列的大小的属性。  
  
|属性|描述|  
|--------------|-----------------|  
|<xref:System.Windows.Controls.DataGrid.MaxColumnWidth%2A?displayProperty=nameWithType>|设置中的所有列的上限<xref:System.Windows.Controls.DataGrid>。|  
|<xref:System.Windows.Controls.DataGridColumn.MaxWidth%2A?displayProperty=nameWithType>|设置为单个列的上限。 重写<xref:System.Windows.Controls.DataGrid.MaxColumnWidth%2A?displayProperty=nameWithType>。|  
|<xref:System.Windows.Controls.DataGrid.MinColumnWidth%2A?displayProperty=nameWithType>|设置中的所有列的下限<xref:System.Windows.Controls.DataGrid>。|  
|<xref:System.Windows.Controls.DataGridColumn.MinWidth%2A?displayProperty=nameWithType>|设置为单个列的下限。 重写<xref:System.Windows.Controls.DataGrid.MinColumnWidth%2A?displayProperty=nameWithType>。|  
|<xref:System.Windows.Controls.DataGrid.ColumnWidth%2A?displayProperty=nameWithType>|设置中的所有列的特定宽度<xref:System.Windows.Controls.DataGrid>。|  
|<xref:System.Windows.Controls.DataGridColumn.Width%2A?displayProperty=nameWithType>|设置特定宽度为单个列。 重写<xref:System.Windows.Controls.DataGrid.ColumnWidth%2A?displayProperty=nameWithType>。|  
  
### <a name="datagrid-column-headers"></a>DataGrid 列标题  
 默认情况下，<xref:System.Windows.Controls.DataGrid>显示列标题。 若要隐藏列标题，<xref:System.Windows.Controls.DataGrid.HeadersVisibility%2A>属性必须设置为<xref:System.Windows.Controls.DataGridHeadersVisibility.Row?displayProperty=nameWithType>或<xref:System.Windows.Controls.DataGridHeadersVisibility.None?displayProperty=nameWithType>。 默认情况下，当显示列标题时，自动调整大小以适应其内容。 列标题可以通过设置指定特定高度<xref:System.Windows.Controls.DataGrid.ColumnHeaderHeight%2A?displayProperty=nameWithType>属性。  
  
### <a name="resizing-with-the-mouse"></a>使用鼠标调整大小  
 用户可以调整大小<xref:System.Windows.Controls.DataGrid>行和列通过拖动行或列标题分隔符。 <xref:System.Windows.Controls.DataGrid>还支持自动调整大小的行和列通过双击行或列标题分隔符。 若要防止用户调整特定列的大小，将设置<xref:System.Windows.Controls.DataGridColumn.CanUserResize%2A?displayProperty=nameWithType>属性`false`各个列。 若要阻止用户调整所有列，设置<xref:System.Windows.Controls.DataGrid.CanUserResizeColumns%2A?displayProperty=nameWithType>属性`false`。 若要阻止用户调整所有行，将设置<xref:System.Windows.Controls.DataGrid.CanUserResizeRows%2A?displayProperty=nameWithType>属性`false`。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Controls.DataGrid>  
 <xref:System.Windows.Controls.DataGridColumn>  
 <xref:System.Windows.Controls.DataGridLength>  
 <xref:System.Windows.Controls.DataGridLengthConverter>
