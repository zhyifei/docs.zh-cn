---
title: "&lt;alwaysFlowImpersonationPolicy&gt;元素"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/alwaysFlowImpersonationPolicy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#alwaysFlowImpersonationPolicy
helpviewer_keywords:
- alwaysFlowImpersonationPolicy element
- <alwaysFlowImpersonationPolicy> element
ms.assetid: ee622801-9e46-470b-85ab-88c4b1dd2ee1
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 52cdb26f6f78ed740efa1f27958368e8c7e2ae78
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="ltalwaysflowimpersonationpolicygt-element"></a>&lt;alwaysFlowImpersonationPolicy&gt;元素
指定 Windows 标识始终流经异步点，而不考虑执行模拟的方式。  
  
 \<configuration>  
\<运行时 >  
\<alwaysFlowImpersonationPolicy >  
  
## <a name="syntax"></a>语法  
  
```xml  
<alwaysFlowImpersonationPolicy    
  enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|`enabled`|必需的特性。<br /><br /> 指示是否的 Windows 标识流经异步点。|  
  
## <a name="enabled-attribute"></a>enabled 特性  
  
|值|描述|  
|-----------|-----------------|  
|`false`|标识不流经异步点，除非通过执行模拟的 Windows 托管方法，如<xref:System.Security.Principal.WindowsIdentity.Impersonate%2A>。 这是默认设置。|  
|`true`|Windows 标识始终流经异步点，而不考虑如何执行模拟。|  
  
### <a name="child-elements"></a>子元素  
 无。  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|`configuration`|公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。|  
|`runtime`|包含有关程序集绑定和垃圾回收的信息。|  
  
## <a name="remarks"></a>备注  
 在.NET framework 1.0 和 1.1 版中，Windows 标识不会各异步点之间流动。 在.NET Framework 2.0 版中，没有<xref:System.Threading.ExecutionContext>包含有关当前正在执行的线程的信息并流经应用程序域中的异步点对象。 <xref:System.Security.Principal.WindowsIdentity>还作为流经异步的点，模拟已实现使用提供的信息的一部分的流托管方法如<xref:System.Security.Principal.WindowsIdentity.Impersonate%2A>并不是通过其他方式如平台调用到本机方法。 此元素用于指定 Windows 标识未流经异步点，而不考虑模拟已通过得以实现。  
  
 你可以更改此默认行为，另外两种：  
  
1.  中基于每个线程的托管代码。  
  
     你可以修改来取消显示的每个线程基础上的流<xref:System.Threading.ExecutionContext>和<xref:System.Security.SecurityContext>设置通过使用<xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType>， <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType>，或<xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType>方法。  
  
2.  在加载公共语言运行时 (CLR) 的非托管承载接口的调用。  
  
     如果使用非托管承载接口 （而不是一个简单托管可执行文件） 用于加载 CLR，则可以对的调用中指定的特殊标志[CorBindToRuntimeEx 函数](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)函数。 若要启用的整个过程的兼容性模式，设置`flags`参数[CorBindToRuntimeEx 函数](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)到`STARTUP_ALWAYSFLOW_IMPERSONATION`。  
  
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
 下面的示例演示如何指定 Windows 标识流经异步点，即使模拟实现通过非托管方法。  
  
```xml  
<configuration>  
  <runtime>  
    <alwaysFlowImpersonationPolicy enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>另请参阅  
 [运行时设置架构](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [配置文件架构](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [\<legacyImpersonationPolicy > 元素](../../../../../docs/framework/configure-apps/file-schema/runtime/legacyimpersonationpolicy-element.md)
