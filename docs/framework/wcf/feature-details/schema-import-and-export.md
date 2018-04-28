---
title: 架构导入和导出
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, schema import and export
- XsdDataContractExporter class
- XsdDataContractImporter class
ms.assetid: 0da32b50-ccd9-463a-844c-7fe803d3bf44
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 8489c0bf20d3d62501db269c5a72de657bcbbc97
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2018
---
# <a name="schema-import-and-export"></a><span data-ttu-id="1f91e-102">架构导入和导出</span><span class="sxs-lookup"><span data-stu-id="1f91e-102">Schema Import and Export</span></span>
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]<span data-ttu-id="1f91e-103"> 包括新序列化引擎 <xref:System.Runtime.Serialization.DataContractSerializer>。</span><span class="sxs-lookup"><span data-stu-id="1f91e-103"> includes a new serialization engine, the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span> <span data-ttu-id="1f91e-104">`DataContractSerializer` 在 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 对象和 XML 之间进行转换（双向）。</span><span class="sxs-lookup"><span data-stu-id="1f91e-104">The `DataContractSerializer` translates between [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] objects and XML (in both directions).</span></span> <span data-ttu-id="1f91e-105">除了序列化程序本身，[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 还包括关联的架构导入和架构导出机制。</span><span class="sxs-lookup"><span data-stu-id="1f91e-105">In addition to the serializer itself, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] includes associated schema import and schema export mechanisms.</span></span> <span data-ttu-id="1f91e-106">*架构*是序列化程序生成或反序列化程序可以访问的 XML 的形状的正式、 精确和计算机可读说明。</span><span class="sxs-lookup"><span data-stu-id="1f91e-106">*Schema* is a formal, precise, and machine-readable description of the shape of XML that the serializer produces or that the deserializer can access.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="1f91e-107"> 使用万维网联合会 (W3C) XML 架构定义语言 (XSD) 作为其架构表示形式，它可以与许多第三方平台广泛互操作。</span><span class="sxs-lookup"><span data-stu-id="1f91e-107"> uses the World Wide Web Consortium (W3C) XML Schema definition language (XSD) as its schema representation, which is widely interoperable with numerous third-party platforms.</span></span>  
  
 <span data-ttu-id="1f91e-108">架构导入组件 <xref:System.Runtime.Serialization.XsdDataContractImporter> 使用 XSD 架构文档并生成 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 类（通常为数据协定类），使序列化格式对应于给定架构。</span><span class="sxs-lookup"><span data-stu-id="1f91e-108">The schema import component, <xref:System.Runtime.Serialization.XsdDataContractImporter>, takes an XSD schema document and generates [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] classes (normally data contract classes) such that the serialized forms correspond to the given schema.</span></span>  
  
 <span data-ttu-id="1f91e-109">例如，以下架构片段：</span><span class="sxs-lookup"><span data-stu-id="1f91e-109">For example, the following schema fragment:</span></span>  
  
 [!code-csharp[c_SchemaImportExport#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_schemaimportexport/cs/source.cs#8)]
 [!code-vb[c_SchemaImportExport#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_schemaimportexport/vb/source.vb#8)]  
  
 <span data-ttu-id="1f91e-110">生成以下类型（略经简化以便于阅读）。</span><span class="sxs-lookup"><span data-stu-id="1f91e-110">generates the following type (simplified slightly for better readability).</span></span>  
  
 [!code-csharp[c_SchemaImportExport#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_schemaimportexport/cs/source.cs#1)]
 [!code-vb[c_SchemaImportExport#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_schemaimportexport/vb/source.vb#1)]  
  
 <span data-ttu-id="1f91e-111">请注意，生成的类型遵循多种数据协定最佳做法 (位于[最佳做法： 数据协定版本管理](../../../../docs/framework/wcf/best-practices-data-contract-versioning.md)):</span><span class="sxs-lookup"><span data-stu-id="1f91e-111">Note that the generated type follows several data contract best practices (found in [Best Practices: Data Contract Versioning](../../../../docs/framework/wcf/best-practices-data-contract-versioning.md)):</span></span>  
  
-   <span data-ttu-id="1f91e-112">此类型实现 <xref:System.Runtime.Serialization.IExtensibleDataObject> 接口。</span><span class="sxs-lookup"><span data-stu-id="1f91e-112">The type implements the <xref:System.Runtime.Serialization.IExtensibleDataObject> interface.</span></span> <span data-ttu-id="1f91e-113">有关详细信息，请参阅[向前兼容的数据协定](../../../../docs/framework/wcf/feature-details/forward-compatible-data-contracts.md)。</span><span class="sxs-lookup"><span data-stu-id="1f91e-113">For more information, see [Forward-Compatible Data Contracts](../../../../docs/framework/wcf/feature-details/forward-compatible-data-contracts.md).</span></span>  
  
-   <span data-ttu-id="1f91e-114">数据成员作为封装私有字段的公共属性来实现。</span><span class="sxs-lookup"><span data-stu-id="1f91e-114">Data members are implemented as public properties that wrap private fields.</span></span>  
  
-   <span data-ttu-id="1f91e-115">此类是一个分部类，不修改生成的代码就可以添加内容。</span><span class="sxs-lookup"><span data-stu-id="1f91e-115">The class is a partial class, and additions can be made without modifying generated code.</span></span>  
  
 <span data-ttu-id="1f91e-116"><xref:System.Runtime.Serialization.XsdDataContractExporter> 使您能够进行反向操作，使用可用 `DataContractSerializer` 进行序列化的类型并生成 XSD 架构文档。</span><span class="sxs-lookup"><span data-stu-id="1f91e-116">The <xref:System.Runtime.Serialization.XsdDataContractExporter> enables you to do the reverse—take types that are serializable with the `DataContractSerializer` and generate an XSD Schema document.</span></span>  
  
## <a name="fidelity-is-not-guaranteed"></a><span data-ttu-id="1f91e-117">不保证保真</span><span class="sxs-lookup"><span data-stu-id="1f91e-117">Fidelity Is Not Guaranteed</span></span>  
 <span data-ttu-id="1f91e-118">不保证进行往返行程的架构或类型完全保真。</span><span class="sxs-lookup"><span data-stu-id="1f91e-118">It is not guaranteed that schema or types make a round trip with total fidelity.</span></span> <span data-ttu-id="1f91e-119">(A*往返*意味着若要导入架构以创建一组类，并导出结果以重新创建架构。)可能不会返回相同的架构。</span><span class="sxs-lookup"><span data-stu-id="1f91e-119">(A *round trip* means to import a schema to create a set of classes, and export the result to create a schema again.) The same schema may not be returned.</span></span> <span data-ttu-id="1f91e-120">反向过程也不保证保真。</span><span class="sxs-lookup"><span data-stu-id="1f91e-120">Reversing the process is also not guaranteed to preserve fidelity.</span></span> <span data-ttu-id="1f91e-121">（导出类型以生成其架构，然后重新导入此类型。</span><span class="sxs-lookup"><span data-stu-id="1f91e-121">(Export a type to generate its schema, and then import the type back.</span></span> <span data-ttu-id="1f91e-122">不太可能返回相同的类型。）</span><span class="sxs-lookup"><span data-stu-id="1f91e-122">It is unlikely the same type is returned.)</span></span>  
  
## <a name="supported-types"></a><span data-ttu-id="1f91e-123">支持的类型</span><span class="sxs-lookup"><span data-stu-id="1f91e-123">Supported Types</span></span>  
 <span data-ttu-id="1f91e-124">数据协定模型只支持有限的 WC3 架构子集。</span><span class="sxs-lookup"><span data-stu-id="1f91e-124">The data contract model supports only a limited subset of the WC3 schema.</span></span> <span data-ttu-id="1f91e-125">导入过程中任何不符合此子集的架构都将导致异常。</span><span class="sxs-lookup"><span data-stu-id="1f91e-125">Any schema that does not conform to this subset will cause an exception during the import process.</span></span> <span data-ttu-id="1f91e-126">例如，没有办法可以指定数据协定的数据成员应该作为 XML 属性进行序列化。</span><span class="sxs-lookup"><span data-stu-id="1f91e-126">For example, there is no way to specify that a data member of a data contract should be serialized as an XML attribute.</span></span> <span data-ttu-id="1f91e-127">这样，由于不能用正确的 XML 投影生成数据协定，需要使用 XML 属性的架构将不受支持，并且将在导入过程中导致异常。</span><span class="sxs-lookup"><span data-stu-id="1f91e-127">Thus, schemas that require the use of XML attributes are not supported and will cause exceptions during import, because it is impossible to generate a data contract with the correct XML projection.</span></span>  
  
 <span data-ttu-id="1f91e-128">例如，不能使用默认导入设置导入以下架构片段。</span><span class="sxs-lookup"><span data-stu-id="1f91e-128">For example, the following schema fragment cannot be imported using the default import settings.</span></span>  
  
 [!code-xml[c_SchemaImportExport#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_schemaimportexport/common/source.config#9)]  
  
 <span data-ttu-id="1f91e-129">有关详细信息，请参阅[数据协定架构参考](../../../../docs/framework/wcf/feature-details/data-contract-schema-reference.md)。</span><span class="sxs-lookup"><span data-stu-id="1f91e-129">For more information, see [Data Contract Schema Reference](../../../../docs/framework/wcf/feature-details/data-contract-schema-reference.md).</span></span> <span data-ttu-id="1f91e-130">如果架构不符合数据协定规则，请使用另一个序列化引擎。</span><span class="sxs-lookup"><span data-stu-id="1f91e-130">If a schema does not conform to the data contract rules, use a different serialization engine.</span></span> <span data-ttu-id="1f91e-131">例如，<xref:System.Xml.Serialization.XmlSerializer> 使用自己的独立架构导入机制。</span><span class="sxs-lookup"><span data-stu-id="1f91e-131">For example, the <xref:System.Xml.Serialization.XmlSerializer> uses its own separate schema import mechanism.</span></span> <span data-ttu-id="1f91e-132">另有一种特殊的导入模式，可在其中扩展所支持架构的范围。</span><span class="sxs-lookup"><span data-stu-id="1f91e-132">Also, there is a special import mode in which the range of supported schema is expanded.</span></span> <span data-ttu-id="1f91e-133">有关详细信息，请参阅有关生成的部分<xref:System.Xml.Serialization.IXmlSerializable>中的类型[导入架构以生成类](../../../../docs/framework/wcf/feature-details/importing-schema-to-generate-classes.md)。</span><span class="sxs-lookup"><span data-stu-id="1f91e-133">For more information, see the section about generating <xref:System.Xml.Serialization.IXmlSerializable> types in [Importing Schema to Generate Classes](../../../../docs/framework/wcf/feature-details/importing-schema-to-generate-classes.md).</span></span>  
  
 <span data-ttu-id="1f91e-134">`XsdDataContractExporter` 支持可以用 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 序列化的任何 `DataContractSerializer` 类型。</span><span class="sxs-lookup"><span data-stu-id="1f91e-134">The `XsdDataContractExporter` supports any [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] types that can be serialized with the `DataContractSerializer`.</span></span> <span data-ttu-id="1f91e-135">有关详细信息，请参阅[类型受数据协定序列化程序](../../../../docs/framework/wcf/feature-details/types-supported-by-the-data-contract-serializer.md)。</span><span class="sxs-lookup"><span data-stu-id="1f91e-135">For more information, see [Types Supported by the Data Contract Serializer](../../../../docs/framework/wcf/feature-details/types-supported-by-the-data-contract-serializer.md).</span></span> <span data-ttu-id="1f91e-136">请注意，使用 `XsdDataContractExporter` 生成的架构通常是 `XsdDataContractImporter` 可以使用的有效数据（除非 <xref:System.Xml.Serialization.XmlSchemaProviderAttribute> 用于对架构进行自定义）。</span><span class="sxs-lookup"><span data-stu-id="1f91e-136">Note that schema generated using the `XsdDataContractExporter` is normally valid data that the `XsdDataContractImporter` can use (unless the <xref:System.Xml.Serialization.XmlSchemaProviderAttribute> is used to customize the schema).</span></span>  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="1f91e-137"> 使用<xref:System.Runtime.Serialization.XsdDataContractImporter>，请参阅[导入架构以生成类](../../../../docs/framework/wcf/feature-details/importing-schema-to-generate-classes.md)。</span><span class="sxs-lookup"><span data-stu-id="1f91e-137"> using the <xref:System.Runtime.Serialization.XsdDataContractImporter>, see [Importing Schema to Generate Classes](../../../../docs/framework/wcf/feature-details/importing-schema-to-generate-classes.md).</span></span>  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="1f91e-138"> 使用<xref:System.Runtime.Serialization.XsdDataContractExporter>，请参阅[从类导出架构](../../../../docs/framework/wcf/feature-details/exporting-schemas-from-classes.md)。</span><span class="sxs-lookup"><span data-stu-id="1f91e-138"> using the <xref:System.Runtime.Serialization.XsdDataContractExporter>, see [Exporting Schemas from Classes](../../../../docs/framework/wcf/feature-details/exporting-schemas-from-classes.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f91e-139">请参阅</span><span class="sxs-lookup"><span data-stu-id="1f91e-139">See Also</span></span>  
 <xref:System.Runtime.Serialization.DataContractSerializer>  
 <xref:System.Runtime.Serialization.XsdDataContractImporter>  
 <xref:System.Runtime.Serialization.XsdDataContractExporter>  
 [<span data-ttu-id="1f91e-140">导入架构以生成类</span><span class="sxs-lookup"><span data-stu-id="1f91e-140">Importing Schema to Generate Classes</span></span>](../../../../docs/framework/wcf/feature-details/importing-schema-to-generate-classes.md)  
 [<span data-ttu-id="1f91e-141">从类导出架构</span><span class="sxs-lookup"><span data-stu-id="1f91e-141">Exporting Schemas from Classes</span></span>](../../../../docs/framework/wcf/feature-details/exporting-schemas-from-classes.md)
