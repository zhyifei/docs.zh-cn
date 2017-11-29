---
title: "&amp;运算符 (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.&
helpviewer_keywords:
- And (&) operator
- ampersand operator (&)
- '& operator'
- concatenation operators [Visual Basic], syntax
- strings [Visual Basic], concatenating
ms.assetid: fefc3d00-cbf1-475c-8c5e-6fb213b3f85a
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 76c8fc52a518dfe7850a5680b7d4f06f3d09bf73
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="amp-operator-visual-basic"></a><span data-ttu-id="36efe-102">&amp;运算符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="36efe-102">&amp; Operator (Visual Basic)</span></span>
<span data-ttu-id="36efe-103">生成两个表达式的字符串串联。</span><span class="sxs-lookup"><span data-stu-id="36efe-103">Generates a string concatenation of two expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36efe-104">语法</span><span class="sxs-lookup"><span data-stu-id="36efe-104">Syntax</span></span>  
  
```  
result = expression1 & expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="36efe-105">部件</span><span class="sxs-lookup"><span data-stu-id="36efe-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="36efe-106">必需。</span><span class="sxs-lookup"><span data-stu-id="36efe-106">Required.</span></span> <span data-ttu-id="36efe-107">任何`String`或`Object`变量。</span><span class="sxs-lookup"><span data-stu-id="36efe-107">Any `String` or `Object` variable.</span></span>  
  
 `expression1`  
 <span data-ttu-id="36efe-108">必需。</span><span class="sxs-lookup"><span data-stu-id="36efe-108">Required.</span></span> <span data-ttu-id="36efe-109">具有数据类型扩大到任何表达式`String`。</span><span class="sxs-lookup"><span data-stu-id="36efe-109">Any expression with a data type that widens to `String`.</span></span>  
  
 `expression2`  
 <span data-ttu-id="36efe-110">必需。</span><span class="sxs-lookup"><span data-stu-id="36efe-110">Required.</span></span> <span data-ttu-id="36efe-111">具有数据类型扩大到任何表达式`String`。</span><span class="sxs-lookup"><span data-stu-id="36efe-111">Any expression with a data type that widens to `String`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="36efe-112">备注</span><span class="sxs-lookup"><span data-stu-id="36efe-112">Remarks</span></span>  
 <span data-ttu-id="36efe-113">如果数据类型的`expression1`或`expression2`不`String`但扩大到`String`，它将转换为`String`。</span><span class="sxs-lookup"><span data-stu-id="36efe-113">If the data type of `expression1` or `expression2` is not `String` but widens to `String`, it is converted to `String`.</span></span> <span data-ttu-id="36efe-114">如果任一数据类型不会扩大到`String`，编译器将生成错误。</span><span class="sxs-lookup"><span data-stu-id="36efe-114">If either of the data types does not widen to `String`, the compiler generates an error.</span></span>  
  
 <span data-ttu-id="36efe-115">数据类型`result`是`String`。</span><span class="sxs-lookup"><span data-stu-id="36efe-115">The data type of `result` is `String`.</span></span> <span data-ttu-id="36efe-116">如果一个或两个表达式的计算结果为[执行任何操作](../../../visual-basic/language-reference/nothing.md)或必须具有的值<xref:System.DBNull.Value?displayProperty=nameWithType>，它们被视为包含的值的字符串""。</span><span class="sxs-lookup"><span data-stu-id="36efe-116">If one or both expressions evaluate to [Nothing](../../../visual-basic/language-reference/nothing.md) or have a value of <xref:System.DBNull.Value?displayProperty=nameWithType>, they are treated as a string with a value of "".</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="36efe-117">`&`运算符可以被*重载*，这意味着，一个类或结构可以重新定义其行为时，操作数的类或结构的类型。</span><span class="sxs-lookup"><span data-stu-id="36efe-117">The `&` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="36efe-118">如果你的代码使用此运算符对这样的类或结构，请确保你了解其重新定义的行为。</span><span class="sxs-lookup"><span data-stu-id="36efe-118">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="36efe-119">有关详细信息，请参阅[运算符过程](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)。</span><span class="sxs-lookup"><span data-stu-id="36efe-119">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="36efe-120">And 符 (&) 符也可用来标识为类型的变量`Long`。</span><span class="sxs-lookup"><span data-stu-id="36efe-120">The ampersand (&) character can also be used to identify variables as type `Long`.</span></span> <span data-ttu-id="36efe-121">有关详细信息，请参阅[类型字符](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)。</span><span class="sxs-lookup"><span data-stu-id="36efe-121">For more information, see [Type Characters](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="36efe-122">示例</span><span class="sxs-lookup"><span data-stu-id="36efe-122">Example</span></span>  
 <span data-ttu-id="36efe-123">此示例使用`&`运算符来强制字符串串联。</span><span class="sxs-lookup"><span data-stu-id="36efe-123">This example uses the `&` operator to force string concatenation.</span></span> <span data-ttu-id="36efe-124">结果是表示的两个字符串操作数串联的字符串值。</span><span class="sxs-lookup"><span data-stu-id="36efe-124">The result is a string value representing the concatenation of the two string operands.</span></span>  
  
 [!code-vb[VbVbalrOperators#2](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/concatenation-operator_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="36efe-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="36efe-125">See Also</span></span>  
 [<span data-ttu-id="36efe-126">&= 运算符</span><span class="sxs-lookup"><span data-stu-id="36efe-126">&= Operator</span></span>](../../../visual-basic/language-reference/operators/and-assignment-operator.md)  
 [<span data-ttu-id="36efe-127">串联运算符</span><span class="sxs-lookup"><span data-stu-id="36efe-127">Concatenation Operators</span></span>](../../../visual-basic/language-reference/operators/concatenation-operators.md)  
 [<span data-ttu-id="36efe-128">Visual Basic 中的运算符优先级</span><span class="sxs-lookup"><span data-stu-id="36efe-128">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="36efe-129">按功能列出的运算符</span><span class="sxs-lookup"><span data-stu-id="36efe-129">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="36efe-130">在 Visual Basic 中的串联运算符</span><span class="sxs-lookup"><span data-stu-id="36efe-130">Concatenation Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md)
