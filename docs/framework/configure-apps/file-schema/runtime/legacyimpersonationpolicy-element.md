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
ms.openlocfilehash: da01d0dac2e67d6c0131a2b5965472bbd19213fe
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69927317"
---
# <a name="legacyimpersonationpolicy-element"></a><span data-ttu-id="06ae1-102">\<legacyImpersonationPolicy > 元素</span><span class="sxs-lookup"><span data-stu-id="06ae1-102">\<legacyImpersonationPolicy> Element</span></span>
<span data-ttu-id="06ae1-103">指定 Windows 标识不流经异步点，而不考虑当前线程上执行上下文的流设置。</span><span class="sxs-lookup"><span data-stu-id="06ae1-103">Specifies that the Windows identity does not flow across asynchronous points, regardless of the flow settings for the execution context on the current thread.</span></span>  
  
 <span data-ttu-id="06ae1-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="06ae1-104">\<configuration></span></span>  
<span data-ttu-id="06ae1-105">\<运行时 ></span><span class="sxs-lookup"><span data-stu-id="06ae1-105">\<runtime></span></span>  
<span data-ttu-id="06ae1-106">\<legacyImpersonationPolicy></span><span class="sxs-lookup"><span data-stu-id="06ae1-106">\<legacyImpersonationPolicy></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06ae1-107">语法</span><span class="sxs-lookup"><span data-stu-id="06ae1-107">Syntax</span></span>  
  
