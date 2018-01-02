---
title: "&lt;服务&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 13123dd6-c4a9-4a04-a984-df184b851788
caps.latest.revision: "27"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 689dfae90baffa3e9895258d1635c7840d8df6b2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ltservicegt"></a><span data-ttu-id="3cbd3-102">&lt;服务&gt;</span><span class="sxs-lookup"><span data-stu-id="3cbd3-102">&lt;service&gt;</span></span>
<span data-ttu-id="3cbd3-103">`service` 元素包含 Windows Communication Foundation (WCF) 服务的设置。</span><span class="sxs-lookup"><span data-stu-id="3cbd3-103">The `service` element contains the settings for a Windows Communication Foundation (WCF) service.</span></span> <span data-ttu-id="3cbd3-104">它还包含公开此服务的终结点。</span><span class="sxs-lookup"><span data-stu-id="3cbd3-104">It also contains endpoints that expose the service.</span></span>  
  
 <span data-ttu-id="3cbd3-105">\<系统。ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="3cbd3-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="3cbd3-106">\<服务 ></span><span class="sxs-lookup"><span data-stu-id="3cbd3-106">\<services></span></span>  
<span data-ttu-id="3cbd3-107">\<服务 ></span><span class="sxs-lookup"><span data-stu-id="3cbd3-107">\<service></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3cbd3-108">语法</span><span class="sxs-lookup"><span data-stu-id="3cbd3-108">Syntax</span></span>  
  
