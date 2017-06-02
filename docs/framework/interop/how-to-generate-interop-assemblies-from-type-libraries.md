---
title: "如何：从类型库生成互操作程序集 | Microsoft Docs"
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
  - "COM 互操作, 导入类型库"
  - "导入类型库"
  - "互操作程序集, 生成"
  - "类型库"
  - "类型库导入程序"
ms.assetid: 4afd40c3-68f2-41c5-8ec1-4951bc148b9c
caps.latest.revision: 6
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 6
---
# 如何：从类型库生成互操作程序集
[类型库导入程序 \(Tlbimp.exe\)](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md) 是一种命令行工具，它可以将包含在 COM 类型库中的 coclass 和接口转换为元数据。  此工具将自动为类型信息创建互操作程序集和命名空间。  当类的元数据变为可用时，托管客户端可以创建 COM 类型的实例并调用其方法，就像它是 .NET 实例一样。  Tlbimp.exe 一次将整个类型库转换为元数据，它不能为类型库中所定义的类型的子集生成类型信息。  
  
### 从类型库生成互操作程序集  
  
1.  使用以下命令：  
  
     **tlbimp** \<*类型库文件*\>  
  
     如果添加 **\/out:** 开关，将生成一个名称已更改的互操作程序集（如 LOANLib.dll）。  更改互操作程序集名称有助于将它同初始的 COM DLL 区分开来，并避免可能因重名而导致的问题。  
  
## 示例  
 以下命令在 `Loanlib` 命名空间中生成 Loanlib.dll 程序集。  
  
```  
tlbimp Loanlib.dll  
```  
  
 以下命令生成具有经过变动的名称 \(LOANLib.dll\) 的互操作程序集。  
  
```  
tlbimp LoanLib.dll /out: LOANLib.dll  
```  
  
## 请参阅  
 [将类型库当作程序集导入](../../../docs/framework/interop/importing-a-type-library-as-an-assembly.md)   
 [向 .NET Framework 公开 COM 组件](../../../docs/framework/interop/exposing-com-components.md)