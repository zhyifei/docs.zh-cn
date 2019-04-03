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
ms.openlocfilehash: 38e56b8c0ec6bab89052ee42a2cd9c24053c658e
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2019
ms.locfileid: "58835695"
---
# <a name="like-operator-visual-basic"></a><span data-ttu-id="eecca-102">Like 运算符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="eecca-102">Like Operator (Visual Basic)</span></span>
<span data-ttu-id="eecca-103">将字符串与模式进行比较。</span><span class="sxs-lookup"><span data-stu-id="eecca-103">Compares a string against a pattern.</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="eecca-104">`Like` .NET Core 和.NET Standard 项目中当前不支持运算符。</span><span class="sxs-lookup"><span data-stu-id="eecca-104">The `Like` operator is currently not supported in .NET Core and .NET Standard projects.</span></span>

## <a name="syntax"></a><span data-ttu-id="eecca-105">语法</span><span class="sxs-lookup"><span data-stu-id="eecca-105">Syntax</span></span>  
  
```  
result = string Like pattern  
```  
  
## <a name="parts"></a><span data-ttu-id="eecca-106">部件</span><span class="sxs-lookup"><span data-stu-id="eecca-106">Parts</span></span>  
 `result`  
 <span data-ttu-id="eecca-107">必需。</span><span class="sxs-lookup"><span data-stu-id="eecca-107">Required.</span></span> <span data-ttu-id="eecca-108">任何`Boolean`变量。</span><span class="sxs-lookup"><span data-stu-id="eecca-108">Any `Boolean` variable.</span></span> <span data-ttu-id="eecca-109">结果是`Boolean`值，该值指示是否`string`满足`pattern`。</span><span class="sxs-lookup"><span data-stu-id="eecca-109">The result is a `Boolean` value indicating whether or not the `string` satisfies the `pattern`.</span></span>  
  
 `string`  
 <span data-ttu-id="eecca-110">必需。</span><span class="sxs-lookup"><span data-stu-id="eecca-110">Required.</span></span> <span data-ttu-id="eecca-111">任何 `String` 表达式。</span><span class="sxs-lookup"><span data-stu-id="eecca-111">Any `String` expression.</span></span>  
  
 `pattern`  
 <span data-ttu-id="eecca-112">必需。</span><span class="sxs-lookup"><span data-stu-id="eecca-112">Required.</span></span> <span data-ttu-id="eecca-113">任何`String`符合"备注。"中所述的模式匹配约定的表达式</span><span class="sxs-lookup"><span data-stu-id="eecca-113">Any `String` expression conforming to the pattern-matching conventions described in "Remarks."</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="eecca-114">备注</span><span class="sxs-lookup"><span data-stu-id="eecca-114">Remarks</span></span>  
 <span data-ttu-id="eecca-115">如果中的值`string`满足中包含的模式`pattern`，`result`是`True`。</span><span class="sxs-lookup"><span data-stu-id="eecca-115">If the value in `string` satisfies the pattern contained in `pattern`, `result` is `True`.</span></span> <span data-ttu-id="eecca-116">如果字符串不符合该模式中，`result`是`False`。</span><span class="sxs-lookup"><span data-stu-id="eecca-116">If the string does not satisfy the pattern, `result` is `False`.</span></span> <span data-ttu-id="eecca-117">如果这两个`string`并`pattern`都是空字符串，其结果是`True`。</span><span class="sxs-lookup"><span data-stu-id="eecca-117">If both `string` and `pattern` are empty strings, the result is `True`.</span></span>  
  
