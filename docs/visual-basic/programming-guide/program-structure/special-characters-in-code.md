---
title: "代码中的特殊字符 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.)
- vb.(
- vb.colon
- vb.!
- vb..
- 'vb.:'
helpviewer_keywords:
- special characters [Visual Basic], in code
- parentheses [Visual Basic], using in code
- colons (:)
- period character in code
- dot operator (.)
- dictionary access operator [Visual Basic]
- concatenation operators [Visual Basic], special characters in code
- concatenation operators [Visual Basic], vs. addition operator
- '! operator'
- separators [Visual Basic], using in code
- operators [Visual Basic], dictionary access
- ': separator character'
- member access operator [Visual Basic]
- addition operator [Visual Basic]
- operators [Visual Basic], member access
- . operator
- exclamation points
- separators
- exclamation point operator (!)
- Visual Basic code, special characters
ms.assetid: 310dce0c-45b5-4e0d-83e9-32df258d2a3e
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 11c5ef9ad41fc2362d9ba4f2cb5eb5b63a9ca31c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="special-characters-in-code-visual-basic"></a>代码中的特殊字符 (Visual Basic)
有时您必须使用特殊字符，在代码中，即，不是字母或数字的字符。 标点和特殊字符中的[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]字符集各有其用途，从组织程序文本到定义编译器或已编译的程序执行的任务。 它们不指定要执行的操作。  
  
## <a name="parentheses"></a>括号  
 当你定义的过程中，如使用括号`Sub`或`Function`。 必须将所有过程自变量列表都括在括号中。 你还使用括号的变量或自变量置于逻辑组，特别是可重写中的复杂表达式的运算符优先级的默认顺序。 下面的示例阐释了这一点。  
  
 [!code-vb[VbVbcnConventions#11](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/special-characters-in-code_1.vb)]  
  
 按照前面的代码的值执行`d`8.225 和的值`e`为 3。 对计算`d`使用默认优先顺序，`/`通过`+`并且等效于`d = b + (c / a)`。 计算中的括号`e`重写默认的优先级。  
  
## <a name="separators"></a>分隔符  
 分隔符执行其名称所示： 分隔各部分的代码。 在[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]，分隔符字符是冒号 (`:`)。 当你想要包括在单独的行，而不是单独的行的多个语句时，请使用分隔符。 这可以节省空间，并提高代码的可读性。 下面的示例演示用冒号分隔的三个语句。  
  
 [!code-vb[VbVbcnConventions#12](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/special-characters-in-code_2.vb)]  
  
 有关详细信息，请参阅[How to： 中断和合并代码中的语句](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)。  
  
 冒号 (`:`) 字符也用于标识语句标签。 有关详细信息，请参阅[How to： 标签语句](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md)。  
  
## <a name="concatenation"></a>串联  
 使用`&`运算符*串联*，或将字符串链接在一起。 不要将其与混淆`+`运算符，将数值相加。 如果你使用`+`运算符来连接在基于数值，运行时可以获得不正确的结果。 下面的示例演示这一操作。  
  
 [!code-vb[VbVbcnConventions#13](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/special-characters-in-code_3.vb)]  
  
 按照前面的代码的值执行`resultA`为 21.01，而值`resultB`为"10.0111"。  
  
## <a name="member-access-operators"></a>成员访问运算符  
 若要访问的类型成员，你可以使用点 (`.`) 或感叹号 (`!`) 之间的类型名称和成员名称的运算符。  
  
### <a name="dot--operator"></a>句点 （.）运算符  
 使用`.`运算符作为成员访问运算符的类、 结构、 接口或枚举。 成员可以是字段、 属性、 事件或方法。 下面的示例阐释了这一点。  
  
 [!code-vb[VbVbcnConventions#14](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/special-characters-in-code_4.vb)]  
  
### <a name="exclamation-point--operator"></a>惊叹号 （！）运算符  
 使用`!`运算符仅在类或接口上的用作字典访问运算符。 类或接口必须具有一个默认属性，接受单个`String`自变量。 紧随`!`运算符将成为传递给以字符串形式的默认属性的自变量值。 下面的示例演示这一操作。  
  
 [!code-vb[VbVbcnConventions#15](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/special-characters-in-code_5.vb)]  
  
 三个输出行`MsgBox`所有显示的值`32856`。 第一行使用传统的访问权限属性`index`，第二个利用这一事实，`index`是类的默认属性`hasDefault`，和第三个使用字典访问权限类。  
  
 请注意，第二个操作数的`!`运算符必须是有效的 Visual Basic 标识符，未括在双引号 (`" "`)。 换而言之，你不能使用字符串文本或字符串变量。 以下到最后一个更改行的`MsgBox`调用生成错误，因为`"X"`未括起来的字符串文字。  
  
 `"Dictionary access returns " & hD!"X")`  
  
> [!NOTE]
>  必须显式默认集合的引用。 具体而言，不能使用`!`后期绑定变量上的运算符。  
  
 `!`字符也用作`Single`类型字符。  
  
## <a name="see-also"></a>另请参阅  
 [程序结构和代码约定](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)  
 [类型字符](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)
