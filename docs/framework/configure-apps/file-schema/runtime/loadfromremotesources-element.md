---
title: <loadFromRemoteSources> 元素
ms.date: 05/24/2018
helpviewer_keywords:
- loadFromRemoteSources element
- <loadFromRemoteSources> element
ms.assetid: 006d1280-2ac3-4db6-a984-a3d4e275046a
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ebb32a74f5413f9c927a84ababf2d60d20e0b024
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2019
ms.locfileid: "55269687"
---
# <a name="loadfromremotesources-element"></a><span data-ttu-id="6ca17-102">\<loadFromRemoteSources > 元素</span><span class="sxs-lookup"><span data-stu-id="6ca17-102">\<loadFromRemoteSources> element</span></span>
<span data-ttu-id="6ca17-103">指定是否应为从远程源加载的程序集授予完全信任在.NET Framework 4 及更高版本。</span><span class="sxs-lookup"><span data-stu-id="6ca17-103">Specifies whether assemblies loaded from remote sources should be granted full trust in .NET Framework 4 and later.</span></span>
  
> [!NOTE]
>  <span data-ttu-id="6ca17-104">如果由于中的 Visual Studio 项目错误列表或生成错误的错误消息被转到本主题，请参阅[如何：使用 Visual Studio 中的程序集从 Web](https://msdn.microsoft.com/library/d8635b63-89a0-41aa-90f4-f351b2111070)。</span><span class="sxs-lookup"><span data-stu-id="6ca17-104">If you were directed to this topic because of an error message in the Visual Studio project error list or a build error, see [How to: Use an Assembly from the Web in Visual Studio](https://msdn.microsoft.com/library/d8635b63-89a0-41aa-90f4-f351b2111070).</span></span>  
  
 <span data-ttu-id="6ca17-105">\<configuration></span><span class="sxs-lookup"><span data-stu-id="6ca17-105">\<configuration></span></span>  
<span data-ttu-id="6ca17-106">\<运行时 ></span><span class="sxs-lookup"><span data-stu-id="6ca17-106">\<runtime></span></span>  
<span data-ttu-id="6ca17-107">\<loadFromRemoteSources></span><span class="sxs-lookup"><span data-stu-id="6ca17-107">\<loadFromRemoteSources></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6ca17-108">语法</span><span class="sxs-lookup"><span data-stu-id="6ca17-108">Syntax</span></span>  
  
```xml  
<loadFromRemoteSources    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6ca17-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="6ca17-109">Attributes and elements</span></span>
 <span data-ttu-id="6ca17-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="6ca17-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6ca17-111">特性</span><span class="sxs-lookup"><span data-stu-id="6ca17-111">Attributes</span></span>  
  
|<span data-ttu-id="6ca17-112">特性</span><span class="sxs-lookup"><span data-stu-id="6ca17-112">Attribute</span></span>|<span data-ttu-id="6ca17-113">描述</span><span class="sxs-lookup"><span data-stu-id="6ca17-113">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="6ca17-114">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="6ca17-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="6ca17-115">指定是否应为从远程源加载的程序集授予完全信任。</span><span class="sxs-lookup"><span data-stu-id="6ca17-115">Specifies whether an assembly that is loaded from a remote source should be granted full trust.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="6ca17-116">已启用的属性</span><span class="sxs-lookup"><span data-stu-id="6ca17-116">enabled attribute</span></span>  
  
|<span data-ttu-id="6ca17-117">“值”</span><span class="sxs-lookup"><span data-stu-id="6ca17-117">Value</span></span>|<span data-ttu-id="6ca17-118">描述</span><span class="sxs-lookup"><span data-stu-id="6ca17-118">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="6ca17-119">不要授予完全信任应用程序从远程源。</span><span class="sxs-lookup"><span data-stu-id="6ca17-119">Do not grant full trust to applications from remote sources.</span></span> <span data-ttu-id="6ca17-120">这是默认设置。</span><span class="sxs-lookup"><span data-stu-id="6ca17-120">This is the default.</span></span>|  
|`true`|<span data-ttu-id="6ca17-121">从远程源向应用程序授予完全信任。</span><span class="sxs-lookup"><span data-stu-id="6ca17-121">Grant full trust to applications from remote sources.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6ca17-122">子元素</span><span class="sxs-lookup"><span data-stu-id="6ca17-122">Child elements</span></span>  
 <span data-ttu-id="6ca17-123">无。</span><span class="sxs-lookup"><span data-stu-id="6ca17-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6ca17-124">父元素</span><span class="sxs-lookup"><span data-stu-id="6ca17-124">Parent elements</span></span>  
  
|<span data-ttu-id="6ca17-125">元素</span><span class="sxs-lookup"><span data-stu-id="6ca17-125">Element</span></span>|<span data-ttu-id="6ca17-126">描述</span><span class="sxs-lookup"><span data-stu-id="6ca17-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="6ca17-127">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="6ca17-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="6ca17-128">包含有关运行时初始化选项的信息。</span><span class="sxs-lookup"><span data-stu-id="6ca17-128">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6ca17-129">备注</span><span class="sxs-lookup"><span data-stu-id="6ca17-129">Remarks</span></span>

<span data-ttu-id="6ca17-130">在.NET Framework 3.5 和更早版本中，如果从远程位置，加载程序集则在程序集中的代码运行时中以部分信任方式取决于从中加载该区域的授予集。</span><span class="sxs-lookup"><span data-stu-id="6ca17-130">In the .NET Framework 3.5 and earlier versions, if you load an assembly from a remote location, code in the assembly runs in partial trust with a grant set that depends on the zone from which it is loaded.</span></span> <span data-ttu-id="6ca17-131">例如，如果从网站加载程序集，它将加载到 Internet 区域，并向其授予 Internet 权限集。</span><span class="sxs-lookup"><span data-stu-id="6ca17-131">For example, if you load an assembly from a website, it is loaded into the Internet zone and granted the Internet permission set.</span></span> <span data-ttu-id="6ca17-132">换而言之，它将执行在 Internet 沙箱中。</span><span class="sxs-lookup"><span data-stu-id="6ca17-132">In other words, it executes in an Internet sandbox.</span></span>

<span data-ttu-id="6ca17-133">从.NET Framework 4 开始，已禁用代码访问安全性 (CAS) 策略和程序集被加载到完全信任。</span><span class="sxs-lookup"><span data-stu-id="6ca17-133">Starting with the .NET Framework 4, code access security (CAS) policy is disabled and assemblies are loaded in full trust.</span></span> <span data-ttu-id="6ca17-134">通常，这会向与加载的程序集授予完全信任<xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType>以前曾沙盒的方法。</span><span class="sxs-lookup"><span data-stu-id="6ca17-134">Ordinarily, this would grant full trust to assemblies loaded with the <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType> method that previously had been sandboxed.</span></span> <span data-ttu-id="6ca17-135">若要防止此情况，默认情况下禁用从远程源加载的程序集在运行代码的能力。</span><span class="sxs-lookup"><span data-stu-id="6ca17-135">To prevent this, the ability to run code in assemblies loaded from a remote source is disabled by default.</span></span> <span data-ttu-id="6ca17-136">默认情况下，如果你尝试加载远程程序集，<xref:System.IO.FileLoadException>使用像引发以下异常消息：</span><span class="sxs-lookup"><span data-stu-id="6ca17-136">By default, if you attempt to load a remote assembly, a <xref:System.IO.FileLoadException> with an exception message like the following is thrown:</span></span>

```text
System.IO.FileNotFoundException: Could not load file or assembly 'file:assem.dll' or one of its dependencies. Operation is not supported. 
(Exception from HRESULT: 0x80131515)
File name: 'file:assem.dll' ---> 
System.NotSupportedException: An attempt was made to load an assembly from a network location which would have caused the assembly 
to be sandboxed in previous versions of the .NET Framework. This release of the .NET Framework does not enable CAS policy by default, 
so this load may be dangerous. If this load is not intended to sandbox the assembly, please enable the loadFromRemoteSources switch. 
```

<span data-ttu-id="6ca17-137">若要加载的程序集和执行其代码，您必须：</span><span class="sxs-lookup"><span data-stu-id="6ca17-137">To load the assembly and execute its code, you must either:</span></span>

- <span data-ttu-id="6ca17-138">显式程序集创建一个沙盒 (请参阅[如何：运行沙盒中部分受信任的代码](../../../../../docs/framework/misc/how-to-run-partially-trusted-code-in-a-sandbox.md))。</span><span class="sxs-lookup"><span data-stu-id="6ca17-138">Explicitly create a sandbox for the assembly (see [How to: Run Partially Trusted Code in a Sandbox](../../../../../docs/framework/misc/how-to-run-partially-trusted-code-in-a-sandbox.md)).</span></span>

- <span data-ttu-id="6ca17-139">在完全信任环境中运行该程序集的代码。</span><span class="sxs-lookup"><span data-stu-id="6ca17-139">Run the assembly's code in full trust.</span></span> <span data-ttu-id="6ca17-140">执行此操作通过配置`<loadFromRemoteSources>`元素。</span><span class="sxs-lookup"><span data-stu-id="6ca17-140">You do this by configuring the `<loadFromRemoteSources>` element.</span></span> <span data-ttu-id="6ca17-141">它允许您指定在早期版本的.NET Framework 中的部分信任中运行的程序集现在运行在完全信任环境中的.NET Framework 4 和更高版本。</span><span class="sxs-lookup"><span data-stu-id="6ca17-141">It lets you specify that the assemblies that run in partial trust in earlier versions of the .NET Framework now run in full trust in the .NET Framework 4 and later versions.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6ca17-142">如果该程序集不应在完全信任环境中运行，则不要设置此配置元素。</span><span class="sxs-lookup"><span data-stu-id="6ca17-142">If the assembly should not run in full trust, do not set this configuration element.</span></span> <span data-ttu-id="6ca17-143">相反，创建沙盒<xref:System.AppDomain>要在其中加载程序集。</span><span class="sxs-lookup"><span data-stu-id="6ca17-143">Instead, create a sandboxed <xref:System.AppDomain> in which to load the assembly.</span></span>

<span data-ttu-id="6ca17-144">`enabled`属性`<loadFromRemoteSources>`元素仅当禁用代码访问安全性 (CAS) 时才有效。</span><span class="sxs-lookup"><span data-stu-id="6ca17-144">The `enabled` attribute for the `<loadFromRemoteSources>` element is effective only when code access security (CAS) is disabled.</span></span> <span data-ttu-id="6ca17-145">默认情况下，在.NET Framework 4 和更高版本中禁用 CAS 策略。</span><span class="sxs-lookup"><span data-stu-id="6ca17-145">By default, CAS policy is disabled in the .NET Framework 4 and later versions.</span></span> <span data-ttu-id="6ca17-146">如果您设置`enabled`到`true`，远程程序集被授予完全信任。</span><span class="sxs-lookup"><span data-stu-id="6ca17-146">If you set `enabled` to `true`, remote assemblies are granted full trust.</span></span>

<span data-ttu-id="6ca17-147">如果`enabled`未设置为`true`、<xref:System.IO.FileLoadException>引发在以下条件之一：</span><span class="sxs-lookup"><span data-stu-id="6ca17-147">If `enabled` is not set to `true`, a <xref:System.IO.FileLoadException> is thrown under the either of the following conditions:</span></span>

- <span data-ttu-id="6ca17-148">当前域的沙盒行为是不同于.NET Framework 3.5 中其行为。</span><span class="sxs-lookup"><span data-stu-id="6ca17-148">The sandboxing behavior of the current domain is different from its behavior in the .NET Framework 3.5.</span></span> <span data-ttu-id="6ca17-149">这要求 CAS 策略才可被禁用，并且不被进行沙箱处理的当前域。</span><span class="sxs-lookup"><span data-stu-id="6ca17-149">This requires CAS policy to be disabled, and the current domain not to be sandboxed.</span></span>

- <span data-ttu-id="6ca17-150">正在加载的程序集不是来自`MyComputer`区域。</span><span class="sxs-lookup"><span data-stu-id="6ca17-150">The assembly being loaded is not from the `MyComputer` zone.</span></span>

<span data-ttu-id="6ca17-151">设置`<loadFromRemoteSources>`元素`true`可防止引发此异常。</span><span class="sxs-lookup"><span data-stu-id="6ca17-151">Setting the `<loadFromRemoteSources>` element to `true` prevents this exception from being thrown.</span></span> <span data-ttu-id="6ca17-152">它可用于指定，您不依赖于到沙盒公共语言运行时加载的程序集的安全性，和他们可以有权执行在完全信任。</span><span class="sxs-lookup"><span data-stu-id="6ca17-152">It enables you to specify that you are not relying on the common language runtime to sandbox the loaded assemblies for security, and that they can be allowed to execute in full trust.</span></span>

## <a name="notes"></a><span data-ttu-id="6ca17-153">说明</span><span class="sxs-lookup"><span data-stu-id="6ca17-153">Notes</span></span>

- <span data-ttu-id="6ca17-154">在.NET Framework 4.5 和更高版本中，本地网络共享上的程序集在完全信任环境中默认情况下运行;无需启用`<loadFromRemoteSources>`元素。</span><span class="sxs-lookup"><span data-stu-id="6ca17-154">In the .NET Framework 4.5 and later versions, assemblies on local network shares run in full trust by default; you do not have to enable the `<loadFromRemoteSources>` element.</span></span>

- <span data-ttu-id="6ca17-155">如果应用程序是从 Web 复制而来，Windows 会将其标记为 Web 应用程序，即使它驻留在本地计算机上也不例外。</span><span class="sxs-lookup"><span data-stu-id="6ca17-155">If an application has been copied from the web, it is flagged by Windows as being a web application, even if it resides on the local computer.</span></span> <span data-ttu-id="6ca17-156">可以通过更改其文件属性，更改该标记也可以使用`<loadFromRemoteSources>`元素对程序集授予完全信任。</span><span class="sxs-lookup"><span data-stu-id="6ca17-156">You can change that designation by changing its file properties, or you can use the `<loadFromRemoteSources>` element to grant the assembly full trust.</span></span> <span data-ttu-id="6ca17-157">对于操作系统标记为从 Web 加载的本地程序集，也可以使用 <xref:System.Reflection.Assembly.UnsafeLoadFrom%2A> 方法进行加载。</span><span class="sxs-lookup"><span data-stu-id="6ca17-157">As an alternative, you can use the <xref:System.Reflection.Assembly.UnsafeLoadFrom%2A> method to load a local assembly that the operating system has flagged as having been loaded from the web.</span></span>

- <span data-ttu-id="6ca17-158">你可能会收到<xref:System.IO.FileLoadException>Windows Virtual PC 应用程序中运行的应用程序中。</span><span class="sxs-lookup"><span data-stu-id="6ca17-158">You may get a <xref:System.IO.FileLoadException> in an application that is running in a Windows Virtual PC application.</span></span> <span data-ttu-id="6ca17-159">当你尝试从托管计算机上的链接文件夹加载文件时，可以发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="6ca17-159">This can happen when you try to load a file from linked folders on the hosting computer.</span></span> <span data-ttu-id="6ca17-160">当你尝试将文件从上链接的文件夹加载它也会发生[远程桌面服务](https://go.microsoft.com/fwlink/?LinkId=182775)(Terminal Services)。</span><span class="sxs-lookup"><span data-stu-id="6ca17-160">It can also occur when you try to load a file from a folder linked over [Remote Desktop Services](https://go.microsoft.com/fwlink/?LinkId=182775) (Terminal Services).</span></span> <span data-ttu-id="6ca17-161">若要避免此异常，设置`enabled`到`true`。</span><span class="sxs-lookup"><span data-stu-id="6ca17-161">To avoid the exception, set `enabled` to `true`.</span></span>

## <a name="configuration-file"></a><span data-ttu-id="6ca17-162">配置文件</span><span class="sxs-lookup"><span data-stu-id="6ca17-162">Configuration file</span></span>

<span data-ttu-id="6ca17-163">此元素通常用在应用程序配置文件中，但可根据上下文用于其他配置文件。</span><span class="sxs-lookup"><span data-stu-id="6ca17-163">This element is typically used in the application configuration file, but can be used in other configuration files depending upon the context.</span></span> <span data-ttu-id="6ca17-164">有关详细信息，请参阅文章[多个隐式使用 CAS 策略： loadFromRemoteSources](https://go.microsoft.com/fwlink/p/?LinkId=266839) .NET 安全性博客中。</span><span class="sxs-lookup"><span data-stu-id="6ca17-164">For more information, see the article [More Implicit Uses of CAS Policy: loadFromRemoteSources](https://go.microsoft.com/fwlink/p/?LinkId=266839) in the .NET Security blog.</span></span>  

## <a name="example"></a><span data-ttu-id="6ca17-165">示例</span><span class="sxs-lookup"><span data-stu-id="6ca17-165">Example</span></span>

<span data-ttu-id="6ca17-166">下面的示例演示如何向从远程源加载的程序集授予完全信任。</span><span class="sxs-lookup"><span data-stu-id="6ca17-166">The following example shows how to grant full trust to assemblies loaded from remote sources.</span></span>

```xml
<configuration>  
   <runtime>  
      <loadFromRemoteSources enabled="true"/>  
   </runtime>  
</configuration>  
```

## <a name="see-also"></a><span data-ttu-id="6ca17-167">请参阅</span><span class="sxs-lookup"><span data-stu-id="6ca17-167">See also</span></span>

- [<span data-ttu-id="6ca17-168">更多隐式使用 CAS 策略： loadFromRemoteSources</span><span class="sxs-lookup"><span data-stu-id="6ca17-168">More Implicit Uses of CAS Policy: loadFromRemoteSources</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=266839)
- [<span data-ttu-id="6ca17-169">如何：运行沙盒中部分受信任的代码</span><span class="sxs-lookup"><span data-stu-id="6ca17-169">How to: Run Partially Trusted Code in a Sandbox</span></span>](../../../../../docs/framework/misc/how-to-run-partially-trusted-code-in-a-sandbox.md)
- [<span data-ttu-id="6ca17-170">运行时设置架构</span><span class="sxs-lookup"><span data-stu-id="6ca17-170">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="6ca17-171">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="6ca17-171">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType>
