---
title: XML 注释异常必须具有&#39;cref&#39;属性
ms.date: 07/20/2015
f1_keywords:
- bc42319
- vbc42319
helpviewer_keywords:
- BC42319
ms.assetid: 62eeeba3-6811-48be-b1ef-c2e4feda3177
ms.openlocfilehash: abe9fe0f6216f81fa223fe83a122b580577e1c32
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/01/2018
ms.locfileid: "43404760"
---
# <a name="xml-comment-exception-must-have-a-39cref39-attribute"></a>XML 注释异常必须具有&#39;cref&#39;属性
\<异常 > 标记提供了一种方法来记录方法可能引发的异常。 所需`cref`特性将指定的成员，它由文档生成器检查名称。 如果存在该成员，它被转换为文档文件中的规范的元素名称。  
  
 **错误 ID:** BC42319  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
-   添加`cref`属性为异常，如下所示：  
  
    ```  
    '''<exception cref="member">description</exception>  
    ```  
  
## <a name="see-also"></a>请参阅  
 [\<exception>](../../../visual-basic/language-reference/xmldoc/exception.md)  
 [如何：创建 XML 文档](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)  
 [XML 注释标记](../../../visual-basic/language-reference/xmldoc/index.md)
