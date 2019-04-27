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
ms.openlocfilehash: 6139af65958cefe43578f436204fa6836a71de0b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61917834"
---
# <a name="scope-in-visual-basic"></a><span data-ttu-id="fced9-102">Visual Basic 中的范围</span><span class="sxs-lookup"><span data-stu-id="fced9-102">Scope in Visual Basic</span></span>
<span data-ttu-id="fced9-103">*作用域*声明的元素是一组的所有代码都可以引用它而无需限定其名称或使其可通过[Imports 语句 （.NET Namespace 和类型）](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)。</span><span class="sxs-lookup"><span data-stu-id="fced9-103">The *scope* of a declared element is the set of all code that can refer to it without qualifying its name or making it available through an [Imports Statement (.NET Namespace and Type)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).</span></span> <span data-ttu-id="fced9-104">元素可以具有以下级别之一的作用域：</span><span class="sxs-lookup"><span data-stu-id="fced9-104">An element can have scope at one of the following levels:</span></span>  
  
|<span data-ttu-id="fced9-105">级别</span><span class="sxs-lookup"><span data-stu-id="fced9-105">Level</span></span>|<span data-ttu-id="fced9-106">描述</span><span class="sxs-lookup"><span data-stu-id="fced9-106">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="fced9-107">块范围</span><span class="sxs-lookup"><span data-stu-id="fced9-107">Block scope</span></span>|<span data-ttu-id="fced9-108">在声明它仅在代码中的可用块</span><span class="sxs-lookup"><span data-stu-id="fced9-108">Available only within the code block in which it is declared</span></span>|  
|<span data-ttu-id="fced9-109">过程范围</span><span class="sxs-lookup"><span data-stu-id="fced9-109">Procedure scope</span></span>|<span data-ttu-id="fced9-110">适用于在其中声明的过程中的所有代码</span><span class="sxs-lookup"><span data-stu-id="fced9-110">Available to all code within the procedure in which it is declared</span></span>|  
|<span data-ttu-id="fced9-111">模块范围内</span><span class="sxs-lookup"><span data-stu-id="fced9-111">Module scope</span></span>|<span data-ttu-id="fced9-112">适用于在模块、 类或结构声明它的所有代码</span><span class="sxs-lookup"><span data-stu-id="fced9-112">Available to all code within the module, class, or structure in which it is declared</span></span>|  
|<span data-ttu-id="fced9-113">Namespace 作用域</span><span class="sxs-lookup"><span data-stu-id="fced9-113">Namespace scope</span></span>|<span data-ttu-id="fced9-114">适用于在其中声明的命名空间中的所有代码</span><span class="sxs-lookup"><span data-stu-id="fced9-114">Available to all code in the namespace in which it is declared</span></span>|  
  
 <span data-ttu-id="fced9-115">这些级别范围从最小 （块） 到最宽 （命名空间），其中*最小范围*意味着可以引用而无需限定的元素的代码的最小集。</span><span class="sxs-lookup"><span data-stu-id="fced9-115">These levels of scope progress from the narrowest (block) to the widest (namespace), where *narrowest scope* means the smallest set of code that can refer to the element without qualification.</span></span> <span data-ttu-id="fced9-116">有关详细信息，请参阅此页上的"级别的作用域"。</span><span class="sxs-lookup"><span data-stu-id="fced9-116">For more information, see "Levels of Scope" on this page.</span></span>  
  
## <a name="specifying-scope-and-defining-variables"></a><span data-ttu-id="fced9-117">指定作用域，以及定义变量</span><span class="sxs-lookup"><span data-stu-id="fced9-117">Specifying Scope and Defining Variables</span></span>  
 <span data-ttu-id="fced9-118">在声明它时指定元素的范围。</span><span class="sxs-lookup"><span data-stu-id="fced9-118">You specify the scope of an element when you declare it.</span></span> <span data-ttu-id="fced9-119">作用域取决于以下因素：</span><span class="sxs-lookup"><span data-stu-id="fced9-119">The scope can depend on the following factors:</span></span>  
  
