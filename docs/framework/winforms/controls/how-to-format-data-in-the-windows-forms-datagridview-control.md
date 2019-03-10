---
title: 如何：Windows 中的数据格式窗体 DataGridView 控件
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], formatting data
- data [Windows Forms], formatting in DataGridView control
- data grids [Windows Forms], enabling wordwrap
- currency values [Windows Forms], formatting in data grids
- data grids [Windows Forms], currency values
- data grids [Windows Forms], formatting data
- data grids [Windows Forms], text alignment
- data grids [Windows Forms], date values
- cells [Windows Forms], text alignment
ms.assetid: 8c33543c-9c08-4636-a65a-fdf714a529b7
ms.openlocfilehash: 0699aec73c0a48efe88fc2901ef11c70d6f639d7
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/09/2019
ms.locfileid: "57721276"
---
# <a name="how-to-format-data-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="49698-102">如何：Windows 中的数据格式窗体 DataGridView 控件</span><span class="sxs-lookup"><span data-stu-id="49698-102">How to: Format Data in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="49698-103">下面的过程介绍使用的单元值的基本格式设置<xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A>属性的<xref:System.Windows.Forms.DataGridView>控件和控件中的特定列。</span><span class="sxs-lookup"><span data-stu-id="49698-103">The following procedures demonstrate basic formatting of cell values using the <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A> property of a <xref:System.Windows.Forms.DataGridView> control and of specific columns in a control.</span></span> <span data-ttu-id="49698-104">有关高级的数据格式设置信息，请参阅[如何：自定义 Windows 窗体 DataGridView 控件中的数据格式设置](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)。</span><span class="sxs-lookup"><span data-stu-id="49698-104">For information about advanced data formatting, see [How to: Customize Data Formatting in the Windows Forms DataGridView Control](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md).</span></span>  
  
### <a name="to-format-currency-and-date-values"></a><span data-ttu-id="49698-105">若要设置货币格式和日期值</span><span class="sxs-lookup"><span data-stu-id="49698-105">To format currency and date values</span></span>  
  
-   <span data-ttu-id="49698-106">设置 <xref:System.Windows.Forms.DataGridViewCellStyle> 的 <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="49698-106">Set the <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> property of a <xref:System.Windows.Forms.DataGridViewCellStyle>.</span></span> <span data-ttu-id="49698-107">下面的代码示例将使用的特定列的格式设置<xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A>列的属性。</span><span class="sxs-lookup"><span data-stu-id="49698-107">The following code example sets the format for specific columns using the <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A> property of the columns.</span></span> <span data-ttu-id="49698-108">中的值以`UnitPrice`列出现在当前的特定于区域性的货币格式，并将负值括在括号。</span><span class="sxs-lookup"><span data-stu-id="49698-108">Values in the `UnitPrice` column appear in the current culture-specific currency format, with negative values surrounded by parentheses.</span></span> <span data-ttu-id="49698-109">中的值以`ShipDate`列出现在当前的特定于区域性的短日期格式。</span><span class="sxs-lookup"><span data-stu-id="49698-109">Values in the `ShipDate` column appear in the current culture-specific short date format.</span></span> <span data-ttu-id="49698-110">有关详细信息<xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A>值，请参阅[格式设置类型](../../../standard/base-types/formatting-types.md)。</span><span class="sxs-lookup"><span data-stu-id="49698-110">For more information about <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> values, see [Formatting Types](../../../standard/base-types/formatting-types.md).</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#071](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#071)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#071](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#071)]  
  
### <a name="to-customize-the-display-of-null-database-values"></a><span data-ttu-id="49698-111">若要自定义显示内容的空数据库值</span><span class="sxs-lookup"><span data-stu-id="49698-111">To customize the display of null database values</span></span>  
  
-   <span data-ttu-id="49698-112">设置 <xref:System.Windows.Forms.DataGridViewCellStyle> 的 <xref:System.Windows.Forms.DataGridViewCellStyle.NullValue%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="49698-112">Set the <xref:System.Windows.Forms.DataGridViewCellStyle.NullValue%2A> property of a <xref:System.Windows.Forms.DataGridViewCellStyle>.</span></span> <span data-ttu-id="49698-113">下面的代码示例使用<xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>属性中包含值等于属性值的所有单元格显示"没有条目" <xref:System.DBNull.Value?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="49698-113">The following code example uses the <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType> property to display "no entry" in all cells containing values equal to <xref:System.DBNull.Value?displayProperty=nameWithType>.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#073](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#073)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#073](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#073)]  
  
### <a name="to-enable-wordwrap-in-text-based-cells"></a><span data-ttu-id="49698-114">若要启用基于文本的单元格中的换行</span><span class="sxs-lookup"><span data-stu-id="49698-114">To enable wordwrap in text-based cells</span></span>  
  
