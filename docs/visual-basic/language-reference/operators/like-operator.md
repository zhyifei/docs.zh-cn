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
ms.openlocfilehash: 795ecc2e80d57af29ccd50c50d2dd209c6425e40
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2019
ms.locfileid: "71701126"
---
# <a name="like-operator-visual-basic"></a><span data-ttu-id="d31f8-102">Like 运算符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d31f8-102">Like Operator (Visual Basic)</span></span>
<span data-ttu-id="d31f8-103">将字符串与模式进行比较。</span><span class="sxs-lookup"><span data-stu-id="d31f8-103">Compares a string against a pattern.</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="d31f8-104">.NET Core 和 .NET Standard 项目目前不支持 @no__t 0 运算符。</span><span class="sxs-lookup"><span data-stu-id="d31f8-104">The `Like` operator is currently not supported in .NET Core and .NET Standard projects.</span></span>

## <a name="syntax"></a><span data-ttu-id="d31f8-105">语法</span><span class="sxs-lookup"><span data-stu-id="d31f8-105">Syntax</span></span>  
  
```vb  
result = string Like pattern  
```  
  
## <a name="parts"></a><span data-ttu-id="d31f8-106">部件</span><span class="sxs-lookup"><span data-stu-id="d31f8-106">Parts</span></span>  
 `result`  
 <span data-ttu-id="d31f8-107">必需。</span><span class="sxs-lookup"><span data-stu-id="d31f8-107">Required.</span></span> <span data-ttu-id="d31f8-108">任何 @no__t 0 变量。</span><span class="sxs-lookup"><span data-stu-id="d31f8-108">Any `Boolean` variable.</span></span> <span data-ttu-id="d31f8-109">结果为 `Boolean` 值，指示 @no__t 是否满足 @no__t 2。</span><span class="sxs-lookup"><span data-stu-id="d31f8-109">The result is a `Boolean` value indicating whether or not the `string` satisfies the `pattern`.</span></span>  
  
 `string`  
 <span data-ttu-id="d31f8-110">必需。</span><span class="sxs-lookup"><span data-stu-id="d31f8-110">Required.</span></span> <span data-ttu-id="d31f8-111">任何 `String` 表达式。</span><span class="sxs-lookup"><span data-stu-id="d31f8-111">Any `String` expression.</span></span>  
  
 `pattern`  
 <span data-ttu-id="d31f8-112">必需。</span><span class="sxs-lookup"><span data-stu-id="d31f8-112">Required.</span></span> <span data-ttu-id="d31f8-113">符合 "备注" 中所述的模式匹配约定的任何 @no__t 0 表达式。</span><span class="sxs-lookup"><span data-stu-id="d31f8-113">Any `String` expression conforming to the pattern-matching conventions described in "Remarks."</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d31f8-114">备注</span><span class="sxs-lookup"><span data-stu-id="d31f8-114">Remarks</span></span>  
 <span data-ttu-id="d31f8-115">如果 `string` 中的值满足 @no__t 中包含的模式，`result` 则 @no__t 为-3。</span><span class="sxs-lookup"><span data-stu-id="d31f8-115">If the value in `string` satisfies the pattern contained in `pattern`, `result` is `True`.</span></span> <span data-ttu-id="d31f8-116">如果字符串不满足模式，则 `result` @no__t 为-1。</span><span class="sxs-lookup"><span data-stu-id="d31f8-116">If the string does not satisfy the pattern, `result` is `False`.</span></span> <span data-ttu-id="d31f8-117">如果 @no__t 0 和 `pattern` 均为空字符串，则结果为 `True`。</span><span class="sxs-lookup"><span data-stu-id="d31f8-117">If both `string` and `pattern` are empty strings, the result is `True`.</span></span>  
  
