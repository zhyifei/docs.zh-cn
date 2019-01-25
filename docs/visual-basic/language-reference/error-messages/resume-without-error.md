---
title: 无错误继续执行
ms.date: 07/20/2015
f1_keywords:
- vbrID20
ms.assetid: f9631804-fd36-4443-b36c-30db827e6176
ms.openlocfilehash: 55295997e5e534b091063815d5ad1a37b81638ff
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54686616"
---
# <a name="resume-without-error"></a>无错误继续执行
一个`Resume`语句出现在错误处理代码之外或代码改为使用错误处理程序，即使没有错误。  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
1.  移动`Resume`语句到错误处理程序，或将其删除。  
  
2.  跳转到标签不能过程中出现，因此，请搜索的标签用于标识错误处理程序的过程。 如果找到指定的目标为重复的标签`GoTo`语句而非`On Error GoTo`语句中，更改行标签，以便与其预期目标。  
  
## <a name="see-also"></a>请参阅
- [Resume 语句](../../../visual-basic/language-reference/statements/resume-statement.md)
- [On Error 语句](../../../visual-basic/language-reference/statements/on-error-statement.md)
