---
title: '&amp;= 运算符 (Visual Basic)'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.&=
helpviewer_keywords:
- operator &=
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- '&= operator [Visual Basic]'
- compound assignment statements [Visual Basic]
ms.assetid: 0cf262fc-1a05-419a-a503-60013f111c8a
caps.latest.revision: 15
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 929a9e8c3384451679fc52ad478eb03219d67192
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="amp-operator-visual-basic"></a><span data-ttu-id="300bf-102">&amp;= 运算符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="300bf-102">&amp;= Operator (Visual Basic)</span></span>
<span data-ttu-id="300bf-103">串联`String`表达式`String`变量或属性并将结果赋给该变量或属性。</span><span class="sxs-lookup"><span data-stu-id="300bf-103">Concatenates a `String` expression to a `String` variable or property and assigns the result to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="300bf-104">语法</span><span class="sxs-lookup"><span data-stu-id="300bf-104">Syntax</span></span>  
  
```  
variableorproperty &= expression  
```  
  
## <a name="parts"></a><span data-ttu-id="300bf-105">部件</span><span class="sxs-lookup"><span data-stu-id="300bf-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="300bf-106">必需。</span><span class="sxs-lookup"><span data-stu-id="300bf-106">Required.</span></span> <span data-ttu-id="300bf-107">任何`String`变量或属性。</span><span class="sxs-lookup"><span data-stu-id="300bf-107">Any `String` variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="300bf-108">必需。</span><span class="sxs-lookup"><span data-stu-id="300bf-108">Required.</span></span> <span data-ttu-id="300bf-109">任何 `String` 表达式。</span><span class="sxs-lookup"><span data-stu-id="300bf-109">Any `String` expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="300bf-110">备注</span><span class="sxs-lookup"><span data-stu-id="300bf-110">Remarks</span></span>  
 <span data-ttu-id="300bf-111">在左侧的元素`&=`运算符可以是简单的标量变量、 属性或数组的元素。</span><span class="sxs-lookup"><span data-stu-id="300bf-111">The element on the left side of the `&=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="300bf-112">变量或属性不能为[ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)。</span><span class="sxs-lookup"><span data-stu-id="300bf-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span> <span data-ttu-id="300bf-113">`&=`运算符串联`String`到右侧的表达式`String`变量或属性在其左侧，并将结果赋给该变量或与其左侧的属性。</span><span class="sxs-lookup"><span data-stu-id="300bf-113">The `&=` operator concatenates the `String` expression on its right to the `String` variable or property on its left, and assigns the result to the variable or property on its left.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="300bf-114">重载</span><span class="sxs-lookup"><span data-stu-id="300bf-114">Overloading</span></span>  
 <span data-ttu-id="300bf-115">[& 运算符](../../../visual-basic/language-reference/operators/concatenation-operator.md)可以是*重载*，这意味着，一个类或结构可以重新定义其行为时，操作数的类或结构的类型。</span><span class="sxs-lookup"><span data-stu-id="300bf-115">The [& Operator](../../../visual-basic/language-reference/operators/concatenation-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="300bf-116">重载`&`运算符会影响的行为`&=`运算符。</span><span class="sxs-lookup"><span data-stu-id="300bf-116">Overloading the `&` operator affects the behavior of the `&=` operator.</span></span> <span data-ttu-id="300bf-117">如果你的代码使用`&=`对类或重载的结构`&`，确保你理解其重新定义的行为。</span><span class="sxs-lookup"><span data-stu-id="300bf-117">If your code uses `&=` on a class or structure that overloads `&`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="300bf-118">有关详细信息，请参阅[运算符过程](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)。</span><span class="sxs-lookup"><span data-stu-id="300bf-118">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="300bf-119">示例</span><span class="sxs-lookup"><span data-stu-id="300bf-119">Example</span></span>  
 <span data-ttu-id="300bf-120">下面的示例使用`&=`运算符来连接两个`String`变量并将结果赋给第一个变量。</span><span class="sxs-lookup"><span data-stu-id="300bf-120">The following example uses the `&=` operator to concatenate two `String` variables and assign the result to the first variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#3](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/and-assignment-operator_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="300bf-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="300bf-121">See Also</span></span>  
 [<span data-ttu-id="300bf-122">& 运算符</span><span class="sxs-lookup"><span data-stu-id="300bf-122">& Operator</span></span>](../../../visual-basic/language-reference/operators/concatenation-operator.md)  
 [<span data-ttu-id="300bf-123">+= 运算符</span><span class="sxs-lookup"><span data-stu-id="300bf-123">+= Operator</span></span>](../../../visual-basic/language-reference/operators/addition-assignment-operator.md)  
 [<span data-ttu-id="300bf-124">赋值运算符</span><span class="sxs-lookup"><span data-stu-id="300bf-124">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)  
 [<span data-ttu-id="300bf-125">串联运算符</span><span class="sxs-lookup"><span data-stu-id="300bf-125">Concatenation Operators</span></span>](../../../visual-basic/language-reference/operators/concatenation-operators.md)  
 [<span data-ttu-id="300bf-126">Visual Basic 中的运算符优先级</span><span class="sxs-lookup"><span data-stu-id="300bf-126">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="300bf-127">按功能列出的运算符</span><span class="sxs-lookup"><span data-stu-id="300bf-127">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="300bf-128">语句</span><span class="sxs-lookup"><span data-stu-id="300bf-128">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
