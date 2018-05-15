---
title: '&lt;alwaysFlowImpersonationPolicy&gt;元素'
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
ms.openlocfilehash: 5cc704bbf8631936dbbeb3539ea5ed0d8499f378
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="ltalwaysflowimpersonationpolicygt-element"></a><span data-ttu-id="a1bba-102">&lt;alwaysFlowImpersonationPolicy&gt;元素</span><span class="sxs-lookup"><span data-stu-id="a1bba-102">&lt;alwaysFlowImpersonationPolicy&gt; Element</span></span>
<span data-ttu-id="a1bba-103">指定 Windows 标识始终流经异步点，而不考虑执行模拟的方式。</span><span class="sxs-lookup"><span data-stu-id="a1bba-103">Specifies that the Windows identity always flows across asynchronous points, regardless of how impersonation was performed.</span></span>  
  
 <span data-ttu-id="a1bba-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="a1bba-104">\<configuration></span></span>  
<span data-ttu-id="a1bba-105">\<运行时 ></span><span class="sxs-lookup"><span data-stu-id="a1bba-105">\<runtime></span></span>  
<span data-ttu-id="a1bba-106">\<alwaysFlowImpersonationPolicy></span><span class="sxs-lookup"><span data-stu-id="a1bba-106">\<alwaysFlowImpersonationPolicy></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1bba-107">语法</span><span class="sxs-lookup"><span data-stu-id="a1bba-107">Syntax</span></span>  
  
