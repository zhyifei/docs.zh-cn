---
title: "Using 语句 (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.using
helpviewer_keywords:
- resource disposal
- Try...Catch...Finally statements, equivalent to Using statement
- resources [Visual Basic], disposing
- Using statement [Visual Basic]
ms.assetid: 665d1580-dd54-4e96-a9a9-6be2a68948f1
caps.latest.revision: "36"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ed9cc0d04c89eac1fe342a0924dd89bb1e258a11
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="using-statement-visual-basic"></a><span data-ttu-id="f51e9-102">Using 语句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f51e9-102">Using Statement (Visual Basic)</span></span>
<span data-ttu-id="f51e9-103">声明的开头`Using`阻止并根据需要获取该块控制的系统资源。</span><span class="sxs-lookup"><span data-stu-id="f51e9-103">Declares the beginning of a `Using` block and optionally acquires the system resources that the block controls.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f51e9-104">语法</span><span class="sxs-lookup"><span data-stu-id="f51e9-104">Syntax</span></span>  
  
```  
Using { resourcelist | resourceexpression }  
    [ statements ]  
End Using  
```  
  
## <a name="parts"></a><span data-ttu-id="f51e9-105">部件</span><span class="sxs-lookup"><span data-stu-id="f51e9-105">Parts</span></span>  
  
|<span data-ttu-id="f51e9-106">术语</span><span class="sxs-lookup"><span data-stu-id="f51e9-106">Term</span></span>|<span data-ttu-id="f51e9-107">定义</span><span class="sxs-lookup"><span data-stu-id="f51e9-107">Definition</span></span>|  
|---|---|  
|`resourcelist`|<span data-ttu-id="f51e9-108">如果未提供所需`resourceexpression`。</span><span class="sxs-lookup"><span data-stu-id="f51e9-108">Required if you do not supply `resourceexpression`.</span></span> <span data-ttu-id="f51e9-109">该列表的一个或多个系统资源`Using`阻止控件，并用逗号隔开。</span><span class="sxs-lookup"><span data-stu-id="f51e9-109">List of one or more system resources that this `Using` block controls, separated by commas.</span></span>|  
|`resourceexpression`|<span data-ttu-id="f51e9-110">如果未提供所需`resourcelist`。</span><span class="sxs-lookup"><span data-stu-id="f51e9-110">Required if you do not supply `resourcelist`.</span></span> <span data-ttu-id="f51e9-111">引用变量或表达式引用系统资源，以控制此`Using`块。</span><span class="sxs-lookup"><span data-stu-id="f51e9-111">Reference variable or expression referring to a system resource to be controlled by this `Using` block.</span></span>|  
|`statements`|<span data-ttu-id="f51e9-112">可选。</span><span class="sxs-lookup"><span data-stu-id="f51e9-112">Optional.</span></span> <span data-ttu-id="f51e9-113">语句块的`Using`块将运行。</span><span class="sxs-lookup"><span data-stu-id="f51e9-113">Block of statements that the `Using` block runs.</span></span>|  
|`End Using`|<span data-ttu-id="f51e9-114">必需。</span><span class="sxs-lookup"><span data-stu-id="f51e9-114">Required.</span></span> <span data-ttu-id="f51e9-115">终止的定义`Using`块，并释放它所控制的所有资源。</span><span class="sxs-lookup"><span data-stu-id="f51e9-115">Terminates the definition of the `Using` block and disposes of all the resources that it controls.</span></span>|  
  
 <span data-ttu-id="f51e9-116">在每个资源`resourcelist`部件具有以下语法和部件：</span><span class="sxs-lookup"><span data-stu-id="f51e9-116">Each resource in the `resourcelist` part has the following syntax and parts:</span></span>  
  
 `resourcename As New resourcetype [ ( [ arglist ] ) ]`  
  
 <span data-ttu-id="f51e9-117">- 或 -</span><span class="sxs-lookup"><span data-stu-id="f51e9-117">-or-</span></span>  
  
 `resourcename As resourcetype = resourceexpression`  
  
## <a name="resourcelist-parts"></a><span data-ttu-id="f51e9-118">resourcelist 部件</span><span class="sxs-lookup"><span data-stu-id="f51e9-118">resourcelist Parts</span></span>  
  
