---
title: <UseSmallInternalThreadStacks> 元素
ms.date: 03/30/2017
helpviewer_keywords:
- UseSmallInternalThreadStacks element
- <UseSmallInternalThreadStacks> element
ms.assetid: 1e3f6ec0-1cac-4e1c-9c81-17d948ae5874
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8ee4df12a017429de333dd4e93df27973b658dad
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69920668"
---
# <a name="usesmallinternalthreadstacks-element"></a><span data-ttu-id="a7bde-102">\<UseSmallInternalThreadStacks > 元素</span><span class="sxs-lookup"><span data-stu-id="a7bde-102">\<UseSmallInternalThreadStacks> Element</span></span>
<span data-ttu-id="a7bde-103">请求公共语言运行时 (CLR) 在创建其内部使用的某些线程时, 通过指定显式堆栈大小来减少内存使用, 而不是使用这些线程的默认堆栈大小。</span><span class="sxs-lookup"><span data-stu-id="a7bde-103">Requests that the common language runtime (CLR) reduce memory use by specifying explicit stack sizes when it creates certain threads that it uses internally, instead of using the default stack size for those threads.</span></span>  
  
 <span data-ttu-id="a7bde-104">\<配置 > 元素</span><span class="sxs-lookup"><span data-stu-id="a7bde-104">\<configuration> Element</span></span>  
<span data-ttu-id="a7bde-105">\<运行时 > 元素</span><span class="sxs-lookup"><span data-stu-id="a7bde-105">\<runtime> Element</span></span>  
<span data-ttu-id="a7bde-106">\<UseSmallInternalThreadStacks > 元素</span><span class="sxs-lookup"><span data-stu-id="a7bde-106">\<UseSmallInternalThreadStacks> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7bde-107">语法</span><span class="sxs-lookup"><span data-stu-id="a7bde-107">Syntax</span></span>  
  
