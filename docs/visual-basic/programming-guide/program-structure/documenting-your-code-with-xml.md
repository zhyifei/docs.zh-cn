---
title: 使用 XML 将代码文档化 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- XML [Visual Basic], documenting code
- XML comments, Visual Basic
- Visual Basic code, documenting with XML
ms.assetid: a0d35dc7-c5f9-4d74-92ff-a1c6f28d5235
ms.openlocfilehash: fa642adcfea9e80b41b5fc148df2b95b8fa44d88
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33650496"
---
# <a name="documenting-your-code-with-xml-visual-basic"></a>使用 XML 将代码文档化 (Visual Basic)
在 Visual Basic 中，可以记录你的代码使用 XML  
  
## <a name="xml-documentation-comments"></a>XML 文档注释  
 Visual Basic 可以轻松地自动创建的项目的 XML 文档。 你可以自动生成类型和成员的 XML 主干并且然后为每个参数和其他备注中提供摘要、 描述性文档。 借助适当的安装中，XML 文档在自动发送到具有相同名称为你的项目和.xml 扩展名的 XML 文件。 有关详细信息，请参阅 [/doc](../../../visual-basic/reference/command-line-compiler/doc.md)。  
  
 可以使用或其他操作以 XML 形式的 XML 文件。 此文件位于与你的项目的输出.exe 或.dll 文件相同的目录中。  
  
 XML 文档开头`'''`。 处理这些注释时存在一些限制：  
  
-   文档必须是格式正确的 XML。 如果 XML 的格式不正确，会生成一个警告，并且文档文件包含条注释，指出遇到错误。  
  
-   开发人员可以随意创建自己的标记集。 没有一套建议的标记 （请参阅本主题中的"相关章节"）。 部分建议标记具有特殊含义：  
  
    -   \<param> 标记用于描述参数。 如果使用，编译器将验证该参数是否存在，以及文档是否描述了所有参数。 如果验证失败，编译器会发出警告。  
  
    -   `cref` 属性可以附加到任何标记，以提供对代码元素的引用。 编译器会验证此代码元素存在。 如果验证失败，编译器会发出警告。 编译器还将考虑所有`Imports`语句时查找类型中所述`cref`属性。  
  
    -   \<摘要 > 标记用于通过 Visual Studio 中的 IntelliSense，以显示有关类型或成员的其他信息。  
  
## <a name="related-sections"></a>相关章节  
 有关创建带有文档注释的 XML 文件的详细信息，请参阅以下主题：  
  
-   [/doc](../../../visual-basic/reference/command-line-compiler/doc.md)  
  
-   [XML 注释标记](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)  
  
-   [处理 XML 文件](../../../visual-basic/programming-guide/program-structure/processing-the-xml-file.md)  
  
-   [如何：创建 XML 文档](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)  
  
-   [Visual Studio 中的 XML 工具](/visualstudio/xml-tools/xml-tools-in-visual-studio)  
  
## <a name="see-also"></a>请参阅  
 [使用 Visual Basic 开发应用程序](../../../visual-basic/developing-apps/index.md)  
 [Visual Basic 编程指南](../../../visual-basic/programming-guide/index.md)
