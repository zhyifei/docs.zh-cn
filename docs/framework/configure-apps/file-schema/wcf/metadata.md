---
title: <metadata>
ms.date: 03/30/2017
ms.assetid: d09653eb-e355-4c73-b87b-28f93d56480d
ms.openlocfilehash: 028e4d3fbe7bce06caa7497c8f95f3b293a4b068
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855224"
---
# <a name="metadata"></a><span data-ttu-id="40e05-101">\<元数据 ></span><span class="sxs-lookup"><span data-stu-id="40e05-101">\<metadata></span></span>
<span data-ttu-id="40e05-102">指定可以处理服务元数据的方式。</span><span class="sxs-lookup"><span data-stu-id="40e05-102">Specifies how service metadata can be processed.</span></span>  
  
<span data-ttu-id="40e05-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="40e05-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="40e05-104">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="40e05-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="40e05-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<客户端 >** ](client.md)</span><span class="sxs-lookup"><span data-stu-id="40e05-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)</span></span>\
<span data-ttu-id="40e05-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<元数据 >**</span><span class="sxs-lookup"><span data-stu-id="40e05-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<metadata>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40e05-107">语法</span><span class="sxs-lookup"><span data-stu-id="40e05-107">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <client>
    <metadata>
      <policyImporters>
        <policyImporter type="string" />
      </policyImporters>
      <wsdlImporters>
        <wsdlImporter type="string" />
      </wsdlImporters>
    </metadata>
  </client>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="40e05-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="40e05-108">Attributes and Elements</span></span>  
 <span data-ttu-id="40e05-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="40e05-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="40e05-110">特性</span><span class="sxs-lookup"><span data-stu-id="40e05-110">Attributes</span></span>  
 <span data-ttu-id="40e05-111">无。</span><span class="sxs-lookup"><span data-stu-id="40e05-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="40e05-112">子元素</span><span class="sxs-lookup"><span data-stu-id="40e05-112">Child Elements</span></span>  
  
|<span data-ttu-id="40e05-113">元素</span><span class="sxs-lookup"><span data-stu-id="40e05-113">Element</span></span>|<span data-ttu-id="40e05-114">描述</span><span class="sxs-lookup"><span data-stu-id="40e05-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="40e05-115">\<policyImporters></span><span class="sxs-lookup"><span data-stu-id="40e05-115">\<policyImporters></span></span>](policyimporters.md)|<span data-ttu-id="40e05-116">指定用于控制有关绑定的自定义策略断言的导入的所有策略导入程序。</span><span class="sxs-lookup"><span data-stu-id="40e05-116">Specifies all the policy importers that control the import of custom policy assertions about bindings.</span></span> <span data-ttu-id="40e05-117">策略导入程序用于搜索有关绑定功能的自定义策略断言，并附加一个实现断言所需功能的自定义绑定元素。</span><span class="sxs-lookup"><span data-stu-id="40e05-117">A policy importer is used to search custom policy assertions about binding features, as well as attach a custom binding element that implements the features the assertion requires.</span></span>|  
|[<span data-ttu-id="40e05-118">\<wsdlImporters></span><span class="sxs-lookup"><span data-stu-id="40e05-118">\<wsdlImporters></span></span>](wsdlimporters.md)|<span data-ttu-id="40e05-119">指定可导入带有 WS-Policy 附件的 Web 服务描述语言 (WSDL) 1.1 元数据的所有 WSDL 导入程序。</span><span class="sxs-lookup"><span data-stu-id="40e05-119">Specifies all the WSDL importers that import Web Services Description Language (WSDL) 1.1 metadata with WS-Policy attachments.</span></span> <span data-ttu-id="40e05-120">WSDL 导入程序可用于导入元数据并将这些信息转换为各种表示协定和终结点信息的类。</span><span class="sxs-lookup"><span data-stu-id="40e05-120">A WSDL importer is used to import metadata as well as convert that information into various classes that represent contract and endpoint information.</span></span> <span data-ttu-id="40e05-121">它可以有选择地导入协定和终结点信息以及公开任何导入错误的属性，并接受与导入和转换过程相关的类型信息。</span><span class="sxs-lookup"><span data-stu-id="40e05-121">It can selectively import contract and endpoint information and properties that expose any import errors and accept type information relevant to the import and conversion process.</span></span> <span data-ttu-id="40e05-122">它还支持导入某些绑定信息和属性，这些信息和属性提供了对任何策略文档、WSDL 文档、WSDL 扩展和 XML 架构文档的访问。</span><span class="sxs-lookup"><span data-stu-id="40e05-122">It also supports importing binding information and properties that provide access to any policy documents, WSDL documents, WSDL extensions, and XML schema documents.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="40e05-123">父元素</span><span class="sxs-lookup"><span data-stu-id="40e05-123">Parent Elements</span></span>  
  
|<span data-ttu-id="40e05-124">元素</span><span class="sxs-lookup"><span data-stu-id="40e05-124">Element</span></span>|<span data-ttu-id="40e05-125">描述</span><span class="sxs-lookup"><span data-stu-id="40e05-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="40e05-126">\<client></span><span class="sxs-lookup"><span data-stu-id="40e05-126">\<client></span></span>](client.md)|<span data-ttu-id="40e05-127">client 节定义客户端可以连接的终结点的列表。</span><span class="sxs-lookup"><span data-stu-id="40e05-127">The client section defines a list of endpoints that a client can connect to.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="40e05-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="40e05-128">See also</span></span>

- <xref:System.ServiceModel.Configuration.MetadataElement>
- <xref:System.ServiceModel.Configuration.PolicyImporterElementCollection>
- <xref:System.ServiceModel.Configuration.WsdlImporterElementCollection>
- <xref:System.ServiceModel.Description.MetadataImporter>
- <xref:System.ServiceModel.Description.WsdlImporter>
- [<span data-ttu-id="40e05-129">WCF 客户端配置</span><span class="sxs-lookup"><span data-stu-id="40e05-129">WCF Client Configuration</span></span>](../../../wcf/feature-details/client-configuration.md)
- [<span data-ttu-id="40e05-130">客户端</span><span class="sxs-lookup"><span data-stu-id="40e05-130">Clients</span></span>](../../../wcf/feature-details/clients.md)
