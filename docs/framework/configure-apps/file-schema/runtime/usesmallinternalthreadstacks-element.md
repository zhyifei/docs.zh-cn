---
title: <UseSmallInternalThreadStacks> 元素
ms.date: 03/30/2017
helpviewer_keywords:
- UseSmallInternalThreadStacks element
- <UseSmallInternalThreadStacks> element
ms.assetid: 1e3f6ec0-1cac-4e1c-9c81-17d948ae5874
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d78d03956db3f50b4d01f06c9a6438afd62fac5d
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2019
ms.locfileid: "55289791"
---
# <a name="usesmallinternalthreadstacks-element"></a><span data-ttu-id="e1baf-102">\<UseSmallInternalThreadStacks > 元素</span><span class="sxs-lookup"><span data-stu-id="e1baf-102">\<UseSmallInternalThreadStacks> Element</span></span>
<span data-ttu-id="e1baf-103">请求公共语言运行时 (CLR)，减少内存使用通过指定显式堆栈大小，当它创建的某些线程，它在内部使用，而不是使用这些线程的默认堆栈大小。</span><span class="sxs-lookup"><span data-stu-id="e1baf-103">Requests that the common language runtime (CLR) reduce memory use by specifying explicit stack sizes when it creates certain threads that it uses internally, instead of using the default stack size for those threads.</span></span>  
  
 <span data-ttu-id="e1baf-104">\<配置 > 元素</span><span class="sxs-lookup"><span data-stu-id="e1baf-104">\<configuration> Element</span></span>  
<span data-ttu-id="e1baf-105">\<运行时 > 元素</span><span class="sxs-lookup"><span data-stu-id="e1baf-105">\<runtime> Element</span></span>  
<span data-ttu-id="e1baf-106">\<UseSmallInternalThreadStacks > 元素</span><span class="sxs-lookup"><span data-stu-id="e1baf-106">\<UseSmallInternalThreadStacks> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e1baf-107">语法</span><span class="sxs-lookup"><span data-stu-id="e1baf-107">Syntax</span></span>  
  
