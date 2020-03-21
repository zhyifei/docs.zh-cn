---
title: <providerOption> 元素
ms.date: 03/30/2017
f1_keywords:
- provideroption
helpviewer_keywords:
- <provideroption> element
- providerOptions
- provideroption element
ms.assetid: 014f2e0b-c0b5-4fc4-92d3-73f02978b2a1
ms.openlocfilehash: c8ba5b9a0680f5e5102c13eb5bb0c1904a168c07
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155396"
---
# <a name="provideroption-element"></a>\<提供程序选项>元素
指定语言提供程序的编译器版本属性。  

[**\<配置>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<系统.代码>**](system-codedom-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<编译器>**](compilers-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<编译器>**](compiler-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<提供商选项>**

## <a name="syntax"></a>语法  
  
```xml  
<providerOption  
  name="option-name"  
  value="option-value"  
/>  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>属性  
  
|Attribute|说明|  
|---------------|-----------------|  
|`name`|必需的特性。<br /><br /> 指定选项的名称;例如，"编译器版本"。|  
|`value`|必需的特性。<br /><br /> 指定选项的值;例如，"v3.5"。|  
  
### <a name="child-elements"></a>子元素  
 无。  
  
### <a name="parent-elements"></a>父元素  
  
|元素|说明|  
|-------------|-----------------|  
|[\<配置>元素](../configuration-element.md)|公共语言运行库和 .NET Framework 应用程序所使用的每个配置文件中的根元素。|  
|[\<系统.代码>元素](system-codedom-element.md)|指定可用语言提供程序的编译器配置设置。|  
|[\<编译器>元素](compilers-element.md)|用于编译器配置元素的容器;包含零个或多个`<compiler>`元素。|  
|[\<编译器>元素](compiler-element.md)|指定语言提供程序的编译器配置属性。|  
  
## <a name="remarks"></a>备注  
 在 .NET 框架版本 3.5 中，代码文档对象模型 （CodeDOM） 代码提供程序可以使用`<providerOption>`元素支持特定于提供程序的选项。  
  
 .NET 框架 3.5 包括更新的 .NET 框架 2.0 程序集，并提供包含新类型的新版本 3.5 程序集。 Microsoft C# 和 Visual Basic 代码提供程序包含在 .NET 框架 2.0 程序集中，但已更新以支持版本 3.5 编译器。 默认情况下，更新的代码提供程序为版本 2.0 编译器生成代码。 可以使用 元素`<providerOption>`将目标编译器版本更改为 3.5。 为此，请为`name`属性指定"编译器版本"，为`value`属性指定"v3.5"。 必须在版本号前面加上小写"v"。  
  
 通过将元素添加到 .NET 框架 2.0 计算机.config 或 root Web.config 文件，`<providerOption>`可以使版本规范成为全局。 如果在 Machine.config 文件中将默认编译器版本更新为 3.5，则可以使用应用程序配置文件中`<providerOption>`的元素，按应用程序将其更改回 2.0。  
  
 CodeDOM 代码提供程序实现者可以通过提供采用`providerOptions`类型 参数<xref:System.Collections.Generic.IDictionary%602>的构造函数来处理自定义选项。  
  
## <a name="example"></a>示例  
 下面的示例演示如何指定应使用 C# 代码提供程序的版本 3.5。  
  
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
        warningLevel="1" >  
          <providerOption  
            name="CompilerVersion"  
            value="v3.5" />  
      </compiler>  
    </compilers>  
  </system.codedom>  
</configuration>  
```  
  
## <a name="see-also"></a>另请参阅

- <xref:System.CodeDom.Compiler.CompilerInfo>
- <xref:System.CodeDom.Compiler.CodeDomProvider>
- [配置文件架构](../index.md)
- [\<编译器>元素](compilers-element.md)
- [指定完全限定的类型名称](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)
- [compilation 的 compilers 的 compiler 元素（ASP.NET 设置架构）](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/a15ebt6c(v=vs.100))
