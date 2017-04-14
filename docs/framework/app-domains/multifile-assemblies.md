---
title: "多文件程序集 | Microsoft Docs"
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
  - "程序集 [.NET Framework], 多文件"
  - "程序集清单, 多文件程序集"
  - "代码模块"
  - "命令行编译器"
  - "编译程序集"
  - "程序集的入口点"
  - "多文件程序集"
ms.assetid: 13509e73-db77-4645-8165-aad8dfaedff6
caps.latest.revision: 9
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 9
---
# 多文件程序集
可以使用命令行编译器或带有 Visual C\+\+ 的 [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)] 创建多文件程序集。  程序集中的一个文件必须包含程序集清单。  启动应用程序的程序集还必须包含入口点，例如 Main 或 WinMain 方法。  
  
 例如，假设您的应用程序包含 Client.cs 和 Stringer.cs 两个代码模块。  Stringer.cs 创建由 Client.cs 中的代码引用的 `myStringer` 命名空间。  Client.cs 包含 `Main` 方法，该方法是应用程序的入口点。  在此示例中，您编译两个代码模块，然后创建第三个包含程序集清单的文件（用于启动应用程序）。  程序集清单引用 `Client` 和 `Stringer` 两个模块。  
  
> [!NOTE]
>  多文件程序集只能有一个入口点，即使程序集有多个代码模块。  
  
 创建多文件程序集的原因有以下几个：  
  
-   合并用不同语言编写的模块。  这是创建多文件程序集最常见的原因。  
  
-   将不常用的类型放在只在需要时才下载的模块中，以优化应用程序的下载。  
  
    > [!NOTE]
    >  如果所创建的应用程序将使用 `<object>` 标记和 Microsoft Internet Explorer 来进行下载，那么创建多文件程序集就很重要。  在此方案中，创建与只包含程序集清单的代码模块分开的文件。  Internet Explorer 首先下载程序集清单，然后创建辅助线程以下载所需的任何其他模块或程序集。  由于正在下载包含程序集清单的文件，Internet Explorer 将不响应用户的输入。  包含程序集清单的文件越小，Internet Explorer 不作响应的时间就越短。  
  
-   合并由几个开发人员编写的代码模块。  虽然每一位开发人员都可以将各个代码模块编译成程序集，但这样会强制一些类型公开（如果所有模块均放在多文件程序集中，则不会公开）。  
  
 创建程序集后，可为包含程序集清单（并因此包含程序集）的文件签名，或者为文件（及程序集）指定强名称并将其放在全局程序集缓存中。  
  
## 请参阅  
 [如何：生成多文件程序集](../../../docs/framework/app-domains/how-to-build-a-multifile-assembly.md)   
 [使用程序集编程](../../../docs/framework/app-domains/programming-with-assemblies.md)