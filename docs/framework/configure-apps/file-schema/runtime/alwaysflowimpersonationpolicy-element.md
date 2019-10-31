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
ms.openlocfilehash: 06e91ea6989dcdf0b2a179e7d6ce79b8d9aaff03
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73118342"
---
# <a name="alwaysflowimpersonationpolicy-element"></a>\<alwaysFlowImpersonationPolicy > 元素
指定 Windows 标识始终流经异步点，而不考虑执行模拟的方式。  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp; &nbsp;[ **\<runtime >** ](runtime-element.md) \
&nbsp;&nbsp;&nbsp;&nbsp; **\<alwaysFlowImpersonationPolicy >** \  
  
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
|`enabled`|必需的特性。<br /><br /> 指示 Windows 标识是否流经异步点。|  
  
## <a name="enabled-attribute"></a>enabled 特性  
  
|“值”|描述|  
|-----------|-----------------|  
|`false`|Windows 标识不流经异步点，除非模拟是通过托管方法（如 <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A>）执行的。 这是默认设置。|  
|`true`|无论模拟的执行方式如何，Windows 标识始终流经异步点。|  
  
### <a name="child-elements"></a>子元素  
 无。  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|`configuration`|公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。|  
|`runtime`|包含有关程序集绑定和垃圾回收的信息。|  
  
## <a name="remarks"></a>备注  
 在 .NET Framework 版本1.0 和1.1 中，Windows 标识不流经异步点。 在 .NET Framework 版本2.0 中，有一个 <xref:System.Threading.ExecutionContext> 对象，其中包含当前正在执行的线程的相关信息，并在应用程序域中的异步点之间流动。 <xref:System.Security.Principal.WindowsIdentity> 还将作为流过异步点的信息的一部分进行传递，前提是通过使用托管方法（如 <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A>）实现模拟，而不是通过其他方式（例如，平台调用到本机方法）实现的。 此元素用于指定无论如何实现模拟，Windows 标识都将流经异步点。  
  
 可以通过两种其他方式更改此默认行为：  
  
1. 在托管代码中，在每个线程的基础上。  
  
     您可以通过使用 <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType>、<xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType>或 <xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType> 方法修改 <xref:System.Threading.ExecutionContext> 和 <xref:System.Security.SecurityContext> 设置来禁用每个线程的流。  
  
2. 在调用非托管承载接口以加载公共语言运行时（CLR）。  
  
     如果使用非托管宿主接口（而不是简单的托管可执行文件）加载 CLR，则可以在调用[CorBindToRuntimeEx 函数](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md)函数时指定特殊标志。 若要为整个进程启用兼容模式，请将[CorBindToRuntimeEx 函数](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md)的 `flags` 参数设置为 `STARTUP_ALWAYSFLOW_IMPERSONATION`。  
  
## <a name="configuration-file"></a>配置文件  
 在 .NET Framework 应用程序中，此元素只能在应用程序配置文件中使用。  
  
 对于 ASP.NET 应用程序，可以在 \<Windows 文件夹 > \Microsoft.NET\Framework\vx.x.xxxx 目录中找到的 aspnet .config 文件中配置模拟流。  
  
 默认情况下，ASP.NET 使用以下配置设置禁用 aspnet 文件中的模拟流：  
  
```xml
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="true"/>  
      <alwaysFlowImpersonationPolicy enabled="false"/>  
   </runtime>  
</configuration>  
```  
  
 在 ASP.NET 中，如果要改为允许模拟流，则必须显式使用以下配置设置：  
  
```xml  
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="false"/>  
      <alwaysFlowImpersonationPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="example"></a>示例  
 下面的示例演示如何指定 Windows 标识流经异步点，即使通过非托管方法实现模拟也是如此。  
  
```xml  
<configuration>  
  <runtime>  
    <alwaysFlowImpersonationPolicy enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>请参阅

- [运行时设置架构](index.md)
- [配置文件架构](../index.md)
- [\<legacyImpersonationPolicy > 元素](legacyimpersonationpolicy-element.md)
