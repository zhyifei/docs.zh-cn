---
title: 为 DOM 中的元素创建新属性
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: dd6dc920-b011-418a-b3db-f1580a7d9251
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 870e800220031338557792fa612d4a3101e79f90
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/24/2018
ms.locfileid: "47027115"
---
# <a name="creating-new-attributes-for-elements-in-the-dom"></a><span data-ttu-id="88aaf-102">为 DOM 中的元素创建新属性</span><span class="sxs-lookup"><span data-stu-id="88aaf-102">Creating New Attributes for Elements in the DOM</span></span>
<span data-ttu-id="88aaf-103">新建属性不同于创建其他节点类型，因为属性不是节点，而是元素节点的属性，包含在与元素关联的 XmlAttributeCollection 中。</span><span class="sxs-lookup"><span data-stu-id="88aaf-103">Creating new attributes is different than creating other node types, because attributes are not nodes, but are properties of an element node and are contained in an **XmlAttributeCollection** associated with the element.</span></span> <span data-ttu-id="88aaf-104">有多种方法可创建属性并将其附加到元素：</span><span class="sxs-lookup"><span data-stu-id="88aaf-104">There are multiple ways to create an attribute and attach it to an element:</span></span>  
  
-   <span data-ttu-id="88aaf-105">获取元素节点，并使用 SetAttribute 将属性添加到相应元素的属性集合。</span><span class="sxs-lookup"><span data-stu-id="88aaf-105">Get the element node and use **SetAttribute** to add an attribute to the attribute collection of that element.</span></span>  
  
-   <span data-ttu-id="88aaf-106">使用 CreateAttribute 方法创建 XmlAttribute 节点，获取元素节点，再使用 SetAttributeNode 将节点添加到相应元素的属性集合。</span><span class="sxs-lookup"><span data-stu-id="88aaf-106">Create an **XmlAttribute** node using the **CreateAttribute** method, get the element node, then use **SetAttributeNode** to add the node to the attribute collection of that element.</span></span>  
  
 <span data-ttu-id="88aaf-107">下面的示例展示了如何使用 SetAttribute 方法将属性添加到元素。</span><span class="sxs-lookup"><span data-stu-id="88aaf-107">The following example shows how to add an attribute to an element using the **SetAttribute** method.</span></span>  
  
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
  
 <span data-ttu-id="88aaf-108">下面的示例展示了使用 CreateAttribute 方法新建的属性。</span><span class="sxs-lookup"><span data-stu-id="88aaf-108">The following example shows a new attribute being created using the **CreateAttribute** method.</span></span> <span data-ttu-id="88aaf-109">然后展示了使用 SetAttributeNode 方法添加到 book 元素的属性集合的属性。</span><span class="sxs-lookup"><span data-stu-id="88aaf-109">It then shows the attribute added to the attribute collection of the **book** element using the **SetAttributeNode** method.</span></span>  
  
 <span data-ttu-id="88aaf-110">已知下列 XML：</span><span class="sxs-lookup"><span data-stu-id="88aaf-110">Given the following XML:</span></span>  
  
```xml  
<book genre='novel' ISBN='1-861001-57-5'>  
<title>Pride And Prejudice</title>  
</book>  
```  
  
 <span data-ttu-id="88aaf-111">创建一个新属性并为其提供值：</span><span class="sxs-lookup"><span data-stu-id="88aaf-111">create a new attribute and give it a value:</span></span>  
  
```vb  
Dim attr As XmlAttribute = doc.CreateAttribute("publisher")  
   attr.Value = "WorldWide Publishing"  
```  
  
```csharp  
XmlAttribute attr = doc.CreateAttribute("publisher");  
attr.Value = "WorldWide Publishing";  
```  
  
 <span data-ttu-id="88aaf-112">将其附加到此元素：</span><span class="sxs-lookup"><span data-stu-id="88aaf-112">and attach it to the element:</span></span>  
  
```vb  
doc.DocumentElement.SetAttributeNode(attr)  
```  
  
```csharp  
doc.DocumentElement.SetAttributeNode(attr);  
```  
  
 <span data-ttu-id="88aaf-113">**输出**</span><span class="sxs-lookup"><span data-stu-id="88aaf-113">**Output**</span></span>  
  
