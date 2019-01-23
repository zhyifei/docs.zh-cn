---
title: '&lt;shadowCopyVerifyByTimestamp&gt;元素'
ms.date: 03/30/2017
helpviewer_keywords:
- <shadowCopyTimeStampVerification> element
- shadowCopyTimeStampVerification element
ms.assetid: 2f1648e5-997b-435e-a4f9-d236c574c66c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9a37e41aa653fb3cd5990b75f3c5467a88660113
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54622255"
---
# <a name="ltshadowcopyverifybytimestampgt-element"></a><span data-ttu-id="7920f-102">&lt;shadowCopyVerifyByTimestamp&gt;元素</span><span class="sxs-lookup"><span data-stu-id="7920f-102">&lt;shadowCopyVerifyByTimestamp&gt; Element</span></span>
<span data-ttu-id="7920f-103">指定卷影复制是否使用 [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] 中引入的默认启动行为，或恢复到 .NET Framework 的早期版本的启动行为。</span><span class="sxs-lookup"><span data-stu-id="7920f-103">Specifies whether shadow copying uses the default startup behavior introduced in the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], or reverts to the startup behavior of earlier versions of the .NET Framework.</span></span>  
  
 <span data-ttu-id="7920f-104">\<配置 > 元素</span><span class="sxs-lookup"><span data-stu-id="7920f-104">\<configuration> Element</span></span>  
<span data-ttu-id="7920f-105">\<运行时 > 元素</span><span class="sxs-lookup"><span data-stu-id="7920f-105">\<runtime> Element</span></span>  
<span data-ttu-id="7920f-106">\<shadowCopyVerifyByTimestamp > 元素</span><span class="sxs-lookup"><span data-stu-id="7920f-106">\<shadowCopyVerifyByTimestamp> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7920f-107">语法</span><span class="sxs-lookup"><span data-stu-id="7920f-107">Syntax</span></span>  
  
