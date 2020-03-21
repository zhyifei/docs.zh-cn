---
title: <appDomainManagerType> 元素
ms.date: 03/30/2017
helpviewer_keywords:
- appDomainManagerType element
- <appDomainManagerType> element
ms.assetid: ae8d5a7e-e7f7-47f7-98d9-455cc243a322
ms.openlocfilehash: 8eb6129b3fafaeb81a94d5a4078e41a16583a226
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154417"
---
# <a name="appdomainmanagertype-element"></a>\<应用域管理器类型>元素
指定用作默认应用程序域的应用程序域管理器的类型。  
  
[**\<配置>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<运行时>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<应用域管理器类型>**  
  
## <a name="syntax"></a>语法  
  
```xml  
<appDomainManagerAssembly
   value="type name" />  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>属性  
  
|Attribute|说明|  
|---------------|-----------------|  
|`value`|必需的特性。 指定作为进程中默认应用程序域的应用程序域管理器的类型的名称（包括命名空间）。|  
  
### <a name="child-elements"></a>子元素  
 无。  
  
### <a name="parent-elements"></a>父元素  
  
|元素|说明|  
|-------------|-----------------|  
|`configuration`|公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。|  
|`runtime`|包含有关程序集绑定和垃圾回收的信息。|  
  
## <a name="remarks"></a>备注  
 要指定应用程序域管理器的类型，必须同时指定此元素和[\<appDomainManagerAssembly>](appdomainmanagerassembly-element.md)元素。 如果未指定其中任一元素，则忽略另一个元素。  
  
 加载默认应用程序域时，<xref:System.TypeLoadException>如果[\<应用域管理器组件>](appdomainmanagerassembly-element.md)元素指定的程序集中不存在指定的类型，则引发该类型;进程无法启动。  
  
 当您为默认应用程序域指定应用程序域管理器类型时，从默认应用程序域创建的其他应用程序域将继承应用程序域管理器类型。 使用<xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType>和<xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType>属性为新的应用程序域指定不同的应用程序域管理器类型。  
  
 指定应用程序域管理器类型需要应用程序具有完全信任。 （例如，在桌面上运行的应用程序具有完全信任。如果应用程序没有完全信任，则引发 。 <xref:System.TypeLoadException>  
  
 类型和命名空间的格式与用于属性的<xref:System.Type.FullName%2A?displayProperty=nameWithType>格式相同。  
  
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
- [\<应用程序域管理器程序集>元素](appdomainmanagerassembly-element.md)
- [运行时设置架构](index.md)
- [配置文件架构](../index.md)
- [SetAppDomainManagerType 方法](../../../unmanaged-api/hosting/iclrcontrol-setappdomainmanagertype-method.md)
