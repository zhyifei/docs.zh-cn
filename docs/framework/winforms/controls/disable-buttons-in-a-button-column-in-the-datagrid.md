---
title: 如何：禁用 Windows 窗体 DataGridView 控件的按钮列中的按钮
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data grids [Windows Forms], disabling buttons
- buttons [Windows Forms], disabling in button columns
- DataGridView control [Windows Forms], disabling button cells
ms.assetid: 5c344d01-013a-4a6b-8f8d-62ec9321d81e
ms.openlocfilehash: 8c3c9cf000266a902b42b15a4abe31c979224f8f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59105581"
---
# <a name="how-to-disable-buttons-in-a-button-column-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="bf3c4-102">如何：禁用 Windows 窗体 DataGridView 控件的按钮列中的按钮</span><span class="sxs-lookup"><span data-stu-id="bf3c4-102">How to: Disable Buttons in a Button Column in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="bf3c4-103"><xref:System.Windows.Forms.DataGridView> 控件包括 <xref:System.Windows.Forms.DataGridViewButtonCell> 类，其用于显示具有与按钮类似的用户界面 (UI) 的单元格。</span><span class="sxs-lookup"><span data-stu-id="bf3c4-103">The <xref:System.Windows.Forms.DataGridView> control includes the <xref:System.Windows.Forms.DataGridViewButtonCell> class for displaying cells with a user interface (UI) like a button.</span></span> <span data-ttu-id="bf3c4-104">但是，<xref:System.Windows.Forms.DataGridViewButtonCell> 不提供禁用单元格所显示按钮外观的方法。</span><span class="sxs-lookup"><span data-stu-id="bf3c4-104">However, <xref:System.Windows.Forms.DataGridViewButtonCell> does not provide a way to disable the appearance of the button displayed by the cell.</span></span>  
  
 <span data-ttu-id="bf3c4-105">以下代码示例演示如何自定义 <xref:System.Windows.Forms.DataGridViewButtonCell> 类以显示可以显示为禁用的按钮。</span><span class="sxs-lookup"><span data-stu-id="bf3c4-105">The following code example demonstrates how to customize the <xref:System.Windows.Forms.DataGridViewButtonCell> class to display buttons that can appear disabled.</span></span> <span data-ttu-id="bf3c4-106">此示例定义了一个新的单元格类型，即从 <xref:System.Windows.Forms.DataGridViewButtonCell> 派生的 `DataGridViewDisableButtonCell`。</span><span class="sxs-lookup"><span data-stu-id="bf3c4-106">The example defines a new cell type, `DataGridViewDisableButtonCell`, that derives from <xref:System.Windows.Forms.DataGridViewButtonCell>.</span></span> <span data-ttu-id="bf3c4-107">此单元格类型提供了一种新 `Enabled` 属性，可设置为 `false` 以拖动单元格中已禁用的按钮。</span><span class="sxs-lookup"><span data-stu-id="bf3c4-107">This cell type provides a new `Enabled` property that can be set to `false` to draw a disabled button in the cell.</span></span> <span data-ttu-id="bf3c4-108">此示例还定义了一个新的列类型，即显示 `DataGridViewDisableButtonCell` 对象的 `DataGridViewDisableButtonColumn`。</span><span class="sxs-lookup"><span data-stu-id="bf3c4-108">The example also defines a new column type, `DataGridViewDisableButtonColumn`, that displays `DataGridViewDisableButtonCell` objects.</span></span> <span data-ttu-id="bf3c4-109">为了演示此新单元格和列类型，父级 <xref:System.Windows.Forms.DataGridView> 中的每个 <xref:System.Windows.Forms.DataGridViewCheckBoxCell> 的当前值确定了相同行中 `DataGridViewDisableButtonCell` 的 `Enabled` 属性是否是 `true` 或 `false`。</span><span class="sxs-lookup"><span data-stu-id="bf3c4-109">To demonstrate this new cell and column type, the current value of each <xref:System.Windows.Forms.DataGridViewCheckBoxCell> in the parent <xref:System.Windows.Forms.DataGridView> determines whether the `Enabled` property of the `DataGridViewDisableButtonCell` in the same row is `true` or `false`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bf3c4-110">当从 <xref:System.Windows.Forms.DataGridViewCell> 或 <xref:System.Windows.Forms.DataGridViewColumn> 进行派生并将新属性添加到派生的类时，请确保重写 `Clone` 方法以在克隆操作过程中复制新属性。</span><span class="sxs-lookup"><span data-stu-id="bf3c4-110">When you derive from <xref:System.Windows.Forms.DataGridViewCell> or <xref:System.Windows.Forms.DataGridViewColumn> and add new properties to the derived class, be sure to override the `Clone` method to copy the new properties during cloning operations.</span></span> <span data-ttu-id="bf3c4-111">还应调用基类的 `Clone` 方法，以便将基类的属性复制到新的单元格或列。</span><span class="sxs-lookup"><span data-stu-id="bf3c4-111">You should also call the base class's `Clone` method so that the properties of the base class are copied to the new cell or column.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bf3c4-112">示例</span><span class="sxs-lookup"><span data-stu-id="bf3c4-112">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridView.DisabledButtons#0](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DisabledButtons/CS/form1.cs#0)]
 [!code-vb[System.Windows.Forms.DataGridView.DisabledButtons#0](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DisabledButtons/VB/form1.vb#0)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="bf3c4-113">编译代码</span><span class="sxs-lookup"><span data-stu-id="bf3c4-113">Compiling the Code</span></span>  
 <span data-ttu-id="bf3c4-114">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="bf3c4-114">This example requires:</span></span>  
  
-   <span data-ttu-id="bf3c4-115">对 the System、System.Drawing、System.Windows.Forms 和 System.Windows.Forms.VisualStyles 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="bf3c4-115">References to the System, System.Drawing, System.Windows.Forms and System.Windows.Forms.VisualStyles assemblies.</span></span>  
  
 <span data-ttu-id="bf3c4-116">Visual Basic 或 Visual C# 生成命令行中的此示例的信息，请参阅[从命令行生成](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md)或[命令行上使用 csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)。</span><span class="sxs-lookup"><span data-stu-id="bf3c4-116">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="bf3c4-117">也可以通过将代码粘贴到新的项目中生成此示例在 Visual Studio 中。</span><span class="sxs-lookup"><span data-stu-id="bf3c4-117">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf3c4-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="bf3c4-118">See also</span></span>

- [<span data-ttu-id="bf3c4-119">自定义 Windows 窗体 DataGridView 控件</span><span class="sxs-lookup"><span data-stu-id="bf3c4-119">Customizing the Windows Forms DataGridView Control</span></span>](customizing-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="bf3c4-120">DataGridView 控件体系结构</span><span class="sxs-lookup"><span data-stu-id="bf3c4-120">DataGridView Control Architecture</span></span>](datagridview-control-architecture-windows-forms.md)
- [<span data-ttu-id="bf3c4-121">Windows 窗体 DataGridView 控件中的列类型</span><span class="sxs-lookup"><span data-stu-id="bf3c4-121">Column Types in the Windows Forms DataGridView Control</span></span>](column-types-in-the-windows-forms-datagridview-control.md)
