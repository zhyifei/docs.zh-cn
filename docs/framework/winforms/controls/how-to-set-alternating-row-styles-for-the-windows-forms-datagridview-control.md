---
title: 如何：为 Windows 窗体 DataGridView 控件设置交替行样式
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], row styles
- data grids [Windows Forms], row styles
- rows [Windows Forms], data grids
ms.assetid: 699ef759-458c-426d-ac87-7c7e71b018ae
ms.openlocfilehash: 06b93a756b351213a87e1f52bc691aaa27558ac4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62013278"
---
# <a name="how-to-set-alternating-row-styles-for-the-windows-forms-datagridview-control"></a><span data-ttu-id="1221c-102">如何：为 Windows 窗体 DataGridView 控件设置交替行样式</span><span class="sxs-lookup"><span data-stu-id="1221c-102">How to: Set Alternating Row Styles for the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="1221c-103">表格数据通常以类似帐目的格式向用户显示，其中的交替行具有不同的背景色。</span><span class="sxs-lookup"><span data-stu-id="1221c-103">Tabular data is often presented to users in a ledger-like format where alternating rows have different background colors.</span></span> <span data-ttu-id="1221c-104">这种格式使用户可以更轻松地分辨每一行的单元格，尤其是有多列的宽表。</span><span class="sxs-lookup"><span data-stu-id="1221c-104">This format makes it easier for users to tell which cells are in each row, especially with wide tables that have many columns.</span></span>  
  
 <span data-ttu-id="1221c-105">借助 <xref:System.Windows.Forms.DataGridView> 控件，可为交替行指定完整的样式信息。</span><span class="sxs-lookup"><span data-stu-id="1221c-105">With the <xref:System.Windows.Forms.DataGridView> control, you can specify complete style information for alternating rows.</span></span> <span data-ttu-id="1221c-106">这使你可以使用背景色以及样式特性（如前景色和字体）区分交替行。</span><span class="sxs-lookup"><span data-stu-id="1221c-106">This enables you use style characteristics like foreground color and font, in addition to background color, to differentiate alternating rows.</span></span>  
  
 <span data-ttu-id="1221c-107">Visual Studio 中对此任务提供支持。</span><span class="sxs-lookup"><span data-stu-id="1221c-107">There is support for this task in Visual Studio.</span></span>  <span data-ttu-id="1221c-108">另请参阅[如何：设置 Windows 窗体 DataGridView 控件使用设计器的交替行样式](set-alternating-row-styles-for-the-datagrid-using-the-designer.md)。</span><span class="sxs-lookup"><span data-stu-id="1221c-108">Also see [How to: Set Alternating Row Styles for the Windows Forms DataGridView Control Using the Designer](set-alternating-row-styles-for-the-datagrid-using-the-designer.md).</span></span>  
  
### <a name="to-set-alternating-row-styles-programmatically"></a><span data-ttu-id="1221c-109">若要以编程方式设置交替行样式</span><span class="sxs-lookup"><span data-stu-id="1221c-109">To set alternating row styles programmatically</span></span>  
  
- <span data-ttu-id="1221c-110">设置 <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A> 返回的 <xref:System.Windows.Forms.DataGridViewCellStyle> 对象的属性以及 <xref:System.Windows.Forms.DataGridView> 的 <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="1221c-110">Set the properties of the <xref:System.Windows.Forms.DataGridViewCellStyle> objects returned by the <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A> and <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A> properties of the <xref:System.Windows.Forms.DataGridView>.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#068](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#068)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#068](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#068)]  
  
    > [!NOTE]
    >  <span data-ttu-id="1221c-111">使用 <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A> 和 <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A> 属性指定的样式会重写列上以 <xref:System.Windows.Forms.DataGridView> 级别指定的样式，但被单独的行和单元格级别上设置的样式重写。</span><span class="sxs-lookup"><span data-stu-id="1221c-111">The styles specified using the <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A> and <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A> properties override the styles specified on the column and <xref:System.Windows.Forms.DataGridView> level, but are overridden by the styles set on the individual row and cell level.</span></span> <span data-ttu-id="1221c-112">有关详细信息，请参阅[Windows 窗体 DataGridView 控件中的单元格样式](cell-styles-in-the-windows-forms-datagridview-control.md)。</span><span class="sxs-lookup"><span data-stu-id="1221c-112">For more information, see [Cell Styles in the Windows Forms DataGridView Control](cell-styles-in-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="1221c-113">编译代码</span><span class="sxs-lookup"><span data-stu-id="1221c-113">Compiling the Code</span></span>  
 <span data-ttu-id="1221c-114">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="1221c-114">This example requires:</span></span>  
  
- <span data-ttu-id="1221c-115">名为 `dataGridView1` 的 <xref:System.Windows.Forms.DataGridView> 控件。</span><span class="sxs-lookup"><span data-stu-id="1221c-115">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
- <span data-ttu-id="1221c-116">对 <xref:System?displayProperty=nameWithType><xref:System.Drawing?displayProperty=nameWithType> 和 <xref:System.Windows.Forms?displayProperty=nameWithType> 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="1221c-116">References to the <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType>, and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="1221c-117">可靠编程</span><span class="sxs-lookup"><span data-stu-id="1221c-117">Robust Programming</span></span>  
 <span data-ttu-id="1221c-118">为实现最大的可伸缩性，应在使用相同样式的多个行、列或单元格间共享 <xref:System.Windows.Forms.DataGridViewCellStyle> 对象，而不是分别设置单个元素的样式属性。</span><span class="sxs-lookup"><span data-stu-id="1221c-118">For maximum scalability, you should share <xref:System.Windows.Forms.DataGridViewCellStyle> objects across multiple rows, columns, or cells that use the same styles, rather than setting the style properties for each element separately.</span></span> <span data-ttu-id="1221c-119">有关详细信息，请参阅[缩放 Windows 窗体 DataGridView 控件的最佳做法](best-practices-for-scaling-the-windows-forms-datagridview-control.md)。</span><span class="sxs-lookup"><span data-stu-id="1221c-119">For more information, see [Best Practices for Scaling the Windows Forms DataGridView Control](best-practices-for-scaling-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1221c-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="1221c-120">See also</span></span>

- <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewCellStyle>
- [<span data-ttu-id="1221c-121">Windows 窗体 DataGridView 控件中的基本格式和样式设置</span><span class="sxs-lookup"><span data-stu-id="1221c-121">Basic Formatting and Styling in the Windows Forms DataGridView Control</span></span>](basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="1221c-122">Windows 窗体 DataGridView 控件中的单元格样式</span><span class="sxs-lookup"><span data-stu-id="1221c-122">Cell Styles in the Windows Forms DataGridView Control</span></span>](cell-styles-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="1221c-123">有关缩放 Windows 窗体 DataGridView 控件的最佳做法</span><span class="sxs-lookup"><span data-stu-id="1221c-123">Best Practices for Scaling the Windows Forms DataGridView Control</span></span>](best-practices-for-scaling-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="1221c-124">如何：在 Windows 窗体 DataGridView 控件中设置字体和颜色样式</span><span class="sxs-lookup"><span data-stu-id="1221c-124">How to: Set Font and Color Styles in the Windows Forms DataGridView Control</span></span>](how-to-set-font-and-color-styles-in-the-windows-forms-datagridview-control.md)
