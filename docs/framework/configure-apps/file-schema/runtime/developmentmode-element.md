---
title: <developmentMode> 元素
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
ms.openlocfilehash: d7c7f866cdbcd39194d61a3db821bf973b4e057e
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/21/2019
ms.locfileid: "69663806"
---
# <a name="developmentmode-element"></a>\<developmentMode > 元素
指定运行时是否搜索由 DEVPATH 环境变量指定的目录中的程序集。  
  
 \<configuration>  
\<运行时 >  
\<developmentMode>  
  
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
  
## <a name="developerinstallation-attribute"></a>developerInstallation 特性  
  
|值|描述|  
|-----------|-----------------|  
|**true**|在由 DEVPATH 环境变量指定的目录中搜索程序集。|  
|**false**|不搜索由 DEVPATH 环境变量指定的目录中的程序集。 这是默认值|  
  
### <a name="child-elements"></a>子元素  
 无。  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|`configuration`|公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。|  
|`runtime`|包含有关程序集绑定和垃圾回收的信息。|  
  
## <a name="remarks"></a>备注  
 仅在开发时使用此设置。 运行时不检查在 DEVPATH 中找到的具有强名称的程序集的版本。 它只使用它找到的第一个程序集。  
  
## <a name="example"></a>示例  
 下面的示例演示如何使运行时在由 DEVPATH 环境变量指定的目录中搜索程序集。  
  
```xml  
<configuration>  
   <runtime>  
      <developmentMode developerInstallation="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>请参阅

- [运行时设置架构](index.md)
- [配置文件架构](../index.md)
- [如何：使用 DEVPATH 查找程序集](../../how-to-locate-assemblies-by-using-devpath.md)
