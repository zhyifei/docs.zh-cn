---
title: Is 运算符 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.is
helpviewer_keywords:
- comparison operators [Visual Basic]
- equivalent objects
- TypeOf...Is expression
- Is operator [Visual Basic]
ms.assetid: 8045a6c8-2a83-45b6-ad47-d09a704c656d
ms.openlocfilehash: a59ff4c956724c614342f0ee4c0622a67f1c25e7
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2019
ms.locfileid: "58817066"
---
# <a name="is-operator-visual-basic"></a><span data-ttu-id="b3381-102">Is 运算符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b3381-102">Is Operator (Visual Basic)</span></span>
<span data-ttu-id="b3381-103">两个对象引用变量进行比较。</span><span class="sxs-lookup"><span data-stu-id="b3381-103">Compares two object reference variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b3381-104">语法</span><span class="sxs-lookup"><span data-stu-id="b3381-104">Syntax</span></span>  
  
```  
result = object1 Is object2  
```  
  
## <a name="parts"></a><span data-ttu-id="b3381-105">部件</span><span class="sxs-lookup"><span data-stu-id="b3381-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="b3381-106">必需。</span><span class="sxs-lookup"><span data-stu-id="b3381-106">Required.</span></span> <span data-ttu-id="b3381-107">任何`Boolean`值。</span><span class="sxs-lookup"><span data-stu-id="b3381-107">Any `Boolean` value.</span></span>  
  
 `object1`  
 <span data-ttu-id="b3381-108">必需。</span><span class="sxs-lookup"><span data-stu-id="b3381-108">Required.</span></span> <span data-ttu-id="b3381-109">任何`Object`名称。</span><span class="sxs-lookup"><span data-stu-id="b3381-109">Any `Object` name.</span></span>  
  
 `object2`  
 <span data-ttu-id="b3381-110">必需。</span><span class="sxs-lookup"><span data-stu-id="b3381-110">Required.</span></span> <span data-ttu-id="b3381-111">任何`Object`名称。</span><span class="sxs-lookup"><span data-stu-id="b3381-111">Any `Object` name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b3381-112">备注</span><span class="sxs-lookup"><span data-stu-id="b3381-112">Remarks</span></span>  
 <span data-ttu-id="b3381-113">`Is`运算符确定两个对象引用是否引用同一对象。</span><span class="sxs-lookup"><span data-stu-id="b3381-113">The `Is` operator determines if two object references refer to the same object.</span></span> <span data-ttu-id="b3381-114">但是，它不会执行值的比较。</span><span class="sxs-lookup"><span data-stu-id="b3381-114">However, it does not perform value comparisons.</span></span> <span data-ttu-id="b3381-115">如果`object1`并`object2`都是指完全相同的对象实例`result`是`True`; 如果不是这样，`result`是`False`。</span><span class="sxs-lookup"><span data-stu-id="b3381-115">If `object1` and `object2` both refer to the exact same object instance, `result` is `True`; if they do not, `result` is `False`.</span></span>  
  
 <span data-ttu-id="b3381-116">`Is` 也可以用于`TypeOf`关键字来使`TypeOf`...`Is`测试是否与数据类型兼容的对象变量的表达式。</span><span class="sxs-lookup"><span data-stu-id="b3381-116">`Is` can also be used with the `TypeOf` keyword to make a `TypeOf`...`Is` expression, which tests whether an object variable is compatible with a data type.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b3381-117">`Is`关键字还用于[选择...Case 语句](../../../visual-basic/language-reference/statements/select-case-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="b3381-117">The `Is` keyword is also used in the [Select...Case Statement](../../../visual-basic/language-reference/statements/select-case-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b3381-118">示例</span><span class="sxs-lookup"><span data-stu-id="b3381-118">Example</span></span>  
 <span data-ttu-id="b3381-119">下面的示例使用`Is`运算符进行比较的对象引用对。</span><span class="sxs-lookup"><span data-stu-id="b3381-119">The following example uses the `Is` operator to compare pairs of object references.</span></span> <span data-ttu-id="b3381-120">结果被赋值给`Boolean`值，该值表示两个对象是否相同。</span><span class="sxs-lookup"><span data-stu-id="b3381-120">The results are assigned to a `Boolean` value representing whether the two objects are identical.</span></span>  
  
 [!code-vb[VbVbalrOperators#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#27)]  
  
 <span data-ttu-id="b3381-121">如前面的示例所示，可以使用`Is`运算符来测试同时早期绑定和后期绑定对象。</span><span class="sxs-lookup"><span data-stu-id="b3381-121">As the preceding example demonstrates, you can use the `Is` operator to test both early bound and late bound objects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3381-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="b3381-122">See also</span></span>

- [<span data-ttu-id="b3381-123">TypeOf 运算符</span><span class="sxs-lookup"><span data-stu-id="b3381-123">TypeOf Operator</span></span>](../../../visual-basic/language-reference/operators/typeof-operator.md)
- [<span data-ttu-id="b3381-124">IsNot 运算符</span><span class="sxs-lookup"><span data-stu-id="b3381-124">IsNot Operator</span></span>](../../../visual-basic/language-reference/operators/isnot-operator.md)
- [<span data-ttu-id="b3381-125">在 Visual Basic 中的比较运算符</span><span class="sxs-lookup"><span data-stu-id="b3381-125">Comparison Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [<span data-ttu-id="b3381-126">Visual Basic 中的运算符优先级</span><span class="sxs-lookup"><span data-stu-id="b3381-126">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="b3381-127">按功能列出的运算符</span><span class="sxs-lookup"><span data-stu-id="b3381-127">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="b3381-128">运算符和表达式</span><span class="sxs-lookup"><span data-stu-id="b3381-128">Operators and Expressions</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
