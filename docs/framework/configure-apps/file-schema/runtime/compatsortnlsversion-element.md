---
title: <CompatSortNLSVersion> 元素
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- <CompatSortNLSVersion> element
- CompatSortNLSVersion element
ms.assetid: 782cc82e-83f7-404a-80b7-6d3061a8b6e3
ms.openlocfilehash: 30afeb2ab9380db75cbeb723ea15a23e4313c9e8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154265"
---
# <a name="compatsortnlsversion-element"></a><span data-ttu-id="f6cce-102">\<比较排序NLSversion>元素</span><span class="sxs-lookup"><span data-stu-id="f6cce-102">\<CompatSortNLSVersion> Element</span></span>
<span data-ttu-id="f6cce-103">指定在执行字符串比较时，运行时应使用旧排序顺序。</span><span class="sxs-lookup"><span data-stu-id="f6cce-103">Specifies that the runtime should use legacy sort orders when performing string comparisons.</span></span>  
  
<span data-ttu-id="f6cce-104">[**\<配置>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="f6cce-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="f6cce-105">&nbsp;&nbsp;[**\<运行时>**](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="f6cce-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="f6cce-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<比较>**</span><span class="sxs-lookup"><span data-stu-id="f6cce-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<CompatSortNLSVersion>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6cce-107">语法</span><span class="sxs-lookup"><span data-stu-id="f6cce-107">Syntax</span></span>  
  
```xml  
<CompatSortNLSVersion
   enabled="4096"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f6cce-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="f6cce-108">Attributes and Elements</span></span>  
 <span data-ttu-id="f6cce-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="f6cce-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f6cce-110">属性</span><span class="sxs-lookup"><span data-stu-id="f6cce-110">Attributes</span></span>  
  
|<span data-ttu-id="f6cce-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="f6cce-111">Attribute</span></span>|<span data-ttu-id="f6cce-112">说明</span><span class="sxs-lookup"><span data-stu-id="f6cce-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="f6cce-113">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="f6cce-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="f6cce-114">指定要使用其排序顺序的区域设置 ID。</span><span class="sxs-lookup"><span data-stu-id="f6cce-114">Specifies the locale ID whose sort order is to be used.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="f6cce-115">enabled 特性</span><span class="sxs-lookup"><span data-stu-id="f6cce-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="f6cce-116">值</span><span class="sxs-lookup"><span data-stu-id="f6cce-116">Value</span></span>|<span data-ttu-id="f6cce-117">说明</span><span class="sxs-lookup"><span data-stu-id="f6cce-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="f6cce-118">4096</span><span class="sxs-lookup"><span data-stu-id="f6cce-118">4096</span></span>|<span data-ttu-id="f6cce-119">表示备选排序顺序的区域设置 ID。</span><span class="sxs-lookup"><span data-stu-id="f6cce-119">The locale ID that represents an alternate sort order.</span></span> <span data-ttu-id="f6cce-120">在这种情况下，4096 表示 .NET 框架 3.5 和早期版本的排序顺序。</span><span class="sxs-lookup"><span data-stu-id="f6cce-120">In this case, 4096 represents the sort order of the .NET Framework 3.5 and earlier versions.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f6cce-121">子元素</span><span class="sxs-lookup"><span data-stu-id="f6cce-121">Child Elements</span></span>  
 <span data-ttu-id="f6cce-122">无。</span><span class="sxs-lookup"><span data-stu-id="f6cce-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f6cce-123">父元素</span><span class="sxs-lookup"><span data-stu-id="f6cce-123">Parent Elements</span></span>  
  
|<span data-ttu-id="f6cce-124">元素</span><span class="sxs-lookup"><span data-stu-id="f6cce-124">Element</span></span>|<span data-ttu-id="f6cce-125">说明</span><span class="sxs-lookup"><span data-stu-id="f6cce-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="f6cce-126">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="f6cce-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="f6cce-127">包含有关运行时初始化选项的信息。</span><span class="sxs-lookup"><span data-stu-id="f6cce-127">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f6cce-128">备注</span><span class="sxs-lookup"><span data-stu-id="f6cce-128">Remarks</span></span>  
 <span data-ttu-id="f6cce-129">由于在 .NET 框架 4 中由<xref:System.Globalization.CompareInfo?displayProperty=nameWithType>类执行的字符串比较、排序和套管操作符合 Unicode 5.1 标准，因此字符串比较<xref:System.String.Compare%28System.String%2CSystem.String%29?displayProperty=nameWithType>方法<xref:System.String.LastIndexOf%28System.String%29?displayProperty=nameWithType>的结果（如 和）可能与 .NET Framework 的早期版本不同。</span><span class="sxs-lookup"><span data-stu-id="f6cce-129">Because string comparison, sorting, and casing operations performed by the <xref:System.Globalization.CompareInfo?displayProperty=nameWithType> class in the .NET Framework 4 conform to the Unicode 5.1 standard, the results of string comparison methods such as <xref:System.String.Compare%28System.String%2CSystem.String%29?displayProperty=nameWithType> and <xref:System.String.LastIndexOf%28System.String%29?displayProperty=nameWithType> may differ from previous versions of the .NET Framework.</span></span> <span data-ttu-id="f6cce-130">如果应用程序依赖于旧行为，则可以通过将`<CompatSortNLSVersion>`元素包括在应用程序的配置文件中来还原 .NET Framework 3.5 和早期版本中使用的字符串比较和排序规则。</span><span class="sxs-lookup"><span data-stu-id="f6cce-130">If your application depends on legacy behavior, you can restore the string comparison and sorting rules used in the .NET Framework 3.5 and earlier versions by including the `<CompatSortNLSVersion>` element in your application's configuration file.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="f6cce-131">还原旧的字符串比较和排序规则还要求 sort00001000.dll 动态链接库在本地系统上可用。</span><span class="sxs-lookup"><span data-stu-id="f6cce-131">Restoring legacy string comparison and sorting rules also requires the sort00001000.dll dynamic link library to be available on the local system.</span></span>  
  
 <span data-ttu-id="f6cce-132">此外，通过在创建应用程序域时将字符串“NetFx40_Legacy20SortingBehavior”传递到 <xref:System.AppDomainSetup.SetCompatibilitySwitches%2A> 方法，可以在特定的应用程序域中使用旧的字符串排序和比较规则。</span><span class="sxs-lookup"><span data-stu-id="f6cce-132">You can also use legacy string sorting and comparison rules in a specific application domain by passing the string "NetFx40_Legacy20SortingBehavior" to the <xref:System.AppDomainSetup.SetCompatibilitySwitches%2A> method when you create the application domain.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f6cce-133">示例</span><span class="sxs-lookup"><span data-stu-id="f6cce-133">Example</span></span>  
 <span data-ttu-id="f6cce-134">下面的示例实例化两个 <xref:System.String> 对象，并调用 <xref:System.String.Compare%28System.String%2CSystem.String%2CSystem.StringComparison%29?displayProperty=nameWithType> 方法以通过使用当前区域性的约定对它们进行比较。</span><span class="sxs-lookup"><span data-stu-id="f6cce-134">The following example instantiates two <xref:System.String> objects and calls the <xref:System.String.Compare%28System.String%2CSystem.String%2CSystem.StringComparison%29?displayProperty=nameWithType> method to compare them by using the conventions of the current culture.</span></span>  
  
 [!code-csharp[String.BreakingChanges#1](../../../../../samples/snippets/csharp/VS_Snippets_CLR/string.breakingchanges/cs/example1.cs#1)]
 [!code-vb[String.BreakingChanges#1](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR/string.breakingchanges/vb/example1.vb#1)]  
  
 <span data-ttu-id="f6cce-135">在 .NET 框架 4 上运行示例时，将显示以下输出：</span><span class="sxs-lookup"><span data-stu-id="f6cce-135">When you run the example on the .NET Framework 4, it displays the following output:</span></span>
  
```console
sta follows a in the sort order.  
```  
  
 <span data-ttu-id="f6cce-136">这与在 .NET Framework 3.5 上运行示例时显示的输出完全不同：</span><span class="sxs-lookup"><span data-stu-id="f6cce-136">This is completely different from the output that is displayed when you run the example on the .NET Framework 3.5:</span></span>
  
```console
sta equals a in the sort order.  
```  
  
 <span data-ttu-id="f6cce-137">但是，如果将以下配置文件添加到示例的目录中，然后在 .NET Framework 4 上运行示例，则输出与在 .NET Framework 3.5 上运行时的示例生成的输出相同。</span><span class="sxs-lookup"><span data-stu-id="f6cce-137">However, if you add the following configuration file to the example's directory and then run the example on the .NET Framework 4, the output is identical to that produced by the example when it is run on the .NET Framework 3.5.</span></span>  
  
```xml  
<?xml version ="1.0"?>  
<configuration>  
   <runtime>  
      <CompatSortNLSVersion enabled="4096"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f6cce-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f6cce-138">See also</span></span>

- [<span data-ttu-id="f6cce-139">运行时设置架构</span><span class="sxs-lookup"><span data-stu-id="f6cce-139">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="f6cce-140">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="f6cce-140">Configuration File Schema</span></span>](../index.md)
