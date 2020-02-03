---
title: 自定义 DataGridView 控件中的数据格式设置
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], formatting data
- DataGridView control [Windows Forms], cell styles
- cells [Windows Forms], changing colors in DataGridView control [Windows Forms]
- colors [Windows Forms], changing in DataGridView control [Windows Forms]
- data [Windows Forms], formatting in DataGridView control
- DataGridView control [Windows Forms], cell customization
- DataGridView control [Windows Forms], changing cell colors
- Windows Forms, changing colors of DataGridView cells
- DataGridView control [Windows Forms], substituting cell values for display
- data grids [Windows Forms], formatting data
ms.assetid: a6e72c70-ce18-425f-828d-d57be6f96ab6
ms.openlocfilehash: 6bc1a65b876df842df322db165dc08fcc0c931dc
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746786"
---
# <a name="how-to-customize-data-formatting-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="8b76c-102">如何：自定义 Windows 窗体 DataGridView 控件中的数据格式设置</span><span class="sxs-lookup"><span data-stu-id="8b76c-102">How to: Customize Data Formatting in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="8b76c-103">下面的代码示例演示如何实现 <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType> 事件的处理程序，该事件根据单元格的列和值更改单元格的显示方式。</span><span class="sxs-lookup"><span data-stu-id="8b76c-103">The following code example demonstrates how to implement a handler for the <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType> event that changes how cells are displayed depending on their columns and values.</span></span>  
  
 <span data-ttu-id="8b76c-104">包含负数的 `Balance` 列中的单元格的背景颜色设为红色。</span><span class="sxs-lookup"><span data-stu-id="8b76c-104">Cells in the `Balance` column that contain negative numbers are given a red background.</span></span> <span data-ttu-id="8b76c-105">也可将这些单元格的格式设置为货币，以显示负值两边的括号。</span><span class="sxs-lookup"><span data-stu-id="8b76c-105">You can also format these cells as currency to display parentheses around negative values.</span></span> <span data-ttu-id="8b76c-106">有关详细信息，请参阅[如何：设置 Windows 窗体 DataGridView 控件中的数据格式](how-to-format-data-in-the-windows-forms-datagridview-control.md)。</span><span class="sxs-lookup"><span data-stu-id="8b76c-106">For more information, see [How to: Format Data in the Windows Forms DataGridView Control](how-to-format-data-in-the-windows-forms-datagridview-control.md).</span></span>  
  
 <span data-ttu-id="8b76c-107">`Priority` 列中的单元格显示图像以代替对应文本单元格值。</span><span class="sxs-lookup"><span data-stu-id="8b76c-107">Cells in the `Priority` column display images in place of corresponding textual cell values.</span></span> <span data-ttu-id="8b76c-108"><xref:System.Windows.Forms.ConvertEventArgs.Value%2A> 的 <xref:System.Windows.Forms.DataGridViewCellFormattingEventArgs> 属性同时用于获取文本单元格的值以及设置相应的图像显示值。</span><span class="sxs-lookup"><span data-stu-id="8b76c-108">The <xref:System.Windows.Forms.ConvertEventArgs.Value%2A> property of the <xref:System.Windows.Forms.DataGridViewCellFormattingEventArgs> is used both to get the textual cell value and to set the corresponding image display value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8b76c-109">示例</span><span class="sxs-lookup"><span data-stu-id="8b76c-109">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewCustomizeDataFormatting#00](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCustomizeDataFormatting/cs/customFormatting.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewCustomizeDataFormatting#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCustomizeDataFormatting/vb/customFormatting.vb#00)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="8b76c-110">编译代码</span><span class="sxs-lookup"><span data-stu-id="8b76c-110">Compiling the Code</span></span>  
 <span data-ttu-id="8b76c-111">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="8b76c-111">This example requires:</span></span>  
  
- <span data-ttu-id="8b76c-112">对 System、System.Drawing 和 System.Windows.Forms 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="8b76c-112">References to the System, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
- <span data-ttu-id="8b76c-113">名为 <xref:System.Drawing.Bitmap>、`highPri.bmp` 和 `mediumPri.bmp` 的 `lowPri.bmp` 图像，这些图像与可执行文件驻留在相同的目录中。</span><span class="sxs-lookup"><span data-stu-id="8b76c-113"><xref:System.Drawing.Bitmap> images named `highPri.bmp`, `mediumPri.bmp`, and `lowPri.bmp` residing in the same directory as the executable file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b76c-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8b76c-114">See also</span></span>

- <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewBand.DefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewCellStyle>
- <xref:System.Drawing.Bitmap>
- [<span data-ttu-id="8b76c-115">在 Windows 窗体 DataGridView 控件中显示数据</span><span class="sxs-lookup"><span data-stu-id="8b76c-115">Displaying Data in the Windows Forms DataGridView Control</span></span>](displaying-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="8b76c-116">如何：在 Windows 窗体 DataGridView 控件中设置数据格式</span><span class="sxs-lookup"><span data-stu-id="8b76c-116">How to: Format Data in the Windows Forms DataGridView Control</span></span>](how-to-format-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="8b76c-117">Windows 窗体 DataGridView 控件中的单元格样式</span><span class="sxs-lookup"><span data-stu-id="8b76c-117">Cell Styles in the Windows Forms DataGridView Control</span></span>](cell-styles-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="8b76c-118">Windows 窗体 DataGridView 控件中的数据格式设置</span><span class="sxs-lookup"><span data-stu-id="8b76c-118">Data Formatting in the Windows Forms DataGridView Control</span></span>](data-formatting-in-the-windows-forms-datagridview-control.md)
