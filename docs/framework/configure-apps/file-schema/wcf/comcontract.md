---
title: '&lt;comContract&gt;'
ms.date: 03/30/2017
ms.assetid: 3f8e1c0c-cfdf-4c79-ac65-c64e9323a51c
ms.openlocfilehash: e2addbada7f55076ae919d93c897991a7ec0fcd8
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/23/2018
ms.locfileid: "46703403"
---
# <a name="ltcomcontractgt"></a><span data-ttu-id="0e2f6-102">&lt;comContract&gt;</span><span class="sxs-lookup"><span data-stu-id="0e2f6-102">&lt;comContract&gt;</span></span>
<span data-ttu-id="0e2f6-103">指定 COM+ 集成服务协定。</span><span class="sxs-lookup"><span data-stu-id="0e2f6-103">Specifies a COM+ integration service contract.</span></span>  
  
 <span data-ttu-id="0e2f6-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="0e2f6-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="0e2f6-105">\<comContracts></span><span class="sxs-lookup"><span data-stu-id="0e2f6-105">\<comContracts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0e2f6-106">语法</span><span class="sxs-lookup"><span data-stu-id="0e2f6-106">Syntax</span></span>  
  
```xml  
<comContracts>  
  <comContract  
      contract="string"  
      namespace="string"  
      name="string"  
      requireSession="Boolean">  
      <exposedMethods>  
         <exposedMethod name="string" />  
      </exposedMethods>  
      <userDefinedTypes>  
         <userDefinedType name="string"  
            typeLibID="string"  
            typeLibVersion="string"  
            typeDefID="string">  
         </userDefinedType>  
      </userDefinedTypes>  
      <persistableTypes>  
         <persistableType id="string"  
            name="string">  
         </persistableType>  
      </persistableTypes>  
  </comContract>  
</comContracts>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0e2f6-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="0e2f6-107">Attributes and Elements</span></span>  
 <span data-ttu-id="0e2f6-108">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="0e2f6-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0e2f6-109">特性</span><span class="sxs-lookup"><span data-stu-id="0e2f6-109">Attributes</span></span>  
  
|<span data-ttu-id="0e2f6-110">特性</span><span class="sxs-lookup"><span data-stu-id="0e2f6-110">Attribute</span></span>|<span data-ttu-id="0e2f6-111">描述</span><span class="sxs-lookup"><span data-stu-id="0e2f6-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0e2f6-112">Contract — 协定</span><span class="sxs-lookup"><span data-stu-id="0e2f6-112">contract</span></span>|<span data-ttu-id="0e2f6-113">一个包含协定类型的字符串。</span><span class="sxs-lookup"><span data-stu-id="0e2f6-113">A string that contains the contract type.</span></span>|  
|<span data-ttu-id="0e2f6-114">name</span><span class="sxs-lookup"><span data-stu-id="0e2f6-114">name</span></span>|<span data-ttu-id="0e2f6-115">一个包含协定名称的字符串。</span><span class="sxs-lookup"><span data-stu-id="0e2f6-115">A string that contains the contract name.</span></span>|  
|<span data-ttu-id="0e2f6-116">namespace</span><span class="sxs-lookup"><span data-stu-id="0e2f6-116">namespace</span></span>|<span data-ttu-id="0e2f6-117">一个包含协定命名空间的字符串。</span><span class="sxs-lookup"><span data-stu-id="0e2f6-117">A string that contains the contract namespace.</span></span>|  
|<span data-ttu-id="0e2f6-118">requiresSession</span><span class="sxs-lookup"><span data-stu-id="0e2f6-118">requiresSession</span></span>|<span data-ttu-id="0e2f6-119">一个布尔值，指定是否只能在会话绑定上使用该协定。</span><span class="sxs-lookup"><span data-stu-id="0e2f6-119">A Boolean value that specifies whether the contract can only be used on sessionful bindings.</span></span> <span data-ttu-id="0e2f6-120">在初始化服务时，集成运行库可以确保此设置与要使用的绑定的类型一致。</span><span class="sxs-lookup"><span data-stu-id="0e2f6-120">When the service is initialized, the integration runtime ensures that this setting is consistent with the type of binding to be used.</span></span> <span data-ttu-id="0e2f6-121">如果协定的一个或多个绑定存在冲突，则会生成异常。</span><span class="sxs-lookup"><span data-stu-id="0e2f6-121">An exception is generated if one or more of the bindings for the contract are in conflict.</span></span> <span data-ttu-id="0e2f6-122">如果此属性为 `false`、使用的是单向通道并且存在任何 [out] 参数，则也会生成异常。</span><span class="sxs-lookup"><span data-stu-id="0e2f6-122">If this property is `false`, and a one-way channel is in use and there are any [out] parameters, an exception is also generated.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0e2f6-123">子元素</span><span class="sxs-lookup"><span data-stu-id="0e2f6-123">Child Elements</span></span>  
  
|<span data-ttu-id="0e2f6-124">元素</span><span class="sxs-lookup"><span data-stu-id="0e2f6-124">Element</span></span>|<span data-ttu-id="0e2f6-125">描述</span><span class="sxs-lookup"><span data-stu-id="0e2f6-125">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0e2f6-126">persistableTypes</span><span class="sxs-lookup"><span data-stu-id="0e2f6-126">persistableTypes</span></span>|<span data-ttu-id="0e2f6-127">所有持久类型。</span><span class="sxs-lookup"><span data-stu-id="0e2f6-127">All the persistable types.</span></span>|  
|<span data-ttu-id="0e2f6-128">userDefinedTypes</span><span class="sxs-lookup"><span data-stu-id="0e2f6-128">userDefinedTypes</span></span>|<span data-ttu-id="0e2f6-129">一个要包括在服务协定中的用户定义的类型 (UDT) 的集合。</span><span class="sxs-lookup"><span data-stu-id="0e2f6-129">A collection of User Defined Types (UDT) that is to be included in the service contract.</span></span>|  
|<span data-ttu-id="0e2f6-130">exposedMethods</span><span class="sxs-lookup"><span data-stu-id="0e2f6-130">exposedMethods</span></span>|<span data-ttu-id="0e2f6-131">一个在 COM+ 组件上的接口作为 Web 服务公开时所公开的 COM+ 方法的集合。</span><span class="sxs-lookup"><span data-stu-id="0e2f6-131">A collection of COM+ methods that are exposed when the interface on a COM+ component is exposed as a Web service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0e2f6-132">父元素</span><span class="sxs-lookup"><span data-stu-id="0e2f6-132">Parent Elements</span></span>  
  
|<span data-ttu-id="0e2f6-133">元素</span><span class="sxs-lookup"><span data-stu-id="0e2f6-133">Element</span></span>|<span data-ttu-id="0e2f6-134">描述</span><span class="sxs-lookup"><span data-stu-id="0e2f6-134">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0e2f6-135">comContracts</span><span class="sxs-lookup"><span data-stu-id="0e2f6-135">comContracts</span></span>|<span data-ttu-id="0e2f6-136">包含 `comContract` 元素的集合。</span><span class="sxs-lookup"><span data-stu-id="0e2f6-136">Contains a collection of `comContract` elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0e2f6-137">备注</span><span class="sxs-lookup"><span data-stu-id="0e2f6-137">Remarks</span></span>  
 <span data-ttu-id="0e2f6-138">COM + 集成服务协定是当前只限于`http://tempuri.org`命名空间，而从提供支持的 COM 接口派生的协定名称。</span><span class="sxs-lookup"><span data-stu-id="0e2f6-138">COM+ integration service contracts are currently restricted to the `http://tempuri.org` namespace, and contract name is derived from the supporting COM interface.</span></span> <span data-ttu-id="0e2f6-139">但是，可以使用配置文件中的 `comContracts` 节以及 `comContract` 元素来指定替代服务协定。</span><span class="sxs-lookup"><span data-stu-id="0e2f6-139">You can, however, specify alternatives by using the `comContracts` section, as well as the `comContract` element in the configuration file.</span></span> <span data-ttu-id="0e2f6-140">例如，可以使用下面的配置来指定服务协定的命名空间、协定名称、要包含的用户定义类型以及其他设置。</span><span class="sxs-lookup"><span data-stu-id="0e2f6-140">For example, you can use the following configuration to specify the namespace, contract name, and user defined types to be included, as well as other settings for a service contract.</span></span>  
  
