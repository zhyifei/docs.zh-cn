---
title: IsTrue 运算符
ms.date: 07/20/2015
f1_keywords:
- vb.istrue
helpviewer_keywords:
- IsTrue operator [Visual Basic]
- OrElse operator [Visual Basic]
ms.assetid: b6cec0f2-61b1-4331-a7f0-4d07ee3179d6
ms.openlocfilehash: 4b863eed8406a10b9a44d7139f8659ac5cb758ad
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349516"
---
# <a name="istrue-operator-visual-basic"></a>IsTrue 运算符 (Visual Basic)
确定表达式是否 `True`。  
  
 你不能在代码中显式调用 `IsTrue`，但 Visual Basic 编译器可以使用它从 `OrElse` 子句生成代码。 如果定义类或结构，然后在 `OrElse` 子句中使用该类型的变量，则必须在该类或结构上定义 `IsTrue`。  
  
 编译器将 `IsTrue` 和 `IsFalse` 运算符视为*匹配对*。 这意味着，如果定义其中一个类型，则还必须定义另一个。  
  
## <a name="compiler-use-of-istrue"></a>IsTrue 的编译器使用  
 定义了类或结构后，可以在 `For`、`If`、`Else If`或 `While` 语句中或 `When` 子句中使用该类型的变量。 如果执行此操作，则编译器需要一个运算符，该运算符将您的类型转换为 `Boolean` 值，以便它可以测试条件。 它按以下顺序搜索合适的运算符：  
  
1. 从你的类或结构到 `Boolean`的扩大转换运算符。  
  
2. 从你的类或结构到 `Boolean?`的扩大转换运算符。  
  
3. 类或结构上的 `IsTrue` 运算符。  
  
4. 到不涉及从 `Boolean` 到 `Boolean?`的转换的 `Boolean?` 的收缩转换。  
  
5. 要 `Boolean`的类或结构中的收缩转换运算符。  
  
 如果未定义任何到 `Boolean` 或 `IsTrue` 运算符的转换，则编译器会发出错误消息。  
  
> [!NOTE]
> 可以*重载*`IsTrue` 运算符，这意味着当类或结构的操作数具有该类或结构的类型时，它可以重新定义其行为。 如果你的代码在该类或结构上使用此运算符，请确保了解其重新定义的行为。 有关更多信息，请参见 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)。  
  
## <a name="example"></a>示例  
 下面的代码示例定义了结构的轮廓，该结构包含 `IsFalse` 和 `IsTrue` 运算符的定义。  
  
 [!code-vb[VbVbalrOperators#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#28)]  
  
## <a name="see-also"></a>另请参阅

- [IsFalse 运算符](../../../visual-basic/language-reference/operators/isfalse-operator.md)
- [如何：定义运算符](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [OrElse 运算符](../../../visual-basic/language-reference/operators/orelse-operator.md)
