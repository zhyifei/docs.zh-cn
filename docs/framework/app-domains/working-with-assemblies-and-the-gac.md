---
title: "使用程序集和全局程序集缓存 | Microsoft Docs"
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
  - "访问控制列表 [.NET Framework]"
  - "ACL [.NET Framework]"
  - "程序集 [.NET Framework], 全局程序集缓存"
  - "GAC（全局程序集缓存）, 优点"
  - "全局程序集缓存, 优点"
ms.assetid: 8a18e5c2-d41d-49ef-abcb-7c27e2469433
caps.latest.revision: 12
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 12
---
# 使用程序集和全局程序集缓存
如果您需要在几个应用程序间共享程序集，可将其安装到全局程序集缓存中。  安装了公共语言运行时的每台计算机均具有此计算机范围的代码缓存。  全局程序集缓存中存储了专门指定给由计算机中若干应用程序共享的程序集。  要安装到全局程序集缓存中，程序集必须具有强名称。  
  
> [!NOTE]
>  全局程序集缓存中放置的程序集必须具有相同的程序集名称和文件名（不包括文件扩展名）。  例如，程序集名称为 myAssembly 的程序集必须具有名为 myAssembly.exe 或 myAssembly.dll 的文件。  
  
 应当只在必要时才将程序集安装到全局程序集缓存中来共享程序集。  一般原则是：程序集依赖项保持专用，并在应用程序目录中定位程序集，除非明确要求共享程序集。  另外，您不必为了使 COM 互操作 或非托管代码可以访问程序集而将程序集安装到全局程序集缓存。  
  
 要将程序集安装到全局程序集缓存中的原因有以下几点：  
  
-   共享位置。  
  
     可将应用程序应该使用的程序集放在全局程序集缓存中。  例如，如果所有的应用程序都应使用位于全局程序集缓存中的程序集，则可将版本策略语句添加到 Machine.config 文件（此文件将引用重新定向到程序集）。  
  
-   文件安全性。  
  
     管理员通常使用访问控制列表 \(ACL\) 来保护 systemroot 目录，以控制写入和执行访问。  因为全局程序集缓存安装在 systemroot 目录中，它继承了该目录的 ACL。  建议只允许具有“管理员”权限的用户从全局程序集缓存中删除文件。  
  
-   并行版本控制。  
  
     可在全局程序集缓存中维护程序集的多个副本（名称相同但版本信息不同）。  
  
-   其他搜索位置。  
  
     在探测或使用配置文件中的基本代码信息之前，公共语言运行时会先检查全局程序集缓存中符合程序集请求的程序集。  
  
 请注意，在有些情况下，您肯定不需要将程序集安装到全局程序集缓存中。  如果将组成应用程序的某个程序集放在全局程序集缓存中，就无法再通过使用 XCOPY 复制应用程序目录来复制或安装应用程序。  在这种情况下，还必须将程序集移到全局程序集缓存中。  
  
## 本节内容  
 [如何：将程序集安装到全局程序集缓存](../../../docs/framework/app-domains/how-to-install-an-assembly-into-the-gac.md)  
 描述将程序集安装到全局程序集缓存的方法。  
  
 [如何：查看全局程序集缓存的内容](../../../docs/framework/app-domains/how-to-view-the-contents-of-the-gac.md)  
 解释如何使用[Gacutil.exe（全局程序集缓存工具）](../../../docs/framework/tools/gacutil-exe-gac-tool.md) 查看全局程序集缓存的内容。  
  
 [如何：从全局程序集缓存中移除程序集](../../../docs/framework/app-domains/how-to-remove-an-assembly-from-the-gac.md)  
 解释如何使用[Gacutil.exe（全局程序集缓存工具）](../../../docs/framework/tools/gacutil-exe-gac-tool.md) 从全局程序集缓存中移除程序集。  
  
 [在服务组件中使用全局程序集缓存](../../../docs/framework/app-domains/use-serviced-components-with-the-gac.md)  
 解释服务组件（托管 COM\+ 组件）为何应当放在全局程序集缓存中。  
  
## 相关章节  
 [创建程序集](../../../docs/framework/app-domains/create-assemblies.md)  
 提供创建程序集的概述。  
  
 [全局程序集缓存](../../../docs/framework/app-domains/gac.md)  
 描述全局程序集缓存。  
  
 [如何：查看程序集内容](../../../docs/framework/app-domains/how-to-view-assembly-contents.md)  
 解释如何使用 [Ildasm.exe（IL 反汇编程序）](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) 查看程序集中的 Microsoft 中间语言 \(MSIL\) 信息。  
  
 [运行时如何定位程序集](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)  
 描述公共语言运行时如何定位并加载构成应用程序的程序集。  
  
 [使用程序集编程](../../../docs/framework/app-domains/programming-with-assemblies.md)  
 描述托管应用程序的构造块 \-\- 程序集。