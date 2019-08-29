---
title: 字符数据类型 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- data types [Visual Basic], character
- String data type [Visual Basic], character data types
- character data types [Visual Basic]
- Char data type [Visual Basic], character data types
- data types [Visual Basic], choosing
ms.assetid: 902479ef-1679-47fc-9911-0c1c5008226c
ms.openlocfilehash: d29e8771d61c04cf35aa71b5ba7fbba0d308c730
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69965680"
---
# <a name="character-data-types-visual-basic"></a>字符数据类型 (Visual Basic)
Visual Basic 提供了用于处理可打印和可显示字符的*字符数据类型*。 虽然这两种方法都能处理`Char` Unicode 字符, 但包含`String`一个字符, 但包含无数个字符。  
  
 有关显示 Visual Basic 数据类型的并行比较的表, 请参阅[数据类型](../../../../visual-basic/language-reference/data-types/index.md)。  
  
## <a name="char-type"></a>Char 类型  
 `Char`数据类型是单个双字节 (16 位) Unicode 字符。 如果变量始终只存储一个字符, 则将其声明`Char`为。 例如:  
  
 [!code-vb[VbVbalrCharTypes#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrchartypes/vb/module1.vb#1)]
  
 `Char` 或`String`变量中的每个可能值都是 Unicode 字符集中的一个*码位*或字符代码。 Unicode 字符包含基本 ASCII 字符集、各种其他字母数字、重音、货币符号、分数、音调符号和数学符号以及技术符号。  
  
> [!NOTE]
> Unicode 字符集为*代理项对*保留了 D800 到 DFFF (55296 到 55551 decimal) 的代码点, 这需要 2 16 位值来表示单个码位。 变量不能包含代理项对, `String`且使用两个位置来保存这种对。 `Char`  
  
 有关详细信息, 请参阅[Char Data Type](../../../../visual-basic/language-reference/data-types/char-data-type.md)。  
  
## <a name="string-type"></a>字符串类型  
 `String`数据类型是由零个或多个双字节 (16 位) Unicode 字符组成的序列。 如果变量可以包含无限数量的字符, 则将其声明为`String`。 例如:  
  
 [!code-vb[VbVbalrCharTypes#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrchartypes/vb/module1.vb#2)]
  
 有关详细信息, 请参阅[String 数据类型](../../../../visual-basic/language-reference/data-types/string-data-type.md)。  
  
## <a name="see-also"></a>请参阅

- [基本数据类型](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)
- [复合数据类型](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)
- [Generic Types in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
- [Visual Basic 中的类型转换](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [数据类型疑难解答](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [类型字符](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)
