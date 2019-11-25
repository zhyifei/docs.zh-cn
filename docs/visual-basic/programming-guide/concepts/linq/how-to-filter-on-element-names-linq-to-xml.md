---
title: 如何：筛选元素名称 (LINQ to XML)
ms.date: 07/20/2015
ms.assetid: b1437b4a-48aa-4546-834a-d6d3ab015fe1
ms.openlocfilehash: 0c443ffa17f7bd4f7537068b97165cda97a37ced
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74353025"
---
# <a name="how-to-filter-on-element-names-linq-to-xml-visual-basic"></a><span data-ttu-id="85404-102">How to: Filter on Element Names (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="85404-102">How to: Filter on Element Names (LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="85404-103">当调用返回 <xref:System.Collections.Generic.IEnumerable%601> 的 <xref:System.Xml.Linq.XElement> 的方法之一时，可以根据元素名称进行筛选。</span><span class="sxs-lookup"><span data-stu-id="85404-103">When you call one of the methods that return <xref:System.Collections.Generic.IEnumerable%601> of <xref:System.Xml.Linq.XElement>, you can filter on the element name.</span></span>  
  
## <a name="example"></a><span data-ttu-id="85404-104">示例</span><span class="sxs-lookup"><span data-stu-id="85404-104">Example</span></span>  
 <span data-ttu-id="85404-105">本示例说明如何检索经过筛选仅包含具有指定名称的子代的集合。</span><span class="sxs-lookup"><span data-stu-id="85404-105">This example retrieves a collection of descendants that is filtered to contain only descendants with the specified name.</span></span>  
  
 <span data-ttu-id="85404-106">本示例使用以下 XML 文档：[示例 XML 文件：典型采购订单 (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml.md)。</span><span class="sxs-lookup"><span data-stu-id="85404-106">This example uses the following XML document: [Sample XML File: Typical Purchase Order (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml.md).</span></span>  
  
```vb  
Dim po As XElement = XElement.Load("PurchaseOrder.xml")  
Dim items As IEnumerable(Of XElement) = _  
    From el In po...<ProductName> _  
    Select el  
For Each prdName As XElement In items  
    Console.WriteLine(prdName.Name.ToString & ":" & prdName.Value)  
Next  
```  
  
 <span data-ttu-id="85404-107">此代码生成以下输出：</span><span class="sxs-lookup"><span data-stu-id="85404-107">This code produces the following output:</span></span>  
  
```console  
ProductName:Lawnmower  
ProductName:Baby Monitor  
```  
  
 <span data-ttu-id="85404-108">其他返回 <xref:System.Collections.Generic.IEnumerable%601> 集合的 <xref:System.Xml.Linq.XElement> 的方法都遵循相同的模式。</span><span class="sxs-lookup"><span data-stu-id="85404-108">The other methods that return <xref:System.Collections.Generic.IEnumerable%601> of <xref:System.Xml.Linq.XElement> collections follow the same pattern.</span></span> <span data-ttu-id="85404-109">它们的签名类似于 <xref:System.Xml.Linq.XContainer.Elements%2A> 和 <xref:System.Xml.Linq.XContainer.Descendants%2A>。</span><span class="sxs-lookup"><span data-stu-id="85404-109">Their signatures are similar to <xref:System.Xml.Linq.XContainer.Elements%2A> and <xref:System.Xml.Linq.XContainer.Descendants%2A>.</span></span> <span data-ttu-id="85404-110">以下是具有相似方法签名的完整方法列表：</span><span class="sxs-lookup"><span data-stu-id="85404-110">The following is the complete list of methods that have similar method signatures:</span></span>  
  
- <xref:System.Xml.Linq.XNode.Ancestors%2A>  
  
- <xref:System.Xml.Linq.XContainer.Descendants%2A>  
  
- <xref:System.Xml.Linq.XContainer.Elements%2A>  
  
- <xref:System.Xml.Linq.XNode.ElementsAfterSelf%2A>  
  
- <xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A>  
  
- <xref:System.Xml.Linq.XElement.AncestorsAndSelf%2A>  
  
- <xref:System.Xml.Linq.XElement.DescendantsAndSelf%2A>  
  
## <a name="example"></a><span data-ttu-id="85404-111">示例</span><span class="sxs-lookup"><span data-stu-id="85404-111">Example</span></span>  
 <span data-ttu-id="85404-112">下面的示例演示如何对命名空间中的 XML 进行同样的查询。</span><span class="sxs-lookup"><span data-stu-id="85404-112">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="85404-113">For more information, see [Namespaces Overview (LINQ to XML) (Visual Basic)](namespaces-overview-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="85404-113">For more information, see [Namespaces Overview (LINQ to XML) (Visual Basic)](namespaces-overview-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="85404-114">本示例使用以下 XML 文档：[示例 XML 文件：命名空间中的典型采购订单](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-in-a-namespace.md)。</span><span class="sxs-lookup"><span data-stu-id="85404-114">This example uses the following XML document: [Sample XML File: Typical Purchase Order in a Namespace](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-in-a-namespace.md).</span></span>  
  
```vb  
Imports <xmlns:aw="http://www.adventure-works.com">  
  
Module Module1  
    Sub Main()  
        Dim po As XElement = XElement.Load("PurchaseOrderInNamespace.xml")  
        Dim items As IEnumerable(Of XElement) = _  
            From el In po...<aw:ProductName> _  
            Select el  
        For Each prdName As XElement In items  
            Console.WriteLine(prdName.Name.ToString & ":" & prdName.Value)  
        Next  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="85404-115">此代码生成以下输出：</span><span class="sxs-lookup"><span data-stu-id="85404-115">This code produces the following output:</span></span>  
  
```console  
{http://www.adventure-works.com}ProductName:Lawnmower  
{http://www.adventure-works.com}ProductName:Baby Monitor  
```  
  
## <a name="see-also"></a><span data-ttu-id="85404-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="85404-116">See also</span></span>

- [<span data-ttu-id="85404-117">LINQ to XML 轴 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="85404-117">LINQ to XML Axes (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-axes.md)
