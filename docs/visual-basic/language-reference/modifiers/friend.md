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
ms.openlocfilehash: 2a5a2d6b9d99693a551480fa047cedf42888fdf3
ms.sourcegitcommit: 7b1ce327e8c84f115f007be4728d29a89efe11ef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/13/2019
ms.locfileid: "70969055"
---
# <a name="friend-visual-basic"></a><span data-ttu-id="470bb-102">Friend (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="470bb-102">Friend (Visual Basic)</span></span>
<span data-ttu-id="470bb-103">指定只能从包含其声明的程序集内部访问一个或多个已声明的编程元素。</span><span class="sxs-lookup"><span data-stu-id="470bb-103">Specifies that one or more declared programming elements are accessible only from within the assembly that contains their declaration.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="470bb-104">备注</span><span class="sxs-lookup"><span data-stu-id="470bb-104">Remarks</span></span>  
 <span data-ttu-id="470bb-105">在许多情况下，需要由整个程序集使用的编程元素（如类和结构），而不是由声明它们的组件使用。</span><span class="sxs-lookup"><span data-stu-id="470bb-105">In many cases, you want programming elements such as classes and structures to be used by the entire assembly, not only by the component that declares them.</span></span> <span data-ttu-id="470bb-106">但是，可能不希望程序集外部的代码（例如，应用程序是专有的）可以访问这些文件。</span><span class="sxs-lookup"><span data-stu-id="470bb-106">However, you might not want them to be accessible by code outside the assembly (for example, if the application is proprietary).</span></span> <span data-ttu-id="470bb-107">如果要以这种方式限制对某个元素的访问，则可以使用`Friend`修饰符来声明它。</span><span class="sxs-lookup"><span data-stu-id="470bb-107">If you want to limit access to an element in this way, you can declare it by using the `Friend` modifier.</span></span>  
  
 <span data-ttu-id="470bb-108">编译为同一程序集的其他类、结构和模块中的代码可以访问该程序集中`Friend`的所有元素。</span><span class="sxs-lookup"><span data-stu-id="470bb-108">Code in other classes, structures, and modules that are compiled to the same assembly can access all the `Friend` elements in that assembly.</span></span>  
  
 <span data-ttu-id="470bb-109">`Friend`访问通常是应用程序编程元素的首选级别， `Friend`是接口、模块、类或结构的默认访问级别。</span><span class="sxs-lookup"><span data-stu-id="470bb-109">`Friend` access is often the preferred level for an application's programming elements, and `Friend` is the default access level of an interface, a module, a class, or a structure.</span></span>  
  
 <span data-ttu-id="470bb-110">只能在模块`Friend` 、接口或命名空间级别使用。</span><span class="sxs-lookup"><span data-stu-id="470bb-110">You can use `Friend` only at the module, interface, or namespace level.</span></span> <span data-ttu-id="470bb-111">因此， `Friend`元素的声明上下文必须是源文件、命名空间、接口、模块、类或结构; 它不能是过程。</span><span class="sxs-lookup"><span data-stu-id="470bb-111">Therefore, the declaration context for a `Friend` element must be a source file, a namespace, an interface, a module, a class, or a structure; it can't be a procedure.</span></span>  

> [!NOTE]
> <span data-ttu-id="470bb-112">你还可以使用[受保护的 Friend](protected-friend.md)访问修饰符，使类成员可从该类、派生类和类定义的同一程序集中访问。</span><span class="sxs-lookup"><span data-stu-id="470bb-112">You can also use the [Protected Friend](protected-friend.md) access modifier, which makes a class member accessible from within that class, from derived classes, and from the same assembly in which the class is defined.</span></span> <span data-ttu-id="470bb-113">若要从同一程序集中的类和派生类中限制对成员的访问，请使用[私有受保护](private-protected.md)的访问修饰符。</span><span class="sxs-lookup"><span data-stu-id="470bb-113">To restrict access to a member from within its class and from derived classes in the same assembly, you use the [Private Protected](private-protected.md) access modifier.</span></span>

 <span data-ttu-id="470bb-114">有关和其他访问`Friend`修饰符的比较，请参阅[Visual Basic 中的访问级别](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)。</span><span class="sxs-lookup"><span data-stu-id="470bb-114">For a comparison of `Friend` and the other access modifiers, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="470bb-115">可以指定另一个程序集是友元程序集，该程序集允许其访问标记为`Friend`的所有类型和成员。</span><span class="sxs-lookup"><span data-stu-id="470bb-115">You can specify that another assembly is a friend assembly, which allows it to access all types and members that are marked as `Friend`.</span></span> <span data-ttu-id="470bb-116">有关详细信息，请参阅[友元程序集](../../../standard/assembly/friend.md)。</span><span class="sxs-lookup"><span data-stu-id="470bb-116">For more information, see [Friend Assemblies](../../../standard/assembly/friend.md).</span></span>

