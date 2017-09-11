---
title: "预先原子化 XName 对象 (LINQ to XML) (Visual Basic 中) |Microsoft 文档"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 06ea104b-f44c-4bb2-9c34-889ae025c80d
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 4871fab18d04ce9d715299fd06138c493e666466
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017


---
# <a name="pre-atomization-of-xname-objects-linq-to-xml-visual-basic"></a><span data-ttu-id="cee6e-102">预先原子化 XName 对象 (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cee6e-102">Pre-Atomization of XName Objects (LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="cee6e-103">提高 LINQ to XML 中的性能的一种方法是预原子化<xref:System.Xml.Linq.XName>对象。</xref:System.Xml.Linq.XName></span><span class="sxs-lookup"><span data-stu-id="cee6e-103">One way to improve performance in LINQ to XML is to pre-atomize <xref:System.Xml.Linq.XName> objects.</span></span> <span data-ttu-id="cee6e-104">预原子化是指将分配到的字符串<xref:System.Xml.Linq.XName>对象之前使用的构造函数创建 XML 树<xref:System.Xml.Linq.XElement>和<xref:System.Xml.Linq.XAttribute>类。</xref:System.Xml.Linq.XAttribute> </xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XName></span><span class="sxs-lookup"><span data-stu-id="cee6e-104">Pre-atomization means that you assign a string to an <xref:System.Xml.Linq.XName> object before you create the XML tree by using the constructors of the <xref:System.Xml.Linq.XElement> and  <xref:System.Xml.Linq.XAttribute> classes.</span></span> <span data-ttu-id="cee6e-105">然后，而不是将字符串传递给构造函数，此过程将使用隐式转换从字符串到<xref:System.Xml.Linq.XName>，传递初始化<xref:System.Xml.Linq.XName>对象。</xref:System.Xml.Linq.XName> </xref:System.Xml.Linq.XName></span><span class="sxs-lookup"><span data-stu-id="cee6e-105">Then, instead of passing a string to the constructor, which would use the implicit conversion from string to <xref:System.Xml.Linq.XName>, you pass the initialized <xref:System.Xml.Linq.XName> object.</span></span>  
  
 <span data-ttu-id="cee6e-106">当创建其中重复出现特定名称的大型 XML 树时，这样可以提高性能。</span><span class="sxs-lookup"><span data-stu-id="cee6e-106">This improves performance when you create a large XML tree in which specific names are repeated.</span></span> <span data-ttu-id="cee6e-107">若要执行此操作，您可以声明并初始化<xref:System.Xml.Linq.XName>对象之前构造 XML 树，然后使用<xref:System.Xml.Linq.XName>对象而不是指定元素和属性名称的字符串。</xref:System.Xml.Linq.XName> </xref:System.Xml.Linq.XName></span><span class="sxs-lookup"><span data-stu-id="cee6e-107">To do this, you declare and initialize <xref:System.Xml.Linq.XName> objects before you construct the XML tree, and then use the <xref:System.Xml.Linq.XName> objects instead of specifying strings for the element and attribute names.</span></span> <span data-ttu-id="cee6e-108">当创建大量具有相同名称的元素（或属性）时，此技术可以显著提高性能。</span><span class="sxs-lookup"><span data-stu-id="cee6e-108">This technique can yield significant performance gains if you are creating a large number of elements (or attributes) with the same name.</span></span>  
  
 <span data-ttu-id="cee6e-109">应针对您的方案测试预原子化以确定是否应使用它。</span><span class="sxs-lookup"><span data-stu-id="cee6e-109">You should test pre-atomization with your scenario to decide if you should use it.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cee6e-110">示例</span><span class="sxs-lookup"><span data-stu-id="cee6e-110">Example</span></span>  
 <span data-ttu-id="cee6e-111">下面的示例演示这一操作。</span><span class="sxs-lookup"><span data-stu-id="cee6e-111">The following example demonstrates this.</span></span>  
  
```vb  
Dim Root__1 As XName = "Root"  
Dim Data As XName = "Data"  
Dim ID As XName = "ID"  
  
Dim root__2 As New XElement(Root__1, New XElement(Data, New XAttribute(ID, "1"), "4,100,000"), New XElement(Data, New XAttribute(ID, "2"), "3,700,000"), New XElement(Data, New XAttribute(ID, "3"), "1,150,000"))  
  
Console.WriteLine(root__2)  
```  
  
 <span data-ttu-id="cee6e-112">该示例产生下面的输出：</span><span class="sxs-lookup"><span data-stu-id="cee6e-112">This example produces the following output:</span></span>  
  
