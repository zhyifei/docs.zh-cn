---
title: 可修改和不可修改自变量之间的差异 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], arguments
- procedure arguments
- arguments [Visual Basic], nonmodifiable
- Visual Basic code, procedures
- arguments [Visual Basic], modifiable
ms.assetid: 87b2df69-e1f7-4657-9caf-b3f48d693428
ms.openlocfilehash: 06f3009d984f7a303a0ee6e8d529a3ff60900fbc
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54498672"
---
# <a name="differences-between-modifiable-and-nonmodifiable-arguments-visual-basic"></a><span data-ttu-id="0e1e9-102">可修改和不可修改自变量之间的差异 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0e1e9-102">Differences Between Modifiable and Nonmodifiable Arguments (Visual Basic)</span></span>
<span data-ttu-id="0e1e9-103">在调用过程时，通常向其传递一个或多个自变量。</span><span class="sxs-lookup"><span data-stu-id="0e1e9-103">When you call a procedure, you typically pass one or more arguments to it.</span></span> <span data-ttu-id="0e1e9-104">每个自变量对应于基础编程元素。</span><span class="sxs-lookup"><span data-stu-id="0e1e9-104">Each argument corresponds to an underlying programming element.</span></span> <span data-ttu-id="0e1e9-105">基础元素和参数本身可以是可修改或不可修改。</span><span class="sxs-lookup"><span data-stu-id="0e1e9-105">Both the underlying elements and the arguments themselves can be either modifiable or nonmodifiable.</span></span>  
  
## <a name="modifiable-and-nonmodifiable-elements"></a><span data-ttu-id="0e1e9-106">可修改和不可修改的元素</span><span class="sxs-lookup"><span data-stu-id="0e1e9-106">Modifiable and Nonmodifiable Elements</span></span>  
 <span data-ttu-id="0e1e9-107">编程元素可以是*可修改的元素*，它可以具有其值已更改，或*不可更改元素*，一旦已创建具有固定的值。</span><span class="sxs-lookup"><span data-stu-id="0e1e9-107">A programming element can be either a *modifiable element*, which can have its value changed, or a *nonmodifiable element*, which has a fixed value once it has been created.</span></span>  
  
 <span data-ttu-id="0e1e9-108">下表列出了可修改和不可修改的编程元素。</span><span class="sxs-lookup"><span data-stu-id="0e1e9-108">The following table lists modifiable and nonmodifiable programming elements.</span></span>  
  
|<span data-ttu-id="0e1e9-109">可修改的元素</span><span class="sxs-lookup"><span data-stu-id="0e1e9-109">Modifiable elements</span></span>|<span data-ttu-id="0e1e9-110">不可修改的元素</span><span class="sxs-lookup"><span data-stu-id="0e1e9-110">Nonmodifiable elements</span></span>|  
|-------------------------|----------------------------|  
|<span data-ttu-id="0e1e9-111">本地变量 （在过程声明），包括对象变量，包括只读</span><span class="sxs-lookup"><span data-stu-id="0e1e9-111">Local variables (declared inside procedures), including object variables, except for read-only</span></span>|<span data-ttu-id="0e1e9-112">只读变量、 字段和属性</span><span class="sxs-lookup"><span data-stu-id="0e1e9-112">Read-only variables, fields, and properties</span></span>|  
|<span data-ttu-id="0e1e9-113">包括只读字段 （的模块、 类和结构的成员变量）</span><span class="sxs-lookup"><span data-stu-id="0e1e9-113">Fields (member variables of modules, classes, and structures), except for read-only</span></span>|<span data-ttu-id="0e1e9-114">常量和文本</span><span class="sxs-lookup"><span data-stu-id="0e1e9-114">Constants and literals</span></span>|  
|<span data-ttu-id="0e1e9-115">属性，包括只读</span><span class="sxs-lookup"><span data-stu-id="0e1e9-115">Properties, except for read-only</span></span>|<span data-ttu-id="0e1e9-116">枚举成员</span><span class="sxs-lookup"><span data-stu-id="0e1e9-116">Enumeration members</span></span>|  
|<span data-ttu-id="0e1e9-117">数组元素</span><span class="sxs-lookup"><span data-stu-id="0e1e9-117">Array elements</span></span>|<span data-ttu-id="0e1e9-118">表达式 （即使其元素是可修改）</span><span class="sxs-lookup"><span data-stu-id="0e1e9-118">Expressions (even if their elements are modifiable)</span></span>|  
  
