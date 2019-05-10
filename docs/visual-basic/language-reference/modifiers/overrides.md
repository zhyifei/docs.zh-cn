---
title: Overrides (Visual Basic)
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
ms.openlocfilehash: 7fff91d993743574d13030aa3d5cc1e462e76838
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64751026"
---
# <a name="overrides-visual-basic"></a><span data-ttu-id="13e75-102">Overrides (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="13e75-102">Overrides (Visual Basic)</span></span>

<span data-ttu-id="13e75-103">指定某一属性或过程可重写从基类中继承的具有相同名称的属性或过程。</span><span class="sxs-lookup"><span data-stu-id="13e75-103">Specifies that a property or procedure overrides an identically named property or procedure inherited from a base class.</span></span>

## <a name="rules"></a><span data-ttu-id="13e75-104">规则</span><span class="sxs-lookup"><span data-stu-id="13e75-104">Rules</span></span>

- <span data-ttu-id="13e75-105">**声明上下文。**</span><span class="sxs-lookup"><span data-stu-id="13e75-105">**Declaration Context.**</span></span> <span data-ttu-id="13e75-106">只能在属性或过程声明语句中使用 `Overrides`。</span><span class="sxs-lookup"><span data-stu-id="13e75-106">You can use `Overrides` only in a property or procedure declaration statement.</span></span>

- <span data-ttu-id="13e75-107">**组合的修饰符。**</span><span class="sxs-lookup"><span data-stu-id="13e75-107">**Combined Modifiers.**</span></span> <span data-ttu-id="13e75-108">不能在同一过程声明中同时指定 `Overrides` 和 `Shadows` 或 `Shared`。</span><span class="sxs-lookup"><span data-stu-id="13e75-108">You cannot specify `Overrides` together with `Shadows` or `Shared` in the same declaration.</span></span> <span data-ttu-id="13e75-109">由于重写元素是隐式可重写的，因此不能将 `Overridable` 与 `Overrides` 组合到一起。</span><span class="sxs-lookup"><span data-stu-id="13e75-109">Because an overriding element is implicitly overridable, you cannot combine `Overridable` with `Overrides`.</span></span>

- <span data-ttu-id="13e75-110">**匹配的签名。**</span><span class="sxs-lookup"><span data-stu-id="13e75-110">**Matching Signatures.**</span></span> <span data-ttu-id="13e75-111">此声明的签名必须完全匹配*签名*属性或过程，它会重写。</span><span class="sxs-lookup"><span data-stu-id="13e75-111">The signature of this declaration must exactly match the *signature* of the property or procedure that it overrides.</span></span> <span data-ttu-id="13e75-112">这意味着参数列表必须具有相同数量的参数，并且排序顺序和数据类型都必须完全相同。</span><span class="sxs-lookup"><span data-stu-id="13e75-112">This means the parameter lists must have the same number of parameters, in the same order, with the same data types.</span></span>

  <span data-ttu-id="13e75-113">除签名外，重写的声明还必须完全匹配以下项：</span><span class="sxs-lookup"><span data-stu-id="13e75-113">In addition to the signature, the overriding declaration must also exactly match the following:</span></span>

  - <span data-ttu-id="13e75-114">访问级别</span><span class="sxs-lookup"><span data-stu-id="13e75-114">The access level</span></span>

  - <span data-ttu-id="13e75-115">返回类型（如有）</span><span class="sxs-lookup"><span data-stu-id="13e75-115">The return type, if any</span></span>

- <span data-ttu-id="13e75-116">**泛型签名。**</span><span class="sxs-lookup"><span data-stu-id="13e75-116">**Generic Signatures.**</span></span> <span data-ttu-id="13e75-117">对于泛型过程，签名包括类型参数的数量。</span><span class="sxs-lookup"><span data-stu-id="13e75-117">For a generic procedure, the signature includes the number of type parameters.</span></span> <span data-ttu-id="13e75-118">因此，重写的声明必须在这方面与基类版本匹配。</span><span class="sxs-lookup"><span data-stu-id="13e75-118">Therefore, the overriding declaration must match the base class version in that respect as well.</span></span>

