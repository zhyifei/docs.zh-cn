---
title: Friend (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Friend
helpviewer_keywords:
- Friend keyword [Visual Basic]
- Friend access modifier
- Friend keyword [Visual Basic], syntax
- Protected Friend keyword combination
- Friend keyword [Visual Basic], and Protected
ms.assetid: b664605e-1c79-4728-b996-aa59c50846bc
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: df0e8ad1990fe7a1aa495e1794c942813cffb5bc
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="friend-visual-basic"></a><span data-ttu-id="fe677-102">Friend (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fe677-102">Friend (Visual Basic)</span></span>
<span data-ttu-id="fe677-103">指定一个或多个已声明的编程元素只能在包含其声明的程序集内访问。</span><span class="sxs-lookup"><span data-stu-id="fe677-103">Specifies that one or more declared programming elements are accessible only from within the assembly that contains their declaration.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fe677-104">备注</span><span class="sxs-lookup"><span data-stu-id="fe677-104">Remarks</span></span>  
 <span data-ttu-id="fe677-105">在许多情况下，所需编程元素，如类和结构为供由整个程序集，不仅声明它们的组件。</span><span class="sxs-lookup"><span data-stu-id="fe677-105">In many cases, you want programming elements such as classes and structures to be used by the entire assembly, not only by the component that declares them.</span></span> <span data-ttu-id="fe677-106">但是，你可能不希望它们可由程序集外部的代码 （例如，如果应用程序是专有）。</span><span class="sxs-lookup"><span data-stu-id="fe677-106">However, you might not want them to be accessible by code outside the assembly (for example, if the application is proprietary).</span></span> <span data-ttu-id="fe677-107">如果你想要限制到这种方式中的元素的访问，可以将其声明使用`Friend`修饰符。</span><span class="sxs-lookup"><span data-stu-id="fe677-107">If you want to limit access to an element in this way, you can declare it by using the `Friend` modifier.</span></span>  
  
 <span data-ttu-id="fe677-108">其他类、 结构和编译为相同的模块中的代码程序集可以访问所有`Friend`该程序集中的元素。</span><span class="sxs-lookup"><span data-stu-id="fe677-108">Code in other classes, structures, and modules that are compiled to the same assembly can access all the `Friend` elements in that assembly.</span></span>  
  
 <span data-ttu-id="fe677-109">`Friend`访问通常是应用程序的编程元素的首选的级别和`Friend`是默认访问接口、 模块、 类或结构的级别。</span><span class="sxs-lookup"><span data-stu-id="fe677-109">`Friend` access is often the preferred level for an application's programming elements, and `Friend` is the default access level of an interface, a module, a class, or a structure.</span></span>  
  
 <span data-ttu-id="fe677-110">你可以使用`Friend`只能在模块、 接口或命名空间级别。</span><span class="sxs-lookup"><span data-stu-id="fe677-110">You can use `Friend` only at the module, interface, or namespace level.</span></span> <span data-ttu-id="fe677-111">因此，声明上下文`Friend`元素必须是源文件、 命名空间、 接口、 模块、 类或结构; 它不能是一个过程。</span><span class="sxs-lookup"><span data-stu-id="fe677-111">Therefore, the declaration context for a `Friend` element must be a source file, a namespace, an interface, a module, a class, or a structure; it can't be a procedure.</span></span>  
  
 <span data-ttu-id="fe677-112">你可以使用`Friend`结合修饰符[受保护](../../../visual-basic/language-reference/modifiers/protected.md)同一声明中的修饰符。</span><span class="sxs-lookup"><span data-stu-id="fe677-112">You can use the `Friend` modifier in conjunction with the [Protected](../../../visual-basic/language-reference/modifiers/protected.md) modifier in the same declaration.</span></span> <span data-ttu-id="fe677-113">此组合授予同时`Friend`访问和上已声明的元素，这样便可从同一程序集，从其自身的类，以及从派生类中的任何位置访问受保护的访问。</span><span class="sxs-lookup"><span data-stu-id="fe677-113">This combination confers both `Friend` access and protected access on the declared elements, so they are accessible from anywhere in the same assembly, from their own class, and from derived classes.</span></span> <span data-ttu-id="fe677-114">你可以指定`Protected Friend`仅适用于的类的成员。</span><span class="sxs-lookup"><span data-stu-id="fe677-114">You can specify `Protected Friend` only on members of classes.</span></span>  
  
 <span data-ttu-id="fe677-115">有关的比较`Friend`以及其他访问修饰符，请参阅[访问 Visual Basic 中的级别](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)。</span><span class="sxs-lookup"><span data-stu-id="fe677-115">For a comparison of `Friend` and the other access modifiers, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fe677-116">你可以指定另一个程序集是友元程序集，从而使其可以访问所有类型和成员标记为`Friend`。</span><span class="sxs-lookup"><span data-stu-id="fe677-116">You can specify that another assembly is a friend assembly, which allows it to access all types and members that are marked as `Friend`.</span></span> <span data-ttu-id="fe677-117">有关详细信息，请参阅[友元程序集](../../programming-guide/concepts/assemblies-gac/friend-assemblies.md)。</span><span class="sxs-lookup"><span data-stu-id="fe677-117">For more information, see [Friend Assemblies](../../programming-guide/concepts/assemblies-gac/friend-assemblies.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="fe677-118">示例</span><span class="sxs-lookup"><span data-stu-id="fe677-118">Example</span></span>  
 <span data-ttu-id="fe677-119">下面的类使用`Friend`修饰符以允许访问某些成员同一程序集内的其他编程元素。</span><span class="sxs-lookup"><span data-stu-id="fe677-119">The following class uses the `Friend` modifier to allow other programming elements within the same assembly to access certain members.</span></span>  
  
 [!code-vb[VbVbalrAccessModifiers#1](../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/friend_1.vb)]  
  
## <a name="usage"></a><span data-ttu-id="fe677-120">用法</span><span class="sxs-lookup"><span data-stu-id="fe677-120">Usage</span></span>  
 <span data-ttu-id="fe677-121">你可以使用`Friend`修饰符在这两个上下文：</span><span class="sxs-lookup"><span data-stu-id="fe677-121">You can use the `Friend` modifier in these contexts:</span></span>  
  
 [<span data-ttu-id="fe677-122">Class 语句</span><span class="sxs-lookup"><span data-stu-id="fe677-122">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [<span data-ttu-id="fe677-123">Const 语句</span><span class="sxs-lookup"><span data-stu-id="fe677-123">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)  
  
 [<span data-ttu-id="fe677-124">Declare 语句</span><span class="sxs-lookup"><span data-stu-id="fe677-124">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [<span data-ttu-id="fe677-125">Delegate 语句</span><span class="sxs-lookup"><span data-stu-id="fe677-125">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [<span data-ttu-id="fe677-126">Dim 语句</span><span class="sxs-lookup"><span data-stu-id="fe677-126">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [<span data-ttu-id="fe677-127">Enum 语句</span><span class="sxs-lookup"><span data-stu-id="fe677-127">Enum Statement</span></span>](../../../visual-basic/language-reference/statements/enum-statement.md)  
  
 [<span data-ttu-id="fe677-128">Event 语句</span><span class="sxs-lookup"><span data-stu-id="fe677-128">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [<span data-ttu-id="fe677-129">Function 语句</span><span class="sxs-lookup"><span data-stu-id="fe677-129">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="fe677-130">Interface 语句</span><span class="sxs-lookup"><span data-stu-id="fe677-130">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [<span data-ttu-id="fe677-131">Module 语句</span><span class="sxs-lookup"><span data-stu-id="fe677-131">Module Statement</span></span>](../../../visual-basic/language-reference/statements/module-statement.md)  
  
 [<span data-ttu-id="fe677-132">Property 语句</span><span class="sxs-lookup"><span data-stu-id="fe677-132">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="fe677-133">Structure 语句</span><span class="sxs-lookup"><span data-stu-id="fe677-133">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [<span data-ttu-id="fe677-134">Sub 语句</span><span class="sxs-lookup"><span data-stu-id="fe677-134">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="fe677-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="fe677-135">See Also</span></span>  
 <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>  
 [<span data-ttu-id="fe677-136">Public</span><span class="sxs-lookup"><span data-stu-id="fe677-136">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)  
 [<span data-ttu-id="fe677-137">Protected</span><span class="sxs-lookup"><span data-stu-id="fe677-137">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)  
 [<span data-ttu-id="fe677-138">Private</span><span class="sxs-lookup"><span data-stu-id="fe677-138">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)  
 [<span data-ttu-id="fe677-139">在 Visual Basic 中的访问级别</span><span class="sxs-lookup"><span data-stu-id="fe677-139">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)  
 [<span data-ttu-id="fe677-140">过程</span><span class="sxs-lookup"><span data-stu-id="fe677-140">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)  
 [<span data-ttu-id="fe677-141">结构</span><span class="sxs-lookup"><span data-stu-id="fe677-141">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [<span data-ttu-id="fe677-142">对象和类</span><span class="sxs-lookup"><span data-stu-id="fe677-142">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
