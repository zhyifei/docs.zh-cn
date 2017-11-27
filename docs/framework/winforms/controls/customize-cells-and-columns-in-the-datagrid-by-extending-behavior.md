---
title: "如何：通过扩展 Windows 窗体 DataGridView 控件中单元格和列的行为和外观对其进行自定义"
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
- DataGridView control [Windows Forms], cell customization
- columns [Windows Forms], customizing in DataGridView control
- cells [Windows Forms], customizing in DataGridView control
ms.assetid: 9b7dc7b6-5ce6-4566-9949-902f74f17a81
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a65d9abbd13c811c8796c2e5f57ed5d259ef57ce
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-customize-cells-and-columns-in-the-windows-forms-datagridview-control-by-extending-their-behavior-and-appearance"></a><span data-ttu-id="da23a-102">如何：通过扩展 Windows 窗体 DataGridView 控件中单元格和列的行为和外观对其进行自定义</span><span class="sxs-lookup"><span data-stu-id="da23a-102">How to: Customize Cells and Columns in the Windows Forms DataGridView Control by Extending Their Behavior and Appearance</span></span>
<span data-ttu-id="da23a-103"><xref:System.Windows.Forms.DataGridView> 控件提供使用属性、事件和伴生类自定义其外观和行为的多种方式。</span><span class="sxs-lookup"><span data-stu-id="da23a-103">The <xref:System.Windows.Forms.DataGridView> control provides a number of ways to customize its appearance and behavior using properties, events, and companion classes.</span></span> <span data-ttu-id="da23a-104">有时，你可能对这些功能不提供的单元格有要求。</span><span class="sxs-lookup"><span data-stu-id="da23a-104">Occasionally, you may have requirements for your cells that go beyond what these features can provide.</span></span> <span data-ttu-id="da23a-105">你可以创建自己的自定义 <xref:System.Windows.Forms.DataGridViewCell> 类以提供扩展功能。</span><span class="sxs-lookup"><span data-stu-id="da23a-105">You can create your own custom <xref:System.Windows.Forms.DataGridViewCell> class to provide extended functionality.</span></span>  
  
 <span data-ttu-id="da23a-106">你可以通过从 <xref:System.Windows.Forms.DataGridViewCell> 基类或其派生类之一派生创建自定义 <xref:System.Windows.Forms.DataGridViewCell> 类。</span><span class="sxs-lookup"><span data-stu-id="da23a-106">You create a custom <xref:System.Windows.Forms.DataGridViewCell> class by deriving from the <xref:System.Windows.Forms.DataGridViewCell> base class or one of its derived classes.</span></span> <span data-ttu-id="da23a-107">尽管可以在任何类型的列中显示任何类型的单元格，但通常仍会创建一个专用于显示单元格类型的自定义 <xref:System.Windows.Forms.DataGridViewColumn> 类。</span><span class="sxs-lookup"><span data-stu-id="da23a-107">Although you can display any type of cell in any type of column, you will typically also create a custom <xref:System.Windows.Forms.DataGridViewColumn> class specialized for displaying your cell type.</span></span> <span data-ttu-id="da23a-108">列类派生自 <xref:System.Windows.Forms.DataGridViewColumn> 或其派生类之一。</span><span class="sxs-lookup"><span data-stu-id="da23a-108">Column classes derive from <xref:System.Windows.Forms.DataGridViewColumn> or one of its derived types.</span></span>  
  
 <span data-ttu-id="da23a-109">在以下代码示例中，你将创建一个名为 `DataGridViewRolloverCell` 的自定义单元格类，用于检测鼠标进入和离开单元格边界的时间。</span><span class="sxs-lookup"><span data-stu-id="da23a-109">In the following code example, you will create a custom cell class called `DataGridViewRolloverCell` that detects when the mouse enters and leaves the cell boundaries.</span></span> <span data-ttu-id="da23a-110">当鼠标位于单元格的边界内时，会绘制一个内嵌的矩形。</span><span class="sxs-lookup"><span data-stu-id="da23a-110">While the mouse is within the cell's bounds, an inset rectangle is drawn.</span></span> <span data-ttu-id="da23a-111">这个新类型派生自 <xref:System.Windows.Forms.DataGridViewTextBoxCell>，在所有其他方面均表现为其基类。</span><span class="sxs-lookup"><span data-stu-id="da23a-111">This new type derives from <xref:System.Windows.Forms.DataGridViewTextBoxCell> and behaves in all other respects as its base class.</span></span> <span data-ttu-id="da23a-112">伴生列类称为 `DataGridViewRolloverColumn`。</span><span class="sxs-lookup"><span data-stu-id="da23a-112">The companion column class is called `DataGridViewRolloverColumn`.</span></span>  
  
 <span data-ttu-id="da23a-113">若要使用这些类，可创建一个包含 <xref:System.Windows.Forms.DataGridView> 控件的窗体，向 <xref:System.Windows.Forms.DataGridView.Columns%2A> 集合添加一个或多个 `DataGridViewRolloverColumn` 对象，并用包含值的行填充该控件。</span><span class="sxs-lookup"><span data-stu-id="da23a-113">To use these classes, create a form containing a <xref:System.Windows.Forms.DataGridView> control, add one or more `DataGridViewRolloverColumn` objects to the <xref:System.Windows.Forms.DataGridView.Columns%2A> collection, and populate the control with rows containing values.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="da23a-114">如果添加空行，此示例将无法正常工作。</span><span class="sxs-lookup"><span data-stu-id="da23a-114">This example will not work correctly if you add empty rows.</span></span> <span data-ttu-id="da23a-115">例如，当你通过设置 <xref:System.Windows.Forms.DataGridView.RowCount%2A> 属性将行添加到该控件时，则会创建空行。</span><span class="sxs-lookup"><span data-stu-id="da23a-115">Empty rows are created, for example, when you add rows to the control by setting the <xref:System.Windows.Forms.DataGridView.RowCount%2A> property.</span></span> <span data-ttu-id="da23a-116">这是因为在这种情况下添加的行将被自动共享，即在你单击一个单元格之后才会实例化 `DataGridViewRolloverCell` 对象，这就导致关联的行变为非共享。</span><span class="sxs-lookup"><span data-stu-id="da23a-116">This is because the rows added in this case are automatically shared, which means that `DataGridViewRolloverCell` objects are not instantiated until you click on individual cells, thereby causing the associated rows to become unshared.</span></span>  
  
 <span data-ttu-id="da23a-117">由于这种类型的单元格自定义需要非共享行，因此其不适用于大型数据集。</span><span class="sxs-lookup"><span data-stu-id="da23a-117">Because this type of cell customization requires unshared rows, it is not appropriate for use with large data sets.</span></span> <span data-ttu-id="da23a-118">有关行共享的详细信息，请参阅[缩放 Windows 窗体 DataGridView 控件的最佳做法](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md)。</span><span class="sxs-lookup"><span data-stu-id="da23a-118">For more information about row sharing, see [Best Practices for Scaling the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="da23a-119">当从 <xref:System.Windows.Forms.DataGridViewCell> 或 <xref:System.Windows.Forms.DataGridViewColumn> 进行派生并将新属性添加到派生的类时，请确保重写 `Clone` 方法以在克隆操作过程中复制新属性。</span><span class="sxs-lookup"><span data-stu-id="da23a-119">When you derive from <xref:System.Windows.Forms.DataGridViewCell> or <xref:System.Windows.Forms.DataGridViewColumn> and add new properties to the derived class, be sure to override the `Clone` method to copy the new properties during cloning operations.</span></span> <span data-ttu-id="da23a-120">还应调用基类的 `Clone` 方法，以便将基类的属性复制到新的单元格或列。</span><span class="sxs-lookup"><span data-stu-id="da23a-120">You should also call the base class's `Clone` method so that the properties of the base class are copied to the new cell or column.</span></span>  
  
### <a name="to-customize-cells-and-columns-in-the-datagridview-control"></a><span data-ttu-id="da23a-121">自定义 DataGridView 控件中的单元格和列</span><span class="sxs-lookup"><span data-stu-id="da23a-121">To customize cells and columns in the DataGridView control</span></span>  
  
1.  <span data-ttu-id="da23a-122">从 <xref:System.Windows.Forms.DataGridViewTextBoxCell> 类型派生一个名为 `DataGridViewRolloverCell` 的新单元格类。</span><span class="sxs-lookup"><span data-stu-id="da23a-122">Derive a new cell class, called `DataGridViewRolloverCell`, from the <xref:System.Windows.Forms.DataGridViewTextBoxCell> type.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewRolloverCell#201](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewRolloverCell/CS/rollovercell.cs#201)]
     [!code-vb[System.Windows.Forms.DataGridViewRolloverCell#201](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewRolloverCell/VB/rollovercell.vb#201)]  
    [!code-csharp[System.Windows.Forms.DataGridViewRolloverCell#202](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewRolloverCell/CS/rollovercell.cs#202)]
    [!code-vb[System.Windows.Forms.DataGridViewRolloverCell#202](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewRolloverCell/VB/rollovercell.vb#202)]  
  
2.  <span data-ttu-id="da23a-123">重写 <xref:System.Windows.Forms.DataGridViewTextBoxCell.Paint%2A> 类中的 `DataGridViewRolloverCell` 方法。</span><span class="sxs-lookup"><span data-stu-id="da23a-123">Override the <xref:System.Windows.Forms.DataGridViewTextBoxCell.Paint%2A> method in the `DataGridViewRolloverCell` class.</span></span> <span data-ttu-id="da23a-124">在重写时，首先调用基类实现，基类实现处理托管文本框的功能。</span><span class="sxs-lookup"><span data-stu-id="da23a-124">In the override, first call the base class implementation, which handles the hosted text box functionality.</span></span> <span data-ttu-id="da23a-125">然后使用控件的 <xref:System.Windows.Forms.Control.PointToClient%2A> 方法，将光标位置（在屏幕坐标中）转换为 <xref:System.Windows.Forms.DataGridView> 客户端区域的坐标。</span><span class="sxs-lookup"><span data-stu-id="da23a-125">Then use the control's <xref:System.Windows.Forms.Control.PointToClient%2A> method to transform the cursor position (in screen coordinates) to the <xref:System.Windows.Forms.DataGridView> client area's coordinates.</span></span> <span data-ttu-id="da23a-126">如果鼠标坐标位于单元格的边界之内，则绘制内嵌矩形。</span><span class="sxs-lookup"><span data-stu-id="da23a-126">If the mouse coordinates fall within the bounds of the cell, draw the inset rectangle.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewRolloverCell#210](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewRolloverCell/CS/rollovercell.cs#210)]
     [!code-vb[System.Windows.Forms.DataGridViewRolloverCell#210](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewRolloverCell/VB/rollovercell.vb#210)]  
  
3.  <span data-ttu-id="da23a-127">重写 `DataGridViewRolloverCell` 类中的 <xref:System.Windows.Forms.DataGridViewCell.OnMouseEnter%2A> 和 <xref:System.Windows.Forms.DataGridViewCell.OnMouseLeave%2A> 方法，以强制单元格在鼠标指针进入或离开它们时重新绘制自己。</span><span class="sxs-lookup"><span data-stu-id="da23a-127">Override the <xref:System.Windows.Forms.DataGridViewCell.OnMouseEnter%2A> and <xref:System.Windows.Forms.DataGridViewCell.OnMouseLeave%2A> methods in the `DataGridViewRolloverCell` class to force cells to repaint themselves when the mouse pointer enters or leaves them.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewRolloverCell#220](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewRolloverCell/CS/rollovercell.cs#220)]
     [!code-vb[System.Windows.Forms.DataGridViewRolloverCell#220](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewRolloverCell/VB/rollovercell.vb#220)]  
  
4.  <span data-ttu-id="da23a-128">从 <xref:System.Windows.Forms.DataGridViewColumn> 类型派生一个名为 `DataGridViewRolloverCellColumn` 的新类。</span><span class="sxs-lookup"><span data-stu-id="da23a-128">Derive a new class, called `DataGridViewRolloverCellColumn`, from the <xref:System.Windows.Forms.DataGridViewColumn> type.</span></span> <span data-ttu-id="da23a-129">在构造函数中，向其 <xref:System.Windows.Forms.DataGridViewColumn.CellTemplate%2A> 属性分配一个新的 `DataGridViewRolloverCell` 对象。</span><span class="sxs-lookup"><span data-stu-id="da23a-129">In the constructor, assign a new `DataGridViewRolloverCell` object to its <xref:System.Windows.Forms.DataGridViewColumn.CellTemplate%2A> property.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewRolloverCell#300](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewRolloverCell/CS/rollovercell.cs#300)]
     [!code-vb[System.Windows.Forms.DataGridViewRolloverCell#300](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewRolloverCell/VB/rollovercell.vb#300)]  
  
## <a name="example"></a><span data-ttu-id="da23a-130">示例</span><span class="sxs-lookup"><span data-stu-id="da23a-130">Example</span></span>  
 <span data-ttu-id="da23a-131">完整的代码示例包含一个小型测试窗体，用于演示自定义单元格类型的行为。</span><span class="sxs-lookup"><span data-stu-id="da23a-131">The complete code example includes a small test form that demonstrates the behavior of the custom cell type.</span></span>  
  
 [!code-csharp[System.Windows.Forms.DataGridViewRolloverCell#000](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewRolloverCell/CS/rollovercell.cs#000)]
 [!code-vb[System.Windows.Forms.DataGridViewRolloverCell#000](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewRolloverCell/VB/rollovercell.vb#000)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="da23a-132">编译代码</span><span class="sxs-lookup"><span data-stu-id="da23a-132">Compiling the Code</span></span>  
 <span data-ttu-id="da23a-133">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="da23a-133">This example requires:</span></span>  
  
-   <span data-ttu-id="da23a-134">对 System、System.Windows.Forms 和 System.Drawing 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="da23a-134">References to the System, System.Windows.Forms, and System.Drawing assemblies.</span></span>  
  
 <span data-ttu-id="da23a-135">有关从 [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] 或 [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] 的命令行生成此示例的信息，请参阅[从命令行生成](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md)或[在命令行上使用 csc.exe 生成](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)。</span><span class="sxs-lookup"><span data-stu-id="da23a-135">For information about building this example from the command line for [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] or [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="da23a-136">还可以通过将代码粘贴到新项目，在 [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] 中生成此示例。</span><span class="sxs-lookup"><span data-stu-id="da23a-136">You can also build this example in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] by pasting the code into a new project.</span></span>  <span data-ttu-id="da23a-137">另请参阅[如何：使用 Visual Studio 编译和运行完整的 Windows 窗体代码示例](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\))。</span><span class="sxs-lookup"><span data-stu-id="da23a-137">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da23a-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="da23a-138">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridViewCell>  
 <xref:System.Windows.Forms.DataGridViewColumn>  
 [<span data-ttu-id="da23a-139">自定义 Windows 窗体 DataGridView 控件</span><span class="sxs-lookup"><span data-stu-id="da23a-139">Customizing the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/customizing-the-windows-forms-datagridview-control.md)  
 [<span data-ttu-id="da23a-140">DataGridView 控件体系结构</span><span class="sxs-lookup"><span data-stu-id="da23a-140">DataGridView Control Architecture</span></span>](../../../../docs/framework/winforms/controls/datagridview-control-architecture-windows-forms.md)  
 [<span data-ttu-id="da23a-141">Windows 窗体 DataGridView 控件中的列类型</span><span class="sxs-lookup"><span data-stu-id="da23a-141">Column Types in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/column-types-in-the-windows-forms-datagridview-control.md)  
 [<span data-ttu-id="da23a-142">有关缩放 Windows 窗体 DataGridView 控件的最佳做法</span><span class="sxs-lookup"><span data-stu-id="da23a-142">Best Practices for Scaling the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md)
