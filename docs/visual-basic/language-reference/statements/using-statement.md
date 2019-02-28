---
title: Using 语句 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.using
helpviewer_keywords:
- resource disposal
- Try...Catch...Finally statements, equivalent to Using statement
- resources [Visual Basic], disposing
- Using statement [Visual Basic]
ms.assetid: 665d1580-dd54-4e96-a9a9-6be2a68948f1
ms.openlocfilehash: 1cf0772bf4e9a77474849c59454617261475fa76
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2019
ms.locfileid: "56966081"
---
# <a name="using-statement-visual-basic"></a><span data-ttu-id="347dc-102">Using 语句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="347dc-102">Using Statement (Visual Basic)</span></span>
<span data-ttu-id="347dc-103">声明的开头`Using`阻止并根据需要获取块控制的系统资源。</span><span class="sxs-lookup"><span data-stu-id="347dc-103">Declares the beginning of a `Using` block and optionally acquires the system resources that the block controls.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="347dc-104">语法</span><span class="sxs-lookup"><span data-stu-id="347dc-104">Syntax</span></span>  
  
```  
Using { resourcelist | resourceexpression }  
    [ statements ]  
End Using  
```  
  
## <a name="parts"></a><span data-ttu-id="347dc-105">部件</span><span class="sxs-lookup"><span data-stu-id="347dc-105">Parts</span></span>  
  
|<span data-ttu-id="347dc-106">术语</span><span class="sxs-lookup"><span data-stu-id="347dc-106">Term</span></span>|<span data-ttu-id="347dc-107">定义</span><span class="sxs-lookup"><span data-stu-id="347dc-107">Definition</span></span>|  
|---|---|  
|`resourcelist`|<span data-ttu-id="347dc-108">如果未提供所需`resourceexpression`。</span><span class="sxs-lookup"><span data-stu-id="347dc-108">Required if you do not supply `resourceexpression`.</span></span> <span data-ttu-id="347dc-109">该列表的一个或多个系统资源`Using`阻止控件，由逗号分隔。</span><span class="sxs-lookup"><span data-stu-id="347dc-109">List of one or more system resources that this `Using` block controls, separated by commas.</span></span>|  
|`resourceexpression`|<span data-ttu-id="347dc-110">如果未提供所需`resourcelist`。</span><span class="sxs-lookup"><span data-stu-id="347dc-110">Required if you do not supply `resourcelist`.</span></span> <span data-ttu-id="347dc-111">引用变量或表达式中引用系统资源，以控制此`Using`块。</span><span class="sxs-lookup"><span data-stu-id="347dc-111">Reference variable or expression referring to a system resource to be controlled by this `Using` block.</span></span>|  
|`statements`|<span data-ttu-id="347dc-112">可选。</span><span class="sxs-lookup"><span data-stu-id="347dc-112">Optional.</span></span> <span data-ttu-id="347dc-113">语句块的`Using`块将运行。</span><span class="sxs-lookup"><span data-stu-id="347dc-113">Block of statements that the `Using` block runs.</span></span>|  
|`End Using`|<span data-ttu-id="347dc-114">必需。</span><span class="sxs-lookup"><span data-stu-id="347dc-114">Required.</span></span> <span data-ttu-id="347dc-115">终止的定义`Using`块和控制的所有资源。</span><span class="sxs-lookup"><span data-stu-id="347dc-115">Terminates the definition of the `Using` block and disposes of all the resources that it controls.</span></span>|  
  
 <span data-ttu-id="347dc-116">在每个资源`resourcelist`部分具有以下语法和部分：</span><span class="sxs-lookup"><span data-stu-id="347dc-116">Each resource in the `resourcelist` part has the following syntax and parts:</span></span>  
  
 `resourcename As New resourcetype [ ( [ arglist ] ) ]`  
  
 <span data-ttu-id="347dc-117">或</span><span class="sxs-lookup"><span data-stu-id="347dc-117">-or-</span></span>  
  
 `resourcename As resourcetype = resourceexpression`  
  
## <a name="resourcelist-parts"></a><span data-ttu-id="347dc-118">resourcelist 部件</span><span class="sxs-lookup"><span data-stu-id="347dc-118">resourcelist Parts</span></span>  
  
