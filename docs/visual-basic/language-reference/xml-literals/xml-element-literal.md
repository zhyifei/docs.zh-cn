---
title: XML 元素文本
ms.date: 07/20/2015
f1_keywords:
- vb.XmlLiteralElement
helpviewer_keywords:
- XML element literal [Visual Basic]
- element literal [Visual Basic]
- XML literals [Visual Basic], element
ms.assetid: 95039642-7893-48b7-b23f-45a6c55d8f67
ms.openlocfilehash: d6d900ca6868cfffe6b0e5b349321a79c5716c46
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347032"
---
# <a name="xml-element-literal-visual-basic"></a>XML 元素文本 (Visual Basic)

表示 <xref:System.Xml.Linq.XElement> 对象的文本。

## <a name="syntax"></a>语法

```xml
<name [ attributeList ] />
-or-
<name [ attributeList ] > [ elementContents ] </[ name ]>
```

## <a name="parts"></a>部件

- `<`

  必需。 打开开始元素标记。

- `name`

  必需。 元素名称。 格式为以下格式之一：

  - 元素名称的文本文本，格式为 `[ePrefix:]eName`，其中：

    |部件|说明|
    |---|---|
    |`ePrefix`|可选。 元素的 XML 命名空间前缀。 必须是一个全局 XML 命名空间，该命名空间是使用文件中的 `Imports` 语句或项目级别定义的，或者是在此元素或父元素中定义的本地 XML 命名空间。|
    |`eName`|必需。 元素名称。 格式为以下格式之一：<br /><br /> 文本。 请参阅已[声明的 XML 元素和属性的名称](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)。<br />-形式 `<%= eNameExp %>`的嵌入式表达式。 `eNameExp` 的类型必须 `String` 或可隐式转换为 <xref:System.Xml.Linq.XName>的类型。|

  - 格式 `<%= nameExp %>`的嵌入式表达式。 `nameExp` 的类型必须 `String` 或可隐式转换为 <xref:System.Xml.Linq.XName>的类型。 元素的结束标记中不允许使用嵌入式表达式。

- `attributeList`

  可选。 在文本中声明的属性的列表。

  `attribute [ attribute ... ]`

  每个 `attribute` 都具有以下语法之一：

  - 属性分配，格式为 `[aPrefix:]aName=aValue`，其中：

    |部件|说明|
    |---|---|
    |`aPrefix`|可选。 特性的 XML 命名空间前缀。 必须是使用 `Imports` 语句定义的全局 XML 命名空间，或此元素或父元素中定义的本地 XML 命名空间。|
    |`aName`|必需。 属性的名称。 格式为以下格式之一：<br /><br /> 文本。 请参阅已[声明的 XML 元素和属性的名称](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)。<br />-形式 `<%= aNameExp %>`的嵌入式表达式。 `aNameExp` 的类型必须 `String` 或可隐式转换为 <xref:System.Xml.Linq.XName>的类型。|
    |`aValue`|可选。 特性的值。 格式为以下格式之一：<br /><br /> 文本文本，用引号引起来。<br />-形式 `<%= aValueExp %>`的嵌入式表达式。 允许任何类型。|

  - 格式 `<%= aExp %>`的嵌入式表达式。

- `/>`

  可选。 指示元素是一个空元素，不包含内容。

- `>`

  必需。 结束开始或空元素标记。

- `elementContents`

  可选。 元素的内容。

  `content [ content ... ]`

  每个 `content` 可以是以下各项之一：

  - 文本。 如果有任何文本文本，`elementContents` 中的所有空格都非常重要。

  - 格式 `<%= contentExp %>`的嵌入式表达式。

  - XML 元素文本。

  - XML 注释文本。 请参阅[XML 注释文本](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md)。

  - XML 处理指令文本。 请参阅[XML 处理指令文本](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md)。

  - XML CDATA 文本。 请参阅[XML CDATA 文本](../../../visual-basic/language-reference/xml-literals/xml-cdata-literal.md)。

- `</[name]>`

  可选。 表示元素的结束标记。 当可选 `name` 参数是嵌入式表达式的结果时，不允许使用该参数。

## <a name="return-value"></a>返回值

一个 <xref:System.Xml.Linq.XElement> 对象。

## <a name="remarks"></a>备注

可以使用 XML 元素文本语法在代码中创建 <xref:System.Xml.Linq.XElement> 对象。

> [!NOTE]
> XML 文本可以跨多行，而无需使用行继续符。 此功能使你能够从 XML 文档复制内容并将其直接粘贴到 Visual Basic 程序。

利用形式 `<%= exp %>` 的嵌入式表达式，你可以向 XML 元素文本添加动态信息。 有关详细信息，请参阅[XML 中的嵌入式表达式](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)。

Visual Basic 编译器将 XML 元素文本转换为对 <xref:System.Xml.Linq.XElement.%23ctor%2A> 构造函数的调用，如果需要，则转换为 <xref:System.Xml.Linq.XAttribute.%23ctor%2A> 构造函数。

## <a name="xml-namespaces"></a>XML 命名空间

当你必须在代码中多次使用同一命名空间中的元素创建 XML 文本时，XML 命名空间前缀非常有用。 你可以使用全局 XML 命名空间前缀，该前缀是使用 `Imports` 语句定义的，或者是通过使用 `xmlns:xmlPrefix="xmlNamespace"` 特性语法定义的本地前缀。 有关详细信息，请参阅[Imports 语句（XML 命名空间）](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)。

根据 XML 命名空间的作用域规则，本地前缀优先于全局前缀。 但是，如果 XML 文本定义了 XML 命名空间，则该命名空间不能用于出现在嵌入表达式中的表达式。 嵌入的表达式只能访问全局 XML 命名空间。

Visual Basic 编译器将 XML 文本使用的每个全局 XML 命名空间转换为生成的代码中的一个本地命名空间定义。 不使用的全局 XML 命名空间不会出现在生成的代码中。

## <a name="example"></a>示例

下面的示例演示如何创建一个具有两个嵌套空元素的简单 XML 元素。

[!code-vb[VbXMLSamples#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples9.vb#20)]

该示例显示以下文本。 请注意，文本将保留空元素的结构。

```xml
<outer>
  <inner1></inner1>
  <inner2 />
</outer>
```

## <a name="example"></a>示例

下面的示例演示如何使用嵌入的表达式来命名元素并创建属性。

[!code-vb[VbXMLSamples#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples9.vb#21)]

此代码显示以下文本：

```xml
<book isbn="1234" author="My Author" year="1999" title="My Book" />
```

## <a name="example"></a>示例

下面的示例声明 `ns` 作为 XML 命名空间前缀。 然后，它使用命名空间的前缀创建 XML 文本，并显示该元素的最终形式。

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

请注意，编译器将全局 XML 命名空间的前缀转换为 XML 命名空间的前缀定义。 \<ns：中间 > 元素将重定义 \<ns： inner1 > 元素的 XML 命名空间前缀。 但 \<ns： inner2 > 元素使用由 `Imports` 语句定义的命名空间。

## <a name="see-also"></a>另请参阅

- <xref:System.Xml.Linq.XElement>
- [已声明的 XML 元素和特性的名称](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)
- [XML 注释文本](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md)
- [XML CDATA 文本](../../../visual-basic/language-reference/xml-literals/xml-cdata-literal.md)
- [XML 文本](../../../visual-basic/language-reference/xml-literals/index.md)
- [在 Visual Basic 中创建 XML](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [XML 中的嵌入式表达式](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)
- [Imports 语句（XML 命名空间）](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)
