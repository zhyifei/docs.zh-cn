---
title: "Is 运算符 (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.is
helpviewer_keywords:
- comparison operators [Visual Basic]
- equivalent objects
- TypeOf...Is expression
- Is operator [Visual Basic]
ms.assetid: 8045a6c8-2a83-45b6-ad47-d09a704c656d
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4b1f3f0fa1fd782550c08c816f47b7541399198e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="is-operator-visual-basic"></a><span data-ttu-id="c26fd-102">Is 运算符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c26fd-102">Is Operator (Visual Basic)</span></span>
<span data-ttu-id="c26fd-103">比较两个对象引用变量。</span><span class="sxs-lookup"><span data-stu-id="c26fd-103">Compares two object reference variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c26fd-104">语法</span><span class="sxs-lookup"><span data-stu-id="c26fd-104">Syntax</span></span>  
  
```  
result = object1 Is object2  
```  
  
## <a name="parts"></a><span data-ttu-id="c26fd-105">部件</span><span class="sxs-lookup"><span data-stu-id="c26fd-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="c26fd-106">必需。</span><span class="sxs-lookup"><span data-stu-id="c26fd-106">Required.</span></span> <span data-ttu-id="c26fd-107">任何`Boolean`值。</span><span class="sxs-lookup"><span data-stu-id="c26fd-107">Any `Boolean` value.</span></span>  
  
 `object1`  
 <span data-ttu-id="c26fd-108">必需。</span><span class="sxs-lookup"><span data-stu-id="c26fd-108">Required.</span></span> <span data-ttu-id="c26fd-109">任何`Object`名称。</span><span class="sxs-lookup"><span data-stu-id="c26fd-109">Any `Object` name.</span></span>  
  
 `object2`  
 <span data-ttu-id="c26fd-110">必需。</span><span class="sxs-lookup"><span data-stu-id="c26fd-110">Required.</span></span> <span data-ttu-id="c26fd-111">任何`Object`名称。</span><span class="sxs-lookup"><span data-stu-id="c26fd-111">Any `Object` name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c26fd-112">备注</span><span class="sxs-lookup"><span data-stu-id="c26fd-112">Remarks</span></span>  
 <span data-ttu-id="c26fd-113">`Is`运算符确定两个对象引用是否引用同一对象。</span><span class="sxs-lookup"><span data-stu-id="c26fd-113">The `Is` operator determines if two object references refer to the same object.</span></span> <span data-ttu-id="c26fd-114">但是，它不执行值的比较。</span><span class="sxs-lookup"><span data-stu-id="c26fd-114">However, it does not perform value comparisons.</span></span> <span data-ttu-id="c26fd-115">如果`object1`和`object2`都是指完全相同的对象实例，`result`是`True`; 如果不是这样，`result`是`False`。</span><span class="sxs-lookup"><span data-stu-id="c26fd-115">If `object1` and `object2` both refer to the exact same object instance, `result` is `True`; if they do not, `result` is `False`.</span></span>  
  
 <span data-ttu-id="c26fd-116">`Is`也可以用于`TypeOf`关键字使`TypeOf`...`Is`表达式，测试的对象变量是否与数据类型兼容。</span><span class="sxs-lookup"><span data-stu-id="c26fd-116">`Is` can also be used with the `TypeOf` keyword to make a `TypeOf`...`Is` expression, which tests whether an object variable is compatible with a data type.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c26fd-117">`Is`关键字还用于[选择...Case 语句](../../../visual-basic/language-reference/statements/select-case-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="c26fd-117">The `Is` keyword is also used in the [Select...Case Statement](../../../visual-basic/language-reference/statements/select-case-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c26fd-118">示例</span><span class="sxs-lookup"><span data-stu-id="c26fd-118">Example</span></span>  
 <span data-ttu-id="c26fd-119">下面的示例使用`Is`运算符比较的对象引用的对。</span><span class="sxs-lookup"><span data-stu-id="c26fd-119">The following example uses the `Is` operator to compare pairs of object references.</span></span> <span data-ttu-id="c26fd-120">结果分配给`Boolean`值表示两个对象是否相同。</span><span class="sxs-lookup"><span data-stu-id="c26fd-120">The results are assigned to a `Boolean` value representing whether the two objects are identical.</span></span>  
  
 [!code-vb[VbVbalrOperators#27](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/is-operator_1.vb)]  
  
 <span data-ttu-id="c26fd-121">如前面的示例所示，你可以使用`Is`运算符测试早期绑定和后期绑定对象。</span><span class="sxs-lookup"><span data-stu-id="c26fd-121">As the preceding example demonstrates, you can use the `Is` operator to test both early bound and late bound objects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c26fd-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c26fd-122">See Also</span></span>  
 [<span data-ttu-id="c26fd-123">TypeOf 运算符</span><span class="sxs-lookup"><span data-stu-id="c26fd-123">TypeOf Operator</span></span>](../../../visual-basic/language-reference/operators/typeof-operator.md)  
 [<span data-ttu-id="c26fd-124">IsNot 运算符</span><span class="sxs-lookup"><span data-stu-id="c26fd-124">IsNot Operator</span></span>](../../../visual-basic/language-reference/operators/isnot-operator.md)  
 [<span data-ttu-id="c26fd-125">在 Visual Basic 中的比较运算符</span><span class="sxs-lookup"><span data-stu-id="c26fd-125">Comparison Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)  
 [<span data-ttu-id="c26fd-126">Visual Basic 中的运算符优先级</span><span class="sxs-lookup"><span data-stu-id="c26fd-126">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="c26fd-127">按功能列出的运算符</span><span class="sxs-lookup"><span data-stu-id="c26fd-127">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="c26fd-128">运算符和表达式</span><span class="sxs-lookup"><span data-stu-id="c26fd-128">Operators and Expressions</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
