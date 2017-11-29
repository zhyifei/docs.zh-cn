---
title: "&lt;PreferComInsteadOfManagedRemoting&gt;元素"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- <PreferComInsteadOfManagedRemoting> element
- PreferComInsteadOfManagedRemoting element
ms.assetid: a279a42a-c415-4e79-88cf-64244ebda613
caps.latest.revision: "17"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7aed6baa227b2bdf90c26f02d38ee67c1ffbbda1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="ltprefercominsteadofmanagedremotinggt-element"></a><span data-ttu-id="3c7b1-102">&lt;PreferComInsteadOfManagedRemoting&gt;元素</span><span class="sxs-lookup"><span data-stu-id="3c7b1-102">&lt;PreferComInsteadOfManagedRemoting&gt; Element</span></span>
<span data-ttu-id="3c7b1-103">指定是否运行时将使用 COM 互操作而不是远程处理所有调用跨应用程序域边界。</span><span class="sxs-lookup"><span data-stu-id="3c7b1-103">Specifies whether the runtime will use COM interop instead of remoting for all calls across application domain boundaries.</span></span>  
  
 <span data-ttu-id="3c7b1-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="3c7b1-104">\<configuration></span></span>  
<span data-ttu-id="3c7b1-105">\<运行时 ></span><span class="sxs-lookup"><span data-stu-id="3c7b1-105">\<runtime></span></span>  
<span data-ttu-id="3c7b1-106">\<PreferComInsteadOfManagedRemoting ></span><span class="sxs-lookup"><span data-stu-id="3c7b1-106">\<PreferComInsteadOfManagedRemoting></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c7b1-107">语法</span><span class="sxs-lookup"><span data-stu-id="3c7b1-107">Syntax</span></span>  
  
