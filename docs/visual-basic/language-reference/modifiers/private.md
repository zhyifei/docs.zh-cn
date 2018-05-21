---
title: Private (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Private
helpviewer_keywords:
- Private keyword [Visual Basic]
- Private keyword [Visual Basic], syntax
ms.assetid: aba74a2e-5824-4613-bf63-b9ec7787f4e6
ms.openlocfilehash: 40b64b8d2b6306d458b7a9cc657c5b7dc4270eb2
ms.sourcegitcommit: 22c3c8f74eaa138dbbbb02eb7d720fce87fc30a9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/17/2018
---
# <a name="private-visual-basic"></a><span data-ttu-id="fea0d-102">Private (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fea0d-102">Private (Visual Basic)</span></span>
<span data-ttu-id="fea0d-103">指定的一个或多个已声明的编程元素都可以访问只能从在其声明上下文中，包括从文件内包含的任何类型。</span><span class="sxs-lookup"><span data-stu-id="fea0d-103">Specifies that one or more declared programming elements are accessible only from within their declaration context, including from within any contained types.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fea0d-104">备注</span><span class="sxs-lookup"><span data-stu-id="fea0d-104">Remarks</span></span>  
 <span data-ttu-id="fea0d-105">如果编程元素表示专有的功能，或包含机密数据，你通常想要尽可能严格限制对其的访问。</span><span class="sxs-lookup"><span data-stu-id="fea0d-105">If a programming element represents proprietary functionality, or contains confidential data, you usually want to limit access to it as strictly as possible.</span></span> <span data-ttu-id="fea0d-106">允许模块、 类或结构，它定义其进行访问，从而实现的最大限制。</span><span class="sxs-lookup"><span data-stu-id="fea0d-106">You achieve the maximum limitation by allowing only the module, class, or structure that defines it to access it.</span></span> <span data-ttu-id="fea0d-107">若要限制到这种方式中的元素的访问，可将其与声明`Private`。</span><span class="sxs-lookup"><span data-stu-id="fea0d-107">To limit access to an element in this way, you can declare it with `Private`.</span></span>  

> [!NOTE]
> <span data-ttu-id="fea0d-108">你还可以使用[私有受保护](private-protected.md)使成员可访问从该类中以及从位于其包含的程序集的派生类的访问修饰符。</span><span class="sxs-lookup"><span data-stu-id="fea0d-108">You can also use the [Private Protected](private-protected.md) access modifier, which makes a member accessible from within that class and from derived classes located in its containing assembly.</span></span>

## <a name="rules"></a><span data-ttu-id="fea0d-109">规则</span><span class="sxs-lookup"><span data-stu-id="fea0d-109">Rules</span></span>  

-   <span data-ttu-id="fea0d-110">**声明上下文。**</span><span class="sxs-lookup"><span data-stu-id="fea0d-110">**Declaration Context.**</span></span> <span data-ttu-id="fea0d-111">只能在模块级别使用 `Private`。</span><span class="sxs-lookup"><span data-stu-id="fea0d-111">You can use `Private` only at module level.</span></span> <span data-ttu-id="fea0d-112">这意味着的声明上下文`Private`元素必须是模块、 类或结构，并且不能是源文件、 命名空间、 接口或过程。</span><span class="sxs-lookup"><span data-stu-id="fea0d-112">This means the declaration context for a `Private` element must be a module, class, or structure, and cannot be a source file, namespace, interface, or procedure.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="fea0d-113">行为</span><span class="sxs-lookup"><span data-stu-id="fea0d-113">Behavior</span></span>  
  
-   <span data-ttu-id="fea0d-114">**访问级别。**</span><span class="sxs-lookup"><span data-stu-id="fea0d-114">**Access Level.**</span></span> <span data-ttu-id="fea0d-115">声明上下文中的所有代码可以都访问其`Private`元素。</span><span class="sxs-lookup"><span data-stu-id="fea0d-115">All code within a declaration context can access its `Private` elements.</span></span> <span data-ttu-id="fea0d-116">这包括所包含的类型，例如嵌套的类或枚举中的赋值表达式中的代码。</span><span class="sxs-lookup"><span data-stu-id="fea0d-116">This includes code within a contained type, such as a nested class or an assignment expression in an enumeration.</span></span> <span data-ttu-id="fea0d-117">外部声明上下文没有代码可以访问其`Private`元素。</span><span class="sxs-lookup"><span data-stu-id="fea0d-117">No code outside of the declaration context can access its `Private` elements.</span></span>  
  
-   <span data-ttu-id="fea0d-118">**访问修饰符。**</span><span class="sxs-lookup"><span data-stu-id="fea0d-118">**Access Modifiers.**</span></span> <span data-ttu-id="fea0d-119">指定的访问级别的关键字称为*访问修饰符*。</span><span class="sxs-lookup"><span data-stu-id="fea0d-119">The keywords that specify access level are called *access modifiers*.</span></span> <span data-ttu-id="fea0d-120">访问修饰符的比较，请参阅[访问 Visual Basic 中的级别](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)。</span><span class="sxs-lookup"><span data-stu-id="fea0d-120">For a comparison of the access modifiers, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
 <span data-ttu-id="fea0d-121">`Private` 修饰符可用于下面的上下文中：</span><span class="sxs-lookup"><span data-stu-id="fea0d-121">The `Private` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="fea0d-122">Class 语句</span><span class="sxs-lookup"><span data-stu-id="fea0d-122">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [<span data-ttu-id="fea0d-123">Const 语句</span><span class="sxs-lookup"><span data-stu-id="fea0d-123">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)  
  
 [<span data-ttu-id="fea0d-124">Declare 语句</span><span class="sxs-lookup"><span data-stu-id="fea0d-124">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [<span data-ttu-id="fea0d-125">Delegate 语句</span><span class="sxs-lookup"><span data-stu-id="fea0d-125">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [<span data-ttu-id="fea0d-126">Dim 语句</span><span class="sxs-lookup"><span data-stu-id="fea0d-126">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [<span data-ttu-id="fea0d-127">Enum 语句</span><span class="sxs-lookup"><span data-stu-id="fea0d-127">Enum Statement</span></span>](../../../visual-basic/language-reference/statements/enum-statement.md)  
  
 [<span data-ttu-id="fea0d-128">Event 语句</span><span class="sxs-lookup"><span data-stu-id="fea0d-128">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [<span data-ttu-id="fea0d-129">Function 语句</span><span class="sxs-lookup"><span data-stu-id="fea0d-129">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="fea0d-130">Interface 语句</span><span class="sxs-lookup"><span data-stu-id="fea0d-130">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [<span data-ttu-id="fea0d-131">Property 语句</span><span class="sxs-lookup"><span data-stu-id="fea0d-131">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="fea0d-132">Structure 语句</span><span class="sxs-lookup"><span data-stu-id="fea0d-132">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [<span data-ttu-id="fea0d-133">Sub 语句</span><span class="sxs-lookup"><span data-stu-id="fea0d-133">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="fea0d-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="fea0d-134">See Also</span></span>  
 [<span data-ttu-id="fea0d-135">Public</span><span class="sxs-lookup"><span data-stu-id="fea0d-135">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)  
 [<span data-ttu-id="fea0d-136">Protected</span><span class="sxs-lookup"><span data-stu-id="fea0d-136">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)  
 [<span data-ttu-id="fea0d-137">Friend</span><span class="sxs-lookup"><span data-stu-id="fea0d-137">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)  
 <span data-ttu-id="fea0d-138">[私有受保护](./private-protected.md) </span><span class="sxs-lookup"><span data-stu-id="fea0d-138">[Private Protected](./private-protected.md) </span></span>  
 <span data-ttu-id="fea0d-139">[受保护的友元](./protected-friend.md)[访问 Visual Basic 中的级别    ](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)</span><span class="sxs-lookup"><span data-stu-id="fea0d-139">[Protected Friend](./protected-friend.md)    [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)</span></span>  
 [<span data-ttu-id="fea0d-140">过程</span><span class="sxs-lookup"><span data-stu-id="fea0d-140">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)  
 [<span data-ttu-id="fea0d-141">结构</span><span class="sxs-lookup"><span data-stu-id="fea0d-141">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [<span data-ttu-id="fea0d-142">对象和类</span><span class="sxs-lookup"><span data-stu-id="fea0d-142">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
