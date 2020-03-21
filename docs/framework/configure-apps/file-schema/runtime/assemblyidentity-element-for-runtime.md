---
title: <runtime> 的 <assemblyIdentity> 元素
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/dependentAssembly/assemblyIdentity
- http://schemas.microsoft.com/.NetConfiguration/v2.0#assemblyIdentity
helpviewer_keywords:
- <assemblyIdentity> element
- container tags, <assemblyIdentity> element
- assemblyIdentity element
ms.assetid: cea4d187-6398-4da4-af09-c1abc6a349c1
ms.openlocfilehash: b026dafbde796bbd8726de56b532ed6710ba2290
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154304"
---
# <a name="assemblyidentity-element-for-runtime"></a>\<用于运行时>的\<程序集标识>元素
包含有关程序集的标识信息。  
  
[**\<配置>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<运行时>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<程序集绑定>**](assemblybinding-element-for-runtime.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<从属装配>**](dependentassembly-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<程序集标识>**  
  
## <a name="syntax"></a>语法  
  
```xml  
   <assemblyIdentity
name="assembly name"  
publicKeyToken="public key token"  
culture="assembly culture"/>  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>属性  
  
|Attribute|说明|  
|---------------|-----------------|  
|`name`|必需的特性。<br /><br /> 程序集的名称|  
|`culture`|可选特性。<br /><br /> 指定程序集的语言和国家/区域的字符串。|  
|`publicKeyToken`|可选特性。<br /><br /> 指定程序集的强名称的十六进制值。|  
|`processorArchitecture`|可选特性。<br /><br /> 值"x86"、"amd64"、"msil"或"ia64"的值之一，指定包含特定于处理器代码的程序集的处理器体系结构。 这些值不区分大小写。 如果为该属性分配了任何其他值，则忽略`<assemblyIdentity>`整个元素。 请参阅 <xref:System.Reflection.ProcessorArchitecture>。|  
  
## <a name="processorarchitecture-attribute"></a>处理器体系结构属性  
  
|值|说明|  
|-----------|-----------------|  
|`amd64`|仅限 AMD x86-64 架构。|  
|`ia64`|仅限英特尔 Itanium 架构。|  
|`msil`|不特定于处理器和每字位数。|  
|`x86`|32 位 x86 处理器，本机处理器或 Windows 上 Windows （WOW） 环境中的 64 位平台。|  
  
### <a name="child-elements"></a>子元素  
 无。  
  
### <a name="parent-elements"></a>父元素  
  
|元素|说明|  
|-------------|-----------------|  
|`assemblyBinding`|包含有关程序集版本重定向和程序集位置的信息。|  
|`configuration`|公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。|  
|`dependentAssembly`|封装每个程序集的绑定策略和程序集位置。 为每个程序集`<dependentAssembly>`使用一个元素。|  
|`runtime`|包含有关程序集绑定和垃圾回收的信息。|  
  
## <a name="remarks"></a>备注  
 每个**\<从属程序集>** 元素必须具有一个**\<程序集标识>** 子元素。  
  
 如果存在该`processorArchitecture`属性，则`<assemblyIdentity>`该元素仅适用于具有相应处理器体系结构的程序集。 如果属性`processorArchitecture`不存在，则`<assemblyIdentity>`元素可以应用于具有任何处理器体系结构的程序集。  
  
 下面的示例显示了两个具有相同名称的程序集的配置文件，该文件针对的是两个不同的两个不同的处理器体系结构，并且其版本尚未同步维护。当应用程序在 x86 平台上执行时，将`<assemblyIdentity>`应用第一个元素，忽略另一个元素。 如果应用程序在 x86 或 ia64 以外的平台上执行，则两者都将被忽略。  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <dependentAssembly>  
            <assemblyIdentity name="MyAssembly"  
                  publicKeyToken="14a739be0244c389"  
                  culture="neutral"  
                  processorArchitecture="x86" />  
            <bindingRedirect oldVersion= "1.0.0.0"
                  newVersion="1.1.0.0" />  
         </dependentAssembly>  
         <dependentAssembly>  
            <assemblyIdentity name="MyAssembly"  
                  publicKeyToken="14a739be0244c389"  
                  culture="neutral"
                  processorArchitecture="ia64" />  
            <bindingRedirect oldVersion="1.0.0.0"
                  newVersion="2.0.0.0" />  
         </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
 如果配置文件包含没有`<assemblyIdentity>``processorArchitecture`属性的元素，并且不包含与平台匹配的元素，则使用没有该`processorArchitecture`属性的元素。  
  
## <a name="example"></a>示例  
 下面的示例演示如何提供有关程序集的信息。  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <dependentAssembly>  
            <assemblyIdentity name="myAssembly"  
                              publicKeyToken="32ab4ba45e0a69a1"  
                              culture="neutral" />  
            <!--Redirection and codeBase policy for myAssembly.-->  
         </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>另请参阅

- [运行时设置架构](index.md)
- [配置文件架构](../index.md)
- [重定向程序集版本](../../redirect-assembly-versions.md)
