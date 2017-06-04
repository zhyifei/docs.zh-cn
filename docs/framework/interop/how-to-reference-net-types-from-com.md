---
title: "如何：从 COM 中引用 .NET 类型 | Microsoft Docs"
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
  - "COM 互操作, 引用 .NET 类型"
  - "导入类型库"
  - "与非托管代码间的互操作, 导入类型库"
  - "与非托管代码间的互操作, 引用 .NET 类型"
  - "引用 .NET 类型"
  - "类型库"
ms.assetid: 54917f6f-cb18-4103-b622-856b55da93f3
caps.latest.revision: 7
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 7
---
# 如何：从 COM 中引用 .NET 类型
就客户端和服务器代码而言，COM 和 .NET Framework 之间大多数差异都是不可见的。  Microsoft Visual Basic 客户端可以在对象浏览器中查看 .NET 对象，该浏览器将公开对象方法及语法、属性和字段，就像该对象是其他任何 COM 对象一样。  
  
 对于 C\+\+ 客户端，虽然可以使用相同的工具将元数据导出到 COM 类型库中，但导入类型库的过程要略微复杂一些。  要从非托管的 C\+\+ 客户端引用 .NET 对象成员，应使用 **\#import** 指令引用 TLB 文件（用 Tlbexp.exe 生成）。  从 C\+\+ 中引用类型库时，必须指定 **raw\_interfaces\_only** 选项或导入基类库 Mscorlib.tlb 中的定义。  
  
### 导入库  
  
-   在 **\#import** 指令中指定 **raw\_interfaces\_only** 选项。  例如：  
  
    ```cpp  
    #import "..\LoanLib\LoanLib.tlb" raw_interfaces_only  
    ```  
  
     \- 或 \-  
  
-   包括 Mscorlib.tlb 的 \#import 指令。  例如：  
  
    ```cpp  
    #import "mscorlib.tlb"  
    #import "..\LoanLib\LoanLib.tlb"  
    ```  
  
## 请参阅  
 [向 COM 公开 .NET Framework 组件](../../../docs/framework/interop/exposing-dotnet-components-to-com.md)   
 [向 COM 注册程序集](../../../docs/framework/interop/registering-assemblies-with-com.md)   
 [Calling a .NET Object](http://msdn.microsoft.com/zh-cn/40c9626c-aea6-4bad-b8f0-c1de462efd33)   
 [Deploying an Application for COM Access](http://msdn.microsoft.com/zh-cn/fb63564c-c1b9-4655-a094-a235625882ce)