|<span data-ttu-id="347dc-119">术语</span><span class="sxs-lookup"><span data-stu-id="347dc-119">Term</span></span>|<span data-ttu-id="347dc-120">定义</span><span class="sxs-lookup"><span data-stu-id="347dc-120">Definition</span></span>|  
|---|---|  
|`resourcename`|<span data-ttu-id="347dc-121">必需。</span><span class="sxs-lookup"><span data-stu-id="347dc-121">Required.</span></span> <span data-ttu-id="347dc-122">指的是一种系统资源的引用变量的`Using`阻止控件。</span><span class="sxs-lookup"><span data-stu-id="347dc-122">Reference variable that refers to a system resource that the `Using` block controls.</span></span>|  
|`New`|<span data-ttu-id="347dc-123">如果使用`Using`语句将获取该资源。</span><span class="sxs-lookup"><span data-stu-id="347dc-123">Required if the `Using` statement acquires the resource.</span></span> <span data-ttu-id="347dc-124">如果你已获取资源，使用第二个语法替代方法。</span><span class="sxs-lookup"><span data-stu-id="347dc-124">If you have already acquired the resource, use the second syntax alternative.</span></span>|  
|`resourcetype`|<span data-ttu-id="347dc-125">必需。</span><span class="sxs-lookup"><span data-stu-id="347dc-125">Required.</span></span> <span data-ttu-id="347dc-126">资源的类。</span><span class="sxs-lookup"><span data-stu-id="347dc-126">The class of the resource.</span></span> <span data-ttu-id="347dc-127">类必须实现<xref:System.IDisposable>接口。</span><span class="sxs-lookup"><span data-stu-id="347dc-127">The class must implement the <xref:System.IDisposable> interface.</span></span>|  
|`arglist`|<span data-ttu-id="347dc-128">可选。</span><span class="sxs-lookup"><span data-stu-id="347dc-128">Optional.</span></span> <span data-ttu-id="347dc-129">要传递给要创建的实例的构造函数的参数列表的`resourcetype`。</span><span class="sxs-lookup"><span data-stu-id="347dc-129">List of arguments you are passing to the constructor to create an instance of `resourcetype`.</span></span> <span data-ttu-id="347dc-130">请参阅[参数列表](../../../visual-basic/language-reference/statements/parameter-list.md)。</span><span class="sxs-lookup"><span data-stu-id="347dc-130">See [Parameter List](../../../visual-basic/language-reference/statements/parameter-list.md).</span></span>|  
|`resourceexpression`|<span data-ttu-id="347dc-131">必需。</span><span class="sxs-lookup"><span data-stu-id="347dc-131">Required.</span></span> <span data-ttu-id="347dc-132">为满足要求的系统资源引用变量或表达式`resourcetype`。</span><span class="sxs-lookup"><span data-stu-id="347dc-132">Variable or expression referring to a system resource satisfying the requirements of `resourcetype`.</span></span> <span data-ttu-id="347dc-133">如果使用第二个语法替代方法，您必须将控制权传递给之前获取资源`Using`语句。</span><span class="sxs-lookup"><span data-stu-id="347dc-133">If you use the second syntax alternative, you must acquire the resource before passing control to the `Using` statement.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="347dc-134">备注</span><span class="sxs-lookup"><span data-stu-id="347dc-134">Remarks</span></span>  
 <span data-ttu-id="347dc-135">有时你的代码需要非托管的资源，如文件句柄、 COM 包装器或 SQL 连接。</span><span class="sxs-lookup"><span data-stu-id="347dc-135">Sometimes your code requires an unmanaged resource, such as a file handle, a COM wrapper, or a SQL connection.</span></span> <span data-ttu-id="347dc-136">一个`Using`块确保一个或多个此类资源的释放你的代码完成与之时。</span><span class="sxs-lookup"><span data-stu-id="347dc-136">A `Using` block guarantees the disposal of one or more such resources when your code is finished with them.</span></span> <span data-ttu-id="347dc-137">这使它们可用于其他代码使用。</span><span class="sxs-lookup"><span data-stu-id="347dc-137">This makes them available for other code to use.</span></span>  
  
 <span data-ttu-id="347dc-138">托管的资源释放由.NET Framework 垃圾回收器 (GC) 而无需您采取任何额外的编码。</span><span class="sxs-lookup"><span data-stu-id="347dc-138">Managed resources are disposed of by the .NET Framework garbage collector (GC) without any extra coding on your part.</span></span> <span data-ttu-id="347dc-139">不需要`Using`托管资源的块。</span><span class="sxs-lookup"><span data-stu-id="347dc-139">You do not need a `Using` block for managed resources.</span></span> <span data-ttu-id="347dc-140">但是，仍可以使用`Using`块以强制释放托管资源而不是等待垃圾回收器。</span><span class="sxs-lookup"><span data-stu-id="347dc-140">However, you can still use a `Using` block to force the disposal of a managed resource instead of waiting for the garbage collector.</span></span>  
  
 <span data-ttu-id="347dc-141">一个`Using`块都有三个部分： 获取、 使用情况和可供使用。</span><span class="sxs-lookup"><span data-stu-id="347dc-141">A `Using` block has three parts: acquisition, usage, and disposal.</span></span>  
  
