---
title: 需要语句结束
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30205
- vbc30205
helpviewer_keywords:
- BC30205
ms.assetid: 53c7f825-a737-4b76-a1fa-f67745b8bd40
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4934952015cb4871bcd90cef982eab5425b1617f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="end-of-statement-expected"></a>需要语句结束
语句语法上完成，但是完成该语句的元素后面有一个附加的编程元素。 需要在每个语句的末尾行结束符。
  
 行结束符将分成行的 Visual Basic 源代码文件的字符。 行终止符的示例包括 Unicode 回车符返回字符 (& HD)，Unicode 换行字符 (& HA)，并使用 Unicode 回车字符后跟 Unicode 换行符字符。 有关行终止符的详细信息，请参阅[Visual Basic 语言规范](../../../visual-basic/reference/language-specification/index.md)。
  
 **错误 ID:** BC30205
  
## <a name="to-correct-this-error"></a>更正此错误
  
1.  检查以确定是否两个不同的语句无意中已放在同一行。
  
2.  完成该语句的元素后面插入行结束符。
  
## <a name="see-also"></a>另请参阅  
 [如何：在代码中拆分和合并语句](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)  
 [语句](../../../visual-basic/programming-guide/language-features/statements.md)
