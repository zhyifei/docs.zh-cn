---
title: <bypassTrustedAppStrongNames> 元素
ms.date: 03/30/2017
helpviewer_keywords:
- strong-name bypass feature
- bypassTrustedAppStrongNames element
- strong-named assemblies, loading into trusted application domains
- <bypassTrustedAppStrongNames> element
ms.assetid: 71b2ebf6-3843-41e2-ad52-ffa5cd083a40
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6c39d9a1e3da9cccb2f027e9597a6f2272d187ec
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59179135"
---
# <a name="bypasstrustedappstrongnames-element"></a><span data-ttu-id="149ff-102">\<bypassTrustedAppStrongNames > 元素</span><span class="sxs-lookup"><span data-stu-id="149ff-102">\<bypassTrustedAppStrongNames> Element</span></span>
<span data-ttu-id="149ff-103">指定是否以跳过上加载到完全信任的完全信任程序集的强名称验证<xref:System.AppDomain>。</span><span class="sxs-lookup"><span data-stu-id="149ff-103">Specifies whether to bypass the validation of strong names on full-trust assemblies that are loaded into a full-trust <xref:System.AppDomain>.</span></span>  
  
 <span data-ttu-id="149ff-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="149ff-104">\<configuration></span></span>  
<span data-ttu-id="149ff-105">\<运行时 ></span><span class="sxs-lookup"><span data-stu-id="149ff-105">\<runtime></span></span>  
<span data-ttu-id="149ff-106">\<bypassTrustedAppStrongNames></span><span class="sxs-lookup"><span data-stu-id="149ff-106">\<bypassTrustedAppStrongNames></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="149ff-107">语法</span><span class="sxs-lookup"><span data-stu-id="149ff-107">Syntax</span></span>  
  
