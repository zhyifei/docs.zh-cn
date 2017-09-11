---
title: "示例 XML 文件：命名空间 3 中的数值数据"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 51750cab-3c66-4511-90fb-b9d211308d31
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 5b02c0990a73aa18b4ce7e7b6ff652ad485ed854
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="sample-xml-file-numerical-data-in-a-namespace"></a><span data-ttu-id="be030-102">示例 XML 文件：命名空间中的数值数据</span><span class="sxs-lookup"><span data-stu-id="be030-102">Sample XML File: Numerical Data in a Namespace</span></span>
<span data-ttu-id="be030-103">下面的 XML 文件用在 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 文档的很多示例中。</span><span class="sxs-lookup"><span data-stu-id="be030-103">The following XML file is used in various examples in the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] documentation.</span></span> <span data-ttu-id="be030-104">此文件包含数值数据，用于求和、求平均值和分组。</span><span class="sxs-lookup"><span data-stu-id="be030-104">This file contains numerical data for summing, averaging, and grouping.</span></span> <span data-ttu-id="be030-105">该 XML 在某个命名空间中。</span><span class="sxs-lookup"><span data-stu-id="be030-105">The XML is in a namespace.</span></span>  
  
## <a name="data"></a><span data-ttu-id="be030-106">数据</span><span class="sxs-lookup"><span data-stu-id="be030-106">Data</span></span>  
  
```xml  
<Root xmlns='http://www.adatum.com'>  
  <TaxRate>7.25</TaxRate>  
  <Data>  
    <Category>A</Category>  
    <Quantity>3</Quantity>  
    <Price>24.50</Price>  
  </Data>  
  <Data>  
    <Category>B</Category>  
    <Quantity>1</Quantity>  
    <Price>89.99</Price>  
  </Data>  
  <Data>  
    <Category>A</Category>  
    <Quantity>5</Quantity>  
    <Price>4.95</Price>  
  </Data>  
  <Data>  
    <Category>A</Category>  
    <Quantity>3</Quantity>  
    <Price>66.00</Price>  
  </Data>  
  <Data>  
    <Category>B</Category>  
    <Quantity>10</Quantity>  
    <Price>.99</Price>  
  </Data>  
  <Data>  
    <Category>A</Category>  
    <Quantity>15</Quantity>  
    <Price>29.00</Price>  
  </Data>  
  <Data>  
    <Category>B</Category>  
    <Quantity>8</Quantity>  
    <Price>6.99</Price>  
  </Data>  
</Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="be030-107">请参阅</span><span class="sxs-lookup"><span data-stu-id="be030-107">See Also</span></span>  
 [<span data-ttu-id="be030-108">示例 XML 文档 (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="be030-108">Sample XML Documents (LINQ to XML)</span></span>](../../../../csharp/programming-guide/concepts/linq/sample-xml-documents-linq-to-xml.md)

