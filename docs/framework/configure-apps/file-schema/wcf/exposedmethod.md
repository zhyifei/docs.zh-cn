---
title: '&lt;exposedMethod&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 61c938cd-4ee9-4b06-ab28-922ef491ab11
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ecef8049a980f662cce4c421f62ccd3703400d69
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="ltexposedmethodgt"></a><span data-ttu-id="45792-102">&lt;exposedMethod&gt;</span><span class="sxs-lookup"><span data-stu-id="45792-102">&lt;exposedMethod&gt;</span></span>
<span data-ttu-id="45792-103">表示一个在 COM+ 组件上的接口作为 Web 服务公开时公开的 COM+ 方法。</span><span class="sxs-lookup"><span data-stu-id="45792-103">Represents a COM+ method that is exposed when the interface on a COM+ component is exposed as a Web service.</span></span>  
  
 <span data-ttu-id="45792-104">\<系统。ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="45792-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="45792-105">\<comContracts ></span><span class="sxs-lookup"><span data-stu-id="45792-105">\<comContracts></span></span>  
<span data-ttu-id="45792-106">\<comContract ></span><span class="sxs-lookup"><span data-stu-id="45792-106">\<comContract></span></span>  
<span data-ttu-id="45792-107">\<方法 ></span><span class="sxs-lookup"><span data-stu-id="45792-107">\<methods></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="45792-108">语法</span><span class="sxs-lookup"><span data-stu-id="45792-108">Syntax</span></span>  
  
```xml  
<comContracts>  
  <comContract>  
      <exposedMethods>  
         <exposedMethod name="string" />  
      </exposedMethods>  
  </comContract>  
</comContracts>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="45792-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="45792-109">Attributes and Elements</span></span>  
 <span data-ttu-id="45792-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="45792-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="45792-111">特性</span><span class="sxs-lookup"><span data-stu-id="45792-111">Attributes</span></span>  
  
|<span data-ttu-id="45792-112">特性</span><span class="sxs-lookup"><span data-stu-id="45792-112">Attribute</span></span>|<span data-ttu-id="45792-113">描述</span><span class="sxs-lookup"><span data-stu-id="45792-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="45792-114">name</span><span class="sxs-lookup"><span data-stu-id="45792-114">name</span></span>|<span data-ttu-id="45792-115">一个字符串，包含在 COM+ 组件上的接口作为 Web 服务公开时公开的 COM+ 方法。</span><span class="sxs-lookup"><span data-stu-id="45792-115">A string that contains the COM+ method that is exposed when the interface on a COM+ component is exposed as a Web service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="45792-116">子元素</span><span class="sxs-lookup"><span data-stu-id="45792-116">Child Elements</span></span>  
 <span data-ttu-id="45792-117">无。</span><span class="sxs-lookup"><span data-stu-id="45792-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="45792-118">父元素</span><span class="sxs-lookup"><span data-stu-id="45792-118">Parent Elements</span></span>  
  
|<span data-ttu-id="45792-119">元素</span><span class="sxs-lookup"><span data-stu-id="45792-119">Element</span></span>|<span data-ttu-id="45792-120">描述</span><span class="sxs-lookup"><span data-stu-id="45792-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="45792-121">\<exposedMethods ></span><span class="sxs-lookup"><span data-stu-id="45792-121">\<exposedMethods></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethods.md)|<span data-ttu-id="45792-122">集合[ \<exposedMethod >](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md)元素。</span><span class="sxs-lookup"><span data-stu-id="45792-122">A collection of [\<exposedMethod>](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md) elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="45792-123">备注</span><span class="sxs-lookup"><span data-stu-id="45792-123">Remarks</span></span>  
 <span data-ttu-id="45792-124">可以使用 COM+ 集成配置工具 (ComSvcConfig.exe) 来添加 COM 接口中的特定方法，使其出现在生成的服务协定中。</span><span class="sxs-lookup"><span data-stu-id="45792-124">The COM+ integration configuration tool (ComSvcConfig.exe) can be used to add specific methods from a COM interface to appear on the generated service contract.</span></span>  
  
 <span data-ttu-id="45792-125">例如，可以使用以下命令将 `IFinances`.Financial 组件上的 `ItemOrders` COM 接口中的三个命名方法添加到生成的服务协定中。</span><span class="sxs-lookup"><span data-stu-id="45792-125">For example, you can use the following command to add the three named methods from the `IFinances` COM interface on the `ItemOrders`.Financial component, to the generated service contract.</span></span>  
  
 `ComSvcConfig.exe /i /application:OnlineStore /contract:ItemOrders.Financial,IFinances.{TransferFunds,AddFunds,RemoveFunds} /hosting:complus`  
  
 <span data-ttu-id="45792-126">时也运行 ComSvcConfig.exe，它会生成以下服务协定列出作为先前提到的方法[ \<exposedMethod >](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md)元素。</span><span class="sxs-lookup"><span data-stu-id="45792-126">When you also run the ComSvcConfig.exe, it then generates the following service contract listing the previously mentioned methods as [\<exposedMethod>](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md) elements.</span></span>  
  
```xml  
<comContract contractType="{C551FBA9-E3AA-4272-8C2A-84BD8D290AC7}" name="IFinances" namespace="http://contoso.com/services/financial">  
    <exposedMethod name="TransferFunds"/>  
    <exposedMethod name="AddFunds"/>  
    <exposedMethod name="RemoveFunds"/>  
</comContract>  
```  
  
 <span data-ttu-id="45792-127">在服务初始化时，在运行时尝试通过反射和添加仅在列表中所包括的方法来生成服务协定[ \<exposedMethod >](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md)元素。</span><span class="sxs-lookup"><span data-stu-id="45792-127">At service initialization time, the runtime attempts to generate a service contract by reflecting over and adding only the methods included in the list of [\<exposedMethod>](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md) elements.</span></span> <span data-ttu-id="45792-128">对于该服务协定中未包括的每个接口方法，都会产生一个跟踪。</span><span class="sxs-lookup"><span data-stu-id="45792-128">A trace is produced for every interface method that is not included on the service contract.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45792-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="45792-129">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ComMethodElementCollection>  
 <xref:System.ServiceModel.Configuration.ComMethodElement>  
 [<span data-ttu-id="45792-130">\<comContracts ></span><span class="sxs-lookup"><span data-stu-id="45792-130">\<comContracts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/comcontracts.md)  
 [<span data-ttu-id="45792-131">与 COM + 应用程序集成</span><span class="sxs-lookup"><span data-stu-id="45792-131">Integrating with COM+ Applications</span></span>](../../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications.md)  
 [<span data-ttu-id="45792-132">如何： 配置 COM + 服务设置</span><span class="sxs-lookup"><span data-stu-id="45792-132">How to: Configure COM+ Service Settings</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-com-service-settings.md)
