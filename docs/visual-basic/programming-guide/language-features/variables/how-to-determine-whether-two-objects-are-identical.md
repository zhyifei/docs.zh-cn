---
title: "如何：确定两个对象是否相同 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- testing [Visual Basic], objects
- objects [Visual Basic], comparing
- object variables [Visual Basic], determining identity
ms.assetid: 7829f817-0d1f-4749-a707-de0b95e0cf5c
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 02083a93e63fe799f529776f777ca877d2d138b1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-determine-whether-two-objects-are-identical-visual-basic"></a><span data-ttu-id="9d3ab-102">如何：确定两个对象是否相同 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9d3ab-102">How to: Determine Whether Two Objects Are Identical (Visual Basic)</span></span>
<span data-ttu-id="9d3ab-103">在[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]，两个变量的引用将被视为同一如果其指针相同，即，如果两个变量指向内存中的同一个类实例。</span><span class="sxs-lookup"><span data-stu-id="9d3ab-103">In [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)], two variable references are considered identical if their pointers are the same, that is, if both variables point to the same class instance in memory.</span></span> <span data-ttu-id="9d3ab-104">例如，在 Windows 窗体应用程序中，你可能想要进行比较以确定是否当前的实例 (`Me`) 等同于一个特定实例，如`Form2`。</span><span class="sxs-lookup"><span data-stu-id="9d3ab-104">For example, in a Windows Forms application, you might want to make a comparison to determine whether the current instance (`Me`) is the same as a particular instance, such as `Form2`.</span></span>  
  
 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]<span data-ttu-id="9d3ab-105">提供两个运算符比较指针。</span><span class="sxs-lookup"><span data-stu-id="9d3ab-105"> provides two operators to compare pointers.</span></span> <span data-ttu-id="9d3ab-106">[Is 运算符](../../../../visual-basic/language-reference/operators/is-operator.md)返回`True`如果对象是相同的与[IsNot 运算符](../../../../visual-basic/language-reference/operators/isnot-operator.md)返回`True`如果它们不是。</span><span class="sxs-lookup"><span data-stu-id="9d3ab-106">The [Is Operator](../../../../visual-basic/language-reference/operators/is-operator.md) returns `True` if the objects are identical, and the [IsNot Operator](../../../../visual-basic/language-reference/operators/isnot-operator.md) returns `True` if they are not.</span></span>  
  
## <a name="determining-if-two-objects-are-identical"></a><span data-ttu-id="9d3ab-107">确定两个对象是否相同</span><span class="sxs-lookup"><span data-stu-id="9d3ab-107">Determining if Two Objects Are Identical</span></span>  
  
#### <a name="to-determine-if-two-objects-are-identical"></a><span data-ttu-id="9d3ab-108">若要确定两个对象是否相同</span><span class="sxs-lookup"><span data-stu-id="9d3ab-108">To determine if two objects are identical</span></span>  
  
1.  <span data-ttu-id="9d3ab-109">设置`Boolean`要测试两个对象表达式。</span><span class="sxs-lookup"><span data-stu-id="9d3ab-109">Set up a `Boolean` expression to test the two objects.</span></span>  
  
2.  <span data-ttu-id="9d3ab-110">在测试表达式中，使用`Is`运算符具有两个对象作为操作数。</span><span class="sxs-lookup"><span data-stu-id="9d3ab-110">In your testing expression, use the `Is` operator with the two objects as operands.</span></span>  
  
     <span data-ttu-id="9d3ab-111">`Is`返回`True`如果对象指向相同的类实例。</span><span class="sxs-lookup"><span data-stu-id="9d3ab-111">`Is` returns `True` if the objects point to the same class instance.</span></span>  
  
