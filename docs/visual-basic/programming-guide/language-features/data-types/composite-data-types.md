---
title: 复合数据类型 (Visual Basic)
ms.custom: ''
ms.date: 04/25/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
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
caps.latest.revision: 19
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: caa832fc191ad925674e21b1237ac98328ce0bd7
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="composite-data-types-visual-basic"></a>复合数据类型 (Visual Basic)
除了基本数据类型 Visual Basic 提供，也可以组合不同的类型创建的项目*复合数据类型*如结构、 数组和类。 基本类型和其他复合类型，你可以构建复合数据类型。 例如，可以与数组成员中定义的结构元素的数组或结构。  
  
## <a name="data-types"></a>数据类型  
 复合类型是不同的任一种情况及其组件的数据类型。 例如，数组的`Integer`元素不属于`Integer`数据类型。  
  
 数组数据类型通常表示根据需要使用元素类型、 圆括号和逗号。 例如，一维数组的`String`元素表示为`String()`，和一个二维数组的`Boolean`元素表示为`Boolean(,)`。  
  
## <a name="structure-types"></a>结构类型  
 不存在包含所有结构的单个数据类型。 相反，每个定义的结构表示唯一的数据类型，即使两个结构定义相同的元素顺序相同。 但是，如果你创建具有相同结构的两个或多个实例，则 Visual Basic 将认为它们是相同的数据类型。  
  
## <a name="tuples"></a>元组

元组是包含其类型预定义的两个或多个字段的轻量结构。 从 Visual Basic 自 2017 年开始支持元组。 元组通常用于从单个方法调用返回多个值，而无需通过引用传递自变量或打包多重型的类或结构中返回的字段。 请参阅[元组](tuples.md)元组的详细信息的主题。

## <a name="array-types"></a>数组类型  
 不存在包含所有数组的单个数据类型。 由以下确定数组的特定实例的数据类型：  
  
-   确实为数组  
  
-   数组的秩 （维数）  
  
-   数组的元素类型  
  
 具体而言，给定维度的长度不是实例的数据类型的一部分。 下面的示例阐释了这一点。  
  
```  
Dim arrayA( ) As Byte = New Byte(12) {}  
Dim arrayB( ) As Byte = New Byte(100) {}  
Dim arrayC( ) As Short = New Short(100) {}  
Dim arrayD( , ) As Short  
Dim arrayE( , ) As Short = New Short(4, 10) {}  
```  
  
 在前面的示例中，数组变量`arrayA`和`arrayB`被视为相同的数据类型- `Byte()` — 即使它们将初始化为不同长度也是如此。 变量`arrayB`和`arrayC`不属于同一类型，因为它们的元素类型不同。 变量`arrayC`和`arrayD`不属于同一类型，因为它们的秩不同。 变量`arrayD`和`arrayE`具有相同的类型- `Short(,)` -因为它们的秩和元素类型是相同的即使`arrayD`尚未初始化。  
  
 在阵列上的详细信息，请参阅[数组](../../../../visual-basic/programming-guide/language-features/arrays/index.md)。  
  
## <a name="class-types"></a>类类型  
 不存在包含所有类的单个数据类型。 尽管一个类可以从另一个类继承的每个是单独的数据类型。 同一个类的多个实例均为相同的数据类型。 如果将一个类实例变量分配到另一个，不仅它们具有相同的数据类型，它们指向内存中的同一个类实例。  
  
 类的详细信息，请参阅[对象和类](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)。  
  
## <a name="see-also"></a>请参阅  
 [数据类型](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 [基本数据类型](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)  
 [Visual Basic 中的泛型类型](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)  
 [值类型和引用类型](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)  
 [在 Visual Basic 中的类型转换](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)  
 [结构](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [数据类型疑难解答](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 [如何：在一个变量中保存多个值](../../../../visual-basic/programming-guide/language-features/data-types/how-to-hold-more-than-one-value-in-a-variable.md)
