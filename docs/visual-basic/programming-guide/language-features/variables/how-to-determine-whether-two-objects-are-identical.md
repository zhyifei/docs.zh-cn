---
title: 如何：确定两个对象是否相同 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- testing [Visual Basic], objects
- objects [Visual Basic], comparing
- object variables [Visual Basic], determining identity
ms.assetid: 7829f817-0d1f-4749-a707-de0b95e0cf5c
ms.openlocfilehash: aae053ae0473ed6ced0f28da3d5e5afc0be629df
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61769078"
---
# <a name="how-to-determine-whether-two-objects-are-identical-visual-basic"></a><span data-ttu-id="318d3-102">如何：确定两个对象是否相同 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="318d3-102">How to: Determine Whether Two Objects Are Identical (Visual Basic)</span></span>
<span data-ttu-id="318d3-103">在 Visual Basic 中，两个变量的引用被视为相同的条件是其指针是相同的也就是说，如果这两个变量指向内存中的同一个类实例。</span><span class="sxs-lookup"><span data-stu-id="318d3-103">In Visual Basic, two variable references are considered identical if their pointers are the same, that is, if both variables point to the same class instance in memory.</span></span> <span data-ttu-id="318d3-104">例如，在 Windows 窗体应用程序中，可能想要进行比较以确定是否当前实例 (`Me`) 等同于一个特定实例，如`Form2`。</span><span class="sxs-lookup"><span data-stu-id="318d3-104">For example, in a Windows Forms application, you might want to make a comparison to determine whether the current instance (`Me`) is the same as a particular instance, such as `Form2`.</span></span>  
  
 <span data-ttu-id="318d3-105">Visual Basic 提供了两个运算符比较指针。</span><span class="sxs-lookup"><span data-stu-id="318d3-105">Visual Basic provides two operators to compare pointers.</span></span> <span data-ttu-id="318d3-106">[Is 运算符](../../../../visual-basic/language-reference/operators/is-operator.md)返回`True`如果对象相同的并且[IsNot 运算符](../../../../visual-basic/language-reference/operators/isnot-operator.md)返回`True`如果它们不是。</span><span class="sxs-lookup"><span data-stu-id="318d3-106">The [Is Operator](../../../../visual-basic/language-reference/operators/is-operator.md) returns `True` if the objects are identical, and the [IsNot Operator](../../../../visual-basic/language-reference/operators/isnot-operator.md) returns `True` if they are not.</span></span>  
  
## <a name="determining-if-two-objects-are-identical"></a><span data-ttu-id="318d3-107">确定两个对象是否相同</span><span class="sxs-lookup"><span data-stu-id="318d3-107">Determining if Two Objects Are Identical</span></span>  
  
#### <a name="to-determine-if-two-objects-are-identical"></a><span data-ttu-id="318d3-108">若要确定两个对象是否相同</span><span class="sxs-lookup"><span data-stu-id="318d3-108">To determine if two objects are identical</span></span>  
  
1. <span data-ttu-id="318d3-109">设置`Boolean`要测试两个对象表达式。</span><span class="sxs-lookup"><span data-stu-id="318d3-109">Set up a `Boolean` expression to test the two objects.</span></span>  
  
2. <span data-ttu-id="318d3-110">测试表达式中，在使用`Is`运算符具有两个对象作为操作数。</span><span class="sxs-lookup"><span data-stu-id="318d3-110">In your testing expression, use the `Is` operator with the two objects as operands.</span></span>  
  
     <span data-ttu-id="318d3-111">`Is` 返回`True`如果对象指向同一个类实例。</span><span class="sxs-lookup"><span data-stu-id="318d3-111">`Is` returns `True` if the objects point to the same class instance.</span></span>  
  
