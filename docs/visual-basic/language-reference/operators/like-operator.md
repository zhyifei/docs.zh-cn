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
ms.openlocfilehash: a9c672a397510c69c9ee67358689feff80d8831a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33605415"
---
# <a name="like-operator-visual-basic"></a>Like 运算符 (Visual Basic)
将字符串与模式进行比较。  
  
## <a name="syntax"></a>语法  
  
```  
result = string Like pattern  
```  
  
## <a name="parts"></a>部件  
 `result`  
 必须的。 任何`Boolean`变量。 结果是`Boolean`值，该值指示是否`string`满足`pattern`。  
  
 `string`  
 必须的。 任何 `String` 表达式。  
  
 `pattern`  
 必须的。 任何`String`符合"备注。"中所述的模式匹配的约定的表达式  
  
## <a name="remarks"></a>备注  
 如果中的值`string`满足中包含的模式`pattern`，`result`是`True`。 如果字符串不符合该模式中，`result`是`False`。 如果这两个`string`和`pattern`都是空字符串，则结果是`True`。  
  
## <a name="comparison-method"></a>比较方法  
 行为`Like`取决于运算符[选项比较语句](../../../visual-basic/language-reference/statements/option-compare-statement.md)。 每个源代码文件的默认字符串比较方法是`Option Compare Binary`。  
  
## <a name="pattern-options"></a>模式选项  
 内置的模式匹配的字符串比较提供通用工具。 模式匹配功能可让你中的每个字符相匹配`string`针对特定的字符、 通配符、 字符列表或字符范围。 下表显示在允许的字符数`pattern`和它们的匹配。  
  
|中的字符 `pattern`|中的匹配项 `string`|  
|-----------------------------|-------------------------|  
|`?`|任何单个字符|  
|`*`|零个或多个字符|  
|`#`|任何单个数字 (0-9)|  
|`[charlist]`|任何单个字符 `charlist`|  
|`[!charlist]`|不在任何单个字符 `charlist`|  
  
## <a name="character-lists"></a>字符列表  
 一组的一个或多个字符 (`charlist`) 用括号括起来 (`[ ]`) 可以使用来匹配任何单个字符`string`并且可以包含几乎任何字符代码，包括数字。  
  
 感叹号 (`!`) 开头的`charlist`意味着，如果中的字符以外的任意字符，将生成一个匹配`charlist`中找到`string`。 当使用方括号外面，感叹号匹配其本身。  
  
## <a name="special-characters"></a>特殊字符  
 若要匹配该左的括号，特殊字符 (`[`)，问号 (`?`)，数字符号 (`#`)，和星号 (`*`)，将它们括在括号中。 右括号 (`]`) 不能用于组中与自身匹配，但它作为单个字符可在组外。  
  
 字符序列`[]`被视为零长度字符串 (`""`)。 但是，它不能是括在方括号内的字符列表的一部分。 如果你想要检查是否中的位置`string`包含一个字符或根本没有字符的组，您可以使用`Like`两次。 有关示例，请参阅[如何： 将字符串与模式相匹配](../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-match-a-string-against-a-pattern.md)。  
  
## <a name="character-ranges"></a>字符范围  
 通过使用连字符 (`–`) 来分隔的范围下限和上限`charlist`可以指定的字符范围。 例如，`[A–Z]`导致匹配项，如果相应的字符位置中`string`包含范围内的任何字符`A`–`Z`，和`[!H–L]`导致匹配项，如果相应的字符位置包含范围以外的任何字符`H`–`L`。  
  
 在你指定的字符范围，它们必须显示以升序排序，即从最低到最高。 因此，`[A–Z]`是有效的模式，但`[Z–A]`不是。  
  
### <a name="multiple-character-ranges"></a>多个字符范围  
 若要指定的相同的字符位置的多个范围，请将它们放置在而不用分隔符相同方括号内。 例如，`[A–CX–Z]`导致匹配项，如果相应的字符位置中`string`包含任一范围内的任何字符`A`–`C`或范围`X`–`Z`。  
  
### <a name="usage-of-the-hyphen"></a>该连字符的使用情况  
 连字符 (`–`) 可以出现在 （之后感叹号，如果有） 的开头或末尾`charlist`来与自身匹配。 在任何其他位置，连字符标识由连字符的任何一侧的字符分隔的字符范围。  
  
## <a name="collating-sequence"></a>排序规则序列  
 指定范围的含义取决于在运行时，所确定的那样排序的字符`Option``Compare`和系统的区域设置中正在运行代码。 与`Option``Compare``Binary`，范围`[A–E]`匹配`A`， `B`， `C`， `D`，和`E`。 与`Option``Compare``Text`，`[A–E]`匹配`A`， `a`， `À`， `à`， `B`， `b`， `C`， `c`， `D`， `d`， `E`，和`e`。 范围不匹配`Ê`或`ê`因为重音的字符 collate 在排序顺序中的非重音个字符。  
  
## <a name="digraph-characters"></a>二合字母字符  
 在某些语言中，有一些表示两个单独的字符的字母字符。 例如，有几种语言使用字符`æ`来表示字符`a`和`e`它们一起出现。 `Like`运算符认为是等效的单个二合字母字符与这两个字符。  
  
 如果在系统区域设置中指定使用二合字母字符的语言、 中的单个二合字母字符的匹配项`pattern`或`string`匹配中另一个字符串等效的双字符序列。 同样中的二合字母字符`pattern`用方括号括起来 （本身，在列表中，或一系列） 匹配中等效的双字符序列`string`。  
  
## <a name="overloading"></a>重载  
 `Like`运算符可以被*重载*，这意味着，一个类或结构可以重新定义其行为时，操作数的类或结构的类型。 如果你的代码使用此运算符对这样的类或结构，请确保你了解其重新定义的行为。 有关详细信息，请参阅[运算符过程](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)。  
  
## <a name="example"></a>示例  
 此示例使用`Like`运算符比较字符串转换为各种模式。 结果进入`Boolean`变量，用于指示每个字符串是否满足模式。  
  
 [!code-vb[VbVbalrOperators#30](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/like-operator_1.vb)]  
  
## <a name="see-also"></a>请参阅  
 <xref:Microsoft.VisualBasic.Strings.InStr%2A>  
 <xref:Microsoft.VisualBasic.Strings.StrComp%2A>  
 [比较运算符](../../../visual-basic/language-reference/operators/comparison-operators.md)  
 [Visual Basic 中的运算符优先级](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [按功能列出的运算符](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [Option Compare 语句](../../../visual-basic/language-reference/statements/option-compare-statement.md)  
 [运算符和表达式](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)  
 [如何：将字符串与模式相匹配](../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-match-a-string-against-a-pattern.md)
