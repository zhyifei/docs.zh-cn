---
title: 'How to: Define a Conversion Operator'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- operators [Visual Basic], defining
- procedures [Visual Basic], operator
- operators [Visual Basic], overloading
- return values [Visual Basic], Operator procedures
- operator overloading
ms.assetid: 54203dfa-c24b-463f-9942-d5153e89e762
ms.openlocfilehash: 0ff95390206947e5a28f7a5b85547b496746a9cc
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344898"
---
# <a name="how-to-define-a-conversion-operator-visual-basic"></a><span data-ttu-id="b1d04-102">如何：定义转换运算符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b1d04-102">How to: Define a Conversion Operator (Visual Basic)</span></span>
<span data-ttu-id="b1d04-103">如果已定义类或结构，则可以在类或结构的类型与另一种数据类型（如 `Integer`、`Double`或 `String`）之间定义类型转换运算符。</span><span class="sxs-lookup"><span data-stu-id="b1d04-103">If you have defined a class or structure, you can define a type conversion operator between the type of your class or structure and another data type (such as `Integer`, `Double`, or `String`).</span></span>  
  
 <span data-ttu-id="b1d04-104">将类型转换定义为类或结构中的[CType 函数](../../../../visual-basic/language-reference/functions/ctype-function.md)过程。</span><span class="sxs-lookup"><span data-stu-id="b1d04-104">Define the type conversion as a [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md) procedure within the class or structure.</span></span> <span data-ttu-id="b1d04-105">必须 `Public Shared`所有转换过程，并且每个转换过程必须指定[扩大](../../../../visual-basic/language-reference/modifiers/widening.md)或[收缩](../../../../visual-basic/language-reference/modifiers/narrowing.md)。</span><span class="sxs-lookup"><span data-stu-id="b1d04-105">All conversion procedures must be `Public Shared`, and each one must specify either [Widening](../../../../visual-basic/language-reference/modifiers/widening.md) or [Narrowing](../../../../visual-basic/language-reference/modifiers/narrowing.md).</span></span>  
  
 <span data-ttu-id="b1d04-106">在类或结构上定义运算符也称为*重载*运算符。</span><span class="sxs-lookup"><span data-stu-id="b1d04-106">Defining an operator on a class or structure is also called *overloading* the operator.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b1d04-107">示例</span><span class="sxs-lookup"><span data-stu-id="b1d04-107">Example</span></span>  
 <span data-ttu-id="b1d04-108">下面的示例定义名为 `digit` 和 `Byte`的结构之间的转换运算符。</span><span class="sxs-lookup"><span data-stu-id="b1d04-108">The following example defines conversion operators between a structure called `digit` and a `Byte`.</span></span>  
  
 [!code-vb[VbVbcnProcedures#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#27)]  
  
 <span data-ttu-id="b1d04-109">可以通过以下代码测试 `digit` 的结构。</span><span class="sxs-lookup"><span data-stu-id="b1d04-109">You can test the structure `digit` with the following code.</span></span>  
  
 [!code-vb[VbVbcnProcedures#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#28)]  
  
## <a name="see-also"></a><span data-ttu-id="b1d04-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b1d04-110">See also</span></span>

- [<span data-ttu-id="b1d04-111">运算符过程</span><span class="sxs-lookup"><span data-stu-id="b1d04-111">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="b1d04-112">如何：定义运算符</span><span class="sxs-lookup"><span data-stu-id="b1d04-112">How to: Define an Operator</span></span>](./how-to-define-an-operator.md)
- [<span data-ttu-id="b1d04-113">如何：调用运算符过程</span><span class="sxs-lookup"><span data-stu-id="b1d04-113">How to: Call an Operator Procedure</span></span>](./how-to-call-an-operator-procedure.md)
- [<span data-ttu-id="b1d04-114">如何：使用定义运算符的类</span><span class="sxs-lookup"><span data-stu-id="b1d04-114">How to: Use a Class that Defines Operators</span></span>](./how-to-use-a-class-that-defines-operators.md)
- [<span data-ttu-id="b1d04-115">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="b1d04-115">Operator Statement</span></span>](../../../../visual-basic/language-reference/statements/operator-statement.md)
- [<span data-ttu-id="b1d04-116">Structure 语句</span><span class="sxs-lookup"><span data-stu-id="b1d04-116">Structure Statement</span></span>](../../../../visual-basic/language-reference/statements/structure-statement.md)
- [<span data-ttu-id="b1d04-117">如何：声明结构</span><span class="sxs-lookup"><span data-stu-id="b1d04-117">How to: Declare a Structure</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
- [<span data-ttu-id="b1d04-118">隐式转换和显式转换</span><span class="sxs-lookup"><span data-stu-id="b1d04-118">Implicit and Explicit Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [<span data-ttu-id="b1d04-119">扩大转换和收缩转换</span><span class="sxs-lookup"><span data-stu-id="b1d04-119">Widening and Narrowing Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
