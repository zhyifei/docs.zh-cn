---
title: GCLOHThreshold 元素
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
# <a name="gclohthreshold-element"></a><span data-ttu-id="10d3d-102">GCLOHThreshold 元素</span><span class="sxs-lookup"><span data-stu-id="10d3d-102">GCLOHThreshold element</span></span>

<span data-ttu-id="10d3d-103">指定导致垃圾回收器将对象置于大对象堆（LOH）上的阈值大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="10d3d-103">Specifies the threshold size, in bytes, that causes the garbage collector to put objects on the large object heap (LOH).</span></span>

<span data-ttu-id="10d3d-104">[\<configuration>](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="10d3d-104">[\<configuration>](../configuration-element.md)</span></span>\
<span data-ttu-id="10d3d-105">&nbsp;&nbsp;[\<运行时 >](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="10d3d-105">&nbsp;&nbsp;[\<runtime>](runtime-element.md)</span></span>\
<span data-ttu-id="10d3d-106">&nbsp;&nbsp;&nbsp;&nbsp;\<GCLOHThreshold ></span><span class="sxs-lookup"><span data-stu-id="10d3d-106">&nbsp;&nbsp;&nbsp;&nbsp;\<GCLOHThreshold></span></span>

## <a name="syntax"></a><span data-ttu-id="10d3d-107">语法</span><span class="sxs-lookup"><span data-stu-id="10d3d-107">Syntax</span></span>

```xml
<GCLOHThreshold
   enabled="nnnn"/>
```

## <a name="attributes"></a><span data-ttu-id="10d3d-108">Attributes</span><span class="sxs-lookup"><span data-stu-id="10d3d-108">Attributes</span></span>

|<span data-ttu-id="10d3d-109">属性</span><span class="sxs-lookup"><span data-stu-id="10d3d-109">Attribute</span></span>|<span data-ttu-id="10d3d-110">说明</span><span class="sxs-lookup"><span data-stu-id="10d3d-110">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="10d3d-111">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="10d3d-111">Required attribute.</span></span><br /><br /><span data-ttu-id="10d3d-112">指定导致对象在大型对象堆上的阈值大小。</span><span class="sxs-lookup"><span data-stu-id="10d3d-112">Specifies the threshold size that causes objects to go on the large object heap.</span></span>|

### <a name="enabled-attribute"></a><span data-ttu-id="10d3d-113">enabled 属性</span><span class="sxs-lookup"><span data-stu-id="10d3d-113">enabled attribute</span></span>

|<span data-ttu-id="10d3d-114">值</span><span class="sxs-lookup"><span data-stu-id="10d3d-114">Value</span></span>|<span data-ttu-id="10d3d-115">说明</span><span class="sxs-lookup"><span data-stu-id="10d3d-115">Description</span></span>|
|-----------|-----------------|
|`nnnn`|<span data-ttu-id="10d3d-116">导致对象在大型对象堆上的阈值大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="10d3d-116">The threshold size, in bytes, that causes objects to go on the large object heap.</span></span>|

## <a name="child-elements"></a><span data-ttu-id="10d3d-117">子元素</span><span class="sxs-lookup"><span data-stu-id="10d3d-117">Child elements</span></span>

<span data-ttu-id="10d3d-118">无。</span><span class="sxs-lookup"><span data-stu-id="10d3d-118">None.</span></span>

## <a name="parent-elements"></a><span data-ttu-id="10d3d-119">父元素</span><span class="sxs-lookup"><span data-stu-id="10d3d-119">Parent elements</span></span>

|<span data-ttu-id="10d3d-120">元素</span><span class="sxs-lookup"><span data-stu-id="10d3d-120">Element</span></span>|<span data-ttu-id="10d3d-121">说明</span><span class="sxs-lookup"><span data-stu-id="10d3d-121">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="10d3d-122">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="10d3d-122">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="10d3d-123">包含有关程序集绑定和垃圾回收的信息。</span><span class="sxs-lookup"><span data-stu-id="10d3d-123">Contains information about assembly binding and garbage collection.</span></span>|

## <a name="remarks"></a><span data-ttu-id="10d3d-124">备注</span><span class="sxs-lookup"><span data-stu-id="10d3d-124">Remarks</span></span>

<span data-ttu-id="10d3d-125">.NET Framework 4.8 中引入了此设置。</span><span class="sxs-lookup"><span data-stu-id="10d3d-125">This setting was introduced in .NET Framework 4.8.</span></span>

## <a name="see-also"></a><span data-ttu-id="10d3d-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="10d3d-126">See also</span></span>

- [<span data-ttu-id="10d3d-127">运行时设置架构</span><span class="sxs-lookup"><span data-stu-id="10d3d-127">Run-time settings schema</span></span>](index.md)
- [<span data-ttu-id="10d3d-128">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="10d3d-128">Configuration file schema</span></span>](../index.md)
- [<span data-ttu-id="10d3d-129">垃圾回收的基本知识</span><span class="sxs-lookup"><span data-stu-id="10d3d-129">Fundamentals of garbage collection</span></span>](../../../../standard/garbage-collection/fundamentals.md)
- [<span data-ttu-id="10d3d-130">用于 GC 的 NET Core 运行时配置选项</span><span class="sxs-lookup"><span data-stu-id="10d3d-130">NET Core run-time config options for GC</span></span>](../../../../core/run-time-config/garbage-collector.md)
