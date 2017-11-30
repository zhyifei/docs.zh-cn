---
title: "将对象层次结构映射到 XML 数据"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 450e350b-6a68-4634-a2a5-33f4dc33baf0
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 1bf43922fb702988e9057f541833cd58d33c820a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="mapping-the-object-hierarchy-to-xml-data"></a><span data-ttu-id="909b1-102">将对象层次结构映射到 XML 数据</span><span class="sxs-lookup"><span data-stu-id="909b1-102">Mapping the Object Hierarchy to XML Data</span></span>
<span data-ttu-id="909b1-103">当 XML 文档在内存中时，概念上的表示形式是树。</span><span class="sxs-lookup"><span data-stu-id="909b1-103">When an XML document is in memory, the conceptual representation is a tree.</span></span> <span data-ttu-id="909b1-104">编程时可使用对象层次结构访问树节点。</span><span class="sxs-lookup"><span data-stu-id="909b1-104">For programming, you have an object hierarchy to access the nodes of the tree.</span></span> <span data-ttu-id="909b1-105">下面的示例显示 XML 内容如何成为节点。</span><span class="sxs-lookup"><span data-stu-id="909b1-105">The following example shows you how the XML content becomes nodes.</span></span>  
  
 <span data-ttu-id="909b1-106">当将 XML 读入 XML 文档对象模型 (DOM) 中时，各片段被转换为节点，这些节点保留有关自身的附加元数据，如它们的节点类型和值。</span><span class="sxs-lookup"><span data-stu-id="909b1-106">As the XML is read into the XML Document Object Model (DOM), the pieces are translated into nodes, and these nodes retain additional metadata about themselves, such as their node type and values.</span></span> <span data-ttu-id="909b1-107">节点类型是节点的对象，确定可执行的操作以及可设置或检索的属性。</span><span class="sxs-lookup"><span data-stu-id="909b1-107">The node type is its object and is what determines what actions can be performed and what properties can be set or retrieved.</span></span>  
  
 <span data-ttu-id="909b1-108">如果具有下面的简单 XML：</span><span class="sxs-lookup"><span data-stu-id="909b1-108">If you have the following simple XML:</span></span>  
  
 <span data-ttu-id="909b1-109">**输入**</span><span class="sxs-lookup"><span data-stu-id="909b1-109">**Input**</span></span>  
  
```xml  
<book>  
    <title>The Handmaid's Tale</title>  
</book>  
```  
  
 <span data-ttu-id="909b1-110">输入在内存中表示为具有分配的节点类型属性的下列节点树：</span><span class="sxs-lookup"><span data-stu-id="909b1-110">The input is represented in memory as the following node tree with the assigned node type property:</span></span>  
  
 <span data-ttu-id="909b1-111">![示例节点树](../../../../docs/standard/data/xml/media/simple-xml.gif "Simple_XML")</span><span class="sxs-lookup"><span data-stu-id="909b1-111">![example node tree](../../../../docs/standard/data/xml/media/simple-xml.gif "Simple_XML")</span></span>  
