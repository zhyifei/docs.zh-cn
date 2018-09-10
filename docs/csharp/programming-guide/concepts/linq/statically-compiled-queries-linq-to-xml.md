---
title: 静态编译的查询 (LINQ to XML) (C#)
ms.date: 07/20/2015
ms.assetid: 3bf558fe-0705-479d-86d4-00188f5fcf9c
ms.openlocfilehash: 0febb0c1ccae544e9767b472f2be8bd4eef7f4c2
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "44087233"
---
# <a name="statically-compiled-queries-linq-to-xml-c"></a><span data-ttu-id="dee55-102">静态编译的查询 (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="dee55-102">Statically Compiled Queries (LINQ to XML) (C#)</span></span>
<span data-ttu-id="dee55-103">LINQ to XML 的一个最重要的性能优势（与 <xref:System.Xml.XmlDocument> 相比）为：LINQ to XML 中的查询是静态编译的，而 XPath 查询则必须在运行时进行解释。</span><span class="sxs-lookup"><span data-stu-id="dee55-103">One of the most important performance benefits LINQ to XML, as opposed to <xref:System.Xml.XmlDocument>, is that queries in LINQ to XML are statically compiled, whereas XPath queries must be interpreted at run time.</span></span> <span data-ttu-id="dee55-104">此功能是 LINQ to XML 的内置功能，因此您不必执行额外的步骤即可利用此功能，但在这两项技术之间做出选择时了解它们的区别将很有帮助。</span><span class="sxs-lookup"><span data-stu-id="dee55-104">This feature is built in to LINQ to XML, so you do not have to perform extra steps to take advantage of it, but it is helpful to understand the distinction when choosing between the two technologies.</span></span> <span data-ttu-id="dee55-105">本主题解释了其中的区别。</span><span class="sxs-lookup"><span data-stu-id="dee55-105">This topic explains the difference.</span></span>  
  
## <a name="statically-compiled-queries-vs-xpath"></a><span data-ttu-id="dee55-106">静态编译的查询与XPath</span><span class="sxs-lookup"><span data-stu-id="dee55-106">Statically Compiled Queries vs. XPath</span></span>  
 <span data-ttu-id="dee55-107">下面的示例演示如何获取具有指定名称并包含带有指定值的属性的子代元素。</span><span class="sxs-lookup"><span data-stu-id="dee55-107">The following example shows how to get the descendant elements with a specified name, and with an attribute with a specified value.</span></span>  
  
 <span data-ttu-id="dee55-108">以下是等效的 XPath 表达式：</span><span class="sxs-lookup"><span data-stu-id="dee55-108">The following is the equivalent XPath expression:</span></span>  
  
```  
//Address[@Type='Shipping']  
```  
  
```csharp  
XDocument po = XDocument.Load("PurchaseOrders.xml");  
  
IEnumerable<XElement> list1 =  
    from el in po.Descendants("Address")  
    where (string)el.Attribute("Type") == "Shipping"  
    select el;  
  
foreach (XElement el in list1)  
    Console.WriteLine(el);  
```  
  
 <span data-ttu-id="dee55-109">编译器将本示例中的查询表达式重新编写为基于方法的查询语法。</span><span class="sxs-lookup"><span data-stu-id="dee55-109">The query expression in this example is re-written by the compiler to method-based query syntax.</span></span> <span data-ttu-id="dee55-110">以下使用基于方法的查询语法编写的示例将生成与上一示例相同的结果：</span><span class="sxs-lookup"><span data-stu-id="dee55-110">The following example, which is written in method-based query syntax, produces the same results as the previous one:</span></span>  
  
```csharp  
XDocument po = XDocument.Load("PurchaseOrders.xml");  
  
IEnumerable<XElement> list1 =  
    po  
    .Descendants("Address")  
    .Where(el => (string)el.Attribute("Type") == "Shipping");  
  
foreach (XElement el in list1)  
    Console.WriteLine(el);  
```  
  
 <span data-ttu-id="dee55-111"><xref:System.Linq.Enumerable.Where%2A> 方法为扩展方法。</span><span class="sxs-lookup"><span data-stu-id="dee55-111">The <xref:System.Linq.Enumerable.Where%2A> method is an extension method.</span></span> <span data-ttu-id="dee55-112">有关详细信息，请参阅[扩展方法](../../../../csharp/programming-guide/classes-and-structs/extension-methods.md)</span><span class="sxs-lookup"><span data-stu-id="dee55-112">For more information, see [Extension Methods](../../../../csharp/programming-guide/classes-and-structs/extension-methods.md).</span></span> <span data-ttu-id="dee55-113">由于 <xref:System.Linq.Enumerable.Where%2A> 是一个扩展方法，因此会将上面的查询视为按以下形式编写的查询进行编译：</span><span class="sxs-lookup"><span data-stu-id="dee55-113">Because <xref:System.Linq.Enumerable.Where%2A> is an extension method, the query above is compiled as though it were written as follows:</span></span>  
  
```csharp  
XDocument po = XDocument.Load("PurchaseOrders.xml");  
  
IEnumerable<XElement> list1 =  
    System.Linq.Enumerable.Where(  
        po.Descendants("Address"),  
        el => (string)el.Attribute("Type") == "Shipping");  
  
foreach (XElement el in list1)  
    Console.WriteLine(el);  
```  
  
 <span data-ttu-id="dee55-114">此示例将生成与前面两个示例完全相同的结果。</span><span class="sxs-lookup"><span data-stu-id="dee55-114">This example produces exactly the same results as the previous two examples.</span></span> <span data-ttu-id="dee55-115">这一结果表明：这些查询已被有效地编译成静态链接的方法调用。</span><span class="sxs-lookup"><span data-stu-id="dee55-115">This illustrates the fact that queries are effectively compiled into statically linked method calls.</span></span> <span data-ttu-id="dee55-116">这与迭代器的延迟执行语义一起可提高性能。</span><span class="sxs-lookup"><span data-stu-id="dee55-116">This, combined with the deferred execution semantics of iterators, improves performance.</span></span> <span data-ttu-id="dee55-117">有关迭代器的延迟执行语义的详细信息，请参阅 [LINQ to XML 中的延迟执行和迟缓计算 (C#)](../../../../csharp/programming-guide/concepts/linq/deferred-execution-and-lazy-evaluation-in-linq-to-xml.md)。</span><span class="sxs-lookup"><span data-stu-id="dee55-117">For more information about the deferred execution semantics of iterators, see [Deferred Execution and Lazy Evaluation in LINQ to XML (C#)](../../../../csharp/programming-guide/concepts/linq/deferred-execution-and-lazy-evaluation-in-linq-to-xml.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dee55-118">这些示例代表了编译器可能编写的代码。</span><span class="sxs-lookup"><span data-stu-id="dee55-118">These examples are representative of the code that the compiler might write.</span></span> <span data-ttu-id="dee55-119">这些示例的实际实现可能会略有不同，但对于这些示例来说，执行的性能是相同或类似的。</span><span class="sxs-lookup"><span data-stu-id="dee55-119">The actual implementation might differ slightly from these examples, but the performance will be the same or similar to these examples.</span></span>  
  
## <a name="executing-xpath-expressions-with-xmldocument"></a><span data-ttu-id="dee55-120">使用 XmlDocument 执行 XPath 表达式</span><span class="sxs-lookup"><span data-stu-id="dee55-120">Executing XPath Expressions with XmlDocument</span></span>  
 <span data-ttu-id="dee55-121">下面的示例使用 <xref:System.Xml.XmlDocument> 来完成与前面的示例相同的结果：</span><span class="sxs-lookup"><span data-stu-id="dee55-121">The following example uses <xref:System.Xml.XmlDocument> to accomplish the same results as the previous examples:</span></span>  
  
```csharp  
XmlReader reader = XmlReader.Create("PurchaseOrders.xml");  
XmlDocument doc = new XmlDocument();  
doc.Load(reader);  
XmlNodeList nl = doc.SelectNodes(".//Address[@Type='Shipping']");  
foreach (XmlNode n in nl)  
    Console.WriteLine(n.OuterXml);  
reader.Close();  
```  
  
 <span data-ttu-id="dee55-122">此查询将返回与使用 LINQ to XML 的示例相同的输出；唯一的差别是：LINQ to XML 会缩进输出的 XML，而 <xref:System.Xml.XmlDocument> 不会。</span><span class="sxs-lookup"><span data-stu-id="dee55-122">This query returns the same output as the examples that use LINQ to XML; the only difference is that LINQ to XML indents the printed XML, whereas <xref:System.Xml.XmlDocument> does not.</span></span>  
  
 <span data-ttu-id="dee55-123">但是，<xref:System.Xml.XmlDocument> 方法的执行性能通常不如 LINQ to XML，因为在每次调用 <xref:System.Xml.XmlNode.SelectNodes%2A> 方法时，它都必须在内部执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="dee55-123">However, the <xref:System.Xml.XmlDocument> approach generally does not perform as well as LINQ to XML, because the <xref:System.Xml.XmlNode.SelectNodes%2A> method must do the following internally every time it is called:</span></span>  
  
-   <span data-ttu-id="dee55-124">分析包含 XPath 表达式的字符串，并将字符串划分成多个标记。</span><span class="sxs-lookup"><span data-stu-id="dee55-124">It parses the string that contains the XPath expression, breaking the string into tokens.</span></span>  
  
-   <span data-ttu-id="dee55-125">验证这些标记以确保 XPath 表达式有效。</span><span class="sxs-lookup"><span data-stu-id="dee55-125">It validates the tokens to make sure that the XPath expression is valid.</span></span>  
  
-   <span data-ttu-id="dee55-126">将表达式转换为内部表达式树。</span><span class="sxs-lookup"><span data-stu-id="dee55-126">It translates the expression into an internal expression tree.</span></span>  
  
-   <span data-ttu-id="dee55-127">循环访问节点，为基于表达式计算的结果集选择适当的节点。</span><span class="sxs-lookup"><span data-stu-id="dee55-127">It iterates through the nodes, appropriately selecting the nodes for the result set based on the evaluation of the expression.</span></span>  
  
 <span data-ttu-id="dee55-128">与相应的 LINQ to XML 查询完成的工作相比，这需要执行非常多的工作。</span><span class="sxs-lookup"><span data-stu-id="dee55-128">This is significantly more than the work done by the corresponding LINQ to XML query.</span></span> <span data-ttu-id="dee55-129">特定的性能差异将因不同的查询类型而异，但一般来说，与使用 <xref:System.Xml.XmlDocument> 计算 XPath 表达式相比，LINQ to XML 查询执行的工作较少，因此会获得更好的性能。</span><span class="sxs-lookup"><span data-stu-id="dee55-129">The specific performance difference varies for different types of queries, but in general LINQ to XML queries do less work, and therefore perform better, than evaluating XPath expressions using <xref:System.Xml.XmlDocument>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dee55-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="dee55-130">See Also</span></span>

- [<span data-ttu-id="dee55-131">性能 (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="dee55-131">Performance (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/performance-linq-to-xml.md)
