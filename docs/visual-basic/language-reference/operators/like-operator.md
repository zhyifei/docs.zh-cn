---
title: "Like 运算符 (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- Like
- vb.Like
helpviewer_keywords:
- similar to
- pattern matching
- Like operator [Visual Basic]
- '? symbol, wildcard character'
- string comparison [Visual Basic], Like operator
- strings [Visual Basic], comparing
- comparison operators [Visual Basic]
- symbols, wildcard
- wildcards, Like operator
- strings [Visual Basic], matching
- string comparison [Visual Basic], sorting data
- data [Visual Basic], sorting
- text [Visual Basic], comparing
- operators [Visual Basic], pattern-matching
- data [Visual Basic], string comparisons
- string comparison [Visual Basic], Like operators
ms.assetid: 966283ec-80e2-4294-baa8-c75baff804f9
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ad5729515362bfd52b0c3b401f218a49f569726e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="like-operator-visual-basic"></a><span data-ttu-id="2ad14-102">Like 运算符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2ad14-102">Like Operator (Visual Basic)</span></span>
<span data-ttu-id="2ad14-103">将字符串与模式进行比较。</span><span class="sxs-lookup"><span data-stu-id="2ad14-103">Compares a string against a pattern.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ad14-104">语法</span><span class="sxs-lookup"><span data-stu-id="2ad14-104">Syntax</span></span>  
  
```  
result = string Like pattern  
```  
  
## <a name="parts"></a><span data-ttu-id="2ad14-105">部件</span><span class="sxs-lookup"><span data-stu-id="2ad14-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="2ad14-106">必需。</span><span class="sxs-lookup"><span data-stu-id="2ad14-106">Required.</span></span> <span data-ttu-id="2ad14-107">任何`Boolean`变量。</span><span class="sxs-lookup"><span data-stu-id="2ad14-107">Any `Boolean` variable.</span></span> <span data-ttu-id="2ad14-108">结果是`Boolean`值，该值指示是否`string`满足`pattern`。</span><span class="sxs-lookup"><span data-stu-id="2ad14-108">The result is a `Boolean` value indicating whether or not the `string` satisfies the `pattern`.</span></span>  
  
 `string`  
 <span data-ttu-id="2ad14-109">必需。</span><span class="sxs-lookup"><span data-stu-id="2ad14-109">Required.</span></span> <span data-ttu-id="2ad14-110">任何 `String` 表达式。</span><span class="sxs-lookup"><span data-stu-id="2ad14-110">Any `String` expression.</span></span>  
  
 `pattern`  
 <span data-ttu-id="2ad14-111">必需。</span><span class="sxs-lookup"><span data-stu-id="2ad14-111">Required.</span></span> <span data-ttu-id="2ad14-112">任何`String`符合"备注。"中所述的模式匹配的约定的表达式</span><span class="sxs-lookup"><span data-stu-id="2ad14-112">Any `String` expression conforming to the pattern-matching conventions described in "Remarks."</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2ad14-113">备注</span><span class="sxs-lookup"><span data-stu-id="2ad14-113">Remarks</span></span>  
 <span data-ttu-id="2ad14-114">如果中的值`string`满足中包含的模式`pattern`，`result`是`True`。</span><span class="sxs-lookup"><span data-stu-id="2ad14-114">If the value in `string` satisfies the pattern contained in `pattern`, `result` is `True`.</span></span> <span data-ttu-id="2ad14-115">如果字符串不符合该模式中，`result`是`False`。</span><span class="sxs-lookup"><span data-stu-id="2ad14-115">If the string does not satisfy the pattern, `result` is `False`.</span></span> <span data-ttu-id="2ad14-116">如果这两个`string`和`pattern`都是空字符串，则结果是`True`。</span><span class="sxs-lookup"><span data-stu-id="2ad14-116">If both `string` and `pattern` are empty strings, the result is `True`.</span></span>  
  
