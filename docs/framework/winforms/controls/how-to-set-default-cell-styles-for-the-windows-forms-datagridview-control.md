---
title: "如何：设置 Windows 窗体 DataGridView 控件的默认单元格样式"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], cell styles
- cells [Windows Forms], styles
- data grids [Windows Forms], cell styles
ms.assetid: 1aaaca43-5340-447e-99c0-9177d9776aa1
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c817f62ede780ad0164ef78156b1a028e0c7a0a6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control"></a><span data-ttu-id="0ce13-102">如何：设置 Windows 窗体 DataGridView 控件的默认单元格样式</span><span class="sxs-lookup"><span data-stu-id="0ce13-102">How to: Set Default Cell Styles for the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="0ce13-103">借助 <xref:System.Windows.Forms.DataGridView> 控件，可以指定整个控件以及特定列和行的默认单元格样式。</span><span class="sxs-lookup"><span data-stu-id="0ce13-103">With the <xref:System.Windows.Forms.DataGridView> control, you can specify default cell styles for the entire control and for specific columns and rows.</span></span> <span data-ttu-id="0ce13-104">这些默认设置依次向下筛选：从控件级别到列级别，然后到行级别，再到单元格级别。</span><span class="sxs-lookup"><span data-stu-id="0ce13-104">These defaults filter down from the control level to the column level, then to the row level, then to the cell level.</span></span> <span data-ttu-id="0ce13-105">如果未在单元格级别设置特定 <xref:System.Windows.Forms.DataGridViewCellStyle> 属性，则使用行级别的默认属性设置。</span><span class="sxs-lookup"><span data-stu-id="0ce13-105">If a particular <xref:System.Windows.Forms.DataGridViewCellStyle> property is not set at the cell level, the default property setting at the row level is used.</span></span> <span data-ttu-id="0ce13-106">如果在行级别也未设置该属性，则使用默认列设置。</span><span class="sxs-lookup"><span data-stu-id="0ce13-106">If the property is also not set at the row level, the default column setting is used.</span></span> <span data-ttu-id="0ce13-107">最后，如果在列级别也未设置该属性，那么则使用默认的 <xref:System.Windows.Forms.DataGridView> 设置。</span><span class="sxs-lookup"><span data-stu-id="0ce13-107">Finally, if the property is also not set at the column level, the default <xref:System.Windows.Forms.DataGridView> setting is used.</span></span> <span data-ttu-id="0ce13-108">借助此设置，可以避免必须重复多个级别的属性设置。</span><span class="sxs-lookup"><span data-stu-id="0ce13-108">With this setting, you can avoid having to duplicate the property settings at multiple levels.</span></span> <span data-ttu-id="0ce13-109">在每个级别，只需指定与其上级别不同的样式。</span><span class="sxs-lookup"><span data-stu-id="0ce13-109">At each level, simply specify the styles that differ from the levels above it.</span></span> <span data-ttu-id="0ce13-110">有关详细信息，请参阅[在 Windows 窗体 DataGridView 控件中的单元格样式](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md)。</span><span class="sxs-lookup"><span data-stu-id="0ce13-110">For more information, see [Cell Styles in the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md).</span></span>  
  
 <span data-ttu-id="0ce13-111">Visual Studio 中对此任务提供广泛支持。</span><span class="sxs-lookup"><span data-stu-id="0ce13-111">There is extensive support for this task in Visual Studio.</span></span>  <span data-ttu-id="0ce13-112">另请参阅[如何： 设置默认单元格样式和数据格式以获得 Windows 窗体 DataGridView 控件使用设计器](http://msdn.microsoft.com/library/95y5fz2x\(v=vs.110\))。</span><span class="sxs-lookup"><span data-stu-id="0ce13-112">Also see [How to: Set Default Cell Styles and Data Formats for the Windows Forms DataGridView Control Using the Designer](http://msdn.microsoft.com/library/95y5fz2x\(v=vs.110\)).</span></span>  
  
### <a name="to-set-the-default-cell-styles-programmatically"></a><span data-ttu-id="0ce13-113">以编程方式设置默认单元格样式</span><span class="sxs-lookup"><span data-stu-id="0ce13-113">To set the default cell styles programmatically</span></span>  
  
1.  <span data-ttu-id="0ce13-114">设置通过 <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType> 属性检索的 <xref:System.Windows.Forms.DataGridViewCellStyle> 的属性。</span><span class="sxs-lookup"><span data-stu-id="0ce13-114">Set the properties of the <xref:System.Windows.Forms.DataGridViewCellStyle> retrieved through the <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType> property.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#141](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#141)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#141](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#141)]  
  
2.  <span data-ttu-id="0ce13-115">创建和初始化供多个行和列使用的新 <xref:System.Windows.Forms.DataGridViewCellStyle> 对象。</span><span class="sxs-lookup"><span data-stu-id="0ce13-115">Create and initialize new <xref:System.Windows.Forms.DataGridViewCellStyle> objects for use by multiple rows and columns.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#142](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#142)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#142](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#142)]  
  
3.  <span data-ttu-id="0ce13-116">设置特定行和列的 `DefaultCellStyle` 属性。</span><span class="sxs-lookup"><span data-stu-id="0ce13-116">Set the `DefaultCellStyle` property of specific rows and columns.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#143](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#143)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#143](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#143)]  
  
## <a name="example"></a><span data-ttu-id="0ce13-117">示例</span><span class="sxs-lookup"><span data-stu-id="0ce13-117">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#140](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#140)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#140](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#140)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="0ce13-118">编译代码</span><span class="sxs-lookup"><span data-stu-id="0ce13-118">Compiling the Code</span></span>  
 <span data-ttu-id="0ce13-119">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="0ce13-119">This example requires:</span></span>  
  
-   <span data-ttu-id="0ce13-120">名为 `dataGridView1` 的 <xref:System.Windows.Forms.DataGridView> 控件。</span><span class="sxs-lookup"><span data-stu-id="0ce13-120">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
-   <span data-ttu-id="0ce13-121">对 <xref:System?displayProperty=nameWithType><xref:System.Drawing?displayProperty=nameWithType> 和 <xref:System.Windows.Forms?displayProperty=nameWithType> 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="0ce13-121">References to the <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType>, and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="0ce13-122">可靠编程</span><span class="sxs-lookup"><span data-stu-id="0ce13-122">Robust Programming</span></span>  
 <span data-ttu-id="0ce13-123">若要在处理很大的数据集时实现最大可伸缩性，则应在多个使用相同样式的行、列或单元格之间共享 <xref:System.Windows.Forms.DataGridViewCellStyle> 对象，而不是分别设置单个元素的样式属性。</span><span class="sxs-lookup"><span data-stu-id="0ce13-123">To achieve maximum scalability when you work with very large data sets, you should share <xref:System.Windows.Forms.DataGridViewCellStyle> objects across multiple rows, columns, or cells that use the same styles, rather than set the style properties for individual elements separately.</span></span> <span data-ttu-id="0ce13-124">此外，应创建共享行并使用 <xref:System.Windows.Forms.DataGridViewRowCollection.SharedRow%2A?displayProperty=nameWithType> 属性对其进行访问。</span><span class="sxs-lookup"><span data-stu-id="0ce13-124">Additionally, you should create shared rows and access them by using the <xref:System.Windows.Forms.DataGridViewRowCollection.SharedRow%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="0ce13-125">有关详细信息，请参阅[缩放 Windows 窗体 DataGridView 控件的最佳做法](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md)。</span><span class="sxs-lookup"><span data-stu-id="0ce13-125">For more information, see [Best Practices for Scaling the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ce13-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="0ce13-126">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridViewCellStyle>  
 <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewBand.DefaultCellStyle%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="0ce13-127">Windows 窗体 DataGridView 控件中的基本格式和样式设置</span><span class="sxs-lookup"><span data-stu-id="0ce13-127">Basic Formatting and Styling in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)  
 [<span data-ttu-id="0ce13-128">Windows 窗体 DataGridView 控件中的单元格样式</span><span class="sxs-lookup"><span data-stu-id="0ce13-128">Cell Styles in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md)  
 [<span data-ttu-id="0ce13-129">有关缩放 Windows 窗体 DataGridView 控件的最佳做法</span><span class="sxs-lookup"><span data-stu-id="0ce13-129">Best Practices for Scaling the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md)  
 [<span data-ttu-id="0ce13-130">如何：设置 Windows 窗体 DataGridView 控件的交替行样式</span><span class="sxs-lookup"><span data-stu-id="0ce13-130">How to: Set Alternating Row Styles for the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-set-alternating-row-styles-for-the-windows-forms-datagridview-control.md)
