---
title: "编译器和语言提供程序设置架构 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "编译器配置元素"
  - "编译器配置元素, 架构"
  - "编译器配置设置"
  - "编译器配置设置, 架构"
  - "配置架构 [.NET Framework], 编译器设置"
  - "配置设置 [.NET Framework], 编译器"
  - "语言提供程序"
  - "语言提供程序, 设置架构"
ms.assetid: c020b139-8699-4f0d-9ac9-70d0c5b2a8c8
caps.latest.revision: 9
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 9
---
# 编译器和语言提供程序设置架构
编译器和语言提供程序设置为可用的语言提供程序指定编译器配置元素。  每个编译器配置元素指定代码提供程序类型名称、编译器参数、受支持的语言名称以及受支持的文件扩展名。  
  
 .NET Framework 在计算机配置文件 \(Machine.config\) 中定义初始编译器设置。  开发人员和编译器供应商可以为新的 <xref:System.CodeDom.Compiler.CodeDomProvider> 实现添加配置设置。  使用 <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=fullName> 方法可在计算机上以编程方式枚举语言提供程序和编译器配置设置。  
  
 [\<configuration\> 元素](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)  
  
 [\<system.codedom\>](../../../../../docs/framework/configure-apps/file-schema/compiler/system-codedom-element.md)  
  
 [\<编译器\>](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md)  
  
 [\<compiler\>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md)  
  
|元素|说明|  
|--------|--------|  
|[\<system.codedom\>](../../../../../docs/framework/configure-apps/file-schema/compiler/system-codedom-element.md)|指定可用语言提供程序的编译器配置设置。|  
|[\<编译器\>](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md)|编译器配置元素的容器；包含0或者多个[\<compiler\>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md)元素。|  
|[\<compiler\>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md)|指定语言提供程序的编译器配置特性。|  
  
## 示例  
 下面的示例阐释了一个典型的编译器配置元素。  
  
```  
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
  
## 请参阅  
 <xref:System.CodeDom.Compiler.CompilerInfo>   
 <xref:System.CodeDom.Compiler.CodeDomProvider>   
 [配置文件架构](../../../../../docs/framework/configure-apps/file-schema/index.md)   
 [\<compiler\> 元素](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md)