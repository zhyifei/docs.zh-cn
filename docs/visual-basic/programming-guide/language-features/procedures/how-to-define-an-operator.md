---
title: 如何：定义运算符 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- operators [Visual Basic], defining
- procedures [Visual Basic], operator
- Visual Basic code, operators
- syntax [Visual Basic], Operator procedures
- operators [Visual Basic], overloading
- operator procedures [Visual Basic], about operator procedures
- return values [Visual Basic], Operator procedures
- operator overloading
ms.assetid: d4b0e253-092a-4e6e-9fe2-01f562140a29
ms.openlocfilehash: fb150298562c1ec91f73f3c8075f4f8a4fc20b27
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54679521"
---
# <a name="how-to-define-an-operator-visual-basic"></a><span data-ttu-id="95e05-102">如何：定义运算符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="95e05-102">How to: Define an Operator (Visual Basic)</span></span>
<span data-ttu-id="95e05-103">如果已定义的类或结构，可以定义标准运算符的行为 (如`*`， `<>`，或`And`) 当一个或两个操作数是类或结构的类型。</span><span class="sxs-lookup"><span data-stu-id="95e05-103">If you have defined a class or structure, you can define the behavior of a standard operator (such as `*`, `<>`, or `And`) when one or both of the operands is of the type of your class or structure.</span></span>  
  
 <span data-ttu-id="95e05-104">标准运算符定义为类或结构中的运算符过程。</span><span class="sxs-lookup"><span data-stu-id="95e05-104">Define the standard operator as an operator procedure within the class or structure.</span></span> <span data-ttu-id="95e05-105">所有运算符过程都必须都是`Public` `Shared`。</span><span class="sxs-lookup"><span data-stu-id="95e05-105">All operator procedures must be `Public` `Shared`.</span></span>  
  
 <span data-ttu-id="95e05-106">在类或结构上定义一个运算符也称为*重载*运算符。</span><span class="sxs-lookup"><span data-stu-id="95e05-106">Defining an operator on a class or structure is also called *overloading* the operator.</span></span>  
  
## <a name="example"></a><span data-ttu-id="95e05-107">示例</span><span class="sxs-lookup"><span data-stu-id="95e05-107">Example</span></span>  
 <span data-ttu-id="95e05-108">下面的示例定义`+`调用的运算符为结构`height`。</span><span class="sxs-lookup"><span data-stu-id="95e05-108">The following example defines the `+` operator for a structure called `height`.</span></span> <span data-ttu-id="95e05-109">该结构的高度以英尺、 英寸为单位。</span><span class="sxs-lookup"><span data-stu-id="95e05-109">The structure uses heights measured in feet and inches.</span></span> <span data-ttu-id="95e05-110">一个*英寸*2.54 厘米和一个*foot*为 12 英寸。</span><span class="sxs-lookup"><span data-stu-id="95e05-110">One *inch* is 2.54 centimeters, and one *foot* is 12 inches.</span></span> <span data-ttu-id="95e05-111">若要确保规范化的值 (英寸 < 12.0)，该构造函数执行*取模*12 的运算。</span><span class="sxs-lookup"><span data-stu-id="95e05-111">To ensure normalized values (inches < 12.0), the constructor performs *modulo* 12 arithmetic.</span></span> <span data-ttu-id="95e05-112">`+`运算符使用构造函数生成规范化的值。</span><span class="sxs-lookup"><span data-stu-id="95e05-112">The `+` operator uses the constructor to generate normalized values.</span></span>  
  
 [!code-vb[VbVbcnProcedures#25](./codesnippet/VisualBasic/how-to-define-an-operator_1.vb)]  
  
 <span data-ttu-id="95e05-113">可以测试结构`height`用下面的代码。</span><span class="sxs-lookup"><span data-stu-id="95e05-113">You can test the structure `height` with the following code.</span></span>  
  
 [!code-vb[VbVbcnProcedures#26](./codesnippet/VisualBasic/how-to-define-an-operator_2.vb)]  
  
 <span data-ttu-id="95e05-114">有关详细信息和示例，请参阅 [Visual Basic 2005 中的运算符重载](https://msdn.microsoft.com/library/ms379613(v=vs.80).aspx)。</span><span class="sxs-lookup"><span data-stu-id="95e05-114">For more information and examples, see [Operator Overloading in Visual Basic 2005](https://msdn.microsoft.com/library/ms379613(v=vs.80).aspx).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95e05-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="95e05-115">See also</span></span>
- [<span data-ttu-id="95e05-116">运算符过程</span><span class="sxs-lookup"><span data-stu-id="95e05-116">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="95e05-117">如何：定义转换运算符</span><span class="sxs-lookup"><span data-stu-id="95e05-117">How to: Define a Conversion Operator</span></span>](./how-to-define-a-conversion-operator.md)
- [<span data-ttu-id="95e05-118">如何：调用运算符过程</span><span class="sxs-lookup"><span data-stu-id="95e05-118">How to: Call an Operator Procedure</span></span>](./how-to-call-an-operator-procedure.md)
- [<span data-ttu-id="95e05-119">如何：使用定义运算符的类</span><span class="sxs-lookup"><span data-stu-id="95e05-119">How to: Use a Class that Defines Operators</span></span>](./how-to-use-a-class-that-defines-operators.md)
- [<span data-ttu-id="95e05-120">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="95e05-120">Operator Statement</span></span>](../../../../visual-basic/language-reference/statements/operator-statement.md)
- [<span data-ttu-id="95e05-121">Structure 语句</span><span class="sxs-lookup"><span data-stu-id="95e05-121">Structure Statement</span></span>](../../../../visual-basic/language-reference/statements/structure-statement.md)
- [<span data-ttu-id="95e05-122">如何：声明结构</span><span class="sxs-lookup"><span data-stu-id="95e05-122">How to: Declare a Structure</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
- [<span data-ttu-id="95e05-123">Mod 运算符</span><span class="sxs-lookup"><span data-stu-id="95e05-123">Mod Operator</span></span>](../../../../visual-basic/language-reference/operators/mod-operator.md)
