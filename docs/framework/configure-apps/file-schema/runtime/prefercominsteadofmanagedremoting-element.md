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
ms.workload: dotnet
ms.openlocfilehash: ad60d73e30bf02fd52f9c8f3bd707b571959bdd0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ltprefercominsteadofmanagedremotinggt-element"></a><span data-ttu-id="4ddce-102">&lt;PreferComInsteadOfManagedRemoting&gt;元素</span><span class="sxs-lookup"><span data-stu-id="4ddce-102">&lt;PreferComInsteadOfManagedRemoting&gt; Element</span></span>
<span data-ttu-id="4ddce-103">指定是否运行时将使用 COM 互操作而不是远程处理所有调用跨应用程序域边界。</span><span class="sxs-lookup"><span data-stu-id="4ddce-103">Specifies whether the runtime will use COM interop instead of remoting for all calls across application domain boundaries.</span></span>  
  
 <span data-ttu-id="4ddce-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="4ddce-104">\<configuration></span></span>  
<span data-ttu-id="4ddce-105">\<运行时 ></span><span class="sxs-lookup"><span data-stu-id="4ddce-105">\<runtime></span></span>  
<span data-ttu-id="4ddce-106">\<PreferComInsteadOfManagedRemoting ></span><span class="sxs-lookup"><span data-stu-id="4ddce-106">\<PreferComInsteadOfManagedRemoting></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4ddce-107">语法</span><span class="sxs-lookup"><span data-stu-id="4ddce-107">Syntax</span></span>  
  
```xml  
<PreferComInsteadOfManagedRemoting enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4ddce-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="4ddce-108">Attributes and Elements</span></span>  
 <span data-ttu-id="4ddce-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="4ddce-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4ddce-110">特性</span><span class="sxs-lookup"><span data-stu-id="4ddce-110">Attributes</span></span>  
  
|<span data-ttu-id="4ddce-111">特性</span><span class="sxs-lookup"><span data-stu-id="4ddce-111">Attribute</span></span>|<span data-ttu-id="4ddce-112">描述</span><span class="sxs-lookup"><span data-stu-id="4ddce-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="4ddce-113">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="4ddce-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="4ddce-114">指示运行时将使用 COM 互操作而不是远程处理跨应用程序域边界。</span><span class="sxs-lookup"><span data-stu-id="4ddce-114">Indicates whether the runtime will use COM interop instead of remoting across application domain boundaries.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="4ddce-115">enabled 特性</span><span class="sxs-lookup"><span data-stu-id="4ddce-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="4ddce-116">值</span><span class="sxs-lookup"><span data-stu-id="4ddce-116">Value</span></span>|<span data-ttu-id="4ddce-117">描述</span><span class="sxs-lookup"><span data-stu-id="4ddce-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="4ddce-118">运行时将跨应用程序域边界使用远程处理。</span><span class="sxs-lookup"><span data-stu-id="4ddce-118">The runtime will use remoting across application domain boundaries.</span></span> <span data-ttu-id="4ddce-119">这是默认设置。</span><span class="sxs-lookup"><span data-stu-id="4ddce-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="4ddce-120">运行时将跨应用程序域边界使用 COM 互操作。</span><span class="sxs-lookup"><span data-stu-id="4ddce-120">The runtime will use COM interop across application domain boundaries.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4ddce-121">子元素</span><span class="sxs-lookup"><span data-stu-id="4ddce-121">Child Elements</span></span>  
 <span data-ttu-id="4ddce-122">无。</span><span class="sxs-lookup"><span data-stu-id="4ddce-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4ddce-123">父元素</span><span class="sxs-lookup"><span data-stu-id="4ddce-123">Parent Elements</span></span>  
  
|<span data-ttu-id="4ddce-124">元素</span><span class="sxs-lookup"><span data-stu-id="4ddce-124">Element</span></span>|<span data-ttu-id="4ddce-125">说明</span><span class="sxs-lookup"><span data-stu-id="4ddce-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="4ddce-126">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="4ddce-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="4ddce-127">包含有关程序集绑定和垃圾回收的信息。</span><span class="sxs-lookup"><span data-stu-id="4ddce-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4ddce-128">备注</span><span class="sxs-lookup"><span data-stu-id="4ddce-128">Remarks</span></span>  
 <span data-ttu-id="4ddce-129">当你将设置`enabled`属性设为`true`，运行时的行为，如下所示：</span><span class="sxs-lookup"><span data-stu-id="4ddce-129">When you set the `enabled` attribute to `true`, the runtime behaves as follows:</span></span>  
  
-   <span data-ttu-id="4ddce-130">运行时不会调用[iunknown:: Queryinterface](http://go.microsoft.com/fwlink/?LinkID=144867)为[IManagedObject](../../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md)接口时[IUnknown](http://go.microsoft.com/fwlink/?LinkId=148003)接口进入通过 COM 接口域。</span><span class="sxs-lookup"><span data-stu-id="4ddce-130">The runtime does not call [IUnknown::QueryInterface](http://go.microsoft.com/fwlink/?LinkID=144867) for an [IManagedObject](../../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md) interface when an [IUnknown](http://go.microsoft.com/fwlink/?LinkId=148003) interface enters the domain through a COM interface.</span></span> <span data-ttu-id="4ddce-131">相反，它构造[运行时可调用包装器](../../../../../docs/framework/interop/runtime-callable-wrapper.md)(RCW) 针对对象。</span><span class="sxs-lookup"><span data-stu-id="4ddce-131">Instead, it constructs a [Runtime Callable Wrapper](../../../../../docs/framework/interop/runtime-callable-wrapper.md) (RCW) around the object.</span></span>  
  
-   <span data-ttu-id="4ddce-132">在接收时，则运行时将返回 E_NOINTERFACE`QueryInterface`寻求[IManagedObject](../../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md)任何接口[COM 可调用包装](../../../../../docs/framework/interop/com-callable-wrapper.md)(CCW) 已在此域中创建。</span><span class="sxs-lookup"><span data-stu-id="4ddce-132">The runtime returns E_NOINTERFACE when it receives a `QueryInterface` call for an [IManagedObject](../../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md) interface for any [COM Callable Wrapper](../../../../../docs/framework/interop/com-callable-wrapper.md) (CCW) that has been created in this domain.</span></span>  
  
 <span data-ttu-id="4ddce-133">请确保这两种行为，COM 上的所有调用之间的都接口的托管的对象跨应用程序域边界使用 COM 和 COM 互操作而不是远程处理。</span><span class="sxs-lookup"><span data-stu-id="4ddce-133">These two behaviors ensure that all calls over COM interfaces between managed objects across application domain boundaries use COM and COM interop instead of remoting.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4ddce-134">示例</span><span class="sxs-lookup"><span data-stu-id="4ddce-134">Example</span></span>  
 <span data-ttu-id="4ddce-135">下面的示例演示如何指定运行时应使用 COM 互操作跨隔离边界：</span><span class="sxs-lookup"><span data-stu-id="4ddce-135">The following example shows how to specify that the runtime should use COM interop across isolation boundaries:</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <PreferComInsteadOfManagedRemoting enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="4ddce-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="4ddce-136">See Also</span></span>  
 [<span data-ttu-id="4ddce-137">运行时设置架构</span><span class="sxs-lookup"><span data-stu-id="4ddce-137">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="4ddce-138">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="4ddce-138">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
