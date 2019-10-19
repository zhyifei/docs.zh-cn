---
title: Imports 语句-XML 命名空间（Visual Basic）
ms.date: 07/20/2015
f1_keywords:
- vb.ImportsXmlns
helpviewer_keywords:
- XML namespace [Visual Basic], importing
- imports [Visual Basic]
- Imports statement [Visual Basic]
- namespaces [Visual Basic], importing
ms.assetid: 1f4d50a6-08c7-4c2e-8206-ccae35fcd1b4
ms.openlocfilehash: 0fca0caecfd69580510a539317856209108e5a32
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2019
ms.locfileid: "72581767"
---
# <a name="imports-statement-xml-namespace"></a>Imports 语句（XML 命名空间）

导入用于 XML 文本和 XML 轴属性的 XML 命名空间前缀。

## <a name="syntax"></a>语法

```vb
Imports <xmlns:xmlNamespacePrefix = "xmlNamespaceName">
```

## <a name="parts"></a>部件

`xmlNamespacePrefix`  
可选。 XML 元素和属性可用于引用 `xmlNamespaceName` 的字符串。 如果未提供 `xmlNamespacePrefix`，则导入的 XML 命名空间为默认的 XML 命名空间。 必须是有效的 XML 标识符。 有关详细信息，请参阅已[声明的 XML 元素和属性的名称](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)。

`xmlNamespaceName`  
必须的。 标识要导入的 XML 命名空间的字符串。

## <a name="remarks"></a>备注

您可以使用 `Imports` 语句来定义可用于 XML 文本和 XML 轴属性的全局 XML 命名空间，或用作传递到 `GetXmlNamespace` 运算符的参数。 （有关使用 `Imports` 语句导入可用于在代码中使用类型名称的别名的信息，请参阅[Imports 语句（.Net 命名空间和类型）](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)。）使用 `Imports` 语句声明 XML 命名空间的语法与 XML 中使用的语法相同。 因此，您可以复制 XML 文件中的命名空间声明，并在 `Imports` 语句中使用它。

如果要重复创建来自相同命名空间的 XML 元素，XML 命名空间前缀会很有用。 使用 `Imports` 语句声明的 XML 命名空间前缀是全局性的，因为它可用于文件中的所有代码。 当你创建 XML 元素文本以及访问 XML 轴属性时，可以使用此方法。 有关详细信息，请参阅[XML 元素文本](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)和[xml 轴属性](../../../visual-basic/language-reference/xml-axis/index.md)。

如果定义不带命名空间前缀的全局 XML 命名空间（例如 `Imports <xmlns="http://SomeNameSpace>"`），则该命名空间将被视为默认的 XML 命名空间。 默认的 XML 命名空间用于未显式指定命名空间的任何 XML 元素文本或 XML 特性轴属性。 如果指定的命名空间为空命名空间（即 `xmlns=""`），也会使用默认命名空间。 默认的 XML 命名空间不适用于 XML 文本中的 XML 特性或没有命名空间的 XML 特性轴属性。

Xml 文本（称为*本地 xml 命名空间*）中定义的 xml 命名空间优先于由 `Imports` 语句定义为 GLOBAL 的 xml 命名空间。 @No__t_0 语句定义的 XML 命名空间优先于为 Visual Basic 项目导入的 XML 命名空间。 如果 XML 文本定义了 XML 命名空间，则该本地命名空间不适用于嵌入的表达式。

全局 XML 命名空间遵循与 .NET Framework 命名空间相同的作用域和定义规则。 因此，可以在可导入 .NET Framework 命名空间的任何位置包含 `Imports` 语句来定义全局 XML 命名空间。 这包括代码文件和项目级别导入的命名空间。 有关项目级别导入命名空间的信息，请参阅[引用页、项目设计器（Visual Basic）](/visualstudio/ide/reference/references-page-project-designer-visual-basic)。

每个源文件可以包含任意数量的 `Imports` 语句。 它们必须遵循选项声明（如 `Option Strict` 语句），并且必须位于编程元素声明（如 `Module` 或 `Class` 语句）之前。

## <a name="example"></a>示例

下面的示例导入默认的 XML 命名空间和使用前缀 `ns` 标识的 XML 命名空间。 然后创建使用这两个命名空间的 XML 文本。

[!code-vb[VbXMLSamples#45](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/Module1.vb#45)]

此代码显示以下文本：

```xml
<ns:outer xmlns="http://DefaultNamespace"
          xmlns:ns="http://NewNamespace">
  <ns:innerElement></ns:innerElement>
  <siblingElement></siblingElement>
  <innerElement />
</ns:outer>
```

## <a name="example"></a>示例

下面的示例 `ns` 导入 XML 命名空间前缀。 然后，它创建一个使用命名空间前缀的 XML 文本，并显示该元素的最终形式。

[!code-vb[VbXMLSamples#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples10.vb#22)]

此代码显示以下文本：

```xml
<ns:outer xmlns:ns="http://SomeNamespace">
  <ns:middle xmlns:ns="http://NewNamespace">
    <ns:inner1 />
    <inner2 xmlns="http://SomeNamespace" />
  </ns:middle>
</ns:outer>
```

请注意，编译器将 XML 命名空间前缀从全局前缀转换为本地前缀定义。

## <a name="example"></a>示例

下面的示例 `ns` 导入 XML 命名空间前缀。 然后它使用该命名空间前缀来创建 XML 文本并访问具有限定名称 `ns:name` 的第一个子节点。

[!code-vb[VbXMLSamples#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples8.vb#19)]

此代码显示以下文本：

`Patrick Hines`

## <a name="see-also"></a>请参阅

- [XML 元素文本](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)
- [XML 轴属性](../../../visual-basic/language-reference/xml-axis/index.md)
- [已声明的 XML 元素和特性的名称](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)
- [GetXmlNamespace 运算符](../../../visual-basic/language-reference/operators/getxmlnamespace-operator.md)