<span data-ttu-id="909b1-112">book 和 title 节点树表示形式</span><span class="sxs-lookup"><span data-stu-id="909b1-112">Book and title node tree representation</span></span>  
  
 <span data-ttu-id="909b1-113">`book`元素将成为**XmlElement**对象、 下一个元素， `title`，也将变为**XmlElement**，而元素内容成为**XmlText**对象。</span><span class="sxs-lookup"><span data-stu-id="909b1-113">The `book` element becomes an **XmlElement** object, the next element, `title`, also becomes an **XmlElement**, while the element content becomes an **XmlText** object.</span></span> <span data-ttu-id="909b1-114">查看**XmlElement**方法和属性、 方法和属性将不同的方法和属性上可用**XmlText**对象。</span><span class="sxs-lookup"><span data-stu-id="909b1-114">In looking at the **XmlElement** methods and properties, the methods and properties are different than the methods and properties available on an **XmlText** object.</span></span> <span data-ttu-id="909b1-115">因此，知道 XML 标记成为的节点类型至关重要，因为其节点类型确定可以执行的操作。</span><span class="sxs-lookup"><span data-stu-id="909b1-115">So knowing what node type the XML markup becomes is vital, as its node type determines the actions that can be performed.</span></span>  
  
 <span data-ttu-id="909b1-116">下面的示例读入 XML 数据并根据节点类型写出不同的文本。</span><span class="sxs-lookup"><span data-stu-id="909b1-116">The following example reads in XML data and writes out different text, depending on the node type.</span></span> <span data-ttu-id="909b1-117">使用下面的 XML 数据文件作为输入， **items.xml**:</span><span class="sxs-lookup"><span data-stu-id="909b1-117">Using the following XML data file as input, **items.xml**:</span></span>  
  
 <span data-ttu-id="909b1-118">**输入**</span><span class="sxs-lookup"><span data-stu-id="909b1-118">**Input**</span></span>  
  
```xml  
<?xml version="1.0"?>  
<!-- This is a sample XML document -->  
<!DOCTYPE Items [<!ENTITY number "123">]>  
<Items>  
  <Item>Test with an entity: &number;</Item>  
  <Item>test with a child element <more/> stuff</Item>  
  <Item>test with a CDATA section <![CDATA[<456>]]> def</Item>  
  <Item>Test with a char entity: A</Item>  
  <!-- Fourteen chars in this element.-->  
  <Item>1234567890ABCD</Item>  
</Items>  
```  
  
 <span data-ttu-id="909b1-119">下面的代码示例读取**items.xml**文件并显示每个节点类型的信息。</span><span class="sxs-lookup"><span data-stu-id="909b1-119">The following code example reads the **items.xml** file and displays information for each node type.</span></span>  
  
```vb  
Imports System  
Imports System.IO  
Imports System.Xml  
  
Public Class Sample  
    Private Const filename As String = "items.xml"  
  
    Public Shared Sub Main()  
  
        Dim reader As XmlTextReader = Nothing  
  
        Try  
            ' Load the reader with the data file and   
            'ignore all white space nodes.   
            reader = New XmlTextReader(filename)  
            reader.WhitespaceHandling = WhitespaceHandling.None  
  
            ' Parse the file and display each of the nodes.  
            While reader.Read()  
                Select Case reader.NodeType  
                    Case XmlNodeType.Element  
                        Console.Write("<{0}>", reader.Name)  
                    Case XmlNodeType.Text  
                        Console.Write(reader.Value)  
                    Case XmlNodeType.CDATA  
                        Console.Write("<![CDATA[{0}]]>", reader.Value)  
                    Case XmlNodeType.ProcessingInstruction  
                        Console.Write("<?{0} {1}?>", reader.Name, reader.Value)  
                    Case XmlNodeType.Comment  
                        Console.Write("<!--{0}-->", reader.Value)  
                    Case XmlNodeType.XmlDeclaration  
                        Console.Write("<?xml version='1.0'?>")  
                    Case XmlNodeType.Document  
                    Case XmlNodeType.DocumentType  
                        Console.Write("<!DOCTYPE {0} [{1}]", reader.Name, reader.Value)  
                    Case XmlNodeType.EntityReference  
                        Console.Write(reader.Name)  
                    Case XmlNodeType.EndElement  
                        Console.Write("</{0}>", reader.Name)  
                End Select  
            End While  
  
        Finally  
            If Not (reader Is Nothing) Then  
                reader.Close()  
            End If  
        End Try  
    End Sub 'Main ' End class  
End Class 'Sample  
```  
  
