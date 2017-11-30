---
title: "访问 DOM 中的属性"
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
ms.assetid: ce2df341-a1a4-4e97-8e1b-cd45b8e3e71e
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: a433ec5f83a50aa4fe4b2017a0dac3d2a5e5710c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="accessing-attributes-in-the-dom"></a><span data-ttu-id="e7ad9-102">访问 DOM 中的属性</span><span class="sxs-lookup"><span data-stu-id="e7ad9-102">Accessing Attributes in the DOM</span></span>
<span data-ttu-id="e7ad9-103">属性是元素的属性，不是元素的子级。</span><span class="sxs-lookup"><span data-stu-id="e7ad9-103">Attributes are properties of the element, not children of the element.</span></span> <span data-ttu-id="e7ad9-104">这一区别很重要，因为用来浏览 XML 文档对象模型 (DOM) 的同级、父级和子节点的方法不同。</span><span class="sxs-lookup"><span data-stu-id="e7ad9-104">This distinction is important because of the methods used to navigate sibling, parent, and child nodes of the XML Document Object Model (DOM).</span></span> <span data-ttu-id="e7ad9-105">例如， **PreviousSibling**和**NextSibling**方法不用来从元素导航，到属性或属性之间。</span><span class="sxs-lookup"><span data-stu-id="e7ad9-105">For example, the **PreviousSibling** and **NextSibling** methods are not used to navigate from an element to an attribute or between attributes.</span></span> <span data-ttu-id="e7ad9-106">相反，属性为元素的属性，归元素，具有**OwnerElement**属性而不**parentNode**属性，并且具有不同的浏览方法。</span><span class="sxs-lookup"><span data-stu-id="e7ad9-106">Instead, an attribute is a property of an element and is owned by an element, has an **OwnerElement** property and not a **parentNode** property, and has distinct methods of navigation.</span></span>  
  
 <span data-ttu-id="e7ad9-107">元素的当前节点时，请使用**HasAttribute**方法，以查看是否存在任何与元素关联的属性。</span><span class="sxs-lookup"><span data-stu-id="e7ad9-107">When the current node is an element, use the **HasAttribute** method to see if there are any attributes associated with the element.</span></span> <span data-ttu-id="e7ad9-108">如果已知元素具有属性，有多种方法可以访问这些属性。</span><span class="sxs-lookup"><span data-stu-id="e7ad9-108">Once it is known that an element has attributes, there are multiple methods for accessing attributes.</span></span> <span data-ttu-id="e7ad9-109">若要从元素中检索单个属性，可以使用**GetAttribute**和**GetAttributeNode**方法**XmlElement**或者，你可以获得所有属性到一个集合。</span><span class="sxs-lookup"><span data-stu-id="e7ad9-109">To retrieve a single attribute from the element, you can use the **GetAttribute** and **GetAttributeNode** methods of the **XmlElement** or you can obtain all the attributes into a collection.</span></span> <span data-ttu-id="e7ad9-110">如果需要循环访问集合，获取集合就很有用。</span><span class="sxs-lookup"><span data-stu-id="e7ad9-110">Obtaining the collection is useful if you need to iterate over the collection.</span></span> <span data-ttu-id="e7ad9-111">如果你想从元素的所有属性，使用**属性**要检索到一个集合的所有属性的元素的属性。</span><span class="sxs-lookup"><span data-stu-id="e7ad9-111">If you want all attributes from the element, use the **Attributes** property of the element to retrieve all the attributes into a collection.</span></span>  
  
