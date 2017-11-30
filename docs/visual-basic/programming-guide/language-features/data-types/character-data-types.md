---
title: "字符数据类型 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- data types [Visual Basic], character
- String data type [Visual Basic], character data types
- character data types [Visual Basic]
- Char data type [Visual Basic], character data types
- data types [Visual Basic], choosing
ms.assetid: 902479ef-1679-47fc-9911-0c1c5008226c
caps.latest.revision: "23"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d1066444ba3a98f26fc2a35135a50b2954c6b992
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="character-data-types-visual-basic"></a>字符数据类型 (Visual Basic)
[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]提供*字符数据类型*来处理可打印和可显示的字符。 尽管它们都使用 Unicode 字符，处理`Char`包含单个字符，而`String`包含的字符数量不确定。  
  
 有关的表，显示的并排显示比较[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]数据类型，请参阅[数据类型](../../../../visual-basic/language-reference/data-types/data-type-summary.md)。  
  
## <a name="char-type"></a>Char 类型  
 `Char`数据类型是一个单一的两个字节 （16 位） Unicode 字符。 如果某个变量始终存储恰好一个字符，将其声明为`Char`。 例如:   
  
 [!code-vb[VbVbalrCharTypes#1](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/character-data-types_1.vb)]  
  
 在每个可能值`Char`或`String`变量是*代码点*，或字符代码，在 Unicode 字符集。 Unicode 字符包含基本 ASCII 字符集、 各种其他字母、 重音符号、 货币符号、 分数 （竖式）、 标注字符和数学和技术符号。  
  
> [!NOTE]
>  Unicode 字符集的代码点 D800 到 DFFF (十进制是从 55296 到 55551) 有关的预留*代理项对*，这需要两个 16 位值来表示单个码位。 A`Char`变量不能包含代理项对，和一个`String`使用两个位置来保存此类对。  
  
 有关详细信息，请参阅[Char 数据类型](../../../../visual-basic/language-reference/data-types/char-data-type.md)。  
  
## <a name="string-type"></a>字符串类型  
 `String`数据类型是零个或多个双字节 （16 位） Unicode 字符序列。 如果变量可以包含任意个数的字符，将其声明为`String`。 例如:   
  
 [!code-vb[VbVbalrCharTypes#2](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/character-data-types_2.vb)]  
  
 有关详细信息，请参阅[字符串数据类型](../../../../visual-basic/language-reference/data-types/string-data-type.md)。  
  
## <a name="see-also"></a>另请参阅  
 [基本数据类型](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)  
 [复合数据类型](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)  
 [Visual Basic 中的泛型类型](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)  
 [值类型和引用类型](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)  
 [在 Visual Basic 中的类型转换](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)  
 [数据类型疑难解答](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 [类型字符](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)
