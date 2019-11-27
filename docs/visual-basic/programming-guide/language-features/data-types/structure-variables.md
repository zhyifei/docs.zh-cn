---
title: 结构变量
ms.date: 07/20/2015
helpviewer_keywords:
- structures [Visual Basic], variables
- structures [Visual Basic], structure variables
- variables [Visual Basic], structure variables
- structure variables [Visual Basic]
ms.assetid: 156872f8-aabc-4454-8e2d-f2253c3c13c9
ms.openlocfilehash: 16b6cdc5a849b50f6caa8b7963dac5c12d63cf3e
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346296"
---
# <a name="structure-variables-visual-basic"></a>结构变量 (Visual Basic)

创建结构后，可以声明该类型的过程级和模块级变量。 例如，可以创建一个结构来记录有关计算机系统的信息。 下面的示例演示这一操作。

```vb
Public Structure systemInfo
    Public cPU As String
    Public memory As Long
    Public purchaseDate As Date
End Structure
```

现在可以声明该类型的变量。 下面的声明阐释了这一点。

```vb
Dim mySystem, yourSystem As systemInfo
```

> [!NOTE]
> 在类和模块中，使用[Dim 语句](../../../../visual-basic/language-reference/statements/dim-statement.md)声明的结构默认为公共访问。 如果要将结构设置为私有，请确保使用[private](../../../../visual-basic/language-reference/modifiers/private.md)关键字对其进行声明。

## <a name="access-to-structure-values"></a>对结构值的访问

若要分配和检索结构变量的元素中的值，请使用与用于设置和获取对象属性相同的语法。 将成员访问运算符（`.`）放置在结构变量名和元素名之间。 下面的示例访问之前声明为类型 `systemInfo`的变量元素。

```vb
mySystem.cPU = "486"
Dim tooOld As Boolean
If yourSystem.purchaseDate < #1/1/1992# Then tooOld = True
```

## <a name="assigning-structure-variables"></a>分配结构变量

如果两个变量具有相同的结构类型，则也可以将其分配给另一个变量。 这会将一个结构的所有元素复制到另一个结构中的相应元素。 下面的声明阐释了这一点。

```vb
yourSystem = mySystem
```

如果结构元素是引用类型（如 `String`、`Object`或数组），则会复制指向数据的指针。 在前面的示例中，如果 `systemInfo` 包含一个对象变量，则前面的示例会将指针从 `mySystem` 复制到 `yourSystem`，并且通过一个结构对该对象的数据的更改将在通过其他结构访问时生效。

## <a name="see-also"></a>另请参阅

- [数据类型](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [基本数据类型](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)
- [复合数据类型](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)
- [值类型和引用类型](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
- [结构](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [数据类型疑难解答](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [如何：声明结构](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
- [结构和其他编程元素](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-other-programming-elements.md)
- [结构和类](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md)
- [Structure 语句](../../../../visual-basic/language-reference/statements/structure-statement.md)
