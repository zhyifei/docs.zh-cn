---
title: 如何：更改整个 XML 树的命名空间 (C#)
ms.date: 07/20/2015
ms.assetid: 1584ff3b-c77d-4241-ab62-80adfb7bfc1b
ms.openlocfilehash: d046e01798c193ee0ea459f522a5c29187c697d7
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2019
ms.locfileid: "66487462"
---
# <a name="how-to-change-the-namespace-for-an-entire-xml-tree-c"></a><span data-ttu-id="25fbc-102">如何：更改整个 XML 树的命名空间 (C#)</span><span class="sxs-lookup"><span data-stu-id="25fbc-102">How to: Change the Namespace for an Entire XML Tree (C#)</span></span>
<span data-ttu-id="25fbc-103">有时需要以编程方式更改元素或属性的命名空间。</span><span class="sxs-lookup"><span data-stu-id="25fbc-103">You sometimes have to programmatically change the namespace for an element or an attribute.</span></span> <span data-ttu-id="25fbc-104">LINQ to XML 可简化此任务。</span><span class="sxs-lookup"><span data-stu-id="25fbc-104">LINQ to XML makes this easy.</span></span> <span data-ttu-id="25fbc-105">可以设置 <xref:System.Xml.Linq.XElement.Name%2A?displayProperty=nameWithType> 属性。</span><span class="sxs-lookup"><span data-stu-id="25fbc-105">The <xref:System.Xml.Linq.XElement.Name%2A?displayProperty=nameWithType> property can be set.</span></span> <span data-ttu-id="25fbc-106">不能设置 <xref:System.Xml.Linq.XAttribute.Name%2A?displayProperty=nameWithType> 属性 (Property)，但是很容易将属性 (Attribute) 复制到 <xref:System.Collections.Generic.List%601?displayProperty=nameWithType> 中，移除现有属性 (Attribute)，然后添加位于新命名空间中的新属性 (Attribute)。</span><span class="sxs-lookup"><span data-stu-id="25fbc-106">The <xref:System.Xml.Linq.XAttribute.Name%2A?displayProperty=nameWithType> property cannot be set, but you can easily copy the attributes into a <xref:System.Collections.Generic.List%601?displayProperty=nameWithType>, remove the existing attributes, and then add new attributes that are in the new desired namespace.</span></span>  
  
 <span data-ttu-id="25fbc-107">有关详细信息，请参阅[使用 XML 命名空间 (C#)](../../../../csharp/programming-guide/concepts/linq/namespaces-overview-linq-to-xml.md)。</span><span class="sxs-lookup"><span data-stu-id="25fbc-107">For more information, see [Working with XML Namespaces (C#)](../../../../csharp/programming-guide/concepts/linq/namespaces-overview-linq-to-xml.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="25fbc-108">示例</span><span class="sxs-lookup"><span data-stu-id="25fbc-108">Example</span></span>  
 <span data-ttu-id="25fbc-109">下面的代码创建两个不在命名空间中的 XML 树。</span><span class="sxs-lookup"><span data-stu-id="25fbc-109">The following code creates two XML trees in no namespace.</span></span> <span data-ttu-id="25fbc-110">然后更改每个树的命名空间，再将它们合并到一个树中。</span><span class="sxs-lookup"><span data-stu-id="25fbc-110">It then changes the namespace of each of the trees, and combines them into a single tree.</span></span>  
  
```csharp  
XElement tree1 = new XElement("Data",  
    new XElement("Child", "content",  
        new XAttribute("MyAttr", "content")  
    )  
);  
XElement tree2 = new XElement("Data",  
    new XElement("Child", "content",  
        new XAttribute("MyAttr", "content")  
    )  
);  
XNamespace aw = "http://www.adventure-works.com";  
XNamespace ad = "http://www.adatum.com";  
// change the namespace of every element and attribute in the first tree  
foreach (XElement el in tree1.DescendantsAndSelf())  
{  
    el.Name = aw.GetName(el.Name.LocalName);  
    List<XAttribute> atList = el.Attributes().ToList();  
    el.Attributes().Remove();  
    foreach (XAttribute at in atList)  
        el.Add(new XAttribute(aw.GetName(at.Name.LocalName), at.Value));  
}  
// change the namespace of every element and attribute in the second tree  
foreach (XElement el in tree2.DescendantsAndSelf())  
{  
    el.Name = ad.GetName(el.Name.LocalName);  
    List<XAttribute> atList = el.Attributes().ToList();  
    el.Attributes().Remove();  
    foreach (XAttribute at in atList)  
        el.Add(new XAttribute(ad.GetName(at.Name.LocalName), at.Value));  
}  
// add attribute namespaces so that the tree will be serialized with  
// the aw and ad namespace prefixes  
tree1.Add(  
    new XAttribute(XNamespace.Xmlns + "aw", "http://www.adventure-works.com")  
);  
tree2.Add(  
    new XAttribute(XNamespace.Xmlns + "ad", "http://www.adatum.com")  
);  
// create a new composite tree  
XElement root = new XElement("Root",  
    tree1,  
    tree2  
);  
Console.WriteLine(root);  
```  
  
 <span data-ttu-id="25fbc-111">该示例产生下面的输出：</span><span class="sxs-lookup"><span data-stu-id="25fbc-111">This example produces the following output:</span></span>  
  
```xml  
<Root>  
  <aw:Data xmlns:aw="http://www.adventure-works.com">  
    <aw:Child aw:MyAttr="content">content</aw:Child>  
  </aw:Data>  
  <ad:Data xmlns:ad="http://www.adatum.com">  
    <ad:Child ad:MyAttr="content">content</ad:Child>  
  </ad:Data>  
</Root>  
```  
