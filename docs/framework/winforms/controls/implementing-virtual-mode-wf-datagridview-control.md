---
title: 演练：在 Windows 窗体 DataGridView 控件中实现虚拟模式
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- data [Windows Forms], managing large data sets
- DataGridView control [Windows Forms], virtual mode
- virtual mode [Windows Forms], walkthroughs
- DataGridView control [Windows Forms], large data sets
- walkthroughs [Windows Forms], DataGridView control
ms.assetid: 74eb5276-5ab8-4ce0-8005-dae751d85f7c
ms.openlocfilehash: 7f6bf1703a6536f4d22b3a2fbe412579c59d39dd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61973766"
---
# <a name="walkthrough-implementing-virtual-mode-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="459f8-102">演练：在 Windows 窗体 DataGridView 控件中实现虚拟模式</span><span class="sxs-lookup"><span data-stu-id="459f8-102">Walkthrough: Implementing Virtual Mode in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="459f8-103">如果想要显示非常大量的表格数据<xref:System.Windows.Forms.DataGridView>控件，可以设置<xref:System.Windows.Forms.DataGridView.VirtualMode%2A>属性设置为`true`和显式管理其数据存储区与控件的交互。</span><span class="sxs-lookup"><span data-stu-id="459f8-103">When you want to display very large quantities of tabular data in a <xref:System.Windows.Forms.DataGridView> control, you can set the <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> property to `true` and explicitly manage the control's interaction with its data store.</span></span> <span data-ttu-id="459f8-104">这样可以微调控件在此情况下的性能。</span><span class="sxs-lookup"><span data-stu-id="459f8-104">This lets you fine-tune the performance of the control in this situation.</span></span>  
  
 <span data-ttu-id="459f8-105"><xref:System.Windows.Forms.DataGridView>控件提供了可以处理与自定义数据存储进行交互的多个事件。</span><span class="sxs-lookup"><span data-stu-id="459f8-105">The <xref:System.Windows.Forms.DataGridView> control provides several events that you can handle to interact with a custom data store.</span></span> <span data-ttu-id="459f8-106">本演练将指导您完成实现这些事件处理程序的过程。</span><span class="sxs-lookup"><span data-stu-id="459f8-106">This walkthrough guides you through the process of implementing these event handlers.</span></span> <span data-ttu-id="459f8-107">本主题中的代码示例用于说明目的使用非常简单的数据源。</span><span class="sxs-lookup"><span data-stu-id="459f8-107">The code example in this topic uses a very simple data source for illustration purposes.</span></span> <span data-ttu-id="459f8-108">在生产设置中，通常将加载只有需要到缓存中，显示和处理的行<xref:System.Windows.Forms.DataGridView>事件进行交互并更新缓存。</span><span class="sxs-lookup"><span data-stu-id="459f8-108">In a production setting, you will typically load only the rows you need to display into a cache, and handle <xref:System.Windows.Forms.DataGridView> events to interact with and update the cache.</span></span> <span data-ttu-id="459f8-109">有关详细信息，请参阅[实时数据加载 Windows 窗体 DataGridView 控件中实现虚拟模式](implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)</span><span class="sxs-lookup"><span data-stu-id="459f8-109">For more information, see [Implementing Virtual Mode with Just-In-Time Data Loading in the Windows Forms DataGridView Control](implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)</span></span>  
  
 <span data-ttu-id="459f8-110">要将本主题中的代码作为单个列表进行复制，请参阅[如何：Windows 中的实现虚拟模式窗体 DataGridView 控件](how-to-implement-virtual-mode-in-the-windows-forms-datagridview-control.md)。</span><span class="sxs-lookup"><span data-stu-id="459f8-110">To copy the code in this topic as a single listing, see [How to: Implement Virtual Mode in the Windows Forms DataGridView Control](how-to-implement-virtual-mode-in-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="creating-the-form"></a><span data-ttu-id="459f8-111">创建窗体</span><span class="sxs-lookup"><span data-stu-id="459f8-111">Creating the Form</span></span>  
  
#### <a name="to-implement-virtual-mode"></a><span data-ttu-id="459f8-112">若要实现虚拟模式</span><span class="sxs-lookup"><span data-stu-id="459f8-112">To implement virtual mode</span></span>  
  
1. <span data-ttu-id="459f8-113">创建派生的类<xref:System.Windows.Forms.Form>和包含<xref:System.Windows.Forms.DataGridView>控件。</span><span class="sxs-lookup"><span data-stu-id="459f8-113">Create a class that derives from <xref:System.Windows.Forms.Form> and contains a <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
     <span data-ttu-id="459f8-114">下面的代码包含一些基本的初始化。</span><span class="sxs-lookup"><span data-stu-id="459f8-114">The following code contains some basic initialization.</span></span> <span data-ttu-id="459f8-115">它声明一些将在后续步骤中使用的变量，提供`Main`方法，并提供了类构造函数中的简单窗体布局。</span><span class="sxs-lookup"><span data-stu-id="459f8-115">It declares some variables that will be used in later steps, provides a `Main` method, and provides a simple form layout in the class constructor.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#001](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#001)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#001](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#001)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#001](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#001)]  
    [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#002](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#002)]
    [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#002](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#002)]
    [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#002](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#002)]  
  
2. <span data-ttu-id="459f8-116">实现窗体的一个处理程序<xref:System.Windows.Forms.Form.Load>初始化的事件<xref:System.Windows.Forms.DataGridView>控制，并填充具有示例值的数据存储区。</span><span class="sxs-lookup"><span data-stu-id="459f8-116">Implement a handler for your form's <xref:System.Windows.Forms.Form.Load> event that initializes the <xref:System.Windows.Forms.DataGridView> control and populates the data store with sample values.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#110](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#110)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#110](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#110)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#110](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#110)]  
  
3. <span data-ttu-id="459f8-117">实现的处理程序<xref:System.Windows.Forms.DataGridView.CellValueNeeded>从数据存储中检索请求的单元格的值的事件或`Customer`当前正在编辑的对象。</span><span class="sxs-lookup"><span data-stu-id="459f8-117">Implement a handler for the <xref:System.Windows.Forms.DataGridView.CellValueNeeded> event that retrieves the requested cell value from the data store or the `Customer` object currently in edit.</span></span>  
  
     <span data-ttu-id="459f8-118">每当发生此事件<xref:System.Windows.Forms.DataGridView>控件需要绘制单元格。</span><span class="sxs-lookup"><span data-stu-id="459f8-118">This event occurs whenever the <xref:System.Windows.Forms.DataGridView> control needs to paint a cell.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#120](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#120)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#120](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#120)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#120](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#120)]  
  
4. <span data-ttu-id="459f8-119">实现的处理程序<xref:System.Windows.Forms.DataGridView.CellValuePushed>编辑的单元格将值存储在事件`Customer`对象，表示编辑过的行。</span><span class="sxs-lookup"><span data-stu-id="459f8-119">Implement a handler for the <xref:System.Windows.Forms.DataGridView.CellValuePushed> event that stores an edited cell value in the `Customer` object representing the edited row.</span></span> <span data-ttu-id="459f8-120">每当用户提交一个单元格的值更改时，将发生此事件。</span><span class="sxs-lookup"><span data-stu-id="459f8-120">This event occurs whenever the user commits a cell value change.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#130](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#130)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#130](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#130)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#130](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#130)]  
  
5. <span data-ttu-id="459f8-121">实现的处理程序<xref:System.Windows.Forms.DataGridView.NewRowNeeded>创建一个新的事件`Customer`对象，表示新创建的行。</span><span class="sxs-lookup"><span data-stu-id="459f8-121">Implement a handler for the <xref:System.Windows.Forms.DataGridView.NewRowNeeded> event that creates a new `Customer` object representing a newly created row.</span></span>  
  
     <span data-ttu-id="459f8-122">每当用户输入新记录的行，将发生此事件。</span><span class="sxs-lookup"><span data-stu-id="459f8-122">This event occurs whenever the user enters the row for new records.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#140](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#140)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#140](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#140)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#140](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#140)]  
  
6. <span data-ttu-id="459f8-123">实现的处理程序<xref:System.Windows.Forms.DataGridView.RowValidated>将新的或已修改行保存到数据存储的事件。</span><span class="sxs-lookup"><span data-stu-id="459f8-123">Implement a handler for the <xref:System.Windows.Forms.DataGridView.RowValidated> event that saves new or modified rows to the data store.</span></span>  
  
     <span data-ttu-id="459f8-124">每当用户更改当前行时，将发生此事件。</span><span class="sxs-lookup"><span data-stu-id="459f8-124">This event occurs whenever the user changes the current row.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#150](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#150)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#150](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#150)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#150](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#150)]  
  
7. <span data-ttu-id="459f8-125">实现的处理程序<xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded>事件，该值指示是否<xref:System.Windows.Forms.DataGridView.CancelRowEdit>用户两次在编辑模式下或在非编辑模式，按 esc 键指示行恢复时，事件将会发生。</span><span class="sxs-lookup"><span data-stu-id="459f8-125">Implement a handler for the <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded> event that indicates whether the <xref:System.Windows.Forms.DataGridView.CancelRowEdit> event will occur when the user signals row reversion by pressing ESC twice in edit mode or once outside of edit mode.</span></span>  
  
     <span data-ttu-id="459f8-126">默认情况下<xref:System.Windows.Forms.DataGridView.CancelRowEdit>在恢复行的当前行中的任何单元格已被修改，除非时发生<xref:System.Windows.Forms.QuestionEventArgs.Response%2A?displayProperty=nameWithType>属性设置为`true`中<xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded>事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="459f8-126">By default, <xref:System.Windows.Forms.DataGridView.CancelRowEdit> occurs upon row reversion when any cells in the current row have been modified unless the <xref:System.Windows.Forms.QuestionEventArgs.Response%2A?displayProperty=nameWithType> property is set to `true` in the <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded> event handler.</span></span> <span data-ttu-id="459f8-127">在运行时确定提交作用域时，此事件非常有用。</span><span class="sxs-lookup"><span data-stu-id="459f8-127">This event is useful when the commit scope is determined at run time.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#160](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#160)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#160](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#160)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#160](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#160)]  
  
8. <span data-ttu-id="459f8-128">实现的处理程序<xref:System.Windows.Forms.DataGridView.CancelRowEdit>放弃的值的事件`Customer`对象，表示当前行。</span><span class="sxs-lookup"><span data-stu-id="459f8-128">Implement a handler for the <xref:System.Windows.Forms.DataGridView.CancelRowEdit> event that discards the values of the `Customer` object representing the current row.</span></span>  
  
     <span data-ttu-id="459f8-129">当用户在编辑模式中两次或一次非编辑模式，按 esc 键指示行恢复时，将发生此事件。</span><span class="sxs-lookup"><span data-stu-id="459f8-129">This event occurs when the user signals row reversion by pressing ESC twice in edit mode or once outside of edit mode.</span></span> <span data-ttu-id="459f8-130">如果没有当前行中的单元格已被修改，或如果不会发生此事件的值<xref:System.Windows.Forms.QuestionEventArgs.Response%2A?displayProperty=nameWithType>属性已设置为`false`中<xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded>事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="459f8-130">This event does not occur if no cells in the current row have been modified or if the value of the <xref:System.Windows.Forms.QuestionEventArgs.Response%2A?displayProperty=nameWithType> property has been set to `false` in a <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded> event handler.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#170](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#170)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#170](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#170)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#170](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#170)]  
  
9. <span data-ttu-id="459f8-131">实现的处理程序<xref:System.Windows.Forms.DataGridView.UserDeletingRow>删除现有的事件`Customer`数据存储区中的对象或放弃未保存`Customer`对象，表示新创建的行。</span><span class="sxs-lookup"><span data-stu-id="459f8-131">Implement a handler for the <xref:System.Windows.Forms.DataGridView.UserDeletingRow> event that deletes an existing `Customer` object from the data store or discards an unsaved `Customer` object representing a newly created row.</span></span>  
  
     <span data-ttu-id="459f8-132">每当用户通过单击行标题并按 DELETE 键删除行时，将发生此事件。</span><span class="sxs-lookup"><span data-stu-id="459f8-132">This event occurs whenever the user deletes a row by clicking a row header and pressing the DELETE key.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#180](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#180)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#180](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#180)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#180](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#180)]  
  
10. <span data-ttu-id="459f8-133">实现一个简单`Customers`类来表示此代码示例使用的数据项目。</span><span class="sxs-lookup"><span data-stu-id="459f8-133">Implement a simple `Customers` class to represent the data items used by this code example.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#200](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#200)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#200](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#200)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#200](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#200)]  
  
## <a name="testing-the-application"></a><span data-ttu-id="459f8-134">测试应用程序</span><span class="sxs-lookup"><span data-stu-id="459f8-134">Testing the Application</span></span>  
 <span data-ttu-id="459f8-135">现在可以测试窗体，以确保其行为符合预期。</span><span class="sxs-lookup"><span data-stu-id="459f8-135">You can now test the form to make sure it behaves as expected.</span></span>  
  
#### <a name="to-test-the-form"></a><span data-ttu-id="459f8-136">若要测试窗体</span><span class="sxs-lookup"><span data-stu-id="459f8-136">To test the form</span></span>  
  
- <span data-ttu-id="459f8-137">编译并运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="459f8-137">Compile and run the application.</span></span>  
  
     <span data-ttu-id="459f8-138">你将看到<xref:System.Windows.Forms.DataGridView>控件填充三个客户记录。</span><span class="sxs-lookup"><span data-stu-id="459f8-138">You will see a <xref:System.Windows.Forms.DataGridView> control populated with three customer records.</span></span> <span data-ttu-id="459f8-139">可以修改行中的多个单元格的值，并在编辑模式中两次，一次非编辑模式，若要还原到其原始值的整行，请按 esc 键。</span><span class="sxs-lookup"><span data-stu-id="459f8-139">You can modify the values of multiple cells in a row and press ESC twice in edit mode and once outside of edit mode to revert the entire row to its original values.</span></span> <span data-ttu-id="459f8-140">当你修改、 添加或删除控件中的行时`Customer`修改、 添加或删除数据存储中的对象。</span><span class="sxs-lookup"><span data-stu-id="459f8-140">When you modify, add, or delete rows in the control, `Customer` objects in the data store are modified, added, or deleted as well.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="459f8-141">后续步骤</span><span class="sxs-lookup"><span data-stu-id="459f8-141">Next Steps</span></span>  
 <span data-ttu-id="459f8-142">此应用程序为您提供了必须处理实现中的虚拟模式的事件的一个基本的了解<xref:System.Windows.Forms.DataGridView>控件。</span><span class="sxs-lookup"><span data-stu-id="459f8-142">This application gives you a basic understanding of the events you must handle to implement virtual mode in the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="459f8-143">您可以提高在多方面此基本应用程序：</span><span class="sxs-lookup"><span data-stu-id="459f8-143">You can improve this basic application in a number of ways:</span></span>  
  
- <span data-ttu-id="459f8-144">实现缓存来自外部数据库的值的数据存储。</span><span class="sxs-lookup"><span data-stu-id="459f8-144">Implement a data store that caches values from an external database.</span></span> <span data-ttu-id="459f8-145">缓存应检索并放弃根据需要的值，使其仅包含必要的操作时使用少量内存客户端计算机上的显示。</span><span class="sxs-lookup"><span data-stu-id="459f8-145">The cache should retrieve and discard values as necessary so that it only contains what is necessary for display while consuming a small amount of memory on the client computer.</span></span>  
  
- <span data-ttu-id="459f8-146">对数据存储，具体取决于你的需求的性能进行微调。</span><span class="sxs-lookup"><span data-stu-id="459f8-146">Fine-tune the performance of the data store depending on your requirements.</span></span> <span data-ttu-id="459f8-147">例如，你可能想要通过使用更大的缓存大小和最大程度减少数据库查询的次数补偿慢速网络连接，而客户端计算机的内存限制。</span><span class="sxs-lookup"><span data-stu-id="459f8-147">For example, you might want to compensate for slow network connections rather than client-computer memory limitations by using a larger cache size and minimizing the number of database queries.</span></span>  
  
 <span data-ttu-id="459f8-148">有关缓存来自外部数据库的值的详细信息，请参阅[如何：实现虚拟模式在 Windows 中实时数据加载窗体 DataGridView 控件](virtual-mode-with-just-in-time-data-loading-in-the-datagrid.md)。</span><span class="sxs-lookup"><span data-stu-id="459f8-148">For more information about caching values from an external database, see [How to: Implement Virtual Mode with Just-In-Time Data Loading in the Windows Forms DataGridView Control](virtual-mode-with-just-in-time-data-loading-in-the-datagrid.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="459f8-149">请参阅</span><span class="sxs-lookup"><span data-stu-id="459f8-149">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>
- <xref:System.Windows.Forms.DataGridView.CellValueNeeded>
- <xref:System.Windows.Forms.DataGridView.CellValuePushed>
- <xref:System.Windows.Forms.DataGridView.NewRowNeeded>
- <xref:System.Windows.Forms.DataGridView.RowValidated>
- <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded>
- <xref:System.Windows.Forms.DataGridView.CancelRowEdit>
- <xref:System.Windows.Forms.DataGridView.UserDeletingRow>
- [<span data-ttu-id="459f8-150">Windows 窗体 DataGridView 控件中的性能调整</span><span class="sxs-lookup"><span data-stu-id="459f8-150">Performance Tuning in the Windows Forms DataGridView Control</span></span>](performance-tuning-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="459f8-151">有关缩放 Windows 窗体 DataGridView 控件的最佳做法</span><span class="sxs-lookup"><span data-stu-id="459f8-151">Best Practices for Scaling the Windows Forms DataGridView Control</span></span>](best-practices-for-scaling-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="459f8-152">在 Windows 窗体 DataGridView 控件中实现实时数据加载的虚拟模式</span><span class="sxs-lookup"><span data-stu-id="459f8-152">Implementing Virtual Mode with Just-In-Time Data Loading in the Windows Forms DataGridView Control</span></span>](implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)
- [<span data-ttu-id="459f8-153">如何：在 Windows 窗体 DataGridView 控件中实现虚拟模式</span><span class="sxs-lookup"><span data-stu-id="459f8-153">How to: Implement Virtual Mode in the Windows Forms DataGridView Control</span></span>](how-to-implement-virtual-mode-in-the-windows-forms-datagridview-control.md)
