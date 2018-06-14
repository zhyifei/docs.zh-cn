---
title: 通过值和通过引用传递自变量 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- ByRef keyword [Visual Basic], passing arguments by reference
- Visual Basic code, procedures
- passing arguments [Visual Basic], by value or by reference
- ByVal keyword [Visual Basic], passing arguments by value
- arguments [Visual Basic], passing by value or by reference
- argument passing [Visual Basic], by value or by reference
ms.assetid: fd8a9de6-7178-44d5-a9bf-458d4ad907c2
ms.openlocfilehash: 2d333bc873ba055d7a7b53c50fcfeec4cc0f9491
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33654172"
---
# <a name="passing-arguments-by-value-and-by-reference-visual-basic"></a>通过值和通过引用传递自变量 (Visual Basic)
在 Visual Basic 中，可以传递了参数给过程*按值*或*通过引用*。 这称为*传递机制*，同时确定过程是否可以修改调用代码中的以该参数基础的编程元素。 过程声明确定每个参数的传递机制，通过指定[ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)或[ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)关键字。  
  
## <a name="distinctions"></a>区别  
 如果将参数传递给过程中，应注意的彼此交互的几点差异：  
  
-   基础的编程元素是可修改或不可修改  
  
-   自变量本身是可修改或不可修改  
  
-   自变量通过值还是引用传递  
  
-   参数数据类型是否是值类型或引用类型  
  
 有关详细信息，请参阅[差异之间可修改和不可修改自变量](./differences-between-modifiable-and-nonmodifiable-arguments.md)和[差异之间传递自变量传递的值和按引用](./differences-between-passing-an-argument-by-value-and-by-reference.md)。  
  
## <a name="choice-of-passing-mechanism"></a>选择的传递机制  
 你应该选择仔细为每个参数的传递机制。  
  
-   **保护**。 在两个传递机制之间进行选择，最重要的标准是要更改的调用变量公开。 传递自变量的优点`ByRef`是过程可以返回到调用代码通过该自变量的值。 传递自变量的优点`ByVal`是它可防止变量被过程正在更改。  
  
-   **性能**。 尽管的传递机制可能会影响代码的性能，区别在于通常无意义。 一个例外是值类型传递`ByVal`。 在这种情况下，Visual Basic 将复制自变量的整个数据内容。 因此，较大的值类型，如一个结构，它可以更高效，以将其传递`ByRef`。  
  
     对于引用类型，仅指向的数据为复制 （四个字节在 32 位平台上，在 64 位平台上的 8 个字节）。 因此，你可以将类型自变量传递`String`或`Object`的值，从而不会降低性能。  
  
## <a name="determination-of-the-passing-mechanism"></a>确定的传递机制  
 过程声明指定每个参数的传递机制。 调用的代码不能重写`ByVal`机制。  
  
 如果参数用声明`ByRef`，调用代码可以强制机制来`ByVal`通过将在调用中的括号中的自变量名称。 有关详细信息，请参阅[如何： 强制通过值传递到自变量](./how-to-force-an-argument-to-be-passed-by-value.md)。  
  
 Visual Basic 中的默认值是通过值传递自变量。  
  
## <a name="when-to-pass-an-argument-by-value"></a>何时通过值传递自变量  
  
-   如果基础自变量调用的代码元素是不可修改的元素，声明对应的形参[ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)。 没有代码可以更改不可修改的元素的值。  
  
-   如果基础元素是可修改，但不是希望能够更改其值的过程，将参数声明`ByVal`。 仅调用代码可以更改可修改元素的值传递的值。  
  
## <a name="when-to-pass-an-argument-by-reference"></a>何时通过引用传递自变量  
  
-   如果过程有正版需要更改中调用代码的基础元素，声明对应的形参[ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)。  
  
-   如果代码正确执行依赖于更改中调用代码的基础元素的过程，将参数声明`ByRef`。 如果将其传递的值，或者调用代码重写`ByRef`传递机制，通过将实参括在括号内，过程调用可能会产生意外的结果。  
  
## <a name="example"></a>示例  
  
### <a name="description"></a>描述  
 下面的示例演示了何时通过值传递自变量以及何时将它们通过引用传递。 过程`Calculate`同时具有`ByVal`和`ByRef`参数。 给定利率， `rate`，和的金额，总和`debt`，该过程的任务是计算为的新值`debt`，它是对应用的结果利率的原始值`debt`。 因为`debt`是`ByRef`参数，对应于调用代码中的自变量的值中反映新的总计`debt`。 参数`rate`是`ByVal`参数因为`Calculate`不应更改其值。  
  
### <a name="code"></a>代码  
 [!code-vb[VbVbcnProcedures#74](./codesnippet/VisualBasic/passing-arguments-by-value-and-by-reference_1.vb)]  
  
## <a name="see-also"></a>请参阅  
 [过程](./index.md)  
 [过程参数和自变量](./procedure-parameters-and-arguments.md)  
 [如何：将自变量传递给过程](./how-to-pass-arguments-to-a-procedure.md)  
 [如何：更改过程自变量的值](./how-to-change-the-value-of-a-procedure-argument.md)  
 [如何：防止过程自变量的值被更改](./how-to-protect-a-procedure-argument-against-value-changes.md)  
 [如何：强制通过值传递自变量](./how-to-force-an-argument-to-be-passed-by-value.md)  
 [按位置和按名称传递自变量](./passing-arguments-by-position-and-by-name.md)  
 [值类型和引用类型](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
