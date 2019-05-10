---
title: 如何：设置 Windows 窗体 DataGridView 控件的默认单元格样式
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], cell styles
- cells [Windows Forms], styles
- data grids [Windows Forms], cell styles
ms.assetid: 1aaaca43-5340-447e-99c0-9177d9776aa1
ms.openlocfilehash: de939051b613a0622f60178a566fd19dbca53694
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64638166"
---
# <a name="how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control"></a><span data-ttu-id="e73dd-102">如何：设置 Windows 窗体 DataGridView 控件的默认单元格样式</span><span class="sxs-lookup"><span data-stu-id="e73dd-102">How to: Set Default Cell Styles for the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="e73dd-103">借助 <xref:System.Windows.Forms.DataGridView> 控件，可以指定整个控件以及特定列和行的默认单元格样式。</span><span class="sxs-lookup"><span data-stu-id="e73dd-103">With the <xref:System.Windows.Forms.DataGridView> control, you can specify default cell styles for the entire control and for specific columns and rows.</span></span> <span data-ttu-id="e73dd-104">这些默认设置依次向下筛选：从控件级别到列级别，然后到行级别，再到单元格级别。</span><span class="sxs-lookup"><span data-stu-id="e73dd-104">These defaults filter down from the control level to the column level, then to the row level, then to the cell level.</span></span> <span data-ttu-id="e73dd-105">如果未在单元格级别设置特定 <xref:System.Windows.Forms.DataGridViewCellStyle> 属性，则使用行级别的默认属性设置。</span><span class="sxs-lookup"><span data-stu-id="e73dd-105">If a particular <xref:System.Windows.Forms.DataGridViewCellStyle> property is not set at the cell level, the default property setting at the row level is used.</span></span> <span data-ttu-id="e73dd-106">如果在行级别也未设置该属性，则使用默认列设置。</span><span class="sxs-lookup"><span data-stu-id="e73dd-106">If the property is also not set at the row level, the default column setting is used.</span></span> <span data-ttu-id="e73dd-107">最后，如果在列级别也未设置该属性，那么则使用默认的 <xref:System.Windows.Forms.DataGridView> 设置。</span><span class="sxs-lookup"><span data-stu-id="e73dd-107">Finally, if the property is also not set at the column level, the default <xref:System.Windows.Forms.DataGridView> setting is used.</span></span> <span data-ttu-id="e73dd-108">借助此设置，可以避免必须重复多个级别的属性设置。</span><span class="sxs-lookup"><span data-stu-id="e73dd-108">With this setting, you can avoid having to duplicate the property settings at multiple levels.</span></span> <span data-ttu-id="e73dd-109">在每个级别，只需指定与其上级别不同的样式。</span><span class="sxs-lookup"><span data-stu-id="e73dd-109">At each level, simply specify the styles that differ from the levels above it.</span></span> <span data-ttu-id="e73dd-110">有关详细信息，请参阅[Windows 窗体 DataGridView 控件中的单元格样式](cell-styles-in-the-windows-forms-datagridview-control.md)。</span><span class="sxs-lookup"><span data-stu-id="e73dd-110">For more information, see [Cell Styles in the Windows Forms DataGridView Control](cell-styles-in-the-windows-forms-datagridview-control.md).</span></span>  
  
 <span data-ttu-id="e73dd-111">Visual Studio 中对此任务提供广泛支持。</span><span class="sxs-lookup"><span data-stu-id="e73dd-111">There is extensive support for this task in Visual Studio.</span></span>  <span data-ttu-id="e73dd-112">另请参阅[如何：设置 Windows 窗体 DataGridView 控件使用设计器的默认单元格样式和数据格式](default-cell-styles-datagridview.md)。</span><span class="sxs-lookup"><span data-stu-id="e73dd-112">Also see [How to: Set Default Cell Styles and Data Formats for the Windows Forms DataGridView Control Using the Designer](default-cell-styles-datagridview.md).</span></span>  
  
### <a name="to-set-the-default-cell-styles-programmatically"></a><span data-ttu-id="e73dd-113">以编程方式设置默认单元格样式</span><span class="sxs-lookup"><span data-stu-id="e73dd-113">To set the default cell styles programmatically</span></span>  
  
1. <span data-ttu-id="e73dd-114">设置通过 <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType> 属性检索的 <xref:System.Windows.Forms.DataGridViewCellStyle> 的属性。</span><span class="sxs-lookup"><span data-stu-id="e73dd-114">Set the properties of the <xref:System.Windows.Forms.DataGridViewCellStyle> retrieved through the <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType> property.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#141](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#141)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#141](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#141)]  
  
