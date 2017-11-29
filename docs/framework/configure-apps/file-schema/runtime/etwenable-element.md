---
title: "&lt;etwEnable&gt;元素"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- etwEnable element
- <etwEnable> element
ms.assetid: 29dde982-6d8b-4099-8867-ad0d7733f6dc
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b36c52338754df0f4fd3c963848e36afeb140501
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="ltetwenablegt-element"></a><span data-ttu-id="7cd89-102">&lt;etwEnable&gt;元素</span><span class="sxs-lookup"><span data-stu-id="7cd89-102">&lt;etwEnable&gt; Element</span></span>
<span data-ttu-id="7cd89-103">指定是否为公共语言运行时事件启用 Windows 事件跟踪 (ETW)。</span><span class="sxs-lookup"><span data-stu-id="7cd89-103">Specifies whether to enable event tracing for Windows (ETW) for common language runtime events.</span></span>  
  
 <span data-ttu-id="7cd89-104">\<配置 > 元素</span><span class="sxs-lookup"><span data-stu-id="7cd89-104">\<configuration> Element</span></span>  
<span data-ttu-id="7cd89-105">\<运行时 > 元素</span><span class="sxs-lookup"><span data-stu-id="7cd89-105">\<runtime> Element</span></span>  
<span data-ttu-id="7cd89-106">\<etwEnabled ></span><span class="sxs-lookup"><span data-stu-id="7cd89-106">\<etwEnabled></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7cd89-107">语法</span><span class="sxs-lookup"><span data-stu-id="7cd89-107">Syntax</span></span>  
  
```xml  
<etwEnable enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7cd89-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="7cd89-108">Attributes and Elements</span></span>  
 <span data-ttu-id="7cd89-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="7cd89-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7cd89-110">特性</span><span class="sxs-lookup"><span data-stu-id="7cd89-110">Attributes</span></span>  
  
|<span data-ttu-id="7cd89-111">特性</span><span class="sxs-lookup"><span data-stu-id="7cd89-111">Attribute</span></span>|<span data-ttu-id="7cd89-112">描述</span><span class="sxs-lookup"><span data-stu-id="7cd89-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7cd89-113">enabled</span><span class="sxs-lookup"><span data-stu-id="7cd89-113">enabled</span></span>|<span data-ttu-id="7cd89-114">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="7cd89-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="7cd89-115">指定是否应启用 ETW。</span><span class="sxs-lookup"><span data-stu-id="7cd89-115">Specifies whether ETW should be enabled.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="7cd89-116">enabled 特性</span><span class="sxs-lookup"><span data-stu-id="7cd89-116">enabled Attribute</span></span>  
  
|<span data-ttu-id="7cd89-117">值</span><span class="sxs-lookup"><span data-stu-id="7cd89-117">Value</span></span>|<span data-ttu-id="7cd89-118">描述</span><span class="sxs-lookup"><span data-stu-id="7cd89-118">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="7cd89-119">true</span><span class="sxs-lookup"><span data-stu-id="7cd89-119">true</span></span>|<span data-ttu-id="7cd89-120">启用 ETW。</span><span class="sxs-lookup"><span data-stu-id="7cd89-120">Enable ETW.</span></span> <span data-ttu-id="7cd89-121">这是从开始在 Windows Vista 和 Windows Server 2008 操作系统的 Windows 版本的默认值。</span><span class="sxs-lookup"><span data-stu-id="7cd89-121">This is the default for versions of Windows beginning with the Windows Vista and Windows Server 2008 operating systems.</span></span>|  
|<span data-ttu-id="7cd89-122">false</span><span class="sxs-lookup"><span data-stu-id="7cd89-122">false</span></span>|<span data-ttu-id="7cd89-123">禁用 ETW。</span><span class="sxs-lookup"><span data-stu-id="7cd89-123">Disable ETW.</span></span> <span data-ttu-id="7cd89-124">这是早期版本的 Windows 的默认值。</span><span class="sxs-lookup"><span data-stu-id="7cd89-124">This is the default for earlier versions of Windows.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7cd89-125">子元素</span><span class="sxs-lookup"><span data-stu-id="7cd89-125">Child Elements</span></span>  
 <span data-ttu-id="7cd89-126">无。</span><span class="sxs-lookup"><span data-stu-id="7cd89-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7cd89-127">父元素</span><span class="sxs-lookup"><span data-stu-id="7cd89-127">Parent Elements</span></span>  
  
|<span data-ttu-id="7cd89-128">元素</span><span class="sxs-lookup"><span data-stu-id="7cd89-128">Element</span></span>|<span data-ttu-id="7cd89-129">描述</span><span class="sxs-lookup"><span data-stu-id="7cd89-129">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="7cd89-130">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="7cd89-130">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="7cd89-131">包含有关程序集绑定和垃圾回收的信息。</span><span class="sxs-lookup"><span data-stu-id="7cd89-131">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7cd89-132">备注</span><span class="sxs-lookup"><span data-stu-id="7cd89-132">Remarks</span></span>  
 <span data-ttu-id="7cd89-133">从 Windows Vista 开始，将默认启用 ETW。</span><span class="sxs-lookup"><span data-stu-id="7cd89-133">Beginning with Windows Vista, ETW is enabled by default.</span></span> <span data-ttu-id="7cd89-134">使用此元素用于禁用 ETW 的应用程序。</span><span class="sxs-lookup"><span data-stu-id="7cd89-134">Use this element to disable ETW for an application.</span></span> <span data-ttu-id="7cd89-135">在早期版本的 Windows 中，使用此元素可为应用程序启用 ETW。</span><span class="sxs-lookup"><span data-stu-id="7cd89-135">In earlier versions of Windows, use this element to enable ETW for an application.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7cd89-136">可以启用或通过使用注册表设置的服务器上全局禁用 ETW。</span><span class="sxs-lookup"><span data-stu-id="7cd89-136">ETW can be enabled or disabled globally on a server by using a registry setting.</span></span> <span data-ttu-id="7cd89-137">请参阅[控制.NET Framework 日志记录](../../../../../docs/framework/performance/controlling-logging.md)。</span><span class="sxs-lookup"><span data-stu-id="7cd89-137">See [Controlling .NET Framework Logging](../../../../../docs/framework/performance/controlling-logging.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="7cd89-138">示例</span><span class="sxs-lookup"><span data-stu-id="7cd89-138">Example</span></span>  
 <span data-ttu-id="7cd89-139">下面的示例演示如何启用应用程序的 ETW 跟踪。</span><span class="sxs-lookup"><span data-stu-id="7cd89-139">The following example shows how to enable ETW tracing for an application.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <etwEnable enabled="true" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="7cd89-140">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7cd89-140">See Also</span></span>  
 [<span data-ttu-id="7cd89-141">运行时设置架构</span><span class="sxs-lookup"><span data-stu-id="7cd89-141">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="7cd89-142">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="7cd89-142">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="7cd89-143">控制 .NET Framework 日志记录</span><span class="sxs-lookup"><span data-stu-id="7cd89-143">Controlling .NET Framework Logging</span></span>](../../../../../docs/framework/performance/controlling-logging.md)
