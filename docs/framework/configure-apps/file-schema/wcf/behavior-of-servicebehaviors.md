---
title: <behavior> 的 <serviceBehaviors>
ms.date: 03/30/2017
ms.assetid: 78fc0a08-55de-416a-ac12-a5e6ffc9a987
ms.openlocfilehash: 8c847368934cc4cd8ccaab017ede00b7b8963897
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69926408"
---
# <a name="behavior-of-servicebehaviors"></a><span data-ttu-id="eb5a6-102">\<serviceBehaviors > 的\<行为 ></span><span class="sxs-lookup"><span data-stu-id="eb5a6-102">\<behavior> of \<serviceBehaviors></span></span>
<span data-ttu-id="eb5a6-103">`behavior` 元素包含服务行为的设置集合。</span><span class="sxs-lookup"><span data-stu-id="eb5a6-103">The `behavior` element contains a collection of settings for the behavior of a service.</span></span> <span data-ttu-id="eb5a6-104">每个行为都按其 `name` 进行索引。</span><span class="sxs-lookup"><span data-stu-id="eb5a6-104">Each behavior is indexed by its `name`.</span></span> <span data-ttu-id="eb5a6-105">服务可以使用`behaviorConfiguration` [ \<端点 >](endpoint-element.md)元素的属性, 通过此名称链接到每个行为。</span><span class="sxs-lookup"><span data-stu-id="eb5a6-105">Services can link to each behavior through this name using the `behaviorConfiguration` attribute of the [\<endpoint>](endpoint-element.md) element.</span></span> <span data-ttu-id="eb5a6-106">这样，终结点可以共享公共行为配置而不用重新定义设置。</span><span class="sxs-lookup"><span data-stu-id="eb5a6-106">This allows endpoints to share common behavior configurations without redefining the settings.</span></span> <span data-ttu-id="eb5a6-107">从 [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] 开始，不要求绑定和行为具有名称。</span><span class="sxs-lookup"><span data-stu-id="eb5a6-107">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="eb5a6-108">有关默认配置和无值绑定和行为的详细信息, 请参阅[WCF 服务的](../../../wcf/samples/simplified-configuration-for-wcf-services.md)[简化配置](../../../wcf/simplified-configuration.md)和简化配置。</span><span class="sxs-lookup"><span data-stu-id="eb5a6-108">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="eb5a6-109">特定于 Windows 工作流活动的行为元素, 例如[ \<sendMessageChannelCache >](../windows-workflow-foundation/sendmessagechannelcache.md)元素, 在[ \< \<serviceBehaviors > 页的行为 >](../windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md)中进行了介绍。</span><span class="sxs-lookup"><span data-stu-id="eb5a6-109">Behavior elements specific to Windows Workflow activities, such as the [\<sendMessageChannelCache>](../windows-workflow-foundation/sendmessagechannelcache.md) element, are documented in the [\<behavior> of \<serviceBehaviors>](../windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md) page.</span></span>  
  
 <span data-ttu-id="eb5a6-110">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="eb5a6-110">\<system.ServiceModel></span></span>  
<span data-ttu-id="eb5a6-111">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="eb5a6-111">\<behaviors></span></span>  
<span data-ttu-id="eb5a6-112">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="eb5a6-112">\<serviceBehaviors></span></span>  
<span data-ttu-id="eb5a6-113">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="eb5a6-113">\<behavior></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eb5a6-114">语法</span><span class="sxs-lookup"><span data-stu-id="eb5a6-114">Syntax</span></span>  
  
