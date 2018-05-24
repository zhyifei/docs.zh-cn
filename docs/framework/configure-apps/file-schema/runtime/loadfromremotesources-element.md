---
title: '&lt;loadFromRemoteSources&gt;元素'
ms.date: 03/30/2017
helpviewer_keywords:
- loadFromRemoteSources element
- <loadFromRemoteSources> element
ms.assetid: 006d1280-2ac3-4db6-a984-a3d4e275046a
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: acd66cdff9f2c68e7d665b1fd236b18eeb9b4bac
ms.sourcegitcommit: 43924acbdbb3981d103e11049bbe460457d42073
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/23/2018
---
# <a name="ltloadfromremotesourcesgt-element"></a><span data-ttu-id="4faf5-102">&lt;loadFromRemoteSources&gt;元素</span><span class="sxs-lookup"><span data-stu-id="4faf5-102">&lt;loadFromRemoteSources&gt; Element</span></span>
<span data-ttu-id="4faf5-103">指定是否从远程数据源的程序集应被授予完全信任。</span><span class="sxs-lookup"><span data-stu-id="4faf5-103">Specifies whether assemblies from remote sources should be granted full trust.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4faf5-104">如果你已由于采用 Visual Studio 项目错误列表或生成错误的错误消息定向到本主题，请参阅[如何： 使用 Visual Studio 中的来自 Web 的程序集](http://msdn.microsoft.com/library/d8635b63-89a0-41aa-90f4-f351b2111070)。</span><span class="sxs-lookup"><span data-stu-id="4faf5-104">If you were directed to this topic because of an error message in the Visual Studio project error list or a build error, see [How to: Use an Assembly from the Web in Visual Studio](http://msdn.microsoft.com/library/d8635b63-89a0-41aa-90f4-f351b2111070).</span></span>  
  
 <span data-ttu-id="4faf5-105">\<configuration></span><span class="sxs-lookup"><span data-stu-id="4faf5-105">\<configuration></span></span>  
<span data-ttu-id="4faf5-106">\<运行时 ></span><span class="sxs-lookup"><span data-stu-id="4faf5-106">\<runtime></span></span>  
<span data-ttu-id="4faf5-107">\<loadFromRemoteSources></span><span class="sxs-lookup"><span data-stu-id="4faf5-107">\<loadFromRemoteSources></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4faf5-108">语法</span><span class="sxs-lookup"><span data-stu-id="4faf5-108">Syntax</span></span>  
  
