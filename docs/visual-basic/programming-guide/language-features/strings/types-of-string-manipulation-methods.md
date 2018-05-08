---
title: 字符串操作方法的类型 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], manipulating [Visual Basic]
- string manipulation
ms.assetid: 905055cd-7f50-48fb-9eed-b0995af1dc1f
ms.openlocfilehash: 11903e067c064f129ecd2df80244edb6741c73be
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="types-of-string-manipulation-methods-in-visual-basic"></a>字符串操作方法的类型 (Visual Basic)
有多种不同的方式来分析和操作字符串。 一些方法属于的 Visual Basic 语言中，而其他则中的固有`String`类。  
  
## <a name="visual-basic-language-and-the-net-framework"></a>Visual Basic 语言和.NET Framework  
 Visual Basic 方法用作固有函数的语言。 它们可能用于而无需在代码中的限定。 下面的示例演示 Visual Basic 字符串操作命令的典型用法：  
  
 [!code-vb[VbVbalrStrings#44](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/types-of-string-manipulation-methods_1.vb)]  
  
 在此示例中，`Mid`函数上执行的直接操作`aString`和将该值赋给`bString`。  
  
 Visual Basic 字符串操作方法的列表，请参阅[字符串操作摘要](../../../../visual-basic/language-reference/keywords/string-manipulation-summary.md)。  
  
### <a name="shared-methods-and-instance-methods"></a>共享的方法和实例方法  
 您还可以使用方法的操作字符串`String`类。 有两种类型中的方法的`String`:*共享*方法和*实例*方法。  
  
#### <a name="shared-methods"></a>共享的方法  
 共享的方法是起源于方法`String`类本身并不需要此类工作的实例。 这些方法可以使用的类名称限定 (`String`) 而不是与实例`String`类。 例如：  
  
 [!code-vb[VbVbalrStrings#45](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/types-of-string-manipulation-methods_2.vb)]  
  
 在前面的示例中，<xref:System.String.Copy%2A?displayProperty=nameWithType>方法是静态方法，对表达式的行为它给定并将该生成值赋给`bString`。  
  
#### <a name="instance-methods"></a>实例方法  
 实例方法，与此相反，源于的特定实例`String`并且必须具有实例名称进行限定。 例如：  
  
 [!code-vb[VbVbalrStrings#46](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/types-of-string-manipulation-methods_3.vb)]  
  
 在此示例中，<xref:System.String.Substring%2A?displayProperty=nameWithType>方法是实例方法`String`(即， `aString`)。 它执行的操作上`aString`和将该值赋给`bString`。  
  
 有关详细信息，请参阅的文档<xref:System.String>类。  
  
## <a name="see-also"></a>请参阅  
 [Visual Basic 中的字符串简介](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
