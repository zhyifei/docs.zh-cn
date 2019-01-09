---
title: '&lt;transportConfigurationTypes&gt;'
ms.date: 03/30/2017
ms.assetid: 929c8b0a-5460-4f66-a098-2cb8d4e10b69
ms.openlocfilehash: 5a51450d198ea395098f8a6a38d9104d0fe8538b
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/09/2019
ms.locfileid: "54145466"
---
# <a name="lttransportconfigurationtypesgt"></a><span data-ttu-id="e8c6a-102">&lt;transportConfigurationTypes&gt;</span><span class="sxs-lookup"><span data-stu-id="e8c6a-102">&lt;transportConfigurationTypes&gt;</span></span>
<span data-ttu-id="e8c6a-103">表示一个配置元素集合，这些元素标识了特定传输的类型。</span><span class="sxs-lookup"><span data-stu-id="e8c6a-103">Represents a collection of configuration elements that identify the type of a particular transport.</span></span> <span data-ttu-id="e8c6a-104">这可以用于添加自定义 WAS 协议。</span><span class="sxs-lookup"><span data-stu-id="e8c6a-104">This can be used to add custom WAS protocols.</span></span>  
  
 <span data-ttu-id="e8c6a-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="e8c6a-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="e8c6a-106">\<serviceHostingEnvironment ></span><span class="sxs-lookup"><span data-stu-id="e8c6a-106">\<ServiceHostingEnvironment></span></span>  
<span data-ttu-id="e8c6a-107">\<transportConfigurationTypes ></span><span class="sxs-lookup"><span data-stu-id="e8c6a-107">\<transportConfigurationTypes></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8c6a-108">语法</span><span class="sxs-lookup"><span data-stu-id="e8c6a-108">Syntax</span></span>  
  
```xml  
<serviceHostingEnvironment>
  <transportConfigurationTypes>
    <add name="String"
         transportConfigurationType="String" />
  </transportConfigurationTypes>
</serviceHostingEnvironment>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e8c6a-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="e8c6a-109">Attributes and Elements</span></span>  
 <span data-ttu-id="e8c6a-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="e8c6a-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e8c6a-111">特性</span><span class="sxs-lookup"><span data-stu-id="e8c6a-111">Attributes</span></span>  
  
|<span data-ttu-id="e8c6a-112">特性</span><span class="sxs-lookup"><span data-stu-id="e8c6a-112">Attribute</span></span>|<span data-ttu-id="e8c6a-113">描述</span><span class="sxs-lookup"><span data-stu-id="e8c6a-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e8c6a-114">name</span><span class="sxs-lookup"><span data-stu-id="e8c6a-114">name</span></span>|<span data-ttu-id="e8c6a-115">传输的名称</span><span class="sxs-lookup"><span data-stu-id="e8c6a-115">The name of the transport</span></span>|  
|<span data-ttu-id="e8c6a-116">transportConfigurationType</span><span class="sxs-lookup"><span data-stu-id="e8c6a-116">transportConfigurationType</span></span>|<span data-ttu-id="e8c6a-117">实现传输的类型</span><span class="sxs-lookup"><span data-stu-id="e8c6a-117">The type that implements the transport</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e8c6a-118">子元素</span><span class="sxs-lookup"><span data-stu-id="e8c6a-118">Child Elements</span></span>  
  
|<span data-ttu-id="e8c6a-119">元素</span><span class="sxs-lookup"><span data-stu-id="e8c6a-119">Element</span></span>|<span data-ttu-id="e8c6a-120">描述</span><span class="sxs-lookup"><span data-stu-id="e8c6a-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e8c6a-121">\<add></span><span class="sxs-lookup"><span data-stu-id="e8c6a-121">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-transportconfigurationtype.md)|<span data-ttu-id="e8c6a-122">添加一个用于标识特定传输的类型的配置元素。</span><span class="sxs-lookup"><span data-stu-id="e8c6a-122">Adds a configuration element that identifies the type of a particular transport.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e8c6a-123">父元素</span><span class="sxs-lookup"><span data-stu-id="e8c6a-123">Parent Elements</span></span>  
  
|<span data-ttu-id="e8c6a-124">元素</span><span class="sxs-lookup"><span data-stu-id="e8c6a-124">Element</span></span>|<span data-ttu-id="e8c6a-125">描述</span><span class="sxs-lookup"><span data-stu-id="e8c6a-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e8c6a-126">\<serviceHostingEnvironment ></span><span class="sxs-lookup"><span data-stu-id="e8c6a-126">\<serviceHostingEnvironment></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md)|<span data-ttu-id="e8c6a-127">定义服务承载环境要为特定传输实例化的类型。</span><span class="sxs-lookup"><span data-stu-id="e8c6a-127">Defines the type the service hosting environment instantiates for a particular transport.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e8c6a-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="e8c6a-128">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>  
 <xref:System.ServiceModel.ServiceHostingEnvironment>  
 <xref:System.ServiceModel.Configuration.TransportConfigurationTypeElementCollection>  
 [<span data-ttu-id="e8c6a-129">承载</span><span class="sxs-lookup"><span data-stu-id="e8c6a-129">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
