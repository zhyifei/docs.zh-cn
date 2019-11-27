---
title: <GCCpuGroup> 元素
ms.date: 03/30/2017
helpviewer_keywords:
- GCCpuGroup element
- <GCCpuGroup> element
ms.assetid: c1fc7d6c-7220-475c-a312-5b8b201f66e0
ms.openlocfilehash: ae9c96c9d49cf3f6be94da3f77b91423cab12e0b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74430479"
---
# <a name="gccpugroup-element"></a><span data-ttu-id="0b7de-102">\<GCCpuGroup > 元素</span><span class="sxs-lookup"><span data-stu-id="0b7de-102">\<GCCpuGroup> Element</span></span>

<span data-ttu-id="0b7de-103">指定垃圾回收是否支持多个 CPU 组。</span><span class="sxs-lookup"><span data-stu-id="0b7de-103">Specifies whether garbage collection supports multiple CPU groups.</span></span>

<span data-ttu-id="0b7de-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="0b7de-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="0b7de-105">&nbsp;&nbsp;[ **\<运行时 >** ](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="0b7de-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="0b7de-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<GCCpuGroup >**</span><span class="sxs-lookup"><span data-stu-id="0b7de-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<GCCpuGroup>**</span></span>

## <a name="syntax"></a><span data-ttu-id="0b7de-107">语法</span><span class="sxs-lookup"><span data-stu-id="0b7de-107">Syntax</span></span>

```xml
<GCCpuGroup
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="0b7de-108">属性和元素</span><span class="sxs-lookup"><span data-stu-id="0b7de-108">Attributes and Elements</span></span>

<span data-ttu-id="0b7de-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="0b7de-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="0b7de-110">Attributes</span><span class="sxs-lookup"><span data-stu-id="0b7de-110">Attributes</span></span>

|<span data-ttu-id="0b7de-111">属性</span><span class="sxs-lookup"><span data-stu-id="0b7de-111">Attribute</span></span>|<span data-ttu-id="0b7de-112">说明</span><span class="sxs-lookup"><span data-stu-id="0b7de-112">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="0b7de-113">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="0b7de-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="0b7de-114">指定垃圾回收是否支持多个 CPU 组。</span><span class="sxs-lookup"><span data-stu-id="0b7de-114">Specifies whether garbage collection supports multiple CPU groups.</span></span>|

## <a name="enabled-attribute"></a><span data-ttu-id="0b7de-115">enabled 特性</span><span class="sxs-lookup"><span data-stu-id="0b7de-115">enabled Attribute</span></span>

|<span data-ttu-id="0b7de-116">值</span><span class="sxs-lookup"><span data-stu-id="0b7de-116">Value</span></span>|<span data-ttu-id="0b7de-117">说明</span><span class="sxs-lookup"><span data-stu-id="0b7de-117">Description</span></span>|
|-----------|-----------------|
|`false`|<span data-ttu-id="0b7de-118">垃圾回收不支持多个 CPU 组。</span><span class="sxs-lookup"><span data-stu-id="0b7de-118">Garbage collection does not support multiple CPU groups.</span></span> <span data-ttu-id="0b7de-119">这是默认设置。</span><span class="sxs-lookup"><span data-stu-id="0b7de-119">This is the default.</span></span>|
|`true`|<span data-ttu-id="0b7de-120">如果启用了服务器垃圾回收，则垃圾回收支持多个 CPU 组。</span><span class="sxs-lookup"><span data-stu-id="0b7de-120">Garbage collection supports multiple CPU groups, if server garbage collection is enabled.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="0b7de-121">子元素</span><span class="sxs-lookup"><span data-stu-id="0b7de-121">Child Elements</span></span>

<span data-ttu-id="0b7de-122">无。</span><span class="sxs-lookup"><span data-stu-id="0b7de-122">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="0b7de-123">父元素</span><span class="sxs-lookup"><span data-stu-id="0b7de-123">Parent Elements</span></span>

|<span data-ttu-id="0b7de-124">元素</span><span class="sxs-lookup"><span data-stu-id="0b7de-124">Element</span></span>|<span data-ttu-id="0b7de-125">说明</span><span class="sxs-lookup"><span data-stu-id="0b7de-125">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="0b7de-126">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="0b7de-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="0b7de-127">包含有关程序集绑定和垃圾回收的信息。</span><span class="sxs-lookup"><span data-stu-id="0b7de-127">Contains information about assembly binding and garbage collection.</span></span>|

## <a name="remarks"></a><span data-ttu-id="0b7de-128">备注</span><span class="sxs-lookup"><span data-stu-id="0b7de-128">Remarks</span></span>

<span data-ttu-id="0b7de-129">当计算机具有多个 CPU 组并且启用了服务器垃圾回收功能时（请参阅[\<r >](gcserver-element.md)元素），启用此元素可跨所有 CPU 组扩展垃圾回收，并在创建和平衡堆时考虑所有内核。</span><span class="sxs-lookup"><span data-stu-id="0b7de-129">When a computer has multiple CPU groups and server garbage collection is enabled (see the [\<gcServer>](gcserver-element.md) element), enabling this element extends garbage collection across all CPU groups and takes all cores into account when creating and balancing heaps.</span></span>

> [!NOTE]
> <span data-ttu-id="0b7de-130">此元素仅适用于垃圾回收线程。</span><span class="sxs-lookup"><span data-stu-id="0b7de-130">This element applies only to garbage collection threads.</span></span> <span data-ttu-id="0b7de-131">若要使运行时能够在所有 CPU 组之间分配用户线程，还必须启用[Thread_UseAllCpuGroups >](thread-useallcpugroups-element.md)元素的\<。</span><span class="sxs-lookup"><span data-stu-id="0b7de-131">To enable the runtime to distribute user threads across all CPU groups, you must also enable the [\<Thread_UseAllCpuGroups>](thread-useallcpugroups-element.md) element.</span></span>

## <a name="example"></a><span data-ttu-id="0b7de-132">示例</span><span class="sxs-lookup"><span data-stu-id="0b7de-132">Example</span></span>

<span data-ttu-id="0b7de-133">下面的示例演示如何为多个 CPU 组启用垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="0b7de-133">The following example shows how to enable garbage collection for multiple CPU groups.</span></span>

```xml
<configuration>
   <runtime>
      <GCCpuGroup enabled="true"/>
      <gcServer enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="0b7de-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0b7de-134">See also</span></span>

- [<span data-ttu-id="0b7de-135">运行时设置架构</span><span class="sxs-lookup"><span data-stu-id="0b7de-135">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="0b7de-136">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="0b7de-136">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="0b7de-137">禁用并发垃圾回收</span><span class="sxs-lookup"><span data-stu-id="0b7de-137">To disable concurrent garbage collection</span></span>](gcconcurrent-element.md#to-disable-background-garbage-collection)
- [<span data-ttu-id="0b7de-138">工作站和服务器垃圾回收</span><span class="sxs-lookup"><span data-stu-id="0b7de-138">Workstation and server garbage collection</span></span>](../../../../standard/garbage-collection/fundamentals.md#workstation-and-server-garbage-collection)
