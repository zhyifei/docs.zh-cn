---
title: 如何查找根元素 (XPath-LINQ to XML) (C#)
ms.date: 07/20/2015
ms.assetid: 4fd824e0-4d39-429b-b092-f6a5c046ee6c
ms.openlocfilehash: 1c5526f436b5b9d88ca359ef7e0fc04c5c3cf43c
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/25/2019
ms.locfileid: "75345945"
---
# <a name="how-to-find-the-root-element-xpath-linq-to-xml-c"></a><span data-ttu-id="65e54-102">如何查找根元素 (XPath-LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="65e54-102">How to find the root element (XPath-LINQ to XML) (C#)</span></span>
<span data-ttu-id="65e54-103">本主题演示如何使用 XPath 和 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 获取根元素。</span><span class="sxs-lookup"><span data-stu-id="65e54-103">This topic shows how to get the root element with XPath and [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span></span>  
  
 <span data-ttu-id="65e54-104">XPath 表达式为：</span><span class="sxs-lookup"><span data-stu-id="65e54-104">The XPath expression is:</span></span>  
  
 `/PurchaseOrders`  
  
## <a name="example"></a><span data-ttu-id="65e54-105">示例</span><span class="sxs-lookup"><span data-stu-id="65e54-105">Example</span></span>  
 <span data-ttu-id="65e54-106">此示例查找根元素。</span><span class="sxs-lookup"><span data-stu-id="65e54-106">This example finds the root element.</span></span>  
  
 <span data-ttu-id="65e54-107">本示例使用下面的 XML 文档：[示例 XML 文件：多个采购订单 (LINQ to XML)](./sample-xml-file-multiple-purchase-orders-linq-to-xml.md)。</span><span class="sxs-lookup"><span data-stu-id="65e54-107">This example uses the following XML document: [Sample XML File: Multiple Purchase Orders (LINQ to XML)](./sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span></span>  
  
```csharp  
XDocument po = XDocument.Load("PurchaseOrders.xml");  
  
// LINQ to XML query  
XElement el1 = po.Root;  
  
// XPath expression  
XElement el2 = po.XPathSelectElement("/PurchaseOrders");  
  
if (el1 == el2)  
    Console.WriteLine("Results are identical");  
else  
    Console.WriteLine("Results differ");  
Console.WriteLine(el1.Name);  
```  
  
 <span data-ttu-id="65e54-108">该示例产生下面的输出：</span><span class="sxs-lookup"><span data-stu-id="65e54-108">This example produces the following output:</span></span>  
  
```output  
Results are identical  
PurchaseOrders  
```  