## <a name="comparison-method"></a><span data-ttu-id="2ad14-117">比较方法</span><span class="sxs-lookup"><span data-stu-id="2ad14-117">Comparison Method</span></span>  
 <span data-ttu-id="2ad14-118">行为`Like`取决于运算符[选项比较语句](../../../visual-basic/language-reference/statements/option-compare-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="2ad14-118">The behavior of the `Like` operator depends on the [Option Compare Statement](../../../visual-basic/language-reference/statements/option-compare-statement.md).</span></span> <span data-ttu-id="2ad14-119">每个源代码文件的默认字符串比较方法是`Option Compare Binary`。</span><span class="sxs-lookup"><span data-stu-id="2ad14-119">The default string comparison method for each source file is `Option Compare Binary`.</span></span>  
  
## <a name="pattern-options"></a><span data-ttu-id="2ad14-120">模式选项</span><span class="sxs-lookup"><span data-stu-id="2ad14-120">Pattern Options</span></span>  
 <span data-ttu-id="2ad14-121">内置的模式匹配的字符串比较提供通用工具。</span><span class="sxs-lookup"><span data-stu-id="2ad14-121">Built-in pattern matching provides a versatile tool for string comparisons.</span></span> <span data-ttu-id="2ad14-122">模式匹配功能可让你中的每个字符相匹配`string`针对特定的字符、 通配符、 字符列表或字符范围。</span><span class="sxs-lookup"><span data-stu-id="2ad14-122">The pattern-matching features allow you to match each character in `string` against a specific character, a wildcard character, a character list, or a character range.</span></span> <span data-ttu-id="2ad14-123">下表显示在允许的字符数`pattern`和它们的匹配。</span><span class="sxs-lookup"><span data-stu-id="2ad14-123">The following table shows the characters allowed in `pattern` and what they match.</span></span>  
  
|<span data-ttu-id="2ad14-124">中的字符`pattern`</span><span class="sxs-lookup"><span data-stu-id="2ad14-124">Characters in `pattern`</span></span>|<span data-ttu-id="2ad14-125">中的匹配项`string`</span><span class="sxs-lookup"><span data-stu-id="2ad14-125">Matches in `string`</span></span>|  
|-----------------------------|-------------------------|  
|`?`|<span data-ttu-id="2ad14-126">任何单个字符</span><span class="sxs-lookup"><span data-stu-id="2ad14-126">Any single character</span></span>|  
|`*`|<span data-ttu-id="2ad14-127">零个或多个字符</span><span class="sxs-lookup"><span data-stu-id="2ad14-127">Zero or more characters</span></span>|  
|`#`|<span data-ttu-id="2ad14-128">任何单个数字 (0-9)</span><span class="sxs-lookup"><span data-stu-id="2ad14-128">Any single digit (0–9)</span></span>|  
|`[charlist]`|<span data-ttu-id="2ad14-129">任何单个字符`charlist`</span><span class="sxs-lookup"><span data-stu-id="2ad14-129">Any single character in `charlist`</span></span>|  
|`[!charlist]`|<span data-ttu-id="2ad14-130">不在任何单个字符`charlist`</span><span class="sxs-lookup"><span data-stu-id="2ad14-130">Any single character not in `charlist`</span></span>|  
  
## <a name="character-lists"></a><span data-ttu-id="2ad14-131">字符列表</span><span class="sxs-lookup"><span data-stu-id="2ad14-131">Character Lists</span></span>  
 <span data-ttu-id="2ad14-132">一组的一个或多个字符 (`charlist`) 用括号括起来 (`[ ]`) 可以使用来匹配任何单个字符`string`并且可以包含几乎任何字符代码，包括数字。</span><span class="sxs-lookup"><span data-stu-id="2ad14-132">A group of one or more characters (`charlist`) enclosed in brackets (`[ ]`) can be used to match any single character in `string` and can include almost any character code, including digits.</span></span>  
  
 <span data-ttu-id="2ad14-133">感叹号 (`!`) 开头的`charlist`意味着，如果中的字符以外的任意字符，将生成一个匹配`charlist`中找到`string`。</span><span class="sxs-lookup"><span data-stu-id="2ad14-133">An exclamation point (`!`) at the beginning of `charlist` means that a match is made if any character except the characters in `charlist` is found in `string`.</span></span> <span data-ttu-id="2ad14-134">当使用方括号外面，感叹号匹配其本身。</span><span class="sxs-lookup"><span data-stu-id="2ad14-134">When used outside brackets, the exclamation point matches itself.</span></span>  
  
## <a name="special-characters"></a><span data-ttu-id="2ad14-135">特殊字符</span><span class="sxs-lookup"><span data-stu-id="2ad14-135">Special Characters</span></span>  
 <span data-ttu-id="2ad14-136">若要匹配该左的括号，特殊字符 (`[`)，问号 (`?`)，数字符号 (`#`)，和星号 (`*`)，将它们括在括号中。</span><span class="sxs-lookup"><span data-stu-id="2ad14-136">To match the special characters left bracket (`[`), question mark (`?`), number sign (`#`), and asterisk (`*`), enclose them in brackets.</span></span> <span data-ttu-id="2ad14-137">右括号 (`]`) 不能用于组中与自身匹配，但它作为单个字符可在组外。</span><span class="sxs-lookup"><span data-stu-id="2ad14-137">The right bracket (`]`) cannot be used within a group to match itself, but it can be used outside a group as an individual character.</span></span>  
  
 <span data-ttu-id="2ad14-138">字符序列`[]`被视为零长度字符串 (`""`)。</span><span class="sxs-lookup"><span data-stu-id="2ad14-138">The character sequence `[]` is considered a zero-length string (`""`).</span></span> <span data-ttu-id="2ad14-139">但是，它不能是括在方括号内的字符列表的一部分。</span><span class="sxs-lookup"><span data-stu-id="2ad14-139">However, it cannot be part of a character list enclosed in brackets.</span></span> <span data-ttu-id="2ad14-140">如果你想要检查是否中的位置`string`包含一个字符或根本没有字符的组，您可以使用`Like`两次。</span><span class="sxs-lookup"><span data-stu-id="2ad14-140">If you want to check whether a position in `string` contains one of a group of characters or no character at all, you can use `Like` twice.</span></span> <span data-ttu-id="2ad14-141">有关示例，请参阅[如何： 将字符串与模式相匹配](../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-match-a-string-against-a-pattern.md)。</span><span class="sxs-lookup"><span data-stu-id="2ad14-141">For an example, see [How to: Match a String against a Pattern](../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-match-a-string-against-a-pattern.md).</span></span>  
  
## <a name="character-ranges"></a><span data-ttu-id="2ad14-142">字符范围</span><span class="sxs-lookup"><span data-stu-id="2ad14-142">Character Ranges</span></span>  
 <span data-ttu-id="2ad14-143">通过使用连字符 (`–`) 来分隔的范围下限和上限`charlist`可以指定的字符范围。</span><span class="sxs-lookup"><span data-stu-id="2ad14-143">By using a hyphen (`–`) to separate the lower and upper bounds of the range, `charlist` can specify a range of characters.</span></span> <span data-ttu-id="2ad14-144">例如，`[A–Z]`导致匹配项，如果相应的字符位置中`string`包含范围内的任何字符`A`–`Z`，和`[!H–L]`导致匹配项，如果相应的字符位置包含范围以外的任何字符`H`–`L`。</span><span class="sxs-lookup"><span data-stu-id="2ad14-144">For example, `[A–Z]` results in a match if the corresponding character position in `string` contains any character within the range `A`–`Z`, and `[!H–L]` results in a match if the corresponding character position contains any character outside the range `H`–`L`.</span></span>  
  
 <span data-ttu-id="2ad14-145">在你指定的字符范围，它们必须显示以升序排序，即从最低到最高。</span><span class="sxs-lookup"><span data-stu-id="2ad14-145">When you specify a range of characters, they must appear in ascending sort order, that is, from lowest to highest.</span></span> <span data-ttu-id="2ad14-146">因此，`[A–Z]`是有效的模式，但`[Z–A]`不是。</span><span class="sxs-lookup"><span data-stu-id="2ad14-146">Thus, `[A–Z]` is a valid pattern, but `[Z–A]` is not.</span></span>  
  
### <a name="multiple-character-ranges"></a><span data-ttu-id="2ad14-147">多个字符范围</span><span class="sxs-lookup"><span data-stu-id="2ad14-147">Multiple Character Ranges</span></span>  
 <span data-ttu-id="2ad14-148">若要指定的相同的字符位置的多个范围，请将它们放置在而不用分隔符相同方括号内。</span><span class="sxs-lookup"><span data-stu-id="2ad14-148">To specify multiple ranges for the same character position, put them within the same brackets without delimiters.</span></span> <span data-ttu-id="2ad14-149">例如，`[A–CX–Z]`导致匹配项，如果相应的字符位置中`string`包含任一范围内的任何字符`A`–`C`或范围`X`–`Z`。</span><span class="sxs-lookup"><span data-stu-id="2ad14-149">For example, `[A–CX–Z]` results in a match if the corresponding character position in `string` contains any character within either the range `A`–`C` or the range `X`–`Z`.</span></span>  
  
### <a name="usage-of-the-hyphen"></a><span data-ttu-id="2ad14-150">该连字符的使用情况</span><span class="sxs-lookup"><span data-stu-id="2ad14-150">Usage of the Hyphen</span></span>  
 <span data-ttu-id="2ad14-151">连字符 (`–`) 可以出现在 （之后感叹号，如果有） 的开头或末尾`charlist`来与自身匹配。</span><span class="sxs-lookup"><span data-stu-id="2ad14-151">A hyphen (`–`) can appear either at the beginning (after an exclamation point, if any) or at the end of `charlist` to match itself.</span></span> <span data-ttu-id="2ad14-152">在任何其他位置，连字符标识由连字符的任何一侧的字符分隔的字符范围。</span><span class="sxs-lookup"><span data-stu-id="2ad14-152">In any other location, the hyphen identifies a range of characters delimited by the characters on either side of the hyphen.</span></span>  
  
## <a name="collating-sequence"></a><span data-ttu-id="2ad14-153">排序规则序列</span><span class="sxs-lookup"><span data-stu-id="2ad14-153">Collating Sequence</span></span>  
 <span data-ttu-id="2ad14-154">指定范围的含义取决于在运行时，所确定的那样排序的字符`Option``Compare`和系统的区域设置中正在运行代码。</span><span class="sxs-lookup"><span data-stu-id="2ad14-154">The meaning of a specified range depends on the character ordering at run time, as determined by `Option``Compare` and the locale setting of the system the code is running on.</span></span> <span data-ttu-id="2ad14-155">与`Option``Compare``Binary`，范围`[A–E]`匹配`A`， `B`， `C`， `D`，和`E`。</span><span class="sxs-lookup"><span data-stu-id="2ad14-155">With `Option``Compare``Binary`, the range `[A–E]` matches `A`, `B`, `C`, `D`, and `E`.</span></span> <span data-ttu-id="2ad14-156">与`Option``Compare``Text`，`[A–E]`匹配`A`， `a`， `À`， `à`， `B`， `b`， `C`， `c`， `D`， `d`， `E`，和`e`。</span><span class="sxs-lookup"><span data-stu-id="2ad14-156">With `Option``Compare``Text`, `[A–E]` matches `A`, `a`, `À`, `à`, `B`, `b`, `C`, `c`, `D`, `d`, `E`, and `e`.</span></span> <span data-ttu-id="2ad14-157">范围不匹配`Ê`或`ê`因为重音的字符 collate 在排序顺序中的非重音个字符。</span><span class="sxs-lookup"><span data-stu-id="2ad14-157">The range does not match `Ê` or `ê` because accented characters collate after unaccented characters in the sort order.</span></span>  
  
## <a name="digraph-characters"></a><span data-ttu-id="2ad14-158">二合字母字符</span><span class="sxs-lookup"><span data-stu-id="2ad14-158">Digraph Characters</span></span>  
 <span data-ttu-id="2ad14-159">在某些语言中，有一些表示两个单独的字符的字母字符。</span><span class="sxs-lookup"><span data-stu-id="2ad14-159">In some languages, there are alphabetic characters that represent two separate characters.</span></span> <span data-ttu-id="2ad14-160">例如，有几种语言使用字符`æ`来表示字符`a`和`e`它们一起出现。</span><span class="sxs-lookup"><span data-stu-id="2ad14-160">For example, several languages use the character `æ` to represent the characters `a` and `e` when they appear together.</span></span> <span data-ttu-id="2ad14-161">`Like`运算符认为是等效的单个二合字母字符与这两个字符。</span><span class="sxs-lookup"><span data-stu-id="2ad14-161">The `Like` operator recognizes that the single digraph character and the two individual characters are equivalent.</span></span>  
  
 <span data-ttu-id="2ad14-162">如果在系统区域设置中指定使用二合字母字符的语言、 中的单个二合字母字符的匹配项`pattern`或`string`匹配中另一个字符串等效的双字符序列。</span><span class="sxs-lookup"><span data-stu-id="2ad14-162">When a language that uses a digraph character is specified in the system locale settings, an occurrence of the single digraph character in either `pattern` or `string` matches the equivalent two-character sequence in the other string.</span></span> <span data-ttu-id="2ad14-163">同样中的二合字母字符`pattern`用方括号括起来 （本身，在列表中，或一系列） 匹配中等效的双字符序列`string`。</span><span class="sxs-lookup"><span data-stu-id="2ad14-163">Similarly, a digraph character in `pattern` enclosed in brackets (by itself, in a list, or in a range) matches the equivalent two-character sequence in `string`.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="2ad14-164">重载</span><span class="sxs-lookup"><span data-stu-id="2ad14-164">Overloading</span></span>  
 <span data-ttu-id="2ad14-165">`Like`运算符可以被*重载*，这意味着，一个类或结构可以重新定义其行为时，操作数的类或结构的类型。</span><span class="sxs-lookup"><span data-stu-id="2ad14-165">The `Like` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="2ad14-166">如果你的代码使用此运算符对这样的类或结构，请确保你了解其重新定义的行为。</span><span class="sxs-lookup"><span data-stu-id="2ad14-166">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="2ad14-167">有关详细信息，请参阅[运算符过程](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)。</span><span class="sxs-lookup"><span data-stu-id="2ad14-167">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="2ad14-168">示例</span><span class="sxs-lookup"><span data-stu-id="2ad14-168">Example</span></span>  
 <span data-ttu-id="2ad14-169">此示例使用`Like`运算符比较字符串转换为各种模式。</span><span class="sxs-lookup"><span data-stu-id="2ad14-169">This example uses the `Like` operator to compare strings to various patterns.</span></span> <span data-ttu-id="2ad14-170">结果进入`Boolean`变量，用于指示每个字符串是否满足模式。</span><span class="sxs-lookup"><span data-stu-id="2ad14-170">The results go into a `Boolean` variable indicating whether each string satisfies the pattern.</span></span>  
  
 [!code-vb[VbVbalrOperators#30](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/like-operator_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="2ad14-171">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2ad14-171">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Strings.InStr%2A>  
 <xref:Microsoft.VisualBasic.Strings.StrComp%2A>  
 [<span data-ttu-id="2ad14-172">比较运算符</span><span class="sxs-lookup"><span data-stu-id="2ad14-172">Comparison Operators</span></span>](../../../visual-basic/language-reference/operators/comparison-operators.md)  
 [<span data-ttu-id="2ad14-173">Visual Basic 中的运算符优先级</span><span class="sxs-lookup"><span data-stu-id="2ad14-173">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="2ad14-174">按功能列出的运算符</span><span class="sxs-lookup"><span data-stu-id="2ad14-174">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="2ad14-175">Option Compare 语句</span><span class="sxs-lookup"><span data-stu-id="2ad14-175">Option Compare Statement</span></span>](../../../visual-basic/language-reference/statements/option-compare-statement.md)  
 [<span data-ttu-id="2ad14-176">运算符和表达式</span><span class="sxs-lookup"><span data-stu-id="2ad14-176">Operators and Expressions</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)  
 [<span data-ttu-id="2ad14-177">如何：将字符串与模式相匹配</span><span class="sxs-lookup"><span data-stu-id="2ad14-177">How to: Match a String against a Pattern</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-match-a-string-against-a-pattern.md)
