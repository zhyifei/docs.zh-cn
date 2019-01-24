---
title: Shared (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Shared
helpviewer_keywords:
- Shared keyword [Visual Basic]
- members [Visual Basic], shared
- shared members
- nonshared
- shared [elements VB]
- elements [Visual Basic], shared
ms.assetid: 2bf7cf2c-b0dd-485e-8749-b5d674dab4cd
ms.openlocfilehash: 001baa8d3cbd294772bef634825c67ea13b23458
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54597276"
---
# <a name="shared-visual-basic"></a><span data-ttu-id="ae74e-102">Shared (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ae74e-102">Shared (Visual Basic)</span></span>
<span data-ttu-id="ae74e-103">指定一个或多个声明的编程元素与类或结构在整体上，而不是与类或结构的特定实例相关联。</span><span class="sxs-lookup"><span data-stu-id="ae74e-103">Specifies that one or more declared programming elements are associated with a class or structure at large, and not with a specific instance of the class or structure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ae74e-104">备注</span><span class="sxs-lookup"><span data-stu-id="ae74e-104">Remarks</span></span>  
  
## <a name="when-to-use-shared"></a><span data-ttu-id="ae74e-105">何时使用共享</span><span class="sxs-lookup"><span data-stu-id="ae74e-105">When to Use Shared</span></span>  
 <span data-ttu-id="ae74e-106">共享的类或结构成员将其提供给每个实例，而非*非共享*，其中每个实例都需要其自己的副本。</span><span class="sxs-lookup"><span data-stu-id="ae74e-106">Sharing a member of a class or structure makes it available to every instance, rather than *nonshared*, where each instance keeps its own copy.</span></span> <span data-ttu-id="ae74e-107">这很有用，例如，如果变量的值适用于整个应用程序。</span><span class="sxs-lookup"><span data-stu-id="ae74e-107">This is useful, for example, if the value of a variable applies to the entire application.</span></span> <span data-ttu-id="ae74e-108">如果声明该变量为`Shared`、 所有实例都访问相同的存储位置，然后，如果一个实例更改变量的值，所有实例都都访问更新后的值。</span><span class="sxs-lookup"><span data-stu-id="ae74e-108">If you declare that variable to be `Shared`, then all instances access the same storage location, and if one instance changes the variable's value, all instances access the updated value.</span></span>  
  
 <span data-ttu-id="ae74e-109">共享不会更改成员的访问级别。</span><span class="sxs-lookup"><span data-stu-id="ae74e-109">Sharing does not alter the access level of a member.</span></span> <span data-ttu-id="ae74e-110">例如，可以共享类成员和专用 （可访问只能从类中），或非共享和公共。</span><span class="sxs-lookup"><span data-stu-id="ae74e-110">For example, a class member can be shared and private (accessible only from within the class), or nonshared and public.</span></span> <span data-ttu-id="ae74e-111">有关详细信息，请参阅[访问 Visual Basic 中的级别](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)。</span><span class="sxs-lookup"><span data-stu-id="ae74e-111">For more information, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
## <a name="rules"></a><span data-ttu-id="ae74e-112">规则</span><span class="sxs-lookup"><span data-stu-id="ae74e-112">Rules</span></span>  
  
-   <span data-ttu-id="ae74e-113">**声明上下文。**</span><span class="sxs-lookup"><span data-stu-id="ae74e-113">**Declaration Context.**</span></span> <span data-ttu-id="ae74e-114">只能在模块级别使用 `Shared`。</span><span class="sxs-lookup"><span data-stu-id="ae74e-114">You can use `Shared` only at module level.</span></span> <span data-ttu-id="ae74e-115">这意味着声明上下文`Shared`元素必须是类或结构，并且不能是源文件、 命名空间或过程。</span><span class="sxs-lookup"><span data-stu-id="ae74e-115">This means the declaration context for a `Shared` element must be a class or structure, and cannot be a source file, namespace, or procedure.</span></span>  
  
-   <span data-ttu-id="ae74e-116">**组合的修饰符。**</span><span class="sxs-lookup"><span data-stu-id="ae74e-116">**Combined Modifiers.**</span></span> <span data-ttu-id="ae74e-117">不能指定`Shared`连同[重写](../../../visual-basic/language-reference/modifiers/overrides.md)， [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md)， [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md)， [MustOverride](../../../visual-basic/language-reference/modifiers/mustoverride.md)，或[静态](../../../visual-basic/language-reference/modifiers/static.md)同一声明中。</span><span class="sxs-lookup"><span data-stu-id="ae74e-117">You cannot specify `Shared` together with [Overrides](../../../visual-basic/language-reference/modifiers/overrides.md), [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md), [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md), [MustOverride](../../../visual-basic/language-reference/modifiers/mustoverride.md), or [Static](../../../visual-basic/language-reference/modifiers/static.md) in the same declaration.</span></span>  
  
-   <span data-ttu-id="ae74e-118">**访问。**</span><span class="sxs-lookup"><span data-stu-id="ae74e-118">**Accessing.**</span></span> <span data-ttu-id="ae74e-119">通过其类或结构的名称而不是类或结构的特定实例的变量名称限定其访问的共享的元素。</span><span class="sxs-lookup"><span data-stu-id="ae74e-119">You access a shared element by qualifying it with its class or structure name, not with the variable name of a specific instance of its class or structure.</span></span> <span data-ttu-id="ae74e-120">甚至不需要创建类或结构来访问它的共享的成员的实例。</span><span class="sxs-lookup"><span data-stu-id="ae74e-120">You do not even have to create an instance of a class or structure to access its shared members.</span></span>  
  
     <span data-ttu-id="ae74e-121">下面的示例调用共享的过程<xref:System.Double.IsNaN%2A>公开的<xref:System.Double>结构。</span><span class="sxs-lookup"><span data-stu-id="ae74e-121">The following example calls the shared procedure <xref:System.Double.IsNaN%2A> exposed by the <xref:System.Double> structure.</span></span>  
  
     `If Double.IsNaN(result) Then MsgBox("Result is mathematically undefined.")`  
  
-   <span data-ttu-id="ae74e-122">**隐式共享。**</span><span class="sxs-lookup"><span data-stu-id="ae74e-122">**Implicit Sharing.**</span></span> <span data-ttu-id="ae74e-123">不能使用`Shared`修饰符[Const 语句](../../../visual-basic/language-reference/statements/const-statement.md)，但常量被隐式共享。</span><span class="sxs-lookup"><span data-stu-id="ae74e-123">You cannot use the `Shared` modifier in a [Const Statement](../../../visual-basic/language-reference/statements/const-statement.md), but constants are implicitly shared.</span></span> <span data-ttu-id="ae74e-124">同样，不能声明为模块或接口的成员`Shared`，但它们会被隐式共享。</span><span class="sxs-lookup"><span data-stu-id="ae74e-124">Similarly, you cannot declare a member of a module or an interface to be `Shared`, but they are implicitly shared.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="ae74e-125">行为</span><span class="sxs-lookup"><span data-stu-id="ae74e-125">Behavior</span></span>  
  
-   <span data-ttu-id="ae74e-126">**存储。**</span><span class="sxs-lookup"><span data-stu-id="ae74e-126">**Storage.**</span></span> <span data-ttu-id="ae74e-127">只有一次，无论多少或少数几个实例创建的类或结构，在内存中存储的共享的变量或事件。</span><span class="sxs-lookup"><span data-stu-id="ae74e-127">A shared variable or event is stored in memory only once, no matter how many or few instances you create of its class or structure.</span></span> <span data-ttu-id="ae74e-128">同样，共享的过程或属性包含只有一组本地变量。</span><span class="sxs-lookup"><span data-stu-id="ae74e-128">Similarly, a shared procedure or property holds only one set of local variables.</span></span>  
  
-   <span data-ttu-id="ae74e-129">**通过实例变量访问。**</span><span class="sxs-lookup"><span data-stu-id="ae74e-129">**Accessing through an Instance Variable.**</span></span> <span data-ttu-id="ae74e-130">就可以通过用包含类或结构的特定实例的变量的名称限定其访问的共享的元素。</span><span class="sxs-lookup"><span data-stu-id="ae74e-130">It is possible to access a shared element by qualifying it with the name of a variable that contains a specific instance of its class or structure.</span></span> <span data-ttu-id="ae74e-131">虽然这通常按预期工作，编译器将生成一条警告消息，并使通过类或结构的名称，而不是变量的访问权限。</span><span class="sxs-lookup"><span data-stu-id="ae74e-131">Although this usually works as expected, the compiler generates a warning message and makes the access through the class or structure name instead of the variable.</span></span>  
  
-   <span data-ttu-id="ae74e-132">**通过的实例表达式进行访问。**</span><span class="sxs-lookup"><span data-stu-id="ae74e-132">**Accessing through an Instance Expression.**</span></span> <span data-ttu-id="ae74e-133">如果通过一个表达式，返回其类或结构的实例访问共享的元素，编译器可让通过类或结构的名称，而不是计算表达式的访问权限。</span><span class="sxs-lookup"><span data-stu-id="ae74e-133">If you access a shared element through an expression that returns an instance of its class or structure, the compiler makes the access through the class or structure name instead of evaluating the expression.</span></span> <span data-ttu-id="ae74e-134">如果你想要执行其他操作以及返回实例的表达式，这将会产生意外的结果。</span><span class="sxs-lookup"><span data-stu-id="ae74e-134">This produces unexpected results if you intended the expression to perform other actions as well as returning the instance.</span></span> <span data-ttu-id="ae74e-135">下面的示例阐释了这一点。</span><span class="sxs-lookup"><span data-stu-id="ae74e-135">The following example illustrates this.</span></span>  
  
    ```vb
    Sub main()  
        shareTotal.total = 10  
        ' The preceding line is the preferred way to access total.  
        Dim instanceVar As New shareTotal  
        instanceVar.total += 100  
        ' The preceding line generates a compiler warning message and  
        ' accesses total through class shareTotal instead of through  
        ' the variable instanceVar. This works as expected and adds  
        ' 100 to total.  
        returnClass().total += 1000  
        ' The preceding line generates a compiler warning message and  
        ' accesses total through class shareTotal instead of calling  
        ' returnClass(). This adds 1000 to total but does not work as  
        ' expected, because the MsgBox in returnClass() does not run.  
        MsgBox("Value of total is " & CStr(shareTotal.total))  
    End Sub  
    Public Function returnClass() As shareTotal  
        MsgBox("Function returnClass() called")  
        Return New shareTotal  
    End Function  
    Public Class shareTotal  
        Public Shared total As Integer  
    End Class  
    ```  
  
     <span data-ttu-id="ae74e-136">在前面的示例中，编译器将生成一条警告消息的代码可访问共享的变量这两个时间`total`通过实例。</span><span class="sxs-lookup"><span data-stu-id="ae74e-136">In the preceding example, the compiler generates a warning message both times the code accesses the shared variable `total` through an instance.</span></span> <span data-ttu-id="ae74e-137">每种情况下它都使通过类直接访问`shareTotal`，而不进行使用的任何实例。</span><span class="sxs-lookup"><span data-stu-id="ae74e-137">In each case it makes the access directly through the class `shareTotal` and does not make use of any instance.</span></span> <span data-ttu-id="ae74e-138">在对过程的预期调用的情况下`returnClass`，这意味着即使生成调用`returnClass`，因此不执行其他操作的显示"调用函数 returnClass()"。</span><span class="sxs-lookup"><span data-stu-id="ae74e-138">In the case of the intended call to the procedure `returnClass`, this means it does not even generate a call to `returnClass`, so the additional action of displaying "Function returnClass() called" is not performed.</span></span>  
  
 <span data-ttu-id="ae74e-139">`Shared` 修饰符可用于下面的上下文中：</span><span class="sxs-lookup"><span data-stu-id="ae74e-139">The `Shared` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="ae74e-140">Dim 语句</span><span class="sxs-lookup"><span data-stu-id="ae74e-140">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [<span data-ttu-id="ae74e-141">Event 语句</span><span class="sxs-lookup"><span data-stu-id="ae74e-141">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [<span data-ttu-id="ae74e-142">Function 语句</span><span class="sxs-lookup"><span data-stu-id="ae74e-142">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="ae74e-143">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="ae74e-143">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
 [<span data-ttu-id="ae74e-144">Property 语句</span><span class="sxs-lookup"><span data-stu-id="ae74e-144">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="ae74e-145">Sub 语句</span><span class="sxs-lookup"><span data-stu-id="ae74e-145">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="ae74e-146">请参阅</span><span class="sxs-lookup"><span data-stu-id="ae74e-146">See also</span></span>
- [<span data-ttu-id="ae74e-147">Shadows</span><span class="sxs-lookup"><span data-stu-id="ae74e-147">Shadows</span></span>](../../../visual-basic/language-reference/modifiers/shadows.md)
- [<span data-ttu-id="ae74e-148">Static</span><span class="sxs-lookup"><span data-stu-id="ae74e-148">Static</span></span>](../../../visual-basic/language-reference/modifiers/static.md)
- [<span data-ttu-id="ae74e-149">在 Visual Basic 中的生存期</span><span class="sxs-lookup"><span data-stu-id="ae74e-149">Lifetime in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)
- [<span data-ttu-id="ae74e-150">过程</span><span class="sxs-lookup"><span data-stu-id="ae74e-150">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="ae74e-151">结构</span><span class="sxs-lookup"><span data-stu-id="ae74e-151">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="ae74e-152">对象和类</span><span class="sxs-lookup"><span data-stu-id="ae74e-152">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
