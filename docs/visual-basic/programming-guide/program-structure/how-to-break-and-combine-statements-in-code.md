---
title: 如何：在代码中拆分和合并语句 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb._
helpviewer_keywords:
- colons (:)
- line continuation
- _ line-continuation character
- ': line separator character'
- Visual Basic code, line breaks in
- Visual Basic code, line breaks
- Visual Basic code, line continuation
- long lines of code
- line terminator
- line-continuation sequence
- underscores [Visual Basic], in code
- statements [Visual Basic], line continuation in
- line breaks [Visual Basic], in code
- line-continuation character [Visual Basic]
- Visual Basic code, line continuation in
- statements [Visual Basic], line breaks in
ms.assetid: dea01dad-a8ac-484a-bb3a-8c45a1b1eccc
ms.openlocfilehash: 6bca3d62cb3e886ee08b9169d63d4c3a38247f3f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-break-and-combine-statements-in-code-visual-basic"></a>如何：在代码中拆分和合并语句 (Visual Basic)
当编写代码时，你有时可能会创建一些冗长需要水平滚动在代码编辑器中的语句。 尽管这不会影响的方式代码运行，这使得困难为你或任何其他人阅读代码，因为在监视器上显示。 在这种情况下，你应考虑将单个长语句拆分为多个行。  
  
### <a name="to-break-a-single-statement-into-multiple-lines"></a>若要拆分为多行的单个语句  
  
-   使用行继续符，它是一个下划线 (`_`)，在您想要中断的行的点。 该下划线必须紧跟在空格后，并且在它后面紧跟行终止符（回车）。  
  
    > [!NOTE]
    >  在某些情况下，如果省略行继续符，Visual Basic 编译器将隐式 continue 语句在下一行代码上。 有关可以为其省略行继续符的语法元素的列表，请参阅"隐式行继续符"[语句](../../../visual-basic/programming-guide/language-features/statements.md)。  
  
     在下面的示例中，该语句将划分成四个行与行继续符终止所有但最后一行。  
  
     [!code-vb[VbVbcnConventions#20](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/how-to-break-and-combine-statements-in-code_1.vb)]  
  
     使用此序列使得你的代码易于阅读，不管是联机还是在打印。  
  
     行继续符必须在行上的最后一个字符。 你不能与它与任何其他内容相同的行。  
  
     存在一些限制，可以使用行继续符中;例如，你无法使用它中间自变量名称。 你可以中断自变量列表与行继续符，但自变量的单个名称必须保持不变。  
  
     通过使用行继续符将无法继续注释。 编译器不检查具有特殊含义的注释中的字符。 对于多行注释，请重复注释符号 (`'`) 在每一行上。  
  
 尽管推荐的方法是将每个语句放在单独的行，Visual Basic 还允许你在同一行上放置多个语句。  
  
### <a name="to-place-multiple-statements-on-the-same-line"></a>若要在同一行上放置多个语句  
  
-   用冒号分隔的语句 (`:`)，如下面的示例。  
  
     [!code-vb[VbVbcnConventions#10](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/how-to-break-and-combine-statements-in-code_2.vb)]  
  
## <a name="see-also"></a>请参阅  
 [程序结构和代码约定](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)  
 [语句](../../../visual-basic/programming-guide/language-features/statements.md)
