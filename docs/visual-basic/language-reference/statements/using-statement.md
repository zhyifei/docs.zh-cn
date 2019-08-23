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
ms.openlocfilehash: 346a26ad5751599831d8b0d3e0497e4d488eb76c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69957543"
---
# <a name="using-statement-visual-basic"></a><span data-ttu-id="2a14c-102">Using 语句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2a14c-102">Using Statement (Visual Basic)</span></span>
<span data-ttu-id="2a14c-103">声明`Using`块的开头, 并根据需要获取块所控制的系统资源。</span><span class="sxs-lookup"><span data-stu-id="2a14c-103">Declares the beginning of a `Using` block and optionally acquires the system resources that the block controls.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a14c-104">语法</span><span class="sxs-lookup"><span data-stu-id="2a14c-104">Syntax</span></span>  
  
```  
Using { resourcelist | resourceexpression }  
    [ statements ]  
End Using  
```  
  
## <a name="parts"></a><span data-ttu-id="2a14c-105">部件</span><span class="sxs-lookup"><span data-stu-id="2a14c-105">Parts</span></span>  
  
|<span data-ttu-id="2a14c-106">术语</span><span class="sxs-lookup"><span data-stu-id="2a14c-106">Term</span></span>|<span data-ttu-id="2a14c-107">定义</span><span class="sxs-lookup"><span data-stu-id="2a14c-107">Definition</span></span>|  
|---|---|  
|`resourcelist`|<span data-ttu-id="2a14c-108">如果未提供`resourceexpression`, 则为必需。</span><span class="sxs-lookup"><span data-stu-id="2a14c-108">Required if you do not supply `resourceexpression`.</span></span> <span data-ttu-id="2a14c-109">此`Using`块控制的一个或多个系统资源的列表 (用逗号分隔)。</span><span class="sxs-lookup"><span data-stu-id="2a14c-109">List of one or more system resources that this `Using` block controls, separated by commas.</span></span>|  
|`resourceexpression`|<span data-ttu-id="2a14c-110">如果未提供`resourcelist`, 则为必需。</span><span class="sxs-lookup"><span data-stu-id="2a14c-110">Required if you do not supply `resourcelist`.</span></span> <span data-ttu-id="2a14c-111">引用由此`Using`块控制的系统资源的引用变量或表达式。</span><span class="sxs-lookup"><span data-stu-id="2a14c-111">Reference variable or expression referring to a system resource to be controlled by this `Using` block.</span></span>|  
|`statements`|<span data-ttu-id="2a14c-112">可选。</span><span class="sxs-lookup"><span data-stu-id="2a14c-112">Optional.</span></span> <span data-ttu-id="2a14c-113">`Using`块运行的语句块。</span><span class="sxs-lookup"><span data-stu-id="2a14c-113">Block of statements that the `Using` block runs.</span></span>|  
|`End Using`|<span data-ttu-id="2a14c-114">必需。</span><span class="sxs-lookup"><span data-stu-id="2a14c-114">Required.</span></span> <span data-ttu-id="2a14c-115">终止`Using`块的定义, 并释放其控制的所有资源。</span><span class="sxs-lookup"><span data-stu-id="2a14c-115">Terminates the definition of the `Using` block and disposes of all the resources that it controls.</span></span>|  
  
 <span data-ttu-id="2a14c-116">此`resourcelist`部分中的每个资源都具有以下语法和部分:</span><span class="sxs-lookup"><span data-stu-id="2a14c-116">Each resource in the `resourcelist` part has the following syntax and parts:</span></span>  
  
 `resourcename As New resourcetype [ ( [ arglist ] ) ]`  
  
 <span data-ttu-id="2a14c-117">或</span><span class="sxs-lookup"><span data-stu-id="2a14c-117">-or-</span></span>  
  
 `resourcename As resourcetype = resourceexpression`  
  
## <a name="resourcelist-parts"></a><span data-ttu-id="2a14c-118">resourcelist 部件</span><span class="sxs-lookup"><span data-stu-id="2a14c-118">resourcelist Parts</span></span>  
  
