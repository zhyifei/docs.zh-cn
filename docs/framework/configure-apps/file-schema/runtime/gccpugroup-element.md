---
title: <GCCpuGroup> 元素
ms.date: 03/30/2017
helpviewer_keywords:
- GCCpuGroup element
- <GCCpuGroup> element
ms.assetid: c1fc7d6c-7220-475c-a312-5b8b201f66e0
ms.openlocfilehash: 352890519c1a227d664d877c3123866e5e4e1657
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73116835"
---
# <a name="gccpugroup-element"></a><span data-ttu-id="521bc-102">\<GCCpuGroup > 元素</span><span class="sxs-lookup"><span data-stu-id="521bc-102">\<GCCpuGroup> Element</span></span>

<span data-ttu-id="521bc-103">指定垃圾回收是否支持多个 CPU 组。</span><span class="sxs-lookup"><span data-stu-id="521bc-103">Specifies whether garbage collection supports multiple CPU groups.</span></span>

<span data-ttu-id="521bc-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="521bc-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="521bc-105">&nbsp; &nbsp;[ **\<runtime >** ](runtime-element.md) </span><span class="sxs-lookup"><span data-stu-id="521bc-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="521bc-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<GCCpuGroup >**</span><span class="sxs-lookup"><span data-stu-id="521bc-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<GCCpuGroup>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="521bc-107">语法</span><span class="sxs-lookup"><span data-stu-id="521bc-107">Syntax</span></span>

```xml
<GCCpuGroup
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="521bc-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="521bc-108">Attributes and Elements</span></span>

<span data-ttu-id="521bc-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="521bc-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="521bc-110">特性</span><span class="sxs-lookup"><span data-stu-id="521bc-110">Attributes</span></span>

|<span data-ttu-id="521bc-111">特性</span><span class="sxs-lookup"><span data-stu-id="521bc-111">Attribute</span></span>|<span data-ttu-id="521bc-112">描述</span><span class="sxs-lookup"><span data-stu-id="521bc-112">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="521bc-113">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="521bc-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="521bc-114">指定垃圾回收是否支持多个 CPU 组。</span><span class="sxs-lookup"><span data-stu-id="521bc-114">Specifies whether garbage collection supports multiple CPU groups.</span></span>|

## <a name="enabled-attribute"></a><span data-ttu-id="521bc-115">enabled 特性</span><span class="sxs-lookup"><span data-stu-id="521bc-115">enabled Attribute</span></span>

|<span data-ttu-id="521bc-116">“值”</span><span class="sxs-lookup"><span data-stu-id="521bc-116">Value</span></span>|<span data-ttu-id="521bc-117">描述</span><span class="sxs-lookup"><span data-stu-id="521bc-117">Description</span></span>|
|-----------|-----------------|
|`false`|<span data-ttu-id="521bc-118">垃圾回收不支持多个 CPU 组。</span><span class="sxs-lookup"><span data-stu-id="521bc-118">Garbage collection does not support multiple CPU groups.</span></span> <span data-ttu-id="521bc-119">这是默认设置。</span><span class="sxs-lookup"><span data-stu-id="521bc-119">This is the default.</span></span>|
|`true`|<span data-ttu-id="521bc-120">如果启用了服务器垃圾回收，则垃圾回收支持多个 CPU 组。</span><span class="sxs-lookup"><span data-stu-id="521bc-120">Garbage collection supports multiple CPU groups, if server garbage collection is enabled.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="521bc-121">子元素</span><span class="sxs-lookup"><span data-stu-id="521bc-121">Child Elements</span></span>

<span data-ttu-id="521bc-122">无。</span><span class="sxs-lookup"><span data-stu-id="521bc-122">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="521bc-123">父元素</span><span class="sxs-lookup"><span data-stu-id="521bc-123">Parent Elements</span></span>

|<span data-ttu-id="521bc-124">元素</span><span class="sxs-lookup"><span data-stu-id="521bc-124">Element</span></span>|<span data-ttu-id="521bc-125">描述</span><span class="sxs-lookup"><span data-stu-id="521bc-125">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="521bc-126">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="521bc-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="521bc-127">包含有关程序集绑定和垃圾回收的信息。</span><span class="sxs-lookup"><span data-stu-id="521bc-127">Contains information about assembly binding and garbage collection.</span></span>|

## <a name="remarks"></a><span data-ttu-id="521bc-128">备注</span><span class="sxs-lookup"><span data-stu-id="521bc-128">Remarks</span></span>

<span data-ttu-id="521bc-129">如果计算机具有多个 CPU 组并且启用了服务器垃圾回收（请参阅[\<r >](gcserver-element.md)元素），则启用此元素会在所有 CPU 组之间扩展垃圾回收，并在创建和平衡堆。</span><span class="sxs-lookup"><span data-stu-id="521bc-129">When a computer has multiple CPU groups and server garbage collection is enabled (see the [\<gcServer>](gcserver-element.md) element), enabling this element extends garbage collection across all CPU groups and takes all cores into account when creating and balancing heaps.</span></span>

> [!NOTE]
> <span data-ttu-id="521bc-130">此元素仅适用于垃圾回收线程。</span><span class="sxs-lookup"><span data-stu-id="521bc-130">This element applies only to garbage collection threads.</span></span> <span data-ttu-id="521bc-131">若要使运行时能够在所有 CPU 组之间分配用户线程，还必须启用[\<Thread_UseAllCpuGroups >](thread-useallcpugroups-element.md)元素。</span><span class="sxs-lookup"><span data-stu-id="521bc-131">To enable the runtime to distribute user threads across all CPU groups, you must also enable the [\<Thread_UseAllCpuGroups>](thread-useallcpugroups-element.md) element.</span></span>

## <a name="example"></a><span data-ttu-id="521bc-132">示例</span><span class="sxs-lookup"><span data-stu-id="521bc-132">Example</span></span>

<span data-ttu-id="521bc-133">下面的示例演示如何为多个 CPU 组启用垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="521bc-133">The following example shows how to enable garbage collection for multiple CPU groups.</span></span>

```xml
<configuration>
   <runtime>
      <GCCpuGroup enabled="true"/>
      <gcServer enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="521bc-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="521bc-134">See also</span></span>

- [<span data-ttu-id="521bc-135">运行时设置架构</span><span class="sxs-lookup"><span data-stu-id="521bc-135">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="521bc-136">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="521bc-136">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="521bc-137">禁用并发垃圾回收</span><span class="sxs-lookup"><span data-stu-id="521bc-137">To disable concurrent garbage collection</span></span>](gcconcurrent-element.md#to-disable-background-garbage-collection)
- [<span data-ttu-id="521bc-138">工作站和服务器垃圾回收</span><span class="sxs-lookup"><span data-stu-id="521bc-138">Workstation and server garbage collection</span></span>](../../../../standard/garbage-collection/fundamentals.md#workstation_and_server_garbage_collection)
