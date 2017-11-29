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
# <a name="how-to-match-a-string-against-a-pattern-visual-basic"></a>如何：将字符串与模式相匹配 (Visual Basic)
如果你想要找出的表达式[字符串数据类型](../../../../visual-basic/language-reference/data-types/string-data-type.md)满足一种模式，则你可以使用[Like 运算符](../../../../visual-basic/language-reference/operators/like-operator.md)。  
  
 `Like`采用两个操作数。 左的操作数是字符串表达式和右操作数是一个包含要用于匹配的模式字符串。 `Like`返回`Boolean`值，该值指示字符串表达式是否满足模式。  
  
 你可以匹配字符串表达式针对特定的字符、 通配符、 字符列表或字符范围中的每个字符。 模式字符串中的规范的位置对应的字符串表达式中要匹配的字符的位置。  
  
### <a name="to-match-a-character-in-the-string-expression-against-a-specific-character"></a>针对特定的字符的字符串表达式中的字符相匹配  
  
-   特定的字符将直接放在模式字符串。 某些特殊字符必须括在方括号中 (`[ ]`)。 有关详细信息，请参阅[Like 运算符](../../../../visual-basic/language-reference/operators/like-operator.md)。  
  
     下面的示例测试是否`myString`只包含单个字符`H`。  
  
     [!code-vb[VbVbalrOperators#70](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-match-a-string-against-a-pattern_1.vb)]  
  
### <a name="to-match-a-character-in-the-string-expression-against-a-wildcard-character"></a>在对通配符字符的字符串表达式中的字符相匹配  
  
-   将问号 (`?`) 中的模式字符串。 此位置中的任何有效字符可以成功匹配。  
  
     下面的示例测试是否`myString`包含的单个字符`W`跟恰好两个字符的任何值。  
  
     [!code-vb[VbVbalrOperators#71](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-match-a-string-against-a-pattern_2.vb)]  
  
### <a name="to-match-a-character-in-the-string-expression-against-a-list-of-characters"></a>根据列表的字符的字符串表达式中的字符相匹配  
  
-   将括号放 (`[ ]`) 中的模式字符串，并将字符的列表放括号内。 不要用逗号或任何其他分隔符分隔字符。 在列表中的任何单个字符可成功匹配。  
  
     下面的示例测试是否`myString`包含任何有效字符后跟字符中恰好有一个`A`， `C`，或`E`。  
  
     [!code-vb[VbVbalrOperators#72](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-match-a-string-against-a-pattern_3.vb)]  
  
     请注意，此匹配区分大小写。  
  
### <a name="to-match-a-character-in-the-string-expression-against-a-range-of-characters"></a>在针对某一范围的字符的字符串表达式中的字符相匹配  
  
-   将括号放 (`[ ]`) 以连字符分隔模式字符串中和 put 的最低和最高的字符范围中括号内，(`–`)。 范围内的任何单个字符可成功匹配。  
  
     下面的示例测试是否`myString`字符组成`num`恰好有一个字符后跟`i`， `j`， `k`， `l`， `m`，或`n`。  
  
     [!code-vb[VbVbalrOperators#73](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-match-a-string-against-a-pattern_4.vb)]  
  
     请注意，此匹配区分大小写。  
  
## <a name="matching-empty-strings"></a>匹配空字符串  
 `Like`将序列`[]`为零长度字符串 (`""`)。 你可以使用`[]`来测试是否将整个字符串表达式为空，但不能使用它来测试是否为空字符串表达式中的特定位置。 如果为空的位置是另一种需要对其进行，你可以使用测试`Like`不止一次。  
  
#### <a name="to-match-a-character-in-the-string-expression-against-a-list-of-characters-or-no-character"></a>根据列表的字符或无任何字符的字符串表达式中的字符相匹配  
  
1.  调用`Like`两次上相同的运算符的字符串表达式，并使用连接的两个调用[或运算符](../../../../visual-basic/language-reference/operators/or-operator.md)或[OrElse 运算符](../../../../visual-basic/language-reference/operators/orelse-operator.md)。  
  
2.  第一个的模式字符串中`Like`子句，包括字符列表，用括号括起来 (`[ ]`)。  
  
3.  第二个模式字符串中`Like`子句，不要将放在任何字符的位置问题。  
  
     下面的示例测试七位数电话号码`phoneNum`为 3 个数字后, 跟一个空格，连字符 (`–`)，一段时间 (`.`)，或任何字符后, 跟 4 个数字。  
  
     [!code-vb[VbVbalrOperators#74](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-match-a-string-against-a-pattern_5.vb)]  
  
## <a name="see-also"></a>另请参阅  
 [比较运算符](../../../../visual-basic/language-reference/operators/comparison-operators.md)  
 [运算符和表达式](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)  
 [Like 运算符](../../../../visual-basic/language-reference/operators/like-operator.md)  
 [String 数据类型](../../../../visual-basic/language-reference/data-types/string-data-type.md)
