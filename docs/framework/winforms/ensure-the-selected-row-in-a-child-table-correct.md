---
title: 如何：确保子表中的选定行保持在正确的位置
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- master-details view
- row position [Windows Forms]
- parent/child view [Windows Forms]
- resetting child position
- data binding [.NET Framework], row selection
- caching [.NET Framework], child position
- child position
- master/details view [Windows Forms]
- child tables row selection
- current child position
ms.assetid: c5fa2562-43a4-46fa-a604-52d8526a87bd
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 30929c6163a279bc0ea47d1262f54ec5ff75a87c
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-ensure-the-selected-row-in-a-child-table-remains-at-the-correct-position"></a><span data-ttu-id="fb6a9-102">如何：确保子表中的选定行保持在正确的位置</span><span class="sxs-lookup"><span data-stu-id="fb6a9-102">How to: Ensure the Selected Row in a Child Table Remains at the Correct Position</span></span>
<span data-ttu-id="fb6a9-103">通常当在 Windows 窗体中使用数据绑定时，将显示称为父/子视图或母版/详细视图中的数据。</span><span class="sxs-lookup"><span data-stu-id="fb6a9-103">Oftentimes when you work with data binding in Windows Forms, you will display data in what is called a parent/child or master/details view.</span></span> <span data-ttu-id="fb6a9-104">这是指一个数据绑定方案，其中来自同一源的数据将显示在两个控件中。</span><span class="sxs-lookup"><span data-stu-id="fb6a9-104">This refers to a data-binding scenario where data from the same source is displayed in two controls.</span></span> <span data-ttu-id="fb6a9-105">更改一个控件中的选定内容会导致在第二个控件中显示的数据变动。</span><span class="sxs-lookup"><span data-stu-id="fb6a9-105">Changing the selection in one control causes the data displayed in the second control to change.</span></span> <span data-ttu-id="fb6a9-106">例如，第一个控件可能会包含一个客户列表，而第二个控件则可能包含与第一个控件中选定客户相关的订单列表。</span><span class="sxs-lookup"><span data-stu-id="fb6a9-106">For example, the first control might contain a list of customers and the second a list of orders related to the selected customer in the first control.</span></span>  
  
 <span data-ttu-id="fb6a9-107">开始使用.NET Framework 2.0 版本，当在父/子视图中显示数据时，可能需要采取额外步骤来确保子表中当前所选的行不会重置为表的第一行。</span><span class="sxs-lookup"><span data-stu-id="fb6a9-107">Starting with the .NET Framework version 2.0, when you display data in a parent/child view you might have to take extra steps to make sure that the currently selected row in the child table is not reset to the first row of the table.</span></span> <span data-ttu-id="fb6a9-108">为了执行此操作，必须缓存子表位置并在父表发生更改后将其重置。</span><span class="sxs-lookup"><span data-stu-id="fb6a9-108">In order to do this, you will have to cache the child table position and reset it after the parent table changes.</span></span> <span data-ttu-id="fb6a9-109">父表某一行中的字段第一次更改时通常会发生子表重置。</span><span class="sxs-lookup"><span data-stu-id="fb6a9-109">Typically the child reset occurs the first time a field in a row of the parent table changes.</span></span>  
  
### <a name="to-cache-the-current-child-position"></a><span data-ttu-id="fb6a9-110">若要缓存当前子表位置</span><span class="sxs-lookup"><span data-stu-id="fb6a9-110">To Cache the Current Child Position</span></span>  
  
