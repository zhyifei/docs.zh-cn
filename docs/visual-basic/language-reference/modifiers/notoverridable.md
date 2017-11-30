---
title: NotOverridable (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 6fc5fb006b36cda1b6ad0e128604bc3bb427fd94
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="notoverridable-visual-basic"></a><span data-ttu-id="86777-102">NotOverridable (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="86777-102">NotOverridable (Visual Basic)</span></span>
<span data-ttu-id="86777-103">指定的属性或过程不能重写派生类中。</span><span class="sxs-lookup"><span data-stu-id="86777-103">Specifies that a property or procedure cannot be overridden in a derived class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="86777-104">备注</span><span class="sxs-lookup"><span data-stu-id="86777-104">Remarks</span></span>  
 <span data-ttu-id="86777-105">`NotOverridable`修饰符防止属性或方法被重写派生类中。</span><span class="sxs-lookup"><span data-stu-id="86777-105">The `NotOverridable` modifier prevents a property or method from being overridden in a derived class.</span></span>  <span data-ttu-id="86777-106">[可重写](../../../visual-basic/language-reference/modifiers/overridable.md)修饰符在派生类中重写的类中允许的属性或方法。</span><span class="sxs-lookup"><span data-stu-id="86777-106">The [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md) modifier allows a property or method in a class to be overridden in a derived class.</span></span> <span data-ttu-id="86777-107">有关详细信息，请参阅[继承基础知识](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)。</span><span class="sxs-lookup"><span data-stu-id="86777-107">For more information, see [Inheritance Basics](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md).</span></span>  
  
 <span data-ttu-id="86777-108">如果`Overridable`或`NotOverridable`修饰符未指定，则默认设置取决于是否属性或方法重写基类属性或方法。</span><span class="sxs-lookup"><span data-stu-id="86777-108">If the `Overridable` or `NotOverridable` modifier is not specified, the default setting depends on whether the property or method overrides a base class property or method.</span></span> <span data-ttu-id="86777-109">如果属性或方法重写基类属性或方法，默认设置是`Overridable`; 否则为它是`NotOverridable`。</span><span class="sxs-lookup"><span data-stu-id="86777-109">If the property or method overrides a base class property or method, the default setting is `Overridable`; otherwise, it is `NotOverridable`.</span></span>  
  
 <span data-ttu-id="86777-110">不能重写元素有时称为*密封*元素。</span><span class="sxs-lookup"><span data-stu-id="86777-110">An element that cannot be overridden is sometimes called a *sealed* element.</span></span>  
  
 <span data-ttu-id="86777-111">只能在属性或过程声明语句中使用 `NotOverridable`。</span><span class="sxs-lookup"><span data-stu-id="86777-111">You can use `NotOverridable` only in a property or procedure declaration statement.</span></span> <span data-ttu-id="86777-112">你可以指定`NotOverridable`只会在属性或另一个属性或过程，也就是说，仅在中重写与结合使用的过程`Overrides`。</span><span class="sxs-lookup"><span data-stu-id="86777-112">You can specify `NotOverridable` only on a property or procedure that overrides another property or procedure, that is, only in combination with `Overrides`.</span></span>  
  
## <a name="combined-modifiers"></a><span data-ttu-id="86777-113">组合的修饰符</span><span class="sxs-lookup"><span data-stu-id="86777-113">Combined Modifiers</span></span>  
 <span data-ttu-id="86777-114">不能指定`Overridable`或`NotOverridable`为`Private`方法。</span><span class="sxs-lookup"><span data-stu-id="86777-114">You cannot specify `Overridable` or `NotOverridable` for a `Private` method.</span></span>  
  
 <span data-ttu-id="86777-115">不能指定`NotOverridable`连同`MustOverride`， `Overridable`，或`Shared`同一声明中。</span><span class="sxs-lookup"><span data-stu-id="86777-115">You cannot specify `NotOverridable` together with `MustOverride`, `Overridable`, or `Shared` in the same declaration.</span></span>  
  
## <a name="usage"></a><span data-ttu-id="86777-116">用法</span><span class="sxs-lookup"><span data-stu-id="86777-116">Usage</span></span>  
 <span data-ttu-id="86777-117">`NotOverridable` 修饰符可用于下面的上下文中：</span><span class="sxs-lookup"><span data-stu-id="86777-117">The `NotOverridable` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="86777-118">Function 语句</span><span class="sxs-lookup"><span data-stu-id="86777-118">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="86777-119">Property 语句</span><span class="sxs-lookup"><span data-stu-id="86777-119">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="86777-120">Sub 语句</span><span class="sxs-lookup"><span data-stu-id="86777-120">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="86777-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="86777-121">See Also</span></span>  
 [<span data-ttu-id="86777-122">修饰符</span><span class="sxs-lookup"><span data-stu-id="86777-122">Modifiers</span></span>](../../../visual-basic/language-reference/modifiers/index.md)  
 [<span data-ttu-id="86777-123">继承的基础知识</span><span class="sxs-lookup"><span data-stu-id="86777-123">Inheritance Basics</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)  
 [<span data-ttu-id="86777-124">MustOverride</span><span class="sxs-lookup"><span data-stu-id="86777-124">MustOverride</span></span>](../../../visual-basic/language-reference/modifiers/mustoverride.md)  
 [<span data-ttu-id="86777-125">Overridable</span><span class="sxs-lookup"><span data-stu-id="86777-125">Overridable</span></span>](../../../visual-basic/language-reference/modifiers/overridable.md)  
 [<span data-ttu-id="86777-126">Overrides</span><span class="sxs-lookup"><span data-stu-id="86777-126">Overrides</span></span>](../../../visual-basic/language-reference/modifiers/overrides.md)  
 [<span data-ttu-id="86777-127">关键字</span><span class="sxs-lookup"><span data-stu-id="86777-127">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)  
 [<span data-ttu-id="86777-128">在 Visual Basic 中隐藏</span><span class="sxs-lookup"><span data-stu-id="86777-128">Shadowing in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
