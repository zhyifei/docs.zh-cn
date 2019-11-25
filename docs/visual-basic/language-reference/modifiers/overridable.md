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
# <a name="overridable-visual-basic"></a><span data-ttu-id="c733a-102">Overridable (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c733a-102">Overridable (Visual Basic)</span></span>
<span data-ttu-id="c733a-103">Specifies that a property or procedure can be overridden by an identically named property or procedure in a derived class.</span><span class="sxs-lookup"><span data-stu-id="c733a-103">Specifies that a property or procedure can be overridden by an identically named property or procedure in a derived class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c733a-104">备注</span><span class="sxs-lookup"><span data-stu-id="c733a-104">Remarks</span></span>  
 <span data-ttu-id="c733a-105">The `Overridable` modifier allows a property or method in a class to be overridden in a derived class.</span><span class="sxs-lookup"><span data-stu-id="c733a-105">The `Overridable` modifier allows a property or method in a class to be overridden in a derived class.</span></span> <span data-ttu-id="c733a-106">The [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md) modifier prevents a property or method from being overridden in a derived class.</span><span class="sxs-lookup"><span data-stu-id="c733a-106">The [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md) modifier prevents a property or method from being overridden in a derived class.</span></span>  <span data-ttu-id="c733a-107">有关详细信息，请参阅[继承基础知识](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)。</span><span class="sxs-lookup"><span data-stu-id="c733a-107">For more information, see [Inheritance Basics](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md).</span></span>  
  
 <span data-ttu-id="c733a-108">If the `Overridable` or `NotOverridable` modifier is not specified, the default setting depends on whether the property or method overrides a base class property or method.</span><span class="sxs-lookup"><span data-stu-id="c733a-108">If the `Overridable` or `NotOverridable` modifier is not specified, the default setting depends on whether the property or method overrides a base class property or method.</span></span> <span data-ttu-id="c733a-109">If the property or method overrides a base class property or method, the default setting is `Overridable`; otherwise, it is `NotOverridable`.</span><span class="sxs-lookup"><span data-stu-id="c733a-109">If the property or method overrides a base class property or method, the default setting is `Overridable`; otherwise, it is `NotOverridable`.</span></span>  
  
 <span data-ttu-id="c733a-110">You can shadow or override to redefine an inherited element, but there are significant differences between the two approaches.</span><span class="sxs-lookup"><span data-stu-id="c733a-110">You can shadow or override to redefine an inherited element, but there are significant differences between the two approaches.</span></span> <span data-ttu-id="c733a-111">For more information, see [Shadowing in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).</span><span class="sxs-lookup"><span data-stu-id="c733a-111">For more information, see [Shadowing in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).</span></span>  
  
 <span data-ttu-id="c733a-112">An element that can be overridden is sometimes referred to as a *virtual* element.</span><span class="sxs-lookup"><span data-stu-id="c733a-112">An element that can be overridden is sometimes referred to as a *virtual* element.</span></span> <span data-ttu-id="c733a-113">If it can be overridden, but does not have to be, it is sometimes also called a *concrete* element.</span><span class="sxs-lookup"><span data-stu-id="c733a-113">If it can be overridden, but does not have to be, it is sometimes also called a *concrete* element.</span></span>  
  
 <span data-ttu-id="c733a-114">You can use `Overridable` only in a property or procedure declaration statement.</span><span class="sxs-lookup"><span data-stu-id="c733a-114">You can use `Overridable` only in a property or procedure declaration statement.</span></span>  
  
## <a name="combined-modifiers"></a><span data-ttu-id="c733a-115">Combined Modifiers</span><span class="sxs-lookup"><span data-stu-id="c733a-115">Combined Modifiers</span></span>  
 <span data-ttu-id="c733a-116">You cannot specify `Overridable` or `NotOverridable` for a `Private` method.</span><span class="sxs-lookup"><span data-stu-id="c733a-116">You cannot specify `Overridable` or `NotOverridable` for a `Private` method.</span></span>  
  
 <span data-ttu-id="c733a-117">You cannot specify `Overridable` together with `MustOverride`, `NotOverridable`, or `Shared` in the same declaration.</span><span class="sxs-lookup"><span data-stu-id="c733a-117">You cannot specify `Overridable` together with `MustOverride`, `NotOverridable`, or `Shared` in the same declaration.</span></span>  
  
 <span data-ttu-id="c733a-118">由于重写元素是隐式可重写的，因此不能将 `Overridable` 与 `Overrides` 组合到一起。</span><span class="sxs-lookup"><span data-stu-id="c733a-118">Because an overriding element is implicitly overridable, you cannot combine `Overridable` with `Overrides`.</span></span>  
  
## <a name="usage"></a><span data-ttu-id="c733a-119">用法</span><span class="sxs-lookup"><span data-stu-id="c733a-119">Usage</span></span>  
 <span data-ttu-id="c733a-120">`Overridable` 修饰符可用于下面的上下文中：</span><span class="sxs-lookup"><span data-stu-id="c733a-120">The `Overridable` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="c733a-121">Function 语句</span><span class="sxs-lookup"><span data-stu-id="c733a-121">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="c733a-122">Property 语句</span><span class="sxs-lookup"><span data-stu-id="c733a-122">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="c733a-123">Sub 语句</span><span class="sxs-lookup"><span data-stu-id="c733a-123">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="c733a-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="c733a-124">See also</span></span>

- [<span data-ttu-id="c733a-125">修饰符</span><span class="sxs-lookup"><span data-stu-id="c733a-125">Modifiers</span></span>](../../../visual-basic/language-reference/modifiers/index.md)
- [<span data-ttu-id="c733a-126">继承的基础知识</span><span class="sxs-lookup"><span data-stu-id="c733a-126">Inheritance Basics</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
- [<span data-ttu-id="c733a-127">New</span><span class="sxs-lookup"><span data-stu-id="c733a-127">MustOverride</span></span>](../../../visual-basic/language-reference/modifiers/mustoverride.md)
- [<span data-ttu-id="c733a-128">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="c733a-128">NotOverridable</span></span>](../../../visual-basic/language-reference/modifiers/notoverridable.md)
- [<span data-ttu-id="c733a-129">Overrides</span><span class="sxs-lookup"><span data-stu-id="c733a-129">Overrides</span></span>](../../../visual-basic/language-reference/modifiers/overrides.md)
- [<span data-ttu-id="c733a-130">关键字</span><span class="sxs-lookup"><span data-stu-id="c733a-130">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
- [<span data-ttu-id="c733a-131">Shadowing in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c733a-131">Shadowing in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
