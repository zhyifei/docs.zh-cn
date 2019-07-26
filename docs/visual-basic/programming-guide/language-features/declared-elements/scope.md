---
title: Visual Basic 中的范围
ms.date: 07/20/2015
helpviewer_keywords:
- module scope [Visual Basic]
- scope [Visual Basic], levels
- module level
- procedures [Visual Basic], scope
- declared elements [Visual Basic], scope
- namespaces [Visual Basic], scope
- scope [Visual Basic], declared elements
- scope [Visual Basic], about scope
- levels of scope [Visual Basic]
- block scope [Visual Basic]
- scope [Visual Basic], Visual Basic
- procedure scope [Visual Basic]
ms.assetid: 208106fe-79c9-4eec-93c6-55f08548895f
ms.openlocfilehash: 7f7e32d6ac838e250c260987d3d5c375f8697c45
ms.sourcegitcommit: 463f3f050cecc0b6403e67f19a61f870fb8e7b7d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/26/2019
ms.locfileid: "68512852"
---
# <a name="scope-in-visual-basic"></a><span data-ttu-id="db702-102">Visual Basic 中的范围</span><span class="sxs-lookup"><span data-stu-id="db702-102">Scope in Visual Basic</span></span>

<span data-ttu-id="db702-103">已声明元素的*作用域*是所有可引用它的代码的集合, 无需限定其名称或通过[Imports 语句 (.net 命名空间和类型)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)提供它。</span><span class="sxs-lookup"><span data-stu-id="db702-103">The *scope* of a declared element is the set of all code that can refer to it without qualifying its name or making it available through an [Imports Statement (.NET Namespace and Type)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).</span></span> <span data-ttu-id="db702-104">元素可以具有以下级别之一的作用域:</span><span class="sxs-lookup"><span data-stu-id="db702-104">An element can have scope at one of the following levels:</span></span>

|<span data-ttu-id="db702-105">级别</span><span class="sxs-lookup"><span data-stu-id="db702-105">Level</span></span>|<span data-ttu-id="db702-106">描述</span><span class="sxs-lookup"><span data-stu-id="db702-106">Description</span></span>|
|-----------|-----------------|
|<span data-ttu-id="db702-107">块范围</span><span class="sxs-lookup"><span data-stu-id="db702-107">Block scope</span></span>|<span data-ttu-id="db702-108">仅在声明它的代码块内可用</span><span class="sxs-lookup"><span data-stu-id="db702-108">Available only within the code block in which it is declared</span></span>|
|<span data-ttu-id="db702-109">过程范围</span><span class="sxs-lookup"><span data-stu-id="db702-109">Procedure scope</span></span>|<span data-ttu-id="db702-110">对声明它的过程中的所有代码可用</span><span class="sxs-lookup"><span data-stu-id="db702-110">Available to all code within the procedure in which it is declared</span></span>|
|<span data-ttu-id="db702-111">模块范围</span><span class="sxs-lookup"><span data-stu-id="db702-111">Module scope</span></span>|<span data-ttu-id="db702-112">适用于声明它的模块、类或结构中的所有代码</span><span class="sxs-lookup"><span data-stu-id="db702-112">Available to all code within the module, class, or structure in which it is declared</span></span>|
|<span data-ttu-id="db702-113">命名空间范围</span><span class="sxs-lookup"><span data-stu-id="db702-113">Namespace scope</span></span>|<span data-ttu-id="db702-114">可用于声明它的命名空间中的所有代码</span><span class="sxs-lookup"><span data-stu-id="db702-114">Available to all code in the namespace in which it is declared</span></span>|

<span data-ttu-id="db702-115">这种级别的作用域从最小 (块) 到最宽 (命名空间) 的范围进度, 其中最*窄的范围*指的是可以引用元素而不进行限定的最小代码集。</span><span class="sxs-lookup"><span data-stu-id="db702-115">These levels of scope progress from the narrowest (block) to the widest (namespace), where *narrowest scope* means the smallest set of code that can refer to the element without qualification.</span></span> <span data-ttu-id="db702-116">有关详细信息, 请参阅本页上的 "范围级别"。</span><span class="sxs-lookup"><span data-stu-id="db702-116">For more information, see "Levels of Scope" on this page.</span></span>

