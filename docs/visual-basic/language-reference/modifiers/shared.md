---
title: Shared
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
ms.openlocfilehash: 98fa25d2283408dfb80e82fbc620a1b284e5c530
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349119"
---
# <a name="shared-visual-basic"></a><span data-ttu-id="19252-102">Shared (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="19252-102">Shared (Visual Basic)</span></span>
<span data-ttu-id="19252-103">指定一个或多个已声明的编程元素与较大的类或结构关联，而不是与类或结构的特定实例相关联。</span><span class="sxs-lookup"><span data-stu-id="19252-103">Specifies that one or more declared programming elements are associated with a class or structure at large, and not with a specific instance of the class or structure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="19252-104">备注</span><span class="sxs-lookup"><span data-stu-id="19252-104">Remarks</span></span>  
  
## <a name="when-to-use-shared"></a><span data-ttu-id="19252-105">何时使用共享</span><span class="sxs-lookup"><span data-stu-id="19252-105">When to Use Shared</span></span>  
 <span data-ttu-id="19252-106">共享类或结构的成员使其可用于每个实例，而不是*共享，其中*每个实例都保留其自己的副本。</span><span class="sxs-lookup"><span data-stu-id="19252-106">Sharing a member of a class or structure makes it available to every instance, rather than *nonshared*, where each instance keeps its own copy.</span></span> <span data-ttu-id="19252-107">例如，如果将变量的值应用于整个应用程序，则此方法很有用。</span><span class="sxs-lookup"><span data-stu-id="19252-107">This is useful, for example, if the value of a variable applies to the entire application.</span></span> <span data-ttu-id="19252-108">如果声明要 `Shared`的变量，则所有实例都将访问相同的存储位置，并且如果一个实例更改该变量的值，则所有实例都将访问更新的值。</span><span class="sxs-lookup"><span data-stu-id="19252-108">If you declare that variable to be `Shared`, then all instances access the same storage location, and if one instance changes the variable's value, all instances access the updated value.</span></span>  
  
 <span data-ttu-id="19252-109">共享不会更改成员的访问级别。</span><span class="sxs-lookup"><span data-stu-id="19252-109">Sharing does not alter the access level of a member.</span></span> <span data-ttu-id="19252-110">例如，类成员可以是共享的，也可以是专用的（只能从类中访问），也可以是非共享和公共的。</span><span class="sxs-lookup"><span data-stu-id="19252-110">For example, a class member can be shared and private (accessible only from within the class), or nonshared and public.</span></span> <span data-ttu-id="19252-111">有关详细信息，请参阅[Visual Basic 中的访问级别](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)。</span><span class="sxs-lookup"><span data-stu-id="19252-111">For more information, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
## <a name="rules"></a><span data-ttu-id="19252-112">规则</span><span class="sxs-lookup"><span data-stu-id="19252-112">Rules</span></span>  
  
- <span data-ttu-id="19252-113">**声明上下文。**</span><span class="sxs-lookup"><span data-stu-id="19252-113">**Declaration Context.**</span></span> <span data-ttu-id="19252-114">只能在模块级别使用 `Shared`。</span><span class="sxs-lookup"><span data-stu-id="19252-114">You can use `Shared` only at module level.</span></span> <span data-ttu-id="19252-115">这意味着 `Shared` 元素的声明上下文必须是类或结构，不能是源文件、命名空间或过程。</span><span class="sxs-lookup"><span data-stu-id="19252-115">This means the declaration context for a `Shared` element must be a class or structure, and cannot be a source file, namespace, or procedure.</span></span>  
  
- <span data-ttu-id="19252-116">**组合修饰符。**</span><span class="sxs-lookup"><span data-stu-id="19252-116">**Combined Modifiers.**</span></span> <span data-ttu-id="19252-117">不能在同一声明中同时指定 `Shared` 和[重写](../../../visual-basic/language-reference/modifiers/overrides.md)、可[重写](../../../visual-basic/language-reference/modifiers/overridable.md)、 [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md)、 [MustOverride](../../../visual-basic/language-reference/modifiers/mustoverride.md)或[静态](../../../visual-basic/language-reference/modifiers/static.md)。</span><span class="sxs-lookup"><span data-stu-id="19252-117">You cannot specify `Shared` together with [Overrides](../../../visual-basic/language-reference/modifiers/overrides.md), [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md), [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md), [MustOverride](../../../visual-basic/language-reference/modifiers/mustoverride.md), or [Static](../../../visual-basic/language-reference/modifiers/static.md) in the same declaration.</span></span>  
  
