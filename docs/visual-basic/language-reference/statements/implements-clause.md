---
title: Implements 子句 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.ImplementsClause
helpviewer_keywords:
- interface implementation [Visual Basic], reimplementation
- interface members [Visual Basic], reimplementation
- interface members [Visual Basic], Implements keyword
- interface members
- members [Visual Basic], reimplementation
- interface implementation [Visual Basic], Implements keyword
- interface members [Visual Basic], implementing
- Implements keyword [Visual Basic]
- Implements statement [Visual Basic], about Implements
- members [Visual Basic], implementing
- members [Visual Basic], Implements keyword
- reimplementation
ms.assetid: 5252cdf9-964d-4fc6-af0f-0449b7126b5a
ms.openlocfilehash: 1e34245ac528e9e2463afbfd07dff91bf693830b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33603400"
---
# <a name="implements-clause-visual-basic"></a><span data-ttu-id="4168d-102">Implements 子句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4168d-102">Implements Clause (Visual Basic)</span></span>
<span data-ttu-id="4168d-103">指示类或结构成员提供在接口中定义的成员的实现。</span><span class="sxs-lookup"><span data-stu-id="4168d-103">Indicates that a class or structure member is providing the implementation for a member defined in an interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4168d-104">备注</span><span class="sxs-lookup"><span data-stu-id="4168d-104">Remarks</span></span>  
<span data-ttu-id="4168d-105">`Implements`关键字不与相同[Implements 语句](../../../visual-basic/language-reference/statements/implements-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="4168d-105">The `Implements` keyword is not the same as the [Implements Statement](../../../visual-basic/language-reference/statements/implements-statement.md).</span></span> <span data-ttu-id="4168d-106">你使用`Implements`语句指定的类或结构实现一个或多个接口，证书，然后为每个成员你使用`Implements`关键字来指定哪个接口和哪个成员它实现。</span><span class="sxs-lookup"><span data-stu-id="4168d-106">You use the `Implements` statement to specify that a class or structure implements one or more interfaces, and then for each member you use the `Implements` keyword to specify which interface and which member it implements.</span></span>

<span data-ttu-id="4168d-107">如果类或结构实现接口时，它必须包含`Implements`语句后立即[类语句](../../../visual-basic/language-reference/statements/class-statement.md)或[Structure 语句](../../../visual-basic/language-reference/statements/structure-statement.md)，并且它必须实现的所有成员定义由接口。</span><span class="sxs-lookup"><span data-stu-id="4168d-107">If a class or structure implements an interface, it must include the `Implements` statement immediately after the [Class Statement](../../../visual-basic/language-reference/statements/class-statement.md) or [Structure Statement](../../../visual-basic/language-reference/statements/structure-statement.md), and it must implement all the members defined by the interface.</span></span>

## <a name="reimplementation"></a><span data-ttu-id="4168d-108">重新实现</span><span class="sxs-lookup"><span data-stu-id="4168d-108">Reimplementation</span></span>  
<span data-ttu-id="4168d-109">在派生类中，你可以重新实现接口成员的基类实现。</span><span class="sxs-lookup"><span data-stu-id="4168d-109">In a derived class, you can reimplement an interface member that the base class has already implemented.</span></span> <span data-ttu-id="4168d-110">这是不同于重写基类成员在以下方面：</span><span class="sxs-lookup"><span data-stu-id="4168d-110">This is different from overriding the base class member in the following respects:</span></span>

- <span data-ttu-id="4168d-111">基类成员不需要为[可重写](../../../visual-basic/language-reference/modifiers/overridable.md)若要将根据。</span><span class="sxs-lookup"><span data-stu-id="4168d-111">The base class member does not need to be [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md) to be reimplemented.</span></span>
- <span data-ttu-id="4168d-112">你可以重新实现具有不同名称的成员。</span><span class="sxs-lookup"><span data-stu-id="4168d-112">You can reimplement the member with a different name.</span></span>

<span data-ttu-id="4168d-113">`Implements`关键字可以在以下上下文中使用：</span><span class="sxs-lookup"><span data-stu-id="4168d-113">The `Implements` keyword can be used in the following contexts:</span></span>
- [<span data-ttu-id="4168d-114">Event 语句</span><span class="sxs-lookup"><span data-stu-id="4168d-114">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)
- [<span data-ttu-id="4168d-115">Function 语句</span><span class="sxs-lookup"><span data-stu-id="4168d-115">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="4168d-116">Property 语句</span><span class="sxs-lookup"><span data-stu-id="4168d-116">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)
- [<span data-ttu-id="4168d-117">Sub 语句</span><span class="sxs-lookup"><span data-stu-id="4168d-117">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="4168d-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="4168d-118">See Also</span></span>  
 [<span data-ttu-id="4168d-119">Implements 语句</span><span class="sxs-lookup"><span data-stu-id="4168d-119">Implements Statement</span></span>](../../../visual-basic/language-reference/statements/implements-statement.md)  
 [<span data-ttu-id="4168d-120">Interface 语句</span><span class="sxs-lookup"><span data-stu-id="4168d-120">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
 [<span data-ttu-id="4168d-121">Class 语句</span><span class="sxs-lookup"><span data-stu-id="4168d-121">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
 [<span data-ttu-id="4168d-122">Structure 语句</span><span class="sxs-lookup"><span data-stu-id="4168d-122">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)
