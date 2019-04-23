---
title: <legacyImpersonationPolicy> 元素
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#legacyImpersonationPolicy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/legacyImpersonationPolicy
helpviewer_keywords:
- <legacyImpersonationPolicy> element
- legacyImpersonationPolicy element
ms.assetid: 6e00af10-42f3-4235-8415-1bb2db78394e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c39ee551dde19d87a75403f3db7433d1ef829f3b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59333985"
---
# <a name="legacyimpersonationpolicy-element"></a><span data-ttu-id="2c6c3-102">\<legacyImpersonationPolicy > 元素</span><span class="sxs-lookup"><span data-stu-id="2c6c3-102">\<legacyImpersonationPolicy> Element</span></span>
<span data-ttu-id="2c6c3-103">指定 Windows 标识不流经异步点，而不考虑当前线程上执行上下文的流设置。</span><span class="sxs-lookup"><span data-stu-id="2c6c3-103">Specifies that the Windows identity does not flow across asynchronous points, regardless of the flow settings for the execution context on the current thread.</span></span>  
  
 <span data-ttu-id="2c6c3-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="2c6c3-104">\<configuration></span></span>  
<span data-ttu-id="2c6c3-105">\<运行时 ></span><span class="sxs-lookup"><span data-stu-id="2c6c3-105">\<runtime></span></span>  
<span data-ttu-id="2c6c3-106">\<legacyImpersonationPolicy></span><span class="sxs-lookup"><span data-stu-id="2c6c3-106">\<legacyImpersonationPolicy></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c6c3-107">语法</span><span class="sxs-lookup"><span data-stu-id="2c6c3-107">Syntax</span></span>  
  
