---
title: "公共语言运行时中的类型转发 | Microsoft Docs"
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
  - "程序集 [.NET Framework]，类型转发"
  - "类型转发"
ms.assetid: 51f8ffa3-c253-4201-a3d3-c4fad85ae097
caps.latest.revision: 7
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 7
---
# 公共语言运行时中的类型转发
使用类型转发可以将类型移到另一个程序集，而不必重新编译使用原始程序集的应用程序。  
  
 例如，假设应用程序使用名为 `Utility.dll` 的程序集中的 `Example` 类。  `Utility.dll` 的开发人员可能决定重构该程序集，并且在重构过程中可能将 `Example` 类移到另一个程序集。  如果旧版本的 `Utility.dll` 由新版本的 `Utility.dll` 及其配套程序集取代，则使用 `Example` 类的应用程序将失败，因其无法在新版本的 `Utility.dll` 中找到 `Example` 类。  
  
 `Utility.dll` 的开发人员可以使用 <xref:System.Runtime.CompilerServices.TypeForwardedToAttribute> 特性转发对 `Example` 类的请求，从而避免此问题。  如果已向新版本的 `Utility.dll` 应用了该特性，则对 `Example` 类的请求将转发到该类目前所属的程序集。  现有应用程序将继续正常执行，无需重新编译。  
  
> [!NOTE]
>  在 .NET Framework 2.0 版中，无法从使用 Visual Basic 编写的程序集转发类型。  但是，用 Visual Basic 编写的应用程序可以使用经转发的类型。  也就是说，如果应用程序使用通过 C\# 或 C\+\+ 编码的程序集，并且该程序集中的某类型被转发至另一个程序集，则 Visual Basic 应用程序可以使用该转发的类型。  
  
## 转发类型  
 转发类型有四个步骤：  
  
1.  将类型的源代码从原始程序集移到目标程序集。  
  
2.  在该类型原来所属的程序集中，为被移动的类型添加 <xref:System.Runtime.CompilerServices.TypeForwardedToAttribute>。  下面的代码显示名为 `Example` 的被移动类型的特性。  
  
    ```csharp  
    [assembly:TypeForwardedToAttribute(typeof(Example))]  
    ```  
  
    ```cpp#  
    [assembly:TypeForwardedToAttribute(Example::typeid)]  
    ```  
  
3.  编译现在包含该类型的程序集。  
  
4.  重新编译该类型原来所属的程序集，其中带有对现在包含该类型的程序集的引用。  例如，如果从命令行编译一个 C\# 文件，则使用 [\/reference \(Import Metadata\)](../Topic/-reference%20\(C%23%20Compiler%20Options\).md) 选项指定包含类型的程序集。  在 C\+\+ 中，在源文件中使用 [\#using](../Topic/%23using%20Directive%20\(C++\).md) 指令指定包含类型的程序集。  
  
## 请参阅  
 <xref:System.Runtime.CompilerServices.TypeForwardedToAttribute>   
 [类型转发 \(C\+\+\/CLI\)](../Topic/Type%20Forwarding%20\(C++-CLI\).md)   
 [\#using 指令](../Topic/%23using%20Directive%20\(C++\).md)