## <a name="comparison-method"></a><span data-ttu-id="eecca-118">比较方法</span><span class="sxs-lookup"><span data-stu-id="eecca-118">Comparison Method</span></span>  
 <span data-ttu-id="eecca-119">行为`Like`取决于运算符[Option 比较语句](../../../visual-basic/language-reference/statements/option-compare-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="eecca-119">The behavior of the `Like` operator depends on the [Option Compare Statement](../../../visual-basic/language-reference/statements/option-compare-statement.md).</span></span> <span data-ttu-id="eecca-120">每个源文件的默认字符串比较方法是`Option Compare Binary`。</span><span class="sxs-lookup"><span data-stu-id="eecca-120">The default string comparison method for each source file is `Option Compare Binary`.</span></span>  
  
## <a name="pattern-options"></a><span data-ttu-id="eecca-121">模式选项</span><span class="sxs-lookup"><span data-stu-id="eecca-121">Pattern Options</span></span>  
 <span data-ttu-id="eecca-122">内置的模式匹配的字符串比较提供的多用途工具。</span><span class="sxs-lookup"><span data-stu-id="eecca-122">Built-in pattern matching provides a versatile tool for string comparisons.</span></span> <span data-ttu-id="eecca-123">模式匹配功能，可以与中的每个字符匹配`string`针对特定字符、 通配符字符、 字符列表或字符范围。</span><span class="sxs-lookup"><span data-stu-id="eecca-123">The pattern-matching features allow you to match each character in `string` against a specific character, a wildcard character, a character list, or a character range.</span></span> <span data-ttu-id="eecca-124">下表显示了在允许的字符数`pattern`，它们的匹配。</span><span class="sxs-lookup"><span data-stu-id="eecca-124">The following table shows the characters allowed in `pattern` and what they match.</span></span>  
  
|<span data-ttu-id="eecca-125">中的字符 `pattern`</span><span class="sxs-lookup"><span data-stu-id="eecca-125">Characters in `pattern`</span></span>|<span data-ttu-id="eecca-126">中的匹配项 `string`</span><span class="sxs-lookup"><span data-stu-id="eecca-126">Matches in `string`</span></span>|  
|-----------------------------|-------------------------|  
|`?`|<span data-ttu-id="eecca-127">任何单个字符</span><span class="sxs-lookup"><span data-stu-id="eecca-127">Any single character</span></span>|  
|`*`|<span data-ttu-id="eecca-128">零个或多个字符</span><span class="sxs-lookup"><span data-stu-id="eecca-128">Zero or more characters</span></span>|  
|`#`|<span data-ttu-id="eecca-129">任何单个数字 (0 – 9)</span><span class="sxs-lookup"><span data-stu-id="eecca-129">Any single digit (0–9)</span></span>|  
|`[charlist]`|<span data-ttu-id="eecca-130">中的任何单个字符 `charlist`</span><span class="sxs-lookup"><span data-stu-id="eecca-130">Any single character in `charlist`</span></span>|  
|`[!charlist]`|<span data-ttu-id="eecca-131">未在任何单个字符 `charlist`</span><span class="sxs-lookup"><span data-stu-id="eecca-131">Any single character not in `charlist`</span></span>|  
  
## <a name="character-lists"></a><span data-ttu-id="eecca-132">字符列表</span><span class="sxs-lookup"><span data-stu-id="eecca-132">Character Lists</span></span>  
 <span data-ttu-id="eecca-133">一个或多个字符的组 (`charlist`) 括在方括号中 (`[ ]`) 可用于匹配任何单个字符`string`并且可以包含几乎任何字符代码，包括数字。</span><span class="sxs-lookup"><span data-stu-id="eecca-133">A group of one or more characters (`charlist`) enclosed in brackets (`[ ]`) can be used to match any single character in `string` and can include almost any character code, including digits.</span></span>  
  
 <span data-ttu-id="eecca-134">惊叹号 (`!`) 的开始处`charlist`意味着，如果中的字符以外的任意字符，将生成一个匹配`charlist`中找到`string`。</span><span class="sxs-lookup"><span data-stu-id="eecca-134">An exclamation point (`!`) at the beginning of `charlist` means that a match is made if any character except the characters in `charlist` is found in `string`.</span></span> <span data-ttu-id="eecca-135">在括号外使用，感叹点与匹配本身。</span><span class="sxs-lookup"><span data-stu-id="eecca-135">When used outside brackets, the exclamation point matches itself.</span></span>  
  
## <a name="special-characters"></a><span data-ttu-id="eecca-136">特殊字符</span><span class="sxs-lookup"><span data-stu-id="eecca-136">Special Characters</span></span>  
 <span data-ttu-id="eecca-137">若要匹配的特殊字符的左的括号 (`[`)，问号 (`?`)，数字符号 (`#`)，和星号 (`*`)，将它们括在方括号中。</span><span class="sxs-lookup"><span data-stu-id="eecca-137">To match the special characters left bracket (`[`), question mark (`?`), number sign (`#`), and asterisk (`*`), enclose them in brackets.</span></span> <span data-ttu-id="eecca-138">右方括号 (`]`) 不能用于组中与自身匹配，但它可以在组外使用，作为单个字符。</span><span class="sxs-lookup"><span data-stu-id="eecca-138">The right bracket (`]`) cannot be used within a group to match itself, but it can be used outside a group as an individual character.</span></span>  
  
 <span data-ttu-id="eecca-139">字符序列`[]`被视为一个零长度字符串 (`""`)。</span><span class="sxs-lookup"><span data-stu-id="eecca-139">The character sequence `[]` is considered a zero-length string (`""`).</span></span> <span data-ttu-id="eecca-140">但是，它不能是用方括号括起来的字符列表的一部分。</span><span class="sxs-lookup"><span data-stu-id="eecca-140">However, it cannot be part of a character list enclosed in brackets.</span></span> <span data-ttu-id="eecca-141">如果你想要检查是否中的位置`string`包含一个的一组字符或根本没有字符，可以使用`Like`两次。</span><span class="sxs-lookup"><span data-stu-id="eecca-141">If you want to check whether a position in `string` contains one of a group of characters or no character at all, you can use `Like` twice.</span></span> <span data-ttu-id="eecca-142">有关示例，请参见 [如何：字符串与模式相匹配](../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-match-a-string-against-a-pattern.md)。</span><span class="sxs-lookup"><span data-stu-id="eecca-142">For an example, see [How to: Match a String against a Pattern](../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-match-a-string-against-a-pattern.md).</span></span>  
  
## <a name="character-ranges"></a><span data-ttu-id="eecca-143">字符范围</span><span class="sxs-lookup"><span data-stu-id="eecca-143">Character Ranges</span></span>  
 <span data-ttu-id="eecca-144">使用连字符 (`–`) 来分隔的范围的下限和上限`charlist`可以指定一系列字符。</span><span class="sxs-lookup"><span data-stu-id="eecca-144">By using a hyphen (`–`) to separate the lower and upper bounds of the range, `charlist` can specify a range of characters.</span></span> <span data-ttu-id="eecca-145">例如，`[A–Z]`导致匹配项，如果相应的字符位置中`string`包含的范围内的任何字符`A`–`Z`，和`[!H–L]`结果匹配，如果相应的字符位置包含范围之外的任何字符`H`–`L`。</span><span class="sxs-lookup"><span data-stu-id="eecca-145">For example, `[A–Z]` results in a match if the corresponding character position in `string` contains any character within the range `A`–`Z`, and `[!H–L]` results in a match if the corresponding character position contains any character outside the range `H`–`L`.</span></span>  
  
 <span data-ttu-id="eecca-146">当指定的字符范围时，它们必须出现在升序排序顺序，即从最低到最高。</span><span class="sxs-lookup"><span data-stu-id="eecca-146">When you specify a range of characters, they must appear in ascending sort order, that is, from lowest to highest.</span></span> <span data-ttu-id="eecca-147">因此，`[A–Z]`是有效的模式，但`[Z–A]`不是。</span><span class="sxs-lookup"><span data-stu-id="eecca-147">Thus, `[A–Z]` is a valid pattern, but `[Z–A]` is not.</span></span>  
  
### <a name="multiple-character-ranges"></a><span data-ttu-id="eecca-148">多个字符范围</span><span class="sxs-lookup"><span data-stu-id="eecca-148">Multiple Character Ranges</span></span>  
 <span data-ttu-id="eecca-149">若要指定相同的字符位置的多个范围，请将它们放在不带分隔符相同的方括号内。</span><span class="sxs-lookup"><span data-stu-id="eecca-149">To specify multiple ranges for the same character position, put them within the same brackets without delimiters.</span></span> <span data-ttu-id="eecca-150">例如，`[A–CX–Z]`导致匹配项，如果相应的字符位置中`string`包含范围中的任意字符`A`–`C`或范围`X`–`Z`。</span><span class="sxs-lookup"><span data-stu-id="eecca-150">For example, `[A–CX–Z]` results in a match if the corresponding character position in `string` contains any character within either the range `A`–`C` or the range `X`–`Z`.</span></span>  
  
### <a name="usage-of-the-hyphen"></a><span data-ttu-id="eecca-151">连字符的使用情况</span><span class="sxs-lookup"><span data-stu-id="eecca-151">Usage of the Hyphen</span></span>  
 <span data-ttu-id="eecca-152">连字符 (`–`) 可以显示 （后感叹号，如果有） 的开头或末尾`charlist`来与自身匹配。</span><span class="sxs-lookup"><span data-stu-id="eecca-152">A hyphen (`–`) can appear either at the beginning (after an exclamation point, if any) or at the end of `charlist` to match itself.</span></span> <span data-ttu-id="eecca-153">在任何其他位置，连字符标识两侧的连字符字符分隔的字符的范围。</span><span class="sxs-lookup"><span data-stu-id="eecca-153">In any other location, the hyphen identifies a range of characters delimited by the characters on either side of the hyphen.</span></span>  
  
## <a name="collating-sequence"></a><span data-ttu-id="eecca-154">对序列进行排序</span><span class="sxs-lookup"><span data-stu-id="eecca-154">Collating Sequence</span></span>  
 <span data-ttu-id="eecca-155">指定范围的含义取决于在运行时，由确定排序字符`Option Compare`和运行这段代码的系统区域设置。</span><span class="sxs-lookup"><span data-stu-id="eecca-155">The meaning of a specified range depends on the character ordering at run time, as determined by `Option Compare` and the locale setting of the system the code is running on.</span></span> <span data-ttu-id="eecca-156">与`Option Compare Binary`，范围`[A–E]`匹配`A`， `B`， `C`， `D`，和`E`。</span><span class="sxs-lookup"><span data-stu-id="eecca-156">With `Option Compare Binary`, the range `[A–E]` matches `A`, `B`, `C`, `D`, and `E`.</span></span> <span data-ttu-id="eecca-157">与`Option Compare Text`，`[A–E]`匹配`A`， `a`， `À`， `à`， `B`， `b`， `C`， `c`， `D`， `d`， `E`，和`e`。</span><span class="sxs-lookup"><span data-stu-id="eecca-157">With `Option Compare Text`, `[A–E]` matches `A`, `a`, `À`, `à`, `B`, `b`, `C`, `c`, `D`, `d`, `E`, and `e`.</span></span> <span data-ttu-id="eecca-158">范围不匹配`Ê`或`ê`因为带重音符的字符排序在排序顺序中的非重音字符之后。</span><span class="sxs-lookup"><span data-stu-id="eecca-158">The range does not match `Ê` or `ê` because accented characters collate after unaccented characters in the sort order.</span></span>  
  
## <a name="digraph-characters"></a><span data-ttu-id="eecca-159">二合字母字符</span><span class="sxs-lookup"><span data-stu-id="eecca-159">Digraph Characters</span></span>  
 <span data-ttu-id="eecca-160">在某些语言中，有表示两个字符的字母字符。</span><span class="sxs-lookup"><span data-stu-id="eecca-160">In some languages, there are alphabetic characters that represent two separate characters.</span></span> <span data-ttu-id="eecca-161">例如，有几种语言使用字符`æ`来表示字符`a`和`e`它们一起出现。</span><span class="sxs-lookup"><span data-stu-id="eecca-161">For example, several languages use the character `æ` to represent the characters `a` and `e` when they appear together.</span></span> <span data-ttu-id="eecca-162">`Like`认为单个二合字母字符，并且这两个字符是等效的运算符。</span><span class="sxs-lookup"><span data-stu-id="eecca-162">The `Like` operator recognizes that the single digraph character and the two individual characters are equivalent.</span></span>  
  
 <span data-ttu-id="eecca-163">当系统区域设置中指定一种语言，使用二合字母字符时，出现在单个二合字母字符`pattern`或`string`匹配其他字符串中等效的两个字符序列。</span><span class="sxs-lookup"><span data-stu-id="eecca-163">When a language that uses a digraph character is specified in the system locale settings, an occurrence of the single digraph character in either `pattern` or `string` matches the equivalent two-character sequence in the other string.</span></span> <span data-ttu-id="eecca-164">同样中的有向图时会字符`pattern`括在方括号中 （本身，在列表中，或某个范围内） 匹配中等效的双字符序列`string`。</span><span class="sxs-lookup"><span data-stu-id="eecca-164">Similarly, a digraph character in `pattern` enclosed in brackets (by itself, in a list, or in a range) matches the equivalent two-character sequence in `string`.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="eecca-165">重载</span><span class="sxs-lookup"><span data-stu-id="eecca-165">Overloading</span></span>  
 <span data-ttu-id="eecca-166">`Like`运算符可以被*重载*，这意味着，某个类或结构可以重新定义其行为时，操作数的类或结构的类型。</span><span class="sxs-lookup"><span data-stu-id="eecca-166">The `Like` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="eecca-167">如果你的代码对此类的类或结构使用此运算符，请确保了解其被重新定义的行为。</span><span class="sxs-lookup"><span data-stu-id="eecca-167">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="eecca-168">有关详细信息，请参阅 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)。</span><span class="sxs-lookup"><span data-stu-id="eecca-168">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="eecca-169">示例</span><span class="sxs-lookup"><span data-stu-id="eecca-169">Example</span></span>  
 <span data-ttu-id="eecca-170">此示例使用`Like`运算符来比较各种模式的字符串。</span><span class="sxs-lookup"><span data-stu-id="eecca-170">This example uses the `Like` operator to compare strings to various patterns.</span></span> <span data-ttu-id="eecca-171">结果进入`Boolean`变量，用于指示每个字符串是否满足模式的要求。</span><span class="sxs-lookup"><span data-stu-id="eecca-171">The results go into a `Boolean` variable indicating whether each string satisfies the pattern.</span></span>  
  
 [!code-vb[VbVbalrOperators#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#30)]  
  
## <a name="see-also"></a><span data-ttu-id="eecca-172">请参阅</span><span class="sxs-lookup"><span data-stu-id="eecca-172">See also</span></span>

- <xref:Microsoft.VisualBasic.Strings.InStr%2A>
- <xref:Microsoft.VisualBasic.Strings.StrComp%2A>
- [<span data-ttu-id="eecca-173">比较运算符</span><span class="sxs-lookup"><span data-stu-id="eecca-173">Comparison Operators</span></span>](../../../visual-basic/language-reference/operators/comparison-operators.md)
- [<span data-ttu-id="eecca-174">Visual Basic 中的运算符优先级</span><span class="sxs-lookup"><span data-stu-id="eecca-174">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="eecca-175">按功能列出的运算符</span><span class="sxs-lookup"><span data-stu-id="eecca-175">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="eecca-176">Option Compare 语句</span><span class="sxs-lookup"><span data-stu-id="eecca-176">Option Compare Statement</span></span>](../../../visual-basic/language-reference/statements/option-compare-statement.md)
- [<span data-ttu-id="eecca-177">运算符和表达式</span><span class="sxs-lookup"><span data-stu-id="eecca-177">Operators and Expressions</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
- [<span data-ttu-id="eecca-178">如何：字符串与模式相匹配</span><span class="sxs-lookup"><span data-stu-id="eecca-178">How to: Match a String against a Pattern</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-match-a-string-against-a-pattern.md)
