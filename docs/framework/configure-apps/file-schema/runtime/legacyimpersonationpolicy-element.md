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
# <a name="ltlegacyimpersonationpolicygt-element"></a>&lt;legacyImpersonationPolicy&gt;元素
指定 Windows 标识不流经异步点，而不考虑当前线程上执行上下文的流设置。  
  
 \<configuration>  
\<运行时 >  
\<legacyImpersonationPolicy >  
  
## <a name="syntax"></a>语法  
  
```xml  
<legacyImpersonationPolicy    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|`enabled`|必需的特性。<br /><br /> 指定<xref:System.Security.Principal.WindowsIdentity>不流经异步点，而不考虑<xref:System.Threading.ExecutionContext>流当前线程上的设置。|  
  
## <a name="enabled-attribute"></a>enabled 特性  
  
|值|描述|  
|-----------|-----------------|  
|`false`|<xref:System.Security.Principal.WindowsIdentity>流经异步点，具体取决于<xref:System.Threading.ExecutionContext>流设置确定是否当前的线程。 这是默认设置。|  
|`true`|<xref:System.Security.Principal.WindowsIdentity>不流经异步点，而不考虑<xref:System.Threading.ExecutionContext>流当前线程上的设置。|  
  
### <a name="child-elements"></a>子元素  
 无。  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|`configuration`|公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。|  
|`runtime`|包含有关程序集绑定和垃圾回收的信息。|  
  
## <a name="remarks"></a>备注  
 在.NET framework 1.0 和 1.1 中，<xref:System.Security.Principal.WindowsIdentity>不流经任何用户定义的异步点。 从.NET Framework 2.0 版开始，没有<xref:System.Threading.ExecutionContext>对象，其中包含有关当前正在执行的线程，并在它的信息流经应用程序域中的异步点。 <xref:System.Security.Principal.WindowsIdentity>包含在此执行上下文中，因此也会流过异步的点，这意味着，如果存在模拟上下文，它会流动。  
  
 从.NET Framework 2.0 开始，你可以使用`<legacyImpersonationPolicy>`元素来指定：<xref:System.Security.Principal.WindowsIdentity>不流经异步点。  
  
> [!NOTE]
>  公共语言运行时 (CLR) 时注意到使用托管的代码，不执行的模拟外部托管代码中，如通过平台执行的操作调用到非托管代码或通过直接调用 Win32 函数的模拟。 仅托管<xref:System.Security.Principal.WindowsIdentity>对象可以流经异步点，除非`alwaysFlowImpersonationPolicy`元素已设置为 true (`<alwaysFlowImpersonationPolicy enabled="true"/>`)。 设置`alwaysFlowImpersonationPolicy`为 true 的元素指定的 Windows 标识始终异步点，而不考虑如何执行模拟间流动。 有关详细信息流动非模拟托管流经异步点，请参阅[ \<alwaysFlowImpersonationPolicy > 元素](../../../../../docs/framework/configure-apps/file-schema/runtime/alwaysflowimpersonationpolicy-element.md)。  
  
 你可以更改此默认行为，另外两种：  
  
1.  中基于每个线程的托管代码。  
  
     你可以修改来取消显示的每个线程基础上的流<xref:System.Threading.ExecutionContext>和<xref:System.Security.SecurityContext>设置通过使用<xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType>，<xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType>或<xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType>方法。  
  
2.  在加载公共语言运行时 (CLR) 的非托管承载接口的调用。  
  
     如果使用非托管承载接口 （而不是一个简单托管可执行文件） 用于加载 CLR，则可以对的调用中指定的特殊标志[CorBindToRuntimeEx 函数](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)函数。 若要启用的整个过程的兼容性模式，设置`flags`参数[CorBindToRuntimeEx 函数](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)到 STARTUP_LEGACY_IMPERSONATION。  
  
 有关详细信息，请参阅[ \<alwaysFlowImpersonationPolicy > 元素](../../../../../docs/framework/configure-apps/file-schema/runtime/alwaysflowimpersonationpolicy-element.md)。  
  
## <a name="configuration-file"></a>配置文件  
 在.NET Framework 应用程序，可以仅在应用程序配置文件中使用此元素。  
  
 在 aspnet.config 文件中可以 ASP.NET 应用程序，配置模拟流\<Windows 文件夹 > \Microsoft.NET\Framework\vx.x.xxxx 目录。  
  
 默认情况下的 ASP.NET 通过使用以下配置设置来禁用下的 aspnet.config 文件中的模拟流：  
  
```  
configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="true"/>  
      <alwaysFlowImpersonationPolicy enabled="false"/>  
   </runtime>  
</configuration>  
```  
  
 在 ASP.NET 中，如果你想要允许的模拟流相反，你必须显式使用以下配置设置：  
  
```xml  
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="false"/>  
      <alwaysFlowImpersonationPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="example"></a>示例  
 下面的示例演示如何指定不会各异步点之间流动的 Windows 标识的旧行为。  
  
```xml  
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>另请参阅  
 [运行时设置架构](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [配置文件架构](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [\<alwaysFlowImpersonationPolicy > 元素](../../../../../docs/framework/configure-apps/file-schema/runtime/alwaysflowimpersonationpolicy-element.md)
