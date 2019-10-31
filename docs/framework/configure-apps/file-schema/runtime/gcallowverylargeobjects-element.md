---
title: <gcAllowVeryLargeObjects> 元素
ms.date: 03/30/2017
helpviewer_keywords:
- gcAllowVeryLargeObjects element
- <gcAllowVeryLargeObjects> element
ms.assetid: 5c7ea24a-39ac-4e5f-83b7-b9f9a1b556ab
ms.openlocfilehash: b6230833808ec45d702502e36f929db4e03173e1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73116794"
---
# <a name="gcallowverylargeobjects-element"></a><span data-ttu-id="d4e8e-102">\<gcAllowVeryLargeObjects > 元素</span><span class="sxs-lookup"><span data-stu-id="d4e8e-102">\<gcAllowVeryLargeObjects> Element</span></span>
<span data-ttu-id="d4e8e-103">在 64 位平台上，启用总大小大于 2 千兆字节 (GB) 的数组。</span><span class="sxs-lookup"><span data-stu-id="d4e8e-103">On 64-bit platforms, enables arrays that are greater than 2 gigabytes (GB) in total size.</span></span>  
  
<span data-ttu-id="d4e8e-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="d4e8e-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="d4e8e-105">&nbsp; &nbsp;[ **\<runtime >** ](runtime-element.md) </span><span class="sxs-lookup"><span data-stu-id="d4e8e-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="d4e8e-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<gcAllowVeryLargeObjects >**</span><span class="sxs-lookup"><span data-stu-id="d4e8e-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<gcAllowVeryLargeObjects>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4e8e-107">语法</span><span class="sxs-lookup"><span data-stu-id="d4e8e-107">Syntax</span></span>  
  
