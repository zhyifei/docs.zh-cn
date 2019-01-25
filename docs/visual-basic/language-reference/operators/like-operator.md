---
title: Like 运算符 (Visual Basic)
ms.date: 07/20/2015
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
ms.openlocfilehash: b1621131b3f5e4669eb637c054be1548597cf252
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54703258"
---
# <a name="like-operator-visual-basic"></a><span data-ttu-id="b970f-102">Like 运算符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b970f-102">Like Operator (Visual Basic)</span></span>
<span data-ttu-id="b970f-103">将字符串与模式进行比较。</span><span class="sxs-lookup"><span data-stu-id="b970f-103">Compares a string against a pattern.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b970f-104">语法</span><span class="sxs-lookup"><span data-stu-id="b970f-104">Syntax</span></span>  
  
```  
result = string Like pattern  
```  
  
## <a name="parts"></a><span data-ttu-id="b970f-105">部件</span><span class="sxs-lookup"><span data-stu-id="b970f-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="b970f-106">必需。</span><span class="sxs-lookup"><span data-stu-id="b970f-106">Required.</span></span> <span data-ttu-id="b970f-107">任何`Boolean`变量。</span><span class="sxs-lookup"><span data-stu-id="b970f-107">Any `Boolean` variable.</span></span> <span data-ttu-id="b970f-108">结果是`Boolean`值，该值指示是否`string`满足`pattern`。</span><span class="sxs-lookup"><span data-stu-id="b970f-108">The result is a `Boolean` value indicating whether or not the `string` satisfies the `pattern`.</span></span>  
  
 `string`  
 <span data-ttu-id="b970f-109">必需。</span><span class="sxs-lookup"><span data-stu-id="b970f-109">Required.</span></span> <span data-ttu-id="b970f-110">任何 `String` 表达式。</span><span class="sxs-lookup"><span data-stu-id="b970f-110">Any `String` expression.</span></span>  
  
 `pattern`  
 <span data-ttu-id="b970f-111">必需。</span><span class="sxs-lookup"><span data-stu-id="b970f-111">Required.</span></span> <span data-ttu-id="b970f-112">任何`String`符合"备注。"中所述的模式匹配约定的表达式</span><span class="sxs-lookup"><span data-stu-id="b970f-112">Any `String` expression conforming to the pattern-matching conventions described in "Remarks."</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b970f-113">备注</span><span class="sxs-lookup"><span data-stu-id="b970f-113">Remarks</span></span>  
 <span data-ttu-id="b970f-114">如果中的值`string`满足中包含的模式`pattern`，`result`是`True`。</span><span class="sxs-lookup"><span data-stu-id="b970f-114">If the value in `string` satisfies the pattern contained in `pattern`, `result` is `True`.</span></span> <span data-ttu-id="b970f-115">如果字符串不符合该模式中，`result`是`False`。</span><span class="sxs-lookup"><span data-stu-id="b970f-115">If the string does not satisfy the pattern, `result` is `False`.</span></span> <span data-ttu-id="b970f-116">如果这两个`string`并`pattern`都是空字符串，其结果是`True`。</span><span class="sxs-lookup"><span data-stu-id="b970f-116">If both `string` and `pattern` are empty strings, the result is `True`.</span></span>  
  
