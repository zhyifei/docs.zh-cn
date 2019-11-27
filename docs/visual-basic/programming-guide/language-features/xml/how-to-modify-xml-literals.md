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
# <a name="how-to-modify-xml-literals-visual-basic"></a><span data-ttu-id="69456-102">如何：修改 XML 文本 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="69456-102">How to: Modify XML Literals (Visual Basic)</span></span>

<span data-ttu-id="69456-103">Visual Basic 提供了修改 XML 文本的便利方法。</span><span class="sxs-lookup"><span data-stu-id="69456-103">Visual Basic provides convenient ways to modify XML literals.</span></span> <span data-ttu-id="69456-104">您可以添加或删除元素和属性，还可以将现有元素替换为新的 XML 元素。</span><span class="sxs-lookup"><span data-stu-id="69456-104">You can add or delete elements and attributes, and you can also replace an existing element with a new XML element.</span></span> <span data-ttu-id="69456-105">本主题提供了几个示例，演示如何修改现有的 XML 文本。</span><span class="sxs-lookup"><span data-stu-id="69456-105">This topic provides several examples of how to modify an existing XML literal.</span></span>

### <a name="to-modify-the-value-of-an-xml-literal"></a><span data-ttu-id="69456-106">修改 XML 文本的值</span><span class="sxs-lookup"><span data-stu-id="69456-106">To modify the value of an XML literal</span></span>

