---
title: 在 Visual Basic 中实现 IEnumerable
ms.date: 07/31/2018
helpviewer_keywords:
- control flow [Visual Basic]
- enumerable interfaces
- loop structures [Visual Basic], optimizing performance
- control flow [Visual Basic]
ms.assetid: c60d7589-51f2-4463-a2d5-22506bbc1554
ms.openlocfilehash: be2eefdc52d38df3071d457b7a71dbac6eaa2657
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2018
ms.locfileid: "43879622"
---
# <a name="walkthrough-implementing-ienumerableof-t-in-visual-basic"></a><span data-ttu-id="c6d63-102">演练：在 Visual Basic 中实现 IEnumerable(Of T)</span><span class="sxs-lookup"><span data-stu-id="c6d63-102">Walkthrough: Implementing IEnumerable(Of T) in Visual Basic</span></span>
<span data-ttu-id="c6d63-103"><xref:System.Collections.Generic.IEnumerable%601>接口由类实现，可以一次返回一系列值的一项。</span><span class="sxs-lookup"><span data-stu-id="c6d63-103">The <xref:System.Collections.Generic.IEnumerable%601> interface is implemented by classes that can return a sequence of values one item at a time.</span></span> <span data-ttu-id="c6d63-104">返回的数据一次的一项是不需要完整的数据集加载到内存中才能使用它的优点。</span><span class="sxs-lookup"><span data-stu-id="c6d63-104">The advantage of returning data one item at a time is that you do not have to load the complete set of data into memory to work with it.</span></span> <span data-ttu-id="c6d63-105">只需使用足够的内存将数据从加载单个项。</span><span class="sxs-lookup"><span data-stu-id="c6d63-105">You only have to use sufficient memory to load a single item from the data.</span></span> <span data-ttu-id="c6d63-106">类实现`IEnumerable(T)`接口可与`For Each`循环或 LINQ 查询。</span><span class="sxs-lookup"><span data-stu-id="c6d63-106">Classes that implement the `IEnumerable(T)` interface can be used with `For Each` loops or LINQ queries.</span></span>  
  
 <span data-ttu-id="c6d63-107">例如，假设应用程序必须读取一个大型文本文件，并从与特定搜索条件匹配的文件返回每个行。</span><span class="sxs-lookup"><span data-stu-id="c6d63-107">For example, consider an application that must read a large text file and return each line from the file that matches particular search criteria.</span></span> <span data-ttu-id="c6d63-108">应用程序使用 LINQ 查询返回与指定的条件匹配的文件中的行。</span><span class="sxs-lookup"><span data-stu-id="c6d63-108">The application uses a LINQ query to return lines from the file that match the specified criteria.</span></span> <span data-ttu-id="c6d63-109">若要使用 LINQ 查询来查询该文件的内容，应用程序可以加载到一个数组或集合的文件的内容。</span><span class="sxs-lookup"><span data-stu-id="c6d63-109">To query the contents of the file by using a LINQ query, the application could load the contents of the file into an array or a collection.</span></span> <span data-ttu-id="c6d63-110">但是，将整个文件加载到数组或集合会占用比所需内存比以往更多的内存。</span><span class="sxs-lookup"><span data-stu-id="c6d63-110">However, loading the whole file into an array or collection would consume far more memory than is required.</span></span> <span data-ttu-id="c6d63-111">LINQ 查询无法使用 enumerable 类，返回与搜索条件匹配的值改为查询文件内容。</span><span class="sxs-lookup"><span data-stu-id="c6d63-111">The LINQ query could instead query the file contents by using an enumerable class, returning only values that match the search criteria.</span></span> <span data-ttu-id="c6d63-112">返回只有少量的查询匹配的值会占用更少内存。</span><span class="sxs-lookup"><span data-stu-id="c6d63-112">Queries that return only a few matching values would consume far less memory.</span></span>  
  
 <span data-ttu-id="c6d63-113">可以创建一个实现类<xref:System.Collections.Generic.IEnumerable%601>接口，以公开可枚举的数据的源数据。</span><span class="sxs-lookup"><span data-stu-id="c6d63-113">You can create a class that implements the <xref:System.Collections.Generic.IEnumerable%601> interface to expose source data as enumerable data.</span></span> <span data-ttu-id="c6d63-114">类实现`IEnumerable(T)`接口需要实现的另一个类<xref:System.Collections.Generic.IEnumerator%601>接口以循环访问源数据。</span><span class="sxs-lookup"><span data-stu-id="c6d63-114">Your class that implements the `IEnumerable(T)` interface will require another class that implements the <xref:System.Collections.Generic.IEnumerator%601> interface to iterate through the source data.</span></span> <span data-ttu-id="c6d63-115">这两个类，可按顺序为特定类型返回的数据的项。</span><span class="sxs-lookup"><span data-stu-id="c6d63-115">These two classes enable you to return items of data sequentially as a specific type.</span></span>  
  
 <span data-ttu-id="c6d63-116">在本演练中，您将创建一个类实现`IEnumerable(Of String)`接口和类，用以实现`IEnumerator(Of String)`接口一次读取一行文本文件。</span><span class="sxs-lookup"><span data-stu-id="c6d63-116">In this walkthrough, you will create a class that implements the `IEnumerable(Of String)` interface and a class that implements the `IEnumerator(Of String)` interface to read a text file one line at a time.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="creating-the-enumerable-class"></a><span data-ttu-id="c6d63-117">创建可枚举类</span><span class="sxs-lookup"><span data-stu-id="c6d63-117">Creating the Enumerable Class</span></span>  
  
