---
title: "如何：在一个变量中保存多个值 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: c8c567ec2ba01d094819c98a2937af75cd105956
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-hold-more-than-one-value-in-a-variable-visual-basic"></a>如何：在一个变量中保存多个值 (Visual Basic)
变量包含多个值，如果将其的声明*复合数据类型*。  
  
 [复合数据类型](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)包括结构、 数组和类。 复合数据类型的变量可以包含基本数据类型和其他复合类型的组合。 结构和类可以保存代码，以及数据。  
  
### <a name="to-hold-more-than-one-value-in-a-variable"></a>在变量中保存多个值  
  
1.  确定想要用于您定义的变量复合数据类型。  
  
2.  如果尚未定义的复合数据类型，定义它，以便你的变量可以使用它。  
  
    -   定义具有的结构[Structure 语句](../../../../visual-basic/language-reference/statements/structure-statement.md)。  
  
    -   定义具有数组[Dim 语句](../../../../visual-basic/language-reference/statements/dim-statement.md)。  
  
    -   使用定义类[类语句](../../../../visual-basic/language-reference/statements/class-statement.md)。  
  
3.  声明具有你变量`Dim`语句。  
  
4.  变量名后面加`As`子句。  
  
5.  请按照`As`关键字适当的复合数据类型的名称。  
  
## <a name="see-also"></a>另请参阅  
 [数据类型](../../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [类型字符](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)  
 [复合数据类型](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)  
 [结构](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [阵列](../../../../visual-basic/programming-guide/language-features/arrays/index.md)  
 [对象和类](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)  
 [值类型和引用类型](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
