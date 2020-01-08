---
title: Private
ms.date: 07/20/2015
f1_keywords:
- vb.Private
helpviewer_keywords:
- Private keyword [Visual Basic]
- Private keyword [Visual Basic], syntax
ms.assetid: aba74a2e-5824-4613-bf63-b9ec7787f4e6
ms.openlocfilehash: 0c855c4e08b365b4cb75ab062d2ec304a79612ab
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/25/2019
ms.locfileid: "75347919"
---
# <a name="private-visual-basic"></a><span data-ttu-id="e09c7-102">Private (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e09c7-102">Private (Visual Basic)</span></span>
<span data-ttu-id="e09c7-103">指定一个或多个已声明的编程元素只能从其声明上下文中访问，包括从任何包含的类型中。</span><span class="sxs-lookup"><span data-stu-id="e09c7-103">Specifies that one or more declared programming elements are accessible only from within their declaration context, including from within any contained types.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e09c7-104">备注</span><span class="sxs-lookup"><span data-stu-id="e09c7-104">Remarks</span></span>  
 <span data-ttu-id="e09c7-105">如果编程元素表示专有功能，或包含机密数据，则通常需要尽可能严格地限制对其的访问。</span><span class="sxs-lookup"><span data-stu-id="e09c7-105">If a programming element represents proprietary functionality, or contains confidential data, you usually want to limit access to it as strictly as possible.</span></span> <span data-ttu-id="e09c7-106">通过只允许定义它的模块、类或结构可以实现最大限制。</span><span class="sxs-lookup"><span data-stu-id="e09c7-106">You achieve the maximum limitation by allowing only the module, class, or structure that defines it to access it.</span></span> <span data-ttu-id="e09c7-107">若要以这种方式限制对某个元素的访问，可使用 `Private`声明该元素。</span><span class="sxs-lookup"><span data-stu-id="e09c7-107">To limit access to an element in this way, you can declare it with `Private`.</span></span>  

> [!NOTE]
> <span data-ttu-id="e09c7-108">你还可以使用[私有受保护](private-protected.md)的访问修饰符，这使得成员可从该类内和其包含的程序集中的派生类中访问。</span><span class="sxs-lookup"><span data-stu-id="e09c7-108">You can also use the [Private Protected](private-protected.md) access modifier, which makes a member accessible from within that class and from derived classes located in its containing assembly.</span></span>

## <a name="rules"></a><span data-ttu-id="e09c7-109">规则</span><span class="sxs-lookup"><span data-stu-id="e09c7-109">Rules</span></span>  

- <span data-ttu-id="e09c7-110">**声明上下文。**</span><span class="sxs-lookup"><span data-stu-id="e09c7-110">**Declaration Context.**</span></span> <span data-ttu-id="e09c7-111">只能在模块级别使用 `Private`。</span><span class="sxs-lookup"><span data-stu-id="e09c7-111">You can use `Private` only at module level.</span></span> <span data-ttu-id="e09c7-112">这意味着 `Private` 元素的声明上下文必须是模块、类或结构，并且不能是源文件、命名空间、接口或过程。</span><span class="sxs-lookup"><span data-stu-id="e09c7-112">This means the declaration context for a `Private` element must be a module, class, or structure, and cannot be a source file, namespace, interface, or procedure.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="e09c7-113">行为</span><span class="sxs-lookup"><span data-stu-id="e09c7-113">Behavior</span></span>  
  
- <span data-ttu-id="e09c7-114">**访问级别。**</span><span class="sxs-lookup"><span data-stu-id="e09c7-114">**Access Level.**</span></span> <span data-ttu-id="e09c7-115">声明上下文内的所有代码都可以访问其 `Private` 元素。</span><span class="sxs-lookup"><span data-stu-id="e09c7-115">All code within a declaration context can access its `Private` elements.</span></span> <span data-ttu-id="e09c7-116">这包括包含类型中的代码，如枚举中的嵌套类或赋值表达式。</span><span class="sxs-lookup"><span data-stu-id="e09c7-116">This includes code within a contained type, such as a nested class or an assignment expression in an enumeration.</span></span> <span data-ttu-id="e09c7-117">声明上下文外的任何代码都不能访问其 `Private` 元素。</span><span class="sxs-lookup"><span data-stu-id="e09c7-117">No code outside of the declaration context can access its `Private` elements.</span></span>  
  