<span data-ttu-id="c6d63-118">**创建可枚举类项目**</span><span class="sxs-lookup"><span data-stu-id="c6d63-118">**Create the enumerable class project**</span></span>

1.  <span data-ttu-id="c6d63-119">在 Visual Basic 中上**文件**菜单，依次指向**新建**，然后单击**项目**。</span><span class="sxs-lookup"><span data-stu-id="c6d63-119">In Visual Basic, on the **File** menu, point to **New** and then click **Project**.</span></span>

1.  <span data-ttu-id="c6d63-120">在“新建项目”对话框的“项目类型”窗格中，确保选中“Windows”。</span><span class="sxs-lookup"><span data-stu-id="c6d63-120">In the **New Project** dialog box, in the **Project Types** pane, make sure that **Windows** is selected.</span></span> <span data-ttu-id="c6d63-121">在“模板”窗格中，选择“类库”。</span><span class="sxs-lookup"><span data-stu-id="c6d63-121">Select **Class Library** in the **Templates** pane.</span></span> <span data-ttu-id="c6d63-122">在“名称”框中，键入 `StreamReaderEnumerable`，然后单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="c6d63-122">In the **Name** box, type `StreamReaderEnumerable`, and then click **OK**.</span></span> <span data-ttu-id="c6d63-123">显示新的项目。</span><span class="sxs-lookup"><span data-stu-id="c6d63-123">The new project is displayed.</span></span>

1.  <span data-ttu-id="c6d63-124">在中**解决方案资源管理器**，右键单击 Class1.vb 文件，然后单击**重命名**。</span><span class="sxs-lookup"><span data-stu-id="c6d63-124">In **Solution Explorer**, right-click the Class1.vb file and click **Rename**.</span></span> <span data-ttu-id="c6d63-125">将文件重命名为 `StreamReaderEnumerable.vb`，然后按 Enter。</span><span class="sxs-lookup"><span data-stu-id="c6d63-125">Rename the file to `StreamReaderEnumerable.vb` and press ENTER.</span></span> <span data-ttu-id="c6d63-126">重命名文件也会将类重命名为 `StreamReaderEnumerable`。</span><span class="sxs-lookup"><span data-stu-id="c6d63-126">Renaming the file will also rename the class to `StreamReaderEnumerable`.</span></span> <span data-ttu-id="c6d63-127">此类将实现 `IEnumerable(Of String)` 接口。</span><span class="sxs-lookup"><span data-stu-id="c6d63-127">This class will implement the `IEnumerable(Of String)` interface.</span></span>

