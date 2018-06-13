---
title: MustOverride (Visual Basic)
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
ms.openlocfilehash: 5dabd90d29bc41d017436876af24a67fa87e8e17
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33599865"
---
# <a name="mustoverride-visual-basic"></a><span data-ttu-id="9e81a-102">MustOverride (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9e81a-102">MustOverride (Visual Basic)</span></span>
<span data-ttu-id="9e81a-103">指定属性或过程中此类未实现，并且必须重写派生类中才可以使用。</span><span class="sxs-lookup"><span data-stu-id="9e81a-103">Specifies that a property or procedure is not implemented in this class and must be overridden in a derived class before it can be used.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9e81a-104">备注</span><span class="sxs-lookup"><span data-stu-id="9e81a-104">Remarks</span></span>  
 <span data-ttu-id="9e81a-105">只能在属性或过程声明语句中使用 `MustOverride`。</span><span class="sxs-lookup"><span data-stu-id="9e81a-105">You can use `MustOverride` only in a property or procedure declaration statement.</span></span> <span data-ttu-id="9e81a-106">属性或过程的指定`MustOverride`必须是类的成员并且类必须加以标记[MustInherit](../../../visual-basic/language-reference/modifiers/mustinherit.md)。</span><span class="sxs-lookup"><span data-stu-id="9e81a-106">The property or procedure that specifies `MustOverride` must be a member of a class, and the class must be marked [MustInherit](../../../visual-basic/language-reference/modifiers/mustinherit.md).</span></span>  
  
## <a name="rules"></a><span data-ttu-id="9e81a-107">规则</span><span class="sxs-lookup"><span data-stu-id="9e81a-107">Rules</span></span>  
  
-   <span data-ttu-id="9e81a-108">**不完整的声明。**</span><span class="sxs-lookup"><span data-stu-id="9e81a-108">**Incomplete Declaration.**</span></span> <span data-ttu-id="9e81a-109">当指定`MustOverride`，不会不提供任何其他代码行的属性或过程，即使`End Function`， `End Property`，或`End Sub`语句。</span><span class="sxs-lookup"><span data-stu-id="9e81a-109">When you specify `MustOverride`, you do not supply any additional lines of code for the property or procedure, not even the `End Function`, `End Property`, or `End Sub` statement.</span></span>  
  
-   <span data-ttu-id="9e81a-110">**组合的修饰符。**</span><span class="sxs-lookup"><span data-stu-id="9e81a-110">**Combined Modifiers.**</span></span> <span data-ttu-id="9e81a-111">不能指定`MustOverride`连同`NotOverridable`， `Overridable`，或`Shared`同一声明中。</span><span class="sxs-lookup"><span data-stu-id="9e81a-111">You cannot specify `MustOverride` together with `NotOverridable`, `Overridable`, or `Shared` in the same declaration.</span></span>  
  
-   <span data-ttu-id="9e81a-112">**隐藏和重写。**</span><span class="sxs-lookup"><span data-stu-id="9e81a-112">**Shadowing and Overriding.**</span></span> <span data-ttu-id="9e81a-113">隐藏和重写操作都可重新定义继承的元素，但这两种方法之间又具有很大的差异。</span><span class="sxs-lookup"><span data-stu-id="9e81a-113">Both shadowing and overriding redefine an inherited element, but there are significant differences between the two approaches.</span></span> <span data-ttu-id="9e81a-114">有关详细信息，请参阅[Visual Basic 中的隐藏](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)。</span><span class="sxs-lookup"><span data-stu-id="9e81a-114">For more information, see [Shadowing in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).</span></span>  
  
-   <span data-ttu-id="9e81a-115">**替换术语。**</span><span class="sxs-lookup"><span data-stu-id="9e81a-115">**Alternate Terms.**</span></span> <span data-ttu-id="9e81a-116">除不能用作重写中的元素有时称为*纯虚拟*元素。</span><span class="sxs-lookup"><span data-stu-id="9e81a-116">An element that cannot be used except in an override is sometimes called a *pure virtual* element.</span></span>  
  
 <span data-ttu-id="9e81a-117">`MustOverride` 修饰符可用于下面的上下文中：</span><span class="sxs-lookup"><span data-stu-id="9e81a-117">The `MustOverride` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="9e81a-118">Function 语句</span><span class="sxs-lookup"><span data-stu-id="9e81a-118">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="9e81a-119">Property 语句</span><span class="sxs-lookup"><span data-stu-id="9e81a-119">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="9e81a-120">Sub 语句</span><span class="sxs-lookup"><span data-stu-id="9e81a-120">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="9e81a-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="9e81a-121">See Also</span></span>  
 [<span data-ttu-id="9e81a-122">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="9e81a-122">NotOverridable</span></span>](../../../visual-basic/language-reference/modifiers/notoverridable.md)  
 [<span data-ttu-id="9e81a-123">Overridable</span><span class="sxs-lookup"><span data-stu-id="9e81a-123">Overridable</span></span>](../../../visual-basic/language-reference/modifiers/overridable.md)  
 [<span data-ttu-id="9e81a-124">Overrides</span><span class="sxs-lookup"><span data-stu-id="9e81a-124">Overrides</span></span>](../../../visual-basic/language-reference/modifiers/overrides.md)  
 [<span data-ttu-id="9e81a-125">MustInherit</span><span class="sxs-lookup"><span data-stu-id="9e81a-125">MustInherit</span></span>](../../../visual-basic/language-reference/modifiers/mustinherit.md)  
 [<span data-ttu-id="9e81a-126">关键字</span><span class="sxs-lookup"><span data-stu-id="9e81a-126">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)  
 [<span data-ttu-id="9e81a-127">在 Visual Basic 中隐藏</span><span class="sxs-lookup"><span data-stu-id="9e81a-127">Shadowing in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
