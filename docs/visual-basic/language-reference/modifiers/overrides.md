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
ms.openlocfilehash: 81118b9e97f320bffdbb58e5e1a2859052c4cee5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33602513"
---
# <a name="overrides-visual-basic"></a><span data-ttu-id="4f927-102">Overrides (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4f927-102">Overrides (Visual Basic)</span></span>
<span data-ttu-id="4f927-103">指定某一属性或过程可重写从基类中继承的具有相同名称的属性或过程。</span><span class="sxs-lookup"><span data-stu-id="4f927-103">Specifies that a property or procedure overrides an identically named property or procedure inherited from a base class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4f927-104">备注</span><span class="sxs-lookup"><span data-stu-id="4f927-104">Remarks</span></span>  
  
## <a name="rules"></a><span data-ttu-id="4f927-105">规则</span><span class="sxs-lookup"><span data-stu-id="4f927-105">Rules</span></span>  
  
-   <span data-ttu-id="4f927-106">**声明上下文。**</span><span class="sxs-lookup"><span data-stu-id="4f927-106">**Declaration Context.**</span></span> <span data-ttu-id="4f927-107">只能在属性或过程声明语句中使用 `Overrides`。</span><span class="sxs-lookup"><span data-stu-id="4f927-107">You can use `Overrides` only in a property or procedure declaration statement.</span></span>  
  
-   <span data-ttu-id="4f927-108">**组合的修饰符。**</span><span class="sxs-lookup"><span data-stu-id="4f927-108">**Combined Modifiers.**</span></span> <span data-ttu-id="4f927-109">不能在同一过程声明中同时指定 `Overrides` 和 `Shadows` 或 `Shared`。</span><span class="sxs-lookup"><span data-stu-id="4f927-109">You cannot specify `Overrides` together with `Shadows` or `Shared` in the same declaration.</span></span> <span data-ttu-id="4f927-110">由于重写元素是隐式可重写的，因此不能将 `Overridable` 与 `Overrides` 组合到一起。</span><span class="sxs-lookup"><span data-stu-id="4f927-110">Because an overriding element is implicitly overridable, you cannot combine `Overridable` with `Overrides`.</span></span>  
  
-   <span data-ttu-id="4f927-111">**匹配的签名。**</span><span class="sxs-lookup"><span data-stu-id="4f927-111">**Matching Signatures.**</span></span> <span data-ttu-id="4f927-112">此声明的签名必须完全匹配*签名*的属性或过程，它将重写。</span><span class="sxs-lookup"><span data-stu-id="4f927-112">The signature of this declaration must exactly match the *signature* of the property or procedure that it overrides.</span></span> <span data-ttu-id="4f927-113">这意味着参数列表必须具有相同数量的参数，并且排序顺序和数据类型都必须完全相同。</span><span class="sxs-lookup"><span data-stu-id="4f927-113">This means the parameter lists must have the same number of parameters, in the same order, with the same data types.</span></span>  
  
     <span data-ttu-id="4f927-114">除签名外，重写的声明还必须完全匹配以下项：</span><span class="sxs-lookup"><span data-stu-id="4f927-114">In addition to the signature, the overriding declaration must also exactly match the following:</span></span>  
  
    -   <span data-ttu-id="4f927-115">访问级别</span><span class="sxs-lookup"><span data-stu-id="4f927-115">The access level</span></span>  
  
    -   <span data-ttu-id="4f927-116">返回类型（如有）</span><span class="sxs-lookup"><span data-stu-id="4f927-116">The return type, if any</span></span>  
  
-   <span data-ttu-id="4f927-117">**泛型签名。**</span><span class="sxs-lookup"><span data-stu-id="4f927-117">**Generic Signatures.**</span></span> <span data-ttu-id="4f927-118">对于泛型过程，签名包括类型参数的数量。</span><span class="sxs-lookup"><span data-stu-id="4f927-118">For a generic procedure, the signature includes the number of type parameters.</span></span> <span data-ttu-id="4f927-119">因此，重写的声明必须在这方面与基类版本匹配。</span><span class="sxs-lookup"><span data-stu-id="4f927-119">Therefore, the overriding declaration must match the base class version in that respect as well.</span></span>  
  
