---
title: XML 注释异常必须具有“cref”特性
ms.date: 07/20/2015
f1_keywords:
- bc42319
- vbc42319
helpviewer_keywords:
- BC42319
ms.assetid: 62eeeba3-6811-48be-b1ef-c2e4feda3177
ms.openlocfilehash: 2e57dc63cb7ad8b2e061296a082d6fa79b464f08
ms.sourcegitcommit: 35da8fb45b4cca4e59cc99a5c56262c356977159
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/28/2019
ms.locfileid: "71592031"
---
# <a name="xml-comment-exception-must-have-a-cref-attribute"></a>XML 注释异常必须具有“cref”特性
@No__t-0exception > 标记提供了一种方法来记录可由方法引发的异常。 必需的 `cref` 特性指定了文档生成器检查的成员的名称。 如果该成员存在，则将其转换为文档文件中的规范元素名称。  
  
 **错误 ID：** BC42319  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
- 将 `cref` 特性添加到异常，如下所示：  
  
    xml  
    "" "<exception cref="member">说明</exception>  
    ```  
  
## See also

- [\<exception>](../../../visual-basic/language-reference/xmldoc/exception.md)
- [How to: Create XML Documentation](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)
- [XML Comment Tags](../../../visual-basic/language-reference/xmldoc/index.md)