|<span data-ttu-id="f51e9-119">术语</span><span class="sxs-lookup"><span data-stu-id="f51e9-119">Term</span></span>|<span data-ttu-id="f51e9-120">定义</span><span class="sxs-lookup"><span data-stu-id="f51e9-120">Definition</span></span>|  
|---|---|  
|`resourcename`|<span data-ttu-id="f51e9-121">必需。</span><span class="sxs-lookup"><span data-stu-id="f51e9-121">Required.</span></span> <span data-ttu-id="f51e9-122">指系统资源的引用变量，`Using`阻止控件。</span><span class="sxs-lookup"><span data-stu-id="f51e9-122">Reference variable that refers to a system resource that the `Using` block controls.</span></span>|  
|`New`|<span data-ttu-id="f51e9-123">如果存在`Using`语句获取资源。</span><span class="sxs-lookup"><span data-stu-id="f51e9-123">Required if the `Using` statement acquires the resource.</span></span> <span data-ttu-id="f51e9-124">如果你已获取资源，使用第二个语法替代项。</span><span class="sxs-lookup"><span data-stu-id="f51e9-124">If you have already acquired the resource, use the second syntax alternative.</span></span>|  
|`resourcetype`|<span data-ttu-id="f51e9-125">必需。</span><span class="sxs-lookup"><span data-stu-id="f51e9-125">Required.</span></span> <span data-ttu-id="f51e9-126">资源的类。</span><span class="sxs-lookup"><span data-stu-id="f51e9-126">The class of the resource.</span></span> <span data-ttu-id="f51e9-127">类必须实现<xref:System.IDisposable>接口。</span><span class="sxs-lookup"><span data-stu-id="f51e9-127">The class must implement the <xref:System.IDisposable> interface.</span></span>|  
|`arglist`|<span data-ttu-id="f51e9-128">可选。</span><span class="sxs-lookup"><span data-stu-id="f51e9-128">Optional.</span></span> <span data-ttu-id="f51e9-129">你传递给构造函数来创建的实例的自变量列表的`resourcetype`。</span><span class="sxs-lookup"><span data-stu-id="f51e9-129">List of arguments you are passing to the constructor to create an instance of `resourcetype`.</span></span> <span data-ttu-id="f51e9-130">请参阅[参数列表](../../../visual-basic/language-reference/statements/parameter-list.md)。</span><span class="sxs-lookup"><span data-stu-id="f51e9-130">See [Parameter List](../../../visual-basic/language-reference/statements/parameter-list.md).</span></span>|  
|`resourceexpression`|<span data-ttu-id="f51e9-131">必需。</span><span class="sxs-lookup"><span data-stu-id="f51e9-131">Required.</span></span> <span data-ttu-id="f51e9-132">为满足的要求的系统资源引用变量或表达式`resourcetype`。</span><span class="sxs-lookup"><span data-stu-id="f51e9-132">Variable or expression referring to a system resource satisfying the requirements of `resourcetype`.</span></span> <span data-ttu-id="f51e9-133">如果你使用第二个语法替代方法，您必须在将控制权传递给之前获取资源`Using`语句。</span><span class="sxs-lookup"><span data-stu-id="f51e9-133">If you use the second syntax alternative, you must acquire the resource before passing control to the `Using` statement.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f51e9-134">备注</span><span class="sxs-lookup"><span data-stu-id="f51e9-134">Remarks</span></span>  
 <span data-ttu-id="f51e9-135">有时，代码需要一个非托管的资源，如文件句柄、 COM 包装器或 SQL 连接。</span><span class="sxs-lookup"><span data-stu-id="f51e9-135">Sometimes your code requires an unmanaged resource, such as a file handle, a COM wrapper, or a SQL connection.</span></span> <span data-ttu-id="f51e9-136">A`Using`块时你的代码已完成，但它们都可确保对一个或多个此类资源处置。</span><span class="sxs-lookup"><span data-stu-id="f51e9-136">A `Using` block guarantees the disposal of one or more such resources when your code is finished with them.</span></span> <span data-ttu-id="f51e9-137">这使它们可供其他代码使用。</span><span class="sxs-lookup"><span data-stu-id="f51e9-137">This makes them available for other code to use.</span></span>  
  
 <span data-ttu-id="f51e9-138">托管释放资源的.NET Framework 垃圾回收器 (GC) 而无需您采取任何额外编码。</span><span class="sxs-lookup"><span data-stu-id="f51e9-138">Managed resources are disposed of by the .NET Framework garbage collector (GC) without any extra coding on your part.</span></span> <span data-ttu-id="f51e9-139">不需要`Using`托管资源的块。</span><span class="sxs-lookup"><span data-stu-id="f51e9-139">You do not need a `Using` block for managed resources.</span></span> <span data-ttu-id="f51e9-140">但是，你仍可以使用`Using`块以强制释放托管资源而不是等待垃圾回收器。</span><span class="sxs-lookup"><span data-stu-id="f51e9-140">However, you can still use a `Using` block to force the disposal of a managed resource instead of waiting for the garbage collector.</span></span>  
  
 <span data-ttu-id="f51e9-141">A`Using`块都有三个部分： 获取用量、 使用量以及可供使用。</span><span class="sxs-lookup"><span data-stu-id="f51e9-141">A `Using` block has three parts: acquisition, usage, and disposal.</span></span>  
  
