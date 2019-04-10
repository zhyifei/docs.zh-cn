---
title: <exposedMethod>
ms.date: 03/30/2017
ms.assetid: 61c938cd-4ee9-4b06-ab28-922ef491ab11
ms.openlocfilehash: 91eafa46aa73b5e6d359fcbe48f098f9f8a4d0f0
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59174507"
---
# <a name="exposedmethod"></a><span data-ttu-id="a4f92-101">\<exposedMethod></span><span class="sxs-lookup"><span data-stu-id="a4f92-101">\<exposedMethod></span></span>
<span data-ttu-id="a4f92-102">表示一个在 COM+ 组件上的接口作为 Web 服务公开时公开的 COM+ 方法。</span><span class="sxs-lookup"><span data-stu-id="a4f92-102">Represents a COM+ method that is exposed when the interface on a COM+ component is exposed as a Web service.</span></span>  
  
 <span data-ttu-id="a4f92-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="a4f92-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="a4f92-104">\<comContracts></span><span class="sxs-lookup"><span data-stu-id="a4f92-104">\<comContracts></span></span>  
<span data-ttu-id="a4f92-105">\<comContract></span><span class="sxs-lookup"><span data-stu-id="a4f92-105">\<comContract></span></span>  
<span data-ttu-id="a4f92-106">\<方法 ></span><span class="sxs-lookup"><span data-stu-id="a4f92-106">\<methods></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a4f92-107">语法</span><span class="sxs-lookup"><span data-stu-id="a4f92-107">Syntax</span></span>  
  
```xml  
<comContracts>
  <comContract>
    <exposedMethods>
      <exposedMethod name="String" />
    </exposedMethods>
  </comContract>
</comContracts>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a4f92-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="a4f92-108">Attributes and Elements</span></span>  
 <span data-ttu-id="a4f92-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="a4f92-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a4f92-110">特性</span><span class="sxs-lookup"><span data-stu-id="a4f92-110">Attributes</span></span>  
  
|<span data-ttu-id="a4f92-111">特性</span><span class="sxs-lookup"><span data-stu-id="a4f92-111">Attribute</span></span>|<span data-ttu-id="a4f92-112">描述</span><span class="sxs-lookup"><span data-stu-id="a4f92-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a4f92-113">name</span><span class="sxs-lookup"><span data-stu-id="a4f92-113">name</span></span>|<span data-ttu-id="a4f92-114">一个字符串，包含在 COM+ 组件上的接口作为 Web 服务公开时公开的 COM+ 方法。</span><span class="sxs-lookup"><span data-stu-id="a4f92-114">A string that contains the COM+ method that is exposed when the interface on a COM+ component is exposed as a Web service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a4f92-115">子元素</span><span class="sxs-lookup"><span data-stu-id="a4f92-115">Child Elements</span></span>  
 <span data-ttu-id="a4f92-116">无。</span><span class="sxs-lookup"><span data-stu-id="a4f92-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a4f92-117">父元素</span><span class="sxs-lookup"><span data-stu-id="a4f92-117">Parent Elements</span></span>  
  
|<span data-ttu-id="a4f92-118">元素</span><span class="sxs-lookup"><span data-stu-id="a4f92-118">Element</span></span>|<span data-ttu-id="a4f92-119">描述</span><span class="sxs-lookup"><span data-stu-id="a4f92-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a4f92-120">\<exposedMethods></span><span class="sxs-lookup"><span data-stu-id="a4f92-120">\<exposedMethods></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethods.md)|<span data-ttu-id="a4f92-121">一系列[ \<exposedMethod >](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md)元素。</span><span class="sxs-lookup"><span data-stu-id="a4f92-121">A collection of [\<exposedMethod>](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md) elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a4f92-122">备注</span><span class="sxs-lookup"><span data-stu-id="a4f92-122">Remarks</span></span>  
 <span data-ttu-id="a4f92-123">可以使用 COM+ 集成配置工具 (ComSvcConfig.exe) 来添加 COM 接口中的特定方法，使其出现在生成的服务协定中。</span><span class="sxs-lookup"><span data-stu-id="a4f92-123">The COM+ integration configuration tool (ComSvcConfig.exe) can be used to add specific methods from a COM interface to appear on the generated service contract.</span></span>  
  
 <span data-ttu-id="a4f92-124">例如，可以使用以下命令将 `IFinances`.Financial 组件上的 `ItemOrders` COM 接口中的三个命名方法添加到生成的服务协定中。</span><span class="sxs-lookup"><span data-stu-id="a4f92-124">For example, you can use the following command to add the three named methods from the `IFinances` COM interface on the `ItemOrders`.Financial component, to the generated service contract.</span></span>  
  
 `ComSvcConfig.exe /i /application:OnlineStore /contract:ItemOrders.Financial,IFinances.{TransferFunds,AddFunds,RemoveFunds} /hosting:complus`  
  
 <span data-ttu-id="a4f92-125">此外运行 ComSvcConfig.exe 时，会生成以下服务协定列出以前提到的方法作为[ \<exposedMethod >](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md)元素。</span><span class="sxs-lookup"><span data-stu-id="a4f92-125">When you also run the ComSvcConfig.exe, it then generates the following service contract listing the previously mentioned methods as [\<exposedMethod>](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md) elements.</span></span>  
  
```xml  
<comContract contractType="{C551FBA9-E3AA-4272-8C2A-84BD8D290AC7}"
             name="IFinances"
             namespace="http://contoso.com/services/financial">
  <exposedMethod name="TransferFunds"/>
  <exposedMethod name="AddFunds"/>
  <exposedMethod name="RemoveFunds"/>
</comContract>
```  
  
 <span data-ttu-id="a4f92-126">在服务初始化时，则运行时会尝试通过反射和添加仅包含在列表中的方法来生成服务协定[ \<exposedMethod >](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md)元素。</span><span class="sxs-lookup"><span data-stu-id="a4f92-126">At service initialization time, the runtime attempts to generate a service contract by reflecting over and adding only the methods included in the list of [\<exposedMethod>](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md) elements.</span></span> <span data-ttu-id="a4f92-127">对于该服务协定中未包括的每个接口方法，都会产生一个跟踪。</span><span class="sxs-lookup"><span data-stu-id="a4f92-127">A trace is produced for every interface method that is not included on the service contract.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4f92-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="a4f92-128">See also</span></span>

- <xref:System.ServiceModel.Configuration.ComMethodElementCollection>
- <xref:System.ServiceModel.Configuration.ComMethodElement>
- [<span data-ttu-id="a4f92-129">\<comContracts></span><span class="sxs-lookup"><span data-stu-id="a4f92-129">\<comContracts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/comcontracts.md)
- [<span data-ttu-id="a4f92-130">与 COM+ 应用程序集成</span><span class="sxs-lookup"><span data-stu-id="a4f92-130">Integrating with COM+ Applications</span></span>](../../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications.md)
- [<span data-ttu-id="a4f92-131">如何：配置 COM+ 服务设置</span><span class="sxs-lookup"><span data-stu-id="a4f92-131">How to: Configure COM+ Service Settings</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-com-service-settings.md)