```xml  
<shadowCopyVerifyByTimestamp enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7920f-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="7920f-108">Attributes and Elements</span></span>  
 <span data-ttu-id="7920f-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="7920f-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7920f-110">特性</span><span class="sxs-lookup"><span data-stu-id="7920f-110">Attributes</span></span>  
  
|<span data-ttu-id="7920f-111">特性</span><span class="sxs-lookup"><span data-stu-id="7920f-111">Attribute</span></span>|<span data-ttu-id="7920f-112">描述</span><span class="sxs-lookup"><span data-stu-id="7920f-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7920f-113">enabled</span><span class="sxs-lookup"><span data-stu-id="7920f-113">enabled</span></span>|<span data-ttu-id="7920f-114">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="7920f-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="7920f-115">指定是否使用卷影复制的应用程序域进行比较的程序集时间戳时启动，以确定是否已在卷影复制程序集之前更新程序集。</span><span class="sxs-lookup"><span data-stu-id="7920f-115">Specifies whether application domains that use shadow copying compare assembly time stamps when starting up, to determine whether an assembly has been updated before shadow copying the assembly.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="7920f-116">enabled 特性</span><span class="sxs-lookup"><span data-stu-id="7920f-116">enabled Attribute</span></span>  
  
|<span data-ttu-id="7920f-117">值</span><span class="sxs-lookup"><span data-stu-id="7920f-117">Value</span></span>|<span data-ttu-id="7920f-118">描述</span><span class="sxs-lookup"><span data-stu-id="7920f-118">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="7920f-119">true</span><span class="sxs-lookup"><span data-stu-id="7920f-119">true</span></span>|<span data-ttu-id="7920f-120">在启动时，将复制仅后，它们上次复制到卷影复制目录已更新的程序集。</span><span class="sxs-lookup"><span data-stu-id="7920f-120">At startup, copies only assemblies that have been updated since they were last copied to the shadow copy directory.</span></span> <span data-ttu-id="7920f-121">这是默认[!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="7920f-121">This is the default for the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)].</span></span>|  
|<span data-ttu-id="7920f-122">False</span><span class="sxs-lookup"><span data-stu-id="7920f-122">false</span></span>|<span data-ttu-id="7920f-123">将恢复为以前版本的.NET Framework 的启动行为是将在启动时的所有文件复制。</span><span class="sxs-lookup"><span data-stu-id="7920f-123">Reverts to the startup behavior of previous versions of the .NET Framework, which was to copy all files at startup.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7920f-124">子元素</span><span class="sxs-lookup"><span data-stu-id="7920f-124">Child Elements</span></span>  
 <span data-ttu-id="7920f-125">无。</span><span class="sxs-lookup"><span data-stu-id="7920f-125">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7920f-126">父元素</span><span class="sxs-lookup"><span data-stu-id="7920f-126">Parent Elements</span></span>  
  
|<span data-ttu-id="7920f-127">元素</span><span class="sxs-lookup"><span data-stu-id="7920f-127">Element</span></span>|<span data-ttu-id="7920f-128">描述</span><span class="sxs-lookup"><span data-stu-id="7920f-128">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="7920f-129">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="7920f-129">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="7920f-130">包含有关程序集绑定和垃圾回收的信息。</span><span class="sxs-lookup"><span data-stu-id="7920f-130">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7920f-131">备注</span><span class="sxs-lookup"><span data-stu-id="7920f-131">Remarks</span></span>  
 <span data-ttu-id="7920f-132">从开始[!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)]，程序集进行卷影复制仅当其时间戳指示自上次复制到卷影复制目录了这些以来已更改。</span><span class="sxs-lookup"><span data-stu-id="7920f-132">Starting with the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], assemblies are shadow copied only if their time stamps indicate that they have changed since they were last copied to the shadow copy directory.</span></span> <span data-ttu-id="7920f-133">这提高了使用卷影复制，许多应用程序的启动时间，如中所述[卷影复制程序集](../../../../../docs/framework/app-domains/shadow-copy-assemblies.md)。</span><span class="sxs-lookup"><span data-stu-id="7920f-133">This improves startup times for many applications that use shadow copying, as described in [Shadow Copying Assemblies](../../../../../docs/framework/app-domains/shadow-copy-assemblies.md).</span></span> <span data-ttu-id="7920f-134">对于程序集更新百分比和频率都很高的应用程序，可能不会从此行为改变中获益。</span><span class="sxs-lookup"><span data-stu-id="7920f-134">Applications that have a high percentage and frequency of assembly updates might not benefit from this change in behavior.</span></span> <span data-ttu-id="7920f-135">在此情况下，可以使用此元素存储 .NET Framework 早先版本的行为。</span><span class="sxs-lookup"><span data-stu-id="7920f-135">In that case, you can use this element to restore the behavior of previous versions of the .NET Framework.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7920f-136">示例</span><span class="sxs-lookup"><span data-stu-id="7920f-136">Example</span></span>  
 <span data-ttu-id="7920f-137">下面的示例演示如何禁用中卷影复制的默认启动行为[!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)]，并恢复为以前版本的.NET Framework 的启动行为。</span><span class="sxs-lookup"><span data-stu-id="7920f-137">The following example shows how to disable the default startup behavior of shadow copying in the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], and revert to the startup behavior of previous versions of the .NET Framework.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <shadowCopyVerifyByTimestamp enabled="false" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="7920f-138">请参阅</span><span class="sxs-lookup"><span data-stu-id="7920f-138">See also</span></span>
- [<span data-ttu-id="7920f-139">运行时设置架构</span><span class="sxs-lookup"><span data-stu-id="7920f-139">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="7920f-140">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="7920f-140">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="7920f-141">卷影复制程序集</span><span class="sxs-lookup"><span data-stu-id="7920f-141">Shadow Copying Assemblies</span></span>](../../../../../docs/framework/app-domains/shadow-copy-assemblies.md)
