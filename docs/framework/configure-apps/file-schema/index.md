---
title: ".NET Framework 的配置文件架构 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
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
  - ".NET Framework 应用程序配置, 配置架构"
  - "app.config 文件, 架构"
  - "应用程序配置文件, 架构"
  - "应用程序开发 [.NET Framework], 架构"
  - "配置架构 [.NET Framework]"
  - "配置设置 [.NET Framework], 应用程序"
  - "容器标记"
  - "enterprisesec 配置文件"
  - "enterprisesec.config 文件"
  - "计算机配置文件"
  - "machine.config 文件"
  - "架构配置设置"
  - "架构, 配置设置"
  - "安全性 [.NET Framework], 配置文件"
  - "security.config 文件"
  - "格式良好的 XML"
  - "XML 标记"
ms.assetid: 69003d39-dc8a-460c-a6be-e6d93e690b38
caps.latest.revision: 20
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 18
---
# .NET Framework 的配置文件架构
配置文件是可用来更改应用设置并为其设置策略的标准 XML 文件。  .NET Framework 配置架构由一些可在配置文件中用来控制应用行为的元素组成。  本节的目录反映了架构的层次结构：启动、运行时、网络和其他配置设置类型。  
  
 有关配置文件类型、格式和位置的信息，请参见[配置应用](../../../../docs/framework/configure-apps/index.md)一文。  如果希望直接编辑配置文件，你需要熟悉 XML。  
  
> [!IMPORTANT]
>  配置文件中的 XML 标记和特性区分大小写。  
  
## 本节内容  
 [\<configuration\> 元素](../../../../docs/framework/configure-apps/file-schema/configuration-element.md)  
 描述 `<configuration>` 元素，它是所有配置文件的顶级元素。  
  
 [\<assemblyBinding\> 元素](../../../../docs/framework/configure-apps/file-schema/assemblybinding-element-for-configuration.md)  
 指定配置级的程序集绑定策略。  
  
 [\<linkedConfiguration\> 元素](../../../../docs/framework/configure-apps/file-schema/linkedconfiguration-element.md)  
 指定要包含的配置文件。  
  
 [启动设置架构](../../../../docs/framework/configure-apps/file-schema/startup/index.md)  
 描述指定要使用的公共语言运行时版本的元素。  
  
 [运行时设置架构](../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 描述配置程序集绑定和运行时行为的元素。  
  
 [网络设置架构](../../../../docs/framework/configure-apps/file-schema/network/index.md)  
 描述指定 .NET Framework 如何连接到 Internet 的元素。  
  
 [密码设置架构](../../../../docs/framework/configure-apps/file-schema/cryptography/index.md)  
 描述将友好算法名映射到实现密码算法的类的元素。  
  
 [配置节架构](../../../../docs/framework/configure-apps/file-schema/configuration-sections-schema.md)  
 描述用于创建和使用自定义设置的配置节的元素。  
  
 [跟踪和调试设置架构](../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)  
 描述指定跟踪开关和侦听器的元素。  
  
 [编译器和语言提供程序设置架构](../../../../docs/framework/configure-apps/file-schema/compiler/index.md)  
 描述指定可用语言提供程序的编译器配置的元素。  
  
 [应用程序设置架构](../../../../docs/framework/configure-apps/file-schema/application-settings-schema.md)  
 描述允许 Windows 窗体或 ASP.NET 应用程序存储和检索应用程序范围和用户范围的设置的元素。  
  
 [Web 设置架构](../../../../docs/framework/configure-apps/file-schema/web/index.md)  
 Web 设置架构中的所有元素，包括用于配置 ASP.NET 如何与宿主应用程序（如 IIS）一起工作的元素。  在 aspnet.config 文件中使用。  
  
## 相关章节  
 [Remoting Settings Schema](http://msdn.microsoft.com/zh-cn/dc2d1e62-9af7-4ca1-99fd-98b93bb4db9e)  
 描述对实现远程处理的客户端和服务器应用程序进行配置的元素。  
  
 [ASP.NET 设置架构](http://msdn.microsoft.com/library/b5ysx397\(v=vs.100\).aspx)  
 描述控制 ASP.NET Web 应用程序的行为的元素。  
  
 [Web Services Settings Schema](http://msdn.microsoft.com/zh-cn/f84d6d55-1add-4eb7-ae46-33df5833ea2e)  
 描述控制 ASP.NET Web 服务以及它们的客户端的行为的元素。  
  
 [Configuring .NET Framework Apps](http://msdn.microsoft.com/zh-cn/d789b592-fcb5-4e3d-8ac9-e0299adaaa42)  
 描述如何在 .NET Framework 中配置安全性、程序集绑定和远程处理。