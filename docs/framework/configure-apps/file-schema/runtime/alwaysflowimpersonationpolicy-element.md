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
ms.openlocfilehash: 7c8ac37932a528ff0f000cbaab49124dec51b88c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154478"
---
# <a name="alwaysflowimpersonationpolicy-element"></a><span data-ttu-id="5a140-102">\<源流模拟策略>元素</span><span class="sxs-lookup"><span data-stu-id="5a140-102">\<alwaysFlowImpersonationPolicy> Element</span></span>
<span data-ttu-id="5a140-103">指定 Windows 标识始终流经异步点，而不考虑执行模拟的方式。</span><span class="sxs-lookup"><span data-stu-id="5a140-103">Specifies that the Windows identity always flows across asynchronous points, regardless of how impersonation was performed.</span></span>  
  
<span data-ttu-id="5a140-104">[**\<配置>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="5a140-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="5a140-105">&nbsp;&nbsp;[**\<运行时>**](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="5a140-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="5a140-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<始终流模拟策略>**</span><span class="sxs-lookup"><span data-stu-id="5a140-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<alwaysFlowImpersonationPolicy>**</span></span>\  
  
## <a name="syntax"></a><span data-ttu-id="5a140-107">语法</span><span class="sxs-lookup"><span data-stu-id="5a140-107">Syntax</span></span>  
  
```xml  
<alwaysFlowImpersonationPolicy
  enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5a140-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="5a140-108">Attributes and Elements</span></span>  
 <span data-ttu-id="5a140-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="5a140-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5a140-110">属性</span><span class="sxs-lookup"><span data-stu-id="5a140-110">Attributes</span></span>  
  
|<span data-ttu-id="5a140-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="5a140-111">Attribute</span></span>|<span data-ttu-id="5a140-112">说明</span><span class="sxs-lookup"><span data-stu-id="5a140-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="5a140-113">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="5a140-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="5a140-114">指示 Windows 标识是否跨异步点流动。</span><span class="sxs-lookup"><span data-stu-id="5a140-114">Indicates whether the Windows identity flows across asynchronous points.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="5a140-115">enabled 特性</span><span class="sxs-lookup"><span data-stu-id="5a140-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="5a140-116">值</span><span class="sxs-lookup"><span data-stu-id="5a140-116">Value</span></span>|<span data-ttu-id="5a140-117">说明</span><span class="sxs-lookup"><span data-stu-id="5a140-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="5a140-118">Windows 标识不会跨异步点流动，除非通过托管方法（如<xref:System.Security.Principal.WindowsIdentity.Impersonate%2A>） 执行模拟。</span><span class="sxs-lookup"><span data-stu-id="5a140-118">The Windows identity does not flow across asynchronous points, unless the impersonation is performed through managed methods such as <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A>.</span></span> <span data-ttu-id="5a140-119">这是默认值。</span><span class="sxs-lookup"><span data-stu-id="5a140-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="5a140-120">无论模拟执行方式如何，Windows 标识始终跨异步点流动。</span><span class="sxs-lookup"><span data-stu-id="5a140-120">The Windows identity always flows across asynchronous points, regardless of how impersonation was performed.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5a140-121">子元素</span><span class="sxs-lookup"><span data-stu-id="5a140-121">Child Elements</span></span>  
 <span data-ttu-id="5a140-122">无。</span><span class="sxs-lookup"><span data-stu-id="5a140-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5a140-123">父元素</span><span class="sxs-lookup"><span data-stu-id="5a140-123">Parent Elements</span></span>  
  
|<span data-ttu-id="5a140-124">元素</span><span class="sxs-lookup"><span data-stu-id="5a140-124">Element</span></span>|<span data-ttu-id="5a140-125">说明</span><span class="sxs-lookup"><span data-stu-id="5a140-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="5a140-126">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="5a140-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="5a140-127">包含有关程序集绑定和垃圾回收的信息。</span><span class="sxs-lookup"><span data-stu-id="5a140-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5a140-128">备注</span><span class="sxs-lookup"><span data-stu-id="5a140-128">Remarks</span></span>  
 <span data-ttu-id="5a140-129">在 .NET 框架版本 1.0 和 1.1 中，Windows 标识不会跨异步点流动。</span><span class="sxs-lookup"><span data-stu-id="5a140-129">In the .NET Framework versions 1.0 and 1.1, the Windows identity does not flow across asynchronous points.</span></span> <span data-ttu-id="5a140-130">在 .NET Framework 版本 2.0<xref:System.Threading.ExecutionContext>中，有一个对象包含有关当前正在执行的线程的信息，并跨应用程序域中的异步点进行流。</span><span class="sxs-lookup"><span data-stu-id="5a140-130">In the .NET Framework version 2.0, there is an <xref:System.Threading.ExecutionContext> object that contains information about the currently executing thread, and flows it across asynchronous points within an application domain.</span></span> <span data-ttu-id="5a140-131">如果<xref:System.Security.Principal.WindowsIdentity>模拟是使用托管方法（如，<xref:System.Security.Principal.WindowsIdentity.Impersonate%2A>而不是通过其他方法（如平台调用本机方法）实现的，则该函数也会作为流经异步点的信息的一部分进行流动。</span><span class="sxs-lookup"><span data-stu-id="5a140-131">The <xref:System.Security.Principal.WindowsIdentity> also flows as part of the information that flows across the asynchronous points, provided the impersonation was achieved using managed methods such as <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A> and not through other means such as platform invoke to native methods.</span></span> <span data-ttu-id="5a140-132">此元素用于指定 Windows 标识确实跨异步点流动，而不考虑模拟是如何实现的。</span><span class="sxs-lookup"><span data-stu-id="5a140-132">This element is used to specify that the Windows identity does flow across asynchronous points, regardless of how the impersonation was achieved.</span></span>  
  
 <span data-ttu-id="5a140-133">您可以通过两种其他方式更改此默认行为：</span><span class="sxs-lookup"><span data-stu-id="5a140-133">You can alter this default behavior in two other ways:</span></span>  
  
1. <span data-ttu-id="5a140-134">在基于每个线程的托管代码中。</span><span class="sxs-lookup"><span data-stu-id="5a140-134">In managed code on a per-thread basis.</span></span>  
  
     <span data-ttu-id="5a140-135"><xref:System.Threading.ExecutionContext>通过使用 、 或<xref:System.Security.SecurityContext><xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType><xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType><xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType>方法修改 和 设置，可以按线程禁止流。</span><span class="sxs-lookup"><span data-stu-id="5a140-135">You can suppress the flow on a per-thread basis by modifying the <xref:System.Threading.ExecutionContext> and <xref:System.Security.SecurityContext> settings by using the <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType>, <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType>, or <xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType> method.</span></span>  
  
2. <span data-ttu-id="5a140-136">在调用非托管主机接口以加载通用语言运行时 （CLR）。</span><span class="sxs-lookup"><span data-stu-id="5a140-136">In the call to the unmanaged hosting interface to load the common language runtime (CLR).</span></span>  
  
     <span data-ttu-id="5a140-137">如果使用非托管托管接口（而不是简单的托管可执行文件）来加载 CLR，则可以在[CorBindToRuntimeEx 函数](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md)的调用中指定一个特殊的标志。</span><span class="sxs-lookup"><span data-stu-id="5a140-137">If an unmanaged hosting interface (instead of a simple managed executable) is used to load the CLR, you can specify a special flag in the call to the [CorBindToRuntimeEx Function](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) function.</span></span> <span data-ttu-id="5a140-138">要为整个过程启用兼容性模式，将`flags`[CorBindToRuntimeEx 函数](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md)的参数设置为`STARTUP_ALWAYSFLOW_IMPERSONATION`。</span><span class="sxs-lookup"><span data-stu-id="5a140-138">To enable the compatibility mode for the entire process, set the `flags` parameter for [CorBindToRuntimeEx Function](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) to `STARTUP_ALWAYSFLOW_IMPERSONATION`.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="5a140-139">配置文件</span><span class="sxs-lookup"><span data-stu-id="5a140-139">Configuration File</span></span>  
 <span data-ttu-id="5a140-140">在 .NET 框架应用程序中，此元素只能在应用程序配置文件中使用。</span><span class="sxs-lookup"><span data-stu-id="5a140-140">In a .NET Framework application, this element can be used only in the application configuration file.</span></span>  
  
 <span data-ttu-id="5a140-141">对于ASP.NET应用程序，可以在\<Windows 文件夹>_Microsoft.NET_Framework_vx.x.xxx 目录中的 aspnet.config 文件中配置模拟流。</span><span class="sxs-lookup"><span data-stu-id="5a140-141">For an ASP.NET application, the impersonation flow can be configured in the aspnet.config file found in the \<Windows Folder>\Microsoft.NET\Framework\vx.x.xxxx directory.</span></span>  
  
 <span data-ttu-id="5a140-142">默认情况下ASP.NET使用以下配置设置禁用 aspnet.config 文件中的模拟流：</span><span class="sxs-lookup"><span data-stu-id="5a140-142">ASP.NET by default disables the impersonation flow in the aspnet.config file by using the following configuration settings:</span></span>  
  
```xml
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="true"/>  
      <alwaysFlowImpersonationPolicy enabled="false"/>  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="5a140-143">在ASP.NET中，如果要改为允许模拟流，则必须显式使用以下配置设置：</span><span class="sxs-lookup"><span data-stu-id="5a140-143">In ASP.NET, if you want to allow the flow of impersonation instead, you must explicitly use the following configuration settings:</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="false"/>  
      <alwaysFlowImpersonationPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="example"></a><span data-ttu-id="5a140-144">示例</span><span class="sxs-lookup"><span data-stu-id="5a140-144">Example</span></span>  
 <span data-ttu-id="5a140-145">下面的示例演示如何指定 Windows 标识跨异步点流动，即使模拟是通过托管方法以外的方法实现的。</span><span class="sxs-lookup"><span data-stu-id="5a140-145">The following example shows how to specify that the Windows identity flows across asynchronous points, even when the impersonation is achieved through means other than managed methods.</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <alwaysFlowImpersonationPolicy enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="5a140-146">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5a140-146">See also</span></span>

- [<span data-ttu-id="5a140-147">运行时设置架构</span><span class="sxs-lookup"><span data-stu-id="5a140-147">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="5a140-148">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="5a140-148">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="5a140-149">\<传统模拟策略>元素</span><span class="sxs-lookup"><span data-stu-id="5a140-149">\<legacyImpersonationPolicy> Element</span></span>](legacyimpersonationpolicy-element.md)
