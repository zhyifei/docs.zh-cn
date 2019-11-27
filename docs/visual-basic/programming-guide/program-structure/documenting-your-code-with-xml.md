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

在 Visual Basic 中，可以使用 XML 记录代码

## <a name="xml-documentation-comments"></a>XML 文档注释

Visual Basic 提供了一种简单的方法来自动创建项目的 XML 文档。 可以为类型和成员自动生成 XML 主干，然后提供每个参数的摘要、描述性文档和其他备注。 使用适当的设置，XML 文档将自动发送到与你的项目具有相同名称和 .xml 扩展名的 XML 文件中。 有关详细信息，请参阅 [-doc](../../../visual-basic/reference/command-line-compiler/doc.md)。

可以使用 XML 文件或以其他方式将其作为 XML 来处理。 此文件与项目的输出 .exe 或 .dll 文件位于同一目录中。

XML 文档从 `'''`开始。 处理这些注释时存在一些限制：

- 文档必须是格式正确的 XML。 如果 XML 格式不正确，则会生成警告，并且文档文件将会显示一条注释，指出遇到了错误。

- 开发人员可以随意创建自己的标记集。 建议使用一组标记（请参阅本主题中的 "相关部分"）。 部分建议标记具有特殊含义：

  - \<param> 标记用于描述参数。 如果使用，编译器将验证该参数是否存在，以及文档是否描述了所有参数。 如果验证失败，则编译器会发出警告。

  - `cref` 属性可以附加到任何标记，以提供对代码元素的引用。 编译器验证此代码元素是否存在。 如果验证失败，则编译器会发出警告。 查找 `cref` 属性中所述的类型时，编译器还会考虑任何 `Imports` 语句。

  - Visual Studio 中的 IntelliSense 使用 \<summary > 标记来显示有关某个类型或成员的其他信息。

## <a name="related-sections"></a>相关章节

有关创建包含文档注释的 XML 文件的详细信息，请参阅以下主题：

- [-doc](../../../visual-basic/reference/command-line-compiler/doc.md)

- [XML 注释标记](../../../visual-basic/language-reference/xmldoc/index.md)

- [处理 XML 文件](../../../visual-basic/programming-guide/program-structure/processing-the-xml-file.md)

- [如何：创建 XML 文档](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)

- [Visual Studio 中的 XML 工具](/visualstudio/xml-tools/xml-tools-in-visual-studio)

## <a name="see-also"></a>另请参阅

- [使用 Visual Basic 开发应用程序](../../../visual-basic/developing-apps/index.md)
- [Visual Basic 编程指南](../../../visual-basic/programming-guide/index.md)