|<span data-ttu-id="2a14c-119">术语</span><span class="sxs-lookup"><span data-stu-id="2a14c-119">Term</span></span>|<span data-ttu-id="2a14c-120">定义</span><span class="sxs-lookup"><span data-stu-id="2a14c-120">Definition</span></span>|  
|---|---|  
|`resourcename`|<span data-ttu-id="2a14c-121">必需。</span><span class="sxs-lookup"><span data-stu-id="2a14c-121">Required.</span></span> <span data-ttu-id="2a14c-122">引用变量, 该变量引用`Using`块所控制的系统资源。</span><span class="sxs-lookup"><span data-stu-id="2a14c-122">Reference variable that refers to a system resource that the `Using` block controls.</span></span>|  
|`New`|<span data-ttu-id="2a14c-123">如果语句获取`Using`资源, 则为必需。</span><span class="sxs-lookup"><span data-stu-id="2a14c-123">Required if the `Using` statement acquires the resource.</span></span> <span data-ttu-id="2a14c-124">如果已获取资源, 请使用第二种语法替代方法。</span><span class="sxs-lookup"><span data-stu-id="2a14c-124">If you have already acquired the resource, use the second syntax alternative.</span></span>|  
|`resourcetype`|<span data-ttu-id="2a14c-125">必需。</span><span class="sxs-lookup"><span data-stu-id="2a14c-125">Required.</span></span> <span data-ttu-id="2a14c-126">资源的类。</span><span class="sxs-lookup"><span data-stu-id="2a14c-126">The class of the resource.</span></span> <span data-ttu-id="2a14c-127">类必须实现<xref:System.IDisposable>接口。</span><span class="sxs-lookup"><span data-stu-id="2a14c-127">The class must implement the <xref:System.IDisposable> interface.</span></span>|  
|`arglist`|<span data-ttu-id="2a14c-128">可选。</span><span class="sxs-lookup"><span data-stu-id="2a14c-128">Optional.</span></span> <span data-ttu-id="2a14c-129">要传递给构造函数来创建实例的`resourcetype`参数的列表。</span><span class="sxs-lookup"><span data-stu-id="2a14c-129">List of arguments you are passing to the constructor to create an instance of `resourcetype`.</span></span> <span data-ttu-id="2a14c-130">请参阅[参数列表](../../../visual-basic/language-reference/statements/parameter-list.md)。</span><span class="sxs-lookup"><span data-stu-id="2a14c-130">See [Parameter List](../../../visual-basic/language-reference/statements/parameter-list.md).</span></span>|  
|`resourceexpression`|<span data-ttu-id="2a14c-131">必需。</span><span class="sxs-lookup"><span data-stu-id="2a14c-131">Required.</span></span> <span data-ttu-id="2a14c-132">引用满足的要求的`resourcetype`系统资源的变量或表达式。</span><span class="sxs-lookup"><span data-stu-id="2a14c-132">Variable or expression referring to a system resource satisfying the requirements of `resourcetype`.</span></span> <span data-ttu-id="2a14c-133">如果使用第二种语法替代方法, 则必须先获取资源, 然后才能将`Using`控制传递给语句。</span><span class="sxs-lookup"><span data-stu-id="2a14c-133">If you use the second syntax alternative, you must acquire the resource before passing control to the `Using` statement.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2a14c-134">备注</span><span class="sxs-lookup"><span data-stu-id="2a14c-134">Remarks</span></span>  
 <span data-ttu-id="2a14c-135">有时, 您的代码需要非托管资源, 如文件句柄、COM 包装或 SQL 连接。</span><span class="sxs-lookup"><span data-stu-id="2a14c-135">Sometimes your code requires an unmanaged resource, such as a file handle, a COM wrapper, or a SQL connection.</span></span> <span data-ttu-id="2a14c-136">当你的代码完成了一个或多个此类资源时,块可保证其释放。`Using`</span><span class="sxs-lookup"><span data-stu-id="2a14c-136">A `Using` block guarantees the disposal of one or more such resources when your code is finished with them.</span></span> <span data-ttu-id="2a14c-137">这使它们可供其他代码使用。</span><span class="sxs-lookup"><span data-stu-id="2a14c-137">This makes them available for other code to use.</span></span>  
  
 <span data-ttu-id="2a14c-138">.NET Framework 垃圾回收器 (GC) 释放托管资源, 而不会对你的部分进行任何额外编码。</span><span class="sxs-lookup"><span data-stu-id="2a14c-138">Managed resources are disposed of by the .NET Framework garbage collector (GC) without any extra coding on your part.</span></span> <span data-ttu-id="2a14c-139">对于托管资源, 无`Using`需使用块。</span><span class="sxs-lookup"><span data-stu-id="2a14c-139">You do not need a `Using` block for managed resources.</span></span> <span data-ttu-id="2a14c-140">但是, 您仍然可以使用`Using`块来强制处置托管资源, 而不是等待垃圾回收器。</span><span class="sxs-lookup"><span data-stu-id="2a14c-140">However, you can still use a `Using` block to force the disposal of a managed resource instead of waiting for the garbage collector.</span></span>  
  
 <span data-ttu-id="2a14c-141">`Using`块有三个部分: 获取、使用和处理。</span><span class="sxs-lookup"><span data-stu-id="2a14c-141">A `Using` block has three parts: acquisition, usage, and disposal.</span></span>  
  
