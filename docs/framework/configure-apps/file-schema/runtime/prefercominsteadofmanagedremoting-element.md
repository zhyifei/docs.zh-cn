---
title: <PreferComInsteadOfManagedRemoting> 元素
ms.date: 03/30/2017
helpviewer_keywords:
- <PreferComInsteadOfManagedRemoting> element
- PreferComInsteadOfManagedRemoting element
ms.assetid: a279a42a-c415-4e79-88cf-64244ebda613
ms.openlocfilehash: 47c568a8d6e89a195414552b3db5953ee61d1e55
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73116018"
---
# <a name="prefercominsteadofmanagedremoting-element"></a><span data-ttu-id="e73d6-102">\<PreferComInsteadOfManagedRemoting > 元素</span><span class="sxs-lookup"><span data-stu-id="e73d6-102">\<PreferComInsteadOfManagedRemoting> Element</span></span>
<span data-ttu-id="e73d6-103">指定运行时是否将对跨应用程序域边界的所有调用使用 COM 互操作而不是远程处理。</span><span class="sxs-lookup"><span data-stu-id="e73d6-103">Specifies whether the runtime will use COM interop instead of remoting for all calls across application domain boundaries.</span></span>  
  
<span data-ttu-id="e73d6-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="e73d6-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="e73d6-105">&nbsp; &nbsp;[ **\<runtime >** ](runtime-element.md) </span><span class="sxs-lookup"><span data-stu-id="e73d6-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="e73d6-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<PreferComInsteadOfManagedRemoting >**</span><span class="sxs-lookup"><span data-stu-id="e73d6-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<PreferComInsteadOfManagedRemoting>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e73d6-107">语法</span><span class="sxs-lookup"><span data-stu-id="e73d6-107">Syntax</span></span>  
  