- <span data-ttu-id="19252-118">**访问.**</span><span class="sxs-lookup"><span data-stu-id="19252-118">**Accessing.**</span></span> <span data-ttu-id="19252-119">使用共享元素的类或结构名称（而不是其类或结构的特定实例的变量名称）来限定共享元素。</span><span class="sxs-lookup"><span data-stu-id="19252-119">You access a shared element by qualifying it with its class or structure name, not with the variable name of a specific instance of its class or structure.</span></span> <span data-ttu-id="19252-120">甚至不必创建类或结构的实例即可访问其共享成员。</span><span class="sxs-lookup"><span data-stu-id="19252-120">You do not even have to create an instance of a class or structure to access its shared members.</span></span>  
  
     <span data-ttu-id="19252-121">下面的示例调用 <xref:System.Double.IsNaN%2A> <xref:System.Double> 结构公开的共享过程。</span><span class="sxs-lookup"><span data-stu-id="19252-121">The following example calls the shared procedure <xref:System.Double.IsNaN%2A> exposed by the <xref:System.Double> structure.</span></span>  
  
     `If Double.IsNaN(result) Then MsgBox("Result is mathematically undefined.")`  
  
- <span data-ttu-id="19252-122">**隐式共享。**</span><span class="sxs-lookup"><span data-stu-id="19252-122">**Implicit Sharing.**</span></span> <span data-ttu-id="19252-123">不能在[Const 语句](../../../visual-basic/language-reference/statements/const-statement.md)中使用 `Shared` 修饰符，而是隐式共享常量。</span><span class="sxs-lookup"><span data-stu-id="19252-123">You cannot use the `Shared` modifier in a [Const Statement](../../../visual-basic/language-reference/statements/const-statement.md), but constants are implicitly shared.</span></span> <span data-ttu-id="19252-124">同样，你不能声明要 `Shared`的模块或接口的成员，但它们是隐式共享的。</span><span class="sxs-lookup"><span data-stu-id="19252-124">Similarly, you cannot declare a member of a module or an interface to be `Shared`, but they are implicitly shared.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="19252-125">行为</span><span class="sxs-lookup"><span data-stu-id="19252-125">Behavior</span></span>  
  
- <span data-ttu-id="19252-126">**储存.**</span><span class="sxs-lookup"><span data-stu-id="19252-126">**Storage.**</span></span> <span data-ttu-id="19252-127">共享的变量或事件只存储在内存中，无论您创建的是多少或几个实例的类或结构。</span><span class="sxs-lookup"><span data-stu-id="19252-127">A shared variable or event is stored in memory only once, no matter how many or few instances you create of its class or structure.</span></span> <span data-ttu-id="19252-128">同样，共享过程或属性仅保存一组局部变量。</span><span class="sxs-lookup"><span data-stu-id="19252-128">Similarly, a shared procedure or property holds only one set of local variables.</span></span>  
  
- <span data-ttu-id="19252-129">**通过实例变量访问。**</span><span class="sxs-lookup"><span data-stu-id="19252-129">**Accessing through an Instance Variable.**</span></span> <span data-ttu-id="19252-130">可以通过使用包含其类或结构的特定实例的变量的名称来限定共享元素，从而访问该共享元素。</span><span class="sxs-lookup"><span data-stu-id="19252-130">It is possible to access a shared element by qualifying it with the name of a variable that contains a specific instance of its class or structure.</span></span> <span data-ttu-id="19252-131">虽然这通常按预期方式工作，但编译器会生成一条警告消息，并通过类或结构名称而不是变量来进行访问。</span><span class="sxs-lookup"><span data-stu-id="19252-131">Although this usually works as expected, the compiler generates a warning message and makes the access through the class or structure name instead of the variable.</span></span>  
  
