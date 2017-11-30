---
title: "如何：在 Visual Basic 中使用 StringBuilder 创建字符串"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- StringBuilder class
- strings [Visual Basic], using StringBuilder
ms.assetid: 9c042880-aa16-432e-9ccb-cd00abda9ae3
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: c799794b319843b0239ce9589e0c556c603c8617
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-strings-using-a-stringbuilder-in-visual-basic"></a>如何：在 Visual Basic 中使用 StringBuilder 创建字符串
此示例构造从使用许多较小的字符串的长字符串<xref:System.Text.StringBuilder>类。 <xref:System.Text.StringBuilder>类是比效率更高`&=`将许多字符串连接的运算符。  
  
## <a name="example"></a>示例  
 下面的示例创建的实例<xref:System.Text.StringBuilder>类，将 1,000 字符串追加到该实例，然后返回其字符串表示形式。  
  
 [!code-vb[VbVbalrStrings#70](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-to-create-strings-using-a-stringbuilder_1.vb)]  
  
## <a name="see-also"></a>另请参阅  
 [使用 StringBuilder 类](../../../../standard/base-types/stringbuilder.md)  
 [&= 运算符](../../../../visual-basic/language-reference/operators/and-assignment-operator.md)  
 [字符串](../../../../visual-basic/programming-guide/language-features/strings/index.md)  
 [新建字符串](../../../../standard/base-types/creating-new.md)  
 [控制字符串](../../../../standard/base-types/manipulating-strings.md)  
 [字符串示例](http://msdn.microsoft.com/en-us/be9e82a3-dc95-4aaa-9396-61b66e467e02)