```xml  
<comContracts>  
  <comContract  
      contract="{5163B1E7-F0CF-4B6A-9A02-4AB654F34284}"  
      namespace="http://tempuri.org/5163B1E7-F0CF-4B6A-9A02-4AB654F34284"  
      name="_Broker"  
      requireSession="true">  
      <exposedMethods>  
         <exposedMethod name="BuyStock" />  
         <exposedMethod name="SellStock" />  
         <exposedMethod name="ExecuteTransaction" />  
      </exposedMethods>  
  </comContract>  
</comContracts>  
```  
  
 <span data-ttu-id="0e2f6-141">在初始化服务时，指定的命名空间和协定名称将应用到生成的服务说明。</span><span class="sxs-lookup"><span data-stu-id="0e2f6-141">When the service is initialized, the specified namespaces and contract names are applied to the generated service descriptions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e2f6-142">请参阅</span><span class="sxs-lookup"><span data-stu-id="0e2f6-142">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ComContractElementCollection>  
 <xref:System.ServiceModel.Configuration.ComContractElementCollection>  
 <xref:System.ServiceModel.Configuration.ComContractElement>  
 [<span data-ttu-id="0e2f6-143">\<comContracts></span><span class="sxs-lookup"><span data-stu-id="0e2f6-143">\<comContracts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/comcontracts.md)  
 [<span data-ttu-id="0e2f6-144">与 COM+ 应用程序集成</span><span class="sxs-lookup"><span data-stu-id="0e2f6-144">Integrating with COM+ Applications</span></span>](../../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications.md)  
 [<span data-ttu-id="0e2f6-145">如何：配置 COM+ 服务设置</span><span class="sxs-lookup"><span data-stu-id="0e2f6-145">How to: Configure COM+ Service Settings</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-com-service-settings.md)
