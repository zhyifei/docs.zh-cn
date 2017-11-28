---
title: "&lt;bypassTrustedAppStrongNames&gt;元素"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- strong-name bypass feature
- bypassTrustedAppStrongNames element
- strong-named assemblies, loading into trusted application domains
- <bypassTrustedAppStrongNames> element
ms.assetid: 71b2ebf6-3843-41e2-ad52-ffa5cd083a40
caps.latest.revision: "18"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2b3e1cb839e9e7fd81a5452c0e034c3552b230cb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="ltbypasstrustedappstrongnamesgt-element"></a><span data-ttu-id="2d180-102">&lt;bypassTrustedAppStrongNames&gt;元素</span><span class="sxs-lookup"><span data-stu-id="2d180-102">&lt;bypassTrustedAppStrongNames&gt; Element</span></span>
<span data-ttu-id="2d180-103">指定是否跳过上加载到完全信任的完全信任程序集的强名称验证<xref:System.AppDomain>。</span><span class="sxs-lookup"><span data-stu-id="2d180-103">Specifies whether to bypass the validation of strong names on full-trust assemblies that are loaded into a full-trust <xref:System.AppDomain>.</span></span>  
  
 <span data-ttu-id="2d180-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="2d180-104">\<configuration></span></span>  
<span data-ttu-id="2d180-105">\<运行时 ></span><span class="sxs-lookup"><span data-stu-id="2d180-105">\<runtime></span></span>  
<span data-ttu-id="2d180-106">\<bypassTrustedAppStrongNames ></span><span class="sxs-lookup"><span data-stu-id="2d180-106">\<bypassTrustedAppStrongNames></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2d180-107">语法</span><span class="sxs-lookup"><span data-stu-id="2d180-107">Syntax</span></span>  
  
