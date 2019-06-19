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
ms.openlocfilehash: 022f0efbbb2e6e9a4ac9d3d7ddcc1fb1022cdbee
ms.sourcegitcommit: a8d3504f0eae1a40bda2b06bd441ba01f1631ef0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/18/2019
ms.locfileid: "67169774"
---
# <a name="startup-element"></a><span data-ttu-id="9e7cd-102">\<启动 > 元素</span><span class="sxs-lookup"><span data-stu-id="9e7cd-102">\<startup> element</span></span>

<span data-ttu-id="9e7cd-103">指定公共语言运行时启动信息。</span><span class="sxs-lookup"><span data-stu-id="9e7cd-103">Specifies common language runtime startup information.</span></span>

 <span data-ttu-id="9e7cd-104">\<configuration> \<startup></span><span class="sxs-lookup"><span data-stu-id="9e7cd-104">\<configuration> \<startup></span></span>

## <a name="syntax"></a><span data-ttu-id="9e7cd-105">语法</span><span class="sxs-lookup"><span data-stu-id="9e7cd-105">Syntax</span></span>

```xml
<startup useLegacyV2RuntimeActivationPolicy="true|false" > 
</startup>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="9e7cd-106">特性和元素</span><span class="sxs-lookup"><span data-stu-id="9e7cd-106">Attributes and elements</span></span>

 <span data-ttu-id="9e7cd-107">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="9e7cd-107">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="9e7cd-108">特性</span><span class="sxs-lookup"><span data-stu-id="9e7cd-108">Attributes</span></span>

|<span data-ttu-id="9e7cd-109">特性</span><span class="sxs-lookup"><span data-stu-id="9e7cd-109">Attribute</span></span>|<span data-ttu-id="9e7cd-110">描述</span><span class="sxs-lookup"><span data-stu-id="9e7cd-110">Description</span></span>|
|---------------|-----------------|
|`useLegacyV2RuntimeActivationPolicy`|<span data-ttu-id="9e7cd-111">可选特性。</span><span class="sxs-lookup"><span data-stu-id="9e7cd-111">Optional attribute.</span></span><br /><br /> <span data-ttu-id="9e7cd-112">指定是否启用.NET Framework 2.0 运行时激活策略或使用.NET Framework 4 激活策略。</span><span class="sxs-lookup"><span data-stu-id="9e7cd-112">Specifies whether to enable the .NET Framework 2.0 runtime activation policy or to use the .NET Framework 4 activation policy.</span></span>|

## <a name="uselegacyv2runtimeactivationpolicy-attribute"></a><span data-ttu-id="9e7cd-113">useLegacyV2RuntimeActivationPolicy 属性</span><span class="sxs-lookup"><span data-stu-id="9e7cd-113">useLegacyV2RuntimeActivationPolicy attribute</span></span>

|<span data-ttu-id="9e7cd-114">值</span><span class="sxs-lookup"><span data-stu-id="9e7cd-114">Value</span></span>|<span data-ttu-id="9e7cd-115">描述</span><span class="sxs-lookup"><span data-stu-id="9e7cd-115">Description</span></span>|
|-----------|-----------------|
|`true`|<span data-ttu-id="9e7cd-116">启用.NET Framework 2.0 运行时激活策略对于所选的运行时，它将绑定旧式运行时激活技术 (如[CorBindToRuntimeEx 函数](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md)) 到运行时改为选择从配置文件在 CLR 版本 2.0 将达到其上限。</span><span class="sxs-lookup"><span data-stu-id="9e7cd-116">Enable .NET Framework 2.0 runtime activation policy for the chosen runtime, which is to bind legacy runtime activation techniques (such as the [CorBindToRuntimeEx function](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md)) to the runtime chosen from the configuration file instead of capping them at CLR version 2.0.</span></span> <span data-ttu-id="9e7cd-117">因此，如果从配置文件选择 CLR 版本 4 或更高版本，则使用.NET Framework 的早期版本创建的混合模式程序集是加载与所选的 CLR 版本。</span><span class="sxs-lookup"><span data-stu-id="9e7cd-117">Thus, if CLR version 4 or later is chosen from the configuration file, mixed-mode assemblies created with earlier versions of the .NET Framework are loaded with the chosen CLR version.</span></span> <span data-ttu-id="9e7cd-118">设置此值可防止 CLR 版本 1.1 或 CLR 版本 2.0 加载到同一个进程，有效地禁用进程内并行的功能。</span><span class="sxs-lookup"><span data-stu-id="9e7cd-118">Setting this value prevents CLR version 1.1 or CLR version 2.0 from loading into the same process, effectively disabling the in-process side-by-side feature.</span></span>|
|`false`|<span data-ttu-id="9e7cd-119">使用默认激活策略适用于.NET Framework 4 及更高版本，这是以允许旧的运行时加载到进程的 CLR 版本 1.1 或 2.0 的激活方法。</span><span class="sxs-lookup"><span data-stu-id="9e7cd-119">Use the default activation policy for the .NET Framework 4 and later, which is to allow legacy runtime activation techniques to load CLR version 1.1 or 2.0 into the process.</span></span> <span data-ttu-id="9e7cd-120">将设置此值可阻止混合模式程序集加载到.NET Framework 4 或更高版本，除非在.NET Framework 4 或更高版本生成它们。</span><span class="sxs-lookup"><span data-stu-id="9e7cd-120">Setting this value prevents mixed-mode assemblies from loading into the .NET Framework 4 or later unless they were built with the .NET Framework 4 or later.</span></span> <span data-ttu-id="9e7cd-121">此值是默认值。</span><span class="sxs-lookup"><span data-stu-id="9e7cd-121">This value is the default.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="9e7cd-122">子元素</span><span class="sxs-lookup"><span data-stu-id="9e7cd-122">Child elements</span></span>

|<span data-ttu-id="9e7cd-123">元素</span><span class="sxs-lookup"><span data-stu-id="9e7cd-123">Element</span></span>|<span data-ttu-id="9e7cd-124">描述</span><span class="sxs-lookup"><span data-stu-id="9e7cd-124">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="9e7cd-125">\<requiredRuntime></span><span class="sxs-lookup"><span data-stu-id="9e7cd-125">\<requiredRuntime></span></span>](requiredruntime-element.md)|<span data-ttu-id="9e7cd-126">指定应用程序仅支持 1.0 版本的公共语言运行时。</span><span class="sxs-lookup"><span data-stu-id="9e7cd-126">Specifies that the application supports only version 1.0 of the common language runtime.</span></span> <span data-ttu-id="9e7cd-127">运行时 1.1 版或更高版本构建的应用程序应使用 **\<supportedRuntime >** 元素。</span><span class="sxs-lookup"><span data-stu-id="9e7cd-127">Applications built with runtime version 1.1 or later should use the **\<supportedRuntime>** element.</span></span>|
|[<span data-ttu-id="9e7cd-128">\<supportedRuntime></span><span class="sxs-lookup"><span data-stu-id="9e7cd-128">\<supportedRuntime></span></span>](supportedruntime-element.md)|<span data-ttu-id="9e7cd-129">指定应用程序支持的公共语言运行时版本。</span><span class="sxs-lookup"><span data-stu-id="9e7cd-129">Specifies which versions of the common language runtime the application supports.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="9e7cd-130">父元素</span><span class="sxs-lookup"><span data-stu-id="9e7cd-130">Parent elements</span></span>

|<span data-ttu-id="9e7cd-131">元素</span><span class="sxs-lookup"><span data-stu-id="9e7cd-131">Element</span></span>|<span data-ttu-id="9e7cd-132">描述</span><span class="sxs-lookup"><span data-stu-id="9e7cd-132">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="9e7cd-133">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="9e7cd-133">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|

## <a name="remarks"></a><span data-ttu-id="9e7cd-134">备注</span><span class="sxs-lookup"><span data-stu-id="9e7cd-134">Remarks</span></span>

 <span data-ttu-id="9e7cd-135">**\<SupportedRuntime>** 元素应由使用 1.1 版或更高版本的运行时版本生成的所有应用程序。</span><span class="sxs-lookup"><span data-stu-id="9e7cd-135">The **\<supportedRuntime>** element should be used by all applications built using version 1.1 or later of the runtime.</span></span> <span data-ttu-id="9e7cd-136">仅支持 1.0 版的运行时生成的应用程序必须使用 **\<requiredRuntime >** 元素。</span><span class="sxs-lookup"><span data-stu-id="9e7cd-136">Applications built to support only version 1.0 of the runtime must use the **\<requiredRuntime>** element.</span></span>

 <span data-ttu-id="9e7cd-137">在 Microsoft Internet Explorer 中托管的应用程序的启动代码将忽略 **\<启动 >** 元素和子元素。</span><span class="sxs-lookup"><span data-stu-id="9e7cd-137">The startup code for an application hosted in Microsoft Internet Explorer ignores the **\<startup>** element and its child elements.</span></span>

## <a name="the-uselegacyv2runtimeactivationpolicy-attribute"></a><span data-ttu-id="9e7cd-138">UseLegacyV2RuntimeActivationPolicy 属性</span><span class="sxs-lookup"><span data-stu-id="9e7cd-138">The useLegacyV2RuntimeActivationPolicy attribute</span></span>

 <span data-ttu-id="9e7cd-139">此特性会非常有用，如果你的应用程序使用旧式激活路径，例如[CorBindToRuntimeEx 函数](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md)，并且希望这些路径来激活而不是早期版本的 CLR 版本 4 或如果你的应用程序使用生成.NET Framework 4 但在使用.NET Framework 的早期版本构建的混合模式程序集具有依赖项。</span><span class="sxs-lookup"><span data-stu-id="9e7cd-139">This attribute is useful if your application uses legacy activation paths, such as the [CorBindToRuntimeEx function](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md), and you want those paths to activate version 4 of the CLR instead of an earlier version, or if your application is built with the .NET Framework 4 but has a dependency on a mixed-mode assembly built with an earlier version of the .NET Framework.</span></span> <span data-ttu-id="9e7cd-140">在这些情况下，将属性设置为`true`。</span><span class="sxs-lookup"><span data-stu-id="9e7cd-140">In those scenarios, set the attribute to `true`.</span></span>

> [!NOTE]
> <span data-ttu-id="9e7cd-141">将属性设置为`true`防止 CLR 版本 1.1 或 CLR 版本 2.0 加载到同一个进程，有效地禁用进程内并行的功能 (请参阅[COM 互操作的并行执行](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8t8td04t(v=vs.100)))。</span><span class="sxs-lookup"><span data-stu-id="9e7cd-141">Setting the attribute to `true` prevents CLR version 1.1 or CLR version 2.0 from loading into the same process, effectively disabling the in-process side-by-side feature (see [Side-by-Side Execution for COM Interop](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8t8td04t(v=vs.100))).</span></span>

## <a name="example"></a><span data-ttu-id="9e7cd-142">示例</span><span class="sxs-lookup"><span data-stu-id="9e7cd-142">Example</span></span>

 <span data-ttu-id="9e7cd-143">下面的示例演示如何在配置文件中指定的运行时版本。</span><span class="sxs-lookup"><span data-stu-id="9e7cd-143">The following example shows how to specify the runtime version in a configuration file.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="9e7cd-144">请参阅</span><span class="sxs-lookup"><span data-stu-id="9e7cd-144">See also</span></span>

- [<span data-ttu-id="9e7cd-145">启动设置架构</span><span class="sxs-lookup"><span data-stu-id="9e7cd-145">Startup Settings Schema</span></span>](index.md)
- [<span data-ttu-id="9e7cd-146">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="9e7cd-146">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="9e7cd-147">如何：将应用配置为支持 .NET Framework 4 或更高版本</span><span class="sxs-lookup"><span data-stu-id="9e7cd-147">How to: Configure an app to support .NET Framework 4 or later versions</span></span>](../../../migration-guide/how-to-configure-an-app-to-support-net-framework-4-or-4-5.md)
- <span data-ttu-id="9e7cd-148">[COM 互操作的的并行执行](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8t8td04t(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="9e7cd-148">[Side-by-Side Execution for COM Interop](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8t8td04t(v=vs.100))</span></span>
- [<span data-ttu-id="9e7cd-149">进程内并行执行</span><span class="sxs-lookup"><span data-stu-id="9e7cd-149">In-Process Side-by-Side Execution</span></span>](../../../deployment/in-process-side-by-side-execution.md)
