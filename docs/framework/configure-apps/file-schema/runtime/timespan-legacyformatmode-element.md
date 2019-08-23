---
title: <TimeSpan_LegacyFormatMode> 元素
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- <TimeSpan_LegacyFormatMode> element
- TimeSpan_LegacyFormatMode element
ms.assetid: 865e7207-d050-4442-b574-57ea29d5e2d6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f16a2bbd2470b4aec9e95ab67ccb0e736c4c6d02
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69920691"
---
# <a name="timespan_legacyformatmode-element"></a><span data-ttu-id="a5585-102">\<TimeSpan_LegacyFormatMode > 元素</span><span class="sxs-lookup"><span data-stu-id="a5585-102">\<TimeSpan_LegacyFormatMode> Element</span></span>

<span data-ttu-id="a5585-103">确定运行时是否在格式设置操作<xref:System.TimeSpan?displayProperty=nameWithType>中保留值。</span><span class="sxs-lookup"><span data-stu-id="a5585-103">Determines whether the runtime preserves legacy behavior in formatting operations with <xref:System.TimeSpan?displayProperty=nameWithType> values.</span></span>

<span data-ttu-id="a5585-104">\<配置 > </span><span class="sxs-lookup"><span data-stu-id="a5585-104">\<configuration></span></span>\
<span data-ttu-id="a5585-105">\<运行时 > </span><span class="sxs-lookup"><span data-stu-id="a5585-105">\<runtime></span></span>\
<span data-ttu-id="a5585-106">\<TimeSpan_LegacyFormatMode></span><span class="sxs-lookup"><span data-stu-id="a5585-106">\<TimeSpan_LegacyFormatMode></span></span>

## <a name="syntax"></a><span data-ttu-id="a5585-107">语法</span><span class="sxs-lookup"><span data-stu-id="a5585-107">Syntax</span></span>

