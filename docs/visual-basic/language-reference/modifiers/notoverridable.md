---
title: NotOverridable
ms.date: 07/20/2015
f1_keywords:
- vb.NotOverridable
- NotOverridable
helpviewer_keywords:
- sealed methods [Visual Basic]
- NotOverridable keyword [Visual Basic]
- properties [Visual Basic], redefining
- elements [Visual Basic], sealed
- sealed [elements VB]
- procedures [Visual Basic], overriding
- procedures [Visual Basic], redefining
- overriding
- methods [Visual Basic], sealed
- properties [Visual Basic], overriding
ms.assetid: 66ec6984-f5f5-4857-b362-6a3907aaf9e0
ms.openlocfilehash: c55d57bb3008b2825fe5382844908ea32f0d500c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351446"
---
# <a name="notoverridable-visual-basic"></a><span data-ttu-id="0f87d-102">NotOverridable (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0f87d-102">NotOverridable (Visual Basic)</span></span>
<span data-ttu-id="0f87d-103">指定不能在派生类中重写属性或过程。</span><span class="sxs-lookup"><span data-stu-id="0f87d-103">Specifies that a property or procedure cannot be overridden in a derived class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0f87d-104">备注</span><span class="sxs-lookup"><span data-stu-id="0f87d-104">Remarks</span></span>  
 <span data-ttu-id="0f87d-105">`NotOverridable` 修饰符可防止在派生类中重写属性或方法。</span><span class="sxs-lookup"><span data-stu-id="0f87d-105">The `NotOverridable` modifier prevents a property or method from being overridden in a derived class.</span></span>  <span data-ttu-id="0f87d-106">可[重写](../../../visual-basic/language-reference/modifiers/overridable.md)的修饰符允许在派生类中重写类中的属性或方法。</span><span class="sxs-lookup"><span data-stu-id="0f87d-106">The [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md) modifier allows a property or method in a class to be overridden in a derived class.</span></span> <span data-ttu-id="0f87d-107">有关详细信息，请参阅[继承基础知识](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)。</span><span class="sxs-lookup"><span data-stu-id="0f87d-107">For more information, see [Inheritance Basics](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md).</span></span>  
  
 <span data-ttu-id="0f87d-108">如果未指定 `Overridable` 或 `NotOverridable` 修饰符，则默认设置取决于属性或方法是重写基类属性还是重写方法。</span><span class="sxs-lookup"><span data-stu-id="0f87d-108">If the `Overridable` or `NotOverridable` modifier is not specified, the default setting depends on whether the property or method overrides a base class property or method.</span></span> <span data-ttu-id="0f87d-109">如果属性或方法重写基类属性或方法，则默认设置为 `Overridable`;否则，`NotOverridable`。</span><span class="sxs-lookup"><span data-stu-id="0f87d-109">If the property or method overrides a base class property or method, the default setting is `Overridable`; otherwise, it is `NotOverridable`.</span></span>  
  
 <span data-ttu-id="0f87d-110">不能重写的元素有时称为*密封*元素。</span><span class="sxs-lookup"><span data-stu-id="0f87d-110">An element that cannot be overridden is sometimes called a *sealed* element.</span></span>  
  
 <span data-ttu-id="0f87d-111">只能在属性或过程声明语句中使用 `NotOverridable`。</span><span class="sxs-lookup"><span data-stu-id="0f87d-111">You can use `NotOverridable` only in a property or procedure declaration statement.</span></span> <span data-ttu-id="0f87d-112">只能在替代另一个属性或过程的属性或过程上指定 `NotOverridable`，也就是说，只能与 `Overrides`结合使用。</span><span class="sxs-lookup"><span data-stu-id="0f87d-112">You can specify `NotOverridable` only on a property or procedure that overrides another property or procedure, that is, only in combination with `Overrides`.</span></span>  
  
## <a name="combined-modifiers"></a><span data-ttu-id="0f87d-113">组合修饰符</span><span class="sxs-lookup"><span data-stu-id="0f87d-113">Combined Modifiers</span></span>  
 <span data-ttu-id="0f87d-114">不能为 `Private` 方法指定 `Overridable` 或 `NotOverridable`。</span><span class="sxs-lookup"><span data-stu-id="0f87d-114">You cannot specify `Overridable` or `NotOverridable` for a `Private` method.</span></span>  
  
 <span data-ttu-id="0f87d-115">不能在同一声明中同时指定 `NotOverridable` 与 `MustOverride`、`Overridable`或 `Shared`。</span><span class="sxs-lookup"><span data-stu-id="0f87d-115">You cannot specify `NotOverridable` together with `MustOverride`, `Overridable`, or `Shared` in the same declaration.</span></span>  
  
## <a name="usage"></a><span data-ttu-id="0f87d-116">用法</span><span class="sxs-lookup"><span data-stu-id="0f87d-116">Usage</span></span>  
 <span data-ttu-id="0f87d-117">`NotOverridable` 修饰符可用于下面的上下文中：</span><span class="sxs-lookup"><span data-stu-id="0f87d-117">The `NotOverridable` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="0f87d-118">Function 语句</span><span class="sxs-lookup"><span data-stu-id="0f87d-118">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="0f87d-119">Property 语句</span><span class="sxs-lookup"><span data-stu-id="0f87d-119">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="0f87d-120">Sub 语句</span><span class="sxs-lookup"><span data-stu-id="0f87d-120">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="0f87d-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0f87d-121">See also</span></span>

- [<span data-ttu-id="0f87d-122">修饰符</span><span class="sxs-lookup"><span data-stu-id="0f87d-122">Modifiers</span></span>](../../../visual-basic/language-reference/modifiers/index.md)
- [<span data-ttu-id="0f87d-123">继承的基础知识</span><span class="sxs-lookup"><span data-stu-id="0f87d-123">Inheritance Basics</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
- [<span data-ttu-id="0f87d-124">MyBase</span><span class="sxs-lookup"><span data-stu-id="0f87d-124">MustOverride</span></span>](../../../visual-basic/language-reference/modifiers/mustoverride.md)
- [<span data-ttu-id="0f87d-125">Overrides</span><span class="sxs-lookup"><span data-stu-id="0f87d-125">Overridable</span></span>](../../../visual-basic/language-reference/modifiers/overridable.md)
- [<span data-ttu-id="0f87d-126">Overrides</span><span class="sxs-lookup"><span data-stu-id="0f87d-126">Overrides</span></span>](../../../visual-basic/language-reference/modifiers/overrides.md)
- [<span data-ttu-id="0f87d-127">关键字</span><span class="sxs-lookup"><span data-stu-id="0f87d-127">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
- [<span data-ttu-id="0f87d-128">Visual Basic 中的阴影</span><span class="sxs-lookup"><span data-stu-id="0f87d-128">Shadowing in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
