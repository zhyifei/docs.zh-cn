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
ms.openlocfilehash: 52e93ebe0b2903fdf2fe97f4ce812331e740f8b0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33539914"
---
# <a name="walkthrough-implementing-virtual-mode-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="96523-102">演练：在 Windows 窗体 DataGridView 控件中实现虚拟模式</span><span class="sxs-lookup"><span data-stu-id="96523-102">Walkthrough: Implementing Virtual Mode in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="96523-103">如果想要显示非常大量的表格数据<xref:System.Windows.Forms.DataGridView>控件，则可设置<xref:System.Windows.Forms.DataGridView.VirtualMode%2A>属性`true`和显式管理与其数据存储区的控件的交互。</span><span class="sxs-lookup"><span data-stu-id="96523-103">When you want to display very large quantities of tabular data in a <xref:System.Windows.Forms.DataGridView> control, you can set the <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> property to `true` and explicitly manage the control's interaction with its data store.</span></span> <span data-ttu-id="96523-104">这样可以微调控件在此情况下的性能。</span><span class="sxs-lookup"><span data-stu-id="96523-104">This lets you fine-tune the performance of the control in this situation.</span></span>  
  
 <span data-ttu-id="96523-105"><xref:System.Windows.Forms.DataGridView>控件提供可以处理与自定义数据存储区交互的几个事件。</span><span class="sxs-lookup"><span data-stu-id="96523-105">The <xref:System.Windows.Forms.DataGridView> control provides several events that you can handle to interact with a custom data store.</span></span> <span data-ttu-id="96523-106">本演练将指导你完成实现这些事件处理程序的过程。</span><span class="sxs-lookup"><span data-stu-id="96523-106">This walkthrough guides you through the process of implementing these event handlers.</span></span> <span data-ttu-id="96523-107">本主题中的代码示例用于说明目的使用非常简单的数据源。</span><span class="sxs-lookup"><span data-stu-id="96523-107">The code example in this topic uses a very simple data source for illustration purposes.</span></span> <span data-ttu-id="96523-108">在生产设置中，你通常将加载只有需要到缓存中，显示和处理的行<xref:System.Windows.Forms.DataGridView>事件交互并进行更新缓存。</span><span class="sxs-lookup"><span data-stu-id="96523-108">In a production setting, you will typically load only the rows you need to display into a cache, and handle <xref:System.Windows.Forms.DataGridView> events to interact with and update the cache.</span></span> <span data-ttu-id="96523-109">有关详细信息，请参阅[实时数据加载在 Windows 窗体 DataGridView 控件中实现虚拟模式](../../../../docs/framework/winforms/controls/implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)</span><span class="sxs-lookup"><span data-stu-id="96523-109">For more information, see [Implementing Virtual Mode with Just-In-Time Data Loading in the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)</span></span>  
  
 <span data-ttu-id="96523-110">若要将代码复制本主题中的一个单独的清单，请参阅[如何： 在 Windows 窗体 DataGridView 控件中实现虚拟模式](../../../../docs/framework/winforms/controls/how-to-implement-virtual-mode-in-the-windows-forms-datagridview-control.md)。</span><span class="sxs-lookup"><span data-stu-id="96523-110">To copy the code in this topic as a single listing, see [How to: Implement Virtual Mode in the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/how-to-implement-virtual-mode-in-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="creating-the-form"></a><span data-ttu-id="96523-111">创建窗体</span><span class="sxs-lookup"><span data-stu-id="96523-111">Creating the Form</span></span>  
  
#### <a name="to-implement-virtual-mode"></a><span data-ttu-id="96523-112">若要实现虚拟模式</span><span class="sxs-lookup"><span data-stu-id="96523-112">To implement virtual mode</span></span>  
  
1.  <span data-ttu-id="96523-113">创建一个类，派生自<xref:System.Windows.Forms.Form>和包含<xref:System.Windows.Forms.DataGridView>控件。</span><span class="sxs-lookup"><span data-stu-id="96523-113">Create a class that derives from <xref:System.Windows.Forms.Form> and contains a <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
     <span data-ttu-id="96523-114">下面的代码包含一些基本的初始化。</span><span class="sxs-lookup"><span data-stu-id="96523-114">The following code contains some basic initialization.</span></span> <span data-ttu-id="96523-115">它声明将在后续步骤中使用某些变量，提供`Main`方法，并提供在类构造函数的简单窗体布局。</span><span class="sxs-lookup"><span data-stu-id="96523-115">It declares some variables that will be used in later steps, provides a `Main` method, and provides a simple form layout in the class constructor.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#001](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#001)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#001](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#001)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#001](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#001)]  
    [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#002](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#002)]
    [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#002](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#002)]
    [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#002](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#002)]  
  
2.  <span data-ttu-id="96523-116">实现你的窗体的处理<xref:System.Windows.Forms.Form.Load>初始化的事件<xref:System.Windows.Forms.DataGridView>控件并填充具有示例值的数据存储区。</span><span class="sxs-lookup"><span data-stu-id="96523-116">Implement a handler for your form's <xref:System.Windows.Forms.Form.Load> event that initializes the <xref:System.Windows.Forms.DataGridView> control and populates the data store with sample values.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#110](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#110)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#110](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#110)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#110](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#110)]  
  
3.  <span data-ttu-id="96523-117">实现的处理程序<xref:System.Windows.Forms.DataGridView.CellValueNeeded>从数据存储中检索请求的单元格的值的事件或`Customer`当前正在编辑的对象。</span><span class="sxs-lookup"><span data-stu-id="96523-117">Implement a handler for the <xref:System.Windows.Forms.DataGridView.CellValueNeeded> event that retrieves the requested cell value from the data store or the `Customer` object currently in edit.</span></span>  
  
     <span data-ttu-id="96523-118">每当发生此事件<xref:System.Windows.Forms.DataGridView>控件需要绘制单元格。</span><span class="sxs-lookup"><span data-stu-id="96523-118">This event occurs whenever the <xref:System.Windows.Forms.DataGridView> control needs to paint a cell.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#120](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#120)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#120](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#120)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#120](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#120)]  
  
4.  <span data-ttu-id="96523-119">实现的处理程序<xref:System.Windows.Forms.DataGridView.CellValuePushed>存储中的编辑后的单元值的事件`Customer`表示编辑过的行的对象。</span><span class="sxs-lookup"><span data-stu-id="96523-119">Implement a handler for the <xref:System.Windows.Forms.DataGridView.CellValuePushed> event that stores an edited cell value in the `Customer` object representing the edited row.</span></span> <span data-ttu-id="96523-120">每当用户提交单元格值更改，将发生此事件。</span><span class="sxs-lookup"><span data-stu-id="96523-120">This event occurs whenever the user commits a cell value change.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#130](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#130)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#130](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#130)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#130](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#130)]  
  
5.  <span data-ttu-id="96523-121">实现的处理程序<xref:System.Windows.Forms.DataGridView.NewRowNeeded>创建一个新的事件`Customer`表示新创建的行的对象。</span><span class="sxs-lookup"><span data-stu-id="96523-121">Implement a handler for the <xref:System.Windows.Forms.DataGridView.NewRowNeeded> event that creates a new `Customer` object representing a newly created row.</span></span>  
  
     <span data-ttu-id="96523-122">每当用户输入新记录的行，将发生此事件。</span><span class="sxs-lookup"><span data-stu-id="96523-122">This event occurs whenever the user enters the row for new records.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#140](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#140)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#140](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#140)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#140](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#140)]  
  
6.  <span data-ttu-id="96523-123">实现的处理程序<xref:System.Windows.Forms.DataGridView.RowValidated>将新的或已修改行保存到数据存储的事件。</span><span class="sxs-lookup"><span data-stu-id="96523-123">Implement a handler for the <xref:System.Windows.Forms.DataGridView.RowValidated> event that saves new or modified rows to the data store.</span></span>  
  
     <span data-ttu-id="96523-124">每当用户更改当前行，将发生此事件。</span><span class="sxs-lookup"><span data-stu-id="96523-124">This event occurs whenever the user changes the current row.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#150](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#150)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#150](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#150)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#150](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#150)]  
  
7.  <span data-ttu-id="96523-125">实现的处理程序<xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded>事件，该值指示是否<xref:System.Windows.Forms.DataGridView.CancelRowEdit>用户按 esc 键两次处于编辑模式或第一次外部编辑模式，用信号通知行恢复时，事件将会发生。</span><span class="sxs-lookup"><span data-stu-id="96523-125">Implement a handler for the <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded> event that indicates whether the <xref:System.Windows.Forms.DataGridView.CancelRowEdit> event will occur when the user signals row reversion by pressing ESC twice in edit mode or once outside of edit mode.</span></span>  
  
     <span data-ttu-id="96523-126">默认情况下，<xref:System.Windows.Forms.DataGridView.CancelRowEdit>在恢复行已被修改任何当前行中的单元格，除非时发生<xref:System.Windows.Forms.QuestionEventArgs.Response%2A?displayProperty=nameWithType>属性设置为`true`中<xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded>事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="96523-126">By default, <xref:System.Windows.Forms.DataGridView.CancelRowEdit> occurs upon row reversion when any cells in the current row have been modified unless the <xref:System.Windows.Forms.QuestionEventArgs.Response%2A?displayProperty=nameWithType> property is set to `true` in the <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded> event handler.</span></span> <span data-ttu-id="96523-127">当在运行时确定提交作用域时，此事件非常有用。</span><span class="sxs-lookup"><span data-stu-id="96523-127">This event is useful when the commit scope is determined at run time.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#160](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#160)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#160](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#160)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#160](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#160)]  
  
8.  <span data-ttu-id="96523-128">实现的处理程序<xref:System.Windows.Forms.DataGridView.CancelRowEdit>放弃的值的事件`Customer`对象，表示当前行。</span><span class="sxs-lookup"><span data-stu-id="96523-128">Implement a handler for the <xref:System.Windows.Forms.DataGridView.CancelRowEdit> event that discards the values of the `Customer` object representing the current row.</span></span>  
  
     <span data-ttu-id="96523-129">当用户按 esc 键两次处于编辑模式或第一次外部编辑模式，用信号通知行恢复时，将发生此事件。</span><span class="sxs-lookup"><span data-stu-id="96523-129">This event occurs when the user signals row reversion by pressing ESC twice in edit mode or once outside of edit mode.</span></span> <span data-ttu-id="96523-130">如果没有当前行中的单元格进行了修改，或如果不会发生此事件的值<xref:System.Windows.Forms.QuestionEventArgs.Response%2A?displayProperty=nameWithType>属性已设置为`false`中<xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded>事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="96523-130">This event does not occur if no cells in the current row have been modified or if the value of the <xref:System.Windows.Forms.QuestionEventArgs.Response%2A?displayProperty=nameWithType> property has been set to `false` in a <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded> event handler.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#170](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#170)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#170](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#170)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#170](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#170)]  
  
9. <span data-ttu-id="96523-131">实现的处理程序<xref:System.Windows.Forms.DataGridView.UserDeletingRow>删除现有的事件`Customer`从数据存储的对象或放弃未保存`Customer`表示新创建的行的对象。</span><span class="sxs-lookup"><span data-stu-id="96523-131">Implement a handler for the <xref:System.Windows.Forms.DataGridView.UserDeletingRow> event that deletes an existing `Customer` object from the data store or discards an unsaved `Customer` object representing a newly created row.</span></span>  
  
     <span data-ttu-id="96523-132">每当用户通过单击行标题并按 DELETE 键删除行，将发生此事件。</span><span class="sxs-lookup"><span data-stu-id="96523-132">This event occurs whenever the user deletes a row by clicking a row header and pressing the DELETE key.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#180](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#180)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#180](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#180)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#180](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#180)]  
  
10. <span data-ttu-id="96523-133">实现一个简单`Customers`类来表示此代码示例使用的数据项目。</span><span class="sxs-lookup"><span data-stu-id="96523-133">Implement a simple `Customers` class to represent the data items used by this code example.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#200](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#200)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#200](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#200)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#200](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#200)]  
  
## <a name="testing-the-application"></a><span data-ttu-id="96523-134">测试应用程序</span><span class="sxs-lookup"><span data-stu-id="96523-134">Testing the Application</span></span>  
 <span data-ttu-id="96523-135">你现在可以测试窗体，以确保其行为与预期相同。</span><span class="sxs-lookup"><span data-stu-id="96523-135">You can now test the form to make sure it behaves as expected.</span></span>  
  
#### <a name="to-test-the-form"></a><span data-ttu-id="96523-136">若要测试窗体</span><span class="sxs-lookup"><span data-stu-id="96523-136">To test the form</span></span>  
  
-   <span data-ttu-id="96523-137">编译并运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="96523-137">Compile and run the application.</span></span>  
  
     <span data-ttu-id="96523-138">你将看到<xref:System.Windows.Forms.DataGridView>填充三个客户记录的控件。</span><span class="sxs-lookup"><span data-stu-id="96523-138">You will see a <xref:System.Windows.Forms.DataGridView> control populated with three customer records.</span></span> <span data-ttu-id="96523-139">你可以修改行中的多个单元格的值，并按 ESC，两次处于编辑模式和一次外部编辑模式，以便还原为其原始值的整个行。</span><span class="sxs-lookup"><span data-stu-id="96523-139">You can modify the values of multiple cells in a row and press ESC twice in edit mode and once outside of edit mode to revert the entire row to its original values.</span></span> <span data-ttu-id="96523-140">当你修改、 添加或删除在控件中，行`Customer`修改、 添加或删除以及数据存储区中的对象。</span><span class="sxs-lookup"><span data-stu-id="96523-140">When you modify, add, or delete rows in the control, `Customer` objects in the data store are modified, added, or deleted as well.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="96523-141">后续步骤</span><span class="sxs-lookup"><span data-stu-id="96523-141">Next Steps</span></span>  
 <span data-ttu-id="96523-142">此应用程序，必须处理才能实现中的虚拟模式的事件基本了解<xref:System.Windows.Forms.DataGridView>控件。</span><span class="sxs-lookup"><span data-stu-id="96523-142">This application gives you a basic understanding of the events you must handle to implement virtual mode in the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="96523-143">您可以提高此多种方式的基本应用程序：</span><span class="sxs-lookup"><span data-stu-id="96523-143">You can improve this basic application in a number of ways:</span></span>  
  
-   <span data-ttu-id="96523-144">实现缓存从外部数据库的值的数据存储区。</span><span class="sxs-lookup"><span data-stu-id="96523-144">Implement a data store that caches values from an external database.</span></span> <span data-ttu-id="96523-145">缓存应检索并放弃根据需要的值，以使其仅包含必要的操作时使用的少量内存客户端计算机上的显示。</span><span class="sxs-lookup"><span data-stu-id="96523-145">The cache should retrieve and discard values as necessary so that it only contains what is necessary for display while consuming a small amount of memory on the client computer.</span></span>  
  
-   <span data-ttu-id="96523-146">微调具体取决于你的要求的数据存储的性能。</span><span class="sxs-lookup"><span data-stu-id="96523-146">Fine-tune the performance of the data store depending on your requirements.</span></span> <span data-ttu-id="96523-147">例如，你可能想要通过使用更大的缓存大小以及尽量减少数据库查询数补偿慢速网络连接，而不是客户端计算机的内存限制。</span><span class="sxs-lookup"><span data-stu-id="96523-147">For example, you might want to compensate for slow network connections rather than client-computer memory limitations by using a larger cache size and minimizing the number of database queries.</span></span>  
  
 <span data-ttu-id="96523-148">有关缓存从外部数据库的值的详细信息，请参阅[如何： 实现虚拟模式在 Windows 窗体 DataGridView 控件中的实时数据加载](../../../../docs/framework/winforms/controls/virtual-mode-with-just-in-time-data-loading-in-the-datagrid.md)。</span><span class="sxs-lookup"><span data-stu-id="96523-148">For more information about caching values from an external database, see [How to: Implement Virtual Mode with Just-In-Time Data Loading in the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/virtual-mode-with-just-in-time-data-loading-in-the-datagrid.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96523-149">请参阅</span><span class="sxs-lookup"><span data-stu-id="96523-149">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>  
 <xref:System.Windows.Forms.DataGridView.CellValueNeeded>  
 <xref:System.Windows.Forms.DataGridView.CellValuePushed>  
 <xref:System.Windows.Forms.DataGridView.NewRowNeeded>  
 <xref:System.Windows.Forms.DataGridView.RowValidated>  
 <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded>  
 <xref:System.Windows.Forms.DataGridView.CancelRowEdit>  
 <xref:System.Windows.Forms.DataGridView.UserDeletingRow>  
 [<span data-ttu-id="96523-150">Windows 窗体 DataGridView 控件中的性能调整</span><span class="sxs-lookup"><span data-stu-id="96523-150">Performance Tuning in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/performance-tuning-in-the-windows-forms-datagridview-control.md)  
 [<span data-ttu-id="96523-151">有关缩放 Windows 窗体 DataGridView 控件的最佳做法</span><span class="sxs-lookup"><span data-stu-id="96523-151">Best Practices for Scaling the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md)  
 [<span data-ttu-id="96523-152">在 Windows 窗体 DataGridView 控件中实现实时数据加载的虚拟模式</span><span class="sxs-lookup"><span data-stu-id="96523-152">Implementing Virtual Mode with Just-In-Time Data Loading in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)  
 [<span data-ttu-id="96523-153">如何：在 Windows 窗体 DataGridView 控件中实现虚拟模式</span><span class="sxs-lookup"><span data-stu-id="96523-153">How to: Implement Virtual Mode in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-implement-virtual-mode-in-the-windows-forms-datagridview-control.md)
