---
title: '&lt;TimeSpan_LegacyFormatMode&gt;元素'
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
ms.openlocfilehash: d167af6c9e4bbd919a4cfeb279a6d68a14139c33
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54535029"
---
# <a name="lttimespanlegacyformatmodegt-element"></a><span data-ttu-id="48ea4-102">&lt;TimeSpan_LegacyFormatMode&gt;元素</span><span class="sxs-lookup"><span data-stu-id="48ea4-102">&lt;TimeSpan_LegacyFormatMode&gt; Element</span></span>
<span data-ttu-id="48ea4-103">确定运行时是否保留旧行为中的格式设置操作<xref:System.TimeSpan?displayProperty=nameWithType>值。</span><span class="sxs-lookup"><span data-stu-id="48ea4-103">Determines whether the runtime preserves legacy behavior in formatting operations with <xref:System.TimeSpan?displayProperty=nameWithType> values.</span></span>  
  
 <span data-ttu-id="48ea4-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="48ea4-104">\<configuration></span></span>  
<span data-ttu-id="48ea4-105">\<运行时 ></span><span class="sxs-lookup"><span data-stu-id="48ea4-105">\<runtime></span></span>  
<span data-ttu-id="48ea4-106"><TimeSpan_LegacyFormatMode></span><span class="sxs-lookup"><span data-stu-id="48ea4-106"><TimeSpan_LegacyFormatMode></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48ea4-107">语法</span><span class="sxs-lookup"><span data-stu-id="48ea4-107">Syntax</span></span>  
  
