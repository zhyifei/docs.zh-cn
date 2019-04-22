---
title: 如何：匹配字符串与模式 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- comparison operators [Visual Basic], comparing strings
- pattern matching
- strings [Visual Basic], comparing
- string comparison [Visual Basic], operators
- Visual Basic code, operators
- pattern matching [Visual Basic], string comparison
- string comparison [Visual Basic]
- Like operator [Visual Basic], pattern matching
- pattern matching, empty strings
- operators [Visual Basic], comparison
ms.assetid: 19a83804-b5af-4739-928b-ac93e64e457f
ms.openlocfilehash: c14aa35ce15549ad9eccabe2330a7c43b6795140
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59316266"
---
# <a name="how-to-match-a-string-against-a-pattern-visual-basic"></a><span data-ttu-id="c418a-102">如何：匹配字符串与模式 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c418a-102">How to: Match a String against a Pattern (Visual Basic)</span></span>
<span data-ttu-id="c418a-103">如果想要找出的表达式[字符串数据类型](../../../../visual-basic/language-reference/data-types/string-data-type.md)满足一种模式，则可以使用[Like 运算符](../../../../visual-basic/language-reference/operators/like-operator.md)。</span><span class="sxs-lookup"><span data-stu-id="c418a-103">If you want to find out if an expression of the [String Data Type](../../../../visual-basic/language-reference/data-types/string-data-type.md) satisfies a pattern, then you can use the [Like Operator](../../../../visual-basic/language-reference/operators/like-operator.md).</span></span>  
  
 <span data-ttu-id="c418a-104">`Like` 采用两个操作数。</span><span class="sxs-lookup"><span data-stu-id="c418a-104">`Like` takes two operands.</span></span> <span data-ttu-id="c418a-105">左的操作数是字符串表达式和右操作数是一个包含要用于匹配的模式字符串。</span><span class="sxs-lookup"><span data-stu-id="c418a-105">The left operand is a string expression, and the right operand is a string containing the pattern to be used for matching.</span></span> <span data-ttu-id="c418a-106">`Like` 返回`Boolean`值，该值指示字符串表达式是否满足模式的要求。</span><span class="sxs-lookup"><span data-stu-id="c418a-106">`Like` returns a `Boolean` value indicating whether the string expression satisfies the pattern.</span></span>  
  
 <span data-ttu-id="c418a-107">可以与匹配针对特定字符、 通配符字符、 字符列表或字符范围的字符串表达式中的每个字符。</span><span class="sxs-lookup"><span data-stu-id="c418a-107">You can match each character in the string expression against a specific character, a wildcard character, a character list, or a character range.</span></span> <span data-ttu-id="c418a-108">模式字符串中的规范的位置对应于要在字符串表达式中匹配的字符的位置。</span><span class="sxs-lookup"><span data-stu-id="c418a-108">The positions of the specifications in the pattern string correspond to the positions of the characters to be matched in the string expression.</span></span>  
  
### <a name="to-match-a-character-in-the-string-expression-against-a-specific-character"></a><span data-ttu-id="c418a-109">若要匹配针对特定字符的字符串表达式中的字符</span><span class="sxs-lookup"><span data-stu-id="c418a-109">To match a character in the string expression against a specific character</span></span>  
  
