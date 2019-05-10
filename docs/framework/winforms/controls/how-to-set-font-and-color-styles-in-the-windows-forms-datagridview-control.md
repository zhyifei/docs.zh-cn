---
title: 如何：设置 Windows 窗体 DataGridView 控件中的字体和颜色样式
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], cell customization
- data grids [Windows Forms], customizing cells
- data grids [Windows Forms], font styles
- data grids [Windows Forms], color styles
ms.assetid: 588f2c57-d963-41b1-9c1d-d02d71818113
ms.openlocfilehash: ad2426ed9643fd46927c4f8b6373fedbec372d38
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64638095"
---
# <a name="how-to-set-font-and-color-styles-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="e746b-102">如何：设置 Windows 窗体 DataGridView 控件中的字体和颜色样式</span><span class="sxs-lookup"><span data-stu-id="e746b-102">How to: Set Font and Color Styles in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="e746b-103">可以通过设置 <xref:System.Windows.Forms.DataGridViewCellStyle> 类的属性，指定 <xref:System.Windows.Forms.DataGridView> 控件内单元格的可视外观。</span><span class="sxs-lookup"><span data-stu-id="e746b-103">You can specify the visual appearance of cells within a <xref:System.Windows.Forms.DataGridView> control by setting properties of the <xref:System.Windows.Forms.DataGridViewCellStyle> class.</span></span> <span data-ttu-id="e746b-104">可以从 <xref:System.Windows.Forms.DataGridView> 类及其伴生类的各个属性检索此类的实例，或可实例化 <xref:System.Windows.Forms.DataGridViewCellStyle> 对象以分配到这些属性。</span><span class="sxs-lookup"><span data-stu-id="e746b-104">You can retrieve instances of this class from various properties of the <xref:System.Windows.Forms.DataGridView> class and its companion classes, or you can instantiate <xref:System.Windows.Forms.DataGridViewCellStyle> objects for assignment to these properties.</span></span>  
  
 <span data-ttu-id="e746b-105">以下步骤演示使用 <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A> 属性进行单元格外观的基本自定义。</span><span class="sxs-lookup"><span data-stu-id="e746b-105">The following procedures demonstrate basic customization of cell appearance using the <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A> property.</span></span> <span data-ttu-id="e746b-106">控件中每个单元格将继承通过此属性指定的样式，除非它们在列、行或单元格级别中重写。</span><span class="sxs-lookup"><span data-stu-id="e746b-106">Every cell in the control inherits the styles specified through this property unless they are overridden at the column, row, or cell level.</span></span> <span data-ttu-id="e746b-107">有关样式继承的示例，请参阅[如何：设置 Windows 窗体 DataGridView 控件的默认单元格样式](how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md)。</span><span class="sxs-lookup"><span data-stu-id="e746b-107">For an example of style inheritance, see [How to: Set Default Cell Styles for the Windows Forms DataGridView Control](how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md).</span></span> <span data-ttu-id="e746b-108">有关的 <xref:System.Windows.Forms.DataGridViewCellStyle> 类更多用法的信息，请参阅“另请参阅”部分中列出的主题。</span><span class="sxs-lookup"><span data-stu-id="e746b-108">For information about additional uses of the <xref:System.Windows.Forms.DataGridViewCellStyle> class, see the topics listed in the See Also section.</span></span>  
  
 <span data-ttu-id="e746b-109">Visual Studio 中对此任务提供广泛支持。</span><span class="sxs-lookup"><span data-stu-id="e746b-109">There is extensive support for this task in Visual Studio.</span></span>  <span data-ttu-id="e746b-110">另请参阅[如何：设置 Windows 窗体 DataGridView 控件使用设计器的默认单元格样式和数据格式](default-cell-styles-datagridview.md)。</span><span class="sxs-lookup"><span data-stu-id="e746b-110">Also see [How to: Set Default Cell Styles and Data Formats for the Windows Forms DataGridView Control Using the Designer](default-cell-styles-datagridview.md).</span></span>  
  
### <a name="to-specify-the-font-used-by-datagridview-cells"></a><span data-ttu-id="e746b-111">若要指定 DataGridView 单元格所使用的字体</span><span class="sxs-lookup"><span data-stu-id="e746b-111">To specify the font used by DataGridView cells</span></span>  
  
- <span data-ttu-id="e746b-112">设置 <xref:System.Windows.Forms.DataGridViewCellStyle> 的 <xref:System.Windows.Forms.DataGridViewCellStyle.Font%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="e746b-112">Set the <xref:System.Windows.Forms.DataGridViewCellStyle.Font%2A> property of a <xref:System.Windows.Forms.DataGridViewCellStyle>.</span></span> <span data-ttu-id="e746b-113">以下代码示例使用 <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType> 属性设置整个控件的字体。</span><span class="sxs-lookup"><span data-stu-id="e746b-113">The following code example uses the <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType> property to set the font for the entire control.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#101](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#101)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#101](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#101)]  
  