## <a name="example"></a><span data-ttu-id="470bb-117">示例</span><span class="sxs-lookup"><span data-stu-id="470bb-117">Example</span></span>  
 <span data-ttu-id="470bb-118">下面的类使用`Friend`修饰符允许同一程序集中的其他编程元素访问某些成员。</span><span class="sxs-lookup"><span data-stu-id="470bb-118">The following class uses the `Friend` modifier to allow other programming elements within the same assembly to access certain members.</span></span>  
  
 [!code-vb[VbVbalrAccessModifiers#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalraccessmodifiers/vb/class1.vb#1)]  
  
## <a name="usage"></a><span data-ttu-id="470bb-119">用法</span><span class="sxs-lookup"><span data-stu-id="470bb-119">Usage</span></span>  
 <span data-ttu-id="470bb-120">可以在以下上下文`Friend`中使用修饰符：</span><span class="sxs-lookup"><span data-stu-id="470bb-120">You can use the `Friend` modifier in these contexts:</span></span>  
  
 [<span data-ttu-id="470bb-121">Class 语句</span><span class="sxs-lookup"><span data-stu-id="470bb-121">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [<span data-ttu-id="470bb-122">Const 语句</span><span class="sxs-lookup"><span data-stu-id="470bb-122">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)  
  
 [<span data-ttu-id="470bb-123">Declare 语句</span><span class="sxs-lookup"><span data-stu-id="470bb-123">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [<span data-ttu-id="470bb-124">Delegate 语句</span><span class="sxs-lookup"><span data-stu-id="470bb-124">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [<span data-ttu-id="470bb-125">Dim 语句</span><span class="sxs-lookup"><span data-stu-id="470bb-125">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [<span data-ttu-id="470bb-126">Enum 语句</span><span class="sxs-lookup"><span data-stu-id="470bb-126">Enum Statement</span></span>](../../../visual-basic/language-reference/statements/enum-statement.md)  
  
 [<span data-ttu-id="470bb-127">Event 语句</span><span class="sxs-lookup"><span data-stu-id="470bb-127">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [<span data-ttu-id="470bb-128">Function 语句</span><span class="sxs-lookup"><span data-stu-id="470bb-128">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="470bb-129">Interface 语句</span><span class="sxs-lookup"><span data-stu-id="470bb-129">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [<span data-ttu-id="470bb-130">Module 语句</span><span class="sxs-lookup"><span data-stu-id="470bb-130">Module Statement</span></span>](../../../visual-basic/language-reference/statements/module-statement.md)  
  
 [<span data-ttu-id="470bb-131">Property 语句</span><span class="sxs-lookup"><span data-stu-id="470bb-131">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="470bb-132">Structure 语句</span><span class="sxs-lookup"><span data-stu-id="470bb-132">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [<span data-ttu-id="470bb-133">Sub 语句</span><span class="sxs-lookup"><span data-stu-id="470bb-133">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="470bb-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="470bb-134">See also</span></span>

- <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>
- [<span data-ttu-id="470bb-135">Public</span><span class="sxs-lookup"><span data-stu-id="470bb-135">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)
- [<span data-ttu-id="470bb-136">Protected</span><span class="sxs-lookup"><span data-stu-id="470bb-136">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)
- [<span data-ttu-id="470bb-137">Private</span><span class="sxs-lookup"><span data-stu-id="470bb-137">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)
- [<span data-ttu-id="470bb-138">Private Protected</span><span class="sxs-lookup"><span data-stu-id="470bb-138">Private Protected</span></span>](./private-protected.md)
- [<span data-ttu-id="470bb-139">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="470bb-139">Protected Friend</span></span>](./protected-friend.md)
- [<span data-ttu-id="470bb-140">Visual Basic 中的访问级别</span><span class="sxs-lookup"><span data-stu-id="470bb-140">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [<span data-ttu-id="470bb-141">过程</span><span class="sxs-lookup"><span data-stu-id="470bb-141">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="470bb-142">结构</span><span class="sxs-lookup"><span data-stu-id="470bb-142">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="470bb-143">对象和类</span><span class="sxs-lookup"><span data-stu-id="470bb-143">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