## <a name="modifiable-and-nonmodifiable-arguments"></a><span data-ttu-id="0e1e9-119">可修改和不可修改自变量</span><span class="sxs-lookup"><span data-stu-id="0e1e9-119">Modifiable and Nonmodifiable Arguments</span></span>  
 <span data-ttu-id="0e1e9-120">一个*可修改参数*是另一个使用可修改的基础元素。</span><span class="sxs-lookup"><span data-stu-id="0e1e9-120">A *modifiable argument* is one with a modifiable underlying element.</span></span> <span data-ttu-id="0e1e9-121">调用代码可以将新值存储在任何时候，如果传递参数[ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)，过程中的代码还可以修改调用代码中的基础元素。</span><span class="sxs-lookup"><span data-stu-id="0e1e9-121">The calling code can store a new value at any time, and if you pass the argument [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), the code in the procedure can also modify the underlying element in the calling code.</span></span>  
  
 <span data-ttu-id="0e1e9-122">一个*不可修改自变量*具有不可修改的基础元素或传递[ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)。</span><span class="sxs-lookup"><span data-stu-id="0e1e9-122">A *nonmodifiable argument* either has a nonmodifiable underlying element or is passed [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md).</span></span> <span data-ttu-id="0e1e9-123">该过程不能修改调用代码中的基础元素，即使它是可修改的元素。</span><span class="sxs-lookup"><span data-stu-id="0e1e9-123">The procedure cannot modify the underlying element in the calling code, even if it is a modifiable element.</span></span> <span data-ttu-id="0e1e9-124">如果它是不可修改的元素，调用代码本身不能修改它。</span><span class="sxs-lookup"><span data-stu-id="0e1e9-124">If it is a nonmodifiable element, the calling code itself cannot modify it.</span></span>  
  
 <span data-ttu-id="0e1e9-125">被调用的过程可能会修改其不可修改的参数的本地副本，但修改不会影响调用代码中的基础元素。</span><span class="sxs-lookup"><span data-stu-id="0e1e9-125">The called procedure might modify its local copy of a nonmodifiable argument, but that modification does not affect the underlying element in the calling code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e1e9-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="0e1e9-126">See also</span></span>
- [<span data-ttu-id="0e1e9-127">过程</span><span class="sxs-lookup"><span data-stu-id="0e1e9-127">Procedures</span></span>](./index.md)
- [<span data-ttu-id="0e1e9-128">过程参数和自变量</span><span class="sxs-lookup"><span data-stu-id="0e1e9-128">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="0e1e9-129">如何：将参数传递给过程</span><span class="sxs-lookup"><span data-stu-id="0e1e9-129">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)
- [<span data-ttu-id="0e1e9-130">按值和按引用传递自变量</span><span class="sxs-lookup"><span data-stu-id="0e1e9-130">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)
- [<span data-ttu-id="0e1e9-131">通过值传递自变量和通过引用传递自变量之间的差异</span><span class="sxs-lookup"><span data-stu-id="0e1e9-131">Differences Between Passing an Argument By Value and By Reference</span></span>](./differences-between-passing-an-argument-by-value-and-by-reference.md)
- [<span data-ttu-id="0e1e9-132">如何：更改过程自变量的值</span><span class="sxs-lookup"><span data-stu-id="0e1e9-132">How to: Change the Value of a Procedure Argument</span></span>](./how-to-change-the-value-of-a-procedure-argument.md)
- [<span data-ttu-id="0e1e9-133">如何：防止过程自变量的值更改</span><span class="sxs-lookup"><span data-stu-id="0e1e9-133">How to: Protect a Procedure Argument Against Value Changes</span></span>](./how-to-protect-a-procedure-argument-against-value-changes.md)
- [<span data-ttu-id="0e1e9-134">如何：强制通过值传递自变量</span><span class="sxs-lookup"><span data-stu-id="0e1e9-134">How to: Force an Argument to Be Passed by Value</span></span>](./how-to-force-an-argument-to-be-passed-by-value.md)
- [<span data-ttu-id="0e1e9-135">按位置和按名称传递自变量</span><span class="sxs-lookup"><span data-stu-id="0e1e9-135">Passing Arguments by Position and by Name</span></span>](./passing-arguments-by-position-and-by-name.md)
- [<span data-ttu-id="0e1e9-136">值类型和引用类型</span><span class="sxs-lookup"><span data-stu-id="0e1e9-136">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
