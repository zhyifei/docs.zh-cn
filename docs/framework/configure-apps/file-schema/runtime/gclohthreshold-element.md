---
title: GCLOHThreshold element
ms.date: 11/20/2019
helpviewer_keywords:
- GCLOHThreshold element
- <GCLOHThreshold> element
ms.openlocfilehash: d72dc9d27984f60dfb6296217263ce8b176093c6
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74451322"
---
# <a name="gclohthreshold-element"></a><span data-ttu-id="13711-102">GCLOHThreshold element</span><span class="sxs-lookup"><span data-stu-id="13711-102">GCLOHThreshold element</span></span>

<span data-ttu-id="13711-103">Specifies the threshold size, in bytes, that causes the garbage collector to put objects on the large object heap (LOH).</span><span class="sxs-lookup"><span data-stu-id="13711-103">Specifies the threshold size, in bytes, that causes the garbage collector to put objects on the large object heap (LOH).</span></span>

<span data-ttu-id="13711-104">[\<configuration>](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="13711-104">[\<configuration>](../configuration-element.md)</span></span>\
<span data-ttu-id="13711-105">&nbsp;&nbsp;[\<runtime>](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="13711-105">&nbsp;&nbsp;[\<runtime>](runtime-element.md)</span></span>\
<span data-ttu-id="13711-106">&nbsp;&nbsp;&nbsp;&nbsp;\<GCLOHThreshold></span><span class="sxs-lookup"><span data-stu-id="13711-106">&nbsp;&nbsp;&nbsp;&nbsp;\<GCLOHThreshold></span></span>

## <a name="syntax"></a><span data-ttu-id="13711-107">语法</span><span class="sxs-lookup"><span data-stu-id="13711-107">Syntax</span></span>

```xml
<GCLOHThreshold
   enabled="nnnn"/>
```

## <a name="attributes"></a><span data-ttu-id="13711-108">特性</span><span class="sxs-lookup"><span data-stu-id="13711-108">Attributes</span></span>

|<span data-ttu-id="13711-109">特性</span><span class="sxs-lookup"><span data-stu-id="13711-109">Attribute</span></span>|<span data-ttu-id="13711-110">描述</span><span class="sxs-lookup"><span data-stu-id="13711-110">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="13711-111">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="13711-111">Required attribute.</span></span><br /><br /><span data-ttu-id="13711-112">Specifies the threshold size that causes objects to go on the large object heap.</span><span class="sxs-lookup"><span data-stu-id="13711-112">Specifies the threshold size that causes objects to go on the large object heap.</span></span>|

### <a name="enabled-attribute"></a><span data-ttu-id="13711-113">enabled attribute</span><span class="sxs-lookup"><span data-stu-id="13711-113">enabled attribute</span></span>

|<span data-ttu-id="13711-114">“值”</span><span class="sxs-lookup"><span data-stu-id="13711-114">Value</span></span>|<span data-ttu-id="13711-115">描述</span><span class="sxs-lookup"><span data-stu-id="13711-115">Description</span></span>|
|-----------|-----------------|
|`nnnn`|<span data-ttu-id="13711-116">The threshold size, in bytes, that causes objects to go on the large object heap.</span><span class="sxs-lookup"><span data-stu-id="13711-116">The threshold size, in bytes, that causes objects to go on the large object heap.</span></span>|

## <a name="child-elements"></a><span data-ttu-id="13711-117">子元素</span><span class="sxs-lookup"><span data-stu-id="13711-117">Child elements</span></span>

<span data-ttu-id="13711-118">无。</span><span class="sxs-lookup"><span data-stu-id="13711-118">None.</span></span>

## <a name="parent-elements"></a><span data-ttu-id="13711-119">父元素</span><span class="sxs-lookup"><span data-stu-id="13711-119">Parent elements</span></span>

|<span data-ttu-id="13711-120">元素</span><span class="sxs-lookup"><span data-stu-id="13711-120">Element</span></span>|<span data-ttu-id="13711-121">描述</span><span class="sxs-lookup"><span data-stu-id="13711-121">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="13711-122">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="13711-122">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="13711-123">包含有关程序集绑定和垃圾回收的信息。</span><span class="sxs-lookup"><span data-stu-id="13711-123">Contains information about assembly binding and garbage collection.</span></span>|

## <a name="remarks"></a><span data-ttu-id="13711-124">备注</span><span class="sxs-lookup"><span data-stu-id="13711-124">Remarks</span></span>

<span data-ttu-id="13711-125">This setting was introduced in .NET Framework 4.8.</span><span class="sxs-lookup"><span data-stu-id="13711-125">This setting was introduced in .NET Framework 4.8.</span></span>

## <a name="see-also"></a><span data-ttu-id="13711-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="13711-126">See also</span></span>

- [<span data-ttu-id="13711-127">Run-time settings schema</span><span class="sxs-lookup"><span data-stu-id="13711-127">Run-time settings schema</span></span>](index.md)
- [<span data-ttu-id="13711-128">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="13711-128">Configuration file schema</span></span>](../index.md)
- [<span data-ttu-id="13711-129">垃圾回收的基本知识</span><span class="sxs-lookup"><span data-stu-id="13711-129">Fundamentals of garbage collection</span></span>](../../../../standard/garbage-collection/fundamentals.md)
- [<span data-ttu-id="13711-130">NET Core run-time config options for GC</span><span class="sxs-lookup"><span data-stu-id="13711-130">NET Core run-time config options for GC</span></span>](../../../../core/run-time-config/garbage-collector.md)
