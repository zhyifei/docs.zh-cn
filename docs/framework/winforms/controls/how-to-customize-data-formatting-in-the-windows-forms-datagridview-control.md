---
title: 如何：在 Windows 窗体 DataGridView 控件中自定义数据格式设置
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
ms.openlocfilehash: 5ce43054130db88792acab852b1e886285ff34d7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59116046"
---
# <a name="how-to-customize-data-formatting-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="f62ff-102">如何：在 Windows 窗体 DataGridView 控件中自定义数据格式设置</span><span class="sxs-lookup"><span data-stu-id="f62ff-102">How to: Customize Data Formatting in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="f62ff-103">下面的代码示例演示如何实现 <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType> 事件的处理程序，该事件根据单元格的列和值更改单元格的显示方式。</span><span class="sxs-lookup"><span data-stu-id="f62ff-103">The following code example demonstrates how to implement a handler for the <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType> event that changes how cells are displayed depending on their columns and values.</span></span>  
  
 <span data-ttu-id="f62ff-104">包含负数的 `Balance` 列中的单元格的背景颜色设为红色。</span><span class="sxs-lookup"><span data-stu-id="f62ff-104">Cells in the `Balance` column that contain negative numbers are given a red background.</span></span> <span data-ttu-id="f62ff-105">也可将这些单元格的格式设置为货币，以显示负值两边的括号。</span><span class="sxs-lookup"><span data-stu-id="f62ff-105">You can also format these cells as currency to display parentheses around negative values.</span></span> <span data-ttu-id="f62ff-106">有关详细信息，请参阅[如何：Windows 中的数据格式窗体 DataGridView 控件](how-to-format-data-in-the-windows-forms-datagridview-control.md)。</span><span class="sxs-lookup"><span data-stu-id="f62ff-106">For more information, see [How to: Format Data in the Windows Forms DataGridView Control](how-to-format-data-in-the-windows-forms-datagridview-control.md).</span></span>  
  
 <span data-ttu-id="f62ff-107">`Priority` 列中的单元格显示图像以代替对应文本单元格值。</span><span class="sxs-lookup"><span data-stu-id="f62ff-107">Cells in the `Priority` column display images in place of corresponding textual cell values.</span></span> <span data-ttu-id="f62ff-108"><xref:System.Windows.Forms.DataGridViewCellFormattingEventArgs> 的 <xref:System.Windows.Forms.ConvertEventArgs.Value%2A> 属性同时用于获取文本单元格的值以及设置相应的图像显示值。</span><span class="sxs-lookup"><span data-stu-id="f62ff-108">The <xref:System.Windows.Forms.ConvertEventArgs.Value%2A> property of the <xref:System.Windows.Forms.DataGridViewCellFormattingEventArgs> is used both to get the textual cell value and to set the corresponding image display value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f62ff-109">示例</span><span class="sxs-lookup"><span data-stu-id="f62ff-109">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewCustomizeDataFormatting#00](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCustomizeDataFormatting/cs/customFormatting.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewCustomizeDataFormatting#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCustomizeDataFormatting/vb/customFormatting.vb#00)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="f62ff-110">编译代码</span><span class="sxs-lookup"><span data-stu-id="f62ff-110">Compiling the Code</span></span>  
 <span data-ttu-id="f62ff-111">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="f62ff-111">This example requires:</span></span>  
  
-   <span data-ttu-id="f62ff-112">对 System、System.Drawing 和 System.Windows.Forms 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="f62ff-112">References to the System, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
-   <span data-ttu-id="f62ff-113">名为 `highPri.bmp`、`mediumPri.bmp` 和 `lowPri.bmp` 的 <xref:System.Drawing.Bitmap> 图像，这些图像与可执行文件驻留在相同的目录中。</span><span class="sxs-lookup"><span data-stu-id="f62ff-113"><xref:System.Drawing.Bitmap> images named `highPri.bmp`, `mediumPri.bmp`, and `lowPri.bmp` residing in the same directory as the executable file.</span></span>  
  
 <span data-ttu-id="f62ff-114">Visual Basic 或 Visual C# 生成命令行中的此示例的信息，请参阅[从命令行生成](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md)或[命令行上使用 csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)。</span><span class="sxs-lookup"><span data-stu-id="f62ff-114">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="f62ff-115">也可以通过将代码粘贴到新的项目中生成此示例在 Visual Studio 中。</span><span class="sxs-lookup"><span data-stu-id="f62ff-115">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f62ff-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="f62ff-116">See also</span></span>

- <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewBand.DefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewCellStyle>
- <xref:System.Drawing.Bitmap>
- [<span data-ttu-id="f62ff-117">在 Windows 窗体 DataGridView 控件中显示数据</span><span class="sxs-lookup"><span data-stu-id="f62ff-117">Displaying Data in the Windows Forms DataGridView Control</span></span>](displaying-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="f62ff-118">如何：Windows 中的数据格式窗体 DataGridView 控件</span><span class="sxs-lookup"><span data-stu-id="f62ff-118">How to: Format Data in the Windows Forms DataGridView Control</span></span>](how-to-format-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="f62ff-119">Windows 窗体 DataGridView 控件中的单元格样式</span><span class="sxs-lookup"><span data-stu-id="f62ff-119">Cell Styles in the Windows Forms DataGridView Control</span></span>](cell-styles-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="f62ff-120">Windows 窗体 DataGridView 控件中的数据格式设置</span><span class="sxs-lookup"><span data-stu-id="f62ff-120">Data Formatting in the Windows Forms DataGridView Control</span></span>](data-formatting-in-the-windows-forms-datagridview-control.md)