-   <span data-ttu-id="fced9-120">在其中声明该元素的区域 （块、 过程、 模块、 类或结构）</span><span class="sxs-lookup"><span data-stu-id="fced9-120">The region (block, procedure, module, class, or structure) in which you declare the element</span></span>  
  
-   <span data-ttu-id="fced9-121">包含元素的声明的命名空间</span><span class="sxs-lookup"><span data-stu-id="fced9-121">The namespace containing the element's declaration</span></span>  
  
-   <span data-ttu-id="fced9-122">为元素声明的访问级别</span><span class="sxs-lookup"><span data-stu-id="fced9-122">The access level you declare for the element</span></span>  
  
 <span data-ttu-id="fced9-123">时要格外小心定义变量具有相同名称但不同的作用域，因为这样做可能会导致意外结果。</span><span class="sxs-lookup"><span data-stu-id="fced9-123">Use care when you define variables with the same name but different scope, because doing so can lead to unexpected results.</span></span> <span data-ttu-id="fced9-124">有关详细信息，请参阅 [References to Declared Elements](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)。</span><span class="sxs-lookup"><span data-stu-id="fced9-124">For more information, see [References to Declared Elements](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span></span>  
  
## <a name="levels-of-scope"></a><span data-ttu-id="fced9-125">级别的作用域</span><span class="sxs-lookup"><span data-stu-id="fced9-125">Levels of Scope</span></span>  
 <span data-ttu-id="fced9-126">编程元素是在整个声明它的区域中可用。</span><span class="sxs-lookup"><span data-stu-id="fced9-126">A programming element is available throughout the region in which you declare it.</span></span> <span data-ttu-id="fced9-127">同一区域中的所有代码可以无需限定其名称都引用该元素。</span><span class="sxs-lookup"><span data-stu-id="fced9-127">All code in the same region can refer to the element without qualifying its name.</span></span>  
  
### <a name="block-scope"></a><span data-ttu-id="fced9-128">块范围</span><span class="sxs-lookup"><span data-stu-id="fced9-128">Block Scope</span></span>  
 <span data-ttu-id="fced9-129">块是一组语句包含在启动和终止声明语句，如下所示：</span><span class="sxs-lookup"><span data-stu-id="fced9-129">A block is a set of statements enclosed within initiating and terminating declaration statements, such as the following:</span></span>  
  
-   <span data-ttu-id="fced9-130">`Do` 和 `Loop`</span><span class="sxs-lookup"><span data-stu-id="fced9-130">`Do` and `Loop`</span></span>  
  
-   <span data-ttu-id="fced9-131">`For` [`Each`] 和 `Next`</span><span class="sxs-lookup"><span data-stu-id="fced9-131">`For` [`Each`] and `Next`</span></span>  
  
-   <span data-ttu-id="fced9-132">`If` 和 `End If`</span><span class="sxs-lookup"><span data-stu-id="fced9-132">`If` and `End If`</span></span>  
  
-   <span data-ttu-id="fced9-133">`Select` 和 `End Select`</span><span class="sxs-lookup"><span data-stu-id="fced9-133">`Select` and `End Select`</span></span>  
  
-   <span data-ttu-id="fced9-134">`SyncLock` 和 `End SyncLock`</span><span class="sxs-lookup"><span data-stu-id="fced9-134">`SyncLock` and `End SyncLock`</span></span>  
  
-   <span data-ttu-id="fced9-135">`Try` 和 `End Try`</span><span class="sxs-lookup"><span data-stu-id="fced9-135">`Try` and `End Try`</span></span>  
  
-   <span data-ttu-id="fced9-136">`While` 和 `End While`</span><span class="sxs-lookup"><span data-stu-id="fced9-136">`While` and `End While`</span></span>  
  
-   <span data-ttu-id="fced9-137">`With` 和 `End With`</span><span class="sxs-lookup"><span data-stu-id="fced9-137">`With` and `End With`</span></span>  
  
 <span data-ttu-id="fced9-138">如果您声明一个块内的变量，可以仅在该块中使用它。</span><span class="sxs-lookup"><span data-stu-id="fced9-138">If you declare a variable within a block, you can use it only within that block.</span></span> <span data-ttu-id="fced9-139">在下面的示例中，整数变量的作用域`cube`是块之间`If`和`End If`，你可以不再引用`cube`时将执行传递到块之外。</span><span class="sxs-lookup"><span data-stu-id="fced9-139">In the following example, the scope of the integer variable `cube` is the block between `If` and `End If`, and you can no longer refer to `cube` when execution passes out of the block.</span></span>  
  
```  
If n < 1291 Then  
    Dim cube As Integer  
    cube = n ^ 3  
End If  
```  
  
> [!NOTE]
>  <span data-ttu-id="fced9-140">即使变量的作用域仅限于一个块，其生存期内仍为整个过程。</span><span class="sxs-lookup"><span data-stu-id="fced9-140">Even if the scope of a variable is limited to a block, its lifetime is still that of the entire procedure.</span></span> <span data-ttu-id="fced9-141">如果在该过程一次输入块，每个块变量将保留以前的值。</span><span class="sxs-lookup"><span data-stu-id="fced9-141">If you enter the block more than once during the procedure, each block variable retains its previous value.</span></span> <span data-ttu-id="fced9-142">若要避免这种情况中的意外的结果，明智的做法是在块的开始处的块变量进行初始化。</span><span class="sxs-lookup"><span data-stu-id="fced9-142">To avoid unexpected results in such a case, it is wise to initialize block variables at the beginning of the block.</span></span>  
  
### <a name="procedure-scope"></a><span data-ttu-id="fced9-143">过程范围</span><span class="sxs-lookup"><span data-stu-id="fced9-143">Procedure Scope</span></span>  
 <span data-ttu-id="fced9-144">一个过程中声明的元素不在该过程外可用。</span><span class="sxs-lookup"><span data-stu-id="fced9-144">An element declared within a procedure is not available outside that procedure.</span></span> <span data-ttu-id="fced9-145">仅包含声明的过程可以使用它。</span><span class="sxs-lookup"><span data-stu-id="fced9-145">Only the procedure that contains the declaration can use it.</span></span> <span data-ttu-id="fced9-146">在此级别的变量是也称为*局部变量*。</span><span class="sxs-lookup"><span data-stu-id="fced9-146">Variables at this level are also known as *local variables*.</span></span> <span data-ttu-id="fced9-147">将它们与声明[Dim 语句](../../../../visual-basic/language-reference/statements/dim-statement.md)用或者不用[静态](../../../../visual-basic/language-reference/modifiers/static.md)关键字。</span><span class="sxs-lookup"><span data-stu-id="fced9-147">You declare them with the [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md), with or without the [Static](../../../../visual-basic/language-reference/modifiers/static.md) keyword.</span></span>  
  
 <span data-ttu-id="fced9-148">过程和块范围关系十分紧密。</span><span class="sxs-lookup"><span data-stu-id="fced9-148">Procedure and block scope are closely related.</span></span> <span data-ttu-id="fced9-149">如果要声明的变量在过程内，但在该过程中的任何块外，您可以将变量作为具有块范围，其中块就是整个过程。</span><span class="sxs-lookup"><span data-stu-id="fced9-149">If you declare a variable inside a procedure but outside any block within that procedure, you can think of the variable as having block scope, where the block is the entire procedure.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fced9-150">所有局部元素，即使它们是`Static`变量，是专用于其显示的过程。</span><span class="sxs-lookup"><span data-stu-id="fced9-150">All local elements, even if they are `Static` variables, are private to the procedure in which they appear.</span></span> <span data-ttu-id="fced9-151">不能声明任何元素使用[公共](../../../../visual-basic/language-reference/modifiers/public.md)过程中的关键字。</span><span class="sxs-lookup"><span data-stu-id="fced9-151">You cannot declare any element using the [Public](../../../../visual-basic/language-reference/modifiers/public.md) keyword within a procedure.</span></span>  
  
### <a name="module-scope"></a><span data-ttu-id="fced9-152">模块范围内</span><span class="sxs-lookup"><span data-stu-id="fced9-152">Module Scope</span></span>  
 <span data-ttu-id="fced9-153">为方便起见，单个字词*模块级别*同样适用于模块、 类和结构。</span><span class="sxs-lookup"><span data-stu-id="fced9-153">For convenience, the single term *module level* applies equally to modules, classes, and structures.</span></span> <span data-ttu-id="fced9-154">可以通过将声明语句之外的任何过程或块，但模块、 类或结构中声明此级别的元素。</span><span class="sxs-lookup"><span data-stu-id="fced9-154">You can declare elements at this level by placing the declaration statement outside of any procedure or block but within the module, class, or structure.</span></span>  
  
 <span data-ttu-id="fced9-155">在模块级别声明时，你选择的访问权限级别确定作用域。</span><span class="sxs-lookup"><span data-stu-id="fced9-155">When you make a declaration at the module level, the access level you choose determines the scope.</span></span> <span data-ttu-id="fced9-156">包含模块、 类或结构的命名空间还会影响作用域。</span><span class="sxs-lookup"><span data-stu-id="fced9-156">The namespace that contains the module, class, or structure also affects the scope.</span></span>  
  
 <span data-ttu-id="fced9-157">为其声明的元素[专用](../../../../visual-basic/language-reference/modifiers/private.md)访问级别都可用的另一个模块中的任何代码的每个过程在该模块中，而不可用。</span><span class="sxs-lookup"><span data-stu-id="fced9-157">Elements for which you declare [Private](../../../../visual-basic/language-reference/modifiers/private.md) access level are available to every procedure in that module, but not to any code in a different module.</span></span> <span data-ttu-id="fced9-158">`Dim`语句在模块级别的默认值为`Private`如果不使用任何访问级别关键字。</span><span class="sxs-lookup"><span data-stu-id="fced9-158">The `Dim` statement at module level defaults to `Private` if you do not use any access level keywords.</span></span> <span data-ttu-id="fced9-159">但是，您使用可以进行的作用域和访问级别更明显`Private`中的关键字`Dim`语句。</span><span class="sxs-lookup"><span data-stu-id="fced9-159">However, you can make the scope and access level more obvious by using the `Private` keyword in the `Dim` statement.</span></span>  
  
 <span data-ttu-id="fced9-160">模块中定义的所有过程的字符串变量，在以下示例中，可以都引用`strMsg`。</span><span class="sxs-lookup"><span data-stu-id="fced9-160">In the following example, all procedures defined in the module can refer to the string variable `strMsg`.</span></span> <span data-ttu-id="fced9-161">当调用第二个过程时，它将显示的字符串变量的内容`strMsg`对话框框中。</span><span class="sxs-lookup"><span data-stu-id="fced9-161">When the second procedure is called, it displays the contents of the string variable `strMsg` in a dialog box.</span></span>  
  
```  
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
  
### <a name="namespace-scope"></a><span data-ttu-id="fced9-162">Namespace 作用域</span><span class="sxs-lookup"><span data-stu-id="fced9-162">Namespace Scope</span></span>  
 <span data-ttu-id="fced9-163">如果声明在模块级别使用的元素[友元](../../../../visual-basic/language-reference/modifiers/friend.md)或[公共](../../../../visual-basic/language-reference/modifiers/public.md)关键字，将其提供给整个在其中声明该元素的命名空间的所有过程。</span><span class="sxs-lookup"><span data-stu-id="fced9-163">If you declare an element at module level using the [Friend](../../../../visual-basic/language-reference/modifiers/friend.md) or [Public](../../../../visual-basic/language-reference/modifiers/public.md) keyword, it becomes available to all procedures throughout the namespace in which the element is declared.</span></span> <span data-ttu-id="fced9-164">与前面的示例中，字符串变量进行如下更改`strMsg`可以由其声明的命名空间中的任意位置的代码引用。</span><span class="sxs-lookup"><span data-stu-id="fced9-164">With the following alteration to the preceding example, the string variable `strMsg` can be referred to by code anywhere in the namespace of its declaration.</span></span>  
  
```  
' Include this declaration at module level (not inside any procedure).  
Public strMsg As String  
```  
  
 <span data-ttu-id="fced9-165">Namespace 作用域包括嵌套的命名空间。</span><span class="sxs-lookup"><span data-stu-id="fced9-165">Namespace scope includes nested namespaces.</span></span> <span data-ttu-id="fced9-166">可从命名空间内的元素也是可从嵌套在该命名空间内的任何命名空间。</span><span class="sxs-lookup"><span data-stu-id="fced9-166">An element available from within a namespace is also available from within any namespace nested inside that namespace.</span></span>  
  
 <span data-ttu-id="fced9-167">如果你的项目不包含任何[Namespace 语句](../../../../visual-basic/language-reference/statements/namespace-statement.md)s，项目中的所有内容都是相同的命名空间中。</span><span class="sxs-lookup"><span data-stu-id="fced9-167">If your project does not contain any [Namespace Statement](../../../../visual-basic/language-reference/statements/namespace-statement.md)s, everything in the project is in the same namespace.</span></span> <span data-ttu-id="fced9-168">在这种情况下，可以将命名空间范围视为项目范围。</span><span class="sxs-lookup"><span data-stu-id="fced9-168">In this case, namespace scope can be thought of as project scope.</span></span> <span data-ttu-id="fced9-169">`Public` 模块、 类或结构中的元素也是可用于引用其项目的任何项目。</span><span class="sxs-lookup"><span data-stu-id="fced9-169">`Public` elements in a module, class, or structure are also available to any project that references their project.</span></span>  
  
## <a name="choice-of-scope"></a><span data-ttu-id="fced9-170">所选的作用域</span><span class="sxs-lookup"><span data-stu-id="fced9-170">Choice of Scope</span></span>  
 <span data-ttu-id="fced9-171">在声明变量时，您应记住以下几点选择其作用域内时。</span><span class="sxs-lookup"><span data-stu-id="fced9-171">When you declare a variable, you should keep in mind the following points when choosing its scope.</span></span>  
  
### <a name="advantages-of-local-variables"></a><span data-ttu-id="fced9-172">本地变量的优点</span><span class="sxs-lookup"><span data-stu-id="fced9-172">Advantages of Local Variables</span></span>  
 <span data-ttu-id="fced9-173">本地变量是出于以下原因适合用于临时计算的任何类型：</span><span class="sxs-lookup"><span data-stu-id="fced9-173">Local variables are a good choice for any kind of temporary calculation, for the following reasons:</span></span>  
  
-   <span data-ttu-id="fced9-174">**避免名称冲突。**</span><span class="sxs-lookup"><span data-stu-id="fced9-174">**Name Conflict Avoidance.**</span></span> <span data-ttu-id="fced9-175">本地变量名称不容易发生冲突。</span><span class="sxs-lookup"><span data-stu-id="fced9-175">Local variable names are not susceptible to conflict.</span></span> <span data-ttu-id="fced9-176">例如，可以创建多个不同的过程包含一个名为变量`intTemp`。</span><span class="sxs-lookup"><span data-stu-id="fced9-176">For example, you can create several different procedures containing a variable called `intTemp`.</span></span> <span data-ttu-id="fced9-177">只要每个`intTemp`被声明为局部变量，每个过程识别其自己的版本的`intTemp`。</span><span class="sxs-lookup"><span data-stu-id="fced9-177">As long as each `intTemp` is declared as a local variable, each procedure recognizes only its own version of `intTemp`.</span></span> <span data-ttu-id="fced9-178">任何一个步骤可能会更改其本地中的值`intTemp`而不会影响`intTemp`其他过程中的变量。</span><span class="sxs-lookup"><span data-stu-id="fced9-178">Any one procedure can alter the value in its local `intTemp` without affecting `intTemp` variables in other procedures.</span></span>  
  
-   <span data-ttu-id="fced9-179">**内存占用情况。**</span><span class="sxs-lookup"><span data-stu-id="fced9-179">**Memory Consumption.**</span></span> <span data-ttu-id="fced9-180">本地变量仅在其过程运行时占用的内存。</span><span class="sxs-lookup"><span data-stu-id="fced9-180">Local variables consume memory only while their procedure is running.</span></span> <span data-ttu-id="fced9-181">该过程返回到调用代码时，会释放其内存。</span><span class="sxs-lookup"><span data-stu-id="fced9-181">Their memory is released when the procedure returns to the calling code.</span></span> <span data-ttu-id="fced9-182">与此相反，[共享](../../../../visual-basic/language-reference/modifiers/shared.md)并[静态](../../../../visual-basic/language-reference/modifiers/static.md)变量消耗内存资源，直到你的应用程序停止运行，因此，它们仅在必要时使用。</span><span class="sxs-lookup"><span data-stu-id="fced9-182">By contrast, [Shared](../../../../visual-basic/language-reference/modifiers/shared.md) and [Static](../../../../visual-basic/language-reference/modifiers/static.md) variables consume memory resources until your application stops running, so use them only when necessary.</span></span> <span data-ttu-id="fced9-183">*实例变量*占用内存实例继续存在，这使它们更少比本地变量有效，但可能会比效率更高`Shared`或`Static`变量。</span><span class="sxs-lookup"><span data-stu-id="fced9-183">*Instance variables* consume memory while their instance continues to exist, which makes them less efficient than local variables, but potentially more efficient than `Shared` or `Static` variables.</span></span>  
  
### <a name="minimizing-scope"></a><span data-ttu-id="fced9-184">最大程度减少作用域</span><span class="sxs-lookup"><span data-stu-id="fced9-184">Minimizing Scope</span></span>  
 <span data-ttu-id="fced9-185">一般情况下，当声明的任何变量或常量时，它编程最佳做法是使其范围尽可能窄 （块范围是最小）。</span><span class="sxs-lookup"><span data-stu-id="fced9-185">In general, when declaring any variable or constant, it is good programming practice to make the scope as narrow as possible (block scope is the narrowest).</span></span> <span data-ttu-id="fced9-186">这有助于节约内存和最大程度减少你错误地引用错误的变量的代码的可能性。</span><span class="sxs-lookup"><span data-stu-id="fced9-186">This helps conserve memory and minimizes the chances of your code erroneously referring to the wrong variable.</span></span> <span data-ttu-id="fced9-187">同样，应将变量声明[静态](../../../../visual-basic/language-reference/modifiers/static.md)仅当有必要过程调用之间保留值。</span><span class="sxs-lookup"><span data-stu-id="fced9-187">Similarly, you should declare a variable to be [Static](../../../../visual-basic/language-reference/modifiers/static.md) only when it is necessary to preserve its value between procedure calls.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fced9-188">请参阅</span><span class="sxs-lookup"><span data-stu-id="fced9-188">See also</span></span>

- [<span data-ttu-id="fced9-189">已声明元素的特性</span><span class="sxs-lookup"><span data-stu-id="fced9-189">Declared Element Characteristics</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)
- [<span data-ttu-id="fced9-190">如何：控制变量的作用域</span><span class="sxs-lookup"><span data-stu-id="fced9-190">How to: Control the Scope of a Variable</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-control-the-scope-of-a-variable.md)
- [<span data-ttu-id="fced9-191">在 Visual Basic 中的生存期</span><span class="sxs-lookup"><span data-stu-id="fced9-191">Lifetime in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)
- [<span data-ttu-id="fced9-192">在 Visual Basic 中的访问级别</span><span class="sxs-lookup"><span data-stu-id="fced9-192">Access levels in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [<span data-ttu-id="fced9-193">对已声明元素的引用</span><span class="sxs-lookup"><span data-stu-id="fced9-193">References to Declared Elements</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [<span data-ttu-id="fced9-194">变量声明</span><span class="sxs-lookup"><span data-stu-id="fced9-194">Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
