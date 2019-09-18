---
title: 如何：在一个变量中保存多个值（Visual Basic）
ms.date: 07/20/2015
helpviewer_keywords:
- classes [Visual Basic], composite data types
- composite types [Visual Basic]
- composite data types [Visual Basic]
- data types [Visual Basic], composite
- arrays [Visual Basic], composite data types
- structures [Visual Basic], composite data types
- arrays [Visual Basic], compilation errors
- types [Visual Basic], composite
ms.assetid: 5fe0e558-aac2-4a40-b7f2-7cfea7336917
ms.openlocfilehash: 8d07a34a98303f9d220dba0a3c955120b421340e
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/17/2019
ms.locfileid: "71054198"
---
# <a name="how-to-hold-more-than-one-value-in-a-variable-visual-basic"></a>如何：在一个变量中保存多个值（Visual Basic）

如果将变量声明为*复合数据类型*，则该变量包含多个值。

[复合数据类型](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)包括结构、数组和类。 复合数据类型的变量可以包含基本数据类型和其他复合类型的组合。 结构和类可以保存代码以及数据。

## <a name="to-hold-more-than-one-value-in-a-variable"></a>在一个变量中保存多个值

1. 确定要为变量使用哪种复合数据类型。

2. 如果尚未定义复合数据类型，请对其进行定义，使变量可以使用它。

    - 使用[结构语句](../../../../visual-basic/language-reference/statements/structure-statement.md)定义结构。

    - 定义带有[Dim 语句](../../../../visual-basic/language-reference/statements/dim-statement.md)的数组。

    - 使用[类语句](../../../../visual-basic/language-reference/statements/class-statement.md)定义类。

3. 使用`Dim`语句声明变量。

4. 使用`As`子句的变量名称。

5. 在`As`关键字后跟适当的复合数据类型的名称。

## <a name="see-also"></a>请参阅

- [数据类型](../../../../visual-basic/language-reference/data-types/index.md)
- [类型字符](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)
- [复合数据类型](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)
- [结构](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [数组](../../../../visual-basic/programming-guide/language-features/arrays/index.md)
- [对象和类](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
- [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
