---
title: '&lt;policyImporter&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b0d03456-546f-44bb-ab12-1b2ce7f98fca
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 99bb7c6be02bad85792dfce9de1f6ef8ba1dcd17
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="ltpolicyimportergt"></a><span data-ttu-id="50204-102">&lt;policyImporter&gt;</span><span class="sxs-lookup"><span data-stu-id="50204-102">&lt;policyImporter&gt;</span></span>
<span data-ttu-id="50204-103">指定一个策略导入程序，用于控制有关绑定的自定义策略断言的导入。</span><span class="sxs-lookup"><span data-stu-id="50204-103">Specifies a policy importer that controls the import of custom policy assertions about bindings.</span></span>  
  
 <span data-ttu-id="50204-104">\<系统。ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="50204-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="50204-105">\<客户端 ></span><span class="sxs-lookup"><span data-stu-id="50204-105">\<client></span></span>  
<span data-ttu-id="50204-106">\<元数据 ></span><span class="sxs-lookup"><span data-stu-id="50204-106">\<metadata></span></span>  
<span data-ttu-id="50204-107">\<policyImporters ></span><span class="sxs-lookup"><span data-stu-id="50204-107">\<policyImporters></span></span>  
<span data-ttu-id="50204-108">\<policyImporter ></span><span class="sxs-lookup"><span data-stu-id="50204-108">\<policyImporter></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="50204-109">语法</span><span class="sxs-lookup"><span data-stu-id="50204-109">Syntax</span></span>  
  
```xml  
<metadata>  
   <policyImporters>  
      <policyImporter type="string" />  
   </policyImporters>  
</metadata>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="50204-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="50204-110">Attributes and Elements</span></span>  
 <span data-ttu-id="50204-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="50204-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="50204-112">特性</span><span class="sxs-lookup"><span data-stu-id="50204-112">Attributes</span></span>  
  
|<span data-ttu-id="50204-113">特性</span><span class="sxs-lookup"><span data-stu-id="50204-113">Attribute</span></span>|<span data-ttu-id="50204-114">描述</span><span class="sxs-lookup"><span data-stu-id="50204-114">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="50204-115">此元素的类型。</span><span class="sxs-lookup"><span data-stu-id="50204-115">The type of this element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="50204-116">子元素</span><span class="sxs-lookup"><span data-stu-id="50204-116">Child Elements</span></span>  
 <span data-ttu-id="50204-117">无</span><span class="sxs-lookup"><span data-stu-id="50204-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="50204-118">父元素</span><span class="sxs-lookup"><span data-stu-id="50204-118">Parent Elements</span></span>  
  
|<span data-ttu-id="50204-119">元素</span><span class="sxs-lookup"><span data-stu-id="50204-119">Element</span></span>|<span data-ttu-id="50204-120">描述</span><span class="sxs-lookup"><span data-stu-id="50204-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="50204-121">\<policyImporters ></span><span class="sxs-lookup"><span data-stu-id="50204-121">\<policyImporters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/policyimporters.md)|<span data-ttu-id="50204-122">指定用于控制有关绑定的自定义策略断言的导入的所有策略导入程序。</span><span class="sxs-lookup"><span data-stu-id="50204-122">Specifies all the policy importers that control the import of custom policy assertions about bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="50204-123">备注</span><span class="sxs-lookup"><span data-stu-id="50204-123">Remarks</span></span>  
 <span data-ttu-id="50204-124">策略导入程序用于搜索有关绑定功能的自定义策略断言，并附加一个实现断言所需功能的自定义绑定元素。</span><span class="sxs-lookup"><span data-stu-id="50204-124">A policy importer is used to search custom policy assertions about binding features, as well as attach a custom binding element that implements the features the assertion requires.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50204-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="50204-125">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.PolicyImporterElementCollection>  
 <xref:System.ServiceModel.Configuration.PolicyImporterElement>  
 <xref:System.ServiceModel.Configuration.MetadataElement>  
 <xref:System.ServiceModel.Description.MetadataImporter>  
 [<span data-ttu-id="50204-126">WCF 客户端配置</span><span class="sxs-lookup"><span data-stu-id="50204-126">WCF Client Configuration</span></span>](../../../../../docs/framework/wcf/feature-details/client-configuration.md)  
 [<span data-ttu-id="50204-127">客户端</span><span class="sxs-lookup"><span data-stu-id="50204-127">Clients</span></span>](../../../../../docs/framework/wcf/feature-details/clients.md)
