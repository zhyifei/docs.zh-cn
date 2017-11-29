---
title: "如何：将字符串与模式相匹配 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 83433bdb41df0ce40d0979f3f44603f10ba1c7d5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-match-a-string-against-a-pattern-visual-basic"></a><span data-ttu-id="f7d13-102">如何：将字符串与模式相匹配 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f7d13-102">How to: Match a String against a Pattern (Visual Basic)</span></span>
<span data-ttu-id="f7d13-103">如果你想要找出的表达式[字符串数据类型](../../../../visual-basic/language-reference/data-types/string-data-type.md)满足一种模式，则你可以使用[Like 运算符](../../../../visual-basic/language-reference/operators/like-operator.md)。</span><span class="sxs-lookup"><span data-stu-id="f7d13-103">If you want to find out if an expression of the [String Data Type](../../../../visual-basic/language-reference/data-types/string-data-type.md) satisfies a pattern, then you can use the [Like Operator](../../../../visual-basic/language-reference/operators/like-operator.md).</span></span>  
  
 <span data-ttu-id="f7d13-104">`Like`采用两个操作数。</span><span class="sxs-lookup"><span data-stu-id="f7d13-104">`Like` takes two operands.</span></span> <span data-ttu-id="f7d13-105">左的操作数是字符串表达式和右操作数是一个包含要用于匹配的模式字符串。</span><span class="sxs-lookup"><span data-stu-id="f7d13-105">The left operand is a string expression, and the right operand is a string containing the pattern to be used for matching.</span></span> <span data-ttu-id="f7d13-106">`Like`返回`Boolean`值，该值指示字符串表达式是否满足模式。</span><span class="sxs-lookup"><span data-stu-id="f7d13-106">`Like` returns a `Boolean` value indicating whether the string expression satisfies the pattern.</span></span>  
  
 <span data-ttu-id="f7d13-107">你可以匹配字符串表达式针对特定的字符、 通配符、 字符列表或字符范围中的每个字符。</span><span class="sxs-lookup"><span data-stu-id="f7d13-107">You can match each character in the string expression against a specific character, a wildcard character, a character list, or a character range.</span></span> <span data-ttu-id="f7d13-108">模式字符串中的规范的位置对应的字符串表达式中要匹配的字符的位置。</span><span class="sxs-lookup"><span data-stu-id="f7d13-108">The positions of the specifications in the pattern string correspond to the positions of the characters to be matched in the string expression.</span></span>  
  
### <a name="to-match-a-character-in-the-string-expression-against-a-specific-character"></a><span data-ttu-id="f7d13-109">针对特定的字符的字符串表达式中的字符相匹配</span><span class="sxs-lookup"><span data-stu-id="f7d13-109">To match a character in the string expression against a specific character</span></span>  
  
