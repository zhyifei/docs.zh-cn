---
title: '&lt;PreferComInsteadOfManagedRemoting&gt;元素'
ms.date: 03/30/2017
helpviewer_keywords:
- <PreferComInsteadOfManagedRemoting> element
- PreferComInsteadOfManagedRemoting element
ms.assetid: a279a42a-c415-4e79-88cf-64244ebda613
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c05e27226a58086c806e8977ba50a55873d1167e
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/05/2018
ms.locfileid: "43735883"
---
# <a name="ltprefercominsteadofmanagedremotinggt-element"></a><span data-ttu-id="70c98-102">&lt;PreferComInsteadOfManagedRemoting&gt;元素</span><span class="sxs-lookup"><span data-stu-id="70c98-102">&lt;PreferComInsteadOfManagedRemoting&gt; Element</span></span>
<span data-ttu-id="70c98-103">指定是否在运行时将使用 COM 互操作而不是远程处理的所有调用跨应用程序域边界。</span><span class="sxs-lookup"><span data-stu-id="70c98-103">Specifies whether the runtime will use COM interop instead of remoting for all calls across application domain boundaries.</span></span>  
  
 <span data-ttu-id="70c98-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="70c98-104">\<configuration></span></span>  
<span data-ttu-id="70c98-105">\<运行时 ></span><span class="sxs-lookup"><span data-stu-id="70c98-105">\<runtime></span></span>  
<span data-ttu-id="70c98-106">\<PreferComInsteadOfManagedRemoting ></span><span class="sxs-lookup"><span data-stu-id="70c98-106">\<PreferComInsteadOfManagedRemoting></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="70c98-107">语法</span><span class="sxs-lookup"><span data-stu-id="70c98-107">Syntax</span></span>  
  
```xml  
<PreferComInsteadOfManagedRemoting enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="70c98-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="70c98-108">Attributes and Elements</span></span>  
 <span data-ttu-id="70c98-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="70c98-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="70c98-110">特性</span><span class="sxs-lookup"><span data-stu-id="70c98-110">Attributes</span></span>  
  
|<span data-ttu-id="70c98-111">特性</span><span class="sxs-lookup"><span data-stu-id="70c98-111">Attribute</span></span>|<span data-ttu-id="70c98-112">描述</span><span class="sxs-lookup"><span data-stu-id="70c98-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="70c98-113">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="70c98-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="70c98-114">指示是否在运行时将跨应用程序域边界而不是远程处理中使用 COM 互操作。</span><span class="sxs-lookup"><span data-stu-id="70c98-114">Indicates whether the runtime will use COM interop instead of remoting across application domain boundaries.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="70c98-115">enabled 特性</span><span class="sxs-lookup"><span data-stu-id="70c98-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="70c98-116">值</span><span class="sxs-lookup"><span data-stu-id="70c98-116">Value</span></span>|<span data-ttu-id="70c98-117">描述</span><span class="sxs-lookup"><span data-stu-id="70c98-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="70c98-118">在运行时将使用远程处理跨应用程序域边界。</span><span class="sxs-lookup"><span data-stu-id="70c98-118">The runtime will use remoting across application domain boundaries.</span></span> <span data-ttu-id="70c98-119">这是默认设置。</span><span class="sxs-lookup"><span data-stu-id="70c98-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="70c98-120">运行时将跨应用程序域边界使用 COM 互操作。</span><span class="sxs-lookup"><span data-stu-id="70c98-120">The runtime will use COM interop across application domain boundaries.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="70c98-121">子元素</span><span class="sxs-lookup"><span data-stu-id="70c98-121">Child Elements</span></span>  
 <span data-ttu-id="70c98-122">无。</span><span class="sxs-lookup"><span data-stu-id="70c98-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="70c98-123">父元素</span><span class="sxs-lookup"><span data-stu-id="70c98-123">Parent Elements</span></span>  
  
|<span data-ttu-id="70c98-124">元素</span><span class="sxs-lookup"><span data-stu-id="70c98-124">Element</span></span>|<span data-ttu-id="70c98-125">描述</span><span class="sxs-lookup"><span data-stu-id="70c98-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="70c98-126">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="70c98-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="70c98-127">包含有关程序集绑定和垃圾回收的信息。</span><span class="sxs-lookup"><span data-stu-id="70c98-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="70c98-128">备注</span><span class="sxs-lookup"><span data-stu-id="70c98-128">Remarks</span></span>  
 <span data-ttu-id="70c98-129">当您将设置`enabled`属性为`true`，运行时的行为，如下所示：</span><span class="sxs-lookup"><span data-stu-id="70c98-129">When you set the `enabled` attribute to `true`, the runtime behaves as follows:</span></span>  
  
-   <span data-ttu-id="70c98-130">在运行时不会调用[iunknown:: Queryinterface](https://go.microsoft.com/fwlink/?LinkID=144867)有关[IManagedObject](../../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md)接口时[IUnknown](https://go.microsoft.com/fwlink/?LinkId=148003)接口进入域通过 COM 接口。</span><span class="sxs-lookup"><span data-stu-id="70c98-130">The runtime does not call [IUnknown::QueryInterface](https://go.microsoft.com/fwlink/?LinkID=144867) for an [IManagedObject](../../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md) interface when an [IUnknown](https://go.microsoft.com/fwlink/?LinkId=148003) interface enters the domain through a COM interface.</span></span> <span data-ttu-id="70c98-131">相反，它构造[运行时可调用包装器](../../../../../docs/framework/interop/runtime-callable-wrapper.md)(RCW) 对象周围。</span><span class="sxs-lookup"><span data-stu-id="70c98-131">Instead, it constructs a [Runtime Callable Wrapper](../../../../../docs/framework/interop/runtime-callable-wrapper.md) (RCW) around the object.</span></span>  
  
-   <span data-ttu-id="70c98-132">在接收时，运行时将返回 E_NOINTERFACE`QueryInterface`寻求[IManagedObject](../../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md)接口的任何[COM 可调用包装器](../../../../../docs/framework/interop/com-callable-wrapper.md)(CCW) 已在此域中创建。</span><span class="sxs-lookup"><span data-stu-id="70c98-132">The runtime returns E_NOINTERFACE when it receives a `QueryInterface` call for an [IManagedObject](../../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md) interface for any [COM Callable Wrapper](../../../../../docs/framework/interop/com-callable-wrapper.md) (CCW) that has been created in this domain.</span></span>  
  
 <span data-ttu-id="70c98-133">请确保这两种行为，COM 上的所有调用之间的都接口的托管的对象跨应用程序域边界使用 COM 和 COM 互操作而不是远程处理。</span><span class="sxs-lookup"><span data-stu-id="70c98-133">These two behaviors ensure that all calls over COM interfaces between managed objects across application domain boundaries use COM and COM interop instead of remoting.</span></span>  
  
## <a name="example"></a><span data-ttu-id="70c98-134">示例</span><span class="sxs-lookup"><span data-stu-id="70c98-134">Example</span></span>  
 <span data-ttu-id="70c98-135">下面的示例演示如何指定运行时应使用 COM 互操作跨隔离边界：</span><span class="sxs-lookup"><span data-stu-id="70c98-135">The following example shows how to specify that the runtime should use COM interop across isolation boundaries:</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <PreferComInsteadOfManagedRemoting enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="70c98-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="70c98-136">See Also</span></span>  
 [<span data-ttu-id="70c98-137">运行时设置架构</span><span class="sxs-lookup"><span data-stu-id="70c98-137">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="70c98-138">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="70c98-138">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
