---
title: 如何：筛选元素名称 (LINQ to XML) (C#)
ms.date: 07/20/2015
ms.assetid: 1849fb03-f075-421f-863c-e8fb32773cdf
ms.openlocfilehash: 586c371fdd014eee6eb21563214d9e26a0e264fe
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54540775"
---
# <a name="how-to-filter-on-element-names-linq-to-xml-c"></a><span data-ttu-id="b57e8-102">如何：筛选元素名称 (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="b57e8-102">How to: Filter on Element Names (LINQ to XML) (C#)</span></span>
<span data-ttu-id="b57e8-103">当调用返回 <xref:System.Collections.Generic.IEnumerable%601> 的 <xref:System.Xml.Linq.XElement> 的方法之一时，可以根据元素名称进行筛选。</span><span class="sxs-lookup"><span data-stu-id="b57e8-103">When you call one of the methods that return <xref:System.Collections.Generic.IEnumerable%601> of <xref:System.Xml.Linq.XElement>, you can filter on the element name.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b57e8-104">示例</span><span class="sxs-lookup"><span data-stu-id="b57e8-104">Example</span></span>  
 <span data-ttu-id="b57e8-105">本示例说明如何检索经过筛选仅包含具有指定名称的子代的集合。</span><span class="sxs-lookup"><span data-stu-id="b57e8-105">This example retrieves a collection of descendants that is filtered to contain only descendants with the specified name.</span></span>  
  
 <span data-ttu-id="b57e8-106">本示例使用下面的 XML 文档：[示例 XML 文件：典型采购订单 (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml-1.md)。</span><span class="sxs-lookup"><span data-stu-id="b57e8-106">This example uses the following XML document: [Sample XML File: Typical Purchase Order (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml-1.md).</span></span>  
  
```csharp  
XElement po = XElement.Load("PurchaseOrder.xml");  
IEnumerable<XElement> items =  
    from el in po.Descendants("ProductName")  
    select el;  
foreach(XElement prdName in items)  
    Console.WriteLine(prdName.Name + ":" + (string) prdName);  
```  
  
 <span data-ttu-id="b57e8-107">此代码生成以下输出：</span><span class="sxs-lookup"><span data-stu-id="b57e8-107">This code produces the following output:</span></span>  
  
```  
ProductName:Lawnmower  
ProductName:Baby Monitor  
```  
  
 <span data-ttu-id="b57e8-108">其他返回 <xref:System.Collections.Generic.IEnumerable%601> 集合的 <xref:System.Xml.Linq.XElement> 的方法都遵循相同的模式。</span><span class="sxs-lookup"><span data-stu-id="b57e8-108">The other methods that return <xref:System.Collections.Generic.IEnumerable%601> of <xref:System.Xml.Linq.XElement> collections follow the same pattern.</span></span> <span data-ttu-id="b57e8-109">它们的签名类似于 <xref:System.Xml.Linq.XContainer.Elements%2A> 和 <xref:System.Xml.Linq.XContainer.Descendants%2A>。</span><span class="sxs-lookup"><span data-stu-id="b57e8-109">Their signatures are similar to <xref:System.Xml.Linq.XContainer.Elements%2A> and <xref:System.Xml.Linq.XContainer.Descendants%2A>.</span></span> <span data-ttu-id="b57e8-110">以下是具有相似方法签名的完整方法列表：</span><span class="sxs-lookup"><span data-stu-id="b57e8-110">The following is the complete list of methods that have similar method signatures:</span></span>  
  
-   <xref:System.Xml.Linq.XNode.Ancestors%2A>  
  
-   <xref:System.Xml.Linq.XContainer.Descendants%2A>  
  
-   <xref:System.Xml.Linq.XContainer.Elements%2A>  
  
-   <xref:System.Xml.Linq.XNode.ElementsAfterSelf%2A>  
  
-   <xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A>  
  
-   <xref:System.Xml.Linq.XElement.AncestorsAndSelf%2A>  
  
-   <xref:System.Xml.Linq.XElement.DescendantsAndSelf%2A>  
  
## <a name="example"></a><span data-ttu-id="b57e8-111">示例</span><span class="sxs-lookup"><span data-stu-id="b57e8-111">Example</span></span>  
 <span data-ttu-id="b57e8-112">下面的示例演示如何对命名空间中的 XML 进行同样的查询。</span><span class="sxs-lookup"><span data-stu-id="b57e8-112">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="b57e8-113">有关详细信息，请参阅[使用 XML 命名空间 (C#)](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md)。</span><span class="sxs-lookup"><span data-stu-id="b57e8-113">For more information, see [Working with XML Namespaces (C#)](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span></span>  
  
 <span data-ttu-id="b57e8-114">本示例使用下面的 XML 文档：[示例 XML 文件：命名空间中的典型采购单](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-in-a-namespace.md)。</span><span class="sxs-lookup"><span data-stu-id="b57e8-114">This example uses the following XML document: [Sample XML File: Typical Purchase Order in a Namespace](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-in-a-namespace.md).</span></span>  
  
```csharp  
XNamespace aw = "http://www.adventure-works.com";  
XElement po = XElement.Load("PurchaseOrderInNamespace.xml");  
IEnumerable<XElement> items =  
    from el in po.Descendants(aw + "ProductName")  
    select el;  
foreach (XElement prdName in items)  
    Console.WriteLine(prdName.Name + ":" + (string)prdName);  
```  
  
 <span data-ttu-id="b57e8-115">此代码生成以下输出：</span><span class="sxs-lookup"><span data-stu-id="b57e8-115">This code produces the following output:</span></span>  
  
```  
{http://www.adventure-works.com}ProductName:Lawnmower  
{http://www.adventure-works.com}ProductName:Baby Monitor  
```  
  
## <a name="see-also"></a><span data-ttu-id="b57e8-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="b57e8-116">See also</span></span>

- [<span data-ttu-id="b57e8-117">LINQ to XML 轴 (C#)</span><span class="sxs-lookup"><span data-stu-id="b57e8-117">LINQ to XML Axes (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-axes.md)
