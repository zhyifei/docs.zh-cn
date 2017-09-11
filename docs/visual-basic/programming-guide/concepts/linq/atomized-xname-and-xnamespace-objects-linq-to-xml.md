---
title: "原子化 XName 和 XNamespace 对象 (LINQ to XML) (Visual Basic 中) |Microsoft 文档"
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
ms.assetid: 21ee7585-7df9-40b4-8c76-a12bb5f29bb3
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
ms.translationtype: Machine Translation
ms.sourcegitcommit: a32f50ce8a92fa22d9627a1510a4b3ec1087364e
ms.openlocfilehash: 1303d0be3715bb6462ef28b1b2286b999661d240
ms.contentlocale: zh-cn
ms.lasthandoff: 06/01/2017


---
# <a name="atomized-xname-and-xnamespace-objects-linq-to-xml-visual-basic"></a><span data-ttu-id="f73f6-102">原子化 XName 和 XNamespace 对象 (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f73f6-102">Atomized XName and XNamespace Objects (LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="f73f6-103"><xref:System.Xml.Linq.XName>和<xref:System.Xml.Linq.XNamespace>对象*原子化*; 也就是说，如果它们包含相同的限定的名，它们是指同一对象。</xref:System.Xml.Linq.XNamespace></xref:System.Xml.Linq.XName></span><span class="sxs-lookup"><span data-stu-id="f73f6-103"><xref:System.Xml.Linq.XName> and <xref:System.Xml.Linq.XNamespace> objects are *atomized*; that is, if they contain the same qualified name, they refer to the same object.</span></span> <span data-ttu-id="f73f6-104">这将提高查询性能：当比较两个原子化名称是否相等时，基础中间语言只需确定这两个引用是否指向同一个对象。</span><span class="sxs-lookup"><span data-stu-id="f73f6-104">This yields performance benefits for queries: When you compare two atomized names for equality, the underlying intermediate language only has to determine whether the two references point to the same object.</span></span> <span data-ttu-id="f73f6-105">基础代码不必进行很耗费时间的字符串比较。</span><span class="sxs-lookup"><span data-stu-id="f73f6-105">The underlying code does not have to do string comparisons, which would be time consuming.</span></span>  
  
## <a name="atomization-semantics"></a><span data-ttu-id="f73f6-106">原子化语义</span><span class="sxs-lookup"><span data-stu-id="f73f6-106">Atomization Semantics</span></span>  
 <span data-ttu-id="f73f6-107">原子化是指如果两个<xref:System.Xml.Linq.XName>对象具有相同的本地名称和它们处于相同的命名空间，则它们共享同一个实例。</xref:System.Xml.Linq.XName></span><span class="sxs-lookup"><span data-stu-id="f73f6-107">Atomization means that if two <xref:System.Xml.Linq.XName> objects have the same local name, and they are in the same namespace, they share the same instance.</span></span> <span data-ttu-id="f73f6-108">同样，如果两个<xref:System.Xml.Linq.XNamespace>对象具有相同的命名空间 URI，则它们共享同一个实例。</xref:System.Xml.Linq.XNamespace></span><span class="sxs-lookup"><span data-stu-id="f73f6-108">In the same way, if two <xref:System.Xml.Linq.XNamespace> objects have the same namespace URI, they share the same instance.</span></span>  
  
 <span data-ttu-id="f73f6-109">对于启用原子化对象的类，该类的构造函数必须是私有的，而不是公共的。</span><span class="sxs-lookup"><span data-stu-id="f73f6-109">For a class to enable atomized objects, the constructor for the class must be private, not public.</span></span> <span data-ttu-id="f73f6-110">这是因为如果构造函数是公共的，则您可以创建非原子化对象。</span><span class="sxs-lookup"><span data-stu-id="f73f6-110">This is because if the constructor were public, you could create a non-atomized object.</span></span> <span data-ttu-id="f73f6-111"><xref:System.Xml.Linq.XName><xref:System.Xml.Linq.XNamespace>类实现一个隐式转换运算符将字符串转换<xref:System.Xml.Linq.XName>或<xref:System.Xml.Linq.XNamespace>.</xref:System.Xml.Linq.XNamespace></xref:System.Xml.Linq.XName></xref:System.Xml.Linq.XNamespace>和</xref:System.Xml.Linq.XName></span><span class="sxs-lookup"><span data-stu-id="f73f6-111">The <xref:System.Xml.Linq.XName> and <xref:System.Xml.Linq.XNamespace> classes implement an implicit conversion operator to convert a string into an <xref:System.Xml.Linq.XName> or <xref:System.Xml.Linq.XNamespace>.</span></span> <span data-ttu-id="f73f6-112">这是获取这些对象的实例的方式。</span><span class="sxs-lookup"><span data-stu-id="f73f6-112">This is how you get an instance of these objects.</span></span> <span data-ttu-id="f73f6-113">不能通过使用构造函数来获得实例，因为构造函数是不可访问的。</span><span class="sxs-lookup"><span data-stu-id="f73f6-113">You cannot get an instance by using a constructor, because the constructor is inaccessible.</span></span>  
  
 <span data-ttu-id="f73f6-114"><xref:System.Xml.Linq.XName>和<xref:System.Xml.Linq.XNamespace>还实现相等和不相等运算符，以确定两个比较对象是否正在对同一实例的引用。</xref:System.Xml.Linq.XNamespace></xref:System.Xml.Linq.XName></span><span class="sxs-lookup"><span data-stu-id="f73f6-114"><xref:System.Xml.Linq.XName> and <xref:System.Xml.Linq.XNamespace> also implement the equality and inequality operators, to determine whether the two objects being compared are references to the same instance.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f73f6-115">示例</span><span class="sxs-lookup"><span data-stu-id="f73f6-115">Example</span></span>  
 <span data-ttu-id="f73f6-116">下面的代码创建一些<xref:System.Xml.Linq.XElement>对象，并演示相同的名称共享同一个实例。</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="f73f6-116">The following code creates some <xref:System.Xml.Linq.XElement> objects and demonstrates that identical names share the same instance.</span></span>  
  
