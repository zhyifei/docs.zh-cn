---
title: <startup> 元素
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/startup
- http://schemas.microsoft.com/.NetConfiguration/v2.0#startup
helpviewer_keywords:
- container tags, <startup> element
- <startup> element
- startup element
ms.assetid: 536acfd8-f827-452f-838a-e14fa3b87621
ms.openlocfilehash: e936c069275bfa9f7ac81ef1c6fc6228828182a8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153721"
---
# <a name="startup-element"></a><span data-ttu-id="ac0cf-102">\<启动>元素</span><span class="sxs-lookup"><span data-stu-id="ac0cf-102">\<startup> element</span></span>

<span data-ttu-id="ac0cf-103">指定通用语言运行时启动信息。</span><span class="sxs-lookup"><span data-stu-id="ac0cf-103">Specifies common language runtime startup information.</span></span>

[<span data-ttu-id="ac0cf-104">**\<配置>**</span><span class="sxs-lookup"><span data-stu-id="ac0cf-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="ac0cf-105">&nbsp;&nbsp;**\<启动>**</span><span class="sxs-lookup"><span data-stu-id="ac0cf-105">&nbsp;&nbsp;**\<startup>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="ac0cf-106">语法</span><span class="sxs-lookup"><span data-stu-id="ac0cf-106">Syntax</span></span>

```xml
<startup useLegacyV2RuntimeActivationPolicy="true|false" >
</startup>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="ac0cf-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="ac0cf-107">Attributes and elements</span></span>

 <span data-ttu-id="ac0cf-108">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="ac0cf-108">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="ac0cf-109">属性</span><span class="sxs-lookup"><span data-stu-id="ac0cf-109">Attributes</span></span>

|<span data-ttu-id="ac0cf-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="ac0cf-110">Attribute</span></span>|<span data-ttu-id="ac0cf-111">说明</span><span class="sxs-lookup"><span data-stu-id="ac0cf-111">Description</span></span>|
|---------------|-----------------|
|`useLegacyV2RuntimeActivationPolicy`|<span data-ttu-id="ac0cf-112">可选特性。</span><span class="sxs-lookup"><span data-stu-id="ac0cf-112">Optional attribute.</span></span><br /><br /> <span data-ttu-id="ac0cf-113">指定是启用 .NET 框架 2.0 运行时激活策略还是使用 .NET 框架 4 激活策略。</span><span class="sxs-lookup"><span data-stu-id="ac0cf-113">Specifies whether to enable the .NET Framework 2.0 runtime activation policy or to use the .NET Framework 4 activation policy.</span></span>|

## <a name="uselegacyv2runtimeactivationpolicy-attribute"></a><span data-ttu-id="ac0cf-114">使用传统V2运行时激活策略属性</span><span class="sxs-lookup"><span data-stu-id="ac0cf-114">useLegacyV2RuntimeActivationPolicy attribute</span></span>

|<span data-ttu-id="ac0cf-115">值</span><span class="sxs-lookup"><span data-stu-id="ac0cf-115">Value</span></span>|<span data-ttu-id="ac0cf-116">说明</span><span class="sxs-lookup"><span data-stu-id="ac0cf-116">Description</span></span>|
|-----------|-----------------|
|`true`|<span data-ttu-id="ac0cf-117">为所选运行时启用 .NET Framework 2.0 运行时激活策略，即将旧式运行时激活技术（如[CorBindToRuntimeEx 函数](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md)）绑定到从配置文件中选择的运行时，而不是在 CLR 版本 2.0 上将其封顶。</span><span class="sxs-lookup"><span data-stu-id="ac0cf-117">Enable .NET Framework 2.0 runtime activation policy for the chosen runtime, which is to bind legacy runtime activation techniques (such as the [CorBindToRuntimeEx function](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md)) to the runtime chosen from the configuration file instead of capping them at CLR version 2.0.</span></span> <span data-ttu-id="ac0cf-118">因此，如果从配置文件中选择 CLR 版本 4 或更高版本，则使用早期版本的 .NET Framework 创建的混合模式程序集将加载所选 CLR 版本。</span><span class="sxs-lookup"><span data-stu-id="ac0cf-118">Thus, if CLR version 4 or later is chosen from the configuration file, mixed-mode assemblies created with earlier versions of the .NET Framework are loaded with the chosen CLR version.</span></span> <span data-ttu-id="ac0cf-119">设置此值可防止 CLR 版本 1.1 或 CLR 版本 2.0 加载到同一进程中，从而有效地禁用进程内并排功能。</span><span class="sxs-lookup"><span data-stu-id="ac0cf-119">Setting this value prevents CLR version 1.1 or CLR version 2.0 from loading into the same process, effectively disabling the in-process side-by-side feature.</span></span>|
|`false`|<span data-ttu-id="ac0cf-120">对 .NET 框架 4 及更高版本使用默认激活策略，即允许旧式运行时激活技术将 CLR 版本 1.1 或 2.0 加载到进程中。</span><span class="sxs-lookup"><span data-stu-id="ac0cf-120">Use the default activation policy for the .NET Framework 4 and later, which is to allow legacy runtime activation techniques to load CLR version 1.1 or 2.0 into the process.</span></span> <span data-ttu-id="ac0cf-121">设置此值可防止混合模式程序集加载到 .NET 框架 4 或更高版本，除非这些程序集是使用 .NET 框架 4 或更高版本构建的。</span><span class="sxs-lookup"><span data-stu-id="ac0cf-121">Setting this value prevents mixed-mode assemblies from loading into the .NET Framework 4 or later unless they were built with the .NET Framework 4 or later.</span></span> <span data-ttu-id="ac0cf-122">此值为默认值。</span><span class="sxs-lookup"><span data-stu-id="ac0cf-122">This value is the default.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="ac0cf-123">子元素</span><span class="sxs-lookup"><span data-stu-id="ac0cf-123">Child elements</span></span>

|<span data-ttu-id="ac0cf-124">元素</span><span class="sxs-lookup"><span data-stu-id="ac0cf-124">Element</span></span>|<span data-ttu-id="ac0cf-125">说明</span><span class="sxs-lookup"><span data-stu-id="ac0cf-125">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="ac0cf-126">\<所需的运行时></span><span class="sxs-lookup"><span data-stu-id="ac0cf-126">\<requiredRuntime></span></span>](requiredruntime-element.md)|<span data-ttu-id="ac0cf-127">指定应用程序仅支持 1.0 版本的公共语言运行时。</span><span class="sxs-lookup"><span data-stu-id="ac0cf-127">Specifies that the application supports only version 1.0 of the common language runtime.</span></span> <span data-ttu-id="ac0cf-128">使用运行时版本 1.1 或更高版本构建的应用程序应使用**\<支持的 Runtime>** 元素。</span><span class="sxs-lookup"><span data-stu-id="ac0cf-128">Applications built with runtime version 1.1 or later should use the **\<supportedRuntime>** element.</span></span>|
|[<span data-ttu-id="ac0cf-129">\<支持的运行时></span><span class="sxs-lookup"><span data-stu-id="ac0cf-129">\<supportedRuntime></span></span>](supportedruntime-element.md)|<span data-ttu-id="ac0cf-130">指定应用程序支持的公共语言运行时版本。</span><span class="sxs-lookup"><span data-stu-id="ac0cf-130">Specifies which versions of the common language runtime the application supports.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="ac0cf-131">父元素</span><span class="sxs-lookup"><span data-stu-id="ac0cf-131">Parent elements</span></span>

|<span data-ttu-id="ac0cf-132">元素</span><span class="sxs-lookup"><span data-stu-id="ac0cf-132">Element</span></span>|<span data-ttu-id="ac0cf-133">说明</span><span class="sxs-lookup"><span data-stu-id="ac0cf-133">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="ac0cf-134">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="ac0cf-134">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|

## <a name="remarks"></a><span data-ttu-id="ac0cf-135">备注</span><span class="sxs-lookup"><span data-stu-id="ac0cf-135">Remarks</span></span>

 <span data-ttu-id="ac0cf-136">**\<支持的 Runtime>** 元素应由使用运行时版本 1.1 或更高版本构建的所有应用程序使用。</span><span class="sxs-lookup"><span data-stu-id="ac0cf-136">The **\<supportedRuntime>** element should be used by all applications built using version 1.1 or later of the runtime.</span></span> <span data-ttu-id="ac0cf-137">为仅支持运行时版本 1.0 而构建的应用程序必须使用**\<所需的 Runtime>** 元素。</span><span class="sxs-lookup"><span data-stu-id="ac0cf-137">Applications built to support only version 1.0 of the runtime must use the **\<requiredRuntime>** element.</span></span>

 <span data-ttu-id="ac0cf-138">Microsoft Internet Explorer 中托管的应用程序的启动代码忽略**\<启动>** 元素及其子元素。</span><span class="sxs-lookup"><span data-stu-id="ac0cf-138">The startup code for an application hosted in Microsoft Internet Explorer ignores the **\<startup>** element and its child elements.</span></span>

## <a name="the-uselegacyv2runtimeactivationpolicy-attribute"></a><span data-ttu-id="ac0cf-139">使用传统V2运行时激活策略属性</span><span class="sxs-lookup"><span data-stu-id="ac0cf-139">The useLegacyV2RuntimeActivationPolicy attribute</span></span>

 <span data-ttu-id="ac0cf-140">如果应用程序使用旧版激活路径（如[CorBindToRuntimeEx 函数](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md)），并且希望这些路径激活 CLR 的版本 4 而不是早期版本，或者应用程序是使用 .NET 框架 4 构建的，但依赖于使用早期版本的 .NET Framework 构建的混合模式程序集，则此属性非常有用。</span><span class="sxs-lookup"><span data-stu-id="ac0cf-140">This attribute is useful if your application uses legacy activation paths, such as the [CorBindToRuntimeEx function](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md), and you want those paths to activate version 4 of the CLR instead of an earlier version, or if your application is built with the .NET Framework 4 but has a dependency on a mixed-mode assembly built with an earlier version of the .NET Framework.</span></span> <span data-ttu-id="ac0cf-141">在这些情况下，将属性设置为`true`。</span><span class="sxs-lookup"><span data-stu-id="ac0cf-141">In those scenarios, set the attribute to `true`.</span></span>

> [!NOTE]
> <span data-ttu-id="ac0cf-142">设置属性以防止`true`CLR 版本 1.1 或 CLR 版本 2.0 加载到同一进程中，从而有效地禁用进程内并行功能（请参阅[COM 内部操作的并行执行](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8t8td04t(v=vs.100))）。</span><span class="sxs-lookup"><span data-stu-id="ac0cf-142">Setting the attribute to `true` prevents CLR version 1.1 or CLR version 2.0 from loading into the same process, effectively disabling the in-process side-by-side feature (see [Side-by-Side Execution for COM Interop](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8t8td04t(v=vs.100))).</span></span>

## <a name="example"></a><span data-ttu-id="ac0cf-143">示例</span><span class="sxs-lookup"><span data-stu-id="ac0cf-143">Example</span></span>

 <span data-ttu-id="ac0cf-144">下面的示例演示如何在配置文件中指定运行时版本。</span><span class="sxs-lookup"><span data-stu-id="ac0cf-144">The following example shows how to specify the runtime version in a configuration file.</span></span>

```xml
<!-- When used with version 1.0 of the .NET Framework runtime -->
<configuration>
   <startup>
      <requiredRuntime version="v1.0.3705" safemode="true"/>
   </startup>
</configuration>
<!-- When used with version 1.1 (or later) of the runtime -->
<configuration>
   <startup>
      <supportedRuntime version="v1.1.4322"/>
      <supportedRuntime version="v1.0.3705"/>
   </startup>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="ac0cf-145">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ac0cf-145">See also</span></span>

- [<span data-ttu-id="ac0cf-146">启动设置架构</span><span class="sxs-lookup"><span data-stu-id="ac0cf-146">Startup Settings Schema</span></span>](index.md)
- [<span data-ttu-id="ac0cf-147">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="ac0cf-147">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="ac0cf-148">如何：将应用配置为支持 .NET 框架 4 或更高版本</span><span class="sxs-lookup"><span data-stu-id="ac0cf-148">How to: Configure an app to support .NET Framework 4 or later versions</span></span>](../../../migration-guide/how-to-configure-an-app-to-support-net-framework-4-or-4-5.md)
- <span data-ttu-id="ac0cf-149">[COM 互操作的并行执行](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8t8td04t(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="ac0cf-149">[Side-by-Side Execution for COM Interop](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8t8td04t(v=vs.100))</span></span>
- [<span data-ttu-id="ac0cf-150">进程内并行执行</span><span class="sxs-lookup"><span data-stu-id="ac0cf-150">In-Process Side-by-Side Execution</span></span>](../../../deployment/in-process-side-by-side-execution.md)
