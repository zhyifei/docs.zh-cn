---
title: Shadows (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Shadows
- shadows
helpviewer_keywords:
- shadowing
- duplicate names [Visual Basic]
- scope [Visual Basic], shadowing
- Shadows keyword [Visual Basic]
- names [Visual Basic], shadowing
ms.assetid: 6bf687cd-0544-4797-b51b-911125ec57c6
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: bb767c372cc05d61d569227af8eef0dc3c67489b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="shadows-visual-basic"></a><span data-ttu-id="3fe67-102">Shadows (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3fe67-102">Shadows (Visual Basic)</span></span>
<span data-ttu-id="3fe67-103">指定声明的编程元素重新声明并隐藏具有相同名称的元素或在基类中的重载元素集。</span><span class="sxs-lookup"><span data-stu-id="3fe67-103">Specifies that a declared programming element redeclares and hides an identically named element, or set of overloaded elements, in a base class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3fe67-104">备注</span><span class="sxs-lookup"><span data-stu-id="3fe67-104">Remarks</span></span>  
 <span data-ttu-id="3fe67-105">隐藏的主要用途 (也称为即*按名称隐藏*) 是保留你的类成员的定义。</span><span class="sxs-lookup"><span data-stu-id="3fe67-105">The main purpose of shadowing (which is also known as *hiding by name*) is to preserve the definition of your class members.</span></span> <span data-ttu-id="3fe67-106">基类可能会经历创建具有与一个已定义同名的元素的更改。</span><span class="sxs-lookup"><span data-stu-id="3fe67-106">The base class might undergo a change that creates an element with the same name as one you have already defined.</span></span> <span data-ttu-id="3fe67-107">如果发生这种情况，`Shadows`修饰符强制就会通过引用您的类将解析为成员你定义，而不是到新的基类元素。</span><span class="sxs-lookup"><span data-stu-id="3fe67-107">If this happens, the `Shadows` modifier forces references through your class to be resolved to the member you defined, instead of to the new base class element.</span></span>  
  
 <span data-ttu-id="3fe67-108">隐藏和重写操作都可重新定义继承的元素，但这两种方法之间又具有很大的差异。</span><span class="sxs-lookup"><span data-stu-id="3fe67-108">Both shadowing and overriding redefine an inherited element, but there are significant differences between the two approaches.</span></span> <span data-ttu-id="3fe67-109">有关详细信息，请参阅[Visual Basic 中的隐藏](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)。</span><span class="sxs-lookup"><span data-stu-id="3fe67-109">For more information, see [Shadowing in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).</span></span>  
  
## <a name="rules"></a><span data-ttu-id="3fe67-110">规则</span><span class="sxs-lookup"><span data-stu-id="3fe67-110">Rules</span></span>  
  
-   <span data-ttu-id="3fe67-111">**声明上下文。**</span><span class="sxs-lookup"><span data-stu-id="3fe67-111">**Declaration Context.**</span></span> <span data-ttu-id="3fe67-112">你可以使用`Shadows`只能在类级别。</span><span class="sxs-lookup"><span data-stu-id="3fe67-112">You can use `Shadows` only at class level.</span></span> <span data-ttu-id="3fe67-113">这意味着的声明上下文`Shadows`元素必须是类，并且不能为源文件、 命名空间、 接口、 模块、 结构或过程。</span><span class="sxs-lookup"><span data-stu-id="3fe67-113">This means the declaration context for a `Shadows` element must be a class, and cannot be a source file, namespace, interface, module, structure, or procedure.</span></span>  
  
     <span data-ttu-id="3fe67-114">您可以声明在单个声明语句中只能有一个隐藏的元素。</span><span class="sxs-lookup"><span data-stu-id="3fe67-114">You can declare only one shadowing element in a single declaration statement.</span></span>  
  
-   <span data-ttu-id="3fe67-115">**组合的修饰符。**</span><span class="sxs-lookup"><span data-stu-id="3fe67-115">**Combined Modifiers.**</span></span> <span data-ttu-id="3fe67-116">不能指定`Shadows`连同`Overloads`， `Overrides`，或`Static`同一声明中。</span><span class="sxs-lookup"><span data-stu-id="3fe67-116">You cannot specify `Shadows` together with `Overloads`, `Overrides`, or `Static` in the same declaration.</span></span>  
  
-   <span data-ttu-id="3fe67-117">**元素类型。**</span><span class="sxs-lookup"><span data-stu-id="3fe67-117">**Element Types.**</span></span> <span data-ttu-id="3fe67-118">可以与任何其他类型一起隐藏任何类型的已声明元素。</span><span class="sxs-lookup"><span data-stu-id="3fe67-118">You can shadow any kind of declared element with any other kind.</span></span> <span data-ttu-id="3fe67-119">如果你隐藏属性或过程与其他属性或过程，参数和返回类型无需与基类属性或过程中匹配。</span><span class="sxs-lookup"><span data-stu-id="3fe67-119">If you shadow a property or procedure with another property or procedure, the parameters and the return type do not have to match those in the base class property or procedure.</span></span>  
  
-   <span data-ttu-id="3fe67-120">**访问。**</span><span class="sxs-lookup"><span data-stu-id="3fe67-120">**Accessing.**</span></span> <span data-ttu-id="3fe67-121">基类中隐藏的元素不可用通常从隐藏它的派生类中。</span><span class="sxs-lookup"><span data-stu-id="3fe67-121">The shadowed element in the base class is normally unavailable from within the derived class that shadows it.</span></span> <span data-ttu-id="3fe67-122">但是，适用以下注意事项。</span><span class="sxs-lookup"><span data-stu-id="3fe67-122">However, the following considerations apply.</span></span>  
  
    -   <span data-ttu-id="3fe67-123">如果不能从引用它的代码访问隐藏的元素，该引用被解析为隐藏的元素。</span><span class="sxs-lookup"><span data-stu-id="3fe67-123">If the shadowing element is not accessible from the code referring to it, the reference is resolved to the shadowed element.</span></span> <span data-ttu-id="3fe67-124">例如，如果`Private`元素隐藏一个基类元素，没有访问权限的代码`Private`元素改为访问基类元素。</span><span class="sxs-lookup"><span data-stu-id="3fe67-124">For example, if a `Private` element shadows a base class element, code that does not have permission to access the `Private` element accesses the base class element instead.</span></span>  
  
    -   <span data-ttu-id="3fe67-125">如果隐藏某个元素时，仍可以通过使用基本类的类型声明的对象来访问隐藏的元素。</span><span class="sxs-lookup"><span data-stu-id="3fe67-125">If you shadow an element, you can still access the shadowed element through an object declared with the type of the base class.</span></span> <span data-ttu-id="3fe67-126">你还可以访问该通过`MyBase`。</span><span class="sxs-lookup"><span data-stu-id="3fe67-126">You can also access it through `MyBase`.</span></span>  
  
 <span data-ttu-id="3fe67-127">`Shadows` 修饰符可用于下面的上下文中：</span><span class="sxs-lookup"><span data-stu-id="3fe67-127">The `Shadows` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="3fe67-128">Class 语句</span><span class="sxs-lookup"><span data-stu-id="3fe67-128">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [<span data-ttu-id="3fe67-129">Const 语句</span><span class="sxs-lookup"><span data-stu-id="3fe67-129">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)  
  
 [<span data-ttu-id="3fe67-130">Declare 语句</span><span class="sxs-lookup"><span data-stu-id="3fe67-130">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [<span data-ttu-id="3fe67-131">Delegate 语句</span><span class="sxs-lookup"><span data-stu-id="3fe67-131">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [<span data-ttu-id="3fe67-132">Dim 语句</span><span class="sxs-lookup"><span data-stu-id="3fe67-132">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [<span data-ttu-id="3fe67-133">Enum 语句</span><span class="sxs-lookup"><span data-stu-id="3fe67-133">Enum Statement</span></span>](../../../visual-basic/language-reference/statements/enum-statement.md)  
  
 [<span data-ttu-id="3fe67-134">Event 语句</span><span class="sxs-lookup"><span data-stu-id="3fe67-134">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [<span data-ttu-id="3fe67-135">Function 语句</span><span class="sxs-lookup"><span data-stu-id="3fe67-135">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="3fe67-136">Interface 语句</span><span class="sxs-lookup"><span data-stu-id="3fe67-136">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [<span data-ttu-id="3fe67-137">Property 语句</span><span class="sxs-lookup"><span data-stu-id="3fe67-137">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="3fe67-138">Structure 语句</span><span class="sxs-lookup"><span data-stu-id="3fe67-138">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [<span data-ttu-id="3fe67-139">Sub 语句</span><span class="sxs-lookup"><span data-stu-id="3fe67-139">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="3fe67-140">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3fe67-140">See Also</span></span>  
 [<span data-ttu-id="3fe67-141">Shared</span><span class="sxs-lookup"><span data-stu-id="3fe67-141">Shared</span></span>](../../../visual-basic/language-reference/modifiers/shared.md)  
 [<span data-ttu-id="3fe67-142">Static</span><span class="sxs-lookup"><span data-stu-id="3fe67-142">Static</span></span>](../../../visual-basic/language-reference/modifiers/static.md)  
 [<span data-ttu-id="3fe67-143">Private</span><span class="sxs-lookup"><span data-stu-id="3fe67-143">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)  
 [<span data-ttu-id="3fe67-144">Me、My、MyBase 和 MyClass</span><span class="sxs-lookup"><span data-stu-id="3fe67-144">Me, My, MyBase, and MyClass</span></span>](../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)  
 [<span data-ttu-id="3fe67-145">继承的基础知识</span><span class="sxs-lookup"><span data-stu-id="3fe67-145">Inheritance Basics</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)  
 [<span data-ttu-id="3fe67-146">MustOverride</span><span class="sxs-lookup"><span data-stu-id="3fe67-146">MustOverride</span></span>](../../../visual-basic/language-reference/modifiers/mustoverride.md)  
 [<span data-ttu-id="3fe67-147">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="3fe67-147">NotOverridable</span></span>](../../../visual-basic/language-reference/modifiers/notoverridable.md)  
 [<span data-ttu-id="3fe67-148">重载</span><span class="sxs-lookup"><span data-stu-id="3fe67-148">Overloads</span></span>](../../../visual-basic/language-reference/modifiers/overloads.md)  
 [<span data-ttu-id="3fe67-149">Overridable</span><span class="sxs-lookup"><span data-stu-id="3fe67-149">Overridable</span></span>](../../../visual-basic/language-reference/modifiers/overridable.md)  
 [<span data-ttu-id="3fe67-150">Overrides</span><span class="sxs-lookup"><span data-stu-id="3fe67-150">Overrides</span></span>](../../../visual-basic/language-reference/modifiers/overrides.md)  
 [<span data-ttu-id="3fe67-151">在 Visual Basic 中隐藏</span><span class="sxs-lookup"><span data-stu-id="3fe67-151">Shadowing in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
