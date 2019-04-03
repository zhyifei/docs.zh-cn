---
title: Shadows (Visual Basic)
ms.date: 07/20/2015
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
ms.openlocfilehash: c314db90a1a0f89613e20897387bdec8ec534837
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2019
ms.locfileid: "58834135"
---
# <a name="shadows-visual-basic"></a><span data-ttu-id="4cbaf-102">Shadows (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4cbaf-102">Shadows (Visual Basic)</span></span>
<span data-ttu-id="4cbaf-103">指定声明的编程元素重新声明并隐藏具有相同名称的元素或在基类中的重载元素集。</span><span class="sxs-lookup"><span data-stu-id="4cbaf-103">Specifies that a declared programming element redeclares and hides an identically named element, or set of overloaded elements, in a base class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4cbaf-104">备注</span><span class="sxs-lookup"><span data-stu-id="4cbaf-104">Remarks</span></span>  
 <span data-ttu-id="4cbaf-105">隐藏的主要目的 (也称为*按名称隐藏*) 是保留的类成员定义。</span><span class="sxs-lookup"><span data-stu-id="4cbaf-105">The main purpose of shadowing (which is also known as *hiding by name*) is to preserve the definition of your class members.</span></span> <span data-ttu-id="4cbaf-106">基本类可能需要进行更改，创建具有作为一个已定义的相同名称的元素。</span><span class="sxs-lookup"><span data-stu-id="4cbaf-106">The base class might undergo a change that creates an element with the same name as one you have already defined.</span></span> <span data-ttu-id="4cbaf-107">如果发生这种情况，`Shadows`通过您的类将解析为成员的修饰符强制引用你定义，而不是新基类元素。</span><span class="sxs-lookup"><span data-stu-id="4cbaf-107">If this happens, the `Shadows` modifier forces references through your class to be resolved to the member you defined, instead of to the new base class element.</span></span>  
  
 <span data-ttu-id="4cbaf-108">隐藏和重写操作都可重新定义继承的元素，但这两种方法之间又具有很大的差异。</span><span class="sxs-lookup"><span data-stu-id="4cbaf-108">Both shadowing and overriding redefine an inherited element, but there are significant differences between the two approaches.</span></span> <span data-ttu-id="4cbaf-109">有关详细信息，请参阅[Visual Basic 中的隐藏](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)。</span><span class="sxs-lookup"><span data-stu-id="4cbaf-109">For more information, see [Shadowing in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).</span></span>  
  
## <a name="rules"></a><span data-ttu-id="4cbaf-110">规则</span><span class="sxs-lookup"><span data-stu-id="4cbaf-110">Rules</span></span>  
  
-   <span data-ttu-id="4cbaf-111">**声明上下文。**</span><span class="sxs-lookup"><span data-stu-id="4cbaf-111">**Declaration Context.**</span></span> <span data-ttu-id="4cbaf-112">可以使用`Shadows`仅在类级别。</span><span class="sxs-lookup"><span data-stu-id="4cbaf-112">You can use `Shadows` only at class level.</span></span> <span data-ttu-id="4cbaf-113">这意味着声明上下文`Shadows`元素必须是类，且不能为源文件、 命名空间、 接口、 模块、 结构或过程。</span><span class="sxs-lookup"><span data-stu-id="4cbaf-113">This means the declaration context for a `Shadows` element must be a class, and cannot be a source file, namespace, interface, module, structure, or procedure.</span></span>  
  
     <span data-ttu-id="4cbaf-114">您可以声明在单个声明语句中只能有一个隐藏的元素。</span><span class="sxs-lookup"><span data-stu-id="4cbaf-114">You can declare only one shadowing element in a single declaration statement.</span></span>  
  
-   <span data-ttu-id="4cbaf-115">**组合的修饰符。**</span><span class="sxs-lookup"><span data-stu-id="4cbaf-115">**Combined Modifiers.**</span></span> <span data-ttu-id="4cbaf-116">不能指定`Shadows`连同`Overloads`， `Overrides`，或`Static`同一声明中。</span><span class="sxs-lookup"><span data-stu-id="4cbaf-116">You cannot specify `Shadows` together with `Overloads`, `Overrides`, or `Static` in the same declaration.</span></span>  
  
-   <span data-ttu-id="4cbaf-117">**元素类型。**</span><span class="sxs-lookup"><span data-stu-id="4cbaf-117">**Element Types.**</span></span> <span data-ttu-id="4cbaf-118">可以与任何其他类型一起隐藏任何类型的已声明元素。</span><span class="sxs-lookup"><span data-stu-id="4cbaf-118">You can shadow any kind of declared element with any other kind.</span></span> <span data-ttu-id="4cbaf-119">如果隐藏属性或使用另一个属性或过程的过程，参数和返回类型无需与基类属性或过程中的匹配。</span><span class="sxs-lookup"><span data-stu-id="4cbaf-119">If you shadow a property or procedure with another property or procedure, the parameters and the return type do not have to match those in the base class property or procedure.</span></span>  
  
