---
title: 建议的用于文档注释的 XML 标记 (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.XmlDocComment
helpviewer_keywords:
- tags, XML
- XML comments, recommended tags [Visual Basic]
- comments, recommended XML tags
ms.assetid: 294e0736-ff1e-498e-af83-6db71ed41a72
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 54712deb8bb2a5ed1e7b1f5fb8aa073dcdaf76d6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="recommended-xml-tags-for-documentation-comments-visual-basic"></a>建议的用于文档注释的 XML 标记 (Visual Basic)
[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]编译器可以处理你的代码的 XML 文件中的文档注释。 其他工具可用于文档处理 XML 文件。  
  
 XML 注释允许在如类型的代码构造和类型成员。 分部类型，只有一个类型的一部分有 XML 注释，但没有注释其成员不受限制。  
  
> [!NOTE]
>  文档注释不能应用于命名空间。 原因是一个命名空间可跨越多个程序集，并且不是所有程序集具有要同时加载。  
  
 编译器处理任何为有效的 XML 标记。 以下标记提供用户文档中的常用的功能。  
  
||||  
|---|---|---|  
|[\<c>](../../../visual-basic/language-reference/xmldoc/c.md)|[\<code>](../../../visual-basic/language-reference/xmldoc/code.md)|[\<example>](../../../visual-basic/language-reference/xmldoc/example.md)|  
|[\<异常 >](../../../visual-basic/language-reference/xmldoc/exception.md) <sup>1</sup>|[\<包括 >](../../../visual-basic/language-reference/xmldoc/include.md) <sup>1</sup>|[\<list>](../../../visual-basic/language-reference/xmldoc/list.md)|  
|[\<para>](../../../visual-basic/language-reference/xmldoc/para.md)|[\<param >](../../../visual-basic/language-reference/xmldoc/param.md) <sup>1</sup>|[\<paramref>](../../../visual-basic/language-reference/xmldoc/paramref.md)|  
|[\<权限 >](../../../visual-basic/language-reference/xmldoc/permission.md) <sup>1</sup>|[\<remarks>](../../../visual-basic/language-reference/xmldoc/remarks.md)|[\<returns>](../../../visual-basic/language-reference/xmldoc/returns.md)|  
|[\<请参阅 >](../../../visual-basic/language-reference/xmldoc/see.md) <sup>1</sup>|[\<另请参阅 >](../../../visual-basic/language-reference/xmldoc/seealso.md) <sup>1</sup>|[\<summary>](../../../visual-basic/language-reference/xmldoc/summary.md)|  
|[\<typeparam >](../../../visual-basic/language-reference/xmldoc/typeparam.md) <sup>1</sup>|[\<value>](../../../visual-basic/language-reference/xmldoc/value.md)||  
  
 (<sup>1</sup>编译器验证语法。)  
  
> [!NOTE]
>  如果你希望命令的尖括号显示的文档注释的文本中，使用`<`和`>`。 例如，在字符串`"<text in angle brackets>"`将显示为`<text in angle``brackets>`。  
  
## <a name="see-also"></a>另请参阅  
 [使用 XML 记录代码](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md)  
 [/doc](../../../visual-basic/reference/command-line-compiler/doc.md)  
 [如何：创建 XML 文档](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)
