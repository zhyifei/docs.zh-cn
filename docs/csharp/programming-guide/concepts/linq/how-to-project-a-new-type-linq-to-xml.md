---
title: 如何：投影新类型 (LINQ to XML) (C#)
ms.date: 07/20/2015
ms.assetid: 48145cf9-1e0b-4e73-bbfd-28fc04800dc4
ms.openlocfilehash: f9a46e78a0f80f33764e9f87e3e8ce3560a8e0f3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33323766"
---
# <a name="how-to-project-a-new-type-linq-to-xml-c"></a><span data-ttu-id="18f8f-102">如何：投影新类型 (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="18f8f-102">How to: Project a New Type (LINQ to XML) (C#)</span></span>
<span data-ttu-id="18f8f-103">本节中的其他示例已演示了一些查询，这些查询以 <xref:System.Collections.Generic.IEnumerable%601> 的 <xref:System.Xml.Linq.XElement>、<xref:System.Collections.Generic.IEnumerable%601> 的 `string` 和 <xref:System.Collections.Generic.IEnumerable%601> 的 `int` 的形式返回结果。</span><span class="sxs-lookup"><span data-stu-id="18f8f-103">Other examples in this section have shown queries that return results as <xref:System.Collections.Generic.IEnumerable%601> of <xref:System.Xml.Linq.XElement>, <xref:System.Collections.Generic.IEnumerable%601> of `string`, and <xref:System.Collections.Generic.IEnumerable%601> of `int`.</span></span> <span data-ttu-id="18f8f-104">这些是常见结果类型，但它们不是对所有情况都适用。</span><span class="sxs-lookup"><span data-stu-id="18f8f-104">These are common result types, but they are not appropriate for every scenario.</span></span> <span data-ttu-id="18f8f-105">在很多情况下，会希望查询返回其他类型的 <xref:System.Collections.Generic.IEnumerable%601>。</span><span class="sxs-lookup"><span data-stu-id="18f8f-105">In many cases you will want your queries to return an <xref:System.Collections.Generic.IEnumerable%601> of some other type.</span></span>  
  
## <a name="example"></a><span data-ttu-id="18f8f-106">示例</span><span class="sxs-lookup"><span data-stu-id="18f8f-106">Example</span></span>  
 <span data-ttu-id="18f8f-107">此示例演示如何在 `select` 子句中实例化对象。</span><span class="sxs-lookup"><span data-stu-id="18f8f-107">This example shows how to instantiate objects in the `select` clause.</span></span> <span data-ttu-id="18f8f-108">代码首先定义一个具有一个构造函数的新类，然后修改 `select` 语句，使该表达式成为新类的新实例。</span><span class="sxs-lookup"><span data-stu-id="18f8f-108">The code first defines a new class with a constructor, and then modifies the `select` statement so that the expression is a new instance of the new class.</span></span>  
  
 <span data-ttu-id="18f8f-109">本示例使用以下 XML 文档：[示例 XML 文件：典型采购订单 (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml-1.md)。</span><span class="sxs-lookup"><span data-stu-id="18f8f-109">This example uses the following XML document: [Sample XML File: Typical Purchase Order (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml-1.md).</span></span>  
  
```csharp  
class NameQty {  
    public string name;  
    public int qty;  
    public NameQty(string n, int q)  
    {  
        name = n;  
        qty = q;  
    }  
};  
  
class Program {  
    public static void Main() {  
        XElement po = XElement.Load("PurchaseOrder.xml");  
  
        IEnumerable<NameQty> nqList =  
            from n in po.Descendants("Item")  
            select new NameQty(  
                    (string)n.Element("ProductName"),  
                    (int)n.Element("Quantity")  
                );  
  
        foreach (NameQty n in nqList)  
            Console.WriteLine(n.name + ":" + n.qty);  
    }  
}  
```  
  
 <span data-ttu-id="18f8f-110">本示例使用主题[如何：检索单个子元素 (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-retrieve-a-single-child-element-linq-to-xml.md)中引入的 `M:System.Xml.Linq.XElement.Element` 方法。</span><span class="sxs-lookup"><span data-stu-id="18f8f-110">This example uses the `M:System.Xml.Linq.XElement.Element` method that was introduced in the topic [How to: Retrieve a Single Child Element (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-retrieve-a-single-child-element-linq-to-xml.md).</span></span> <span data-ttu-id="18f8f-111">还使用强制转换来检索 `M:System.Xml.Linq.XElement.Element` 方法返回的元素值。</span><span class="sxs-lookup"><span data-stu-id="18f8f-111">It also uses casts to retrieve the values of the elements that are returned by the `M:System.Xml.Linq.XElement.Element` method.</span></span>  
  
 <span data-ttu-id="18f8f-112">该示例产生下面的输出：</span><span class="sxs-lookup"><span data-stu-id="18f8f-112">This example produces the following output:</span></span>  
  
```  
Lawnmower:1  
Baby Monitor:2  
```  
  
## <a name="see-also"></a><span data-ttu-id="18f8f-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="18f8f-113">See Also</span></span>  
 [<span data-ttu-id="18f8f-114">投影和转换 (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="18f8f-114">Projections and Transformations (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/projections-and-transformations-linq-to-xml.md)
