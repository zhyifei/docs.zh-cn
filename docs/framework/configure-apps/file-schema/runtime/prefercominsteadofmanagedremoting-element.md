---
title: <PreferComInsteadOfManagedRemoting> 元素
ms.date: 03/30/2017
helpviewer_keywords:
- <PreferComInsteadOfManagedRemoting> element
- PreferComInsteadOfManagedRemoting element
ms.assetid: a279a42a-c415-4e79-88cf-64244ebda613
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c79c76717acf7ff309375313b30534dd0aff9399
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69920696"
---
# <a name="prefercominsteadofmanagedremoting-element"></a><span data-ttu-id="d2c4d-102">\<PreferComInsteadOfManagedRemoting > 元素</span><span class="sxs-lookup"><span data-stu-id="d2c4d-102">\<PreferComInsteadOfManagedRemoting> Element</span></span>
<span data-ttu-id="d2c4d-103">指定运行时是否将对跨应用程序域边界的所有调用使用 COM 互操作而不是远程处理。</span><span class="sxs-lookup"><span data-stu-id="d2c4d-103">Specifies whether the runtime will use COM interop instead of remoting for all calls across application domain boundaries.</span></span>  
  
 <span data-ttu-id="d2c4d-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="d2c4d-104">\<configuration></span></span>  
<span data-ttu-id="d2c4d-105">\<运行时 ></span><span class="sxs-lookup"><span data-stu-id="d2c4d-105">\<runtime></span></span>  
<span data-ttu-id="d2c4d-106">\<PreferComInsteadOfManagedRemoting></span><span class="sxs-lookup"><span data-stu-id="d2c4d-106">\<PreferComInsteadOfManagedRemoting></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d2c4d-107">语法</span><span class="sxs-lookup"><span data-stu-id="d2c4d-107">Syntax</span></span>  
  
