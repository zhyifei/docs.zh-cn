---
title: 如何：修改 XML 文本 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- XML axis [Visual Basic], Value
- XML literals [Visual Basic]
- XML literals [Visual Basic], modifying
ms.assetid: 4e864522-a37a-43a2-8236-af80277c5482
ms.openlocfilehash: 6e11c1ed4cfe4edc1c88dbbff2e9f555b1a028c4
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2019
ms.locfileid: "56974713"
---
# <a name="how-to-modify-xml-literals-visual-basic"></a><span data-ttu-id="4eb1b-102">如何：修改 XML 文本 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4eb1b-102">How to: Modify XML Literals (Visual Basic)</span></span>
<span data-ttu-id="4eb1b-103">Visual Basic 提供方便的方式来修改 XML 文本。</span><span class="sxs-lookup"><span data-stu-id="4eb1b-103">Visual Basic provides convenient ways to modify XML literals.</span></span> <span data-ttu-id="4eb1b-104">可以添加或删除元素和属性，并还可以使用新的 XML 元素来替换现有元素。</span><span class="sxs-lookup"><span data-stu-id="4eb1b-104">You can add or delete elements and attributes, and you can also replace an existing element with a new XML element.</span></span> <span data-ttu-id="4eb1b-105">本主题提供如何修改现有 XML 文本的几个示例。</span><span class="sxs-lookup"><span data-stu-id="4eb1b-105">This topic provides several examples of how to modify an existing XML literal.</span></span>  
  
### <a name="to-modify-the-value-of-an-xml-literal"></a><span data-ttu-id="4eb1b-106">若要修改的 XML 文本值</span><span class="sxs-lookup"><span data-stu-id="4eb1b-106">To modify the value of an XML literal</span></span>  
  
