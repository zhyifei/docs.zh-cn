---
title: <etwEnable> 元素
ms.date: 03/30/2017
helpviewer_keywords:
- etwEnable element
- <etwEnable> element
ms.assetid: 29dde982-6d8b-4099-8867-ad0d7733f6dc
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cb4d0ed5b33170c40aacb32bebbf1b59ca659be4
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252616"
---
# <a name="etwenable-element"></a><span data-ttu-id="edec6-102">\<etwEnable > 元素</span><span class="sxs-lookup"><span data-stu-id="edec6-102">\<etwEnable> Element</span></span>
<span data-ttu-id="edec6-103">指定是否为公共语言运行时事件启用 Windows 事件跟踪 (ETW)。</span><span class="sxs-lookup"><span data-stu-id="edec6-103">Specifies whether to enable event tracing for Windows (ETW) for common language runtime events.</span></span>  
  
<span data-ttu-id="edec6-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="edec6-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="edec6-105">&nbsp;&nbsp;[ **\<运行时 >** ](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="edec6-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="edec6-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<etwEnabled >**</span><span class="sxs-lookup"><span data-stu-id="edec6-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<etwEnabled>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="edec6-107">语法</span><span class="sxs-lookup"><span data-stu-id="edec6-107">Syntax</span></span>  
  
```xml  
<etwEnable enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="edec6-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="edec6-108">Attributes and Elements</span></span>  
 <span data-ttu-id="edec6-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="edec6-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="edec6-110">特性</span><span class="sxs-lookup"><span data-stu-id="edec6-110">Attributes</span></span>  
  
|<span data-ttu-id="edec6-111">特性</span><span class="sxs-lookup"><span data-stu-id="edec6-111">Attribute</span></span>|<span data-ttu-id="edec6-112">描述</span><span class="sxs-lookup"><span data-stu-id="edec6-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="edec6-113">enabled</span><span class="sxs-lookup"><span data-stu-id="edec6-113">enabled</span></span>|<span data-ttu-id="edec6-114">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="edec6-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="edec6-115">指定是否应启用 ETW。</span><span class="sxs-lookup"><span data-stu-id="edec6-115">Specifies whether ETW should be enabled.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="edec6-116">enabled 特性</span><span class="sxs-lookup"><span data-stu-id="edec6-116">enabled Attribute</span></span>  
  
|<span data-ttu-id="edec6-117">值</span><span class="sxs-lookup"><span data-stu-id="edec6-117">Value</span></span>|<span data-ttu-id="edec6-118">描述</span><span class="sxs-lookup"><span data-stu-id="edec6-118">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="edec6-119">真</span><span class="sxs-lookup"><span data-stu-id="edec6-119">true</span></span>|<span data-ttu-id="edec6-120">启用 ETW。</span><span class="sxs-lookup"><span data-stu-id="edec6-120">Enable ETW.</span></span> <span data-ttu-id="edec6-121">这是从 Windows Vista 和 Windows Server 2008 操作系统开始的 Windows 版本的默认值。</span><span class="sxs-lookup"><span data-stu-id="edec6-121">This is the default for versions of Windows beginning with the Windows Vista and Windows Server 2008 operating systems.</span></span>|  
|<span data-ttu-id="edec6-122">假</span><span class="sxs-lookup"><span data-stu-id="edec6-122">false</span></span>|<span data-ttu-id="edec6-123">禁用 ETW。</span><span class="sxs-lookup"><span data-stu-id="edec6-123">Disable ETW.</span></span> <span data-ttu-id="edec6-124">这是早期版本的 Windows 的默认设置。</span><span class="sxs-lookup"><span data-stu-id="edec6-124">This is the default for earlier versions of Windows.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="edec6-125">子元素</span><span class="sxs-lookup"><span data-stu-id="edec6-125">Child Elements</span></span>  
 <span data-ttu-id="edec6-126">无。</span><span class="sxs-lookup"><span data-stu-id="edec6-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="edec6-127">父元素</span><span class="sxs-lookup"><span data-stu-id="edec6-127">Parent Elements</span></span>  
  
|<span data-ttu-id="edec6-128">元素</span><span class="sxs-lookup"><span data-stu-id="edec6-128">Element</span></span>|<span data-ttu-id="edec6-129">描述</span><span class="sxs-lookup"><span data-stu-id="edec6-129">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="edec6-130">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="edec6-130">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="edec6-131">包含有关程序集绑定和垃圾回收的信息。</span><span class="sxs-lookup"><span data-stu-id="edec6-131">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="edec6-132">备注</span><span class="sxs-lookup"><span data-stu-id="edec6-132">Remarks</span></span>  
 <span data-ttu-id="edec6-133">从 Windows Vista 开始，默认情况下启用 ETW。</span><span class="sxs-lookup"><span data-stu-id="edec6-133">Beginning with Windows Vista, ETW is enabled by default.</span></span> <span data-ttu-id="edec6-134">使用此元素可禁用应用程序的 ETW。</span><span class="sxs-lookup"><span data-stu-id="edec6-134">Use this element to disable ETW for an application.</span></span> <span data-ttu-id="edec6-135">在早期版本的 Windows 中，使用此元素为应用程序启用 ETW。</span><span class="sxs-lookup"><span data-stu-id="edec6-135">In earlier versions of Windows, use this element to enable ETW for an application.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="edec6-136">可以通过使用注册表设置在服务器上全局启用或禁用 ETW。</span><span class="sxs-lookup"><span data-stu-id="edec6-136">ETW can be enabled or disabled globally on a server by using a registry setting.</span></span> <span data-ttu-id="edec6-137">请参阅[控制 .NET Framework 日志记录](../../../performance/controlling-logging.md)。</span><span class="sxs-lookup"><span data-stu-id="edec6-137">See [Controlling .NET Framework Logging](../../../performance/controlling-logging.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="edec6-138">示例</span><span class="sxs-lookup"><span data-stu-id="edec6-138">Example</span></span>  
 <span data-ttu-id="edec6-139">下面的示例演示如何为应用程序启用 ETW 跟踪。</span><span class="sxs-lookup"><span data-stu-id="edec6-139">The following example shows how to enable ETW tracing for an application.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <etwEnable enabled="true" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="edec6-140">请参阅</span><span class="sxs-lookup"><span data-stu-id="edec6-140">See also</span></span>

- [<span data-ttu-id="edec6-141">运行时设置架构</span><span class="sxs-lookup"><span data-stu-id="edec6-141">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="edec6-142">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="edec6-142">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="edec6-143">控制 .NET Framework 日志记录</span><span class="sxs-lookup"><span data-stu-id="edec6-143">Controlling .NET Framework Logging</span></span>](../../../performance/controlling-logging.md)
