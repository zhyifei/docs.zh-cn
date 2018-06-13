---
title: Overridable (Visual Basic)
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
ms.openlocfilehash: 4844bf7f3ecf23335715b950a96be15e54ebc601
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33603764"
---
# <a name="overridable-visual-basic"></a><span data-ttu-id="1f34d-102">Overridable (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1f34d-102">Overridable (Visual Basic)</span></span>
<span data-ttu-id="1f34d-103">指定属性或过程可以覆盖具有相同名称的属性或派生类中的过程。</span><span class="sxs-lookup"><span data-stu-id="1f34d-103">Specifies that a property or procedure can be overridden by an identically named property or procedure in a derived class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1f34d-104">备注</span><span class="sxs-lookup"><span data-stu-id="1f34d-104">Remarks</span></span>  
 <span data-ttu-id="1f34d-105">`Overridable`修饰符在派生类中重写的类中允许的属性或方法。</span><span class="sxs-lookup"><span data-stu-id="1f34d-105">The `Overridable` modifier allows a property or method in a class to be overridden in a derived class.</span></span> <span data-ttu-id="1f34d-106">[NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md)修饰符防止属性或方法被重写派生类中。</span><span class="sxs-lookup"><span data-stu-id="1f34d-106">The [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md) modifier prevents a property or method from being overridden in a derived class.</span></span>  <span data-ttu-id="1f34d-107">有关详细信息，请参阅[继承基础知识](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)。</span><span class="sxs-lookup"><span data-stu-id="1f34d-107">For more information, see [Inheritance Basics](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md).</span></span>  
  
 <span data-ttu-id="1f34d-108">如果`Overridable`或`NotOverridable`修饰符未指定，则默认设置取决于是否属性或方法重写基类属性或方法。</span><span class="sxs-lookup"><span data-stu-id="1f34d-108">If the `Overridable` or `NotOverridable` modifier is not specified, the default setting depends on whether the property or method overrides a base class property or method.</span></span> <span data-ttu-id="1f34d-109">如果属性或方法重写基类属性或方法，默认设置是`Overridable`; 否则为它是`NotOverridable`。</span><span class="sxs-lookup"><span data-stu-id="1f34d-109">If the property or method overrides a base class property or method, the default setting is `Overridable`; otherwise, it is `NotOverridable`.</span></span>  
  
 <span data-ttu-id="1f34d-110">你可以通过隐藏或重写以重新定义继承的元素，但有两种方法之间的重要差异。</span><span class="sxs-lookup"><span data-stu-id="1f34d-110">You can shadow or override to redefine an inherited element, but there are significant differences between the two approaches.</span></span> <span data-ttu-id="1f34d-111">有关详细信息，请参阅[Visual Basic 中的隐藏](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)。</span><span class="sxs-lookup"><span data-stu-id="1f34d-111">For more information, see [Shadowing in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).</span></span>  
  
 <span data-ttu-id="1f34d-112">可以重写的元素有时称为*虚拟*元素。</span><span class="sxs-lookup"><span data-stu-id="1f34d-112">An element that can be overridden is sometimes referred to as a *virtual* element.</span></span> <span data-ttu-id="1f34d-113">如果它可以重写，但不一定要它有时也称为*具体*元素。</span><span class="sxs-lookup"><span data-stu-id="1f34d-113">If it can be overridden, but does not have to be, it is sometimes also called a *concrete* element.</span></span>  
  
 <span data-ttu-id="1f34d-114">只能在属性或过程声明语句中使用 `Overridable`。</span><span class="sxs-lookup"><span data-stu-id="1f34d-114">You can use `Overridable` only in a property or procedure declaration statement.</span></span>  
  
## <a name="combined-modifiers"></a><span data-ttu-id="1f34d-115">组合的修饰符</span><span class="sxs-lookup"><span data-stu-id="1f34d-115">Combined Modifiers</span></span>  
 <span data-ttu-id="1f34d-116">不能指定`Overridable`或`NotOverridable`为`Private`方法。</span><span class="sxs-lookup"><span data-stu-id="1f34d-116">You cannot specify `Overridable` or `NotOverridable` for a `Private` method.</span></span>  
  
 <span data-ttu-id="1f34d-117">不能指定`Overridable`连同`MustOverride`， `NotOverridable`，或`Shared`同一声明中。</span><span class="sxs-lookup"><span data-stu-id="1f34d-117">You cannot specify `Overridable` together with `MustOverride`, `NotOverridable`, or `Shared` in the same declaration.</span></span>  
  
 <span data-ttu-id="1f34d-118">由于重写元素是隐式可重写的，因此不能将 `Overridable` 与 `Overrides` 组合到一起。</span><span class="sxs-lookup"><span data-stu-id="1f34d-118">Because an overriding element is implicitly overridable, you cannot combine `Overridable` with `Overrides`.</span></span>  
  
## <a name="usage"></a><span data-ttu-id="1f34d-119">用法</span><span class="sxs-lookup"><span data-stu-id="1f34d-119">Usage</span></span>  
 <span data-ttu-id="1f34d-120">`Overridable` 修饰符可用于下面的上下文中：</span><span class="sxs-lookup"><span data-stu-id="1f34d-120">The `Overridable` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="1f34d-121">Function 语句</span><span class="sxs-lookup"><span data-stu-id="1f34d-121">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="1f34d-122">Property 语句</span><span class="sxs-lookup"><span data-stu-id="1f34d-122">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="1f34d-123">Sub 语句</span><span class="sxs-lookup"><span data-stu-id="1f34d-123">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="1f34d-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="1f34d-124">See Also</span></span>  
 [<span data-ttu-id="1f34d-125">修饰符</span><span class="sxs-lookup"><span data-stu-id="1f34d-125">Modifiers</span></span>](../../../visual-basic/language-reference/modifiers/index.md)  
 [<span data-ttu-id="1f34d-126">继承的基础知识</span><span class="sxs-lookup"><span data-stu-id="1f34d-126">Inheritance Basics</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)  
 [<span data-ttu-id="1f34d-127">MustOverride</span><span class="sxs-lookup"><span data-stu-id="1f34d-127">MustOverride</span></span>](../../../visual-basic/language-reference/modifiers/mustoverride.md)  
 [<span data-ttu-id="1f34d-128">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="1f34d-128">NotOverridable</span></span>](../../../visual-basic/language-reference/modifiers/notoverridable.md)  
 [<span data-ttu-id="1f34d-129">Overrides</span><span class="sxs-lookup"><span data-stu-id="1f34d-129">Overrides</span></span>](../../../visual-basic/language-reference/modifiers/overrides.md)  
 [<span data-ttu-id="1f34d-130">关键字</span><span class="sxs-lookup"><span data-stu-id="1f34d-130">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)  
 [<span data-ttu-id="1f34d-131">在 Visual Basic 中隐藏</span><span class="sxs-lookup"><span data-stu-id="1f34d-131">Shadowing in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