```xml  
<PreferComInsteadOfManagedRemoting enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3c7b1-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="3c7b1-108">Attributes and Elements</span></span>  
 <span data-ttu-id="3c7b1-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="3c7b1-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3c7b1-110">特性</span><span class="sxs-lookup"><span data-stu-id="3c7b1-110">Attributes</span></span>  
  
|<span data-ttu-id="3c7b1-111">特性</span><span class="sxs-lookup"><span data-stu-id="3c7b1-111">Attribute</span></span>|<span data-ttu-id="3c7b1-112">描述</span><span class="sxs-lookup"><span data-stu-id="3c7b1-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="3c7b1-113">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="3c7b1-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="3c7b1-114">指示运行时将使用 COM 互操作而不是远程处理跨应用程序域边界。</span><span class="sxs-lookup"><span data-stu-id="3c7b1-114">Indicates whether the runtime will use COM interop instead of remoting across application domain boundaries.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="3c7b1-115">enabled 特性</span><span class="sxs-lookup"><span data-stu-id="3c7b1-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="3c7b1-116">值</span><span class="sxs-lookup"><span data-stu-id="3c7b1-116">Value</span></span>|<span data-ttu-id="3c7b1-117">描述</span><span class="sxs-lookup"><span data-stu-id="3c7b1-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="3c7b1-118">运行时将跨应用程序域边界使用远程处理。</span><span class="sxs-lookup"><span data-stu-id="3c7b1-118">The runtime will use remoting across application domain boundaries.</span></span> <span data-ttu-id="3c7b1-119">这是默认设置。</span><span class="sxs-lookup"><span data-stu-id="3c7b1-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="3c7b1-120">运行时将跨应用程序域边界使用 COM 互操作。</span><span class="sxs-lookup"><span data-stu-id="3c7b1-120">The runtime will use COM interop across application domain boundaries.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3c7b1-121">子元素</span><span class="sxs-lookup"><span data-stu-id="3c7b1-121">Child Elements</span></span>  
 <span data-ttu-id="3c7b1-122">无。</span><span class="sxs-lookup"><span data-stu-id="3c7b1-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3c7b1-123">父元素</span><span class="sxs-lookup"><span data-stu-id="3c7b1-123">Parent Elements</span></span>  
  
|<span data-ttu-id="3c7b1-124">元素</span><span class="sxs-lookup"><span data-stu-id="3c7b1-124">Element</span></span>|<span data-ttu-id="3c7b1-125">描述</span><span class="sxs-lookup"><span data-stu-id="3c7b1-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="3c7b1-126">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="3c7b1-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="3c7b1-127">包含有关程序集绑定和垃圾回收的信息。</span><span class="sxs-lookup"><span data-stu-id="3c7b1-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3c7b1-128">备注</span><span class="sxs-lookup"><span data-stu-id="3c7b1-128">Remarks</span></span>  
 <span data-ttu-id="3c7b1-129">当你将设置`enabled`属性设为`true`，运行时的行为，如下所示：</span><span class="sxs-lookup"><span data-stu-id="3c7b1-129">When you set the `enabled` attribute to `true`, the runtime behaves as follows:</span></span>  
  
-   <span data-ttu-id="3c7b1-130">运行时不会调用[iunknown:: Queryinterface](http://go.microsoft.com/fwlink/?LinkID=144867)为[IManagedObject](../../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md)接口时[IUnknown](http://go.microsoft.com/fwlink/?LinkId=148003)接口进入通过 COM 接口域。</span><span class="sxs-lookup"><span data-stu-id="3c7b1-130">The runtime does not call [IUnknown::QueryInterface](http://go.microsoft.com/fwlink/?LinkID=144867) for an [IManagedObject](../../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md) interface when an [IUnknown](http://go.microsoft.com/fwlink/?LinkId=148003) interface enters the domain through a COM interface.</span></span> <span data-ttu-id="3c7b1-131">相反，它构造[运行时可调用包装器](../../../../../docs/framework/interop/runtime-callable-wrapper.md)(RCW) 针对对象。</span><span class="sxs-lookup"><span data-stu-id="3c7b1-131">Instead, it constructs a [Runtime Callable Wrapper](../../../../../docs/framework/interop/runtime-callable-wrapper.md) (RCW) around the object.</span></span>  
  
-   <span data-ttu-id="3c7b1-132">在接收时，则运行时将返回 E_NOINTERFACE`QueryInterface`寻求[IManagedObject](../../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md)任何接口[COM 可调用包装](../../../../../docs/framework/interop/com-callable-wrapper.md)(CCW) 已在此域中创建。</span><span class="sxs-lookup"><span data-stu-id="3c7b1-132">The runtime returns E_NOINTERFACE when it receives a `QueryInterface` call for an [IManagedObject](../../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md) interface for any [COM Callable Wrapper](../../../../../docs/framework/interop/com-callable-wrapper.md) (CCW) that has been created in this domain.</span></span>  
  
 <span data-ttu-id="3c7b1-133">请确保这两种行为，COM 上的所有调用之间的都接口的托管的对象跨应用程序域边界使用 COM 和 COM 互操作而不是远程处理。</span><span class="sxs-lookup"><span data-stu-id="3c7b1-133">These two behaviors ensure that all calls over COM interfaces between managed objects across application domain boundaries use COM and COM interop instead of remoting.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3c7b1-134">示例</span><span class="sxs-lookup"><span data-stu-id="3c7b1-134">Example</span></span>  
 <span data-ttu-id="3c7b1-135">下面的示例演示如何指定运行时应使用 COM 互操作跨隔离边界：</span><span class="sxs-lookup"><span data-stu-id="3c7b1-135">The following example shows how to specify that the runtime should use COM interop across isolation boundaries:</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <PreferComInsteadOfManagedRemoting enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="3c7b1-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3c7b1-136">See Also</span></span>  
 [<span data-ttu-id="3c7b1-137">运行时设置架构</span><span class="sxs-lookup"><span data-stu-id="3c7b1-137">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="3c7b1-138">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="3c7b1-138">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
