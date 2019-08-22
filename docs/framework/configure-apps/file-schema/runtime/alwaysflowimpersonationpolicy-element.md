---
title: <alwaysFlowImpersonationPolicy> 元素
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/alwaysFlowImpersonationPolicy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#alwaysFlowImpersonationPolicy
helpviewer_keywords:
- alwaysFlowImpersonationPolicy element
- <alwaysFlowImpersonationPolicy> element
ms.assetid: ee622801-9e46-470b-85ab-88c4b1dd2ee1
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b42c141362d99090db922d3a6b429f05592130cd
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/21/2019
ms.locfileid: "69659019"
---
# <a name="alwaysflowimpersonationpolicy-element"></a><span data-ttu-id="d581e-102">\<alwaysFlowImpersonationPolicy > 元素</span><span class="sxs-lookup"><span data-stu-id="d581e-102">\<alwaysFlowImpersonationPolicy> Element</span></span>
<span data-ttu-id="d581e-103">指定 Windows 标识始终流经异步点，而不考虑执行模拟的方式。</span><span class="sxs-lookup"><span data-stu-id="d581e-103">Specifies that the Windows identity always flows across asynchronous points, regardless of how impersonation was performed.</span></span>  
  
 <span data-ttu-id="d581e-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="d581e-104">\<configuration></span></span>  
<span data-ttu-id="d581e-105">\<运行时 ></span><span class="sxs-lookup"><span data-stu-id="d581e-105">\<runtime></span></span>  
<span data-ttu-id="d581e-106">\<alwaysFlowImpersonationPolicy></span><span class="sxs-lookup"><span data-stu-id="d581e-106">\<alwaysFlowImpersonationPolicy></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d581e-107">语法</span><span class="sxs-lookup"><span data-stu-id="d581e-107">Syntax</span></span>  
  