```xml  
<legacyImpersonationPolicy    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="06ae1-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="06ae1-108">Attributes and Elements</span></span>  
 <span data-ttu-id="06ae1-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="06ae1-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="06ae1-110">特性</span><span class="sxs-lookup"><span data-stu-id="06ae1-110">Attributes</span></span>  
  
|<span data-ttu-id="06ae1-111">特性</span><span class="sxs-lookup"><span data-stu-id="06ae1-111">Attribute</span></span>|<span data-ttu-id="06ae1-112">描述</span><span class="sxs-lookup"><span data-stu-id="06ae1-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="06ae1-113">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="06ae1-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="06ae1-114">指定不流经异步点, 无论<xref:System.Threading.ExecutionContext>当前线程上的流设置如何。 <xref:System.Security.Principal.WindowsIdentity></span><span class="sxs-lookup"><span data-stu-id="06ae1-114">Specifies that the <xref:System.Security.Principal.WindowsIdentity> does not flow across asynchronous points, regardless of the <xref:System.Threading.ExecutionContext> flow settings on the current thread.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="06ae1-115">enabled 特性</span><span class="sxs-lookup"><span data-stu-id="06ae1-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="06ae1-116">值</span><span class="sxs-lookup"><span data-stu-id="06ae1-116">Value</span></span>|<span data-ttu-id="06ae1-117">描述</span><span class="sxs-lookup"><span data-stu-id="06ae1-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="06ae1-118"><xref:System.Security.Principal.WindowsIdentity>根据当前线程的<xref:System.Threading.ExecutionContext>流设置, 跨异步点流动。</span><span class="sxs-lookup"><span data-stu-id="06ae1-118"><xref:System.Security.Principal.WindowsIdentity> flows across asynchronous points depending upon the <xref:System.Threading.ExecutionContext> flow settings for the current thread.</span></span> <span data-ttu-id="06ae1-119">这是默认设置。</span><span class="sxs-lookup"><span data-stu-id="06ae1-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="06ae1-120"><xref:System.Security.Principal.WindowsIdentity>不流经异步点, 无论<xref:System.Threading.ExecutionContext>当前线程上的流设置如何。</span><span class="sxs-lookup"><span data-stu-id="06ae1-120"><xref:System.Security.Principal.WindowsIdentity> does not flow across asynchronous points, regardless of the <xref:System.Threading.ExecutionContext> flow settings on the current thread.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="06ae1-121">子元素</span><span class="sxs-lookup"><span data-stu-id="06ae1-121">Child Elements</span></span>  
 <span data-ttu-id="06ae1-122">无。</span><span class="sxs-lookup"><span data-stu-id="06ae1-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="06ae1-123">父元素</span><span class="sxs-lookup"><span data-stu-id="06ae1-123">Parent Elements</span></span>  
  
|<span data-ttu-id="06ae1-124">元素</span><span class="sxs-lookup"><span data-stu-id="06ae1-124">Element</span></span>|<span data-ttu-id="06ae1-125">描述</span><span class="sxs-lookup"><span data-stu-id="06ae1-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="06ae1-126">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="06ae1-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="06ae1-127">包含有关程序集绑定和垃圾回收的信息。</span><span class="sxs-lookup"><span data-stu-id="06ae1-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="06ae1-128">备注</span><span class="sxs-lookup"><span data-stu-id="06ae1-128">Remarks</span></span>  
 <span data-ttu-id="06ae1-129">在 .NET Framework 版本1.0 和1.1 中, <xref:System.Security.Principal.WindowsIdentity>不在任何用户定义的异步点上流动。</span><span class="sxs-lookup"><span data-stu-id="06ae1-129">In the .NET Framework versions 1.0 and 1.1, the <xref:System.Security.Principal.WindowsIdentity> does not flow across any user-defined asynchronous points.</span></span> <span data-ttu-id="06ae1-130">从 .NET Framework 版本2.0 开始, 有一个<xref:System.Threading.ExecutionContext>对象, 该对象包含当前正在执行的线程的相关信息, 并在应用程序域中的异步点之间流动。</span><span class="sxs-lookup"><span data-stu-id="06ae1-130">Starting with the .NET Framework version 2.0, there is an <xref:System.Threading.ExecutionContext> object that contains information about the currently executing thread, and it flows across asynchronous points within an application domain.</span></span> <span data-ttu-id="06ae1-131"><xref:System.Security.Principal.WindowsIdentity>包含在此执行上下文中, 因此也会流过异步点, 这意味着, 如果存在模拟上下文, 它也会流动。</span><span class="sxs-lookup"><span data-stu-id="06ae1-131">The <xref:System.Security.Principal.WindowsIdentity> is included in this execution context and therefore also flows across the asynchronous points, which means that if an impersonation context exists, it will flow as well.</span></span>  
  
 <span data-ttu-id="06ae1-132">从 .NET Framework 2.0 开始, 可以使用`<legacyImpersonationPolicy>`元素<xref:System.Security.Principal.WindowsIdentity>指定不流经异步点。</span><span class="sxs-lookup"><span data-stu-id="06ae1-132">Starting with the .NET Framework 2.0, you can use the `<legacyImpersonationPolicy>` element to specify that  <xref:System.Security.Principal.WindowsIdentity> does not flow across asynchronous points.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="06ae1-133">公共语言运行时 (CLR) 知道仅使用托管代码执行的模拟操作, 而不是在托管代码之外执行的模拟, 例如通过平台调用到非托管代码或通过直接调用 Win32 函数。</span><span class="sxs-lookup"><span data-stu-id="06ae1-133">The common language runtime (CLR) is aware of impersonation operations performed using only managed code, not of impersonation performed outside of managed code, such as through platform invoke to unmanaged code or through direct calls to Win32 functions.</span></span> <span data-ttu-id="06ae1-134">只有托管<xref:System.Security.Principal.WindowsIdentity>对象才能流经异步点, 除非该`alwaysFlowImpersonationPolicy`元素已设置为 true (`<alwaysFlowImpersonationPolicy enabled="true"/>`)。</span><span class="sxs-lookup"><span data-stu-id="06ae1-134">Only managed <xref:System.Security.Principal.WindowsIdentity> objects can flow across asynchronous points, unless the `alwaysFlowImpersonationPolicy` element has been set to true (`<alwaysFlowImpersonationPolicy enabled="true"/>`).</span></span> <span data-ttu-id="06ae1-135">`alwaysFlowImpersonationPolicy`将元素设置为 true 可指定无论模拟的执行方式如何, Windows 标识总是流经异步点。</span><span class="sxs-lookup"><span data-stu-id="06ae1-135">Setting the `alwaysFlowImpersonationPolicy` element to true specifies that the Windows identity always flows across asynchronous points, regardless of how impersonation was performed.</span></span> <span data-ttu-id="06ae1-136">有关跨异步点流动非托管模拟的详细信息, 请参阅[ \<alwaysFlowImpersonationPolicy > 元素](alwaysflowimpersonationpolicy-element.md)。</span><span class="sxs-lookup"><span data-stu-id="06ae1-136">For more information on flowing unmanaged impersonation across asynchronous points, see [\<alwaysFlowImpersonationPolicy> Element](alwaysflowimpersonationpolicy-element.md).</span></span>  
  
 <span data-ttu-id="06ae1-137">可以通过两种其他方式更改此默认行为:</span><span class="sxs-lookup"><span data-stu-id="06ae1-137">You can alter this default behavior in two other ways:</span></span>  
  
1. <span data-ttu-id="06ae1-138">在托管代码中, 在每个线程的基础上。</span><span class="sxs-lookup"><span data-stu-id="06ae1-138">In managed code on a per-thread basis.</span></span>  
  
     <span data-ttu-id="06ae1-139"><xref:System.Threading.ExecutionContext>通过使用、或<xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType>方法修改和<xref:System.Security.SecurityContext>设置, <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType>可以按线程禁止显示流。 <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="06ae1-139">You can suppress the flow on a per-thread basis by modifying the <xref:System.Threading.ExecutionContext> and <xref:System.Security.SecurityContext> settings by using the <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType>, <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType> or <xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType> method.</span></span>  
  
2. <span data-ttu-id="06ae1-140">在调用非托管承载接口以加载公共语言运行时 (CLR)。</span><span class="sxs-lookup"><span data-stu-id="06ae1-140">In the call to the unmanaged hosting interface to load the common language runtime (CLR).</span></span>  
  
     <span data-ttu-id="06ae1-141">如果使用非托管宿主接口 (而不是简单的托管可执行文件) 加载 CLR, 则可以在调用[CorBindToRuntimeEx 函数](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md)函数时指定特殊标志。</span><span class="sxs-lookup"><span data-stu-id="06ae1-141">If an unmanaged hosting interface (instead of a simple managed executable) is used to load the CLR, you can specify a special flag in the call to the [CorBindToRuntimeEx Function](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) function.</span></span> <span data-ttu-id="06ae1-142">若要为整个进程启用兼容模式, 请将`flags` [CorBindToRuntimeEx 函数](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md)的参数设置为 STARTUP_LEGACY_IMPERSONATION。</span><span class="sxs-lookup"><span data-stu-id="06ae1-142">To enable the compatibility mode for the entire process, set the `flags` parameter for [CorBindToRuntimeEx Function](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) to STARTUP_LEGACY_IMPERSONATION.</span></span>  
  
 <span data-ttu-id="06ae1-143">有关详细信息, 请参阅[ \<alwaysFlowImpersonationPolicy > 元素](alwaysflowimpersonationpolicy-element.md)。</span><span class="sxs-lookup"><span data-stu-id="06ae1-143">For more information, see the [\<alwaysFlowImpersonationPolicy> Element](alwaysflowimpersonationpolicy-element.md).</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="06ae1-144">配置文件</span><span class="sxs-lookup"><span data-stu-id="06ae1-144">Configuration File</span></span>  
 <span data-ttu-id="06ae1-145">在 .NET Framework 应用程序中, 此元素只能在应用程序配置文件中使用。</span><span class="sxs-lookup"><span data-stu-id="06ae1-145">In a .NET Framework application, this element can be used only in the application configuration file.</span></span>  
  
 <span data-ttu-id="06ae1-146">对于 ASP.NET 应用程序, 可以在\<Windows 文件夹 > \Microsoft.NET\Framework\vx.x.xxxx 目录中找到的 aspnet .config 文件中配置模拟流。</span><span class="sxs-lookup"><span data-stu-id="06ae1-146">For an ASP.NET application, the impersonation flow can be configured in the aspnet.config file found in the \<Windows Folder>\Microsoft.NET\Framework\vx.x.xxxx directory.</span></span>  
  
 <span data-ttu-id="06ae1-147">默认情况下, ASP.NET 使用以下配置设置禁用 aspnet 文件中的模拟流:</span><span class="sxs-lookup"><span data-stu-id="06ae1-147">ASP.NET by default disables the impersonation flow in the aspnet.config file by using the following configuration settings:</span></span>  
  
``` xml
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="true"/>  
      <alwaysFlowImpersonationPolicy enabled="false"/>  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="06ae1-148">在 ASP.NET 中, 如果要改为允许模拟流, 则必须显式使用以下配置设置:</span><span class="sxs-lookup"><span data-stu-id="06ae1-148">In ASP.NET, if you want to allow the flow of impersonation instead, you must explicitly use the following configuration settings:</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="false"/>  
      <alwaysFlowImpersonationPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="example"></a><span data-ttu-id="06ae1-149">示例</span><span class="sxs-lookup"><span data-stu-id="06ae1-149">Example</span></span>  
 <span data-ttu-id="06ae1-150">下面的示例演示如何指定不跨异步点流式传输 Windows 标识的旧行为。</span><span class="sxs-lookup"><span data-stu-id="06ae1-150">The following example shows how to specify the legacy behavior that does not flow the Windows identity across asynchronous points.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="06ae1-151">请参阅</span><span class="sxs-lookup"><span data-stu-id="06ae1-151">See also</span></span>

- [<span data-ttu-id="06ae1-152">运行时设置架构</span><span class="sxs-lookup"><span data-stu-id="06ae1-152">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="06ae1-153">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="06ae1-153">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="06ae1-154">\<alwaysFlowImpersonationPolicy > 元素</span><span class="sxs-lookup"><span data-stu-id="06ae1-154">\<alwaysFlowImpersonationPolicy> Element</span></span>](alwaysflowimpersonationpolicy-element.md)
