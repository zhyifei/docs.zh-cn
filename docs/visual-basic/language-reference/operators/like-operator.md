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
# <a name="like-operator-visual-basic"></a>Like 运算符 (Visual Basic)
将字符串与模式进行比较。  

> [!IMPORTANT]
> .NET Core 和 .NET Standard 项目目前不支持 @no__t 0 运算符。

## <a name="syntax"></a>语法  
  
```vb  
result = string Like pattern  
```  
  
## <a name="parts"></a>部件  
 `result`  
 必需。 任何 @no__t 0 变量。 结果为 `Boolean` 值，指示 @no__t 是否满足 @no__t 2。  
  
 `string`  
 必需。 任何 `String` 表达式。  
  
 `pattern`  
 必需。 符合 "备注" 中所述的模式匹配约定的任何 @no__t 0 表达式。  
  
## <a name="remarks"></a>备注  
 如果 `string` 中的值满足 @no__t 中包含的模式，`result` 则 @no__t 为-3。 如果字符串不满足模式，则 `result` @no__t 为-1。 如果 @no__t 0 和 `pattern` 均为空字符串，则结果为 `True`。  
  
## <a name="comparison-method"></a>比较方法  
 @No__t 运算符的行为取决于[Option Compare 语句](../../../visual-basic/language-reference/statements/option-compare-statement.md)。 每个源文件的默认字符串比较方法为 `Option Compare Binary`。  
  
## <a name="pattern-options"></a>模式选项  
 内置模式匹配为字符串比较提供了多种工具。 使用模式匹配功能，可以将 `string` 中的每个字符与特定字符、通配符、字符列表或字符范围匹配。 下表显示 `pattern` 中允许的字符以及它们的匹配内容。  
  
|@No__t 中的字符-0|匹配 `string`|  
|-----------------------------|-------------------------|  
|`?`|任何单个字符|  
|`*`|零个或多个字符|  
|`#`|任何单个数字（0–9）|  
|`[charlist]`|@No__t 中的任何单个字符|  
|`[!charlist]`|不在 @no__t 中的任何单个字符-0|  
  
## <a name="character-lists"></a>字符列表  
 括在方括号（`[ ]`）中的一个或多个字符（`charlist`）的组可用于匹配 `string` 中的任何单个字符，并可包括几乎所有字符代码（包括数字）。  
  
 @No__t 开头的感叹号（`!`）表示如果在 `string` 中找不到 `charlist` 中的字符以外的任何字符，则进行匹配。 当在方括号外使用时，感叹号与自身匹配。  
  
## <a name="special-characters"></a>特殊字符  
 若要匹配特殊字符左方括号（`[`）、问号（`?`）、数字符号（`#`）和星号（`*`），请将它们括在括号中。 不能在组内使用右括号（`]`）来匹配自身，但它可以作为单个字符在组外使用。  
  
 字符序列 @no__t 为长度为零的字符串（@no__t 为-1）。 但是，它不能是括在括号中的字符列表的一部分。 如果要检查 `string` 中的某个位置是否包含一组字符或不包含任何字符，可以两次使用 @no__t。 有关示例，请参见 [如何：将字符串与模式 @ no__t 匹配。  
  
## <a name="character-ranges"></a>字符范围  
 通过使用连字符（`–`）来分隔范围的下限和上限，`charlist` 可以指定字符范围。 例如，如果 `string` 中的相应字符位置包含范围 `A` – @no__t @no__t 中的任何字符 @no__t，则-0 将导致匹配; 如果相应的字符位置包含除范围 `H` – `L`。  
  
 指定字符范围时，它们必须按升序排序，即从最低到最高。 因此，@no__t 是有效的模式，但 @no__t 不是。  
  
### <a name="multiple-character-ranges"></a>多字符范围  
 若要为同一字符位置指定多个范围，请将它们放在不带分隔符的相同括号中。 例如，如果 `string` 中的相应字符位置包含范围 `A` – @no__t 或范围 `X` – @no__t 的任何字符，则 @no__t 0 会导致匹配。  
  
### <a name="usage-of-the-hyphen"></a>连字符的用法  
 连字符（`–`）可以出现在开头（在感叹号后，如果有）或在 `charlist` 的末尾，以匹配其自身。 在其他任何位置，连字符标识由连字符两侧的字符分隔的一系列字符。  
  
## <a name="collating-sequence"></a>排序顺序  
 指定范围的含义取决于运行时的字符排序，由 `Option Compare` 和运行代码的系统的区域设置确定。 对于 `Option Compare Binary`，范围 `[A–E]` 与 `A`、`B`、@no__t、@no__t 和 @no__t 匹配。 对于 `Option Compare Text`，`[A–E]` 匹配 `A`，`a`，`À`，`à`，`B`，`b`，`C`，`c`，0，1，2，3。 该范围不匹配 `Ê` 或 `ê`，因为重音字符在排序顺序中逐字符进行排序。  
  
## <a name="digraph-characters"></a>连字符  
 在某些语言中，有表示两个不同字符的字母字符。 例如，几种语言使用字符 `æ` 来表示字符 `a`，并在它们一起显示时 `e`。 @No__t-0 运算符识别单个连字符和两个单个字符是否等效。  
  
 如果在系统区域设置中指定了使用连字符字符的语言，则在 `pattern` 或 `string` 中出现单合组字符将与另一个字符串中的等效双字符序列匹配。 同样，括在括号中的 `pattern` 中的连字符（单独、列表中或范围）与 `string` 中等效的双字符序列匹配。  
  
## <a name="overloading"></a>重载  
 @No__t-0 运算符可*重载*，这意味着当操作数具有该类或结构的类型时，该类或结构可以重新定义其行为。 如果你的代码在该类或结构上使用此运算符，请确保了解其重新定义的行为。 有关详细信息，请参阅 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)。  
  
## <a name="example"></a>示例  
 此示例使用 `Like` 运算符将字符串与各种模式进行比较。 结果将进入 `Boolean` 变量，该变量指示每个字符串是否满足此模式。  
  
 [!code-vb[VbVbalrOperators#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#30)]  
  
## <a name="see-also"></a>请参阅

- <xref:Microsoft.VisualBasic.Strings.InStr%2A>
- <xref:Microsoft.VisualBasic.Strings.StrComp%2A>
- [比较运算符](../../../visual-basic/language-reference/operators/comparison-operators.md)
- [Visual Basic 中的运算符优先级](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [按功能列出的运算符](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Option Compare 语句](../../../visual-basic/language-reference/statements/option-compare-statement.md)
- [运算符和表达式](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
- [如何：将字符串与模式 @ no__t 匹配
