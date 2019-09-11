---
title: <exposedMethod>
ms.date: 03/30/2017
ms.assetid: 61c938cd-4ee9-4b06-ab28-922ef491ab11
ms.openlocfilehash: 46f2872fb289c2793c356ea179deb3ce52e6d65e
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855308"
---
# <a name="exposedmethod"></a><span data-ttu-id="bdfc9-101">\<exposedMethod ></span><span class="sxs-lookup"><span data-stu-id="bdfc9-101">\<exposedMethod></span></span>
<span data-ttu-id="bdfc9-102">表示一个在 COM+ 组件上的接口作为 Web 服务公开时公开的 COM+ 方法。</span><span class="sxs-lookup"><span data-stu-id="bdfc9-102">Represents a COM+ method that is exposed when the interface on a COM+ component is exposed as a Web service.</span></span>  
  
<span data-ttu-id="bdfc9-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="bdfc9-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="bdfc9-104">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="bdfc9-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="bdfc9-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comContracts >** ](comcontracts.md)</span><span class="sxs-lookup"><span data-stu-id="bdfc9-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<comContracts>**](comcontracts.md)</span></span>\
<span data-ttu-id="bdfc9-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comContract >** ](comcontract.md)</span><span class="sxs-lookup"><span data-stu-id="bdfc9-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<comContract>**](comcontract.md)</span></span>\
<span data-ttu-id="bdfc9-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<exposedMethods >** ](exposedmethods.md)</span><span class="sxs-lookup"><span data-stu-id="bdfc9-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<exposedMethods>**](exposedmethods.md)</span></span>\
<span data-ttu-id="bdfc9-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<exposedMethod >**</span><span class="sxs-lookup"><span data-stu-id="bdfc9-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<exposedMethod>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bdfc9-109">语法</span><span class="sxs-lookup"><span data-stu-id="bdfc9-109">Syntax</span></span>  
  