```xml  
<loadFromRemoteSources    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4faf5-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="4faf5-109">Attributes and Elements</span></span>  
 <span data-ttu-id="4faf5-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="4faf5-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4faf5-111">特性</span><span class="sxs-lookup"><span data-stu-id="4faf5-111">Attributes</span></span>  
  
|<span data-ttu-id="4faf5-112">特性</span><span class="sxs-lookup"><span data-stu-id="4faf5-112">Attribute</span></span>|<span data-ttu-id="4faf5-113">描述</span><span class="sxs-lookup"><span data-stu-id="4faf5-113">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="4faf5-114">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="4faf5-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="4faf5-115">指定是否从远程数据源加载程序集应被授予完全信任。</span><span class="sxs-lookup"><span data-stu-id="4faf5-115">Specifies whether an assembly that is loaded from remote sources should be granted full trust.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="4faf5-116">enabled 特性</span><span class="sxs-lookup"><span data-stu-id="4faf5-116">enabled Attribute</span></span>  
  
|<span data-ttu-id="4faf5-117">值</span><span class="sxs-lookup"><span data-stu-id="4faf5-117">Value</span></span>|<span data-ttu-id="4faf5-118">描述</span><span class="sxs-lookup"><span data-stu-id="4faf5-118">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="4faf5-119">不要授予完全信任应用程序从远程数据源。</span><span class="sxs-lookup"><span data-stu-id="4faf5-119">Do not grant full trust to applications from remote sources.</span></span> <span data-ttu-id="4faf5-120">这是默认设置。</span><span class="sxs-lookup"><span data-stu-id="4faf5-120">This is the default.</span></span>|  
|`true`|<span data-ttu-id="4faf5-121">从远程数据源，请向应用程序授予完全信任。</span><span class="sxs-lookup"><span data-stu-id="4faf5-121">Grant full trust to applications from remote sources.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4faf5-122">子元素</span><span class="sxs-lookup"><span data-stu-id="4faf5-122">Child Elements</span></span>  
 <span data-ttu-id="4faf5-123">无。</span><span class="sxs-lookup"><span data-stu-id="4faf5-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4faf5-124">父元素</span><span class="sxs-lookup"><span data-stu-id="4faf5-124">Parent Elements</span></span>  
  
|<span data-ttu-id="4faf5-125">元素</span><span class="sxs-lookup"><span data-stu-id="4faf5-125">Element</span></span>|<span data-ttu-id="4faf5-126">描述</span><span class="sxs-lookup"><span data-stu-id="4faf5-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="4faf5-127">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="4faf5-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="4faf5-128">包含有关运行时初始化选项的信息。</span><span class="sxs-lookup"><span data-stu-id="4faf5-128">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4faf5-129">备注</span><span class="sxs-lookup"><span data-stu-id="4faf5-129">Remarks</span></span>  
 <span data-ttu-id="4faf5-130">在.NET Framework 版本 3.5 和更早版本中，如果从远程位置，加载程序集的程序集将运行部分受信任的依赖在已加载它区域上的授予集。</span><span class="sxs-lookup"><span data-stu-id="4faf5-130">In the .NET Framework version 3.5 and earlier versions, if you loaded an assembly from a remote location, the assembly would run partially trusted with a grant set that depended on the zone in which it was loaded.</span></span> <span data-ttu-id="4faf5-131">例如，如果从网站加载程序集，则会将其加载到 Internet 区域中并被授予 Internet 权限集。</span><span class="sxs-lookup"><span data-stu-id="4faf5-131">For example, if you loaded an assembly from a website, it was loaded into the Internet zone and granted the Internet permission set.</span></span> <span data-ttu-id="4faf5-132">换而言之，它在中执行 Internet 沙盒。</span><span class="sxs-lookup"><span data-stu-id="4faf5-132">In other words, it executed in an Internet sandbox.</span></span> <span data-ttu-id="4faf5-133">如果你尝试在运行该程序集[!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)]和更高版本，将引发异常; 您必须显式创建沙盒的程序集 (请参阅[如何： 运行部分受信任的代码在沙盒中](../../../../../docs/framework/misc/how-to-run-partially-trusted-code-in-a-sandbox.md))，或在完全信任中运行它。</span><span class="sxs-lookup"><span data-stu-id="4faf5-133">If you try to run that assembly in the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] and later versions, an exception is thrown; you must either explicitly create a sandbox for the assembly (see [How to: Run Partially Trusted Code in a Sandbox](../../../../../docs/framework/misc/how-to-run-partially-trusted-code-in-a-sandbox.md)), or run it in full trust.</span></span>  
  
 <span data-ttu-id="4faf5-134">通过 `<loadFromRemoteSources>` 元素，可以指定那些在先前版本的 .NET Framework 中以部分信任方式运行的程序集在 [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] 和更高版本以完全信任的方式运行。</span><span class="sxs-lookup"><span data-stu-id="4faf5-134">The `<loadFromRemoteSources>` element lets you specify that the assemblies that would have run partially trusted in earlier versions of the .NET Framework are to be run fully trusted in the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] and later versions.</span></span> <span data-ttu-id="4faf5-135">默认情况下，远程程序集不在 [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] 和更高版本中运行。</span><span class="sxs-lookup"><span data-stu-id="4faf5-135">By default, remote assemblies do not run in the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] and later.</span></span> <span data-ttu-id="4faf5-136">若要运行远程程序集，则必须以完全信任方式运行它，或者创建沙盒 <xref:System.AppDomain> 来运行它。</span><span class="sxs-lookup"><span data-stu-id="4faf5-136">To run a remote assembly, you must either run it as fully trusted or create a sandboxed <xref:System.AppDomain> in which to run it.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4faf5-137">在 [!INCLUDE[net_v45](../../../../../includes/net-v45-md.md)] 中，本地网络共享中的程序集默认以完全信任方式运行；您不必启用 `<loadFromRemoteSources>` 元素。</span><span class="sxs-lookup"><span data-stu-id="4faf5-137">In the [!INCLUDE[net_v45](../../../../../includes/net-v45-md.md)], assemblies on local network shares are run as full trust by default; you do not have to enable the `<loadFromRemoteSources>` element.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4faf5-138">如果应用程序是从 Web 复制而来，Windows 会将其标记为 Web 应用程序，即使它驻留在本地计算机上也不例外。</span><span class="sxs-lookup"><span data-stu-id="4faf5-138">If an application has been copied from the web, it is flagged by Windows as being a web application, even if it resides on the local computer.</span></span> <span data-ttu-id="4faf5-139">你可以更改该标记通过更改文件属性，或者可以使用`<loadFromRemoteSources>`元素对程序集授予完全信任。</span><span class="sxs-lookup"><span data-stu-id="4faf5-139">You can change that designation by changing the file properties, or you can use the `<loadFromRemoteSources>` element to grant the assembly full trust.</span></span> <span data-ttu-id="4faf5-140">对于操作系统标记为从 Web 加载的本地程序集，也可以使用 <xref:System.Reflection.Assembly.UnsafeLoadFrom%2A> 方法进行加载。</span><span class="sxs-lookup"><span data-stu-id="4faf5-140">As an alternative, you can use the <xref:System.Reflection.Assembly.UnsafeLoadFrom%2A> method to load a local assembly that the operating system has flagged as having been loaded from the web.</span></span>  
  
 <span data-ttu-id="4faf5-141">`enabled`属性仅当禁用代码访问安全性 (CAS) 时，此元素时有效。</span><span class="sxs-lookup"><span data-stu-id="4faf5-141">The `enabled` attribute for this element is effective only when code access security (CAS) is disabled.</span></span> <span data-ttu-id="4faf5-142">默认情况下，CAS 策略中禁用[!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)]及更高版本。</span><span class="sxs-lookup"><span data-stu-id="4faf5-142">By default, CAS policy is disabled in the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] and later versions.</span></span> <span data-ttu-id="4faf5-143">如果你设置`enabled`到`true`，远程应用程序被授予完全信任。</span><span class="sxs-lookup"><span data-stu-id="4faf5-143">If you set `enabled` to `true`, remote applications are granted full trust.</span></span>  
  
 <span data-ttu-id="4faf5-144">如果`<loadFromRemoteSources>``enabled`未设置为`true`，以下情况下引发异常：</span><span class="sxs-lookup"><span data-stu-id="4faf5-144">If `<loadFromRemoteSources>` `enabled` is not set to `true`, an exception is thrown under the following conditions:</span></span>  
  
-   <span data-ttu-id="4faf5-145">当前域的沙盒处理行为是不同于在其行为[!INCLUDE[net_v35_short](../../../../../includes/net-v35-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="4faf5-145">The sandboxing behavior of the current domain is different from its behavior in the [!INCLUDE[net_v35_short](../../../../../includes/net-v35-short-md.md)].</span></span> <span data-ttu-id="4faf5-146">这要求 CAS 策略被禁用，并且不进行沙盒处理的当前域。</span><span class="sxs-lookup"><span data-stu-id="4faf5-146">This requires CAS policy to be disabled, and the current domain not to be sandboxed.</span></span>  
  
-   <span data-ttu-id="4faf5-147">正在加载的程序集不是来自`MyComputer`区域。</span><span class="sxs-lookup"><span data-stu-id="4faf5-147">The assembly being loaded is not from the `MyComputer` zone.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4faf5-148">你可能会收到<xref:System.IO.FileLoadException>在 Windows Virtual PC 应用程序尝试以从托管计算机上的链接文件夹加载文件时。</span><span class="sxs-lookup"><span data-stu-id="4faf5-148">You may get a <xref:System.IO.FileLoadException> in a Windows Virtual PC application when you try to load a file from linked folders on the hosting computer.</span></span> <span data-ttu-id="4faf5-149">当你尝试从通过链接的文件夹加载文件时，也可能发生此错误[远程桌面服务](http://go.microsoft.com/fwlink/?LinkId=182775)（终端服务）。</span><span class="sxs-lookup"><span data-stu-id="4faf5-149">This error may also occur when you try to load a file from a folder linked over [Remote Desktop Services](http://go.microsoft.com/fwlink/?LinkId=182775) (Terminal Services).</span></span> <span data-ttu-id="4faf5-150">若要避免此异常，设置`enabled`到`true`。</span><span class="sxs-lookup"><span data-stu-id="4faf5-150">To avoid the exception, set `enabled` to `true`.</span></span>  
  
 <span data-ttu-id="4faf5-151">设置`<loadFromRemoteSources>`元素`true`可防止引发此异常。</span><span class="sxs-lookup"><span data-stu-id="4faf5-151">Setting the `<loadFromRemoteSources>` element to `true` prevents this exception from being thrown.</span></span> <span data-ttu-id="4faf5-152">它可用于指定，你将不依赖于公共语言运行时沙盒为安全起见，已加载程序集和它们可以有权以执行完全信任。</span><span class="sxs-lookup"><span data-stu-id="4faf5-152">It enables you to specify that you are not relying on the common language runtime to sandbox the loaded assemblies for security, and that they can be allowed to execute as full trust.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="4faf5-153">如果程序集不应以完全信任权限运行，则不要设置此配置元素。</span><span class="sxs-lookup"><span data-stu-id="4faf5-153">If the assembly should not run in full trust, do not set this configuration element.</span></span> <span data-ttu-id="4faf5-154">相反，创建沙盒<xref:System.AppDomain>要在其中加载程序集。</span><span class="sxs-lookup"><span data-stu-id="4faf5-154">Instead, create a sandboxed <xref:System.AppDomain> in which to load the assembly.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="4faf5-155">配置文件</span><span class="sxs-lookup"><span data-stu-id="4faf5-155">Configuration File</span></span>  
 <span data-ttu-id="4faf5-156">此元素通常用在应用程序配置文件中，但可根据上下文用于其他配置文件。</span><span class="sxs-lookup"><span data-stu-id="4faf5-156">This element is typically used in the application configuration file, but can be used in other configuration files depending upon the context.</span></span> <span data-ttu-id="4faf5-157">有关详细信息，请参阅文章[详细隐式使用的 CAS 策略： loadFromRemoteSources](http://go.microsoft.com/fwlink/p/?LinkId=266839) .NET 安全博客中。</span><span class="sxs-lookup"><span data-stu-id="4faf5-157">For more information, see the article [More Implicit Uses of CAS Policy: loadFromRemoteSources](http://go.microsoft.com/fwlink/p/?LinkId=266839) in the .NET Security blog.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4faf5-158">示例</span><span class="sxs-lookup"><span data-stu-id="4faf5-158">Example</span></span>  
 <span data-ttu-id="4faf5-159">下面的示例演示如何从远程数据源向应用程序授予完全信任。</span><span class="sxs-lookup"><span data-stu-id="4faf5-159">The following example shows how to grant full trust to applications from remote sources.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <loadFromRemoteSources enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="4faf5-160">请参阅</span><span class="sxs-lookup"><span data-stu-id="4faf5-160">See Also</span></span>  
 [<span data-ttu-id="4faf5-161">更多隐式使用 CAS 策略： loadFromRemoteSources</span><span class="sxs-lookup"><span data-stu-id="4faf5-161">More Implicit Uses of CAS Policy: loadFromRemoteSources</span></span>](http://go.microsoft.com/fwlink/p/?LinkId=266839)  
 [<span data-ttu-id="4faf5-162">如何：运行沙盒中部分受信任的代码</span><span class="sxs-lookup"><span data-stu-id="4faf5-162">How to: Run Partially Trusted Code in a Sandbox</span></span>](../../../../../docs/framework/misc/how-to-run-partially-trusted-code-in-a-sandbox.md)  
 [<span data-ttu-id="4faf5-163">运行时设置架构</span><span class="sxs-lookup"><span data-stu-id="4faf5-163">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="4faf5-164">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="4faf5-164">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
