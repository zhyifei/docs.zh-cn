---
title: "memberInfoCacheCreation MDA | Microsoft Docs"
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
  - "member info cache creation"
  - "MemberInfoCacheCreation MDA"
  - "reflection, run-time errors"
  - "MDAs (managed debugging assistants), cache"
  - "cache [.NET Framework], reflection"
  - "managed debugging assistants (MDAs), cache"
  - "MemberInfo cache"
ms.assetid: 5abdad23-1335-4744-8acb-934002c0b6fe
caps.latest.revision: 8
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 8
---
# memberInfoCacheCreation MDA
`memberInfoCacheCreation` 托管调试助手 \(MDA\) 在创建 <xref:System.Reflection.MemberInfo> 缓存时被激活。  这种强烈迹象表明程序正在利用资源昂贵的反射功能。  
  
## 症状  
 程序的工作集增加了，因为程序正在使用资源昂贵的反射。  
  
## 原因  
 涉及 <xref:System.Reflection.MemberInfo> 对象的反射操作被认为是资源昂贵的，因为它们必须读取存储在冷页 \(cold page\) 中的元数据，并且它们一般指示程序正在使用某种类型的后期绑定方案。  
  
## 解决方法  
 通过启用此 MDA 然后在调试器中运行代码，或者在激活 MDA 时附加一个调试器，您可以确定程序中正在使用反射的位置。  在调试器下将获得堆栈跟踪，该跟踪表明 <xref:System.Reflection.MemberInfo> 缓存的创建位置，并且从该位置可以确定程序正在使用反射的位置。  
  
 该解决方案依赖代码的目标。  此 MDA 警告您程序具有后期绑定方案。  您可能想要确定能否替换早期绑定方案，或考虑后期绑定方案的性能。  
  
## 对运行时的影响  
 所创建的每个 <xref:System.Reflection.MemberInfo> 缓存都将激活此 MDA。  性能影响可忽略。  
  
## Output  
 该 MDA 输出一条消息，指示已创建 <xref:System.Reflection.MemberInfo> 缓存。  可使用调试器获取堆栈跟踪，该跟踪表明程序中正在使用反射的位置。  
  
## 配置  
  
```  
<mdaConfig>  
  <assistants>  
    <memberInfoCacheCreation/>  
  </assistants>  
</mdaConfig>  
```  
  
## 示例  
 此代码示例将激活 `memberInfoCacheCreation` MDA。  
  
```  
using System;  
  
public class Exe  
{  
    public static void Main()  
    {  
        typeof(object).GetMethods();  
    }  
}  
```  
  
## 请参阅  
 <xref:System.Reflection.MemberInfo>   
 [Diagnosing Errors with Managed Debugging Assistants](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)