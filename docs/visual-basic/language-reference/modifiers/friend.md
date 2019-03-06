---
title: Friend (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Friend
helpviewer_keywords:
- Friend keyword [Visual Basic]
- Friend access modifier
- Friend keyword [Visual Basic], syntax
- Protected Friend keyword combination
- Friend keyword [Visual Basic], and Protected
ms.assetid: b664605e-1c79-4728-b996-aa59c50846bc
ms.openlocfilehash: 1e6dbaa9201d5c9cd902412797b2427ec488d014
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2019
ms.locfileid: "57371406"
---
# <a name="friend-visual-basic"></a><span data-ttu-id="d49f8-102">Friend (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d49f8-102">Friend (Visual Basic)</span></span>
<span data-ttu-id="d49f8-103">指定一个或多个声明的编程元素只能在包含其声明的程序集内访问。</span><span class="sxs-lookup"><span data-stu-id="d49f8-103">Specifies that one or more declared programming elements are accessible only from within the assembly that contains their declaration.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d49f8-104">备注</span><span class="sxs-lookup"><span data-stu-id="d49f8-104">Remarks</span></span>  
 <span data-ttu-id="d49f8-105">在许多情况下，所需编程元素，如类和结构由整个程序集，不只通过其声明的组件。</span><span class="sxs-lookup"><span data-stu-id="d49f8-105">In many cases, you want programming elements such as classes and structures to be used by the entire assembly, not only by the component that declares them.</span></span> <span data-ttu-id="d49f8-106">但是，您可能不希望其可由程序集外部的代码 （例如，如果应用程序是专有）。</span><span class="sxs-lookup"><span data-stu-id="d49f8-106">However, you might not want them to be accessible by code outside the assembly (for example, if the application is proprietary).</span></span> <span data-ttu-id="d49f8-107">如果你想要限制对这种方式中的元素的访问，可以将其声明使用`Friend`修饰符。</span><span class="sxs-lookup"><span data-stu-id="d49f8-107">If you want to limit access to an element in this way, you can declare it by using the `Friend` modifier.</span></span>  
  
 <span data-ttu-id="d49f8-108">其他类、 结构和编译到同一模块中的代码程序集可以访问所有`Friend`中该程序集的元素。</span><span class="sxs-lookup"><span data-stu-id="d49f8-108">Code in other classes, structures, and modules that are compiled to the same assembly can access all the `Friend` elements in that assembly.</span></span>  
  
 <span data-ttu-id="d49f8-109">`Friend` 访问通常是应用程序的编程元素的首选的级别和`Friend`是默认访问接口、 模块、 类或结构的级别。</span><span class="sxs-lookup"><span data-stu-id="d49f8-109">`Friend` access is often the preferred level for an application's programming elements, and `Friend` is the default access level of an interface, a module, a class, or a structure.</span></span>  
  
 <span data-ttu-id="d49f8-110">可以使用`Friend`仅在模块、 接口或命名空间级别。</span><span class="sxs-lookup"><span data-stu-id="d49f8-110">You can use `Friend` only at the module, interface, or namespace level.</span></span> <span data-ttu-id="d49f8-111">因此，对于声明上下文`Friend`元素必须是源文件、 命名空间、 接口、 模块、 类或结构，不能为一个过程。</span><span class="sxs-lookup"><span data-stu-id="d49f8-111">Therefore, the declaration context for a `Friend` element must be a source file, a namespace, an interface, a module, a class, or a structure; it can't be a procedure.</span></span>  

> [!NOTE]
> <span data-ttu-id="d49f8-112">此外可以使用[Protected Friend](protected-friend.md)访问修饰符，这使得可以从该类中，从派生类中，和在其中定义类的相同程序集内访问类成员。</span><span class="sxs-lookup"><span data-stu-id="d49f8-112">You can also use the [Protected Friend](protected-friend.md) access modifier, which makes a class member accessible from within that class, from derived classes, and from the same assembly in which the class is defined.</span></span> <span data-ttu-id="d49f8-113">若要限制中的成员在它的类并从同一程序集中的派生类访问，您可以使用[Private Protected](private-protected.md)访问修饰符。</span><span class="sxs-lookup"><span data-stu-id="d49f8-113">To restrict access to a member from within its class and from derived classes in the same assembly, you use the [Private Protected](private-protected.md) access modifier.</span></span>

 <span data-ttu-id="d49f8-114">有关的比较`Friend`和其他访问修饰符，请参阅[访问 Visual Basic 中的级别](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)。</span><span class="sxs-lookup"><span data-stu-id="d49f8-114">For a comparison of `Friend` and the other access modifiers, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d49f8-115">你可以指定另一个程序集为友元程序集，这使它可以访问所有类型和成员标记为`Friend`。</span><span class="sxs-lookup"><span data-stu-id="d49f8-115">You can specify that another assembly is a friend assembly, which allows it to access all types and members that are marked as `Friend`.</span></span> <span data-ttu-id="d49f8-116">有关详细信息，请参阅[友元程序集](../../../standard/assembly/friend-assemblies.md)。</span><span class="sxs-lookup"><span data-stu-id="d49f8-116">For more information, see [Friend Assemblies](../../../standard/assembly/friend-assemblies.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d49f8-117">示例</span><span class="sxs-lookup"><span data-stu-id="d49f8-117">Example</span></span>  
 <span data-ttu-id="d49f8-118">下面的类使用`Friend`修饰符来允许访问某些成员在同一程序集中的其他编程元素。</span><span class="sxs-lookup"><span data-stu-id="d49f8-118">The following class uses the `Friend` modifier to allow other programming elements within the same assembly to access certain members.</span></span>  
  
 [!code-vb[VbVbalrAccessModifiers#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalraccessmodifiers/vb/class1.vb#1)]  
  
## <a name="usage"></a><span data-ttu-id="d49f8-119">用法</span><span class="sxs-lookup"><span data-stu-id="d49f8-119">Usage</span></span>  
 <span data-ttu-id="d49f8-120">可以使用`Friend`修饰符在这些上下文中：</span><span class="sxs-lookup"><span data-stu-id="d49f8-120">You can use the `Friend` modifier in these contexts:</span></span>  
  
 [<span data-ttu-id="d49f8-121">Class 语句</span><span class="sxs-lookup"><span data-stu-id="d49f8-121">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [<span data-ttu-id="d49f8-122">Const 语句</span><span class="sxs-lookup"><span data-stu-id="d49f8-122">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)  
  
 [<span data-ttu-id="d49f8-123">Declare 语句</span><span class="sxs-lookup"><span data-stu-id="d49f8-123">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [<span data-ttu-id="d49f8-124">Delegate 语句</span><span class="sxs-lookup"><span data-stu-id="d49f8-124">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [<span data-ttu-id="d49f8-125">Dim 语句</span><span class="sxs-lookup"><span data-stu-id="d49f8-125">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [<span data-ttu-id="d49f8-126">Enum 语句</span><span class="sxs-lookup"><span data-stu-id="d49f8-126">Enum Statement</span></span>](../../../visual-basic/language-reference/statements/enum-statement.md)  
  
 [<span data-ttu-id="d49f8-127">Event 语句</span><span class="sxs-lookup"><span data-stu-id="d49f8-127">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [<span data-ttu-id="d49f8-128">Function 语句</span><span class="sxs-lookup"><span data-stu-id="d49f8-128">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="d49f8-129">Interface 语句</span><span class="sxs-lookup"><span data-stu-id="d49f8-129">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [<span data-ttu-id="d49f8-130">Module 语句</span><span class="sxs-lookup"><span data-stu-id="d49f8-130">Module Statement</span></span>](../../../visual-basic/language-reference/statements/module-statement.md)  
  
 [<span data-ttu-id="d49f8-131">Property 语句</span><span class="sxs-lookup"><span data-stu-id="d49f8-131">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="d49f8-132">Structure 语句</span><span class="sxs-lookup"><span data-stu-id="d49f8-132">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [<span data-ttu-id="d49f8-133">Sub 语句</span><span class="sxs-lookup"><span data-stu-id="d49f8-133">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="d49f8-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="d49f8-134">See also</span></span>
- <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>
- [<span data-ttu-id="d49f8-135">Public</span><span class="sxs-lookup"><span data-stu-id="d49f8-135">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)
- [<span data-ttu-id="d49f8-136">Protected</span><span class="sxs-lookup"><span data-stu-id="d49f8-136">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)
- [<span data-ttu-id="d49f8-137">Private</span><span class="sxs-lookup"><span data-stu-id="d49f8-137">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)
- [<span data-ttu-id="d49f8-138">Private Protected</span><span class="sxs-lookup"><span data-stu-id="d49f8-138">Private Protected</span></span>](./private-protected.md)
- [<span data-ttu-id="d49f8-139">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="d49f8-139">Protected Friend</span></span>](./protected-friend.md)
- [<span data-ttu-id="d49f8-140">在 Visual Basic 中的访问级别</span><span class="sxs-lookup"><span data-stu-id="d49f8-140">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [<span data-ttu-id="d49f8-141">过程</span><span class="sxs-lookup"><span data-stu-id="d49f8-141">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="d49f8-142">结构</span><span class="sxs-lookup"><span data-stu-id="d49f8-142">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="d49f8-143">对象和类</span><span class="sxs-lookup"><span data-stu-id="d49f8-143">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
