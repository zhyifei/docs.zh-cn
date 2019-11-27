---
title: IsFalse 运算符
ms.date: 07/20/2015
f1_keywords:
- vb.isfalse
helpviewer_keywords:
- AndAlso operator [Visual Basic]
- IsFalse operator [Visual Basic]
ms.assetid: 37fc9dbf-e5cc-4570-b93f-7213447974df
ms.openlocfilehash: 51b7bfb2cf5301a39818e6566b408ee0677689f2
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349519"
---
# <a name="isfalse-operator-visual-basic"></a>IsFalse 运算符 (Visual Basic)
确定表达式是否 `False`。  
  
 你不能在代码中显式调用 `IsFalse`，但 Visual Basic 编译器可以使用它从 `AndAlso` 子句生成代码。 如果定义类或结构，然后在 `AndAlso` 子句中使用该类型的变量，则必须在该类或结构上定义 `IsFalse`。  
  
 编译器将 `IsFalse` 和 `IsTrue` 运算符视为*匹配对*。 这意味着，如果定义其中一个类型，则还必须定义另一个。  
  
> [!NOTE]
> 可以*重载*`IsFalse` 运算符，这意味着当类或结构的操作数具有该类或结构的类型时，它可以重新定义其行为。 如果你的代码在该类或结构上使用此运算符，请确保了解其重新定义的行为。 有关更多信息，请参见 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)。  
  
## <a name="example"></a>示例  
 下面的代码示例定义了结构的轮廓，该结构包含 `IsFalse` 和 `IsTrue` 运算符的定义。  
  
 [!code-vb[VbVbalrOperators#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#28)]  
  
## <a name="see-also"></a>另请参阅

- [IsTrue 运算符](../../../visual-basic/language-reference/operators/istrue-operator.md)
- [如何：定义运算符](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [AndAlso 运算符](../../../visual-basic/language-reference/operators/andalso-operator.md)
