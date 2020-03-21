---
title: 实现 IE500
ms.date: 07/31/2018
helpviewer_keywords:
- control flow [Visual Basic]
- enumerable interfaces
- loop structures [Visual Basic], optimizing performance
- control flow [Visual Basic]
ms.assetid: c60d7589-51f2-4463-a2d5-22506bbc1554
ms.openlocfilehash: 4151a680050f234d450d8de5e67a767c54e8df68
ms.sourcegitcommit: 43d10ef65f0f1fd6c3b515e363bde11a3fcd8d6d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/04/2020
ms.locfileid: "78266906"
---
# <a name="walkthrough-implementing-ienumerableof-t-in-visual-basic"></a><span data-ttu-id="90deb-102">演练：在 Visual Basic 中实现 IEnumerable(Of T)</span><span class="sxs-lookup"><span data-stu-id="90deb-102">Walkthrough: Implementing IEnumerable(Of T) in Visual Basic</span></span>
<span data-ttu-id="90deb-103">接口<xref:System.Collections.Generic.IEnumerable%601>由类实现，这些类可以一次返回一个项的值序列。</span><span class="sxs-lookup"><span data-stu-id="90deb-103">The <xref:System.Collections.Generic.IEnumerable%601> interface is implemented by classes that can return a sequence of values one item at a time.</span></span> <span data-ttu-id="90deb-104">一次返回一个项目的数据的优点是，您不必将完整的数据集加载到内存中才能使用它。</span><span class="sxs-lookup"><span data-stu-id="90deb-104">The advantage of returning data one item at a time is that you do not have to load the complete set of data into memory to work with it.</span></span> <span data-ttu-id="90deb-105">您只需要使用足够的内存从数据加载单个项。</span><span class="sxs-lookup"><span data-stu-id="90deb-105">You only have to use sufficient memory to load a single item from the data.</span></span> <span data-ttu-id="90deb-106">实现接口的`IEnumerable(T)`类可用于`For Each`循环或 LINQ 查询。</span><span class="sxs-lookup"><span data-stu-id="90deb-106">Classes that implement the `IEnumerable(T)` interface can be used with `For Each` loops or LINQ queries.</span></span>  
  
 <span data-ttu-id="90deb-107">例如，考虑一个应用程序，该应用程序必须读取大型文本文件，并从文件返回与特定搜索条件匹配的每行。</span><span class="sxs-lookup"><span data-stu-id="90deb-107">For example, consider an application that must read a large text file and return each line from the file that matches particular search criteria.</span></span> <span data-ttu-id="90deb-108">应用程序使用 LINQ 查询从文件返回与指定条件匹配的行。</span><span class="sxs-lookup"><span data-stu-id="90deb-108">The application uses a LINQ query to return lines from the file that match the specified criteria.</span></span> <span data-ttu-id="90deb-109">要使用 LINQ 查询查询文件的内容，应用程序可以将文件的内容加载到数组或集合中。</span><span class="sxs-lookup"><span data-stu-id="90deb-109">To query the contents of the file by using a LINQ query, the application could load the contents of the file into an array or a collection.</span></span> <span data-ttu-id="90deb-110">但是，将整个文件加载到数组或集合中会消耗的内存远远多于所需的内存。</span><span class="sxs-lookup"><span data-stu-id="90deb-110">However, loading the whole file into an array or collection would consume far more memory than is required.</span></span> <span data-ttu-id="90deb-111">LINQ 查询可以使用枚举类查询文件内容，仅返回与搜索条件匹配的值。</span><span class="sxs-lookup"><span data-stu-id="90deb-111">The LINQ query could instead query the file contents by using an enumerable class, returning only values that match the search criteria.</span></span> <span data-ttu-id="90deb-112">仅返回几个匹配值的查询消耗的内存要少得多。</span><span class="sxs-lookup"><span data-stu-id="90deb-112">Queries that return only a few matching values would consume far less memory.</span></span>  
  
 <span data-ttu-id="90deb-113">您可以创建实现接口的类，<xref:System.Collections.Generic.IEnumerable%601>以将源数据公开为枚举数据。</span><span class="sxs-lookup"><span data-stu-id="90deb-113">You can create a class that implements the <xref:System.Collections.Generic.IEnumerable%601> interface to expose source data as enumerable data.</span></span> <span data-ttu-id="90deb-114">实现接口的`IEnumerable(T)`类将需要实现<xref:System.Collections.Generic.IEnumerator%601>接口的另一个类来遍经源数据迭代。</span><span class="sxs-lookup"><span data-stu-id="90deb-114">Your class that implements the `IEnumerable(T)` interface will require another class that implements the <xref:System.Collections.Generic.IEnumerator%601> interface to iterate through the source data.</span></span> <span data-ttu-id="90deb-115">这两个类使您能够按顺序将数据项作为特定类型返回。</span><span class="sxs-lookup"><span data-stu-id="90deb-115">These two classes enable you to return items of data sequentially as a specific type.</span></span>  
  
 <span data-ttu-id="90deb-116">在本演练中，您将创建实现接口的`IEnumerable(Of String)`类和实现`IEnumerator(Of String)`接口一次读取一行文本文件的类。</span><span class="sxs-lookup"><span data-stu-id="90deb-116">In this walkthrough, you will create a class that implements the `IEnumerable(Of String)` interface and a class that implements the `IEnumerator(Of String)` interface to read a text file one line at a time.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="creating-the-enumerable-class"></a><span data-ttu-id="90deb-117">创建可枚举类</span><span class="sxs-lookup"><span data-stu-id="90deb-117">Creating the Enumerable Class</span></span>  
  
