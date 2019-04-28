---
title: <wsdlImporter>
ms.date: 03/30/2017
ms.assetid: 986b2165-8430-4dba-b1b8-00396841bb96
ms.openlocfilehash: 1f34486296465b3ea0b5b05bd9492062c85ad8c8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61670243"
---
# <a name="wsdlimporter"></a><span data-ttu-id="9ea4b-101">\<wsdlImporter></span><span class="sxs-lookup"><span data-stu-id="9ea4b-101">\<wsdlImporter></span></span>
<span data-ttu-id="9ea4b-102">指定可导入带有 WS-Policy 附件的 Web 服务描述语言 (WSDL) 1.1 元数据的所有 WSDL 导入程序。</span><span class="sxs-lookup"><span data-stu-id="9ea4b-102">Specifies all the WSDL importers that imports Web Services Description Language (WSDL) 1.1 metadata with WS-Policy attachments.</span></span>  
  
<span data-ttu-id="9ea4b-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="9ea4b-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="9ea4b-104">\<client></span><span class="sxs-lookup"><span data-stu-id="9ea4b-104">\<client></span></span>  
<span data-ttu-id="9ea4b-105">\<metadata></span><span class="sxs-lookup"><span data-stu-id="9ea4b-105">\<metadata></span></span>  
<span data-ttu-id="9ea4b-106">\<wsdlImporters></span><span class="sxs-lookup"><span data-stu-id="9ea4b-106">\<wsdlImporters></span></span>  
<span data-ttu-id="9ea4b-107">\<wsdlImporter></span><span class="sxs-lookup"><span data-stu-id="9ea4b-107">\<wsdlImporter></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ea4b-108">语法</span><span class="sxs-lookup"><span data-stu-id="9ea4b-108">Syntax</span></span>  
  
```xml  
<metadata>
  <wsdlImporters>
    <wsdlImporter type="string" />
  </wsdlImporters>
</metadata>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9ea4b-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="9ea4b-109">Attributes and Elements</span></span>  
 <span data-ttu-id="9ea4b-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="9ea4b-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9ea4b-111">特性</span><span class="sxs-lookup"><span data-stu-id="9ea4b-111">Attributes</span></span>  
  
|<span data-ttu-id="9ea4b-112">特性</span><span class="sxs-lookup"><span data-stu-id="9ea4b-112">Attribute</span></span>|<span data-ttu-id="9ea4b-113">描述</span><span class="sxs-lookup"><span data-stu-id="9ea4b-113">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="9ea4b-114">此元素的类型。</span><span class="sxs-lookup"><span data-stu-id="9ea4b-114">The type of this element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9ea4b-115">子元素</span><span class="sxs-lookup"><span data-stu-id="9ea4b-115">Child Elements</span></span>  
 <span data-ttu-id="9ea4b-116">无。</span><span class="sxs-lookup"><span data-stu-id="9ea4b-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9ea4b-117">父元素</span><span class="sxs-lookup"><span data-stu-id="9ea4b-117">Parent Elements</span></span>  
  
|<span data-ttu-id="9ea4b-118">元素</span><span class="sxs-lookup"><span data-stu-id="9ea4b-118">Element</span></span>|<span data-ttu-id="9ea4b-119">描述</span><span class="sxs-lookup"><span data-stu-id="9ea4b-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9ea4b-120">\<wsdlImporters></span><span class="sxs-lookup"><span data-stu-id="9ea4b-120">\<wsdlImporters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdlimporters.md)|<span data-ttu-id="9ea4b-121">指定可导入带有 WS-Policy 附件的 Web 服务描述语言 (WSDL) 1.1 元数据的所有 WSDL 导入程序。</span><span class="sxs-lookup"><span data-stu-id="9ea4b-121">Specifies all the WSDL importers that imports Web Services Description Language (WSDL) 1.1 metadata with WS-Policy attachments.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9ea4b-122">备注</span><span class="sxs-lookup"><span data-stu-id="9ea4b-122">Remarks</span></span>  
 <span data-ttu-id="9ea4b-123">WSDL 导入程序可用于导入元数据并将这些信息转换为各种表示协定和终结点信息的类。</span><span class="sxs-lookup"><span data-stu-id="9ea4b-123">A WSDL importer is used to import metadata as well as convert that information into various classes that represent contract and endpoint information.</span></span> <span data-ttu-id="9ea4b-124">它可以有选择地导入协定和终结点信息以及公开任何导入错误的属性，并接受与导入和转换过程相关的类型信息。</span><span class="sxs-lookup"><span data-stu-id="9ea4b-124">It can selectively import contract and endpoint information and properties that expose any import errors and accept type information relevant to the import and conversion process.</span></span> <span data-ttu-id="9ea4b-125">它还支持导入某些绑定信息和属性，这些信息和属性提供了对任何策略文档、WSDL 文档、WSDL 扩展和 XML 架构文档的访问。</span><span class="sxs-lookup"><span data-stu-id="9ea4b-125">It also supports importing binding information and properties that provide access to any policy documents, WSDL documents, WSDL extensions, and XML schema documents.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ea4b-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="9ea4b-126">See also</span></span>

- <xref:System.ServiceModel.Configuration.WsdlImporterElement>
- <xref:System.ServiceModel.Configuration.MetadataElement>
- <xref:System.ServiceModel.Configuration.WsdlImporterElementCollection>
- <xref:System.ServiceModel.Description.MetadataImporter>
- <xref:System.ServiceModel.Description.WsdlImporter>
- [<span data-ttu-id="9ea4b-127">WCF 客户端配置</span><span class="sxs-lookup"><span data-stu-id="9ea4b-127">WCF Client Configuration</span></span>](../../../../../docs/framework/wcf/feature-details/client-configuration.md)
- [<span data-ttu-id="9ea4b-128">客户端</span><span class="sxs-lookup"><span data-stu-id="9ea4b-128">Clients</span></span>](../../../../../docs/framework/wcf/feature-details/clients.md)
