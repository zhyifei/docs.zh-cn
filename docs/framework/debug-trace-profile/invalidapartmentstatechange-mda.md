---
title: "invalidApartmentStateChange MDA | Microsoft Docs"
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
  - "MDAs (managed debugging assistants), invalid apartment state"
  - "managed debugging assistants (MDAs), invalid apartment state"
  - "InvalidApartmentStateChange MDA"
  - "invalid apartment state changes"
  - "threading [.NET Framework], apartment states"
  - "apartment states"
  - "threading [.NET Framework], managed debugging assistants"
  - "COM apartment states"
ms.assetid: e56fb9df-5286-4be7-b313-540c4d876cd7
caps.latest.revision: 12
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 12
---
# invalidApartmentStateChange MDA
如果出现以下两个问题之一，则将激活 `invalidApartmentStateChange` 托管调试助手 \(MDS\)：  
  
-   尝试将一个线程的 COM 单元状态（已经由 COM 进行了初始化）更改为其他单元状态。  
  
-   一个线程的 COM 单元状态意外更改。  
  
## 症状  
  
-   线程的 COM 单元状态不是所请求的单元状态。  这可能会导致代理将要用于的 COM 组件的线程处理模型与当前的不同。  如果调用 COM 对象时所通过的接口不是为跨单元封送处理设置的接口，则这种模型差异进而又会导致引发 <xref:System.InvalidCastException>。  
  
-   线程的 COM 单元状态不正常。  在对 [运行时可调用包装](../../../docs/framework/interop/runtime-callable-wrapper.md) \(RCW\) 发出调用时，这可能导致 <xref:System.InvalidCastException> 以及 RPC\_E\_WRONG\_THREAD 的 HRESULT 出现 <xref:System.Runtime.InteropServices.COMException>。  这还有可能导致一些单线程 COM 组件同时由多个线程访问，进而导致损坏或数据丢失。  
  
## 原因  
  
-   早先将线程初始化成了一种不同的 COM 单元状态。  请注意，线程的单元状态既可以显式设置，也可以隐式设置。  显式操作包括 <xref:System.Threading.Thread.ApartmentState%2A?displayProperty=fullName> 属性以及 <xref:System.Threading.Thread.SetApartmentState%2A> 方法和 <xref:System.Threading.Thread.TrySetApartmentState%2A> 方法。  除非在线程启动之前调用 <xref:System.Threading.Thread.SetApartmentState%2A>，否则使用 <xref:System.Threading.Thread.Start%2A> 方法创建的线程会被隐式设置为 <xref:System.Threading.ApartmentState>。  除非在主方法上指定 <xref:System.STAThreadAttribute> 特性，否则应用程序的主线程也会被隐式初始化为 <xref:System.Threading.ApartmentState>。  
  
-   对线程调用了使用一种不同的并发模型的 `CoUninitialize` 方法（或 `CoInitializeEx` 方法）。  
  
## 解决方法  
 在线程开始执行之前设置线程的单元状态，或将 <xref:System.STAThreadAttribute> 特性或 <xref:System.MTAThreadAttribute> 特性应用于应用程序的主方法。  
  
 对于第二个原因，理想情况下，应将调用 `CoUninitialize` 方法的代码修改为延迟此调用，一直延迟到线程即将终止并且没有任何 RCW 及其基础 COM 组件仍在被线程使用为止。  但是，如果无法修改调用 `CoUninitialize` 方法的代码，则不应从那些未以此方式初始化的线程使用任何 RCW。  
  
## 对运行时的影响  
 此 MDA 对 CLR 无任何影响。  
  
## Output  
 当前线程的 COM 单元状态和代码尝试应用的状态。  
  
## 配置  
  
```  
<mdaConfig>  
  <assistants>  
    <invalidApartmentStateChange />  
  </assistants>  
</mdaConfig>  
```  
  
## 示例  
 下面的代码示例演示一种可激活此 MDA 的情况。  
  
```  
using System.Threading;  
namespace ApartmentStateMDA  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            Thread.CurrentThread.SetApartmentState(ApartmentState.STA);  
        }  
    }  
}  
```  
  
## 请参阅  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>   
 [Diagnosing Errors with Managed Debugging Assistants](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)   
 [互操作封送处理](../../../docs/framework/interop/interop-marshaling.md)