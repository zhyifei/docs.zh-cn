---
title: <runtime> 的 <assemblyBinding> 元素
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding
helpviewer_keywords:
- <assemblyBinding> element
- assemblyBinding element
- container tags, <assemblyBinding> element
ms.assetid: 964cbb35-ab49-4498-8471-209689e5dada
ms.openlocfilehash: 202b063ad3f0f9696cdc12aff434d61fe5a813e6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154317"
---
# <a name="assemblybinding-element-for-runtime"></a>\<用于\<运行时>的程序集绑定>元素
包含有关程序集版本重定向和程序集位置的信息。  
  
[**\<配置>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<运行时>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<程序集绑定>**  
  
## <a name="syntax"></a>语法  
  
```xml  
      <assemblyBinding
   xmlns="urn:schemas-microsoft-com:asm.v1" appliesTo="v1.0.3705">  
</assemblyBinding>  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>属性  
  
|Attribute|说明|  
|---------------|-----------------|  
|**xmlns**|必需的特性。<br /><br /> 指定程序集绑定所需的 XML 命名空间。 使用字符串“urn: 架构-microsoft-com:asm.v1”作为值。|  
|**适用于**|指定 .NET Framework 程序集重定向适用的运行时版本。 此可选特性用 .NET Framework 版本号来指示其适用的版本。 如果没有指定 appliesTo 特性，\<assemblyBinding> 元素将适用于 .NET Framework 的所有版本********。 **应用到**属性在 .NET 框架版本 1.1 中引入;.NET 框架版本 1.0 会忽略它。 这意味着在使用 .NET Framework 版本 1.0 时应用所有**\<程序集绑定>** 元素，即使指定了**应用To**属性也是如此。|  
  
### <a name="child-elements"></a>子元素  
  
|元素|说明|  
|-------------|-----------------|  
|[\<从属装配>](dependentassembly-element.md)|封装程序集的绑定策略和程序集位置。 为每个程序集使用一个**\<从属程序集>** 标记。|  
|[\<探测>](probing-element.md)|指定加载程序集时公共语言运行时搜索的子目录。|  
|[\<发布者策略>](publisherpolicy-element.md)|指定运行时是否使用发布者策略。|  
|[\<符合条件>](qualifyassembly-element.md)|指定使用部分名称时应动态加载的程序集全名。|  
  
### <a name="parent-elements"></a>父元素  
  
|元素|说明|  
|-------------|-----------------|  
|`configuration`|公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。|  
|`runtime`|包含有关程序集绑定和垃圾回收的信息。|  
  
## <a name="example"></a>示例  
 下面的示例显示如何将一个程序集版本重定向到另一个版本并提供基本代码。  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <dependentAssembly>  
            <assemblyIdentity name="myAssembly"  
                              publicKeyToken="32ab4ba45e0a69a1"  
                              culture="neutral" />  
            <bindingRedirect oldVersion="1.0.0.0"  
                             newVersion="2.0.0.0"/>  
            <codeBase version="2.0.0.0"  
                      href="http://www.litwareinc.com/myAssembly.dll"/>  
         </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
 下面的示例演示如何使用**应用 To**属性重定向 .NET 框架程序集的绑定。  
  
```xml  
<runtime>  
   <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1" appliesTo="v1.0.3705">  
      <dependentAssembly>
         <assemblyIdentity name="mscorcfg" publicKeyToken="b03f5f7f11d50a3a" culture=""/>  
         <bindingRedirect oldVersion="0.0.0.0-65535.65535.65535.65535" newVersion="1.0.3300.0"/>  
      </dependentAssembly>  
   </assemblyBinding>  
</runtime>  
```  
  
## <a name="see-also"></a>另请参阅

- [运行时设置架构](index.md)
- [配置文件架构](../index.md)
- [重定向程序集版本](../../redirect-assembly-versions.md)
