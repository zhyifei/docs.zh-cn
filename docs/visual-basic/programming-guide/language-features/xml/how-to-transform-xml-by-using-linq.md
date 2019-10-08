---
title: 如何：使用 LINQ （Visual Basic）转换 XML
ms.date: 07/20/2015
helpviewer_keywords:
- XML [Visual Basic], transforming
- LINQ to XML [Visual Basic], transforming XML
ms.assetid: 815687f4-0bc2-4c0b-adc6-d78744aa356f
ms.openlocfilehash: 08378775f2c30d8ebfcc4f7ceea6fc3ecb2066e5
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/07/2019
ms.locfileid: "72003261"
---
# <a name="how-to-transform-xml-by-using-linq-visual-basic"></a>如何：使用 LINQ （Visual Basic）转换 XML
使用[Xml 文本](../../../../visual-basic/language-reference/xml-literals/index.md)可以轻松地从一个源读取 XML，并将其转换为新的 xml 格式。 您可以利用 LINQ 查询来检索要转换的内容，或者将现有文档中的内容更改为新的 XML 格式。  
  
 本主题中的示例将 XML 源文档中的内容转换为 HTML，以便在浏览器中查看。  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-transform-an-xml-document"></a>转换 XML 文档  
  
1. 在 Visual Studio 中，在 "**控制台应用程序**" 项目模板中创建新的 Visual Basic 项目。  
  
2. 双击在项目中创建的 Module1 文件以修改 Visual Basic 代码。 将以下代码添加到 @no__t 模块的 @no__t 0。 此代码创建源 XML 文档作为 @no__t 的对象。  
  
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
  
     [如何：从文件、字符串或流加载 XML @ no__t-0。  
  
3. 在代码中创建源 XML 文档后，添加以下代码以检索该对象中的所有 @no__t 0Book > 元素，并将其转换为 HTML 文档。 @No__t-0Book > 元素的列表是使用 LINQ 查询创建的，该查询返回包含已转换的 HTML 的 @no__t 1 对象的集合。 您可以使用嵌入式表达式将源文档中的值置于新的 XML 格式。  
  
     通过使用 <xref:System.Xml.Linq.XElement.Save%2A> 方法将生成的 HTML 文档写入文件。  
  
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
  
4. 在 @no__t `Module1` 后，添加一个新方法（`Sub`），以将 @no__t 3Description > 节点转换为指定的 HTML 格式。 此方法由上一步中的代码调用，用于保留 \<Description > 元素的格式。  
  
     此方法用 HTML 替换 \<Description > 元素的子元素。 @No__t-0 方法用于保留子元素的位置。 HTML 段落（\< p >）元素中包含 \<Description > 元素的转换内容。 @No__t-0 属性用于检索 @no__t 1Description > 元素的转换内容。 这可确保子元素包含在转换后的内容中。  
  
     将以下代码添加到 @no__t `Module1` 之后。  
  
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
  
5. 保存更改。  
  
6. 按 F5 运行代码。 生成的已保存文档将类似于以下内容：  
  
    ```html  
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
  
## <a name="see-also"></a>请参阅

- [XML 文本](../../../../visual-basic/language-reference/xml-literals/index.md)
- [在 Visual Basic 中操控 XML](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)
- [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)
- [如何：从文件、字符串或流加载 XML @ no__t-0
- [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [Visual Basic 中的 LINQ 简介](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
