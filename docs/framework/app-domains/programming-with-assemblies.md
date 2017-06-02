---
title: "使用程序集编程 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-bcl"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "程序集 [.NET Framework], 编程"
  - "编程程序集"
ms.assetid: 25918b15-701d-42c7-95fc-c290d08648d6
caps.latest.revision: 18
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 18
---
# 使用程序集编程
程序集是 .NET Framework 的生成块，它们构成基本部署单元、版本控制、重新使用、激活范围和安全权限。  程序集向公共语言运行时提供了解类型实现所需要的信息。  它是为共同运行和形成功能逻辑单元而生成的类型和资源的集合。  对于运行时，类型不存在于程序集上下文之外。  
  
 本节描述如何创建模块，如何从模块创建程序集，如何创建密钥对并使用强名称为程序集签名，以及如何将程序集安装至全局程序集缓存。  此外，本节还描述了如何使用 [MSIL 反汇编程序 \(Ildasm.exe\)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) 查看程序集清单信息。  
  
> [!NOTE]
>  从 .NET Framework 2.0 版开始，对于版本号高于当前已加载运行时的 .NET Framework 版本，运行时将不加载由其进行编译的程序集。  这同样适用于主版本号和次版本号的组合。  
  
## 本节内容  
 [创建程序集](../../../docs/framework/app-domains/create-assemblies.md)  
 提供单文件和多文件程序集的概述。  
  
 [程序集名称](../../../docs/framework/app-domains/assembly-names.md)  
 提供程序集命名的概述。  
  
 [如何：确定程序集的完全限定名](../../../docs/framework/app-domains/how-to-determine-assembly-fully-qualified-name.md)  
 描述如何确定程序集的完全限定名。  
  
 [在完全信任环境中运行 Intranet 应用程序](../../../docs/framework/app-domains/running-intranet-applications-in-full-trust.md)  
 描述如何对 Intranet 共享中的完全信任程序集指定旧版本的安全策略。  
  
 [程序集位置](../../../docs/framework/app-domains/assembly-location.md)  
 提供在何处定位程序集的概述。  
  
 [如何：生成单文件程序集](../../../docs/framework/app-domains/how-to-build-a-single-file-assembly.md)  
 介绍如何创建单文件程序集。  
  
 [多文件程序集](../../../docs/framework/app-domains/multifile-assemblies.md)  
 描述创建多文件程序集的原因。  
  
 [如何：生成多文件程序集](../../../docs/framework/app-domains/how-to-build-a-multifile-assembly.md)  
 介绍如何创建多文件程序集。  
  
 [设置程序集特性](../../../docs/framework/app-domains/set-assembly-attributes.md)  
 介绍程序集特性及其设置方法。  
  
 [创建和使用具有强名称的程序集](../../../docs/framework/app-domains/create-and-use-strong-named-assemblies.md)  
 描述如何使用强名称为程序集签名及其原因，包括帮助主题。  
  
 [延迟为程序集签名](../../../docs/framework/app-domains/delay-sign-assembly.md)  
 介绍如何延迟对程序集签名。  
  
 [使用程序集和全局程序集缓存](../../../docs/framework/app-domains/working-with-assemblies-and-the-gac.md)  
 介绍如何将程序集添加到全局程序集缓存及其原因，包括帮助主题。  
  
 [如何：查看程序集内容](../../../docs/framework/app-domains/how-to-view-assembly-contents.md)  
 描述如何使用 MSIL 反汇编程序 \(Ildasm.exe\) 查看程序集内容。  
  
 [公共语言运行时中的类型转发](../../../docs/framework/app-domains/type-forwarding-in-the-common-language-runtime.md)  
 描述如何使用类型转发将类型移到另一程序集中，而不中断现有应用程序。  
  
## 参考  
 <xref:System.Reflection.Assembly>  
 表示程序集的 .NET Framework 类。  
  
## 相关章节  
 [如何：从程序集获得类型和成员信息](../../../docs/framework/app-domains/how-to-obtain-type-and-member-information-from-an-assembly.md)  
 描述如何以编程方式从程序集中获取类型和其他信息。  
  
 [公共语言运行时中的程序集](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)  
 提供公共语言运行时程序集的概念性概述。  
  
 [程序集版本控制](../../../docs/framework/app-domains/assembly-versioning.md)  
 概述程序集绑定以及 <xref:System.Reflection.AssemblyVersionAttribute> 特性和 <xref:System.Reflection.AssemblyInformationalVersionAttribute> 特性。  
  
 [运行时如何定位程序集](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)  
 介绍运行时如何确定用于满足绑定请求的程序集。  
  
 [反射](../../../docs/framework/reflection-and-codedom/reflection.md)  
 描述如何使用 **Reflection** 类获取有关程序集的信息。