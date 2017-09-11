---
title: "如何︰ 确定两个对象是否相同 (Visual Basic) |Microsoft 文档"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- testing, objects
- objects [Visual Basic], comparing
- object variables, determining identity
ms.assetid: 7829f817-0d1f-4749-a707-de0b95e0cf5c
caps.latest.revision: 19
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
ms.openlocfilehash: c9621412eb1429ed07d8861114a67a67b6c1d58c
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-determine-whether-two-objects-are-identical-visual-basic"></a><span data-ttu-id="96a8e-102">如何：确定两个对象是否相同 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="96a8e-102">How to: Determine Whether Two Objects Are Identical (Visual Basic)</span></span>
<span data-ttu-id="96a8e-103">在[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]，两个变量的引用将被视为相同的指针是相同的也就是说，如果这两个变量指向内存中的同一个类实例。</span><span class="sxs-lookup"><span data-stu-id="96a8e-103">In [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], two variable references are considered identical if their pointers are the same, that is, if both variables point to the same class instance in memory.</span></span> <span data-ttu-id="96a8e-104">例如，在 Windows 窗体应用程序中，可能想要进行比较以确定是否当前实例 (`Me`) 等同于一个特定实例，如`Form2`。</span><span class="sxs-lookup"><span data-stu-id="96a8e-104">For example, in a Windows Forms application, you might want to make a comparison to determine whether the current instance (`Me`) is the same as a particular instance, such as `Form2`.</span></span>  
  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="96a8e-105">提供了两个运算符比较指针。</span><span class="sxs-lookup"><span data-stu-id="96a8e-105"> provides two operators to compare pointers.</span></span> <span data-ttu-id="96a8e-106">[Is 运算符](../../../../visual-basic/language-reference/operators/is-operator.md)返回`True`如果对象相同的与[IsNot 运算符](../../../../visual-basic/language-reference/operators/isnot-operator.md)返回`True`如果它们不是。</span><span class="sxs-lookup"><span data-stu-id="96a8e-106">The [Is Operator](../../../../visual-basic/language-reference/operators/is-operator.md) returns `True` if the objects are identical, and the [IsNot Operator](../../../../visual-basic/language-reference/operators/isnot-operator.md) returns `True` if they are not.</span></span>  
  
## <a name="determining-if-two-objects-are-identical"></a><span data-ttu-id="96a8e-107">确定两个对象是否相同</span><span class="sxs-lookup"><span data-stu-id="96a8e-107">Determining if Two Objects Are Identical</span></span>  
  
#### <a name="to-determine-if-two-objects-are-identical"></a><span data-ttu-id="96a8e-108">若要确定两个对象是否相同</span><span class="sxs-lookup"><span data-stu-id="96a8e-108">To determine if two objects are identical</span></span>  
  
1.  <span data-ttu-id="96a8e-109">设置`Boolean`表达式来测试两个对象。</span><span class="sxs-lookup"><span data-stu-id="96a8e-109">Set up a `Boolean` expression to test the two objects.</span></span>  
  
2.  <span data-ttu-id="96a8e-110">测试表达式中，在使用`Is`两个对象作为操作数的运算符。</span><span class="sxs-lookup"><span data-stu-id="96a8e-110">In your testing expression, use the `Is` operator with the two objects as operands.</span></span>  
  
     <span data-ttu-id="96a8e-111">`Is`返回`True`如果指向同一个类实例的对象。</span><span class="sxs-lookup"><span data-stu-id="96a8e-111">`Is` returns `True` if the objects point to the same class instance.</span></span>  
  
## <a name="determining-if-two-objects-are-not-identical"></a><span data-ttu-id="96a8e-112">确定两个对象是否不相同</span><span class="sxs-lookup"><span data-stu-id="96a8e-112">Determining if Two Objects Are Not Identical</span></span>  
 <span data-ttu-id="96a8e-113">有时您想要执行的操作，如果两个对象不完全相同，并且可以适于组合`Not`和`Is`，例如`If Not obj1 Is obj2`。</span><span class="sxs-lookup"><span data-stu-id="96a8e-113">Sometimes you want to perform an action if the two objects are not identical, and it can be awkward to combine `Not` and `Is`, for example `If Not obj1 Is obj2`.</span></span> <span data-ttu-id="96a8e-114">在这种情况下可以使用`IsNot`运算符。</span><span class="sxs-lookup"><span data-stu-id="96a8e-114">In such a case you can use the `IsNot` operator.</span></span>  
  
