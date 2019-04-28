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
ms.openlocfilehash: 05de1d9f8966c17d84deba34f27819cce4aff3fe
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61637753"
---
# <a name="implements-clause-visual-basic"></a><span data-ttu-id="63e0e-102">Implements 子句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="63e0e-102">Implements Clause (Visual Basic)</span></span>
<span data-ttu-id="63e0e-103">指示类或结构成员提供在接口中定义的成员的实现。</span><span class="sxs-lookup"><span data-stu-id="63e0e-103">Indicates that a class or structure member is providing the implementation for a member defined in an interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="63e0e-104">备注</span><span class="sxs-lookup"><span data-stu-id="63e0e-104">Remarks</span></span>  
<span data-ttu-id="63e0e-105">`Implements`关键字不是与相同[Implements 语句](../../../visual-basic/language-reference/statements/implements-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="63e0e-105">The `Implements` keyword is not the same as the [Implements Statement](../../../visual-basic/language-reference/statements/implements-statement.md).</span></span> <span data-ttu-id="63e0e-106">您使用`Implements`语句指定的类或结构实现一个或多个接口，然后为每个成员使用`Implements`关键字来指定哪个接口和哪个成员实现。</span><span class="sxs-lookup"><span data-stu-id="63e0e-106">You use the `Implements` statement to specify that a class or structure implements one or more interfaces, and then for each member you use the `Implements` keyword to specify which interface and which member it implements.</span></span>

<span data-ttu-id="63e0e-107">如果类或结构实现一个接口，它必须包括`Implements`语句之后立即[Class 语句](../../../visual-basic/language-reference/statements/class-statement.md)或[Structure 语句](../../../visual-basic/language-reference/statements/structure-statement.md)，并且它必须实现的所有成员定义由接口。</span><span class="sxs-lookup"><span data-stu-id="63e0e-107">If a class or structure implements an interface, it must include the `Implements` statement immediately after the [Class Statement](../../../visual-basic/language-reference/statements/class-statement.md) or [Structure Statement](../../../visual-basic/language-reference/statements/structure-statement.md), and it must implement all the members defined by the interface.</span></span>

## <a name="reimplementation"></a><span data-ttu-id="63e0e-108">重新实现</span><span class="sxs-lookup"><span data-stu-id="63e0e-108">Reimplementation</span></span>  
<span data-ttu-id="63e0e-109">在派生类中，可以重新实现接口成员的已实现的基类。</span><span class="sxs-lookup"><span data-stu-id="63e0e-109">In a derived class, you can reimplement an interface member that the base class has already implemented.</span></span> <span data-ttu-id="63e0e-110">这是不同于重写基类成员在以下方面：</span><span class="sxs-lookup"><span data-stu-id="63e0e-110">This is different from overriding the base class member in the following respects:</span></span>

- <span data-ttu-id="63e0e-111">基类成员不需要进行[Overridable](../../../visual-basic/language-reference/modifiers/overridable.md)来重新实现。</span><span class="sxs-lookup"><span data-stu-id="63e0e-111">The base class member does not need to be [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md) to be reimplemented.</span></span>
- <span data-ttu-id="63e0e-112">您可以重新实现具有不同名称的成员。</span><span class="sxs-lookup"><span data-stu-id="63e0e-112">You can reimplement the member with a different name.</span></span>

<span data-ttu-id="63e0e-113">`Implements`关键字可以在以下上下文中使用：</span><span class="sxs-lookup"><span data-stu-id="63e0e-113">The `Implements` keyword can be used in the following contexts:</span></span>
- [<span data-ttu-id="63e0e-114">Event 语句</span><span class="sxs-lookup"><span data-stu-id="63e0e-114">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)
- [<span data-ttu-id="63e0e-115">Function 语句</span><span class="sxs-lookup"><span data-stu-id="63e0e-115">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="63e0e-116">Property 语句</span><span class="sxs-lookup"><span data-stu-id="63e0e-116">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)
- [<span data-ttu-id="63e0e-117">Sub 语句</span><span class="sxs-lookup"><span data-stu-id="63e0e-117">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="63e0e-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="63e0e-118">See also</span></span>

- [<span data-ttu-id="63e0e-119">Implements 语句</span><span class="sxs-lookup"><span data-stu-id="63e0e-119">Implements Statement</span></span>](../../../visual-basic/language-reference/statements/implements-statement.md)
- [<span data-ttu-id="63e0e-120">Interface 语句</span><span class="sxs-lookup"><span data-stu-id="63e0e-120">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)
- [<span data-ttu-id="63e0e-121">Class 语句</span><span class="sxs-lookup"><span data-stu-id="63e0e-121">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)
- [<span data-ttu-id="63e0e-122">Structure 语句</span><span class="sxs-lookup"><span data-stu-id="63e0e-122">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)
