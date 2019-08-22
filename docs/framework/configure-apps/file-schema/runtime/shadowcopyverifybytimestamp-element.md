---
title: <shadowCopyVerifyByTimestamp> 元素
ms.date: 03/30/2017
helpviewer_keywords:
- <shadowCopyTimeStampVerification> element
- shadowCopyTimeStampVerification element
ms.assetid: 2f1648e5-997b-435e-a4f9-d236c574c66c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6f3ea57364832553d16c7e34fc887b1c9f821602
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/21/2019
ms.locfileid: "69663453"
---
# <a name="shadowcopyverifybytimestamp-element"></a><span data-ttu-id="cf98e-102">\<shadowCopyVerifyByTimestamp> 元素</span><span class="sxs-lookup"><span data-stu-id="cf98e-102">\<shadowCopyVerifyByTimestamp> Element</span></span>
<span data-ttu-id="cf98e-103">指定卷影复制是否使用 .NET Framework 4 中引入的默认启动行为, 或恢复为 .NET Framework 早期版本的启动行为。</span><span class="sxs-lookup"><span data-stu-id="cf98e-103">Specifies whether shadow copying uses the default startup behavior introduced in the .NET Framework 4, or reverts to the startup behavior of earlier versions of the .NET Framework.</span></span>  
  
 <span data-ttu-id="cf98e-104">\<配置 > 元素</span><span class="sxs-lookup"><span data-stu-id="cf98e-104">\<configuration> Element</span></span>  
<span data-ttu-id="cf98e-105">\<运行时 > 元素</span><span class="sxs-lookup"><span data-stu-id="cf98e-105">\<runtime> Element</span></span>  
<span data-ttu-id="cf98e-106">\<shadowCopyVerifyByTimestamp> 元素</span><span class="sxs-lookup"><span data-stu-id="cf98e-106">\<shadowCopyVerifyByTimestamp> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf98e-107">语法</span><span class="sxs-lookup"><span data-stu-id="cf98e-107">Syntax</span></span>  
  
