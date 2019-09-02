---
title: 推断限制
ms.date: 03/30/2017
ms.assetid: 78517994-5d57-44f8-9d20-38812977de09
ms.openlocfilehash: 4e0f63776162b60c9333ba47be58ea78a9b6805d
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/31/2019
ms.locfileid: "70204830"
---
# <a name="inference-limitations"></a><span data-ttu-id="3d61c-102">推断限制</span><span class="sxs-lookup"><span data-stu-id="3d61c-102">Inference Limitations</span></span>
<span data-ttu-id="3d61c-103">根据每个文档中的 XML 元素，从 XML 推断 <xref:System.Data.DataSet> 架构的过程会产生不同的架构。</span><span class="sxs-lookup"><span data-stu-id="3d61c-103">The process of inferring a <xref:System.Data.DataSet> schema from XML can result in different schemas depending on the XML elements in each document.</span></span> <span data-ttu-id="3d61c-104">例如，考虑以下 XML 文档。</span><span class="sxs-lookup"><span data-stu-id="3d61c-104">For example, consider the following XML documents.</span></span>  
  
 <span data-ttu-id="3d61c-105">Document1：</span><span class="sxs-lookup"><span data-stu-id="3d61c-105">Document1:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>Text1</Element1>  
  <Element1>Text2</Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="3d61c-106">Document2：</span><span class="sxs-lookup"><span data-stu-id="3d61c-106">Document2:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>Text1</Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="3d61c-107">对于 "Document1", 推理过程将生成一个名为 "DocumentElement" 的**数据集**和一个名为 "Element1" 的表, 因为 "Element1" 是重复元素。</span><span class="sxs-lookup"><span data-stu-id="3d61c-107">For "Document1," the inference process produces a **DataSet** named "DocumentElement" and a table named "Element1," because "Element1" is a repeating element.</span></span>  
  
 <span data-ttu-id="3d61c-108">**集会**DocumentElement</span><span class="sxs-lookup"><span data-stu-id="3d61c-108">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="3d61c-109">**数据表**Element1</span><span class="sxs-lookup"><span data-stu-id="3d61c-109">**Table:** Element1</span></span>  
  
|<span data-ttu-id="3d61c-110">Element1_Text</span><span class="sxs-lookup"><span data-stu-id="3d61c-110">Element1_Text</span></span>|  
|--------------------|  
|<span data-ttu-id="3d61c-111">Text1</span><span class="sxs-lookup"><span data-stu-id="3d61c-111">Text1</span></span>|  
|<span data-ttu-id="3d61c-112">Text2</span><span class="sxs-lookup"><span data-stu-id="3d61c-112">Text2</span></span>|  
  
 <span data-ttu-id="3d61c-113">但是, 对于 "Document2", 推理过程将生成一个名为 "NewDataSet" 的**数据集**和一个名为 "DocumentElement" 的表。</span><span class="sxs-lookup"><span data-stu-id="3d61c-113">However, for "Document2," the inference process produces a **DataSet** named "NewDataSet" and a table named "DocumentElement."</span></span> <span data-ttu-id="3d61c-114">由于“Element1”不具有属性和子元素，它将被推断为列。</span><span class="sxs-lookup"><span data-stu-id="3d61c-114">"Element1" is inferred as a column because it has no attributes and no child elements.</span></span>  
  
 <span data-ttu-id="3d61c-115">**集会**NewDataSet</span><span class="sxs-lookup"><span data-stu-id="3d61c-115">**DataSet:** NewDataSet</span></span>  
  
 <span data-ttu-id="3d61c-116">**数据表**DocumentElement</span><span class="sxs-lookup"><span data-stu-id="3d61c-116">**Table:** DocumentElement</span></span>  
  
|<span data-ttu-id="3d61c-117">Element1</span><span class="sxs-lookup"><span data-stu-id="3d61c-117">Element1</span></span>|  
|--------------|  
|<span data-ttu-id="3d61c-118">Text1</span><span class="sxs-lookup"><span data-stu-id="3d61c-118">Text1</span></span>|  
  
 <span data-ttu-id="3d61c-119">这两个 XML 文档可能本应生成相同的架构，但根据每个文档中包含的不同元素，推断过程生成了极不相同的结果。</span><span class="sxs-lookup"><span data-stu-id="3d61c-119">These two XML documents may have been intended to produce the same schema, but the inference process produces very different results based on the elements contained in each document.</span></span>  
  
 <span data-ttu-id="3d61c-120">为了避免在从 XML 文档生成架构时可能出现的差异, 我们建议您在从 XML 加载**数据集**时使用 xml 架构定义语言 (XSD) 或 Xml 数据缩减 (XDR) 显式指定架构。</span><span class="sxs-lookup"><span data-stu-id="3d61c-120">To avoid the discrepancies that can occur when generating schema from an XML document, we recommend that you explicitly specify a schema using XML Schema definition language (XSD) or XML-Data Reduced (XDR) when loading a **DataSet** from XML.</span></span> <span data-ttu-id="3d61c-121">有关使用 XML 架构显式指定**数据集**架构的详细信息, 请参阅[从 Xml 架构派生数据集关系结构 (XSD)](deriving-dataset-relational-structure-from-xml-schema-xsd.md)。</span><span class="sxs-lookup"><span data-stu-id="3d61c-121">For more information about explicitly specifying a **DataSet** schema with XML Schema, see [Deriving DataSet Relational Structure from XML Schema (XSD)](deriving-dataset-relational-structure-from-xml-schema-xsd.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d61c-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="3d61c-122">See also</span></span>

- [<span data-ttu-id="3d61c-123">从 XML 推断数据集关系结构</span><span class="sxs-lookup"><span data-stu-id="3d61c-123">Inferring DataSet Relational Structure from XML</span></span>](inferring-dataset-relational-structure-from-xml.md)
- [<span data-ttu-id="3d61c-124">从 XML 加载数据集</span><span class="sxs-lookup"><span data-stu-id="3d61c-124">Loading a DataSet from XML</span></span>](loading-a-dataset-from-xml.md)
- [<span data-ttu-id="3d61c-125">从 XML 加载数据集构架信息</span><span class="sxs-lookup"><span data-stu-id="3d61c-125">Loading DataSet Schema Information from XML</span></span>](loading-dataset-schema-information-from-xml.md)
- [<span data-ttu-id="3d61c-126">在数据集中使用 XML</span><span class="sxs-lookup"><span data-stu-id="3d61c-126">Using XML in a DataSet</span></span>](using-xml-in-a-dataset.md)
- [<span data-ttu-id="3d61c-127">数据集、数据表和数据视图</span><span class="sxs-lookup"><span data-stu-id="3d61c-127">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="3d61c-128">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="3d61c-128">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
