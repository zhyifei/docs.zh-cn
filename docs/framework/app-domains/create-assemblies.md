---
title: "创建程序集 | Microsoft Docs"
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
  - "程序集 [.NET Framework], 创建"
  - "程序集 [.NET Framework], 多文件"
  - "多文件程序集"
  - "单文件程序集"
ms.assetid: 54832ee9-dca8-4c8b-913c-c0b9d265e9a4
caps.latest.revision: 8
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 8
---
# 创建程序集
您可以使用 IDE（如 [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)]）或 [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] 提供的编译器和工具来创建单文件程序集或多文件程序集。  最简单的程序集是具有简单名称并载入单个应用程序域的单个文件。  此程序集无法由应用程序目录以外的其他程序集引用，并且不接受版本检查。  要卸由载程序集组成的应用程序，只需删除应用程序所在的目录即可。  对于许多开发人员而言，部署应用程序只需使用具有这些功能的程序集。  
  
 您可以从几个代码模块和资源文件中创建多文件程序集。  也可以创建可由多个应用程序共享的程序集。  共享的程序集必须具有强名称，并且可以在全局程序集缓存中部署。  
  
 将代码模块和资源分组为程序集时会有多个选项，这取决于以下因素：  
  
-   版本控制  
  
     将应具有相同版本信息的模块分组。  
  
-   部署  
  
     将支持部署模型的代码模块和资源分组。  
  
-   重复使用  
  
     将可在逻辑上一起使用以达到某目的模块分组。  例如，程序维护时不经常使用的类型和类组成的程序集可以放在同一程序集中。  此外，计划要与多个应用程序共享的类型应分组为程序集，并且程序集应使用强名称签名。  
  
-   安全性  
  
     将包含要求相同安全权限的类型的模块分组。  
  
-   限定范围  
  
     将包含其可见性应限于相同程序集的类型的模块分组。  
  
 当非托管 COM 应用程序可使用公共语言运行时程序集时，需要特殊考虑。  有关使用非托管代码的更多信息，请参见 [向 COM 公开 .NET Framework 组件](../../../docs/framework/interop/exposing-dotnet-components-to-com.md)。  
  
## 请参阅  
 [使用程序集编程](../../../docs/framework/app-domains/programming-with-assemblies.md)   
 [程序集版本控制](../../../docs/framework/app-domains/assembly-versioning.md)   
 [如何：生成单文件程序集](../../../docs/framework/app-domains/how-to-build-a-single-file-assembly.md)   
 [如何：生成多文件程序集](../../../docs/framework/app-domains/how-to-build-a-multifile-assembly.md)   
 [运行时如何定位程序集](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)   
 [多文件程序集](../../../docs/framework/app-domains/multifile-assemblies.md)