```xml  
<book genre="novel" ISBN="1-861001-57-5" publisher="WorldWide Publishing">  
<title>Pride And Prejudice</title>  
</book>  
```  
  
 <span data-ttu-id="88aaf-114">有关完整代码示例，可以参阅 <xref:System.Xml.XmlDocument.CreateAttribute%2A>。</span><span class="sxs-lookup"><span data-stu-id="88aaf-114">The full code sample can be found at <xref:System.Xml.XmlDocument.CreateAttribute%2A>.</span></span>  
  
 <span data-ttu-id="88aaf-115">也可以创建 XmlAttribute 节点，并使用 InsertBefore 或 InsertAfter 方法，将它添加到集合中的适当位置。</span><span class="sxs-lookup"><span data-stu-id="88aaf-115">You can also create an **XmlAttribute** node and use the **InsertBefore** or **InsertAfter** methods to place it in the appropriate position in the collection.</span></span> <span data-ttu-id="88aaf-116">如果属性集合中已有同名的属性，将会从集合中删除现有 XmlAttribute 节点，并插入新的 XmlAttribute 节点。</span><span class="sxs-lookup"><span data-stu-id="88aaf-116">If an attribute with the same name is already present in the attribute collection, the existing **XmlAttribute** node is removed from the collection and the new **XmlAttribute** node is inserted.</span></span> <span data-ttu-id="88aaf-117">这与 SetAttribute 方法执行的操作一样。</span><span class="sxs-lookup"><span data-stu-id="88aaf-117">This performs the same way as the **SetAttribute** method.</span></span> <span data-ttu-id="88aaf-118">这些方法需要使用现有节点作为参数，以用作执行 InsertBefore 和 InsertAfter 的参考点。</span><span class="sxs-lookup"><span data-stu-id="88aaf-118">These methods take, as a parameter, an existing node as a reference point to do the **InsertBefore** and **InsertAfter**.</span></span> <span data-ttu-id="88aaf-119">如果不提供指示新节点插入位置的参考节点，InsertAfter 方法默认在集合的开头插入新节点。</span><span class="sxs-lookup"><span data-stu-id="88aaf-119">If you do not provide a reference node indicating where to insert the new node, the default for the **InsertAfter** method is to insert the new node at the beginning of the collection.</span></span> <span data-ttu-id="88aaf-120">如果未提供任何参考节点，InsertBefore 默认在集合的末尾插入新节点。</span><span class="sxs-lookup"><span data-stu-id="88aaf-120">The default position for the **InsertBefore**, if no reference node is provided, is at the end of the collection.</span></span>  
  
 <span data-ttu-id="88aaf-121">如果创建了属性的 XmlNamedNodeMap，可以使用 <xref:System.Xml.XmlNamedNodeMap.SetNamedItem%2A> 按名称添加属性。</span><span class="sxs-lookup"><span data-stu-id="88aaf-121">If you created an **XmlNamedNodeMap** of attributes, you can add an attribute by name using the <xref:System.Xml.XmlNamedNodeMap.SetNamedItem%2A>.</span></span> <span data-ttu-id="88aaf-122">有关详细信息，请参阅 [NamedNodeMaps 和 NodeLists 中的节点集合](../../../../docs/standard/data/xml/node-collections-in-namednodemaps-and-nodelists.md)。</span><span class="sxs-lookup"><span data-stu-id="88aaf-122">For more information, see [Node Collections in NamedNodeMaps and NodeLists](../../../../docs/standard/data/xml/node-collections-in-namednodemaps-and-nodelists.md).</span></span>  
  
## <a name="default-attributes"></a><span data-ttu-id="88aaf-123">默认属性</span><span class="sxs-lookup"><span data-stu-id="88aaf-123">Default Attributes</span></span>  
 <span data-ttu-id="88aaf-124">如果创建一个声明为具有默认属性的元素，则 XML 文档对象模型 (DOM) 创建一个带默认值的新默认属性并将其附加到该元素。</span><span class="sxs-lookup"><span data-stu-id="88aaf-124">If you create an element that is declared to have a default attribute, then a new default attribute with its default value is created by the XML Document Object Model (DOM) and attached to the element.</span></span> <span data-ttu-id="88aaf-125">此时还创建默认属性的子节点。</span><span class="sxs-lookup"><span data-stu-id="88aaf-125">The child nodes of the default attribute are also created at this time.</span></span>  
  
## <a name="attribute-child-nodes"></a><span data-ttu-id="88aaf-126">属性子节点</span><span class="sxs-lookup"><span data-stu-id="88aaf-126">Attribute Child Nodes</span></span>  
 <span data-ttu-id="88aaf-127">属性节点的值成为它的子节点。</span><span class="sxs-lookup"><span data-stu-id="88aaf-127">The value of an attribute node becomes its child nodes.</span></span> <span data-ttu-id="88aaf-128">有效子节点只有以下两种类型：XmlText 节点和 XmlEntityReference 节点。</span><span class="sxs-lookup"><span data-stu-id="88aaf-128">There are only two types of valid child nodes: **XmlText** nodes, and **XmlEntityReference** nodes.</span></span> <span data-ttu-id="88aaf-129">这些之所以是子节点是因为，FirstChild 和 LastChild 等方法按子节点处理它们。</span><span class="sxs-lookup"><span data-stu-id="88aaf-129">These are child nodes in the sense that methods such as **FirstChild** and **LastChild** process them as child nodes.</span></span> <span data-ttu-id="88aaf-130">当试图移除属性或属性子节点时，属性这种具有子节点的特性很重要。</span><span class="sxs-lookup"><span data-stu-id="88aaf-130">This distinction of an attribute having child nodes is important when trying to remove attributes or attribute child nodes.</span></span> <span data-ttu-id="88aaf-131">有关详细信息，请参阅[删除 DOM 中元素节点的属性](../../../../docs/standard/data/xml/removing-attributes-from-an-element-node-in-the-dom.md)。</span><span class="sxs-lookup"><span data-stu-id="88aaf-131">For more information, see [Removing Attributes from an Element Node in the DOM](../../../../docs/standard/data/xml/removing-attributes-from-an-element-node-in-the-dom.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88aaf-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="88aaf-132">See also</span></span>

- [<span data-ttu-id="88aaf-133">XML 文档对象模型 (DOM)</span><span class="sxs-lookup"><span data-stu-id="88aaf-133">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
