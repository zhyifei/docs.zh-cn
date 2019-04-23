---
title: <service>
ms.date: 03/30/2017
ms.assetid: 13123dd6-c4a9-4a04-a984-df184b851788
ms.openlocfilehash: 68bddc01b02d9885b3f0fc4c2cbc5c3249de03f4
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59197953"
---
# <a name="service"></a><span data-ttu-id="71776-101">\<service></span><span class="sxs-lookup"><span data-stu-id="71776-101">\<service></span></span>
<span data-ttu-id="71776-102">`service` 元素包含 Windows Communication Foundation (WCF) 服务的设置。</span><span class="sxs-lookup"><span data-stu-id="71776-102">The `service` element contains the settings for a Windows Communication Foundation (WCF) service.</span></span> <span data-ttu-id="71776-103">它还包含公开此服务的终结点。</span><span class="sxs-lookup"><span data-stu-id="71776-103">It also contains endpoints that expose the service.</span></span>  
  
 <span data-ttu-id="71776-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="71776-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="71776-105">\<services></span><span class="sxs-lookup"><span data-stu-id="71776-105">\<services></span></span>  
<span data-ttu-id="71776-106">\<service></span><span class="sxs-lookup"><span data-stu-id="71776-106">\<service></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71776-107">语法</span><span class="sxs-lookup"><span data-stu-id="71776-107">Syntax</span></span>  
  
