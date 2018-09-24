---
title: 如何：调试空查询结果集 (C#)
ms.date: 07/20/2015
ms.assetid: b569f0dc-425e-45a6-acbf-770fb761c981
ms.openlocfilehash: 4760b1e5274634954bd5fe4b3880fd4415af2510
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/24/2018
ms.locfileid: "47026982"
---
# <a name="how-to-debug-empty-query-results-sets-c"></a><span data-ttu-id="7549b-102">如何：调试空查询结果集 (C#)</span><span class="sxs-lookup"><span data-stu-id="7549b-102">How to: Debug Empty Query Results Sets (C#)</span></span>
<span data-ttu-id="7549b-103">查询 XML 树时遇到的一个最常见问题是，如果 XML 树具有默认命名空间，开发人员在编写查询时，有时会将 XML 视为不在命名空间内。</span><span class="sxs-lookup"><span data-stu-id="7549b-103">One of the most common problems when querying XML trees is that if the XML tree has a default namespace, the developer sometimes writes the query as though the XML were not in a namespace.</span></span>  
  
 <span data-ttu-id="7549b-104">本主题的第一个示例集演示一种加载并按不正确方式查询默认命名空间中的 XML 的典型方式。</span><span class="sxs-lookup"><span data-stu-id="7549b-104">The first set of examples in this topic shows a typical way that XML in a default namespace is loaded, and is queried improperly.</span></span>  
  
 <span data-ttu-id="7549b-105">第二个示例集演示必需的更正，以便可以查询命名空间中的 XML。</span><span class="sxs-lookup"><span data-stu-id="7549b-105">The second set of examples show the necessary corrections so that you can query XML in a namespace.</span></span>  
  
 <span data-ttu-id="7549b-106">有关详细信息，请参阅[使用 XML 命名空间 (C#)](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md)。</span><span class="sxs-lookup"><span data-stu-id="7549b-106">For more information, see [Working with XML Namespaces (C#)](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="7549b-107">示例</span><span class="sxs-lookup"><span data-stu-id="7549b-107">Example</span></span>  
 <span data-ttu-id="7549b-108">此示例演示如何在命名空间中创建 XML 和一个返回空结果集的查询。</span><span class="sxs-lookup"><span data-stu-id="7549b-108">This example shows creation of XML in a namespace, and a query that returns an empty result set.</span></span>  
  
```csharp  
XElement root = XElement.Parse(  
@"<Root xmlns='http://www.adventure-works.com'>  
    <Child>1</Child>  
    <Child>2</Child>  
    <Child>3</Child>  
    <AnotherChild>4</AnotherChild>  
    <AnotherChild>5</AnotherChild>  
    <AnotherChild>6</AnotherChild>  
</Root>");  
IEnumerable<XElement> c1 =  
    from el in root.Elements("Child")  
    select el;  
Console.WriteLine("Result set follows:");  
foreach (XElement el in c1)  
    Console.WriteLine((int)el);  
Console.WriteLine("End of result set");  
```  
  
 <span data-ttu-id="7549b-109">此示例产生下面的结果：</span><span class="sxs-lookup"><span data-stu-id="7549b-109">This example produces the following result:</span></span>  
  
```  
Result set follows:  
End of result set  
```  
  
## <a name="example"></a><span data-ttu-id="7549b-110">示例</span><span class="sxs-lookup"><span data-stu-id="7549b-110">Example</span></span>  
 <span data-ttu-id="7549b-111">本示例演示如何在命名空间中创建 XML 和一个正确编码的查询。</span><span class="sxs-lookup"><span data-stu-id="7549b-111">This example shows creation of XML in a namespace, and a query that is coded properly.</span></span>  
  
 <span data-ttu-id="7549b-112">解决方案为声明和初始化一个 <xref:System.Xml.Linq.XNamespace> 对象，并在指定 <xref:System.Xml.Linq.XName> 对象时使用该对象。</span><span class="sxs-lookup"><span data-stu-id="7549b-112">The solution is to declare and initialize an <xref:System.Xml.Linq.XNamespace> object, and to use it when specifying <xref:System.Xml.Linq.XName> objects.</span></span> <span data-ttu-id="7549b-113">在这种情况下，<xref:System.Xml.Linq.XElement.Elements%2A> 方法的参数是一个 <xref:System.Xml.Linq.XName> 对象。</span><span class="sxs-lookup"><span data-stu-id="7549b-113">In this case, the argument to the <xref:System.Xml.Linq.XElement.Elements%2A> method is an <xref:System.Xml.Linq.XName> object.</span></span>  
  
```csharp  
XElement root = XElement.Parse(  
@"<Root xmlns='http://www.adventure-works.com'>  
    <Child>1</Child>  
    <Child>2</Child>  
    <Child>3</Child>  
    <AnotherChild>4</AnotherChild>  
    <AnotherChild>5</AnotherChild>  
    <AnotherChild>6</AnotherChild>  
</Root>");  
XNamespace aw = "http://www.adventure-works.com";  
IEnumerable<XElement> c1 =  
    from el in root.Elements(aw + "Child")  
    select el;  
Console.WriteLine("Result set follows:");  
foreach (XElement el in c1)  
    Console.WriteLine((int)el);  
Console.WriteLine("End of result set");  
```  
  
 <span data-ttu-id="7549b-114">此示例产生下面的结果：</span><span class="sxs-lookup"><span data-stu-id="7549b-114">This example produces the following result:</span></span>  
  
```  
Result set follows:  
1  
2  
3  
End of result set  
```  
  
## <a name="see-also"></a><span data-ttu-id="7549b-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="7549b-115">See Also</span></span>

- [<span data-ttu-id="7549b-116">基本查询 (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="7549b-116">Basic Queries (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)
