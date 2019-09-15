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
ms.openlocfilehash: 35b4c6201b5181b8d7241906f60a731e4175d523
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/14/2019
ms.locfileid: "70991226"
---
# <a name="bypasstrustedappstrongnames-element"></a><span data-ttu-id="ffac4-102">\<bypassTrustedAppStrongNames> 元素</span><span class="sxs-lookup"><span data-stu-id="ffac4-102">\<bypassTrustedAppStrongNames> Element</span></span>

<span data-ttu-id="ffac4-103">指定是否在加载到完全信任<xref:System.AppDomain>的完全信任程序集上绕过强名称验证。</span><span class="sxs-lookup"><span data-stu-id="ffac4-103">Specifies whether to bypass the validation of strong names on full-trust assemblies that are loaded into a full-trust <xref:System.AppDomain>.</span></span>

<span data-ttu-id="ffac4-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="ffac4-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="ffac4-105">&nbsp;&nbsp;[ **\<运行时 >** ](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="ffac4-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="ffac4-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<bypassTrustedAppStrongNames>**</span><span class="sxs-lookup"><span data-stu-id="ffac4-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<bypassTrustedAppStrongNames>**</span></span>

## <a name="syntax"></a><span data-ttu-id="ffac4-107">语法</span><span class="sxs-lookup"><span data-stu-id="ffac4-107">Syntax</span></span>

```xml
<bypassTrustedAppStrongNames
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="ffac4-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="ffac4-108">Attributes and Elements</span></span>

<span data-ttu-id="ffac4-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="ffac4-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="ffac4-110">特性</span><span class="sxs-lookup"><span data-stu-id="ffac4-110">Attributes</span></span>

|<span data-ttu-id="ffac4-111">特性</span><span class="sxs-lookup"><span data-stu-id="ffac4-111">Attribute</span></span>|<span data-ttu-id="ffac4-112">描述</span><span class="sxs-lookup"><span data-stu-id="ffac4-112">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="ffac4-113">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="ffac4-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="ffac4-114">指定是否启用回避功能，以避免为完全信任程序集验证强名称。</span><span class="sxs-lookup"><span data-stu-id="ffac4-114">Specifies whether the bypass feature that avoids validating strong names for full-trust assemblies is enabled.</span></span> <span data-ttu-id="ffac4-115">当启用此功能时，加载程序集时，不会验证强名称是否正确。</span><span class="sxs-lookup"><span data-stu-id="ffac4-115">When this feature is enabled, strong names are not validated for correctness when the assembly is loaded.</span></span> <span data-ttu-id="ffac4-116">默认值为 `true`。</span><span class="sxs-lookup"><span data-stu-id="ffac4-116">The default is `true`.</span></span>|

## <a name="enabled-attribute"></a><span data-ttu-id="ffac4-117">enabled 特性</span><span class="sxs-lookup"><span data-stu-id="ffac4-117">enabled Attribute</span></span>

|<span data-ttu-id="ffac4-118">值</span><span class="sxs-lookup"><span data-stu-id="ffac4-118">Value</span></span>|<span data-ttu-id="ffac4-119">描述</span><span class="sxs-lookup"><span data-stu-id="ffac4-119">Description</span></span>|
|-----------|-----------------|
|`true`|<span data-ttu-id="ffac4-120">将程序集加载到完全信任<xref:System.AppDomain>时，不会验证完全信任程序集上的强名称签名。</span><span class="sxs-lookup"><span data-stu-id="ffac4-120">Strong-name signatures on full-trust assemblies are not validated when the assemblies are loaded into a full-trust <xref:System.AppDomain>.</span></span> <span data-ttu-id="ffac4-121">这是默认设置。</span><span class="sxs-lookup"><span data-stu-id="ffac4-121">This is the default.</span></span>|
|`false`|<span data-ttu-id="ffac4-122">将程序集加载到完全信任<xref:System.AppDomain>时，会验证完全信任程序集上的强名称签名。</span><span class="sxs-lookup"><span data-stu-id="ffac4-122">Strong-name signatures on full-trust assemblies are validated when the assemblies are loaded into a full-trust <xref:System.AppDomain>.</span></span> <span data-ttu-id="ffac4-123">仅对签名正确性检查强名称签名;与另一个匹配的强名称没有比较。</span><span class="sxs-lookup"><span data-stu-id="ffac4-123">The strong-name signature is checked only for signature correctness; it is not compared to another strong name for a match.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="ffac4-124">子元素</span><span class="sxs-lookup"><span data-stu-id="ffac4-124">Child Elements</span></span>

<span data-ttu-id="ffac4-125">无。</span><span class="sxs-lookup"><span data-stu-id="ffac4-125">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="ffac4-126">父元素</span><span class="sxs-lookup"><span data-stu-id="ffac4-126">Parent Elements</span></span>

|<span data-ttu-id="ffac4-127">元素</span><span class="sxs-lookup"><span data-stu-id="ffac4-127">Element</span></span>|<span data-ttu-id="ffac4-128">描述</span><span class="sxs-lookup"><span data-stu-id="ffac4-128">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="ffac4-129">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="ffac4-129">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="ffac4-130">包含有关程序集绑定和垃圾回收的信息。</span><span class="sxs-lookup"><span data-stu-id="ffac4-130">Contains information about assembly binding and garbage collection.</span></span>|

## <a name="remarks"></a><span data-ttu-id="ffac4-131">备注</span><span class="sxs-lookup"><span data-stu-id="ffac4-131">Remarks</span></span>

<span data-ttu-id="ffac4-132">强名称跳过功能可避免完全信任程序集的强名称签名验证的系统开销。</span><span class="sxs-lookup"><span data-stu-id="ffac4-132">The strong-name bypass feature avoids the overhead of strong-name signature verification of full-trust assemblies.</span></span>

<span data-ttu-id="ffac4-133">跳过功能适用于使用强名称进行签名及具有以下特征的任何程序集：</span><span class="sxs-lookup"><span data-stu-id="ffac4-133">The bypass feature applies to any assembly that is signed with a strong name and that has the following characteristics:</span></span>

- <span data-ttu-id="ffac4-134">完全受信任， <xref:System.Security.Policy.StrongName>无需证据（如具有`MyComputer`区域证据）。</span><span class="sxs-lookup"><span data-stu-id="ffac4-134">Fully trusted without the <xref:System.Security.Policy.StrongName> evidence (for example, has `MyComputer` zone evidence).</span></span>

- <span data-ttu-id="ffac4-135">加载到完全受信任的 <xref:System.AppDomain>。</span><span class="sxs-lookup"><span data-stu-id="ffac4-135">Loaded into a fully trusted <xref:System.AppDomain>.</span></span>

- <span data-ttu-id="ffac4-136">加载自该 <xref:System.AppDomain> 的 <xref:System.AppDomainSetup.ApplicationBase%2A> 属性下的某个位置。</span><span class="sxs-lookup"><span data-stu-id="ffac4-136">Loaded from a location under the <xref:System.AppDomainSetup.ApplicationBase%2A> property of that <xref:System.AppDomain>.</span></span>

- <span data-ttu-id="ffac4-137">签名没有延迟。</span><span class="sxs-lookup"><span data-stu-id="ffac4-137">Not delay-signed.</span></span>

> [!NOTE]
> <span data-ttu-id="ffac4-138">如果对计算机上的所有应用程序使用注册表项关闭了绕过功能，则此配置文件设置将不起作用。</span><span class="sxs-lookup"><span data-stu-id="ffac4-138">If the bypass feature has been turned off for all applications on the computer by using a registry key, this configuration file setting has no effect.</span></span> <span data-ttu-id="ffac4-139">有关详细信息，请参阅[如何：禁用强名称绕过功能](../../../app-domains/how-to-disable-the-strong-name-bypass-feature.md)。</span><span class="sxs-lookup"><span data-stu-id="ffac4-139">For more information, see [How to: Disable the Strong-Name Bypass Feature](../../../app-domains/how-to-disable-the-strong-name-bypass-feature.md).</span></span>

## <a name="example"></a><span data-ttu-id="ffac4-140">示例</span><span class="sxs-lookup"><span data-stu-id="ffac4-140">Example</span></span>

<span data-ttu-id="ffac4-141">下面的示例演示如何指定对完全信任程序集的强名称签名进行验证的行为。</span><span class="sxs-lookup"><span data-stu-id="ffac4-141">The following example shows how to specify the behavior that validates the strong-name signature on full-trust assemblies.</span></span>

```xml
<configuration>
   <runtime>
      <bypassTrustedAppStrongNames enabled="false"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="ffac4-142">请参阅</span><span class="sxs-lookup"><span data-stu-id="ffac4-142">See also</span></span>

- [<span data-ttu-id="ffac4-143">运行时设置架构</span><span class="sxs-lookup"><span data-stu-id="ffac4-143">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="ffac4-144">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="ffac4-144">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="ffac4-145">如何：禁用强名称跳过功能</span><span class="sxs-lookup"><span data-stu-id="ffac4-145">How to: Disable the strong-name bypass feature</span></span>](../../../../standard/assembly/disable-strong-name-bypass-feature.md)