```xml  
<alwaysFlowImpersonationPolicy    
  enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a1bba-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="a1bba-108">Attributes and Elements</span></span>  
 <span data-ttu-id="a1bba-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="a1bba-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a1bba-110">特性</span><span class="sxs-lookup"><span data-stu-id="a1bba-110">Attributes</span></span>  
  
|<span data-ttu-id="a1bba-111">特性</span><span class="sxs-lookup"><span data-stu-id="a1bba-111">Attribute</span></span>|<span data-ttu-id="a1bba-112">描述</span><span class="sxs-lookup"><span data-stu-id="a1bba-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="a1bba-113">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="a1bba-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="a1bba-114">指示是否的 Windows 标识流经异步点。</span><span class="sxs-lookup"><span data-stu-id="a1bba-114">Indicates whether the Windows identity flows across asynchronous points.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="a1bba-115">enabled 特性</span><span class="sxs-lookup"><span data-stu-id="a1bba-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="a1bba-116">值</span><span class="sxs-lookup"><span data-stu-id="a1bba-116">Value</span></span>|<span data-ttu-id="a1bba-117">描述</span><span class="sxs-lookup"><span data-stu-id="a1bba-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="a1bba-118">标识不流经异步点，除非通过执行模拟的 Windows 托管方法，如<xref:System.Security.Principal.WindowsIdentity.Impersonate%2A>。</span><span class="sxs-lookup"><span data-stu-id="a1bba-118">The Windows identity does not flow across asynchronous points, unless the impersonation is performed through managed methods such as <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A>.</span></span> <span data-ttu-id="a1bba-119">这是默认设置。</span><span class="sxs-lookup"><span data-stu-id="a1bba-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="a1bba-120">Windows 标识始终流经异步点，而不考虑如何执行模拟。</span><span class="sxs-lookup"><span data-stu-id="a1bba-120">The Windows identity always flows across asynchronous points, regardless of how impersonation was performed.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a1bba-121">子元素</span><span class="sxs-lookup"><span data-stu-id="a1bba-121">Child Elements</span></span>  
 <span data-ttu-id="a1bba-122">无。</span><span class="sxs-lookup"><span data-stu-id="a1bba-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a1bba-123">父元素</span><span class="sxs-lookup"><span data-stu-id="a1bba-123">Parent Elements</span></span>  
  
|<span data-ttu-id="a1bba-124">元素</span><span class="sxs-lookup"><span data-stu-id="a1bba-124">Element</span></span>|<span data-ttu-id="a1bba-125">描述</span><span class="sxs-lookup"><span data-stu-id="a1bba-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="a1bba-126">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="a1bba-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="a1bba-127">包含有关程序集绑定和垃圾回收的信息。</span><span class="sxs-lookup"><span data-stu-id="a1bba-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a1bba-128">备注</span><span class="sxs-lookup"><span data-stu-id="a1bba-128">Remarks</span></span>  
 <span data-ttu-id="a1bba-129">在.NET framework 1.0 和 1.1 版中，Windows 标识不会各异步点之间流动。</span><span class="sxs-lookup"><span data-stu-id="a1bba-129">In the .NET Framework versions 1.0 and 1.1, the Windows identity does not flow across asynchronous points.</span></span> <span data-ttu-id="a1bba-130">在.NET Framework 2.0 版中，没有<xref:System.Threading.ExecutionContext>包含有关当前正在执行的线程的信息并流经应用程序域中的异步点对象。</span><span class="sxs-lookup"><span data-stu-id="a1bba-130">In the .NET Framework version 2.0, there is an <xref:System.Threading.ExecutionContext> object that contains information about the currently executing thread, and flows it across asynchronous points within an application domain.</span></span> <span data-ttu-id="a1bba-131"><xref:System.Security.Principal.WindowsIdentity>还作为流经异步的点，模拟已实现使用提供的信息的一部分的流托管方法如<xref:System.Security.Principal.WindowsIdentity.Impersonate%2A>并不是通过其他方式如平台调用到本机方法。</span><span class="sxs-lookup"><span data-stu-id="a1bba-131">The <xref:System.Security.Principal.WindowsIdentity> also flows as part of the information that flows across the asynchronous points, provided the impersonation was achieved using managed methods such as <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A> and not through other means such as platform invoke to native methods.</span></span> <span data-ttu-id="a1bba-132">此元素用于指定 Windows 标识未流经异步点，而不考虑模拟已通过得以实现。</span><span class="sxs-lookup"><span data-stu-id="a1bba-132">This element is used to specify that the Windows identity does flow across asynchronous points, regardless of how the impersonation was achieved.</span></span>  
  
 <span data-ttu-id="a1bba-133">你可以更改此默认行为，另外两种：</span><span class="sxs-lookup"><span data-stu-id="a1bba-133">You can alter this default behavior in two other ways:</span></span>  
  
1.  <span data-ttu-id="a1bba-134">中基于每个线程的托管代码。</span><span class="sxs-lookup"><span data-stu-id="a1bba-134">In managed code on a per-thread basis.</span></span>  
  
     <span data-ttu-id="a1bba-135">你可以修改来取消显示的每个线程基础上的流<xref:System.Threading.ExecutionContext>和<xref:System.Security.SecurityContext>设置通过使用<xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType>， <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType>，或<xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType>方法。</span><span class="sxs-lookup"><span data-stu-id="a1bba-135">You can suppress the flow on a per-thread basis by modifying the <xref:System.Threading.ExecutionContext> and <xref:System.Security.SecurityContext> settings by using the <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType>, <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType>, or <xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType> method.</span></span>  
  
2.  <span data-ttu-id="a1bba-136">在加载公共语言运行时 (CLR) 的非托管承载接口的调用。</span><span class="sxs-lookup"><span data-stu-id="a1bba-136">In the call to the unmanaged hosting interface to load the common language runtime (CLR).</span></span>  
  
     <span data-ttu-id="a1bba-137">如果使用非托管承载接口 （而不是一个简单托管可执行文件） 用于加载 CLR，则可以对的调用中指定的特殊标志[CorBindToRuntimeEx 函数](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)函数。</span><span class="sxs-lookup"><span data-stu-id="a1bba-137">If an unmanaged hosting interface (instead of a simple managed executable) is used to load the CLR, you can specify a special flag in the call to the [CorBindToRuntimeEx Function](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) function.</span></span> <span data-ttu-id="a1bba-138">若要启用的整个过程的兼容性模式，设置`flags`参数[CorBindToRuntimeEx 函数](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)到`STARTUP_ALWAYSFLOW_IMPERSONATION`。</span><span class="sxs-lookup"><span data-stu-id="a1bba-138">To enable the compatibility mode for the entire process, set the `flags` parameter for [CorBindToRuntimeEx Function](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) to `STARTUP_ALWAYSFLOW_IMPERSONATION`.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="a1bba-139">配置文件</span><span class="sxs-lookup"><span data-stu-id="a1bba-139">Configuration File</span></span>  
 <span data-ttu-id="a1bba-140">在.NET Framework 应用程序，可以仅在应用程序配置文件中使用此元素。</span><span class="sxs-lookup"><span data-stu-id="a1bba-140">In a .NET Framework application, this element can be used only in the application configuration file.</span></span>  
  
 <span data-ttu-id="a1bba-141">在 aspnet.config 文件中可以 ASP.NET 应用程序，配置模拟流\<Windows 文件夹 > \Microsoft.NET\Framework\vx.x.xxxx 目录。</span><span class="sxs-lookup"><span data-stu-id="a1bba-141">For an ASP.NET application, the impersonation flow can be configured in the aspnet.config file found in the \<Windows Folder>\Microsoft.NET\Framework\vx.x.xxxx directory.</span></span>  
  
 <span data-ttu-id="a1bba-142">默认情况下的 ASP.NET 通过使用以下配置设置来禁用下的 aspnet.config 文件中的模拟流：</span><span class="sxs-lookup"><span data-stu-id="a1bba-142">ASP.NET by default disables the impersonation flow in the aspnet.config file by using the following configuration settings:</span></span>  
  
```xml
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="true"/>  
      <alwaysFlowImpersonationPolicy enabled="false"/>  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="a1bba-143">在 ASP.NET 中，如果你想要允许的模拟流相反，你必须显式使用以下配置设置：</span><span class="sxs-lookup"><span data-stu-id="a1bba-143">In ASP.NET, if you want to allow the flow of impersonation instead, you must explicitly use the following configuration settings:</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="false"/>  
      <alwaysFlowImpersonationPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="example"></a><span data-ttu-id="a1bba-144">示例</span><span class="sxs-lookup"><span data-stu-id="a1bba-144">Example</span></span>  
 <span data-ttu-id="a1bba-145">下面的示例演示如何指定 Windows 标识流经异步点，即使模拟实现通过非托管方法。</span><span class="sxs-lookup"><span data-stu-id="a1bba-145">The following example shows how to specify that the Windows identity flows across asynchronous points, even when the impersonation is achieved through means other than managed methods.</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <alwaysFlowImpersonationPolicy enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a1bba-146">请参阅</span><span class="sxs-lookup"><span data-stu-id="a1bba-146">See Also</span></span>  
 [<span data-ttu-id="a1bba-147">运行时设置架构</span><span class="sxs-lookup"><span data-stu-id="a1bba-147">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="a1bba-148">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="a1bba-148">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="a1bba-149">\<legacyImpersonationPolicy > 元素</span><span class="sxs-lookup"><span data-stu-id="a1bba-149">\<legacyImpersonationPolicy> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/legacyimpersonationpolicy-element.md)
