---
title: '&lt;NetFx40_LegacySecurityPolicy&gt;元素'
ms.date: 03/30/2017
helpviewer_keywords:
- <NetFx40_LegacySecurityPolicy> element
- NetFx40_LegacySecurityPolicy element
ms.assetid: 07132b9c-4a72-4710-99d7-e702405e02d4
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7045623872364160d76f4bc0c1522b0450a81bd2
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/19/2018
ms.locfileid: "53611589"
---
# <a name="ltnetfx40legacysecuritypolicygt-element"></a><span data-ttu-id="a69b1-102">&lt;NetFx40_LegacySecurityPolicy&gt;元素</span><span class="sxs-lookup"><span data-stu-id="a69b1-102">&lt;NetFx40_LegacySecurityPolicy&gt; Element</span></span>
<span data-ttu-id="a69b1-103">指定运行时是否使用旧版代码访问安全性 (CAS) 策略。</span><span class="sxs-lookup"><span data-stu-id="a69b1-103">Specifies whether the runtime uses legacy code access security (CAS) policy.</span></span>  
  
 <span data-ttu-id="a69b1-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="a69b1-104">\<configuration></span></span>  
<span data-ttu-id="a69b1-105">\<运行时 ></span><span class="sxs-lookup"><span data-stu-id="a69b1-105">\<runtime></span></span>  
<span data-ttu-id="a69b1-106"><NetFx40_LegacySecurityPolicy></span><span class="sxs-lookup"><span data-stu-id="a69b1-106"><NetFx40_LegacySecurityPolicy></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a69b1-107">语法</span><span class="sxs-lookup"><span data-stu-id="a69b1-107">Syntax</span></span>  
  
