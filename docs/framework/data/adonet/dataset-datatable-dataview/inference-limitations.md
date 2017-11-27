---
title: "推断限制"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 78517994-5d57-44f8-9d20-38812977de09
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 98ea3d5fa4427b391ef06b3fc6ace9a05dfb819a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="inference-limitations"></a><span data-ttu-id="30a4d-102">推断限制</span><span class="sxs-lookup"><span data-stu-id="30a4d-102">Inference Limitations</span></span>
<span data-ttu-id="30a4d-103">根据每个文档中的 XML 元素，从 XML 推断 <xref:System.Data.DataSet> 架构的过程会产生不同的架构。</span><span class="sxs-lookup"><span data-stu-id="30a4d-103">The process of inferring a <xref:System.Data.DataSet> schema from XML can result in different schemas depending on the XML elements in each document.</span></span> <span data-ttu-id="30a4d-104">例如，考虑以下 XML 文档。</span><span class="sxs-lookup"><span data-stu-id="30a4d-104">For example, consider the following XML documents.</span></span>  
  
 <span data-ttu-id="30a4d-105">Document1：</span><span class="sxs-lookup"><span data-stu-id="30a4d-105">Document1:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>Text1</Element1>  
  <Element1>Text2</Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="30a4d-106">Document2：</span><span class="sxs-lookup"><span data-stu-id="30a4d-106">Document2:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>Text1</Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="30a4d-107">对于"Document1"，推断过程将生成**数据集**命名为"DocumentElement"和名为"Element1"的表，因为"Element1"是重复的元素。</span><span class="sxs-lookup"><span data-stu-id="30a4d-107">For "Document1," the inference process produces a **DataSet** named "DocumentElement" and a table named "Element1," because "Element1" is a repeating element.</span></span>  
  
 <span data-ttu-id="30a4d-108">**数据集：** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="30a4d-108">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="30a4d-109">**表：** Element1</span><span class="sxs-lookup"><span data-stu-id="30a4d-109">**Table:** Element1</span></span>  
  
|<span data-ttu-id="30a4d-110">Element1_Text</span><span class="sxs-lookup"><span data-stu-id="30a4d-110">Element1_Text</span></span>|  
|--------------------|  
|<span data-ttu-id="30a4d-111">Text1</span><span class="sxs-lookup"><span data-stu-id="30a4d-111">Text1</span></span>|  
|<span data-ttu-id="30a4d-112">Text2</span><span class="sxs-lookup"><span data-stu-id="30a4d-112">Text2</span></span>|  
  
 <span data-ttu-id="30a4d-113">但是，对于"Document2，"推断过程产生**数据集**名为"NewDataSet"和名为"DocumentElement。"的表</span><span class="sxs-lookup"><span data-stu-id="30a4d-113">However, for "Document2," the inference process produces a **DataSet** named "NewDataSet" and a table named "DocumentElement."</span></span> <span data-ttu-id="30a4d-114">由于“Element1”不具有属性和子元素，它将被推断为列。</span><span class="sxs-lookup"><span data-stu-id="30a4d-114">"Element1" is inferred as a column because it has no attributes and no child elements.</span></span>  
  
 <span data-ttu-id="30a4d-115">**数据集：** NewDataSet</span><span class="sxs-lookup"><span data-stu-id="30a4d-115">**DataSet:** NewDataSet</span></span>  
  
 <span data-ttu-id="30a4d-116">**表：** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="30a4d-116">**Table:** DocumentElement</span></span>  
  
|<span data-ttu-id="30a4d-117">Element1</span><span class="sxs-lookup"><span data-stu-id="30a4d-117">Element1</span></span>|  
|--------------|  
|<span data-ttu-id="30a4d-118">Text1</span><span class="sxs-lookup"><span data-stu-id="30a4d-118">Text1</span></span>|  
  
 <span data-ttu-id="30a4d-119">这两个 XML 文档可能本应生成相同的架构，但根据每个文档中包含的不同元素，推断过程生成了极不相同的结果。</span><span class="sxs-lookup"><span data-stu-id="30a4d-119">These two XML documents may have been intended to produce the same schema, but the inference process produces very different results based on the elements contained in each document.</span></span>  
  
 <span data-ttu-id="30a4d-120">若要避免的差异，从 XML 文档生成架构时可能发生，我们建议您显式指定在加载时使用 XML 架构定义语言 (XSD) 或 XML 数据简化 (XDR) 架构**数据集**从XML。</span><span class="sxs-lookup"><span data-stu-id="30a4d-120">To avoid the discrepancies that can occur when generating schema from an XML document, we recommend that you explicitly specify a schema using XML Schema definition language (XSD) or XML-Data Reduced (XDR) when loading a **DataSet** from XML.</span></span> <span data-ttu-id="30a4d-121">有关显式指定的详细信息**数据集**架构和 XML 架构，请参阅[派生数据集关系结构从 XML 架构 (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md)。</span><span class="sxs-lookup"><span data-stu-id="30a4d-121">For more information about explicitly specifying a **DataSet** schema with XML Schema, see [Deriving DataSet Relational Structure from XML Schema (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30a4d-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="30a4d-122">See Also</span></span>  
 [<span data-ttu-id="30a4d-123">从 XML 推断数据集关系结构</span><span class="sxs-lookup"><span data-stu-id="30a4d-123">Inferring DataSet Relational Structure from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)  
 [<span data-ttu-id="30a4d-124">从 XML 加载数据集</span><span class="sxs-lookup"><span data-stu-id="30a4d-124">Loading a DataSet from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)  
 [<span data-ttu-id="30a4d-125">从 XML 加载数据集架构信息</span><span class="sxs-lookup"><span data-stu-id="30a4d-125">Loading DataSet Schema Information from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)  
 [<span data-ttu-id="30a4d-126">在数据集中使用 XML</span><span class="sxs-lookup"><span data-stu-id="30a4d-126">Using XML in a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 [<span data-ttu-id="30a4d-127">数据集、数据表和数据视图</span><span class="sxs-lookup"><span data-stu-id="30a4d-127">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [<span data-ttu-id="30a4d-128">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="30a4d-128">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
