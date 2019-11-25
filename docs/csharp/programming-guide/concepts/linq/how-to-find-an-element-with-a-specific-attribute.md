---
title: 如何查找具有特定特性的元素 (C#)
ms.date: 07/20/2015
ms.assetid: b92591aa-3cfb-490e-99f6-da8de335e362
ms.openlocfilehash: 106885b8658c493caab3101e6b4ce921589076eb
ms.sourcegitcommit: fbb8a593a511ce667992502a3ce6d8f65c594edf
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/16/2019
ms.locfileid: "74141165"
---
# <a name="how-to-find-an-element-with-a-specific-attribute-c"></a><span data-ttu-id="f12b1-102">如何查找具有特定特性的元素 (C#)</span><span class="sxs-lookup"><span data-stu-id="f12b1-102">How to find an element with a specific attribute (C#)</span></span>
<span data-ttu-id="f12b1-103">本主题演示如何查找其属性具有特定值的元素。</span><span class="sxs-lookup"><span data-stu-id="f12b1-103">This topic shows how to find an element that has an attribute that has a specific value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f12b1-104">示例</span><span class="sxs-lookup"><span data-stu-id="f12b1-104">Example</span></span>  
 <span data-ttu-id="f12b1-105">本示例演示如何查找具有值为“Billing”的 `Address` 属性的 `Type` 元素。</span><span class="sxs-lookup"><span data-stu-id="f12b1-105">The example shows how to find the `Address` element that has a `Type` attribute with a value of "Billing".</span></span>  
  
 <span data-ttu-id="f12b1-106">本示例使用下面的 XML 文档：[示例 XML 文件：典型采购订单 (LINQ to XML)](./sample-xml-file-typical-purchase-order-linq-to-xml-1.md)。</span><span class="sxs-lookup"><span data-stu-id="f12b1-106">This example uses the following XML document: [Sample XML File: Typical Purchase Order (LINQ to XML)](./sample-xml-file-typical-purchase-order-linq-to-xml-1.md).</span></span>  
  
```csharp  
XElement root = XElement.Load("PurchaseOrder.xml");  
IEnumerable<XElement> address =  
    from el in root.Elements("Address")  
    where (string)el.Attribute("Type") == "Billing"  
    select el;  
foreach (XElement el in address)  
    Console.WriteLine(el);  
```  
  
 <span data-ttu-id="f12b1-107">此代码生成以下输出：</span><span class="sxs-lookup"><span data-stu-id="f12b1-107">This code produces the following output:</span></span>  
  
```xml  
<Address Type="Billing">  
  <Name>Tai Yee</Name>  
  <Street>8 Oak Avenue</Street>  
  <City>Old Town</City>  
  <State>PA</State>  
  <Zip>95819</Zip>  
  <Country>USA</Country>  
</Address>  
```  
  
## <a name="example"></a><span data-ttu-id="f12b1-108">示例</span><span class="sxs-lookup"><span data-stu-id="f12b1-108">Example</span></span>  
 <span data-ttu-id="f12b1-109">下面的示例演示如何对命名空间中的 XML 进行同样的查询。</span><span class="sxs-lookup"><span data-stu-id="f12b1-109">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="f12b1-110">有关详细信息，请参阅[命名空间概述(LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md)。</span><span class="sxs-lookup"><span data-stu-id="f12b1-110">For more information, see [Namespaces Overview (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="f12b1-111">本示例使用下面的 XML 文档：[示例 XML 文件：命名空间中的典型采购单](./sample-xml-file-typical-purchase-order-in-a-namespace.md)。</span><span class="sxs-lookup"><span data-stu-id="f12b1-111">This example uses the following XML document: [Sample XML File: Typical Purchase Order in a Namespace](./sample-xml-file-typical-purchase-order-in-a-namespace.md).</span></span>  
  
```csharp  
XElement root = XElement.Load("PurchaseOrderInNamespace.xml");  
XNamespace aw = "http://www.adventure-works.com";  
IEnumerable<XElement> address =  
    from el in root.Elements(aw + "Address")  
    where (string)el.Attribute(aw + "Type") == "Billing"  
    select el;  
foreach (XElement el in address)  
    Console.WriteLine(el);  
```  
  
 <span data-ttu-id="f12b1-112">此代码生成以下输出：</span><span class="sxs-lookup"><span data-stu-id="f12b1-112">This code produces the following output:</span></span>  
  
```xml  
<aw:Address aw:Type="Billing" xmlns:aw="http://www.adventure-works.com">  
  <aw:Name>Tai Yee</aw:Name>  
  <aw:Street>8 Oak Avenue</aw:Street>  
  <aw:City>Old Town</aw:City>  
  <aw:State>PA</aw:State>  
  <aw:Zip>95819</aw:Zip>  
  <aw:Country>USA</aw:Country>  
</aw:Address>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f12b1-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="f12b1-113">See also</span></span>

- <xref:System.Xml.Linq.XElement.Attribute%2A>
- <xref:System.Xml.Linq.XContainer.Elements%2A>
- [<span data-ttu-id="f12b1-114">标准查询运算符概述 (C#)</span><span class="sxs-lookup"><span data-stu-id="f12b1-114">Standard Query Operators Overview (C#)</span></span>](./standard-query-operators-overview.md)
- [<span data-ttu-id="f12b1-115">投影运算 (C#)</span><span class="sxs-lookup"><span data-stu-id="f12b1-115">Projection Operations (C#)</span></span>](./projection-operations.md)
