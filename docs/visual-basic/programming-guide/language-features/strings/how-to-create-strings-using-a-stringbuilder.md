---
title: 如何：在 Visual Basic 中使用 StringBuilder 创建字符串
ms.date: 07/20/2015
helpviewer_keywords:
- StringBuilder class
- strings [Visual Basic], using StringBuilder
ms.assetid: 9c042880-aa16-432e-9ccb-cd00abda9ae3
ms.openlocfilehash: 49f3271d41e9e858c6ecafe1dde5330ebff767f6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33647727"
---
# <a name="how-to-create-strings-using-a-stringbuilder-in-visual-basic"></a>如何：在 Visual Basic 中使用 StringBuilder 创建字符串
此示例构造从使用许多较小的字符串的长字符串<xref:System.Text.StringBuilder>类。 <xref:System.Text.StringBuilder>类是比效率更高`&=`将许多字符串连接的运算符。  
  
## <a name="example"></a>示例  
 下面的示例创建的实例<xref:System.Text.StringBuilder>类，将 1,000 字符串追加到该实例，然后返回其字符串表示形式。  
  
 [!code-vb[VbVbalrStrings#70](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-to-create-strings-using-a-stringbuilder_1.vb)]  
  
## <a name="see-also"></a>请参阅  
 [使用 StringBuilder 类](../../../../standard/base-types/stringbuilder.md)  
 [&= 运算符](../../../../visual-basic/language-reference/operators/and-assignment-operator.md)  
 [字符串](../../../../visual-basic/programming-guide/language-features/strings/index.md)  
 [新建字符串](../../../../standard/base-types/creating-new.md)  
 [控制字符串](../../../../standard/base-types/manipulating-strings.md)  
 [字符串示例](https://msdn.microsoft.com/library/be9e82a3-dc95-4aaa-9396-61b66e467e02(v=vs.100))