```xml  
<UseSmallInternalThreadStacks enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a7bde-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="a7bde-108">Attributes and Elements</span></span>  
 <span data-ttu-id="a7bde-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="a7bde-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a7bde-110">特性</span><span class="sxs-lookup"><span data-stu-id="a7bde-110">Attributes</span></span>  
  
|<span data-ttu-id="a7bde-111">特性</span><span class="sxs-lookup"><span data-stu-id="a7bde-111">Attribute</span></span>|<span data-ttu-id="a7bde-112">描述</span><span class="sxs-lookup"><span data-stu-id="a7bde-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a7bde-113">enabled</span><span class="sxs-lookup"><span data-stu-id="a7bde-113">enabled</span></span>|<span data-ttu-id="a7bde-114">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="a7bde-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="a7bde-115">指定是否请求 CLR 在创建其内部使用的某些线程时使用显式堆栈大小而不是默认堆栈大小。</span><span class="sxs-lookup"><span data-stu-id="a7bde-115">Specifies whether to request that the CLR use explicit stack sizes instead of the default stack size when it creates certain threads that it uses internally.</span></span> <span data-ttu-id="a7bde-116">显式堆栈大小小于默认堆栈大小 1 MB。</span><span class="sxs-lookup"><span data-stu-id="a7bde-116">The explicit stack sizes are smaller than the default stack size of 1 MB.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="a7bde-117">enabled 特性</span><span class="sxs-lookup"><span data-stu-id="a7bde-117">enabled Attribute</span></span>  
  
|<span data-ttu-id="a7bde-118">值</span><span class="sxs-lookup"><span data-stu-id="a7bde-118">Value</span></span>|<span data-ttu-id="a7bde-119">描述</span><span class="sxs-lookup"><span data-stu-id="a7bde-119">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a7bde-120">真</span><span class="sxs-lookup"><span data-stu-id="a7bde-120">true</span></span>|<span data-ttu-id="a7bde-121">请求显式堆栈大小。</span><span class="sxs-lookup"><span data-stu-id="a7bde-121">Request explicit stack sizes.</span></span>|  
|<span data-ttu-id="a7bde-122">假</span><span class="sxs-lookup"><span data-stu-id="a7bde-122">false</span></span>|<span data-ttu-id="a7bde-123">使用默认堆栈大小。</span><span class="sxs-lookup"><span data-stu-id="a7bde-123">Use the default stack size.</span></span> <span data-ttu-id="a7bde-124">这是 .NET Framework 4 的默认值。</span><span class="sxs-lookup"><span data-stu-id="a7bde-124">This is the default for the .NET Framework 4.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a7bde-125">子元素</span><span class="sxs-lookup"><span data-stu-id="a7bde-125">Child Elements</span></span>  
 <span data-ttu-id="a7bde-126">无。</span><span class="sxs-lookup"><span data-stu-id="a7bde-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a7bde-127">父元素</span><span class="sxs-lookup"><span data-stu-id="a7bde-127">Parent Elements</span></span>  
  
|<span data-ttu-id="a7bde-128">元素</span><span class="sxs-lookup"><span data-stu-id="a7bde-128">Element</span></span>|<span data-ttu-id="a7bde-129">描述</span><span class="sxs-lookup"><span data-stu-id="a7bde-129">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="a7bde-130">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="a7bde-130">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="a7bde-131">包含有关程序集绑定和垃圾回收的信息。</span><span class="sxs-lookup"><span data-stu-id="a7bde-131">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a7bde-132">备注</span><span class="sxs-lookup"><span data-stu-id="a7bde-132">Remarks</span></span>  
 <span data-ttu-id="a7bde-133">此配置元素用于请求进程中减少的虚拟内存使用, 因为 CLR 用于其内部线程的显式线程大小 (如果请求被接受) 小于默认大小。</span><span class="sxs-lookup"><span data-stu-id="a7bde-133">This configuration element is used to request reduced virtual memory use in a process, because the explicit thread sizes that the CLR uses for its internal threads, if the request is honored, are smaller than the default size.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="a7bde-134">此配置元素是对 CLR 的请求, 而不是绝对要求。</span><span class="sxs-lookup"><span data-stu-id="a7bde-134">This configuration element is a request to the CLR rather than an absolute requirement.</span></span> <span data-ttu-id="a7bde-135">在 .NET Framework 4 中, 请求仅适用于 x86 体系结构。</span><span class="sxs-lookup"><span data-stu-id="a7bde-135">In the .NET Framework 4, the request is honored only for the x86 architecture.</span></span> <span data-ttu-id="a7bde-136">在未来版本的 CLR 中, 可能会完全忽略此元素, 或将其替换为所选内部线程始终使用的显式堆栈大小。</span><span class="sxs-lookup"><span data-stu-id="a7bde-136">This element might be ignored completely in future versions of the CLR, or replaced by explicit stack sizes that are always used for selected internal threads.</span></span>  
  
 <span data-ttu-id="a7bde-137">如果 CLR 接受请求, 则指定此配置元素会在较小的虚拟内存使用情况下提高可靠性, 因为较小的堆栈大小可能会导致堆栈溢出。</span><span class="sxs-lookup"><span data-stu-id="a7bde-137">Specifying this configuration element trades reliability for smaller virtual memory use if the CLR honors the request, because smaller stack sizes could potentially make stack overflows more likely.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a7bde-138">示例</span><span class="sxs-lookup"><span data-stu-id="a7bde-138">Example</span></span>  
 <span data-ttu-id="a7bde-139">下面的示例演示如何请求 CLR 对其内部使用的某些线程使用显式堆栈大小。</span><span class="sxs-lookup"><span data-stu-id="a7bde-139">The following example shows how to request that the CLR use explicit stack sizes for certain threads that it uses internally.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <UseSmallInternalThreadStacks enabled="true" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a7bde-140">请参阅</span><span class="sxs-lookup"><span data-stu-id="a7bde-140">See also</span></span>

- [<span data-ttu-id="a7bde-141">运行时设置架构</span><span class="sxs-lookup"><span data-stu-id="a7bde-141">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="a7bde-142">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="a7bde-142">Configuration File Schema</span></span>](../index.md)
