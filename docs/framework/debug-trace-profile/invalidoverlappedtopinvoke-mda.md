---
title: "invalidOverlappedToPinvoke MDA | Microsoft Docs"
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
  - "overlapped pointers"
  - "managed debugging assistants (MDAs), overlapped pointers"
  - "invalid overlapped pointer to platform invoke"
  - "InvalidOverlappedToPinvoke MDA"
  - "MDAs (managed debugging assistants), overlapped pointers"
  - "pointers, overlapped"
ms.assetid: 28876047-58bd-4fed-9452-c7da346d67c0
caps.latest.revision: 14
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 14
---
# invalidOverlappedToPinvoke MDA
当将不是在垃圾回收堆上创建的重叠指针传递给特定的 Win32 函数时，将激活 `invalidOverlappedToPinvoke` 托管调试助手 \(MDA\)。  
  
> [!NOTE]
>  默认情况下，仅当代码中定义了平台调用，并且调试器报告每个方法的 JustMyCode 状态（请参见）时，此 MDA 才会被激活。  不理解 JustMyCode 的调试器（例如无扩展的 MDbg.exe）不会激活此 MDA。  可以使用配置文件并在 .mda.config 文件 `(<invalidOverlappedToPinvoke enable="true" justMyCode="false"/>` 中显式设置 `justMyCode="false"` 来为那些调试器启用此 MDA。  
  
## 症状  
 崩溃或无法解释的堆损坏。  
  
## 原因  
 将不是在垃圾回收堆上创建的重叠指针传递给了特定的操作系统函数。  
  
 下表显示了此 MDA 跟踪的函数。  
  
|模块|功能|  
|--------|--------|  
|HttpApi.dll|`HttpReceiveHttpRequest`|  
|IpHlpApi.dll|`NotifyAddrChange`|  
|kernel32.dll|`ReadFile`|  
|kernel32.dll|`ReadFileEx`|  
|kernel32.dll|`WriteFile`|  
|kernel32.dll|`WriteFileEx`|  
|kernel32.dll|`ReadDirectoryChangesW`|  
|kernel32.dll|`PostQueuedCompletionStatus`|  
|MSWSock.dll|`ConnectEx`|  
|WS2\_32.dll|`WSASend`|  
|WS2\_32.dll|`WSASendTo`|  
|WS2\_32.dll|`WSARecv`|  
|WS2\_32.dll|`WSARecvFrom`|  
|MQRT.dll|`MQReceiveMessage`|  
  
 此条件损坏堆的可能性很大，因为发出调用的 <xref:System.AppDomain> 可能卸载。  如果 <xref:System.AppDomain> 卸载，应用程序代码或者将释放重叠指针的内存，从而在操作完成时导致损坏；或者该代码将泄漏内存，从而在稍后带来难题。  
  
## 解决方法  
 使用 <xref:System.Threading.Overlapped> 对象调用 <xref:System.Threading.Overlapped.Pack%2A> 方法，以获取能够传递给函数的 <xref:System.Threading.NativeOverlapped> 结构。  如果 <xref:System.AppDomain> 卸载，CLR 将等待直至异步操作完成，然后才释放指针。  
  
## 对运行时的影响  
 此 MDA 对 CLR 没有影响。  
  
## Output  
 下面是来自此 MDA 的输出的示例。  
  
 `An overlapped pointer (0x00ea3430) that was not allocated on the GC heap was passed via Pinvoke to the Win32 function 'WriteFile' in module 'KERNEL32.DLL'.  If the AppDomain is shut down, this can cause heap corruption when the async I/O completes.  The best solution is to pass a NativeOverlapped structure retrieved from a call to System.Threading.Overlapped.Pack().  If the AppDomain exits, the CLR will keep this structure alive and pinned until the I/O completes.`  
  
## 配置  
  
```  
<mdaConfig>  
  <assistants>  
    <invalidOverlappedToPinvoke/>  
  </assistants>  
</mdaConfig>  
```  
  
## 请参阅  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>   
 [Diagnosing Errors with Managed Debugging Assistants](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)   
 [互操作封送处理](../../../docs/framework/interop/interop-marshaling.md)