```xml  
<UseSmallInternalThreadStacks enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e1baf-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="e1baf-108">Attributes and Elements</span></span>  
 <span data-ttu-id="e1baf-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="e1baf-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e1baf-110">特性</span><span class="sxs-lookup"><span data-stu-id="e1baf-110">Attributes</span></span>  
  
|<span data-ttu-id="e1baf-111">特性</span><span class="sxs-lookup"><span data-stu-id="e1baf-111">Attribute</span></span>|<span data-ttu-id="e1baf-112">描述</span><span class="sxs-lookup"><span data-stu-id="e1baf-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e1baf-113">enabled</span><span class="sxs-lookup"><span data-stu-id="e1baf-113">enabled</span></span>|<span data-ttu-id="e1baf-114">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="e1baf-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="e1baf-115">指定是否要求，CLR 使用显式堆栈大小，而不是默认堆栈大小时创建的某些线程，它在内部使用。</span><span class="sxs-lookup"><span data-stu-id="e1baf-115">Specifies whether to request that the CLR use explicit stack sizes instead of the default stack size when it creates certain threads that it uses internally.</span></span> <span data-ttu-id="e1baf-116">显式堆栈大小都小于 1 MB 的默认堆栈大小。</span><span class="sxs-lookup"><span data-stu-id="e1baf-116">The explicit stack sizes are smaller than the default stack size of 1 MB.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="e1baf-117">enabled 特性</span><span class="sxs-lookup"><span data-stu-id="e1baf-117">enabled Attribute</span></span>  
  
|<span data-ttu-id="e1baf-118">值</span><span class="sxs-lookup"><span data-stu-id="e1baf-118">Value</span></span>|<span data-ttu-id="e1baf-119">描述</span><span class="sxs-lookup"><span data-stu-id="e1baf-119">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="e1baf-120">true</span><span class="sxs-lookup"><span data-stu-id="e1baf-120">true</span></span>|<span data-ttu-id="e1baf-121">请求显式堆栈大小。</span><span class="sxs-lookup"><span data-stu-id="e1baf-121">Request explicit stack sizes.</span></span>|  
|<span data-ttu-id="e1baf-122">False</span><span class="sxs-lookup"><span data-stu-id="e1baf-122">false</span></span>|<span data-ttu-id="e1baf-123">使用默认堆栈大小。</span><span class="sxs-lookup"><span data-stu-id="e1baf-123">Use the default stack size.</span></span> <span data-ttu-id="e1baf-124">这是默认[!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="e1baf-124">This is the default for the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)].</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e1baf-125">子元素</span><span class="sxs-lookup"><span data-stu-id="e1baf-125">Child Elements</span></span>  
 <span data-ttu-id="e1baf-126">无。</span><span class="sxs-lookup"><span data-stu-id="e1baf-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e1baf-127">父元素</span><span class="sxs-lookup"><span data-stu-id="e1baf-127">Parent Elements</span></span>  
  
|<span data-ttu-id="e1baf-128">元素</span><span class="sxs-lookup"><span data-stu-id="e1baf-128">Element</span></span>|<span data-ttu-id="e1baf-129">描述</span><span class="sxs-lookup"><span data-stu-id="e1baf-129">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="e1baf-130">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="e1baf-130">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="e1baf-131">包含有关程序集绑定和垃圾回收的信息。</span><span class="sxs-lookup"><span data-stu-id="e1baf-131">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e1baf-132">备注</span><span class="sxs-lookup"><span data-stu-id="e1baf-132">Remarks</span></span>  
 <span data-ttu-id="e1baf-133">此配置元素用于请求降低了的虚拟内存使用在进程中，因为 CLR 如果接受请求，对其内部线程，使用显式线程大小小于默认大小。</span><span class="sxs-lookup"><span data-stu-id="e1baf-133">This configuration element is used to request reduced virtual memory use in a process, because the explicit thread sizes that the CLR uses for its internal threads, if the request is honored, are smaller than the default size.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="e1baf-134">此配置元素是对 CLR，而不是绝对要求的请求。</span><span class="sxs-lookup"><span data-stu-id="e1baf-134">This configuration element is a request to the CLR rather than an absolute requirement.</span></span> <span data-ttu-id="e1baf-135">在[!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)]，则请求响应仅针对 x86 体系结构。</span><span class="sxs-lookup"><span data-stu-id="e1baf-135">In the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], the request is honored only for the x86 architecture.</span></span> <span data-ttu-id="e1baf-136">此元素可能会在 CLR 的未来版本中完全忽略或替换为显式堆栈大小始终用于所选的内部线程。</span><span class="sxs-lookup"><span data-stu-id="e1baf-136">This element might be ignored completely in future versions of the CLR, or replaced by explicit stack sizes that are always used for selected internal threads.</span></span>  
  
 <span data-ttu-id="e1baf-137">指定此配置元素交易的可靠性较小的虚拟内存使用 CLR 允许该请求，但是否因为较小的堆栈大小可能会使堆栈更有可能溢出。</span><span class="sxs-lookup"><span data-stu-id="e1baf-137">Specifying this configuration element trades reliability for smaller virtual memory use if the CLR honors the request, because smaller stack sizes could potentially make stack overflows more likely.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e1baf-138">示例</span><span class="sxs-lookup"><span data-stu-id="e1baf-138">Example</span></span>  
 <span data-ttu-id="e1baf-139">下面的示例演示如何请求 CLR 使用显式堆栈调整某些大小在内部使用的线程。</span><span class="sxs-lookup"><span data-stu-id="e1baf-139">The following example shows how to request that the CLR use explicit stack sizes for certain threads that it uses internally.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <UseSmallInternalThreadStacks enabled="true" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e1baf-140">请参阅</span><span class="sxs-lookup"><span data-stu-id="e1baf-140">See also</span></span>
- [<span data-ttu-id="e1baf-141">运行时设置架构</span><span class="sxs-lookup"><span data-stu-id="e1baf-141">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="e1baf-142">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="e1baf-142">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
