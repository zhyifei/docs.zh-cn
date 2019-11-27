---
title: Overrides
ms.date: 07/20/2015
f1_keywords:
- Overridable
- vb.Overridable
helpviewer_keywords:
- elements [Visual Basic], concrete
- properties [Visual Basic], redefining
- overriding, Overridable keyword
- elements [Visual Basic], virtual
- virtual [elements VB]
- procedures [Visual Basic], overriding
- concrete [elements VB]
- procedures [Visual Basic], redefining
- Overridable keyword [Visual Basic]
- properties [Visual Basic], overriding
ms.assetid: 612581e7-8a4c-4a5d-beff-3402fffa6f35
ms.openlocfilehash: 9c639665fd92a56de6fb6e5147cda873ef457b45
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351392"
---
# <a name="overridable-visual-basic"></a><span data-ttu-id="c912a-102">Overridable (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c912a-102">Overridable (Visual Basic)</span></span>
<span data-ttu-id="c912a-103">指定属性或过程可由派生类中具有相同名称的属性或过程重写。</span><span class="sxs-lookup"><span data-stu-id="c912a-103">Specifies that a property or procedure can be overridden by an identically named property or procedure in a derived class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c912a-104">备注</span><span class="sxs-lookup"><span data-stu-id="c912a-104">Remarks</span></span>  
 <span data-ttu-id="c912a-105">`Overridable` 修饰符允许在派生类中重写类中的属性或方法。</span><span class="sxs-lookup"><span data-stu-id="c912a-105">The `Overridable` modifier allows a property or method in a class to be overridden in a derived class.</span></span> <span data-ttu-id="c912a-106">[NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md)修饰符防止在派生类中重写属性或方法。</span><span class="sxs-lookup"><span data-stu-id="c912a-106">The [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md) modifier prevents a property or method from being overridden in a derived class.</span></span>  <span data-ttu-id="c912a-107">有关详细信息，请参阅[继承基础知识](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)。</span><span class="sxs-lookup"><span data-stu-id="c912a-107">For more information, see [Inheritance Basics](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md).</span></span>  
  
 <span data-ttu-id="c912a-108">如果未指定 `Overridable` 或 `NotOverridable` 修饰符，则默认设置取决于属性或方法是重写基类属性还是重写方法。</span><span class="sxs-lookup"><span data-stu-id="c912a-108">If the `Overridable` or `NotOverridable` modifier is not specified, the default setting depends on whether the property or method overrides a base class property or method.</span></span> <span data-ttu-id="c912a-109">如果属性或方法重写基类属性或方法，则默认设置为 `Overridable`;否则，`NotOverridable`。</span><span class="sxs-lookup"><span data-stu-id="c912a-109">If the property or method overrides a base class property or method, the default setting is `Overridable`; otherwise, it is `NotOverridable`.</span></span>  
  
 <span data-ttu-id="c912a-110">您可以隐藏或重写来重新定义继承的元素，但这两种方法之间的差异很大。</span><span class="sxs-lookup"><span data-stu-id="c912a-110">You can shadow or override to redefine an inherited element, but there are significant differences between the two approaches.</span></span> <span data-ttu-id="c912a-111">有关详细信息，请参阅[Visual Basic 中的隐藏](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)。</span><span class="sxs-lookup"><span data-stu-id="c912a-111">For more information, see [Shadowing in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).</span></span>  
  
 <span data-ttu-id="c912a-112">可以重写的元素有时称为*虚拟*元素。</span><span class="sxs-lookup"><span data-stu-id="c912a-112">An element that can be overridden is sometimes referred to as a *virtual* element.</span></span> <span data-ttu-id="c912a-113">如果可以重写，但不一定是，则有时也称为*具体*元素。</span><span class="sxs-lookup"><span data-stu-id="c912a-113">If it can be overridden, but does not have to be, it is sometimes also called a *concrete* element.</span></span>  
  
 <span data-ttu-id="c912a-114">只能在属性或过程声明语句中使用 `Overridable`。</span><span class="sxs-lookup"><span data-stu-id="c912a-114">You can use `Overridable` only in a property or procedure declaration statement.</span></span>  
  
## <a name="combined-modifiers"></a><span data-ttu-id="c912a-115">组合修饰符</span><span class="sxs-lookup"><span data-stu-id="c912a-115">Combined Modifiers</span></span>  
 <span data-ttu-id="c912a-116">不能为 `Private` 方法指定 `Overridable` 或 `NotOverridable`。</span><span class="sxs-lookup"><span data-stu-id="c912a-116">You cannot specify `Overridable` or `NotOverridable` for a `Private` method.</span></span>  
  
 <span data-ttu-id="c912a-117">不能在同一声明中同时指定 `Overridable` 与 `MustOverride`、`NotOverridable`或 `Shared`。</span><span class="sxs-lookup"><span data-stu-id="c912a-117">You cannot specify `Overridable` together with `MustOverride`, `NotOverridable`, or `Shared` in the same declaration.</span></span>  
  
 <span data-ttu-id="c912a-118">由于重写元素是隐式可重写的，因此不能将 `Overridable` 与 `Overrides` 组合到一起。</span><span class="sxs-lookup"><span data-stu-id="c912a-118">Because an overriding element is implicitly overridable, you cannot combine `Overridable` with `Overrides`.</span></span>  
  
## <a name="usage"></a><span data-ttu-id="c912a-119">用法</span><span class="sxs-lookup"><span data-stu-id="c912a-119">Usage</span></span>  
 <span data-ttu-id="c912a-120">`Overridable` 修饰符可用于下面的上下文中：</span><span class="sxs-lookup"><span data-stu-id="c912a-120">The `Overridable` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="c912a-121">Function 语句</span><span class="sxs-lookup"><span data-stu-id="c912a-121">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="c912a-122">Property 语句</span><span class="sxs-lookup"><span data-stu-id="c912a-122">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="c912a-123">Sub 语句</span><span class="sxs-lookup"><span data-stu-id="c912a-123">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="c912a-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c912a-124">See also</span></span>

- [<span data-ttu-id="c912a-125">修饰符</span><span class="sxs-lookup"><span data-stu-id="c912a-125">Modifiers</span></span>](../../../visual-basic/language-reference/modifiers/index.md)
- [<span data-ttu-id="c912a-126">继承的基础知识</span><span class="sxs-lookup"><span data-stu-id="c912a-126">Inheritance Basics</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
- [<span data-ttu-id="c912a-127">MyBase</span><span class="sxs-lookup"><span data-stu-id="c912a-127">MustOverride</span></span>](../../../visual-basic/language-reference/modifiers/mustoverride.md)
- [<span data-ttu-id="c912a-128">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="c912a-128">NotOverridable</span></span>](../../../visual-basic/language-reference/modifiers/notoverridable.md)
- [<span data-ttu-id="c912a-129">Overrides</span><span class="sxs-lookup"><span data-stu-id="c912a-129">Overrides</span></span>](../../../visual-basic/language-reference/modifiers/overrides.md)
- [<span data-ttu-id="c912a-130">关键字</span><span class="sxs-lookup"><span data-stu-id="c912a-130">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
- [<span data-ttu-id="c912a-131">Visual Basic 中的阴影</span><span class="sxs-lookup"><span data-stu-id="c912a-131">Shadowing in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
