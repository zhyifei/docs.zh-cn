---
title: "loadFromContext MDA | Microsoft Docs"
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
  - "MDAs (managed debugging assistants), LoadFrom context"
  - "managed debugging assistants (MDAs), LoadFrom context"
  - "LoadFrom context"
  - "LoadFromContext MDA"
ms.assetid: a9b14db1-d3a9-4150-a767-dcf3aea0071a
caps.latest.revision: 8
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 8
---
# loadFromContext MDA
如果向 `LoadFrom` 上下文中加载了一个程序集，则将激活 `loadFromContext` 托管调试助手 \(MDA\)。  调用 <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=fullName> 或其他的类似方法时会发生这种情况。  
  
## 症状  
 使用某些加载程序方法可能会导致向 `LoadFrom` 上下文中加载程序集。  使用此上下文可导致序列化、强制转换和依赖项解析出现意外行为。  通常，建议将程序集加载到 `Load` 上下文中以避免出现这些问题。  如果不使用此 MDA，则很难确定程序集加载到了哪个上下文中。  
  
## 原因  
 通常，如果从 `Load` 上下文之外的路径（如全局程序集缓存或 <xref:System.AppDomainSetup.ApplicationBase%2A?displayProperty=fullName> 属性）加载程序集，则程序集会被加载到 `LoadFrom` 上下文中。  
  
## 解决方法  
 配置应用程序使其不再需要 <xref:System.Reflection.Assembly.LoadFrom%2A> 调用。  您可以使用以下技术来实现此目的：  
  
-   在全局程序集缓存中安装程序集。  
  
-   将程序集放置在 <xref:System.AppDomain> 的 <xref:System.AppDomainSetup.ApplicationBase%2A> 目录中。  对于默认域，<xref:System.AppDomainSetup.ApplicationBase%2A> 目录是启动进程的可执行文件所在的目录。  如果不能方便地移动程序集，则可能还需要创建一个新的 <xref:System.AppDomain>。  
  
-   如果依赖程序集位于相对于可执行文件的子目录中，则应向您的应用程序配置 \(.config\) 文件或辅助应用程序域添加一个探测路径。  
  
 在每种情况下，都可以更改代码以使用 <xref:System.Reflection.Assembly.Load%2A?displayProperty=fullName> 方法。  
  
## 对运行时的影响  
 此 MDA 对 CLR 无任何影响。  它会报告因加载请求而使用的上下文。  
  
## Output  
 此 MDA 会报告已将程序集加载到 `LoadFrom` 上下文中。  它指定该程序集的简单名称和路径。  它还建议进行迁移以避免使用 `LoadFrom` 上下文。  
  
## 配置  
  
```  
<mdaConfig>  
  <assistants>  
    <loadFromContext />  
  </assistants>  
</mdaConfig>  
```  
  
## 示例  
 下面的代码示例演示一种可激活此 MDA 的情况：  
  
```  
using System.Reflection;  
namespace ConsoleApplication1  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            // The following call caused the LoadFrom context to be used  
            // because the assembly is loaded using LoadFrom and the path is   
            // located outside of the Load context probing path.   
            Assembly.LoadFrom(@"C:\Text\Test.dll");  
        }  
    }  
}  
```  
  
## 请参阅  
 [Diagnosing Errors with Managed Debugging Assistants](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)