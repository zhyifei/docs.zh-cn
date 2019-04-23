---
title: 如何：在 Windows 窗体 DataGridView 控件的单元格中显示图像
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cells [Windows Forms], displaying images
- data grids [Windows Forms], displaying in grids
- DataGridView control [Windows Forms], displaying images
- data grids [Windows Forms], displaying images in cells
ms.assetid: 53b13d31-1b56-476d-9ab4-18bfac138a22
ms.openlocfilehash: 90aaff419ecc2c890a8b3802f3aaf12092febb73
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59082988"
---
# <a name="how-to-display-images-in-cells-of-the-windows-forms-datagridview-control"></a><span data-ttu-id="e236d-102">如何：在 Windows 窗体 DataGridView 控件的单元格中显示图像</span><span class="sxs-lookup"><span data-stu-id="e236d-102">How to: Display Images in Cells of the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="e236d-103">图片或图形是可以在数据行中显示的值之一。</span><span class="sxs-lookup"><span data-stu-id="e236d-103">A picture or graphic is one of the values that you can display in a row of data.</span></span> <span data-ttu-id="e236d-104">通常情况下，这些图形需要员工的照片或公司徽标的形式。</span><span class="sxs-lookup"><span data-stu-id="e236d-104">Frequently, these graphics take the form of an employee's photograph or a company logo.</span></span>  
  
 <span data-ttu-id="e236d-105">当显示中的数据并入图片很简单<xref:System.Windows.Forms.DataGridView>控件。</span><span class="sxs-lookup"><span data-stu-id="e236d-105">Incorporating pictures is simple when you display data within the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="e236d-106"><xref:System.Windows.Forms.DataGridView>控件本身处理所支持的任何图像格式<xref:System.Drawing.Image>类，以及 OLE 的图片使用某些数据库格式。</span><span class="sxs-lookup"><span data-stu-id="e236d-106">The <xref:System.Windows.Forms.DataGridView> control natively handles any image format supported by the <xref:System.Drawing.Image> class, as well as the OLE picture format used by some databases.</span></span>  
  
 <span data-ttu-id="e236d-107">如果<xref:System.Windows.Forms.DataGridView>控件的数据源包含一个映像，将自动显示<xref:System.Windows.Forms.DataGridView>控件。</span><span class="sxs-lookup"><span data-stu-id="e236d-107">If the <xref:System.Windows.Forms.DataGridView> control's data source has a column of images, they will be displayed automatically by the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 <span data-ttu-id="e236d-108">下面的代码示例演示如何从嵌入的资源提取一个图标，并将其转换为 image 列的每个单元格中显示的位图。</span><span class="sxs-lookup"><span data-stu-id="e236d-108">The following code example demonstrates how to extract an icon from an embedded resource and convert it to a bitmap for display in every cell of an image column.</span></span> <span data-ttu-id="e236d-109">文本单元格的值替换为相应的图像的另一个示例，请参阅[如何：自定义 Windows 窗体 DataGridView 控件中的数据格式设置](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)。</span><span class="sxs-lookup"><span data-stu-id="e236d-109">For another example that replaces textual cell values with corresponding images, see [How to: Customize Data Formatting in the Windows Forms DataGridView Control](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e236d-110">示例</span><span class="sxs-lookup"><span data-stu-id="e236d-110">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#050](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#050)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#050](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#050)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="e236d-111">编译代码</span><span class="sxs-lookup"><span data-stu-id="e236d-111">Compiling the Code</span></span>  
 <span data-ttu-id="e236d-112">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="e236d-112">This example requires:</span></span>  
  
-   <span data-ttu-id="e236d-113">名为 `dataGridView1` 的 <xref:System.Windows.Forms.DataGridView> 控件。</span><span class="sxs-lookup"><span data-stu-id="e236d-113">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
-   <span data-ttu-id="e236d-114">一个名为嵌入的图标资源`tree.ico`。</span><span class="sxs-lookup"><span data-stu-id="e236d-114">An embedded icon resource named `tree.ico`.</span></span>  
  
-   <span data-ttu-id="e236d-115">对 <xref:System?displayProperty=nameWithType><xref:System.Windows.Forms?displayProperty=nameWithType> 和 <xref:System.Drawing?displayProperty=nameWithType> 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="e236d-115">References to the <xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType>, and <xref:System.Drawing?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e236d-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="e236d-116">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- [<span data-ttu-id="e236d-117">Windows 窗体 DataGridView 控件中的列、行和单元格基本功能</span><span class="sxs-lookup"><span data-stu-id="e236d-117">Basic Column, Row, and Cell Features in the Windows Forms DataGridView Control</span></span>](basic-column-row-and-cell-features-wf-datagridview-control.md)
- [<span data-ttu-id="e236d-118">如何：自定义 Windows 窗体 DataGridView 控件中的数据格式设置</span><span class="sxs-lookup"><span data-stu-id="e236d-118">How to: Customize Data Formatting in the Windows Forms DataGridView Control</span></span>](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)