<span data-ttu-id="90deb-118">**创建枚举类项目**</span><span class="sxs-lookup"><span data-stu-id="90deb-118">**Create the enumerable class project**</span></span>

1. <span data-ttu-id="90deb-119">在"可视化基本"中，在 **"文件"** 菜单上，指向 **"新建"，** 然后单击"**项目**"。</span><span class="sxs-lookup"><span data-stu-id="90deb-119">In Visual Basic, on the **File** menu, point to **New** and then click **Project**.</span></span>

1. <span data-ttu-id="90deb-120">在“新建项目”\*\*\*\* 对话框的“项目类型”\*\*\*\* 窗格中，确保选中“Windows”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="90deb-120">In the **New Project** dialog box, in the **Project Types** pane, make sure that **Windows** is selected.</span></span> <span data-ttu-id="90deb-121">在“模板”\*\*\*\* 窗格中，选择“类库”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="90deb-121">Select **Class Library** in the **Templates** pane.</span></span> <span data-ttu-id="90deb-122">在“名称”\*\*\*\* 框中，键入 `StreamReaderEnumerable`，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="90deb-122">In the **Name** box, type `StreamReaderEnumerable`, and then click **OK**.</span></span> <span data-ttu-id="90deb-123">将显示新项目。</span><span class="sxs-lookup"><span data-stu-id="90deb-123">The new project is displayed.</span></span>

1. <span data-ttu-id="90deb-124">在**解决方案资源管理器**中，右键单击 Class1.vb 文件，然后单击 **"重命名**"。</span><span class="sxs-lookup"><span data-stu-id="90deb-124">In **Solution Explorer**, right-click the Class1.vb file and click **Rename**.</span></span> <span data-ttu-id="90deb-125">将文件重命名为 `StreamReaderEnumerable.vb`，然后按 Enter。</span><span class="sxs-lookup"><span data-stu-id="90deb-125">Rename the file to `StreamReaderEnumerable.vb` and press ENTER.</span></span> <span data-ttu-id="90deb-126">重命名文件也会将类重命名为 `StreamReaderEnumerable`。</span><span class="sxs-lookup"><span data-stu-id="90deb-126">Renaming the file will also rename the class to `StreamReaderEnumerable`.</span></span> <span data-ttu-id="90deb-127">此类将实现 `IEnumerable(Of String)` 接口。</span><span class="sxs-lookup"><span data-stu-id="90deb-127">This class will implement the `IEnumerable(Of String)` interface.</span></span>

