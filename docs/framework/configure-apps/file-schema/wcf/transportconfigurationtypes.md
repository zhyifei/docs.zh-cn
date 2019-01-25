---
title: '&lt;transportConfigurationTypes&gt;'
ms.date: 03/30/2017
ms.assetid: 929c8b0a-5460-4f66-a098-2cb8d4e10b69
ms.openlocfilehash: 37ce20c5fb0791596264bb7b6c03d5d0f2cc2388
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54704912"
---
# <a name="lttransportconfigurationtypesgt"></a><span data-ttu-id="23688-102">&lt;transportConfigurationTypes&gt;</span><span class="sxs-lookup"><span data-stu-id="23688-102">&lt;transportConfigurationTypes&gt;</span></span>
<span data-ttu-id="23688-103">表示一个配置元素集合，这些元素标识了特定传输的类型。</span><span class="sxs-lookup"><span data-stu-id="23688-103">Represents a collection of configuration elements that identify the type of a particular transport.</span></span> <span data-ttu-id="23688-104">这可以用于添加自定义 WAS 协议。</span><span class="sxs-lookup"><span data-stu-id="23688-104">This can be used to add custom WAS protocols.</span></span>  
  
 <span data-ttu-id="23688-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="23688-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="23688-106">\<ServiceHostingEnvironment></span><span class="sxs-lookup"><span data-stu-id="23688-106">\<ServiceHostingEnvironment></span></span>  
<span data-ttu-id="23688-107">\<transportConfigurationTypes></span><span class="sxs-lookup"><span data-stu-id="23688-107">\<transportConfigurationTypes></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="23688-108">语法</span><span class="sxs-lookup"><span data-stu-id="23688-108">Syntax</span></span>  
  
```xml  
<serviceHostingEnvironment>
  <transportConfigurationTypes>
    <add name="String"
         transportConfigurationType="String" />
  </transportConfigurationTypes>
</serviceHostingEnvironment>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="23688-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="23688-109">Attributes and Elements</span></span>  
 <span data-ttu-id="23688-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="23688-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="23688-111">特性</span><span class="sxs-lookup"><span data-stu-id="23688-111">Attributes</span></span>  
  
|<span data-ttu-id="23688-112">特性</span><span class="sxs-lookup"><span data-stu-id="23688-112">Attribute</span></span>|<span data-ttu-id="23688-113">描述</span><span class="sxs-lookup"><span data-stu-id="23688-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="23688-114">name</span><span class="sxs-lookup"><span data-stu-id="23688-114">name</span></span>|<span data-ttu-id="23688-115">传输的名称</span><span class="sxs-lookup"><span data-stu-id="23688-115">The name of the transport</span></span>|  
|<span data-ttu-id="23688-116">transportConfigurationType</span><span class="sxs-lookup"><span data-stu-id="23688-116">transportConfigurationType</span></span>|<span data-ttu-id="23688-117">实现传输的类型</span><span class="sxs-lookup"><span data-stu-id="23688-117">The type that implements the transport</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="23688-118">子元素</span><span class="sxs-lookup"><span data-stu-id="23688-118">Child Elements</span></span>  
  
|<span data-ttu-id="23688-119">元素</span><span class="sxs-lookup"><span data-stu-id="23688-119">Element</span></span>|<span data-ttu-id="23688-120">描述</span><span class="sxs-lookup"><span data-stu-id="23688-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="23688-121">\<add></span><span class="sxs-lookup"><span data-stu-id="23688-121">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-transportconfigurationtype.md)|<span data-ttu-id="23688-122">添加一个用于标识特定传输的类型的配置元素。</span><span class="sxs-lookup"><span data-stu-id="23688-122">Adds a configuration element that identifies the type of a particular transport.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="23688-123">父元素</span><span class="sxs-lookup"><span data-stu-id="23688-123">Parent Elements</span></span>  
  
|<span data-ttu-id="23688-124">元素</span><span class="sxs-lookup"><span data-stu-id="23688-124">Element</span></span>|<span data-ttu-id="23688-125">描述</span><span class="sxs-lookup"><span data-stu-id="23688-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="23688-126">\<serviceHostingEnvironment></span><span class="sxs-lookup"><span data-stu-id="23688-126">\<serviceHostingEnvironment></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md)|<span data-ttu-id="23688-127">定义服务承载环境要为特定传输实例化的类型。</span><span class="sxs-lookup"><span data-stu-id="23688-127">Defines the type the service hosting environment instantiates for a particular transport.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="23688-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="23688-128">See also</span></span>
- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>
- <xref:System.ServiceModel.Configuration.TransportConfigurationTypeElementCollection>
- [<span data-ttu-id="23688-129">承载</span><span class="sxs-lookup"><span data-stu-id="23688-129">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