## <a name="determining-if-two-objects-are-not-identical"></a><span data-ttu-id="9d3ab-112">确定两个对象是否不相同</span><span class="sxs-lookup"><span data-stu-id="9d3ab-112">Determining if Two Objects Are Not Identical</span></span>  
 <span data-ttu-id="9d3ab-113">有时你想要执行的操作，如果两个对象不完全相同，并且它可能难以合并`Not`和`Is`，例如`If Not obj1 Is obj2`。</span><span class="sxs-lookup"><span data-stu-id="9d3ab-113">Sometimes you want to perform an action if the two objects are not identical, and it can be awkward to combine `Not` and `Is`, for example `If Not obj1 Is obj2`.</span></span> <span data-ttu-id="9d3ab-114">在这种情况下可以使用`IsNot`运算符。</span><span class="sxs-lookup"><span data-stu-id="9d3ab-114">In such a case you can use the `IsNot` operator.</span></span>  
  
#### <a name="to-determine-if-two-objects-are-not-identical"></a><span data-ttu-id="9d3ab-115">若要确定两个对象是否不相同</span><span class="sxs-lookup"><span data-stu-id="9d3ab-115">To determine if two objects are not identical</span></span>  
  
1.  <span data-ttu-id="9d3ab-116">设置`Boolean`要测试两个对象表达式。</span><span class="sxs-lookup"><span data-stu-id="9d3ab-116">Set up a `Boolean` expression to test the two objects.</span></span>  
  
2.  <span data-ttu-id="9d3ab-117">在测试表达式中，使用`IsNot`运算符具有两个对象作为操作数。</span><span class="sxs-lookup"><span data-stu-id="9d3ab-117">In your testing expression, use the `IsNot` operator with the two objects as operands.</span></span>  
  
     <span data-ttu-id="9d3ab-118">`IsNot`返回`True`如果对象未指向相同的类实例。</span><span class="sxs-lookup"><span data-stu-id="9d3ab-118">`IsNot` returns `True` if the objects do not point to the same class instance.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9d3ab-119">示例</span><span class="sxs-lookup"><span data-stu-id="9d3ab-119">Example</span></span>  
 <span data-ttu-id="9d3ab-120">下面的示例测试对`Object`变量上以查看它们是否指向相同的类实例。</span><span class="sxs-lookup"><span data-stu-id="9d3ab-120">The following example tests pairs of `Object` variables to see if they point to the same class instance.</span></span>  
  
 [!code-vb[VbVbalrKeywords#14](../../../../visual-basic/language-reference/codesnippet/VisualBasic/how-to-determine-whether-two-objects-are-identical_1.vb)]  
  
 <span data-ttu-id="9d3ab-121">前面的示例显示下面的输出。</span><span class="sxs-lookup"><span data-stu-id="9d3ab-121">The preceding example displays the following output.</span></span>  
  
 `objA different from objB? True`  
  
 `objA identical to objC? True`  
  
## <a name="see-also"></a><span data-ttu-id="9d3ab-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9d3ab-122">See Also</span></span>  
 [<span data-ttu-id="9d3ab-123">Object 数据类型</span><span class="sxs-lookup"><span data-stu-id="9d3ab-123">Object Data Type</span></span>](../../../../visual-basic/language-reference/data-types/object-data-type.md)  
 [<span data-ttu-id="9d3ab-124">对象变量</span><span class="sxs-lookup"><span data-stu-id="9d3ab-124">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)  
 [<span data-ttu-id="9d3ab-125">对象变量值</span><span class="sxs-lookup"><span data-stu-id="9d3ab-125">Object Variable Values</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)  
 [<span data-ttu-id="9d3ab-126">Is 运算符</span><span class="sxs-lookup"><span data-stu-id="9d3ab-126">Is Operator</span></span>](../../../../visual-basic/language-reference/operators/is-operator.md)  
 [<span data-ttu-id="9d3ab-127">IsNot 运算符</span><span class="sxs-lookup"><span data-stu-id="9d3ab-127">IsNot Operator</span></span>](../../../../visual-basic/language-reference/operators/isnot-operator.md)  
 [<span data-ttu-id="9d3ab-128">如何：确定两个对象是否相关</span><span class="sxs-lookup"><span data-stu-id="9d3ab-128">How to: Determine Whether Two Objects Are Related</span></span>](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-related.md)  
 [<span data-ttu-id="9d3ab-129">Me、My、MyBase 和 MyClass</span><span class="sxs-lookup"><span data-stu-id="9d3ab-129">Me, My, MyBase, and MyClass</span></span>](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
