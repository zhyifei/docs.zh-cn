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
ms.openlocfilehash: 634d9c5248c33619abec50d441d95c111febdcbf
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2019
ms.locfileid: "71699413"
---
# <a name="startup-element"></a><span data-ttu-id="6752e-102">\<启动 > 元素</span><span class="sxs-lookup"><span data-stu-id="6752e-102">\<startup> element</span></span>

<span data-ttu-id="6752e-103">指定公共语言运行时启动信息。</span><span class="sxs-lookup"><span data-stu-id="6752e-103">Specifies common language runtime startup information.</span></span>

[<span data-ttu-id="6752e-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="6752e-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="6752e-105">&nbsp;&nbsp; **\<startup>**</span><span class="sxs-lookup"><span data-stu-id="6752e-105">&nbsp;&nbsp;**\<startup>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="6752e-106">语法</span><span class="sxs-lookup"><span data-stu-id="6752e-106">Syntax</span></span>

```xml
<startup useLegacyV2RuntimeActivationPolicy="true|false" > 
</startup>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="6752e-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="6752e-107">Attributes and elements</span></span>

 <span data-ttu-id="6752e-108">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="6752e-108">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="6752e-109">Attributes</span><span class="sxs-lookup"><span data-stu-id="6752e-109">Attributes</span></span>

|<span data-ttu-id="6752e-110">属性</span><span class="sxs-lookup"><span data-stu-id="6752e-110">Attribute</span></span>|<span data-ttu-id="6752e-111">说明</span><span class="sxs-lookup"><span data-stu-id="6752e-111">Description</span></span>|
|---------------|-----------------|
|`useLegacyV2RuntimeActivationPolicy`|<span data-ttu-id="6752e-112">可选特性。</span><span class="sxs-lookup"><span data-stu-id="6752e-112">Optional attribute.</span></span><br /><br /> <span data-ttu-id="6752e-113">指定是启用 .NET Framework 2.0 运行时激活策略还是使用 .NET Framework 4 激活策略。</span><span class="sxs-lookup"><span data-stu-id="6752e-113">Specifies whether to enable the .NET Framework 2.0 runtime activation policy or to use the .NET Framework 4 activation policy.</span></span>|

## <a name="uselegacyv2runtimeactivationpolicy-attribute"></a><span data-ttu-id="6752e-114">useLegacyV2RuntimeActivationPolicy 特性</span><span class="sxs-lookup"><span data-stu-id="6752e-114">useLegacyV2RuntimeActivationPolicy attribute</span></span>

|<span data-ttu-id="6752e-115">值</span><span class="sxs-lookup"><span data-stu-id="6752e-115">Value</span></span>|<span data-ttu-id="6752e-116">说明</span><span class="sxs-lookup"><span data-stu-id="6752e-116">Description</span></span>|
|-----------|-----------------|
|`true`|<span data-ttu-id="6752e-117">为所选运行时启用 .NET Framework 2.0 运行时激活策略，该策略将旧式运行时激活技术（如[CorBindToRuntimeEx 函数](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md)）绑定到从配置文件中选择的运行时，而不是在 CLR 版本2.0 上覆盖它们。</span><span class="sxs-lookup"><span data-stu-id="6752e-117">Enable .NET Framework 2.0 runtime activation policy for the chosen runtime, which is to bind legacy runtime activation techniques (such as the [CorBindToRuntimeEx function](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md)) to the runtime chosen from the configuration file instead of capping them at CLR version 2.0.</span></span> <span data-ttu-id="6752e-118">因此，如果从配置文件中选择了 CLR 版本4或更高版本，则将用所选的 CLR 版本加载随 .NET Framework 早期版本创建的混合模式程序集。</span><span class="sxs-lookup"><span data-stu-id="6752e-118">Thus, if CLR version 4 or later is chosen from the configuration file, mixed-mode assemblies created with earlier versions of the .NET Framework are loaded with the chosen CLR version.</span></span> <span data-ttu-id="6752e-119">设置此值可防止 CLR 版本1.1 或 CLR 版本2.0 加载到同一进程中，从而有效禁用进程内并行功能。</span><span class="sxs-lookup"><span data-stu-id="6752e-119">Setting this value prevents CLR version 1.1 or CLR version 2.0 from loading into the same process, effectively disabling the in-process side-by-side feature.</span></span>|
|`false`|<span data-ttu-id="6752e-120">使用 .NET Framework 4 和更高版本的默认激活策略，这是为了允许旧的运行时激活技术将 CLR 版本1.1 或2.0 加载到进程中。</span><span class="sxs-lookup"><span data-stu-id="6752e-120">Use the default activation policy for the .NET Framework 4 and later, which is to allow legacy runtime activation techniques to load CLR version 1.1 or 2.0 into the process.</span></span> <span data-ttu-id="6752e-121">设置此值可防止混合模式程序集加载到 .NET Framework 4 或更高版本中，除非它们是用 .NET Framework 4 或更高版本生成的。</span><span class="sxs-lookup"><span data-stu-id="6752e-121">Setting this value prevents mixed-mode assemblies from loading into the .NET Framework 4 or later unless they were built with the .NET Framework 4 or later.</span></span> <span data-ttu-id="6752e-122">此值是默认值。</span><span class="sxs-lookup"><span data-stu-id="6752e-122">This value is the default.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="6752e-123">子元素</span><span class="sxs-lookup"><span data-stu-id="6752e-123">Child elements</span></span>

|<span data-ttu-id="6752e-124">元素</span><span class="sxs-lookup"><span data-stu-id="6752e-124">Element</span></span>|<span data-ttu-id="6752e-125">说明</span><span class="sxs-lookup"><span data-stu-id="6752e-125">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="6752e-126">\<requiredRuntime></span><span class="sxs-lookup"><span data-stu-id="6752e-126">\<requiredRuntime></span></span>](requiredruntime-element.md)|<span data-ttu-id="6752e-127">指定应用程序仅支持 1.0 版本的公共语言运行时。</span><span class="sxs-lookup"><span data-stu-id="6752e-127">Specifies that the application supports only version 1.0 of the common language runtime.</span></span> <span data-ttu-id="6752e-128">使用运行时版本1.1 或更高版本生成的应用程序应使用 **\<supportedRuntime >** 元素。</span><span class="sxs-lookup"><span data-stu-id="6752e-128">Applications built with runtime version 1.1 or later should use the **\<supportedRuntime>** element.</span></span>|
|[<span data-ttu-id="6752e-129">\<supportedRuntime></span><span class="sxs-lookup"><span data-stu-id="6752e-129">\<supportedRuntime></span></span>](supportedruntime-element.md)|<span data-ttu-id="6752e-130">指定应用程序支持的公共语言运行时版本。</span><span class="sxs-lookup"><span data-stu-id="6752e-130">Specifies which versions of the common language runtime the application supports.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="6752e-131">父元素</span><span class="sxs-lookup"><span data-stu-id="6752e-131">Parent elements</span></span>

|<span data-ttu-id="6752e-132">元素</span><span class="sxs-lookup"><span data-stu-id="6752e-132">Element</span></span>|<span data-ttu-id="6752e-133">说明</span><span class="sxs-lookup"><span data-stu-id="6752e-133">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="6752e-134">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="6752e-134">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|

## <a name="remarks"></a><span data-ttu-id="6752e-135">备注</span><span class="sxs-lookup"><span data-stu-id="6752e-135">Remarks</span></span>

 <span data-ttu-id="6752e-136">**\<SupportedRuntime>** 元素应由使用 1.1 版或更高版本的运行时版本生成的所有应用程序。</span><span class="sxs-lookup"><span data-stu-id="6752e-136">The **\<supportedRuntime>** element should be used by all applications built using version 1.1 or later of the runtime.</span></span> <span data-ttu-id="6752e-137">构建为仅支持1.0 版运行时的应用程序必须使用 **\<q >** 元素。</span><span class="sxs-lookup"><span data-stu-id="6752e-137">Applications built to support only version 1.0 of the runtime must use the **\<requiredRuntime>** element.</span></span>

 <span data-ttu-id="6752e-138">在 Microsoft Internet Explorer 中托管的应用程序的启动代码将忽略 **\<启动 >** 元素及其子元素。</span><span class="sxs-lookup"><span data-stu-id="6752e-138">The startup code for an application hosted in Microsoft Internet Explorer ignores the **\<startup>** element and its child elements.</span></span>

## <a name="the-uselegacyv2runtimeactivationpolicy-attribute"></a><span data-ttu-id="6752e-139">UseLegacyV2RuntimeActivationPolicy 特性</span><span class="sxs-lookup"><span data-stu-id="6752e-139">The useLegacyV2RuntimeActivationPolicy attribute</span></span>

 <span data-ttu-id="6752e-140">如果你的应用程序使用旧的激活路径（如[CorBindToRuntimeEx 函数](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md)），并且你希望这些路径激活 CLR 版本4（而不是早期版本），或者如果你的应用程序是 .NET Framework 使用 .NET Framework 早期版本生成的混合模式程序集生成的，则此属性很有用。</span><span class="sxs-lookup"><span data-stu-id="6752e-140">This attribute is useful if your application uses legacy activation paths, such as the [CorBindToRuntimeEx function](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md), and you want those paths to activate version 4 of the CLR instead of an earlier version, or if your application is built with the .NET Framework 4 but has a dependency on a mixed-mode assembly built with an earlier version of the .NET Framework.</span></span> <span data-ttu-id="6752e-141">在这些情况下，请将属性设置为 `true`。</span><span class="sxs-lookup"><span data-stu-id="6752e-141">In those scenarios, set the attribute to `true`.</span></span>

> [!NOTE]
> <span data-ttu-id="6752e-142">将属性设置为 `true` 可防止 CLR 版本1.1 或 CLR 版本2.0 加载到同一进程中，从而有效禁用进程内并行功能（请参阅[COM 互操作的并行执行](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8t8td04t(v=vs.100))）。</span><span class="sxs-lookup"><span data-stu-id="6752e-142">Setting the attribute to `true` prevents CLR version 1.1 or CLR version 2.0 from loading into the same process, effectively disabling the in-process side-by-side feature (see [Side-by-Side Execution for COM Interop](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8t8td04t(v=vs.100))).</span></span>

## <a name="example"></a><span data-ttu-id="6752e-143">示例</span><span class="sxs-lookup"><span data-stu-id="6752e-143">Example</span></span>

 <span data-ttu-id="6752e-144">下面的示例演示如何在配置文件中指定运行时版本。</span><span class="sxs-lookup"><span data-stu-id="6752e-144">The following example shows how to specify the runtime version in a configuration file.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="6752e-145">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6752e-145">See also</span></span>

- [<span data-ttu-id="6752e-146">启动设置架构</span><span class="sxs-lookup"><span data-stu-id="6752e-146">Startup Settings Schema</span></span>](index.md)
- [<span data-ttu-id="6752e-147">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="6752e-147">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="6752e-148">如何：配置应用以支持 .NET Framework 4 或更高版本</span><span class="sxs-lookup"><span data-stu-id="6752e-148">How to: Configure an app to support .NET Framework 4 or later versions</span></span>](../../../migration-guide/how-to-configure-an-app-to-support-net-framework-4-or-4-5.md)
- <span data-ttu-id="6752e-149">[并行执行 COM 互操作](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8t8td04t(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="6752e-149">[Side-by-Side Execution for COM Interop](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8t8td04t(v=vs.100))</span></span>
- [<span data-ttu-id="6752e-150">进程内并行执行</span><span class="sxs-lookup"><span data-stu-id="6752e-150">In-Process Side-by-Side Execution</span></span>](../../../deployment/in-process-side-by-side-execution.md)
