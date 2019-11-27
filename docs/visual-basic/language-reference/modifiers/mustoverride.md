---
title: New
ms.date: 07/20/2015
f1_keywords:
- vb.MustOverride
- MustOverride
helpviewer_keywords:
- virtual elements [Visual Basic], pure
- elements [Visual Basic], pure virtual
- properties [Visual Basic], redefining
- procedures [Visual Basic], overriding
- overriding, MustOverride keyword
- procedures [Visual Basic], redefining
- pure virtual elements [Visual Basic]
- MustOverride keyword [Visual Basic]
- properties [Visual Basic], overriding
ms.assetid: 6e9d9ad6-bb64-433f-b32b-3ef84293bf96
ms.openlocfilehash: dc6a153a604fd0e5cee9d7d46ebcd63294f33628
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351484"
---
# <a name="mustoverride-visual-basic"></a><span data-ttu-id="60685-102">MustOverride (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="60685-102">MustOverride (Visual Basic)</span></span>
<span data-ttu-id="60685-103">指定在此类中未实现的属性或过程，并且在使用之前必须在派生类中重写该属性或过程。</span><span class="sxs-lookup"><span data-stu-id="60685-103">Specifies that a property or procedure is not implemented in this class and must be overridden in a derived class before it can be used.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="60685-104">备注</span><span class="sxs-lookup"><span data-stu-id="60685-104">Remarks</span></span>  
 <span data-ttu-id="60685-105">只能在属性或过程声明语句中使用 `MustOverride`。</span><span class="sxs-lookup"><span data-stu-id="60685-105">You can use `MustOverride` only in a property or procedure declaration statement.</span></span> <span data-ttu-id="60685-106">指定 `MustOverride` 的属性或过程必须是类的成员，并且该类必须标记为[MustInherit](../../../visual-basic/language-reference/modifiers/mustinherit.md)。</span><span class="sxs-lookup"><span data-stu-id="60685-106">The property or procedure that specifies `MustOverride` must be a member of a class, and the class must be marked [MustInherit](../../../visual-basic/language-reference/modifiers/mustinherit.md).</span></span>  
  
## <a name="rules"></a><span data-ttu-id="60685-107">规则</span><span class="sxs-lookup"><span data-stu-id="60685-107">Rules</span></span>  
  
- <span data-ttu-id="60685-108">**不完整声明。**</span><span class="sxs-lookup"><span data-stu-id="60685-108">**Incomplete Declaration.**</span></span> <span data-ttu-id="60685-109">当指定 `MustOverride`时，您不会为该属性或过程（甚至 `End Function`、`End Property`或 `End Sub` 语句）提供任何其他代码行。</span><span class="sxs-lookup"><span data-stu-id="60685-109">When you specify `MustOverride`, you do not supply any additional lines of code for the property or procedure, not even the `End Function`, `End Property`, or `End Sub` statement.</span></span>  
  
- <span data-ttu-id="60685-110">**组合修饰符。**</span><span class="sxs-lookup"><span data-stu-id="60685-110">**Combined Modifiers.**</span></span> <span data-ttu-id="60685-111">不能在同一声明中同时指定 `MustOverride` 与 `NotOverridable`、`Overridable`或 `Shared`。</span><span class="sxs-lookup"><span data-stu-id="60685-111">You cannot specify `MustOverride` together with `NotOverridable`, `Overridable`, or `Shared` in the same declaration.</span></span>  
  
- <span data-ttu-id="60685-112">**隐藏和重写。**</span><span class="sxs-lookup"><span data-stu-id="60685-112">**Shadowing and Overriding.**</span></span> <span data-ttu-id="60685-113">隐藏和重写操作都可重新定义继承的元素，但这两种方法之间又具有很大的差异。</span><span class="sxs-lookup"><span data-stu-id="60685-113">Both shadowing and overriding redefine an inherited element, but there are significant differences between the two approaches.</span></span> <span data-ttu-id="60685-114">有关详细信息，请参阅[Visual Basic 中的隐藏](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)。</span><span class="sxs-lookup"><span data-stu-id="60685-114">For more information, see [Shadowing in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).</span></span>  
  
- <span data-ttu-id="60685-115">**替代条款。**</span><span class="sxs-lookup"><span data-stu-id="60685-115">**Alternate Terms.**</span></span> <span data-ttu-id="60685-116">除了在重写中外，不能使用的元素有时称为*纯虚拟*元素。</span><span class="sxs-lookup"><span data-stu-id="60685-116">An element that cannot be used except in an override is sometimes called a *pure virtual* element.</span></span>  
  
 <span data-ttu-id="60685-117">`MustOverride` 修饰符可用于下面的上下文中：</span><span class="sxs-lookup"><span data-stu-id="60685-117">The `MustOverride` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="60685-118">Function 语句</span><span class="sxs-lookup"><span data-stu-id="60685-118">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="60685-119">Property 语句</span><span class="sxs-lookup"><span data-stu-id="60685-119">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="60685-120">Sub 语句</span><span class="sxs-lookup"><span data-stu-id="60685-120">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="60685-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="60685-121">See also</span></span>

- [<span data-ttu-id="60685-122">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="60685-122">NotOverridable</span></span>](../../../visual-basic/language-reference/modifiers/notoverridable.md)
- [<span data-ttu-id="60685-123">Overrides</span><span class="sxs-lookup"><span data-stu-id="60685-123">Overridable</span></span>](../../../visual-basic/language-reference/modifiers/overridable.md)
- [<span data-ttu-id="60685-124">Overrides</span><span class="sxs-lookup"><span data-stu-id="60685-124">Overrides</span></span>](../../../visual-basic/language-reference/modifiers/overrides.md)
- [<span data-ttu-id="60685-125">MustInherit</span><span class="sxs-lookup"><span data-stu-id="60685-125">MustInherit</span></span>](../../../visual-basic/language-reference/modifiers/mustinherit.md)
- [<span data-ttu-id="60685-126">关键字</span><span class="sxs-lookup"><span data-stu-id="60685-126">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
- [<span data-ttu-id="60685-127">Visual Basic 中的阴影</span><span class="sxs-lookup"><span data-stu-id="60685-127">Shadowing in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
