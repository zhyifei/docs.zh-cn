---
title: '&amp;= 运算符 (Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- vb.&=
helpviewer_keywords:
- operator &=
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- '&= operator [Visual Basic]'
- compound assignment statements [Visual Basic]
ms.assetid: 0cf262fc-1a05-419a-a503-60013f111c8a
ms.openlocfilehash: fa009168be3781c727cd5a9cb6976b8c16fb2843
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2019
ms.locfileid: "56967485"
---
# <a name="amp-operator-visual-basic"></a><span data-ttu-id="02619-102">&amp;= 运算符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="02619-102">&amp;= Operator (Visual Basic)</span></span>
<span data-ttu-id="02619-103">将连接在一起`String`表达式`String`变量或属性，并将结果赋给变量或属性。</span><span class="sxs-lookup"><span data-stu-id="02619-103">Concatenates a `String` expression to a `String` variable or property and assigns the result to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02619-104">语法</span><span class="sxs-lookup"><span data-stu-id="02619-104">Syntax</span></span>  
  
```  
variableorproperty &= expression  
```  
  
## <a name="parts"></a><span data-ttu-id="02619-105">部件</span><span class="sxs-lookup"><span data-stu-id="02619-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="02619-106">必需。</span><span class="sxs-lookup"><span data-stu-id="02619-106">Required.</span></span> <span data-ttu-id="02619-107">任何`String`变量或属性。</span><span class="sxs-lookup"><span data-stu-id="02619-107">Any `String` variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="02619-108">必需。</span><span class="sxs-lookup"><span data-stu-id="02619-108">Required.</span></span> <span data-ttu-id="02619-109">任何 `String` 表达式。</span><span class="sxs-lookup"><span data-stu-id="02619-109">Any `String` expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="02619-110">备注</span><span class="sxs-lookup"><span data-stu-id="02619-110">Remarks</span></span>  
 <span data-ttu-id="02619-111">在左侧和右侧的元素`&=`运算符可以是简单的标量变量、 属性或数组的元素。</span><span class="sxs-lookup"><span data-stu-id="02619-111">The element on the left side of the `&=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="02619-112">变量或属性不能[ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)。</span><span class="sxs-lookup"><span data-stu-id="02619-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span> <span data-ttu-id="02619-113">`&=`运算符串联`String`到其右侧的表达式`String`变量或属性在其左侧，并将结果赋给变量或在其左侧的属性。</span><span class="sxs-lookup"><span data-stu-id="02619-113">The `&=` operator concatenates the `String` expression on its right to the `String` variable or property on its left, and assigns the result to the variable or property on its left.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="02619-114">重载</span><span class="sxs-lookup"><span data-stu-id="02619-114">Overloading</span></span>  
 <span data-ttu-id="02619-115">[& 运算符](../../../visual-basic/language-reference/operators/concatenation-operator.md)可以是*重载*，这意味着，某个类或结构可以重新定义其行为时，操作数的类或结构的类型。</span><span class="sxs-lookup"><span data-stu-id="02619-115">The [& Operator](../../../visual-basic/language-reference/operators/concatenation-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="02619-116">重载`&`运算符会影响的行为`&=`运算符。</span><span class="sxs-lookup"><span data-stu-id="02619-116">Overloading the `&` operator affects the behavior of the `&=` operator.</span></span> <span data-ttu-id="02619-117">如果你的代码使用`&=`上类或结构的重载`&`，确保了解其重新定义的行为。</span><span class="sxs-lookup"><span data-stu-id="02619-117">If your code uses `&=` on a class or structure that overloads `&`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="02619-118">有关详细信息，请参阅 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)。</span><span class="sxs-lookup"><span data-stu-id="02619-118">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="02619-119">示例</span><span class="sxs-lookup"><span data-stu-id="02619-119">Example</span></span>  
 <span data-ttu-id="02619-120">下面的示例使用`&=`运算符来串联两个`String`变量并将结果赋给第一个变量。</span><span class="sxs-lookup"><span data-stu-id="02619-120">The following example uses the `&=` operator to concatenate two `String` variables and assign the result to the first variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="02619-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="02619-121">See also</span></span>
- [<span data-ttu-id="02619-122">& 运算符</span><span class="sxs-lookup"><span data-stu-id="02619-122">& Operator</span></span>](../../../visual-basic/language-reference/operators/concatenation-operator.md)
- [<span data-ttu-id="02619-123">+= 运算符</span><span class="sxs-lookup"><span data-stu-id="02619-123">+= Operator</span></span>](../../../visual-basic/language-reference/operators/addition-assignment-operator.md)
- [<span data-ttu-id="02619-124">赋值运算符</span><span class="sxs-lookup"><span data-stu-id="02619-124">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [<span data-ttu-id="02619-125">串联运算符</span><span class="sxs-lookup"><span data-stu-id="02619-125">Concatenation Operators</span></span>](../../../visual-basic/language-reference/operators/concatenation-operators.md)
- [<span data-ttu-id="02619-126">Visual Basic 中的运算符优先级</span><span class="sxs-lookup"><span data-stu-id="02619-126">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="02619-127">按功能列出的运算符</span><span class="sxs-lookup"><span data-stu-id="02619-127">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="02619-128">语句</span><span class="sxs-lookup"><span data-stu-id="02619-128">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
