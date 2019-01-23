---
title: 通过值传递自变量和通过引用传递自变量之间的差异 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- ByRef keyword [Visual Basic], passing arguments by reference
- Visual Basic code, procedures
- procedures [Visual Basic], passing arguments
- ByVal keyword [Visual Basic], passing arguments by value
- arguments [Visual Basic], passing by value or by reference
ms.assetid: 5f5c38fe-3e2d-494c-8fff-f4025b55ec93
ms.openlocfilehash: 129bb01184d051572ac757a2883aac4de8469d2c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54513303"
---
# <a name="differences-between-passing-an-argument-by-value-and-by-reference-visual-basic"></a><span data-ttu-id="b4932-102">通过值传递自变量和通过引用传递自变量之间的差异 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b4932-102">Differences Between Passing an Argument By Value and By Reference (Visual Basic)</span></span>
<span data-ttu-id="b4932-103">当将一个或多个自变量传递给过程中时，每个自变量对应于调用代码中的基础编程元素。</span><span class="sxs-lookup"><span data-stu-id="b4932-103">When you pass one or more arguments to a procedure, each argument corresponds to an underlying programming element in the calling code.</span></span> <span data-ttu-id="b4932-104">可以传递此基础元素的值，或者对它的引用。</span><span class="sxs-lookup"><span data-stu-id="b4932-104">You can pass either the value of this underlying element, or a reference to it.</span></span> <span data-ttu-id="b4932-105">这称为*传递机制*。</span><span class="sxs-lookup"><span data-stu-id="b4932-105">This is known as the *passing mechanism*.</span></span>  
  
## <a name="passing-by-value"></a><span data-ttu-id="b4932-106">按值传递</span><span class="sxs-lookup"><span data-stu-id="b4932-106">Passing by Value</span></span>  
 <span data-ttu-id="b4932-107">传递参数*按值*通过指定[ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)过程定义中的相应参数的关键字。</span><span class="sxs-lookup"><span data-stu-id="b4932-107">You pass an argument *by value* by specifying the [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) keyword for the corresponding parameter in the procedure definition.</span></span> <span data-ttu-id="b4932-108">当使用此传递机制时，Visual Basic 将基础编程元素的值复制到该过程中的本地变量。</span><span class="sxs-lookup"><span data-stu-id="b4932-108">When you use this passing mechanism, Visual Basic copies the value of the underlying programming element into a local variable in the procedure.</span></span> <span data-ttu-id="b4932-109">过程代码中调用代码没有任何对基础元素的访问。</span><span class="sxs-lookup"><span data-stu-id="b4932-109">The procedure code does not have any access to the underlying element in the calling code.</span></span>  
  
## <a name="passing-by-reference"></a><span data-ttu-id="b4932-110">按引用传递</span><span class="sxs-lookup"><span data-stu-id="b4932-110">Passing by Reference</span></span>  
 <span data-ttu-id="b4932-111">传递参数*通过引用*通过指定[ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)过程定义中的相应参数的关键字。</span><span class="sxs-lookup"><span data-stu-id="b4932-111">You pass an argument *by reference* by specifying the [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) keyword for the corresponding parameter in the procedure definition.</span></span> <span data-ttu-id="b4932-112">当使用此传递机制时，Visual Basic 使过程对基础编程元素的直接引用中调用代码。</span><span class="sxs-lookup"><span data-stu-id="b4932-112">When you use this passing mechanism, Visual Basic gives the procedure a direct reference to the underlying programming element in the calling code.</span></span>  
  
## <a name="passing-mechanism-and-element-type"></a><span data-ttu-id="b4932-113">传递机制和元素类型</span><span class="sxs-lookup"><span data-stu-id="b4932-113">Passing Mechanism and Element Type</span></span>  
 <span data-ttu-id="b4932-114">选择的传递机制不是相同的基础元素类型的分类。</span><span class="sxs-lookup"><span data-stu-id="b4932-114">The choice of passing mechanism is not the same as the classification of the underlying element type.</span></span> <span data-ttu-id="b4932-115">按值或按引用传递引用 Visual Basic 提供的过程代码。</span><span class="sxs-lookup"><span data-stu-id="b4932-115">Passing by value or by reference refers to what Visual Basic supplies to the procedure code.</span></span> <span data-ttu-id="b4932-116">值类型或引用类型引用的编程元素在内存中的存储方式。</span><span class="sxs-lookup"><span data-stu-id="b4932-116">A value type or reference type refers to how a programming element is stored in memory.</span></span>  
  
 <span data-ttu-id="b4932-117">但是，传递机制和元素类型是相互关联。</span><span class="sxs-lookup"><span data-stu-id="b4932-117">However, the passing mechanism and element type are interrelated.</span></span> <span data-ttu-id="b4932-118">引用类型的值是指向内存中其他位置的数据。</span><span class="sxs-lookup"><span data-stu-id="b4932-118">The value of a reference type is a pointer to the data elsewhere in memory.</span></span> <span data-ttu-id="b4932-119">这意味着当通过值传递引用类型，过程代码具有指向基础元素的数据，即使它不能访问基础元素本身也是如此。</span><span class="sxs-lookup"><span data-stu-id="b4932-119">This means that when you pass a reference type by value, the procedure code has a pointer to the underlying element's data, even though it cannot access the underlying element itself.</span></span> <span data-ttu-id="b4932-120">例如，如果该元素为数组变量，过程代码不具有访问该变量本身，但它可以访问的数组成员。</span><span class="sxs-lookup"><span data-stu-id="b4932-120">For example, if the element is an array variable, the procedure code does not have access to the variable itself, but it can access the array members.</span></span>  
  
