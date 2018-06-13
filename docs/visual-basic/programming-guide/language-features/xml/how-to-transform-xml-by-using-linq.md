---
title: 如何：使用 LINQ 转换 XML (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- XML [Visual Basic], transforming
- LINQ to XML [Visual Basic], transforming XML
ms.assetid: 815687f4-0bc2-4c0b-adc6-d78744aa356f
ms.openlocfilehash: 94ad5180c7921a5ace09f9161de5f275475e46d4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33652956"
---
# <a name="how-to-transform-xml-by-using-linq-visual-basic"></a><span data-ttu-id="56614-102">如何：使用 LINQ 转换 XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="56614-102">How to: Transform XML by Using LINQ (Visual Basic)</span></span>
<span data-ttu-id="56614-103">[XML 文本](../../../../visual-basic/language-reference/xml-literals/index.md)方便地从一个源读取的 XML 并将它转换为新的 XML 格式。</span><span class="sxs-lookup"><span data-stu-id="56614-103">[XML Literals](../../../../visual-basic/language-reference/xml-literals/index.md) make it easy to read XML from one source and transform it to a new XML format.</span></span> <span data-ttu-id="56614-104">你可以利用 LINQ 查询以检索内容后，若要转换，或将现有的文档中的内容更改为新的 XML 格式。</span><span class="sxs-lookup"><span data-stu-id="56614-104">You can take advantage of LINQ queries to retrieve the content to transform, or change content in an existing document to a new XML format.</span></span>  
  
 <span data-ttu-id="56614-105">本主题中的示例将转换为 HTML，以在浏览器中查看从 XML 源文档的内容。</span><span class="sxs-lookup"><span data-stu-id="56614-105">The example in this topic transforms content from an XML source document to HTML to be viewed in a browser.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-transform-an-xml-document"></a><span data-ttu-id="56614-106">要转换的 XML 文档</span><span class="sxs-lookup"><span data-stu-id="56614-106">To transform an XML document</span></span>  
  
1.  <span data-ttu-id="56614-107">在 Visual Studio 中，创建一个新的 Visual Basic 项目中**控制台应用程序**项目模板。</span><span class="sxs-lookup"><span data-stu-id="56614-107">In Visual Studio, create a new Visual Basic project in the **Console Application** project template.</span></span>  
  
2.  <span data-ttu-id="56614-108">双击要修改的 Visual Basic 代码的项目中创建的 Module1.vb 文件。</span><span class="sxs-lookup"><span data-stu-id="56614-108">Double-click the Module1.vb file created in the project to modify the Visual Basic code.</span></span> <span data-ttu-id="56614-109">以下代码添加到`Sub Main`的`Module1`模块。</span><span class="sxs-lookup"><span data-stu-id="56614-109">Add the following code to the `Sub Main` of the `Module1` module.</span></span> <span data-ttu-id="56614-110">此代码将创建源 XML 文档作为<xref:System.Xml.Linq.XDocument>对象。</span><span class="sxs-lookup"><span data-stu-id="56614-110">This code creates the source XML document as an <xref:System.Xml.Linq.XDocument> object.</span></span>  
  
    ```vb  
    Dim catalog =   
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
              Get the expert insights, practical code samples,   
              and best practices you need   
              to advance your expertise with <technology>Visual   
              Basic .NET</technology>.   
              Learn how to create faster, more reliable applications  
              based on professional,   
              pragmatic guidance by today's top <audience>developers</audience>.  
            </Description>  
          </Book>  
        </Catalog>  
    ```  
  
     <span data-ttu-id="56614-111">[如何： 从文件、 字符串或流加载 XML](../../../../visual-basic/programming-guide/language-features/xml/how-to-load-xml-from-a-file-string-or-stream.md)。</span><span class="sxs-lookup"><span data-stu-id="56614-111">[How to: Load XML from a File, String, or Stream](../../../../visual-basic/programming-guide/language-features/xml/how-to-load-xml-from-a-file-string-or-stream.md).</span></span>  
  
3.  <span data-ttu-id="56614-112">用于创建源 XML 文档的代码后, 添加以下代码以检索所有\<簿 > 对象元素并将它们转换为 HTML 文档。</span><span class="sxs-lookup"><span data-stu-id="56614-112">After the code to create the source XML document, add the following code to retrieve all the \<Book> elements from the object and transform them into an HTML document.</span></span> <span data-ttu-id="56614-113">列表\<簿 > 元素通过使用 LINQ 查询返回的集合创建<xref:System.Xml.Linq.XElement>包含转换后的 HTML 的对象。</span><span class="sxs-lookup"><span data-stu-id="56614-113">The list of \<Book> elements is created by using a LINQ query that returns a collection of <xref:System.Xml.Linq.XElement> objects that contain the transformed HTML.</span></span> <span data-ttu-id="56614-114">可以使用嵌入式的表达式可以将值更改的源文档中新的 XML 格式。</span><span class="sxs-lookup"><span data-stu-id="56614-114">You can use embedded expressions to put the values from the source document in the new XML format.</span></span>  
  
     <span data-ttu-id="56614-115">通过将生成的 HTML 文档写入到文件<xref:System.Xml.Linq.XElement.Save%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="56614-115">The resulting HTML document is written to a file by using the <xref:System.Xml.Linq.XElement.Save%2A> method.</span></span>  
  
    ```vb  
    Dim htmlOutput =   
      <html>  
        <body>  
          <%= From book In catalog.<Catalog>.<Book>   
              Select <div>  
                       <h1><%= book.<Title>.Value %></h1>  
                       <h3><%= "By " & book.<Author>.Value %></h3>  
                        <h3><%= "Price = " & book.<Price>.Value %></h3>  
                        <h2>Description</h2>  
                        <%= TransformDescription(book.<Description>(0)) %>  
                        <hr/>  
                      </div> %>  
        </body>  
      </html>  
  
    htmlOutput.Save("BookDescription.html")  
    ```  
  
4.  <span data-ttu-id="56614-116">后`Sub Main`的`Module1`，添加一个新方法 (`Sub`) 来转换\<说明 > 到指定的 HTML 格式的节点。</span><span class="sxs-lookup"><span data-stu-id="56614-116">After `Sub Main` of `Module1`, add a new method (`Sub`) to transform a \<Description> node into the specified HTML format.</span></span> <span data-ttu-id="56614-117">此方法由上一步中的代码调用和用于保留的格式\<说明 > 元素。</span><span class="sxs-lookup"><span data-stu-id="56614-117">This method is called by the code in the previous step and is used to preserve the format of the \<Description> elements.</span></span>  
  
     <span data-ttu-id="56614-118">此方法将子元素替换为\<说明 > 具有 HTML 元素。</span><span class="sxs-lookup"><span data-stu-id="56614-118">This method replaces sub-elements of the \<Description> element with HTML.</span></span> <span data-ttu-id="56614-119">`ReplaceWith`方法用于保留的子元素的位置。</span><span class="sxs-lookup"><span data-stu-id="56614-119">The `ReplaceWith` method is used to preserve the location of the sub-elements.</span></span> <span data-ttu-id="56614-120">转换后的内容的\<说明 > 元素包含在 HTML 段落 (\<p >) 元素。</span><span class="sxs-lookup"><span data-stu-id="56614-120">The transformed content of the \<Description> element is included in an HTML paragraph (\<p>) element.</span></span> <span data-ttu-id="56614-121"><xref:System.Xml.Linq.XContainer.Nodes%2A>属性用于检索的转换后的内容\<说明 > 元素。</span><span class="sxs-lookup"><span data-stu-id="56614-121">The <xref:System.Xml.Linq.XContainer.Nodes%2A> property is used to retrieve the transformed content of the \<Description> element.</span></span> <span data-ttu-id="56614-122">这可确保在转换后的内容中包含子元素。</span><span class="sxs-lookup"><span data-stu-id="56614-122">This ensures that sub-elements are included in the transformed content.</span></span>  
  
     <span data-ttu-id="56614-123">添加以下代码后的`Sub Main`的`Module1`。</span><span class="sxs-lookup"><span data-stu-id="56614-123">Add the following code after `Sub Main` of `Module1`.</span></span>  
  
    ```vb  
    Public Function TransformDescription(ByVal desc As XElement) As XElement  
  
      ' Replace <technology> elements with <b>.  
      Dim content = (From element In desc...<technology>).ToList()  
  
      If content.Count > 0 Then  
        For i = 0 To content.Count - 1  
          content(i).ReplaceWith(<b><%= content(i).Value %></b>)  
        Next  
      End If  
  
      ' Replace <audience> elements with <i>.  
      content = (From element In desc...<audience>).ToList()  
  
      If content.Count > 0 Then  
        For i = 0 To content.Count - 1  
          content(i).ReplaceWith(<i><%= content(i).Value %></i>)  
        Next  
      End If  
  
      ' Return the updated contents of the <Description> element.  
      Return <p><%= desc.Nodes %></p>  
    End Function  
    ```  
  
5.  <span data-ttu-id="56614-124">保存更改。</span><span class="sxs-lookup"><span data-stu-id="56614-124">Save your changes.</span></span>  
  
6.  <span data-ttu-id="56614-125">按 f5 键以运行代码。</span><span class="sxs-lookup"><span data-stu-id="56614-125">Press F5 to run the code.</span></span> <span data-ttu-id="56614-126">产生的保存的文档将如下所示：</span><span class="sxs-lookup"><span data-stu-id="56614-126">The resulting saved document will resemble the following:</span></span>  
  
    ```  
    <?xml version="1.0"?>  
    <html>  
      <body>  
        <div>  
          <h1>XML Developer's Guide</h1>  
          <h3>By Garghentini, Davide</h3>  
          <h3>Price = 44.95</h3>  
          <h2>Description</h2>  
          <p>  
            An in-depth look at creating applications  
            with <b>XML</b>. For   
            <i>beginners</i> or   
            <i>advanced</i> developers.  
          </p>  
          <hr />  
        </div>  
        <div>  
          <h1>Developing Applications with Visual Basic .NET</h1>  
          <h3>By Spencer, Phil</h3>  
          <h3>Price = 45.95</h3>  
          <h2>Description</h2>  
          <p>  
            Get the expert insights, practical code   
            samples, and best practices you need   
            to advance your expertise with <b>Visual   
            Basic .NET</b>. Learn how to create faster,  
            more reliable applications based on  
            professional, pragmatic guidance by today's   
            top <i>developers</i>.  
          </p>  
          <hr />  
        </div>  
      </body>  
    </html>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="56614-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="56614-127">See Also</span></span>  
 [<span data-ttu-id="56614-128">XML 文本</span><span class="sxs-lookup"><span data-stu-id="56614-128">XML Literals</span></span>](../../../../visual-basic/language-reference/xml-literals/index.md)  
 [<span data-ttu-id="56614-129">在 Visual Basic 中操控 XML</span><span class="sxs-lookup"><span data-stu-id="56614-129">Manipulating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)  
 [<span data-ttu-id="56614-130">XML</span><span class="sxs-lookup"><span data-stu-id="56614-130">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)  
 [<span data-ttu-id="56614-131">如何：从文件、字符串或流加载 XML</span><span class="sxs-lookup"><span data-stu-id="56614-131">How to: Load XML from a File, String, or Stream</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-load-xml-from-a-file-string-or-stream.md)  
 [<span data-ttu-id="56614-132">LINQ</span><span class="sxs-lookup"><span data-stu-id="56614-132">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)  
 [<span data-ttu-id="56614-133">Visual Basic 中的 LINQ 简介</span><span class="sxs-lookup"><span data-stu-id="56614-133">Introduction to LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
