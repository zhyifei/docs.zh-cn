---
title: <system.codedom> 元素
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.codedom
- http://schemas.microsoft.com/.NetConfiguration/v2.0#system.codedom
helpviewer_keywords:
- compiler configuration elements, <system.codedom> element
- system.codedom element
- <system.codedom> element
ms.assetid: 672a68f7-e69f-4479-ac30-e980085ec4fe
ms.openlocfilehash: 40a3c84e1deed4d215383670176623a6a79ac41d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155383"
---
# <a name="systemcodedom-element"></a>\<系统.代码>元素
指定可用语言提供程序的编译器配置设置。  
  
[**\<配置>**](../configuration-element.md)  
&nbsp;&nbsp;**\<系统.代码>**  
  
## <a name="syntax"></a>语法  
  
```xml  
<system.codedom>  
  <compilers> ... </compilers>  
</system.codedom>  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>属性  
 无。  
  
### <a name="child-elements"></a>子元素  
  
|元素|说明|  
|-------------|-----------------|  
|[\<编译器>](compilers-element.md)|用于编译器配置元素的容器;包含零个或多个[\<编译器>](compiler-element.md)元素。|  
  
### <a name="parent-elements"></a>父元素  
  
|元素|说明|  
|-------------|-----------------|  
|[\<配置>](../configuration-element.md)|公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。|  
  
## <a name="remarks"></a>备注  
  
## <a name="net-framework-version-20"></a>.NET 框架版本 2.0  
 [\<系统.codedom>](system-codedom-element.md)元素包含计算机上安装的语言提供程序的编译器配置设置，以及随 .NET 框架一起安装的默认提供程序（如 和<xref:Microsoft.CSharp.CSharpCodeProvider> <xref:Microsoft.VisualBasic.VBCodeProvider>。 [\<编译器>](compilers-element.md)元素包含零个或多个[\<编译器>](compiler-element.md)元素。 每个[\<编译器>](compiler-element.md)元素指定特定语言提供程序的编译器配置属性。  
  
 开发人员和编译器供应商可以将配置设置添加到计算机配置文件 （Machine.config） 以用于新<xref:System.CodeDom.Compiler.CodeDomProvider>实现。 使用<xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType>方法以编程方式枚举计算机上的编译器配置设置标识的默认语言提供程序和语言提供程序。  
  
> [!NOTE]
> 在 .NET 框架版本 1.0 和 1.1 中，.NET Framework 提供的默认语言提供程序在[\<编译器>](compilers-element.md)元素中标识。 在 .NET Framework 版本 2.0 中，默认语言提供程序不会在[\<编译器>](compilers-element.md)元素中标识，但可以使用 方法<xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A>枚举。  
  
## <a name="net-framework-versions-10-and-11"></a>.NET 框架版本 1.0 和 1.1  
 [\<系统.codedom>](system-codedom-element.md)元素包含计算机上的语言提供程序的编译器配置设置。 [\<编译器>](compilers-element.md)元素包含零个或多个[\<编译器>](compiler-element.md)元素。 每个[\<编译器>](compiler-element.md)元素指定特定语言提供程序的编译器配置属性。  
  
 .NET Framework 在计算机配置文件 (Machine.config) 中定义初始编译器设置。 开发人员和编译器供应商可以添加新 <xref:System.CodeDom.Compiler.CodeDomProvider> 实现的配置设置。 使用 <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> 方法，以编程方式枚举计算机上的语言提供程序和编译器配置设置。  
  
## <a name="configuration-file"></a>配置文件  
 此元素可用于计算机配置文件和应用程序配置文件。  
  
## <a name="example"></a>示例  
 下面的示例说明了典型的编译器配置。  
  
```xml  
<configuration>  
  <system.codedom>  
    <compilers>  
      <!-- zero or more compiler elements -->  
      <compiler
        language="c#;cs;csharp"  
        extension=".cs"  
        type="Microsoft.CSharp.CSharpCodeProvider, System,
          Version=1.0.5000.0, Culture=neutral,
          PublicKeyToken=b77a5c561934e089"  
        compilerOptions=""  
        warningLevel="1" />  
    </compilers>  
  </system.codedom>  
</configuration>  
```  
  
## <a name="see-also"></a>另请参阅

- <xref:System.CodeDom.Compiler.CompilerInfo>
- <xref:System.CodeDom.Compiler.CodeDomProvider>
- [配置文件架构](../index.md)
- [编译器和语言提供程序设置架构](index.md)
- [\<编译器>元素](compiler-element.md)
