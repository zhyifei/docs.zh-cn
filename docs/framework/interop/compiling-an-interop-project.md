---
title: "编译互操作项目 | Microsoft Docs"
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
  - "COM 互操作, 编译"
  - "COM 互操作, 公开 COM 组件"
  - "编译互操作项目"
  - "向 .NET Framework 公开 COM 组件"
  - "与非托管代码间的互操作, 编译"
  - "与非托管代码间的互操作, 公开 COM 组件"
ms.assetid: 6fcf6588-5e25-41af-b4ae-780974f2c3df
caps.latest.revision: 16
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 16
---
# 编译互操作项目
如果 COM 互操作 项目引用一个或多个包含导入 COM 类型的程序集，则可以像其他任何托管项目一样进行编译。  您可以在诸如 Visual Studio 的开发环境中引用互操作程序集，也可以在使用命令行编译器时引用互操作程序集。  在这两种情况下，若要正确地进行编译，互操作程序集必须与其他项目文件位于同一个目录中。  
  
 可以通过以下两种方式引用互操作程序集：  
  
-   嵌入互操作类型：从 [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)]和 [!INCLUDE[vs_dev10_long](../../../includes/vs-dev10-long-md.md)] 开始，您可以指示编译器将互操作程序集中的类型信息嵌入到可执行文件中。  这是推荐采用的方法。  
  
-   部署互操作程序集：您可以创建一个对互操作程序集的标准引用。  在本例中，互操作程序集必须与您的应用程序一起部署。  
  
 这两项技术之间的差异在[Using COM Types in Managed Code](http://msdn.microsoft.com/zh-cn/1a95a8ca-c8b8-4464-90b0-5ee1a1135b66)中有更详细的讨论。  
  
 [演练：嵌入 Microsoft Office 程序集中的类型信息](../Topic/Walkthrough:%20Embedding%20Type%20Information%20from%20Microsoft%20Office%20Assemblies%20\(C%23%20and%20Visual%20Basic\).md)和[演练：嵌入托管程序集中的类型](../Topic/Walkthrough:%20Embedding%20Types%20from%20Managed%20Assemblies%20\(C%23%20and%20Visual%20Basic\).md)中演示了如何通过 Visual Studio 嵌入互操作类型。  
  
 若要使用命令行编译器引用互操作程序集并将类型信息嵌入到可执行文件中，请使用 [\/link \(Link to COM Assembly\)](../Topic/-link%20\(C%23%20Compiler%20Options\).md)或 [\/link](../Topic/-link%20\(Visual%20Basic\).md) 编译器开关并指定互操作程序集的名称。  
  
> [!NOTE]
>  虽然 Visual C\+\+ 应用程序无法嵌入类型信息，但是这些应用程序可以与执行嵌入操作的应用程序或外接程序进行交互操作。  
  
 若要编译在部署时包括主互操作程序集的应用程序，请使用 **\/reference** 编译器开关并指定互操作程序集的名称。  
  
## 请参阅  
 [向 .NET Framework 公开 COM 组件](../../../docs/framework/interop/exposing-com-components.md)   
 [语言独立性和与语言无关的组件](../../../docs/standard/language-independence-and-language-independent-components.md)   
 [Using COM Types in Managed Code](http://msdn.microsoft.com/zh-cn/1a95a8ca-c8b8-4464-90b0-5ee1a1135b66)   
 [演练：嵌入 Microsoft Office 程序集中的类型信息](../Topic/Walkthrough:%20Embedding%20Type%20Information%20from%20Microsoft%20Office%20Assemblies%20\(C%23%20and%20Visual%20Basic\).md)   
 [演练：嵌入托管程序集中的类型](../Topic/Walkthrough:%20Embedding%20Types%20from%20Managed%20Assemblies%20\(C%23%20and%20Visual%20Basic\).md)   
 [将类型库当作程序集导入](../../../docs/framework/interop/importing-a-type-library-as-an-assembly.md)