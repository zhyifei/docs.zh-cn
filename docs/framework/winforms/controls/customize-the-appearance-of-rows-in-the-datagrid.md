---
title: 如何：自定义 Windows 窗体 DataGridView 控件中行的外观
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data grids [Windows Forms], customizing rows
- rows [Windows Forms], customizing in DataGridView control
- DataGridView control [Windows Forms], customizing rows
ms.assetid: d40b53d2-7e7c-48c5-8570-6e79d15c3bbb
ms.openlocfilehash: 32a21705b553ec915b4510dbe2fa32a0ae097d96
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64648164"
---
# <a name="how-to-customize-the-appearance-of-rows-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="fd8b0-102">如何：自定义 Windows 窗体 DataGridView 控件中行的外观</span><span class="sxs-lookup"><span data-stu-id="fd8b0-102">How to: Customize the Appearance of Rows in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="fd8b0-103">通过处理 <xref:System.Windows.Forms.DataGridView.RowPrePaint?displayProperty=nameWithType> 和 <xref:System.Windows.Forms.DataGridView.RowPostPaint?displayProperty=nameWithType> 事件之一或两者同时处理，可以控制 <xref:System.Windows.Forms.DataGridView> 行的外观。</span><span class="sxs-lookup"><span data-stu-id="fd8b0-103">You can control the appearance of <xref:System.Windows.Forms.DataGridView> rows by handling one or both of the <xref:System.Windows.Forms.DataGridView.RowPrePaint?displayProperty=nameWithType> and <xref:System.Windows.Forms.DataGridView.RowPostPaint?displayProperty=nameWithType> events.</span></span> <span data-ttu-id="fd8b0-104">这些事件设计用于使你可以仅绘制想绘制的内容，同时使 <xref:System.Windows.Forms.DataGridView> 控件绘制其余内容。</span><span class="sxs-lookup"><span data-stu-id="fd8b0-104">These events are designed so that you can paint only what you want to while letting the <xref:System.Windows.Forms.DataGridView> control paint the rest.</span></span> <span data-ttu-id="fd8b0-105">例如，如果要绘制自定义背景，则可以处理 <xref:System.Windows.Forms.DataGridView.RowPrePaint?displayProperty=nameWithType> 事件并让各个单元格自行绘制自己的前景内容。</span><span class="sxs-lookup"><span data-stu-id="fd8b0-105">For example, if you want to paint a custom background, you can handle the <xref:System.Windows.Forms.DataGridView.RowPrePaint?displayProperty=nameWithType> event and let the individual cells paint their own foreground content.</span></span> <span data-ttu-id="fd8b0-106">或者，还可以让单元格自行绘制，并在 <xref:System.Windows.Forms.DataGridView.RowPostPaint?displayProperty=nameWithType> 事件的处理程序中添加自定义前景内容。</span><span class="sxs-lookup"><span data-stu-id="fd8b0-106">Alternately, you can let the cells paint themselves and add custom foreground content in a handler for the <xref:System.Windows.Forms.DataGridView.RowPostPaint?displayProperty=nameWithType> event.</span></span> <span data-ttu-id="fd8b0-107">此外，还可以禁用单元格绘制，并在 <xref:System.Windows.Forms.DataGridView.RowPrePaint?displayProperty=nameWithType> 事件处理程序中亲自绘制所有内容。</span><span class="sxs-lookup"><span data-stu-id="fd8b0-107">You can also disable cell painting and paint everything yourself in a <xref:System.Windows.Forms.DataGridView.RowPrePaint?displayProperty=nameWithType> event handler.</span></span>  
  
 <span data-ttu-id="fd8b0-108">下面的代码示例实现两个事件的处理程序，以便提供渐变选区背景和某些跨多个列的自定义前景内容。</span><span class="sxs-lookup"><span data-stu-id="fd8b0-108">The following code example implements handlers for both events in order to provide a gradient selection background and some custom foreground content that spans multiple columns.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fd8b0-109">示例</span><span class="sxs-lookup"><span data-stu-id="fd8b0-109">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewRowPainting#00](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewRowPainting/CS/datagridviewrowpainting.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewRowPainting#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewRowPainting/VB/datagridviewrowpainting.vb#00)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="fd8b0-110">编译代码</span><span class="sxs-lookup"><span data-stu-id="fd8b0-110">Compiling the Code</span></span>  
 <span data-ttu-id="fd8b0-111">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="fd8b0-111">This example requires:</span></span>  
  
- <span data-ttu-id="fd8b0-112">对 System、System.Drawing 和 System.Windows.Forms 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="fd8b0-112">References to the System, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="fd8b0-113">Visual Basic 或 Visual C# 生成命令行中的此示例的信息，请参阅[从命令行生成](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md)或[命令行上使用 csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)。</span><span class="sxs-lookup"><span data-stu-id="fd8b0-113">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="fd8b0-114">也可以通过将代码粘贴到新的项目中生成此示例在 Visual Studio 中。</span><span class="sxs-lookup"><span data-stu-id="fd8b0-114">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  

## <a name="see-also"></a><span data-ttu-id="fd8b0-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="fd8b0-115">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.RowPrePaint?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.RowPostPaint?displayProperty=nameWithType>
- [<span data-ttu-id="fd8b0-116">自定义 Windows 窗体 DataGridView 控件</span><span class="sxs-lookup"><span data-stu-id="fd8b0-116">Customizing the Windows Forms DataGridView Control</span></span>](customizing-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="fd8b0-117">DataGridView 控件体系结构</span><span class="sxs-lookup"><span data-stu-id="fd8b0-117">DataGridView Control Architecture</span></span>](datagridview-control-architecture-windows-forms.md)