## <a name="determining-if-two-objects-are-not-identical"></a><span data-ttu-id="318d3-112">确定两个对象是否不相同</span><span class="sxs-lookup"><span data-stu-id="318d3-112">Determining if Two Objects Are Not Identical</span></span>  
 <span data-ttu-id="318d3-113">有时您想要执行的操作，如果两个对象不完全相同，并且可以适于组合`Not`并`Is`，例如`If Not obj1 Is obj2`。</span><span class="sxs-lookup"><span data-stu-id="318d3-113">Sometimes you want to perform an action if the two objects are not identical, and it can be awkward to combine `Not` and `Is`, for example `If Not obj1 Is obj2`.</span></span> <span data-ttu-id="318d3-114">在这种情况下可以使用`IsNot`运算符。</span><span class="sxs-lookup"><span data-stu-id="318d3-114">In such a case you can use the `IsNot` operator.</span></span>  
  
#### <a name="to-determine-if-two-objects-are-not-identical"></a><span data-ttu-id="318d3-115">若要确定两个对象是否不相同</span><span class="sxs-lookup"><span data-stu-id="318d3-115">To determine if two objects are not identical</span></span>  
  
1. <span data-ttu-id="318d3-116">设置`Boolean`要测试两个对象表达式。</span><span class="sxs-lookup"><span data-stu-id="318d3-116">Set up a `Boolean` expression to test the two objects.</span></span>  
  
2. <span data-ttu-id="318d3-117">测试表达式中，在使用`IsNot`运算符具有两个对象作为操作数。</span><span class="sxs-lookup"><span data-stu-id="318d3-117">In your testing expression, use the `IsNot` operator with the two objects as operands.</span></span>  
  
     <span data-ttu-id="318d3-118">`IsNot` 返回`True`如果对象未指向同一类实例。</span><span class="sxs-lookup"><span data-stu-id="318d3-118">`IsNot` returns `True` if the objects do not point to the same class instance.</span></span>  
  
## <a name="example"></a><span data-ttu-id="318d3-119">示例</span><span class="sxs-lookup"><span data-stu-id="318d3-119">Example</span></span>  
 <span data-ttu-id="318d3-120">下面的示例测试对`Object`变量以查看是否指向同一个类实例。</span><span class="sxs-lookup"><span data-stu-id="318d3-120">The following example tests pairs of `Object` variables to see if they point to the same class instance.</span></span>  
  
 [!code-vb[VbVbalrKeywords#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/class7.vb#14)]  
  
 <span data-ttu-id="318d3-121">前面的示例中显示以下输出。</span><span class="sxs-lookup"><span data-stu-id="318d3-121">The preceding example displays the following output.</span></span>  
  
 `objA different from objB? True`  
  
 `objA identical to objC? True`  
  
## <a name="see-also"></a><span data-ttu-id="318d3-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="318d3-122">See also</span></span>

- [<span data-ttu-id="318d3-123">Object 数据类型</span><span class="sxs-lookup"><span data-stu-id="318d3-123">Object Data Type</span></span>](../../../../visual-basic/language-reference/data-types/object-data-type.md)
- [<span data-ttu-id="318d3-124">对象变量</span><span class="sxs-lookup"><span data-stu-id="318d3-124">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [<span data-ttu-id="318d3-125">对象变量值</span><span class="sxs-lookup"><span data-stu-id="318d3-125">Object Variable Values</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)
- [<span data-ttu-id="318d3-126">Is 运算符</span><span class="sxs-lookup"><span data-stu-id="318d3-126">Is Operator</span></span>](../../../../visual-basic/language-reference/operators/is-operator.md)
- [<span data-ttu-id="318d3-127">IsNot 运算符</span><span class="sxs-lookup"><span data-stu-id="318d3-127">IsNot Operator</span></span>](../../../../visual-basic/language-reference/operators/isnot-operator.md)
- [<span data-ttu-id="318d3-128">如何：确定两个对象是否相关</span><span class="sxs-lookup"><span data-stu-id="318d3-128">How to: Determine Whether Two Objects Are Related</span></span>](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-related.md)
- [<span data-ttu-id="318d3-129">Me、My、MyBase 和 MyClass</span><span class="sxs-lookup"><span data-stu-id="318d3-129">Me, My, MyBase, and MyClass</span></span>](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
