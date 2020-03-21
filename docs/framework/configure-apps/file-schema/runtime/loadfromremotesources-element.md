---
title: <loadFromRemoteSources> 元素
ms.date: 05/24/2018
helpviewer_keywords:
- loadFromRemoteSources element
- <loadFromRemoteSources> element
ms.assetid: 006d1280-2ac3-4db6-a984-a3d4e275046a
ms.openlocfilehash: a0dcffe378cdd09de0fbd8f0a6ef0635c033fd9c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154057"
---
# <a name="loadfromremotesources-element"></a><span data-ttu-id="a0875-102">\<负载从远程源>元素</span><span class="sxs-lookup"><span data-stu-id="a0875-102">\<loadFromRemoteSources> element</span></span>
<span data-ttu-id="a0875-103">指定是否应授予从远程源加载的程序集对 .NET 框架 4 和更高版本完全信任。</span><span class="sxs-lookup"><span data-stu-id="a0875-103">Specifies whether assemblies loaded from remote sources should be granted full trust in .NET Framework 4 and later.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a0875-104">如果您因为 Visual Studio 项目错误列表中的错误消息或生成错误而被定向到本文，请参阅["如何：在可视化工作室中的 Web 中使用程序集](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ee890038(v=vs.100))"。</span><span class="sxs-lookup"><span data-stu-id="a0875-104">If you were directed to this article because of an error message in the Visual Studio project error list or a build error, see [How to: Use an Assembly from the Web in Visual Studio](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ee890038(v=vs.100)).</span></span>  
  