## <a name="ability-to-modify"></a><span data-ttu-id="b4932-121">若要修改的功能</span><span class="sxs-lookup"><span data-stu-id="b4932-121">Ability to Modify</span></span>  
 <span data-ttu-id="b4932-122">时作为参数传递不可修改的元素，该过程可以永远不能修改它调用代码中是否超过`ByVal`或`ByRef`。</span><span class="sxs-lookup"><span data-stu-id="b4932-122">When you pass a nonmodifiable element as an argument, the procedure can never modify it in the calling code, whether it is passed `ByVal` or `ByRef`.</span></span>  
  
 <span data-ttu-id="b4932-123">对于可修改的元素下, 表总结了元素类型和传递机制之间的交互。</span><span class="sxs-lookup"><span data-stu-id="b4932-123">For a modifiable element, the following table summarizes the interaction between the element type and the passing mechanism.</span></span>  
  
|<span data-ttu-id="b4932-124">元素类型</span><span class="sxs-lookup"><span data-stu-id="b4932-124">Element type</span></span>|<span data-ttu-id="b4932-125">传递 `ByVal`</span><span class="sxs-lookup"><span data-stu-id="b4932-125">Passed `ByVal`</span></span>|<span data-ttu-id="b4932-126">传递 `ByRef`</span><span class="sxs-lookup"><span data-stu-id="b4932-126">Passed `ByRef`</span></span>|  
|------------------|--------------------|--------------------|  
|<span data-ttu-id="b4932-127">值类型 （只包含一个值）</span><span class="sxs-lookup"><span data-stu-id="b4932-127">Value type (contains only a value)</span></span>|<span data-ttu-id="b4932-128">该过程不能更改该变量或其任何成员。</span><span class="sxs-lookup"><span data-stu-id="b4932-128">The procedure cannot change the variable or any of its members.</span></span>|<span data-ttu-id="b4932-129">该过程可以更改变量和其成员。</span><span class="sxs-lookup"><span data-stu-id="b4932-129">The procedure can change the variable and its members.</span></span>|  
|<span data-ttu-id="b4932-130">引用类型 （包含的类或结构实例的指针）</span><span class="sxs-lookup"><span data-stu-id="b4932-130">Reference type (contains a pointer to a class or structure instance)</span></span>|<span data-ttu-id="b4932-131">该过程不能更改该变量，但可以更改它所指向的实例的成员。</span><span class="sxs-lookup"><span data-stu-id="b4932-131">The procedure cannot change the variable but can change members of the instance to which it points.</span></span>|<span data-ttu-id="b4932-132">该过程可以更改变量和它所指向的实例的成员。</span><span class="sxs-lookup"><span data-stu-id="b4932-132">The procedure can change the variable and members of the instance to which it points.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b4932-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="b4932-133">See also</span></span>
- [<span data-ttu-id="b4932-134">过程</span><span class="sxs-lookup"><span data-stu-id="b4932-134">Procedures</span></span>](./index.md)
- [<span data-ttu-id="b4932-135">过程参数和自变量</span><span class="sxs-lookup"><span data-stu-id="b4932-135">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="b4932-136">如何：将参数传递给过程</span><span class="sxs-lookup"><span data-stu-id="b4932-136">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)
- [<span data-ttu-id="b4932-137">按值和按引用传递自变量</span><span class="sxs-lookup"><span data-stu-id="b4932-137">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)
- [<span data-ttu-id="b4932-138">可修改和不可修改自变量之间的差异</span><span class="sxs-lookup"><span data-stu-id="b4932-138">Differences Between Modifiable and Nonmodifiable Arguments</span></span>](./differences-between-modifiable-and-nonmodifiable-arguments.md)
- [<span data-ttu-id="b4932-139">如何：更改过程自变量的值</span><span class="sxs-lookup"><span data-stu-id="b4932-139">How to: Change the Value of a Procedure Argument</span></span>](./how-to-change-the-value-of-a-procedure-argument.md)
- [<span data-ttu-id="b4932-140">如何：防止过程自变量的值更改</span><span class="sxs-lookup"><span data-stu-id="b4932-140">How to: Protect a Procedure Argument Against Value Changes</span></span>](./how-to-protect-a-procedure-argument-against-value-changes.md)
- [<span data-ttu-id="b4932-141">如何：强制通过值传递自变量</span><span class="sxs-lookup"><span data-stu-id="b4932-141">How to: Force an Argument to Be Passed by Value</span></span>](./how-to-force-an-argument-to-be-passed-by-value.md)
- [<span data-ttu-id="b4932-142">按位置和按名称传递自变量</span><span class="sxs-lookup"><span data-stu-id="b4932-142">Passing Arguments by Position and by Name</span></span>](./passing-arguments-by-position-and-by-name.md)
- [<span data-ttu-id="b4932-143">值类型和引用类型</span><span class="sxs-lookup"><span data-stu-id="b4932-143">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
