---
title: "为 DOM 中的元素创建新属性"
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
ms.assetid: dd6dc920-b011-418a-b3db-f1580a7d9251
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 6970ffc38e900c9b47c58c8ae4b81b9551f5589b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="creating-new-attributes-for-elements-in-the-dom"></a><span data-ttu-id="d1f93-102">为 DOM 中的元素创建新属性</span><span class="sxs-lookup"><span data-stu-id="d1f93-102">Creating New Attributes for Elements in the DOM</span></span>
<span data-ttu-id="d1f93-103">创建新属性是不同于创建其他节点类型，因为属性不是节点，但是元素节点的属性和中包含**XmlAttributeCollection**与元素关联。</span><span class="sxs-lookup"><span data-stu-id="d1f93-103">Creating new attributes is different than creating other node types, because attributes are not nodes, but are properties of an element node and are contained in an **XmlAttributeCollection** associated with the element.</span></span> <span data-ttu-id="d1f93-104">有多种方法可创建属性并将其附加到元素：</span><span class="sxs-lookup"><span data-stu-id="d1f93-104">There are multiple ways to create an attribute and attach it to an element:</span></span>  
  
-   <span data-ttu-id="d1f93-105">获取元素节点并使用**SetAttribute**将属性添加到该元素的属性集合。</span><span class="sxs-lookup"><span data-stu-id="d1f93-105">Get the element node and use **SetAttribute** to add an attribute to the attribute collection of that element.</span></span>  
  
-   <span data-ttu-id="d1f93-106">创建**XmlAttribute**节点使用**CreateAttribute**方法，获取元素节点，然后使用**SetAttributeNode**将节点添加到属性集合的元素。</span><span class="sxs-lookup"><span data-stu-id="d1f93-106">Create an **XmlAttribute** node using the **CreateAttribute** method, get the element node, then use **SetAttributeNode** to add the node to the attribute collection of that element.</span></span>  
  
 <span data-ttu-id="d1f93-107">下面的示例演示如何将属性添加到元素使用**SetAttribute**方法。</span><span class="sxs-lookup"><span data-stu-id="d1f93-107">The following example shows how to add an attribute to an element using the **SetAttribute** method.</span></span>  
  
```vb  
Imports System  
Imports System.IO  
Imports System.Xml  
  
public class Sample  
  
  public shared sub Main()  
  
  Dim doc as XmlDocument = new XmlDocument()  
  doc.LoadXml("<book xmlns:bk='urn:samples' bk:ISBN='1-861001-57-5'>" & _  
              "<title>Pride And Prejudice</title>" & _  
              "</book>")  
  Dim root as XmlElement = doc.DocumentElement  
  
  'Add a new attribute.  
  root.SetAttribute("genre", "urn:samples", "novel")  
  
  Console.WriteLine("Display the modified XML...")  
  Console.WriteLine(doc.InnerXml)  
  
  end sub  
end class  
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
    doc.LoadXml("<book xmlns:bk='urn:samples' bk:ISBN='1-861001-57-5'>" +  
                "<title>Pride And Prejudice</title>" +  
                "</book>");  
    XmlElement root = doc.DocumentElement;  
  
    // Add a new attribute.  
    root.SetAttribute("genre", "urn:samples", "novel");  
  
    Console.WriteLine("Display the modified XML...");  
    Console.WriteLine(doc.InnerXml);  
  }  
```  
  
 <span data-ttu-id="d1f93-108">下面的示例演示一个新属性正在创建使用**CreateAttribute**方法。</span><span class="sxs-lookup"><span data-stu-id="d1f93-108">The following example shows a new attribute being created using the **CreateAttribute** method.</span></span> <span data-ttu-id="d1f93-109">然后，它演示添加到的属性集合的属性**簿**元素使用**SetAttributeNode**方法。</span><span class="sxs-lookup"><span data-stu-id="d1f93-109">It then shows the attribute added to the attribute collection of the **book** element using the **SetAttributeNode** method.</span></span>  
  
 <span data-ttu-id="d1f93-110">已知下列 XML：</span><span class="sxs-lookup"><span data-stu-id="d1f93-110">Given the following XML:</span></span>  
  