-   <span data-ttu-id="f7d13-110">特定的字符将直接放在模式字符串。</span><span class="sxs-lookup"><span data-stu-id="f7d13-110">Put the specific character directly in the pattern string.</span></span> <span data-ttu-id="f7d13-111">某些特殊字符必须括在方括号中 (`[ ]`)。</span><span class="sxs-lookup"><span data-stu-id="f7d13-111">Certain special characters must be enclosed in brackets (`[ ]`).</span></span> <span data-ttu-id="f7d13-112">有关详细信息，请参阅[Like 运算符](../../../../visual-basic/language-reference/operators/like-operator.md)。</span><span class="sxs-lookup"><span data-stu-id="f7d13-112">For more information, see [Like Operator](../../../../visual-basic/language-reference/operators/like-operator.md).</span></span>  
  
     <span data-ttu-id="f7d13-113">下面的示例测试是否`myString`只包含单个字符`H`。</span><span class="sxs-lookup"><span data-stu-id="f7d13-113">The following example tests whether `myString` consists exactly of the single character `H`.</span></span>  
  
     [!code-vb[VbVbalrOperators#70](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-match-a-string-against-a-pattern_1.vb)]  
  
### <a name="to-match-a-character-in-the-string-expression-against-a-wildcard-character"></a><span data-ttu-id="f7d13-114">在对通配符字符的字符串表达式中的字符相匹配</span><span class="sxs-lookup"><span data-stu-id="f7d13-114">To match a character in the string expression against a wildcard character</span></span>  
  
-   <span data-ttu-id="f7d13-115">将问号 (`?`) 中的模式字符串。</span><span class="sxs-lookup"><span data-stu-id="f7d13-115">Put a question mark (`?`) in the pattern string.</span></span> <span data-ttu-id="f7d13-116">此位置中的任何有效字符可以成功匹配。</span><span class="sxs-lookup"><span data-stu-id="f7d13-116">Any valid character in this position makes a successful match.</span></span>  
  
     <span data-ttu-id="f7d13-117">下面的示例测试是否`myString`包含的单个字符`W`跟恰好两个字符的任何值。</span><span class="sxs-lookup"><span data-stu-id="f7d13-117">The following example tests whether `myString` consists of the single character `W` followed by exactly two characters of any values.</span></span>  
  
     [!code-vb[VbVbalrOperators#71](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-match-a-string-against-a-pattern_2.vb)]  
  
### <a name="to-match-a-character-in-the-string-expression-against-a-list-of-characters"></a><span data-ttu-id="f7d13-118">根据列表的字符的字符串表达式中的字符相匹配</span><span class="sxs-lookup"><span data-stu-id="f7d13-118">To match a character in the string expression against a list of characters</span></span>  
  
-   <span data-ttu-id="f7d13-119">将括号放 (`[ ]`) 中的模式字符串，并将字符的列表放括号内。</span><span class="sxs-lookup"><span data-stu-id="f7d13-119">Put brackets (`[ ]`) in the pattern string, and inside the brackets put the list of characters.</span></span> <span data-ttu-id="f7d13-120">不要用逗号或任何其他分隔符分隔字符。</span><span class="sxs-lookup"><span data-stu-id="f7d13-120">Do not separate the characters with commas or any other separator.</span></span> <span data-ttu-id="f7d13-121">在列表中的任何单个字符可成功匹配。</span><span class="sxs-lookup"><span data-stu-id="f7d13-121">Any single character in the list makes a successful match.</span></span>  
  
     <span data-ttu-id="f7d13-122">下面的示例测试是否`myString`包含任何有效字符后跟字符中恰好有一个`A`， `C`，或`E`。</span><span class="sxs-lookup"><span data-stu-id="f7d13-122">The following example tests whether `myString` consists of any valid character followed by exactly one of the characters `A`, `C`, or `E`.</span></span>  
  
     [!code-vb[VbVbalrOperators#72](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-match-a-string-against-a-pattern_3.vb)]  
  
     <span data-ttu-id="f7d13-123">请注意，此匹配区分大小写。</span><span class="sxs-lookup"><span data-stu-id="f7d13-123">Note that this match is case-sensitive.</span></span>  
  
### <a name="to-match-a-character-in-the-string-expression-against-a-range-of-characters"></a><span data-ttu-id="f7d13-124">在针对某一范围的字符的字符串表达式中的字符相匹配</span><span class="sxs-lookup"><span data-stu-id="f7d13-124">To match a character in the string expression against a range of characters</span></span>  
  
-   <span data-ttu-id="f7d13-125">将括号放 (`[ ]`) 以连字符分隔模式字符串中和 put 的最低和最高的字符范围中括号内，(`–`)。</span><span class="sxs-lookup"><span data-stu-id="f7d13-125">Put brackets (`[ ]`) in the pattern string, and inside the brackets put the lowest and highest characters in the range, separated by a hyphen (`–`).</span></span> <span data-ttu-id="f7d13-126">范围内的任何单个字符可成功匹配。</span><span class="sxs-lookup"><span data-stu-id="f7d13-126">Any single character within the range makes a successful match.</span></span>  
  
     <span data-ttu-id="f7d13-127">下面的示例测试是否`myString`字符组成`num`恰好有一个字符后跟`i`， `j`， `k`， `l`， `m`，或`n`。</span><span class="sxs-lookup"><span data-stu-id="f7d13-127">The following example tests whether `myString` consists of the characters `num` followed by exactly one of the characters `i`, `j`, `k`, `l`, `m`, or `n`.</span></span>  
  
     [!code-vb[VbVbalrOperators#73](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-match-a-string-against-a-pattern_4.vb)]  
  
     <span data-ttu-id="f7d13-128">请注意，此匹配区分大小写。</span><span class="sxs-lookup"><span data-stu-id="f7d13-128">Note that this match is case-sensitive.</span></span>  
  
## <a name="matching-empty-strings"></a><span data-ttu-id="f7d13-129">匹配空字符串</span><span class="sxs-lookup"><span data-stu-id="f7d13-129">Matching Empty Strings</span></span>  
 <span data-ttu-id="f7d13-130">`Like`将序列`[]`为零长度字符串 (`""`)。</span><span class="sxs-lookup"><span data-stu-id="f7d13-130">`Like` treats the sequence `[]` as a zero-length string (`""`).</span></span> <span data-ttu-id="f7d13-131">你可以使用`[]`来测试是否将整个字符串表达式为空，但不能使用它来测试是否为空字符串表达式中的特定位置。</span><span class="sxs-lookup"><span data-stu-id="f7d13-131">You can use `[]` to test whether the entire string expression is empty, but you cannot use it to test if a particular position in the string expression is empty.</span></span> <span data-ttu-id="f7d13-132">如果为空的位置是另一种需要对其进行，你可以使用测试`Like`不止一次。</span><span class="sxs-lookup"><span data-stu-id="f7d13-132">If an empty position is one of the options you need to test for, you can use `Like` more than once.</span></span>  
  
#### <a name="to-match-a-character-in-the-string-expression-against-a-list-of-characters-or-no-character"></a><span data-ttu-id="f7d13-133">根据列表的字符或无任何字符的字符串表达式中的字符相匹配</span><span class="sxs-lookup"><span data-stu-id="f7d13-133">To match a character in the string expression against a list of characters or no character</span></span>  
  
1.  <span data-ttu-id="f7d13-134">调用`Like`两次上相同的运算符的字符串表达式，并使用连接的两个调用[或运算符](../../../../visual-basic/language-reference/operators/or-operator.md)或[OrElse 运算符](../../../../visual-basic/language-reference/operators/orelse-operator.md)。</span><span class="sxs-lookup"><span data-stu-id="f7d13-134">Call the `Like` operator twice on the same string expression, and connect the two calls with either the [Or Operator](../../../../visual-basic/language-reference/operators/or-operator.md) or the [OrElse Operator](../../../../visual-basic/language-reference/operators/orelse-operator.md).</span></span>  
  
2.  <span data-ttu-id="f7d13-135">第一个的模式字符串中`Like`子句，包括字符列表，用括号括起来 (`[ ]`)。</span><span class="sxs-lookup"><span data-stu-id="f7d13-135">In the pattern string for the first `Like` clause, include the character list, enclosed in brackets (`[ ]`).</span></span>  
  
3.  <span data-ttu-id="f7d13-136">第二个模式字符串中`Like`子句，不要将放在任何字符的位置问题。</span><span class="sxs-lookup"><span data-stu-id="f7d13-136">In the pattern string for the second `Like` clause, do not put any character at the position in question.</span></span>  
  
     <span data-ttu-id="f7d13-137">下面的示例测试七位数电话号码`phoneNum`为 3 个数字后, 跟一个空格，连字符 (`–`)，一段时间 (`.`)，或任何字符后, 跟 4 个数字。</span><span class="sxs-lookup"><span data-stu-id="f7d13-137">The following example tests the seven-digit telephone number `phoneNum` for exactly three numeric digits, followed by a space, a hyphen (`–`), a period (`.`), or no character at all, followed by exactly four numeric digits.</span></span>  
  
     [!code-vb[VbVbalrOperators#74](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-match-a-string-against-a-pattern_5.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="f7d13-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f7d13-138">See Also</span></span>  
 [<span data-ttu-id="f7d13-139">比较运算符</span><span class="sxs-lookup"><span data-stu-id="f7d13-139">Comparison Operators</span></span>](../../../../visual-basic/language-reference/operators/comparison-operators.md)  
 [<span data-ttu-id="f7d13-140">运算符和表达式</span><span class="sxs-lookup"><span data-stu-id="f7d13-140">Operators and Expressions</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)  
 [<span data-ttu-id="f7d13-141">Like 运算符</span><span class="sxs-lookup"><span data-stu-id="f7d13-141">Like Operator</span></span>](../../../../visual-basic/language-reference/operators/like-operator.md)  
 [<span data-ttu-id="f7d13-142">String 数据类型</span><span class="sxs-lookup"><span data-stu-id="f7d13-142">String Data Type</span></span>](../../../../visual-basic/language-reference/data-types/string-data-type.md)
