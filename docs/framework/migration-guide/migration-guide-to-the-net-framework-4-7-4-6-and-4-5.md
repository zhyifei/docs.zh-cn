---
title: ".NET Framework 4.6 和 4.5 的迁移指南  | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - ".NET Framework，将应用程序迁移到"
  - "迁移，NET Framework"
ms.assetid: 02d55147-9b3a-4557-a45f-fa936fadae3b
caps.latest.revision: 56
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
---
# .NET Framework 4.6 和 4.5 的迁移指南 
如果使用早期版本的 .NET Framework 创建了应用程序，则通常能将该应用程序轻松升级到 .NET Framework 4.5、4.5.1 或 4.6。 在 Visual Studio 中打开项目。 如果已在早期版本中创建项目，则**“项目兼容性”**对话框将自动打开。 有关升级 Visual Studio 2013 中的项目的详细信息，请参阅[如何：升级在 Visual Studio 早期版本中创建的项目](http://msdn.microsoft.com/library/vstudio/ms185327\(v=vs.100\).aspx) 和 [移植、迁移和升级 Visual Studio 项目](../Topic/Porting,%20Migrating,%20and%20Upgrading%20Visual%20Studio%20Projects.md)。  
  
 但是，.NET Framework 中的某些更改需要更改你的代码。 你可能还希望利用 .NET Framework 4.5 、其单点版本或 .NET Framework 4.6 中的新增功能。 通常，针对新版本的 .NET Framework 来对应用程序进行这些类型的更改的过程称作“迁移”。 如果不必迁移应用，那么你可以在 .NET Framework 4.5 或更高版本中运行它，而无需编译它。  
  
## 迁移资源  
 在将应用从 .NET Framework 的早期版本迁移到版本 4.5、4.5.1 或 4.5.2 之前，请查看以下文档：  
  
-   请参阅 [版本和依赖关系](../../../docs/framework/migration-guide/versions-and-dependencies.md) 以了解作为每个 .NET Framework 版本基础的 CLR 版本，并查看成功定位应用的指南。  
  
-   查看 [应用程序兼容性](../../../docs/framework/migration-guide/application-compatibility.md) 以了解有关运行时和可能影响你的应用的重定目标更改的信息以及如何处理它们的信息。  
  
-   查看 [类库中过时的内容](../../../docs/framework/whats-new/whats-obsolete.md) 以确定代码中已过时的任何类型或成员以及建议的备选项。  
  
-   查看 [新增功能](../../../docs/framework/whats-new/index.md) 了解你可能想要添加到应用的新功能的说明。  
  
## 请参阅  
 [4.5.1 中的应用程序兼容性](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-5-1.md)   
 [4.5 中的应用程序兼容性](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-5.md)   
 [从 .NET Framework 1.1 迁移](../../../docs/framework/migration-guide/migrating-from-the-net-framework-1-1.md)   
 [版本兼容性](../../../docs/framework/migration-guide/version-compatibility.md)   
 [版本和依赖关系](../../../docs/framework/migration-guide/versions-and-dependencies.md)   
 [如何：配置应用程序以支持 .NET Framework 4 或 4.5](../../../docs/framework/migration-guide/how-to-configure-an-app-to-support-net-framework-4-or-4-5.md)   
 [新增功能](../../../docs/framework/whats-new/index.md)   
 [类库中过时的内容](../../../docs/framework/whats-new/whats-obsolete.md)   
 [.NET framework 版本和程序集信息](http://go.microsoft.com/fwlink/?LinkId=201701)   
 [Microsoft .NET Framework 支持生命周期策略](http://go.microsoft.com/fwlink/?LinkId=196607)