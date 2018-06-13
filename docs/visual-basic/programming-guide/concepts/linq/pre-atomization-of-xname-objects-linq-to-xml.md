---
title: 预原子化的 XName 对象 (LINQ to XML) (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 06ea104b-f44c-4bb2-9c34-889ae025c80d
ms.openlocfilehash: 141aa5e19e75e4a09b2d7aa04d83e8a24d2a27f9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33645715"
---
# <a name="pre-atomization-of-xname-objects-linq-to-xml-visual-basic"></a><span data-ttu-id="520c7-102">预原子化的 XName 对象 (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="520c7-102">Pre-Atomization of XName Objects (LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="520c7-103">提高 LINQ to XML 中的性能的一种方法是预原子化 <xref:System.Xml.Linq.XName> 对象。</span><span class="sxs-lookup"><span data-stu-id="520c7-103">One way to improve performance in LINQ to XML is to pre-atomize <xref:System.Xml.Linq.XName> objects.</span></span> <span data-ttu-id="520c7-104">预原子化是指在通过使用 <xref:System.Xml.Linq.XName> 和 <xref:System.Xml.Linq.XElement> 类的构造函数创建 XML 树之前，先将字符串分配给 <xref:System.Xml.Linq.XAttribute> 对象。</span><span class="sxs-lookup"><span data-stu-id="520c7-104">Pre-atomization means that you assign a string to an <xref:System.Xml.Linq.XName> object before you create the XML tree by using the constructors of the <xref:System.Xml.Linq.XElement> and  <xref:System.Xml.Linq.XAttribute> classes.</span></span> <span data-ttu-id="520c7-105">然后传递初始化的 <xref:System.Xml.Linq.XName> 对象，而不是将字符串传递给构造函数（此过程将使用从字符串到 <xref:System.Xml.Linq.XName> 的隐式转换）。</span><span class="sxs-lookup"><span data-stu-id="520c7-105">Then, instead of passing a string to the constructor, which would use the implicit conversion from string to <xref:System.Xml.Linq.XName>, you pass the initialized <xref:System.Xml.Linq.XName> object.</span></span>  
  
 <span data-ttu-id="520c7-106">当创建其中重复出现特定名称的大型 XML 树时，这样可以提高性能。</span><span class="sxs-lookup"><span data-stu-id="520c7-106">This improves performance when you create a large XML tree in which specific names are repeated.</span></span> <span data-ttu-id="520c7-107">为此，请在构造 XML 树之前声明和初始化 <xref:System.Xml.Linq.XName> 对象，然后使用 <xref:System.Xml.Linq.XName> 对象，而不是指定元素和属性名称的字符串。</span><span class="sxs-lookup"><span data-stu-id="520c7-107">To do this, you declare and initialize <xref:System.Xml.Linq.XName> objects before you construct the XML tree, and then use the <xref:System.Xml.Linq.XName> objects instead of specifying strings for the element and attribute names.</span></span> <span data-ttu-id="520c7-108">当创建大量具有相同名称的元素（或属性）时，此技术可以显著提高性能。</span><span class="sxs-lookup"><span data-stu-id="520c7-108">This technique can yield significant performance gains if you are creating a large number of elements (or attributes) with the same name.</span></span>  
  
 <span data-ttu-id="520c7-109">应针对您的方案测试预原子化以确定是否应使用它。</span><span class="sxs-lookup"><span data-stu-id="520c7-109">You should test pre-atomization with your scenario to decide if you should use it.</span></span>  
  
## <a name="example"></a><span data-ttu-id="520c7-110">示例</span><span class="sxs-lookup"><span data-stu-id="520c7-110">Example</span></span>  
 <span data-ttu-id="520c7-111">下面的示例演示这一操作。</span><span class="sxs-lookup"><span data-stu-id="520c7-111">The following example demonstrates this.</span></span>  
  
```vb  
Dim Root__1 As XName = "Root"  
Dim Data As XName = "Data"  
Dim ID As XName = "ID"  
  
Dim root__2 As New XElement(Root__1, New XElement(Data, New XAttribute(ID, "1"), "4,100,000"), New XElement(Data, New XAttribute(ID, "2"), "3,700,000"), New XElement(Data, New XAttribute(ID, "3"), "1,150,000"))  
  
Console.WriteLine(root__2)  
```  
  
 <span data-ttu-id="520c7-112">该示例产生下面的输出：</span><span class="sxs-lookup"><span data-stu-id="520c7-112">This example produces the following output:</span></span>  
  
```xml  
<Root>  
  <Data ID="1">4,100,000</Data>  
  <Data ID="2">3,700,000</Data>  
  <Data ID="3">1,150,000</Data>  
</Root>  
```  
  
 <span data-ttu-id="520c7-113">下面的示例演示针对命名空间中的 XML 文档的相同技术：</span><span class="sxs-lookup"><span data-stu-id="520c7-113">The following example shows the same technique where the XML document is in a namespace:</span></span>  
  
```vb  
Dim aw As XNamespace = "http://www.adventure-works.com"  
Dim Root__1 As XName = aw + "Root"  
Dim Data As XName = aw + "Data"  
Dim ID As XName = "ID"  
  
Dim root__2 As New XElement(Root__1, New XAttribute(XNamespace.Xmlns + "aw", aw), New XElement(Data, New XAttribute(ID, "1"), "4,100,000"), New XElement(Data, New XAttribute(ID, "2"), "3,700,000"), New XElement(Data, New XAttribute(ID, "3"), "1,150,000"))  
  
Console.WriteLine(root__2)  
```  
  
 <span data-ttu-id="520c7-114">该示例产生下面的输出：</span><span class="sxs-lookup"><span data-stu-id="520c7-114">This example produces the following output:</span></span>  
  
```xml  
<aw:Root xmlns:aw="http://www.adventure-works.com">  
  <aw:Data ID="1">4,100,000</aw:Data>  
  <aw:Data ID="2">3,700,000</aw:Data>  
  <aw:Data ID="3">1,150,000</aw:Data>  
</aw:Root>  
```  
  
 <span data-ttu-id="520c7-115">下面的示例更类似于实际中可能遇到的情况。</span><span class="sxs-lookup"><span data-stu-id="520c7-115">The following example is more similar to what you will likely encounter in the real world.</span></span> <span data-ttu-id="520c7-116">在此示例中，元素的内容由查询提供：</span><span class="sxs-lookup"><span data-stu-id="520c7-116">In this example, the content of the element is supplied by a query:</span></span>  
  
```vb  
Dim Root__1 As XName = "Root"  
Dim Data As XName = "Data"  
Dim ID As XName = "ID"  
  
Dim t1 As DateTime = DateTime.Now  
Dim root__2 As New XElement(Root__1, From i In System.Linq.Enumerable.Range(1, 100000)New XElement(Data, New XAttribute(ID, i), i * 5))  
Dim t2 As DateTime = DateTime.Now  
  
Console.WriteLine("Time to construct:{0}", t2 - t1)  
```  
  
 <span data-ttu-id="520c7-117">上一示例的执行性能优于下面的示例（其中未对名称进行预原子化）：</span><span class="sxs-lookup"><span data-stu-id="520c7-117">The previous example performs better than the following example, in which names are not pre-atomized:</span></span>  
  
```vb  
Dim t1 As DateTime = DateTime.Now  
Dim root As New XElement("Root", From i In System.Linq.Enumerable.Range(1, 100000)New XElement("Data", New XAttribute("ID", i), i * 5))  
Dim t2 As DateTime = DateTime.Now  
  
Console.WriteLine("Time to construct:{0}", t2 - t1)  
```  
  
## <a name="see-also"></a><span data-ttu-id="520c7-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="520c7-118">See Also</span></span>  
 [<span data-ttu-id="520c7-119">性能 (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="520c7-119">Performance (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/performance-linq-to-xml.md)  
 [<span data-ttu-id="520c7-120">原子化的 XName 和 XNamespace 对象 (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="520c7-120">Atomized XName and XNamespace Objects (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/atomized-xname-and-xnamespace-objects-linq-to-xml.md)
