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
# <a name="alwaysflowimpersonationpolicy-element"></a>\<源流模拟策略>元素
指定 Windows 标识始终流经异步点，而不考虑执行模拟的方式。  
  
[**\<配置>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<运行时>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<始终流模拟策略>**\  
  
## <a name="syntax"></a>语法  
  
```xml  
<alwaysFlowImpersonationPolicy
  enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>属性  
  
|Attribute|说明|  
|---------------|-----------------|  
|`enabled`|必需的特性。<br /><br /> 指示 Windows 标识是否跨异步点流动。|  
  
## <a name="enabled-attribute"></a>enabled 特性  
  
|值|说明|  
|-----------|-----------------|  
|`false`|Windows 标识不会跨异步点流动，除非通过托管方法（如<xref:System.Security.Principal.WindowsIdentity.Impersonate%2A>） 执行模拟。 这是默认值。|  
|`true`|无论模拟执行方式如何，Windows 标识始终跨异步点流动。|  
  
### <a name="child-elements"></a>子元素  
 无。  
  
### <a name="parent-elements"></a>父元素  
  
|元素|说明|  
|-------------|-----------------|  
|`configuration`|公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。|  
|`runtime`|包含有关程序集绑定和垃圾回收的信息。|  
  
## <a name="remarks"></a>备注  
 在 .NET 框架版本 1.0 和 1.1 中，Windows 标识不会跨异步点流动。 在 .NET Framework 版本 2.0<xref:System.Threading.ExecutionContext>中，有一个对象包含有关当前正在执行的线程的信息，并跨应用程序域中的异步点进行流。 如果<xref:System.Security.Principal.WindowsIdentity>模拟是使用托管方法（如，<xref:System.Security.Principal.WindowsIdentity.Impersonate%2A>而不是通过其他方法（如平台调用本机方法）实现的，则该函数也会作为流经异步点的信息的一部分进行流动。 此元素用于指定 Windows 标识确实跨异步点流动，而不考虑模拟是如何实现的。  
  
 您可以通过两种其他方式更改此默认行为：  
  
1. 在基于每个线程的托管代码中。  
  
     <xref:System.Threading.ExecutionContext>通过使用 、 或<xref:System.Security.SecurityContext><xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType><xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType><xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType>方法修改 和 设置，可以按线程禁止流。  
  
2. 在调用非托管主机接口以加载通用语言运行时 （CLR）。  
  
     如果使用非托管托管接口（而不是简单的托管可执行文件）来加载 CLR，则可以在[CorBindToRuntimeEx 函数](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md)的调用中指定一个特殊的标志。 要为整个过程启用兼容性模式，将`flags`[CorBindToRuntimeEx 函数](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md)的参数设置为`STARTUP_ALWAYSFLOW_IMPERSONATION`。  
  
## <a name="configuration-file"></a>配置文件  
 在 .NET 框架应用程序中，此元素只能在应用程序配置文件中使用。  
  
 对于ASP.NET应用程序，可以在\<Windows 文件夹>_Microsoft.NET_Framework_vx.x.xxx 目录中的 aspnet.config 文件中配置模拟流。  
  
 默认情况下ASP.NET使用以下配置设置禁用 aspnet.config 文件中的模拟流：  
  
```xml
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="true"/>  
      <alwaysFlowImpersonationPolicy enabled="false"/>  
   </runtime>  
</configuration>  
```  
  
 在ASP.NET中，如果要改为允许模拟流，则必须显式使用以下配置设置：  
  
```xml  
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="false"/>  
      <alwaysFlowImpersonationPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="example"></a>示例  
 下面的示例演示如何指定 Windows 标识跨异步点流动，即使模拟是通过托管方法以外的方法实现的。  
  
```xml  
<configuration>  
  <runtime>  
    <alwaysFlowImpersonationPolicy enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>另请参阅

- [运行时设置架构](index.md)
- [配置文件架构](../index.md)
- [\<传统模拟策略>元素](legacyimpersonationpolicy-element.md)