1. <span data-ttu-id="90deb-128">右键单击 StreamReaderE"项目，指向 **"添加**"，然后单击 **"新项目**"。</span><span class="sxs-lookup"><span data-stu-id="90deb-128">Right-click the StreamReaderEnumerable project, point to **Add**, and then click **New Item**.</span></span> <span data-ttu-id="90deb-129">选择**类**模板。</span><span class="sxs-lookup"><span data-stu-id="90deb-129">Select the **Class** template.</span></span> <span data-ttu-id="90deb-130">在“名称”框中，键入 `StreamReaderEnumerator.vb`，然后单击“确定”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="90deb-130">In the **Name** box, type `StreamReaderEnumerator.vb` and click **OK**.</span></span>

 <span data-ttu-id="90deb-131">此项目中的第一个类是枚举类，将实现接口`IEnumerable(Of String)`。</span><span class="sxs-lookup"><span data-stu-id="90deb-131">The first class in this project is the enumerable class and will implement the `IEnumerable(Of String)` interface.</span></span> <span data-ttu-id="90deb-132">此泛型接口实现<xref:System.Collections.IEnumerable>接口，并保证此类的使用者可以访问键入为`String`的值。</span><span class="sxs-lookup"><span data-stu-id="90deb-132">This generic interface implements the <xref:System.Collections.IEnumerable> interface and guarantees that consumers of this class can access values typed as `String`.</span></span>  
  
<span data-ttu-id="90deb-133">**添加代码以实现 IE500**</span><span class="sxs-lookup"><span data-stu-id="90deb-133">**Add the code to implement IEnumerable**</span></span>

1. <span data-ttu-id="90deb-134">打开流阅读器数字.vb 文件。</span><span class="sxs-lookup"><span data-stu-id="90deb-134">Open the StreamReaderEnumerable.vb file.</span></span>

