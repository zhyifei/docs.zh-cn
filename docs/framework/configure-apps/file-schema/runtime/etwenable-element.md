---
title: '&lt;etwEnable&gt;元素'
ms.date: 03/30/2017
helpviewer_keywords:
- etwEnable element
- <etwEnable> element
ms.assetid: 29dde982-6d8b-4099-8867-ad0d7733f6dc
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 788eee71c718c003110ad8242505f2d7868e836c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54506922"
---
# <a name="ltetwenablegt-element"></a><span data-ttu-id="72494-102">&lt;etwEnable&gt;元素</span><span class="sxs-lookup"><span data-stu-id="72494-102">&lt;etwEnable&gt; Element</span></span>
<span data-ttu-id="72494-103">指定是否为公共语言运行时事件启用 Windows 事件跟踪 (ETW)。</span><span class="sxs-lookup"><span data-stu-id="72494-103">Specifies whether to enable event tracing for Windows (ETW) for common language runtime events.</span></span>  
  
 <span data-ttu-id="72494-104">\<配置 > 元素</span><span class="sxs-lookup"><span data-stu-id="72494-104">\<configuration> Element</span></span>  
<span data-ttu-id="72494-105">\<运行时 > 元素</span><span class="sxs-lookup"><span data-stu-id="72494-105">\<runtime> Element</span></span>  
<span data-ttu-id="72494-106">\<etwEnabled></span><span class="sxs-lookup"><span data-stu-id="72494-106">\<etwEnabled></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="72494-107">语法</span><span class="sxs-lookup"><span data-stu-id="72494-107">Syntax</span></span>  
  
```xml  
<etwEnable enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="72494-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="72494-108">Attributes and Elements</span></span>  
 <span data-ttu-id="72494-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="72494-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="72494-110">特性</span><span class="sxs-lookup"><span data-stu-id="72494-110">Attributes</span></span>  
  
|<span data-ttu-id="72494-111">特性</span><span class="sxs-lookup"><span data-stu-id="72494-111">Attribute</span></span>|<span data-ttu-id="72494-112">描述</span><span class="sxs-lookup"><span data-stu-id="72494-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="72494-113">enabled</span><span class="sxs-lookup"><span data-stu-id="72494-113">enabled</span></span>|<span data-ttu-id="72494-114">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="72494-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="72494-115">指定是否应启用 ETW。</span><span class="sxs-lookup"><span data-stu-id="72494-115">Specifies whether ETW should be enabled.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="72494-116">enabled 特性</span><span class="sxs-lookup"><span data-stu-id="72494-116">enabled Attribute</span></span>  
  
|<span data-ttu-id="72494-117">值</span><span class="sxs-lookup"><span data-stu-id="72494-117">Value</span></span>|<span data-ttu-id="72494-118">描述</span><span class="sxs-lookup"><span data-stu-id="72494-118">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="72494-119">true</span><span class="sxs-lookup"><span data-stu-id="72494-119">true</span></span>|<span data-ttu-id="72494-120">启用 ETW。</span><span class="sxs-lookup"><span data-stu-id="72494-120">Enable ETW.</span></span> <span data-ttu-id="72494-121">这是 Windows 从开始，在 Windows Vista 和 Windows Server 2008 操作系统的版本的默认值。</span><span class="sxs-lookup"><span data-stu-id="72494-121">This is the default for versions of Windows beginning with the Windows Vista and Windows Server 2008 operating systems.</span></span>|  
|<span data-ttu-id="72494-122">False</span><span class="sxs-lookup"><span data-stu-id="72494-122">false</span></span>|<span data-ttu-id="72494-123">禁用 ETW。</span><span class="sxs-lookup"><span data-stu-id="72494-123">Disable ETW.</span></span> <span data-ttu-id="72494-124">这是早期版本的 Windows 的默认值。</span><span class="sxs-lookup"><span data-stu-id="72494-124">This is the default for earlier versions of Windows.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="72494-125">子元素</span><span class="sxs-lookup"><span data-stu-id="72494-125">Child Elements</span></span>  
 <span data-ttu-id="72494-126">无。</span><span class="sxs-lookup"><span data-stu-id="72494-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="72494-127">父元素</span><span class="sxs-lookup"><span data-stu-id="72494-127">Parent Elements</span></span>  
  
|<span data-ttu-id="72494-128">元素</span><span class="sxs-lookup"><span data-stu-id="72494-128">Element</span></span>|<span data-ttu-id="72494-129">描述</span><span class="sxs-lookup"><span data-stu-id="72494-129">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="72494-130">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="72494-130">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="72494-131">包含有关程序集绑定和垃圾回收的信息。</span><span class="sxs-lookup"><span data-stu-id="72494-131">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="72494-132">备注</span><span class="sxs-lookup"><span data-stu-id="72494-132">Remarks</span></span>  
 <span data-ttu-id="72494-133">从 Windows Vista 开始，默认情况下启用 ETW。</span><span class="sxs-lookup"><span data-stu-id="72494-133">Beginning with Windows Vista, ETW is enabled by default.</span></span> <span data-ttu-id="72494-134">使用此元素用于禁用 ETW 的应用程序。</span><span class="sxs-lookup"><span data-stu-id="72494-134">Use this element to disable ETW for an application.</span></span> <span data-ttu-id="72494-135">在早期版本的 Windows 中，使用此元素为应用程序启用 ETW。</span><span class="sxs-lookup"><span data-stu-id="72494-135">In earlier versions of Windows, use this element to enable ETW for an application.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="72494-136">ETW 可以启用或被全局禁用服务器上通过使用注册表设置。</span><span class="sxs-lookup"><span data-stu-id="72494-136">ETW can be enabled or disabled globally on a server by using a registry setting.</span></span> <span data-ttu-id="72494-137">请参阅[控制.NET Framework 日志记录](../../../../../docs/framework/performance/controlling-logging.md)。</span><span class="sxs-lookup"><span data-stu-id="72494-137">See [Controlling .NET Framework Logging](../../../../../docs/framework/performance/controlling-logging.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="72494-138">示例</span><span class="sxs-lookup"><span data-stu-id="72494-138">Example</span></span>  
 <span data-ttu-id="72494-139">下面的示例演示如何启用应用程序的 ETW 跟踪。</span><span class="sxs-lookup"><span data-stu-id="72494-139">The following example shows how to enable ETW tracing for an application.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <etwEnable enabled="true" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="72494-140">请参阅</span><span class="sxs-lookup"><span data-stu-id="72494-140">See also</span></span>
- [<span data-ttu-id="72494-141">运行时设置架构</span><span class="sxs-lookup"><span data-stu-id="72494-141">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="72494-142">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="72494-142">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="72494-143">控制 .NET Framework 日志记录</span><span class="sxs-lookup"><span data-stu-id="72494-143">Controlling .NET Framework Logging</span></span>](../../../../../docs/framework/performance/controlling-logging.md)
