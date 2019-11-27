---
title: 字符串操作方法的类型
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], manipulating [Visual Basic]
- string manipulation
ms.assetid: 905055cd-7f50-48fb-9eed-b0995af1dc1f
ms.openlocfilehash: a02278abfb71efb2f31f239a89a22ad1c8ee7a18
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346272"
---
# <a name="types-of-string-manipulation-methods-in-visual-basic"></a>字符串操作方法的类型 (Visual Basic)
可以通过多种不同的方法来分析和操作字符串。 某些方法是 Visual Basic 语言的一部分，其他方法是 `String` 类中的固有方法。  
  
## <a name="visual-basic-language-and-the-net-framework"></a>Visual Basic 语言和 .NET Framework  
 Visual Basic 方法用作语言的固有功能。 在代码中，可以使用它们而无需进行限定。 下面的示例演示了 Visual Basic 字符串操作命令的典型用法：  
  
 [!code-vb[VbVbalrStrings#44](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#44)]  
  
 在此示例中，`Mid` 函数对 `aString` 执行直接操作，并将值分配给 `bString`。  
  
 有关 Visual Basic 字符串操作方法的列表，请参阅[字符串操作摘要](../../../../visual-basic/language-reference/keywords/string-manipulation-summary.md)。  
  
### <a name="shared-methods-and-instance-methods"></a>共享方法和实例方法  
 还可以通过 `String` 类的方法操作字符串。 `String`中有两种类型的方法：*共享*方法和*实例*方法。  
  
#### <a name="shared-methods"></a>共享方法  
 共享方法是源自 `String` 类本身，不需要该类的实例即可工作的方法。 可以使用类的名称（`String`）而不是 `String` 类的实例来限定这些方法。 例如：  
  
 [!code-vb[VbVbalrStrings#45](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#45)]  
  
 在前面的示例中，<xref:System.String.Copy%2A?displayProperty=nameWithType> 方法是静态方法，它在给定的表达式上操作，并将生成的值分配给 `bString`。  
  
#### <a name="instance-methods"></a>实例方法  
 相反，实例方法源于 `String` 的特定实例，并且必须使用实例名称进行限定。 例如：  
  
 [!code-vb[VbVbalrStrings#46](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#46)]  
  
 在此示例中，<xref:System.String.Substring%2A?displayProperty=nameWithType> 方法是 `String` 的实例（即 `aString`）的方法。 它在 `aString` 上执行操作，并将该值分配给 `bString`。  
  
 有关详细信息，请参阅 <xref:System.String> 类的文档。  
  
## <a name="see-also"></a>另请参阅

- [Visual Basic 中的字符串简介](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