- <span data-ttu-id="e09c7-118">**访问修饰符。**</span><span class="sxs-lookup"><span data-stu-id="e09c7-118">**Access Modifiers.**</span></span> <span data-ttu-id="e09c7-119">指定访问级别的关键字称为*访问修饰符*。</span><span class="sxs-lookup"><span data-stu-id="e09c7-119">The keywords that specify access level are called *access modifiers*.</span></span> <span data-ttu-id="e09c7-120">有关访问修饰符的比较，请参阅[Visual Basic 中的访问级别](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)。</span><span class="sxs-lookup"><span data-stu-id="e09c7-120">For a comparison of the access modifiers, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
 <span data-ttu-id="e09c7-121">`Private` 修饰符可用于下面的上下文中：</span><span class="sxs-lookup"><span data-stu-id="e09c7-121">The `Private` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="e09c7-122">Class 语句</span><span class="sxs-lookup"><span data-stu-id="e09c7-122">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [<span data-ttu-id="e09c7-123">Const 语句</span><span class="sxs-lookup"><span data-stu-id="e09c7-123">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)  
  
 [<span data-ttu-id="e09c7-124">Declare Statement</span><span class="sxs-lookup"><span data-stu-id="e09c7-124">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [<span data-ttu-id="e09c7-125">Delegate 语句</span><span class="sxs-lookup"><span data-stu-id="e09c7-125">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [<span data-ttu-id="e09c7-126">Dim 语句</span><span class="sxs-lookup"><span data-stu-id="e09c7-126">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [<span data-ttu-id="e09c7-127">Enum 语句</span><span class="sxs-lookup"><span data-stu-id="e09c7-127">Enum Statement</span></span>](../../../visual-basic/language-reference/statements/enum-statement.md)  
  
 [<span data-ttu-id="e09c7-128">Event 语句</span><span class="sxs-lookup"><span data-stu-id="e09c7-128">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [<span data-ttu-id="e09c7-129">Function 语句</span><span class="sxs-lookup"><span data-stu-id="e09c7-129">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="e09c7-130">Interface 语句</span><span class="sxs-lookup"><span data-stu-id="e09c7-130">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [<span data-ttu-id="e09c7-131">Property 语句</span><span class="sxs-lookup"><span data-stu-id="e09c7-131">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="e09c7-132">Structure 语句</span><span class="sxs-lookup"><span data-stu-id="e09c7-132">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [<span data-ttu-id="e09c7-133">Sub 语句</span><span class="sxs-lookup"><span data-stu-id="e09c7-133">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="e09c7-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e09c7-134">See also</span></span>

- [<span data-ttu-id="e09c7-135">Public</span><span class="sxs-lookup"><span data-stu-id="e09c7-135">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)
- [<span data-ttu-id="e09c7-136">Protected</span><span class="sxs-lookup"><span data-stu-id="e09c7-136">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)
- [<span data-ttu-id="e09c7-137">Friend</span><span class="sxs-lookup"><span data-stu-id="e09c7-137">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)
- [<span data-ttu-id="e09c7-138">Private Protected</span><span class="sxs-lookup"><span data-stu-id="e09c7-138">Private Protected</span></span>](./private-protected.md)
- [<span data-ttu-id="e09c7-139">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="e09c7-139">Protected Friend</span></span>](./protected-friend.md)
- [<span data-ttu-id="e09c7-140">Visual Basic 中的访问级别</span><span class="sxs-lookup"><span data-stu-id="e09c7-140">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [<span data-ttu-id="e09c7-141">过程</span><span class="sxs-lookup"><span data-stu-id="e09c7-141">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="e09c7-142">结构</span><span class="sxs-lookup"><span data-stu-id="e09c7-142">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="e09c7-143">对象和类</span><span class="sxs-lookup"><span data-stu-id="e09c7-143">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