#### <a name="to-determine-if-two-objects-are-not-identical"></a><span data-ttu-id="96a8e-115">若要确定两个对象是否不相同</span><span class="sxs-lookup"><span data-stu-id="96a8e-115">To determine if two objects are not identical</span></span>  
  
1.  <span data-ttu-id="96a8e-116">设置`Boolean`表达式来测试两个对象。</span><span class="sxs-lookup"><span data-stu-id="96a8e-116">Set up a `Boolean` expression to test the two objects.</span></span>  
  
2.  <span data-ttu-id="96a8e-117">测试表达式中，在使用`IsNot`两个对象作为操作数的运算符。</span><span class="sxs-lookup"><span data-stu-id="96a8e-117">In your testing expression, use the `IsNot` operator with the two objects as operands.</span></span>  
  
     <span data-ttu-id="96a8e-118">`IsNot`返回`True`如果对象未指向同一类实例。</span><span class="sxs-lookup"><span data-stu-id="96a8e-118">`IsNot` returns `True` if the objects do not point to the same class instance.</span></span>  
  
## <a name="example"></a><span data-ttu-id="96a8e-119">示例</span><span class="sxs-lookup"><span data-stu-id="96a8e-119">Example</span></span>  
 <span data-ttu-id="96a8e-120">下面的示例测试对`Object`变量上以查看是否指向同一个类实例。</span><span class="sxs-lookup"><span data-stu-id="96a8e-120">The following example tests pairs of `Object` variables to see if they point to the same class instance.</span></span>  
  
 <span data-ttu-id="96a8e-121">[!code-vb[VbVbalrKeywords #&14;](../../../../visual-basic/language-reference/codesnippet/VisualBasic/how-to-determine-whether-two-objects-are-identical_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="96a8e-121">[!code-vb[VbVbalrKeywords#14](../../../../visual-basic/language-reference/codesnippet/VisualBasic/how-to-determine-whether-two-objects-are-identical_1.vb)]</span></span>  
  
 <span data-ttu-id="96a8e-122">前面的示例显示以下输出。</span><span class="sxs-lookup"><span data-stu-id="96a8e-122">The preceding example displays the following output.</span></span>  
  
 `objA different from objB? True`  
  
 `objA identical to objC? True`  
  
## <a name="see-also"></a><span data-ttu-id="96a8e-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="96a8e-123">See Also</span></span>  
 <span data-ttu-id="96a8e-124">[Object 数据类型](../../../../visual-basic/language-reference/data-types/object-data-type.md) </span><span class="sxs-lookup"><span data-stu-id="96a8e-124">[Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md) </span></span>  
<span data-ttu-id="96a8e-125"> [对象变量](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md) </span><span class="sxs-lookup"><span data-stu-id="96a8e-125"> [Object Variables](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md) </span></span>  
<span data-ttu-id="96a8e-126"> [对象变量值](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md) </span><span class="sxs-lookup"><span data-stu-id="96a8e-126"> [Object Variable Values](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md) </span></span>  
<span data-ttu-id="96a8e-127"> [Is 运算符](../../../../visual-basic/language-reference/operators/is-operator.md) </span><span class="sxs-lookup"><span data-stu-id="96a8e-127"> [Is Operator](../../../../visual-basic/language-reference/operators/is-operator.md) </span></span>  
<span data-ttu-id="96a8e-128"> [IsNot 运算符](../../../../visual-basic/language-reference/operators/isnot-operator.md) </span><span class="sxs-lookup"><span data-stu-id="96a8e-128"> [IsNot Operator](../../../../visual-basic/language-reference/operators/isnot-operator.md) </span></span>  
<span data-ttu-id="96a8e-129"> [如何︰ 确定两个对象是否相关](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-related.md) </span><span class="sxs-lookup"><span data-stu-id="96a8e-129"> [How to: Determine Whether Two Objects Are Related](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-related.md) </span></span>  
<span data-ttu-id="96a8e-130"> [Me、My、MyBase 和 MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)</span><span class="sxs-lookup"><span data-stu-id="96a8e-130"> [Me, My, MyBase, and MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)</span></span>
