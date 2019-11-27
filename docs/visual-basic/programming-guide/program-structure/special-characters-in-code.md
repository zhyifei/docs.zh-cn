---
title: 代码中的特殊字符
ms.date: 07/20/2015
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
ms.openlocfilehash: f4ab35b56d48ae86bdb024ffea27735b39decdc2
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347258"
---
# <a name="special-characters-in-code-visual-basic"></a>代码中的特殊字符 (Visual Basic)
有时，您必须在代码中使用特殊字符，即不是字母或数字的字符。 Visual Basic 字符集中的标点和特殊字符具有多种用途，从组织程序文本到定义编译器或已编译程序所执行的任务。 它们不指定要执行的操作。  
  
## <a name="parentheses"></a>括号  
 定义过程时使用括号，如 `Sub` 或 `Function`。 必须将所有过程参数列表括在括号中。 还可以使用括号将变量或参数置于逻辑组中，特别是在复杂表达式中覆盖运算符优先级的默认顺序。 下面的示例对此进行了演示。  
  
 [!code-vb[VbVbcnConventions#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#11)]  
  
 执行前面的代码后，`d` 的值为8.225，`e` 的值为3。 `d` 的计算使用 `/` 高于 `+` 的默认优先级，并且等效于 `d = b + (c / a)`。 计算中的括号用于 `e` 覆盖默认优先级。  
  
## <a name="separators"></a>分隔符  
 分隔符可执行其名称建议：它们分隔代码段。 在 Visual Basic 中，分隔符为冒号（`:`）。 如果要在单个行而不是单独的行中包含多个语句，请使用分隔符。 这样可以节省空间，并可提高代码的可读性。 下面的示例显示了以冒号分隔的三个语句。  
  
 [!code-vb[VbVbcnConventions#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#12)]  
  
 有关详细信息，请参阅[如何：在代码中中断和组合语句](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)。  
  
 冒号（`:`）字符还用于标识语句标签。 有关详细信息，请参阅[如何：标签语句](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md)。  
  
## <a name="concatenation"></a>串联  
 使用 `&` 运算符进行*串联*，或将字符串链接在一起。 不要将其与 `+` 运算符混淆，后者将数值相加。 如果在操作数值时使用 `+` 运算符进行连接，则可以获得不正确的结果。 下面的示例演示这一操作。  
  
 [!code-vb[VbVbcnConventions#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#13)]  
  
 执行前面的代码后，`resultA` 的值为21.01，`resultB` 的值为 "10.0111"。  
  
## <a name="member-access-operators"></a>成员访问运算符  
 若要访问类型的成员，请在类型名称和成员名称之间使用点（`.`）或感叹号（`!`）运算符。  
  
### <a name="dot--operator"></a>点（.）操作员  
 在类、结构、接口或枚举上使用 `.` 运算符作为成员访问运算符。 成员可以是字段、属性、事件或方法。 下面的示例对此进行了演示。  
  
 [!code-vb[VbVbcnConventions#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#14)]  
  
### <a name="exclamation-point--operator"></a>感叹号（！）操作员  
 仅对类或接口使用 `!` 运算符作为字典访问运算符。 类或接口必须具有接受单个 `String` 参数的默认属性。 紧跟在 `!` 运算符后面的标识符将成为作为字符串传递到默认属性的参数值。 下面的示例演示这一操作。  
  
 [!code-vb[VbVbcnConventions#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#15)]  
  
 `MsgBox` 的三个输出行均 `32856`显示值。 第一行使用对属性 `index`的传统访问，第二行使用 `index` 是类 `hasDefault`的默认属性的事实，第三行使用对类的字典访问。  
  
 请注意，`!` 运算符的第二个操作数必须是不用双引号（`" "`）括起来的有效 Visual Basic 标识符。 换句话说，您不能使用字符串文本或字符串变量。 对 `MsgBox` 调用的最后一行的以下更改将生成一个错误，因为 `"X"` 是包含的字符串文字。  
  
 `"Dictionary access returns " & hD!"X")`  
  
> [!NOTE]
> 对默认集合的引用必须是显式的。 特别是，不能对后期绑定变量使用 `!` 运算符。  
  
 `!` 字符还用作 `Single` 类型字符。  
  
## <a name="see-also"></a>另请参阅

- [程序结构和代码约定](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)
- [类型字符](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)
