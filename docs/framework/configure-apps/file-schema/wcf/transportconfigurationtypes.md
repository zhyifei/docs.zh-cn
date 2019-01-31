---
title: <transportConfigurationTypes>
ms.date: 03/30/2017
ms.assetid: 929c8b0a-5460-4f66-a098-2cb8d4e10b69
ms.openlocfilehash: 560da96c50e99461d25c1fd65def2dc10c284470
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2019
ms.locfileid: "55261660"
---
# <a name="transportconfigurationtypes"></a><span data-ttu-id="86d60-101">\<transportConfigurationTypes></span><span class="sxs-lookup"><span data-stu-id="86d60-101">\<transportConfigurationTypes></span></span>
<span data-ttu-id="86d60-102">表示一个配置元素集合，这些元素标识了特定传输的类型。</span><span class="sxs-lookup"><span data-stu-id="86d60-102">Represents a collection of configuration elements that identify the type of a particular transport.</span></span> <span data-ttu-id="86d60-103">这可以用于添加自定义 WAS 协议。</span><span class="sxs-lookup"><span data-stu-id="86d60-103">This can be used to add custom WAS protocols.</span></span>  
  
 <span data-ttu-id="86d60-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="86d60-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="86d60-105">\<ServiceHostingEnvironment></span><span class="sxs-lookup"><span data-stu-id="86d60-105">\<ServiceHostingEnvironment></span></span>  
<span data-ttu-id="86d60-106">\<transportConfigurationTypes></span><span class="sxs-lookup"><span data-stu-id="86d60-106">\<transportConfigurationTypes></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="86d60-107">语法</span><span class="sxs-lookup"><span data-stu-id="86d60-107">Syntax</span></span>  
  
```xml  
<serviceHostingEnvironment>
  <transportConfigurationTypes>
    <add name="String"
         transportConfigurationType="String" />
  </transportConfigurationTypes>
</serviceHostingEnvironment>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="86d60-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="86d60-108">Attributes and Elements</span></span>  
 <span data-ttu-id="86d60-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="86d60-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="86d60-110">特性</span><span class="sxs-lookup"><span data-stu-id="86d60-110">Attributes</span></span>  
  
|<span data-ttu-id="86d60-111">特性</span><span class="sxs-lookup"><span data-stu-id="86d60-111">Attribute</span></span>|<span data-ttu-id="86d60-112">描述</span><span class="sxs-lookup"><span data-stu-id="86d60-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="86d60-113">name</span><span class="sxs-lookup"><span data-stu-id="86d60-113">name</span></span>|<span data-ttu-id="86d60-114">传输的名称</span><span class="sxs-lookup"><span data-stu-id="86d60-114">The name of the transport</span></span>|  
|<span data-ttu-id="86d60-115">transportConfigurationType</span><span class="sxs-lookup"><span data-stu-id="86d60-115">transportConfigurationType</span></span>|<span data-ttu-id="86d60-116">实现传输的类型</span><span class="sxs-lookup"><span data-stu-id="86d60-116">The type that implements the transport</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="86d60-117">子元素</span><span class="sxs-lookup"><span data-stu-id="86d60-117">Child Elements</span></span>  
  
|<span data-ttu-id="86d60-118">元素</span><span class="sxs-lookup"><span data-stu-id="86d60-118">Element</span></span>|<span data-ttu-id="86d60-119">描述</span><span class="sxs-lookup"><span data-stu-id="86d60-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="86d60-120">\<add></span><span class="sxs-lookup"><span data-stu-id="86d60-120">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-transportconfigurationtype.md)|<span data-ttu-id="86d60-121">添加一个用于标识特定传输的类型的配置元素。</span><span class="sxs-lookup"><span data-stu-id="86d60-121">Adds a configuration element that identifies the type of a particular transport.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="86d60-122">父元素</span><span class="sxs-lookup"><span data-stu-id="86d60-122">Parent Elements</span></span>  
  
|<span data-ttu-id="86d60-123">元素</span><span class="sxs-lookup"><span data-stu-id="86d60-123">Element</span></span>|<span data-ttu-id="86d60-124">描述</span><span class="sxs-lookup"><span data-stu-id="86d60-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="86d60-125">\<serviceHostingEnvironment></span><span class="sxs-lookup"><span data-stu-id="86d60-125">\<serviceHostingEnvironment></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md)|<span data-ttu-id="86d60-126">定义服务承载环境要为特定传输实例化的类型。</span><span class="sxs-lookup"><span data-stu-id="86d60-126">Defines the type the service hosting environment instantiates for a particular transport.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="86d60-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="86d60-127">See also</span></span>
- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>
- <xref:System.ServiceModel.Configuration.TransportConfigurationTypeElementCollection>
- [<span data-ttu-id="86d60-128">承载</span><span class="sxs-lookup"><span data-stu-id="86d60-128">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