```csharp  
using System;  
using System.IO;  
using System.Xml;  
  
public class Sample  
{  
    private const String filename = "items.xml";  
  
    public static void Main()  
    {  
        XmlTextReader reader = null;  
  
        try  
        {  
            // Load the reader with the data file and ignore   
            // all white space nodes.  
            reader = new XmlTextReader(filename);  
            reader.WhitespaceHandling = WhitespaceHandling.None;  
  
            // Parse the file and display each of the nodes.  
            while (reader.Read())  
            {  
                switch (reader.NodeType)  
                {  
                    case XmlNodeType.Element:  
                        Console.Write("<{0}>", reader.Name);  
                        break;  
                    case XmlNodeType.Text:  
                        Console.Write(reader.Value);  
                        break;  
                    case XmlNodeType.CDATA:  
                        Console.Write("<![CDATA[{0}]]>", reader.Value);  
                        break;  
                    case XmlNodeType.ProcessingInstruction:  
                        Console.Write("<?{0} {1}?>", reader.Name, reader.Value);  
                        break;  
                    case XmlNodeType.Comment:  
                        Console.Write("<!--{0}-->", reader.Value);  
                        break;  
                    case XmlNodeType.XmlDeclaration:  
                        Console.Write("<?xml version='1.0'?>");  
                        break;  
                    case XmlNodeType.Document:  
                        break;  
                    case XmlNodeType.DocumentType:  
                        Console.Write("<!DOCTYPE {0} [{1}]", reader.Name, reader.Value);  
                        break;  
                    case XmlNodeType.EntityReference:  
                        Console.Write(reader.Name);  
                        break;  
                    case XmlNodeType.EndElement:  
                        Console.Write("</{0}>", reader.Name);  
                        break;  
                }  
            }  
        }  
  
        finally  
        {  
            if (reader != null)  
                reader.Close();  
        }  
    }  
} // End class  
```  
  
 <span data-ttu-id="909b1-120">此示例的输出显示数据到节点类型的映射。</span><span class="sxs-lookup"><span data-stu-id="909b1-120">The output from the example reveals the mapping of the data to the node types.</span></span>  
  
 <span data-ttu-id="909b1-121">**输出**</span><span class="sxs-lookup"><span data-stu-id="909b1-121">**Output**</span></span>  
  
```xml  
<?xml version='1.0'?><!--This is a sample XML document --><!DOCTYPE Items [<!ENTITY number "123">]<Items><Item>Test with an entity: 123</Item><Item>test with a child element <more> stuff</Item><Item>test with a CDATA section <![CDATA[<456>]]> def</Item><Item>Test with a char entity: A</Item><--Fourteen chars in this element.--><Item>1234567890ABCD</Item></Items>  
```  
  
 <span data-ttu-id="909b1-122">通过逐行获取输入并使用从代码生成的输出，可以使用下表分析哪个节点测试生成哪些输出行，从而了解哪些 XML 数据成为哪种节点类型。</span><span class="sxs-lookup"><span data-stu-id="909b1-122">Taking the input one line at a time and using the output generated from the code, you can use the following table to analyze what node test generated which lines of output, thereby understanding what XML data became what kind of node type.</span></span>  
  