- <span data-ttu-id="13e75-119">**附加匹配。**</span><span class="sxs-lookup"><span data-stu-id="13e75-119">**Additional Matching.**</span></span> <span data-ttu-id="13e75-120">除匹配基类版本的签名外，此声明还必须在以下方面与其匹配：</span><span class="sxs-lookup"><span data-stu-id="13e75-120">In addition to matching the signature of the base class version, this declaration must also match it in the following respects:</span></span>

  - <span data-ttu-id="13e75-121">访问级别修饰符 (如[公共](../../../visual-basic/language-reference/modifiers/public.md))</span><span class="sxs-lookup"><span data-stu-id="13e75-121">Access-level modifier (such as [Public](../../../visual-basic/language-reference/modifiers/public.md))</span></span>

  - <span data-ttu-id="13e75-122">传递的每个参数的机制 ([ByVal](../../../visual-basic/language-reference/modifiers/byval.md)或[ByRef](../../../visual-basic/language-reference/modifiers/byref.md))</span><span class="sxs-lookup"><span data-stu-id="13e75-122">Passing mechanism of each parameter ([ByVal](../../../visual-basic/language-reference/modifiers/byval.md) or [ByRef](../../../visual-basic/language-reference/modifiers/byref.md))</span></span>

  - <span data-ttu-id="13e75-123">泛型过程的每个类型参数的约束列表</span><span class="sxs-lookup"><span data-stu-id="13e75-123">Constraint lists on each type parameter of a generic procedure</span></span>

- <span data-ttu-id="13e75-124">**隐藏和重写。**</span><span class="sxs-lookup"><span data-stu-id="13e75-124">**Shadowing and Overriding.**</span></span> <span data-ttu-id="13e75-125">隐藏和重写操作都可重新定义继承的元素，但这两种方法之间又具有很大的差异。</span><span class="sxs-lookup"><span data-stu-id="13e75-125">Both shadowing and overriding redefine an inherited element, but there are significant differences between the two approaches.</span></span> <span data-ttu-id="13e75-126">有关详细信息，请参阅[Visual Basic 中的隐藏](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)。</span><span class="sxs-lookup"><span data-stu-id="13e75-126">For more information, see [Shadowing in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).</span></span>

<span data-ttu-id="13e75-127">如果使用 `Overrides`，编译器将隐式添加 `Overloads`，以便库 API 更轻松地使用 C#。</span><span class="sxs-lookup"><span data-stu-id="13e75-127">If you use `Overrides`, the compiler implicitly adds `Overloads` so that your library APIs work with C# more easily.</span></span>

<span data-ttu-id="13e75-128">`Overrides` 修饰符可用于下面的上下文中：</span><span class="sxs-lookup"><span data-stu-id="13e75-128">The `Overrides` modifier can be used in these contexts:</span></span>

- [<span data-ttu-id="13e75-129">Function 语句</span><span class="sxs-lookup"><span data-stu-id="13e75-129">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)

- [<span data-ttu-id="13e75-130">Property 语句</span><span class="sxs-lookup"><span data-stu-id="13e75-130">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)

- [<span data-ttu-id="13e75-131">Sub 语句</span><span class="sxs-lookup"><span data-stu-id="13e75-131">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)

## <a name="see-also"></a><span data-ttu-id="13e75-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="13e75-132">See also</span></span>

- [<span data-ttu-id="13e75-133">MustOverride</span><span class="sxs-lookup"><span data-stu-id="13e75-133">MustOverride</span></span>](../../../visual-basic/language-reference/modifiers/mustoverride.md)
- [<span data-ttu-id="13e75-134">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="13e75-134">NotOverridable</span></span>](../../../visual-basic/language-reference/modifiers/notoverridable.md)
- [<span data-ttu-id="13e75-135">Overridable</span><span class="sxs-lookup"><span data-stu-id="13e75-135">Overridable</span></span>](../../../visual-basic/language-reference/modifiers/overridable.md)
- [<span data-ttu-id="13e75-136">关键字</span><span class="sxs-lookup"><span data-stu-id="13e75-136">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
- [<span data-ttu-id="13e75-137">在 Visual Basic 中隐藏</span><span class="sxs-lookup"><span data-stu-id="13e75-137">Shadowing in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
- [<span data-ttu-id="13e75-138">Visual Basic 中的泛型类型</span><span class="sxs-lookup"><span data-stu-id="13e75-138">Generic Types in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [<span data-ttu-id="13e75-139">类型列表</span><span class="sxs-lookup"><span data-stu-id="13e75-139">Type List</span></span>](../../../visual-basic/language-reference/statements/type-list.md)
