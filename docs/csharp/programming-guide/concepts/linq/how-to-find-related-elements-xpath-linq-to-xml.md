---
title: 如何查找相关元素 (XPath-LINQ to XML) (C#)
ms.date: 07/20/2015
ms.assetid: 41b386ee-562d-4841-bd6b-e44a7eb69f26
ms.openlocfilehash: f74c338019c0451ab5e3ac0d8da10392ae5601ed
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "79169228"
---
# <a name="how-to-find-related-elements-xpath-linq-to-xml-c"></a><span data-ttu-id="e8ef2-102">如何查找相关元素 (XPath-LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="e8ef2-102">How to find related elements (XPath-LINQ to XML) (C#)</span></span>
<span data-ttu-id="e8ef2-103">本主题演示如何在由其他元素的值所引用的属性上获取元素选择。</span><span class="sxs-lookup"><span data-stu-id="e8ef2-103">This topic shows how to get an element selecting on an attribute that is referred to by the value of another element.</span></span>  
  
 <span data-ttu-id="e8ef2-104">XPath 表达式为：</span><span class="sxs-lookup"><span data-stu-id="e8ef2-104">The XPath expression is:</span></span>  
  
 `.//Customer[@CustomerID=/Root/Orders/Order[12]/CustomerID]`  
  
## <a name="example"></a><span data-ttu-id="e8ef2-105">示例</span><span class="sxs-lookup"><span data-stu-id="e8ef2-105">Example</span></span>  
 <span data-ttu-id="e8ef2-106">本示例查找第 12 个 `Order` 元素，然后查找该订单的客户。</span><span class="sxs-lookup"><span data-stu-id="e8ef2-106">This example finds the 12th `Order` element, and then finds the customer for that order.</span></span>  
  
 <span data-ttu-id="e8ef2-107">请注意，在 .NET 中，列表索引是从零开始编制。</span><span class="sxs-lookup"><span data-stu-id="e8ef2-107">Note that indexing into a list in .NET is 'zero' based.</span></span> <span data-ttu-id="e8ef2-108">在 XPath 谓词中，对节点集合的索引是从 1 开始的。</span><span class="sxs-lookup"><span data-stu-id="e8ef2-108">Indexing into a collection of nodes in an XPath predicate is 'one' based.</span></span> <span data-ttu-id="e8ef2-109">本示例反映了这种差别。</span><span class="sxs-lookup"><span data-stu-id="e8ef2-109">This example reflects this difference.</span></span>  
  
 <span data-ttu-id="e8ef2-110">本示例使用下面的 XML 文档：[示例 XML 文件：客户和订单 (LINQ to XML)](./sample-xml-file-customers-and-orders-linq-to-xml-2.md)。</span><span class="sxs-lookup"><span data-stu-id="e8ef2-110">This example uses the following XML document: [Sample XML File: Customers and Orders (LINQ to XML)](./sample-xml-file-customers-and-orders-linq-to-xml-2.md).</span></span>  
  
```csharp  
XDocument co = XDocument.Load("CustomersOrders.xml");  
  
// LINQ to XML query  
XElement customer1 =  
    (from el in co.Descendants("Customer")  
     where (string)el.Attribute("CustomerID") ==  
          (string)(co  
              .Element("Root")  
              .Element("Orders")  
              .Elements("Order")  
              .ToList()[11]  
              .Element("CustomerID"))  
    select el)  
    .First();  
  
// An alternate way to write the query that avoids creation  
// of a System.Collections.Generic.List:  
XElement customer2 =  
    (from el in co.Descendants("Customer")  
     where (string)el.Attribute("CustomerID") ==  
          (string)(co  
              .Element("Root")  
              .Element("Orders")  
              .Elements("Order")  
              .Skip(11).First()  
              .Element("CustomerID"))  
    select el)  
    .First();  
  
// XPath expression  
XElement customer3 = co.XPathSelectElement(  
  ".//Customer[@CustomerID=/Root/Orders/Order[12]/CustomerID]");  
  
if (customer1 == customer2 && customer1 == customer3)  
    Console.WriteLine("Results are identical");  
else  
    Console.WriteLine("Results differ");  
Console.WriteLine(customer1);  
```  
  
 <span data-ttu-id="e8ef2-111">该示例产生下面的输出：</span><span class="sxs-lookup"><span data-stu-id="e8ef2-111">This example produces the following output:</span></span>  
  
```output  
Results are identical  
<Customer CustomerID="HUNGC">  
  <CompanyName>Hungry Coyote Import Store</CompanyName>  
  <ContactName>Yoshi Latimer</ContactName>  
  <ContactTitle>Sales Representative</ContactTitle>  
  <Phone>(503) 555-6874</Phone>  
  <Fax>(503) 555-2376</Fax>  
  <FullAddress>  
    <Address>City Center Plaza 516 Main St.</Address>  
    <City>Elgin</City>  
    <Region>OR</Region>  
    <PostalCode>97827</PostalCode>  
    <Country>USA</Country>  
  </FullAddress>  
</Customer>  
```  
