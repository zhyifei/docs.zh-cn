---
title: Overrides
ms.date: 07/20/2015
f1_keywords:
- Overrides
- vb.Overrides
helpviewer_keywords:
- properties [Visual Basic], redefining
- procedures [Visual Basic], overriding
- procedures [Visual Basic], redefining
- overriding
- Overrides keyword [Visual Basic]
- overriding, Overrides keyword
- properties [Visual Basic], overriding
ms.assetid: 9f5e6144-ce10-465e-842b-1a8f8760af90
ms.openlocfilehash: 04f1cb27d6a8366c2dd13f8fdc1d975d382f1cfd
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351384"
---
# <a name="overrides-visual-basic"></a><span data-ttu-id="cceb2-102">Overrides (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cceb2-102">Overrides (Visual Basic)</span></span>

<span data-ttu-id="cceb2-103">指定某一属性或过程可重写从基类中继承的具有相同名称的属性或过程。</span><span class="sxs-lookup"><span data-stu-id="cceb2-103">Specifies that a property or procedure overrides an identically named property or procedure inherited from a base class.</span></span>

## <a name="rules"></a><span data-ttu-id="cceb2-104">规则</span><span class="sxs-lookup"><span data-stu-id="cceb2-104">Rules</span></span>

- <span data-ttu-id="cceb2-105">**Declaration Context.**</span><span class="sxs-lookup"><span data-stu-id="cceb2-105">**Declaration Context.**</span></span> <span data-ttu-id="cceb2-106">You can use `Overrides` only in a property or procedure declaration statement.</span><span class="sxs-lookup"><span data-stu-id="cceb2-106">You can use `Overrides` only in a property or procedure declaration statement.</span></span>

- <span data-ttu-id="cceb2-107">**Combined Modifiers.**</span><span class="sxs-lookup"><span data-stu-id="cceb2-107">**Combined Modifiers.**</span></span> <span data-ttu-id="cceb2-108">You cannot specify `Overrides` together with `Shadows` or `Shared` in the same declaration.</span><span class="sxs-lookup"><span data-stu-id="cceb2-108">You cannot specify `Overrides` together with `Shadows` or `Shared` in the same declaration.</span></span> <span data-ttu-id="cceb2-109">由于重写元素是隐式可重写的，因此不能将 `Overridable` 与 `Overrides` 组合到一起。</span><span class="sxs-lookup"><span data-stu-id="cceb2-109">Because an overriding element is implicitly overridable, you cannot combine `Overridable` with `Overrides`.</span></span>

- <span data-ttu-id="cceb2-110">**Matching Signatures.**</span><span class="sxs-lookup"><span data-stu-id="cceb2-110">**Matching Signatures.**</span></span> <span data-ttu-id="cceb2-111">The signature of this declaration must exactly match the *signature* of the property or procedure that it overrides.</span><span class="sxs-lookup"><span data-stu-id="cceb2-111">The signature of this declaration must exactly match the *signature* of the property or procedure that it overrides.</span></span> <span data-ttu-id="cceb2-112">这意味着参数列表必须具有相同数量的参数，并且排序顺序和数据类型都必须完全相同。</span><span class="sxs-lookup"><span data-stu-id="cceb2-112">This means the parameter lists must have the same number of parameters, in the same order, with the same data types.</span></span>

  <span data-ttu-id="cceb2-113">除签名外，重写的声明还必须完全匹配以下项：</span><span class="sxs-lookup"><span data-stu-id="cceb2-113">In addition to the signature, the overriding declaration must also exactly match the following:</span></span>

  - <span data-ttu-id="cceb2-114">访问级别</span><span class="sxs-lookup"><span data-stu-id="cceb2-114">The access level</span></span>

  - <span data-ttu-id="cceb2-115">返回类型（如有）</span><span class="sxs-lookup"><span data-stu-id="cceb2-115">The return type, if any</span></span>

- <span data-ttu-id="cceb2-116">**Generic Signatures.**</span><span class="sxs-lookup"><span data-stu-id="cceb2-116">**Generic Signatures.**</span></span> <span data-ttu-id="cceb2-117">对于泛型过程，签名包括类型参数的数量。</span><span class="sxs-lookup"><span data-stu-id="cceb2-117">For a generic procedure, the signature includes the number of type parameters.</span></span> <span data-ttu-id="cceb2-118">因此，重写的声明必须在这方面与基类版本匹配。</span><span class="sxs-lookup"><span data-stu-id="cceb2-118">Therefore, the overriding declaration must match the base class version in that respect as well.</span></span>

