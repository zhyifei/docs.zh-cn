---
title: Public (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Public
helpviewer_keywords:
- Public keyword [Visual Basic]
- Public keyword [Visual Basic], syntax
- Public access modifier
ms.assetid: 284c9e1b-ed23-499b-9bc9-ad87c11485a5
caps.latest.revision: 13
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: e6cd70adf6ec31c56f39d0443d320dd1b00b00d3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="public-visual-basic"></a><span data-ttu-id="b8fec-102">Public (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b8fec-102">Public (Visual Basic)</span></span>
<span data-ttu-id="b8fec-103">指定一个或多个已声明的编程元素具有任何访问限制。</span><span class="sxs-lookup"><span data-stu-id="b8fec-103">Specifies that one or more declared programming elements have no access restrictions.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b8fec-104">备注</span><span class="sxs-lookup"><span data-stu-id="b8fec-104">Remarks</span></span>  
 <span data-ttu-id="b8fec-105">如果您要发布的组件或组组件，如类库，你通常想要可由程序集与互操作的任何代码的编程元素。</span><span class="sxs-lookup"><span data-stu-id="b8fec-105">If you are publishing a component or set of components, such as a class library, you usually want the programming elements to be accessible by any code that interoperates with your assembly.</span></span> <span data-ttu-id="b8fec-106">若要授予此类不限的访问权限，在元素上，可以将其与声明`Public`。</span><span class="sxs-lookup"><span data-stu-id="b8fec-106">To confer such unlimited access on an element, you can declare it with `Public`.</span></span>  
  
 <span data-ttu-id="b8fec-107">公共访问时不需要限制对其的访问，将编程元素的正常级别。</span><span class="sxs-lookup"><span data-stu-id="b8fec-107">Public access is the normal level for a programming element when you do not need to limit access to it.</span></span> <span data-ttu-id="b8fec-108">请注意，接口、 模块、 类或结构中声明的元素的访问级别将默认为`Public`如果未另行声明。</span><span class="sxs-lookup"><span data-stu-id="b8fec-108">Note that the access level of an element declared within an interface, module, class, or structure defaults to `Public` if you do not declare it otherwise.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="b8fec-109">规则</span><span class="sxs-lookup"><span data-stu-id="b8fec-109">Rules</span></span>  
  
-   <span data-ttu-id="b8fec-110">**声明上下文。**</span><span class="sxs-lookup"><span data-stu-id="b8fec-110">**Declaration Context.**</span></span> <span data-ttu-id="b8fec-111">你可以使用`Public`只能在模块、 接口或命名空间级别。</span><span class="sxs-lookup"><span data-stu-id="b8fec-111">You can use `Public` only at module, interface, or namespace level.</span></span> <span data-ttu-id="b8fec-112">这意味着的声明上下文`Public`元素必须是源文件、 命名空间、 接口、 模块、 类或结构，并且不能为一个过程。</span><span class="sxs-lookup"><span data-stu-id="b8fec-112">This means the declaration context for a `Public` element must be a source file, namespace, interface, module, class, or structure, and cannot be a procedure.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="b8fec-113">行为</span><span class="sxs-lookup"><span data-stu-id="b8fec-113">Behavior</span></span>  
  
-   <span data-ttu-id="b8fec-114">**访问级别。**</span><span class="sxs-lookup"><span data-stu-id="b8fec-114">**Access Level.**</span></span> <span data-ttu-id="b8fec-115">所有代码都可以都访问模块、 类或结构可以都访问其`Public`元素。</span><span class="sxs-lookup"><span data-stu-id="b8fec-115">All code that can access a module, class, or structure can access its `Public` elements.</span></span>  
  
-   <span data-ttu-id="b8fec-116">**默认访问权限。**</span><span class="sxs-lookup"><span data-stu-id="b8fec-116">**Default Access.**</span></span> <span data-ttu-id="b8fec-117">内部过程默认为公共访问，并且你的本地变量不能在其上使用任何访问修饰符。</span><span class="sxs-lookup"><span data-stu-id="b8fec-117">Local variables inside a procedure default to public access, and you cannot use any access modifiers on them.</span></span>  
  
-   <span data-ttu-id="b8fec-118">**访问修饰符。**</span><span class="sxs-lookup"><span data-stu-id="b8fec-118">**Access Modifiers.**</span></span> <span data-ttu-id="b8fec-119">指定的访问级别的关键字称为*访问修饰符*。</span><span class="sxs-lookup"><span data-stu-id="b8fec-119">The keywords that specify access level are called *access modifiers*.</span></span> <span data-ttu-id="b8fec-120">访问修饰符的比较，请参阅[访问 Visual Basic 中的级别](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)。</span><span class="sxs-lookup"><span data-stu-id="b8fec-120">For a comparison of the access modifiers, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
 <span data-ttu-id="b8fec-121">`Public` 修饰符可用于下面的上下文中：</span><span class="sxs-lookup"><span data-stu-id="b8fec-121">The `Public` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="b8fec-122">Class 语句</span><span class="sxs-lookup"><span data-stu-id="b8fec-122">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [<span data-ttu-id="b8fec-123">Const 语句</span><span class="sxs-lookup"><span data-stu-id="b8fec-123">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)  
  
 [<span data-ttu-id="b8fec-124">Declare 语句</span><span class="sxs-lookup"><span data-stu-id="b8fec-124">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [<span data-ttu-id="b8fec-125">Delegate 语句</span><span class="sxs-lookup"><span data-stu-id="b8fec-125">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [<span data-ttu-id="b8fec-126">Dim 语句</span><span class="sxs-lookup"><span data-stu-id="b8fec-126">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [<span data-ttu-id="b8fec-127">Enum 语句</span><span class="sxs-lookup"><span data-stu-id="b8fec-127">Enum Statement</span></span>](../../../visual-basic/language-reference/statements/enum-statement.md)  
  
 [<span data-ttu-id="b8fec-128">Event 语句</span><span class="sxs-lookup"><span data-stu-id="b8fec-128">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [<span data-ttu-id="b8fec-129">Function 语句</span><span class="sxs-lookup"><span data-stu-id="b8fec-129">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="b8fec-130">Interface 语句</span><span class="sxs-lookup"><span data-stu-id="b8fec-130">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [<span data-ttu-id="b8fec-131">Module 语句</span><span class="sxs-lookup"><span data-stu-id="b8fec-131">Module Statement</span></span>](../../../visual-basic/language-reference/statements/module-statement.md)  
  
 [<span data-ttu-id="b8fec-132">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="b8fec-132">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
 [<span data-ttu-id="b8fec-133">Property 语句</span><span class="sxs-lookup"><span data-stu-id="b8fec-133">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="b8fec-134">Structure 语句</span><span class="sxs-lookup"><span data-stu-id="b8fec-134">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [<span data-ttu-id="b8fec-135">Sub 语句</span><span class="sxs-lookup"><span data-stu-id="b8fec-135">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="b8fec-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b8fec-136">See Also</span></span>  
 [<span data-ttu-id="b8fec-137">Protected</span><span class="sxs-lookup"><span data-stu-id="b8fec-137">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)  
 [<span data-ttu-id="b8fec-138">Friend</span><span class="sxs-lookup"><span data-stu-id="b8fec-138">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)  
 [<span data-ttu-id="b8fec-139">Private</span><span class="sxs-lookup"><span data-stu-id="b8fec-139">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)  
 [<span data-ttu-id="b8fec-140">在 Visual Basic 中的访问级别</span><span class="sxs-lookup"><span data-stu-id="b8fec-140">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)  
 [<span data-ttu-id="b8fec-141">过程</span><span class="sxs-lookup"><span data-stu-id="b8fec-141">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)  
 [<span data-ttu-id="b8fec-142">结构</span><span class="sxs-lookup"><span data-stu-id="b8fec-142">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [<span data-ttu-id="b8fec-143">对象和类</span><span class="sxs-lookup"><span data-stu-id="b8fec-143">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