<span data-ttu-id="a0875-105">[**\<配置>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="a0875-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="a0875-106">&nbsp;&nbsp;[**\<运行时>**](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="a0875-106">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="a0875-107">&nbsp;&nbsp;&nbsp;&nbsp;**\<负载从远程源>**</span><span class="sxs-lookup"><span data-stu-id="a0875-107">&nbsp;&nbsp;&nbsp;&nbsp;**\<loadFromRemoteSources>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0875-108">语法</span><span class="sxs-lookup"><span data-stu-id="a0875-108">Syntax</span></span>  
  
```xml  
<loadFromRemoteSources
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a0875-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="a0875-109">Attributes and elements</span></span>
 <span data-ttu-id="a0875-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="a0875-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a0875-111">属性</span><span class="sxs-lookup"><span data-stu-id="a0875-111">Attributes</span></span>  
  
|<span data-ttu-id="a0875-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="a0875-112">Attribute</span></span>|<span data-ttu-id="a0875-113">说明</span><span class="sxs-lookup"><span data-stu-id="a0875-113">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="a0875-114">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="a0875-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="a0875-115">指定是否应授予从远程源加载的程序集完全信任。</span><span class="sxs-lookup"><span data-stu-id="a0875-115">Specifies whether an assembly that is loaded from a remote source should be granted full trust.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="a0875-116">启用的属性</span><span class="sxs-lookup"><span data-stu-id="a0875-116">enabled attribute</span></span>  
  
|<span data-ttu-id="a0875-117">值</span><span class="sxs-lookup"><span data-stu-id="a0875-117">Value</span></span>|<span data-ttu-id="a0875-118">说明</span><span class="sxs-lookup"><span data-stu-id="a0875-118">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="a0875-119">不要对来自远程源的应用程序授予完全信任。</span><span class="sxs-lookup"><span data-stu-id="a0875-119">Do not grant full trust to applications from remote sources.</span></span> <span data-ttu-id="a0875-120">这是默认值。</span><span class="sxs-lookup"><span data-stu-id="a0875-120">This is the default.</span></span>|  
|`true`|<span data-ttu-id="a0875-121">完全信任来自远程源的应用程序。</span><span class="sxs-lookup"><span data-stu-id="a0875-121">Grant full trust to applications from remote sources.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a0875-122">子元素</span><span class="sxs-lookup"><span data-stu-id="a0875-122">Child elements</span></span>  
 <span data-ttu-id="a0875-123">无。</span><span class="sxs-lookup"><span data-stu-id="a0875-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a0875-124">父元素</span><span class="sxs-lookup"><span data-stu-id="a0875-124">Parent elements</span></span>  
  
|<span data-ttu-id="a0875-125">元素</span><span class="sxs-lookup"><span data-stu-id="a0875-125">Element</span></span>|<span data-ttu-id="a0875-126">说明</span><span class="sxs-lookup"><span data-stu-id="a0875-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="a0875-127">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="a0875-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="a0875-128">包含有关运行时初始化选项的信息。</span><span class="sxs-lookup"><span data-stu-id="a0875-128">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a0875-129">备注</span><span class="sxs-lookup"><span data-stu-id="a0875-129">Remarks</span></span>

<span data-ttu-id="a0875-130">在 .NET Framework 3.5 和早期版本中，如果从远程位置加载程序集，则程序集中的代码将部分信任地运行，授予集取决于加载该程序集的区域。</span><span class="sxs-lookup"><span data-stu-id="a0875-130">In the .NET Framework 3.5 and earlier versions, if you load an assembly from a remote location, code in the assembly runs in partial trust with a grant set that depends on the zone from which it is loaded.</span></span> <span data-ttu-id="a0875-131">例如，如果从网站加载程序集，则程序集将加载到 Internet 区域并授予 Internet 权限集。</span><span class="sxs-lookup"><span data-stu-id="a0875-131">For example, if you load an assembly from a website, it is loaded into the Internet zone and granted the Internet permission set.</span></span> <span data-ttu-id="a0875-132">换句话说，它在一个互联网沙盒中执行。</span><span class="sxs-lookup"><span data-stu-id="a0875-132">In other words, it executes in an Internet sandbox.</span></span>

<span data-ttu-id="a0875-133">从 .NET 框架 4 开始，代码访问安全 （CAS） 策略被禁用，程序集完全信任地加载。</span><span class="sxs-lookup"><span data-stu-id="a0875-133">Starting with the .NET Framework 4, code access security (CAS) policy is disabled and assemblies are loaded in full trust.</span></span> <span data-ttu-id="a0875-134">通常，这将完全信任加载以前已沙盒<xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType>的方法的程序集。</span><span class="sxs-lookup"><span data-stu-id="a0875-134">Ordinarily, this would grant full trust to assemblies loaded with the <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType> method that previously had been sandboxed.</span></span> <span data-ttu-id="a0875-135">为了防止这种情况，默认情况下禁用在从远程源加载的程序集中运行代码的能力。</span><span class="sxs-lookup"><span data-stu-id="a0875-135">To prevent this, the ability to run code in assemblies loaded from a remote source is disabled by default.</span></span> <span data-ttu-id="a0875-136">默认情况下，如果尝试加载远程程序集，则会引发如下所示的<xref:System.IO.FileLoadException>异常消息：</span><span class="sxs-lookup"><span data-stu-id="a0875-136">By default, if you attempt to load a remote assembly, a <xref:System.IO.FileLoadException> with an exception message like the following is thrown:</span></span>

```text
System.IO.FileNotFoundException: Could not load file or assembly 'file:assem.dll' or one of its dependencies. Operation is not supported.
(Exception from HRESULT: 0x80131515)
File name: 'file:assem.dll' --->
System.NotSupportedException: An attempt was made to load an assembly from a network location which would have caused the assembly
to be sandboxed in previous versions of the .NET Framework. This release of the .NET Framework does not enable CAS policy by default,
so this load may be dangerous. If this load is not intended to sandbox the assembly, please enable the loadFromRemoteSources switch.
```

<span data-ttu-id="a0875-137">要加载程序集并执行其代码，必须：</span><span class="sxs-lookup"><span data-stu-id="a0875-137">To load the assembly and execute its code, you must either:</span></span>

- <span data-ttu-id="a0875-138">显式为程序集创建沙盒（[请参阅如何：在沙盒中运行部分受信任的代码](../../../misc/how-to-run-partially-trusted-code-in-a-sandbox.md)）。</span><span class="sxs-lookup"><span data-stu-id="a0875-138">Explicitly create a sandbox for the assembly (see [How to: Run Partially Trusted Code in a Sandbox](../../../misc/how-to-run-partially-trusted-code-in-a-sandbox.md)).</span></span>

- <span data-ttu-id="a0875-139">完全信任运行程序集的代码。</span><span class="sxs-lookup"><span data-stu-id="a0875-139">Run the assembly's code in full trust.</span></span> <span data-ttu-id="a0875-140">通过配置元素来`<loadFromRemoteSources>`执行此操作。</span><span class="sxs-lookup"><span data-stu-id="a0875-140">You do this by configuring the `<loadFromRemoteSources>` element.</span></span> <span data-ttu-id="a0875-141">它允许您指定在 .NET Framework 的早期版本中以部分信任方式运行的程序集现在完全信任 .NET 框架 4 和更高版本。</span><span class="sxs-lookup"><span data-stu-id="a0875-141">It lets you specify that the assemblies that run in partial trust in earlier versions of the .NET Framework now run in full trust in the .NET Framework 4 and later versions.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a0875-142">如果程序集不应完全信任地运行，请不要设置此配置元素。</span><span class="sxs-lookup"><span data-stu-id="a0875-142">If the assembly should not run in full trust, do not set this configuration element.</span></span> <span data-ttu-id="a0875-143">相反，请创建一个装沙<xref:System.AppDomain>盒以加载程序集。</span><span class="sxs-lookup"><span data-stu-id="a0875-143">Instead, create a sandboxed <xref:System.AppDomain> in which to load the assembly.</span></span>

<span data-ttu-id="a0875-144">仅当`enabled`禁用代码访问`<loadFromRemoteSources>`安全性 （CAS） 时，元素的属性才有效。</span><span class="sxs-lookup"><span data-stu-id="a0875-144">The `enabled` attribute for the `<loadFromRemoteSources>` element is effective only when code access security (CAS) is disabled.</span></span> <span data-ttu-id="a0875-145">默认情况下，在 .NET 框架 4 和更高版本中禁用 CAS 策略。</span><span class="sxs-lookup"><span data-stu-id="a0875-145">By default, CAS policy is disabled in the .NET Framework 4 and later versions.</span></span> <span data-ttu-id="a0875-146">如果设置为`enabled``true`，则远程程序集将被授予完全信任。</span><span class="sxs-lookup"><span data-stu-id="a0875-146">If you set `enabled` to `true`, remote assemblies are granted full trust.</span></span>

<span data-ttu-id="a0875-147">如果未`enabled`设置为`true`，<xref:System.IO.FileLoadException>则 在以下任一条件下引发 ：</span><span class="sxs-lookup"><span data-stu-id="a0875-147">If `enabled` is not set to `true`, a <xref:System.IO.FileLoadException> is thrown under the either of the following conditions:</span></span>

- <span data-ttu-id="a0875-148">当前域的沙盒行为不同于其在 .NET 框架 3.5 中的行为。</span><span class="sxs-lookup"><span data-stu-id="a0875-148">The sandboxing behavior of the current domain is different from its behavior in the .NET Framework 3.5.</span></span> <span data-ttu-id="a0875-149">这要求禁用 CAS 策略，并且当前域不得沙盒化。</span><span class="sxs-lookup"><span data-stu-id="a0875-149">This requires CAS policy to be disabled, and the current domain not to be sandboxed.</span></span>

- <span data-ttu-id="a0875-150">正在加载的程序集不来自`MyComputer`区域。</span><span class="sxs-lookup"><span data-stu-id="a0875-150">The assembly being loaded is not from the `MyComputer` zone.</span></span>

<span data-ttu-id="a0875-151">设置元素`<loadFromRemoteSources>`以防止`true`引发此异常。</span><span class="sxs-lookup"><span data-stu-id="a0875-151">Setting the `<loadFromRemoteSources>` element to `true` prevents this exception from being thrown.</span></span> <span data-ttu-id="a0875-152">它使您能够指定您不依赖通用语言运行时来对加载的程序集进行沙盒，以确保安全性，并且可以允许它们完全信任地执行。</span><span class="sxs-lookup"><span data-stu-id="a0875-152">It enables you to specify that you are not relying on the common language runtime to sandbox the loaded assemblies for security, and that they can be allowed to execute in full trust.</span></span>

## <a name="notes"></a><span data-ttu-id="a0875-153">说明</span><span class="sxs-lookup"><span data-stu-id="a0875-153">Notes</span></span>

- <span data-ttu-id="a0875-154">在 .NET 框架 4.5 和更高版本中，本地网络共享上的程序集默认完全信任运行;您不必启用该`<loadFromRemoteSources>`元素。</span><span class="sxs-lookup"><span data-stu-id="a0875-154">In the .NET Framework 4.5 and later versions, assemblies on local network shares run in full trust by default; you do not have to enable the `<loadFromRemoteSources>` element.</span></span>

- <span data-ttu-id="a0875-155">如果应用程序是从 Web 复制而来，Windows 会将其标记为 Web 应用程序，即使它驻留在本地计算机上也不例外。</span><span class="sxs-lookup"><span data-stu-id="a0875-155">If an application has been copied from the web, it is flagged by Windows as being a web application, even if it resides on the local computer.</span></span> <span data-ttu-id="a0875-156">您可以通过更改其文件属性来更改该名称，也可以使用 元素`<loadFromRemoteSources>`授予程序集完全信任。</span><span class="sxs-lookup"><span data-stu-id="a0875-156">You can change that designation by changing its file properties, or you can use the `<loadFromRemoteSources>` element to grant the assembly full trust.</span></span> <span data-ttu-id="a0875-157">对于操作系统标记为从 Web 加载的本地程序集，也可以使用 <xref:System.Reflection.Assembly.UnsafeLoadFrom%2A> 方法进行加载。</span><span class="sxs-lookup"><span data-stu-id="a0875-157">As an alternative, you can use the <xref:System.Reflection.Assembly.UnsafeLoadFrom%2A> method to load a local assembly that the operating system has flagged as having been loaded from the web.</span></span>

- <span data-ttu-id="a0875-158">您可以在 Windows<xref:System.IO.FileLoadException>虚拟 PC 应用程序中运行的 应用程序中获取 。</span><span class="sxs-lookup"><span data-stu-id="a0875-158">You may get a <xref:System.IO.FileLoadException> in an application that is running in a Windows Virtual PC application.</span></span> <span data-ttu-id="a0875-159">当您尝试从托管计算机上的链接文件夹中加载文件时，可能会发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="a0875-159">This can happen when you try to load a file from linked folders on the hosting computer.</span></span> <span data-ttu-id="a0875-160">当您尝试从通过[远程桌面服务](/windows/win32/termserv/terminal-services-portal)（终端服务）链接的文件夹中加载文件时，也会发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="a0875-160">It can also occur when you try to load a file from a folder linked over [Remote Desktop Services](/windows/win32/termserv/terminal-services-portal) (Terminal Services).</span></span> <span data-ttu-id="a0875-161">为了避免异常，请设置为`enabled``true`。</span><span class="sxs-lookup"><span data-stu-id="a0875-161">To avoid the exception, set `enabled` to `true`.</span></span>

## <a name="configuration-file"></a><span data-ttu-id="a0875-162">配置文件</span><span class="sxs-lookup"><span data-stu-id="a0875-162">Configuration file</span></span>

<span data-ttu-id="a0875-163">此元素通常用在应用程序配置文件中，但可根据上下文用于其他配置文件。</span><span class="sxs-lookup"><span data-stu-id="a0875-163">This element is typically used in the application configuration file, but can be used in other configuration files depending upon the context.</span></span> <span data-ttu-id="a0875-164">有关详细信息，请参阅文章["CAS 策略的更多隐式使用：在](https://docs.microsoft.com/archive/blogs/shawnfa/more-implicit-uses-of-cas-policy-loadfromremotesources).NET 安全博客中加载从远程资源"。</span><span class="sxs-lookup"><span data-stu-id="a0875-164">For more information, see the article [More Implicit Uses of CAS Policy: loadFromRemoteSources](https://docs.microsoft.com/archive/blogs/shawnfa/more-implicit-uses-of-cas-policy-loadfromremotesources) in the .NET Security blog.</span></span>  

## <a name="example"></a><span data-ttu-id="a0875-165">示例</span><span class="sxs-lookup"><span data-stu-id="a0875-165">Example</span></span>

<span data-ttu-id="a0875-166">下面的示例演示如何对从远程源加载的程序集授予完全信任。</span><span class="sxs-lookup"><span data-stu-id="a0875-166">The following example shows how to grant full trust to assemblies loaded from remote sources.</span></span>

```xml
<configuration>  
   <runtime>  
      <loadFromRemoteSources enabled="true"/>  
   </runtime>  
</configuration>  
```

## <a name="see-also"></a><span data-ttu-id="a0875-167">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a0875-167">See also</span></span>

- [<span data-ttu-id="a0875-168">CAS 策略的更多隐式使用：从远程源加载</span><span class="sxs-lookup"><span data-stu-id="a0875-168">More Implicit Uses of CAS Policy: loadFromRemoteSources</span></span>](https://docs.microsoft.com/archive/blogs/shawnfa/more-implicit-uses-of-cas-policy-loadfromremotesources)
- [<span data-ttu-id="a0875-169">如何：运行沙盒中部分受信任的代码</span><span class="sxs-lookup"><span data-stu-id="a0875-169">How to: Run Partially Trusted Code in a Sandbox</span></span>](../../../misc/how-to-run-partially-trusted-code-in-a-sandbox.md)
- [<span data-ttu-id="a0875-170">运行时设置架构</span><span class="sxs-lookup"><span data-stu-id="a0875-170">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="a0875-171">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="a0875-171">Configuration File Schema</span></span>](../index.md)
- <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType>
