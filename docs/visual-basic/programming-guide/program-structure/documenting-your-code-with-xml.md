---
title: 使用 XML 将代码文档化
ms.date: 07/20/2015
helpviewer_keywords:
- XML [Visual Basic], documenting code
- XML comments, Visual Basic
- Visual Basic code, documenting with XML
ms.assetid: a0d35dc7-c5f9-4d74-92ff-a1c6f28d5235
ms.openlocfilehash: bdf0da7a8acc919e4a1d66b81e30c9ed912dd321
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347444"
---
# <a name="documenting-your-code-with-xml-visual-basic"></a>使用 XML 将代码文档化 (Visual Basic)

In Visual Basic, you can document your code using XML

## <a name="xml-documentation-comments"></a>XML 文档注释

Visual Basic provides an easy way to automatically create XML documentation for projects. You can automatically generate an XML skeleton for your types and members, and then provide summaries, descriptive documentation for each parameter, and other remarks. With the appropriate setup, the XML documentation is automatically emitted into an XML file with the same name as your project and the .xml extension. 有关详细信息，请参阅 [-doc](../../../visual-basic/reference/command-line-compiler/doc.md)。

The XML file can be consumed or otherwise manipulated as XML. This file is located in the same directory as the output .exe or .dll file of your project.

XML documentation starts with `'''`. 处理这些注释时存在一些限制：

- 文档必须是格式正确的 XML。 If the XML is not well formed, a warning is generated and the documentation file contains a comment saying that an error was encountered.

- 开发人员可以随意创建自己的标记集。 There is a recommended set of tags (see "Related Sections" in this topic). 部分建议标记具有特殊含义：

  - \<param> 标记用于描述参数。 如果使用，编译器将验证该参数是否存在，以及文档是否描述了所有参数。 If the verification fails, the compiler issues a warning.

  - `cref` 属性可以附加到任何标记，以提供对代码元素的引用。 编译器验证此代码元素是否存在。 If the verification fails, the compiler issues a warning. The compiler also respects any `Imports` statements when looking for a type described in the `cref` attribute.

  - The \<summary> tag is used by IntelliSense in Visual Studio to display additional information about a type or member.

## <a name="related-sections"></a>相关章节

For details on creating an XML file with documentation comments, see the following topics:

- [-doc](../../../visual-basic/reference/command-line-compiler/doc.md)

- [XML 注释标记](../../../visual-basic/language-reference/xmldoc/index.md)

- [处理 XML 文件](../../../visual-basic/programming-guide/program-structure/processing-the-xml-file.md)

- [如何：创建 XML 文档](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)

- [Visual Studio 中的 XML 工具](/visualstudio/xml-tools/xml-tools-in-visual-studio)

## <a name="see-also"></a>请参阅

- [使用 Visual Basic 开发应用程序](../../../visual-basic/developing-apps/index.md)
- [Visual Basic 编程指南](../../../visual-basic/programming-guide/index.md)
