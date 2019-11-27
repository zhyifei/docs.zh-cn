---
title: '&amp;= 运算符'
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
ms.openlocfilehash: 8668bfcbf32bb34b422efe8116bbd12a2d80b1d4
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350268"
---
# <a name="amp-operator-visual-basic"></a><span data-ttu-id="7c293-102">&amp;= 运算符（Visual Basic）</span><span class="sxs-lookup"><span data-stu-id="7c293-102">&amp;= Operator (Visual Basic)</span></span>
<span data-ttu-id="7c293-103">将 `String` 表达式连接到 `String` 变量或属性，并将结果赋给变量或属性。</span><span class="sxs-lookup"><span data-stu-id="7c293-103">Concatenates a `String` expression to a `String` variable or property and assigns the result to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c293-104">语法</span><span class="sxs-lookup"><span data-stu-id="7c293-104">Syntax</span></span>  
  
```vb  
variableorproperty &= expression  
```  
  
## <a name="parts"></a><span data-ttu-id="7c293-105">部件</span><span class="sxs-lookup"><span data-stu-id="7c293-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="7c293-106">必需。</span><span class="sxs-lookup"><span data-stu-id="7c293-106">Required.</span></span> <span data-ttu-id="7c293-107">任何 `String` 变量或属性。</span><span class="sxs-lookup"><span data-stu-id="7c293-107">Any `String` variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="7c293-108">必需。</span><span class="sxs-lookup"><span data-stu-id="7c293-108">Required.</span></span> <span data-ttu-id="7c293-109">任何 `String` 表达式。</span><span class="sxs-lookup"><span data-stu-id="7c293-109">Any `String` expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7c293-110">备注</span><span class="sxs-lookup"><span data-stu-id="7c293-110">Remarks</span></span>  
 <span data-ttu-id="7c293-111">`&=` 运算符左侧的元素可以是简单的标量变量、属性或数组的元素。</span><span class="sxs-lookup"><span data-stu-id="7c293-111">The element on the left side of the `&=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="7c293-112">变量或属性不能是[只读](../../../visual-basic/language-reference/modifiers/readonly.md)的。</span><span class="sxs-lookup"><span data-stu-id="7c293-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span> <span data-ttu-id="7c293-113">`&=` 运算符将其右侧的 `String` 表达式连接到其左边的 `String` 变量或属性，并将结果赋给它左侧的变量或属性。</span><span class="sxs-lookup"><span data-stu-id="7c293-113">The `&=` operator concatenates the `String` expression on its right to the `String` variable or property on its left, and assigns the result to the variable or property on its left.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="7c293-114">重载</span><span class="sxs-lookup"><span data-stu-id="7c293-114">Overloading</span></span>  
 <span data-ttu-id="7c293-115">可以*重载* [& 运算符](../../../visual-basic/language-reference/operators/concatenation-operator.md)，这意味着当操作数具有该类或结构的类型时，该类或结构可以重新定义其行为。</span><span class="sxs-lookup"><span data-stu-id="7c293-115">The [& Operator](../../../visual-basic/language-reference/operators/concatenation-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="7c293-116">重载 `&` 运算符会影响 `&=` 运算符的行为。</span><span class="sxs-lookup"><span data-stu-id="7c293-116">Overloading the `&` operator affects the behavior of the `&=` operator.</span></span> <span data-ttu-id="7c293-117">如果你的代码在重载 `&`的类或结构上使用 `&=`，请确保了解其重新定义的行为。</span><span class="sxs-lookup"><span data-stu-id="7c293-117">If your code uses `&=` on a class or structure that overloads `&`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="7c293-118">有关更多信息，请参见 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)。</span><span class="sxs-lookup"><span data-stu-id="7c293-118">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="7c293-119">示例</span><span class="sxs-lookup"><span data-stu-id="7c293-119">Example</span></span>  
 <span data-ttu-id="7c293-120">下面的示例使用 `&=` 运算符将两个 `String` 变量连接起来，并将结果赋给第一个变量。</span><span class="sxs-lookup"><span data-stu-id="7c293-120">The following example uses the `&=` operator to concatenate two `String` variables and assign the result to the first variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="7c293-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7c293-121">See also</span></span>

- [<span data-ttu-id="7c293-122">& 运算符</span><span class="sxs-lookup"><span data-stu-id="7c293-122">& Operator</span></span>](../../../visual-basic/language-reference/operators/concatenation-operator.md)
- [<span data-ttu-id="7c293-123">+= 运算符</span><span class="sxs-lookup"><span data-stu-id="7c293-123">+= Operator</span></span>](../../../visual-basic/language-reference/operators/addition-assignment-operator.md)
- [<span data-ttu-id="7c293-124">赋值运算符</span><span class="sxs-lookup"><span data-stu-id="7c293-124">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [<span data-ttu-id="7c293-125">串联运算符</span><span class="sxs-lookup"><span data-stu-id="7c293-125">Concatenation Operators</span></span>](../../../visual-basic/language-reference/operators/concatenation-operators.md)
- [<span data-ttu-id="7c293-126">Visual Basic 中的运算符优先级</span><span class="sxs-lookup"><span data-stu-id="7c293-126">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="7c293-127">按功能列出的运算符</span><span class="sxs-lookup"><span data-stu-id="7c293-127">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="7c293-128">语句</span><span class="sxs-lookup"><span data-stu-id="7c293-128">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
