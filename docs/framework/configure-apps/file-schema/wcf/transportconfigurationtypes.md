---
title: <transportConfigurationTypes>
ms.date: 03/30/2017
ms.assetid: 929c8b0a-5460-4f66-a098-2cb8d4e10b69
ms.openlocfilehash: bfd2147a8e772848fc98cab7a875a51bdb53b5cc
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69941162"
---
# <a name="transportconfigurationtypes"></a><span data-ttu-id="d8376-101">\<transportConfigurationTypes></span><span class="sxs-lookup"><span data-stu-id="d8376-101">\<transportConfigurationTypes></span></span>
<span data-ttu-id="d8376-102">表示一个配置元素集合，这些元素标识了特定传输的类型。</span><span class="sxs-lookup"><span data-stu-id="d8376-102">Represents a collection of configuration elements that identify the type of a particular transport.</span></span> <span data-ttu-id="d8376-103">这可以用于添加自定义 WAS 协议。</span><span class="sxs-lookup"><span data-stu-id="d8376-103">This can be used to add custom WAS protocols.</span></span>  
  
 <span data-ttu-id="d8376-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="d8376-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="d8376-105">\<ServiceHostingEnvironment></span><span class="sxs-lookup"><span data-stu-id="d8376-105">\<ServiceHostingEnvironment></span></span>  
<span data-ttu-id="d8376-106">\<transportConfigurationTypes></span><span class="sxs-lookup"><span data-stu-id="d8376-106">\<transportConfigurationTypes></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d8376-107">语法</span><span class="sxs-lookup"><span data-stu-id="d8376-107">Syntax</span></span>  
  
```xml  
<serviceHostingEnvironment>
  <transportConfigurationTypes>
    <add name="String"
         transportConfigurationType="String" />
  </transportConfigurationTypes>
</serviceHostingEnvironment>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d8376-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="d8376-108">Attributes and Elements</span></span>  
 <span data-ttu-id="d8376-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="d8376-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d8376-110">特性</span><span class="sxs-lookup"><span data-stu-id="d8376-110">Attributes</span></span>  
  
|<span data-ttu-id="d8376-111">特性</span><span class="sxs-lookup"><span data-stu-id="d8376-111">Attribute</span></span>|<span data-ttu-id="d8376-112">描述</span><span class="sxs-lookup"><span data-stu-id="d8376-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d8376-113">NAME</span><span class="sxs-lookup"><span data-stu-id="d8376-113">name</span></span>|<span data-ttu-id="d8376-114">传输的名称</span><span class="sxs-lookup"><span data-stu-id="d8376-114">The name of the transport</span></span>|  
|<span data-ttu-id="d8376-115">transportConfigurationType</span><span class="sxs-lookup"><span data-stu-id="d8376-115">transportConfigurationType</span></span>|<span data-ttu-id="d8376-116">实现传输的类型</span><span class="sxs-lookup"><span data-stu-id="d8376-116">The type that implements the transport</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d8376-117">子元素</span><span class="sxs-lookup"><span data-stu-id="d8376-117">Child Elements</span></span>  
  
|<span data-ttu-id="d8376-118">元素</span><span class="sxs-lookup"><span data-stu-id="d8376-118">Element</span></span>|<span data-ttu-id="d8376-119">描述</span><span class="sxs-lookup"><span data-stu-id="d8376-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d8376-120">\<add></span><span class="sxs-lookup"><span data-stu-id="d8376-120">\<add></span></span>](add-of-transportconfigurationtype.md)|<span data-ttu-id="d8376-121">添加一个用于标识特定传输的类型的配置元素。</span><span class="sxs-lookup"><span data-stu-id="d8376-121">Adds a configuration element that identifies the type of a particular transport.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d8376-122">父元素</span><span class="sxs-lookup"><span data-stu-id="d8376-122">Parent Elements</span></span>  
  
|<span data-ttu-id="d8376-123">元素</span><span class="sxs-lookup"><span data-stu-id="d8376-123">Element</span></span>|<span data-ttu-id="d8376-124">描述</span><span class="sxs-lookup"><span data-stu-id="d8376-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d8376-125">\<serviceHostingEnvironment></span><span class="sxs-lookup"><span data-stu-id="d8376-125">\<serviceHostingEnvironment></span></span>](servicehostingenvironment.md)|<span data-ttu-id="d8376-126">定义服务承载环境要为特定传输实例化的类型。</span><span class="sxs-lookup"><span data-stu-id="d8376-126">Defines the type the service hosting environment instantiates for a particular transport.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d8376-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="d8376-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>
- <xref:System.ServiceModel.Configuration.TransportConfigurationTypeElementCollection>
- [<span data-ttu-id="d8376-128">承载</span><span class="sxs-lookup"><span data-stu-id="d8376-128">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
