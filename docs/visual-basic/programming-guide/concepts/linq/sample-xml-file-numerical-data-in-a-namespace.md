---
title: 示例 XML 文件：Namespace1 中的数值数据
ms.date: 07/20/2015
ms.assetid: f01cc0a1-fb55-4b42-8380-16f4be47d6f4
ms.openlocfilehash: 09954798615954d238273b3d4ed71b5ff475394f
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2019
ms.locfileid: "58816195"
---
# <a name="sample-xml-file-numerical-data-in-a-namespace"></a><span data-ttu-id="66e55-102">示例 XML 文件：命名空间中的数值数据</span><span class="sxs-lookup"><span data-stu-id="66e55-102">Sample XML File: Numerical Data in a Namespace</span></span>
<span data-ttu-id="66e55-103">下面的 XML 文件用在 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 文档的很多示例中。</span><span class="sxs-lookup"><span data-stu-id="66e55-103">The following XML file is used in various examples in the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] documentation.</span></span> <span data-ttu-id="66e55-104">此文件包含数值数据，用于求和、求平均值和分组。</span><span class="sxs-lookup"><span data-stu-id="66e55-104">This file contains numerical data for summing, averaging, and grouping.</span></span> <span data-ttu-id="66e55-105">该 XML 在某个命名空间中。</span><span class="sxs-lookup"><span data-stu-id="66e55-105">The XML is in a namespace.</span></span>  
  
## <a name="data"></a><span data-ttu-id="66e55-106">数据</span><span class="sxs-lookup"><span data-stu-id="66e55-106">Data</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="66e55-107">请参阅</span><span class="sxs-lookup"><span data-stu-id="66e55-107">See also</span></span>

- [<span data-ttu-id="66e55-108">示例 XML 文档 (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="66e55-108">Sample XML Documents (LINQ to XML)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-documents-linq-to-xml.md)
