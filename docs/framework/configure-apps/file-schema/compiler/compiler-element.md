---
title: '&lt;编译器&gt;元素'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#compiler
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.codedom/compilers/compiler
helpviewer_keywords:
- compiler configuration elements, <compiler> element
- <compiler> element
- compiler configuration attributes
- compiler element
ms.assetid: 7a151659-b803-4c27-b5ce-1c4aa0d5a823
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: b033e26d64f23398a4da6842bb4688cc94627d68
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="ltcompilergt-element"></a>&lt;编译器&gt;元素
指定语言提供程序的编译器配置属性。  
  
 \<配置元素 >  
\<system.codedom 元素 >  
\<编译器元素 >  
\<编译器 > 元素  
  
## <a name="syntax"></a>语法  
  
```xml  
<compiler  
  language="languageName[;...;...]"  
  extension="fileExtension[;...;...]"  
  type="typeName, assemblyName"  
  warningLevel="number"  
  compilerOptions="option1 option2"  
/>  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|`compilerOptions`|可选特性。<br /><br /> 指定用于编译的其他编译器特定参数。 值`compilerOptions`属性通常编译器编译器选项主题中列出。 在 Visual Studio 2005 文档中，你可以通过查找索引中的"编译器选项"中找到编译器选项。|  
|`extension`|必需的特性。<br /><br /> 提供以分号分隔的文件使用的源的语言提供程序的文件扩展名的列表。 例如，".cs"。|  
|`language`|必需的特性。<br /><br /> 提供的语言提供程序支持的语言名称之间用分号分隔的列表。 例如，"c#; cs; csharp"。|  
|`type`|必需的特性。<br /><br /> 指定语言提供程序，包括包含的提供程序实现的程序集名称的类型名称。 类型名称必须满足中定义的要求[指定完全限定的类型名称](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md)。|  
|`warningLevel`|可选特性。<br /><br /> 指定默认的编译器警告等级;确定在该语言提供程序将编译警告视为错误的级别。|  
  
### <a name="child-elements"></a>子元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<providerOption > 元素](../../../../../docs/framework/configure-apps/file-schema/compiler/provideroption-element.md)|指定语言提供程序的编译器版本特性。|  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<configuration> 元素](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。|  
|[\<system.codedom > 元素](../../../../../docs/framework/configure-apps/file-schema/compiler/system-codedom-element.md)|指定可用语言提供程序的编译器配置设置。|  
|[\<编译器 > 元素](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md)|编译器配置元素，则容器包含零个或多`<compiler>`元素。|  
  
## <a name="remarks"></a>备注  
 每个`<compiler>`元素指定特定的语言提供程序的编译器配置特性。 提供程序扩展<xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType>类特定的语言;`<compiler>`元素定义的编译器和语言提供程序的代码生成器设置。  
  
 .NET Framework 在计算机配置文件 (Machine.config) 中定义初始编译器设置。 开发人员和编译器供应商可以添加新 <xref:System.CodeDom.Compiler.CodeDomProvider> 实现的配置设置。 使用 <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> 方法，以编程方式枚举计算机上的语言提供程序和编译器配置设置。  
  
 在应用程序或 Web 配置文件的编译器元素可以补充或重写计算机配置文件中的设置。 如果为相同的语言名称或相同的文件扩展名配置了多个提供程序实现，最后一个匹配的配置将覆盖任何以前的配置提供程序对这种语言名称或文件扩展名。  
  
## <a name="configuration-file"></a>配置文件  
 计算机配置文件和应用程序配置文件中，可以使用此元素。  
  
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
        type="Microsoft.CSharp.CSharpCodeProvider, System,   
          Version=2.0.3600.0, Culture=neutral,   
          PublicKeyToken=b77a5c561934e089"  
        compilerOptions="/optimize"  
        warningLevel="1" />  
    </compilers>  
  </system.codedom>  
</configuration>  
```  
  
## <a name="see-also"></a>请参阅  
 <xref:System.CodeDom.Compiler.CompilerInfo>  
 <xref:System.CodeDom.Compiler.CodeDomProvider>  
 [配置文件架构](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [\<编译器 > 元素](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md)  
 [指定完全限定的类型名称](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md)  
 [编译器进行编译 （ASP.NET 设置架构） 使用的编译器元素](https://msdn.microsoft.com/library/f7d6b078-5d42-4134-b3f7-62e1aba1df1e(v=vs.100))
