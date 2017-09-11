---
title: "通过值和通过引用 (Visual Basic 中) 传递参数之间的差异 |Microsoft 文档"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- ByRef keyword, passing arguments by reference
- Visual Basic code, procedures
- procedures, passing arguments
- ByVal keyword, passing arguments by value
- arguments [Visual Basic], passing by value or by reference
ms.assetid: 5f5c38fe-3e2d-494c-8fff-f4025b55ec93
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 706c64cd316791a748e2b68fe406e34084b04d5a
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="differences-between-passing-an-argument-by-value-and-by-reference-visual-basic"></a><span data-ttu-id="08976-102">通过值传递自变量和通过引用传递自变量之间的差异 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="08976-102">Differences Between Passing an Argument By Value and By Reference (Visual Basic)</span></span>
<span data-ttu-id="08976-103">当将一个或多个参数传递给过程中时，每个参数对应一个基础编程元素调用的代码中。</span><span class="sxs-lookup"><span data-stu-id="08976-103">When you pass one or more arguments to a procedure, each argument corresponds to an underlying programming element in the calling code.</span></span> <span data-ttu-id="08976-104">您可以传递此基础元素的值，或者对它的引用。</span><span class="sxs-lookup"><span data-stu-id="08976-104">You can pass either the value of this underlying element, or a reference to it.</span></span> <span data-ttu-id="08976-105">这称为*传递机制*。</span><span class="sxs-lookup"><span data-stu-id="08976-105">This is known as the *passing mechanism*.</span></span>  
  
## <a name="passing-by-value"></a><span data-ttu-id="08976-106">按值传递</span><span class="sxs-lookup"><span data-stu-id="08976-106">Passing by Value</span></span>  
 <span data-ttu-id="08976-107">传递了参数*按值*通过指定[ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)在过程定义中的相应参数的关键字。</span><span class="sxs-lookup"><span data-stu-id="08976-107">You pass an argument *by value* by specifying the [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) keyword for the corresponding parameter in the procedure definition.</span></span> <span data-ttu-id="08976-108">当您使用此传递机制，[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]将基础编程元素的值复制到该过程中的局部变量。</span><span class="sxs-lookup"><span data-stu-id="08976-108">When you use this passing mechanism, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] copies the value of the underlying programming element into a local variable in the procedure.</span></span> <span data-ttu-id="08976-109">过程代码中调用代码没有的任何访问权限的基础元素。</span><span class="sxs-lookup"><span data-stu-id="08976-109">The procedure code does not have any access to the underlying element in the calling code.</span></span>  
  
## <a name="passing-by-reference"></a><span data-ttu-id="08976-110">通过引用传递</span><span class="sxs-lookup"><span data-stu-id="08976-110">Passing by Reference</span></span>  
 <span data-ttu-id="08976-111">传递了参数*通过引用*通过指定[ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)在过程定义中的相应参数的关键字。</span><span class="sxs-lookup"><span data-stu-id="08976-111">You pass an argument *by reference* by specifying the [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) keyword for the corresponding parameter in the procedure definition.</span></span> <span data-ttu-id="08976-112">当您使用此传递机制，[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]使过程的基础的编程元素的直接引用中调用代码。</span><span class="sxs-lookup"><span data-stu-id="08976-112">When you use this passing mechanism, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] gives the procedure a direct reference to the underlying programming element in the calling code.</span></span>  
  
## <a name="passing-mechanism-and-element-type"></a><span data-ttu-id="08976-113">传递机制和元素类型</span><span class="sxs-lookup"><span data-stu-id="08976-113">Passing Mechanism and Element Type</span></span>  
 <span data-ttu-id="08976-114">选择传递机制不是相同的基本元素类型的分类。</span><span class="sxs-lookup"><span data-stu-id="08976-114">The choice of passing mechanism is not the same as the classification of the underlying element type.</span></span> <span data-ttu-id="08976-115">按值或按引用传递是指什么[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]提供给该过程代码。</span><span class="sxs-lookup"><span data-stu-id="08976-115">Passing by value or by reference refers to what [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] supplies to the procedure code.</span></span> <span data-ttu-id="08976-116">值类型或引用类型是指在内存中存储的编程元素的方式。</span><span class="sxs-lookup"><span data-stu-id="08976-116">A value type or reference type refers to how a programming element is stored in memory.</span></span>  
  
 <span data-ttu-id="08976-117">但是，传递机制和元素类型是相互关联。</span><span class="sxs-lookup"><span data-stu-id="08976-117">However, the passing mechanism and element type are interrelated.</span></span> <span data-ttu-id="08976-118">引用类型的值是一个指向内存中其他位置的数据。</span><span class="sxs-lookup"><span data-stu-id="08976-118">The value of a reference type is a pointer to the data elsewhere in memory.</span></span> <span data-ttu-id="08976-119">也就是说，当通过值传递引用类型时，过程代码中有一个指向基础元素的数据，即使它不能访问基础元素本身也是如此。</span><span class="sxs-lookup"><span data-stu-id="08976-119">This means that when you pass a reference type by value, the procedure code has a pointer to the underlying element's data, even though it cannot access the underlying element itself.</span></span> <span data-ttu-id="08976-120">例如，如果该元素是一个数组变量，过程代码不具有访问变量本身，但它可以访问数组成员。</span><span class="sxs-lookup"><span data-stu-id="08976-120">For example, if the element is an array variable, the procedure code does not have access to the variable itself, but it can access the array members.</span></span>  
  