-   <span data-ttu-id="f51e9-142">*获取*意味着创建变量并将其初始化，以便指系统资源。</span><span class="sxs-lookup"><span data-stu-id="f51e9-142">*Acquisition* means creating a variable and initializing it to refer to the system resource.</span></span> <span data-ttu-id="f51e9-143">`Using`语句可以获取一个或多个资源，也可以在进入块之前获取恰好一个资源，其提供给`Using`语句。</span><span class="sxs-lookup"><span data-stu-id="f51e9-143">The `Using` statement can acquire one or more resources, or you can acquire exactly one resource before entering the block and supply it to the `Using` statement.</span></span> <span data-ttu-id="f51e9-144">如果你提供`resourceexpression`，您必须在将控制权传递给之前获取资源`Using`语句。</span><span class="sxs-lookup"><span data-stu-id="f51e9-144">If you supply `resourceexpression`, you must acquire the resource before passing control to the `Using` statement.</span></span>  
  
-   <span data-ttu-id="f51e9-145">*使用情况*意味着访问资源并执行与它们的操作。</span><span class="sxs-lookup"><span data-stu-id="f51e9-145">*Usage* means accessing the resources and performing actions with them.</span></span> <span data-ttu-id="f51e9-146">之间的语句`Using`和`End Using`表示资源的使用。</span><span class="sxs-lookup"><span data-stu-id="f51e9-146">The statements between `Using` and `End Using` represent the usage of the resources.</span></span>  
  
-   <span data-ttu-id="f51e9-147">*处置*意味着调用<xref:System.IDisposable.Dispose%2A>方法中的对象`resourcename`。</span><span class="sxs-lookup"><span data-stu-id="f51e9-147">*Disposal* means calling the <xref:System.IDisposable.Dispose%2A> method on the object in `resourcename`.</span></span> <span data-ttu-id="f51e9-148">这样，要完全终止及其资源的对象。</span><span class="sxs-lookup"><span data-stu-id="f51e9-148">This allows the object to cleanly terminate its resources.</span></span> <span data-ttu-id="f51e9-149">`End Using`语句释放资源下`Using`块的控件。</span><span class="sxs-lookup"><span data-stu-id="f51e9-149">The `End Using` statement disposes of the resources under the `Using` block's control.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="f51e9-150">行为</span><span class="sxs-lookup"><span data-stu-id="f51e9-150">Behavior</span></span>  
 <span data-ttu-id="f51e9-151">A`Using`块的行为类似`Try`...`Finally`顺序构造`Try`块使用的资源和`Finally`块释放它们。</span><span class="sxs-lookup"><span data-stu-id="f51e9-151">A `Using` block behaves like a `Try`...`Finally` construction in which the `Try` block uses the resources and the `Finally` block disposes of them.</span></span> <span data-ttu-id="f51e9-152">因此，`Using`块都可确保释放的资源，无论你如何退出块。</span><span class="sxs-lookup"><span data-stu-id="f51e9-152">Because of this, the `Using` block guarantees disposal of the resources, no matter how you exit the block.</span></span> <span data-ttu-id="f51e9-153">即使发生未经处理的异常，也是如此除<xref:System.StackOverflowException>。</span><span class="sxs-lookup"><span data-stu-id="f51e9-153">This is true even in the case of an unhandled exception, except for a <xref:System.StackOverflowException>.</span></span>  
  
 <span data-ttu-id="f51e9-154">获取的每个资源变量的作用域`Using`语句仅限于`Using`块。</span><span class="sxs-lookup"><span data-stu-id="f51e9-154">The scope of every resource variable acquired by the `Using` statement is limited to the `Using` block.</span></span>  
  
 <span data-ttu-id="f51e9-155">如果指定多个中的系统资源`Using`就像你嵌套语句，效果都将是相同`Using`阻止在另一个。</span><span class="sxs-lookup"><span data-stu-id="f51e9-155">If you specify more than one system resource in the `Using` statement, the effect is the same as if you nested `Using` blocks one within another.</span></span>  
  
 <span data-ttu-id="f51e9-156">如果`resourcename`是`Nothing`，不需要调用<xref:System.IDisposable.Dispose%2A>进行，并且会引发任何异常。</span><span class="sxs-lookup"><span data-stu-id="f51e9-156">If `resourcename` is `Nothing`, no call to <xref:System.IDisposable.Dispose%2A> is made, and no exception is thrown.</span></span>  
  