2. <span data-ttu-id="90deb-135">在`Public Class StreamReaderEnumerable`之后的行上键入以下内容，然后按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="90deb-135">On the line after `Public Class StreamReaderEnumerable`, type the following and press ENTER.</span></span>

     [!code-vb[VbVbalrIteratorWalkthrough#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#1)]

   <span data-ttu-id="90deb-136">Visual Basic 使用`IEnumerable(Of String)`接口所需的成员自动填充类。</span><span class="sxs-lookup"><span data-stu-id="90deb-136">Visual Basic automatically populates the class with the members that are required by the `IEnumerable(Of String)` interface.</span></span>
  
3. <span data-ttu-id="90deb-137">此枚举类将一次从文本文件中读取一行。</span><span class="sxs-lookup"><span data-stu-id="90deb-137">This enumerable class will read lines from a text file one line at a time.</span></span> <span data-ttu-id="90deb-138">将以下代码添加到类中，以公开将文件路径作为输入参数的公共构造函数。</span><span class="sxs-lookup"><span data-stu-id="90deb-138">Add the following code to the class to expose a public constructor that takes a file path as an input parameter.</span></span>

     [!code-vb[VbVbalrIteratorWalkthrough#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#2)]

4. <span data-ttu-id="90deb-139">接口方法的实现将返回`StreamReaderEnumerator`类的新实例。 <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> `IEnumerable(Of String)`</span><span class="sxs-lookup"><span data-stu-id="90deb-139">Your implementation of the <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> method of the `IEnumerable(Of String)` interface will return a new instance of the `StreamReaderEnumerator` class.</span></span> <span data-ttu-id="90deb-140">`GetEnumerator`可以实现`IEnumerable``Private`接口的方法，因为您必须只公开`IEnumerable(Of String)`接口的成员。</span><span class="sxs-lookup"><span data-stu-id="90deb-140">The implementation of the `GetEnumerator` method of the `IEnumerable` interface can be made `Private`, because you have to expose only members of the `IEnumerable(Of String)` interface.</span></span> <span data-ttu-id="90deb-141">将 Visual Basic 为`GetEnumerator`方法生成的代码替换为以下代码。</span><span class="sxs-lookup"><span data-stu-id="90deb-141">Replace the code that Visual Basic generated for the `GetEnumerator` methods with the following code.</span></span>

     [!code-vb[VbVbalrIteratorWalkthrough#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#3)]  
  
<span data-ttu-id="90deb-142">**添加代码以实现 IEnumerator**</span><span class="sxs-lookup"><span data-stu-id="90deb-142">**Add the code to implement IEnumerator**</span></span>

1. <span data-ttu-id="90deb-143">打开流阅读器数字器.vb 文件。</span><span class="sxs-lookup"><span data-stu-id="90deb-143">Open the StreamReaderEnumerator.vb file.</span></span>

2. <span data-ttu-id="90deb-144">在`Public Class StreamReaderEnumerator`之后的行上键入以下内容，然后按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="90deb-144">On the line after `Public Class StreamReaderEnumerator`, type the following and press ENTER.</span></span>

     [!code-vb[VbVbalrIteratorWalkthrough#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#4)]

   <span data-ttu-id="90deb-145">Visual Basic 使用`IEnumerator(Of String)`接口所需的成员自动填充类。</span><span class="sxs-lookup"><span data-stu-id="90deb-145">Visual Basic automatically populates the class with the members that are required by the `IEnumerator(Of String)` interface.</span></span>

3. <span data-ttu-id="90deb-146">枚举器类打开文本文件并执行文件 I/O 以从文件中读取行。</span><span class="sxs-lookup"><span data-stu-id="90deb-146">The enumerator class opens the text file and performs the file I/O to read the lines from the file.</span></span> <span data-ttu-id="90deb-147">将以下代码添加到类中，以公开将文件路径作为输入参数的公共构造函数，并打开文本文件进行读取。</span><span class="sxs-lookup"><span data-stu-id="90deb-147">Add the following code to the class to expose a public constructor that takes a file path as an input parameter and open the text file for reading.</span></span>

     [!code-vb[VbVbalrIteratorWalkthrough#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#5)]

4. <span data-ttu-id="90deb-148">`Current``IEnumerator`和 接口的属性将当前项从文本文件返回为`String` `IEnumerator(Of String)`</span><span class="sxs-lookup"><span data-stu-id="90deb-148">The `Current` properties for both the `IEnumerator(Of String)` and `IEnumerator` interfaces return the current item from the text file as a `String`.</span></span> <span data-ttu-id="90deb-149">`Current`可以实现`IEnumerator``Private`接口的属性，因为您必须只公开`IEnumerator(Of String)`接口的成员。</span><span class="sxs-lookup"><span data-stu-id="90deb-149">The implementation of the `Current` property of the `IEnumerator` interface can be made `Private`, because you have to expose only members of the `IEnumerator(Of String)` interface.</span></span> <span data-ttu-id="90deb-150">将 Visual Basic 为`Current`属性生成的代码替换为以下代码。</span><span class="sxs-lookup"><span data-stu-id="90deb-150">Replace the code that Visual Basic generated for the `Current` properties with the following code.</span></span>

     [!code-vb[VbVbalrIteratorWalkthrough#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#6)]

5. <span data-ttu-id="90deb-151">接口的方法导航到文本文件中的下一个项，并更新`Current`属性返回的值。 `MoveNext` `IEnumerator`</span><span class="sxs-lookup"><span data-stu-id="90deb-151">The `MoveNext` method of the `IEnumerator` interface navigates to the next item in the text file and updates the value that is returned by the `Current` property.</span></span> <span data-ttu-id="90deb-152">如果没有要读取的项，`MoveNext`则方法将返回`False`;否则该方法`MoveNext`将返回`True`。</span><span class="sxs-lookup"><span data-stu-id="90deb-152">If there are no more items to read, the `MoveNext` method returns `False`; otherwise the `MoveNext` method returns `True`.</span></span> <span data-ttu-id="90deb-153">将以下代码添加到 `MoveNext` 方法中。</span><span class="sxs-lookup"><span data-stu-id="90deb-153">Add the following code to the `MoveNext` method.</span></span>

     [!code-vb[VbVbalrIteratorWalkthrough#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#7)]

6. <span data-ttu-id="90deb-154">`IEnumerator`接口`Reset`的方法指示迭代器指向文本文件的开头并清除当前项值。</span><span class="sxs-lookup"><span data-stu-id="90deb-154">The `Reset` method of the `IEnumerator` interface directs the iterator to point to the start of the text file and clears the current item value.</span></span> <span data-ttu-id="90deb-155">将以下代码添加到 `Reset` 方法中。</span><span class="sxs-lookup"><span data-stu-id="90deb-155">Add the following code to the `Reset` method.</span></span>

     [!code-vb[VbVbalrIteratorWalkthrough#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#8)]

7. <span data-ttu-id="90deb-156">`IEnumerator`接口`Dispose`的方法保证在销毁迭代器之前释放所有非托管资源。</span><span class="sxs-lookup"><span data-stu-id="90deb-156">The `Dispose` method of the `IEnumerator` interface guarantees that all unmanaged resources are released before the iterator is destroyed.</span></span> <span data-ttu-id="90deb-157">`StreamReader`对象使用的文件句柄是非托管资源，必须在销毁迭代器实例之前关闭。</span><span class="sxs-lookup"><span data-stu-id="90deb-157">The file handle that is used by the `StreamReader` object is an unmanaged resource and must be closed before the iterator instance is destroyed.</span></span> <span data-ttu-id="90deb-158">将为`Dispose`该方法生成的 Visual Basic 的代码替换为以下代码。</span><span class="sxs-lookup"><span data-stu-id="90deb-158">Replace the code that Visual Basic generated for the `Dispose` method with the following code.</span></span>

     [!code-vb[VbVbalrIteratorWalkthrough#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#9)]
  
## <a name="using-the-sample-iterator"></a><span data-ttu-id="90deb-159">使用样品迭代器</span><span class="sxs-lookup"><span data-stu-id="90deb-159">Using the Sample Iterator</span></span>

 <span data-ttu-id="90deb-160">可以在代码中使用枚举类以及需要实现`IEnumerable`的对象（如`For Next`循环或 LINQ 查询）的控件结构。</span><span class="sxs-lookup"><span data-stu-id="90deb-160">You can use an enumerable class in your code together with control structures that require an object that implements `IEnumerable`, such as a `For Next` loop or a LINQ query.</span></span> <span data-ttu-id="90deb-161">下面的示例显示了 LINQ 查询`StreamReaderEnumerable`中的 。</span><span class="sxs-lookup"><span data-stu-id="90deb-161">The following example shows the `StreamReaderEnumerable` in a LINQ query.</span></span>  
  
 [!code-vb[VbVbalrIteratorWalkthrough#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/Module1.vb#10)]  
  
## <a name="see-also"></a><span data-ttu-id="90deb-162">另请参阅</span><span class="sxs-lookup"><span data-stu-id="90deb-162">See also</span></span>

- [<span data-ttu-id="90deb-163">Visual Basic 中的 LINQ 简介</span><span class="sxs-lookup"><span data-stu-id="90deb-163">Introduction to LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="90deb-164">控制流</span><span class="sxs-lookup"><span data-stu-id="90deb-164">Control Flow</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)
- [<span data-ttu-id="90deb-165">循环结构</span><span class="sxs-lookup"><span data-stu-id="90deb-165">Loop Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [<span data-ttu-id="90deb-166">For Each...Next 语句</span><span class="sxs-lookup"><span data-stu-id="90deb-166">For Each...Next Statement</span></span>](../../../../visual-basic/language-reference/statements/for-each-next-statement.md)
