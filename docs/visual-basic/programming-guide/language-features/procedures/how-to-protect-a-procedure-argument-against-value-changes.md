---
title: 如何：防止过程自变量的值被更改
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], arguments
- procedures [Visual Basic], parameters
- procedure arguments
- arguments [Visual Basic], passing by reference
- Visual Basic code, procedures
- arguments [Visual Basic], ByVal
- arguments [Visual Basic], passing by value
- procedure parameters
- procedures [Visual Basic], calling
- arguments [Visual Basic], ByRef
- arguments [Visual Basic], changing value
ms.assetid: d2b7c766-ce16-4d2c-8d79-3fc0e7ba2227
ms.openlocfilehash: 36092eb597b5b20e1da42cd9d15ab8633636cfb1
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344863"
---
# <a name="how-to-protect-a-procedure-argument-against-value-changes-visual-basic"></a>如何：防止过程自变量的值被更改 (Visual Basic)
如果过程将参数声明为[ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)，Visual Basic 将为过程代码提供对调用代码中参数的基础编程元素的直接引用。 这允许过程更改调用代码中参数的基础值。 在某些情况下，调用代码可能需要防止这种更改。  
  
 始终可以通过在过程中声明相应的参数[ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) ，来保护参数不受更改。 如果希望能够在某些情况下更改给定的参数，但不能在其他情况下更改，则可以 `ByRef` 将其声明，并让调用代码确定每个调用中的传递机制。 为此，可将相应的自变量括在括号中，以便按值传递它，或者不将其括在括号中，以便通过引用传递它。 有关详细信息，请参阅[如何：强制通过值传递参数](./how-to-force-an-argument-to-be-passed-by-value.md)。  
  
## <a name="example"></a>示例  
 下面的示例演示了两个过程，这些过程使用数组变量并对其元素进行操作。 `increase` 过程只是向每个元素添加一个。 `replace` 过程将新数组分配给参数 `a()` 然后向每个元素添加一个数组。 但是，重新分配不会影响调用代码中的基础数组变量。  
  
 [!code-vb[VbVbcnProcedures#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#35)]  
  
 [!code-vb[VbVbcnProcedures#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#38)]  
  
 [!code-vb[VbVbcnProcedures#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#37)]  
  
 第一个 `MsgBox` 调用显示 "增加（n）：11，21，31，41" 之后的 "。 由于数组 `n` 是引用类型，因此 `increase` 可以更改其成员，即使传递机制是 `ByVal`的。  
  
 第二个 `MsgBox` 调用显示 "replace （n）：11，21，31，41" 之后的。 由于 `n` 传递 `ByVal`，`replace` 无法通过向其分配新数组来修改调用代码中的变量 `n`。 如果 `replace` 创建新的数组实例 `k` 并将其分配给本地变量 `a`，则它将失去调用代码传入的 `n` 的引用。 当它更改 `a`的成员时，只会影响本地数组 `k`。 因此，`replace` 不会在调用代码中递增数组 `n` 的值。  
  
## <a name="compiling-the-code"></a>编译代码  
 Visual Basic 中的默认值是按值传递参数。 但是，将[ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)或[ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)关键字用于每个声明的参数是一种好的编程做法。 这使代码更易于阅读。  
  
## <a name="see-also"></a>另请参阅

- [过程](./index.md)
- [过程参数和自变量](./procedure-parameters-and-arguments.md)
- [如何：将自变量传递给过程](./how-to-pass-arguments-to-a-procedure.md)
- [按值和按引用传递自变量](./passing-arguments-by-value-and-by-reference.md)
- [可修改和不可修改自变量之间的差异](./differences-between-modifiable-and-nonmodifiable-arguments.md)
- [通过值传递自变量和通过引用传递自变量之间的差异](./differences-between-passing-an-argument-by-value-and-by-reference.md)
- [如何：更改过程自变量的值](./how-to-change-the-value-of-a-procedure-argument.md)
- [如何：强制通过值传递自变量](./how-to-force-an-argument-to-be-passed-by-value.md)
- [按位置和按名称传递自变量](./passing-arguments-by-position-and-by-name.md)
- [值类型和引用类型](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