```xml  
<legacyImpersonationPolicy    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2c6c3-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="2c6c3-108">Attributes and Elements</span></span>  
 <span data-ttu-id="2c6c3-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="2c6c3-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2c6c3-110">特性</span><span class="sxs-lookup"><span data-stu-id="2c6c3-110">Attributes</span></span>  
  
|<span data-ttu-id="2c6c3-111">特性</span><span class="sxs-lookup"><span data-stu-id="2c6c3-111">Attribute</span></span>|<span data-ttu-id="2c6c3-112">描述</span><span class="sxs-lookup"><span data-stu-id="2c6c3-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="2c6c3-113">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="2c6c3-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="2c6c3-114">指定的<xref:System.Security.Principal.WindowsIdentity>不流经异步点，而不考虑<xref:System.Threading.ExecutionContext>流当前线程上的设置。</span><span class="sxs-lookup"><span data-stu-id="2c6c3-114">Specifies that the <xref:System.Security.Principal.WindowsIdentity> does not flow across asynchronous points, regardless of the <xref:System.Threading.ExecutionContext> flow settings on the current thread.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="2c6c3-115">enabled 特性</span><span class="sxs-lookup"><span data-stu-id="2c6c3-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="2c6c3-116">“值”</span><span class="sxs-lookup"><span data-stu-id="2c6c3-116">Value</span></span>|<span data-ttu-id="2c6c3-117">描述</span><span class="sxs-lookup"><span data-stu-id="2c6c3-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="2c6c3-118"><xref:System.Security.Principal.WindowsIdentity> 流经异步点，具体取决于<xref:System.Threading.ExecutionContext>流当前线程的设置。</span><span class="sxs-lookup"><span data-stu-id="2c6c3-118"><xref:System.Security.Principal.WindowsIdentity> flows across asynchronous points depending upon the <xref:System.Threading.ExecutionContext> flow settings for the current thread.</span></span> <span data-ttu-id="2c6c3-119">这是默认设置。</span><span class="sxs-lookup"><span data-stu-id="2c6c3-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="2c6c3-120"><xref:System.Security.Principal.WindowsIdentity> 不流经异步点，而不考虑<xref:System.Threading.ExecutionContext>流当前线程上的设置。</span><span class="sxs-lookup"><span data-stu-id="2c6c3-120"><xref:System.Security.Principal.WindowsIdentity> does not flow across asynchronous points, regardless of the <xref:System.Threading.ExecutionContext> flow settings on the current thread.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2c6c3-121">子元素</span><span class="sxs-lookup"><span data-stu-id="2c6c3-121">Child Elements</span></span>  
 <span data-ttu-id="2c6c3-122">无。</span><span class="sxs-lookup"><span data-stu-id="2c6c3-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2c6c3-123">父元素</span><span class="sxs-lookup"><span data-stu-id="2c6c3-123">Parent Elements</span></span>  
  
|<span data-ttu-id="2c6c3-124">元素</span><span class="sxs-lookup"><span data-stu-id="2c6c3-124">Element</span></span>|<span data-ttu-id="2c6c3-125">描述</span><span class="sxs-lookup"><span data-stu-id="2c6c3-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="2c6c3-126">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="2c6c3-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="2c6c3-127">包含有关程序集绑定和垃圾回收的信息。</span><span class="sxs-lookup"><span data-stu-id="2c6c3-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2c6c3-128">备注</span><span class="sxs-lookup"><span data-stu-id="2c6c3-128">Remarks</span></span>  
 <span data-ttu-id="2c6c3-129">在.NET framework 1.0 和 1.1，<xref:System.Security.Principal.WindowsIdentity>不会跨任何用户定义的异步点流动。</span><span class="sxs-lookup"><span data-stu-id="2c6c3-129">In the .NET Framework versions 1.0 and 1.1, the <xref:System.Security.Principal.WindowsIdentity> does not flow across any user-defined asynchronous points.</span></span> <span data-ttu-id="2c6c3-130">从.NET Framework 2.0 版开始，没有<xref:System.Threading.ExecutionContext>跨异步点在一个应用程序域中的流对象，其中包含有关当前正在执行的线程，和它的信息。</span><span class="sxs-lookup"><span data-stu-id="2c6c3-130">Starting with the .NET Framework version 2.0, there is an <xref:System.Threading.ExecutionContext> object that contains information about the currently executing thread, and it flows across asynchronous points within an application domain.</span></span> <span data-ttu-id="2c6c3-131"><xref:System.Security.Principal.WindowsIdentity>包含在此执行上下文中，因此还流经异步点，这意味着，如果存在的模拟上下文，它会流动。</span><span class="sxs-lookup"><span data-stu-id="2c6c3-131">The <xref:System.Security.Principal.WindowsIdentity> is included in this execution context and therefore also flows across the asynchronous points, which means that if an impersonation context exists, it will flow as well.</span></span>  
  
 <span data-ttu-id="2c6c3-132">从.NET Framework 2.0 开始，你可以使用`<legacyImpersonationPolicy>`元素来指定：<xref:System.Security.Principal.WindowsIdentity>不流经异步点。</span><span class="sxs-lookup"><span data-stu-id="2c6c3-132">Starting with the .NET Framework 2.0, you can use the `<legacyImpersonationPolicy>` element to specify that  <xref:System.Security.Principal.WindowsIdentity> does not flow across asynchronous points.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2c6c3-133">公共语言运行时 (CLR) 可的模拟使用托管的代码，不是模拟平台通过如执行托管代码的外部执行的操作调用到非托管代码或通过直接调用 Win32 函数察觉。</span><span class="sxs-lookup"><span data-stu-id="2c6c3-133">The common language runtime (CLR) is aware of impersonation operations performed using only managed code, not of impersonation performed outside of managed code, such as through platform invoke to unmanaged code or through direct calls to Win32 functions.</span></span> <span data-ttu-id="2c6c3-134">仅托管<xref:System.Security.Principal.WindowsIdentity>对象可以流经异步点，除非`alwaysFlowImpersonationPolicy`元素设置为 true (`<alwaysFlowImpersonationPolicy enabled="true"/>`)。</span><span class="sxs-lookup"><span data-stu-id="2c6c3-134">Only managed <xref:System.Security.Principal.WindowsIdentity> objects can flow across asynchronous points, unless the `alwaysFlowImpersonationPolicy` element has been set to true (`<alwaysFlowImpersonationPolicy enabled="true"/>`).</span></span> <span data-ttu-id="2c6c3-135">设置`alwaysFlowImpersonationPolicy`为 true 的元素指定的 Windows 标识始终流经异步点，而不考虑执行模拟的方式。</span><span class="sxs-lookup"><span data-stu-id="2c6c3-135">Setting the `alwaysFlowImpersonationPolicy` element to true specifies that the Windows identity always flows across asynchronous points, regardless of how impersonation was performed.</span></span> <span data-ttu-id="2c6c3-136">有关详细信息流动非托管模拟流经异步点，请参阅[ \<alwaysFlowImpersonationPolicy > 元素](../../../../../docs/framework/configure-apps/file-schema/runtime/alwaysflowimpersonationpolicy-element.md)。</span><span class="sxs-lookup"><span data-stu-id="2c6c3-136">For more information on flowing unmanaged impersonation across asynchronous points, see [\<alwaysFlowImpersonationPolicy> Element](../../../../../docs/framework/configure-apps/file-schema/runtime/alwaysflowimpersonationpolicy-element.md).</span></span>  
  
 <span data-ttu-id="2c6c3-137">您可以更改此默认行为中两种方法：</span><span class="sxs-lookup"><span data-stu-id="2c6c3-137">You can alter this default behavior in two other ways:</span></span>  
  
1. <span data-ttu-id="2c6c3-138">在每个线程进行的托管代码。</span><span class="sxs-lookup"><span data-stu-id="2c6c3-138">In managed code on a per-thread basis.</span></span>  
  
     <span data-ttu-id="2c6c3-139">可以通过修改禁止显示上每个线程进行的流<xref:System.Threading.ExecutionContext>并<xref:System.Security.SecurityContext>通过使用设置<xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType>，<xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType>或<xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType>方法。</span><span class="sxs-lookup"><span data-stu-id="2c6c3-139">You can suppress the flow on a per-thread basis by modifying the <xref:System.Threading.ExecutionContext> and <xref:System.Security.SecurityContext> settings by using the <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType>, <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType> or <xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType> method.</span></span>  
  
2. <span data-ttu-id="2c6c3-140">在对非托管承载接口来加载公共语言运行时 (CLR) 的调用。</span><span class="sxs-lookup"><span data-stu-id="2c6c3-140">In the call to the unmanaged hosting interface to load the common language runtime (CLR).</span></span>  
  
     <span data-ttu-id="2c6c3-141">如果使用非托管承载接口 （而不是一个简单托管可执行文件） 用于将 CLR 加载，则可以对的调用中指定特殊标志[CorBindToRuntimeEx 函数](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)函数。</span><span class="sxs-lookup"><span data-stu-id="2c6c3-141">If an unmanaged hosting interface (instead of a simple managed executable) is used to load the CLR, you can specify a special flag in the call to the [CorBindToRuntimeEx Function](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) function.</span></span> <span data-ttu-id="2c6c3-142">若要启用的整个过程的兼容性模式，设置`flags`参数[CorBindToRuntimeEx 函数](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)STARTUP_LEGACY_IMPERSONATION 到。</span><span class="sxs-lookup"><span data-stu-id="2c6c3-142">To enable the compatibility mode for the entire process, set the `flags` parameter for [CorBindToRuntimeEx Function](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) to STARTUP_LEGACY_IMPERSONATION.</span></span>  
  
 <span data-ttu-id="2c6c3-143">有关详细信息，请参阅[ \<alwaysFlowImpersonationPolicy > 元素](../../../../../docs/framework/configure-apps/file-schema/runtime/alwaysflowimpersonationpolicy-element.md)。</span><span class="sxs-lookup"><span data-stu-id="2c6c3-143">For more information, see the [\<alwaysFlowImpersonationPolicy> Element](../../../../../docs/framework/configure-apps/file-schema/runtime/alwaysflowimpersonationpolicy-element.md).</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="2c6c3-144">配置文件</span><span class="sxs-lookup"><span data-stu-id="2c6c3-144">Configuration File</span></span>  
 <span data-ttu-id="2c6c3-145">在.NET Framework 应用程序中，可以仅在应用程序配置文件中使用此元素。</span><span class="sxs-lookup"><span data-stu-id="2c6c3-145">In a .NET Framework application, this element can be used only in the application configuration file.</span></span>  
  
 <span data-ttu-id="2c6c3-146">在中找到的 aspnet.config 文件中可以为 ASP.NET 应用程序中，配置模拟流\<Windows 文件夹 > \Microsoft.NET\Framework\vx.x.xxxx 目录。</span><span class="sxs-lookup"><span data-stu-id="2c6c3-146">For an ASP.NET application, the impersonation flow can be configured in the aspnet.config file found in the \<Windows Folder>\Microsoft.NET\Framework\vx.x.xxxx directory.</span></span>  
  
 <span data-ttu-id="2c6c3-147">默认情况下 ASP.NET 通过使用以下配置设置可以禁用 aspnet.config 文件中的模拟流：</span><span class="sxs-lookup"><span data-stu-id="2c6c3-147">ASP.NET by default disables the impersonation flow in the aspnet.config file by using the following configuration settings:</span></span>  
  
``` xml
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="true"/>  
      <alwaysFlowImpersonationPolicy enabled="false"/>  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="2c6c3-148">在 ASP.NET 中，如果你想要允许的模拟流相反，您必须显式使用以下配置设置：</span><span class="sxs-lookup"><span data-stu-id="2c6c3-148">In ASP.NET, if you want to allow the flow of impersonation instead, you must explicitly use the following configuration settings:</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="false"/>  
      <alwaysFlowImpersonationPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="example"></a><span data-ttu-id="2c6c3-149">示例</span><span class="sxs-lookup"><span data-stu-id="2c6c3-149">Example</span></span>  
 <span data-ttu-id="2c6c3-150">下面的示例演示如何指定不会跨异步点流动的 Windows 标识的旧行为。</span><span class="sxs-lookup"><span data-stu-id="2c6c3-150">The following example shows how to specify the legacy behavior that does not flow the Windows identity across asynchronous points.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="2c6c3-151">请参阅</span><span class="sxs-lookup"><span data-stu-id="2c6c3-151">See also</span></span>

- [<span data-ttu-id="2c6c3-152">运行时设置架构</span><span class="sxs-lookup"><span data-stu-id="2c6c3-152">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="2c6c3-153">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="2c6c3-153">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="2c6c3-154">\<alwaysFlowImpersonationPolicy > 元素</span><span class="sxs-lookup"><span data-stu-id="2c6c3-154">\<alwaysFlowImpersonationPolicy> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/alwaysflowimpersonationpolicy-element.md)