2. <span data-ttu-id="e73dd-115">创建和初始化供多个行和列使用的新 <xref:System.Windows.Forms.DataGridViewCellStyle> 对象。</span><span class="sxs-lookup"><span data-stu-id="e73dd-115">Create and initialize new <xref:System.Windows.Forms.DataGridViewCellStyle> objects for use by multiple rows and columns.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#142](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#142)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#142](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#142)]  
  
3. <span data-ttu-id="e73dd-116">设置特定行和列的 `DefaultCellStyle` 属性。</span><span class="sxs-lookup"><span data-stu-id="e73dd-116">Set the `DefaultCellStyle` property of specific rows and columns.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#143](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#143)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#143](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#143)]  
  
## <a name="example"></a><span data-ttu-id="e73dd-117">示例</span><span class="sxs-lookup"><span data-stu-id="e73dd-117">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#140](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#140)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#140](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#140)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="e73dd-118">编译代码</span><span class="sxs-lookup"><span data-stu-id="e73dd-118">Compiling the Code</span></span>  
 <span data-ttu-id="e73dd-119">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="e73dd-119">This example requires:</span></span>  
  
- <span data-ttu-id="e73dd-120">名为 `dataGridView1` 的 <xref:System.Windows.Forms.DataGridView> 控件。</span><span class="sxs-lookup"><span data-stu-id="e73dd-120">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
- <span data-ttu-id="e73dd-121">对 <xref:System?displayProperty=nameWithType><xref:System.Drawing?displayProperty=nameWithType> 和 <xref:System.Windows.Forms?displayProperty=nameWithType> 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="e73dd-121">References to the <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType>, and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="e73dd-122">可靠编程</span><span class="sxs-lookup"><span data-stu-id="e73dd-122">Robust Programming</span></span>  
 <span data-ttu-id="e73dd-123">若要在处理很大的数据集时实现最大可伸缩性，则应在多个使用相同样式的行、列或单元格之间共享 <xref:System.Windows.Forms.DataGridViewCellStyle> 对象，而不是分别设置单个元素的样式属性。</span><span class="sxs-lookup"><span data-stu-id="e73dd-123">To achieve maximum scalability when you work with very large data sets, you should share <xref:System.Windows.Forms.DataGridViewCellStyle> objects across multiple rows, columns, or cells that use the same styles, rather than set the style properties for individual elements separately.</span></span> <span data-ttu-id="e73dd-124">此外，应创建共享行并使用 <xref:System.Windows.Forms.DataGridViewRowCollection.SharedRow%2A?displayProperty=nameWithType> 属性对其进行访问。</span><span class="sxs-lookup"><span data-stu-id="e73dd-124">Additionally, you should create shared rows and access them by using the <xref:System.Windows.Forms.DataGridViewRowCollection.SharedRow%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="e73dd-125">有关详细信息，请参阅[缩放 Windows 窗体 DataGridView 控件的最佳做法](best-practices-for-scaling-the-windows-forms-datagridview-control.md)。</span><span class="sxs-lookup"><span data-stu-id="e73dd-125">For more information, see [Best Practices for Scaling the Windows Forms DataGridView Control](best-practices-for-scaling-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e73dd-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="e73dd-126">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewCellStyle>
- <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewBand.DefaultCellStyle%2A?displayProperty=nameWithType>
- [<span data-ttu-id="e73dd-127">Windows 窗体 DataGridView 控件中的基本格式和样式设置</span><span class="sxs-lookup"><span data-stu-id="e73dd-127">Basic Formatting and Styling in the Windows Forms DataGridView Control</span></span>](basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="e73dd-128">Windows 窗体 DataGridView 控件中的单元格样式</span><span class="sxs-lookup"><span data-stu-id="e73dd-128">Cell Styles in the Windows Forms DataGridView Control</span></span>](cell-styles-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="e73dd-129">有关缩放 Windows 窗体 DataGridView 控件的最佳做法</span><span class="sxs-lookup"><span data-stu-id="e73dd-129">Best Practices for Scaling the Windows Forms DataGridView Control</span></span>](best-practices-for-scaling-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="e73dd-130">如何：设置 Windows 窗体 DataGridView 控件的交替行样式</span><span class="sxs-lookup"><span data-stu-id="e73dd-130">How to: Set Alternating Row Styles for the Windows Forms DataGridView Control</span></span>](how-to-set-alternating-row-styles-for-the-windows-forms-datagridview-control.md)
