---
title: '&lt;wsdlImporter&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 986b2165-8430-4dba-b1b8-00396841bb96
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: fc85c93dc73918d661195e33ce5094622db36af4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ltwsdlimportergt"></a><span data-ttu-id="b9637-102">&lt;wsdlImporter&gt;</span><span class="sxs-lookup"><span data-stu-id="b9637-102">&lt;wsdlImporter&gt;</span></span>
<span data-ttu-id="b9637-103">指定可导入带有 WS-Policy 附件的 Web 服务描述语言 (WSDL) 1.1 元数据的所有 WSDL 导入程序。</span><span class="sxs-lookup"><span data-stu-id="b9637-103">Specifies all the WSDL importers that imports Web Services Description Language (WSDL) 1.1 metadata with WS-Policy attachments.</span></span>  
  
<span data-ttu-id="b9637-104">\<系统。ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="b9637-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="b9637-105">\<客户端 ></span><span class="sxs-lookup"><span data-stu-id="b9637-105">\<client></span></span>  
<span data-ttu-id="b9637-106">\<元数据 ></span><span class="sxs-lookup"><span data-stu-id="b9637-106">\<metadata></span></span>  
<span data-ttu-id="b9637-107">\<wsdlImporters ></span><span class="sxs-lookup"><span data-stu-id="b9637-107">\<wsdlImporters></span></span>  
<span data-ttu-id="b9637-108">\<wsdlImporter ></span><span class="sxs-lookup"><span data-stu-id="b9637-108">\<wsdlImporter></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9637-109">语法</span><span class="sxs-lookup"><span data-stu-id="b9637-109">Syntax</span></span>  
  
```xml  
<metadata>  
  <wsdlImporters>  
    <wsdlImporter type="string" />  
  </wsdlImporters>  
</metadata>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b9637-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="b9637-110">Attributes and Elements</span></span>  
 <span data-ttu-id="b9637-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="b9637-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b9637-112">特性</span><span class="sxs-lookup"><span data-stu-id="b9637-112">Attributes</span></span>  
  
|<span data-ttu-id="b9637-113">特性</span><span class="sxs-lookup"><span data-stu-id="b9637-113">Attribute</span></span>|<span data-ttu-id="b9637-114">描述</span><span class="sxs-lookup"><span data-stu-id="b9637-114">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="b9637-115">此元素的类型。</span><span class="sxs-lookup"><span data-stu-id="b9637-115">The type of this element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b9637-116">子元素</span><span class="sxs-lookup"><span data-stu-id="b9637-116">Child Elements</span></span>  
 <span data-ttu-id="b9637-117">无。</span><span class="sxs-lookup"><span data-stu-id="b9637-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b9637-118">父元素</span><span class="sxs-lookup"><span data-stu-id="b9637-118">Parent Elements</span></span>  
  
|<span data-ttu-id="b9637-119">元素</span><span class="sxs-lookup"><span data-stu-id="b9637-119">Element</span></span>|<span data-ttu-id="b9637-120">描述</span><span class="sxs-lookup"><span data-stu-id="b9637-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b9637-121">\<wsdlImporters ></span><span class="sxs-lookup"><span data-stu-id="b9637-121">\<wsdlImporters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdlimporters.md)|<span data-ttu-id="b9637-122">指定可导入带有 WS-Policy 附件的 Web 服务描述语言 (WSDL) 1.1 元数据的所有 WSDL 导入程序。</span><span class="sxs-lookup"><span data-stu-id="b9637-122">Specifies all the WSDL importers that imports Web Services Description Language (WSDL) 1.1 metadata with WS-Policy attachments.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b9637-123">备注</span><span class="sxs-lookup"><span data-stu-id="b9637-123">Remarks</span></span>  
 <span data-ttu-id="b9637-124">WSDL 导入程序可用于导入元数据并将这些信息转换为各种表示协定和终结点信息的类。</span><span class="sxs-lookup"><span data-stu-id="b9637-124">A WSDL importer is used to import metadata as well as convert that information into various classes that represent contract and endpoint information.</span></span> <span data-ttu-id="b9637-125">它可以有选择地导入协定和终结点信息以及公开任何导入错误的属性，并接受与导入和转换过程相关的类型信息。</span><span class="sxs-lookup"><span data-stu-id="b9637-125">It can selectively import contract and endpoint information and properties that expose any import errors and accept type information relevant to the import and conversion process.</span></span> <span data-ttu-id="b9637-126">它还支持导入某些绑定信息和属性，这些信息和属性提供了对任何策略文档、WSDL 文档、WSDL 扩展和 XML 架构文档的访问。</span><span class="sxs-lookup"><span data-stu-id="b9637-126">It also supports importing binding information and properties that provide access to any policy documents, WSDL documents, WSDL extensions, and XML schema documents.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9637-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="b9637-127">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.WsdlImporterElement>  
 <xref:System.ServiceModel.Configuration.MetadataElement>  
 <xref:System.ServiceModel.Configuration.WsdlImporterElementCollection>  
 <xref:System.ServiceModel.Description.MetadataImporter>  
 <xref:System.ServiceModel.Description.WsdlImporter>  
 [<span data-ttu-id="b9637-128">WCF 客户端配置</span><span class="sxs-lookup"><span data-stu-id="b9637-128">WCF Client Configuration</span></span>](../../../../../docs/framework/wcf/feature-details/client-configuration.md)  
 [<span data-ttu-id="b9637-129">客户端</span><span class="sxs-lookup"><span data-stu-id="b9637-129">Clients</span></span>](../../../../../docs/framework/wcf/feature-details/clients.md)
