---
title: 无错误继续执行
ms.date: 07/20/2015
f1_keywords:
- vbrID20
ms.assetid: f9631804-fd36-4443-b36c-30db827e6176
ms.openlocfilehash: 5e45f713a433365b4bbc8286154a3b877b08ec59
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="resume-without-error"></a>无错误继续执行
A`Resume`语句出现在错误处理代码之外或代码跳转到错误处理程序即使没有任何错误。  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
1.  移动`Resume`语句 into 错误处理程序，或将其删除。  
  
2.  跳转到标签不能过程中出现，因此，请搜索标识错误处理程序的标签的过程。 如果找到指定的目标为一个重复标签`GoTo`语句而非`On Error GoTo`语句中，更改行标签以同意其预期目标。  
  
## <a name="see-also"></a>请参阅  
 [Resume 语句](../../../visual-basic/language-reference/statements/resume-statement.md)  
 [On Error 语句](../../../visual-basic/language-reference/statements/on-error-statement.md)