```xml  
<NetFx40_LegacySecurityPolicy  
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a69b1-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="a69b1-108">Attributes and Elements</span></span>  
 <span data-ttu-id="a69b1-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="a69b1-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a69b1-110">特性</span><span class="sxs-lookup"><span data-stu-id="a69b1-110">Attributes</span></span>  
  
|<span data-ttu-id="a69b1-111">特性</span><span class="sxs-lookup"><span data-stu-id="a69b1-111">Attribute</span></span>|<span data-ttu-id="a69b1-112">描述</span><span class="sxs-lookup"><span data-stu-id="a69b1-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="a69b1-113">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="a69b1-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="a69b1-114">指定运行时是否使用旧版 CAS 策略。</span><span class="sxs-lookup"><span data-stu-id="a69b1-114">Specifies whether the runtime uses legacy CAS policy.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="a69b1-115">enabled 特性</span><span class="sxs-lookup"><span data-stu-id="a69b1-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="a69b1-116">值</span><span class="sxs-lookup"><span data-stu-id="a69b1-116">Value</span></span>|<span data-ttu-id="a69b1-117">描述</span><span class="sxs-lookup"><span data-stu-id="a69b1-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="a69b1-118">在运行时不使用旧版 CAS 策略。</span><span class="sxs-lookup"><span data-stu-id="a69b1-118">The runtime does not use legacy CAS policy.</span></span> <span data-ttu-id="a69b1-119">这是默认设置。</span><span class="sxs-lookup"><span data-stu-id="a69b1-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="a69b1-120">运行时使用旧版 CAS 策略。</span><span class="sxs-lookup"><span data-stu-id="a69b1-120">The runtime uses legacy CAS policy.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a69b1-121">子元素</span><span class="sxs-lookup"><span data-stu-id="a69b1-121">Child Elements</span></span>  
 <span data-ttu-id="a69b1-122">无。</span><span class="sxs-lookup"><span data-stu-id="a69b1-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a69b1-123">父元素</span><span class="sxs-lookup"><span data-stu-id="a69b1-123">Parent Elements</span></span>  
  
|<span data-ttu-id="a69b1-124">元素</span><span class="sxs-lookup"><span data-stu-id="a69b1-124">Element</span></span>|<span data-ttu-id="a69b1-125">描述</span><span class="sxs-lookup"><span data-stu-id="a69b1-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="a69b1-126">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="a69b1-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="a69b1-127">包含有关运行时初始化选项的信息。</span><span class="sxs-lookup"><span data-stu-id="a69b1-127">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a69b1-128">备注</span><span class="sxs-lookup"><span data-stu-id="a69b1-128">Remarks</span></span>  
 <span data-ttu-id="a69b1-129">在.NET Framework 版本 3.5 和更早版本中，CAS 策略都起作用。</span><span class="sxs-lookup"><span data-stu-id="a69b1-129">In the .NET Framework version 3.5 and earlier versions, CAS policy is always in effect.</span></span> <span data-ttu-id="a69b1-130">在[!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)]，必须启用 CAS 策略。</span><span class="sxs-lookup"><span data-stu-id="a69b1-130">In the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], CAS policy must be enabled.</span></span>  
  
 <span data-ttu-id="a69b1-131">CAS 策略是特定于版本的。</span><span class="sxs-lookup"><span data-stu-id="a69b1-131">CAS policy is version-specific.</span></span> <span data-ttu-id="a69b1-132">.NET Framework 的早期版本中存在的自定义 CA 策略必须中再次指定[!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="a69b1-132">Custom CAS policies that exist in earlier versions of the .NET Framework must be respecified in the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)].</span></span>  
  
 <span data-ttu-id="a69b1-133">将应用`<NetFx40_LegacySecurityPolicy>`元素[!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)]程序集不会影响[安全透明代码](../../../../../docs/framework/misc/security-transparent-code.md); 透明度规则仍然适用。</span><span class="sxs-lookup"><span data-stu-id="a69b1-133">Applying the `<NetFx40_LegacySecurityPolicy>` element to a [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] assembly does not affect [security-transparent code](../../../../../docs/framework/misc/security-transparent-code.md); the transparency rules still apply.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="a69b1-134">将应用`<NetFx40_LegacySecurityPolicy>`元素创建的本机映像程序集可能导致显著的性能损失[本机映像生成器 (Ngen.exe)](../../../../../docs/framework/tools/ngen-exe-native-image-generator.md)是否未安装在[全局程序集缓存](../../../../../docs/framework/app-domains/gac.md).</span><span class="sxs-lookup"><span data-stu-id="a69b1-134">Applying the `<NetFx40_LegacySecurityPolicy>` element can result in significant performance penalties for native image assemblies created by the [Native Image Generator (Ngen.exe)](../../../../../docs/framework/tools/ngen-exe-native-image-generator.md) that are not installed in the [global assembly cache](../../../../../docs/framework/app-domains/gac.md).</span></span> <span data-ttu-id="a69b1-135">性能下降由运行时无法应用该特性为本机图像加载程序集，从而导致其被加载，在实时程序集。</span><span class="sxs-lookup"><span data-stu-id="a69b1-135">The performance degradation is caused by the inability of the runtime to load the assemblies as native images when the attribute is applied, resulting in their being loaded as just-in-time assemblies.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a69b1-136">如果指定的目标.NET Framework 版本早于[!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)]在项目设置为你的 Visual Studio 项目中，CAS 策略将启用，包括为该版本指定任何自定义 CA 策略。</span><span class="sxs-lookup"><span data-stu-id="a69b1-136">If you specify a target .NET Framework version that is earlier than the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] in the project settings for your Visual Studio project, CAS policy will be enabled, including any custom CAS policies you specified for that version.</span></span> <span data-ttu-id="a69b1-137">但是，你将无法再使用新的[!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)]类型和成员。</span><span class="sxs-lookup"><span data-stu-id="a69b1-137">However, you will not be able to use new [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] types and members.</span></span> <span data-ttu-id="a69b1-138">此外可以通过使用指定的.NET framework 早期版本[ \<supportedRuntime > 元素](../../../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md)启动设置架构中你[应用程序配置文件](../../../../../docs/framework/configure-apps/index.md)。</span><span class="sxs-lookup"><span data-stu-id="a69b1-138">You can also specify an earlier version of the .NET Framework by using the [\<supportedRuntime> element](../../../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md) in the startup settings schema in your [application configuration file](../../../../../docs/framework/configure-apps/index.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a69b1-139">配置文件语法是区分大小写。</span><span class="sxs-lookup"><span data-stu-id="a69b1-139">Configuration file syntax is case-sensitive.</span></span> <span data-ttu-id="a69b1-140">在语法和示例部分中所述，应使用语法。</span><span class="sxs-lookup"><span data-stu-id="a69b1-140">You should use the syntax as provided in the Syntax and Example sections.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="a69b1-141">配置文件</span><span class="sxs-lookup"><span data-stu-id="a69b1-141">Configuration File</span></span>  
 <span data-ttu-id="a69b1-142">仅在应用程序配置文件中，可以使用此元素。</span><span class="sxs-lookup"><span data-stu-id="a69b1-142">This element can be used only in the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a69b1-143">示例</span><span class="sxs-lookup"><span data-stu-id="a69b1-143">Example</span></span>  
 <span data-ttu-id="a69b1-144">下面的示例演示如何启用旧版 CAS 策略的应用程序。</span><span class="sxs-lookup"><span data-stu-id="a69b1-144">The following example shows how to enable legacy CAS policy for an application.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <NetFx40_LegacySecurityPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a69b1-145">请参阅</span><span class="sxs-lookup"><span data-stu-id="a69b1-145">See Also</span></span>  
- [<span data-ttu-id="a69b1-146">运行时设置架构</span><span class="sxs-lookup"><span data-stu-id="a69b1-146">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
- [<span data-ttu-id="a69b1-147">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="a69b1-147">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