-   <span data-ttu-id="c418a-110">直接在模式字符串中放置的特定字符。</span><span class="sxs-lookup"><span data-stu-id="c418a-110">Put the specific character directly in the pattern string.</span></span> <span data-ttu-id="c418a-111">某些特殊字符必须括在方括号中 (`[ ]`)。</span><span class="sxs-lookup"><span data-stu-id="c418a-111">Certain special characters must be enclosed in brackets (`[ ]`).</span></span> <span data-ttu-id="c418a-112">有关详细信息，请参阅[Like 运算符](../../../../visual-basic/language-reference/operators/like-operator.md)。</span><span class="sxs-lookup"><span data-stu-id="c418a-112">For more information, see [Like Operator](../../../../visual-basic/language-reference/operators/like-operator.md).</span></span>  
  
     <span data-ttu-id="c418a-113">下面的示例测试是否`myString`只包含单个字符`H`。</span><span class="sxs-lookup"><span data-stu-id="c418a-113">The following example tests whether `myString` consists exactly of the single character `H`.</span></span>  
  
     [!code-vb[VbVbalrOperators#70](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#70)]  
  
### <a name="to-match-a-character-in-the-string-expression-against-a-wildcard-character"></a><span data-ttu-id="c418a-114">在对通配符字符的字符串表达式中的字符进行匹配</span><span class="sxs-lookup"><span data-stu-id="c418a-114">To match a character in the string expression against a wildcard character</span></span>  
  
-   <span data-ttu-id="c418a-115">将问号 (`?`) 模式字符串中。</span><span class="sxs-lookup"><span data-stu-id="c418a-115">Put a question mark (`?`) in the pattern string.</span></span> <span data-ttu-id="c418a-116">此位置中的任何有效字符，可以成功匹配。</span><span class="sxs-lookup"><span data-stu-id="c418a-116">Any valid character in this position makes a successful match.</span></span>  
  
     <span data-ttu-id="c418a-117">下面的示例测试是否`myString`包含单个字符`W`跟两个字符的任何值。</span><span class="sxs-lookup"><span data-stu-id="c418a-117">The following example tests whether `myString` consists of the single character `W` followed by exactly two characters of any values.</span></span>  
  
     [!code-vb[VbVbalrOperators#71](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#71)]  
  
### <a name="to-match-a-character-in-the-string-expression-against-a-list-of-characters"></a><span data-ttu-id="c418a-118">针对列表的字符的字符串表达式中的字符进行匹配</span><span class="sxs-lookup"><span data-stu-id="c418a-118">To match a character in the string expression against a list of characters</span></span>  
  
-   <span data-ttu-id="c418a-119">将括号放 (`[ ]`) 在模式字符串，并放置的字符列表括号内。</span><span class="sxs-lookup"><span data-stu-id="c418a-119">Put brackets (`[ ]`) in the pattern string, and inside the brackets put the list of characters.</span></span> <span data-ttu-id="c418a-120">不要用逗号或任何其他分隔符分隔字符。</span><span class="sxs-lookup"><span data-stu-id="c418a-120">Do not separate the characters with commas or any other separator.</span></span> <span data-ttu-id="c418a-121">在列表中的任何单个字符，可以成功匹配。</span><span class="sxs-lookup"><span data-stu-id="c418a-121">Any single character in the list makes a successful match.</span></span>  
  
     <span data-ttu-id="c418a-122">下面的示例测试是否`myString`包含跟一个字符的任意有效字符`A`， `C`，或`E`。</span><span class="sxs-lookup"><span data-stu-id="c418a-122">The following example tests whether `myString` consists of any valid character followed by exactly one of the characters `A`, `C`, or `E`.</span></span>  
  
     [!code-vb[VbVbalrOperators#72](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#72)]  
  
     <span data-ttu-id="c418a-123">请注意，此匹配区分大小写。</span><span class="sxs-lookup"><span data-stu-id="c418a-123">Note that this match is case-sensitive.</span></span>  
  
### <a name="to-match-a-character-in-the-string-expression-against-a-range-of-characters"></a><span data-ttu-id="c418a-124">针对一系列字符的字符串表达式中的字符进行匹配</span><span class="sxs-lookup"><span data-stu-id="c418a-124">To match a character in the string expression against a range of characters</span></span>  
  
-   <span data-ttu-id="c418a-125">将括号放 (`[ ]`) 在模式字符串中，并将最低和最高的字符范围中放入括号内，由连字符分隔 (`–`)。</span><span class="sxs-lookup"><span data-stu-id="c418a-125">Put brackets (`[ ]`) in the pattern string, and inside the brackets put the lowest and highest characters in the range, separated by a hyphen (`–`).</span></span> <span data-ttu-id="c418a-126">在范围内的任何单个字符，可以成功匹配。</span><span class="sxs-lookup"><span data-stu-id="c418a-126">Any single character within the range makes a successful match.</span></span>  
  
     <span data-ttu-id="c418a-127">下面的示例测试是否`myString`包含的字符`num`正好有一个字符后跟`i`， `j`， `k`， `l`， `m`，或`n`。</span><span class="sxs-lookup"><span data-stu-id="c418a-127">The following example tests whether `myString` consists of the characters `num` followed by exactly one of the characters `i`, `j`, `k`, `l`, `m`, or `n`.</span></span>  
  
     [!code-vb[VbVbalrOperators#73](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#73)]  
  
     <span data-ttu-id="c418a-128">请注意，此匹配区分大小写。</span><span class="sxs-lookup"><span data-stu-id="c418a-128">Note that this match is case-sensitive.</span></span>  
  
## <a name="matching-empty-strings"></a><span data-ttu-id="c418a-129">匹配空字符串</span><span class="sxs-lookup"><span data-stu-id="c418a-129">Matching Empty Strings</span></span>  
 <span data-ttu-id="c418a-130">`Like` 将序列`[]`为零长度字符串 (`""`)。</span><span class="sxs-lookup"><span data-stu-id="c418a-130">`Like` treats the sequence `[]` as a zero-length string (`""`).</span></span> <span data-ttu-id="c418a-131">可以使用`[]`来测试是否将整个字符串表达式为空，但不能使用它来测试是否为空的字符串表达式中的特定位置。</span><span class="sxs-lookup"><span data-stu-id="c418a-131">You can use `[]` to test whether the entire string expression is empty, but you cannot use it to test if a particular position in the string expression is empty.</span></span> <span data-ttu-id="c418a-132">如果空位置选项之一需要测试对于您可以使用`Like`不止一次。</span><span class="sxs-lookup"><span data-stu-id="c418a-132">If an empty position is one of the options you need to test for, you can use `Like` more than once.</span></span>  
  
#### <a name="to-match-a-character-in-the-string-expression-against-a-list-of-characters-or-no-character"></a><span data-ttu-id="c418a-133">针对列表的字符或任何字符的字符串表达式中的字符进行匹配</span><span class="sxs-lookup"><span data-stu-id="c418a-133">To match a character in the string expression against a list of characters or no character</span></span>  
  
1. <span data-ttu-id="c418a-134">调用`Like`两次在同一个运算符的字符串表达式，并使用连接的两个调用[或运算符](../../../../visual-basic/language-reference/operators/or-operator.md)或[OrElse 运算符](../../../../visual-basic/language-reference/operators/orelse-operator.md)。</span><span class="sxs-lookup"><span data-stu-id="c418a-134">Call the `Like` operator twice on the same string expression, and connect the two calls with either the [Or Operator](../../../../visual-basic/language-reference/operators/or-operator.md) or the [OrElse Operator](../../../../visual-basic/language-reference/operators/orelse-operator.md).</span></span>  
  
2. <span data-ttu-id="c418a-135">在模式字符串中第一个`Like`子句，包括字符列表中，用方括号括起来 (`[ ]`)。</span><span class="sxs-lookup"><span data-stu-id="c418a-135">In the pattern string for the first `Like` clause, include the character list, enclosed in brackets (`[ ]`).</span></span>  
  
3. <span data-ttu-id="c418a-136">在模式字符串中第二个`Like`子句中，不要将放在任何字符的位置有问题。</span><span class="sxs-lookup"><span data-stu-id="c418a-136">In the pattern string for the second `Like` clause, do not put any character at the position in question.</span></span>  
  
     <span data-ttu-id="c418a-137">下面的示例测试的七位数电话号码`phoneNum`为 3 个数字后, 跟一个空格、 连字符 (`–`)，一段 (`.`)，或没有字符后, 跟 4 个数字。</span><span class="sxs-lookup"><span data-stu-id="c418a-137">The following example tests the seven-digit telephone number `phoneNum` for exactly three numeric digits, followed by a space, a hyphen (`–`), a period (`.`), or no character at all, followed by exactly four numeric digits.</span></span>  
  
     [!code-vb[VbVbalrOperators#74](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#74)]  
  
## <a name="see-also"></a><span data-ttu-id="c418a-138">请参阅</span><span class="sxs-lookup"><span data-stu-id="c418a-138">See also</span></span>

- [<span data-ttu-id="c418a-139">比较运算符</span><span class="sxs-lookup"><span data-stu-id="c418a-139">Comparison Operators</span></span>](../../../../visual-basic/language-reference/operators/comparison-operators.md)
- [<span data-ttu-id="c418a-140">运算符和表达式</span><span class="sxs-lookup"><span data-stu-id="c418a-140">Operators and Expressions</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
- [<span data-ttu-id="c418a-141">Like 运算符</span><span class="sxs-lookup"><span data-stu-id="c418a-141">Like Operator</span></span>](../../../../visual-basic/language-reference/operators/like-operator.md)
- [<span data-ttu-id="c418a-142">String 数据类型</span><span class="sxs-lookup"><span data-stu-id="c418a-142">String Data Type</span></span>](../../../../visual-basic/language-reference/data-types/string-data-type.md)
