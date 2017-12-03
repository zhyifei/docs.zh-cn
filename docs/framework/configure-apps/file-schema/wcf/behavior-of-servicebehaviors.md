---
title: "&lt;serviceBehaviors&gt; 的 &lt;behavior&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 78fc0a08-55de-416a-ac12-a5e6ffc9a987
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 78c912886b5a39fad361994a0aaa302491e71f2d
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="ltbehaviorgt-of-ltservicebehaviorsgt"></a><span data-ttu-id="3397d-102">&lt;serviceBehaviors&gt; 的 &lt;behavior&gt;</span><span class="sxs-lookup"><span data-stu-id="3397d-102">&lt;behavior&gt; of &lt;serviceBehaviors&gt;</span></span>
<span data-ttu-id="3397d-103">`behavior` 元素包含服务行为的设置集合。</span><span class="sxs-lookup"><span data-stu-id="3397d-103">The `behavior` element contains a collection of settings for the behavior of a service.</span></span> <span data-ttu-id="3397d-104">每个行为都按其 `name` 进行索引。</span><span class="sxs-lookup"><span data-stu-id="3397d-104">Each behavior is indexed by its `name`.</span></span> <span data-ttu-id="3397d-105">服务可以将链接到通过此名称使用每个行为`behaviorConfiguration`属性[\<终结点 >](../../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md)元素。</span><span class="sxs-lookup"><span data-stu-id="3397d-105">Services can link to each behavior through this name using the `behaviorConfiguration` attribute of the [\<endpoint>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md) element.</span></span> <span data-ttu-id="3397d-106">这样，终结点可以共享公共行为配置而不用重新定义设置。</span><span class="sxs-lookup"><span data-stu-id="3397d-106">This allows endpoints to share common behavior configurations without redefining the settings.</span></span> <span data-ttu-id="3397d-107">从 [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] 开始，不要求绑定和行为具有名称。</span><span class="sxs-lookup"><span data-stu-id="3397d-107">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="3397d-108">有关默认配置和无名称的绑定和行为的详细信息，请参阅[简化配置](../../../../../docs/framework/wcf/simplified-configuration.md)和[简化配置 WCF 服务](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md)。</span><span class="sxs-lookup"><span data-stu-id="3397d-108">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3397d-109">行为元素特定于 Windows 工作流活动，如[ \<sendMessageChannelCache >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/sendmessagechannelcache.md)元素中, 所述[\<行为 > 的\<serviceBehaviors >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md)页。</span><span class="sxs-lookup"><span data-stu-id="3397d-109">Behavior elements specific to Windows Workflow activities, such as the [\<sendMessageChannelCache>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/sendmessagechannelcache.md) element, are documented in the [\<behavior> of \<serviceBehaviors>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md) page.</span></span>  
  
 <span data-ttu-id="3397d-110">\<系统。ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="3397d-110">\<system.ServiceModel></span></span>  
<span data-ttu-id="3397d-111">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="3397d-111">\<behaviors></span></span>  
<span data-ttu-id="3397d-112">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="3397d-112">\<serviceBehaviors></span></span>  
<span data-ttu-id="3397d-113">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="3397d-113">\<behavior></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3397d-114">语法</span><span class="sxs-lookup"><span data-stu-id="3397d-114">Syntax</span></span>  
  