## <a name="retrieving-all-attributes-into-a-collection"></a><span data-ttu-id="e7ad9-112">将所有属性检索到一个集合中</span><span class="sxs-lookup"><span data-stu-id="e7ad9-112">Retrieving All Attributes into a Collection</span></span>  
 <span data-ttu-id="e7ad9-113">如果您需要将所有元素节点的属性放入集合，调用**XmlElement.Attributes**属性。</span><span class="sxs-lookup"><span data-stu-id="e7ad9-113">If you want all the attributes of an element node put into a collection, call the **XmlElement.Attributes** property.</span></span> <span data-ttu-id="e7ad9-114">这将得到**XmlAttributeCollection**包含的元素的所有属性。</span><span class="sxs-lookup"><span data-stu-id="e7ad9-114">This gets the **XmlAttributeCollection** that contains all the attributes of an element.</span></span> <span data-ttu-id="e7ad9-115">**XmlAttributeCollection**类继承自**XmlNamedNode**映射。</span><span class="sxs-lookup"><span data-stu-id="e7ad9-115">The **XmlAttributeCollection** class inherits from the **XmlNamedNode** map.</span></span> <span data-ttu-id="e7ad9-116">因此，包括方法和属性可在集合上可用的命名的节点映射此外方法和属性特定于**XmlAttributeCollection**类，如**ItemOf**属性或**追加**方法。</span><span class="sxs-lookup"><span data-stu-id="e7ad9-116">Therefore, the methods and properties available on the collection include those available on a named node map in addition to methods and properties specific to the **XmlAttributeCollection** class, such as the **ItemOf** property or the **Append** method.</span></span> <span data-ttu-id="e7ad9-117">该属性集合中的每一项表示**XmlAttribute**节点。</span><span class="sxs-lookup"><span data-stu-id="e7ad9-117">Each item in the attribute collection represents an **XmlAttribute** node.</span></span> <span data-ttu-id="e7ad9-118">若要查找上一个元素的属性数，请获取**XmlAttributeCollection**，并使用**计数**属性以查看多少**XmlAttribute**节点在集合中。</span><span class="sxs-lookup"><span data-stu-id="e7ad9-118">To find the number of attributes on an element, get the **XmlAttributeCollection**, and use the **Count** property to see how many **XmlAttribute** nodes are in the collection.</span></span>  
  
 <span data-ttu-id="e7ad9-119">下面的代码示例演示如何检索一个属性集合，并通过**计数**方法作为循环索引，循环访问它。</span><span class="sxs-lookup"><span data-stu-id="e7ad9-119">The following code example shows how to retrieve an attribute collection and, using the **Count** method for the looping index, iterate over it.</span></span> <span data-ttu-id="e7ad9-120">然后，此代码显示如何从集合中检索单个属性并显示其值。</span><span class="sxs-lookup"><span data-stu-id="e7ad9-120">The code then shows how to retrieve a single attribute from the collection and display its value.</span></span>  
  
```vb  
Imports System  
Imports System.IO  
Imports System.Xml  
  
Public Class Sample  
  
    Public Shared Sub Main()  
  
        Dim doc As XmlDocument = New XmlDocument()  
        doc.LoadXml("<book genre='novel' ISBN='1-861001-57-5' misc='sale item'>" & _  
               "<title>The Handmaid's Tale</title>" & _  
               "<price>14.95</price>" & _  
               "</book>")  
  
        ' Move to an element.   
        Dim myElement As XmlElement = doc.DocumentElement  
  
        ' Create an attribute collection from the element.  
        Dim attrColl As XmlAttributeCollection = myElement.Attributes  
  
        ' Show the collection by iterating over it.  
        Console.WriteLine("Display all the attributes in the collection...")  
        Dim i As Integer  
        For i = 0 To attrColl.Count - 1  
            Console.Write("{0} = ", attrColl.ItemOf(i).Name)  
            Console.Write("{0}", attrColl.ItemOf(i).Value)  
            Console.WriteLine()  
        Next  
  
        ' Retrieve a single attribute from the collection; specifically, the  
        ' attribute with the name "misc".  
        Dim attr As XmlAttribute = attrColl("misc")  
  
        ' Retrieve the value from that attribute.  
        Dim miscValue As String = attr.InnerXml  
  
        Console.WriteLine("Display the attribute information.")  
        Console.WriteLine(miscValue)  
  
    End Sub  
End Class  
```  
  
