---
title: Private (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Private
helpviewer_keywords:
- Private keyword [Visual Basic]
- Private keyword [Visual Basic], syntax
ms.assetid: aba74a2e-5824-4613-bf63-b9ec7787f4e6
ms.openlocfilehash: d6e28e5e87c3a88e4db3fc81177894683dbb0908
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "58819471"
---
# <a name="private-visual-basic"></a><span data-ttu-id="a68ce-102">Private (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a68ce-102">Private (Visual Basic)</span></span>
<span data-ttu-id="a68ce-103">指定一个或多个声明的编程元素中包含的任何类型包括从其声明上下文中只能从可访问。</span><span class="sxs-lookup"><span data-stu-id="a68ce-103">Specifies that one or more declared programming elements are accessible only from within their declaration context, including from within any contained types.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a68ce-104">备注</span><span class="sxs-lookup"><span data-stu-id="a68ce-104">Remarks</span></span>  
 <span data-ttu-id="a68ce-105">如果编程元素表示专有的功能，或包含机密数据，你通常想要尽可能严格限制对它的访问。</span><span class="sxs-lookup"><span data-stu-id="a68ce-105">If a programming element represents proprietary functionality, or contains confidential data, you usually want to limit access to it as strictly as possible.</span></span> <span data-ttu-id="a68ce-106">模块、 类或结构，它定义其进行访问，从而实现最大限制。</span><span class="sxs-lookup"><span data-stu-id="a68ce-106">You achieve the maximum limitation by allowing only the module, class, or structure that defines it to access it.</span></span> <span data-ttu-id="a68ce-107">若要限制到这种方式中的元素的访问，可将其与声明`Private`。</span><span class="sxs-lookup"><span data-stu-id="a68ce-107">To limit access to an element in this way, you can declare it with `Private`.</span></span>  

> [!NOTE]
> <span data-ttu-id="a68ce-108">此外可以使用[Private Protected](private-protected.md)访问修饰符，使成员可访问从使该类中和从派生类中包含的程序集。</span><span class="sxs-lookup"><span data-stu-id="a68ce-108">You can also use the [Private Protected](private-protected.md) access modifier, which makes a member accessible from within that class and from derived classes located in its containing assembly.</span></span>

## <a name="rules"></a><span data-ttu-id="a68ce-109">规则</span><span class="sxs-lookup"><span data-stu-id="a68ce-109">Rules</span></span>  

-   <span data-ttu-id="a68ce-110">**声明上下文。**</span><span class="sxs-lookup"><span data-stu-id="a68ce-110">**Declaration Context.**</span></span> <span data-ttu-id="a68ce-111">只能在模块级别使用 `Private`。</span><span class="sxs-lookup"><span data-stu-id="a68ce-111">You can use `Private` only at module level.</span></span> <span data-ttu-id="a68ce-112">这意味着声明上下文`Private`元素必须是模块、 类或结构，并且不能为源文件、 命名空间、 接口或过程。</span><span class="sxs-lookup"><span data-stu-id="a68ce-112">This means the declaration context for a `Private` element must be a module, class, or structure, and cannot be a source file, namespace, interface, or procedure.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="a68ce-113">行为</span><span class="sxs-lookup"><span data-stu-id="a68ce-113">Behavior</span></span>  
  
-   <span data-ttu-id="a68ce-114">**访问级别。**</span><span class="sxs-lookup"><span data-stu-id="a68ce-114">**Access Level.**</span></span> <span data-ttu-id="a68ce-115">声明上下文中的所有代码可以都访问其`Private`元素。</span><span class="sxs-lookup"><span data-stu-id="a68ce-115">All code within a declaration context can access its `Private` elements.</span></span> <span data-ttu-id="a68ce-116">这包括所包含的类型，例如嵌套的类或枚举中的赋值表达式中的代码。</span><span class="sxs-lookup"><span data-stu-id="a68ce-116">This includes code within a contained type, such as a nested class or an assignment expression in an enumeration.</span></span> <span data-ttu-id="a68ce-117">声明上下文以外的任何代码可以访问其`Private`元素。</span><span class="sxs-lookup"><span data-stu-id="a68ce-117">No code outside of the declaration context can access its `Private` elements.</span></span>  
  
-   <span data-ttu-id="a68ce-118">**访问修饰符。**</span><span class="sxs-lookup"><span data-stu-id="a68ce-118">**Access Modifiers.**</span></span> <span data-ttu-id="a68ce-119">指定的访问级别的关键字称为*访问修饰符*。</span><span class="sxs-lookup"><span data-stu-id="a68ce-119">The keywords that specify access level are called *access modifiers*.</span></span> <span data-ttu-id="a68ce-120">访问修饰符的比较，请参阅[访问 Visual Basic 中的级别](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)。</span><span class="sxs-lookup"><span data-stu-id="a68ce-120">For a comparison of the access modifiers, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
 <span data-ttu-id="a68ce-121">`Private` 修饰符可用于下面的上下文中：</span><span class="sxs-lookup"><span data-stu-id="a68ce-121">The `Private` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="a68ce-122">Class 语句</span><span class="sxs-lookup"><span data-stu-id="a68ce-122">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [<span data-ttu-id="a68ce-123">Const 语句</span><span class="sxs-lookup"><span data-stu-id="a68ce-123">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)  
  
 [<span data-ttu-id="a68ce-124">Declare 语句</span><span class="sxs-lookup"><span data-stu-id="a68ce-124">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [<span data-ttu-id="a68ce-125">Delegate 语句</span><span class="sxs-lookup"><span data-stu-id="a68ce-125">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [<span data-ttu-id="a68ce-126">Dim 语句</span><span class="sxs-lookup"><span data-stu-id="a68ce-126">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [<span data-ttu-id="a68ce-127">Enum 语句</span><span class="sxs-lookup"><span data-stu-id="a68ce-127">Enum Statement</span></span>](../../../visual-basic/language-reference/statements/enum-statement.md)  
  
 [<span data-ttu-id="a68ce-128">Event 语句</span><span class="sxs-lookup"><span data-stu-id="a68ce-128">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [<span data-ttu-id="a68ce-129">Function 语句</span><span class="sxs-lookup"><span data-stu-id="a68ce-129">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="a68ce-130">Interface 语句</span><span class="sxs-lookup"><span data-stu-id="a68ce-130">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [<span data-ttu-id="a68ce-131">Property 语句</span><span class="sxs-lookup"><span data-stu-id="a68ce-131">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="a68ce-132">Structure 语句</span><span class="sxs-lookup"><span data-stu-id="a68ce-132">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [<span data-ttu-id="a68ce-133">Sub 语句</span><span class="sxs-lookup"><span data-stu-id="a68ce-133">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="a68ce-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="a68ce-134">See also</span></span>

- [<span data-ttu-id="a68ce-135">Public</span><span class="sxs-lookup"><span data-stu-id="a68ce-135">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)
- [<span data-ttu-id="a68ce-136">Protected</span><span class="sxs-lookup"><span data-stu-id="a68ce-136">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)
- [<span data-ttu-id="a68ce-137">Friend</span><span class="sxs-lookup"><span data-stu-id="a68ce-137">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)
- [<span data-ttu-id="a68ce-138">Private Protected</span><span class="sxs-lookup"><span data-stu-id="a68ce-138">Private Protected</span></span>](./private-protected.md)
- <span data-ttu-id="a68ce-139">[受保护的友元](./protected-friend.md)[访问 Visual Basic 中的级别](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)</span><span class="sxs-lookup"><span data-stu-id="a68ce-139">[Protected Friend](./protected-friend.md)    [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)</span></span>
- [<span data-ttu-id="a68ce-140">过程</span><span class="sxs-lookup"><span data-stu-id="a68ce-140">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="a68ce-141">结构</span><span class="sxs-lookup"><span data-stu-id="a68ce-141">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="a68ce-142">对象和类</span><span class="sxs-lookup"><span data-stu-id="a68ce-142">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
