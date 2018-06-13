---
title: 需要语句结束
ms.date: 07/20/2015
f1_keywords:
- bc30205
- vbc30205
helpviewer_keywords:
- BC30205
ms.assetid: 53c7f825-a737-4b76-a1fa-f67745b8bd40
ms.openlocfilehash: 7b91d13cbcb9d211d4ca18c8e48c7494bf6eccc6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33588075"
---
# <a name="end-of-statement-expected"></a>需要语句结束
语句语法上完成，但是完成该语句的元素后面有一个附加的编程元素。 需要在每个语句的末尾行结束符。
  
 行结束符将分成行的 Visual Basic 源代码文件的字符。 行终止符的示例包括 Unicode 回车符返回字符 (& HD)，Unicode 换行字符 (& HA)，并使用 Unicode 回车字符后跟 Unicode 换行符字符。 有关行终止符的详细信息，请参阅[Visual Basic 语言规范](../../../visual-basic/reference/language-specification/index.md)。
  
 **错误 ID:** BC30205
  
## <a name="to-correct-this-error"></a>更正此错误
  
1.  检查以确定是否两个不同的语句无意中已放在同一行。
  
2.  完成该语句的元素后面插入行结束符。
  
## <a name="see-also"></a>请参阅  
 [如何：在代码中拆分和合并语句](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)  
 [语句](../../../visual-basic/programming-guide/language-features/statements.md)
