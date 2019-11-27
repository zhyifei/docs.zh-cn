---
title: 如何：将字符串与模式相匹配
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
ms.openlocfilehash: 49328a72c2cff78b8fe13ca73209d224495ad7a1
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343638"
---
# <a name="how-to-match-a-string-against-a-pattern-visual-basic"></a><span data-ttu-id="0b141-102">如何：将字符串与模式相匹配 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0b141-102">How to: Match a String against a Pattern (Visual Basic)</span></span>

<span data-ttu-id="0b141-103">如果要了解[字符串数据类型](../../../../visual-basic/language-reference/data-types/string-data-type.md)的表达式是否满足模式，则可以使用[Like 运算符](../../../../visual-basic/language-reference/operators/like-operator.md)。</span><span class="sxs-lookup"><span data-stu-id="0b141-103">If you want to find out if an expression of the [String Data Type](../../../../visual-basic/language-reference/data-types/string-data-type.md) satisfies a pattern, then you can use the [Like Operator](../../../../visual-basic/language-reference/operators/like-operator.md).</span></span>

<span data-ttu-id="0b141-104">`Like` 采用两个操作数。</span><span class="sxs-lookup"><span data-stu-id="0b141-104">`Like` takes two operands.</span></span> <span data-ttu-id="0b141-105">左操作数是一个字符串表达式，右操作数是包含要用于匹配的模式的字符串。</span><span class="sxs-lookup"><span data-stu-id="0b141-105">The left operand is a string expression, and the right operand is a string containing the pattern to be used for matching.</span></span> <span data-ttu-id="0b141-106">`Like` 返回一个 `Boolean` 值，该值指示字符串表达式是否满足此模式。</span><span class="sxs-lookup"><span data-stu-id="0b141-106">`Like` returns a `Boolean` value indicating whether the string expression satisfies the pattern.</span></span>

<span data-ttu-id="0b141-107">可以将字符串表达式中的每个字符与特定字符、通配符、字符列表或字符范围匹配。</span><span class="sxs-lookup"><span data-stu-id="0b141-107">You can match each character in the string expression against a specific character, a wildcard character, a character list, or a character range.</span></span> <span data-ttu-id="0b141-108">模式字符串中规范的位置与字符串表达式中要匹配的字符的位置相对应。</span><span class="sxs-lookup"><span data-stu-id="0b141-108">The positions of the specifications in the pattern string correspond to the positions of the characters to be matched in the string expression.</span></span>

## <a name="to-match-a-character-in-the-string-expression-against-a-specific-character"></a><span data-ttu-id="0b141-109">根据特定字符匹配字符串表达式中的字符</span><span class="sxs-lookup"><span data-stu-id="0b141-109">To match a character in the string expression against a specific character</span></span>

<span data-ttu-id="0b141-110">将特定字符直接放置在模式字符串中。</span><span class="sxs-lookup"><span data-stu-id="0b141-110">Put the specific character directly in the pattern string.</span></span> <span data-ttu-id="0b141-111">某些特殊字符必须用方括号（`[ ]`）括起来。</span><span class="sxs-lookup"><span data-stu-id="0b141-111">Certain special characters must be enclosed in brackets (`[ ]`).</span></span> <span data-ttu-id="0b141-112">有关详细信息，请参阅[Like 运算符](../../../../visual-basic/language-reference/operators/like-operator.md)。</span><span class="sxs-lookup"><span data-stu-id="0b141-112">For more information, see [Like Operator](../../../../visual-basic/language-reference/operators/like-operator.md).</span></span>

<span data-ttu-id="0b141-113">下面的示例测试 `myString` 是否只包含单个字符 `H`。</span><span class="sxs-lookup"><span data-stu-id="0b141-113">The following example tests whether `myString` consists exactly of the single character `H`.</span></span>

