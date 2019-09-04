---
title: <NetFx40_LegacySecurityPolicy> 元素
ms.date: 03/30/2017
helpviewer_keywords:
- <NetFx40_LegacySecurityPolicy> element
- NetFx40_LegacySecurityPolicy element
ms.assetid: 07132b9c-4a72-4710-99d7-e702405e02d4
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2cd6f937811ae503dd4de7ff989510c4eb8b8933
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252446"
---
# <a name="netfx40_legacysecuritypolicy-element"></a><span data-ttu-id="ceca9-102">\<Y > 元素</span><span class="sxs-lookup"><span data-stu-id="ceca9-102">\<NetFx40_LegacySecurityPolicy> Element</span></span>

<span data-ttu-id="ceca9-103">指定运行时是否使用旧版代码访问安全性 (CAS) 策略。</span><span class="sxs-lookup"><span data-stu-id="ceca9-103">Specifies whether the runtime uses legacy code access security (CAS) policy.</span></span>

<span data-ttu-id="ceca9-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="ceca9-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="ceca9-105">&nbsp;&nbsp;[ **\<运行时 >** ](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="ceca9-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="ceca9-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<Y >**</span><span class="sxs-lookup"><span data-stu-id="ceca9-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<NetFx40_LegacySecurityPolicy>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="ceca9-107">语法</span><span class="sxs-lookup"><span data-stu-id="ceca9-107">Syntax</span></span>

```xml
<NetFx40_LegacySecurityPolicy
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="ceca9-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="ceca9-108">Attributes and Elements</span></span>

<span data-ttu-id="ceca9-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="ceca9-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="ceca9-110">特性</span><span class="sxs-lookup"><span data-stu-id="ceca9-110">Attributes</span></span>

|<span data-ttu-id="ceca9-111">特性</span><span class="sxs-lookup"><span data-stu-id="ceca9-111">Attribute</span></span>|<span data-ttu-id="ceca9-112">描述</span><span class="sxs-lookup"><span data-stu-id="ceca9-112">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="ceca9-113">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="ceca9-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="ceca9-114">指定运行时是否使用旧版 CAS 策略。</span><span class="sxs-lookup"><span data-stu-id="ceca9-114">Specifies whether the runtime uses legacy CAS policy.</span></span>|

## <a name="enabled-attribute"></a><span data-ttu-id="ceca9-115">enabled 特性</span><span class="sxs-lookup"><span data-stu-id="ceca9-115">enabled Attribute</span></span>

|<span data-ttu-id="ceca9-116">值</span><span class="sxs-lookup"><span data-stu-id="ceca9-116">Value</span></span>|<span data-ttu-id="ceca9-117">描述</span><span class="sxs-lookup"><span data-stu-id="ceca9-117">Description</span></span>|
|-----------|-----------------|
|`false`|<span data-ttu-id="ceca9-118">运行时不使用旧的 CAS 策略。</span><span class="sxs-lookup"><span data-stu-id="ceca9-118">The runtime does not use legacy CAS policy.</span></span> <span data-ttu-id="ceca9-119">这是默认设置。</span><span class="sxs-lookup"><span data-stu-id="ceca9-119">This is the default.</span></span>|
|`true`|<span data-ttu-id="ceca9-120">运行时使用旧版 CAS 策略。</span><span class="sxs-lookup"><span data-stu-id="ceca9-120">The runtime uses legacy CAS policy.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="ceca9-121">子元素</span><span class="sxs-lookup"><span data-stu-id="ceca9-121">Child Elements</span></span>

<span data-ttu-id="ceca9-122">无。</span><span class="sxs-lookup"><span data-stu-id="ceca9-122">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="ceca9-123">父元素</span><span class="sxs-lookup"><span data-stu-id="ceca9-123">Parent Elements</span></span>

|<span data-ttu-id="ceca9-124">元素</span><span class="sxs-lookup"><span data-stu-id="ceca9-124">Element</span></span>|<span data-ttu-id="ceca9-125">描述</span><span class="sxs-lookup"><span data-stu-id="ceca9-125">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="ceca9-126">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="ceca9-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="ceca9-127">包含有关运行时初始化选项的信息。</span><span class="sxs-lookup"><span data-stu-id="ceca9-127">Contains information about runtime initialization options.</span></span>|

## <a name="remarks"></a><span data-ttu-id="ceca9-128">备注</span><span class="sxs-lookup"><span data-stu-id="ceca9-128">Remarks</span></span>

<span data-ttu-id="ceca9-129">在 .NET Framework 版本3.5 及更低版本中，CAS 策略始终有效。</span><span class="sxs-lookup"><span data-stu-id="ceca9-129">In the .NET Framework version 3.5 and earlier versions, CAS policy is always in effect.</span></span> <span data-ttu-id="ceca9-130">在 .NET Framework 4 中，必须启用 CAS 策略。</span><span class="sxs-lookup"><span data-stu-id="ceca9-130">In the .NET Framework 4, CAS policy must be enabled.</span></span>

<span data-ttu-id="ceca9-131">CA 策略是特定于版本的。</span><span class="sxs-lookup"><span data-stu-id="ceca9-131">CAS policy is version-specific.</span></span> <span data-ttu-id="ceca9-132">.NET Framework 早期版本中存在的自定义 CAS 策略必须在 .NET Framework 4 中 respecified。</span><span class="sxs-lookup"><span data-stu-id="ceca9-132">Custom CAS policies that exist in earlier versions of the .NET Framework must be respecified in the .NET Framework 4.</span></span>

<span data-ttu-id="ceca9-133">将元素应用到 .NET Framework 4 程序集并不会影响[安全透明的代码](../../../misc/security-transparent-code.md); 透明规则仍适用。 `<NetFx40_LegacySecurityPolicy>`</span><span class="sxs-lookup"><span data-stu-id="ceca9-133">Applying the `<NetFx40_LegacySecurityPolicy>` element to a .NET Framework 4 assembly does not affect [security-transparent code](../../../misc/security-transparent-code.md); the transparency rules still apply.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ceca9-134">对于未安装在[全局程序集缓存](../../../app-domains/gac.md)中的[本机映像生成器（ngen.exe）](../../../tools/ngen-exe-native-image-generator.md)创建的本机映像程序集，应用元素可能会导致严重的性能下降。`<NetFx40_LegacySecurityPolicy>`</span><span class="sxs-lookup"><span data-stu-id="ceca9-134">Applying the `<NetFx40_LegacySecurityPolicy>` element can result in significant performance penalties for native image assemblies created by the [Native Image Generator (Ngen.exe)](../../../tools/ngen-exe-native-image-generator.md) that are not installed in the [global assembly cache](../../../app-domains/gac.md).</span></span> <span data-ttu-id="ceca9-135">性能下降是由运行时在应用属性时无法将程序集加载为本机映像而导致其作为实时程序集加载的。</span><span class="sxs-lookup"><span data-stu-id="ceca9-135">The performance degradation is caused by the inability of the runtime to load the assemblies as native images when the attribute is applied, resulting in their being loaded as just-in-time assemblies.</span></span>

> [!NOTE]
> <span data-ttu-id="ceca9-136">如果指定的目标 .NET Framework 版本早于 Visual Studio 项目的项目设置中的 .NET Framework 4，则将启用 CAS 策略，包括你为该版本指定的任何自定义 CAS 策略。</span><span class="sxs-lookup"><span data-stu-id="ceca9-136">If you specify a target .NET Framework version that is earlier than the .NET Framework 4 in the project settings for your Visual Studio project, CAS policy will be enabled, including any custom CAS policies you specified for that version.</span></span> <span data-ttu-id="ceca9-137">但是，您将不能使用新 .NET Framework 4 类型和成员。</span><span class="sxs-lookup"><span data-stu-id="ceca9-137">However, you will not be able to use new .NET Framework 4 types and members.</span></span> <span data-ttu-id="ceca9-138">你还可以使用[应用程序配置文件](../../index.md)中的 "启动设置" 架构中的[ \<supportedRuntime > 元素](../startup/supportedruntime-element.md)指定 .NET Framework 的早期版本。</span><span class="sxs-lookup"><span data-stu-id="ceca9-138">You can also specify an earlier version of the .NET Framework by using the [\<supportedRuntime> element](../startup/supportedruntime-element.md) in the startup settings schema in your [application configuration file](../../index.md).</span></span>

> [!NOTE]
> <span data-ttu-id="ceca9-139">配置文件语法区分大小写。</span><span class="sxs-lookup"><span data-stu-id="ceca9-139">Configuration file syntax is case-sensitive.</span></span> <span data-ttu-id="ceca9-140">应使用语法和示例部分中提供的语法。</span><span class="sxs-lookup"><span data-stu-id="ceca9-140">You should use the syntax as provided in the Syntax and Example sections.</span></span>

## <a name="configuration-file"></a><span data-ttu-id="ceca9-141">配置文件</span><span class="sxs-lookup"><span data-stu-id="ceca9-141">Configuration File</span></span>

<span data-ttu-id="ceca9-142">此元素只能在应用程序配置文件中使用。</span><span class="sxs-lookup"><span data-stu-id="ceca9-142">This element can be used only in the application configuration file.</span></span>

## <a name="example"></a><span data-ttu-id="ceca9-143">示例</span><span class="sxs-lookup"><span data-stu-id="ceca9-143">Example</span></span>

<span data-ttu-id="ceca9-144">以下示例演示了如何为应用程序启用旧的 CAS 策略。</span><span class="sxs-lookup"><span data-stu-id="ceca9-144">The following example shows how to enable legacy CAS policy for an application.</span></span>

```xml
<configuration>
   <runtime>
      <NetFx40_LegacySecurityPolicy enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="ceca9-145">请参阅</span><span class="sxs-lookup"><span data-stu-id="ceca9-145">See also</span></span>

- [<span data-ttu-id="ceca9-146">运行时设置架构</span><span class="sxs-lookup"><span data-stu-id="ceca9-146">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="ceca9-147">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="ceca9-147">Configuration File Schema</span></span>](../index.md)
