---
title: 如何：强制通过值传递自变量
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], arguments
- procedures [Visual Basic], parameters
- procedure arguments
- Visual Basic code, procedures
- arguments [Visual Basic], ByVal
- arguments [Visual Basic], passing by value
- procedure parameters
- procedures [Visual Basic], calling
- arguments [Visual Basic], in parentheses
- procedure arguments [Visual Basic], in parentheses
- arguments [Visual Basic], changing value
ms.assetid: 77b4f2d2-1055-4c2f-a521-874d1db86946
ms.openlocfilehash: 047738a2cbadc6b7d72f41aade22bbeff16d1bac
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/25/2019
ms.locfileid: "75347584"
---
# <a name="how-to-force-an-argument-to-be-passed-by-value-visual-basic"></a>如何：强制通过值传递参数 (Visual Basic)
过程声明确定传递机制。 如果参数声明为[ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)，则 Visual Basic 要求按引用传递相应的参数。 这使过程可以更改调用代码中参数的基础编程元素的值。 如果要针对此类更改保护基础元素，则可以通过将参数名称括在括号中来覆盖过程调用中的 `ByRef` 传递机制。 除了在调用中包含参数列表的括号外，还需要用到这些括号。  
  
 调用代码无法重写[ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)机制。  
  
### <a name="to-force-an-argument-to-be-passed-by-value"></a>强制按值传递参数  
  
- 如果在过程中 `ByVal` 声明相应的参数，则无需执行任何其他步骤。 Visual Basic 已经要求按值传递参数。  
  
- 如果在过程中 `ByRef` 声明相应的参数，请在过程调用中将参数括在括号中。  
  
## <a name="example"></a>示例  
 下面的示例重写 `ByRef` 参数声明。 在强制 `ByVal`的调用中，请注意括号的两个级别。  
  
 [!code-vb[VbVbcnProcedures#39](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#39)]  
  
 [!code-vb[VbVbcnProcedures#40](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#40)]  
  
 当 `str` 用参数列表中的额外括号括起来时，`setNewString` 过程无法在调用代码中更改其值，`MsgBox` 将显示 "如果传递了 ByVal，则无法替换"。 如果 `str` 未括在额外的括号中，则过程可以更改它，并且 `MsgBox` 显示 "这是 inString 自变量的新值"。  
  
## <a name="compile-the-code"></a>编译代码  
 通过引用传递变量时，必须使用 `ByRef` 关键字来指定此机制。  
  
 Visual Basic 中的默认值是按值传递参数。 但是，将[ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)或[ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)关键字用于每个声明的参数是一种好的编程做法。 这使代码更易于阅读。  
  
## <a name="robust-programming"></a>可靠的编程  
 如果过程声明了参数[ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)，代码的正确执行可能取决于是否能够更改调用代码中的基础元素。 如果调用代码通过将参数括在括号中来重写此调用机制，或者如果传递了不可修改参数，则该过程不能更改基础元素。 这可能会在调用代码中产生意外结果。  
  
## <a name="net-framework-security"></a>.NET Framework 安全性  
 允许过程更改调用代码中参数的基础值始终存在潜在风险。 请确保此值已更改，并在使用之前对其进行检查以确保其有效性。  
  
## <a name="see-also"></a>另请参阅

- [过程](./index.md)
- [过程参数和自变量](./procedure-parameters-and-arguments.md)
- [如何：将自变量传递给过程](./how-to-pass-arguments-to-a-procedure.md)
- [按值和按引用传递自变量](./passing-arguments-by-value-and-by-reference.md)
- [可修改和不可修改自变量之间的差异](./differences-between-modifiable-and-nonmodifiable-arguments.md)
- [通过值传递自变量和通过引用传递自变量之间的差异](./differences-between-passing-an-argument-by-value-and-by-reference.md)
- [如何：更改过程自变量的值](./how-to-change-the-value-of-a-procedure-argument.md)
- [如何：防止过程自变量的值被更改](./how-to-protect-a-procedure-argument-against-value-changes.md)
- [按位置和按名称传递自变量](./passing-arguments-by-position-and-by-name.md)
- [值类型和引用类型](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
