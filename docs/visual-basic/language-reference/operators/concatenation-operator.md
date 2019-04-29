---
title: '&amp; 运算符 (Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- vb.&
helpviewer_keywords:
- And (&) operator
- ampersand operator (&)
- '& operator'
- concatenation operators [Visual Basic], syntax
- strings [Visual Basic], concatenating
ms.assetid: fefc3d00-cbf1-475c-8c5e-6fb213b3f85a
ms.openlocfilehash: dd85363447e9b405241d608550d9484b4760a739
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61778581"
---
# <a name="amp-operator-visual-basic"></a><span data-ttu-id="c028a-102">&amp; 运算符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c028a-102">&amp; Operator (Visual Basic)</span></span>
<span data-ttu-id="c028a-103">生成两个表达式的字符串串联。</span><span class="sxs-lookup"><span data-stu-id="c028a-103">Generates a string concatenation of two expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c028a-104">语法</span><span class="sxs-lookup"><span data-stu-id="c028a-104">Syntax</span></span>  
  
```  
result = expression1 & expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="c028a-105">部件</span><span class="sxs-lookup"><span data-stu-id="c028a-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="c028a-106">必需。</span><span class="sxs-lookup"><span data-stu-id="c028a-106">Required.</span></span> <span data-ttu-id="c028a-107">任何`String`或`Object`变量。</span><span class="sxs-lookup"><span data-stu-id="c028a-107">Any `String` or `Object` variable.</span></span>  
  
 `expression1`  
 <span data-ttu-id="c028a-108">必需。</span><span class="sxs-lookup"><span data-stu-id="c028a-108">Required.</span></span> <span data-ttu-id="c028a-109">具有数据类型扩大到任何表达式`String`。</span><span class="sxs-lookup"><span data-stu-id="c028a-109">Any expression with a data type that widens to `String`.</span></span>  
  
 `expression2`  
 <span data-ttu-id="c028a-110">必需。</span><span class="sxs-lookup"><span data-stu-id="c028a-110">Required.</span></span> <span data-ttu-id="c028a-111">具有数据类型扩大到任何表达式`String`。</span><span class="sxs-lookup"><span data-stu-id="c028a-111">Any expression with a data type that widens to `String`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c028a-112">备注</span><span class="sxs-lookup"><span data-stu-id="c028a-112">Remarks</span></span>  
 <span data-ttu-id="c028a-113">如果的数据类型`expression1`或`expression2`不是`String`加宽到但`String`，它将转换为`String`。</span><span class="sxs-lookup"><span data-stu-id="c028a-113">If the data type of `expression1` or `expression2` is not `String` but widens to `String`, it is converted to `String`.</span></span> <span data-ttu-id="c028a-114">如果任一数据类型不会扩大到`String`，编译器将生成错误。</span><span class="sxs-lookup"><span data-stu-id="c028a-114">If either of the data types does not widen to `String`, the compiler generates an error.</span></span>  
  
 <span data-ttu-id="c028a-115">数据类型`result`是`String`。</span><span class="sxs-lookup"><span data-stu-id="c028a-115">The data type of `result` is `String`.</span></span> <span data-ttu-id="c028a-116">如果一个或两个表达式的计算结果为[Nothing](../../../visual-basic/language-reference/nothing.md) ，或者包含的值<xref:System.DBNull.Value?displayProperty=nameWithType>，它们被视为值为字符串""。</span><span class="sxs-lookup"><span data-stu-id="c028a-116">If one or both expressions evaluate to [Nothing](../../../visual-basic/language-reference/nothing.md) or have a value of <xref:System.DBNull.Value?displayProperty=nameWithType>, they are treated as a string with a value of "".</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c028a-117">`&`运算符可以被*重载*，这意味着，某个类或结构可以重新定义其行为时，操作数的类或结构的类型。</span><span class="sxs-lookup"><span data-stu-id="c028a-117">The `&` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="c028a-118">如果你的代码对此类的类或结构使用此运算符，请确保了解其被重新定义的行为。</span><span class="sxs-lookup"><span data-stu-id="c028a-118">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="c028a-119">有关详细信息，请参阅 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)。</span><span class="sxs-lookup"><span data-stu-id="c028a-119">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c028a-120">And 符 (&) 字符还可用来标识作为类型的变量`Long`。</span><span class="sxs-lookup"><span data-stu-id="c028a-120">The ampersand (&) character can also be used to identify variables as type `Long`.</span></span> <span data-ttu-id="c028a-121">有关详细信息，请参阅[类型字符](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)。</span><span class="sxs-lookup"><span data-stu-id="c028a-121">For more information, see [Type Characters](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c028a-122">示例</span><span class="sxs-lookup"><span data-stu-id="c028a-122">Example</span></span>  
 <span data-ttu-id="c028a-123">此示例使用`&`要强制执行字符串串联运算符。</span><span class="sxs-lookup"><span data-stu-id="c028a-123">This example uses the `&` operator to force string concatenation.</span></span> <span data-ttu-id="c028a-124">结果是表示的两个字符串操作数串联的字符串值。</span><span class="sxs-lookup"><span data-stu-id="c028a-124">The result is a string value representing the concatenation of the two string operands.</span></span>  
  
 [!code-vb[VbVbalrOperators#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="c028a-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="c028a-125">See also</span></span>

- [<span data-ttu-id="c028a-126">&= 运算符</span><span class="sxs-lookup"><span data-stu-id="c028a-126">&= Operator</span></span>](../../../visual-basic/language-reference/operators/and-assignment-operator.md)
- [<span data-ttu-id="c028a-127">串联运算符</span><span class="sxs-lookup"><span data-stu-id="c028a-127">Concatenation Operators</span></span>](../../../visual-basic/language-reference/operators/concatenation-operators.md)
- [<span data-ttu-id="c028a-128">Visual Basic 中的运算符优先级</span><span class="sxs-lookup"><span data-stu-id="c028a-128">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="c028a-129">按功能列出的运算符</span><span class="sxs-lookup"><span data-stu-id="c028a-129">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="c028a-130">在 Visual Basic 中的串联运算符</span><span class="sxs-lookup"><span data-stu-id="c028a-130">Concatenation Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md)