```csharp  
using System;  
using System.IO;  
using System.Xml;  
  
public class Sample  
{  
  
    public static void Main()  
    {  
        XmlDocument doc = new XmlDocument();  
        doc.LoadXml("<book genre='novel' ISBN='1-861001-57-5' misc='sale item'>" +  
                      "<title>The Handmaid's Tale</title>" +  
                      "<price>14.95</price>" +  
                      "</book>");  
  
        // Move to an element.  
        XmlElement myElement = doc.DocumentElement;  
  
        // Create an attribute collection from the element.  
        XmlAttributeCollection attrColl = myElement.Attributes;  
  
        // Show the collection by iterating over it.  
        Console.WriteLine("Display all the attributes in the collection...");  
        for (int i = 0; i < attrColl.Count; i++)  
        {  
            Console.Write("{0} = ", attrColl[i].Name);  
            Console.Write("{0}", attrColl[i].Value);  
            Console.WriteLine();  
        }  
  
        // Retrieve a single attribute from the collection; specifically, the  
        // attribute with the name "misc".  
        XmlAttribute attr = attrColl["misc"];  
  
        // Retrieve the value from that attribute.  
        String miscValue = attr.InnerXml;  
  
        Console.WriteLine("Display the attribute information.");  
        Console.WriteLine(miscValue);  
  
    }  
}  
```  
  
 <span data-ttu-id="e7ad9-121">此示例显示以下输出内容：</span><span class="sxs-lookup"><span data-stu-id="e7ad9-121">This example displays the following output:</span></span>  
  
 <span data-ttu-id="e7ad9-122">**输出**</span><span class="sxs-lookup"><span data-stu-id="e7ad9-122">**Output**</span></span>  
  
 <span data-ttu-id="e7ad9-123">显示集合中的所有属性。</span><span class="sxs-lookup"><span data-stu-id="e7ad9-123">Display all the attributes in the collection.</span></span>  
  
```  
genre = novel  
ISBN = 1-861001-57-5  
misc = sale item  
Display the attribute information.  
sale item  
```  
  
 <span data-ttu-id="e7ad9-124">可按名称或索引号检索属性集合中的信息。</span><span class="sxs-lookup"><span data-stu-id="e7ad9-124">The information in an attribute collection can be retrieved by name or index number.</span></span> <span data-ttu-id="e7ad9-125">上例显示了如何按名称检索数据。</span><span class="sxs-lookup"><span data-stu-id="e7ad9-125">The example above shows how to retrieve data by name.</span></span> <span data-ttu-id="e7ad9-126">下例将显示如何按索引编号检索数据。</span><span class="sxs-lookup"><span data-stu-id="e7ad9-126">The next example shows how to retrieve data by index number.</span></span>  
  
 <span data-ttu-id="e7ad9-127">因为**XmlAttributeCollection**是集合并可以循环访问按名称或索引，此示例显示了选择从使用从零开始的索引和使用下面的文件，该集合的第一个属性**baseuri.xml**作为输入。</span><span class="sxs-lookup"><span data-stu-id="e7ad9-127">Because the **XmlAttributeCollection** is a collection and can be iterated over by name or index, this example shows selecting the first attribute out of the collection using a zero-based index and using the following file, **baseuri.xml**, as input.</span></span>  
  
### <a name="input"></a><span data-ttu-id="e7ad9-128">输入</span><span class="sxs-lookup"><span data-stu-id="e7ad9-128">Input</span></span>  
  
```xml  
<!-- XML fragment -->  
<book genre="novel">  
  <title>Pride And Prejudice</title>  
</book>  
```  
  
```vb  
Option Explicit On  
Option Strict On  
  
Imports System  
Imports System.IO  
Imports System.Xml  
  
Public Class Sample  
  
    Public Shared Sub Main()  
        ' Create the XmlDocument.  
        Dim doc As New XmlDocument()  
        doc.Load("http://localhost/baseuri.xml")  
  
        ' Display information on the attribute node. The value  
        ' returned for BaseURI is 'http://localhost/baseuri.xml'.  
        Dim attr As XmlAttribute = doc.DocumentElement.Attributes(0)  
        Console.WriteLine("Name of the attribute:  {0}", attr.Name)  
        Console.WriteLine("Base URI of the attribute:  {0}", attr.BaseURI)  
        Console.WriteLine("The value of the attribtue:  {0}", attr.InnerText)  
    End Sub 'Main   
End Class 'Sample  
```  
  
```csharp  
using System;  
using System.IO;  
using System.Xml;  
  
public class Sample  
{  
  public static void Main()  
  {  
    // Create the XmlDocument.  
    XmlDocument doc = new XmlDocument();  
  
    doc.Load("http://localhost/baseuri.xml");  
  
    // Display information on the attribute node. The value  
    // returned for BaseURI is 'http://localhost/baseuri.xml'.  
    XmlAttribute attr = doc.DocumentElement.Attributes[0];  
    Console.WriteLine("Name of the attribute:  {0}", attr.Name);  
    Console.WriteLine("Base URI of the attribute:  {0}", attr.BaseURI);  
    Console.WriteLine("The value of the attribtue:  {0}", attr.InnerText);  
  }  
}  
```  
  