```xml  
<TimeSpan_LegacyFormatMode    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="48ea4-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="48ea4-108">Attributes and Elements</span></span>  
 <span data-ttu-id="48ea4-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="48ea4-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="48ea4-110">特性</span><span class="sxs-lookup"><span data-stu-id="48ea4-110">Attributes</span></span>  
  
|<span data-ttu-id="48ea4-111">特性</span><span class="sxs-lookup"><span data-stu-id="48ea4-111">Attribute</span></span>|<span data-ttu-id="48ea4-112">描述</span><span class="sxs-lookup"><span data-stu-id="48ea4-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="48ea4-113">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="48ea4-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="48ea4-114">指定运行时是否使用旧式格式设置行为与<xref:System.TimeSpan?displayProperty=nameWithType>值。</span><span class="sxs-lookup"><span data-stu-id="48ea4-114">Specifies whether the runtime uses legacy formatting behavior with <xref:System.TimeSpan?displayProperty=nameWithType> values.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="48ea4-115">enabled 特性</span><span class="sxs-lookup"><span data-stu-id="48ea4-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="48ea4-116">值</span><span class="sxs-lookup"><span data-stu-id="48ea4-116">Value</span></span>|<span data-ttu-id="48ea4-117">描述</span><span class="sxs-lookup"><span data-stu-id="48ea4-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="48ea4-118">在运行时不会还原旧的格式设置行为。</span><span class="sxs-lookup"><span data-stu-id="48ea4-118">The runtime does not restore legacy formatting behavior.</span></span>|  
|`true`|<span data-ttu-id="48ea4-119">在运行时将还原旧的格式设置行为。</span><span class="sxs-lookup"><span data-stu-id="48ea4-119">The runtime restores legacy formatting behavior.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="48ea4-120">子元素</span><span class="sxs-lookup"><span data-stu-id="48ea4-120">Child Elements</span></span>  
 <span data-ttu-id="48ea4-121">无。</span><span class="sxs-lookup"><span data-stu-id="48ea4-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="48ea4-122">父元素</span><span class="sxs-lookup"><span data-stu-id="48ea4-122">Parent Elements</span></span>  
  
|<span data-ttu-id="48ea4-123">元素</span><span class="sxs-lookup"><span data-stu-id="48ea4-123">Element</span></span>|<span data-ttu-id="48ea4-124">描述</span><span class="sxs-lookup"><span data-stu-id="48ea4-124">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="48ea4-125">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="48ea4-125">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="48ea4-126">包含有关运行时初始化选项的信息。</span><span class="sxs-lookup"><span data-stu-id="48ea4-126">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="48ea4-127">备注</span><span class="sxs-lookup"><span data-stu-id="48ea4-127">Remarks</span></span>  
 <span data-ttu-id="48ea4-128">从开始[!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)]，则<xref:System.TimeSpan?displayProperty=nameWithType>结构实现<xref:System.IFormattable>接口并支持格式设置操作与标准和自定义格式字符串。</span><span class="sxs-lookup"><span data-stu-id="48ea4-128">Starting with the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], the <xref:System.TimeSpan?displayProperty=nameWithType> structure implements the <xref:System.IFormattable> interface and supports formatting operations with standard and custom format strings.</span></span> <span data-ttu-id="48ea4-129">如果分析方法遇到了不受支持的格式说明符或格式字符串，则会引发<xref:System.FormatException>。</span><span class="sxs-lookup"><span data-stu-id="48ea4-129">If a parsing method encounters an unsupported format specifier or format string, it throws a <xref:System.FormatException>.</span></span>  
  
 <span data-ttu-id="48ea4-130">在以前版本的.NET Framework<xref:System.TimeSpan>结构未实现<xref:System.IFormattable>，并且不支持格式字符串。</span><span class="sxs-lookup"><span data-stu-id="48ea4-130">In previous versions of the .NET Framework, the <xref:System.TimeSpan> structure did not implement <xref:System.IFormattable> and did not support format strings.</span></span> <span data-ttu-id="48ea4-131">但是，许多开发人员错误地假定<xref:System.TimeSpan>并支持一组格式字符串并使用它们在[复合格式设置操作](../../../../../docs/standard/base-types/composite-formatting.md)等方法与<xref:System.String.Format%2A?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="48ea4-131">However, many developers mistakenly assumed that <xref:System.TimeSpan> did support a set of format strings and used them in [composite formatting operations](../../../../../docs/standard/base-types/composite-formatting.md) with methods such as <xref:System.String.Format%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="48ea4-132">通常，如果某个类型实现<xref:System.IFormattable>并支持格式字符串，调用格式设置方法与不受支持格式字符串通常引发<xref:System.FormatException>。</span><span class="sxs-lookup"><span data-stu-id="48ea4-132">Ordinarily, if a type implements <xref:System.IFormattable> and supports format strings, calls to formatting methods with unsupported format strings usually throw a <xref:System.FormatException>.</span></span> <span data-ttu-id="48ea4-133">但是，由于<xref:System.TimeSpan>未实现<xref:System.IFormattable>，运行时忽略格式字符串，并改为调用<xref:System.TimeSpan.ToString?displayProperty=nameWithType>方法。</span><span class="sxs-lookup"><span data-stu-id="48ea4-133">However, because <xref:System.TimeSpan> did not implement <xref:System.IFormattable>, the runtime ignored the format string and instead called the <xref:System.TimeSpan.ToString?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="48ea4-134">这意味着，尽管格式字符串，格式设置操作没有影响，但是它们的存在没有导致<xref:System.FormatException>。</span><span class="sxs-lookup"><span data-stu-id="48ea4-134">This means that, although the format strings had no effect on the formatting operation, their presence did not result in a <xref:System.FormatException>.</span></span>  
  
 <span data-ttu-id="48ea4-135">对于在其中旧代码将传递的复合格式设置方法，并为无效格式字符串，而不能重新编译该代码的情况下，你可以使用`<TimeSpan_LegacyFormatMode>`元素来还原旧<xref:System.TimeSpan>行为。</span><span class="sxs-lookup"><span data-stu-id="48ea4-135">For cases in which legacy code passes a composite formatting method and an invalid format string, and that code cannot be recompiled, you can use the `<TimeSpan_LegacyFormatMode>` element to restore the legacy <xref:System.TimeSpan> behavior.</span></span> <span data-ttu-id="48ea4-136">当您将设置`enabled`到此元素的特性`true`、 复合格式设置方法的调用中的结果<xref:System.TimeSpan.ToString?displayProperty=nameWithType>而非<xref:System.TimeSpan.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType>，和一个<xref:System.FormatException>不会引发。</span><span class="sxs-lookup"><span data-stu-id="48ea4-136">When you set the `enabled` attribute of this element to `true`, the composite formatting method results in a call to <xref:System.TimeSpan.ToString?displayProperty=nameWithType> rather than <xref:System.TimeSpan.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType>, and a <xref:System.FormatException> is not thrown.</span></span>  
  
## <a name="example"></a><span data-ttu-id="48ea4-137">示例</span><span class="sxs-lookup"><span data-stu-id="48ea4-137">Example</span></span>  
 <span data-ttu-id="48ea4-138">下面的示例实例化<xref:System.TimeSpan>对象，并尝试将其与格式化<xref:System.String.Format%28System.String%2CSystem.Object%29?displayProperty=nameWithType>使用不受支持的标准格式字符串的方法。</span><span class="sxs-lookup"><span data-stu-id="48ea4-138">The following example instantiates a <xref:System.TimeSpan> object and attempts to format it with the <xref:System.String.Format%28System.String%2CSystem.Object%29?displayProperty=nameWithType> method by using an unsupported standard format string.</span></span>  
  
 [!code-csharp[TimeSpan.BreakingChanges#1](../../../../../samples/snippets/csharp/VS_Snippets_CLR/timespan.breakingchanges/cs/legacyformatmode1.cs#1)]
 [!code-vb[TimeSpan.BreakingChanges#1](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR/timespan.breakingchanges/vb/legacyformatmode1.vb#1)]  
  
 <span data-ttu-id="48ea4-139">上运行此示例[!INCLUDE[net_v35_short](../../../../../includes/net-v35-short-md.md)]或在较早版本，它会显示以下输出：</span><span class="sxs-lookup"><span data-stu-id="48ea4-139">When you run the example on the [!INCLUDE[net_v35_short](../../../../../includes/net-v35-short-md.md)] or on an earlier version, it displays the following output:</span></span>  
  
```  
12:30:45  
```  
  
 <span data-ttu-id="48ea4-140">如果在 [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] 或以后版本上运行此示例，则输出将与此处的输出明显不同：</span><span class="sxs-lookup"><span data-stu-id="48ea4-140">This differs markedly from the output if you run the example on the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] or later version:</span></span>  
  
```  
Invalid Format  
```  
  
 <span data-ttu-id="48ea4-141">但是，如果将下面的配置文件添加到示例的目录中，然后在 [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] 或更高版本上运行此示例，则输出将与示例在 [!INCLUDE[net_v35_short](../../../../../includes/net-v35-short-md.md)] 上运行时产生的输出相同。</span><span class="sxs-lookup"><span data-stu-id="48ea4-141">However, if you add the following configuration file to the example's directory and then run the example on the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] or later version, the output is identical to that produced by the example when it is run on [!INCLUDE[net_v35_short](../../../../../includes/net-v35-short-md.md)].</span></span>  
  
```xml  
<?xml version ="1.0"?>  
<configuration>  
   <runtime>  
      <TimeSpan_LegacyFormatMode enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="48ea4-142">请参阅</span><span class="sxs-lookup"><span data-stu-id="48ea4-142">See also</span></span>
- [<span data-ttu-id="48ea4-143">运行时设置架构</span><span class="sxs-lookup"><span data-stu-id="48ea4-143">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="48ea4-144">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="48ea4-144">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
