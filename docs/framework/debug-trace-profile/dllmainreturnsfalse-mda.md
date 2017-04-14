---
title: "dllMainReturnsFalse MDA | Microsoft Docs"
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
  - "managed debugging assistants (MDAs), DllMain returns false"
  - "DllMainReturnsFalse MDA"
  - "DllMain function"
  - "MDAs (managed debugging assistants), DllMain returns false"
ms.assetid: e2abdd04-f571-4b97-8c16-2221b8588429
caps.latest.revision: 12
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 12
---
# dllMainReturnsFalse MDA
如果用户程序集的托管 `DllMain` 函数（可以称之为 DLL\_PROCESS\_ATTACH）返回 FALSE，则将激活 `dllMainReturnsFalse` 托管调试助手 \(MDA\)。  
  
## 症状  
 `DllMain` 函数返回 FALSE，指示其没有正确执行。  这会导致一些不确定性问题，因为 `DllMain` 函数通常包含重要的初始化代码。  
  
## 原因  
 `DllMain` 可以叫做 DLL\_PROCESS\_ATTACH，用于加载时的 DLL 初始化。  如果它返回 FALSE，则意味着 DLL 初始化失败。  
  
## 解决方法  
 分析失败的 DLL 的 `DllMain` 函数的代码并找出初始化失败的原因。  
  
## 对运行时的影响  
 此 MDA 对 CLR 无任何影响。  它只报告有关 `DllMain` 的返回值的数据。  
  
## Output  
 一条指示 `DllMain` 函数（可以称之为 DLL\_PROCESS\_ATTACH）返回 FALSE 的消息。  请注意，只有在托管代码中实现 `DllMain` 时才会激活此 MDA。  
  
## 配置  
  
```  
<mdaConfig>  
  <assistants>  
    <dllMainReturnsFalse />  
  </assistants>  
</mdaConfig>  
```  
  
## 请参阅  
 [Diagnosing Errors with Managed Debugging Assistants](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)