```xml  
<comContracts>
  <comContract>
    <exposedMethods>
      <exposedMethod name="String" />
    </exposedMethods>
  </comContract>
</comContracts>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bdfc9-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="bdfc9-110">Attributes and Elements</span></span>  
 <span data-ttu-id="bdfc9-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="bdfc9-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bdfc9-112">特性</span><span class="sxs-lookup"><span data-stu-id="bdfc9-112">Attributes</span></span>  
  
|<span data-ttu-id="bdfc9-113">特性</span><span class="sxs-lookup"><span data-stu-id="bdfc9-113">Attribute</span></span>|<span data-ttu-id="bdfc9-114">描述</span><span class="sxs-lookup"><span data-stu-id="bdfc9-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="bdfc9-115">NAME</span><span class="sxs-lookup"><span data-stu-id="bdfc9-115">name</span></span>|<span data-ttu-id="bdfc9-116">一个字符串，包含在 COM+ 组件上的接口作为 Web 服务公开时公开的 COM+ 方法。</span><span class="sxs-lookup"><span data-stu-id="bdfc9-116">A string that contains the COM+ method that is exposed when the interface on a COM+ component is exposed as a Web service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="bdfc9-117">子元素</span><span class="sxs-lookup"><span data-stu-id="bdfc9-117">Child Elements</span></span>  
 <span data-ttu-id="bdfc9-118">无。</span><span class="sxs-lookup"><span data-stu-id="bdfc9-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="bdfc9-119">父元素</span><span class="sxs-lookup"><span data-stu-id="bdfc9-119">Parent Elements</span></span>  
  
|<span data-ttu-id="bdfc9-120">元素</span><span class="sxs-lookup"><span data-stu-id="bdfc9-120">Element</span></span>|<span data-ttu-id="bdfc9-121">描述</span><span class="sxs-lookup"><span data-stu-id="bdfc9-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bdfc9-122">\<exposedMethods></span><span class="sxs-lookup"><span data-stu-id="bdfc9-122">\<exposedMethods></span></span>](exposedmethods.md)|<span data-ttu-id="bdfc9-123">ExposedMethod > 元素的集合。 [ \<](exposedmethod.md)</span><span class="sxs-lookup"><span data-stu-id="bdfc9-123">A collection of [\<exposedMethod>](exposedmethod.md) elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bdfc9-124">备注</span><span class="sxs-lookup"><span data-stu-id="bdfc9-124">Remarks</span></span>  
 <span data-ttu-id="bdfc9-125">可以使用 COM+ 集成配置工具 (ComSvcConfig.exe) 来添加 COM 接口中的特定方法，使其出现在生成的服务协定中。</span><span class="sxs-lookup"><span data-stu-id="bdfc9-125">The COM+ integration configuration tool (ComSvcConfig.exe) can be used to add specific methods from a COM interface to appear on the generated service contract.</span></span>  
  
 <span data-ttu-id="bdfc9-126">例如，可以使用以下命令将 `IFinances`.Financial 组件上的 `ItemOrders` COM 接口中的三个命名方法添加到生成的服务协定中。</span><span class="sxs-lookup"><span data-stu-id="bdfc9-126">For example, you can use the following command to add the three named methods from the `IFinances` COM interface on the `ItemOrders`.Financial component, to the generated service contract.</span></span>  
  
 `ComSvcConfig.exe /i /application:OnlineStore /contract:ItemOrders.Financial,IFinances.{TransferFunds,AddFunds,RemoveFunds} /hosting:complus`  
  
 <span data-ttu-id="bdfc9-127">当你同时运行 comsvcconfig.exe 时，它将生成以下服务协定，其中列出了前面提到的方法作为[ \<exposedMethod >](exposedmethod.md)元素。</span><span class="sxs-lookup"><span data-stu-id="bdfc9-127">When you also run the ComSvcConfig.exe, it then generates the following service contract listing the previously mentioned methods as [\<exposedMethod>](exposedmethod.md) elements.</span></span>  
  
```xml  
<comContract contractType="{C551FBA9-E3AA-4272-8C2A-84BD8D290AC7}"
             name="IFinances"
             namespace="http://contoso.com/services/financial">
  <exposedMethod name="TransferFunds"/>
  <exposedMethod name="AddFunds"/>
  <exposedMethod name="RemoveFunds"/>
</comContract>
```  
  
 <span data-ttu-id="bdfc9-128">在服务初始化时，运行时将尝试通过反射并仅添加[ \<exposedMethod >](exposedmethod.md)元素列表中包含的方法来生成服务协定。</span><span class="sxs-lookup"><span data-stu-id="bdfc9-128">At service initialization time, the runtime attempts to generate a service contract by reflecting over and adding only the methods included in the list of [\<exposedMethod>](exposedmethod.md) elements.</span></span> <span data-ttu-id="bdfc9-129">对于该服务协定中未包括的每个接口方法，都会产生一个跟踪。</span><span class="sxs-lookup"><span data-stu-id="bdfc9-129">A trace is produced for every interface method that is not included on the service contract.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bdfc9-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="bdfc9-130">See also</span></span>

- <xref:System.ServiceModel.Configuration.ComMethodElementCollection>
- <xref:System.ServiceModel.Configuration.ComMethodElement>
- [<span data-ttu-id="bdfc9-131">\<comContracts></span><span class="sxs-lookup"><span data-stu-id="bdfc9-131">\<comContracts></span></span>](comcontracts.md)
- [<span data-ttu-id="bdfc9-132">与 COM+ 应用程序集成</span><span class="sxs-lookup"><span data-stu-id="bdfc9-132">Integrating with COM+ Applications</span></span>](../../../wcf/feature-details/integrating-with-com-plus-applications.md)
- [<span data-ttu-id="bdfc9-133">如何：配置 COM + 服务设置</span><span class="sxs-lookup"><span data-stu-id="bdfc9-133">How to: Configure COM+ Service Settings</span></span>](../../../wcf/feature-details/how-to-configure-com-service-settings.md)
