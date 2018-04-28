---
title: 字符数据类型 (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- data types [Visual Basic], character
- String data type [Visual Basic], character data types
- character data types [Visual Basic]
- Char data type [Visual Basic], character data types
- data types [Visual Basic], choosing
ms.assetid: 902479ef-1679-47fc-9911-0c1c5008226c
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: afd368c00444f136c6d69b02a733c82f0c8eafe0
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2018
---
# <a name="character-data-types-visual-basic"></a>字符数据类型 (Visual Basic)
Visual Basic 提供*字符数据类型*来处理可打印和可显示的字符。 尽管它们都使用 Unicode 字符，处理`Char`包含单个字符，而`String`包含的字符数量不确定。  
  
 显示 Visual Basic 数据类型的并排显示比较表，请参阅[数据类型](../../../../visual-basic/language-reference/data-types/data-type-summary.md)。  
  
## <a name="char-type"></a>Char 类型  
 `Char`数据类型是一个单一的两个字节 （16 位） Unicode 字符。 如果某个变量始终存储恰好一个字符，将其声明为`Char`。 例如：  
  
 [!code-vb[VbVbalrCharTypes#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrchartypes/vb/module1.vb#1)]
  
 在每个可能值`Char`或`String`变量是*代码点*，或字符代码，在 Unicode 字符集。 Unicode 字符包含基本 ASCII 字符集、 各种其他字母、 重音符号、 货币符号、 分数 （竖式）、 标注字符和数学和技术符号。  
  
> [!NOTE]
>  Unicode 字符集的代码点 D800 到 DFFF (十进制是从 55296 到 55551) 有关的预留*代理项对*，这需要两个 16 位值来表示单个码位。 A`Char`变量不能包含代理项对，和一个`String`使用两个位置来保存此类对。  
  
 有关详细信息，请参阅[Char 数据类型](../../../../visual-basic/language-reference/data-types/char-data-type.md)。  
  
## <a name="string-type"></a>字符串类型  
 `String`数据类型是零个或多个双字节 （16 位） Unicode 字符序列。 如果变量可以包含任意个数的字符，将其声明为`String`。 例如：  
  
 [!code-vb[VbVbalrCharTypes#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrchartypes/vb/module1.vb#2)]
  
 有关详细信息，请参阅[字符串数据类型](../../../../visual-basic/language-reference/data-types/string-data-type.md)。  
  
## <a name="see-also"></a>请参阅  
 [基本数据类型](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)  
 [复合数据类型](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)  
 [Visual Basic 中的泛型类型](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)  
 [值类型和引用类型](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)  
 [在 Visual Basic 中的类型转换](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)  
 [数据类型疑难解答](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 [类型字符](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)