-   <span data-ttu-id="347dc-142">*获取*意味着创建变量并将其初始化，以便向系统资源，请参阅。</span><span class="sxs-lookup"><span data-stu-id="347dc-142">*Acquisition* means creating a variable and initializing it to refer to the system resource.</span></span> <span data-ttu-id="347dc-143">`Using`语句可以获取一个或多个资源，也可以在进入块之前获取恰好一个资源，其提供给`Using`语句。</span><span class="sxs-lookup"><span data-stu-id="347dc-143">The `Using` statement can acquire one or more resources, or you can acquire exactly one resource before entering the block and supply it to the `Using` statement.</span></span> <span data-ttu-id="347dc-144">如果你提供`resourceexpression`，必须在将控制权传递给之前获取资源`Using`语句。</span><span class="sxs-lookup"><span data-stu-id="347dc-144">If you supply `resourceexpression`, you must acquire the resource before passing control to the `Using` statement.</span></span>  
  
-   <span data-ttu-id="347dc-145">*使用情况*意味着访问资源并使用它们执行操作。</span><span class="sxs-lookup"><span data-stu-id="347dc-145">*Usage* means accessing the resources and performing actions with them.</span></span> <span data-ttu-id="347dc-146">之间的语句`Using`和`End Using`表示资源的使用。</span><span class="sxs-lookup"><span data-stu-id="347dc-146">The statements between `Using` and `End Using` represent the usage of the resources.</span></span>  
  
-   <span data-ttu-id="347dc-147">*处置*方法调用<xref:System.IDisposable.Dispose%2A>方法中的对象上`resourcename`。</span><span class="sxs-lookup"><span data-stu-id="347dc-147">*Disposal* means calling the <xref:System.IDisposable.Dispose%2A> method on the object in `resourcename`.</span></span> <span data-ttu-id="347dc-148">这允许要明确终止其资源的对象。</span><span class="sxs-lookup"><span data-stu-id="347dc-148">This allows the object to cleanly terminate its resources.</span></span> <span data-ttu-id="347dc-149">`End Using`语句释放的资源下`Using`块的控件。</span><span class="sxs-lookup"><span data-stu-id="347dc-149">The `End Using` statement disposes of the resources under the `Using` block's control.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="347dc-150">行为</span><span class="sxs-lookup"><span data-stu-id="347dc-150">Behavior</span></span>  
 <span data-ttu-id="347dc-151">一个`Using`块的行为类似于`Try`...`Finally`中的构造`Try`块使用的资源和`Finally`块释放它们。</span><span class="sxs-lookup"><span data-stu-id="347dc-151">A `Using` block behaves like a `Try`...`Finally` construction in which the `Try` block uses the resources and the `Finally` block disposes of them.</span></span> <span data-ttu-id="347dc-152">正因为如此，`Using`块可保证可供使用的资源，不管您如何退出块。</span><span class="sxs-lookup"><span data-stu-id="347dc-152">Because of this, the `Using` block guarantees disposal of the resources, no matter how you exit the block.</span></span> <span data-ttu-id="347dc-153">即使发生未经处理的异常，也是如此除<xref:System.StackOverflowException>。</span><span class="sxs-lookup"><span data-stu-id="347dc-153">This is true even in the case of an unhandled exception, except for a <xref:System.StackOverflowException>.</span></span>  
  
 <span data-ttu-id="347dc-154">获取的每个资源变量的作用域`Using`语句仅限于`Using`块。</span><span class="sxs-lookup"><span data-stu-id="347dc-154">The scope of every resource variable acquired by the `Using` statement is limited to the `Using` block.</span></span>  
  
 <span data-ttu-id="347dc-155">如果指定多个中的系统资源`Using`语句，效果是相同像您嵌套`Using`块相互。</span><span class="sxs-lookup"><span data-stu-id="347dc-155">If you specify more than one system resource in the `Using` statement, the effect is the same as if you nested `Using` blocks one within another.</span></span>  
  
 <span data-ttu-id="347dc-156">如果`resourcename`是`Nothing`，没有调用<xref:System.IDisposable.Dispose%2A>进行，并且不会引发异常。</span><span class="sxs-lookup"><span data-stu-id="347dc-156">If `resourcename` is `Nothing`, no call to <xref:System.IDisposable.Dispose%2A> is made, and no exception is thrown.</span></span>  
  
