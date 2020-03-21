---
title: <appDomainManagerAssembly> 元素
ms.date: 03/30/2017
helpviewer_keywords:
- <appDomainManagerAssembly> element
- appDomainManagerAssembly element
ms.assetid: c7c56e39-a700-44f5-b94e-411bfce339d9
ms.openlocfilehash: 4c4ea35bff17a0e5188f26884e93cf77173a7df8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154416"
---
# <a name="appdomainmanagerassembly-element"></a>\<应用程序域管理器程序集>元素
指定为过程中的默认应用程序域提供应用程序域管理器的程序集。  
  
[**\<配置>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<运行时>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<应用程序域管理器组装>**  
  
## <a name="syntax"></a>语法  
  
```xml  
<appDomainManagerAssembly
   value="assembly display name" />  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>属性  
  
|Attribute|说明|  
|---------------|-----------------|  
|`value`|必需的特性。 指定在此过程中为默认应用程序域提供应用程序域管理器的程序集的显示名称。|  
  
### <a name="child-elements"></a>子元素  
 无。  
  
### <a name="parent-elements"></a>父元素  
  
|元素|说明|  
|-------------|-----------------|  
|`configuration`|公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。|  
|`runtime`|包含有关程序集绑定和垃圾回收的信息。|  
  
## <a name="remarks"></a>备注  
 要指定应用程序域管理器的类型，必须同时指定此元素和[\<appDomainManagerType>](appdomainmanagertype-element.md)元素。 如果未指定其中任一元素，则忽略另一个元素。  
  
 加载默认应用程序域时，<xref:System.TypeLoadException>如果指定的程序集不存在，或者程序集不包含[\<appDomainManagerType 指定的类型>](appdomainmanagertype-element.md)元素，则引发该程序集;进程无法启动。 如果找到程序集但版本信息不匹配，则引发 。 <xref:System.IO.FileLoadException>  
  
 当您为默认应用程序域指定应用程序域管理器类型时，从默认应用程序域创建的其他应用程序域将继承应用程序域管理器类型。 使用<xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType>和<xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType>属性为新的应用程序域指定不同的应用程序域管理器类型。  
  
 指定应用程序域管理器类型需要应用程序具有完全信任。 （例如，在桌面上运行的应用程序具有完全信任。如果应用程序没有完全信任，则引发 。 <xref:System.TypeLoadException>  
  
 有关程序集显示名称的格式，请参阅 属性<xref:System.Reflection.Assembly.FullName%2A?displayProperty=nameWithType>。  
  
 此配置元素仅在 .NET 框架 4 和更高版本中可用。  
  
## <a name="example"></a>示例  
 下面的示例演示如何指定进程默认应用程序域的应用程序域管理器是程序集中`MyMgr``AdMgrExample`的类型。  
  
```xml  
<configuration>  
   <runtime>  
      <appDomainManagerType value="MyMgr" />  
      <appDomainManagerAssembly
         value="AdMgrExample, Version=1.0.0.0, Culture=neutral, PublicKeyToken=6856bccf150f00b3" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>另请参阅

- <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType>
- <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType>
- [\<应用域管理器类型>元素](appdomainmanagertype-element.md)
- [运行时设置架构](index.md)
- [配置文件架构](../index.md)
- [SetAppDomainManagerType 方法](../../../unmanaged-api/hosting/iclrcontrol-setappdomainmanagertype-method.md)