```xml  
<system.ServiceModel>  
  <behaviors>  
    <serviceBehaviors>  
       <behavior name="String" />  
    </serviceBehaviors>  
  </behaviors>  
</system.ServiceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3397d-115">特性和元素</span><span class="sxs-lookup"><span data-stu-id="3397d-115">Attributes and Elements</span></span>  
 <span data-ttu-id="3397d-116">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="3397d-116">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3397d-117">特性</span><span class="sxs-lookup"><span data-stu-id="3397d-117">Attributes</span></span>  
  
|<span data-ttu-id="3397d-118">特性</span><span class="sxs-lookup"><span data-stu-id="3397d-118">Attribute</span></span>|<span data-ttu-id="3397d-119">描述</span><span class="sxs-lookup"><span data-stu-id="3397d-119">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3397d-120">name</span><span class="sxs-lookup"><span data-stu-id="3397d-120">name</span></span>|<span data-ttu-id="3397d-121">一个包含行为的配置名称的唯一字符串。</span><span class="sxs-lookup"><span data-stu-id="3397d-121">A unique string that contains the configuration name of the behavior.</span></span> <span data-ttu-id="3397d-122">此值是用户定义的一个字符串，该字符串必须是唯一的，因为它将充当元素的标识字符串。</span><span class="sxs-lookup"><span data-stu-id="3397d-122">This value is a user-defined string that must be unique, since it acts as the identification string for the element.</span></span> <span data-ttu-id="3397d-123">从 [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] 开始，不要求绑定和行为具有名称。</span><span class="sxs-lookup"><span data-stu-id="3397d-123">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="3397d-124">有关默认配置和无名称的绑定和行为的详细信息，请参阅[简化配置](../../../../../docs/framework/wcf/simplified-configuration.md)和[简化配置 WCF 服务](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md)。</span><span class="sxs-lookup"><span data-stu-id="3397d-124">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3397d-125">子元素</span><span class="sxs-lookup"><span data-stu-id="3397d-125">Child Elements</span></span>  
  
|<span data-ttu-id="3397d-126">元素</span><span class="sxs-lookup"><span data-stu-id="3397d-126">Element</span></span>|<span data-ttu-id="3397d-127">描述</span><span class="sxs-lookup"><span data-stu-id="3397d-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3397d-128">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="3397d-128">\<dataContractSerializer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md)|<span data-ttu-id="3397d-129">包含 DataContractSerializer 的配置数据。</span><span class="sxs-lookup"><span data-stu-id="3397d-129">Contains configuration data for the DataContractSerializer.</span></span>|  
|[<span data-ttu-id="3397d-130">\<persistenceProvider ></span><span class="sxs-lookup"><span data-stu-id="3397d-130">\<persistenceProvider></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/persistenceprovider.md)|<span data-ttu-id="3397d-131">指定要使用的持久性提供程序实现的类型以及用于持久性操作的超时值。</span><span class="sxs-lookup"><span data-stu-id="3397d-131">Specifies the type of the persistence provider implementation to use, as well as the time-out to use for persistence operations.</span></span>|  
|[<span data-ttu-id="3397d-132">\<路由 ></span><span class="sxs-lookup"><span data-stu-id="3397d-132">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing-of-servicebehavior.md)|<span data-ttu-id="3397d-133">提供对路由服务的运行时访问以允许对路由配置进行动态修改。</span><span class="sxs-lookup"><span data-stu-id="3397d-133">Provides run-time access to the routing service to allow dynamic modification of the routing configuration.</span></span>|  
|[<span data-ttu-id="3397d-134">\<serviceAuthenticationManager ></span><span class="sxs-lookup"><span data-stu-id="3397d-134">\<serviceAuthenticationManager></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthenticationmanager.md)|<span data-ttu-id="3397d-135">提供一个工作流配置元素，该元素在服务级别建立传输、消息或发起方的有效性。</span><span class="sxs-lookup"><span data-stu-id="3397d-135">Provides a workflow configuration element that establishes at the service level the validity of a transmission, message, or originator..</span></span>|  
|[<span data-ttu-id="3397d-136">\<serviceAuthorization ></span><span class="sxs-lookup"><span data-stu-id="3397d-136">\<serviceAuthorization></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md)|<span data-ttu-id="3397d-137">指定用于授予服务操作访问权限的设置。</span><span class="sxs-lookup"><span data-stu-id="3397d-137">Specifies settings that authorize access to service operations.</span></span>|  
|[<span data-ttu-id="3397d-138">\<serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="3397d-138">\<serviceCredentials></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md)|<span data-ttu-id="3397d-139">指定要用于对服务进行身份验证的凭据以及与客户端凭据验证相关的设置。</span><span class="sxs-lookup"><span data-stu-id="3397d-139">Specifies the credential to be used in authenticating the service and the client credential validation-related settings.</span></span>|  
|[<span data-ttu-id="3397d-140">\<serviceDebug ></span><span class="sxs-lookup"><span data-stu-id="3397d-140">\<serviceDebug></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicedebug.md)|<span data-ttu-id="3397d-141">指定 [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] 服务的调试和帮助信息功能。</span><span class="sxs-lookup"><span data-stu-id="3397d-141">Specifies debugging and help information features for a [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] service.</span></span>|  
|[<span data-ttu-id="3397d-142">\<serviceDiscovery ></span><span class="sxs-lookup"><span data-stu-id="3397d-142">\<serviceDiscovery></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicediscovery.md)|<span data-ttu-id="3397d-143">指定服务终结点的可发现性。</span><span class="sxs-lookup"><span data-stu-id="3397d-143">Specifies the discoverability of service endpoints.</span></span>|  
|[<span data-ttu-id="3397d-144">\<serviceMetadata ></span><span class="sxs-lookup"><span data-stu-id="3397d-144">\<serviceMetadata></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicemetadata.md)|<span data-ttu-id="3397d-145">指定服务元数据的发布和相关信息。</span><span class="sxs-lookup"><span data-stu-id="3397d-145">Specifies the publication of service metadata and associated information.</span></span>|  
|[<span data-ttu-id="3397d-146">\<serviceSecurityAudit ></span><span class="sxs-lookup"><span data-stu-id="3397d-146">\<serviceSecurityAudit></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicesecurityaudit.md)|<span data-ttu-id="3397d-147">指定用于在服务操作过程中启用安全事件审核的设置。</span><span class="sxs-lookup"><span data-stu-id="3397d-147">Specifies settings that enable auditing of security events during service operations.</span></span>|  
|[<span data-ttu-id="3397d-148">\<serviceThrottling ></span><span class="sxs-lookup"><span data-stu-id="3397d-148">\<serviceThrottling></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicethrottling.md)|<span data-ttu-id="3397d-149">指定 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 服务的限制机制。</span><span class="sxs-lookup"><span data-stu-id="3397d-149">Specifies the throttling mechanism of a [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] service.</span></span>|  
|[<span data-ttu-id="3397d-150">\<serviceTimeouts ></span><span class="sxs-lookup"><span data-stu-id="3397d-150">\<serviceTimeouts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicetimeouts.md)|<span data-ttu-id="3397d-151">指定服务的超时。</span><span class="sxs-lookup"><span data-stu-id="3397d-151">Specifies the timeout for a service.</span></span>|  
|[<span data-ttu-id="3397d-152">\<workflowRuntime ></span><span class="sxs-lookup"><span data-stu-id="3397d-152">\<workflowRuntime></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/workflowruntime.md)|<span data-ttu-id="3397d-153">指定用于承载基于工作流的 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 服务的 WorkflowRuntime 实例的设置。</span><span class="sxs-lookup"><span data-stu-id="3397d-153">Specifies settings for an instance of WorkflowRuntime for hosting workflow-based [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] services.</span></span>|  
|[<span data-ttu-id="3397d-154">\<useRequestHeadersForMetadataAddress ></span><span class="sxs-lookup"><span data-stu-id="3397d-154">\<useRequestHeadersForMetadataAddress></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/userequestheadersformetadataaddress.md)|<span data-ttu-id="3397d-155">允许从请求消息头中检索元数据地址信息。</span><span class="sxs-lookup"><span data-stu-id="3397d-155">Enables the retrieval of metadata address information from the request message headers.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3397d-156">父元素</span><span class="sxs-lookup"><span data-stu-id="3397d-156">Parent Elements</span></span>  
  
|<span data-ttu-id="3397d-157">元素</span><span class="sxs-lookup"><span data-stu-id="3397d-157">Element</span></span>|<span data-ttu-id="3397d-158">描述</span><span class="sxs-lookup"><span data-stu-id="3397d-158">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3397d-159">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="3397d-159">\<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md)|<span data-ttu-id="3397d-160">服务行为元素的集合。</span><span class="sxs-lookup"><span data-stu-id="3397d-160">A collection of service behavior elements.</span></span>|
