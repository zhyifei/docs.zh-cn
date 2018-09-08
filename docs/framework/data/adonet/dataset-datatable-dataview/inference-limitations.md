---
title: 推断限制
ms.date: 03/30/2017
ms.assetid: 78517994-5d57-44f8-9d20-38812977de09
ms.openlocfilehash: d113df98cdd339300b3e75ceda49a56d4f346d3c
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "44137221"
---
# <a name="inference-limitations"></a><span data-ttu-id="addcf-102">推断限制</span><span class="sxs-lookup"><span data-stu-id="addcf-102">Inference Limitations</span></span>
<span data-ttu-id="addcf-103">根据每个文档中的 XML 元素，从 XML 推断 <xref:System.Data.DataSet> 架构的过程会产生不同的架构。</span><span class="sxs-lookup"><span data-stu-id="addcf-103">The process of inferring a <xref:System.Data.DataSet> schema from XML can result in different schemas depending on the XML elements in each document.</span></span> <span data-ttu-id="addcf-104">例如，考虑以下 XML 文档。</span><span class="sxs-lookup"><span data-stu-id="addcf-104">For example, consider the following XML documents.</span></span>  
  
 <span data-ttu-id="addcf-105">Document1：</span><span class="sxs-lookup"><span data-stu-id="addcf-105">Document1:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>Text1</Element1>  
  <Element1>Text2</Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="addcf-106">Document2：</span><span class="sxs-lookup"><span data-stu-id="addcf-106">Document2:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>Text1</Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="addcf-107">对于"Document1"，推断过程将生成**数据集**名为"DocumentElement"和名为"Element1"的表，由于"Element1"是重复元素。</span><span class="sxs-lookup"><span data-stu-id="addcf-107">For "Document1," the inference process produces a **DataSet** named "DocumentElement" and a table named "Element1," because "Element1" is a repeating element.</span></span>  
  
 <span data-ttu-id="addcf-108">**数据集：** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="addcf-108">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="addcf-109">**表：** Element1</span><span class="sxs-lookup"><span data-stu-id="addcf-109">**Table:** Element1</span></span>  
  
|<span data-ttu-id="addcf-110">Element1_Text</span><span class="sxs-lookup"><span data-stu-id="addcf-110">Element1_Text</span></span>|  
|--------------------|  
|<span data-ttu-id="addcf-111">Text1</span><span class="sxs-lookup"><span data-stu-id="addcf-111">Text1</span></span>|  
|<span data-ttu-id="addcf-112">Text2</span><span class="sxs-lookup"><span data-stu-id="addcf-112">Text2</span></span>|  
  
 <span data-ttu-id="addcf-113">但是，对于"Document2"推断过程将生成**数据集**名为"NewDataSet"和表名为"DocumentElement"。</span><span class="sxs-lookup"><span data-stu-id="addcf-113">However, for "Document2," the inference process produces a **DataSet** named "NewDataSet" and a table named "DocumentElement."</span></span> <span data-ttu-id="addcf-114">由于“Element1”不具有属性和子元素，它将被推断为列。</span><span class="sxs-lookup"><span data-stu-id="addcf-114">"Element1" is inferred as a column because it has no attributes and no child elements.</span></span>  
  
 <span data-ttu-id="addcf-115">**数据集：** NewDataSet</span><span class="sxs-lookup"><span data-stu-id="addcf-115">**DataSet:** NewDataSet</span></span>  
  
 <span data-ttu-id="addcf-116">**表：** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="addcf-116">**Table:** DocumentElement</span></span>  
  
|<span data-ttu-id="addcf-117">Element1</span><span class="sxs-lookup"><span data-stu-id="addcf-117">Element1</span></span>|  
|--------------|  
|<span data-ttu-id="addcf-118">Text1</span><span class="sxs-lookup"><span data-stu-id="addcf-118">Text1</span></span>|  
  
 <span data-ttu-id="addcf-119">这两个 XML 文档可能本应生成相同的架构，但根据每个文档中包含的不同元素，推断过程生成了极不相同的结果。</span><span class="sxs-lookup"><span data-stu-id="addcf-119">These two XML documents may have been intended to produce the same schema, but the inference process produces very different results based on the elements contained in each document.</span></span>  
  
 <span data-ttu-id="addcf-120">若要避免从 XML 文档生成架构时可能出现的差异，我们建议您显式指定在加载时使用 XML 架构定义语言 (XSD) 或 XML 数据缩减 (XDR) 架构**数据集**从XML。</span><span class="sxs-lookup"><span data-stu-id="addcf-120">To avoid the discrepancies that can occur when generating schema from an XML document, we recommend that you explicitly specify a schema using XML Schema definition language (XSD) or XML-Data Reduced (XDR) when loading a **DataSet** from XML.</span></span> <span data-ttu-id="addcf-121">有关详细信息，有关显式指定**数据集**架构和 XML 架构，请参阅[派生数据集关系结构从 XML 架构 (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md)。</span><span class="sxs-lookup"><span data-stu-id="addcf-121">For more information about explicitly specifying a **DataSet** schema with XML Schema, see [Deriving DataSet Relational Structure from XML Schema (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="addcf-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="addcf-122">See Also</span></span>  
 [<span data-ttu-id="addcf-123">从 XML 推断数据集关系结构</span><span class="sxs-lookup"><span data-stu-id="addcf-123">Inferring DataSet Relational Structure from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)  
 [<span data-ttu-id="addcf-124">从 XML 加载数据集</span><span class="sxs-lookup"><span data-stu-id="addcf-124">Loading a DataSet from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)  
 [<span data-ttu-id="addcf-125">从 XML 加载数据集构架信息</span><span class="sxs-lookup"><span data-stu-id="addcf-125">Loading DataSet Schema Information from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)  
 [<span data-ttu-id="addcf-126">在数据集中使用 XML</span><span class="sxs-lookup"><span data-stu-id="addcf-126">Using XML in a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 [<span data-ttu-id="addcf-127">数据集、数据表和数据视图</span><span class="sxs-lookup"><span data-stu-id="addcf-127">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [<span data-ttu-id="addcf-128">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="addcf-128">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
