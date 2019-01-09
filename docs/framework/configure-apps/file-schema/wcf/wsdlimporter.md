---
title: '&lt;wsdlImporter&gt;'
ms.date: 03/30/2017
ms.assetid: 986b2165-8430-4dba-b1b8-00396841bb96
ms.openlocfilehash: 43c1a50c740cd9c75ee641e4ac4d0fa8ea3ca36b
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/09/2019
ms.locfileid: "54144985"
---
# <a name="ltwsdlimportergt"></a><span data-ttu-id="3ca11-102">&lt;wsdlImporter&gt;</span><span class="sxs-lookup"><span data-stu-id="3ca11-102">&lt;wsdlImporter&gt;</span></span>
<span data-ttu-id="3ca11-103">指定可导入带有 WS-Policy 附件的 Web 服务描述语言 (WSDL) 1.1 元数据的所有 WSDL 导入程序。</span><span class="sxs-lookup"><span data-stu-id="3ca11-103">Specifies all the WSDL importers that imports Web Services Description Language (WSDL) 1.1 metadata with WS-Policy attachments.</span></span>  
  
<span data-ttu-id="3ca11-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="3ca11-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="3ca11-105">\<客户端 ></span><span class="sxs-lookup"><span data-stu-id="3ca11-105">\<client></span></span>  
<span data-ttu-id="3ca11-106">\<元数据 ></span><span class="sxs-lookup"><span data-stu-id="3ca11-106">\<metadata></span></span>  
<span data-ttu-id="3ca11-107">\<wsdlImporters ></span><span class="sxs-lookup"><span data-stu-id="3ca11-107">\<wsdlImporters></span></span>  
<span data-ttu-id="3ca11-108">\<wsdlImporter ></span><span class="sxs-lookup"><span data-stu-id="3ca11-108">\<wsdlImporter></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3ca11-109">语法</span><span class="sxs-lookup"><span data-stu-id="3ca11-109">Syntax</span></span>  
  
```xml  
<metadata>
  <wsdlImporters>
    <wsdlImporter type="string" />
  </wsdlImporters>
</metadata>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3ca11-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="3ca11-110">Attributes and Elements</span></span>  
 <span data-ttu-id="3ca11-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="3ca11-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3ca11-112">特性</span><span class="sxs-lookup"><span data-stu-id="3ca11-112">Attributes</span></span>  
  
|<span data-ttu-id="3ca11-113">特性</span><span class="sxs-lookup"><span data-stu-id="3ca11-113">Attribute</span></span>|<span data-ttu-id="3ca11-114">描述</span><span class="sxs-lookup"><span data-stu-id="3ca11-114">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="3ca11-115">此元素的类型。</span><span class="sxs-lookup"><span data-stu-id="3ca11-115">The type of this element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3ca11-116">子元素</span><span class="sxs-lookup"><span data-stu-id="3ca11-116">Child Elements</span></span>  
 <span data-ttu-id="3ca11-117">无。</span><span class="sxs-lookup"><span data-stu-id="3ca11-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3ca11-118">父元素</span><span class="sxs-lookup"><span data-stu-id="3ca11-118">Parent Elements</span></span>  
  
|<span data-ttu-id="3ca11-119">元素</span><span class="sxs-lookup"><span data-stu-id="3ca11-119">Element</span></span>|<span data-ttu-id="3ca11-120">描述</span><span class="sxs-lookup"><span data-stu-id="3ca11-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3ca11-121">\<wsdlImporters ></span><span class="sxs-lookup"><span data-stu-id="3ca11-121">\<wsdlImporters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdlimporters.md)|<span data-ttu-id="3ca11-122">指定可导入带有 WS-Policy 附件的 Web 服务描述语言 (WSDL) 1.1 元数据的所有 WSDL 导入程序。</span><span class="sxs-lookup"><span data-stu-id="3ca11-122">Specifies all the WSDL importers that imports Web Services Description Language (WSDL) 1.1 metadata with WS-Policy attachments.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3ca11-123">备注</span><span class="sxs-lookup"><span data-stu-id="3ca11-123">Remarks</span></span>  
 <span data-ttu-id="3ca11-124">WSDL 导入程序可用于导入元数据并将这些信息转换为各种表示协定和终结点信息的类。</span><span class="sxs-lookup"><span data-stu-id="3ca11-124">A WSDL importer is used to import metadata as well as convert that information into various classes that represent contract and endpoint information.</span></span> <span data-ttu-id="3ca11-125">它可以有选择地导入协定和终结点信息以及公开任何导入错误的属性，并接受与导入和转换过程相关的类型信息。</span><span class="sxs-lookup"><span data-stu-id="3ca11-125">It can selectively import contract and endpoint information and properties that expose any import errors and accept type information relevant to the import and conversion process.</span></span> <span data-ttu-id="3ca11-126">它还支持导入某些绑定信息和属性，这些信息和属性提供了对任何策略文档、WSDL 文档、WSDL 扩展和 XML 架构文档的访问。</span><span class="sxs-lookup"><span data-stu-id="3ca11-126">It also supports importing binding information and properties that provide access to any policy documents, WSDL documents, WSDL extensions, and XML schema documents.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ca11-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="3ca11-127">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.WsdlImporterElement>  
 <xref:System.ServiceModel.Configuration.MetadataElement>  
 <xref:System.ServiceModel.Configuration.WsdlImporterElementCollection>  
 <xref:System.ServiceModel.Description.MetadataImporter>  
 <xref:System.ServiceModel.Description.WsdlImporter>  
 [<span data-ttu-id="3ca11-128">WCF 客户端配置</span><span class="sxs-lookup"><span data-stu-id="3ca11-128">WCF Client Configuration</span></span>](../../../../../docs/framework/wcf/feature-details/client-configuration.md)  
 [<span data-ttu-id="3ca11-129">客户端</span><span class="sxs-lookup"><span data-stu-id="3ca11-129">Clients</span></span>](../../../../../docs/framework/wcf/feature-details/clients.md)
