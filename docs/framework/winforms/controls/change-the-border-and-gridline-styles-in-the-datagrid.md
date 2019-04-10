---
title: 如何：更改 Windows 窗体 DataGridView 控件中的边框和网格线的样式
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- gridlines [Windows Forms], changing styles
- data grids [Windows Forms], changing gridline styles
- DataGridView control [Windows Forms], border styles
- data grids [Windows Forms], changing border styles
- DataGridView control [Windows Forms], gridline styles
ms.assetid: 2f413c7a-4025-4171-8e3a-66ef908ea583
ms.openlocfilehash: d24adb98c339f911d6bea0312bce4d4b4f198a61
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59224983"
---
# <a name="how-to-change-the-border-and-gridline-styles-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="7dcd0-102">如何：更改 Windows 窗体 DataGridView 控件中的边框和网格线的样式</span><span class="sxs-lookup"><span data-stu-id="7dcd0-102">How to: Change the Border and Gridline Styles in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="7dcd0-103">使用<xref:System.Windows.Forms.DataGridView>控件，您可以自定义控件的边框和网格，以改善用户体验的外观。</span><span class="sxs-lookup"><span data-stu-id="7dcd0-103">With the <xref:System.Windows.Forms.DataGridView> control, you can customize the appearance of the control's border and gridlines to improve the user experience.</span></span> <span data-ttu-id="7dcd0-104">您可以修改网格线颜色和除了在控件内的单元格的边框样式的控件边框样式。</span><span class="sxs-lookup"><span data-stu-id="7dcd0-104">You can modify the gridline color and the control border style in addition to the border styles for the cells within the control.</span></span> <span data-ttu-id="7dcd0-105">您还可以应用不同的单元格普通单元格、 行标题单元格和列标题单元格的边框样式。</span><span class="sxs-lookup"><span data-stu-id="7dcd0-105">You can also apply different cell border styles for ordinary cells, row header cells, and column header cells.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7dcd0-106">网格线颜色仅用于<xref:System.Windows.Forms.DataGridViewCellBorderStyle.Single>， <xref:System.Windows.Forms.DataGridViewCellBorderStyle.SingleHorizontal>，并<xref:System.Windows.Forms.DataGridViewCellBorderStyle.SingleVertical>的值<xref:System.Windows.Forms.DataGridViewCellBorderStyle>枚举并<xref:System.Windows.Forms.DataGridViewHeaderBorderStyle.Single>的值<xref:System.Windows.Forms.DataGridViewHeaderBorderStyle>枚举。</span><span class="sxs-lookup"><span data-stu-id="7dcd0-106">The gridline color is used only with the <xref:System.Windows.Forms.DataGridViewCellBorderStyle.Single>, <xref:System.Windows.Forms.DataGridViewCellBorderStyle.SingleHorizontal>, and <xref:System.Windows.Forms.DataGridViewCellBorderStyle.SingleVertical> values of the <xref:System.Windows.Forms.DataGridViewCellBorderStyle> enumeration and the <xref:System.Windows.Forms.DataGridViewHeaderBorderStyle.Single> value of the <xref:System.Windows.Forms.DataGridViewHeaderBorderStyle> enumeration.</span></span> <span data-ttu-id="7dcd0-107">这些枚举的其他值使用由操作系统指定的颜色。</span><span class="sxs-lookup"><span data-stu-id="7dcd0-107">The other values of these enumerations use colors specified by the operating system.</span></span> <span data-ttu-id="7dcd0-108">此外，当启用了可视样式在 Windows XP 和通过 Windows Server 2003 家族<xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType>方法，<xref:System.Windows.Forms.DataGridView.GridColor%2A>不使用属性值。</span><span class="sxs-lookup"><span data-stu-id="7dcd0-108">Additionally, when visual styles are enabled on Windows XP and the Windows Server 2003 family through the <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> method, the <xref:System.Windows.Forms.DataGridView.GridColor%2A> property value is not used.</span></span>  
  
