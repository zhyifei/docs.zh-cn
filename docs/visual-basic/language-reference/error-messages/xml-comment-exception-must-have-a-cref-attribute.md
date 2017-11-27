---
title: "XML 注释异常必须具有 &#39; cref &#39;属性"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc42319
- vbc42319
helpviewer_keywords: BC42319
ms.assetid: 62eeeba3-6811-48be-b1ef-c2e4feda3177
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: c0c22c9cd9415faf17d027c3751d166662a92b50
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="xml-comment-exception-must-have-a-39cref39-attribute"></a>XML 注释异常必须具有 &#39; cref &#39;属性
\<异常 > 标记使您能够文档可能由方法引发的异常。 所需`cref`特性将指定的成员，它由文档生成器检查的名称。 如果该成员存在，则将其转换为文档文件中的规范的元素名称。  
  
 **错误 ID:** BC42319  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
-   添加`cref`属性设为异常，如下所示：  
  
    ```  
    '''<exception cref="member">description</exception>  
    ```  
  
## <a name="see-also"></a>另请参阅  
 [\<exception>](../../../visual-basic/language-reference/xmldoc/exception.md)  
 [如何：创建 XML 文档](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)  
 [XML 注释标记](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