```vb  
Dim r1 As New XElement("Root", "data1")  
Dim r2 As XElement = XElement.Parse("<Root>data2</Root>")  
  
If DirectCast(r1.Name, Object) = DirectCast(r2.Name, Object) Then  
    Console.WriteLine("r1 and r2 have names that refer to the same instance.")  
Else  
    Console.WriteLine("Different")  
End If  
  
Dim n As XName = "Root"  
  
If DirectCast(n, Object) = DirectCast(r1.Name, Object) Then  
    Console.WriteLine("The name of r1 and the name in 'n' refer to the same instance.")  
Else  
    Console.WriteLine("Different")  
End If  
```  
  
 <span data-ttu-id="f73f6-117">该示例产生下面的输出：</span><span class="sxs-lookup"><span data-stu-id="f73f6-117">This example produces the following output:</span></span>  
  
```  
r1 and r2 have names that refer to the same instance.  
The name of r1 and the name in 'n' refer to the same instance.  
```  
  
 <span data-ttu-id="f73f6-118">使用采用的轴方法的一种时如前面所述，原子化对象的好处是︰<xref:System.Xml.Linq.XName>作为参数，该轴方法只须确定这两个名称引用同一个实例，来选择所需的元素。</xref:System.Xml.Linq.XName></span><span class="sxs-lookup"><span data-stu-id="f73f6-118">As mentioned earlier, the benefit of atomized objects is that when you use one of the axis methods that take an <xref:System.Xml.Linq.XName> as a parameter, the axis method only has to determine that two names reference the same instance to select the desired elements.</span></span>  
  
 <span data-ttu-id="f73f6-119">下面的示例传入<xref:System.Xml.Linq.XName>到<xref:System.Xml.Linq.XContainer.Descendants%2A>方法调用中，这样就会由于使用原子化模式而具有更好的性能。</xref:System.Xml.Linq.XContainer.Descendants%2A> </xref:System.Xml.Linq.XName></span><span class="sxs-lookup"><span data-stu-id="f73f6-119">The following example passes an <xref:System.Xml.Linq.XName> to the <xref:System.Xml.Linq.XContainer.Descendants%2A> method call, which then has better performance because of the atomization pattern.</span></span>  
  
```vb  
Dim root As New XElement("Root", New XElement("C1", 1), New XElement("Z1", New XElement("C1", 2), New XElement("C1", 1)))  
  
Dim query = From e In root.Descendants("C1") Where CInt(e) = 1e  
  
For Each z As var In query  
    Console.WriteLine(z)  
Next  
```  
  
 <span data-ttu-id="f73f6-120">该示例产生下面的输出：</span><span class="sxs-lookup"><span data-stu-id="f73f6-120">This example produces the following output:</span></span>  
  
```xml  
<C1>1</C1>  
<C1>1</C1>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f73f6-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f73f6-121">See Also</span></span>  
 [<span data-ttu-id="f73f6-122">性能 (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f73f6-122">Performance (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/performance-linq-to-xml.md)