### <a name="to-change-the-gridline-color-programmatically"></a><span data-ttu-id="7dcd0-109">若要以编程方式更改网格线颜色</span><span class="sxs-lookup"><span data-stu-id="7dcd0-109">To change the gridline color programmatically</span></span>  
  
-   <span data-ttu-id="7dcd0-110">设置 <xref:System.Windows.Forms.DataGridView.GridColor%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="7dcd0-110">Set the <xref:System.Windows.Forms.DataGridView.GridColor%2A> property.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#031](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#031)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#031](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#031)]  
  
### <a name="to-change-the-border-style-of-the-entire-datagridview-control-programmatically"></a><span data-ttu-id="7dcd0-111">若要以编程方式更改整个 DataGridView 控件的边框样式</span><span class="sxs-lookup"><span data-stu-id="7dcd0-111">To change the border style of the entire DataGridView control programmatically</span></span>  
  
-   <span data-ttu-id="7dcd0-112">将 <xref:System.Windows.Forms.DataGridView.BorderStyle%2A> 属性设置为 <xref:System.Windows.Forms.BorderStyle> 枚举值之一。</span><span class="sxs-lookup"><span data-stu-id="7dcd0-112">Set the <xref:System.Windows.Forms.DataGridView.BorderStyle%2A> property to one of the <xref:System.Windows.Forms.BorderStyle> enumeration values.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#032](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#032)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#032](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#032)]  
  
### <a name="to-change-the-border-styles-for-datagridview-cells-programmatically"></a><span data-ttu-id="7dcd0-113">若要以编程方式更改 DataGridView 单元格的边框样式</span><span class="sxs-lookup"><span data-stu-id="7dcd0-113">To change the border styles for DataGridView cells programmatically</span></span>  
  
-   <span data-ttu-id="7dcd0-114">设置<xref:System.Windows.Forms.DataGridView.CellBorderStyle%2A>， <xref:System.Windows.Forms.DataGridView.RowHeadersBorderStyle%2A>，和<xref:System.Windows.Forms.DataGridView.ColumnHeadersBorderStyle%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="7dcd0-114">Set the <xref:System.Windows.Forms.DataGridView.CellBorderStyle%2A>, <xref:System.Windows.Forms.DataGridView.RowHeadersBorderStyle%2A>, and <xref:System.Windows.Forms.DataGridView.ColumnHeadersBorderStyle%2A> properties.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#033](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#033)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#033](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#033)]  
  
## <a name="example"></a><span data-ttu-id="7dcd0-115">示例</span><span class="sxs-lookup"><span data-stu-id="7dcd0-115">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#030](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#030)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#030](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#030)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="7dcd0-116">编译代码</span><span class="sxs-lookup"><span data-stu-id="7dcd0-116">Compiling the Code</span></span>  
 <span data-ttu-id="7dcd0-117">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="7dcd0-117">This example requires:</span></span>  
  
-   <span data-ttu-id="7dcd0-118">名为 `dataGridView1` 的 <xref:System.Windows.Forms.DataGridView> 控件。</span><span class="sxs-lookup"><span data-stu-id="7dcd0-118">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
-   <span data-ttu-id="7dcd0-119">对 <xref:System?displayProperty=nameWithType><xref:System.Windows.Forms?displayProperty=nameWithType> 和 <xref:System.Drawing?displayProperty=nameWithType> 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="7dcd0-119">References to the <xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType>, and <xref:System.Drawing?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7dcd0-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="7dcd0-120">See also</span></span>

- <xref:System.Windows.Forms.BorderStyle>
- <xref:System.Windows.Forms.DataGridView.BorderStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.CellBorderStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.ColumnHeadersBorderStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.GridColor%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.RowHeadersBorderStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewCellBorderStyle>
- <xref:System.Windows.Forms.DataGridViewHeaderBorderStyle>
- [<span data-ttu-id="7dcd0-121">Windows 窗体 DataGridView 控件中的基本格式设置和样式设置</span><span class="sxs-lookup"><span data-stu-id="7dcd0-121">Basic Formatting and Styling in the Windows Forms DataGridView Control</span></span>](basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)