## <a name="comparison-method"></a><span data-ttu-id="b970f-117">比较方法</span><span class="sxs-lookup"><span data-stu-id="b970f-117">Comparison Method</span></span>  
 <span data-ttu-id="b970f-118">行为`Like`取决于运算符[Option 比较语句](../../../visual-basic/language-reference/statements/option-compare-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="b970f-118">The behavior of the `Like` operator depends on the [Option Compare Statement](../../../visual-basic/language-reference/statements/option-compare-statement.md).</span></span> <span data-ttu-id="b970f-119">每个源文件的默认字符串比较方法是`Option Compare Binary`。</span><span class="sxs-lookup"><span data-stu-id="b970f-119">The default string comparison method for each source file is `Option Compare Binary`.</span></span>  
  
## <a name="pattern-options"></a><span data-ttu-id="b970f-120">模式选项</span><span class="sxs-lookup"><span data-stu-id="b970f-120">Pattern Options</span></span>  
 <span data-ttu-id="b970f-121">内置的模式匹配的字符串比较提供的多用途工具。</span><span class="sxs-lookup"><span data-stu-id="b970f-121">Built-in pattern matching provides a versatile tool for string comparisons.</span></span> <span data-ttu-id="b970f-122">模式匹配功能，可以与中的每个字符匹配`string`针对特定字符、 通配符字符、 字符列表或字符范围。</span><span class="sxs-lookup"><span data-stu-id="b970f-122">The pattern-matching features allow you to match each character in `string` against a specific character, a wildcard character, a character list, or a character range.</span></span> <span data-ttu-id="b970f-123">下表显示了在允许的字符数`pattern`，它们的匹配。</span><span class="sxs-lookup"><span data-stu-id="b970f-123">The following table shows the characters allowed in `pattern` and what they match.</span></span>  
  
|<span data-ttu-id="b970f-124">中的字符 `pattern`</span><span class="sxs-lookup"><span data-stu-id="b970f-124">Characters in `pattern`</span></span>|<span data-ttu-id="b970f-125">中的匹配项 `string`</span><span class="sxs-lookup"><span data-stu-id="b970f-125">Matches in `string`</span></span>|  
|-----------------------------|-------------------------|  
|`?`|<span data-ttu-id="b970f-126">任何单个字符</span><span class="sxs-lookup"><span data-stu-id="b970f-126">Any single character</span></span>|  
|`*`|<span data-ttu-id="b970f-127">零个或多个字符</span><span class="sxs-lookup"><span data-stu-id="b970f-127">Zero or more characters</span></span>|  
|`#`|<span data-ttu-id="b970f-128">任何单个数字 (0 – 9)</span><span class="sxs-lookup"><span data-stu-id="b970f-128">Any single digit (0–9)</span></span>|  
|`[charlist]`|<span data-ttu-id="b970f-129">中的任何单个字符 `charlist`</span><span class="sxs-lookup"><span data-stu-id="b970f-129">Any single character in `charlist`</span></span>|  
|`[!charlist]`|<span data-ttu-id="b970f-130">未在任何单个字符 `charlist`</span><span class="sxs-lookup"><span data-stu-id="b970f-130">Any single character not in `charlist`</span></span>|  
  
## <a name="character-lists"></a><span data-ttu-id="b970f-131">字符列表</span><span class="sxs-lookup"><span data-stu-id="b970f-131">Character Lists</span></span>  
 <span data-ttu-id="b970f-132">一个或多个字符的组 (`charlist`) 括在方括号中 (`[ ]`) 可用于匹配任何单个字符`string`并且可以包含几乎任何字符代码，包括数字。</span><span class="sxs-lookup"><span data-stu-id="b970f-132">A group of one or more characters (`charlist`) enclosed in brackets (`[ ]`) can be used to match any single character in `string` and can include almost any character code, including digits.</span></span>  
  
 <span data-ttu-id="b970f-133">惊叹号 (`!`) 的开始处`charlist`意味着，如果中的字符以外的任意字符，将生成一个匹配`charlist`中找到`string`。</span><span class="sxs-lookup"><span data-stu-id="b970f-133">An exclamation point (`!`) at the beginning of `charlist` means that a match is made if any character except the characters in `charlist` is found in `string`.</span></span> <span data-ttu-id="b970f-134">在括号外使用，感叹点与匹配本身。</span><span class="sxs-lookup"><span data-stu-id="b970f-134">When used outside brackets, the exclamation point matches itself.</span></span>  
  
## <a name="special-characters"></a><span data-ttu-id="b970f-135">特殊字符</span><span class="sxs-lookup"><span data-stu-id="b970f-135">Special Characters</span></span>  
 <span data-ttu-id="b970f-136">若要匹配的特殊字符的左的括号 (`[`)，问号 (`?`)，数字符号 (`#`)，和星号 (`*`)，将它们括在方括号中。</span><span class="sxs-lookup"><span data-stu-id="b970f-136">To match the special characters left bracket (`[`), question mark (`?`), number sign (`#`), and asterisk (`*`), enclose them in brackets.</span></span> <span data-ttu-id="b970f-137">右方括号 (`]`) 不能用于组中与自身匹配，但它可以在组外使用，作为单个字符。</span><span class="sxs-lookup"><span data-stu-id="b970f-137">The right bracket (`]`) cannot be used within a group to match itself, but it can be used outside a group as an individual character.</span></span>  
  
 <span data-ttu-id="b970f-138">字符序列`[]`被视为一个零长度字符串 (`""`)。</span><span class="sxs-lookup"><span data-stu-id="b970f-138">The character sequence `[]` is considered a zero-length string (`""`).</span></span> <span data-ttu-id="b970f-139">但是，它不能是用方括号括起来的字符列表的一部分。</span><span class="sxs-lookup"><span data-stu-id="b970f-139">However, it cannot be part of a character list enclosed in brackets.</span></span> <span data-ttu-id="b970f-140">如果你想要检查是否中的位置`string`包含一个的一组字符或根本没有字符，可以使用`Like`两次。</span><span class="sxs-lookup"><span data-stu-id="b970f-140">If you want to check whether a position in `string` contains one of a group of characters or no character at all, you can use `Like` twice.</span></span> <span data-ttu-id="b970f-141">有关示例，请参见 [如何：字符串与模式相匹配](../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-match-a-string-against-a-pattern.md)。</span><span class="sxs-lookup"><span data-stu-id="b970f-141">For an example, see [How to: Match a String against a Pattern](../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-match-a-string-against-a-pattern.md).</span></span>  
  
## <a name="character-ranges"></a><span data-ttu-id="b970f-142">字符范围</span><span class="sxs-lookup"><span data-stu-id="b970f-142">Character Ranges</span></span>  
 <span data-ttu-id="b970f-143">使用连字符 (`–`) 来分隔的范围的下限和上限`charlist`可以指定一系列字符。</span><span class="sxs-lookup"><span data-stu-id="b970f-143">By using a hyphen (`–`) to separate the lower and upper bounds of the range, `charlist` can specify a range of characters.</span></span> <span data-ttu-id="b970f-144">例如，`[A–Z]`导致匹配项，如果相应的字符位置中`string`包含的范围内的任何字符`A`–`Z`，和`[!H–L]`结果匹配，如果相应的字符位置包含范围之外的任何字符`H`–`L`。</span><span class="sxs-lookup"><span data-stu-id="b970f-144">For example, `[A–Z]` results in a match if the corresponding character position in `string` contains any character within the range `A`–`Z`, and `[!H–L]` results in a match if the corresponding character position contains any character outside the range `H`–`L`.</span></span>  
  
 <span data-ttu-id="b970f-145">当指定的字符范围时，它们必须出现在升序排序顺序，即从最低到最高。</span><span class="sxs-lookup"><span data-stu-id="b970f-145">When you specify a range of characters, they must appear in ascending sort order, that is, from lowest to highest.</span></span> <span data-ttu-id="b970f-146">因此，`[A–Z]`是有效的模式，但`[Z–A]`不是。</span><span class="sxs-lookup"><span data-stu-id="b970f-146">Thus, `[A–Z]` is a valid pattern, but `[Z–A]` is not.</span></span>  
  
### <a name="multiple-character-ranges"></a><span data-ttu-id="b970f-147">多个字符范围</span><span class="sxs-lookup"><span data-stu-id="b970f-147">Multiple Character Ranges</span></span>  
 <span data-ttu-id="b970f-148">若要指定相同的字符位置的多个范围，请将它们放在不带分隔符相同的方括号内。</span><span class="sxs-lookup"><span data-stu-id="b970f-148">To specify multiple ranges for the same character position, put them within the same brackets without delimiters.</span></span> <span data-ttu-id="b970f-149">例如，`[A–CX–Z]`导致匹配项，如果相应的字符位置中`string`包含范围中的任意字符`A`–`C`或范围`X`–`Z`。</span><span class="sxs-lookup"><span data-stu-id="b970f-149">For example, `[A–CX–Z]` results in a match if the corresponding character position in `string` contains any character within either the range `A`–`C` or the range `X`–`Z`.</span></span>  
  
### <a name="usage-of-the-hyphen"></a><span data-ttu-id="b970f-150">连字符的使用情况</span><span class="sxs-lookup"><span data-stu-id="b970f-150">Usage of the Hyphen</span></span>  
 <span data-ttu-id="b970f-151">连字符 (`–`) 可以显示 （后感叹号，如果有） 的开头或末尾`charlist`来与自身匹配。</span><span class="sxs-lookup"><span data-stu-id="b970f-151">A hyphen (`–`) can appear either at the beginning (after an exclamation point, if any) or at the end of `charlist` to match itself.</span></span> <span data-ttu-id="b970f-152">在任何其他位置，连字符标识两侧的连字符字符分隔的字符的范围。</span><span class="sxs-lookup"><span data-stu-id="b970f-152">In any other location, the hyphen identifies a range of characters delimited by the characters on either side of the hyphen.</span></span>  
  
## <a name="collating-sequence"></a><span data-ttu-id="b970f-153">对序列进行排序</span><span class="sxs-lookup"><span data-stu-id="b970f-153">Collating Sequence</span></span>  
 <span data-ttu-id="b970f-154">指定范围的含义取决于在运行时，由确定排序字符`Option Compare`和运行这段代码的系统区域设置。</span><span class="sxs-lookup"><span data-stu-id="b970f-154">The meaning of a specified range depends on the character ordering at run time, as determined by `Option Compare` and the locale setting of the system the code is running on.</span></span> <span data-ttu-id="b970f-155">与`Option Compare Binary`，范围`[A–E]`匹配`A`， `B`， `C`， `D`，和`E`。</span><span class="sxs-lookup"><span data-stu-id="b970f-155">With `Option Compare Binary`, the range `[A–E]` matches `A`, `B`, `C`, `D`, and `E`.</span></span> <span data-ttu-id="b970f-156">与`Option Compare Text`，`[A–E]`匹配`A`， `a`， `À`， `à`， `B`， `b`， `C`， `c`， `D`， `d`， `E`，和`e`。</span><span class="sxs-lookup"><span data-stu-id="b970f-156">With `Option Compare Text`, `[A–E]` matches `A`, `a`, `À`, `à`, `B`, `b`, `C`, `c`, `D`, `d`, `E`, and `e`.</span></span> <span data-ttu-id="b970f-157">范围不匹配`Ê`或`ê`因为带重音符的字符排序在排序顺序中的非重音字符之后。</span><span class="sxs-lookup"><span data-stu-id="b970f-157">The range does not match `Ê` or `ê` because accented characters collate after unaccented characters in the sort order.</span></span>  
  
## <a name="digraph-characters"></a><span data-ttu-id="b970f-158">二合字母字符</span><span class="sxs-lookup"><span data-stu-id="b970f-158">Digraph Characters</span></span>  
 <span data-ttu-id="b970f-159">在某些语言中，有表示两个字符的字母字符。</span><span class="sxs-lookup"><span data-stu-id="b970f-159">In some languages, there are alphabetic characters that represent two separate characters.</span></span> <span data-ttu-id="b970f-160">例如，有几种语言使用字符`æ`来表示字符`a`和`e`它们一起出现。</span><span class="sxs-lookup"><span data-stu-id="b970f-160">For example, several languages use the character `æ` to represent the characters `a` and `e` when they appear together.</span></span> <span data-ttu-id="b970f-161">`Like`认为单个二合字母字符，并且这两个字符是等效的运算符。</span><span class="sxs-lookup"><span data-stu-id="b970f-161">The `Like` operator recognizes that the single digraph character and the two individual characters are equivalent.</span></span>  
  
 <span data-ttu-id="b970f-162">当系统区域设置中指定一种语言，使用二合字母字符时，出现在单个二合字母字符`pattern`或`string`匹配其他字符串中等效的两个字符序列。</span><span class="sxs-lookup"><span data-stu-id="b970f-162">When a language that uses a digraph character is specified in the system locale settings, an occurrence of the single digraph character in either `pattern` or `string` matches the equivalent two-character sequence in the other string.</span></span> <span data-ttu-id="b970f-163">同样中的有向图时会字符`pattern`括在方括号中 （本身，在列表中，或某个范围内） 匹配中等效的双字符序列`string`。</span><span class="sxs-lookup"><span data-stu-id="b970f-163">Similarly, a digraph character in `pattern` enclosed in brackets (by itself, in a list, or in a range) matches the equivalent two-character sequence in `string`.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="b970f-164">重载</span><span class="sxs-lookup"><span data-stu-id="b970f-164">Overloading</span></span>  
 <span data-ttu-id="b970f-165">`Like`运算符可以被*重载*，这意味着，某个类或结构可以重新定义其行为时，操作数的类或结构的类型。</span><span class="sxs-lookup"><span data-stu-id="b970f-165">The `Like` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="b970f-166">如果你的代码对此类的类或结构使用此运算符，请确保了解其被重新定义的行为。</span><span class="sxs-lookup"><span data-stu-id="b970f-166">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="b970f-167">有关详细信息，请参阅 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)。</span><span class="sxs-lookup"><span data-stu-id="b970f-167">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b970f-168">示例</span><span class="sxs-lookup"><span data-stu-id="b970f-168">Example</span></span>  
 <span data-ttu-id="b970f-169">此示例使用`Like`运算符来比较各种模式的字符串。</span><span class="sxs-lookup"><span data-stu-id="b970f-169">This example uses the `Like` operator to compare strings to various patterns.</span></span> <span data-ttu-id="b970f-170">结果进入`Boolean`变量，用于指示每个字符串是否满足模式的要求。</span><span class="sxs-lookup"><span data-stu-id="b970f-170">The results go into a `Boolean` variable indicating whether each string satisfies the pattern.</span></span>  
  
 [!code-vb[VbVbalrOperators#30](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/like-operator_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="b970f-171">请参阅</span><span class="sxs-lookup"><span data-stu-id="b970f-171">See also</span></span>
- <xref:Microsoft.VisualBasic.Strings.InStr%2A>
- <xref:Microsoft.VisualBasic.Strings.StrComp%2A>
- [<span data-ttu-id="b970f-172">比较运算符</span><span class="sxs-lookup"><span data-stu-id="b970f-172">Comparison Operators</span></span>](../../../visual-basic/language-reference/operators/comparison-operators.md)
- [<span data-ttu-id="b970f-173">Visual Basic 中的运算符优先级</span><span class="sxs-lookup"><span data-stu-id="b970f-173">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="b970f-174">按功能列出的运算符</span><span class="sxs-lookup"><span data-stu-id="b970f-174">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="b970f-175">Option Compare 语句</span><span class="sxs-lookup"><span data-stu-id="b970f-175">Option Compare Statement</span></span>](../../../visual-basic/language-reference/statements/option-compare-statement.md)
- [<span data-ttu-id="b970f-176">运算符和表达式</span><span class="sxs-lookup"><span data-stu-id="b970f-176">Operators and Expressions</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
- [<span data-ttu-id="b970f-177">如何：字符串与模式相匹配</span><span class="sxs-lookup"><span data-stu-id="b970f-177">How to: Match a String against a Pattern</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-match-a-string-against-a-pattern.md)
