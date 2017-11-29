---
title: "&lt;gcAllowVeryLargeObjects&gt;元素"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- gcAllowVeryLargeObjects element
- <gcAllowVeryLargeObjects> element
ms.assetid: 5c7ea24a-39ac-4e5f-83b7-b9f9a1b556ab
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 49046c343ef749e597402f7e19a08fe1f2c98ca0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="ltgcallowverylargeobjectsgt-element"></a><span data-ttu-id="a292f-102">&lt;gcAllowVeryLargeObjects&gt;元素</span><span class="sxs-lookup"><span data-stu-id="a292f-102">&lt;gcAllowVeryLargeObjects&gt; Element</span></span>
<span data-ttu-id="a292f-103">在 64 位平台上，启用总大小大于 2 千兆字节 (GB) 的数组。</span><span class="sxs-lookup"><span data-stu-id="a292f-103">On 64-bit platforms, enables arrays that are greater than 2 gigabytes (GB) in total size.</span></span>  
  
 <span data-ttu-id="a292f-104">\<配置 > 元素</span><span class="sxs-lookup"><span data-stu-id="a292f-104">\<configuration> Element</span></span>  
<span data-ttu-id="a292f-105">\<运行时 > 元素</span><span class="sxs-lookup"><span data-stu-id="a292f-105">\<runtime> Element</span></span>  
<span data-ttu-id="a292f-106">\<gcAllowVeryLargeObjects > 元素</span><span class="sxs-lookup"><span data-stu-id="a292f-106">\<gcAllowVeryLargeObjects> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a292f-107">语法</span><span class="sxs-lookup"><span data-stu-id="a292f-107">Syntax</span></span>  
  
```xml  
<gcAllowVeryLargeObjects    
   enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a292f-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="a292f-108">Attributes and Elements</span></span>  
 <span data-ttu-id="a292f-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="a292f-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a292f-110">特性</span><span class="sxs-lookup"><span data-stu-id="a292f-110">Attributes</span></span>  
  
|<span data-ttu-id="a292f-111">特性</span><span class="sxs-lookup"><span data-stu-id="a292f-111">Attribute</span></span>|<span data-ttu-id="a292f-112">描述</span><span class="sxs-lookup"><span data-stu-id="a292f-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="a292f-113">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="a292f-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="a292f-114">指定是否在 64 位平台上启用的总大小大于 2 GB 的数组。</span><span class="sxs-lookup"><span data-stu-id="a292f-114">Specifies whether arrays that are greater than 2 GB in total size are enabled on 64-bit platforms.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="a292f-115">enabled 特性</span><span class="sxs-lookup"><span data-stu-id="a292f-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="a292f-116">值</span><span class="sxs-lookup"><span data-stu-id="a292f-116">Value</span></span>|<span data-ttu-id="a292f-117">描述</span><span class="sxs-lookup"><span data-stu-id="a292f-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="a292f-118">未启用大于总大小中的 2 GB 的数组。</span><span class="sxs-lookup"><span data-stu-id="a292f-118">Arrays greater than 2 GB in total size are not enabled.</span></span> <span data-ttu-id="a292f-119">这是默认设置。</span><span class="sxs-lookup"><span data-stu-id="a292f-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="a292f-120">在 64 位平台上启用大于总大小中的 2 GB 的数组。</span><span class="sxs-lookup"><span data-stu-id="a292f-120">Arrays greater than 2 GB in total size are enabled on 64-bit platforms.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a292f-121">子元素</span><span class="sxs-lookup"><span data-stu-id="a292f-121">Child Elements</span></span>  
 <span data-ttu-id="a292f-122">无。</span><span class="sxs-lookup"><span data-stu-id="a292f-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a292f-123">父元素</span><span class="sxs-lookup"><span data-stu-id="a292f-123">Parent Elements</span></span>  
  
|<span data-ttu-id="a292f-124">元素</span><span class="sxs-lookup"><span data-stu-id="a292f-124">Element</span></span>|<span data-ttu-id="a292f-125">描述</span><span class="sxs-lookup"><span data-stu-id="a292f-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="a292f-126">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="a292f-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="a292f-127">包含有关运行时初始化选项的信息。</span><span class="sxs-lookup"><span data-stu-id="a292f-127">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a292f-128">备注</span><span class="sxs-lookup"><span data-stu-id="a292f-128">Remarks</span></span>  
 <span data-ttu-id="a292f-129">在应用程序配置文件中使用此元素启用数组是大于 2 GB 的大小，但不会更改对象大小或数组大小上的其他限制：</span><span class="sxs-lookup"><span data-stu-id="a292f-129">Using this element in your application configuration file enables arrays that are larger than 2 GB in size, but does not change other limits on object size or array size:</span></span>  
  
-   <span data-ttu-id="a292f-130">数组中元素的最大数目是<xref:System.UInt32.MaxValue?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="a292f-130">The maximum number of elements in an array is <xref:System.UInt32.MaxValue?displayProperty=nameWithType>.</span></span>  
  
-   <span data-ttu-id="a292f-131">任何单个维度中的最大索引是 2,147,483,591 字节数组和单字节结构的数组 (0x7FFFFFC7) 和其他类型的 2,146,435,071 (0X7FEFFFFF)。</span><span class="sxs-lookup"><span data-stu-id="a292f-131">The maximum index in any single dimension is 2,147,483,591 (0x7FFFFFC7) for byte arrays and arrays of single-byte structures, and 2,146,435,071 (0X7FEFFFFF) for other types.</span></span>  
  
-   <span data-ttu-id="a292f-132">字符串和其他非数组对象的最大大小保持不变。</span><span class="sxs-lookup"><span data-stu-id="a292f-132">The maximum size for strings and other non-array objects is unchanged.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="a292f-133">启用此功能前，请确保你的应用程序不包括假设所有数组小于 2 GB 大小的不安全代码。</span><span class="sxs-lookup"><span data-stu-id="a292f-133">Before enabling this feature, ensure that your application does not include unsafe code that assumes that all arrays are smaller than 2 GB in size.</span></span> <span data-ttu-id="a292f-134">例如，使用数组作为缓冲区的不安全代码可能容易受到缓冲区溢出如果写入假定数组将不会超过 2 GB。</span><span class="sxs-lookup"><span data-stu-id="a292f-134">For example, unsafe code that uses arrays as buffers might be susceptible to buffer overruns if it is written on the assumption that arrays will not exceed 2 GB.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a292f-135">示例</span><span class="sxs-lookup"><span data-stu-id="a292f-135">Example</span></span>  
 <span data-ttu-id="a292f-136">下面的示例演示如何对应用程序启用此功能。</span><span class="sxs-lookup"><span data-stu-id="a292f-136">The following example shows how to enable this feature for an application.</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <gcAllowVeryLargeObjects enabled="true" />  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a292f-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a292f-137">See Also</span></span>  
 [<span data-ttu-id="a292f-138">运行时设置架构</span><span class="sxs-lookup"><span data-stu-id="a292f-138">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="a292f-139">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="a292f-139">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