```xml  
<Root>  
  <Data ID="1">4,100,000</Data>  
  <Data ID="2">3,700,000</Data>  
  <Data ID="3">1,150,000</Data>  
</Root>  
```  
  
 <span data-ttu-id="cee6e-113">下面的示例演示针对命名空间中的 XML 文档的相同技术：</span><span class="sxs-lookup"><span data-stu-id="cee6e-113">The following example shows the same technique where the XML document is in a namespace:</span></span>  
  
```vb  
Dim aw As XNamespace = "http://www.adventure-works.com"  
Dim Root__1 As XName = aw + "Root"  
Dim Data As XName = aw + "Data"  
Dim ID As XName = "ID"  
  
Dim root__2 As New XElement(Root__1, New XAttribute(XNamespace.Xmlns + "aw", aw), New XElement(Data, New XAttribute(ID, "1"), "4,100,000"), New XElement(Data, New XAttribute(ID, "2"), "3,700,000"), New XElement(Data, New XAttribute(ID, "3"), "1,150,000"))  
  
Console.WriteLine(root__2)  
```  
  
 <span data-ttu-id="cee6e-114">该示例产生下面的输出：</span><span class="sxs-lookup"><span data-stu-id="cee6e-114">This example produces the following output:</span></span>  
  
```xml  
<aw:Root xmlns:aw="http://www.adventure-works.com">  
  <aw:Data ID="1">4,100,000</aw:Data>  
  <aw:Data ID="2">3,700,000</aw:Data>  
  <aw:Data ID="3">1,150,000</aw:Data>  
</aw:Root>  
```  
  
 <span data-ttu-id="cee6e-115">下面的示例更类似于实际中可能遇到的情况。</span><span class="sxs-lookup"><span data-stu-id="cee6e-115">The following example is more similar to what you will likely encounter in the real world.</span></span> <span data-ttu-id="cee6e-116">在此示例中，元素的内容由查询提供：</span><span class="sxs-lookup"><span data-stu-id="cee6e-116">In this example, the content of the element is supplied by a query:</span></span>  
  
```vb  
Dim Root__1 As XName = "Root"  
Dim Data As XName = "Data"  
Dim ID As XName = "ID"  
  
Dim t1 As DateTime = DateTime.Now  
Dim root__2 As New XElement(Root__1, From i In System.Linq.Enumerable.Range(1, 100000)New XElement(Data, New XAttribute(ID, i), i * 5))  
Dim t2 As DateTime = DateTime.Now  
  
Console.WriteLine("Time to construct:{0}", t2 - t1)  
```  
  
 <span data-ttu-id="cee6e-117">上一示例的执行性能优于下面的示例（其中未对名称进行预原子化）：</span><span class="sxs-lookup"><span data-stu-id="cee6e-117">The previous example performs better than the following example, in which names are not pre-atomized:</span></span>  
  
```vb  
Dim t1 As DateTime = DateTime.Now  
Dim root As New XElement("Root", From i In System.Linq.Enumerable.Range(1, 100000)New XElement("Data", New XAttribute("ID", i), i * 5))  
Dim t2 As DateTime = DateTime.Now  
  
Console.WriteLine("Time to construct:{0}", t2 - t1)  
```  
  
## <a name="see-also"></a><span data-ttu-id="cee6e-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cee6e-118">See Also</span></span>  
 <span data-ttu-id="cee6e-119">[性能 (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/performance-linq-to-xml.md) </span><span class="sxs-lookup"><span data-stu-id="cee6e-119">[Performance (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/performance-linq-to-xml.md) </span></span>  
<span data-ttu-id="cee6e-120"> [原子化 XName 和 XNamespace 对象 (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/atomized-xname-and-xnamespace-objects-linq-to-xml.md)</span><span class="sxs-lookup"><span data-stu-id="cee6e-120"> [Atomized XName and XNamespace Objects (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/atomized-xname-and-xnamespace-objects-linq-to-xml.md)</span></span>
