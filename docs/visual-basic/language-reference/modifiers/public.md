---
title: Public (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Public
helpviewer_keywords:
- Public keyword [Visual Basic]
- Public keyword [Visual Basic], syntax
- Public access modifier
ms.assetid: 284c9e1b-ed23-499b-9bc9-ad87c11485a5
ms.openlocfilehash: 0c85564503f3c83e436044cd92ee3014945f1ef3
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2019
ms.locfileid: "58818379"
---
# <a name="public-visual-basic"></a><span data-ttu-id="f9f47-102">Public (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f9f47-102">Public (Visual Basic)</span></span>
<span data-ttu-id="f9f47-103">指定一个或多个声明的编程元素没有任何访问限制。</span><span class="sxs-lookup"><span data-stu-id="f9f47-103">Specifies that one or more declared programming elements have no access restrictions.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f9f47-104">备注</span><span class="sxs-lookup"><span data-stu-id="f9f47-104">Remarks</span></span>  
 <span data-ttu-id="f9f47-105">如果您要发布一个组件或一组组件，如类库，您通常希望可以访问您的程序集与互操作的任何代码的编程元素。</span><span class="sxs-lookup"><span data-stu-id="f9f47-105">If you are publishing a component or set of components, such as a class library, you usually want the programming elements to be accessible by any code that interoperates with your assembly.</span></span> <span data-ttu-id="f9f47-106">若要授予此类元素上的无限制访问权限，可将其与声明`Public`。</span><span class="sxs-lookup"><span data-stu-id="f9f47-106">To confer such unlimited access on an element, you can declare it with `Public`.</span></span>  
  
 <span data-ttu-id="f9f47-107">公共访问是编程元素的普通级别时不需要限制对它的访问。</span><span class="sxs-lookup"><span data-stu-id="f9f47-107">Public access is the normal level for a programming element when you do not need to limit access to it.</span></span> <span data-ttu-id="f9f47-108">请注意，接口、 模块、 类或结构声明一个元素的访问级别将默认为`Public`如果未另行声明。</span><span class="sxs-lookup"><span data-stu-id="f9f47-108">Note that the access level of an element declared within an interface, module, class, or structure defaults to `Public` if you do not declare it otherwise.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="f9f47-109">规则</span><span class="sxs-lookup"><span data-stu-id="f9f47-109">Rules</span></span>  
  
-   <span data-ttu-id="f9f47-110">**声明上下文。**</span><span class="sxs-lookup"><span data-stu-id="f9f47-110">**Declaration Context.**</span></span> <span data-ttu-id="f9f47-111">可以使用`Public`仅在模块、 接口或命名空间级别。</span><span class="sxs-lookup"><span data-stu-id="f9f47-111">You can use `Public` only at module, interface, or namespace level.</span></span> <span data-ttu-id="f9f47-112">这意味着声明上下文`Public`元素必须是源文件、 命名空间、 接口、 模块、 类或结构，并且不能为一个过程。</span><span class="sxs-lookup"><span data-stu-id="f9f47-112">This means the declaration context for a `Public` element must be a source file, namespace, interface, module, class, or structure, and cannot be a procedure.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="f9f47-113">行为</span><span class="sxs-lookup"><span data-stu-id="f9f47-113">Behavior</span></span>  
  
-   <span data-ttu-id="f9f47-114">**访问级别。**</span><span class="sxs-lookup"><span data-stu-id="f9f47-114">**Access Level.**</span></span> <span data-ttu-id="f9f47-115">模块、 类或结构可以访问所有代码都可以都访问其`Public`元素。</span><span class="sxs-lookup"><span data-stu-id="f9f47-115">All code that can access a module, class, or structure can access its `Public` elements.</span></span>  
  
-   <span data-ttu-id="f9f47-116">**默认访问权限。**</span><span class="sxs-lookup"><span data-stu-id="f9f47-116">**Default Access.**</span></span> <span data-ttu-id="f9f47-117">到公共访问权限，并且您过程默认值中的局部变量不能对其使用任何访问修饰符。</span><span class="sxs-lookup"><span data-stu-id="f9f47-117">Local variables inside a procedure default to public access, and you cannot use any access modifiers on them.</span></span>  
  
-   <span data-ttu-id="f9f47-118">**访问修饰符。**</span><span class="sxs-lookup"><span data-stu-id="f9f47-118">**Access Modifiers.**</span></span> <span data-ttu-id="f9f47-119">指定的访问级别的关键字称为*访问修饰符*。</span><span class="sxs-lookup"><span data-stu-id="f9f47-119">The keywords that specify access level are called *access modifiers*.</span></span> <span data-ttu-id="f9f47-120">访问修饰符的比较，请参阅[访问 Visual Basic 中的级别](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)。</span><span class="sxs-lookup"><span data-stu-id="f9f47-120">For a comparison of the access modifiers, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
 <span data-ttu-id="f9f47-121">`Public` 修饰符可用于下面的上下文中：</span><span class="sxs-lookup"><span data-stu-id="f9f47-121">The `Public` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="f9f47-122">Class 语句</span><span class="sxs-lookup"><span data-stu-id="f9f47-122">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [<span data-ttu-id="f9f47-123">Const 语句</span><span class="sxs-lookup"><span data-stu-id="f9f47-123">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)  
  
 [<span data-ttu-id="f9f47-124">Declare 语句</span><span class="sxs-lookup"><span data-stu-id="f9f47-124">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [<span data-ttu-id="f9f47-125">Delegate 语句</span><span class="sxs-lookup"><span data-stu-id="f9f47-125">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [<span data-ttu-id="f9f47-126">Dim 语句</span><span class="sxs-lookup"><span data-stu-id="f9f47-126">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [<span data-ttu-id="f9f47-127">Enum 语句</span><span class="sxs-lookup"><span data-stu-id="f9f47-127">Enum Statement</span></span>](../../../visual-basic/language-reference/statements/enum-statement.md)  
  
 [<span data-ttu-id="f9f47-128">Event 语句</span><span class="sxs-lookup"><span data-stu-id="f9f47-128">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [<span data-ttu-id="f9f47-129">Function 语句</span><span class="sxs-lookup"><span data-stu-id="f9f47-129">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="f9f47-130">Interface 语句</span><span class="sxs-lookup"><span data-stu-id="f9f47-130">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [<span data-ttu-id="f9f47-131">Module 语句</span><span class="sxs-lookup"><span data-stu-id="f9f47-131">Module Statement</span></span>](../../../visual-basic/language-reference/statements/module-statement.md)  
  
 [<span data-ttu-id="f9f47-132">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="f9f47-132">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
 [<span data-ttu-id="f9f47-133">Property 语句</span><span class="sxs-lookup"><span data-stu-id="f9f47-133">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="f9f47-134">Structure 语句</span><span class="sxs-lookup"><span data-stu-id="f9f47-134">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [<span data-ttu-id="f9f47-135">Sub 语句</span><span class="sxs-lookup"><span data-stu-id="f9f47-135">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="f9f47-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="f9f47-136">See also</span></span>

- [<span data-ttu-id="f9f47-137">Protected</span><span class="sxs-lookup"><span data-stu-id="f9f47-137">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)
- [<span data-ttu-id="f9f47-138">Friend</span><span class="sxs-lookup"><span data-stu-id="f9f47-138">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)
- [<span data-ttu-id="f9f47-139">Private</span><span class="sxs-lookup"><span data-stu-id="f9f47-139">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)
- [<span data-ttu-id="f9f47-140">Private Protected</span><span class="sxs-lookup"><span data-stu-id="f9f47-140">Private Protected</span></span>](private-protected.md)
- [<span data-ttu-id="f9f47-141">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="f9f47-141">Protected Friend</span></span>](protected-friend.md)
- [<span data-ttu-id="f9f47-142">在 Visual Basic 中的访问级别</span><span class="sxs-lookup"><span data-stu-id="f9f47-142">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [<span data-ttu-id="f9f47-143">过程</span><span class="sxs-lookup"><span data-stu-id="f9f47-143">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="f9f47-144">结构</span><span class="sxs-lookup"><span data-stu-id="f9f47-144">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="f9f47-145">对象和类</span><span class="sxs-lookup"><span data-stu-id="f9f47-145">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