- <span data-ttu-id="cceb2-119">**Additional Matching.**</span><span class="sxs-lookup"><span data-stu-id="cceb2-119">**Additional Matching.**</span></span> <span data-ttu-id="cceb2-120">除匹配基类版本的签名外，此声明还必须在以下方面与其匹配：</span><span class="sxs-lookup"><span data-stu-id="cceb2-120">In addition to matching the signature of the base class version, this declaration must also match it in the following respects:</span></span>

  - <span data-ttu-id="cceb2-121">Access-level modifier (such as [Public](../../../visual-basic/language-reference/modifiers/public.md))</span><span class="sxs-lookup"><span data-stu-id="cceb2-121">Access-level modifier (such as [Public](../../../visual-basic/language-reference/modifiers/public.md))</span></span>

  - <span data-ttu-id="cceb2-122">Passing mechanism of each parameter ([ByVal](../../../visual-basic/language-reference/modifiers/byval.md) or [ByRef](../../../visual-basic/language-reference/modifiers/byref.md))</span><span class="sxs-lookup"><span data-stu-id="cceb2-122">Passing mechanism of each parameter ([ByVal](../../../visual-basic/language-reference/modifiers/byval.md) or [ByRef](../../../visual-basic/language-reference/modifiers/byref.md))</span></span>

  - <span data-ttu-id="cceb2-123">泛型过程的每个类型参数的约束列表</span><span class="sxs-lookup"><span data-stu-id="cceb2-123">Constraint lists on each type parameter of a generic procedure</span></span>

- <span data-ttu-id="cceb2-124">**Shadowing and Overriding.**</span><span class="sxs-lookup"><span data-stu-id="cceb2-124">**Shadowing and Overriding.**</span></span> <span data-ttu-id="cceb2-125">隐藏和重写操作都可重新定义继承的元素，但这两种方法之间又具有很大的差异。</span><span class="sxs-lookup"><span data-stu-id="cceb2-125">Both shadowing and overriding redefine an inherited element, but there are significant differences between the two approaches.</span></span> <span data-ttu-id="cceb2-126">For more information, see [Shadowing in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).</span><span class="sxs-lookup"><span data-stu-id="cceb2-126">For more information, see [Shadowing in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).</span></span>

<span data-ttu-id="cceb2-127">如果使用 `Overrides`，编译器将隐式添加 `Overloads`，以便库 API 更轻松地使用 C#。</span><span class="sxs-lookup"><span data-stu-id="cceb2-127">If you use `Overrides`, the compiler implicitly adds `Overloads` so that your library APIs work with C# more easily.</span></span>

<span data-ttu-id="cceb2-128">`Overrides` 修饰符可用于下面的上下文中：</span><span class="sxs-lookup"><span data-stu-id="cceb2-128">The `Overrides` modifier can be used in these contexts:</span></span>

- [<span data-ttu-id="cceb2-129">Function 语句</span><span class="sxs-lookup"><span data-stu-id="cceb2-129">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)

- [<span data-ttu-id="cceb2-130">Property 语句</span><span class="sxs-lookup"><span data-stu-id="cceb2-130">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)

- [<span data-ttu-id="cceb2-131">Sub 语句</span><span class="sxs-lookup"><span data-stu-id="cceb2-131">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)

## <a name="see-also"></a><span data-ttu-id="cceb2-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="cceb2-132">See also</span></span>

- [<span data-ttu-id="cceb2-133">New</span><span class="sxs-lookup"><span data-stu-id="cceb2-133">MustOverride</span></span>](../../../visual-basic/language-reference/modifiers/mustoverride.md)
- [<span data-ttu-id="cceb2-134">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="cceb2-134">NotOverridable</span></span>](../../../visual-basic/language-reference/modifiers/notoverridable.md)
- [<span data-ttu-id="cceb2-135">Overridable</span><span class="sxs-lookup"><span data-stu-id="cceb2-135">Overridable</span></span>](../../../visual-basic/language-reference/modifiers/overridable.md)
- [<span data-ttu-id="cceb2-136">关键字</span><span class="sxs-lookup"><span data-stu-id="cceb2-136">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
- [<span data-ttu-id="cceb2-137">Shadowing in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="cceb2-137">Shadowing in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
- [<span data-ttu-id="cceb2-138">Generic Types in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="cceb2-138">Generic Types in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [<span data-ttu-id="cceb2-139">类型列表</span><span class="sxs-lookup"><span data-stu-id="cceb2-139">Type List</span></span>](../../../visual-basic/language-reference/statements/type-list.md)