1. <span data-ttu-id="69456-107">若要修改 XML 文本的值，请获取对 XML 文本的引用并将 `Value` 属性设置为所需的值。</span><span class="sxs-lookup"><span data-stu-id="69456-107">To modify the value of an XML literal, obtain a reference to the XML literal and set the `Value` property to the desired value.</span></span>

    <span data-ttu-id="69456-108">下面的代码示例更新 XML 文档中所有 \<Price > 元素的值。</span><span class="sxs-lookup"><span data-stu-id="69456-108">The following code example updates the value of all the \<Price> elements in an XML document.</span></span>

    [!code-vb[VbXmlSamples2#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXmlSamples2/VB/Module2.vb#4)]

    <span data-ttu-id="69456-109">下面的示例演示了此代码示例中的示例源 XML 和修改后的 XML。</span><span class="sxs-lookup"><span data-stu-id="69456-109">The following shows sample source XML and modified XML from this code example.</span></span>

    <span data-ttu-id="69456-110">源 XML：</span><span class="sxs-lookup"><span data-stu-id="69456-110">Source XML:</span></span>

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

    <span data-ttu-id="69456-111">修改的 XML：</span><span class="sxs-lookup"><span data-stu-id="69456-111">Modified XML:</span></span>

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
    > <span data-ttu-id="69456-112">`Value` 属性引用集合中的第一个 XML 元素。</span><span class="sxs-lookup"><span data-stu-id="69456-112">The `Value` property refers to the first XML element in a collection.</span></span> <span data-ttu-id="69456-113">如果集合中有多个具有相同名称的元素，则设置 `Value` 属性仅影响集合中的第一个元素。</span><span class="sxs-lookup"><span data-stu-id="69456-113">If there is more than one element that has the same name in a collection, setting the `Value` property affects only the first element in the collection.</span></span>

### <a name="to-add-an-attribute-to-an-xml-literal"></a><span data-ttu-id="69456-114">向 XML 文本添加特性</span><span class="sxs-lookup"><span data-stu-id="69456-114">To add an attribute to an XML literal</span></span>

1. <span data-ttu-id="69456-115">若要向 XML 文本添加特性，请首先获取对 XML 文本的引用。</span><span class="sxs-lookup"><span data-stu-id="69456-115">To add an attribute to an XML literal, first obtain a reference to the XML literal.</span></span> <span data-ttu-id="69456-116">然后，您可以通过添加一个新的 XML 特性轴属性来添加属性。</span><span class="sxs-lookup"><span data-stu-id="69456-116">You can then add an attribute by adding a new XML attribute axis property.</span></span> <span data-ttu-id="69456-117">还可以通过使用 <xref:System.Xml.Linq.XContainer.Add%2A> 方法将新的 <xref:System.Xml.Linq.XAttribute> 对象添加到 XML 文本中。</span><span class="sxs-lookup"><span data-stu-id="69456-117">You can also add a new <xref:System.Xml.Linq.XAttribute> object to the XML literal by using the <xref:System.Xml.Linq.XContainer.Add%2A> method.</span></span> <span data-ttu-id="69456-118">下面的示例演示了这两个选项。</span><span class="sxs-lookup"><span data-stu-id="69456-118">The following example shows both options.</span></span>

    [!code-vb[VbXmlSamples2#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXmlSamples2/VB/Module2.vb#5)]

    <span data-ttu-id="69456-119">下面的示例演示了此代码示例中的示例源 XML 和修改后的 XML。</span><span class="sxs-lookup"><span data-stu-id="69456-119">The following shows sample source XML and modified XML from this code example.</span></span>

    <span data-ttu-id="69456-120">源 XML：</span><span class="sxs-lookup"><span data-stu-id="69456-120">Source XML:</span></span>

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

    <span data-ttu-id="69456-121">修改的 XML：</span><span class="sxs-lookup"><span data-stu-id="69456-121">Modified XML:</span></span>

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

    <span data-ttu-id="69456-122">有关 XML 特性轴属性的详细信息，请参阅[Xml 特性轴属性](../../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md)。</span><span class="sxs-lookup"><span data-stu-id="69456-122">For more information about XML attribute axis properties, see [XML Attribute Axis Property](../../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md).</span></span>

### <a name="to-add-an-element-to-an-xml-literal"></a><span data-ttu-id="69456-123">向 XML 文本添加元素</span><span class="sxs-lookup"><span data-stu-id="69456-123">To add an element to an XML literal</span></span>

1. <span data-ttu-id="69456-124">若要将元素添加到 XML 文本，请首先获取对 XML 文本的引用。</span><span class="sxs-lookup"><span data-stu-id="69456-124">To add an element to an XML literal, first obtain a reference to the XML literal.</span></span> <span data-ttu-id="69456-125">然后，你可以通过使用 <xref:System.Xml.Linq.XContainer.Add%2A> 方法将新的 <xref:System.Xml.Linq.XElement> 对象添加为元素的最后一个子元素。</span><span class="sxs-lookup"><span data-stu-id="69456-125">You can then add a new <xref:System.Xml.Linq.XElement> object as the last sub-element of the element by using the <xref:System.Xml.Linq.XContainer.Add%2A> method.</span></span> <span data-ttu-id="69456-126">您可以通过使用 <xref:System.Xml.Linq.XContainer.AddFirst%2A> 方法添加新的 <xref:System.Xml.Linq.XElement> 对象作为第一个子元素。</span><span class="sxs-lookup"><span data-stu-id="69456-126">You can add a new <xref:System.Xml.Linq.XElement> object as the first sub-element by using the <xref:System.Xml.Linq.XContainer.AddFirst%2A> method.</span></span>

    <span data-ttu-id="69456-127">若要将新元素添加到相对于其他子元素的特定位置，请首先获取对相邻子元素的引用。</span><span class="sxs-lookup"><span data-stu-id="69456-127">To add a new element in a specific location relative to other sub-elements, first obtain a reference to an adjacent sub-element.</span></span> <span data-ttu-id="69456-128">然后，你可以通过使用 <xref:System.Xml.Linq.XNode.AddBeforeSelf%2A> 方法在相邻子元素之前添加新的 <xref:System.Xml.Linq.XElement> 对象。</span><span class="sxs-lookup"><span data-stu-id="69456-128">You can then add the new <xref:System.Xml.Linq.XElement> object before the adjacent sub-element by using the <xref:System.Xml.Linq.XNode.AddBeforeSelf%2A> method.</span></span> <span data-ttu-id="69456-129">还可以通过使用 <xref:System.Xml.Linq.XNode.AddAfterSelf%2A> 方法在相邻子元素之后添加新的 <xref:System.Xml.Linq.XElement> 对象。</span><span class="sxs-lookup"><span data-stu-id="69456-129">You can also add the new <xref:System.Xml.Linq.XElement> object after the adjacent sub-element by using the <xref:System.Xml.Linq.XNode.AddAfterSelf%2A> method.</span></span>

    <span data-ttu-id="69456-130">下面的示例显示了每种方法的示例。</span><span class="sxs-lookup"><span data-stu-id="69456-130">The following example shows examples of each of these techniques.</span></span>

    [!code-vb[VbXmlSamples2#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXmlSamples2/VB/Module2.vb#6)]

    <span data-ttu-id="69456-131">下面的示例演示了此代码示例中的示例源 XML 和修改后的 XML。</span><span class="sxs-lookup"><span data-stu-id="69456-131">The following shows sample source XML and modified XML from this code example.</span></span>

    <span data-ttu-id="69456-132">源 XML：</span><span class="sxs-lookup"><span data-stu-id="69456-132">Source XML:</span></span>

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

    <span data-ttu-id="69456-133">修改的 XML：</span><span class="sxs-lookup"><span data-stu-id="69456-133">Modified XML:</span></span>

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

### <a name="to-remove-an-element-or-attribute-from-an-xml-literal"></a><span data-ttu-id="69456-134">从 XML 文本中删除元素或属性</span><span class="sxs-lookup"><span data-stu-id="69456-134">To remove an element or attribute from an XML literal</span></span>

1. <span data-ttu-id="69456-135">若要从 XML 文本中删除某个元素或属性，请获取对该元素或属性的引用并调用 `Remove` 方法，如以下示例中所示。</span><span class="sxs-lookup"><span data-stu-id="69456-135">To remove an element or an attribute from an XML literal, obtain a reference to the element or attribute and call the `Remove` method, as shown in the following example.</span></span>

    [!code-vb[VbXmlSamples2#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXmlSamples2/VB/Module2.vb#7)]

    <span data-ttu-id="69456-136">下面的示例演示了此代码示例中的示例源 XML 和修改后的 XML。</span><span class="sxs-lookup"><span data-stu-id="69456-136">The following shows sample source XML and modified XML from this code example.</span></span>

    <span data-ttu-id="69456-137">源 XML：</span><span class="sxs-lookup"><span data-stu-id="69456-137">Source XML:</span></span>

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

    <span data-ttu-id="69456-138">修改的 XML：</span><span class="sxs-lookup"><span data-stu-id="69456-138">Modified XML:</span></span>

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

    <span data-ttu-id="69456-139">若要从 XML 文本中删除所有元素或属性，请获取对 XML 文本的引用并调用 <xref:System.Xml.Linq.XElement.RemoveAll%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="69456-139">To remove all elements or attributes from an XML literal, obtain a reference to the XML literal and call the <xref:System.Xml.Linq.XElement.RemoveAll%2A> method.</span></span>

### <a name="to-modify-an-xml-literal"></a><span data-ttu-id="69456-140">修改 XML 文本</span><span class="sxs-lookup"><span data-stu-id="69456-140">To modify an XML literal</span></span>

1. <span data-ttu-id="69456-141">若要更改 XML 元素的名称，请首先获取对元素的引用。</span><span class="sxs-lookup"><span data-stu-id="69456-141">To change the name of an XML element, first obtain a reference to the element.</span></span> <span data-ttu-id="69456-142">然后，你可以创建一个新的 <xref:System.Xml.Linq.XElement> 对象，该对象具有新名称，并将新的 <xref:System.Xml.Linq.XElement> 对象传递到现有 <xref:System.Xml.Linq.XElement> 对象的 <xref:System.Xml.Linq.XNode.ReplaceWith%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="69456-142">You can then create a new <xref:System.Xml.Linq.XElement> object that has a new name and pass the new <xref:System.Xml.Linq.XElement> object to the <xref:System.Xml.Linq.XNode.ReplaceWith%2A> method of the existing <xref:System.Xml.Linq.XElement> object.</span></span>

    <span data-ttu-id="69456-143">如果要替换的元素具有必须保留的子元素，请将新 <xref:System.Xml.Linq.XElement> 对象的值设置为现有元素的 <xref:System.Xml.Linq.XContainer.Nodes%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="69456-143">If the element that you are replacing has sub-elements that must be preserved, set the value of the new <xref:System.Xml.Linq.XElement> object to the <xref:System.Xml.Linq.XContainer.Nodes%2A> property of the existing element.</span></span> <span data-ttu-id="69456-144">这会将新元素的值设置为现有元素的内部 XML。</span><span class="sxs-lookup"><span data-stu-id="69456-144">This will set the value of the new element to the inner XML of the existing element.</span></span> <span data-ttu-id="69456-145">否则，你可以将新元素的值设置为现有元素的 `Value` 属性。</span><span class="sxs-lookup"><span data-stu-id="69456-145">Otherwise, you can set the value of the new element to the `Value` property of the existing element.</span></span>

    <span data-ttu-id="69456-146">下面的代码示例用 \<Abstract > 元素替换所有 \<说明 > 元素。</span><span class="sxs-lookup"><span data-stu-id="69456-146">The following code example replaces all \<Description> elements with an \<Abstract> element.</span></span> <span data-ttu-id="69456-147">\<说明 > 元素的内容将保留在新的 \<Abstract > 元素中，方法是使用 <xref:System.Xml.Linq.XContainer.Nodes%2A> \<> 对象的 <xref:System.Xml.Linq.XElement> 属性。</span><span class="sxs-lookup"><span data-stu-id="69456-147">The content of the \<Description> element is preserved in the new \<Abstract> element by using the <xref:System.Xml.Linq.XContainer.Nodes%2A> property of the \<Description> <xref:System.Xml.Linq.XElement> object.</span></span>

    [!code-vb[VbXmlSamples2#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXmlSamples2/VB/Module2.vb#8)]

    <span data-ttu-id="69456-148">下面的示例演示了此代码示例中的示例源 XML 和修改后的 XML。</span><span class="sxs-lookup"><span data-stu-id="69456-148">The following shows sample source XML and modified XML from this code example.</span></span>

    <span data-ttu-id="69456-149">源 XML：</span><span class="sxs-lookup"><span data-stu-id="69456-149">Source XML:</span></span>

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

    <span data-ttu-id="69456-150">修改的 XML：</span><span class="sxs-lookup"><span data-stu-id="69456-150">Modified XML:</span></span>

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

## <a name="see-also"></a><span data-ttu-id="69456-151">另请参阅</span><span class="sxs-lookup"><span data-stu-id="69456-151">See also</span></span>

- [<span data-ttu-id="69456-152">在 Visual Basic 中操控 XML</span><span class="sxs-lookup"><span data-stu-id="69456-152">Manipulating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)
- [<span data-ttu-id="69456-153">XML</span><span class="sxs-lookup"><span data-stu-id="69456-153">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)
- [<span data-ttu-id="69456-154">如何：从文件、字符串或流加载 XML</span><span class="sxs-lookup"><span data-stu-id="69456-154">How to: Load XML from a File, String, or Stream</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-load-xml-from-a-file-string-or-stream.md)
- [<span data-ttu-id="69456-155">LINQ</span><span class="sxs-lookup"><span data-stu-id="69456-155">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [<span data-ttu-id="69456-156">Visual Basic 中的 LINQ 简介</span><span class="sxs-lookup"><span data-stu-id="69456-156">Introduction to LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
