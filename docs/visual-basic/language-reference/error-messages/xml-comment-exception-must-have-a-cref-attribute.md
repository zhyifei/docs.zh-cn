---
title: XML 注释异常必须具有“cref”特性
ms.date: 07/20/2015
f1_keywords:
- bc42319
- vbc42319
helpviewer_keywords:
- BC42319
ms.assetid: 62eeeba3-6811-48be-b1ef-c2e4feda3177
ms.openlocfilehash: 54965f3796b6c5ef0e387cd354abcb5740476257
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/15/2019
ms.locfileid: "72321177"
---
# <a name="xml-comment-exception-must-have-a-cref-attribute"></a>XML 注释异常必须具有“cref”特性

@No__t_0exception 的 > 标记提供了一种方法来记录可由方法引发的异常。 必需 `cref` 特性指定了文档生成器检查的成员的名称。 如果该成员存在，则将其转换为文档文件中的规范元素名称。

**错误 ID：** BC42319

## <a name="to-correct-this-error"></a>更正此错误

将 `cref` 特性添加到异常，如下所示：

```xml
<exception cref="member">description</exception>
```

## <a name="see-also"></a>请参阅

- [\<exception>](../../../visual-basic/language-reference/xmldoc/exception.md)
- [如何：创建 XML 文档](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)
- [XML 注释标记](../../../visual-basic/language-reference/xmldoc/index.md)
