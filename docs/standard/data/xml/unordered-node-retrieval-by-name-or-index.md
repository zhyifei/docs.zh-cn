---
title: "按名称或索引检索未排序节点"
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
ms.assetid: 2038a90b-92af-4a0a-baaa-08e688d95194
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: a8bea8f373dced08fd7a2a828255a593533df9d7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="unordered-node-retrieval-by-name-or-index"></a><span data-ttu-id="61259-102">按名称或索引检索未排序节点</span><span class="sxs-lookup"><span data-stu-id="61259-102">Unordered Node Retrieval by Name or Index</span></span>
<span data-ttu-id="61259-103">**XmlNamedNodeMap**被描述为 NamedNodeMap World Wide Web Consortium (W3C) 规范中，需要按其名称或索引并引用节点能够处理节点的无序的集。</span><span class="sxs-lookup"><span data-stu-id="61259-103">The **XmlNamedNodeMap** is described in the World Wide Web Consortium (W3C) specification as the NamedNodeMap and is required to handle an unordered set of nodes with the ability to reference nodes by their name or index.</span></span> <span data-ttu-id="61259-104">您有权访问的唯一方法**XmlNamedNodeMap**时**XmlNamedNodeMap**通过方法或属性返回。</span><span class="sxs-lookup"><span data-stu-id="61259-104">The only way you have access to an **XmlNamedNodeMap** is when an **XmlNamedNodeMap** is returned through a method or property.</span></span> <span data-ttu-id="61259-105">有三个方法或属性返回**XmlNamedNodeMap**:</span><span class="sxs-lookup"><span data-stu-id="61259-105">There are three methods or properties that return an **XmlNamedNodeMap**:</span></span>  
  
-   <span data-ttu-id="61259-106">XmlElement.Attributes</span><span class="sxs-lookup"><span data-stu-id="61259-106">XmlElement.Attributes</span></span>  
  
-   <span data-ttu-id="61259-107">XmlDocumentType.Entities</span><span class="sxs-lookup"><span data-stu-id="61259-107">XmlDocumentType.Entities</span></span>  
  
-   <span data-ttu-id="61259-108">XmlDocumentType.Notations</span><span class="sxs-lookup"><span data-stu-id="61259-108">XmlDocumentType.Notations</span></span>  
  
 <span data-ttu-id="61259-109">例如， **XmlDocumentType.Entities**属性获取的集合**XmlEntity**在文档类型声明中声明的节点。</span><span class="sxs-lookup"><span data-stu-id="61259-109">For example, the **XmlDocumentType.Entities** property gets the collection of **XmlEntity** nodes declared in the document type declaration.</span></span> <span data-ttu-id="61259-110">此集合返回作为**XmlNamedNodeMap**，并且你可以循环访问与使用集合**计数**属性并显示实体信息。</span><span class="sxs-lookup"><span data-stu-id="61259-110">This collection is returned as an **XmlNamedNodeMap**, and you can iterate through the collection with the use of the **Count** property and display entity information.</span></span> <span data-ttu-id="61259-111">有关循环访问的示例**XmlNamedNodeMap**，请参阅<xref:System.Xml.XmlDocumentType.Entities%2A>。</span><span class="sxs-lookup"><span data-stu-id="61259-111">For an example of iterating through an **XmlNamedNodeMap**, see <xref:System.Xml.XmlDocumentType.Entities%2A>.</span></span>  
  
 <span data-ttu-id="61259-112">**XmlAttributeCollection**派生自**XmlNamedNodeMap**且只有属性是可修改，而表示法和实体是只读的。</span><span class="sxs-lookup"><span data-stu-id="61259-112">The **XmlAttributeCollection** is derived from **XmlNamedNodeMap** and only attributes are modifiable, while notations and entities are read-only.</span></span> <span data-ttu-id="61259-113">使用**XmlNamedNodeMap**用于属性，可以获取这些基于其 XML 名称的属性的节点。</span><span class="sxs-lookup"><span data-stu-id="61259-113">Using the **XmlNamedNodeMap** for the attributes, you can get nodes for those attributes based on their XML names.</span></span> <span data-ttu-id="61259-114">这样，提供了一个处理元素节点的属性集合的简单方法。</span><span class="sxs-lookup"><span data-stu-id="61259-114">This provides an easy method for manipulating the collection of attributes on an element node.</span></span> <span data-ttu-id="61259-115">这可以直接与对照**XmlNodeList**，后者也实现**IEnumerable**接口，但使用索引访问器，而不是一个字符串。</span><span class="sxs-lookup"><span data-stu-id="61259-115">This can be contrasted directly with **XmlNodeList**, which also implements the **IEnumerable** interface, but with an index accessor rather than a string.</span></span> <span data-ttu-id="61259-116">**RemoveNamedItem**和**SetNamedItem**方法仅在针对**XmlAttributeCollection**。</span><span class="sxs-lookup"><span data-stu-id="61259-116">The **RemoveNamedItem** and **SetNamedItem** methods are only used against an **XmlAttributeCollection**.</span></span> <span data-ttu-id="61259-117">添加或移除属性集合，无论使用**AttributeCollection**或**XmlNamedNodeMap**实现，将修改元素的属性集合。</span><span class="sxs-lookup"><span data-stu-id="61259-117">Adding or removing from an attribute collection, whether using the **AttributeCollection** or the **XmlNamedNodeMap** implementation, modifies the attribute collection on the element.</span></span> <span data-ttu-id="61259-118">下面的代码示例显示如何移动属性并创建新属性。</span><span class="sxs-lookup"><span data-stu-id="61259-118">The following code example shows how to move an attribute and create a new attribute.</span></span>  
  