```xml  
<alwaysFlowImpersonationPolicy    
  enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d581e-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="d581e-108">Attributes and Elements</span></span>  
 <span data-ttu-id="d581e-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="d581e-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d581e-110">特性</span><span class="sxs-lookup"><span data-stu-id="d581e-110">Attributes</span></span>  
  
|<span data-ttu-id="d581e-111">特性</span><span class="sxs-lookup"><span data-stu-id="d581e-111">Attribute</span></span>|<span data-ttu-id="d581e-112">描述</span><span class="sxs-lookup"><span data-stu-id="d581e-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="d581e-113">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="d581e-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="d581e-114">指示 Windows 标识是否流经异步点。</span><span class="sxs-lookup"><span data-stu-id="d581e-114">Indicates whether the Windows identity flows across asynchronous points.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="d581e-115">enabled 特性</span><span class="sxs-lookup"><span data-stu-id="d581e-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="d581e-116">值</span><span class="sxs-lookup"><span data-stu-id="d581e-116">Value</span></span>|<span data-ttu-id="d581e-117">描述</span><span class="sxs-lookup"><span data-stu-id="d581e-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="d581e-118">Windows 标识不流经异步点, 除非模拟是通过托管方法 (如) <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A>执行的。</span><span class="sxs-lookup"><span data-stu-id="d581e-118">The Windows identity does not flow across asynchronous points, unless the impersonation is performed through managed methods such as <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A>.</span></span> <span data-ttu-id="d581e-119">这是默认设置。</span><span class="sxs-lookup"><span data-stu-id="d581e-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="d581e-120">无论模拟的执行方式如何, Windows 标识始终流经异步点。</span><span class="sxs-lookup"><span data-stu-id="d581e-120">The Windows identity always flows across asynchronous points, regardless of how impersonation was performed.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d581e-121">子元素</span><span class="sxs-lookup"><span data-stu-id="d581e-121">Child Elements</span></span>  
 <span data-ttu-id="d581e-122">无。</span><span class="sxs-lookup"><span data-stu-id="d581e-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d581e-123">父元素</span><span class="sxs-lookup"><span data-stu-id="d581e-123">Parent Elements</span></span>  
  
|<span data-ttu-id="d581e-124">元素</span><span class="sxs-lookup"><span data-stu-id="d581e-124">Element</span></span>|<span data-ttu-id="d581e-125">描述</span><span class="sxs-lookup"><span data-stu-id="d581e-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="d581e-126">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="d581e-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="d581e-127">包含有关程序集绑定和垃圾回收的信息。</span><span class="sxs-lookup"><span data-stu-id="d581e-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d581e-128">备注</span><span class="sxs-lookup"><span data-stu-id="d581e-128">Remarks</span></span>  
 <span data-ttu-id="d581e-129">在 .NET Framework 版本1.0 和1.1 中, Windows 标识不流经异步点。</span><span class="sxs-lookup"><span data-stu-id="d581e-129">In the .NET Framework versions 1.0 and 1.1, the Windows identity does not flow across asynchronous points.</span></span> <span data-ttu-id="d581e-130">在 .NET Framework 版本2.0 中, 有一个<xref:System.Threading.ExecutionContext>对象包含当前正在执行的线程的相关信息, 并在应用程序域中的异步点之间流动。</span><span class="sxs-lookup"><span data-stu-id="d581e-130">In the .NET Framework version 2.0, there is an <xref:System.Threading.ExecutionContext> object that contains information about the currently executing thread, and flows it across asynchronous points within an application domain.</span></span> <span data-ttu-id="d581e-131">如果<xref:System.Security.Principal.WindowsIdentity>通过使用托管方法 (如) <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A>而不是通过其他方式 (例如, 平台调用到本机方法) 来实现模拟, 则还会将流作为流过异步点的信息的一部分。</span><span class="sxs-lookup"><span data-stu-id="d581e-131">The <xref:System.Security.Principal.WindowsIdentity> also flows as part of the information that flows across the asynchronous points, provided the impersonation was achieved using managed methods such as <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A> and not through other means such as platform invoke to native methods.</span></span> <span data-ttu-id="d581e-132">此元素用于指定无论如何实现模拟, Windows 标识都将流经异步点。</span><span class="sxs-lookup"><span data-stu-id="d581e-132">This element is used to specify that the Windows identity does flow across asynchronous points, regardless of how the impersonation was achieved.</span></span>  
  
 <span data-ttu-id="d581e-133">可以通过两种其他方式更改此默认行为:</span><span class="sxs-lookup"><span data-stu-id="d581e-133">You can alter this default behavior in two other ways:</span></span>  
  
1. <span data-ttu-id="d581e-134">在托管代码中, 在每个线程的基础上。</span><span class="sxs-lookup"><span data-stu-id="d581e-134">In managed code on a per-thread basis.</span></span>  
  
     <span data-ttu-id="d581e-135"><xref:System.Threading.ExecutionContext>通过使用、或<xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType> <xref:System.Security.SecurityContext> 方法修改和设置,可以在每个线程上禁止显示流。<xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType> <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="d581e-135">You can suppress the flow on a per-thread basis by modifying the <xref:System.Threading.ExecutionContext> and <xref:System.Security.SecurityContext> settings by using the <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType>, <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType>, or <xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType> method.</span></span>  
  
2. <span data-ttu-id="d581e-136">在调用非托管承载接口以加载公共语言运行时 (CLR)。</span><span class="sxs-lookup"><span data-stu-id="d581e-136">In the call to the unmanaged hosting interface to load the common language runtime (CLR).</span></span>  
  
     <span data-ttu-id="d581e-137">如果使用非托管宿主接口 (而不是简单的托管可执行文件) 加载 CLR, 则可以在调用[CorBindToRuntimeEx 函数](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md)函数时指定特殊标志。</span><span class="sxs-lookup"><span data-stu-id="d581e-137">If an unmanaged hosting interface (instead of a simple managed executable) is used to load the CLR, you can specify a special flag in the call to the [CorBindToRuntimeEx Function](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) function.</span></span> <span data-ttu-id="d581e-138">若要为整个进程启用兼容模式, 请将`flags` [CorBindToRuntimeEx 函数](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md)的参数设置为`STARTUP_ALWAYSFLOW_IMPERSONATION`。</span><span class="sxs-lookup"><span data-stu-id="d581e-138">To enable the compatibility mode for the entire process, set the `flags` parameter for [CorBindToRuntimeEx Function](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) to `STARTUP_ALWAYSFLOW_IMPERSONATION`.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="d581e-139">配置文件</span><span class="sxs-lookup"><span data-stu-id="d581e-139">Configuration File</span></span>  
 <span data-ttu-id="d581e-140">在 .NET Framework 应用程序中, 此元素只能在应用程序配置文件中使用。</span><span class="sxs-lookup"><span data-stu-id="d581e-140">In a .NET Framework application, this element can be used only in the application configuration file.</span></span>  
  
 <span data-ttu-id="d581e-141">对于 ASP.NET 应用程序, 可以在\<Windows 文件夹 > \Microsoft.NET\Framework\vx.x.xxxx 目录中找到的 aspnet .config 文件中配置模拟流。</span><span class="sxs-lookup"><span data-stu-id="d581e-141">For an ASP.NET application, the impersonation flow can be configured in the aspnet.config file found in the \<Windows Folder>\Microsoft.NET\Framework\vx.x.xxxx directory.</span></span>  
  
 <span data-ttu-id="d581e-142">默认情况下, ASP.NET 使用以下配置设置禁用 aspnet 文件中的模拟流:</span><span class="sxs-lookup"><span data-stu-id="d581e-142">ASP.NET by default disables the impersonation flow in the aspnet.config file by using the following configuration settings:</span></span>  
  
```xml
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="true"/>  
      <alwaysFlowImpersonationPolicy enabled="false"/>  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="d581e-143">在 ASP.NET 中, 如果要改为允许模拟流, 则必须显式使用以下配置设置:</span><span class="sxs-lookup"><span data-stu-id="d581e-143">In ASP.NET, if you want to allow the flow of impersonation instead, you must explicitly use the following configuration settings:</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="false"/>  
      <alwaysFlowImpersonationPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="example"></a><span data-ttu-id="d581e-144">示例</span><span class="sxs-lookup"><span data-stu-id="d581e-144">Example</span></span>  
 <span data-ttu-id="d581e-145">下面的示例演示如何指定 Windows 标识流经异步点, 即使通过非托管方法实现模拟也是如此。</span><span class="sxs-lookup"><span data-stu-id="d581e-145">The following example shows how to specify that the Windows identity flows across asynchronous points, even when the impersonation is achieved through means other than managed methods.</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <alwaysFlowImpersonationPolicy enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d581e-146">请参阅</span><span class="sxs-lookup"><span data-stu-id="d581e-146">See also</span></span>

- [<span data-ttu-id="d581e-147">运行时设置架构</span><span class="sxs-lookup"><span data-stu-id="d581e-147">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="d581e-148">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="d581e-148">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="d581e-149">\<legacyImpersonationPolicy > 元素</span><span class="sxs-lookup"><span data-stu-id="d581e-149">\<legacyImpersonationPolicy> Element</span></span>](legacyimpersonationpolicy-element.md)