|<span data-ttu-id="909b1-123">输入</span><span class="sxs-lookup"><span data-stu-id="909b1-123">Input</span></span>|<span data-ttu-id="909b1-124">输出</span><span class="sxs-lookup"><span data-stu-id="909b1-124">Output</span></span>|<span data-ttu-id="909b1-125">节点类型测试</span><span class="sxs-lookup"><span data-stu-id="909b1-125">Node Type Test</span></span>|  
|-----------|------------|--------------------|  
|<span data-ttu-id="909b1-126">\<？ xml 版本 ="1.0"？ ></span><span class="sxs-lookup"><span data-stu-id="909b1-126">\<?xml version="1.0"?></span></span>|<span data-ttu-id="909b1-127">\<？ xml 版本 ='1.0 '？ ></span><span class="sxs-lookup"><span data-stu-id="909b1-127">\<?xml version='1.0'?></span></span>|<span data-ttu-id="909b1-128">XmlNodeType.XmlDeclaration</span><span class="sxs-lookup"><span data-stu-id="909b1-128">XmlNodeType.XmlDeclaration</span></span>|  
|<span data-ttu-id="909b1-129">\<！-这是一个示例 XML 文档--></span><span class="sxs-lookup"><span data-stu-id="909b1-129">\<!-- This is a sample XML document --></span></span>|<span data-ttu-id="909b1-130">\<！-这是一个示例 XML 文档--></span><span class="sxs-lookup"><span data-stu-id="909b1-130">\<!--This is a sample XML document --></span></span>|<span data-ttu-id="909b1-131">XmlNodeType.Comment</span><span class="sxs-lookup"><span data-stu-id="909b1-131">XmlNodeType.Comment</span></span>|  
|<span data-ttu-id="909b1-132">\<!DOCTYPE 项 [\<！实体数"123">] ></span><span class="sxs-lookup"><span data-stu-id="909b1-132">\<!DOCTYPE Items [\<!ENTITY number "123">]></span></span>|<span data-ttu-id="909b1-133">\<!DOCTYPE 项 [\<！实体数"123">]</span><span class="sxs-lookup"><span data-stu-id="909b1-133">\<!DOCTYPE Items [\<!ENTITY number "123">]</span></span>|<span data-ttu-id="909b1-134">XmlNodeType.DocumentType</span><span class="sxs-lookup"><span data-stu-id="909b1-134">XmlNodeType.DocumentType</span></span>|  
|<span data-ttu-id="909b1-135">\<项 ></span><span class="sxs-lookup"><span data-stu-id="909b1-135">\<Items></span></span>|<span data-ttu-id="909b1-136">\<项 ></span><span class="sxs-lookup"><span data-stu-id="909b1-136">\<Items></span></span>|<span data-ttu-id="909b1-137">XmlNodeType.Element</span><span class="sxs-lookup"><span data-stu-id="909b1-137">XmlNodeType.Element</span></span>|  
|<span data-ttu-id="909b1-138">\<Item></span><span class="sxs-lookup"><span data-stu-id="909b1-138">\<Item></span></span>|<span data-ttu-id="909b1-139">\<Item></span><span class="sxs-lookup"><span data-stu-id="909b1-139">\<Item></span></span>|<span data-ttu-id="909b1-140">XmlNodeType.Element</span><span class="sxs-lookup"><span data-stu-id="909b1-140">XmlNodeType.Element</span></span>|  
|<span data-ttu-id="909b1-141">以下实体一起测试：&number;</span><span class="sxs-lookup"><span data-stu-id="909b1-141">Test with an entity: &number;</span></span>|<span data-ttu-id="909b1-142">与以下实体一起测试：123</span><span class="sxs-lookup"><span data-stu-id="909b1-142">Test with an entity: 123</span></span>|<span data-ttu-id="909b1-143">XmlNodeType.Text</span><span class="sxs-lookup"><span data-stu-id="909b1-143">XmlNodeType.Text</span></span>|  
|<span data-ttu-id="909b1-144">\</ 项 ></span><span class="sxs-lookup"><span data-stu-id="909b1-144">\</Item></span></span>|<span data-ttu-id="909b1-145">\</ 项 ></span><span class="sxs-lookup"><span data-stu-id="909b1-145">\</Item></span></span>|<span data-ttu-id="909b1-146">XmlNodeType.EndElement</span><span class="sxs-lookup"><span data-stu-id="909b1-146">XmlNodeType.EndElement</span></span>|  
|<span data-ttu-id="909b1-147">\<Item></span><span class="sxs-lookup"><span data-stu-id="909b1-147">\<Item></span></span>|<span data-ttu-id="909b1-148">\<Item></span><span class="sxs-lookup"><span data-stu-id="909b1-148">\<Item></span></span>|<span data-ttu-id="909b1-149">XmNodeType.Element</span><span class="sxs-lookup"><span data-stu-id="909b1-149">XmNodeType.Element</span></span>|  
|<span data-ttu-id="909b1-150">与子元素一起测试</span><span class="sxs-lookup"><span data-stu-id="909b1-150">test with a child element</span></span>|<span data-ttu-id="909b1-151">与子元素一起测试</span><span class="sxs-lookup"><span data-stu-id="909b1-151">test with a child element</span></span>|<span data-ttu-id="909b1-152">XmlNodeType.Text</span><span class="sxs-lookup"><span data-stu-id="909b1-152">XmlNodeType.Text</span></span>|  
|<span data-ttu-id="909b1-153">\<更多 ></span><span class="sxs-lookup"><span data-stu-id="909b1-153">\<more></span></span>|<span data-ttu-id="909b1-154">\<更多 ></span><span class="sxs-lookup"><span data-stu-id="909b1-154">\<more></span></span>|<span data-ttu-id="909b1-155">XmlNodeType.Element</span><span class="sxs-lookup"><span data-stu-id="909b1-155">XmlNodeType.Element</span></span>|  
|<span data-ttu-id="909b1-156">stuff</span><span class="sxs-lookup"><span data-stu-id="909b1-156">stuff</span></span>|<span data-ttu-id="909b1-157">stuff</span><span class="sxs-lookup"><span data-stu-id="909b1-157">stuff</span></span>|<span data-ttu-id="909b1-158">XmlNodeType.Text</span><span class="sxs-lookup"><span data-stu-id="909b1-158">XmlNodeType.Text</span></span>|  
|<span data-ttu-id="909b1-159">\</ 项 ></span><span class="sxs-lookup"><span data-stu-id="909b1-159">\</Item></span></span>|<span data-ttu-id="909b1-160">\</ 项 ></span><span class="sxs-lookup"><span data-stu-id="909b1-160">\</Item></span></span>|<span data-ttu-id="909b1-161">XmlNodeType.EndElement</span><span class="sxs-lookup"><span data-stu-id="909b1-161">XmlNodeType.EndElement</span></span>|  
|<span data-ttu-id="909b1-162">\<Item></span><span class="sxs-lookup"><span data-stu-id="909b1-162">\<Item></span></span>|<span data-ttu-id="909b1-163">\<Item></span><span class="sxs-lookup"><span data-stu-id="909b1-163">\<Item></span></span>|<span data-ttu-id="909b1-164">XmlNodeType.Element</span><span class="sxs-lookup"><span data-stu-id="909b1-164">XmlNodeType.Element</span></span>|  
|<span data-ttu-id="909b1-165">与 CDATA 节一起测试</span><span class="sxs-lookup"><span data-stu-id="909b1-165">test with a CDATA section</span></span>|<span data-ttu-id="909b1-166">与 CDATA 节一起测试</span><span class="sxs-lookup"><span data-stu-id="909b1-166">test with a CDATA section</span></span>|<span data-ttu-id="909b1-167">XmlTest.Text</span><span class="sxs-lookup"><span data-stu-id="909b1-167">XmlTest.Text</span></span>|  
|<span data-ttu-id="909b1-168">< ！[CDATA [\<456 >]]\></span><span class="sxs-lookup"><span data-stu-id="909b1-168"><![CDATA[\<456>]]\></span></span>|<span data-ttu-id="909b1-169">< ！[CDATA [\<456 >]]\></span><span class="sxs-lookup"><span data-stu-id="909b1-169"><![CDATA[\<456>]]\></span></span>|<span data-ttu-id="909b1-170">XmlTest.CDATA</span><span class="sxs-lookup"><span data-stu-id="909b1-170">XmlTest.CDATA</span></span>|  
|<span data-ttu-id="909b1-171">def</span><span class="sxs-lookup"><span data-stu-id="909b1-171">def</span></span>|<span data-ttu-id="909b1-172">def</span><span class="sxs-lookup"><span data-stu-id="909b1-172">def</span></span>|<span data-ttu-id="909b1-173">XmlNodeType.Text</span><span class="sxs-lookup"><span data-stu-id="909b1-173">XmlNodeType.Text</span></span>|  
|<span data-ttu-id="909b1-174">\</ 项 ></span><span class="sxs-lookup"><span data-stu-id="909b1-174">\</Item></span></span>|<span data-ttu-id="909b1-175">\</ 项 ></span><span class="sxs-lookup"><span data-stu-id="909b1-175">\</Item></span></span>|<span data-ttu-id="909b1-176">XmlNodeType.EndElement</span><span class="sxs-lookup"><span data-stu-id="909b1-176">XmlNodeType.EndElement</span></span>|  
|<span data-ttu-id="909b1-177">\<Item></span><span class="sxs-lookup"><span data-stu-id="909b1-177">\<Item></span></span>|<span data-ttu-id="909b1-178">\<Item></span><span class="sxs-lookup"><span data-stu-id="909b1-178">\<Item></span></span>|<span data-ttu-id="909b1-179">XmlNodeType.Element</span><span class="sxs-lookup"><span data-stu-id="909b1-179">XmlNodeType.Element</span></span>|  
|<span data-ttu-id="909b1-180">与字符实体一起测试： &\#65;</span><span class="sxs-lookup"><span data-stu-id="909b1-180">Test with a char entity: &\#65;</span></span>|<span data-ttu-id="909b1-181">与字符实体一起测试：A</span><span class="sxs-lookup"><span data-stu-id="909b1-181">Test with a char entity: A</span></span>|<span data-ttu-id="909b1-182">XmlNodeType.Text</span><span class="sxs-lookup"><span data-stu-id="909b1-182">XmlNodeType.Text</span></span>|  
|<span data-ttu-id="909b1-183">\</ 项 ></span><span class="sxs-lookup"><span data-stu-id="909b1-183">\</Item></span></span>|<span data-ttu-id="909b1-184">\</ 项 ></span><span class="sxs-lookup"><span data-stu-id="909b1-184">\</Item></span></span>|<span data-ttu-id="909b1-185">XmlNodeType.EndElement</span><span class="sxs-lookup"><span data-stu-id="909b1-185">XmlNodeType.EndElement</span></span>|  
|<span data-ttu-id="909b1-186">\<！---> 十四个字符在此元素。</span><span class="sxs-lookup"><span data-stu-id="909b1-186">\<!-- Fourteen chars in this element.--></span></span>|<span data-ttu-id="909b1-187">\<---> 十四个字符在此元素。</span><span class="sxs-lookup"><span data-stu-id="909b1-187">\<--Fourteen chars in this element.--></span></span>|<span data-ttu-id="909b1-188">XmlNodeType.Comment</span><span class="sxs-lookup"><span data-stu-id="909b1-188">XmlNodeType.Comment</span></span>|  
|<span data-ttu-id="909b1-189">\<Item></span><span class="sxs-lookup"><span data-stu-id="909b1-189">\<Item></span></span>|<span data-ttu-id="909b1-190">\<Item></span><span class="sxs-lookup"><span data-stu-id="909b1-190">\<Item></span></span>|<span data-ttu-id="909b1-191">XmlNodeType.Element</span><span class="sxs-lookup"><span data-stu-id="909b1-191">XmlNodeType.Element</span></span>|  
|<span data-ttu-id="909b1-192">1234567890ABCD</span><span class="sxs-lookup"><span data-stu-id="909b1-192">1234567890ABCD</span></span>|<span data-ttu-id="909b1-193">1234567890ABCD</span><span class="sxs-lookup"><span data-stu-id="909b1-193">1234567890ABCD</span></span>|<span data-ttu-id="909b1-194">XmlNodeType.Text</span><span class="sxs-lookup"><span data-stu-id="909b1-194">XmlNodeType.Text</span></span>|  
|<span data-ttu-id="909b1-195">\</ 项 ></span><span class="sxs-lookup"><span data-stu-id="909b1-195">\</Item></span></span>|<span data-ttu-id="909b1-196">\</ 项 ></span><span class="sxs-lookup"><span data-stu-id="909b1-196">\</Item></span></span>|<span data-ttu-id="909b1-197">XmlNodeType.EndElement</span><span class="sxs-lookup"><span data-stu-id="909b1-197">XmlNodeType.EndElement</span></span>|  
|<span data-ttu-id="909b1-198">\</ 项 ></span><span class="sxs-lookup"><span data-stu-id="909b1-198">\</Items></span></span>|<span data-ttu-id="909b1-199">\</ 项 ></span><span class="sxs-lookup"><span data-stu-id="909b1-199">\</Items></span></span>|<span data-ttu-id="909b1-200">XmlNodeType.EndElement</span><span class="sxs-lookup"><span data-stu-id="909b1-200">XmlNodeType.EndElement</span></span>|  
  
 <span data-ttu-id="909b1-201">您必须知道分配的节点类型，因为节点类型控制哪些操作有效，以及可以设置和检索哪些属性。</span><span class="sxs-lookup"><span data-stu-id="909b1-201">You must know what node type is assigned, as the node type controls what kinds of actions are valid and what kind of properties you can set and retrieve.</span></span>  
  
 <span data-ttu-id="909b1-202">数据加载到通过 DOM 中时控制空白的节点创建**PreserveWhitespace**标志。</span><span class="sxs-lookup"><span data-stu-id="909b1-202">Node creation for white space is controlled when the data is loaded into the DOM by the **PreserveWhitespace** flag.</span></span> <span data-ttu-id="909b1-203">有关详细信息，请参阅[空白和有效空白处理加载 DOM 时](../../../../docs/standard/data/xml/white-space-and-significant-white-space-handling-when-loading-the-dom.md)。</span><span class="sxs-lookup"><span data-stu-id="909b1-203">For more information, see [White Space and Significant White Space Handling when Loading the DOM](../../../../docs/standard/data/xml/white-space-and-significant-white-space-handling-when-loading-the-dom.md).</span></span>  
  
 <span data-ttu-id="909b1-204">若要向 DOM 添加新节点，请参阅[将节点插入 XML 文档](../../../../docs/standard/data/xml/inserting-nodes-into-an-xml-document.md)。</span><span class="sxs-lookup"><span data-stu-id="909b1-204">To add new nodes to the DOM, see [Inserting Nodes into an XML Document](../../../../docs/standard/data/xml/inserting-nodes-into-an-xml-document.md).</span></span> <span data-ttu-id="909b1-205">若要从 DOM 中移除节点，请参阅[中移除节点、 内容和值从 XML 文档](../../../../docs/standard/data/xml/removing-nodes-content-and-values-from-an-xml-document.md)。</span><span class="sxs-lookup"><span data-stu-id="909b1-205">To remove nodes from the DOM, see [Removing Nodes, Content, and Values from an XML Document](../../../../docs/standard/data/xml/removing-nodes-content-and-values-from-an-xml-document.md).</span></span> <span data-ttu-id="909b1-206">若要修改 DOM 中的节点的内容，请参阅[修改节点、 内容和 XML 文档中的值](../../../../docs/standard/data/xml/modifying-nodes-content-and-values-in-an-xml-document.md)。</span><span class="sxs-lookup"><span data-stu-id="909b1-206">To modify the content of nodes in the DOM, see [Modifying Nodes, Content, and Values in an XML Document](../../../../docs/standard/data/xml/modifying-nodes-content-and-values-in-an-xml-document.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="909b1-207">另请参阅</span><span class="sxs-lookup"><span data-stu-id="909b1-207">See Also</span></span>  
 [<span data-ttu-id="909b1-208">XML 文档对象模型 (DOM)</span><span class="sxs-lookup"><span data-stu-id="909b1-208">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
