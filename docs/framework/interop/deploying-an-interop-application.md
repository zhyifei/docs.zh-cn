---
title: "部署互操作应用程序 | Microsoft Docs"
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
  - "COM 互操作, 部署应用程序"
  - "COM 互操作, 公开 COM 组件"
  - "部署应用程序 [.NET Framework], 互操作"
  - "向 .NET Framework 公开 COM 组件"
  - "与非托管代码间的互操作, 部署应用程序"
  - "与非托管代码间的互操作, 公开 COM 组件"
  - "专用程序集"
  - "共享程序集"
  - "签名的程序集"
  - "具有强名称的程序集, 互操作应用程序"
  - "未签名的程序集"
ms.assetid: ea8a403e-ae03-4faa-9d9b-02179ec72992
caps.latest.revision: 10
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 10
---
# 部署互操作应用程序
Interop 应用程序通常包括一个 .NET 客户端程序集、一个或多个表示唯一 COM 类型库的互操作程序集，以及一个或多个已注册的 COM 组件。  Visual Studio 和 [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] 提供了用于将类型库导入并转换到互操作程序集的工具，如[将类型库当作程序集导入](../../../docs/framework/interop/importing-a-type-library-as-an-assembly.md)中所述。  可以通过以下两种方式部署互操作应用程序：  
  
-   使用嵌入的互操作类型：从 [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)]开始，您可以指示编译器将互操作程序集中的类型信息嵌入到可执行文件中。  编译器只嵌入您的应用程序所使用的类型信息。  无需将互操作程序集与您的应用程序一起部署。  这是推荐采用的方法。  
  
-   通过部署互操作程序集：您可以创建一个对互操作程序集的标准引用。  在本例中，互操作程序集必须与您的应用程序一起部署。  如果使用此方法，且不使用专用 COM 组件，而是要将某个 COM 组件集成到托管代码中，请始终引用该组件的作者所发布的主互操作程序集 \(PIA\)。  有关生成和使用主互操作程序集的更多信息，请参见[主互操作程序集](http://msdn.microsoft.com/zh-cn/b977a8be-59a0-40a0-a806-b11ffba5c080)。  
  
 如果使用嵌入的互操作类型，则部署过程将既简单又直观。  您不需要执行任何特别的操作。  本文的其余部分将介绍将互操作程序集与您的应用程序一起部署的方案。  
  
## 部署互操作程序集  
 程序集可以具有强名称。  具有强名称的程序集包括发行者的公钥，它用于提供唯一的标识。  [类型库导入程序 \(Tlbimp.exe\)](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md) 生成的程序集可以由发行者使用 **\/keyfile** 选项来进行签名。  您可以将签名的程序集安装到全局程序集缓存中。  未签名的程序集必须作为专用程序集安装在用户的计算机上。  
  
### 专用程序集  
 若要安装专用的程序集，必须在同一目录结构中安装应用程序可执行文件和包含导入的 COM 类型的互操作程序集。  下图显示了将由 Client1.exe 和 Client2.exe（它们位于不同的应用程序目录中）专用的未签名互操作程序集。  此示例中名为 LOANLib.dll 的互操作程序集将安装两次。  
  
 ![目录结构和 Windows 注册表](../../../docs/framework/interop/media/comdeployprivate.gif "comdeployprivate")  
专用部署的目录结构和注册表项  
  
 与应用程序关联的所有 COM 组件都必须安装在 Windows 注册表中。  如果图中的 Client1.exe 和 Client2.exe 安装在不同的计算机上，则必须在这两台计算机上注册 COM 组件。  
  
### 共享程序集  
 多个应用程序共享的程序集应安装在一个称作“全局程序集缓存”的集中储存库中。  对于在全局程序集缓存中签名并安装的互操作程序集，多个 .NET 客户端可以访问该程序集的同一副本。  有关生成和使用主互操作程序集的更多信息，请参见[主互操作程序集](http://msdn.microsoft.com/zh-cn/b977a8be-59a0-40a0-a806-b11ffba5c080)。  
  
## 请参阅  
 [向 .NET Framework 公开 COM 组件](../../../docs/framework/interop/exposing-com-components.md)   
 [将类型库当作程序集导入](../../../docs/framework/interop/importing-a-type-library-as-an-assembly.md)   
 [Using COM Types in Managed Code](http://msdn.microsoft.com/zh-cn/1a95a8ca-c8b8-4464-90b0-5ee1a1135b66)   
 [编译互操作项目](../../../docs/framework/interop/compiling-an-interop-project.md)