## <a name="comparison-method"></a><span data-ttu-id="d31f8-118">比较方法</span><span class="sxs-lookup"><span data-stu-id="d31f8-118">Comparison Method</span></span>  
 <span data-ttu-id="d31f8-119">@No__t 运算符的行为取决于[Option Compare 语句](../../../visual-basic/language-reference/statements/option-compare-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="d31f8-119">The behavior of the `Like` operator depends on the [Option Compare Statement](../../../visual-basic/language-reference/statements/option-compare-statement.md).</span></span> <span data-ttu-id="d31f8-120">每个源文件的默认字符串比较方法为 `Option Compare Binary`。</span><span class="sxs-lookup"><span data-stu-id="d31f8-120">The default string comparison method for each source file is `Option Compare Binary`.</span></span>  
  
## <a name="pattern-options"></a><span data-ttu-id="d31f8-121">模式选项</span><span class="sxs-lookup"><span data-stu-id="d31f8-121">Pattern Options</span></span>  
 <span data-ttu-id="d31f8-122">内置模式匹配为字符串比较提供了多种工具。</span><span class="sxs-lookup"><span data-stu-id="d31f8-122">Built-in pattern matching provides a versatile tool for string comparisons.</span></span> <span data-ttu-id="d31f8-123">使用模式匹配功能，可以将 `string` 中的每个字符与特定字符、通配符、字符列表或字符范围匹配。</span><span class="sxs-lookup"><span data-stu-id="d31f8-123">The pattern-matching features allow you to match each character in `string` against a specific character, a wildcard character, a character list, or a character range.</span></span> <span data-ttu-id="d31f8-124">下表显示 `pattern` 中允许的字符以及它们的匹配内容。</span><span class="sxs-lookup"><span data-stu-id="d31f8-124">The following table shows the characters allowed in `pattern` and what they match.</span></span>  
  
|<span data-ttu-id="d31f8-125">@No__t 中的字符-0</span><span class="sxs-lookup"><span data-stu-id="d31f8-125">Characters in `pattern`</span></span>|<span data-ttu-id="d31f8-126">匹配 `string`</span><span class="sxs-lookup"><span data-stu-id="d31f8-126">Matches in `string`</span></span>|  
|-----------------------------|-------------------------|  
|`?`|<span data-ttu-id="d31f8-127">任何单个字符</span><span class="sxs-lookup"><span data-stu-id="d31f8-127">Any single character</span></span>|  
|`*`|<span data-ttu-id="d31f8-128">零个或多个字符</span><span class="sxs-lookup"><span data-stu-id="d31f8-128">Zero or more characters</span></span>|  
|`#`|<span data-ttu-id="d31f8-129">任何单个数字（0–9）</span><span class="sxs-lookup"><span data-stu-id="d31f8-129">Any single digit (0–9)</span></span>|  
|`[charlist]`|<span data-ttu-id="d31f8-130">@No__t 中的任何单个字符</span><span class="sxs-lookup"><span data-stu-id="d31f8-130">Any single character in `charlist`</span></span>|  
|`[!charlist]`|<span data-ttu-id="d31f8-131">不在 @no__t 中的任何单个字符-0</span><span class="sxs-lookup"><span data-stu-id="d31f8-131">Any single character not in `charlist`</span></span>|  
  
## <a name="character-lists"></a><span data-ttu-id="d31f8-132">字符列表</span><span class="sxs-lookup"><span data-stu-id="d31f8-132">Character Lists</span></span>  
 <span data-ttu-id="d31f8-133">括在方括号（`[ ]`）中的一个或多个字符（`charlist`）的组可用于匹配 `string` 中的任何单个字符，并可包括几乎所有字符代码（包括数字）。</span><span class="sxs-lookup"><span data-stu-id="d31f8-133">A group of one or more characters (`charlist`) enclosed in brackets (`[ ]`) can be used to match any single character in `string` and can include almost any character code, including digits.</span></span>  
  
 <span data-ttu-id="d31f8-134">@No__t 开头的感叹号（`!`）表示如果在 `string` 中找不到 `charlist` 中的字符以外的任何字符，则进行匹配。</span><span class="sxs-lookup"><span data-stu-id="d31f8-134">An exclamation point (`!`) at the beginning of `charlist` means that a match is made if any character except the characters in `charlist` is found in `string`.</span></span> <span data-ttu-id="d31f8-135">当在方括号外使用时，感叹号与自身匹配。</span><span class="sxs-lookup"><span data-stu-id="d31f8-135">When used outside brackets, the exclamation point matches itself.</span></span>  
  
## <a name="special-characters"></a><span data-ttu-id="d31f8-136">特殊字符</span><span class="sxs-lookup"><span data-stu-id="d31f8-136">Special Characters</span></span>  
 <span data-ttu-id="d31f8-137">若要匹配特殊字符左方括号（`[`）、问号（`?`）、数字符号（`#`）和星号（`*`），请将它们括在括号中。</span><span class="sxs-lookup"><span data-stu-id="d31f8-137">To match the special characters left bracket (`[`), question mark (`?`), number sign (`#`), and asterisk (`*`), enclose them in brackets.</span></span> <span data-ttu-id="d31f8-138">不能在组内使用右括号（`]`）来匹配自身，但它可以作为单个字符在组外使用。</span><span class="sxs-lookup"><span data-stu-id="d31f8-138">The right bracket (`]`) cannot be used within a group to match itself, but it can be used outside a group as an individual character.</span></span>  
  
 <span data-ttu-id="d31f8-139">字符序列 @no__t 为长度为零的字符串（@no__t 为-1）。</span><span class="sxs-lookup"><span data-stu-id="d31f8-139">The character sequence `[]` is considered a zero-length string (`""`).</span></span> <span data-ttu-id="d31f8-140">但是，它不能是括在括号中的字符列表的一部分。</span><span class="sxs-lookup"><span data-stu-id="d31f8-140">However, it cannot be part of a character list enclosed in brackets.</span></span> <span data-ttu-id="d31f8-141">如果要检查 `string` 中的某个位置是否包含一组字符或不包含任何字符，可以两次使用 @no__t。</span><span class="sxs-lookup"><span data-stu-id="d31f8-141">If you want to check whether a position in `string` contains one of a group of characters or no character at all, you can use `Like` twice.</span></span> <span data-ttu-id="d31f8-142">有关示例，请参见 [如何：将字符串与模式 @ no__t 匹配。</span><span class="sxs-lookup"><span data-stu-id="d31f8-142">For an example, see [How to: Match a String against a Pattern](../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-match-a-string-against-a-pattern.md).</span></span>  
  
## <a name="character-ranges"></a><span data-ttu-id="d31f8-143">字符范围</span><span class="sxs-lookup"><span data-stu-id="d31f8-143">Character Ranges</span></span>  
 <span data-ttu-id="d31f8-144">通过使用连字符（`–`）来分隔范围的下限和上限，`charlist` 可以指定字符范围。</span><span class="sxs-lookup"><span data-stu-id="d31f8-144">By using a hyphen (`–`) to separate the lower and upper bounds of the range, `charlist` can specify a range of characters.</span></span> <span data-ttu-id="d31f8-145">例如，如果 `string` 中的相应字符位置包含范围 `A` – @no__t @no__t 中的任何字符 @no__t，则-0 将导致匹配; 如果相应的字符位置包含除范围 `H` – `L`。</span><span class="sxs-lookup"><span data-stu-id="d31f8-145">For example, `[A–Z]` results in a match if the corresponding character position in `string` contains any character within the range `A`–`Z`, and `[!H–L]` results in a match if the corresponding character position contains any character outside the range `H`–`L`.</span></span>  
  
 <span data-ttu-id="d31f8-146">指定字符范围时，它们必须按升序排序，即从最低到最高。</span><span class="sxs-lookup"><span data-stu-id="d31f8-146">When you specify a range of characters, they must appear in ascending sort order, that is, from lowest to highest.</span></span> <span data-ttu-id="d31f8-147">因此，@no__t 是有效的模式，但 @no__t 不是。</span><span class="sxs-lookup"><span data-stu-id="d31f8-147">Thus, `[A–Z]` is a valid pattern, but `[Z–A]` is not.</span></span>  
  
### <a name="multiple-character-ranges"></a><span data-ttu-id="d31f8-148">多字符范围</span><span class="sxs-lookup"><span data-stu-id="d31f8-148">Multiple Character Ranges</span></span>  
 <span data-ttu-id="d31f8-149">若要为同一字符位置指定多个范围，请将它们放在不带分隔符的相同括号中。</span><span class="sxs-lookup"><span data-stu-id="d31f8-149">To specify multiple ranges for the same character position, put them within the same brackets without delimiters.</span></span> <span data-ttu-id="d31f8-150">例如，如果 `string` 中的相应字符位置包含范围 `A` – @no__t 或范围 `X` – @no__t 的任何字符，则 @no__t 0 会导致匹配。</span><span class="sxs-lookup"><span data-stu-id="d31f8-150">For example, `[A–CX–Z]` results in a match if the corresponding character position in `string` contains any character within either the range `A`–`C` or the range `X`–`Z`.</span></span>  
  
### <a name="usage-of-the-hyphen"></a><span data-ttu-id="d31f8-151">连字符的用法</span><span class="sxs-lookup"><span data-stu-id="d31f8-151">Usage of the Hyphen</span></span>  
 <span data-ttu-id="d31f8-152">连字符（`–`）可以出现在开头（在感叹号后，如果有）或在 `charlist` 的末尾，以匹配其自身。</span><span class="sxs-lookup"><span data-stu-id="d31f8-152">A hyphen (`–`) can appear either at the beginning (after an exclamation point, if any) or at the end of `charlist` to match itself.</span></span> <span data-ttu-id="d31f8-153">在其他任何位置，连字符标识由连字符两侧的字符分隔的一系列字符。</span><span class="sxs-lookup"><span data-stu-id="d31f8-153">In any other location, the hyphen identifies a range of characters delimited by the characters on either side of the hyphen.</span></span>  
  
## <a name="collating-sequence"></a><span data-ttu-id="d31f8-154">排序顺序</span><span class="sxs-lookup"><span data-stu-id="d31f8-154">Collating Sequence</span></span>  
 <span data-ttu-id="d31f8-155">指定范围的含义取决于运行时的字符排序，由 `Option Compare` 和运行代码的系统的区域设置确定。</span><span class="sxs-lookup"><span data-stu-id="d31f8-155">The meaning of a specified range depends on the character ordering at run time, as determined by `Option Compare` and the locale setting of the system the code is running on.</span></span> <span data-ttu-id="d31f8-156">对于 `Option Compare Binary`，范围 `[A–E]` 与 `A`、`B`、@no__t、@no__t 和 @no__t 匹配。</span><span class="sxs-lookup"><span data-stu-id="d31f8-156">With `Option Compare Binary`, the range `[A–E]` matches `A`, `B`, `C`, `D`, and `E`.</span></span> <span data-ttu-id="d31f8-157">对于 `Option Compare Text`，`[A–E]` 匹配 `A`，`a`，`À`，`à`，`B`，`b`，`C`，`c`，0，1，2，3。</span><span class="sxs-lookup"><span data-stu-id="d31f8-157">With `Option Compare Text`, `[A–E]` matches `A`, `a`, `À`, `à`, `B`, `b`, `C`, `c`, `D`, `d`, `E`, and `e`.</span></span> <span data-ttu-id="d31f8-158">该范围不匹配 `Ê` 或 `ê`，因为重音字符在排序顺序中逐字符进行排序。</span><span class="sxs-lookup"><span data-stu-id="d31f8-158">The range does not match `Ê` or `ê` because accented characters collate after unaccented characters in the sort order.</span></span>  
  
## <a name="digraph-characters"></a><span data-ttu-id="d31f8-159">连字符</span><span class="sxs-lookup"><span data-stu-id="d31f8-159">Digraph Characters</span></span>  
 <span data-ttu-id="d31f8-160">在某些语言中，有表示两个不同字符的字母字符。</span><span class="sxs-lookup"><span data-stu-id="d31f8-160">In some languages, there are alphabetic characters that represent two separate characters.</span></span> <span data-ttu-id="d31f8-161">例如，几种语言使用字符 `æ` 来表示字符 `a`，并在它们一起显示时 `e`。</span><span class="sxs-lookup"><span data-stu-id="d31f8-161">For example, several languages use the character `æ` to represent the characters `a` and `e` when they appear together.</span></span> <span data-ttu-id="d31f8-162">@No__t-0 运算符识别单个连字符和两个单个字符是否等效。</span><span class="sxs-lookup"><span data-stu-id="d31f8-162">The `Like` operator recognizes that the single digraph character and the two individual characters are equivalent.</span></span>  
  
 <span data-ttu-id="d31f8-163">如果在系统区域设置中指定了使用连字符字符的语言，则在 `pattern` 或 `string` 中出现单合组字符将与另一个字符串中的等效双字符序列匹配。</span><span class="sxs-lookup"><span data-stu-id="d31f8-163">When a language that uses a digraph character is specified in the system locale settings, an occurrence of the single digraph character in either `pattern` or `string` matches the equivalent two-character sequence in the other string.</span></span> <span data-ttu-id="d31f8-164">同样，括在括号中的 `pattern` 中的连字符（单独、列表中或范围）与 `string` 中等效的双字符序列匹配。</span><span class="sxs-lookup"><span data-stu-id="d31f8-164">Similarly, a digraph character in `pattern` enclosed in brackets (by itself, in a list, or in a range) matches the equivalent two-character sequence in `string`.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="d31f8-165">重载</span><span class="sxs-lookup"><span data-stu-id="d31f8-165">Overloading</span></span>  
 <span data-ttu-id="d31f8-166">@No__t-0 运算符可*重载*，这意味着当操作数具有该类或结构的类型时，该类或结构可以重新定义其行为。</span><span class="sxs-lookup"><span data-stu-id="d31f8-166">The `Like` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="d31f8-167">如果你的代码在该类或结构上使用此运算符，请确保了解其重新定义的行为。</span><span class="sxs-lookup"><span data-stu-id="d31f8-167">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="d31f8-168">有关详细信息，请参阅 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)。</span><span class="sxs-lookup"><span data-stu-id="d31f8-168">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d31f8-169">示例</span><span class="sxs-lookup"><span data-stu-id="d31f8-169">Example</span></span>  
 <span data-ttu-id="d31f8-170">此示例使用 `Like` 运算符将字符串与各种模式进行比较。</span><span class="sxs-lookup"><span data-stu-id="d31f8-170">This example uses the `Like` operator to compare strings to various patterns.</span></span> <span data-ttu-id="d31f8-171">结果将进入 `Boolean` 变量，该变量指示每个字符串是否满足此模式。</span><span class="sxs-lookup"><span data-stu-id="d31f8-171">The results go into a `Boolean` variable indicating whether each string satisfies the pattern.</span></span>  
  
 [!code-vb[VbVbalrOperators#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#30)]  
  
## <a name="see-also"></a><span data-ttu-id="d31f8-172">请参阅</span><span class="sxs-lookup"><span data-stu-id="d31f8-172">See also</span></span>

- <xref:Microsoft.VisualBasic.Strings.InStr%2A>
- <xref:Microsoft.VisualBasic.Strings.StrComp%2A>
- [<span data-ttu-id="d31f8-173">比较运算符</span><span class="sxs-lookup"><span data-stu-id="d31f8-173">Comparison Operators</span></span>](../../../visual-basic/language-reference/operators/comparison-operators.md)
- [<span data-ttu-id="d31f8-174">Visual Basic 中的运算符优先级</span><span class="sxs-lookup"><span data-stu-id="d31f8-174">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="d31f8-175">按功能列出的运算符</span><span class="sxs-lookup"><span data-stu-id="d31f8-175">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="d31f8-176">Option Compare 语句</span><span class="sxs-lookup"><span data-stu-id="d31f8-176">Option Compare Statement</span></span>](../../../visual-basic/language-reference/statements/option-compare-statement.md)
- [<span data-ttu-id="d31f8-177">运算符和表达式</span><span class="sxs-lookup"><span data-stu-id="d31f8-177">Operators and Expressions</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
- <span data-ttu-id="d31f8-178">[如何：将字符串与模式 @ no__t 匹配</span><span class="sxs-lookup"><span data-stu-id="d31f8-178">[How to: Match a String against a Pattern](../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-match-a-string-against-a-pattern.md)</span></span>
