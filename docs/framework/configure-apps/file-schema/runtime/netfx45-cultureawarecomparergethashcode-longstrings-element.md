---
title: <NetFx45_CultureAwareComparerGetHashCode_LongStrings> 元素
ms.date: 03/30/2017
helpviewer_keywords:
- NetFx45_CultureAwareComparerGetHashCode_LongStrings element
- <NetFx45_CultureAwareComparerGetHashCode_LongStrings> element
- GetHashCode method
- hash codes, calculating
ms.assetid: 3a5f38d1-ebc8-44de-aaeb-2929f6e6b48f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bd59d1bcc489f248cbeb397afffb638071df17b6
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/21/2019
ms.locfileid: "69663592"
---
# <a name="netfx45_cultureawarecomparergethashcode_longstrings-element"></a><span data-ttu-id="f7cac-102">\<NetFx45_CultureAwareComparerGetHashCode_LongStrings > 元素</span><span class="sxs-lookup"><span data-stu-id="f7cac-102">\<NetFx45_CultureAwareComparerGetHashCode_LongStrings> Element</span></span>

<span data-ttu-id="f7cac-103">指定运行时是否使用固定的内存量来计算 <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> 方法的哈希代码。</span><span class="sxs-lookup"><span data-stu-id="f7cac-103">Specifies whether the runtime uses a fixed amount of memory to calculate hash codes for the <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="f7cac-104">\<配置 > </span><span class="sxs-lookup"><span data-stu-id="f7cac-104">\<configuration></span></span>\
<span data-ttu-id="f7cac-105">\<运行时 > </span><span class="sxs-lookup"><span data-stu-id="f7cac-105">\<runtime></span></span>\
<span data-ttu-id="f7cac-106">\<NetFx45_CultureAwareComparerGetHashCode_LongStrings></span><span class="sxs-lookup"><span data-stu-id="f7cac-106">\<NetFx45_CultureAwareComparerGetHashCode_LongStrings></span></span>

## <a name="syntax"></a><span data-ttu-id="f7cac-107">语法</span><span class="sxs-lookup"><span data-stu-id="f7cac-107">Syntax</span></span>

```xml
<NetFx45_CultureAwareComparerGetHashCode_LongStrings enabled="0|1">
```

## <a name="attributes-and-elements"></a><span data-ttu-id="f7cac-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="f7cac-108">Attributes and Elements</span></span>

<span data-ttu-id="f7cac-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="f7cac-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="f7cac-110">特性</span><span class="sxs-lookup"><span data-stu-id="f7cac-110">Attributes</span></span>

|<span data-ttu-id="f7cac-111">特性</span><span class="sxs-lookup"><span data-stu-id="f7cac-111">Attribute</span></span>|<span data-ttu-id="f7cac-112">描述</span><span class="sxs-lookup"><span data-stu-id="f7cac-112">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="f7cac-113">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="f7cac-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="f7cac-114">指定公共语言运行时是否在计算哈希代码时分配固定的内存量。</span><span class="sxs-lookup"><span data-stu-id="f7cac-114">Specifies whether the common language runtime allocates a fixed amount of memory when calculating hash codes.</span></span>|

## <a name="enabled-attribute"></a><span data-ttu-id="f7cac-115">enabled 特性</span><span class="sxs-lookup"><span data-stu-id="f7cac-115">enabled Attribute</span></span>

|<span data-ttu-id="f7cac-116">值</span><span class="sxs-lookup"><span data-stu-id="f7cac-116">Value</span></span>|<span data-ttu-id="f7cac-117">Description</span><span class="sxs-lookup"><span data-stu-id="f7cac-117">Description</span></span>|
|-----------|-----------------|
|<span data-ttu-id="f7cac-118">0</span><span class="sxs-lookup"><span data-stu-id="f7cac-118">0</span></span>|<span data-ttu-id="f7cac-119">公共语言运行时为 <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> 方法分配可变的内存量来计算哈希代码。</span><span class="sxs-lookup"><span data-stu-id="f7cac-119">The common language runtime allocates a variable amount of memory for the <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> method to calculate hash codes.</span></span> <span data-ttu-id="f7cac-120">这是默认设置。</span><span class="sxs-lookup"><span data-stu-id="f7cac-120">This is the default.</span></span>|
|<span data-ttu-id="f7cac-121">1</span><span class="sxs-lookup"><span data-stu-id="f7cac-121">1</span></span>|<span data-ttu-id="f7cac-122">公共语言运行时为 <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> 方法分配固定的内存量来计算哈希代码。</span><span class="sxs-lookup"><span data-stu-id="f7cac-122">The common language runtime allocates a fixed amount of memory for the <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> method to calculate hash codes.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="f7cac-123">子元素</span><span class="sxs-lookup"><span data-stu-id="f7cac-123">Child Elements</span></span>

<span data-ttu-id="f7cac-124">无。</span><span class="sxs-lookup"><span data-stu-id="f7cac-124">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="f7cac-125">父元素</span><span class="sxs-lookup"><span data-stu-id="f7cac-125">Parent Elements</span></span>

|<span data-ttu-id="f7cac-126">元素</span><span class="sxs-lookup"><span data-stu-id="f7cac-126">Element</span></span>|<span data-ttu-id="f7cac-127">描述</span><span class="sxs-lookup"><span data-stu-id="f7cac-127">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="f7cac-128">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="f7cac-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="f7cac-129">包含有关运行时初始化选项的信息。</span><span class="sxs-lookup"><span data-stu-id="f7cac-129">Contains information about runtime initialization options.</span></span>|

## <a name="remarks"></a><span data-ttu-id="f7cac-130">备注</span><span class="sxs-lookup"><span data-stu-id="f7cac-130">Remarks</span></span>

<span data-ttu-id="f7cac-131">默认情况下，公共语言运行时将为 <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> 方法分配可变的内存量，当该方法尝试计算非常大的字符串（几百万个字符以上）的哈希代码时，会引发 <xref:System.ArgumentException> 。</span><span class="sxs-lookup"><span data-stu-id="f7cac-131">By default, the common language runtime allocates a variable amount of memory for the <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> method, and an <xref:System.ArgumentException> can be thrown when the method attempts to compute the hash code of very large strings (over several million characters long).</span></span> <span data-ttu-id="f7cac-132">通过将此元素添加到应用程序配置文件并将其 `enabled` 特性设置为“1”，你可以指定 <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> 方法使用可分配固定内存量以计算哈希代码的替代算法。</span><span class="sxs-lookup"><span data-stu-id="f7cac-132">By adding this element to an application configuration file and setting its `enabled` attribute to "1", you can specify that the <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> method use an alternate algorithm that allocates a fixed amount of memory for the computation of hash codes.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f7cac-133">`<NetFx45_CultureAwareComparerGetHashCode_LongStrings>` 元素不在 [!INCLUDE[win8](../../../../../includes/win8-md.md)] 和更高版本中使用。</span><span class="sxs-lookup"><span data-stu-id="f7cac-133">The `<NetFx45_CultureAwareComparerGetHashCode_LongStrings>` element is not used in [!INCLUDE[win8](../../../../../includes/win8-md.md)] and later versions.</span></span>

## <a name="see-also"></a><span data-ttu-id="f7cac-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="f7cac-134">See also</span></span>

- <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType>
- [<span data-ttu-id="f7cac-135">运行时设置架构</span><span class="sxs-lookup"><span data-stu-id="f7cac-135">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="f7cac-136">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="f7cac-136">Configuration File Schema</span></span>](../index.md)
