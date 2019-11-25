---
title: 如何查找子代元素 (XPath-LINQ to XML) (C#)
ms.date: 07/20/2015
ms.assetid: b318da39-bb8b-4c56-a019-e13b12b01831
ms.openlocfilehash: c90651502629284c67cc16de8a1aa59c392ae178
ms.sourcegitcommit: fbb8a593a511ce667992502a3ce6d8f65c594edf
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/16/2019
ms.locfileid: "74141114"
---
# <a name="how-to-find-descendant-elements-xpath-linq-to-xml-c"></a><span data-ttu-id="daf1e-102">如何查找子代元素 (XPath-LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="daf1e-102">How to find descendant elements (XPath-LINQ to XML) (C#)</span></span>
<span data-ttu-id="daf1e-103">本主题演示如何获取具有特定名称的后代元素。</span><span class="sxs-lookup"><span data-stu-id="daf1e-103">This topic shows how to get the descendant elements with a particular name.</span></span>  
  
 <span data-ttu-id="daf1e-104">XPath 表达式为 `//Name`。</span><span class="sxs-lookup"><span data-stu-id="daf1e-104">The XPath expression is `//Name`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="daf1e-105">示例</span><span class="sxs-lookup"><span data-stu-id="daf1e-105">Example</span></span>  
 <span data-ttu-id="daf1e-106">本示例查找名为 `Name` 的所有后代。</span><span class="sxs-lookup"><span data-stu-id="daf1e-106">This example finds all descendants named `Name`.</span></span>  
  
 <span data-ttu-id="daf1e-107">本示例使用下面的 XML 文档：[示例 XML 文件：多个采购订单 (LINQ to XML)](./sample-xml-file-multiple-purchase-orders-linq-to-xml.md)。</span><span class="sxs-lookup"><span data-stu-id="daf1e-107">This example uses the following XML document: [Sample XML File: Multiple Purchase Orders (LINQ to XML)](./sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span></span>  
  
```csharp  
XDocument po = XDocument.Load("PurchaseOrders.xml");  
  
// LINQ to XML query  
IEnumerable<XElement> list1 = po.Root.Descendants("Name");  
  
// XPath expression  
IEnumerable<XElement> list2 = po.XPathSelectElements("//Name");  
  
if (list1.Count() == list2.Count() &&  
        list1.Intersect(list2).Count() == list1.Count())  
    Console.WriteLine("Results are identical");  
else  
    Console.WriteLine("Results differ");  
foreach (XElement el in list1)  
    Console.WriteLine(el);  
```  
  
 <span data-ttu-id="daf1e-108">该示例产生下面的输出：</span><span class="sxs-lookup"><span data-stu-id="daf1e-108">This example produces the following output:</span></span>  
  
```output  
Results are identical  
<Name>Ellen Adams</Name>  
<Name>Tai Yee</Name>  
<Name>Cristian Osorio</Name>  
<Name>Cristian Osorio</Name>  
<Name>Jessica Arnold</Name>  
<Name>Jessica Arnold</Name>  
```  
