---
title: '&lt;transportConfigurationTypes&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 929c8b0a-5460-4f66-a098-2cb8d4e10b69
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0a4f9396537446920b8976d1bd076fcd5ce5876c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="lttransportconfigurationtypesgt"></a><span data-ttu-id="006fa-102">&lt;transportConfigurationTypes&gt;</span><span class="sxs-lookup"><span data-stu-id="006fa-102">&lt;transportConfigurationTypes&gt;</span></span>
<span data-ttu-id="006fa-103">表示一个配置元素集合，这些元素标识了特定传输的类型。</span><span class="sxs-lookup"><span data-stu-id="006fa-103">Represents a collection of configuration elements that identify the type of a particular transport.</span></span> <span data-ttu-id="006fa-104">这可以用于添加自定义 WAS 协议。</span><span class="sxs-lookup"><span data-stu-id="006fa-104">This can be used to add custom WAS protocols.</span></span>  
  
 <span data-ttu-id="006fa-105">\<系统。ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="006fa-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="006fa-106">\<ServiceHostingEnvironment ></span><span class="sxs-lookup"><span data-stu-id="006fa-106">\<ServiceHostingEnvironment></span></span>  
<span data-ttu-id="006fa-107">\<transportConfigurationTypes ></span><span class="sxs-lookup"><span data-stu-id="006fa-107">\<transportConfigurationTypes></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="006fa-108">语法</span><span class="sxs-lookup"><span data-stu-id="006fa-108">Syntax</span></span>  
  
```xml  
<serviceHostingEnvironment>   
   <transportConfigurationTypes>  
      <add name="String"  
               transportConfigurationType="String"/>   
   </transportConfigurationTypes>  
</serviceHostingEnvironment>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="006fa-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="006fa-109">Attributes and Elements</span></span>  
 <span data-ttu-id="006fa-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="006fa-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="006fa-111">特性</span><span class="sxs-lookup"><span data-stu-id="006fa-111">Attributes</span></span>  
  
|<span data-ttu-id="006fa-112">特性</span><span class="sxs-lookup"><span data-stu-id="006fa-112">Attribute</span></span>|<span data-ttu-id="006fa-113">描述</span><span class="sxs-lookup"><span data-stu-id="006fa-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="006fa-114">name</span><span class="sxs-lookup"><span data-stu-id="006fa-114">name</span></span>|<span data-ttu-id="006fa-115">传输的名称</span><span class="sxs-lookup"><span data-stu-id="006fa-115">The name of the transport</span></span>|  
|<span data-ttu-id="006fa-116">transportConfigurationType</span><span class="sxs-lookup"><span data-stu-id="006fa-116">transportConfigurationType</span></span>|<span data-ttu-id="006fa-117">实现传输的类型</span><span class="sxs-lookup"><span data-stu-id="006fa-117">The type that implements the transport</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="006fa-118">子元素</span><span class="sxs-lookup"><span data-stu-id="006fa-118">Child Elements</span></span>  
  
|<span data-ttu-id="006fa-119">元素</span><span class="sxs-lookup"><span data-stu-id="006fa-119">Element</span></span>|<span data-ttu-id="006fa-120">描述</span><span class="sxs-lookup"><span data-stu-id="006fa-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="006fa-121">\<add></span><span class="sxs-lookup"><span data-stu-id="006fa-121">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-transportconfigurationtype.md)|<span data-ttu-id="006fa-122">添加一个用于标识特定传输的类型的配置元素。</span><span class="sxs-lookup"><span data-stu-id="006fa-122">Adds a configuration element that identifies the type of a particular transport.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="006fa-123">父元素</span><span class="sxs-lookup"><span data-stu-id="006fa-123">Parent Elements</span></span>  
  
|<span data-ttu-id="006fa-124">元素</span><span class="sxs-lookup"><span data-stu-id="006fa-124">Element</span></span>|<span data-ttu-id="006fa-125">描述</span><span class="sxs-lookup"><span data-stu-id="006fa-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="006fa-126">\<serviceHostingEnvironment ></span><span class="sxs-lookup"><span data-stu-id="006fa-126">\<serviceHostingEnvironment></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md)|<span data-ttu-id="006fa-127">定义服务承载环境要为特定传输实例化的类型。</span><span class="sxs-lookup"><span data-stu-id="006fa-127">Defines the type the service hosting environment instantiates for a particular transport.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="006fa-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="006fa-128">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>  
 <xref:System.ServiceModel.ServiceHostingEnvironment>  
 <xref:System.ServiceModel.Configuration.TransportConfigurationTypeElementCollection>  
 [<span data-ttu-id="006fa-129">承载</span><span class="sxs-lookup"><span data-stu-id="006fa-129">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