-   <span data-ttu-id="4cbaf-120">**访问。**</span><span class="sxs-lookup"><span data-stu-id="4cbaf-120">**Accessing.**</span></span> <span data-ttu-id="4cbaf-121">通常情况下隐藏它的派生类中从无法在基类中隐藏的元素。</span><span class="sxs-lookup"><span data-stu-id="4cbaf-121">The shadowed element in the base class is normally unavailable from within the derived class that shadows it.</span></span> <span data-ttu-id="4cbaf-122">但是，以下注意事项适用。</span><span class="sxs-lookup"><span data-stu-id="4cbaf-122">However, the following considerations apply.</span></span>  
  
    -   <span data-ttu-id="4cbaf-123">如果不能从引用它的代码访问隐藏的元素，该引用被解析为隐藏的元素。</span><span class="sxs-lookup"><span data-stu-id="4cbaf-123">If the shadowing element is not accessible from the code referring to it, the reference is resolved to the shadowed element.</span></span> <span data-ttu-id="4cbaf-124">例如，如果`Private`元素将隐藏基类元素，不具有访问权限的代码`Private`元素将改为访问的基类元素。</span><span class="sxs-lookup"><span data-stu-id="4cbaf-124">For example, if a `Private` element shadows a base class element, code that does not have permission to access the `Private` element accesses the base class element instead.</span></span>  
  
    -   <span data-ttu-id="4cbaf-125">如果隐藏某个元素时，仍可以通过使用基类的类型声明的对象来访问隐藏的元素。</span><span class="sxs-lookup"><span data-stu-id="4cbaf-125">If you shadow an element, you can still access the shadowed element through an object declared with the type of the base class.</span></span> <span data-ttu-id="4cbaf-126">您还可以访问通过`MyBase`。</span><span class="sxs-lookup"><span data-stu-id="4cbaf-126">You can also access it through `MyBase`.</span></span>  
  
 <span data-ttu-id="4cbaf-127">`Shadows` 修饰符可用于下面的上下文中：</span><span class="sxs-lookup"><span data-stu-id="4cbaf-127">The `Shadows` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="4cbaf-128">Class 语句</span><span class="sxs-lookup"><span data-stu-id="4cbaf-128">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [<span data-ttu-id="4cbaf-129">Const 语句</span><span class="sxs-lookup"><span data-stu-id="4cbaf-129">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)  
  
 [<span data-ttu-id="4cbaf-130">Declare 语句</span><span class="sxs-lookup"><span data-stu-id="4cbaf-130">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [<span data-ttu-id="4cbaf-131">Delegate 语句</span><span class="sxs-lookup"><span data-stu-id="4cbaf-131">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [<span data-ttu-id="4cbaf-132">Dim 语句</span><span class="sxs-lookup"><span data-stu-id="4cbaf-132">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [<span data-ttu-id="4cbaf-133">Enum 语句</span><span class="sxs-lookup"><span data-stu-id="4cbaf-133">Enum Statement</span></span>](../../../visual-basic/language-reference/statements/enum-statement.md)  
  
 [<span data-ttu-id="4cbaf-134">Event 语句</span><span class="sxs-lookup"><span data-stu-id="4cbaf-134">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [<span data-ttu-id="4cbaf-135">Function 语句</span><span class="sxs-lookup"><span data-stu-id="4cbaf-135">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="4cbaf-136">Interface 语句</span><span class="sxs-lookup"><span data-stu-id="4cbaf-136">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [<span data-ttu-id="4cbaf-137">Property 语句</span><span class="sxs-lookup"><span data-stu-id="4cbaf-137">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="4cbaf-138">Structure 语句</span><span class="sxs-lookup"><span data-stu-id="4cbaf-138">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [<span data-ttu-id="4cbaf-139">Sub 语句</span><span class="sxs-lookup"><span data-stu-id="4cbaf-139">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="4cbaf-140">请参阅</span><span class="sxs-lookup"><span data-stu-id="4cbaf-140">See also</span></span>

- [<span data-ttu-id="4cbaf-141">Shared</span><span class="sxs-lookup"><span data-stu-id="4cbaf-141">Shared</span></span>](../../../visual-basic/language-reference/modifiers/shared.md)
- [<span data-ttu-id="4cbaf-142">Static</span><span class="sxs-lookup"><span data-stu-id="4cbaf-142">Static</span></span>](../../../visual-basic/language-reference/modifiers/static.md)
- [<span data-ttu-id="4cbaf-143">Private</span><span class="sxs-lookup"><span data-stu-id="4cbaf-143">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)
- [<span data-ttu-id="4cbaf-144">Me、My、MyBase 和 MyClass</span><span class="sxs-lookup"><span data-stu-id="4cbaf-144">Me, My, MyBase, and MyClass</span></span>](../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [<span data-ttu-id="4cbaf-145">继承的基础知识</span><span class="sxs-lookup"><span data-stu-id="4cbaf-145">Inheritance Basics</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
- [<span data-ttu-id="4cbaf-146">MustOverride</span><span class="sxs-lookup"><span data-stu-id="4cbaf-146">MustOverride</span></span>](../../../visual-basic/language-reference/modifiers/mustoverride.md)
- [<span data-ttu-id="4cbaf-147">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="4cbaf-147">NotOverridable</span></span>](../../../visual-basic/language-reference/modifiers/notoverridable.md)
- [<span data-ttu-id="4cbaf-148">重载</span><span class="sxs-lookup"><span data-stu-id="4cbaf-148">Overloads</span></span>](../../../visual-basic/language-reference/modifiers/overloads.md)
- [<span data-ttu-id="4cbaf-149">Overridable</span><span class="sxs-lookup"><span data-stu-id="4cbaf-149">Overridable</span></span>](../../../visual-basic/language-reference/modifiers/overridable.md)
- [<span data-ttu-id="4cbaf-150">Overrides</span><span class="sxs-lookup"><span data-stu-id="4cbaf-150">Overrides</span></span>](../../../visual-basic/language-reference/modifiers/overrides.md)
- [<span data-ttu-id="4cbaf-151">在 Visual Basic 中隐藏</span><span class="sxs-lookup"><span data-stu-id="4cbaf-151">Shadowing in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
