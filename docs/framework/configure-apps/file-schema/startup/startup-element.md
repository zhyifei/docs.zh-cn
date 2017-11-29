---
title: "&lt;启动&gt;元素"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/startup
- http://schemas.microsoft.com/.NetConfiguration/v2.0#startup
helpviewer_keywords:
- container tags, <startup> element
- <startup> element
- startup element
ms.assetid: 536acfd8-f827-452f-838a-e14fa3b87621
caps.latest.revision: "19"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: bd2356845c76e81ce2efe87bdf247de293d6115d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="ltstartupgt-element"></a>&lt;启动&gt;元素
指定公共语言运行时启动信息。  
  
 \<configuration>  
\<启动 >  
  
## <a name="syntax"></a>语法  
  
```xml  
<startup useLegacyV2RuntimeActivationPolicy="true|false" >   
</startup>  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|`useLegacyV2RuntimeActivationPolicy`|可选特性。<br /><br /> 指定是否启用[!INCLUDE[dnprdnext](../../../../../includes/dnprdnext-md.md)]运行时激活策略或使用[!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)]激活策略。|  
  
## <a name="uselegacyv2runtimeactivationpolicy-attribute"></a>useLegacyV2RuntimeActivationPolicy 属性  
  
|值|描述|  
|-----------|-----------------|  
|`true`|启用[!INCLUDE[dnprdnext](../../../../../includes/dnprdnext-md.md)]选运行时，是将绑定旧式运行时激活技术的运行时激活策略 (如[CorBindToRuntimeEx 函数](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)) 为运行时从配置文件而不是选择上限它们设置在 CLR 版本 2.0。 因此，如果从配置文件选择 CLR 版本 4 或更高版本，则使用.NET Framework 的早期版本创建的混合模式程序集是加载与选择的 CLR 版本。 将设置此值可防止 CLR 版本 1.1 或 CLR 版本 2.0 加载到相同的过程中，有效地禁用进程内并行的功能。|  
|`false`|使用的默认激活策略[!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)]和更高版本，即允许旧式运行时加载到进程的 CLR 版本 1.1 或 2.0 的激活方法。 设置此值禁止从加载到.NET Framework 4 或更高版本，除非它们生成.NET Framework 4 或更高版本的混合模式程序集。 此值是默认值。|  
  
### <a name="child-elements"></a>子元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<requiredRuntime>](../../../../../docs/framework/configure-apps/file-schema/startup/requiredruntime-element.md)|指定应用程序仅支持 1.0 版本的公共语言运行时。 运行时 1.1 版或更高版本生成的应用程序应使用 **\<supportedRuntime >**元素。|  
|[\<supportedRuntime>](../../../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md)|指定应用程序支持的公共语言运行时版本。|  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|`configuration`|公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。|  
  
## <a name="remarks"></a>备注  
 **\<SupportedRuntime >**元素应由使用版本 1.1 或更高版本的运行时生成的所有应用程序。 为支持仅运行时 1.0 版而生成的应用程序必须使用 **\<requiredRuntime >**元素。  
  
 在 Microsoft Internet Explorer 中托管的应用程序的启动代码将忽略**\<启动 >**元素及其子元素。  
  
## <a name="the-uselegacyv2runtimeactivationpolicy-attribute"></a>UseLegacyV2RuntimeActivationPolicy 属性  
 此属性是很有用，如果你的应用程序使用旧式激活路径，如[CorBindToRuntimeEx 函数](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)，并且你希望这些路径激活而不是早期版本，CLR 版本 4 或如果你的应用程序使用生成[!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)]但在使用.NET Framework 的早期版本生成的混合模式程序集具有的依赖关系。 在这些情况下，将属性设置为`true`。  
  
> [!NOTE]
>  将属性设置为`true`阻止到相同的过程中，有效地禁用进程内的并行功能加载的 CLR 版本 1.1 或 CLR 版本 2.0 (请参阅[为 COM 互操作的并行执行](http://msdn.microsoft.com/en-us/4302318c-3586-49bf-8620-b9a39cdf4a32))。  
  
## <a name="example"></a>示例  
 下面的示例演示如何在配置文件中指定的运行时版本。  
  
```xml  
<!-- When used with version 1.0 of the .NET Framework runtime -->  
<configuration>  
   <startup>  
      <requiredRuntime version="v1.0.3705" safemode="true"/>  
   </startup>  
</configuration>  
<!-- When used with version 1.1 (or later) of the runtime -->  
<configuration>  
   <startup>  
      <supportedRuntime version="v1.1.4322"/>  
      <supportedRuntime version="v1.0.3705"/>  
   </startup>  
</configuration>  
```  
  
## <a name="see-also"></a>另请参阅  
 [启动设置架构](../../../../../docs/framework/configure-apps/file-schema/startup/index.md)  
 [配置文件架构](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [\<PaveOver> 指定要使用的运行时版本](http://msdn.microsoft.com/en-us/c376208d-980d-42b4-865b-fbe0d9cc97c2)  
 [COM 互操作的的并行执行](http://msdn.microsoft.com/en-us/4302318c-3586-49bf-8620-b9a39cdf4a32)  
 [进程内并行执行](../../../../../docs/framework/deployment/in-process-side-by-side-execution.md)