```xml  
<shadowCopyVerifyByTimestamp enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cf98e-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="cf98e-108">Attributes and Elements</span></span>  
 <span data-ttu-id="cf98e-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="cf98e-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cf98e-110">特性</span><span class="sxs-lookup"><span data-stu-id="cf98e-110">Attributes</span></span>  
  
|<span data-ttu-id="cf98e-111">特性</span><span class="sxs-lookup"><span data-stu-id="cf98e-111">Attribute</span></span>|<span data-ttu-id="cf98e-112">描述</span><span class="sxs-lookup"><span data-stu-id="cf98e-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="cf98e-113">enabled</span><span class="sxs-lookup"><span data-stu-id="cf98e-113">enabled</span></span>|<span data-ttu-id="cf98e-114">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="cf98e-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="cf98e-115">指定在启动时, 使用卷影复制的应用程序域是否对程序集时间戳进行比较, 以确定在卷影复制程序集之前是否更新了程序集。</span><span class="sxs-lookup"><span data-stu-id="cf98e-115">Specifies whether application domains that use shadow copying compare assembly time stamps when starting up, to determine whether an assembly has been updated before shadow copying the assembly.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="cf98e-116">enabled 特性</span><span class="sxs-lookup"><span data-stu-id="cf98e-116">enabled Attribute</span></span>  
  
|<span data-ttu-id="cf98e-117">值</span><span class="sxs-lookup"><span data-stu-id="cf98e-117">Value</span></span>|<span data-ttu-id="cf98e-118">描述</span><span class="sxs-lookup"><span data-stu-id="cf98e-118">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="cf98e-119">真</span><span class="sxs-lookup"><span data-stu-id="cf98e-119">true</span></span>|<span data-ttu-id="cf98e-120">在启动时, 仅复制自上次复制到卷影复制目录以来已更新的程序集。</span><span class="sxs-lookup"><span data-stu-id="cf98e-120">At startup, copies only assemblies that have been updated since they were last copied to the shadow copy directory.</span></span> <span data-ttu-id="cf98e-121">这是 .NET Framework 4 的默认值。</span><span class="sxs-lookup"><span data-stu-id="cf98e-121">This is the default for the .NET Framework 4.</span></span>|  
|<span data-ttu-id="cf98e-122">假</span><span class="sxs-lookup"><span data-stu-id="cf98e-122">false</span></span>|<span data-ttu-id="cf98e-123">恢复到 .NET Framework 以前版本的启动行为, 该行为是在启动时复制所有文件。</span><span class="sxs-lookup"><span data-stu-id="cf98e-123">Reverts to the startup behavior of previous versions of the .NET Framework, which was to copy all files at startup.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="cf98e-124">子元素</span><span class="sxs-lookup"><span data-stu-id="cf98e-124">Child Elements</span></span>  
 <span data-ttu-id="cf98e-125">无。</span><span class="sxs-lookup"><span data-stu-id="cf98e-125">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="cf98e-126">父元素</span><span class="sxs-lookup"><span data-stu-id="cf98e-126">Parent Elements</span></span>  
  
|<span data-ttu-id="cf98e-127">元素</span><span class="sxs-lookup"><span data-stu-id="cf98e-127">Element</span></span>|<span data-ttu-id="cf98e-128">描述</span><span class="sxs-lookup"><span data-stu-id="cf98e-128">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="cf98e-129">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="cf98e-129">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="cf98e-130">包含有关程序集绑定和垃圾回收的信息。</span><span class="sxs-lookup"><span data-stu-id="cf98e-130">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cf98e-131">备注</span><span class="sxs-lookup"><span data-stu-id="cf98e-131">Remarks</span></span>  
 <span data-ttu-id="cf98e-132">从 .NET Framework 4 开始, 仅当程序集的时间戳指示它们自上次复制到卷影复制目录后发生了更改时, 才会对程序集进行卷影复制。</span><span class="sxs-lookup"><span data-stu-id="cf98e-132">Starting with the .NET Framework 4, assemblies are shadow copied only if their time stamps indicate that they have changed since they were last copied to the shadow copy directory.</span></span> <span data-ttu-id="cf98e-133">这会缩短使用卷影复制的许多应用程序的启动时间, 如[卷影复制程序集](../../../app-domains/shadow-copy-assemblies.md)中所述。</span><span class="sxs-lookup"><span data-stu-id="cf98e-133">This improves startup times for many applications that use shadow copying, as described in [Shadow Copying Assemblies](../../../app-domains/shadow-copy-assemblies.md).</span></span> <span data-ttu-id="cf98e-134">对于程序集更新百分比和频率都很高的应用程序，可能不会从此行为改变中获益。</span><span class="sxs-lookup"><span data-stu-id="cf98e-134">Applications that have a high percentage and frequency of assembly updates might not benefit from this change in behavior.</span></span> <span data-ttu-id="cf98e-135">在此情况下，可以使用此元素存储 .NET Framework 早先版本的行为。</span><span class="sxs-lookup"><span data-stu-id="cf98e-135">In that case, you can use this element to restore the behavior of previous versions of the .NET Framework.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cf98e-136">示例</span><span class="sxs-lookup"><span data-stu-id="cf98e-136">Example</span></span>  
 <span data-ttu-id="cf98e-137">下面的示例演示如何在 .NET Framework 4 中禁用卷影复制的默认启动行为, 并还原为以前版本的 .NET Framework 的启动行为。</span><span class="sxs-lookup"><span data-stu-id="cf98e-137">The following example shows how to disable the default startup behavior of shadow copying in the .NET Framework 4, and revert to the startup behavior of previous versions of the .NET Framework.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <shadowCopyVerifyByTimestamp enabled="false" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="cf98e-138">请参阅</span><span class="sxs-lookup"><span data-stu-id="cf98e-138">See also</span></span>

- [<span data-ttu-id="cf98e-139">运行时设置架构</span><span class="sxs-lookup"><span data-stu-id="cf98e-139">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="cf98e-140">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="cf98e-140">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="cf98e-141">卷影复制程序集</span><span class="sxs-lookup"><span data-stu-id="cf98e-141">Shadow Copying Assemblies</span></span>](../../../app-domains/shadow-copy-assemblies.md)