```xml  
<service behaviorConfiguration="String"
         name="String">
</service>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="71776-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="71776-108">Attributes and Elements</span></span>  
 <span data-ttu-id="71776-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="71776-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="71776-110">特性</span><span class="sxs-lookup"><span data-stu-id="71776-110">Attributes</span></span>  
  
|<span data-ttu-id="71776-111">特性</span><span class="sxs-lookup"><span data-stu-id="71776-111">Attribute</span></span>|<span data-ttu-id="71776-112">描述</span><span class="sxs-lookup"><span data-stu-id="71776-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="71776-113">behaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="71776-113">behaviorConfiguration</span></span>|<span data-ttu-id="71776-114">一个字符串，其中包含要用于实例化服务的行为的行为名。</span><span class="sxs-lookup"><span data-stu-id="71776-114">A string that contains the behavior name of the behavior to be used to instantiate the service.</span></span> <span data-ttu-id="71776-115">定义服务时，该行为名必须在作用域内。</span><span class="sxs-lookup"><span data-stu-id="71776-115">The behavior name must be in scope at the point the service is defined.</span></span> <span data-ttu-id="71776-116">默认值为一个空字符串。</span><span class="sxs-lookup"><span data-stu-id="71776-116">The default value is an empty string.</span></span>|  
|<span data-ttu-id="71776-117">name</span><span class="sxs-lookup"><span data-stu-id="71776-117">name</span></span>|<span data-ttu-id="71776-118">必需的字符串属性，此属性指定要进行实例化的服务的类型。</span><span class="sxs-lookup"><span data-stu-id="71776-118">Required String attribute that specifies the type of the service to be instantiated.</span></span> <span data-ttu-id="71776-119">此设置必须等同于一个有效类型。</span><span class="sxs-lookup"><span data-stu-id="71776-119">This setting must equate to a valid type.</span></span> <span data-ttu-id="71776-120">格式应为 `Namespace.Class.`</span><span class="sxs-lookup"><span data-stu-id="71776-120">The format should be `Namespace.Class.`</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="71776-121">子元素</span><span class="sxs-lookup"><span data-stu-id="71776-121">Child Elements</span></span>  
  
|<span data-ttu-id="71776-122">元素</span><span class="sxs-lookup"><span data-stu-id="71776-122">Element</span></span>|<span data-ttu-id="71776-123">描述</span><span class="sxs-lookup"><span data-stu-id="71776-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="71776-124">\<endpoint></span><span class="sxs-lookup"><span data-stu-id="71776-124">\<endpoint></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md)|<span data-ttu-id="71776-125">公开此服务的 `endpoint` 元素的集合。</span><span class="sxs-lookup"><span data-stu-id="71776-125">A collection of `endpoint` elements that expose this service.</span></span>|  
|[<span data-ttu-id="71776-126">\<host></span><span class="sxs-lookup"><span data-stu-id="71776-126">\<host></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/host.md)|<span data-ttu-id="71776-127">指定此服务实例的主机。</span><span class="sxs-lookup"><span data-stu-id="71776-127">Specifies the host of this service instance.</span></span> <span data-ttu-id="71776-128">此元素的类型为 <xref:System.ServiceModel.Configuration.HostElement>。</span><span class="sxs-lookup"><span data-stu-id="71776-128">This element is of type <xref:System.ServiceModel.Configuration.HostElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="71776-129">父元素</span><span class="sxs-lookup"><span data-stu-id="71776-129">Parent Elements</span></span>  
  
|<span data-ttu-id="71776-130">元素</span><span class="sxs-lookup"><span data-stu-id="71776-130">Element</span></span>|<span data-ttu-id="71776-131">描述</span><span class="sxs-lookup"><span data-stu-id="71776-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="71776-132">\<services></span><span class="sxs-lookup"><span data-stu-id="71776-132">\<services></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/services.md)|<span data-ttu-id="71776-133">所有 WCF 配置元素的根元素。</span><span class="sxs-lookup"><span data-stu-id="71776-133">The root element of all WCF configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="71776-134">备注</span><span class="sxs-lookup"><span data-stu-id="71776-134">Remarks</span></span>  
 <span data-ttu-id="71776-135">服务是在配置文件的 `services` 节中定义的。</span><span class="sxs-lookup"><span data-stu-id="71776-135">Services are defined in the `services` section of the configuration file.</span></span> <span data-ttu-id="71776-136">程序集可以包含任意多个服务。</span><span class="sxs-lookup"><span data-stu-id="71776-136">An assembly can contain any number of services.</span></span> <span data-ttu-id="71776-137">每个服务都有自己的 `service` 配置节。</span><span class="sxs-lookup"><span data-stu-id="71776-137">Each service has its own `service` configuration section.</span></span> <span data-ttu-id="71776-138">本节及其内容定义特定服务的服务协定、行为和终结点。</span><span class="sxs-lookup"><span data-stu-id="71776-138">This section and its content define the service contract, behavior, and endpoints of the particular service.</span></span>  
  
 <span data-ttu-id="71776-139">`behaviorConfiguration` 元素也是可选的。</span><span class="sxs-lookup"><span data-stu-id="71776-139">The `behaviorConfiguration` element is also optional.</span></span> <span data-ttu-id="71776-140">它标识服务使用的行为。</span><span class="sxs-lookup"><span data-stu-id="71776-140">It identifies the behavior the service uses.</span></span> <span data-ttu-id="71776-141">在此属性中指定的行为必须链接到同一配置文件中的作用域内的行为。</span><span class="sxs-lookup"><span data-stu-id="71776-141">The behavior specified in this attribute must link to a behavior in scope in the same configuration file.</span></span>  
  
 <span data-ttu-id="71776-142">每个服务都将公开一个或多个终结点，每个终结点具有自己的地址和绑定。</span><span class="sxs-lookup"><span data-stu-id="71776-142">Each service exposes one or more endpoints, which has its own address and binding.</span></span> <span data-ttu-id="71776-143">配置文件中使用的所有绑定都必须在该文件的范围内定义。</span><span class="sxs-lookup"><span data-stu-id="71776-143">All bindings used within the configuration file must be defined in the scope of the file.</span></span> <span data-ttu-id="71776-144">绑定通过 `name` 和 `bindingConfiguration` 属性的组合链接到终结点。</span><span class="sxs-lookup"><span data-stu-id="71776-144">Binding are linked to endpoints through the combination of the attributes `name` and `bindingConfiguration`.</span></span> <span data-ttu-id="71776-145">`name` 特性说明在哪个节中定义绑定。</span><span class="sxs-lookup"><span data-stu-id="71776-145">The `name` attribute describes the section the binding is defined in.</span></span> <span data-ttu-id="71776-146">`bindingConfiguration` 特性定义使用绑定节中的哪个配置。</span><span class="sxs-lookup"><span data-stu-id="71776-146">The `bindingConfiguration` attribute defines which configuration within the binding section is used.</span></span> <span data-ttu-id="71776-147">绑定节可以定义若干个配置。</span><span class="sxs-lookup"><span data-stu-id="71776-147">A binding section can define several configurations.</span></span>  
  
## <a name="example"></a><span data-ttu-id="71776-148">示例</span><span class="sxs-lookup"><span data-stu-id="71776-148">Example</span></span>  
 <span data-ttu-id="71776-149">这是服务配置的一个示例。</span><span class="sxs-lookup"><span data-stu-id="71776-149">This is an example of a service configuration.</span></span>  
  
```xml  
<service behaviorConfiguration="testChannelBehavior"
         name="HelloWorld">
  <endpoint address="/HelloWorld2/"
            name="test"
            bindingNamespace="http://www.cohowinery.com/"
            binding="basicHttpBinding"
            contract="IHelloWorld" />
</service>
```  
  
## <a name="see-also"></a><span data-ttu-id="71776-150">请参阅</span><span class="sxs-lookup"><span data-stu-id="71776-150">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceElement>
- [<span data-ttu-id="71776-151">配置服务</span><span class="sxs-lookup"><span data-stu-id="71776-151">Configuring Services</span></span>](../../../../../docs/framework/wcf/configuring-services.md)