- <span data-ttu-id="2a14c-142">*获取*是指创建一个变量并将其初始化, 以引用系统资源。</span><span class="sxs-lookup"><span data-stu-id="2a14c-142">*Acquisition* means creating a variable and initializing it to refer to the system resource.</span></span> <span data-ttu-id="2a14c-143">语句可以获取一个或多个资源, 也可以在输入块之前获取一个资源, 并将其提供`Using`给语句。 `Using`</span><span class="sxs-lookup"><span data-stu-id="2a14c-143">The `Using` statement can acquire one or more resources, or you can acquire exactly one resource before entering the block and supply it to the `Using` statement.</span></span> <span data-ttu-id="2a14c-144">如果提供`resourceexpression`, 则必须先获取资源, 然后才能将控制传递`Using`给语句。</span><span class="sxs-lookup"><span data-stu-id="2a14c-144">If you supply `resourceexpression`, you must acquire the resource before passing control to the `Using` statement.</span></span>  
  
- <span data-ttu-id="2a14c-145">*用法*是指访问资源并对其执行操作。</span><span class="sxs-lookup"><span data-stu-id="2a14c-145">*Usage* means accessing the resources and performing actions with them.</span></span> <span data-ttu-id="2a14c-146">`Using` 和`End Using`之间的语句表示资源的使用情况。</span><span class="sxs-lookup"><span data-stu-id="2a14c-146">The statements between `Using` and `End Using` represent the usage of the resources.</span></span>  
  
- <span data-ttu-id="2a14c-147">处理是指对<xref:System.IDisposable.Dispose%2A>中`resourcename`的对象调用方法。</span><span class="sxs-lookup"><span data-stu-id="2a14c-147">*Disposal* means calling the <xref:System.IDisposable.Dispose%2A> method on the object in `resourcename`.</span></span> <span data-ttu-id="2a14c-148">这使对象可以干净地终止其资源。</span><span class="sxs-lookup"><span data-stu-id="2a14c-148">This allows the object to cleanly terminate its resources.</span></span> <span data-ttu-id="2a14c-149">语句释放`Using`块控件下的资源。 `End Using`</span><span class="sxs-lookup"><span data-stu-id="2a14c-149">The `End Using` statement disposes of the resources under the `Using` block's control.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="2a14c-150">行为</span><span class="sxs-lookup"><span data-stu-id="2a14c-150">Behavior</span></span>  
 <span data-ttu-id="2a14c-151">块的行为`Try`类似于 ... `Using`块使用资源和块处置资源的构造。`Finally` `Try` `Finally`</span><span class="sxs-lookup"><span data-stu-id="2a14c-151">A `Using` block behaves like a `Try`...`Finally` construction in which the `Try` block uses the resources and the `Finally` block disposes of them.</span></span> <span data-ttu-id="2a14c-152">因此, `Using`无论退出块的方式如何, 块都可保证资源的处置。</span><span class="sxs-lookup"><span data-stu-id="2a14c-152">Because of this, the `Using` block guarantees disposal of the resources, no matter how you exit the block.</span></span> <span data-ttu-id="2a14c-153">即使在发生未经处理的异常的情况下也是如此, 但<xref:System.StackOverflowException>除外。</span><span class="sxs-lookup"><span data-stu-id="2a14c-153">This is true even in the case of an unhandled exception, except for a <xref:System.StackOverflowException>.</span></span>  
  
 <span data-ttu-id="2a14c-154">`Using`语句获取的每个资源变量的作用域仅限于`Using`块。</span><span class="sxs-lookup"><span data-stu-id="2a14c-154">The scope of every resource variable acquired by the `Using` statement is limited to the `Using` block.</span></span>  
  
 <span data-ttu-id="2a14c-155">如果在`Using`语句中指定多个系统资源, 则效果与嵌套`Using`块在另一个中时相同。</span><span class="sxs-lookup"><span data-stu-id="2a14c-155">If you specify more than one system resource in the `Using` statement, the effect is the same as if you nested `Using` blocks one within another.</span></span>  
  
 <span data-ttu-id="2a14c-156">如果`resourcename` <xref:System.IDisposable.Dispose%2A>为`Nothing`, 则不进行对的调用, 且不引发异常。</span><span class="sxs-lookup"><span data-stu-id="2a14c-156">If `resourcename` is `Nothing`, no call to <xref:System.IDisposable.Dispose%2A> is made, and no exception is thrown.</span></span>  
  
