---
title: "bindingFailure MDA | Microsoft Docs"
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
  - "binding failure"
  - "binding, failures"
  - "MDAs (managed debugging assistants), binding failures"
  - "assemblies [.NET Framework], binding failures"
  - "managed debugging assistants (MDAs), binding failures"
  - "BindingFailure MDA"
ms.assetid: 26ada5af-175c-4576-931a-9f07fa1723e9
caps.latest.revision: 13
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 13
---
# bindingFailure MDA
如果程序集无法加载，则将激活 `bindingFailure` 托管调试助手 \(MDA\)。  
  
## 症状  
 代码尝试使用静态引用或加载程序方法中的一个方法（例如 <xref:System.Reflection.Assembly.Load%2A?displayProperty=fullName> 或 <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=fullName>）来加载程序集。  未加载程序集，且引发了 <xref:System.IO.FileNotFoundException> 或 <xref:System.IO.FileLoadException> 异常。  
  
## 原因  
 运行时无法加载程序集时发生绑定故障。  引起绑定故障的原因可能是以下几种情况之一：  
  
-   公共语言运行时 \(CLR\) 找不到请求的程序集。  发生这种情况的原因很多，如未安装该程序集或没有为找到该程序集正确配置应用程序。  
  
-   一个常见的出现问题的情形是：向另一个应用程序域传递一个类型，这需要 CLR 加载包含其他应用程序域中的类型的程序集。  如果其他应用程序域和原始应用程序域的配置不同，则运行时可能无法加载该程序集。  例如，两个应用程序域可能具有不同的 <xref:System.AppDomain.BaseDirectory%2A> 属性值。  
  
-   请求的程序集被损坏或不是一个程序集。  
  
-   尝试加载该程序集的代码没有正确的代码访问安全权限用于加载程序集。  
  
-   用户凭据不提供阅读文件所需的权限。  
  
## 解决方法  
 第一步要确定 CLR 未能绑定到请求的程序集的原因。  运行时找不到或无法加载请求的程序集有很多原因，例如“原因”一节列出的各种情形。  若要消除导致绑定故障的原因，建议执行以下操作：  
  
-   使用由 `bindingFailure` MDA 提供的数据确定原因：  
  
    -   运行[Fuslogvw.exe（程序集绑定日志查看器）](../../../docs/framework/tools/fuslogvw-exe-assembly-binding-log-viewer.md) 以读取由程序集联编程序生成的错误日志。  
  
    -   确定该程序集是否位于请求的位置上。  在 <xref:System.Reflection.Assembly.LoadFrom%2A> 和 <xref:System.Reflection.Assembly.LoadFile%2A> 方法中，可轻松确定请求的位置。  在 <xref:System.Reflection.Assembly.Load%2A> 方法（它使用程序集标识进行绑定）中，您必须查找与应用程序域的 <xref:System.AppDomain.BaseDirectory%2A> 属性探测路径和全局程序集缓存中的标识相匹配的程序集。  
  
-   根据上面判断出的原因解决此问题。  下面介绍可行的解决方法：  
  
    -   在全局程序集缓存中安装请求的程序集并调用  <xref:System.Reflection.Assembly.Load%2A> 方法以便按标识加载程序集。  
  
    -   将请求的程序集复制到应用程序目录中并调用 <xref:System.Reflection.Assembly.Load%2A> 方法以便按标识加载该程序集。  
  
    -   重新配置发生绑定故障的应用程序域，更改 <xref:System.AppDomain.BaseDirectory%2A> 属性或添加专用探测路径，以使该应用程序域包括该程序集路径。  
  
    -   更改文件的访问控制列表以便允许已登录的用户读取该文件。  
  
## 对运行时的影响  
 此 MDA 对 CLR 无任何影响。  它只报告有关绑定故障的数据。  
  
## Output  
 MDA 报告无法加载的程序集，包括请求的路径和\/或显示名称、绑定上下文、请求加载的应用程序域以及故障原因。  
  
 如果显示名称或请求的路径对于 CLR 不可用，则这两项数据可能为空。  如果调用 <xref:System.Reflection.Assembly.Load%2A> 方法失败，则运行时未能确定该程序集的显示名称。  
  
## 配置  
  
```  
<mdaConfig>  
  <assistants>  
    <bindingFailure />  
  </assistants>  
</mdaConfig>  
```  
  
## 示例  
 下面的代码示例演示一种可激活此 MDA 的情况：  
  
```  
using System;  
using System.Collections.Generic;  
using System.Text;  
using System.Reflection;  
namespace ConsoleApplication1  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            // This call attempts to load a nonexistent assembly.  
            // The call will throw a System.IO.FileNotFound exception  
            // and cause the activation of the bindingFailure MDA   
            // if it is registered.  
            Assembly.Load("NonExistentAssembly");  
        }  
    }  
}  
```  
  
## 请参阅  
 [Diagnosing Errors with Managed Debugging Assistants](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)