```xml  
<bypassTrustedAppStrongNames    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="149ff-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="149ff-108">Attributes and Elements</span></span>  
 <span data-ttu-id="149ff-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="149ff-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="149ff-110">特性</span><span class="sxs-lookup"><span data-stu-id="149ff-110">Attributes</span></span>  
  
|<span data-ttu-id="149ff-111">特性</span><span class="sxs-lookup"><span data-stu-id="149ff-111">Attribute</span></span>|<span data-ttu-id="149ff-112">描述</span><span class="sxs-lookup"><span data-stu-id="149ff-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="149ff-113">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="149ff-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="149ff-114">指定是否启用可避免验证完全信任程序集的强名称跳过功能。</span><span class="sxs-lookup"><span data-stu-id="149ff-114">Specifies whether the bypass feature that avoids validating strong names for full-trust assemblies is enabled.</span></span> <span data-ttu-id="149ff-115">启用此功能后，强名称的程序集加载时不验证正确。</span><span class="sxs-lookup"><span data-stu-id="149ff-115">When this feature is enabled, strong names are not validated for correctness when the assembly is loaded.</span></span> <span data-ttu-id="149ff-116">默认值为 `true`。</span><span class="sxs-lookup"><span data-stu-id="149ff-116">The default is `true`.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="149ff-117">enabled 特性</span><span class="sxs-lookup"><span data-stu-id="149ff-117">enabled Attribute</span></span>  
  
|<span data-ttu-id="149ff-118">“值”</span><span class="sxs-lookup"><span data-stu-id="149ff-118">Value</span></span>|<span data-ttu-id="149ff-119">描述</span><span class="sxs-lookup"><span data-stu-id="149ff-119">Description</span></span>|  
|-----------|-----------------|  
|`true`|<span data-ttu-id="149ff-120">加载到完全信任程序集时，不会验证在完全信任程序集的强名称签名<xref:System.AppDomain>。</span><span class="sxs-lookup"><span data-stu-id="149ff-120">Strong-name signatures on full-trust assemblies are not validated when the assemblies are loaded into a full-trust <xref:System.AppDomain>.</span></span> <span data-ttu-id="149ff-121">这是默认设置。</span><span class="sxs-lookup"><span data-stu-id="149ff-121">This is the default.</span></span>|  
|`false`|<span data-ttu-id="149ff-122">在完全信任程序集的强名称签名进行验证时将其加载到完全信任程序集<xref:System.AppDomain>。</span><span class="sxs-lookup"><span data-stu-id="149ff-122">Strong-name signatures on full-trust assemblies are validated when the assemblies are loaded into a full-trust <xref:System.AppDomain>.</span></span> <span data-ttu-id="149ff-123">仅检查签名正确性; 强名称签名与另一个强名称的匹配项，它不进行比较。</span><span class="sxs-lookup"><span data-stu-id="149ff-123">The strong-name signature is checked only for signature correctness; it is not compared to another strong name for a match.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="149ff-124">子元素</span><span class="sxs-lookup"><span data-stu-id="149ff-124">Child Elements</span></span>  
 <span data-ttu-id="149ff-125">无。</span><span class="sxs-lookup"><span data-stu-id="149ff-125">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="149ff-126">父元素</span><span class="sxs-lookup"><span data-stu-id="149ff-126">Parent Elements</span></span>  
  
|<span data-ttu-id="149ff-127">元素</span><span class="sxs-lookup"><span data-stu-id="149ff-127">Element</span></span>|<span data-ttu-id="149ff-128">描述</span><span class="sxs-lookup"><span data-stu-id="149ff-128">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="149ff-129">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="149ff-129">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="149ff-130">包含有关程序集绑定和垃圾回收的信息。</span><span class="sxs-lookup"><span data-stu-id="149ff-130">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="149ff-131">备注</span><span class="sxs-lookup"><span data-stu-id="149ff-131">Remarks</span></span>  
 <span data-ttu-id="149ff-132">强名称跳过功能可避免完全信任程序集的强名称签名验证的开销。</span><span class="sxs-lookup"><span data-stu-id="149ff-132">The strong-name bypass feature avoids the overhead of strong-name signature verification of full-trust assemblies.</span></span>  
  
 <span data-ttu-id="149ff-133">跳过功能适用于使用强名称进行签名及具有以下特征的任何程序集：</span><span class="sxs-lookup"><span data-stu-id="149ff-133">The bypass feature applies to any assembly that is signed with a strong name and that has the following characteristics:</span></span>  
  
-   <span data-ttu-id="149ff-134">完全受信任而无需<xref:System.Security.Policy.StrongName>证据 (例如，具有`MyComputer`区域证据)。</span><span class="sxs-lookup"><span data-stu-id="149ff-134">Fully trusted without the <xref:System.Security.Policy.StrongName> evidence (for example, has `MyComputer` zone evidence).</span></span>  
  
-   <span data-ttu-id="149ff-135">加载到完全受信任的 <xref:System.AppDomain>。</span><span class="sxs-lookup"><span data-stu-id="149ff-135">Loaded into a fully trusted <xref:System.AppDomain>.</span></span>  
  
-   <span data-ttu-id="149ff-136">加载自该 <xref:System.AppDomain> 的 <xref:System.AppDomainSetup.ApplicationBase%2A> 属性下的某个位置。</span><span class="sxs-lookup"><span data-stu-id="149ff-136">Loaded from a location under the <xref:System.AppDomainSetup.ApplicationBase%2A> property of that <xref:System.AppDomain>.</span></span>  
  
-   <span data-ttu-id="149ff-137">签名没有延迟。</span><span class="sxs-lookup"><span data-stu-id="149ff-137">Not delay-signed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="149ff-138">如果跳过功能已禁用的计算机上的所有应用程序使用注册表项，则此配置文件设置无效。</span><span class="sxs-lookup"><span data-stu-id="149ff-138">If the bypass feature has been turned off for all applications on the computer by using a registry key, this configuration file setting has no effect.</span></span> <span data-ttu-id="149ff-139">有关详细信息，请参阅[如何：禁用强名称跳过功能](../../../../../docs/framework/app-domains/how-to-disable-the-strong-name-bypass-feature.md)。</span><span class="sxs-lookup"><span data-stu-id="149ff-139">For more information, see [How to: Disable the Strong-Name Bypass Feature](../../../../../docs/framework/app-domains/how-to-disable-the-strong-name-bypass-feature.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="149ff-140">示例</span><span class="sxs-lookup"><span data-stu-id="149ff-140">Example</span></span>  
 <span data-ttu-id="149ff-141">下面的示例演示如何指定验证上完全信任程序集的强名称签名的行为。</span><span class="sxs-lookup"><span data-stu-id="149ff-141">The following example shows how to specify the behavior that validates the strong-name signature on full-trust assemblies.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <bypassTrustedAppStrongNames enabled="false"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="149ff-142">请参阅</span><span class="sxs-lookup"><span data-stu-id="149ff-142">See also</span></span>

- [<span data-ttu-id="149ff-143">运行时设置架构</span><span class="sxs-lookup"><span data-stu-id="149ff-143">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="149ff-144">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="149ff-144">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="149ff-145">如何：禁用强名称跳过功能</span><span class="sxs-lookup"><span data-stu-id="149ff-145">How to: Disable the Strong-Name Bypass Feature</span></span>](../../../../../docs/framework/app-domains/how-to-disable-the-strong-name-bypass-feature.md)
