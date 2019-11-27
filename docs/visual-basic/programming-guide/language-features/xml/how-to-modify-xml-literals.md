---
title: 如何：修改 XML 文本
ms.date: 07/20/2015
helpviewer_keywords:
- XML axis [Visual Basic], Value
- XML literals [Visual Basic]
- XML literals [Visual Basic], modifying
ms.assetid: 4e864522-a37a-43a2-8236-af80277c5482
ms.openlocfilehash: 99ec35addcb9fc8d886c9151cde87227b5113eb9
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74330860"
---
# <a name="how-to-modify-xml-literals-visual-basic"></a>如何：修改 XML 文本 (Visual Basic)

Visual Basic 提供了修改 XML 文本的便利方法。 您可以添加或删除元素和属性，还可以将现有元素替换为新的 XML 元素。 本主题提供了几个示例，演示如何修改现有的 XML 文本。

### <a name="to-modify-the-value-of-an-xml-literal"></a>修改 XML 文本的值

1. 若要修改 XML 文本的值，请获取对 XML 文本的引用并将 `Value` 属性设置为所需的值。

    下面的代码示例更新 XML 文档中所有 \<Price > 元素的值。

    [!code-vb[VbXmlSamples2#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXmlSamples2/VB/Module2.vb#4)]

    下面的示例演示了此代码示例中的示例源 XML 和修改后的 XML。

    源 XML：

    ```xml
    <?xml version="1.0"?>
    <Catalog>
      <Book id="bk101">
        <Author>Garghentini, Davide</Author>
        <Title>XML Developer's Guide</Title>
        <Price>44.95</Price>
      </Book>
      <Book id="bk331">
        <Author>Spencer, Phil</Author>
        <Title>Developing Applications with Visual Basic .NET</Title>
        <Price>45.95</Price>
      </Book>
    </Catalog>
    ```

    修改的 XML：

    ```xml
    <?xml version="1.0"?>
    <Catalog>
      <Book id="bk101">
        <Author>Garghentini, Davide</Author>
        <Title>XML Developer's Guide</Title>
        <Price>47.20</Price>
      </Book>
      <Book id="bk331">
        <Author>Spencer, Phil</Author>
        <Title>Developing Applications with Visual Basic .NET</Title>
        <Price>48.25</Price>
      </Book>
    </Catalog>
    ```

    > [!NOTE]
    > `Value` 属性引用集合中的第一个 XML 元素。 如果集合中有多个具有相同名称的元素，则设置 `Value` 属性仅影响集合中的第一个元素。

### <a name="to-add-an-attribute-to-an-xml-literal"></a>向 XML 文本添加特性

1. 若要向 XML 文本添加特性，请首先获取对 XML 文本的引用。 然后，您可以通过添加一个新的 XML 特性轴属性来添加属性。 还可以通过使用 <xref:System.Xml.Linq.XContainer.Add%2A> 方法将新的 <xref:System.Xml.Linq.XAttribute> 对象添加到 XML 文本中。 下面的示例演示了这两个选项。

    [!code-vb[VbXmlSamples2#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXmlSamples2/VB/Module2.vb#5)]

    下面的示例演示了此代码示例中的示例源 XML 和修改后的 XML。

    源 XML：

    ```xml
    <?xml version="1.0"?>
    <Catalog>
      <Book id="bk101" >
        <Author>Garghentini, Davide</Author>
        <Title>XML Developer's Guide</Title>
        <Price>44.95</Price>
      </Book>
      <Book id="bk331">
        <Author>Spencer, Phil</Author>
        <Title>Developing Applications with Visual Basic .NET</Title>
        <Price>45.95</Price>
      </Book>
    </Catalog>
    ```

    修改的 XML：

    ```xml
    <?xml version="1.0"?>
    <Catalog>
      <Book id="bk101" genre="Computer" editorEmail="someone@example.com">
        <Author>Garghentini, Davide</Author>
        <Title>XML Developer's Guide</Title>
        <Price>44.95</Price>
      </Book>
      <Book id="bk331" genre="Computer" editorEmail="someone@example.com">
        <Author>Spencer, Phil</Author>
        <Title>Developing Applications with Visual Basic .NET</Title>
        <Price>45.95</Price>
      </Book>
    </Catalog>
    ```

    有关 XML 特性轴属性的详细信息，请参阅[Xml 特性轴属性](../../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md)。

### <a name="to-add-an-element-to-an-xml-literal"></a>向 XML 文本添加元素

1. 若要将元素添加到 XML 文本，请首先获取对 XML 文本的引用。 然后，你可以通过使用 <xref:System.Xml.Linq.XContainer.Add%2A> 方法将新的 <xref:System.Xml.Linq.XElement> 对象添加为元素的最后一个子元素。 您可以通过使用 <xref:System.Xml.Linq.XContainer.AddFirst%2A> 方法添加新的 <xref:System.Xml.Linq.XElement> 对象作为第一个子元素。

    若要将新元素添加到相对于其他子元素的特定位置，请首先获取对相邻子元素的引用。 然后，你可以通过使用 <xref:System.Xml.Linq.XNode.AddBeforeSelf%2A> 方法在相邻子元素之前添加新的 <xref:System.Xml.Linq.XElement> 对象。 还可以通过使用 <xref:System.Xml.Linq.XNode.AddAfterSelf%2A> 方法在相邻子元素之后添加新的 <xref:System.Xml.Linq.XElement> 对象。

    下面的示例显示了每种方法的示例。

    [!code-vb[VbXmlSamples2#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXmlSamples2/VB/Module2.vb#6)]

    下面的示例演示了此代码示例中的示例源 XML 和修改后的 XML。

    源 XML：

    ```xml
    <?xml version="1.0"?>
    <Catalog>
      <Book id="bk101" >
        <Author>Garghentini, Davide</Author>
        <Title>XML Developer's Guide</Title>
        <Price>44.95</Price>
      </Book>
      <Book id="bk331">
        <Author>Spencer, Phil</Author>
        <Title>Developing Applications with Visual Basic .NET</Title>
        <Price>45.95</Price>
      </Book>
    </Catalog>
    ```

    修改的 XML：

    ```xml
    <?xml version="1.0"?>
    <Catalog>
      <Book id="bk101" >
        <Author>Garghentini, Davide</Author>
        <Title>XML Developer's Guide</Title>
        <Price>44.95</Price>
      </Book>
      <Book id="bk000"></Book>
      <Book id="bk331">
        <Publisher>Microsoft Press</Publisher>
        <Author>Spencer, Phil</Author>
        <Title>Developing Applications with Visual Basic .NET</Title>
        <Price>45.95</Price>
        <PublishDate>2005-2-14</PublishDate>
      </Book>
      <Book id="bk999"></Book>
    </Catalog>
    ```

### <a name="to-remove-an-element-or-attribute-from-an-xml-literal"></a>从 XML 文本中删除元素或属性

1. 若要从 XML 文本中删除某个元素或属性，请获取对该元素或属性的引用并调用 `Remove` 方法，如以下示例中所示。

    [!code-vb[VbXmlSamples2#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXmlSamples2/VB/Module2.vb#7)]

    下面的示例演示了此代码示例中的示例源 XML 和修改后的 XML。

    源 XML：

    ```xml
    <?xml version="1.0"?>
    <Catalog>
      <Book id="bk101" genre="Computer" editorEmail="someone@example.com">
        <Author>Garghentini, Davide</Author>
        <Title>XML Developer's Guide</Title>
        <Price>44.95</Price>
      </Book>
      <Book id="bk000"></Book>
      <Book id="bk331" genre="Computer" editorEmail="someone@example.com">
        <Author>Spencer, Phil</Author>
        <Title>Developing Applications with Visual Basic .NET</Title>
        <Price>45.95</Price>
      </Book>
      <Book id="bk999"></Book>
    </Catalog>
    ```

    修改的 XML：

    ```xml
    <?xml version="1.0"?>
    <Catalog>
      <Book id="bk101" editorEmail="someone@example.com">
        <Author>Garghentini, Davide</Author>
        <Title>XML Developer's Guide</Title>
        <Price>44.95</Price>
      </Book>
      <Book id="bk000"></Book>
      <Book id="bk331" editorEmail="someone@example.com">
        <Author>Spencer, Phil</Author>
        <Title>Developing Applications with Visual Basic .NET</Title>
        <Price>45.95</Price>
      </Book></Catalog>
    ```

    若要从 XML 文本中删除所有元素或属性，请获取对 XML 文本的引用并调用 <xref:System.Xml.Linq.XElement.RemoveAll%2A> 方法。

### <a name="to-modify-an-xml-literal"></a>修改 XML 文本

1. 若要更改 XML 元素的名称，请首先获取对元素的引用。 然后，你可以创建一个新的 <xref:System.Xml.Linq.XElement> 对象，该对象具有新名称，并将新的 <xref:System.Xml.Linq.XElement> 对象传递到现有 <xref:System.Xml.Linq.XElement> 对象的 <xref:System.Xml.Linq.XNode.ReplaceWith%2A> 方法。

    如果要替换的元素具有必须保留的子元素，请将新 <xref:System.Xml.Linq.XElement> 对象的值设置为现有元素的 <xref:System.Xml.Linq.XContainer.Nodes%2A> 属性。 这会将新元素的值设置为现有元素的内部 XML。 否则，你可以将新元素的值设置为现有元素的 `Value` 属性。

    下面的代码示例用 \<Abstract > 元素替换所有 \<说明 > 元素。 \<说明 > 元素的内容将保留在新的 \<Abstract > 元素中，方法是使用 <xref:System.Xml.Linq.XContainer.Nodes%2A> \<> 对象的 <xref:System.Xml.Linq.XElement> 属性。

    [!code-vb[VbXmlSamples2#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXmlSamples2/VB/Module2.vb#8)]

    下面的示例演示了此代码示例中的示例源 XML 和修改后的 XML。

    源 XML：

    ```xml
    <?xml version="1.0"?>
    <Catalog>
      <Book id="bk101">
        <Author>Garghentini, Davide</Author>
        <Title>XML Developer's Guide</Title>
        <Price>44.95</Price>
        <Description>
          An in-depth look at creating applications
          with <technology>XML</technology>. For
          <audience>beginners</audience> or
          <audience>advanced</audience> developers.
        </Description>
      </Book>
      <Book id="bk331">
        <Author>Spencer, Phil</Author>
        <Title>Developing Applications with Visual Basic .NET</Title>
        <Price>45.95</Price>
        <Description>
          Get the expert insights, practical code samples, and best
          practices you need to advance your expertise with
          <technology>Visual Basic .NET</technology>.
          Learn how to create faster, more reliable applications
          based on professional, pragmatic guidance by today's top
          <audience>developers</audience>.
        </Description>
      </Book>
    </Catalog>
    ```

    修改的 XML：

    ```xml
    <?xml version="1.0"?>
    <Catalog>
      <Book id="bk101">
        <Author>Garghentini, Davide</Author>
        <Title>XML Developer's Guide</Title>
        <MSRP>44.95</MSRP>    <Abstract>
          An in-depth look at creating applications
          with <technology>XML</technology>. For
          <audience>beginners</audience> or
          <audience>advanced</audience> developers.
        </Abstract>
      </Book>
      <Book id="bk331">
        <Author>Spencer, Phil</Author>
        <Title>Developing Applications with Visual Basic .NET</Title>
        <MSRP>45.95</MSRP>    <Abstract>
          Get the expert insights, practical code samples, and best
          practices you need to advance your expertise with
          <technology>Visual Basic .NET</technology>.
          Learn how to create faster, more reliable applications
          based on professional, pragmatic guidance by today's top
          <audience>developers</audience>.
        </Abstract>
      </Book>
    </Catalog>
    ```

## <a name="see-also"></a>另请参阅

- [在 Visual Basic 中操控 XML](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)
- [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)
- [如何：从文件、字符串或流加载 XML](../../../../visual-basic/programming-guide/language-features/xml/how-to-load-xml-from-a-file-string-or-stream.md)
- [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [Visual Basic 中的 LINQ 简介](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