## <a name="specifying-scope-and-defining-variables"></a><span data-ttu-id="db702-117">指定作用域和定义变量</span><span class="sxs-lookup"><span data-stu-id="db702-117">Specifying Scope and Defining Variables</span></span>

<span data-ttu-id="db702-118">在声明元素时指定其作用域。</span><span class="sxs-lookup"><span data-stu-id="db702-118">You specify the scope of an element when you declare it.</span></span> <span data-ttu-id="db702-119">范围可能取决于以下因素:</span><span class="sxs-lookup"><span data-stu-id="db702-119">The scope can depend on the following factors:</span></span>

- <span data-ttu-id="db702-120">声明元素的区域 (块、过程、模块、类或结构)</span><span class="sxs-lookup"><span data-stu-id="db702-120">The region (block, procedure, module, class, or structure) in which you declare the element</span></span>

- <span data-ttu-id="db702-121">包含元素声明的命名空间</span><span class="sxs-lookup"><span data-stu-id="db702-121">The namespace containing the element's declaration</span></span>

- <span data-ttu-id="db702-122">为元素声明的访问级别</span><span class="sxs-lookup"><span data-stu-id="db702-122">The access level you declare for the element</span></span>

<span data-ttu-id="db702-123">定义名称相同但范围不同的变量时请小心, 因为这样做可能会导致意外的结果。</span><span class="sxs-lookup"><span data-stu-id="db702-123">Use care when you define variables with the same name but different scope, because doing so can lead to unexpected results.</span></span> <span data-ttu-id="db702-124">有关详细信息，请参阅 [References to Declared Elements](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)。</span><span class="sxs-lookup"><span data-stu-id="db702-124">For more information, see [References to Declared Elements](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span></span>

## <a name="levels-of-scope"></a><span data-ttu-id="db702-125">范围级别</span><span class="sxs-lookup"><span data-stu-id="db702-125">Levels of Scope</span></span>

<span data-ttu-id="db702-126">编程元素可在声明它的整个区域内使用。</span><span class="sxs-lookup"><span data-stu-id="db702-126">A programming element is available throughout the region in which you declare it.</span></span> <span data-ttu-id="db702-127">同一区域中的所有代码都可以引用元素, 而无需限定其名称。</span><span class="sxs-lookup"><span data-stu-id="db702-127">All code in the same region can refer to the element without qualifying its name.</span></span>

### <a name="block-scope"></a><span data-ttu-id="db702-128">块范围</span><span class="sxs-lookup"><span data-stu-id="db702-128">Block Scope</span></span>

<span data-ttu-id="db702-129">块是包含在启动和终止声明语句中的一组语句, 如下所示:</span><span class="sxs-lookup"><span data-stu-id="db702-129">A block is a set of statements enclosed within initiating and terminating declaration statements, such as the following:</span></span>

- <span data-ttu-id="db702-130">`Do` 和 `Loop`</span><span class="sxs-lookup"><span data-stu-id="db702-130">`Do` and `Loop`</span></span>

- <span data-ttu-id="db702-131">`For`[`Each`] 和`Next`</span><span class="sxs-lookup"><span data-stu-id="db702-131">`For` [`Each`] and `Next`</span></span>

- <span data-ttu-id="db702-132">`If` 和 `End If`</span><span class="sxs-lookup"><span data-stu-id="db702-132">`If` and `End If`</span></span>

- <span data-ttu-id="db702-133">`Select` 和 `End Select`</span><span class="sxs-lookup"><span data-stu-id="db702-133">`Select` and `End Select`</span></span>

- <span data-ttu-id="db702-134">`SyncLock` 和 `End SyncLock`</span><span class="sxs-lookup"><span data-stu-id="db702-134">`SyncLock` and `End SyncLock`</span></span>

- <span data-ttu-id="db702-135">`Try` 和 `End Try`</span><span class="sxs-lookup"><span data-stu-id="db702-135">`Try` and `End Try`</span></span>

- <span data-ttu-id="db702-136">`While` 和 `End While`</span><span class="sxs-lookup"><span data-stu-id="db702-136">`While` and `End While`</span></span>

- <span data-ttu-id="db702-137">`With` 和 `End With`</span><span class="sxs-lookup"><span data-stu-id="db702-137">`With` and `End With`</span></span>

<span data-ttu-id="db702-138">如果在块中声明一个变量, 则只能在该块内使用它。</span><span class="sxs-lookup"><span data-stu-id="db702-138">If you declare a variable within a block, you can use it only within that block.</span></span> <span data-ttu-id="db702-139">在下面的示例中, `cube`整数变量的作用域是介于和`End If`之间`If`的块`cube` , 当执行传递到块时, 你将无法再引用。</span><span class="sxs-lookup"><span data-stu-id="db702-139">In the following example, the scope of the integer variable `cube` is the block between `If` and `End If`, and you can no longer refer to `cube` when execution passes out of the block.</span></span>

```vb
If n < 1291 Then
    Dim cube As Integer
    cube = n ^ 3
End If
```

> [!NOTE]
> <span data-ttu-id="db702-140">即使变量的作用域限制为块, 其生存期仍是整个过程的生存期。</span><span class="sxs-lookup"><span data-stu-id="db702-140">Even if the scope of a variable is limited to a block, its lifetime is still that of the entire procedure.</span></span> <span data-ttu-id="db702-141">如果在过程中多次输入块, 则每个块变量将保留其以前的值。</span><span class="sxs-lookup"><span data-stu-id="db702-141">If you enter the block more than once during the procedure, each block variable retains its previous value.</span></span> <span data-ttu-id="db702-142">若要避免在这种情况下出现意外结果, 最好在块的开头初始化块变量。</span><span class="sxs-lookup"><span data-stu-id="db702-142">To avoid unexpected results in such a case, it is wise to initialize block variables at the beginning of the block.</span></span>

### <a name="procedure-scope"></a><span data-ttu-id="db702-143">过程范围</span><span class="sxs-lookup"><span data-stu-id="db702-143">Procedure Scope</span></span>

<span data-ttu-id="db702-144">在过程中声明的元素在该过程之外不可用。</span><span class="sxs-lookup"><span data-stu-id="db702-144">An element declared within a procedure is not available outside that procedure.</span></span> <span data-ttu-id="db702-145">只有包含声明的过程可以使用它。</span><span class="sxs-lookup"><span data-stu-id="db702-145">Only the procedure that contains the declaration can use it.</span></span> <span data-ttu-id="db702-146">此级别的变量也称为*局部变量*。</span><span class="sxs-lookup"><span data-stu-id="db702-146">Variables at this level are also known as *local variables*.</span></span> <span data-ttu-id="db702-147">用[Dim 语句](../../../../visual-basic/language-reference/statements/dim-statement.md)声明它们, 无论是还是不带[Static](../../../../visual-basic/language-reference/modifiers/static.md)关键字。</span><span class="sxs-lookup"><span data-stu-id="db702-147">You declare them with the [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md), with or without the [Static](../../../../visual-basic/language-reference/modifiers/static.md) keyword.</span></span>

<span data-ttu-id="db702-148">过程和块范围密切相关。</span><span class="sxs-lookup"><span data-stu-id="db702-148">Procedure and block scope are closely related.</span></span> <span data-ttu-id="db702-149">如果在过程内但在该过程中的任何块外声明变量, 则可以将变量视为具有块范围, 其中块是整个过程。</span><span class="sxs-lookup"><span data-stu-id="db702-149">If you declare a variable inside a procedure but outside any block within that procedure, you can think of the variable as having block scope, where the block is the entire procedure.</span></span>

> [!NOTE]
> <span data-ttu-id="db702-150">所有本地元素 (即使它们是`Static`变量) 都专用于它们出现的过程。</span><span class="sxs-lookup"><span data-stu-id="db702-150">All local elements, even if they are `Static` variables, are private to the procedure in which they appear.</span></span> <span data-ttu-id="db702-151">不能在过程中使用[Public](../../../../visual-basic/language-reference/modifiers/public.md)关键字声明任何元素。</span><span class="sxs-lookup"><span data-stu-id="db702-151">You cannot declare any element using the [Public](../../../../visual-basic/language-reference/modifiers/public.md) keyword within a procedure.</span></span>

### <a name="module-scope"></a><span data-ttu-id="db702-152">模块范围</span><span class="sxs-lookup"><span data-stu-id="db702-152">Module Scope</span></span>

<span data-ttu-id="db702-153">为方便起见, 单术语*模块级别*同样适用于模块、类和结构。</span><span class="sxs-lookup"><span data-stu-id="db702-153">For convenience, the single term *module level* applies equally to modules, classes, and structures.</span></span> <span data-ttu-id="db702-154">您可以通过将声明语句置于任何过程或块的外部, 但在模块、类或结构中, 在此级别声明元素。</span><span class="sxs-lookup"><span data-stu-id="db702-154">You can declare elements at this level by placing the declaration statement outside of any procedure or block but within the module, class, or structure.</span></span>

<span data-ttu-id="db702-155">在模块级别进行声明时, 所选的访问级别将确定范围。</span><span class="sxs-lookup"><span data-stu-id="db702-155">When you make a declaration at the module level, the access level you choose determines the scope.</span></span> <span data-ttu-id="db702-156">包含模块、类或结构的命名空间还会影响范围。</span><span class="sxs-lookup"><span data-stu-id="db702-156">The namespace that contains the module, class, or structure also affects the scope.</span></span>

<span data-ttu-id="db702-157">声明[专用](../../../../visual-basic/language-reference/modifiers/private.md)访问级别的元素可用于该模块中的每个过程, 但不能用于不同模块中的任何代码。</span><span class="sxs-lookup"><span data-stu-id="db702-157">Elements for which you declare [Private](../../../../visual-basic/language-reference/modifiers/private.md) access level are available to every procedure in that module, but not to any code in a different module.</span></span> <span data-ttu-id="db702-158">如果`Dim`不使用任何访问级别关键字`Private` , 模块级别的语句将默认为。</span><span class="sxs-lookup"><span data-stu-id="db702-158">The `Dim` statement at module level defaults to `Private` if you do not use any access level keywords.</span></span> <span data-ttu-id="db702-159">但是, 可以`Private` `Dim`在语句中使用关键字, 使作用域和访问级别更明显。</span><span class="sxs-lookup"><span data-stu-id="db702-159">However, you can make the scope and access level more obvious by using the `Private` keyword in the `Dim` statement.</span></span>

<span data-ttu-id="db702-160">在下面的示例中, 模块中定义的所有过程都可以引用字符串变量`strMsg`。</span><span class="sxs-lookup"><span data-stu-id="db702-160">In the following example, all procedures defined in the module can refer to the string variable `strMsg`.</span></span> <span data-ttu-id="db702-161">调用第二个过程时, 将在对话框中显示字符串变量`strMsg`的内容。</span><span class="sxs-lookup"><span data-stu-id="db702-161">When the second procedure is called, it displays the contents of the string variable `strMsg` in a dialog box.</span></span>

```vb
' Put the following declaration at module level (not in any procedure).
Private strMsg As String
' Put the following Sub procedure in the same module.
Sub initializePrivateVariable()
    strMsg = "This variable cannot be used outside this module."
End Sub
' Put the following Sub procedure in the same module.
Sub usePrivateVariable()
    MsgBox(strMsg)
End Sub
```

### <a name="namespace-scope"></a><span data-ttu-id="db702-162">命名空间范围</span><span class="sxs-lookup"><span data-stu-id="db702-162">Namespace Scope</span></span>

<span data-ttu-id="db702-163">如果使用[Friend](../../../../visual-basic/language-reference/modifiers/friend.md)或[Public](../../../../visual-basic/language-reference/modifiers/public.md)关键字在模块级别声明一个元素, 则该元素将可用于声明该元素的整个命名空间中的所有过程。</span><span class="sxs-lookup"><span data-stu-id="db702-163">If you declare an element at module level using the [Friend](../../../../visual-basic/language-reference/modifiers/friend.md) or [Public](../../../../visual-basic/language-reference/modifiers/public.md) keyword, it becomes available to all procedures throughout the namespace in which the element is declared.</span></span> <span data-ttu-id="db702-164">对于前面的示例的以下更改, 字符串变量`strMsg`可以在其声明的命名空间中的任何位置通过代码引用。</span><span class="sxs-lookup"><span data-stu-id="db702-164">With the following alteration to the preceding example, the string variable `strMsg` can be referred to by code anywhere in the namespace of its declaration.</span></span>

```vb
' Include this declaration at module level (not inside any procedure).
Public strMsg As String
```

<span data-ttu-id="db702-165">命名空间范围包括嵌套命名空间。</span><span class="sxs-lookup"><span data-stu-id="db702-165">Namespace scope includes nested namespaces.</span></span> <span data-ttu-id="db702-166">命名空间中的可用元素也可以从嵌套在该命名空间中的任何命名空间中使用。</span><span class="sxs-lookup"><span data-stu-id="db702-166">An element available from within a namespace is also available from within any namespace nested inside that namespace.</span></span>

<span data-ttu-id="db702-167">如果你的项目不包含任何[命名空间语句](../../../../visual-basic/language-reference/statements/namespace-statement.md), 则项目中的所有内容都在相同的命名空间中。</span><span class="sxs-lookup"><span data-stu-id="db702-167">If your project does not contain any [Namespace Statement](../../../../visual-basic/language-reference/statements/namespace-statement.md)s, everything in the project is in the same namespace.</span></span> <span data-ttu-id="db702-168">在这种情况下, 可以将命名空间范围视为项目范围。</span><span class="sxs-lookup"><span data-stu-id="db702-168">In this case, namespace scope can be thought of as project scope.</span></span> <span data-ttu-id="db702-169">`Public`模块、类或结构中的元素也可用于引用其项目的任何项目。</span><span class="sxs-lookup"><span data-stu-id="db702-169">`Public` elements in a module, class, or structure are also available to any project that references their project.</span></span>

## <a name="choice-of-scope"></a><span data-ttu-id="db702-170">范围选择</span><span class="sxs-lookup"><span data-stu-id="db702-170">Choice of Scope</span></span>

<span data-ttu-id="db702-171">当你声明变量时, 在选择其作用域时应牢记以下几点。</span><span class="sxs-lookup"><span data-stu-id="db702-171">When you declare a variable, you should keep in mind the following points when choosing its scope.</span></span>

### <a name="advantages-of-local-variables"></a><span data-ttu-id="db702-172">局部变量的优点</span><span class="sxs-lookup"><span data-stu-id="db702-172">Advantages of Local Variables</span></span>

<span data-ttu-id="db702-173">局部变量对于任何类型的临时计算都是一个不错的选择, 原因如下:</span><span class="sxs-lookup"><span data-stu-id="db702-173">Local variables are a good choice for any kind of temporary calculation, for the following reasons:</span></span>

- <span data-ttu-id="db702-174">**避免名称冲突。**</span><span class="sxs-lookup"><span data-stu-id="db702-174">**Name Conflict Avoidance.**</span></span> <span data-ttu-id="db702-175">局部变量名称不容易发生冲突。</span><span class="sxs-lookup"><span data-stu-id="db702-175">Local variable names are not susceptible to conflict.</span></span> <span data-ttu-id="db702-176">例如, 可以创建几个不同的过程, 其中包含一个`intTemp`名为的变量。</span><span class="sxs-lookup"><span data-stu-id="db702-176">For example, you can create several different procedures containing a variable called `intTemp`.</span></span> <span data-ttu-id="db702-177">只要每个`intTemp`都声明为局部变量, 每个过程就只能识别自己的`intTemp`版本。</span><span class="sxs-lookup"><span data-stu-id="db702-177">As long as each `intTemp` is declared as a local variable, each procedure recognizes only its own version of `intTemp`.</span></span> <span data-ttu-id="db702-178">任何一个过程都可以更改其本地`intTemp`中的值, 而不会影响`intTemp`其他过程中的变量。</span><span class="sxs-lookup"><span data-stu-id="db702-178">Any one procedure can alter the value in its local `intTemp` without affecting `intTemp` variables in other procedures.</span></span>

- <span data-ttu-id="db702-179">**内存消耗。**</span><span class="sxs-lookup"><span data-stu-id="db702-179">**Memory Consumption.**</span></span> <span data-ttu-id="db702-180">局部变量仅在其过程正在运行时占用内存。</span><span class="sxs-lookup"><span data-stu-id="db702-180">Local variables consume memory only while their procedure is running.</span></span> <span data-ttu-id="db702-181">当过程返回到调用代码时, 将释放其内存。</span><span class="sxs-lookup"><span data-stu-id="db702-181">Their memory is released when the procedure returns to the calling code.</span></span> <span data-ttu-id="db702-182">相反,[共享](../../../../visual-basic/language-reference/modifiers/shared.md)和[静态](../../../../visual-basic/language-reference/modifiers/static.md)变量将消耗内存资源, 直到应用程序停止运行, 因此仅在必要时才使用它们。</span><span class="sxs-lookup"><span data-stu-id="db702-182">By contrast, [Shared](../../../../visual-basic/language-reference/modifiers/shared.md) and [Static](../../../../visual-basic/language-reference/modifiers/static.md) variables consume memory resources until your application stops running, so use them only when necessary.</span></span> <span data-ttu-id="db702-183">*实例变量*会在其实例继续存在时使用内存, 这使得它们的效率低于局部变量, 但可能更高效`Shared`。 `Static`</span><span class="sxs-lookup"><span data-stu-id="db702-183">*Instance variables* consume memory while their instance continues to exist, which makes them less efficient than local variables, but potentially more efficient than `Shared` or `Static` variables.</span></span>

### <a name="minimizing-scope"></a><span data-ttu-id="db702-184">最小化范围</span><span class="sxs-lookup"><span data-stu-id="db702-184">Minimizing Scope</span></span>

<span data-ttu-id="db702-185">通常情况下, 在声明任何变量或常量时, 最好将范围设置为尽可能缩小 (块范围是最小)。</span><span class="sxs-lookup"><span data-stu-id="db702-185">In general, when declaring any variable or constant, it is good programming practice to make the scope as narrow as possible (block scope is the narrowest).</span></span> <span data-ttu-id="db702-186">这有助于节省内存, 并最大程度地减少代码错误引用错误变量的几率。</span><span class="sxs-lookup"><span data-stu-id="db702-186">This helps conserve memory and minimizes the chances of your code erroneously referring to the wrong variable.</span></span> <span data-ttu-id="db702-187">同样, 仅当需要在过程调用之间保留变量值时, 才应将该变量声明为[静态](../../../../visual-basic/language-reference/modifiers/static.md)。</span><span class="sxs-lookup"><span data-stu-id="db702-187">Similarly, you should declare a variable to be [Static](../../../../visual-basic/language-reference/modifiers/static.md) only when it is necessary to preserve its value between procedure calls.</span></span>

## <a name="see-also"></a><span data-ttu-id="db702-188">请参阅</span><span class="sxs-lookup"><span data-stu-id="db702-188">See also</span></span>

- [<span data-ttu-id="db702-189">已声明元素的特性</span><span class="sxs-lookup"><span data-stu-id="db702-189">Declared Element Characteristics</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)
- [<span data-ttu-id="db702-190">如何：控制变量的作用域</span><span class="sxs-lookup"><span data-stu-id="db702-190">How to: Control the Scope of a Variable</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-control-the-scope-of-a-variable.md)
- [<span data-ttu-id="db702-191">生存期 (Visual Basic</span><span class="sxs-lookup"><span data-stu-id="db702-191">Lifetime in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)
- [<span data-ttu-id="db702-192">Visual Basic 中的访问级别</span><span class="sxs-lookup"><span data-stu-id="db702-192">Access levels in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [<span data-ttu-id="db702-193">对已声明元素的引用</span><span class="sxs-lookup"><span data-stu-id="db702-193">References to Declared Elements</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [<span data-ttu-id="db702-194">变量声明</span><span class="sxs-lookup"><span data-stu-id="db702-194">Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
