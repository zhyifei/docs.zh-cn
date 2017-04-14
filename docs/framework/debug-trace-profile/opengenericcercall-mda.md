---
title: "openGenericCERCall MDA | Microsoft Docs"
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
  - "MDAs (managed debugging assistants), CER calls"
  - "open generic CER calls"
  - "constrained execution regions"
  - "openGenericCERCall MDA"
  - "CER calls"
  - "managed debugging assistants (MDAs), CER calls"
  - "generics [.NET Framework], open generic CER calls"
ms.assetid: da3e4ff3-2e67-4668-9720-fa776c97407e
caps.latest.revision: 13
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 13
---
# openGenericCERCall MDA
激活 `openGenericCERCall` 托管调试助手是为了警告正在 JIT 编译时或在生成本机映像时处理根方法中带有泛型类型变量的受约束执行区域 \(CER\) 关系图，并且其中至少有一个泛型类型变量是对象引用类型。  
  
## 症状  
 CER 代码未在线程被中止或应用程序域被卸载时运行。  
  
## 原因  
 在 JIT 编译时，包含对象引用类型的实例化只是一个代表，因为结果代码是共享的，并且每个对象引用类型变量可以是任何对象引用类型。  这样将无需提前准备某些运行时资源。  
  
 特别是，具有泛型类型变量的方法可以以非紧急方式在后台分配资源。  这些被称为泛型字典条目。  例如，对于语句 `List<T> list = new List<T>();` ，其中 `T` 是运行时必须查找并且可能会在运行时创建确切的实例化（例如 `List<Object>, List<String>` `` 等等）的泛型类型变量。  这可能因各种原因失败，这些原因超出了开发人员的控制范围，例如内存不足。  
  
 此 MDA 只应在 JIT 编译时激活，而不应在存在确切的实例化时激活。  
  
 当此 MDA 被激活时，可能的症状是 CER 对错误的实例化不起作用。  事实上，运行时并未尝试在导致 MDA 被激活的情况下实现 CER。  因此如果开发人员使用 CER 的共享实例化，则未捕获预期 CER 的区域中的 JIT 编译错误、泛型类型加载错误或线程中止。  
  
## 解决方法  
 不要对可能包含 CER 的方法使用对象引用类型的泛型类型变量。  
  
## 对运行时的影响  
 此 MDA 对 CLR 无任何影响。  
  
## Output  
 下面是来自此 MDA 的输出的示例。  
  
 `Method 'GenericMethodWithCer', which contains at least one constrained execution region, cannot be prepared automatically since it has one or more unbound generic type parameters.`  
  
 `The caller must ensure this method is prepared explicitly at run time prior to execution.`  
  
 `method name="GenericMethodWithCer"`  
  
 `declaringType name="OpenGenericCERCall"`  
  
## 配置  
  
```  
<mdaConfig>  
  <assistants>  
    <openGenericCERCall/>  
  </assistants>  
</mdaConfig>  
```  
  
## 示例  
 未执行 CER 代码。  
  
```  
using System;  
using System.Collections.Generic;  
using System.Runtime.CompilerServices;  
  
class Program  
{  
    static void Main(string[] args)  
    {  
        CallGenericMethods();  
    }  
    static void CallGenericMethods()  
    {  
        // This call is correct. The instantiation of the method  
        // contains only nonreference types.  
        MyClass.GenericMethodWithCer<int>();  
  
        // This call is incorrect. A shared version of the method that  
        // cannot be completely analyzed will be JIT-compiled. The   
        // MDA will be activated at JIT-compile time, not at run time.  
        MyClass.GenericMethodWithCer<String>();  
    }  
}  
  
    class MyClass  
{  
    public static void GenericMethodWithCer<T>()  
    {  
        RuntimeHelpers.PrepareConstrainedRegions();  
        try  
        {  
  
        }  
        finally  
        {  
            // This is the start of the CER.  
            Console.WriteLine("In finally block.");  
        }  
    }  
}  
```  
  
## 请参阅  
 <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareMethod%2A>   
 <xref:System.Runtime.ConstrainedExecution>   
 [Diagnosing Errors with Managed Debugging Assistants](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)