## <a name="ability-to-modify"></a><span data-ttu-id="08976-121">若要修改的能力</span><span class="sxs-lookup"><span data-stu-id="08976-121">Ability to Modify</span></span>  
 <span data-ttu-id="08976-122">当作为参数传递不可更改元素时，过程可以永远不会修改它在调用代码中，不论它的传入`ByVal`或`ByRef`。</span><span class="sxs-lookup"><span data-stu-id="08976-122">When you pass a nonmodifiable element as an argument, the procedure can never modify it in the calling code, whether it is passed `ByVal` or `ByRef`.</span></span>  
  
 <span data-ttu-id="08976-123">对于可修改的元素下, 表总结了元素类型和传递机制之间的交互。</span><span class="sxs-lookup"><span data-stu-id="08976-123">For a modifiable element, the following table summarizes the interaction between the element type and the passing mechanism.</span></span>  
  
|<span data-ttu-id="08976-124">元素类型</span><span class="sxs-lookup"><span data-stu-id="08976-124">Element type</span></span>|<span data-ttu-id="08976-125">传递`ByVal`</span><span class="sxs-lookup"><span data-stu-id="08976-125">Passed `ByVal`</span></span>|<span data-ttu-id="08976-126">传递`ByRef`</span><span class="sxs-lookup"><span data-stu-id="08976-126">Passed `ByRef`</span></span>|  
|------------------|--------------------|--------------------|  
|<span data-ttu-id="08976-127">值类型 （包含只有一个值）</span><span class="sxs-lookup"><span data-stu-id="08976-127">Value type (contains only a value)</span></span>|<span data-ttu-id="08976-128">该过程不能更改该变量或任何成员。</span><span class="sxs-lookup"><span data-stu-id="08976-128">The procedure cannot change the variable or any of its members.</span></span>|<span data-ttu-id="08976-129">该过程可以更改变量和其成员。</span><span class="sxs-lookup"><span data-stu-id="08976-129">The procedure can change the variable and its members.</span></span>|  
|<span data-ttu-id="08976-130">引用类型 （包含指向类或结构的实例的指针）</span><span class="sxs-lookup"><span data-stu-id="08976-130">Reference type (contains a pointer to a class or structure instance)</span></span>|<span data-ttu-id="08976-131">该过程不能更改变量，但可以更改它所指向的实例的成员。</span><span class="sxs-lookup"><span data-stu-id="08976-131">The procedure cannot change the variable but can change members of the instance to which it points.</span></span>|<span data-ttu-id="08976-132">该过程可以更改变量和它所指向的实例的成员。</span><span class="sxs-lookup"><span data-stu-id="08976-132">The procedure can change the variable and members of the instance to which it points.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="08976-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="08976-133">See Also</span></span>  
 <span data-ttu-id="08976-134">[过程](./index.md) </span><span class="sxs-lookup"><span data-stu-id="08976-134">[Procedures](./index.md) </span></span>  
<span data-ttu-id="08976-135"> [过程参数和变量](./procedure-parameters-and-arguments.md) </span><span class="sxs-lookup"><span data-stu-id="08976-135"> [Procedure Parameters and Arguments](./procedure-parameters-and-arguments.md) </span></span>  
<span data-ttu-id="08976-136"> [如何︰ 将参数传递给过程](./how-to-pass-arguments-to-a-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="08976-136"> [How to: Pass Arguments to a Procedure](./how-to-pass-arguments-to-a-procedure.md) </span></span>  
<span data-ttu-id="08976-137"> [通过值和通过引用传递参数](./passing-arguments-by-value-and-by-reference.md) </span><span class="sxs-lookup"><span data-stu-id="08976-137"> [Passing Arguments by Value and by Reference](./passing-arguments-by-value-and-by-reference.md) </span></span>  
<span data-ttu-id="08976-138"> [可修改和不可修改参数之间的差异](./differences-between-modifiable-and-nonmodifiable-arguments.md) </span><span class="sxs-lookup"><span data-stu-id="08976-138"> [Differences Between Modifiable and Nonmodifiable Arguments](./differences-between-modifiable-and-nonmodifiable-arguments.md) </span></span>  
<span data-ttu-id="08976-139"> [如何︰ 更改过程参数的值](./how-to-change-the-value-of-a-procedure-argument.md) </span><span class="sxs-lookup"><span data-stu-id="08976-139"> [How to: Change the Value of a Procedure Argument](./how-to-change-the-value-of-a-procedure-argument.md) </span></span>  
<span data-ttu-id="08976-140"> [如何︰ 防止过程参数的值更改](./how-to-protect-a-procedure-argument-against-value-changes.md) </span><span class="sxs-lookup"><span data-stu-id="08976-140"> [How to: Protect a Procedure Argument Against Value Changes](./how-to-protect-a-procedure-argument-against-value-changes.md) </span></span>  
<span data-ttu-id="08976-141"> [如何︰ 强制通过值传递参数](./how-to-force-an-argument-to-be-passed-by-value.md) </span><span class="sxs-lookup"><span data-stu-id="08976-141"> [How to: Force an Argument to Be Passed by Value](./how-to-force-an-argument-to-be-passed-by-value.md) </span></span>  
<span data-ttu-id="08976-142"> [按位置和按名称传递参数](./passing-arguments-by-position-and-by-name.md) </span><span class="sxs-lookup"><span data-stu-id="08976-142"> [Passing Arguments by Position and by Name](./passing-arguments-by-position-and-by-name.md) </span></span>  
<span data-ttu-id="08976-143"> [值类型和引用类型](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)</span><span class="sxs-lookup"><span data-stu-id="08976-143"> [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)</span></span>
