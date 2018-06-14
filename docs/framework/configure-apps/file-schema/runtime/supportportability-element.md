---
title: '&lt;supportPortability&gt;元素'
ms.date: 03/30/2017
helpviewer_keywords:
- supportPortability element
- <supportPortability> element
ms.assetid: 6453ef66-19b4-41f3-b712-52d0c2abc9ca
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0a8a454919a195a0f0c03ed6890e51b2723f64fb
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
ms.locfileid: "32754101"
---
# <a name="ltsupportportabilitygt-element"></a>&lt;supportPortability&gt;元素
通过禁用将程序集视为等效于应用程序可移植性用途的默认行为来指定应用程序可以在两种不同的 .NET Framework 实现中引用同一程序集。  
  
 \<配置 > 元素  
\<运行时 > 元素  
\<assemblyBinding > 元素  
\<supportPortability > 元素  
  
## <a name="syntax"></a>语法  
  
```xml  
<supportPortability PKT="public_key_token" enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|PKT|必需的特性。<br /><br /> 以字符串形式指定的受影响的程序集的公钥标记。|  
|enabled|可选特性。<br /><br /> 指定是否应启用对指定的.NET Framework 程序集的实现之间的可移植性的支持。|  
  
## <a name="enabled-attribute"></a>enabled 特性  
  
|值|描述|  
|-----------|-----------------|  
|true|启用对指定的.NET Framework 程序集的实现之间的可移植性支持。 这是默认设置。|  
|False|禁用指定的.NET Framework 程序集的实现之间的可移植性的支持。 这使应用程序具有对指定的程序集的多个实现的引用。|  
  
### <a name="child-elements"></a>子元素  
 无。  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|`configuration`|公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。|  
|`runtime`|包含有关程序集绑定和垃圾回收的信息。|  
|`assemblyBinding`|包含有关程序集版本重定向和程序集位置的信息。|  
  
## <a name="remarks"></a>备注  
 开头[!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)]，支持将自动提供给应用程序可以使用的.NET Framework 中，两个实现任一例如.NET Framework 实现或.NET 框架，用于 Silverlight 的实现。 程序集联编程序将特定的.NET Framework 程序集的两个实现视为等效项。 在少数情况下，此应用程序可移植性功能会导致问题。 在这些情况下，`<supportPortability>`元素可以用来禁用该功能。  
  
 其中一种方案是具有以引用的.NET Framework 实现和.NET Framework Silverlight 实现的特定引用程序集的程序集。 例如，编写 Windows Presentation Foundation (WPF) 中的 XAML 设计器可能需要引用这两个的 WPF 桌面实现，用于设计器的用户界面，并在 Silverlight 实现中包含的 WPF 的子集。 默认情况下，单独引用会导致编译器错误，因为程序集绑定将这两个程序集视为等效。 此元素禁用默认行为，并允许编译成功。  
  
> [!IMPORTANT]
>  为了使编译器将信息传递到公共语言运行时的程序集绑定逻辑，必须使用`/appconfig`编译器选项来指定包含此元素的 app.config 文件的位置。  
  
## <a name="example"></a>示例  
 以下示例启用应用程序具有对.NET Framework 实现和 Silverlight 实现这两个实现中存在的任何.NET Framework 程序集的.NET Framework 的引用。 `/appconfig`编译器选项必须用于指定此 app.config 文件的位置。  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding>  
         <supportPortability PKT="7cec85d7bea7798e" enable="false"/>  
         <supportPortability PKT="31bf3856ad364e35" enable="false"/>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>请参阅  
 [/appconfig （C# 编译器选项）](http://msdn.microsoft.com/library/ee523958.aspx)  
 [.NET framework 程序集统一概述](http://msdn.microsoft.com/library/8d8cc65e-031d-463b-bde3-2c6dc2e3bc48)
