---
title: 复合数据类型
ms.date: 04/25/2017
helpviewer_keywords:
- classes [Visual Basic], composite data types
- composite types [Visual Basic]
- composite data types [Visual Basic]
- data types [Visual Basic], composite
- arrays [Visual Basic], composite data types
- structures [Visual Basic], composite data types
- classes [Visual Basic], composite types
- types [Visual Basic], composite
ms.assetid: 62970f2e-52c0-4369-8963-613820f1f434
ms.openlocfilehash: 1c099c5082f1c4173a50c70998c99135c94821e6
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346373"
---
# <a name="composite-data-types-visual-basic"></a>复合数据类型 (Visual Basic)
除了 Visual Basic 提供的基本数据类型之外，还可以组合不同类型的项来创建*复合数据类型*，例如结构、数组和类。 您可以从基本类型和其他复合类型构建复合数据类型。 例如，可以定义结构元素数组或包含数组成员的结构。  
  
## <a name="data-types"></a>数据类型  
 复合类型不同于它的任何组件的数据类型。 例如，`Integer` 元素数组的数据类型不是 `Integer`。  
  
 数组数据类型通常使用元素类型、括号和逗号来表示（如有必要）。 例如，`String` 元素的一维数组表示为 `String()`，而 `Boolean` 元素的二维数组表示为 `Boolean(,)`。  
  
## <a name="structure-types"></a>结构类型  
 没有一种数据类型包含所有结构。 相反，结构的每个定义都表示唯一的数据类型，即使两个结构以相同顺序定义相同的元素也是如此。 但是，如果创建相同结构的两个或多个实例，Visual Basic 会将它们视为相同的数据类型。  
  
## <a name="tuples"></a>Tuples

元组是一种轻型结构，它包含两个或更多已预定义类型的字段。 从 Visual Basic 2017 开始支持元组。 元组通常用于从单个方法调用返回多个值，而无需通过引用传递自变量，也不需要在更高权重的类或结构中打包返回字段。 有关元组的详细信息，请参阅[元组](tuples.md)主题。

## <a name="array-types"></a>数组类型  
 没有一种数据类型包含所有数组。 数组的特定实例的数据类型由以下内容确定：  
  
- 成为数组的事实  
  
- 数组的秩（维数）  
  
- 数组的元素类型  
  
 具体而言，给定维度的长度不是该实例的数据类型的一部分。 下面的示例阐释了这一点。  
  
```vb  
Dim arrayA( ) As Byte = New Byte(12) {}  
Dim arrayB( ) As Byte = New Byte(100) {}  
Dim arrayC( ) As Short = New Short(100) {}  
Dim arrayD( , ) As Short  
Dim arrayE( , ) As Short = New Short(4, 10) {}  
```  
  
 在前面的示例中，数组变量 `arrayA` 和 `arrayB` 被视为具有相同的数据类型（`Byte()`），即使它们被初始化为不同的长度。 变量 `arrayB` 和 `arrayC` 不属于同一类型，因为它们的元素类型不同。 变量 `arrayC` 和 `arrayD` 不属于同一类型，因为它们的秩不同。 变量 `arrayD` 和 `arrayE` 具有相同的类型（`Short(,)`），因为它们的秩和元素类型是相同的，即使尚未初始化 `arrayD` 也是如此。  
  
 有关数组的详细信息，请参阅[数组](../../../../visual-basic/programming-guide/language-features/arrays/index.md)。  
  
## <a name="class-types"></a>类类型  
 没有一种数据类型包含所有类。 尽管一个类可以继承自另一个类，但每个类都是单独的数据类型。 同一类的多个实例具有相同的数据类型。 如果您将一个类实例变量分配给另一个类，则不仅可以使用相同的数据类型，它们指向内存中的同一个类实例。  
  
 有关类的详细信息，请参阅[对象和类](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)。  
  
## <a name="see-also"></a>另请参阅

- [数据类型](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [基本数据类型](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)
- [Visual Basic 中的泛型类型](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [值类型和引用类型](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
- [Visual Basic 中的类型转换](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [结构](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [数据类型疑难解答](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [如何：在一个变量中保存多个值](../../../../visual-basic/programming-guide/language-features/data-types/how-to-hold-more-than-one-value-in-a-variable.md)