### <a name="to-specify-the-foreground-and-background-colors-of-datagridview-cells"></a><span data-ttu-id="e746b-114">若要指定 DataGridView 单元格的前景色和背景色</span><span class="sxs-lookup"><span data-stu-id="e746b-114">To specify the foreground and background colors of DataGridView cells</span></span>  
  
- <span data-ttu-id="e746b-115">设置 <xref:System.Windows.Forms.DataGridViewCellStyle> 的 <xref:System.Windows.Forms.DataGridViewCellStyle.ForeColor%2A> 和 <xref:System.Windows.Forms.DataGridViewCellStyle.BackColor%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="e746b-115">Set the <xref:System.Windows.Forms.DataGridViewCellStyle.ForeColor%2A> and <xref:System.Windows.Forms.DataGridViewCellStyle.BackColor%2A> properties of a <xref:System.Windows.Forms.DataGridViewCellStyle>.</span></span> <span data-ttu-id="e746b-116">以下代码示例使用 <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType> 属性为整个控件设置此类样式。</span><span class="sxs-lookup"><span data-stu-id="e746b-116">The following code example uses the <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType> property to set these styles for the entire control.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#102](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#102)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#102](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#102)]  
  
### <a name="to-specify-the-foreground-and-background-colors-of-selected-datagridview-cells"></a><span data-ttu-id="e746b-117">若要指定选定 DataGridView 单元格的前景色和背景色</span><span class="sxs-lookup"><span data-stu-id="e746b-117">To specify the foreground and background colors of selected DataGridView cells</span></span>  
  
- <span data-ttu-id="e746b-118">设置 <xref:System.Windows.Forms.DataGridViewCellStyle> 的 <xref:System.Windows.Forms.DataGridViewCellStyle.SelectionForeColor%2A> 和 <xref:System.Windows.Forms.DataGridViewCellStyle.SelectionBackColor%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="e746b-118">Set the <xref:System.Windows.Forms.DataGridViewCellStyle.SelectionForeColor%2A> and <xref:System.Windows.Forms.DataGridViewCellStyle.SelectionBackColor%2A> properties of a <xref:System.Windows.Forms.DataGridViewCellStyle>.</span></span> <span data-ttu-id="e746b-119">以下代码示例使用 <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType> 属性为整个控件设置此类样式。</span><span class="sxs-lookup"><span data-stu-id="e746b-119">The following code example uses the <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType> property to set these styles for the entire control.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#103](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#103)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#103](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#103)]  
  
## <a name="example"></a><span data-ttu-id="e746b-120">示例</span><span class="sxs-lookup"><span data-stu-id="e746b-120">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#100](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#100)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#100](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#100)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="e746b-121">编译代码</span><span class="sxs-lookup"><span data-stu-id="e746b-121">Compiling the Code</span></span>  
 <span data-ttu-id="e746b-122">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="e746b-122">This example requires:</span></span>  
  
- <span data-ttu-id="e746b-123">名为 `dataGridView1` 的 <xref:System.Windows.Forms.DataGridView> 控件。</span><span class="sxs-lookup"><span data-stu-id="e746b-123">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
- <span data-ttu-id="e746b-124">对 <xref:System?displayProperty=nameWithType><xref:System.Drawing?displayProperty=nameWithType> 和 <xref:System.Windows.Forms?displayProperty=nameWithType> 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="e746b-124">References to the <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType>, and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="e746b-125">可靠编程</span><span class="sxs-lookup"><span data-stu-id="e746b-125">Robust Programming</span></span>  
 <span data-ttu-id="e746b-126">为实现最大的可伸缩性，应在使用相同样式的多个行、列或单元格间共享 <xref:System.Windows.Forms.DataGridViewCellStyle> 对象，而不是分别设置单个元素的样式属性。</span><span class="sxs-lookup"><span data-stu-id="e746b-126">For maximum scalability, you should share <xref:System.Windows.Forms.DataGridViewCellStyle> objects across multiple rows, columns, or cells that use the same styles, rather than setting the style properties for each element separately.</span></span> <span data-ttu-id="e746b-127">有关详细信息，请参阅[缩放 Windows 窗体 DataGridView 控件的最佳做法](best-practices-for-scaling-the-windows-forms-datagridview-control.md)。</span><span class="sxs-lookup"><span data-stu-id="e746b-127">For more information, see [Best Practices for Scaling the Windows Forms DataGridView Control](best-practices-for-scaling-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e746b-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="e746b-128">See also</span></span>

- <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewCellStyle>
- [<span data-ttu-id="e746b-129">Windows 窗体 DataGridView 控件中的基本格式和样式设置</span><span class="sxs-lookup"><span data-stu-id="e746b-129">Basic Formatting and Styling in the Windows Forms DataGridView Control</span></span>](basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="e746b-130">Windows 窗体 DataGridView 控件中的单元格样式</span><span class="sxs-lookup"><span data-stu-id="e746b-130">Cell Styles in the Windows Forms DataGridView Control</span></span>](cell-styles-in-the-windows-forms-datagridview-control.md)