## <a name="structured-exception-handling-within-a-using-block"></a><span data-ttu-id="2a14c-157">Using 块中的结构化异常处理</span><span class="sxs-lookup"><span data-stu-id="2a14c-157">Structured Exception Handling Within a Using Block</span></span>  
 <span data-ttu-id="2a14c-158">如果需要处理可能在`Using`块中发生的异常, 则可以添加一个完整`Try`的 .。。`Finally`构造。</span><span class="sxs-lookup"><span data-stu-id="2a14c-158">If you need to handle an exception that might occur within the `Using` block, you can add a complete `Try`...`Finally` construction to it.</span></span> <span data-ttu-id="2a14c-159">如果需要处理`Using`语句未能成功获取资源的情况, 则可以进行测试以`resourcename`查看是否为`Nothing`。</span><span class="sxs-lookup"><span data-stu-id="2a14c-159">If you need to handle the case where the `Using` statement is not successful in acquiring a resource, you can test to see if `resourcename` is `Nothing`.</span></span>  
  
## <a name="structured-exception-handling-instead-of-a-using-block"></a><span data-ttu-id="2a14c-160">结构化异常处理而不是 Using 块</span><span class="sxs-lookup"><span data-stu-id="2a14c-160">Structured Exception Handling Instead of a Using Block</span></span>  
 <span data-ttu-id="2a14c-161">如果需要更好地控制资源的获取, 或在`Finally`块中需要其他代码, 则可以将`Using`块重写为`Try`.。。`Finally`构造。</span><span class="sxs-lookup"><span data-stu-id="2a14c-161">If you need finer control over the acquisition of the resources, or you need additional code in the `Finally` block, you can rewrite the `Using` block as a `Try`...`Finally` construction.</span></span> <span data-ttu-id="2a14c-162">下面的示例显示了`Try`的`Using`采集和处置`resource`中等效的主干和构造。</span><span class="sxs-lookup"><span data-stu-id="2a14c-162">The following example shows skeleton `Try` and `Using` constructions that are equivalent in the acquisition and disposal of `resource`.</span></span>  
  
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
> <span data-ttu-id="2a14c-163">`Using`块内的代码不应将`resourcename`对象分配给另一个变量。</span><span class="sxs-lookup"><span data-stu-id="2a14c-163">The code inside the `Using` block should not assign the object in `resourcename` to another variable.</span></span> <span data-ttu-id="2a14c-164">退出`Using`块后, 资源会被释放, 另一个变量将无法访问它所指向的资源。</span><span class="sxs-lookup"><span data-stu-id="2a14c-164">When you exit the `Using` block, the resource is disposed, and the other variable cannot access the resource to which it points.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2a14c-165">示例</span><span class="sxs-lookup"><span data-stu-id="2a14c-165">Example</span></span>  
 <span data-ttu-id="2a14c-166">下面的示例创建一个名为 ".log" 的文件, 并向该文件写入两行文本。</span><span class="sxs-lookup"><span data-stu-id="2a14c-166">The following example creates a file that is named log.txt and writes two lines of text to the file.</span></span> <span data-ttu-id="2a14c-167">该示例还读取该文件并显示文本行。</span><span class="sxs-lookup"><span data-stu-id="2a14c-167">The example also reads that same file and displays the lines of text.</span></span>  
  
 <span data-ttu-id="2a14c-168"><xref:System.IDisposable> `Using`由于和类<xref:System.IO.TextReader>实现接口, 因此代码可以使用语句来确保文件在执行写入和读取操作后正确关闭。 <xref:System.IO.TextWriter></span><span class="sxs-lookup"><span data-stu-id="2a14c-168">Because the <xref:System.IO.TextWriter> and <xref:System.IO.TextReader> classes implement the <xref:System.IDisposable> interface, the code can use `Using` statements to ensure that the file is correctly closed after the write and read operations.</span></span>  
  
 [!code-vb[VbVbalrStatements#50](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#50)]  
  
## <a name="see-also"></a><span data-ttu-id="2a14c-169">请参阅</span><span class="sxs-lookup"><span data-stu-id="2a14c-169">See also</span></span>

- <xref:System.IDisposable>
- [<span data-ttu-id="2a14c-170">Try...Catch...Finally 语句</span><span class="sxs-lookup"><span data-stu-id="2a14c-170">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
- [<span data-ttu-id="2a14c-171">如何：释放系统资源</span><span class="sxs-lookup"><span data-stu-id="2a14c-171">How to: Dispose of a System Resource</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/how-to-dispose-of-a-system-resource.md)