```xml  
<bypassTrustedAppStrongNames    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2d180-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="2d180-108">Attributes and Elements</span></span>  
 <span data-ttu-id="2d180-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="2d180-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2d180-110">特性</span><span class="sxs-lookup"><span data-stu-id="2d180-110">Attributes</span></span>  
  
|<span data-ttu-id="2d180-111">特性</span><span class="sxs-lookup"><span data-stu-id="2d180-111">Attribute</span></span>|<span data-ttu-id="2d180-112">描述</span><span class="sxs-lookup"><span data-stu-id="2d180-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="2d180-113">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="2d180-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="2d180-114">指定是否启用可避免验证完全信任程序集的强名称跳过功能。</span><span class="sxs-lookup"><span data-stu-id="2d180-114">Specifies whether the bypass feature that avoids validating strong names for full-trust assemblies is enabled.</span></span> <span data-ttu-id="2d180-115">启用此功能后，强名称的程序集加载时不验证正确。</span><span class="sxs-lookup"><span data-stu-id="2d180-115">When this feature is enabled, strong names are not validated for correctness when the assembly is loaded.</span></span> <span data-ttu-id="2d180-116">默认值为 `true`。</span><span class="sxs-lookup"><span data-stu-id="2d180-116">The default is `true`.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="2d180-117">enabled 特性</span><span class="sxs-lookup"><span data-stu-id="2d180-117">enabled Attribute</span></span>  
  
|<span data-ttu-id="2d180-118">值</span><span class="sxs-lookup"><span data-stu-id="2d180-118">Value</span></span>|<span data-ttu-id="2d180-119">描述</span><span class="sxs-lookup"><span data-stu-id="2d180-119">Description</span></span>|  
|-----------|-----------------|  
|`true`|<span data-ttu-id="2d180-120">加载到完全信任程序集时，不会验证对完全信任程序集的强名称签名<xref:System.AppDomain>。</span><span class="sxs-lookup"><span data-stu-id="2d180-120">Strong-name signatures on full-trust assemblies are not validated when the assemblies are loaded into a full-trust <xref:System.AppDomain>.</span></span> <span data-ttu-id="2d180-121">这是默认设置。</span><span class="sxs-lookup"><span data-stu-id="2d180-121">This is the default.</span></span>|  
|`false`|<span data-ttu-id="2d180-122">在完全信任程序集的强名称签名进行验证加载到完全信任程序集时<xref:System.AppDomain>。</span><span class="sxs-lookup"><span data-stu-id="2d180-122">Strong-name signatures on full-trust assemblies are validated when the assemblies are loaded into a full-trust <xref:System.AppDomain>.</span></span> <span data-ttu-id="2d180-123">仅检查签名正确性; 强名称签名它不与另一个强名称的匹配项。</span><span class="sxs-lookup"><span data-stu-id="2d180-123">The strong-name signature is checked only for signature correctness; it is not compared to another strong name for a match.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2d180-124">子元素</span><span class="sxs-lookup"><span data-stu-id="2d180-124">Child Elements</span></span>  
 <span data-ttu-id="2d180-125">无。</span><span class="sxs-lookup"><span data-stu-id="2d180-125">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2d180-126">父元素</span><span class="sxs-lookup"><span data-stu-id="2d180-126">Parent Elements</span></span>  
  
|<span data-ttu-id="2d180-127">元素</span><span class="sxs-lookup"><span data-stu-id="2d180-127">Element</span></span>|<span data-ttu-id="2d180-128">描述</span><span class="sxs-lookup"><span data-stu-id="2d180-128">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="2d180-129">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="2d180-129">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="2d180-130">包含有关程序集绑定和垃圾回收的信息。</span><span class="sxs-lookup"><span data-stu-id="2d180-130">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2d180-131">备注</span><span class="sxs-lookup"><span data-stu-id="2d180-131">Remarks</span></span>  
 <span data-ttu-id="2d180-132">强名称跳过功能可避免完全信任程序集的强名称签名验证的开销。</span><span class="sxs-lookup"><span data-stu-id="2d180-132">The strong-name bypass feature avoids the overhead of strong-name signature verification of full-trust assemblies.</span></span>  
  
 <span data-ttu-id="2d180-133">跳过功能适用于使用强名称进行签名及具有以下特征的任何程序集：</span><span class="sxs-lookup"><span data-stu-id="2d180-133">The bypass feature applies to any assembly that is signed with a strong name and that has the following characteristics:</span></span>  
  
-   <span data-ttu-id="2d180-134">完全受信任而没有<xref:System.Security.Policy.StrongName>证据 (例如，具有`MyComputer`区域证据)。</span><span class="sxs-lookup"><span data-stu-id="2d180-134">Fully trusted without the <xref:System.Security.Policy.StrongName> evidence (for example, has `MyComputer` zone evidence).</span></span>  
  
-   <span data-ttu-id="2d180-135">加载到完全受信任的 <xref:System.AppDomain>。</span><span class="sxs-lookup"><span data-stu-id="2d180-135">Loaded into a fully trusted <xref:System.AppDomain>.</span></span>  
  
-   <span data-ttu-id="2d180-136">加载自该 <xref:System.AppDomain> 的 <xref:System.AppDomainSetup.ApplicationBase%2A> 属性下的某个位置。</span><span class="sxs-lookup"><span data-stu-id="2d180-136">Loaded from a location under the <xref:System.AppDomainSetup.ApplicationBase%2A> property of that <xref:System.AppDomain>.</span></span>  
  
-   <span data-ttu-id="2d180-137">签名没有延迟。</span><span class="sxs-lookup"><span data-stu-id="2d180-137">Not delay-signed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2d180-138">如果跳过功能已禁用的计算机上的所有应用程序使用注册表项，则此配置文件设置无效。</span><span class="sxs-lookup"><span data-stu-id="2d180-138">If the bypass feature has been turned off for all applications on the computer by using a registry key, this configuration file setting has no effect.</span></span> <span data-ttu-id="2d180-139">有关详细信息，请参阅[如何： 禁用强名称跳过功能](../../../../../docs/framework/app-domains/how-to-disable-the-strong-name-bypass-feature.md)。</span><span class="sxs-lookup"><span data-stu-id="2d180-139">For more information, see [How to: Disable the Strong-Name Bypass Feature](../../../../../docs/framework/app-domains/how-to-disable-the-strong-name-bypass-feature.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="2d180-140">示例</span><span class="sxs-lookup"><span data-stu-id="2d180-140">Example</span></span>  
 <span data-ttu-id="2d180-141">下面的示例演示如何指定行为，用于验证对完全信任程序集的强名称签名。</span><span class="sxs-lookup"><span data-stu-id="2d180-141">The following example shows how to specify the behavior that validates the strong-name signature on full-trust assemblies.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <bypassTrustedAppStrongNames enabled="false"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="2d180-142">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2d180-142">See Also</span></span>  
 [<span data-ttu-id="2d180-143">运行时设置架构</span><span class="sxs-lookup"><span data-stu-id="2d180-143">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="2d180-144">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="2d180-144">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="2d180-145">如何：禁用强名称跳过功能</span><span class="sxs-lookup"><span data-stu-id="2d180-145">How to: Disable the Strong-Name Bypass Feature</span></span>](../../../../../docs/framework/app-domains/how-to-disable-the-strong-name-bypass-feature.md)