```xml  
<PreferComInsteadOfManagedRemoting enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e73d6-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="e73d6-108">Attributes and Elements</span></span>  
 <span data-ttu-id="e73d6-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="e73d6-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e73d6-110">特性</span><span class="sxs-lookup"><span data-stu-id="e73d6-110">Attributes</span></span>  
  
|<span data-ttu-id="e73d6-111">特性</span><span class="sxs-lookup"><span data-stu-id="e73d6-111">Attribute</span></span>|<span data-ttu-id="e73d6-112">描述</span><span class="sxs-lookup"><span data-stu-id="e73d6-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="e73d6-113">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="e73d6-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="e73d6-114">指示运行时是否将使用 COM 互操作，而不是跨应用程序域边界进行远程处理。</span><span class="sxs-lookup"><span data-stu-id="e73d6-114">Indicates whether the runtime will use COM interop instead of remoting across application domain boundaries.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="e73d6-115">enabled 特性</span><span class="sxs-lookup"><span data-stu-id="e73d6-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="e73d6-116">“值”</span><span class="sxs-lookup"><span data-stu-id="e73d6-116">Value</span></span>|<span data-ttu-id="e73d6-117">描述</span><span class="sxs-lookup"><span data-stu-id="e73d6-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="e73d6-118">运行时将跨应用程序域边界使用远程处理。</span><span class="sxs-lookup"><span data-stu-id="e73d6-118">The runtime will use remoting across application domain boundaries.</span></span> <span data-ttu-id="e73d6-119">这是默认设置。</span><span class="sxs-lookup"><span data-stu-id="e73d6-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="e73d6-120">运行时将跨应用程序域边界使用 COM 互操作。</span><span class="sxs-lookup"><span data-stu-id="e73d6-120">The runtime will use COM interop across application domain boundaries.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e73d6-121">子元素</span><span class="sxs-lookup"><span data-stu-id="e73d6-121">Child Elements</span></span>  
 <span data-ttu-id="e73d6-122">无。</span><span class="sxs-lookup"><span data-stu-id="e73d6-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e73d6-123">父元素</span><span class="sxs-lookup"><span data-stu-id="e73d6-123">Parent Elements</span></span>  
  
|<span data-ttu-id="e73d6-124">元素</span><span class="sxs-lookup"><span data-stu-id="e73d6-124">Element</span></span>|<span data-ttu-id="e73d6-125">描述</span><span class="sxs-lookup"><span data-stu-id="e73d6-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="e73d6-126">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="e73d6-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="e73d6-127">包含有关程序集绑定和垃圾回收的信息。</span><span class="sxs-lookup"><span data-stu-id="e73d6-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e73d6-128">备注</span><span class="sxs-lookup"><span data-stu-id="e73d6-128">Remarks</span></span>  
 <span data-ttu-id="e73d6-129">将 `enabled` 特性设置为 `true`时，运行时的行为如下所示：</span><span class="sxs-lookup"><span data-stu-id="e73d6-129">When you set the `enabled` attribute to `true`, the runtime behaves as follows:</span></span>  
  
- <span data-ttu-id="e73d6-130">当[iunknown](https://go.microsoft.com/fwlink/?LinkId=148003)接口通过 COM 接口进入域时，运行时不为[IManagedObject](../../../unmanaged-api/hosting/imanagedobject-interface.md)接口调用[iunknown：： QueryInterface](https://go.microsoft.com/fwlink/?LinkID=144867) 。</span><span class="sxs-lookup"><span data-stu-id="e73d6-130">The runtime does not call [IUnknown::QueryInterface](https://go.microsoft.com/fwlink/?LinkID=144867) for an [IManagedObject](../../../unmanaged-api/hosting/imanagedobject-interface.md) interface when an [IUnknown](https://go.microsoft.com/fwlink/?LinkId=148003) interface enters the domain through a COM interface.</span></span> <span data-ttu-id="e73d6-131">相反，它会在对象周围构造一个[运行时可调用包装](../../../../standard/native-interop/runtime-callable-wrapper.md)器（RCW）。</span><span class="sxs-lookup"><span data-stu-id="e73d6-131">Instead, it constructs a [Runtime Callable Wrapper](../../../../standard/native-interop/runtime-callable-wrapper.md) (RCW) around the object.</span></span>  
  
- <span data-ttu-id="e73d6-132">当运行时为已在此域中创建的任何[COM 可调用包装](../../../../standard/native-interop/com-callable-wrapper.md)器（CCW）接收针对[IManagedObject](../../../unmanaged-api/hosting/imanagedobject-interface.md)接口的 `QueryInterface` 调用时，将返回 E_NOINTERFACE。</span><span class="sxs-lookup"><span data-stu-id="e73d6-132">The runtime returns E_NOINTERFACE when it receives a `QueryInterface` call for an [IManagedObject](../../../unmanaged-api/hosting/imanagedobject-interface.md) interface for any [COM Callable Wrapper](../../../../standard/native-interop/com-callable-wrapper.md) (CCW) that has been created in this domain.</span></span>  
  
 <span data-ttu-id="e73d6-133">这两个行为确保跨应用程序域边界在托管对象之间对 COM 接口进行的所有调用均使用 COM 和 COM 互操作，而不是远程处理。</span><span class="sxs-lookup"><span data-stu-id="e73d6-133">These two behaviors ensure that all calls over COM interfaces between managed objects across application domain boundaries use COM and COM interop instead of remoting.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e73d6-134">示例</span><span class="sxs-lookup"><span data-stu-id="e73d6-134">Example</span></span>  
 <span data-ttu-id="e73d6-135">下面的示例演示如何指定运行时应跨隔离边界使用 COM 互操作：</span><span class="sxs-lookup"><span data-stu-id="e73d6-135">The following example shows how to specify that the runtime should use COM interop across isolation boundaries:</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <PreferComInsteadOfManagedRemoting enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e73d6-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="e73d6-136">See also</span></span>

- [<span data-ttu-id="e73d6-137">运行时设置架构</span><span class="sxs-lookup"><span data-stu-id="e73d6-137">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="e73d6-138">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="e73d6-138">Configuration File Schema</span></span>](../index.md)
