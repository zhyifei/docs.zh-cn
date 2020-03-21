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
ms.openlocfilehash: 5e43ead278ecd4049014f4000a2f056b2190f7e5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154099"
---
# <a name="legacyimpersonationpolicy-element"></a>\<传统模拟策略>元素
指定 Windows 标识不流经异步点，而不考虑当前线程上执行上下文的流设置。  
  
[**\<配置>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<运行时>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<传统模拟策略>**  
  
## <a name="syntax"></a>语法  
  
```xml  
<legacyImpersonationPolicy
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>属性  
  
|Attribute|说明|  
|---------------|-----------------|  
|`enabled`|必需的特性。<br /><br /> 指定<xref:System.Security.Principal.WindowsIdentity>不跨异步点流动，而不考虑当前线程上的<xref:System.Threading.ExecutionContext>流设置。|  
  
## <a name="enabled-attribute"></a>enabled 特性  
  
|值|说明|  
|-----------|-----------------|  
|`false`|<xref:System.Security.Principal.WindowsIdentity>流经异步点，<xref:System.Threading.ExecutionContext>具体取决于当前线程的流设置。 这是默认值。|  
|`true`|<xref:System.Security.Principal.WindowsIdentity>无论当前线程上的<xref:System.Threading.ExecutionContext>流设置如何，都不会在异步点之间流动。|  
  
### <a name="child-elements"></a>子元素  
 无。  
  
### <a name="parent-elements"></a>父元素  
  
|元素|说明|  
|-------------|-----------------|  
|`configuration`|公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。|  
|`runtime`|包含有关程序集绑定和垃圾回收的信息。|  
  
## <a name="remarks"></a>备注  
 在 .NET 框架版本 1.0 和 1.1 中，<xref:System.Security.Principal.WindowsIdentity>不会流过任何用户定义的异步点。 从 .NET Framework 版本 2.0 开始<xref:System.Threading.ExecutionContext>，有一个对象包含有关当前正在执行的线程的信息，并且它跨应用程序域中的异步点流动。 <xref:System.Security.Principal.WindowsIdentity>包含在此执行上下文中，因此也会跨异步点流动，这意味着如果存在模拟上下文，它也会流动。  
  
 从 .NET 框架 2.0 开始，可以使用`<legacyImpersonationPolicy>`元素指定<xref:System.Security.Principal.WindowsIdentity>不跨异步点流动的元素。  
  
> [!NOTE]
> 通用语言运行时 （CLR） 知道仅使用托管代码执行的模拟操作，而不是在托管代码之外执行的模拟操作，例如通过平台调用非托管代码或直接调用 Win32 函数。 只有托管<xref:System.Security.Principal.WindowsIdentity>对象才能跨异步点流动，除非`alwaysFlowImpersonationPolicy`元素已设置为 true （`<alwaysFlowImpersonationPolicy enabled="true"/>`。 将`alwaysFlowImpersonationPolicy`元素设置为 true 指定 Windows 标识始终跨异步点流动，而不考虑模拟的执行方式。 有关跨异步点的流式非托管模拟的详细信息，请参阅[\<始终 FlowImpersonation 策略>元素](alwaysflowimpersonationpolicy-element.md)。  
  
 您可以通过两种其他方式更改此默认行为：  
  
1. 在基于每个线程的托管代码中。  
  
     通过使用<xref:System.Threading.ExecutionContext>修改 和<xref:System.Security.SecurityContext>设置<xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType><xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType>，可以使用 或<xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType>方法，从而在每个线程的基础上禁止流。  
  
2. 在调用非托管主机接口以加载通用语言运行时 （CLR）。  
  
     如果使用非托管托管接口（而不是简单的托管可执行文件）来加载 CLR，则可以在[CorBindToRuntimeEx 函数](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md)的调用中指定一个特殊的标志。 要为整个过程启用兼容性模式，将`flags` [CorBindToRuntimeEx 函数](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md)的参数设置为STARTUP_LEGACY_IMPERSONATION。  
  
 有关详细信息，请参阅[\<始终 FlowImpersonaton 策略>元素](alwaysflowimpersonationpolicy-element.md)。  
  
## <a name="configuration-file"></a>配置文件  
 在 .NET 框架应用程序中，此元素只能在应用程序配置文件中使用。  
  
 对于ASP.NET应用程序，可以在\<Windows 文件夹>_Microsoft.NET_Framework_vx.x.xxx 目录中的 aspnet.config 文件中配置模拟流。  
  
 默认情况下ASP.NET使用以下配置设置禁用 aspnet.config 文件中的模拟流：  
  
``` xml
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
 下面的示例演示如何指定不跨异步点流式到 Windows 标识的旧行为。  
  
```xml  
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>另请参阅

- [运行时设置架构](index.md)
- [配置文件架构](../index.md)
- [\<源流模拟策略>元素](alwaysflowimpersonationpolicy-element.md)