## <a name="structured-exception-handling-within-a-using-block"></a><span data-ttu-id="f51e9-157">结构化的异常处理在使用块中</span><span class="sxs-lookup"><span data-stu-id="f51e9-157">Structured Exception Handling Within a Using Block</span></span>  
 <span data-ttu-id="f51e9-158">如果你需要处理中可能发生的异常`Using`块中，你可以添加整个`Try`...`Finally`到它的构造。</span><span class="sxs-lookup"><span data-stu-id="f51e9-158">If you need to handle an exception that might occur within the `Using` block, you can add a complete `Try`...`Finally` construction to it.</span></span> <span data-ttu-id="f51e9-159">如果你需要处理的情况其中`Using`语句不是成功获取资源，你可以测试是否`resourcename`是`Nothing`。</span><span class="sxs-lookup"><span data-stu-id="f51e9-159">If you need to handle the case where the `Using` statement is not successful in acquiring a resource, you can test to see if `resourcename` is `Nothing`.</span></span>  
  
## <a name="structured-exception-handling-instead-of-a-using-block"></a><span data-ttu-id="f51e9-160">结构化的异常处理而不使用块</span><span class="sxs-lookup"><span data-stu-id="f51e9-160">Structured Exception Handling Instead of a Using Block</span></span>  
 <span data-ttu-id="f51e9-161">如果你需要更好地控制的获取资源，或者需要中的其他代码`Finally`块中，您可以重新编写`Using`作为阻止`Try`...`Finally`构造。</span><span class="sxs-lookup"><span data-stu-id="f51e9-161">If you need finer control over the acquisition of the resources, or you need additional code in the `Finally` block, you can rewrite the `Using` block as a `Try`...`Finally` construction.</span></span> <span data-ttu-id="f51e9-162">下面的示例演示主干`Try`和`Using`相等，则在购买和处置的构造`resource`。</span><span class="sxs-lookup"><span data-stu-id="f51e9-162">The following example shows skeleton `Try` and `Using` constructions that are equivalent in the acquisition and disposal of `resource`.</span></span>  
  
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
>  <span data-ttu-id="f51e9-163">内的代码`Using`块不应将分配中的对象`resourcename`给另一个变量。</span><span class="sxs-lookup"><span data-stu-id="f51e9-163">The code inside the `Using` block should not assign the object in `resourcename` to another variable.</span></span> <span data-ttu-id="f51e9-164">当您退出`Using`块时，资源将被释放，或另一个变量不能访问它所指向的资源。</span><span class="sxs-lookup"><span data-stu-id="f51e9-164">When you exit the `Using` block, the resource is disposed, and the other variable cannot access the resource to which it points.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f51e9-165">示例</span><span class="sxs-lookup"><span data-stu-id="f51e9-165">Example</span></span>  
 <span data-ttu-id="f51e9-166">下面的示例创建名为 log.txt 并将两个行文本写入文件的文件。</span><span class="sxs-lookup"><span data-stu-id="f51e9-166">The following example creates a file that is named log.txt and writes two lines of text to the file.</span></span> <span data-ttu-id="f51e9-167">该示例还读取该相同的文件，并显示的文本行。</span><span class="sxs-lookup"><span data-stu-id="f51e9-167">The example also reads that same file and displays the lines of text.</span></span>  
  
 <span data-ttu-id="f51e9-168">因为<xref:System.IO.TextWriter>和<xref:System.IO.TextReader>类实现<xref:System.IDisposable>接口，可以使用代码`Using`语句，以确保该文件正确关闭后写入和读取操作。</span><span class="sxs-lookup"><span data-stu-id="f51e9-168">Because the <xref:System.IO.TextWriter> and <xref:System.IO.TextReader> classes implement the <xref:System.IDisposable> interface, the code can use `Using` statements to ensure that the file is correctly closed after the write and read operations.</span></span>  
  
 [!code-vb[VbVbalrStatements#50](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/using-statement_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="f51e9-169">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f51e9-169">See Also</span></span>  
 <xref:System.IDisposable>  
 [<span data-ttu-id="f51e9-170">Try...Catch...Finally 语句</span><span class="sxs-lookup"><span data-stu-id="f51e9-170">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)  
 [<span data-ttu-id="f51e9-171">如何：释放系统资源</span><span class="sxs-lookup"><span data-stu-id="f51e9-171">How to: Dispose of a System Resource</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/how-to-dispose-of-a-system-resource.md)
