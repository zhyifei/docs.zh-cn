---
title: <wsdlImporter>
ms.date: 03/30/2017
ms.assetid: 986b2165-8430-4dba-b1b8-00396841bb96
ms.openlocfilehash: 317921a66fa3b8d1f0026d676ea674b67732b3df
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854758"
---
# <a name="wsdlimporter"></a><span data-ttu-id="1b957-101">\<wsdlImporter></span><span class="sxs-lookup"><span data-stu-id="1b957-101">\<wsdlImporter></span></span>
<span data-ttu-id="1b957-102">指定可导入带有 WS-Policy 附件的 Web 服务描述语言 (WSDL) 1.1 元数据的所有 WSDL 导入程序。</span><span class="sxs-lookup"><span data-stu-id="1b957-102">Specifies all the WSDL importers that imports Web Services Description Language (WSDL) 1.1 metadata with WS-Policy attachments.</span></span>  
  
<span data-ttu-id="1b957-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="1b957-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="1b957-104">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="1b957-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="1b957-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<客户端 >** ](client.md)</span><span class="sxs-lookup"><span data-stu-id="1b957-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)</span></span>\
<span data-ttu-id="1b957-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<元数据 >** ](metadata.md)</span><span class="sxs-lookup"><span data-stu-id="1b957-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<metadata>**](metadata.md)</span></span>\
<span data-ttu-id="1b957-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<wsdlImporters >** ](wsdlimporters.md)</span><span class="sxs-lookup"><span data-stu-id="1b957-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsdlImporters>**](wsdlimporters.md)</span></span>  
<span data-ttu-id="1b957-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<wsdlImporter >**</span><span class="sxs-lookup"><span data-stu-id="1b957-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<wsdlImporter>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1b957-109">语法</span><span class="sxs-lookup"><span data-stu-id="1b957-109">Syntax</span></span>  
  
```xml  
<metadata>
  <wsdlImporters>
    <wsdlImporter type="string" />
  </wsdlImporters>
</metadata>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1b957-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="1b957-110">Attributes and Elements</span></span>  
 <span data-ttu-id="1b957-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="1b957-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1b957-112">特性</span><span class="sxs-lookup"><span data-stu-id="1b957-112">Attributes</span></span>  
  
|<span data-ttu-id="1b957-113">特性</span><span class="sxs-lookup"><span data-stu-id="1b957-113">Attribute</span></span>|<span data-ttu-id="1b957-114">描述</span><span class="sxs-lookup"><span data-stu-id="1b957-114">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="1b957-115">此元素的类型。</span><span class="sxs-lookup"><span data-stu-id="1b957-115">The type of this element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1b957-116">子元素</span><span class="sxs-lookup"><span data-stu-id="1b957-116">Child Elements</span></span>  
 <span data-ttu-id="1b957-117">无。</span><span class="sxs-lookup"><span data-stu-id="1b957-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1b957-118">父元素</span><span class="sxs-lookup"><span data-stu-id="1b957-118">Parent Elements</span></span>  
  
|<span data-ttu-id="1b957-119">元素</span><span class="sxs-lookup"><span data-stu-id="1b957-119">Element</span></span>|<span data-ttu-id="1b957-120">描述</span><span class="sxs-lookup"><span data-stu-id="1b957-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1b957-121">\<wsdlImporters></span><span class="sxs-lookup"><span data-stu-id="1b957-121">\<wsdlImporters></span></span>](wsdlimporters.md)|<span data-ttu-id="1b957-122">指定可导入带有 WS-Policy 附件的 Web 服务描述语言 (WSDL) 1.1 元数据的所有 WSDL 导入程序。</span><span class="sxs-lookup"><span data-stu-id="1b957-122">Specifies all the WSDL importers that imports Web Services Description Language (WSDL) 1.1 metadata with WS-Policy attachments.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1b957-123">备注</span><span class="sxs-lookup"><span data-stu-id="1b957-123">Remarks</span></span>  
 <span data-ttu-id="1b957-124">WSDL 导入程序可用于导入元数据并将这些信息转换为各种表示协定和终结点信息的类。</span><span class="sxs-lookup"><span data-stu-id="1b957-124">A WSDL importer is used to import metadata as well as convert that information into various classes that represent contract and endpoint information.</span></span> <span data-ttu-id="1b957-125">它可以有选择地导入协定和终结点信息以及公开任何导入错误的属性，并接受与导入和转换过程相关的类型信息。</span><span class="sxs-lookup"><span data-stu-id="1b957-125">It can selectively import contract and endpoint information and properties that expose any import errors and accept type information relevant to the import and conversion process.</span></span> <span data-ttu-id="1b957-126">它还支持导入某些绑定信息和属性，这些信息和属性提供了对任何策略文档、WSDL 文档、WSDL 扩展和 XML 架构文档的访问。</span><span class="sxs-lookup"><span data-stu-id="1b957-126">It also supports importing binding information and properties that provide access to any policy documents, WSDL documents, WSDL extensions, and XML schema documents.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b957-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="1b957-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.WsdlImporterElement>
- <xref:System.ServiceModel.Configuration.MetadataElement>
- <xref:System.ServiceModel.Configuration.WsdlImporterElementCollection>
- <xref:System.ServiceModel.Description.MetadataImporter>
- <xref:System.ServiceModel.Description.WsdlImporter>
- [<span data-ttu-id="1b957-128">WCF 客户端配置</span><span class="sxs-lookup"><span data-stu-id="1b957-128">WCF Client Configuration</span></span>](../../../wcf/feature-details/client-configuration.md)
- [<span data-ttu-id="1b957-129">客户端</span><span class="sxs-lookup"><span data-stu-id="1b957-129">Clients</span></span>](../../../wcf/feature-details/clients.md)
