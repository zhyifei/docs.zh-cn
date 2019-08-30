---
title: <compilers> 元素
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#compilers
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.codedom/compilers
helpviewer_keywords:
- compiler configuration elements, <compilers> element
- <compilers> element
- compilers element
ms.assetid: d40fba59-98f9-4783-ae0c-2ebea27ce77b
ms.openlocfilehash: 5232c5bd2d4fad8104d156bfa86141ceb7f0dd93
ms.sourcegitcommit: 1b020356e421a9314dd525539da12463d980ce7a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/30/2019
ms.locfileid: "70167693"
---
# <a name="compilers-element"></a>\<编译器 > 元素
编译器配置元素的容器；包含零个或多个 [\<compiler>](compiler-element.md) 元素。  
  
[ **\<configuration>** ](../configuration-element.md)  
&nbsp;&nbsp;[ **\<system.object >** ](system-codedom-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp; **\<编译器 >**  
  
## <a name="syntax"></a>语法  
  
```xml  
<compilers>  
  <compiler ... />  
</compilers>  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
 无。  
  
### <a name="child-elements"></a>子元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<compiler> Element](compiler-element.md)|指定语言提供程序的编译器配置属性。|  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<configuration> 元素](../configuration-element.md)|公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。|  
|[\<system.object > 元素](system-codedom-element.md)|指定可用语言提供程序的编译器配置设置。|  
  
## <a name="remarks"></a>备注  
 编译器 > 元素包含计算机上的语言提供程序的编译器配置设置。 [ \<](compilers-element.md) 每个[ \<编译器 >](compiler-element.md)元素指定特定语言提供程序的编译器配置特性。  
  
 .NET Framework 在计算机配置文件 (machine.config) 中定义初始编译器和语言提供程序设置。 开发人员和编译器供应商可以添加新 <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType> 实现的配置设置。 使用 <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> 方法，以编程方式枚举计算机上的语言提供程序和编译器配置设置。  
  
## <a name="configuration-file"></a>配置文件  
 此元素可在计算机配置文件和应用程序配置文件中使用。  
  
## <a name="example"></a>示例  
 以下示例说明典型的编译器配置元素。  
  
```xml  
<configuration>  
   <system.codedom>  
     <compilers>  
       <!-- zero or more compiler elements -->  
       <compiler   
          language="c#;cs;csharp"   
          extension=".cs"  
          type="Microsoft.CSharp.CSharpCodeProvider, System, Version=1.0.5000.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"  
          compilerOptions=""    
          warningLevel="1" />  
     </compilers>  
   </system.codedom>  
</configuration>  
```  
  
## <a name="see-also"></a>请参阅

- <xref:System.CodeDom.Compiler.CompilerInfo>
- <xref:System.CodeDom.Compiler.CodeDomProvider>
- [配置文件架构](../index.md)
- [编译器和语言提供程序设置架构](index.md)
- [\<compiler> Element](compiler-element.md)