```xml
<TimeSpan_LegacyFormatMode
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="a5585-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="a5585-108">Attributes and Elements</span></span>

<span data-ttu-id="a5585-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="a5585-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="a5585-110">特性</span><span class="sxs-lookup"><span data-stu-id="a5585-110">Attributes</span></span>

|<span data-ttu-id="a5585-111">特性</span><span class="sxs-lookup"><span data-stu-id="a5585-111">Attribute</span></span>|<span data-ttu-id="a5585-112">描述</span><span class="sxs-lookup"><span data-stu-id="a5585-112">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="a5585-113">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="a5585-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="a5585-114">指定运行时是否对<xref:System.TimeSpan?displayProperty=nameWithType>值使用旧格式设置行为。</span><span class="sxs-lookup"><span data-stu-id="a5585-114">Specifies whether the runtime uses legacy formatting behavior with <xref:System.TimeSpan?displayProperty=nameWithType> values.</span></span>|

## <a name="enabled-attribute"></a><span data-ttu-id="a5585-115">enabled 特性</span><span class="sxs-lookup"><span data-stu-id="a5585-115">enabled Attribute</span></span>

|<span data-ttu-id="a5585-116">值</span><span class="sxs-lookup"><span data-stu-id="a5585-116">Value</span></span>|<span data-ttu-id="a5585-117">描述</span><span class="sxs-lookup"><span data-stu-id="a5585-117">Description</span></span>|
|-----------|-----------------|
|`false`|<span data-ttu-id="a5585-118">运行时不会还原旧的格式设置行为。</span><span class="sxs-lookup"><span data-stu-id="a5585-118">The runtime does not restore legacy formatting behavior.</span></span>|
|`true`|<span data-ttu-id="a5585-119">运行时将还原旧的格式设置行为。</span><span class="sxs-lookup"><span data-stu-id="a5585-119">The runtime restores legacy formatting behavior.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="a5585-120">子元素</span><span class="sxs-lookup"><span data-stu-id="a5585-120">Child Elements</span></span>

<span data-ttu-id="a5585-121">无。</span><span class="sxs-lookup"><span data-stu-id="a5585-121">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="a5585-122">父元素</span><span class="sxs-lookup"><span data-stu-id="a5585-122">Parent Elements</span></span>

|<span data-ttu-id="a5585-123">元素</span><span class="sxs-lookup"><span data-stu-id="a5585-123">Element</span></span>|<span data-ttu-id="a5585-124">描述</span><span class="sxs-lookup"><span data-stu-id="a5585-124">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="a5585-125">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="a5585-125">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="a5585-126">包含有关运行时初始化选项的信息。</span><span class="sxs-lookup"><span data-stu-id="a5585-126">Contains information about runtime initialization options.</span></span>|

## <a name="remarks"></a><span data-ttu-id="a5585-127">备注</span><span class="sxs-lookup"><span data-stu-id="a5585-127">Remarks</span></span>

<span data-ttu-id="a5585-128">从 .NET Framework 4 开始, <xref:System.TimeSpan?displayProperty=nameWithType>结构<xref:System.IFormattable>实现接口, 并支持带有标准和自定义格式字符串的格式设置操作。</span><span class="sxs-lookup"><span data-stu-id="a5585-128">Starting with the .NET Framework 4, the <xref:System.TimeSpan?displayProperty=nameWithType> structure implements the <xref:System.IFormattable> interface and supports formatting operations with standard and custom format strings.</span></span> <span data-ttu-id="a5585-129">如果分析方法遇到不支持的格式说明符或格式字符串, 则将引发<xref:System.FormatException>。</span><span class="sxs-lookup"><span data-stu-id="a5585-129">If a parsing method encounters an unsupported format specifier or format string, it throws a <xref:System.FormatException>.</span></span>

<span data-ttu-id="a5585-130">在 .NET Framework 的以前版本中, <xref:System.TimeSpan>结构未实现<xref:System.IFormattable> , 并且不支持格式字符串。</span><span class="sxs-lookup"><span data-stu-id="a5585-130">In previous versions of the .NET Framework, the <xref:System.TimeSpan> structure did not implement <xref:System.IFormattable> and did not support format strings.</span></span> <span data-ttu-id="a5585-131">但是, 很多开发人员都<xref:System.TimeSpan>认为确实支持一组格式字符串, 并在[复合格式设置操作](../../../../standard/base-types/composite-formatting.md)中将它们用于<xref:System.String.Format%2A?displayProperty=nameWithType>方法 (如)。</span><span class="sxs-lookup"><span data-stu-id="a5585-131">However, many developers mistakenly assumed that <xref:System.TimeSpan> did support a set of format strings and used them in [composite formatting operations](../../../../standard/base-types/composite-formatting.md) with methods such as <xref:System.String.Format%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="a5585-132">通常, 如果某个类型实现<xref:System.IFormattable>并支持格式字符串, 则使用不受支持的格式字符串的格式设置<xref:System.FormatException>方法的调用通常会引发。</span><span class="sxs-lookup"><span data-stu-id="a5585-132">Ordinarily, if a type implements <xref:System.IFormattable> and supports format strings, calls to formatting methods with unsupported format strings usually throw a <xref:System.FormatException>.</span></span> <span data-ttu-id="a5585-133">但是, 因为<xref:System.TimeSpan>未实现<xref:System.IFormattable>, 所以运行时将忽略格式<xref:System.TimeSpan.ToString?displayProperty=nameWithType>字符串, 而改为调用方法。</span><span class="sxs-lookup"><span data-stu-id="a5585-133">However, because <xref:System.TimeSpan> did not implement <xref:System.IFormattable>, the runtime ignored the format string and instead called the <xref:System.TimeSpan.ToString?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="a5585-134">这意味着, 尽管格式字符串对格式设置操作没有影响, 但它们的<xref:System.FormatException>存在不会导致。</span><span class="sxs-lookup"><span data-stu-id="a5585-134">This means that, although the format strings had no effect on the formatting operation, their presence did not result in a <xref:System.FormatException>.</span></span>

<span data-ttu-id="a5585-135">对于旧式代码传递复合格式设置方法和无效格式字符串的情况, 并且无法重新编译该代码, 可以使用`<TimeSpan_LegacyFormatMode>`元素来还原旧<xref:System.TimeSpan>行为。</span><span class="sxs-lookup"><span data-stu-id="a5585-135">For cases in which legacy code passes a composite formatting method and an invalid format string, and that code cannot be recompiled, you can use the `<TimeSpan_LegacyFormatMode>` element to restore the legacy <xref:System.TimeSpan> behavior.</span></span> <span data-ttu-id="a5585-136">将此元素的`enabled`特性设置为`true`时, 复合格式设置方法将<xref:System.TimeSpan.ToString?displayProperty=nameWithType>导致调用而<xref:System.TimeSpan.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType>不是, 并且<xref:System.FormatException>不会引发。</span><span class="sxs-lookup"><span data-stu-id="a5585-136">When you set the `enabled` attribute of this element to `true`, the composite formatting method results in a call to <xref:System.TimeSpan.ToString?displayProperty=nameWithType> rather than <xref:System.TimeSpan.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType>, and a <xref:System.FormatException> is not thrown.</span></span>

## <a name="example"></a><span data-ttu-id="a5585-137">示例</span><span class="sxs-lookup"><span data-stu-id="a5585-137">Example</span></span>

<span data-ttu-id="a5585-138">下面的示例实例化<xref:System.TimeSpan>一个对象, 并使用不受支持<xref:System.String.Format%28System.String%2CSystem.Object%29?displayProperty=nameWithType>的标准格式字符串尝试使用方法对其进行格式设置。</span><span class="sxs-lookup"><span data-stu-id="a5585-138">The following example instantiates a <xref:System.TimeSpan> object and attempts to format it with the <xref:System.String.Format%28System.String%2CSystem.Object%29?displayProperty=nameWithType> method by using an unsupported standard format string.</span></span>

[!code-csharp[TimeSpan.BreakingChanges#1](../../../../../samples/snippets/csharp/VS_Snippets_CLR/timespan.breakingchanges/cs/legacyformatmode1.cs#1)]
[!code-vb[TimeSpan.BreakingChanges#1](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR/timespan.breakingchanges/vb/legacyformatmode1.vb#1)]

<span data-ttu-id="a5585-139">在 .NET Framework 3.5 或更早版本上运行此示例时, 将显示以下输出:</span><span class="sxs-lookup"><span data-stu-id="a5585-139">When you run the example on the .NET Framework 3.5 or on an earlier version, it displays the following output:</span></span>

```
12:30:45
```

<span data-ttu-id="a5585-140">如果在 .NET Framework 4 或更高版本上运行此示例, 则这与输出明显不同:</span><span class="sxs-lookup"><span data-stu-id="a5585-140">This differs markedly from the output if you run the example on the .NET Framework 4 or later version:</span></span>

```
Invalid Format
```

<span data-ttu-id="a5585-141">但是, 如果将下面的配置文件添加到示例的目录中, 然后在 .NET Framework 4 或更高版本上运行此示例, 则输出将与示例在 .NET Framework 3.5 上运行时所生成的输出相同。</span><span class="sxs-lookup"><span data-stu-id="a5585-141">However, if you add the following configuration file to the example's directory and then run the example on the .NET Framework 4 or later version, the output is identical to that produced by the example when it is run on .NET Framework 3.5.</span></span>

```xml
<?xml version ="1.0"?>
<configuration>
   <runtime>
      <TimeSpan_LegacyFormatMode enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="a5585-142">请参阅</span><span class="sxs-lookup"><span data-stu-id="a5585-142">See also</span></span>

- [<span data-ttu-id="a5585-143">运行时设置架构</span><span class="sxs-lookup"><span data-stu-id="a5585-143">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="a5585-144">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="a5585-144">Configuration File Schema</span></span>](../index.md)
