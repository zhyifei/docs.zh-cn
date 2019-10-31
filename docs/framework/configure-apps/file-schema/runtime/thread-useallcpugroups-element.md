---
title: <Thread_UseAllCpuGroups> 元素
ms.date: 03/30/2017
ms.assetid: d30fe7c5-8469-46e2-b804-e3eec7b24256
ms.openlocfilehash: a3a612c0ffbcb211157b9623d298ce8ad7a13e94
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73115400"
---
# <a name="thread_useallcpugroups-element"></a><span data-ttu-id="c2401-102">\<Thread_UseAllCpuGroups > 元素</span><span class="sxs-lookup"><span data-stu-id="c2401-102">\<Thread_UseAllCpuGroups> Element</span></span>

<span data-ttu-id="c2401-103">指定运行时是否跨所有 CPU 组分发托管的线程。</span><span class="sxs-lookup"><span data-stu-id="c2401-103">Specifies whether the runtime distributes managed threads across all CPU groups.</span></span>

<span data-ttu-id="c2401-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="c2401-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="c2401-105">&nbsp; &nbsp;[ **\<runtime >** ](runtime-element.md) </span><span class="sxs-lookup"><span data-stu-id="c2401-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="c2401-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<Thread_UseAllCpuGroups >**</span><span class="sxs-lookup"><span data-stu-id="c2401-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<Thread_UseAllCpuGroups>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="c2401-107">语法</span><span class="sxs-lookup"><span data-stu-id="c2401-107">Syntax</span></span>

```xml
<Thread_UseAllCpuGroups
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="c2401-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="c2401-108">Attributes and Elements</span></span>

<span data-ttu-id="c2401-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="c2401-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="c2401-110">特性</span><span class="sxs-lookup"><span data-stu-id="c2401-110">Attributes</span></span>

|<span data-ttu-id="c2401-111">特性</span><span class="sxs-lookup"><span data-stu-id="c2401-111">Attribute</span></span>|<span data-ttu-id="c2401-112">描述</span><span class="sxs-lookup"><span data-stu-id="c2401-112">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="c2401-113">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="c2401-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="c2401-114">指定运行时是否跨所有 CPU 组分发托管的线程。</span><span class="sxs-lookup"><span data-stu-id="c2401-114">Specifies whether the runtime distributes managed threads across all CPU groups.</span></span>|

## <a name="enabled-attribute"></a><span data-ttu-id="c2401-115">enabled 特性</span><span class="sxs-lookup"><span data-stu-id="c2401-115">enabled Attribute</span></span>

|<span data-ttu-id="c2401-116">“值”</span><span class="sxs-lookup"><span data-stu-id="c2401-116">Value</span></span>|<span data-ttu-id="c2401-117">描述</span><span class="sxs-lookup"><span data-stu-id="c2401-117">Description</span></span>|
|-----------|-----------------|
|`false`|<span data-ttu-id="c2401-118">运行时不会跨多个 CPU 组分发托管线程。</span><span class="sxs-lookup"><span data-stu-id="c2401-118">The runtime does not distribute managed threads across multiple CPU groups.</span></span> <span data-ttu-id="c2401-119">这是默认设置。</span><span class="sxs-lookup"><span data-stu-id="c2401-119">This is the default.</span></span>|
|`true`|<span data-ttu-id="c2401-120">如果计算机具有多个 CPU 组并且启用了[\<GCCpuGroup >](gccpugroup-element.md)元素，则运行时将跨多个 cpu 组分发托管线程。</span><span class="sxs-lookup"><span data-stu-id="c2401-120">The runtime distributes managed threads across multiple CPU groups, if the computer has multiple CPU groups and the [\<GCCpuGroup>](gccpugroup-element.md) element is enabled.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="c2401-121">子元素</span><span class="sxs-lookup"><span data-stu-id="c2401-121">Child Elements</span></span>

<span data-ttu-id="c2401-122">无。</span><span class="sxs-lookup"><span data-stu-id="c2401-122">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="c2401-123">父元素</span><span class="sxs-lookup"><span data-stu-id="c2401-123">Parent Elements</span></span>

|<span data-ttu-id="c2401-124">元素</span><span class="sxs-lookup"><span data-stu-id="c2401-124">Element</span></span>|<span data-ttu-id="c2401-125">描述</span><span class="sxs-lookup"><span data-stu-id="c2401-125">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="c2401-126">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="c2401-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="c2401-127">包含有关程序集绑定和垃圾回收的信息。</span><span class="sxs-lookup"><span data-stu-id="c2401-127">Contains information about assembly binding and garbage collection.</span></span>|

## <a name="remarks"></a><span data-ttu-id="c2401-128">备注</span><span class="sxs-lookup"><span data-stu-id="c2401-128">Remarks</span></span>

<span data-ttu-id="c2401-129">如果计算机具有多个 CPU 组，则启用此元素会使运行时将托管线程分散到所有 CPU 组。</span><span class="sxs-lookup"><span data-stu-id="c2401-129">When a computer has multiple CPU groups, enabling this element causes the runtime to distribute managed threads across all CPU groups.</span></span> <span data-ttu-id="c2401-130">若要使用此功能，还必须启用[\<GCCpuGroup >](gccpugroup-element.md)元素，该元素将垃圾回收扩展到所有 CPU 组，并在创建和平衡堆时考虑所有核心。</span><span class="sxs-lookup"><span data-stu-id="c2401-130">To use this feature, you must also enable the [\<GCCpuGroup>](gccpugroup-element.md) element, which extends garbage collection to all CPU groups and takes all cores into account when creating and balancing heaps.</span></span> <span data-ttu-id="c2401-131">启用[\<GCCpuGroup >](gccpugroup-element.md)元素需要启用[\<r >](gcserver-element.md)元素。</span><span class="sxs-lookup"><span data-stu-id="c2401-131">Enabling the [\<GCCpuGroup>](gccpugroup-element.md) element requires enabling the [\<gcServer>](gcserver-element.md) element.</span></span> <span data-ttu-id="c2401-132">如果未启用这些元素，则启用 `<Thread_UseAllCpuGroups>` 元素不起作用。</span><span class="sxs-lookup"><span data-stu-id="c2401-132">If these elements are not enabled, enabling the `<Thread_UseAllCpuGroups>` element has no effect.</span></span>

## <a name="example"></a><span data-ttu-id="c2401-133">示例</span><span class="sxs-lookup"><span data-stu-id="c2401-133">Example</span></span>

<span data-ttu-id="c2401-134">下面的示例演示如何启用对多个 CPU 组的支持。</span><span class="sxs-lookup"><span data-stu-id="c2401-134">The following example shows how to enable support for multiple CPU groups.</span></span>

```xml
<configuration>
   <runtime>
      <Thread_UseAllCpuGroups enabled="true"/>
      <GCCpuGroup enabled="true"/>
      <gcServer enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="c2401-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="c2401-135">See also</span></span>

- [<span data-ttu-id="c2401-136">运行时设置架构</span><span class="sxs-lookup"><span data-stu-id="c2401-136">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="c2401-137">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="c2401-137">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="c2401-138">\<GCCpuGroup > 元素</span><span class="sxs-lookup"><span data-stu-id="c2401-138">\<GCCpuGroup> Element</span></span>](gccpugroup-element.md)