-   <span data-ttu-id="4f927-120">**附加匹配。**</span><span class="sxs-lookup"><span data-stu-id="4f927-120">**Additional Matching.**</span></span> <span data-ttu-id="4f927-121">除匹配基类版本的签名外，此声明还必须在以下方面与其匹配：</span><span class="sxs-lookup"><span data-stu-id="4f927-121">In addition to matching the signature of the base class version, this declaration must also match it in the following respects:</span></span>  
  
    -   <span data-ttu-id="4f927-122">访问级别修饰符 (如[公共](../../../visual-basic/language-reference/modifiers/public.md))</span><span class="sxs-lookup"><span data-stu-id="4f927-122">Access-level modifier (such as [Public](../../../visual-basic/language-reference/modifiers/public.md))</span></span>  
  
    -   <span data-ttu-id="4f927-123">传递的每个参数的机制 ([ByVal](../../../visual-basic/language-reference/modifiers/byval.md)或[ByRef](../../../visual-basic/language-reference/modifiers/byref.md))</span><span class="sxs-lookup"><span data-stu-id="4f927-123">Passing mechanism of each parameter ([ByVal](../../../visual-basic/language-reference/modifiers/byval.md) or [ByRef](../../../visual-basic/language-reference/modifiers/byref.md))</span></span>  
  
    -   <span data-ttu-id="4f927-124">泛型过程的每个类型参数的约束列表</span><span class="sxs-lookup"><span data-stu-id="4f927-124">Constraint lists on each type parameter of a generic procedure</span></span>  
  
-   <span data-ttu-id="4f927-125">**隐藏和重写。**</span><span class="sxs-lookup"><span data-stu-id="4f927-125">**Shadowing and Overriding.**</span></span> <span data-ttu-id="4f927-126">隐藏和重写操作都可重新定义继承的元素，但这两种方法之间又具有很大的差异。</span><span class="sxs-lookup"><span data-stu-id="4f927-126">Both shadowing and overriding redefine an inherited element, but there are significant differences between the two approaches.</span></span> <span data-ttu-id="4f927-127">有关详细信息，请参阅[Visual Basic 中的隐藏](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)。</span><span class="sxs-lookup"><span data-stu-id="4f927-127">For more information, see [Shadowing in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).</span></span>  
  
 <span data-ttu-id="4f927-128">如果使用 `Overrides`，编译器将隐式添加 `Overloads`，以便库 API 更轻松地使用 C#。</span><span class="sxs-lookup"><span data-stu-id="4f927-128">If you use `Overrides`, the compiler implicitly adds `Overloads` so that your library APIs work with C# more easily.</span></span>  
  
 <span data-ttu-id="4f927-129">`Overrides` 修饰符可用于下面的上下文中：</span><span class="sxs-lookup"><span data-stu-id="4f927-129">The `Overrides` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="4f927-130">Function 语句</span><span class="sxs-lookup"><span data-stu-id="4f927-130">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="4f927-131">Property 语句</span><span class="sxs-lookup"><span data-stu-id="4f927-131">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="4f927-132">Sub 语句</span><span class="sxs-lookup"><span data-stu-id="4f927-132">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="4f927-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="4f927-133">See Also</span></span>  
 [<span data-ttu-id="4f927-134">MustOverride</span><span class="sxs-lookup"><span data-stu-id="4f927-134">MustOverride</span></span>](../../../visual-basic/language-reference/modifiers/mustoverride.md)  
 [<span data-ttu-id="4f927-135">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="4f927-135">NotOverridable</span></span>](../../../visual-basic/language-reference/modifiers/notoverridable.md)  
 [<span data-ttu-id="4f927-136">Overridable</span><span class="sxs-lookup"><span data-stu-id="4f927-136">Overridable</span></span>](../../../visual-basic/language-reference/modifiers/overridable.md)  
 [<span data-ttu-id="4f927-137">关键字</span><span class="sxs-lookup"><span data-stu-id="4f927-137">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)  
 [<span data-ttu-id="4f927-138">在 Visual Basic 中隐藏</span><span class="sxs-lookup"><span data-stu-id="4f927-138">Shadowing in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)  
 [<span data-ttu-id="4f927-139">Visual Basic 中的泛型类型</span><span class="sxs-lookup"><span data-stu-id="4f927-139">Generic Types in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)  
 [<span data-ttu-id="4f927-140">类型列表</span><span class="sxs-lookup"><span data-stu-id="4f927-140">Type List</span></span>](../../../visual-basic/language-reference/statements/type-list.md)
