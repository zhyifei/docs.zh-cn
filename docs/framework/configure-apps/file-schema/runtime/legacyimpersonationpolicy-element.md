---
title: "&lt;legacyImpersonationPolicy&gt;元素"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#legacyImpersonationPolicy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/legacyImpersonationPolicy
helpviewer_keywords:
- <legacyImpersonationPolicy> element
- legacyImpersonationPolicy element
ms.assetid: 6e00af10-42f3-4235-8415-1bb2db78394e
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 8f6bed837ab7b0c6a4aebe6116c5ab28bbc62175
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="ltlegacyimpersonationpolicygt-element"></a><span data-ttu-id="81fff-102">&lt;legacyImpersonationPolicy&gt;元素</span><span class="sxs-lookup"><span data-stu-id="81fff-102">&lt;legacyImpersonationPolicy&gt; Element</span></span>
<span data-ttu-id="81fff-103">指定 Windows 标识不流经异步点，而不考虑当前线程上执行上下文的流设置。</span><span class="sxs-lookup"><span data-stu-id="81fff-103">Specifies that the Windows identity does not flow across asynchronous points, regardless of the flow settings for the execution context on the current thread.</span></span>  
  
 <span data-ttu-id="81fff-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="81fff-104">\<configuration></span></span>  
<span data-ttu-id="81fff-105">\<运行时 ></span><span class="sxs-lookup"><span data-stu-id="81fff-105">\<runtime></span></span>  
<span data-ttu-id="81fff-106">\<legacyImpersonationPolicy ></span><span class="sxs-lookup"><span data-stu-id="81fff-106">\<legacyImpersonationPolicy></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="81fff-107">语法</span><span class="sxs-lookup"><span data-stu-id="81fff-107">Syntax</span></span>  
  