## <a name="retrieving-an-individual-attribute-node"></a><span data-ttu-id="e7ad9-129">检索单个属性节点</span><span class="sxs-lookup"><span data-stu-id="e7ad9-129">Retrieving an Individual Attribute Node</span></span>  
 <span data-ttu-id="e7ad9-130">若要从元素中检索单个属性节点，请使用 <xref:System.Xml.XmlElement.GetAttributeNode%2A?displayProperty=nameWithType> 方法。</span><span class="sxs-lookup"><span data-stu-id="e7ad9-130">To retrieve a single attribute node from an element, the <xref:System.Xml.XmlElement.GetAttributeNode%2A?displayProperty=nameWithType> method is used.</span></span> <span data-ttu-id="e7ad9-131">它将返回类型的对象**XmlAttribute**。</span><span class="sxs-lookup"><span data-stu-id="e7ad9-131">It returns an object of type **XmlAttribute**.</span></span> <span data-ttu-id="e7ad9-132">一旦**XmlAttribute**，所有方法和属性中提供<xref:System.Xml.XmlAttribute?displayProperty=nameWithType>类都位于该对象，例如查找**OwnerElement**。</span><span class="sxs-lookup"><span data-stu-id="e7ad9-132">Once you have an **XmlAttribute**, all the methods and properties available in the <xref:System.Xml.XmlAttribute?displayProperty=nameWithType> class are available on that object, such as finding the **OwnerElement**.</span></span>  
  
```vb  
Imports System  
Imports System.IO  
Imports System.Xml  
  
Public Class Sample  
  
    Public Shared Sub Main()  
  
        Dim doc As XmlDocument = New XmlDocument()  
        doc.LoadXml("<book genre='novel' ISBN='1-861001-57-5' misc='sale item'>" & _  
               "<title>The Handmaid's Tale</title>" & _  
               "<price>14.95</price>" & _  
               "</book>")  
  
        ' Move to an element.  
        Dim root As XmlElement  
        root = doc.DocumentElement  
  
        ' Get an attribute.  
        Dim attr As XmlAttribute  
        attr = root.GetAttributeNode("ISBN")  
  
        ' Display the value of the attribute.  
        Dim attrValue As String  
        attrValue = attr.InnerXml  
        Console.WriteLine(attrValue)  
  
    End Sub  
End Class  
```  
  
```csharp  
using System;  
using System.IO;  
using System.Xml;  
  
 public class Sample  
 {  
      public static void Main()  
      {  
    XmlDocument doc = new XmlDocument();  
     doc.LoadXml("<book genre='novel' ISBN='1-861003-78' misc='sale item'>" +  
                   "<title>The Handmaid's Tale</title>" +  
                   "<price>14.95</price>" +  
                   "</book>");   
  
    // Move to an element.  
     XmlElement root = doc.DocumentElement;  
  
    // Get an attribute.  
     XmlAttribute attr = root.GetAttributeNode("ISBN");  
  
    // Display the value of the attribute.  
     String attrValue = attr.InnerXml;  
     Console.WriteLine(attrValue);  
  
    }  
}  
```  
  
 <span data-ttu-id="e7ad9-133">您也可以如前例所示，从属性集合中检索单个属性节点。</span><span class="sxs-lookup"><span data-stu-id="e7ad9-133">You can also do as shown in the previous example, where a single attribute node is retrieved from the attribute collection.</span></span> <span data-ttu-id="e7ad9-134">以下代码示例显示如何一行代码可以编写中检索单个属性按索引号从 XML 文档的根树，也称为**DocumentElement**属性。</span><span class="sxs-lookup"><span data-stu-id="e7ad9-134">The following code example shows how one line of code can be written to retrieve a single attribute by index number from the root of the XML document tree, also known as the **DocumentElement** property.</span></span>  
  
```  
XmlAttribute attr = doc.DocumentElement.Attributes[0];  
```  
  
## <a name="see-also"></a><span data-ttu-id="e7ad9-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e7ad9-135">See Also</span></span>  
 [<span data-ttu-id="e7ad9-136">XML 文档对象模型 (DOM)</span><span class="sxs-lookup"><span data-stu-id="e7ad9-136">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