1.  <span data-ttu-id="c6d63-128">右键单击 StreamReaderEnumerable 项目，指向**外**，然后单击**新项**。</span><span class="sxs-lookup"><span data-stu-id="c6d63-128">Right-click the StreamReaderEnumerable project, point to **Add**, and then click **New Item**.</span></span> <span data-ttu-id="c6d63-129">选择**类**模板。</span><span class="sxs-lookup"><span data-stu-id="c6d63-129">Select the **Class** template.</span></span> <span data-ttu-id="c6d63-130">在中**名称**框中，键入`StreamReaderEnumerator.vb`然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="c6d63-130">In the **Name** box, type `StreamReaderEnumerator.vb` and click **OK**.</span></span>

 <span data-ttu-id="c6d63-131">此项目中的第一个类是可枚举类，将实现`IEnumerable(Of String)`接口。</span><span class="sxs-lookup"><span data-stu-id="c6d63-131">The first class in this project is the enumerable class and will implement the `IEnumerable(Of String)` interface.</span></span> <span data-ttu-id="c6d63-132">此泛型接口实现<xref:System.Collections.IEnumerable>接口，并保证此类的使用者可以访问值类型化为`String`。</span><span class="sxs-lookup"><span data-stu-id="c6d63-132">This generic interface implements the <xref:System.Collections.IEnumerable> interface and guarantees that consumers of this class can access values typed as `String`.</span></span>  
  
<span data-ttu-id="c6d63-133">**添加代码以实现 IEnumerable**</span><span class="sxs-lookup"><span data-stu-id="c6d63-133">**Add the code to implement IEnumerable**</span></span>

1. <span data-ttu-id="c6d63-134">打开 StreamReaderEnumerable.vb 文件。</span><span class="sxs-lookup"><span data-stu-id="c6d63-134">Open the StreamReaderEnumerable.vb file.</span></span>

