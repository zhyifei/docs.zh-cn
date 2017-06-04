---
title: "moduloObjectHashcode MDA | Microsoft Docs"
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
  - "managed debugging assistants (MDAs), hashcode modulus"
  - "Modulo object hash code"
  - "moduloObjectHashcode MDA"
  - "hashcode modulus"
  - "MDAs (managed debugging assistants), hashcode modulus"
  - "GetHashCode method"
  - "modulus of hashcodes"
ms.assetid: b45366ff-2a7a-4b8e-ab01-537b72e9de68
caps.latest.revision: 10
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 10
---
# moduloObjectHashcode MDA
`moduloObjectHashcode` 托管调试助手 \(MDA\) 更改 <xref:System.Object> 类的行为，以便对 <xref:System.Object.GetHashCode%2A> 方法返回的哈希代码执行求模操作。  此 MDA 的模数默认为 1，这将导致 <xref:System.Object.GetHashCode%2A> 对所有对象都返回 0。  
  
## 症状  
 在迁移到公共语言运行时 \(CLR\) 的新版本后，程序不再正确执行：  
  
-   程序从 <xref:System.Collections.Hashtable> 获得错误的对象。  
  
-   <xref:System.Collections.Hashtable> 中的枚举顺序发生了导致程序中止的更改。  
  
-   以前相等的两个对象不再相等。  
  
-   以前不相等的两个对象现在相等。  
  
## 原因  
 由于 <xref:System.Collections.Hashtable> 中的键的类上的 <xref:System.Object.Equals%2A> 方法的实现通过比较 <xref:System.Object.GetHashCode%2A> 方法调用的结果测试对象是否相等，因此程序可能从 <xref:System.Collections.Hashtable> 获得错误的对象。  不应该使用哈希代码测试对象是否相等，因为即使两个对象各自的字段具有不同的值，它们也可能具有相同的哈希代码。  这些哈希代码冲突虽然在实践中很罕见，但是的确可能发生。  这对 <xref:System.Collections.Hashtable> 查找的影响是两个不相等的键似乎相等，并从 <xref:System.Collections.Hashtable> 返回错误的对象。  出于性能的考虑，<xref:System.Object.GetHashCode%2A> 的实现可能随运行时版本而改变，因此在一个版本中可能不会出现的冲突可能会在随后的版本中出现。  请启用此 MDA 测试您的代码在哈希代码冲突时是否有 bug。  当启用时，此 MDA 将导致 <xref:System.Object.GetHashCode%2A> 方法返回 0，从而引起所有哈希代码冲突。  启用此 MDA 对程序的唯一影响是程序运行得更慢。  
  
 如果用于计算键的哈希代码的算法改变，则 <xref:System.Collections.Hashtable> 中的枚举顺序可能随运行时版本而改变。  若要测试程序是否依赖哈希表的键或值的枚举顺序，可启用此 MDA。  
  
## 解决方法  
 从不使用哈希代码替换对象标识。  实现 <xref:System.Object.Equals%2A?displayProperty=fullName> 方法的重写，以便不比较哈希代码。  
  
 不要创建依赖哈希表中的键或值的枚举顺序的项。  
  
## 对运行时的影响  
 当启用此 MDA 时，应用程序将运行得更慢。  此 MDA 只是取得原本应该返回的哈希代码，改为返回除以某个模数之后得到的余数。  
  
## Output  
 此 MDA 没有输出。  
  
## 配置  
 `modulus` 特性指定对哈希代码使用的模数。  默认值为 1。  
  
```  
<mdaConfig>  
  <assistants>  
    <moduloObjectHashcode modulus="1" />  
  </assistants>  
</mdaConfig>  
```  
  
## 请参阅  
 <xref:System.Object.GetHashCode%2A?displayProperty=fullName>   
 <xref:System.Object.Equals%2A?displayProperty=fullName>   
 [Diagnosing Errors with Managed Debugging Assistants](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)