-   <span data-ttu-id="49698-115">设置<xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A>的属性<xref:System.Windows.Forms.DataGridViewCellStyle>之一<xref:System.Windows.Forms.DataGridViewTriState>枚举值。</span><span class="sxs-lookup"><span data-stu-id="49698-115">Set the <xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A> property of a <xref:System.Windows.Forms.DataGridViewCellStyle> to one of the <xref:System.Windows.Forms.DataGridViewTriState> enumeration values.</span></span> <span data-ttu-id="49698-116">下面的代码示例使用<xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>属性来设置整个控件的自动换行模式。</span><span class="sxs-lookup"><span data-stu-id="49698-116">The following code example uses the <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType> property to set the wrap mode for the entire control.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#074](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#074)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#074](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#074)]  
  
### <a name="to-specify-the-text-alignment-of-datagridview-cells"></a><span data-ttu-id="49698-117">若要指定 DataGridView 单元格的文本对齐方式</span><span class="sxs-lookup"><span data-stu-id="49698-117">To specify the text alignment of DataGridView cells</span></span>  
  
-   <span data-ttu-id="49698-118">设置<xref:System.Windows.Forms.DataGridViewCellStyle.Alignment%2A>的属性<xref:System.Windows.Forms.DataGridViewCellStyle>之一<xref:System.Windows.Forms.DataGridViewContentAlignment>枚举值。</span><span class="sxs-lookup"><span data-stu-id="49698-118">Set the <xref:System.Windows.Forms.DataGridViewCellStyle.Alignment%2A> property of a <xref:System.Windows.Forms.DataGridViewCellStyle> to one of the <xref:System.Windows.Forms.DataGridViewContentAlignment> enumeration values.</span></span> <span data-ttu-id="49698-119">下面的代码示例设置特定列使用的对齐方式<xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A>的列的属性。</span><span class="sxs-lookup"><span data-stu-id="49698-119">The following code example sets the alignment for a specific column using the <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A> property of the column.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#072](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#072)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#072](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#072)]  
  
## <a name="example"></a><span data-ttu-id="49698-120">示例</span><span class="sxs-lookup"><span data-stu-id="49698-120">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#070](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#070)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#070](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#070)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="49698-121">编译代码</span><span class="sxs-lookup"><span data-stu-id="49698-121">Compiling the Code</span></span>  
 <span data-ttu-id="49698-122">这些示例需要：</span><span class="sxs-lookup"><span data-stu-id="49698-122">These examples require:</span></span>  
  
-   <span data-ttu-id="49698-123">一个<xref:System.Windows.Forms.DataGridView>名为控件`dataGridView1`，其中包含名为的列`UnitPrice`，名为的列`ShipDate`，和一个名为列`CustomerName`。</span><span class="sxs-lookup"><span data-stu-id="49698-123">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1` that contains a column named `UnitPrice`, a column named `ShipDate`, and a column named `CustomerName`.</span></span>  
  
-   <span data-ttu-id="49698-124">对 <xref:System?displayProperty=nameWithType><xref:System.Drawing?displayProperty=nameWithType> 和 <xref:System.Windows.Forms?displayProperty=nameWithType> 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="49698-124">References to the <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType>, and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="49698-125">可靠编程</span><span class="sxs-lookup"><span data-stu-id="49698-125">Robust Programming</span></span>  
 <span data-ttu-id="49698-126">为了最大可伸缩性，应共享<xref:System.Windows.Forms.DataGridViewCellStyle>跨多个行、 列或使用相同的样式，而不是分别设置每个元素的样式属性的单元格的对象。</span><span class="sxs-lookup"><span data-stu-id="49698-126">For maximum scalability, you should share <xref:System.Windows.Forms.DataGridViewCellStyle> objects across multiple rows, columns, or cells that use the same styles rather than setting the style properties for each element separately.</span></span> <span data-ttu-id="49698-127">有关详细信息，请参阅[缩放 Windows 窗体 DataGridView 控件的最佳做法](best-practices-for-scaling-the-windows-forms-datagridview-control.md)。</span><span class="sxs-lookup"><span data-stu-id="49698-127">For more information, see [Best Practices for Scaling the Windows Forms DataGridView Control](best-practices-for-scaling-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49698-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="49698-128">See also</span></span>
- <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewBand.DefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewCellStyle>
- [<span data-ttu-id="49698-129">Windows 窗体 DataGridView 控件中的基本格式和样式设置</span><span class="sxs-lookup"><span data-stu-id="49698-129">Basic Formatting and Styling in the Windows Forms DataGridView Control</span></span>](basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="49698-130">Windows 窗体 DataGridView 控件中的单元格样式</span><span class="sxs-lookup"><span data-stu-id="49698-130">Cell Styles in the Windows Forms DataGridView Control</span></span>](cell-styles-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="49698-131">Windows 窗体 DataGridView 控件中的数据格式设置</span><span class="sxs-lookup"><span data-stu-id="49698-131">Data Formatting in the Windows Forms DataGridView Control</span></span>](data-formatting-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="49698-132">如何：自定义 Windows 窗体 DataGridView 控件中的数据格式设置</span><span class="sxs-lookup"><span data-stu-id="49698-132">How to: Customize Data Formatting in the Windows Forms DataGridView Control</span></span>](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="49698-133">格式设置类型</span><span class="sxs-lookup"><span data-stu-id="49698-133">Formatting Types</span></span>](../../../standard/base-types/formatting-types.md)
