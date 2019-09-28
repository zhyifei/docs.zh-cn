---
title: '&amp;运算符（Visual Basic）'
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
ms.openlocfilehash: aaa7c1b9ab7f6c920180d97b55c3bdeb23f00e02
ms.sourcegitcommit: 35da8fb45b4cca4e59cc99a5c56262c356977159
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/28/2019
ms.locfileid: "71592248"
---
# <a name="amp-operator-visual-basic"></a><span data-ttu-id="6427e-102">&amp;运算符（Visual Basic）</span><span class="sxs-lookup"><span data-stu-id="6427e-102">&amp; Operator (Visual Basic)</span></span>
<span data-ttu-id="6427e-103">生成两个表达式的字符串串联。</span><span class="sxs-lookup"><span data-stu-id="6427e-103">Generates a string concatenation of two expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6427e-104">语法</span><span class="sxs-lookup"><span data-stu-id="6427e-104">Syntax</span></span>  
  
```vb  
result = expression1 & expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="6427e-105">部件</span><span class="sxs-lookup"><span data-stu-id="6427e-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="6427e-106">必需。</span><span class="sxs-lookup"><span data-stu-id="6427e-106">Required.</span></span> <span data-ttu-id="6427e-107">Any `String` 或`Object` variable。</span><span class="sxs-lookup"><span data-stu-id="6427e-107">Any `String` or `Object` variable.</span></span>  
  
 `expression1`  
 <span data-ttu-id="6427e-108">必需。</span><span class="sxs-lookup"><span data-stu-id="6427e-108">Required.</span></span> <span data-ttu-id="6427e-109">数据类型扩大到`String`的任何表达式。</span><span class="sxs-lookup"><span data-stu-id="6427e-109">Any expression with a data type that widens to `String`.</span></span>  
  
 `expression2`  
 <span data-ttu-id="6427e-110">必需。</span><span class="sxs-lookup"><span data-stu-id="6427e-110">Required.</span></span> <span data-ttu-id="6427e-111">数据类型扩大到`String`的任何表达式。</span><span class="sxs-lookup"><span data-stu-id="6427e-111">Any expression with a data type that widens to `String`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6427e-112">备注</span><span class="sxs-lookup"><span data-stu-id="6427e-112">Remarks</span></span>  
 <span data-ttu-id="6427e-113">如果`expression1` `String`或`expression2`的数据类型不能`String`扩大到，则会将其转换为`String`。</span><span class="sxs-lookup"><span data-stu-id="6427e-113">If the data type of `expression1` or `expression2` is not `String` but widens to `String`, it is converted to `String`.</span></span> <span data-ttu-id="6427e-114">如果数据类型之一不能扩大到`String`，编译器将生成错误。</span><span class="sxs-lookup"><span data-stu-id="6427e-114">If either of the data types does not widen to `String`, the compiler generates an error.</span></span>  
  
 <span data-ttu-id="6427e-115">的`result`数据类型为`String`。</span><span class="sxs-lookup"><span data-stu-id="6427e-115">The data type of `result` is `String`.</span></span> <span data-ttu-id="6427e-116">如果一个或两个表达式的计算结果都不为 [Nothing](../../../visual-basic/language-reference/nothing.md)，或者其值为，则将它们视为值为 "<xref:System.DBNull.Value?displayProperty=nameWithType>" 的字符串。</span><span class="sxs-lookup"><span data-stu-id="6427e-116">If one or both expressions evaluate to [Nothing](../../../visual-basic/language-reference/nothing.md) or have a value of <xref:System.DBNull.Value?displayProperty=nameWithType>, they are treated as a string with a value of "".</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6427e-117">@No__t-0 运算符可*重载*，这意味着当操作数具有该类或结构的类型时，该类或结构可以重新定义其行为。</span><span class="sxs-lookup"><span data-stu-id="6427e-117">The `&` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="6427e-118">如果你的代码在该类或结构上使用此运算符，请确保了解其重新定义的行为。</span><span class="sxs-lookup"><span data-stu-id="6427e-118">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="6427e-119">有关详细信息，请参阅 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)。</span><span class="sxs-lookup"><span data-stu-id="6427e-119">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6427e-120">与号（&）字符也可用于将变量标识为类型`Long`。</span><span class="sxs-lookup"><span data-stu-id="6427e-120">The ampersand (&) character can also be used to identify variables as type `Long`.</span></span> <span data-ttu-id="6427e-121">有关详细信息，请参阅[类型字符](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)。</span><span class="sxs-lookup"><span data-stu-id="6427e-121">For more information, see [Type Characters](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="6427e-122">示例</span><span class="sxs-lookup"><span data-stu-id="6427e-122">Example</span></span>  
 <span data-ttu-id="6427e-123">此示例使用`&`运算符强制字符串连接。</span><span class="sxs-lookup"><span data-stu-id="6427e-123">This example uses the `&` operator to force string concatenation.</span></span> <span data-ttu-id="6427e-124">结果是一个表示两个字符串操作数串联的字符串值。</span><span class="sxs-lookup"><span data-stu-id="6427e-124">The result is a string value representing the concatenation of the two string operands.</span></span>  
  
 [!code-vb[VbVbalrOperators#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="6427e-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="6427e-125">See also</span></span>

- [<span data-ttu-id="6427e-126">&= 运算符</span><span class="sxs-lookup"><span data-stu-id="6427e-126">&= Operator</span></span>](../../../visual-basic/language-reference/operators/and-assignment-operator.md)
- [<span data-ttu-id="6427e-127">串联运算符</span><span class="sxs-lookup"><span data-stu-id="6427e-127">Concatenation Operators</span></span>](../../../visual-basic/language-reference/operators/concatenation-operators.md)
- [<span data-ttu-id="6427e-128">Visual Basic 中的运算符优先级</span><span class="sxs-lookup"><span data-stu-id="6427e-128">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="6427e-129">按功能列出的运算符</span><span class="sxs-lookup"><span data-stu-id="6427e-129">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="6427e-130">Visual Basic 中的串联运算符</span><span class="sxs-lookup"><span data-stu-id="6427e-130">Concatenation Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md)
