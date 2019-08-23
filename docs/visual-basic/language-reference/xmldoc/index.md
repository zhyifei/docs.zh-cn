---
title: 建议的用于文档注释的 XML 标记 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.XmlDocComment
helpviewer_keywords:
- tags, XML
- XML comments, recommended tags [Visual Basic]
- comments, recommended XML tags
ms.assetid: 294e0736-ff1e-498e-af83-6db71ed41a72
ms.openlocfilehash: 2d6519af8ca1a0e2d59131eec4d63646dce7318b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69913507"
---
# <a name="recommended-xml-tags-for-documentation-comments-visual-basic"></a>建议的用于文档注释的 XML 标记 (Visual Basic)
Visual Basic 编译器可以在代码中将文档注释处理到 XML 文件中。 您可以使用其他工具将 XML 文件处理到文档中。  
  
 允许对代码构造 (如类型和类型成员) 使用 XML 注释。 对于分部类型, 只有一个类型的部分可以有 XML 注释, 尽管注释其成员没有限制。  
  
> [!NOTE]
> 文档注释不能应用于命名空间。 原因是一个命名空间可以跨多个程序集, 而不是所有程序集都必须同时加载。  
  
 编译器将处理任何为有效 XML 的标记。 以下标记提供用户文档中的常用功能。  
  
||||  
|---|---|---|  
|[\<c>](../../../visual-basic/language-reference/xmldoc/c.md)|[\<code>](../../../visual-basic/language-reference/xmldoc/code.md)|[\<example>](../../../visual-basic/language-reference/xmldoc/example.md)|  
|[\<exception>](../../../visual-basic/language-reference/xmldoc/exception.md) <sup>1</sup>|[\<include>](../../../visual-basic/language-reference/xmldoc/include.md) <sup>1</sup>|[\<list>](../../../visual-basic/language-reference/xmldoc/list.md)|  
|[\<para>](../../../visual-basic/language-reference/xmldoc/para.md)|[\<param>](../../../visual-basic/language-reference/xmldoc/param.md) <sup>1</sup>|[\<paramref>](../../../visual-basic/language-reference/xmldoc/paramref.md)|  
|[\<permission>](../../../visual-basic/language-reference/xmldoc/permission.md) <sup>1</sup>|[\<remarks>](../../../visual-basic/language-reference/xmldoc/remarks.md)|[\<returns>](../../../visual-basic/language-reference/xmldoc/returns.md)|  
|请参阅 > <sup>1</sup> [ \<](../../../visual-basic/language-reference/xmldoc/see.md)|[\<seealso>](../../../visual-basic/language-reference/xmldoc/seealso.md) <sup>1</sup>|[\<summary>](../../../visual-basic/language-reference/xmldoc/summary.md)|  
|[\<typeparam>](../../../visual-basic/language-reference/xmldoc/typeparam.md) <sup>1</sup>|[\<value>](../../../visual-basic/language-reference/xmldoc/value.md)||  
  
 (<sup>1</sup>编译器验证语法。)  
  
> [!NOTE]
> 如果要在文档注释的文本中显示尖括号, 请使用`&lt;`和。 `&gt;` 例如, 该字符串`"&lt;text in angle brackets&gt;"`将显示为。 `<text in angle brackets>`  
  
## <a name="see-also"></a>请参阅

- [使用 XML 记录代码](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md)
- [/doc](../../../visual-basic/reference/command-line-compiler/doc.md)
- [如何：创建 XML 文档](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)
