---
title: '&lt;appDomainManagerAssembly&gt;元素'
ms.date: 03/30/2017
helpviewer_keywords:
- <appDomainManagerAssembly> element
- appDomainManagerAssembly element
ms.assetid: c7c56e39-a700-44f5-b94e-411bfce339d9
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7656f4819e8ed6d8c1c87eabcbd5862929d47cdc
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="ltappdomainmanagerassemblygt-element"></a>&lt;appDomainManagerAssembly&gt;元素
指定为过程中的默认应用程序域提供应用程序域管理器的程序集。  
  
 \<configuration>  
\<运行时 >  
\<appDomainManagerAssembly >  
  
## <a name="syntax"></a>语法  
  
```xml  
<appDomainManagerAssembly   
   value="assembly display name" />  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|`value`|必需的特性。 指定用于在过程中的默认应用程序域提供应用程序域管理器的程序集的显示名称。|  
  
### <a name="child-elements"></a>子元素  
 无。  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|`configuration`|公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。|  
|`runtime`|包含有关程序集绑定和垃圾回收的信息。|  
  
## <a name="remarks"></a>备注  
 若要指定应用程序域管理器的类型，你必须同时指定此元素与[ \<p e >](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagertype-element.md)元素。 如果未指定任一这些元素，另一个被忽略。  
  
 加载默认应用程序域后，<xref:System.TypeLoadException>如果指定的程序集中不存在，或者如果程序集不包含由指定的类型将引发[ \<p e >](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagertype-element.md)元素; 和进程无法启动。 如果找到的程序集但不是匹配的版本信息，<xref:System.IO.FileLoadException>引发。  
  
 当指定默认应用程序域的应用程序域管理器类型时，从默认应用程序域创建其他应用程序域继承的应用程序域管理器类型。 使用<xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType>和<xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType>属性以指定新的应用程序域不同的应用程序域管理器类型。  
  
 指定的应用程序域管理器类型要求应用程序具有完全信任。 （例如，在桌面上运行的应用程序具有完全信任。）如果应用程序不具有完全信任，<xref:System.TypeLoadException>引发。  
  
 有关程序集显示名称的格式，请参阅<xref:System.Reflection.Assembly.FullName%2A?displayProperty=nameWithType>属性。  
  
 此配置元素可仅用于[!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)]及更高版本。  
  
## <a name="example"></a>示例  
 下面的示例演示如何指定进程的默认应用程序域的应用程序域管理器是`MyMgr`键入`AdMgrExample`程序集。  
  
```xml  
<configuration>  
   <runtime>  
      <appDomainManagerType value="MyMgr" />  
      <appDomainManagerAssembly   
         value="AdMgrExample, Version=1.0.0.0, Culture=neutral, PublicKeyToken=6856bccf150f00b3" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>请参阅  
 <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType>  
 <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType>  
 [\<p e > 元素](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagertype-element.md)  
 [运行时设置架构](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [配置文件架构](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [SetAppDomainManagerType 方法](../../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-setappdomainmanagertype-method.md)