```xml  
<service behaviorConfiguration=String"  
        name="String"  
</service>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3cbd3-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="3cbd3-109">Attributes and Elements</span></span>  
 <span data-ttu-id="3cbd3-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="3cbd3-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3cbd3-111">特性</span><span class="sxs-lookup"><span data-stu-id="3cbd3-111">Attributes</span></span>  
  
|<span data-ttu-id="3cbd3-112">特性</span><span class="sxs-lookup"><span data-stu-id="3cbd3-112">Attribute</span></span>|<span data-ttu-id="3cbd3-113">描述</span><span class="sxs-lookup"><span data-stu-id="3cbd3-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3cbd3-114">behaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="3cbd3-114">behaviorConfiguration</span></span>|<span data-ttu-id="3cbd3-115">一个字符串，其中包含要用于实例化服务的行为的行为名。</span><span class="sxs-lookup"><span data-stu-id="3cbd3-115">A string that contains the behavior name of the behavior to be used to instantiate the service.</span></span> <span data-ttu-id="3cbd3-116">定义服务时，该行为名必须在作用域内。</span><span class="sxs-lookup"><span data-stu-id="3cbd3-116">The behavior name must be in scope at the point the service is defined.</span></span> <span data-ttu-id="3cbd3-117">默认值为一个空字符串。</span><span class="sxs-lookup"><span data-stu-id="3cbd3-117">The default value is an empty string.</span></span>|  
|<span data-ttu-id="3cbd3-118">name</span><span class="sxs-lookup"><span data-stu-id="3cbd3-118">name</span></span>|<span data-ttu-id="3cbd3-119">必需的字符串属性，此属性指定要进行实例化的服务的类型。</span><span class="sxs-lookup"><span data-stu-id="3cbd3-119">Required String attribute that specifies the type of the service to be instantiated.</span></span> <span data-ttu-id="3cbd3-120">此设置必须等同于一个有效类型。</span><span class="sxs-lookup"><span data-stu-id="3cbd3-120">This setting must equate to a valid type.</span></span> <span data-ttu-id="3cbd3-121">格式应为 `Namespace.Class.`</span><span class="sxs-lookup"><span data-stu-id="3cbd3-121">The format should be `Namespace.Class.`</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3cbd3-122">子元素</span><span class="sxs-lookup"><span data-stu-id="3cbd3-122">Child Elements</span></span>  
  
|<span data-ttu-id="3cbd3-123">元素</span><span class="sxs-lookup"><span data-stu-id="3cbd3-123">Element</span></span>|<span data-ttu-id="3cbd3-124">描述</span><span class="sxs-lookup"><span data-stu-id="3cbd3-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3cbd3-125">\<终结点 ></span><span class="sxs-lookup"><span data-stu-id="3cbd3-125">\<endpoint></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md)|<span data-ttu-id="3cbd3-126">公开此服务的 `endpoint` 元素的集合。</span><span class="sxs-lookup"><span data-stu-id="3cbd3-126">A collection of `endpoint` elements that expose this service.</span></span>|  
|[<span data-ttu-id="3cbd3-127">\<主机 ></span><span class="sxs-lookup"><span data-stu-id="3cbd3-127">\<host></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/host.md)|<span data-ttu-id="3cbd3-128">指定此服务实例的主机。</span><span class="sxs-lookup"><span data-stu-id="3cbd3-128">Specifies the host of this service instance.</span></span> <span data-ttu-id="3cbd3-129">此元素的类型为 <xref:System.ServiceModel.Configuration.HostElement>。</span><span class="sxs-lookup"><span data-stu-id="3cbd3-129">This element is of type <xref:System.ServiceModel.Configuration.HostElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3cbd3-130">父元素</span><span class="sxs-lookup"><span data-stu-id="3cbd3-130">Parent Elements</span></span>  
  
|<span data-ttu-id="3cbd3-131">元素</span><span class="sxs-lookup"><span data-stu-id="3cbd3-131">Element</span></span>|<span data-ttu-id="3cbd3-132">描述</span><span class="sxs-lookup"><span data-stu-id="3cbd3-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3cbd3-133">\<服务 ></span><span class="sxs-lookup"><span data-stu-id="3cbd3-133">\<services></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/services.md)|<span data-ttu-id="3cbd3-134">所有 WCF 配置元素的根元素。</span><span class="sxs-lookup"><span data-stu-id="3cbd3-134">The root element of all WCF configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3cbd3-135">备注</span><span class="sxs-lookup"><span data-stu-id="3cbd3-135">Remarks</span></span>  
 <span data-ttu-id="3cbd3-136">服务是在配置文件的 `services` 节中定义的。</span><span class="sxs-lookup"><span data-stu-id="3cbd3-136">Services are defined in the `services` section of the configuration file.</span></span> <span data-ttu-id="3cbd3-137">程序集可以包含任意多个服务。</span><span class="sxs-lookup"><span data-stu-id="3cbd3-137">An assembly can contain any number of services.</span></span> <span data-ttu-id="3cbd3-138">每个服务都有自己的 `service` 配置节。</span><span class="sxs-lookup"><span data-stu-id="3cbd3-138">Each service has its own `service` configuration section.</span></span> <span data-ttu-id="3cbd3-139">本节及其内容定义特定服务的服务协定、行为和终结点。</span><span class="sxs-lookup"><span data-stu-id="3cbd3-139">This section and its content define the service contract, behavior, and endpoints of the particular service.</span></span>  
  
 <span data-ttu-id="3cbd3-140">`behaviorConfiguration` 元素也是可选的。</span><span class="sxs-lookup"><span data-stu-id="3cbd3-140">The `behaviorConfiguration` element is also optional.</span></span> <span data-ttu-id="3cbd3-141">它标识服务使用的行为。</span><span class="sxs-lookup"><span data-stu-id="3cbd3-141">It identifies the behavior the service uses.</span></span> <span data-ttu-id="3cbd3-142">在此属性中指定的行为必须链接到同一配置文件中的作用域内的行为。</span><span class="sxs-lookup"><span data-stu-id="3cbd3-142">The behavior specified in this attribute must link to a behavior in scope in the same configuration file.</span></span>  
  
 <span data-ttu-id="3cbd3-143">每个服务都将公开一个或多个终结点，每个终结点具有自己的地址和绑定。</span><span class="sxs-lookup"><span data-stu-id="3cbd3-143">Each service exposes one or more endpoints, which has its own address and binding.</span></span> <span data-ttu-id="3cbd3-144">配置文件中使用的所有绑定都必须在该文件的范围内定义。</span><span class="sxs-lookup"><span data-stu-id="3cbd3-144">All bindings used within the configuration file must be defined in the scope of the file.</span></span> <span data-ttu-id="3cbd3-145">绑定通过 `name` 和 `bindingConfiguration` 属性的组合链接到终结点。</span><span class="sxs-lookup"><span data-stu-id="3cbd3-145">Binding are linked to endpoints through the combination of the attributes `name` and `bindingConfiguration`.</span></span> <span data-ttu-id="3cbd3-146">`name` 特性说明在哪个节中定义绑定。</span><span class="sxs-lookup"><span data-stu-id="3cbd3-146">The `name` attribute describes the section the binding is defined in.</span></span> <span data-ttu-id="3cbd3-147">`bindingConfiguration` 特性定义使用绑定节中的哪个配置。</span><span class="sxs-lookup"><span data-stu-id="3cbd3-147">The `bindingConfiguration` attribute defines which configuration within the binding section is used.</span></span> <span data-ttu-id="3cbd3-148">绑定节可以定义若干个配置。</span><span class="sxs-lookup"><span data-stu-id="3cbd3-148">A binding section can define several configurations.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3cbd3-149">示例</span><span class="sxs-lookup"><span data-stu-id="3cbd3-149">Example</span></span>  
 <span data-ttu-id="3cbd3-150">这是服务配置的一个示例。</span><span class="sxs-lookup"><span data-stu-id="3cbd3-150">This is an example of a service configuration.</span></span>  
  
```xml  
<service behaviorConfiguration="testChannelBehavior"   
     name="HelloWorld">  
     <endpoint   
        address="/HelloWorld2/"  
        name="test"  
        bindingNamespace="http://www.cohowinery.com/"  
        binding="basicHttpBinding"  
        contract="IHelloWorld" />  
</service>  
```  
  
## <a name="see-also"></a><span data-ttu-id="3cbd3-151">请参阅</span><span class="sxs-lookup"><span data-stu-id="3cbd3-151">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ServiceElement>  
 [<span data-ttu-id="3cbd3-152">配置服务</span><span class="sxs-lookup"><span data-stu-id="3cbd3-152">Configuring Services</span></span>](../../../../../docs/framework/wcf/configuring-services.md)