```xml  
<legacyImpersonationPolicy    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="81fff-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="81fff-108">Attributes and Elements</span></span>  
 <span data-ttu-id="81fff-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="81fff-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="81fff-110">特性</span><span class="sxs-lookup"><span data-stu-id="81fff-110">Attributes</span></span>  
  
|<span data-ttu-id="81fff-111">特性</span><span class="sxs-lookup"><span data-stu-id="81fff-111">Attribute</span></span>|<span data-ttu-id="81fff-112">描述</span><span class="sxs-lookup"><span data-stu-id="81fff-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="81fff-113">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="81fff-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="81fff-114">指定<xref:System.Security.Principal.WindowsIdentity>不流经异步点，而不考虑<xref:System.Threading.ExecutionContext>流当前线程上的设置。</span><span class="sxs-lookup"><span data-stu-id="81fff-114">Specifies that the <xref:System.Security.Principal.WindowsIdentity> does not flow across asynchronous points, regardless of the <xref:System.Threading.ExecutionContext> flow settings on the current thread.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="81fff-115">enabled 特性</span><span class="sxs-lookup"><span data-stu-id="81fff-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="81fff-116">值</span><span class="sxs-lookup"><span data-stu-id="81fff-116">Value</span></span>|<span data-ttu-id="81fff-117">描述</span><span class="sxs-lookup"><span data-stu-id="81fff-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="81fff-118"><xref:System.Security.Principal.WindowsIdentity>流经异步点，具体取决于<xref:System.Threading.ExecutionContext>流设置确定是否当前的线程。</span><span class="sxs-lookup"><span data-stu-id="81fff-118"><xref:System.Security.Principal.WindowsIdentity> flows across asynchronous points depending upon the <xref:System.Threading.ExecutionContext> flow settings for the current thread.</span></span> <span data-ttu-id="81fff-119">这是默认设置。</span><span class="sxs-lookup"><span data-stu-id="81fff-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="81fff-120"><xref:System.Security.Principal.WindowsIdentity>不流经异步点，而不考虑<xref:System.Threading.ExecutionContext>流当前线程上的设置。</span><span class="sxs-lookup"><span data-stu-id="81fff-120"><xref:System.Security.Principal.WindowsIdentity> does not flow across asynchronous points, regardless of the <xref:System.Threading.ExecutionContext> flow settings on the current thread.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="81fff-121">子元素</span><span class="sxs-lookup"><span data-stu-id="81fff-121">Child Elements</span></span>  
 <span data-ttu-id="81fff-122">无。</span><span class="sxs-lookup"><span data-stu-id="81fff-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="81fff-123">父元素</span><span class="sxs-lookup"><span data-stu-id="81fff-123">Parent Elements</span></span>  
  
|<span data-ttu-id="81fff-124">元素</span><span class="sxs-lookup"><span data-stu-id="81fff-124">Element</span></span>|<span data-ttu-id="81fff-125">描述</span><span class="sxs-lookup"><span data-stu-id="81fff-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="81fff-126">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="81fff-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="81fff-127">包含有关程序集绑定和垃圾回收的信息。</span><span class="sxs-lookup"><span data-stu-id="81fff-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="81fff-128">备注</span><span class="sxs-lookup"><span data-stu-id="81fff-128">Remarks</span></span>  
 <span data-ttu-id="81fff-129">在.NET framework 1.0 和 1.1 中，<xref:System.Security.Principal.WindowsIdentity>不流经任何用户定义的异步点。</span><span class="sxs-lookup"><span data-stu-id="81fff-129">In the .NET Framework versions 1.0 and 1.1, the <xref:System.Security.Principal.WindowsIdentity> does not flow across any user-defined asynchronous points.</span></span> <span data-ttu-id="81fff-130">从.NET Framework 2.0 版开始，没有<xref:System.Threading.ExecutionContext>对象，其中包含有关当前正在执行的线程，并在它的信息流经应用程序域中的异步点。</span><span class="sxs-lookup"><span data-stu-id="81fff-130">Starting with the .NET Framework version 2.0, there is an <xref:System.Threading.ExecutionContext> object that contains information about the currently executing thread, and it flows across asynchronous points within an application domain.</span></span> <span data-ttu-id="81fff-131"><xref:System.Security.Principal.WindowsIdentity>包含在此执行上下文中，因此也会流过异步的点，这意味着，如果存在模拟上下文，它会流动。</span><span class="sxs-lookup"><span data-stu-id="81fff-131">The <xref:System.Security.Principal.WindowsIdentity> is included in this execution context and therefore also flows across the asynchronous points, which means that if an impersonation context exists, it will flow as well.</span></span>  
  
 <span data-ttu-id="81fff-132">从.NET Framework 2.0 开始，你可以使用`<legacyImpersonationPolicy>`元素来指定：<xref:System.Security.Principal.WindowsIdentity>不流经异步点。</span><span class="sxs-lookup"><span data-stu-id="81fff-132">Starting with the .NET Framework 2.0, you can use the `<legacyImpersonationPolicy>` element to specify that  <xref:System.Security.Principal.WindowsIdentity> does not flow across asynchronous points.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="81fff-133">公共语言运行时 (CLR) 时注意到使用托管的代码，不执行的模拟外部托管代码中，如通过平台执行的操作调用到非托管代码或通过直接调用 Win32 函数的模拟。</span><span class="sxs-lookup"><span data-stu-id="81fff-133">The common language runtime (CLR) is aware of impersonation operations performed using only managed code, not of impersonation performed outside of managed code, such as through platform invoke to unmanaged code or through direct calls to Win32 functions.</span></span> <span data-ttu-id="81fff-134">仅托管<xref:System.Security.Principal.WindowsIdentity>对象可以流经异步点，除非`alwaysFlowImpersonationPolicy`元素已设置为 true (`<alwaysFlowImpersonationPolicy enabled="true"/>`)。</span><span class="sxs-lookup"><span data-stu-id="81fff-134">Only managed <xref:System.Security.Principal.WindowsIdentity> objects can flow across asynchronous points, unless the `alwaysFlowImpersonationPolicy` element has been set to true (`<alwaysFlowImpersonationPolicy enabled="true"/>`).</span></span> <span data-ttu-id="81fff-135">设置`alwaysFlowImpersonationPolicy`为 true 的元素指定的 Windows 标识始终异步点，而不考虑如何执行模拟间流动。</span><span class="sxs-lookup"><span data-stu-id="81fff-135">Setting the `alwaysFlowImpersonationPolicy` element to true specifies that the Windows identity always flows across asynchronous points, regardless of how impersonation was performed.</span></span> <span data-ttu-id="81fff-136">有关详细信息流动非模拟托管流经异步点，请参阅[ \<alwaysFlowImpersonationPolicy > 元素](../../../../../docs/framework/configure-apps/file-schema/runtime/alwaysflowimpersonationpolicy-element.md)。</span><span class="sxs-lookup"><span data-stu-id="81fff-136">For more information on flowing unmanaged impersonation across asynchronous points, see [\<alwaysFlowImpersonationPolicy> Element](../../../../../docs/framework/configure-apps/file-schema/runtime/alwaysflowimpersonationpolicy-element.md).</span></span>  
  
 <span data-ttu-id="81fff-137">你可以更改此默认行为，另外两种：</span><span class="sxs-lookup"><span data-stu-id="81fff-137">You can alter this default behavior in two other ways:</span></span>  
  
1.  <span data-ttu-id="81fff-138">中基于每个线程的托管代码。</span><span class="sxs-lookup"><span data-stu-id="81fff-138">In managed code on a per-thread basis.</span></span>  
  
     <span data-ttu-id="81fff-139">你可以修改来取消显示的每个线程基础上的流<xref:System.Threading.ExecutionContext>和<xref:System.Security.SecurityContext>设置通过使用<xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType>，<xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType>或<xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType>方法。</span><span class="sxs-lookup"><span data-stu-id="81fff-139">You can suppress the flow on a per-thread basis by modifying the <xref:System.Threading.ExecutionContext> and <xref:System.Security.SecurityContext> settings by using the <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType>, <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType> or <xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType> method.</span></span>  
  
2.  <span data-ttu-id="81fff-140">在加载公共语言运行时 (CLR) 的非托管承载接口的调用。</span><span class="sxs-lookup"><span data-stu-id="81fff-140">In the call to the unmanaged hosting interface to load the common language runtime (CLR).</span></span>  
  
     <span data-ttu-id="81fff-141">如果使用非托管承载接口 （而不是一个简单托管可执行文件） 用于加载 CLR，则可以对的调用中指定的特殊标志[CorBindToRuntimeEx 函数](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)函数。</span><span class="sxs-lookup"><span data-stu-id="81fff-141">If an unmanaged hosting interface (instead of a simple managed executable) is used to load the CLR, you can specify a special flag in the call to the [CorBindToRuntimeEx Function](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) function.</span></span> <span data-ttu-id="81fff-142">若要启用的整个过程的兼容性模式，设置`flags`参数[CorBindToRuntimeEx 函数](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)到 STARTUP_LEGACY_IMPERSONATION。</span><span class="sxs-lookup"><span data-stu-id="81fff-142">To enable the compatibility mode for the entire process, set the `flags` parameter for [CorBindToRuntimeEx Function](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) to STARTUP_LEGACY_IMPERSONATION.</span></span>  
  
 <span data-ttu-id="81fff-143">有关详细信息，请参阅[ \<alwaysFlowImpersonationPolicy > 元素](../../../../../docs/framework/configure-apps/file-schema/runtime/alwaysflowimpersonationpolicy-element.md)。</span><span class="sxs-lookup"><span data-stu-id="81fff-143">For more information, see the [\<alwaysFlowImpersonationPolicy> Element](../../../../../docs/framework/configure-apps/file-schema/runtime/alwaysflowimpersonationpolicy-element.md).</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="81fff-144">配置文件</span><span class="sxs-lookup"><span data-stu-id="81fff-144">Configuration File</span></span>  
 <span data-ttu-id="81fff-145">在.NET Framework 应用程序，可以仅在应用程序配置文件中使用此元素。</span><span class="sxs-lookup"><span data-stu-id="81fff-145">In a .NET Framework application, this element can be used only in the application configuration file.</span></span>  
  
 <span data-ttu-id="81fff-146">在 aspnet.config 文件中可以 ASP.NET 应用程序，配置模拟流\<Windows 文件夹 > \Microsoft.NET\Framework\vx.x.xxxx 目录。</span><span class="sxs-lookup"><span data-stu-id="81fff-146">For an ASP.NET application, the impersonation flow can be configured in the aspnet.config file found in the \<Windows Folder>\Microsoft.NET\Framework\vx.x.xxxx directory.</span></span>  
  
 <span data-ttu-id="81fff-147">默认情况下的 ASP.NET 通过使用以下配置设置来禁用下的 aspnet.config 文件中的模拟流：</span><span class="sxs-lookup"><span data-stu-id="81fff-147">ASP.NET by default disables the impersonation flow in the aspnet.config file by using the following configuration settings:</span></span>  
  
```  
configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="true"/>  
      <alwaysFlowImpersonationPolicy enabled="false"/>  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="81fff-148">在 ASP.NET 中，如果你想要允许的模拟流相反，你必须显式使用以下配置设置：</span><span class="sxs-lookup"><span data-stu-id="81fff-148">In ASP.NET, if you want to allow the flow of impersonation instead, you must explicitly use the following configuration settings:</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="false"/>  
      <alwaysFlowImpersonationPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="example"></a><span data-ttu-id="81fff-149">示例</span><span class="sxs-lookup"><span data-stu-id="81fff-149">Example</span></span>  
 <span data-ttu-id="81fff-150">下面的示例演示如何指定不会各异步点之间流动的 Windows 标识的旧行为。</span><span class="sxs-lookup"><span data-stu-id="81fff-150">The following example shows how to specify the legacy behavior that does not flow the Windows identity across asynchronous points.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="81fff-151">另请参阅</span><span class="sxs-lookup"><span data-stu-id="81fff-151">See Also</span></span>  
 [<span data-ttu-id="81fff-152">运行时设置架构</span><span class="sxs-lookup"><span data-stu-id="81fff-152">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="81fff-153">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="81fff-153">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="81fff-154">\<alwaysFlowImpersonationPolicy > 元素</span><span class="sxs-lookup"><span data-stu-id="81fff-154">\<alwaysFlowImpersonationPolicy> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/alwaysflowimpersonationpolicy-element.md)