1.  <span data-ttu-id="fb6a9-111">则声明一个整数变量，以存储子列表位置，并声明一个布尔变量，以存储是否缓存子表位置。</span><span class="sxs-lookup"><span data-stu-id="fb6a9-111">Declare an integer variable to store the child list position and a Boolean variable to store whether to cache the child position.</span></span>  
  
     [!code-csharp[System.Windows.Forms.CurrencyManagerReset#4](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.CurrencyManagerReset/CS/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.CurrencyManagerReset#4](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.CurrencyManagerReset/VB/Form1.vb#4)]  
  
2.  <span data-ttu-id="fb6a9-112">为绑定的 <xref:System.Windows.Forms.CurrencyManager> 处理 <xref:System.Windows.Forms.CurrencyManager.ListChanged> 事件并检查 <xref:System.ComponentModel.ListChangedType.Reset> 的 <xref:System.ComponentModel.ListChangedType>。</span><span class="sxs-lookup"><span data-stu-id="fb6a9-112">Handle the <xref:System.Windows.Forms.CurrencyManager.ListChanged> event for the binding's <xref:System.Windows.Forms.CurrencyManager> and check for a <xref:System.ComponentModel.ListChangedType> of <xref:System.ComponentModel.ListChangedType.Reset>.</span></span>  
  
3.  <span data-ttu-id="fb6a9-113">检查 <xref:System.Windows.Forms.CurrencyManager> 的当前位置。</span><span class="sxs-lookup"><span data-stu-id="fb6a9-113">Check the current position of the <xref:System.Windows.Forms.CurrencyManager>.</span></span> <span data-ttu-id="fb6a9-114">如果它大于列表中第一个条目（通常为 0），则将其保存到一个变量。</span><span class="sxs-lookup"><span data-stu-id="fb6a9-114">If it is greater than first entry in the list (typically 0), save it to a variable.</span></span>  
  
     [!code-csharp[System.Windows.Forms.CurrencyManagerReset#2](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.CurrencyManagerReset/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.CurrencyManagerReset#2](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.CurrencyManagerReset/VB/Form1.vb#2)]  
  
4.  <span data-ttu-id="fb6a9-115">为父货币管理器处理父列表的 <xref:System.Windows.Forms.BindingManagerBase.CurrentChanged> 事件。</span><span class="sxs-lookup"><span data-stu-id="fb6a9-115">Handle the parent list's <xref:System.Windows.Forms.BindingManagerBase.CurrentChanged> event for the parent currency manager.</span></span> <span data-ttu-id="fb6a9-116">在处理程序中，设置布尔值，以指示其不是一个缓存方案。</span><span class="sxs-lookup"><span data-stu-id="fb6a9-116">In the handler, set the Boolean value to indicate it is not a caching scenario.</span></span> <span data-ttu-id="fb6a9-117">如果发生了 <xref:System.Windows.Forms.BindingManagerBase.CurrentChanged>，则对父对象的更改是列表位置的更改，而不是项目值的更改。</span><span class="sxs-lookup"><span data-stu-id="fb6a9-117">If the <xref:System.Windows.Forms.BindingManagerBase.CurrentChanged> occurs, the change to the parent is a list position change and not an item value change.</span></span>  
  
     [!code-csharp[System.Windows.Forms.CurrencyManagerReset#5](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.CurrencyManagerReset/CS/Form1.cs#5)]
     [!code-vb[System.Windows.Forms.CurrencyManagerReset#5](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.CurrencyManagerReset/VB/Form1.vb#5)]  
  
### <a name="to-reset-the-child-position"></a><span data-ttu-id="fb6a9-118">若要重置子表位置</span><span class="sxs-lookup"><span data-stu-id="fb6a9-118">To Reset the Child Position</span></span>  
  
1.  <span data-ttu-id="fb6a9-119">为子绑定的 <xref:System.Windows.Forms.CurrencyManager>处理 <xref:System.Windows.Forms.BindingManagerBase.PositionChanged> 事件。</span><span class="sxs-lookup"><span data-stu-id="fb6a9-119">Handle the <xref:System.Windows.Forms.BindingManagerBase.PositionChanged> event for the child binding's <xref:System.Windows.Forms.CurrencyManager>.</span></span>  
  
2.  <span data-ttu-id="fb6a9-120">将子表位置重置到前述过程中保存的缓存位置。</span><span class="sxs-lookup"><span data-stu-id="fb6a9-120">Reset the child table position to the cached position saved in the previous procedure.</span></span>  
  
     [!code-csharp[System.Windows.Forms.CurrencyManagerReset#3](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.CurrencyManagerReset/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.CurrencyManagerReset#3](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.CurrencyManagerReset/VB/Form1.vb#3)]  
  
## <a name="example"></a><span data-ttu-id="fb6a9-121">示例</span><span class="sxs-lookup"><span data-stu-id="fb6a9-121">Example</span></span>  
 <span data-ttu-id="fb6a9-122">以下示例演示了如何在子表的 <xref:System.Windows.Forms.CurrencyManager> 上保存当前位置，并在父表上的编辑完成后重置该位置。</span><span class="sxs-lookup"><span data-stu-id="fb6a9-122">The following example demonstrates how to save the current position on the <xref:System.Windows.Forms.CurrencyManager>.for a child table and reset the position after an edit is completed on the parent table.</span></span> <span data-ttu-id="fb6a9-123">此示例包含通过使用 <xref:System.Windows.Forms.BindingSource> 组件绑定到 <xref:System.Data.DataSet> 中的两个表的两个 <xref:System.Windows.Forms.DataGridView> 控件。</span><span class="sxs-lookup"><span data-stu-id="fb6a9-123">This example contains two <xref:System.Windows.Forms.DataGridView> controls bound to two tables in a <xref:System.Data.DataSet> using a <xref:System.Windows.Forms.BindingSource> component.</span></span> <span data-ttu-id="fb6a9-124">两个表之间建立了关系并将此关系添加到了 <xref:System.Data.DataSet>。</span><span class="sxs-lookup"><span data-stu-id="fb6a9-124">A relation is established between the two tables and the relation is added to the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="fb6a9-125">出于演示目的，子表中的位置最初设置为第三行。</span><span class="sxs-lookup"><span data-stu-id="fb6a9-125">The position in the child table is initially set to the third row for demonstration purposes.</span></span>  
  
 [!code-csharp[System.Windows.Forms.CurrencyManagerReset#1](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.CurrencyManagerReset/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.CurrencyManagerReset#1](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.CurrencyManagerReset/VB/Form1.vb#1)]  
  
 <span data-ttu-id="fb6a9-126">若要测试代码示例，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="fb6a9-126">To test the code example, perform the following steps:</span></span>  
  
1.  <span data-ttu-id="fb6a9-127">运行示例。</span><span class="sxs-lookup"><span data-stu-id="fb6a9-127">Run the example.</span></span>  
  
2.  <span data-ttu-id="fb6a9-128">请确保“缓存并重置位置”复选框处于选中状态。</span><span class="sxs-lookup"><span data-stu-id="fb6a9-128">Make sure the **Cache and reset position** check box is selected.</span></span>  
  
3.  <span data-ttu-id="fb6a9-129">单击“清除父字段”按钮会导致父表的某个字段发生更改。</span><span class="sxs-lookup"><span data-stu-id="fb6a9-129">Click the **Clear parent field** button to cause a change in a field of the parent table.</span></span> <span data-ttu-id="fb6a9-130">请注意，子表中的所选行将不会更改。</span><span class="sxs-lookup"><span data-stu-id="fb6a9-130">Notice that the selected row in the child table does not change.</span></span>  
  
4.  <span data-ttu-id="fb6a9-131">关闭，然后再次运行该示例。</span><span class="sxs-lookup"><span data-stu-id="fb6a9-131">Close and run the example again.</span></span> <span data-ttu-id="fb6a9-132">需要这样做的原因是重置行为仅在父行中第一次更改时发生。</span><span class="sxs-lookup"><span data-stu-id="fb6a9-132">You need to do this because the reset behavior occurs only on the first change in the parent row.</span></span>  
  
5.  <span data-ttu-id="fb6a9-133">清除“缓存并重置位置”复选框。</span><span class="sxs-lookup"><span data-stu-id="fb6a9-133">Clear the **Cache and reset position** check box.</span></span>  
  
6.  <span data-ttu-id="fb6a9-134">单击“清除父字段”按钮。</span><span class="sxs-lookup"><span data-stu-id="fb6a9-134">Click the **Clear parent field** button.</span></span> <span data-ttu-id="fb6a9-135">请注意，子表中的选定的行将更改为第一行。</span><span class="sxs-lookup"><span data-stu-id="fb6a9-135">Notice that the selected row in the child table changes to the first row.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="fb6a9-136">编译代码</span><span class="sxs-lookup"><span data-stu-id="fb6a9-136">Compiling the Code</span></span>  
 <span data-ttu-id="fb6a9-137">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="fb6a9-137">This example requires:</span></span>  
  
-   <span data-ttu-id="fb6a9-138">对 System、System.Data、System.Drawing、System.Windows.Forms 和 System.Xml 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="fb6a9-138">References to the System, System.Data, System.Drawing, System.Windows.Forms, and System.XML assemblies.</span></span>  
  
 <span data-ttu-id="fb6a9-139">有关如何为 Visual Basic 或 Visual C# 中生成此示例从命令行的信息，请参阅[从命令行生成](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md)或[命令行上使用 csc.exe 生成](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)。</span><span class="sxs-lookup"><span data-stu-id="fb6a9-139">For information about how to build this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="fb6a9-140">还可以通过将代码粘贴到新项目，在 [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] 中生成此示例。</span><span class="sxs-lookup"><span data-stu-id="fb6a9-140">You can also build this example in [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] by pasting the code into a new project.</span></span>  <span data-ttu-id="fb6a9-141">另请参阅 [如何：使用 Visual Studio 编译和运行完整的 Windows 窗体代码示例](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\))。</span><span class="sxs-lookup"><span data-stu-id="fb6a9-141">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb6a9-142">请参阅</span><span class="sxs-lookup"><span data-stu-id="fb6a9-142">See Also</span></span>  
 [<span data-ttu-id="fb6a9-143">如何：确保绑定到同一数据源的多个控件保持同步</span><span class="sxs-lookup"><span data-stu-id="fb6a9-143">How to: Ensure Multiple Controls Bound to the Same Data Source Remain Synchronized</span></span>](../../../docs/framework/winforms/multiple-controls-bound-to-data-source-synchronized.md)  
 [<span data-ttu-id="fb6a9-144">BindingSource 组件</span><span class="sxs-lookup"><span data-stu-id="fb6a9-144">BindingSource Component</span></span>](../../../docs/framework/winforms/controls/bindingsource-component.md)  
 [<span data-ttu-id="fb6a9-145">数据绑定和 Windows 窗体</span><span class="sxs-lookup"><span data-stu-id="fb6a9-145">Data Binding and Windows Forms</span></span>](../../../docs/framework/winforms/data-binding-and-windows-forms.md)