```xml  
<PreferComInsteadOfManagedRemoting enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d2c4d-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="d2c4d-108">Attributes and Elements</span></span>  
 <span data-ttu-id="d2c4d-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="d2c4d-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d2c4d-110">特性</span><span class="sxs-lookup"><span data-stu-id="d2c4d-110">Attributes</span></span>  
  
|<span data-ttu-id="d2c4d-111">特性</span><span class="sxs-lookup"><span data-stu-id="d2c4d-111">Attribute</span></span>|<span data-ttu-id="d2c4d-112">描述</span><span class="sxs-lookup"><span data-stu-id="d2c4d-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="d2c4d-113">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="d2c4d-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="d2c4d-114">指示运行时是否将使用 COM 互操作, 而不是跨应用程序域边界进行远程处理。</span><span class="sxs-lookup"><span data-stu-id="d2c4d-114">Indicates whether the runtime will use COM interop instead of remoting across application domain boundaries.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="d2c4d-115">enabled 特性</span><span class="sxs-lookup"><span data-stu-id="d2c4d-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="d2c4d-116">值</span><span class="sxs-lookup"><span data-stu-id="d2c4d-116">Value</span></span>|<span data-ttu-id="d2c4d-117">描述</span><span class="sxs-lookup"><span data-stu-id="d2c4d-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="d2c4d-118">运行时将跨应用程序域边界使用远程处理。</span><span class="sxs-lookup"><span data-stu-id="d2c4d-118">The runtime will use remoting across application domain boundaries.</span></span> <span data-ttu-id="d2c4d-119">这是默认设置。</span><span class="sxs-lookup"><span data-stu-id="d2c4d-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="d2c4d-120">运行时将跨应用程序域边界使用 COM 互操作。</span><span class="sxs-lookup"><span data-stu-id="d2c4d-120">The runtime will use COM interop across application domain boundaries.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d2c4d-121">子元素</span><span class="sxs-lookup"><span data-stu-id="d2c4d-121">Child Elements</span></span>  
 <span data-ttu-id="d2c4d-122">无。</span><span class="sxs-lookup"><span data-stu-id="d2c4d-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d2c4d-123">父元素</span><span class="sxs-lookup"><span data-stu-id="d2c4d-123">Parent Elements</span></span>  
  
|<span data-ttu-id="d2c4d-124">元素</span><span class="sxs-lookup"><span data-stu-id="d2c4d-124">Element</span></span>|<span data-ttu-id="d2c4d-125">描述</span><span class="sxs-lookup"><span data-stu-id="d2c4d-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="d2c4d-126">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="d2c4d-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="d2c4d-127">包含有关程序集绑定和垃圾回收的信息。</span><span class="sxs-lookup"><span data-stu-id="d2c4d-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d2c4d-128">备注</span><span class="sxs-lookup"><span data-stu-id="d2c4d-128">Remarks</span></span>  
 <span data-ttu-id="d2c4d-129">将`enabled`属性设置为`true`时, 运行时的行为如下所示:</span><span class="sxs-lookup"><span data-stu-id="d2c4d-129">When you set the `enabled` attribute to `true`, the runtime behaves as follows:</span></span>  
  
- <span data-ttu-id="d2c4d-130">当[iunknown](https://go.microsoft.com/fwlink/?LinkId=148003)接口通过 COM 接口进入域时, 运行时不为[IManagedObject](../../../unmanaged-api/hosting/imanagedobject-interface.md)接口调用[iunknown:: QueryInterface](https://go.microsoft.com/fwlink/?LinkID=144867) 。</span><span class="sxs-lookup"><span data-stu-id="d2c4d-130">The runtime does not call [IUnknown::QueryInterface](https://go.microsoft.com/fwlink/?LinkID=144867) for an [IManagedObject](../../../unmanaged-api/hosting/imanagedobject-interface.md) interface when an [IUnknown](https://go.microsoft.com/fwlink/?LinkId=148003) interface enters the domain through a COM interface.</span></span> <span data-ttu-id="d2c4d-131">相反, 它会在对象周围构造一个[运行时可调用包装](../../../../standard/native-interop/runtime-callable-wrapper.md)器 (RCW)。</span><span class="sxs-lookup"><span data-stu-id="d2c4d-131">Instead, it constructs a [Runtime Callable Wrapper](../../../../standard/native-interop/runtime-callable-wrapper.md) (RCW) around the object.</span></span>  
  
- <span data-ttu-id="d2c4d-132">运行时在接收到`QueryInterface`已在此域中创建的任何 COM 可[调用包装](../../../../standard/native-interop/com-callable-wrapper.md)器 (CCW) 的[IManagedObject](../../../unmanaged-api/hosting/imanagedobject-interface.md)接口调用时, 将返回 E_NOINTERFACE。</span><span class="sxs-lookup"><span data-stu-id="d2c4d-132">The runtime returns E_NOINTERFACE when it receives a `QueryInterface` call for an [IManagedObject](../../../unmanaged-api/hosting/imanagedobject-interface.md) interface for any [COM Callable Wrapper](../../../../standard/native-interop/com-callable-wrapper.md) (CCW) that has been created in this domain.</span></span>  
  
 <span data-ttu-id="d2c4d-133">这两个行为确保跨应用程序域边界在托管对象之间对 COM 接口进行的所有调用均使用 COM 和 COM 互操作, 而不是远程处理。</span><span class="sxs-lookup"><span data-stu-id="d2c4d-133">These two behaviors ensure that all calls over COM interfaces between managed objects across application domain boundaries use COM and COM interop instead of remoting.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d2c4d-134">示例</span><span class="sxs-lookup"><span data-stu-id="d2c4d-134">Example</span></span>  
 <span data-ttu-id="d2c4d-135">下面的示例演示如何指定运行时应跨隔离边界使用 COM 互操作:</span><span class="sxs-lookup"><span data-stu-id="d2c4d-135">The following example shows how to specify that the runtime should use COM interop across isolation boundaries:</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <PreferComInsteadOfManagedRemoting enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d2c4d-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="d2c4d-136">See also</span></span>

- [<span data-ttu-id="d2c4d-137">运行时设置架构</span><span class="sxs-lookup"><span data-stu-id="d2c4d-137">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="d2c4d-138">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="d2c4d-138">Configuration File Schema</span></span>](../index.md)