- <span data-ttu-id="19252-132">**通过实例表达式访问。**</span><span class="sxs-lookup"><span data-stu-id="19252-132">**Accessing through an Instance Expression.**</span></span> <span data-ttu-id="19252-133">如果通过返回类或结构的实例的表达式访问共享元素，编译器将通过类或结构名称进行访问，而不是计算表达式。</span><span class="sxs-lookup"><span data-stu-id="19252-133">If you access a shared element through an expression that returns an instance of its class or structure, the compiler makes the access through the class or structure name instead of evaluating the expression.</span></span> <span data-ttu-id="19252-134">如果你希望表达式执行其他操作以及返回实例，则会产生意外的结果。</span><span class="sxs-lookup"><span data-stu-id="19252-134">This produces unexpected results if you intended the expression to perform other actions as well as returning the instance.</span></span> <span data-ttu-id="19252-135">下面的示例阐释了这一点。</span><span class="sxs-lookup"><span data-stu-id="19252-135">The following example illustrates this.</span></span>  
  
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
  
     <span data-ttu-id="19252-136">在前面的示例中，编译器会在代码通过实例访问共享变量 `total` 时生成一条警告消息。</span><span class="sxs-lookup"><span data-stu-id="19252-136">In the preceding example, the compiler generates a warning message both times the code accesses the shared variable `total` through an instance.</span></span> <span data-ttu-id="19252-137">在每种情况下，它会通过类 `shareTotal` 直接访问，而不会使用任何实例。</span><span class="sxs-lookup"><span data-stu-id="19252-137">In each case it makes the access directly through the class `shareTotal` and does not make use of any instance.</span></span> <span data-ttu-id="19252-138">如果对过程的预期调用 `returnClass`，这意味着它甚至不会生成对 `returnClass`的调用，因此不会执行显示 "Function returnClass （）" 的其他操作。</span><span class="sxs-lookup"><span data-stu-id="19252-138">In the case of the intended call to the procedure `returnClass`, this means it does not even generate a call to `returnClass`, so the additional action of displaying "Function returnClass() called" is not performed.</span></span>  
  
 <span data-ttu-id="19252-139">`Shared` 修饰符可用于下面的上下文中：</span><span class="sxs-lookup"><span data-stu-id="19252-139">The `Shared` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="19252-140">Dim 语句</span><span class="sxs-lookup"><span data-stu-id="19252-140">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [<span data-ttu-id="19252-141">Event 语句</span><span class="sxs-lookup"><span data-stu-id="19252-141">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [<span data-ttu-id="19252-142">Function 语句</span><span class="sxs-lookup"><span data-stu-id="19252-142">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="19252-143">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="19252-143">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
 [<span data-ttu-id="19252-144">Property 语句</span><span class="sxs-lookup"><span data-stu-id="19252-144">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="19252-145">Sub 语句</span><span class="sxs-lookup"><span data-stu-id="19252-145">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="19252-146">另请参阅</span><span class="sxs-lookup"><span data-stu-id="19252-146">See also</span></span>

- [<span data-ttu-id="19252-147">Shadows</span><span class="sxs-lookup"><span data-stu-id="19252-147">Shadows</span></span>](../../../visual-basic/language-reference/modifiers/shadows.md)
- [<span data-ttu-id="19252-148">Static</span><span class="sxs-lookup"><span data-stu-id="19252-148">Static</span></span>](../../../visual-basic/language-reference/modifiers/static.md)
- [<span data-ttu-id="19252-149">生存期（Visual Basic</span><span class="sxs-lookup"><span data-stu-id="19252-149">Lifetime in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)
- [<span data-ttu-id="19252-150">过程</span><span class="sxs-lookup"><span data-stu-id="19252-150">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="19252-151">结构</span><span class="sxs-lookup"><span data-stu-id="19252-151">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="19252-152">对象和类</span><span class="sxs-lookup"><span data-stu-id="19252-152">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