```xml  
<book genre='novel' ISBN='1-861001-57-5'>  
<title>Pride And Prejudice</title>  
</book>  
```  
  
 <span data-ttu-id="d1f93-111">创建一个新属性并为其提供值：</span><span class="sxs-lookup"><span data-stu-id="d1f93-111">create a new attribute and give it a value:</span></span>  
  
```vb  
Dim attr As XmlAttribute = doc.CreateAttribute("publisher")  
   attr.Value = "WorldWide Publishing"  
```  
  
```csharp  
XmlAttribute attr = doc.CreateAttribute("publisher");  
attr.Value = "WorldWide Publishing";  
```  
  
 <span data-ttu-id="d1f93-112">将其附加到此元素：</span><span class="sxs-lookup"><span data-stu-id="d1f93-112">and attach it to the element:</span></span>  
  
```vb  
doc.DocumentElement.SetAttributeNode(attr)  
```  
  
```csharp  
doc.DocumentElement.SetAttributeNode(attr);  
```  
  
 <span data-ttu-id="d1f93-113">**输出**</span><span class="sxs-lookup"><span data-stu-id="d1f93-113">**Output**</span></span>  
  
```xml  
<book genre="novel" ISBN="1-861001-57-5" publisher="WorldWide Publishing">  
<title>Pride And Prejudice</title>  
</book>  
```  
  
 <span data-ttu-id="d1f93-114">完整代码示例，请参阅<xref:System.Xml.XmlDocument.CreateAttribute%2A>。</span><span class="sxs-lookup"><span data-stu-id="d1f93-114">The full code sample can be found at <xref:System.Xml.XmlDocument.CreateAttribute%2A>.</span></span>  
  
 <span data-ttu-id="d1f93-115">你还可以创建**XmlAttribute**节点并使用**InsertBefore**或**InsertAfter**方法将其放在集合中的适当位置。</span><span class="sxs-lookup"><span data-stu-id="d1f93-115">You can also create an **XmlAttribute** node and use the **InsertBefore** or **InsertAfter** methods to place it in the appropriate position in the collection.</span></span> <span data-ttu-id="d1f93-116">如果具有相同名称的属性已在现有的属性集合中存在**XmlAttribute**节点删除从集合中的新**XmlAttribute**插入节点。</span><span class="sxs-lookup"><span data-stu-id="d1f93-116">If an attribute with the same name is already present in the attribute collection, the existing **XmlAttribute** node is removed from the collection and the new **XmlAttribute** node is inserted.</span></span> <span data-ttu-id="d1f93-117">这将进行相同的方式**SetAttribute**方法。</span><span class="sxs-lookup"><span data-stu-id="d1f93-117">This performs the same way as the **SetAttribute** method.</span></span> <span data-ttu-id="d1f93-118">这些方法作为参数，将现有节点作为执行操作的参考点执行**InsertBefore**和**InsertAfter**。</span><span class="sxs-lookup"><span data-stu-id="d1f93-118">These methods take, as a parameter, an existing node as a reference point to do the **InsertBefore** and **InsertAfter**.</span></span> <span data-ttu-id="d1f93-119">如果未提供指示插入新节点的默认位置的参考节点**InsertAfter**方法是在集合开头插入新节点。</span><span class="sxs-lookup"><span data-stu-id="d1f93-119">If you do not provide a reference node indicating where to insert the new node, the default for the **InsertAfter** method is to insert the new node at the beginning of the collection.</span></span> <span data-ttu-id="d1f93-120">默认位置**InsertBefore**，如果未不提供任何参考节点，是在集合末尾。</span><span class="sxs-lookup"><span data-stu-id="d1f93-120">The default position for the **InsertBefore**, if no reference node is provided, is at the end of the collection.</span></span>  
  
 <span data-ttu-id="d1f93-121">如果你创建**XmlNamedNodeMap**属性，您可以添加的属性名称使用<xref:System.Xml.XmlNamedNodeMap.SetNamedItem%2A>。</span><span class="sxs-lookup"><span data-stu-id="d1f93-121">If you created an **XmlNamedNodeMap** of attributes, you can add an attribute by name using the <xref:System.Xml.XmlNamedNodeMap.SetNamedItem%2A>.</span></span> <span data-ttu-id="d1f93-122">有关详细信息，请参阅[Namednodemap 和 Nodelist 中的节点集合](../../../../docs/standard/data/xml/node-collections-in-namednodemaps-and-nodelists.md)。</span><span class="sxs-lookup"><span data-stu-id="d1f93-122">For more information, see [Node Collections in NamedNodeMaps and NodeLists](../../../../docs/standard/data/xml/node-collections-in-namednodemaps-and-nodelists.md).</span></span>  
  
