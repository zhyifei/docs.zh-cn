---
title: <transportConfigurationTypes>
ms.date: 03/30/2017
ms.assetid: 929c8b0a-5460-4f66-a098-2cb8d4e10b69
ms.openlocfilehash: b3683a198ec403fb9966bb902c936108fd043bfa
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59083636"
---
# <a name="transportconfigurationtypes"></a><span data-ttu-id="153a3-101">\<transportConfigurationTypes></span><span class="sxs-lookup"><span data-stu-id="153a3-101">\<transportConfigurationTypes></span></span>
<span data-ttu-id="153a3-102">表示一个配置元素集合，这些元素标识了特定传输的类型。</span><span class="sxs-lookup"><span data-stu-id="153a3-102">Represents a collection of configuration elements that identify the type of a particular transport.</span></span> <span data-ttu-id="153a3-103">这可以用于添加自定义 WAS 协议。</span><span class="sxs-lookup"><span data-stu-id="153a3-103">This can be used to add custom WAS protocols.</span></span>  
  
 <span data-ttu-id="153a3-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="153a3-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="153a3-105">\<ServiceHostingEnvironment></span><span class="sxs-lookup"><span data-stu-id="153a3-105">\<ServiceHostingEnvironment></span></span>  
<span data-ttu-id="153a3-106">\<transportConfigurationTypes></span><span class="sxs-lookup"><span data-stu-id="153a3-106">\<transportConfigurationTypes></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="153a3-107">语法</span><span class="sxs-lookup"><span data-stu-id="153a3-107">Syntax</span></span>  
  
```xml  
<serviceHostingEnvironment>
  <transportConfigurationTypes>
    <add name="String"
         transportConfigurationType="String" />
  </transportConfigurationTypes>
</serviceHostingEnvironment>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="153a3-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="153a3-108">Attributes and Elements</span></span>  
 <span data-ttu-id="153a3-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="153a3-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="153a3-110">特性</span><span class="sxs-lookup"><span data-stu-id="153a3-110">Attributes</span></span>  
  
|<span data-ttu-id="153a3-111">特性</span><span class="sxs-lookup"><span data-stu-id="153a3-111">Attribute</span></span>|<span data-ttu-id="153a3-112">描述</span><span class="sxs-lookup"><span data-stu-id="153a3-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="153a3-113">name</span><span class="sxs-lookup"><span data-stu-id="153a3-113">name</span></span>|<span data-ttu-id="153a3-114">传输的名称</span><span class="sxs-lookup"><span data-stu-id="153a3-114">The name of the transport</span></span>|  
|<span data-ttu-id="153a3-115">transportConfigurationType</span><span class="sxs-lookup"><span data-stu-id="153a3-115">transportConfigurationType</span></span>|<span data-ttu-id="153a3-116">实现传输的类型</span><span class="sxs-lookup"><span data-stu-id="153a3-116">The type that implements the transport</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="153a3-117">子元素</span><span class="sxs-lookup"><span data-stu-id="153a3-117">Child Elements</span></span>  
  
|<span data-ttu-id="153a3-118">元素</span><span class="sxs-lookup"><span data-stu-id="153a3-118">Element</span></span>|<span data-ttu-id="153a3-119">描述</span><span class="sxs-lookup"><span data-stu-id="153a3-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="153a3-120">\<add></span><span class="sxs-lookup"><span data-stu-id="153a3-120">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-transportconfigurationtype.md)|<span data-ttu-id="153a3-121">添加一个用于标识特定传输的类型的配置元素。</span><span class="sxs-lookup"><span data-stu-id="153a3-121">Adds a configuration element that identifies the type of a particular transport.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="153a3-122">父元素</span><span class="sxs-lookup"><span data-stu-id="153a3-122">Parent Elements</span></span>  
  
|<span data-ttu-id="153a3-123">元素</span><span class="sxs-lookup"><span data-stu-id="153a3-123">Element</span></span>|<span data-ttu-id="153a3-124">描述</span><span class="sxs-lookup"><span data-stu-id="153a3-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="153a3-125">\<serviceHostingEnvironment></span><span class="sxs-lookup"><span data-stu-id="153a3-125">\<serviceHostingEnvironment></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md)|<span data-ttu-id="153a3-126">定义服务承载环境要为特定传输实例化的类型。</span><span class="sxs-lookup"><span data-stu-id="153a3-126">Defines the type the service hosting environment instantiates for a particular transport.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="153a3-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="153a3-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>
- <xref:System.ServiceModel.Configuration.TransportConfigurationTypeElementCollection>
- [<span data-ttu-id="153a3-128">承载</span><span class="sxs-lookup"><span data-stu-id="153a3-128">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
