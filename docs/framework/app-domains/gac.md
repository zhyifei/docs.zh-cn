---
title: "全局程序集缓存 | Microsoft Docs"
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
  - "缓存 [.NET Framework], 全局程序集缓存"
  - "GAC（全局程序集缓存）"
  - "全局程序集缓存"
  - "全局程序集缓存, 关于"
ms.assetid: cf5eacd0-d3ec-4879-b6da-5fd5e4372202
caps.latest.revision: 13
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 13
---
# 全局程序集缓存
安装有公共语言运行时的每台计算机都具有称为全局程序集缓存的计算机范围内的代码缓存。  全局程序集缓存中存储了专门指定给由计算机中若干应用程序共享的程序集。  
  
 应当仅在需要时才将程序集安装到全局程序集缓存中以进行共享。  一般原则是：程序集依赖项保持专用，并在应用程序目录中定位程序集，除非明确要求共享程序集。  另外，不必为了使 COM 互操作或非托管代码可以访问程序集而将程序集安装到全局程序集缓存。  
  
> [!NOTE]
>  在有些情况下，您显然不希望将程序集安装到全局程序集缓存中。  如果您将组成应用程序的某个程序集置于全局程序集缓存中，则将不再能够通过使用 **xcopy** 命令复制应用程序目录来复制或安装该应用程序。  您还必须在全局程序集缓存中移动该程序集。  
  
 有两种方法可以将程序集部署到全局程序集缓存中：  
  
-   使用专用于全局程序集缓存的安装程序。  该方法是将程序集安装到全局程序集缓存的首选方法。  
  
-   使用 [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] 提供的名为[全局程序集缓存工具 \(Gacutil.exe\)](../../../docs/framework/tools/gacutil-exe-gac-tool.md) 的开发工具。  
  
    > [!NOTE]
    >  在部署方案中，应该使用 Windows Installer 将程序集安装到全局程序集缓存中。  我们一般只在开发方案中使用全局程序集缓存工具，这是因为它不提供使用 Windows Installer 时可以提供的程序集引用计数功能和其他功能。  
  
 从 .NET Framework 4 开始，全局程序集缓存的默认位置为 **%windir%\\Microsoft.NET\\assembly**。  在 .NET Framework 的早期版本中，默认位置为 **%windir%\\assembly**。  
  
 管理员通常使用访问控制列表 \(ACL\) 来保护 systemroot 目录，以控制写入和执行访问。  因为全局程序集缓存安装在 systemroot 目录的子目录中，它继承了该目录的 ACL。  建议只允许具有“管理员”权限的用户从全局程序集缓存中删除文件。  
  
 在全局程序集缓存中部署的程序集必须具有强名称。  将一个程序集添加到全局程序集缓存时，必须对构成该程序集的所有文件执行完整性检查。  缓存执行这些完整性检查以确保程序集未被篡改（例如，当文件已更改但清单未反映此更改时）。  
  
## 请参阅  
 [公共语言运行时中的程序集](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)   
 [使用程序集和全局程序集缓存](../../../docs/framework/app-domains/working-with-assemblies-and-the-gac.md)   
 [具有强名称的程序集](../../../docs/framework/app-domains/strong-named-assemblies.md)