[!code-vb[VbVbalrOperators#70](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#70)]

## <a name="to-match-a-character-in-the-string-expression-against-a-wildcard-character"></a><span data-ttu-id="0b141-114">将字符串表达式中的字符与通配符匹配</span><span class="sxs-lookup"><span data-stu-id="0b141-114">To match a character in the string expression against a wildcard character</span></span>

<span data-ttu-id="0b141-115">在模式字符串中放置一个问号（`?`）。</span><span class="sxs-lookup"><span data-stu-id="0b141-115">Put a question mark (`?`) in the pattern string.</span></span> <span data-ttu-id="0b141-116">此位置中的任何有效字符都使匹配成功。</span><span class="sxs-lookup"><span data-stu-id="0b141-116">Any valid character in this position makes a successful match.</span></span>

<span data-ttu-id="0b141-117">下面的示例测试 `myString` 是否包含单个字符 `W` 后跟任意值的两个字符。</span><span class="sxs-lookup"><span data-stu-id="0b141-117">The following example tests whether `myString` consists of the single character `W` followed by exactly two characters of any values.</span></span>

[!code-vb[VbVbalrOperators#71](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#71)]

## <a name="to-match-a-character-in-the-string-expression-against-a-list-of-characters"></a><span data-ttu-id="0b141-118">根据字符列表匹配字符串表达式中的字符</span><span class="sxs-lookup"><span data-stu-id="0b141-118">To match a character in the string expression against a list of characters</span></span>

<span data-ttu-id="0b141-119">将方括号（`[ ]`）放在模式字符串中，并将字符列表放在括号内。</span><span class="sxs-lookup"><span data-stu-id="0b141-119">Put brackets (`[ ]`) in the pattern string, and inside the brackets put the list of characters.</span></span> <span data-ttu-id="0b141-120">不要将字符与逗号或任何其他分隔符分隔开。</span><span class="sxs-lookup"><span data-stu-id="0b141-120">Do not separate the characters with commas or any other separator.</span></span> <span data-ttu-id="0b141-121">列表中的任何单个字符均可成功匹配。</span><span class="sxs-lookup"><span data-stu-id="0b141-121">Any single character in the list makes a successful match.</span></span>

<span data-ttu-id="0b141-122">下面的示例测试 `myString` 是否包含后面紧跟一个字符 `A`、`C`或 `E`的任何有效字符。</span><span class="sxs-lookup"><span data-stu-id="0b141-122">The following example tests whether `myString` consists of any valid character followed by exactly one of the characters `A`, `C`, or `E`.</span></span>

[!code-vb[VbVbalrOperators#72](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#72)]

<span data-ttu-id="0b141-123">请注意，此匹配区分大小写。</span><span class="sxs-lookup"><span data-stu-id="0b141-123">Note that this match is case-sensitive.</span></span>

## <a name="to-match-a-character-in-the-string-expression-against-a-range-of-characters"></a><span data-ttu-id="0b141-124">将字符串表达式中的字符与一系列字符匹配</span><span class="sxs-lookup"><span data-stu-id="0b141-124">To match a character in the string expression against a range of characters</span></span>

<span data-ttu-id="0b141-125">在模式字符串中放置方括号（`[ ]`），并在括号内放入范围中的最小字符和最大字符，并用连字符（`–`）分隔。</span><span class="sxs-lookup"><span data-stu-id="0b141-125">Put brackets (`[ ]`) in the pattern string, and inside the brackets put the lowest and highest characters in the range, separated by a hyphen (`–`).</span></span> <span data-ttu-id="0b141-126">范围内的任何单个字符都使匹配成功。</span><span class="sxs-lookup"><span data-stu-id="0b141-126">Any single character within the range makes a successful match.</span></span>

<span data-ttu-id="0b141-127">下面的示例测试 `myString` 是否包含字符，`num` 后跟 `i`、`j`、`k`、`l`、`m`或 `n`中的一个字符。</span><span class="sxs-lookup"><span data-stu-id="0b141-127">The following example tests whether `myString` consists of the characters `num` followed by exactly one of the characters `i`, `j`, `k`, `l`, `m`, or `n`.</span></span>

[!code-vb[VbVbalrOperators#73](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#73)]

<span data-ttu-id="0b141-128">请注意，此匹配区分大小写。</span><span class="sxs-lookup"><span data-stu-id="0b141-128">Note that this match is case-sensitive.</span></span>

## <a name="matching-empty-strings"></a><span data-ttu-id="0b141-129">匹配的空字符串</span><span class="sxs-lookup"><span data-stu-id="0b141-129">Matching Empty Strings</span></span>

<span data-ttu-id="0b141-130">`Like` 将序列 `[]` 视为长度为零的字符串（`""`）。</span><span class="sxs-lookup"><span data-stu-id="0b141-130">`Like` treats the sequence `[]` as a zero-length string (`""`).</span></span> <span data-ttu-id="0b141-131">您可以使用 `[]` 来测试整个字符串表达式是否为空，但您不能使用它来测试字符串表达式中的特定位置是否为空。</span><span class="sxs-lookup"><span data-stu-id="0b141-131">You can use `[]` to test whether the entire string expression is empty, but you cannot use it to test if a particular position in the string expression is empty.</span></span> <span data-ttu-id="0b141-132">如果空位置是需要测试的选项之一，则可以多次使用 `Like`。</span><span class="sxs-lookup"><span data-stu-id="0b141-132">If an empty position is one of the options you need to test for, you can use `Like` more than once.</span></span>

### <a name="to-match-a-character-in-the-string-expression-against-a-list-of-characters-or-no-character"></a><span data-ttu-id="0b141-133">将字符串表达式中的字符与字符或字符列表匹配</span><span class="sxs-lookup"><span data-stu-id="0b141-133">To match a character in the string expression against a list of characters or no character</span></span>

1. <span data-ttu-id="0b141-134">在同一字符串表达式上两次调用 `Like` 运算符，并将两个调用连接到[或运算符](../../../../visual-basic/language-reference/operators/or-operator.md)或[OrElse 运算符](../../../../visual-basic/language-reference/operators/orelse-operator.md)。</span><span class="sxs-lookup"><span data-stu-id="0b141-134">Call the `Like` operator twice on the same string expression, and connect the two calls with either the [Or Operator](../../../../visual-basic/language-reference/operators/or-operator.md) or the [OrElse Operator](../../../../visual-basic/language-reference/operators/orelse-operator.md).</span></span>

2. <span data-ttu-id="0b141-135">在第一个 `Like` 子句的模式字符串中，包含用方括号（`[ ]`）括起来的字符列表。</span><span class="sxs-lookup"><span data-stu-id="0b141-135">In the pattern string for the first `Like` clause, include the character list, enclosed in brackets (`[ ]`).</span></span>

3. <span data-ttu-id="0b141-136">在第二个 `Like` 子句的模式字符串中，不要将任何字符置于相关位置。</span><span class="sxs-lookup"><span data-stu-id="0b141-136">In the pattern string for the second `Like` clause, do not put any character at the position in question.</span></span>

    <span data-ttu-id="0b141-137">下面的示例测试七位数的电话号码，该号码只 `phoneNum` 三个数字，后跟空格、连字符（`–`）、句点（`.`）或不包含任何字符，然后再后跟四个数字。</span><span class="sxs-lookup"><span data-stu-id="0b141-137">The following example tests the seven-digit telephone number `phoneNum` for exactly three numeric digits, followed by a space, a hyphen (`–`), a period (`.`), or no character at all, followed by exactly four numeric digits.</span></span>

    [!code-vb[VbVbalrOperators#74](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#74)]

## <a name="see-also"></a><span data-ttu-id="0b141-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0b141-138">See also</span></span>

- [<span data-ttu-id="0b141-139">比较运算符</span><span class="sxs-lookup"><span data-stu-id="0b141-139">Comparison Operators</span></span>](../../../../visual-basic/language-reference/operators/comparison-operators.md)
- [<span data-ttu-id="0b141-140">运算符和表达式</span><span class="sxs-lookup"><span data-stu-id="0b141-140">Operators and Expressions</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
- [<span data-ttu-id="0b141-141">Like 运算符</span><span class="sxs-lookup"><span data-stu-id="0b141-141">Like Operator</span></span>](../../../../visual-basic/language-reference/operators/like-operator.md)
- [<span data-ttu-id="0b141-142">String 数据类型</span><span class="sxs-lookup"><span data-stu-id="0b141-142">String Data Type</span></span>](../../../../visual-basic/language-reference/data-types/string-data-type.md)