```xml  
<gcAllowVeryLargeObjects    
   enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d4e8e-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="d4e8e-108">Attributes and Elements</span></span>  
 <span data-ttu-id="d4e8e-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="d4e8e-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d4e8e-110">特性</span><span class="sxs-lookup"><span data-stu-id="d4e8e-110">Attributes</span></span>  
  
|<span data-ttu-id="d4e8e-111">特性</span><span class="sxs-lookup"><span data-stu-id="d4e8e-111">Attribute</span></span>|<span data-ttu-id="d4e8e-112">描述</span><span class="sxs-lookup"><span data-stu-id="d4e8e-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="d4e8e-113">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="d4e8e-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="d4e8e-114">指定是否在64位平台上启用了总大小中大于 2 GB 的数组。</span><span class="sxs-lookup"><span data-stu-id="d4e8e-114">Specifies whether arrays that are greater than 2 GB in total size are enabled on 64-bit platforms.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="d4e8e-115">enabled 特性</span><span class="sxs-lookup"><span data-stu-id="d4e8e-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="d4e8e-116">“值”</span><span class="sxs-lookup"><span data-stu-id="d4e8e-116">Value</span></span>|<span data-ttu-id="d4e8e-117">描述</span><span class="sxs-lookup"><span data-stu-id="d4e8e-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="d4e8e-118">总大小中大于 2 GB 的数组未启用。</span><span class="sxs-lookup"><span data-stu-id="d4e8e-118">Arrays greater than 2 GB in total size are not enabled.</span></span> <span data-ttu-id="d4e8e-119">这是默认设置。</span><span class="sxs-lookup"><span data-stu-id="d4e8e-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="d4e8e-120">在64位平台上，总大小中已启用大于 2 GB 的数组。</span><span class="sxs-lookup"><span data-stu-id="d4e8e-120">Arrays greater than 2 GB in total size are enabled on 64-bit platforms.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d4e8e-121">子元素</span><span class="sxs-lookup"><span data-stu-id="d4e8e-121">Child Elements</span></span>  
 <span data-ttu-id="d4e8e-122">无。</span><span class="sxs-lookup"><span data-stu-id="d4e8e-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d4e8e-123">父元素</span><span class="sxs-lookup"><span data-stu-id="d4e8e-123">Parent Elements</span></span>  
  
|<span data-ttu-id="d4e8e-124">元素</span><span class="sxs-lookup"><span data-stu-id="d4e8e-124">Element</span></span>|<span data-ttu-id="d4e8e-125">描述</span><span class="sxs-lookup"><span data-stu-id="d4e8e-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="d4e8e-126">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="d4e8e-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="d4e8e-127">包含有关运行时初始化选项的信息。</span><span class="sxs-lookup"><span data-stu-id="d4e8e-127">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d4e8e-128">备注</span><span class="sxs-lookup"><span data-stu-id="d4e8e-128">Remarks</span></span>  
 <span data-ttu-id="d4e8e-129">在应用程序配置文件中使用此元素可启用大小大于 2 GB 的数组，但不会更改对象大小或数组大小的其他限制：</span><span class="sxs-lookup"><span data-stu-id="d4e8e-129">Using this element in your application configuration file enables arrays that are larger than 2 GB in size, but does not change other limits on object size or array size:</span></span>  
  
- <span data-ttu-id="d4e8e-130">数组中元素的最大数目为 <xref:System.UInt32.MaxValue?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="d4e8e-130">The maximum number of elements in an array is <xref:System.UInt32.MaxValue?displayProperty=nameWithType>.</span></span>  
  
- <span data-ttu-id="d4e8e-131">任何单个维度中的最大索引为2147483591（0x7FFFFFC7）（对于字节数组）和单字节结构数组，2146435071（0X7FEFFFFF）用于其他类型。</span><span class="sxs-lookup"><span data-stu-id="d4e8e-131">The maximum index in any single dimension is 2,147,483,591 (0x7FFFFFC7) for byte arrays and arrays of single-byte structures, and 2,146,435,071 (0X7FEFFFFF) for other types.</span></span>  
  
- <span data-ttu-id="d4e8e-132">字符串和其他非数组对象的最大大小不变。</span><span class="sxs-lookup"><span data-stu-id="d4e8e-132">The maximum size for strings and other non-array objects is unchanged.</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="d4e8e-133">在启用此功能之前，请确保应用程序不包含不安全代码，该代码假定所有数组大小均小于 2 GB。</span><span class="sxs-lookup"><span data-stu-id="d4e8e-133">Before enabling this feature, ensure that your application does not include unsafe code that assumes that all arrays are smaller than 2 GB in size.</span></span> <span data-ttu-id="d4e8e-134">例如，使用数组作为缓冲区的不安全代码可能容易受到缓冲区溢出的攻击，因为假设数组不会超过 2 GB。</span><span class="sxs-lookup"><span data-stu-id="d4e8e-134">For example, unsafe code that uses arrays as buffers might be susceptible to buffer overruns if it is written on the assumption that arrays will not exceed 2 GB.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d4e8e-135">示例</span><span class="sxs-lookup"><span data-stu-id="d4e8e-135">Example</span></span>  
 <span data-ttu-id="d4e8e-136">下面的示例演示如何为应用程序启用此功能。</span><span class="sxs-lookup"><span data-stu-id="d4e8e-136">The following example shows how to enable this feature for an application.</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <gcAllowVeryLargeObjects enabled="true" />  
  </runtime>  
</configuration>  
```  
  
## <a name="supported-in"></a><span data-ttu-id="d4e8e-137">受以下版本支持：</span><span class="sxs-lookup"><span data-stu-id="d4e8e-137">Supported in</span></span>

<span data-ttu-id="d4e8e-138">.NET Framework 4.5 及更高版本</span><span class="sxs-lookup"><span data-stu-id="d4e8e-138">.NET Framework 4.5 and later versions</span></span>

## <a name="see-also"></a><span data-ttu-id="d4e8e-139">请参阅</span><span class="sxs-lookup"><span data-stu-id="d4e8e-139">See also</span></span>

- [<span data-ttu-id="d4e8e-140">运行时设置架构</span><span class="sxs-lookup"><span data-stu-id="d4e8e-140">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="d4e8e-141">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="d4e8e-141">Configuration File Schema</span></span>](../index.md)