## <a name="structured-exception-handling-within-a-using-block"></a><span data-ttu-id="347dc-157">结构化的异常处理在使用块</span><span class="sxs-lookup"><span data-stu-id="347dc-157">Structured Exception Handling Within a Using Block</span></span>  
 <span data-ttu-id="347dc-158">如果需要处理中可能发生的异常`Using`块中，你可以添加整个`Try`...`Finally`到它的构造。</span><span class="sxs-lookup"><span data-stu-id="347dc-158">If you need to handle an exception that might occur within the `Using` block, you can add a complete `Try`...`Finally` construction to it.</span></span> <span data-ttu-id="347dc-159">如果您需要处理这种情况其中`Using`语句不是成功地获取资源，可以进行测试以查看是否`resourcename`是`Nothing`。</span><span class="sxs-lookup"><span data-stu-id="347dc-159">If you need to handle the case where the `Using` statement is not successful in acquiring a resource, you can test to see if `resourcename` is `Nothing`.</span></span>  
  
## <a name="structured-exception-handling-instead-of-a-using-block"></a><span data-ttu-id="347dc-160">结构化的异常处理而不使用块</span><span class="sxs-lookup"><span data-stu-id="347dc-160">Structured Exception Handling Instead of a Using Block</span></span>  
 <span data-ttu-id="347dc-161">如果您需要的资源，获取更好地控制或者需要其他代码中的`Finally`块中，您可以重写`Using`作为阻止`Try`...`Finally`构造。</span><span class="sxs-lookup"><span data-stu-id="347dc-161">If you need finer control over the acquisition of the resources, or you need additional code in the `Finally` block, you can rewrite the `Using` block as a `Try`...`Finally` construction.</span></span> <span data-ttu-id="347dc-162">下面的示例演示主干`Try`并`Using`构造等效中获取和释放`resource`。</span><span class="sxs-lookup"><span data-stu-id="347dc-162">The following example shows skeleton `Try` and `Using` constructions that are equivalent in the acquisition and disposal of `resource`.</span></span>  
  
```vb  
Using resource As New resourceType   
    ' Insert code to work with resource.  
End Using  
  
' For the acquisition and disposal of resource, the following  
' Try construction is equivalent to the Using block.  
Dim resource As New resourceType  
Try   
    ' Insert code to work with resource.  
Finally   
    If resource IsNot Nothing Then  
        resource.Dispose()   
    End If  
End Try   
```  
  
> [!NOTE]
>  <span data-ttu-id="347dc-163">中的代码`Using`块中的对象不分配`resourcename`到另一个变量。</span><span class="sxs-lookup"><span data-stu-id="347dc-163">The code inside the `Using` block should not assign the object in `resourcename` to another variable.</span></span> <span data-ttu-id="347dc-164">当您退出`Using`块时，资源将被释放，和另一个变量不能访问它所指向的资源。</span><span class="sxs-lookup"><span data-stu-id="347dc-164">When you exit the `Using` block, the resource is disposed, and the other variable cannot access the resource to which it points.</span></span>  
  
## <a name="example"></a><span data-ttu-id="347dc-165">示例</span><span class="sxs-lookup"><span data-stu-id="347dc-165">Example</span></span>  
 <span data-ttu-id="347dc-166">以下示例创建名为 log.txt 和两行文本写入文件的文件。</span><span class="sxs-lookup"><span data-stu-id="347dc-166">The following example creates a file that is named log.txt and writes two lines of text to the file.</span></span> <span data-ttu-id="347dc-167">该示例还读取该同一个文件，并显示的文本行。</span><span class="sxs-lookup"><span data-stu-id="347dc-167">The example also reads that same file and displays the lines of text.</span></span>  
  
 <span data-ttu-id="347dc-168">因为<xref:System.IO.TextWriter>并<xref:System.IO.TextReader>类将实现<xref:System.IDisposable>接口，该代码可以使用`Using`语句，以确保该文件正确关闭后写入和读取操作。</span><span class="sxs-lookup"><span data-stu-id="347dc-168">Because the <xref:System.IO.TextWriter> and <xref:System.IO.TextReader> classes implement the <xref:System.IDisposable> interface, the code can use `Using` statements to ensure that the file is correctly closed after the write and read operations.</span></span>  
  
 [!code-vb[VbVbalrStatements#50](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#50)]  
  
## <a name="see-also"></a><span data-ttu-id="347dc-169">请参阅</span><span class="sxs-lookup"><span data-stu-id="347dc-169">See also</span></span>
- <xref:System.IDisposable>
- [<span data-ttu-id="347dc-170">Try...Catch...Finally 语句</span><span class="sxs-lookup"><span data-stu-id="347dc-170">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
- [<span data-ttu-id="347dc-171">如何：释放系统资源</span><span class="sxs-lookup"><span data-stu-id="347dc-171">How to: Dispose of a System Resource</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/how-to-dispose-of-a-system-resource.md)
