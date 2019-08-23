---
title: <metadata>
ms.date: 03/30/2017
ms.assetid: d09653eb-e355-4c73-b87b-28f93d56480d
ms.openlocfilehash: 4555dc9c2e0b783de2fb57e47c9aada0d69462e7
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69931307"
---
# <a name="metadata"></a><span data-ttu-id="c19bc-101">\<元数据 ></span><span class="sxs-lookup"><span data-stu-id="c19bc-101">\<metadata></span></span>
<span data-ttu-id="c19bc-102">指定可以处理服务元数据的方式。</span><span class="sxs-lookup"><span data-stu-id="c19bc-102">Specifies how service metadata can be processed.</span></span>  
  
 <span data-ttu-id="c19bc-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="c19bc-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="c19bc-104">\<客户端 ></span><span class="sxs-lookup"><span data-stu-id="c19bc-104">\<client></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c19bc-105">语法</span><span class="sxs-lookup"><span data-stu-id="c19bc-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c19bc-106">特性和元素</span><span class="sxs-lookup"><span data-stu-id="c19bc-106">Attributes and Elements</span></span>  
 <span data-ttu-id="c19bc-107">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="c19bc-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c19bc-108">特性</span><span class="sxs-lookup"><span data-stu-id="c19bc-108">Attributes</span></span>  
 <span data-ttu-id="c19bc-109">无。</span><span class="sxs-lookup"><span data-stu-id="c19bc-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="c19bc-110">子元素</span><span class="sxs-lookup"><span data-stu-id="c19bc-110">Child Elements</span></span>  
  
|<span data-ttu-id="c19bc-111">元素</span><span class="sxs-lookup"><span data-stu-id="c19bc-111">Element</span></span>|<span data-ttu-id="c19bc-112">描述</span><span class="sxs-lookup"><span data-stu-id="c19bc-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c19bc-113">\<policyImporters></span><span class="sxs-lookup"><span data-stu-id="c19bc-113">\<policyImporters></span></span>](policyimporters.md)|<span data-ttu-id="c19bc-114">指定用于控制有关绑定的自定义策略断言的导入的所有策略导入程序。</span><span class="sxs-lookup"><span data-stu-id="c19bc-114">Specifies all the policy importers that control the import of custom policy assertions about bindings.</span></span> <span data-ttu-id="c19bc-115">策略导入程序用于搜索有关绑定功能的自定义策略断言，并附加一个实现断言所需功能的自定义绑定元素。</span><span class="sxs-lookup"><span data-stu-id="c19bc-115">A policy importer is used to search custom policy assertions about binding features, as well as attach a custom binding element that implements the features the assertion requires.</span></span>|  
|[<span data-ttu-id="c19bc-116">\<wsdlImporters></span><span class="sxs-lookup"><span data-stu-id="c19bc-116">\<wsdlImporters></span></span>](wsdlimporters.md)|<span data-ttu-id="c19bc-117">指定可导入带有 WS-Policy 附件的 Web 服务描述语言 (WSDL) 1.1 元数据的所有 WSDL 导入程序。</span><span class="sxs-lookup"><span data-stu-id="c19bc-117">Specifies all the WSDL importers that import Web Services Description Language (WSDL) 1.1 metadata with WS-Policy attachments.</span></span> <span data-ttu-id="c19bc-118">WSDL 导入程序可用于导入元数据并将这些信息转换为各种表示协定和终结点信息的类。</span><span class="sxs-lookup"><span data-stu-id="c19bc-118">A WSDL importer is used to import metadata as well as convert that information into various classes that represent contract and endpoint information.</span></span> <span data-ttu-id="c19bc-119">它可以有选择地导入协定和终结点信息以及公开任何导入错误的属性，并接受与导入和转换过程相关的类型信息。</span><span class="sxs-lookup"><span data-stu-id="c19bc-119">It can selectively import contract and endpoint information and properties that expose any import errors and accept type information relevant to the import and conversion process.</span></span> <span data-ttu-id="c19bc-120">它还支持导入某些绑定信息和属性，这些信息和属性提供了对任何策略文档、WSDL 文档、WSDL 扩展和 XML 架构文档的访问。</span><span class="sxs-lookup"><span data-stu-id="c19bc-120">It also supports importing binding information and properties that provide access to any policy documents, WSDL documents, WSDL extensions, and XML schema documents.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c19bc-121">父元素</span><span class="sxs-lookup"><span data-stu-id="c19bc-121">Parent Elements</span></span>  
  
|<span data-ttu-id="c19bc-122">元素</span><span class="sxs-lookup"><span data-stu-id="c19bc-122">Element</span></span>|<span data-ttu-id="c19bc-123">描述</span><span class="sxs-lookup"><span data-stu-id="c19bc-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c19bc-124">\<client></span><span class="sxs-lookup"><span data-stu-id="c19bc-124">\<client></span></span>](client.md)|<span data-ttu-id="c19bc-125">client 节定义客户端可以连接的终结点的列表。</span><span class="sxs-lookup"><span data-stu-id="c19bc-125">The client section defines a list of endpoints that a client can connect to.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c19bc-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="c19bc-126">See also</span></span>

- <xref:System.ServiceModel.Configuration.MetadataElement>
- <xref:System.ServiceModel.Configuration.PolicyImporterElementCollection>
- <xref:System.ServiceModel.Configuration.WsdlImporterElementCollection>
- <xref:System.ServiceModel.Description.MetadataImporter>
- <xref:System.ServiceModel.Description.WsdlImporter>
- [<span data-ttu-id="c19bc-127">WCF 客户端配置</span><span class="sxs-lookup"><span data-stu-id="c19bc-127">WCF Client Configuration</span></span>](../../../wcf/feature-details/client-configuration.md)
- [<span data-ttu-id="c19bc-128">客户端</span><span class="sxs-lookup"><span data-stu-id="c19bc-128">Clients</span></span>](../../../wcf/feature-details/clients.md)
