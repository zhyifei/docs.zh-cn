---
title: '&lt;developmentMode&gt;元素'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/developmentMode
- http://schemas.microsoft.com/.NetConfiguration/v2.0#developmentMode
helpviewer_keywords:
- developmentMode element
- container tags, <developmentMode> element
- <developmentMode> element
ms.assetid: 60e79a8c-415a-497d-be29-b9d0fd9bdee3
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 71b4eb1dfb50774cea2f7a50d5e5350b0338f41e
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="ltdevelopmentmodegt-element"></a>&lt;developmentMode&gt;元素
指定运行时是否搜索由 DEVPATH 环境变量指定的目录中的程序集。  
  
 \<configuration>  
\<运行时 >  
\<developmentMode >  
  
## <a name="syntax"></a>语法  
  
```xml  
<developmentMode developerInstallation="true | false"/>  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|**developerInstallation**|指定运行时是否搜索由 DEVPATH 环境变量指定的目录中的程序集。|  
  
## <a name="developerinstallation-attribute"></a>developerInstallation 属性  
  
|值|描述|  
|-----------|-----------------|  
|**true**|搜索由 DEVPATH 环境变量指定的目录中的程序集。|  
|**false**|不会搜索 DEVPATH 环境变量指定的目录中的程序集。 这是默认值|  
  
### <a name="child-elements"></a>子元素  
 无。  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|`configuration`|公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。|  
|`runtime`|包含有关程序集绑定和垃圾回收的信息。|  
  
## <a name="remarks"></a>备注  
 仅在开发期间使用此设置。 运行时不会检查上 DEVPATH 中找到的具有强名称的程序集的版本。 它只需使用它找到的第一个程序集。  
  
## <a name="example"></a>示例  
 下面的示例演示如何使运行时搜索 DEVPATH 环境变量指定的目录中的程序集。  
  
```xml  
<configuration>  
   <runtime>  
      <developmentMode developerInstallation="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>请参阅  
 [运行时设置架构](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [配置文件架构](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [如何：使用 DEVPATH 查找程序集](../../../../../docs/framework/configure-apps/how-to-locate-assemblies-by-using-devpath.md)