## <a name="default-attributes"></a><span data-ttu-id="d1f93-123">默认属性</span><span class="sxs-lookup"><span data-stu-id="d1f93-123">Default Attributes</span></span>  
 <span data-ttu-id="d1f93-124">如果创建一个声明为具有默认属性的元素，则 XML 文档对象模型 (DOM) 创建一个带默认值的新默认属性并将其附加到该元素。</span><span class="sxs-lookup"><span data-stu-id="d1f93-124">If you create an element that is declared to have a default attribute, then a new default attribute with its default value is created by the XML Document Object Model (DOM) and attached to the element.</span></span> <span data-ttu-id="d1f93-125">此时还创建默认属性的子节点。</span><span class="sxs-lookup"><span data-stu-id="d1f93-125">The child nodes of the default attribute are also created at this time.</span></span>  
  
## <a name="attribute-child-nodes"></a><span data-ttu-id="d1f93-126">属性子节点</span><span class="sxs-lookup"><span data-stu-id="d1f93-126">Attribute Child Nodes</span></span>  
 <span data-ttu-id="d1f93-127">属性节点的值成为它的子节点。</span><span class="sxs-lookup"><span data-stu-id="d1f93-127">The value of an attribute node becomes its child nodes.</span></span> <span data-ttu-id="d1f93-128">有只有两种类型的有效子节点： **XmlText**节点，和**XmlEntityReference**节点。</span><span class="sxs-lookup"><span data-stu-id="d1f93-128">There are only two types of valid child nodes: **XmlText** nodes, and **XmlEntityReference** nodes.</span></span> <span data-ttu-id="d1f93-129">这些是子节点，也就是说，该方法**FirstChild**和**LastChild**处理它们作为子节点。</span><span class="sxs-lookup"><span data-stu-id="d1f93-129">These are child nodes in the sense that methods such as **FirstChild** and **LastChild** process them as child nodes.</span></span> <span data-ttu-id="d1f93-130">当试图移除属性或属性子节点时，属性这种具有子节点的特性很重要。</span><span class="sxs-lookup"><span data-stu-id="d1f93-130">This distinction of an attribute having child nodes is important when trying to remove attributes or attribute child nodes.</span></span> <span data-ttu-id="d1f93-131">有关详细信息，请参阅[移除 DOM 中元素节点的属性](../../../../docs/standard/data/xml/removing-attributes-from-an-element-node-in-the-dom.md)。</span><span class="sxs-lookup"><span data-stu-id="d1f93-131">For more information, see [Removing Attributes from an Element Node in the DOM](../../../../docs/standard/data/xml/removing-attributes-from-an-element-node-in-the-dom.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1f93-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d1f93-132">See Also</span></span>  
 [<span data-ttu-id="d1f93-133">XML 文档对象模型 (DOM)</span><span class="sxs-lookup"><span data-stu-id="d1f93-133">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
