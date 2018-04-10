---
title: Protected (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Protected
helpviewer_keywords:
- Protected Friend keyword combination
- Protected keyword [Visual Basic], and Friend
- Protected keyword [Visual Basic], syntax
- Protected access modifier
- Protected keyword [Visual Basic]
ms.assetid: 74ad3d56-309f-49d2-b60c-1d0157d010e8
caps.latest.revision: 16
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2d0cc7a0cb626a9ec8e2a0e47abc02e5268aed56
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="protected-visual-basic"></a><span data-ttu-id="3aeff-102">Protected (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3aeff-102">Protected (Visual Basic)</span></span>
<span data-ttu-id="3aeff-103">指定的一个或多个已声明的编程元素都可以访问只能从在其自身的类或从派生类。</span><span class="sxs-lookup"><span data-stu-id="3aeff-103">Specifies that one or more declared programming elements are accessible only from within their own class or from a derived class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3aeff-104">备注</span><span class="sxs-lookup"><span data-stu-id="3aeff-104">Remarks</span></span>  
 <span data-ttu-id="3aeff-105">类中声明的编程元素有时包含敏感数据或受限制的代码，并且你想要限制对元素的访问。</span><span class="sxs-lookup"><span data-stu-id="3aeff-105">Sometimes a programming element declared in a class contains sensitive data or restricted code, and you want to limit access to the element.</span></span> <span data-ttu-id="3aeff-106">但是，如果类是可继承，且希望派生类的层次结构，它可能有必要为这些派生的类进行访问的数据或代码。</span><span class="sxs-lookup"><span data-stu-id="3aeff-106">However, if the class is inheritable and you expect a hierarchy of derived classes, it might be necessary for these derived classes to access the data or code.</span></span> <span data-ttu-id="3aeff-107">在这种情况下，你希望可以访问同时从基类和所有的派生类中的元素。</span><span class="sxs-lookup"><span data-stu-id="3aeff-107">In such a case, you want the element to be accessible both from the base class and from all derived classes.</span></span> <span data-ttu-id="3aeff-108">若要限制到这种方式中的元素的访问，可将其与声明`Protected`。</span><span class="sxs-lookup"><span data-stu-id="3aeff-108">To limit access to an element in this manner, you can declare it with `Protected`.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="3aeff-109">规则</span><span class="sxs-lookup"><span data-stu-id="3aeff-109">Rules</span></span>  
  
-   <span data-ttu-id="3aeff-110">**声明上下文。**</span><span class="sxs-lookup"><span data-stu-id="3aeff-110">**Declaration Context.**</span></span> <span data-ttu-id="3aeff-111">你可以使用`Protected`只能在类级别。</span><span class="sxs-lookup"><span data-stu-id="3aeff-111">You can use `Protected` only at class level.</span></span> <span data-ttu-id="3aeff-112">这意味着的声明上下文`Protected`元素必须是类，并且不能为源文件、 命名空间、 接口、 模块、 结构或过程。</span><span class="sxs-lookup"><span data-stu-id="3aeff-112">This means the declaration context for a `Protected` element must be a class, and cannot be a source file, namespace, interface, module, structure, or procedure.</span></span>  
  
-   <span data-ttu-id="3aeff-113">**组合的修饰符。**</span><span class="sxs-lookup"><span data-stu-id="3aeff-113">**Combined Modifiers.**</span></span> <span data-ttu-id="3aeff-114">你可以使用`Protected`修饰符一起与[友元](../../../visual-basic/language-reference/modifiers/friend.md)同一声明中的修饰符。</span><span class="sxs-lookup"><span data-stu-id="3aeff-114">You can use the `Protected` modifier together with the [Friend](../../../visual-basic/language-reference/modifiers/friend.md) modifier in the same declaration.</span></span> <span data-ttu-id="3aeff-115">这种组合使得可以从同一程序集，从其自身的类，以及从派生类中的任何位置访问已声明的元素。</span><span class="sxs-lookup"><span data-stu-id="3aeff-115">This combination makes the declared elements accessible from anywhere in the same assembly, from their own class, and from derived classes.</span></span> <span data-ttu-id="3aeff-116">你可以指定`Protected Friend`仅适用于的类的成员。</span><span class="sxs-lookup"><span data-stu-id="3aeff-116">You can specify `Protected Friend` only on members of classes.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="3aeff-117">行为</span><span class="sxs-lookup"><span data-stu-id="3aeff-117">Behavior</span></span>  
  
-   <span data-ttu-id="3aeff-118">**访问级别。**</span><span class="sxs-lookup"><span data-stu-id="3aeff-118">**Access Level.**</span></span> <span data-ttu-id="3aeff-119">类中的所有代码可以都访问其元素。</span><span class="sxs-lookup"><span data-stu-id="3aeff-119">All code in a class can access its elements.</span></span> <span data-ttu-id="3aeff-120">任何派生自的基类的类中的代码可以访问所有`Protected`元素的基类。</span><span class="sxs-lookup"><span data-stu-id="3aeff-120">Code in any class that derives from a base class can access all the `Protected` elements of the base class.</span></span> <span data-ttu-id="3aeff-121">对派生的每一代是如此。</span><span class="sxs-lookup"><span data-stu-id="3aeff-121">This is true for all generations of derivation.</span></span> <span data-ttu-id="3aeff-122">这意味着，一个类可以访问`Protected`元素的基类的基类，依次类推。</span><span class="sxs-lookup"><span data-stu-id="3aeff-122">This means that a class can access `Protected` elements of the base class of the base class, and so on.</span></span>  
  
     <span data-ttu-id="3aeff-123">受保护的访问不是超集或友元访问权限的子集。</span><span class="sxs-lookup"><span data-stu-id="3aeff-123">Protected access is not a superset or subset of friend access.</span></span>  
  
-   <span data-ttu-id="3aeff-124">**访问修饰符。**</span><span class="sxs-lookup"><span data-stu-id="3aeff-124">**Access Modifiers.**</span></span> <span data-ttu-id="3aeff-125">指定的访问级别的关键字称为*访问修饰符*。</span><span class="sxs-lookup"><span data-stu-id="3aeff-125">The keywords that specify access level are called *access modifiers*.</span></span> <span data-ttu-id="3aeff-126">访问修饰符的比较，请参阅[访问 Visual Basic 中的级别](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)。</span><span class="sxs-lookup"><span data-stu-id="3aeff-126">For a comparison of the access modifiers, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
 <span data-ttu-id="3aeff-127">`Protected` 修饰符可用于下面的上下文中：</span><span class="sxs-lookup"><span data-stu-id="3aeff-127">The `Protected` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="3aeff-128">Class 语句</span><span class="sxs-lookup"><span data-stu-id="3aeff-128">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [<span data-ttu-id="3aeff-129">Const 语句</span><span class="sxs-lookup"><span data-stu-id="3aeff-129">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)  
  
 [<span data-ttu-id="3aeff-130">Declare 语句</span><span class="sxs-lookup"><span data-stu-id="3aeff-130">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [<span data-ttu-id="3aeff-131">Delegate 语句</span><span class="sxs-lookup"><span data-stu-id="3aeff-131">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [<span data-ttu-id="3aeff-132">Dim 语句</span><span class="sxs-lookup"><span data-stu-id="3aeff-132">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [<span data-ttu-id="3aeff-133">Enum 语句</span><span class="sxs-lookup"><span data-stu-id="3aeff-133">Enum Statement</span></span>](../../../visual-basic/language-reference/statements/enum-statement.md)  
  
 [<span data-ttu-id="3aeff-134">Event 语句</span><span class="sxs-lookup"><span data-stu-id="3aeff-134">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [<span data-ttu-id="3aeff-135">Function 语句</span><span class="sxs-lookup"><span data-stu-id="3aeff-135">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="3aeff-136">Interface 语句</span><span class="sxs-lookup"><span data-stu-id="3aeff-136">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [<span data-ttu-id="3aeff-137">Property 语句</span><span class="sxs-lookup"><span data-stu-id="3aeff-137">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="3aeff-138">Structure 语句</span><span class="sxs-lookup"><span data-stu-id="3aeff-138">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [<span data-ttu-id="3aeff-139">Sub 语句</span><span class="sxs-lookup"><span data-stu-id="3aeff-139">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="3aeff-140">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3aeff-140">See Also</span></span>  
 [<span data-ttu-id="3aeff-141">Public</span><span class="sxs-lookup"><span data-stu-id="3aeff-141">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)  
 [<span data-ttu-id="3aeff-142">Friend</span><span class="sxs-lookup"><span data-stu-id="3aeff-142">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)  
 [<span data-ttu-id="3aeff-143">Private</span><span class="sxs-lookup"><span data-stu-id="3aeff-143">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)  
 [<span data-ttu-id="3aeff-144">在 Visual Basic 中的访问级别</span><span class="sxs-lookup"><span data-stu-id="3aeff-144">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)  
 [<span data-ttu-id="3aeff-145">过程</span><span class="sxs-lookup"><span data-stu-id="3aeff-145">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)  
 [<span data-ttu-id="3aeff-146">结构</span><span class="sxs-lookup"><span data-stu-id="3aeff-146">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [<span data-ttu-id="3aeff-147">对象和类</span><span class="sxs-lookup"><span data-stu-id="3aeff-147">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