2. <span data-ttu-id="c6d63-135">在后面的行上`Public Class StreamReaderEnumerable`，键入以下命令并按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="c6d63-135">On the line after `Public Class StreamReaderEnumerable`, type the following and press ENTER.</span></span>

   [!code-vb[VbVbalrIteratorWalkthrough#1](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_1.vb)]

   <span data-ttu-id="c6d63-136">Visual Basic 会自动填充具有所需的成员的类`IEnumerable(Of String)`接口。</span><span class="sxs-lookup"><span data-stu-id="c6d63-136">Visual Basic automatically populates the class with the members that are required by the `IEnumerable(Of String)` interface.</span></span>
  
3. <span data-ttu-id="c6d63-137">一次，此可枚举类将从一行文本文件读取行。</span><span class="sxs-lookup"><span data-stu-id="c6d63-137">This enumerable class will read lines from a text file one line at a time.</span></span> <span data-ttu-id="c6d63-138">以下代码添加到类，以公开以文件路径作为输入参数的公共构造函数。</span><span class="sxs-lookup"><span data-stu-id="c6d63-138">Add the following code to the class to expose a public constructor that takes a file path as an input parameter.</span></span>

   [!code-vb[VbVbalrIteratorWalkthrough#2](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_2.vb)]

4. <span data-ttu-id="c6d63-139">实现<xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A>方法`IEnumerable(Of String)`接口将返回的新实例`StreamReaderEnumerator`类。</span><span class="sxs-lookup"><span data-stu-id="c6d63-139">Your implementation of the <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> method of the `IEnumerable(Of String)` interface will return a new instance of the `StreamReaderEnumerator` class.</span></span> <span data-ttu-id="c6d63-140">实现`GetEnumerator`方法`IEnumerable`接口可以成为`Private`，这是因为您必须将仅的成员公开`IEnumerable(Of String)`接口。</span><span class="sxs-lookup"><span data-stu-id="c6d63-140">The implementation of the `GetEnumerator` method of the `IEnumerable` interface can be made `Private`, because you have to expose only members of the `IEnumerable(Of String)` interface.</span></span> <span data-ttu-id="c6d63-141">为 Visual Basic 生成的代码替换为`GetEnumerator`用下面的代码的方法。</span><span class="sxs-lookup"><span data-stu-id="c6d63-141">Replace the code that Visual Basic generated for the `GetEnumerator` methods with the following code.</span></span>

   [!code-vb[VbVbalrIteratorWalkthrough#3](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_3.vb)]  
  
<span data-ttu-id="c6d63-142">**添加代码以实现 IEnumerator**</span><span class="sxs-lookup"><span data-stu-id="c6d63-142">**Add the code to implement IEnumerator**</span></span>

1. <span data-ttu-id="c6d63-143">打开 StreamReaderEnumerator.vb 文件。</span><span class="sxs-lookup"><span data-stu-id="c6d63-143">Open the StreamReaderEnumerator.vb file.</span></span>

2. <span data-ttu-id="c6d63-144">在后面的行上`Public Class StreamReaderEnumerator`，键入以下命令并按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="c6d63-144">On the line after `Public Class StreamReaderEnumerator`, type the following and press ENTER.</span></span>

   [!code-vb[VbVbalrIteratorWalkthrough#4](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_4.vb)]

   <span data-ttu-id="c6d63-145">Visual Basic 会自动填充具有所需的成员的类`IEnumerator(Of String)`接口。</span><span class="sxs-lookup"><span data-stu-id="c6d63-145">Visual Basic automatically populates the class with the members that are required by the `IEnumerator(Of String)` interface.</span></span>

3. <span data-ttu-id="c6d63-146">枚举器类打开文本文件，并执行文件 I/O，以从文件读取的行。</span><span class="sxs-lookup"><span data-stu-id="c6d63-146">The enumerator class opens the text file and performs the file I/O to read the lines from the file.</span></span> <span data-ttu-id="c6d63-147">以下代码添加到类，以公开以文件路径作为输入参数的公共构造函数并打开文本文件进行读取。</span><span class="sxs-lookup"><span data-stu-id="c6d63-147">Add the following code to the class to expose a public constructor that takes a file path as an input parameter and open the text file for reading.</span></span>

   [!code-vb[VbVbalrIteratorWalkthrough#5](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_5.vb)]

4. <span data-ttu-id="c6d63-148">`Current`属性都`IEnumerator(Of String)`并`IEnumerator`从文本文件作为接口返回的当前项`String`。</span><span class="sxs-lookup"><span data-stu-id="c6d63-148">The `Current` properties for both the `IEnumerator(Of String)` and `IEnumerator` interfaces return the current item from the text file as a `String`.</span></span> <span data-ttu-id="c6d63-149">实现`Current`的属性`IEnumerator`接口可以成为`Private`，这是因为您必须将仅的成员公开`IEnumerator(Of String)`接口。</span><span class="sxs-lookup"><span data-stu-id="c6d63-149">The implementation of the `Current` property of the `IEnumerator` interface can be made `Private`, because you have to expose only members of the `IEnumerator(Of String)` interface.</span></span> <span data-ttu-id="c6d63-150">为 Visual Basic 生成的代码替换为`Current`属性使用以下代码。</span><span class="sxs-lookup"><span data-stu-id="c6d63-150">Replace the code that Visual Basic generated for the `Current` properties with the following code.</span></span>

   [!code-vb[VbVbalrIteratorWalkthrough#6](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_6.vb)]

5. <span data-ttu-id="c6d63-151">`MoveNext`方法`IEnumerator`界面导航到文本文件中的下一项，并更新返回的值`Current`属性。</span><span class="sxs-lookup"><span data-stu-id="c6d63-151">The `MoveNext` method of the `IEnumerator` interface navigates to the next item in the text file and updates the value that is returned by the `Current` property.</span></span> <span data-ttu-id="c6d63-152">若要读取，没有其他项是否`MoveNext`方法将返回`False`; 否则为`MoveNext`方法将返回`True`。</span><span class="sxs-lookup"><span data-stu-id="c6d63-152">If there are no more items to read, the `MoveNext` method returns `False`; otherwise the `MoveNext` method returns `True`.</span></span> <span data-ttu-id="c6d63-153">将以下代码添加到 `MoveNext` 方法中。</span><span class="sxs-lookup"><span data-stu-id="c6d63-153">Add the following code to the `MoveNext` method.</span></span>

   [!code-vb[VbVbalrIteratorWalkthrough#7](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_7.vb)]

6. <span data-ttu-id="c6d63-154">`Reset`方法的`IEnumerator`接口指示迭代器指向文本文件的起点，并清除当前项的值。</span><span class="sxs-lookup"><span data-stu-id="c6d63-154">The `Reset` method of the `IEnumerator` interface directs the iterator to point to the start of the text file and clears the current item value.</span></span> <span data-ttu-id="c6d63-155">将以下代码添加到 `Reset` 方法中。</span><span class="sxs-lookup"><span data-stu-id="c6d63-155">Add the following code to the `Reset` method.</span></span>

   [!code-vb[VbVbalrIteratorWalkthrough#8](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_8.vb)]

7. <span data-ttu-id="c6d63-156">`Dispose`方法的`IEnumerator`接口可保证在销毁迭代器之前，释放所有非托管的资源。</span><span class="sxs-lookup"><span data-stu-id="c6d63-156">The `Dispose` method of the `IEnumerator` interface guarantees that all unmanaged resources are released before the iterator is destroyed.</span></span> <span data-ttu-id="c6d63-157">使用的文件句柄`StreamReader`对象是一种非托管的资源和销毁该迭代器实例之前，必须关闭。</span><span class="sxs-lookup"><span data-stu-id="c6d63-157">The file handle that is used by the `StreamReader` object is an unmanaged resource and must be closed before the iterator instance is destroyed.</span></span> <span data-ttu-id="c6d63-158">为 Visual Basic 生成的代码替换为`Dispose`用下面的代码的方法。</span><span class="sxs-lookup"><span data-stu-id="c6d63-158">Replace the code that Visual Basic generated for the `Dispose` method with the following code.</span></span>

   [!code-vb[VbVbalrIteratorWalkthrough#9](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_9.vb)] 
  
## <a name="using-the-sample-iterator"></a><span data-ttu-id="c6d63-159">使用示例迭代器</span><span class="sxs-lookup"><span data-stu-id="c6d63-159">Using the Sample Iterator</span></span>

 <span data-ttu-id="c6d63-160">可以在需要实现的对象的控制结构以及代码中使用 enumerable 类`IEnumerable`，如`For Next`循环或 LINQ 查询。</span><span class="sxs-lookup"><span data-stu-id="c6d63-160">You can use an enumerable class in your code together with control structures that require an object that implements `IEnumerable`, such as a `For Next` loop or a LINQ query.</span></span> <span data-ttu-id="c6d63-161">下面的示例演示`StreamReaderEnumerable`LINQ 查询中。</span><span class="sxs-lookup"><span data-stu-id="c6d63-161">The following example shows the `StreamReaderEnumerable` in a LINQ query.</span></span>  
  
 [!code-vb[VbVbalrIteratorWalkthrough#10](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_10.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="c6d63-162">请参阅</span><span class="sxs-lookup"><span data-stu-id="c6d63-162">See Also</span></span>  
 [<span data-ttu-id="c6d63-163">Visual Basic 中的 LINQ 简介</span><span class="sxs-lookup"><span data-stu-id="c6d63-163">Introduction to LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [<span data-ttu-id="c6d63-164">控制流</span><span class="sxs-lookup"><span data-stu-id="c6d63-164">Control Flow</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)  
 [<span data-ttu-id="c6d63-165">循环结构</span><span class="sxs-lookup"><span data-stu-id="c6d63-165">Loop Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)  
 [<span data-ttu-id="c6d63-166">For Each...Next 语句</span><span class="sxs-lookup"><span data-stu-id="c6d63-166">For Each...Next Statement</span></span>](../../../../visual-basic/language-reference/statements/for-each-next-statement.md)