```xml  
<system.ServiceModel>
  <behaviors>
    <serviceBehaviors>
       <behavior name="String" />
    </serviceBehaviors>
  </behaviors>
</system.ServiceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="eb5a6-115">特性和元素</span><span class="sxs-lookup"><span data-stu-id="eb5a6-115">Attributes and Elements</span></span>  
 <span data-ttu-id="eb5a6-116">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="eb5a6-116">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="eb5a6-117">特性</span><span class="sxs-lookup"><span data-stu-id="eb5a6-117">Attributes</span></span>  
  
|<span data-ttu-id="eb5a6-118">特性</span><span class="sxs-lookup"><span data-stu-id="eb5a6-118">Attribute</span></span>|<span data-ttu-id="eb5a6-119">描述</span><span class="sxs-lookup"><span data-stu-id="eb5a6-119">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="eb5a6-120">NAME</span><span class="sxs-lookup"><span data-stu-id="eb5a6-120">name</span></span>|<span data-ttu-id="eb5a6-121">一个包含行为的配置名称的唯一字符串。</span><span class="sxs-lookup"><span data-stu-id="eb5a6-121">A unique string that contains the configuration name of the behavior.</span></span> <span data-ttu-id="eb5a6-122">此值是用户定义的一个字符串，该字符串必须是唯一的，因为它将充当元素的标识字符串。</span><span class="sxs-lookup"><span data-stu-id="eb5a6-122">This value is a user-defined string that must be unique, since it acts as the identification string for the element.</span></span> <span data-ttu-id="eb5a6-123">从 [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] 开始，不要求绑定和行为具有名称。</span><span class="sxs-lookup"><span data-stu-id="eb5a6-123">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="eb5a6-124">有关默认配置和无值绑定和行为的详细信息, 请参阅[WCF 服务的](../../../wcf/samples/simplified-configuration-for-wcf-services.md)[简化配置](../../../wcf/simplified-configuration.md)和简化配置。</span><span class="sxs-lookup"><span data-stu-id="eb5a6-124">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="eb5a6-125">子元素</span><span class="sxs-lookup"><span data-stu-id="eb5a6-125">Child Elements</span></span>  
  
|<span data-ttu-id="eb5a6-126">元素</span><span class="sxs-lookup"><span data-stu-id="eb5a6-126">Element</span></span>|<span data-ttu-id="eb5a6-127">描述</span><span class="sxs-lookup"><span data-stu-id="eb5a6-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="eb5a6-128">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="eb5a6-128">\<dataContractSerializer></span></span>](datacontractserializer-element.md)|<span data-ttu-id="eb5a6-129">包含 DataContractSerializer 的配置数据。</span><span class="sxs-lookup"><span data-stu-id="eb5a6-129">Contains configuration data for the DataContractSerializer.</span></span>|  
|[<span data-ttu-id="eb5a6-130">\<persistenceProvider></span><span class="sxs-lookup"><span data-stu-id="eb5a6-130">\<persistenceProvider></span></span>](persistenceprovider.md)|<span data-ttu-id="eb5a6-131">指定要使用的持久性提供程序实现的类型以及用于持久性操作的超时值。</span><span class="sxs-lookup"><span data-stu-id="eb5a6-131">Specifies the type of the persistence provider implementation to use, as well as the time-out to use for persistence operations.</span></span>|  
|[<span data-ttu-id="eb5a6-132">\<routing></span><span class="sxs-lookup"><span data-stu-id="eb5a6-132">\<routing></span></span>](routing-of-servicebehavior.md)|<span data-ttu-id="eb5a6-133">提供对路由服务的运行时访问以允许对路由配置进行动态修改。</span><span class="sxs-lookup"><span data-stu-id="eb5a6-133">Provides run-time access to the routing service to allow dynamic modification of the routing configuration.</span></span>|  
|[<span data-ttu-id="eb5a6-134">\<serviceAuthenticationManager></span><span class="sxs-lookup"><span data-stu-id="eb5a6-134">\<serviceAuthenticationManager></span></span>](serviceauthenticationmanager.md)|<span data-ttu-id="eb5a6-135">提供一个工作流配置元素，该元素在服务级别建立传输、消息或发起方的有效性。</span><span class="sxs-lookup"><span data-stu-id="eb5a6-135">Provides a workflow configuration element that establishes at the service level the validity of a transmission, message, or originator..</span></span>|  
|[<span data-ttu-id="eb5a6-136">\<serviceAuthorization></span><span class="sxs-lookup"><span data-stu-id="eb5a6-136">\<serviceAuthorization></span></span>](serviceauthorization-element.md)|<span data-ttu-id="eb5a6-137">指定用于授予服务操作访问权限的设置。</span><span class="sxs-lookup"><span data-stu-id="eb5a6-137">Specifies settings that authorize access to service operations.</span></span>|  
|[<span data-ttu-id="eb5a6-138">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="eb5a6-138">\<serviceCredentials></span></span>](servicecredentials.md)|<span data-ttu-id="eb5a6-139">指定要用于对服务进行身份验证的凭据以及与客户端凭据验证相关的设置。</span><span class="sxs-lookup"><span data-stu-id="eb5a6-139">Specifies the credential to be used in authenticating the service and the client credential validation-related settings.</span></span>|  
|[<span data-ttu-id="eb5a6-140">\<serviceDebug></span><span class="sxs-lookup"><span data-stu-id="eb5a6-140">\<serviceDebug></span></span>](servicedebug.md)|<span data-ttu-id="eb5a6-141">指定 Windows Communication Foundation (WCF) 服务的调试和帮助信息功能。</span><span class="sxs-lookup"><span data-stu-id="eb5a6-141">Specifies debugging and help information features for a Windows Communication Foundation (WCF) service.</span></span>|  
|[<span data-ttu-id="eb5a6-142">\<serviceDiscovery></span><span class="sxs-lookup"><span data-stu-id="eb5a6-142">\<serviceDiscovery></span></span>](servicediscovery.md)|<span data-ttu-id="eb5a6-143">指定服务终结点的可发现性。</span><span class="sxs-lookup"><span data-stu-id="eb5a6-143">Specifies the discoverability of service endpoints.</span></span>|  
|[<span data-ttu-id="eb5a6-144">\<serviceMetadata></span><span class="sxs-lookup"><span data-stu-id="eb5a6-144">\<serviceMetadata></span></span>](servicemetadata.md)|<span data-ttu-id="eb5a6-145">指定服务元数据的发布和相关信息。</span><span class="sxs-lookup"><span data-stu-id="eb5a6-145">Specifies the publication of service metadata and associated information.</span></span>|  
|[<span data-ttu-id="eb5a6-146">\<serviceSecurityAudit></span><span class="sxs-lookup"><span data-stu-id="eb5a6-146">\<serviceSecurityAudit></span></span>](servicesecurityaudit.md)|<span data-ttu-id="eb5a6-147">指定用于在服务操作过程中启用安全事件审核的设置。</span><span class="sxs-lookup"><span data-stu-id="eb5a6-147">Specifies settings that enable auditing of security events during service operations.</span></span>|  
|[<span data-ttu-id="eb5a6-148">\<serviceThrottling></span><span class="sxs-lookup"><span data-stu-id="eb5a6-148">\<serviceThrottling></span></span>](servicethrottling.md)|<span data-ttu-id="eb5a6-149">指定 WCF 服务的限制机制。</span><span class="sxs-lookup"><span data-stu-id="eb5a6-149">Specifies the throttling mechanism of a WCF service.</span></span>|  
|[<span data-ttu-id="eb5a6-150">\<serviceTimeouts></span><span class="sxs-lookup"><span data-stu-id="eb5a6-150">\<serviceTimeouts></span></span>](servicetimeouts.md)|<span data-ttu-id="eb5a6-151">指定服务的超时。</span><span class="sxs-lookup"><span data-stu-id="eb5a6-151">Specifies the timeout for a service.</span></span>|  
|[<span data-ttu-id="eb5a6-152">\<workflowRuntime></span><span class="sxs-lookup"><span data-stu-id="eb5a6-152">\<workflowRuntime></span></span>](workflowruntime.md)|<span data-ttu-id="eb5a6-153">指定用于承载基于工作流的 WCF 服务的 WorkflowRuntime 实例的设置。</span><span class="sxs-lookup"><span data-stu-id="eb5a6-153">Specifies settings for an instance of WorkflowRuntime for hosting workflow-based WCF services.</span></span>|  
|[<span data-ttu-id="eb5a6-154">\<useRequestHeadersForMetadataAddress></span><span class="sxs-lookup"><span data-stu-id="eb5a6-154">\<useRequestHeadersForMetadataAddress></span></span>](userequestheadersformetadataaddress.md)|<span data-ttu-id="eb5a6-155">允许从请求消息头中检索元数据地址信息。</span><span class="sxs-lookup"><span data-stu-id="eb5a6-155">Enables the retrieval of metadata address information from the request message headers.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="eb5a6-156">父元素</span><span class="sxs-lookup"><span data-stu-id="eb5a6-156">Parent Elements</span></span>  
  
|<span data-ttu-id="eb5a6-157">元素</span><span class="sxs-lookup"><span data-stu-id="eb5a6-157">Element</span></span>|<span data-ttu-id="eb5a6-158">描述</span><span class="sxs-lookup"><span data-stu-id="eb5a6-158">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="eb5a6-159">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="eb5a6-159">\<serviceBehaviors></span></span>](servicebehaviors.md)|<span data-ttu-id="eb5a6-160">服务行为元素的集合。</span><span class="sxs-lookup"><span data-stu-id="eb5a6-160">A collection of service behavior elements.</span></span>|
