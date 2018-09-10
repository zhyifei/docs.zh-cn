---
title: 示例 XML 文件：典型采购订单 (LINQ to XML)
ms.date: 07/20/2015
ms.assetid: dcbfb859-24fc-4758-b01c-51d1b6f644e6
ms.openlocfilehash: 1e4554799937861ac28166247f94c5309b773ab4
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43526773"
---
# <a name="sample-xml-file-typical-purchase-order-linq-to-xml"></a><span data-ttu-id="3b859-102">示例 XML 文件：典型采购订单 (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="3b859-102">Sample XML File: Typical Purchase Order (LINQ to XML)</span></span>
<span data-ttu-id="3b859-103">下面的 XML 文件用在 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 文档的很多示例中。</span><span class="sxs-lookup"><span data-stu-id="3b859-103">The following XML file is used in various examples in the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] documentation.</span></span> <span data-ttu-id="3b859-104">此文件是典型的采购单。</span><span class="sxs-lookup"><span data-stu-id="3b859-104">This file is a typical purchase order.</span></span>  
  
## <a name="purchaseorderxml"></a><span data-ttu-id="3b859-105">PurchaseOrder.xml</span><span class="sxs-lookup"><span data-stu-id="3b859-105">PurchaseOrder.xml</span></span>  
  
```xml  
<?xml version="1.0"?>  
<PurchaseOrder PurchaseOrderNumber="99503" OrderDate="1999-10-20">  
  <Address Type="Shipping">  
    <Name>Ellen Adams</Name>  
    <Street>123 Maple Street</Street>  
    <City>Mill Valley</City>  
    <State>CA</State>  
    <Zip>10999</Zip>  
    <Country>USA</Country>  
  </Address>  
  <Address Type="Billing">  
    <Name>Tai Yee</Name>  
    <Street>8 Oak Avenue</Street>  
    <City>Old Town</City>  
    <State>PA</State>  
    <Zip>95819</Zip>  
    <Country>USA</Country>  
  </Address>  
  <DeliveryNotes>Please leave packages in shed by driveway.</DeliveryNotes>  
  <Items>  
    <Item PartNumber="872-AA">  
      <ProductName>Lawnmower</ProductName>  
      <Quantity>1</Quantity>  
      <USPrice>148.95</USPrice>  
      <Comment>Confirm this is electric</Comment>  
    </Item>  
    <Item PartNumber="926-AA">  
      <ProductName>Baby Monitor</ProductName>  
      <Quantity>2</Quantity>  
      <USPrice>39.98</USPrice>  
      <ShipDate>1999-05-21</ShipDate>  
    </Item>  
  </Items>  
</PurchaseOrder>  
```  
  
## <a name="see-also"></a><span data-ttu-id="3b859-106">请参阅</span><span class="sxs-lookup"><span data-stu-id="3b859-106">See Also</span></span>

- [<span data-ttu-id="3b859-107">示例 XML 文档 (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="3b859-107">Sample XML Documents (LINQ to XML)</span></span>](../../../../csharp/programming-guide/concepts/linq/sample-xml-documents-linq-to-xml.md)
