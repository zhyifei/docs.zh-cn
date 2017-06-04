---
title: "reentrancy MDA | Microsoft Docs"
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
  - "unmanaged code, debugging"
  - "transitioning threads unmanaged to managed code"
  - "reentrancy MDA"
  - "reentrancy without an orderly transition"
  - "managed debugging assistants (MDAs), reentrancy"
  - "illegal reentrancy"
  - "MDAs (managed debugging assistants), reentrancy"
  - "threading [.NET Framework], managed debugging assistants"
  - "managed code, debugging"
  - "native debugging, MDAs"
ms.assetid: 7240c3f3-7df8-4b03-bbf1-17cdce142d45
caps.latest.revision: 8
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 8
---
# reentrancy MDA
在先前未通过有序转换执行从托管代码到本机代码的切换的情况下，如果尝试执行从本机代码到托管代码的转换，则会激活 `reentrancy` 托管调试助手 \(MDA\)。  
  
## 症状  
 在从本机代码转换到托管代码时对象堆被破坏或发生其他严重错误。  
  
 沿任一方向在本机代码和托管代码之间进行切换的线程必须执行有序转换。  但是，操作系统中的某些底层扩展性点（例如向量异常处理程序）允许从托管代码切换到本机代码而无需执行有序转换。这些切换受操作系统控制，而不是受公共语言运行时 \(CLR\) 的控制。在这些扩展性点内执行的任何本机代码都必须避免回调入托管代码。  
  
## 原因  
 在执行托管代码时激活了某个底层操作系统扩展性点，例如向量异常处理程序。通过该扩展性点调用的应用程序代码正在尝试回调入托管代码。  
  
 此问题总是由应用程序代码引起。  
  
## 解决方法  
 检查堆栈跟踪以确定激活此 MDA 的线程。该线程正在尝试非法调入托管代码。堆栈跟踪应该显示使用此扩展性点的应用程序代码、提供此扩展性点的操作系统代码和被该扩展性点中断的托管代码。  
  
 例如，在尝试从向量异常处理程序内部调用托管代码时，您将看到该 MDA 被激活了。在堆栈上，您将看到操作系统异常处理代码和一些触发诸如 <xref:System.DivideByZeroException> 或 <xref:System.AccessViolationException> 等异常的托管代码。  
  
 在此示例中，正确的解决办法是完全以非托管代码实现向量异常处理程序。  
  
## 对运行时的影响  
 此 MDA 对 CLR 无任何影响。  
  
## Output  
 该 MDA 报告正在尝试非法重入。请检查线程的堆栈以确定发生此问题的原因以及如何更正问题。  下面是示例输出。  
  
```  
Additional Information: Attempting to call into managed code without   
transitioning out first.  Do not attempt to run managed code inside   
low-level native extensibility points. Managed Debugging Assistant   
'Reentrancy' has detected a problem in 'D:\ConsoleApplication1\  
ConsoleApplication1\bin\Debug\ConsoleApplication1.vshost.exe'.  
```  
  
## 配置  
  
```  
<mdaConfig>  
  <assistants>  
    <reentrancy />  
  </assistants>  
</mdaConfig>  
```  
  
## 示例  
 下面的代码示例导致引发 <xref:System.AccessViolationException>。在支持向量异常处理程序的 Windows 版本上，此异常将导致调用托管向量异常处理程序。如果启用了 `reentrancy` MDA，该 MDA 将在尝试从操作系统的向量异常处理支持代码调用 `MyHandler` 期间激活。  
  
```  
using System;  
public delegate int ExceptionHandler(IntPtr ptrExceptionInfo);  
  
public class Reenter   
{  
    public static ExceptionHandler keepAlive;  
  
    [System.Runtime.InteropServices.DllImport("kernel32", ExactSpelling=true,   
        CharSet=System.Runtime.InteropServices.CharSet.Auto)]  
    public static extern IntPtr AddVectoredExceptionHandler(int bFirst,   
        ExceptionHandler handler);  
  
    static int MyHandler(IntPtr ptrExceptionInfo)   
    {  
        // EXCEPTION_CONTINUE_SEARCH  
        return 0;  
    }  
    void Run() {}  
  
    static void Main()   
    {  
        keepAlive = new ExceptionHandler(Reenter.MyHandler);  
        IntPtr ret = AddVectoredExceptionHandler(1, keepAlive);  
        try   
        {  
            // Dispatch on null should AV.  
            Reenter r = null;   
            r.Run();  
        }   
        catch { }  
    }  
}  
```  
  
## 请参阅  
 [Diagnosing Errors with Managed Debugging Assistants](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)