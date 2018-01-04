---
title: "如何：禁用 Windows 窗体 DataGridView 控件的按钮列中的按钮"
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
- data grids [Windows Forms], disabling buttons
- buttons [Windows Forms], disabling in button columns
- DataGridView control [Windows Forms], disabling button cells
ms.assetid: 5c344d01-013a-4a6b-8f8d-62ec9321d81e
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: fb16014003540219c789b05e4ccd7f023a98b5c0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-disable-buttons-in-a-button-column-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="8e509-102">如何：禁用 Windows 窗体 DataGridView 控件的按钮列中的按钮</span><span class="sxs-lookup"><span data-stu-id="8e509-102">How to: Disable Buttons in a Button Column in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="8e509-103"><xref:System.Windows.Forms.DataGridView> 控件包括 <xref:System.Windows.Forms.DataGridViewButtonCell> 类，其用于显示具有与按钮类似的用户界面 (UI) 的单元格。</span><span class="sxs-lookup"><span data-stu-id="8e509-103">The <xref:System.Windows.Forms.DataGridView> control includes the <xref:System.Windows.Forms.DataGridViewButtonCell> class for displaying cells with a user interface (UI) like a button.</span></span> <span data-ttu-id="8e509-104">但是，<xref:System.Windows.Forms.DataGridViewButtonCell> 不提供禁用单元格所显示按钮外观的方法。</span><span class="sxs-lookup"><span data-stu-id="8e509-104">However, <xref:System.Windows.Forms.DataGridViewButtonCell> does not provide a way to disable the appearance of the button displayed by the cell.</span></span>  
  
 <span data-ttu-id="8e509-105">以下代码示例演示如何自定义 <xref:System.Windows.Forms.DataGridViewButtonCell> 类以显示可以显示为禁用的按钮。</span><span class="sxs-lookup"><span data-stu-id="8e509-105">The following code example demonstrates how to customize the <xref:System.Windows.Forms.DataGridViewButtonCell> class to display buttons that can appear disabled.</span></span> <span data-ttu-id="8e509-106">此示例定义了一个新的单元格类型，即从 <xref:System.Windows.Forms.DataGridViewButtonCell> 派生的 `DataGridViewDisableButtonCell`。</span><span class="sxs-lookup"><span data-stu-id="8e509-106">The example defines a new cell type, `DataGridViewDisableButtonCell`, that derives from <xref:System.Windows.Forms.DataGridViewButtonCell>.</span></span> <span data-ttu-id="8e509-107">此单元格类型提供了一种新 `Enabled` 属性，可设置为 `false` 以拖动单元格中已禁用的按钮。</span><span class="sxs-lookup"><span data-stu-id="8e509-107">This cell type provides a new `Enabled` property that can be set to `false` to draw a disabled button in the cell.</span></span> <span data-ttu-id="8e509-108">此示例还定义了一个新的列类型，即显示 `DataGridViewDisableButtonCell` 对象的 `DataGridViewDisableButtonColumn`。</span><span class="sxs-lookup"><span data-stu-id="8e509-108">The example also defines a new column type, `DataGridViewDisableButtonColumn`, that displays `DataGridViewDisableButtonCell` objects.</span></span> <span data-ttu-id="8e509-109">为了演示此新单元格和列类型，父级 <xref:System.Windows.Forms.DataGridView> 中的每个 <xref:System.Windows.Forms.DataGridViewCheckBoxCell> 的当前值确定了相同行中 `DataGridViewDisableButtonCell` 的 `Enabled` 属性是否是 `true` 或 `false`。</span><span class="sxs-lookup"><span data-stu-id="8e509-109">To demonstrate this new cell and column type, the current value of each <xref:System.Windows.Forms.DataGridViewCheckBoxCell> in the parent <xref:System.Windows.Forms.DataGridView> determines whether the `Enabled` property of the `DataGridViewDisableButtonCell` in the same row is `true` or `false`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8e509-110">当从 <xref:System.Windows.Forms.DataGridViewCell> 或 <xref:System.Windows.Forms.DataGridViewColumn> 进行派生并将新属性添加到派生的类时，请确保重写 `Clone` 方法以在克隆操作过程中复制新属性。</span><span class="sxs-lookup"><span data-stu-id="8e509-110">When you derive from <xref:System.Windows.Forms.DataGridViewCell> or <xref:System.Windows.Forms.DataGridViewColumn> and add new properties to the derived class, be sure to override the `Clone` method to copy the new properties during cloning operations.</span></span> <span data-ttu-id="8e509-111">还应调用基类的 `Clone` 方法，以便将基类的属性复制到新的单元格或列。</span><span class="sxs-lookup"><span data-stu-id="8e509-111">You should also call the base class's `Clone` method so that the properties of the base class are copied to the new cell or column.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8e509-112">示例</span><span class="sxs-lookup"><span data-stu-id="8e509-112">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridView.DisabledButtons#0](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DisabledButtons/CS/form1.cs#0)]
 [!code-vb[System.Windows.Forms.DataGridView.DisabledButtons#0](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DisabledButtons/VB/form1.vb#0)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="8e509-113">编译代码</span><span class="sxs-lookup"><span data-stu-id="8e509-113">Compiling the Code</span></span>  
 <span data-ttu-id="8e509-114">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="8e509-114">This example requires:</span></span>  
  
-   <span data-ttu-id="8e509-115">对 the System、System.Drawing、System.Windows.Forms 和 System.Windows.Forms.VisualStyles 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="8e509-115">References to the System, System.Drawing, System.Windows.Forms and System.Windows.Forms.VisualStyles assemblies.</span></span>  
  
 <span data-ttu-id="8e509-116">有关从 [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] 或 [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] 的命令行生成此示例的信息，请参阅[从命令行生成](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md)或[在命令行上使用 csc.exe 生成](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)。</span><span class="sxs-lookup"><span data-stu-id="8e509-116">For information about building this example from the command line for [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] or [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="8e509-117">还可以通过将代码粘贴到新项目，在 [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] 中生成此示例。</span><span class="sxs-lookup"><span data-stu-id="8e509-117">You can also build this example in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] by pasting the code into a new project.</span></span>  <span data-ttu-id="8e509-118">另请参阅 [如何：使用 Visual Studio 编译和运行完整的 Windows 窗体代码示例](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\))。</span><span class="sxs-lookup"><span data-stu-id="8e509-118">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e509-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="8e509-119">See Also</span></span>  
 [<span data-ttu-id="8e509-120">自定义 Windows 窗体 DataGridView 控件</span><span class="sxs-lookup"><span data-stu-id="8e509-120">Customizing the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/customizing-the-windows-forms-datagridview-control.md)  
 [<span data-ttu-id="8e509-121">DataGridView 控件体系结构</span><span class="sxs-lookup"><span data-stu-id="8e509-121">DataGridView Control Architecture</span></span>](../../../../docs/framework/winforms/controls/datagridview-control-architecture-windows-forms.md)  
 [<span data-ttu-id="8e509-122">Windows 窗体 DataGridView 控件中的列类型</span><span class="sxs-lookup"><span data-stu-id="8e509-122">Column Types in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/column-types-in-the-windows-forms-datagridview-control.md)