1.  <span data-ttu-id="4eb1b-107">若要修改的 XML 文本的值，获取对 XML 文本，并且已设置的引用`Value`属性设置为所需的值。</span><span class="sxs-lookup"><span data-stu-id="4eb1b-107">To modify the value of an XML literal, obtain a reference to the XML literal and set the `Value` property to the desired value.</span></span>  
  
     <span data-ttu-id="4eb1b-108">以下代码示例将更新的所有值\<价格 > XML 文档中的元素。</span><span class="sxs-lookup"><span data-stu-id="4eb1b-108">The following code example updates the value of all the \<Price> elements in an XML document.</span></span>  
  
     [!code-vb[VbXmlSamples2#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXmlSamples2/VB/Module2.vb#4)]  
  
     <span data-ttu-id="4eb1b-109">下面显示了示例源为 XML 并修改此代码示例中的 XML。</span><span class="sxs-lookup"><span data-stu-id="4eb1b-109">The following shows sample source XML and modified XML from this code example.</span></span>  
  
    ```  
    Source XML:  
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
  
    Modified XML:  
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
    >  <span data-ttu-id="4eb1b-110">`Value`属性是指集合中的第一个 XML 元素。</span><span class="sxs-lookup"><span data-stu-id="4eb1b-110">The `Value` property refers to the first XML element in a collection.</span></span> <span data-ttu-id="4eb1b-111">如果不存在具有相同的名称在集合中的多个元素，则将设置`Value`属性会影响仅在集合中的第一个元素。</span><span class="sxs-lookup"><span data-stu-id="4eb1b-111">If there is more than one element that has the same name in a collection, setting the `Value` property affects only the first element in the collection.</span></span>  
  
### <a name="to-add-an-attribute-to-an-xml-literal"></a><span data-ttu-id="4eb1b-112">将属性添加到 XML 文本</span><span class="sxs-lookup"><span data-stu-id="4eb1b-112">To add an attribute to an XML literal</span></span>  
  
1.  <span data-ttu-id="4eb1b-113">若要将属性添加到 XML 文本，首先获取对 XML 文本的引用。</span><span class="sxs-lookup"><span data-stu-id="4eb1b-113">To add an attribute to an XML literal, first obtain a reference to the XML literal.</span></span> <span data-ttu-id="4eb1b-114">然后可以通过添加新的 XML 特性轴属性添加一个属性。</span><span class="sxs-lookup"><span data-stu-id="4eb1b-114">You can then add an attribute by adding a new XML attribute axis property.</span></span> <span data-ttu-id="4eb1b-115">您还可以添加一个新<xref:System.Xml.Linq.XAttribute>对象与 XML 文本使用<xref:System.Xml.Linq.XContainer.Add%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="4eb1b-115">You can also add a new <xref:System.Xml.Linq.XAttribute> object to the XML literal by using the <xref:System.Xml.Linq.XContainer.Add%2A> method.</span></span> <span data-ttu-id="4eb1b-116">下面的示例显示了这两个选项。</span><span class="sxs-lookup"><span data-stu-id="4eb1b-116">The following example shows both options.</span></span>  
  
     [!code-vb[VbXmlSamples2#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXmlSamples2/VB/Module2.vb#5)]  
  
     <span data-ttu-id="4eb1b-117">下面显示了示例源为 XML 并修改此代码示例中的 XML。</span><span class="sxs-lookup"><span data-stu-id="4eb1b-117">The following shows sample source XML and modified XML from this code example.</span></span>  
  
    ```  
    Source XML:  
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
  
    Modified XML:  
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
  
     <span data-ttu-id="4eb1b-118">有关 XML 特性轴属性的详细信息，请参阅[XML 特性轴属性](../../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md)。</span><span class="sxs-lookup"><span data-stu-id="4eb1b-118">For more information about XML attribute axis properties, see [XML Attribute Axis Property](../../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md).</span></span>  
  
### <a name="to-add-an-element-to-an-xml-literal"></a><span data-ttu-id="4eb1b-119">若要将元素添加到 XML 文本</span><span class="sxs-lookup"><span data-stu-id="4eb1b-119">To add an element to an XML literal</span></span>  
  
1.  <span data-ttu-id="4eb1b-120">若要将元素添加到 XML 文本，首先获取对 XML 文本的引用。</span><span class="sxs-lookup"><span data-stu-id="4eb1b-120">To add an element to an XML literal, first obtain a reference to the XML literal.</span></span> <span data-ttu-id="4eb1b-121">然后，可以添加一个新<xref:System.Xml.Linq.XElement>对象使用的元素的最后一个子元素作为<xref:System.Xml.Linq.XContainer.Add%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="4eb1b-121">You can then add a new <xref:System.Xml.Linq.XElement> object as the last sub-element of the element by using the <xref:System.Xml.Linq.XContainer.Add%2A> method.</span></span> <span data-ttu-id="4eb1b-122">您可以添加一个新<xref:System.Xml.Linq.XElement>对象使用的第一个子元素作为<xref:System.Xml.Linq.XContainer.AddFirst%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="4eb1b-122">You can add a new <xref:System.Xml.Linq.XElement> object as the first sub-element by using the <xref:System.Xml.Linq.XContainer.AddFirst%2A> method.</span></span>  
  
     <span data-ttu-id="4eb1b-123">若要在特定位置相对于其他子元素添加一个新的元素，请首先获取对相邻的子元素的引用。</span><span class="sxs-lookup"><span data-stu-id="4eb1b-123">To add a new element in a specific location relative to other sub-elements, first obtain a reference to an adjacent sub-element.</span></span> <span data-ttu-id="4eb1b-124">然后，可以添加新<xref:System.Xml.Linq.XElement>对象使用相邻的子元素之前的<xref:System.Xml.Linq.XNode.AddBeforeSelf%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="4eb1b-124">You can then add the new <xref:System.Xml.Linq.XElement> object before the adjacent sub-element by using the <xref:System.Xml.Linq.XNode.AddBeforeSelf%2A> method.</span></span> <span data-ttu-id="4eb1b-125">您还可以添加新<xref:System.Xml.Linq.XElement>通过使用相邻的子元素之后的对象<xref:System.Xml.Linq.XNode.AddAfterSelf%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="4eb1b-125">You can also add the new <xref:System.Xml.Linq.XElement> object after the adjacent sub-element by using the <xref:System.Xml.Linq.XNode.AddAfterSelf%2A> method.</span></span>  
  
     <span data-ttu-id="4eb1b-126">下面的示例显示了每种技术的示例。</span><span class="sxs-lookup"><span data-stu-id="4eb1b-126">The following example shows examples of each of these techniques.</span></span>  
  
     [!code-vb[VbXmlSamples2#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXmlSamples2/VB/Module2.vb#6)]  
  
     <span data-ttu-id="4eb1b-127">下面显示了示例源为 XML 并修改此代码示例中的 XML。</span><span class="sxs-lookup"><span data-stu-id="4eb1b-127">The following shows sample source XML and modified XML from this code example.</span></span>  
  
    ```  
    Source XML:  
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
  
    Modified XML:  
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
  
### <a name="to-remove-an-element-or-attribute-from-an-xml-literal"></a><span data-ttu-id="4eb1b-128">若要从 XML 文本中移除的元素或属性</span><span class="sxs-lookup"><span data-stu-id="4eb1b-128">To remove an element or attribute from an XML literal</span></span>  
  
1.  <span data-ttu-id="4eb1b-129">若要从 XML 文本中删除一个元素或属性，请获取对元素或属性与调用的引用`Remove`方法，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="4eb1b-129">To remove an element or an attribute from an XML literal, obtain a reference to the element or attribute and call the `Remove` method, as shown in the following example.</span></span>  
  
     [!code-vb[VbXmlSamples2#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXmlSamples2/VB/Module2.vb#7)]  
  
     <span data-ttu-id="4eb1b-130">下面显示了示例源为 XML 并修改此代码示例中的 XML。</span><span class="sxs-lookup"><span data-stu-id="4eb1b-130">The following shows sample source XML and modified XML from this code example.</span></span>  
  
    ```  
    Source XML:  
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
  
    Modified XML:  
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
  
     <span data-ttu-id="4eb1b-131">若要从 XML 文本中移除所有元素或属性，获取对 XML 文本的引用，并调用<xref:System.Xml.Linq.XElement.RemoveAll%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="4eb1b-131">To remove all elements or attributes from an XML literal, obtain a reference to the XML literal and call the <xref:System.Xml.Linq.XElement.RemoveAll%2A> method.</span></span>  
  
### <a name="to-modify-an-xml-literal"></a><span data-ttu-id="4eb1b-132">若要修改 XML 文本</span><span class="sxs-lookup"><span data-stu-id="4eb1b-132">To modify an XML literal</span></span>  
  
1.  <span data-ttu-id="4eb1b-133">若要更改的 XML 元素的名称，首先获取对元素的引用。</span><span class="sxs-lookup"><span data-stu-id="4eb1b-133">To change the name of an XML element, first obtain a reference to the element.</span></span> <span data-ttu-id="4eb1b-134">然后创建一个新<xref:System.Xml.Linq.XElement>有一个新的命名并传递新的对象<xref:System.Xml.Linq.XElement>对象传递给<xref:System.Xml.Linq.XNode.ReplaceWith%2A>方法的现有<xref:System.Xml.Linq.XElement>对象。</span><span class="sxs-lookup"><span data-stu-id="4eb1b-134">You can then create a new <xref:System.Xml.Linq.XElement> object that has a new name and pass the new <xref:System.Xml.Linq.XElement> object to the <xref:System.Xml.Linq.XNode.ReplaceWith%2A> method of the existing <xref:System.Xml.Linq.XElement> object.</span></span>  
  
     <span data-ttu-id="4eb1b-135">如果要替换的元素具有必须保留的子元素，将新的值设置<xref:System.Xml.Linq.XElement>对象传递给<xref:System.Xml.Linq.XContainer.Nodes%2A>现有元素的属性。</span><span class="sxs-lookup"><span data-stu-id="4eb1b-135">If the element that you are replacing has sub-elements that must be preserved, set the value of the new <xref:System.Xml.Linq.XElement> object to the <xref:System.Xml.Linq.XContainer.Nodes%2A> property of the existing element.</span></span> <span data-ttu-id="4eb1b-136">这会将新元素的值设置为现有元素的内部 XML。</span><span class="sxs-lookup"><span data-stu-id="4eb1b-136">This will set the value of the new element to the inner XML of the existing element.</span></span> <span data-ttu-id="4eb1b-137">另外，可以将新元素的值设置`Value`现有元素的属性。</span><span class="sxs-lookup"><span data-stu-id="4eb1b-137">Otherwise, you can set the value of the new element to the `Value` property of the existing element.</span></span>  
  
     <span data-ttu-id="4eb1b-138">下面的代码示例替换所有\<说明 > 的元素\<抽象 > 元素。</span><span class="sxs-lookup"><span data-stu-id="4eb1b-138">The following code example replaces all \<Description> elements with an \<Abstract> element.</span></span> <span data-ttu-id="4eb1b-139">内容\<说明 > 元素保留在新\<抽象 > 元素中的使用<xref:System.Xml.Linq.XContainer.Nodes%2A>的属性\<说明 ><xref:System.Xml.Linq.XElement>对象。</span><span class="sxs-lookup"><span data-stu-id="4eb1b-139">The content of the \<Description> element is preserved in the new \<Abstract> element by using the <xref:System.Xml.Linq.XContainer.Nodes%2A> property of the \<Description> <xref:System.Xml.Linq.XElement> object.</span></span>  
  
     [!code-vb[VbXmlSamples2#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXmlSamples2/VB/Module2.vb#8)]  
  
     <span data-ttu-id="4eb1b-140">下面显示了示例源为 XML 并修改此代码示例中的 XML。</span><span class="sxs-lookup"><span data-stu-id="4eb1b-140">The following shows sample source XML and modified XML from this code example.</span></span>  
  
    ```  
    Source XML:  
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
  
    Modified XML:  
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
  
## <a name="see-also"></a><span data-ttu-id="4eb1b-141">请参阅</span><span class="sxs-lookup"><span data-stu-id="4eb1b-141">See also</span></span>
- [<span data-ttu-id="4eb1b-142">在 Visual Basic 中操控 XML</span><span class="sxs-lookup"><span data-stu-id="4eb1b-142">Manipulating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)
- [<span data-ttu-id="4eb1b-143">XML</span><span class="sxs-lookup"><span data-stu-id="4eb1b-143">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)
- [<span data-ttu-id="4eb1b-144">如何：从文件、 字符串或 Stream 加载 XML</span><span class="sxs-lookup"><span data-stu-id="4eb1b-144">How to: Load XML from a File, String, or Stream</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-load-xml-from-a-file-string-or-stream.md)
- [<span data-ttu-id="4eb1b-145">LINQ</span><span class="sxs-lookup"><span data-stu-id="4eb1b-145">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [<span data-ttu-id="4eb1b-146">Visual Basic 中的 LINQ 简介</span><span class="sxs-lookup"><span data-stu-id="4eb1b-146">Introduction to LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
