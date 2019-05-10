---
title: Protected (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Protected
helpviewer_keywords:
- Protected Friend keyword combination
- Protected keyword [Visual Basic], and Friend
- Protected keyword [Visual Basic], syntax
- Protected access modifier
- Protected keyword [Visual Basic]
ms.assetid: 74ad3d56-309f-49d2-b60c-1d0157d010e8
ms.openlocfilehash: 86758c68f0f3bfe214a695f656d3924eadd27e31
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64642690"
---
# <a name="protected-visual-basic"></a><span data-ttu-id="ddaeb-102">Protected (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ddaeb-102">Protected (Visual Basic)</span></span>
<span data-ttu-id="ddaeb-103">指定一个或多个声明编程元素的成员访问修饰符只能从来访问其自己的类中或从派生类。</span><span class="sxs-lookup"><span data-stu-id="ddaeb-103">A member access modifier that specifies that one or more declared programming elements are accessible only from within their own class or from a derived class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ddaeb-104">备注</span><span class="sxs-lookup"><span data-stu-id="ddaeb-104">Remarks</span></span>  
 <span data-ttu-id="ddaeb-105">有时，在类中声明的编程元素包含敏感数据或受限制的代码，并且你想要限制对元素的访问。</span><span class="sxs-lookup"><span data-stu-id="ddaeb-105">Sometimes a programming element declared in a class contains sensitive data or restricted code, and you want to limit access to the element.</span></span> <span data-ttu-id="ddaeb-106">但是，如果类是可继承，并预计的派生类层次结构，它可能需要这些派生的类来访问数据或代码。</span><span class="sxs-lookup"><span data-stu-id="ddaeb-106">However, if the class is inheritable and you expect a hierarchy of derived classes, it might be necessary for these derived classes to access the data or code.</span></span> <span data-ttu-id="ddaeb-107">在这种情况下，想要从基本类和所有派生类可访问的元素。</span><span class="sxs-lookup"><span data-stu-id="ddaeb-107">In such a case, you want the element to be accessible both from the base class and from all derived classes.</span></span> <span data-ttu-id="ddaeb-108">若要限制到这种方式中的元素的访问，可将其与声明`Protected`。</span><span class="sxs-lookup"><span data-stu-id="ddaeb-108">To limit access to an element in this manner, you can declare it with `Protected`.</span></span>  

> [!NOTE]
> <span data-ttu-id="ddaeb-109">`Protected`访问修饰符可以结合这两个其他修饰符：</span><span class="sxs-lookup"><span data-stu-id="ddaeb-109">The `Protected` access modifier can be combined with two other modifiers:</span></span>
> - <span data-ttu-id="ddaeb-110">[Protected Friend](protected-friend.md)修饰符使类成员在该类中，从派生类中，和在其中定义类的相同程序集内访问。</span><span class="sxs-lookup"><span data-stu-id="ddaeb-110">The [Protected Friend](protected-friend.md) modifier makes a class member accessible from within that class, from derived classes, and from the same assembly in which the class is defined.</span></span> 
> - <span data-ttu-id="ddaeb-111">[Private Protected](private-protected.md)修饰符使类成员可访问由派生类型，但只能在其包含程序集内。</span><span class="sxs-lookup"><span data-stu-id="ddaeb-111">The [Private Protected](private-protected.md) modifier makes a class member accessible by derived types, but only within its containing assembly.</span></span>
  
## <a name="rules"></a><span data-ttu-id="ddaeb-112">规则</span><span class="sxs-lookup"><span data-stu-id="ddaeb-112">Rules</span></span>  
  
- <span data-ttu-id="ddaeb-113">**声明上下文。**</span><span class="sxs-lookup"><span data-stu-id="ddaeb-113">**Declaration Context.**</span></span> <span data-ttu-id="ddaeb-114">可以使用`Protected`仅在类级别。</span><span class="sxs-lookup"><span data-stu-id="ddaeb-114">You can use `Protected` only at the class level.</span></span> <span data-ttu-id="ddaeb-115">这意味着声明上下文`Protected`元素必须是类，且不能为源文件、 命名空间、 接口、 模块、 结构或过程。</span><span class="sxs-lookup"><span data-stu-id="ddaeb-115">This means the declaration context for a `Protected` element must be a class, and cannot be a source file, namespace, interface, module, structure, or procedure.</span></span>  

## <a name="behavior"></a><span data-ttu-id="ddaeb-116">行为</span><span class="sxs-lookup"><span data-stu-id="ddaeb-116">Behavior</span></span>  
  
- <span data-ttu-id="ddaeb-117">**访问级别。**</span><span class="sxs-lookup"><span data-stu-id="ddaeb-117">**Access Level.**</span></span> <span data-ttu-id="ddaeb-118">在类中的所有代码可以都访问它的元素。</span><span class="sxs-lookup"><span data-stu-id="ddaeb-118">All code in a class can access its elements.</span></span> <span data-ttu-id="ddaeb-119">从基类派生的任何类中的代码可以访问所有`Protected`元素的基类。</span><span class="sxs-lookup"><span data-stu-id="ddaeb-119">Code in any class that derives from a base class can access all the `Protected` elements of the base class.</span></span> <span data-ttu-id="ddaeb-120">这是派生的针对每一代，则返回 true。</span><span class="sxs-lookup"><span data-stu-id="ddaeb-120">This is true for all generations of derivation.</span></span> <span data-ttu-id="ddaeb-121">这意味着，一个类可以访问`Protected`元素的基类的基类，依次类推。</span><span class="sxs-lookup"><span data-stu-id="ddaeb-121">This means that a class can access `Protected` elements of the base class of the base class, and so on.</span></span>  
  
     <span data-ttu-id="ddaeb-122">受保护的访问不是超集或友元访问权限的子集。</span><span class="sxs-lookup"><span data-stu-id="ddaeb-122">Protected access is not a superset or subset of friend access.</span></span>  
  
- <span data-ttu-id="ddaeb-123">**访问修饰符。**</span><span class="sxs-lookup"><span data-stu-id="ddaeb-123">**Access Modifiers.**</span></span> <span data-ttu-id="ddaeb-124">指定的访问级别的关键字称为*访问修饰符*。</span><span class="sxs-lookup"><span data-stu-id="ddaeb-124">The keywords that specify access level are called *access modifiers*.</span></span> <span data-ttu-id="ddaeb-125">访问修饰符的比较，请参阅[访问 Visual Basic 中的级别](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)。</span><span class="sxs-lookup"><span data-stu-id="ddaeb-125">For a comparison of the access modifiers, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
 <span data-ttu-id="ddaeb-126">`Protected` 修饰符可用于下面的上下文中：</span><span class="sxs-lookup"><span data-stu-id="ddaeb-126">The `Protected` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="ddaeb-127">Class 语句</span><span class="sxs-lookup"><span data-stu-id="ddaeb-127">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [<span data-ttu-id="ddaeb-128">Const 语句</span><span class="sxs-lookup"><span data-stu-id="ddaeb-128">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)  
  
 [<span data-ttu-id="ddaeb-129">Declare 语句</span><span class="sxs-lookup"><span data-stu-id="ddaeb-129">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [<span data-ttu-id="ddaeb-130">Delegate 语句</span><span class="sxs-lookup"><span data-stu-id="ddaeb-130">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [<span data-ttu-id="ddaeb-131">Dim 语句</span><span class="sxs-lookup"><span data-stu-id="ddaeb-131">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [<span data-ttu-id="ddaeb-132">Enum 语句</span><span class="sxs-lookup"><span data-stu-id="ddaeb-132">Enum Statement</span></span>](../../../visual-basic/language-reference/statements/enum-statement.md)  
  
 [<span data-ttu-id="ddaeb-133">Event 语句</span><span class="sxs-lookup"><span data-stu-id="ddaeb-133">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [<span data-ttu-id="ddaeb-134">Function 语句</span><span class="sxs-lookup"><span data-stu-id="ddaeb-134">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="ddaeb-135">Interface 语句</span><span class="sxs-lookup"><span data-stu-id="ddaeb-135">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [<span data-ttu-id="ddaeb-136">Property 语句</span><span class="sxs-lookup"><span data-stu-id="ddaeb-136">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="ddaeb-137">Structure 语句</span><span class="sxs-lookup"><span data-stu-id="ddaeb-137">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [<span data-ttu-id="ddaeb-138">Sub 语句</span><span class="sxs-lookup"><span data-stu-id="ddaeb-138">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="ddaeb-139">请参阅</span><span class="sxs-lookup"><span data-stu-id="ddaeb-139">See also</span></span>

- [<span data-ttu-id="ddaeb-140">Public</span><span class="sxs-lookup"><span data-stu-id="ddaeb-140">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)
- [<span data-ttu-id="ddaeb-141">Friend</span><span class="sxs-lookup"><span data-stu-id="ddaeb-141">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)
- [<span data-ttu-id="ddaeb-142">Private</span><span class="sxs-lookup"><span data-stu-id="ddaeb-142">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)
- [<span data-ttu-id="ddaeb-143">Private Protected</span><span class="sxs-lookup"><span data-stu-id="ddaeb-143">Private Protected</span></span>](private-protected.md)
- [<span data-ttu-id="ddaeb-144">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="ddaeb-144">Protected Friend</span></span>](protected-friend.md)
- [<span data-ttu-id="ddaeb-145">在 Visual Basic 中的访问级别</span><span class="sxs-lookup"><span data-stu-id="ddaeb-145">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [<span data-ttu-id="ddaeb-146">过程</span><span class="sxs-lookup"><span data-stu-id="ddaeb-146">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="ddaeb-147">结构</span><span class="sxs-lookup"><span data-stu-id="ddaeb-147">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="ddaeb-148">对象和类</span><span class="sxs-lookup"><span data-stu-id="ddaeb-148">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
