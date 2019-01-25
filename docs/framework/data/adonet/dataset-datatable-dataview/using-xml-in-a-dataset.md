---
title: 在数据集中使用 XML
ms.date: 03/30/2017
ms.assetid: 35138159-e199-49ec-baf7-1ec6777e171e
ms.openlocfilehash: 245e893d052a67e79396fb3d9fc7062eea426215
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54667037"
---
# <a name="using-xml-in-a-dataset"></a><span data-ttu-id="7150e-102">在数据集中使用 XML</span><span class="sxs-lookup"><span data-stu-id="7150e-102">Using XML in a DataSet</span></span>
<span data-ttu-id="7150e-103">通过 ADO.NET，您可以从 XML 流或文档填充 <xref:System.Data.DataSet>。</span><span class="sxs-lookup"><span data-stu-id="7150e-103">With ADO.NET you can fill a <xref:System.Data.DataSet> from an XML stream or document.</span></span> <span data-ttu-id="7150e-104">可以使用 XML 流或文档向 <xref:System.Data.DataSet> 提供数据和/或架构信息。</span><span class="sxs-lookup"><span data-stu-id="7150e-104">You can use the XML stream or document to supply to the <xref:System.Data.DataSet> either data, schema information, or both.</span></span> <span data-ttu-id="7150e-105">从 XML 流或文档中提供的信息可以与已存在于 <xref:System.Data.DataSet> 中的现有数据或架构信息进行组合。</span><span class="sxs-lookup"><span data-stu-id="7150e-105">The information supplied from the XML stream or document can be combined with existing data or schema information already present in the <xref:System.Data.DataSet>.</span></span>  
  
 <span data-ttu-id="7150e-106">为了通过 HTTP 将 <xref:System.Data.DataSet> 传输给其他应用程序或启用了 XML 的平台来使用，ADO.NET 还允许您创建 <xref:System.Data.DataSet> 的 XML 表示形式（包含或不包含架构）。</span><span class="sxs-lookup"><span data-stu-id="7150e-106">ADO.NET also allows you to create an XML representation of a <xref:System.Data.DataSet>, with or without its schema, in order to transport the <xref:System.Data.DataSet> across HTTP for use by another application or XML-enabled platform.</span></span> <span data-ttu-id="7150e-107">在 <xref:System.Data.DataSet> 的 XML 表示形式中，数据以 XML 形式编写，而架构若以内联形式包含在该表示形式中时，则使用 XML 架构定义语言 (XSD) 来编写。</span><span class="sxs-lookup"><span data-stu-id="7150e-107">In an XML representation of a <xref:System.Data.DataSet>, the data is written in XML and the schema, if it is included inline in the representation, is written using the XML Schema definition language (XSD).</span></span> <span data-ttu-id="7150e-108">XML 和 XML 架构提供一种方便的格式与远程客户端之间来回传输 <xref:System.Data.DataSet> 的内容。</span><span class="sxs-lookup"><span data-stu-id="7150e-108">XML and XML Schema provide a convenient format for transferring the contents of a <xref:System.Data.DataSet> to and from remote clients.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7150e-109">本节内容</span><span class="sxs-lookup"><span data-stu-id="7150e-109">In This Section</span></span>  
 [<span data-ttu-id="7150e-110">DiffGrams</span><span class="sxs-lookup"><span data-stu-id="7150e-110">DiffGrams</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/diffgrams.md)  
 <span data-ttu-id="7150e-111">提供有关 DiffGram 的详细信息，DiffGram 是一种用于读写 <xref:System.Data.DataSet> 内容的 XML 格式。</span><span class="sxs-lookup"><span data-stu-id="7150e-111">Provides details on the DiffGram, an XML format used to read and write the contents of a <xref:System.Data.DataSet>.</span></span>  
  
 [<span data-ttu-id="7150e-112">从 XML 加载数据集</span><span class="sxs-lookup"><span data-stu-id="7150e-112">Loading a DataSet from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)  
 <span data-ttu-id="7150e-113">讨论在从 XML 文档中加载 <xref:System.Data.DataSet> 内容时需考虑的不同选项。</span><span class="sxs-lookup"><span data-stu-id="7150e-113">Discusses different options to consider when loading the contents of a <xref:System.Data.DataSet> from an XML document.</span></span>  
  
 [<span data-ttu-id="7150e-114">以 XML 数据的形式编写数据集内容</span><span class="sxs-lookup"><span data-stu-id="7150e-114">Writing DataSet Contents as XML Data</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/writing-dataset-contents-as-xml-data.md)  
 <span data-ttu-id="7150e-115">讨论如何以 XML 数据的形式生成 <xref:System.Data.DataSet> 的内容以及可使用的不同 XML 格式选项。</span><span class="sxs-lookup"><span data-stu-id="7150e-115">Discusses how to generate the contents of a <xref:System.Data.DataSet> as XML data, and the different XML format options you can use.</span></span>  
  
 [<span data-ttu-id="7150e-116">从 XML 加载数据集构架信息</span><span class="sxs-lookup"><span data-stu-id="7150e-116">Loading DataSet Schema Information from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)  
 <span data-ttu-id="7150e-117">讨论用于从 XML 中加载 <xref:System.Data.DataSet> 架构的 <xref:System.Data.DataSet> 方法。</span><span class="sxs-lookup"><span data-stu-id="7150e-117">Discusses the <xref:System.Data.DataSet> methods used to load the schema of a <xref:System.Data.DataSet> from XML.</span></span>  
  
 [<span data-ttu-id="7150e-118">以 XSD 的形式写入数据集构架信息</span><span class="sxs-lookup"><span data-stu-id="7150e-118">Writing DataSet Schema Information as XSD</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/writing-dataset-schema-information-as-xsd.md)  
 <span data-ttu-id="7150e-119">讨论 XML 架构的用途以及如何从 <xref:System.Data.DataSet> 生成 XML 架构。</span><span class="sxs-lookup"><span data-stu-id="7150e-119">Discusses the uses for an XML Schema and how to generate one from a <xref:System.Data.DataSet>.</span></span>  
  
 [<span data-ttu-id="7150e-120">数据集和 XmlDataDocument 同步</span><span class="sxs-lookup"><span data-stu-id="7150e-120">DataSet and XmlDataDocument Synchronization</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataset-and-xmldatadocument-synchronization.md)  
 <span data-ttu-id="7150e-121">讨论 .NET Framework 中提供的同步访问单个数据集的关系和分层视图的功能，并解释如何在 <xref:System.Data.DataSet> 和 <xref:System.Xml.XmlDataDocument> 之间创建同步关系。</span><span class="sxs-lookup"><span data-stu-id="7150e-121">Discusses the capability available in the .NET Framework of synchronous access to both relational and hierarchical views of a single set of data, and shows how to create a synchronous relationship between a <xref:System.Data.DataSet> and an <xref:System.Xml.XmlDataDocument>.</span></span>  
  
 [<span data-ttu-id="7150e-122">嵌套 DataRelation</span><span class="sxs-lookup"><span data-stu-id="7150e-122">Nesting DataRelations</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/nesting-datarelations.md)  
 <span data-ttu-id="7150e-123">讨论嵌套 <xref:System.Data.DataRelation> 对象在以 XML 数据形式表示 <xref:System.Data.DataSet> 内容时的重要性，并描述如何创建这些对象。</span><span class="sxs-lookup"><span data-stu-id="7150e-123">Discusses the importance of nested <xref:System.Data.DataRelation> objects when representing the contents of a <xref:System.Data.DataSet> as XML data, and describes how to create them.</span></span>  
  
 [<span data-ttu-id="7150e-124">从 XML 架构派生数据集关系结构 (XSD)</span><span class="sxs-lookup"><span data-stu-id="7150e-124">Deriving DataSet Relational Structure from XML Schema (XSD)</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md)  
 <span data-ttu-id="7150e-125">描述从 XML 架构创建的 <xref:System.Data.DataSet> 的关系结果（即架构）。</span><span class="sxs-lookup"><span data-stu-id="7150e-125">Describes the relational structure, or schema, of a <xref:System.Data.DataSet> that is created from XML Schema.</span></span>  
  
 [<span data-ttu-id="7150e-126">从 XML 推断数据集关系结构</span><span class="sxs-lookup"><span data-stu-id="7150e-126">Inferring DataSet Relational Structure from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)  
 <span data-ttu-id="7150e-127">描述在从 XML 元素进行推断时所创建的 <xref:System.Data.DataSet> 的结果关系结构（即架构）。</span><span class="sxs-lookup"><span data-stu-id="7150e-127">Describes the resulting relational structure, or schema, of a <xref:System.Data.DataSet> that is created when inferred from XML elements.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="7150e-128">相关章节</span><span class="sxs-lookup"><span data-stu-id="7150e-128">Related Sections</span></span>  
 [<span data-ttu-id="7150e-129">ADO.NET 概述</span><span class="sxs-lookup"><span data-stu-id="7150e-129">ADO.NET Overview</span></span>](../../../../../docs/framework/data/adonet/ado-net-overview.md)  
 <span data-ttu-id="7150e-130">描述 ADO.NET 结构和组件，并说明如何使用它们来访问现有的数据源和管理应用程序数据。</span><span class="sxs-lookup"><span data-stu-id="7150e-130">Describes the ADO.NET architecture and components, and how to use them to access existing data sources as well as to manage application data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7150e-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="7150e-131">See also</span></span>
- [<span data-ttu-id="7150e-132">数据集、数据表和数据视图</span><span class="sxs-lookup"><span data-stu-id="7150e-132">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)
- [<span data-ttu-id="7150e-133">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="7150e-133">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