```vb  
Imports System  
Imports System.Xml  
  
Class test  
  
    Public Shared Sub Main()  
        Dim doc As New XmlDocument()  
        doc.LoadXml("<root> <child1 attr1='val1' attr2='val2'> text1 </child1> <child2 attr3='val3'> text2 </child2> </root> ")  
  
        ' Get the attributes of node "child2 "  
        Dim ac As XmlAttributeCollection = doc.DocumentElement.ChildNodes(1).Attributes  
  
        ' Print out the number of attributes and their names.  
        Console.WriteLine(("Number of Attributes: " + ac.Count))  
        Dim i As Integer  
        For i = 0 To ac.Count - 1  
            Console.WriteLine((i + 1 + ".  Attribute Name: '" + ac(i).Name + "'  Attribute Value:  '" + ac(i).Value + "'"))  
        Next i  
        ' Get the 'attr1' from child1.  
        Dim attr As XmlAttribute = doc.DocumentElement.ChildNodes(0).Attributes(0)  
  
        ' Add this attribute to the attributecollection "ac".  
        ac.SetNamedItem(attr)  
  
        ''attr1' will be removed from 'child1' and added to 'child2'.  
        ' Print out the number of attributes and their names.  
        Console.WriteLine(("Number of Attributes: " + ac.Count))  
  
        For i = 0 To ac.Count - 1  
            Console.WriteLine((i + 1 + ".  Attribute Name: '" + ac(i).Name + "'  Attribute Value:  '" + ac(i).Value + "'"))  
        Next i  
        ' Create a new attribute and add to the collection.  
        Dim attr2 As XmlAttribute = doc.CreateAttribute("attr4")  
        attr2.Value = "val4"  
        ac.SetNamedItem(attr2)  
  
        ' Print out the number of attributes and their names.  
        Console.WriteLine(("Number of Attributes: " + ac.Count))  
  
        For i = 0 To ac.Count - 1  
            Console.WriteLine((i + 1 + ".  Attribute Name: '" + ac(i).Name + "'  Attribute Value:  '" + ac(i).Value + "'"))  
        Next i  
    End Sub 'Main  
End Class 'test  
```  
  
```csharp  
using System;  
using System.Xml;  
class test {  
    public static void Main() {  
        XmlDocument doc = new XmlDocument();  
        doc.LoadXml( "<root> <child1 attr1='val1' attr2='val2'> text1 </child1> <child2 attr3='val3'> text2 </child2> </root> " );  
  
        // Get the attributes of node "child2"  
        XmlAttributeCollection ac = doc.DocumentElement.ChildNodes[1].Attributes;  
  
        // Print out the number of attributes and their names.  
        Console.WriteLine( "Number of Attributes: "+ac.Count );  
        for( int i = 0; i < ac.Count; i++ )  
            Console.WriteLine( (i+1) + ".  Attribute Name: '" +ac[i].Name+ "'  Attribute Value:  '"+ ac[i].Value +"'" );   
  
        // Get the 'attr1' from child1.  
        XmlAttribute attr = doc.DocumentElement.ChildNodes[0].Attributes[0];  
  
        // Add this attribute to the attributecollection "ac".  
        ac.SetNamedItem( attr );  
  
        // 'attr1' will be removed from 'child1' and added to 'child2'.  
        // Print out the number of attributes and their names.  
        Console.WriteLine( "Number of Attributes: "+ac.Count );          
        for( int i = 0; i < ac.Count; i++ )  
            Console.WriteLine( (i+1) + ".  Attribute Name: '" +ac[i].Name+ "'  Attribute Value:  '"+ ac[i].Value +"'" );   
  
        // Create a new attribute and add to the collection.  
        XmlAttribute attr2 = doc.CreateAttribute( "attr4" );  
        attr2.Value = "val4";  
        ac.SetNamedItem( attr2 );  
  
        // Print out the number of attributes and their names.  
        Console.WriteLine( "Number of Attributes: "+ac.Count );          
        for( int i = 0; i < ac.Count; i++ )  
            Console.WriteLine( (i+1) + ".  Attribute Name: '" +ac[i].Name+ "'  Attribute Value:  '"+ ac[i].Value +"'" );           
  
    }  
}  
```  
  
 <span data-ttu-id="61259-119">若要查看额外的代码示例，其中显示了从移除属性**AttributeCollection**，请参阅[XmlNamedNodeMap.RemoveNamedItem 方法](Overload:System.Xml.XmlNamedNodeMap.RemoveNamedItem)。</span><span class="sxs-lookup"><span data-stu-id="61259-119">To see an additional code example which shows an attribute being removed from an **AttributeCollection**, see [XmlNamedNodeMap.RemoveNamedItem Method](Overload:System.Xml.XmlNamedNodeMap.RemoveNamedItem).</span></span> <span data-ttu-id="61259-120">有关方法和属性的详细信息，请参阅[XmlNamedNodeMap 成员](AllMembers.T:System.Xml.XmlNamedNodeMap)。</span><span class="sxs-lookup"><span data-stu-id="61259-120">For more information on the methods and properties, see [XmlNamedNodeMap Members](AllMembers.T:System.Xml.XmlNamedNodeMap).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61259-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="61259-121">See Also</span></span>  
 [<span data-ttu-id="61259-122">XML 文档对象模型 (DOM)</span><span class="sxs-lookup"><span data-stu-id="61259-122">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
