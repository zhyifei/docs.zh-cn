---
title: "streamWriterBufferedDataLost MDA | Microsoft Docs"
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
  - "StreamWriter class, data buffering problems"
  - "managed debugging assistants (MDAs), StreamWriter data buffering"
  - "buffers, StreamWriter problems"
  - "MDAs (managed debugging assistants), StreamWriter data buffering"
  - "StreamWriter buffered data lost"
  - "data buffering problems"
  - "streamWriterBufferedDataLost MDA"
ms.assetid: 6e5c07be-bc5b-437a-8398-8779e23126ab
caps.latest.revision: 8
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 8
---
# streamWriterBufferedDataLost MDA
当对 <xref:System.IO.StreamWriter> 执行写入，但是随后未在销毁 <xref:System.IO.StreamWriter> 的实例之前调用 <xref:System.IO.StreamWriter.Flush%2A> 或 <xref:System.IO.StreamWriter.Close%2A> 方法时，将激活 `streamWriterBufferedDataLost` 托管调试助手 \(MDA\)。  当启用此 MDA 时，运行时将确定 <xref:System.IO.StreamWriter> 中是否仍然存在任何缓冲数据。  如果不存在缓冲数据，则激活该 MDA。  调用 <xref:System.GC.Collect%2A> 和 <xref:System.GC.WaitForPendingFinalizers%2A> 方法可以强制终结器运行。  否则终结器似乎将在任意时间运行，并且可能在进程退出时根本就不运行。  在启用此 MDA 的情况下显式运行终结器将有助于更可靠地重现此类问题。  
  
## 症状  
 <xref:System.IO.StreamWriter> 未将最后 1 至 4 KB 数据写到文件。  
  
## 原因  
 <xref:System.IO.StreamWriter> 在内部缓冲数据，这需要调用 <xref:System.IO.StreamWriter.Close%2A> 或 <xref:System.IO.StreamWriter.Flush%2A> 方法将缓冲数据写到基础数据存储区。  如果没有适当地调用 <xref:System.IO.StreamWriter.Close%2A> 或 <xref:System.IO.StreamWriter.Flush%2A>，<xref:System.IO.StreamWriter> 实例中缓冲的数据可能不会按预期写出。  
  
 下面是此 MDA 应该捕获的编写得很糟糕的代码的示例。  
  
```  
// Poorly written code.  
void Write()   
{  
    StreamWriter sw = new StreamWriter("file.txt");  
    sw.WriteLine("Data");  
    // Problem: forgot to close the StreamWriter.  
}  
```  
  
 如果触发垃圾回收，然后将其挂起直至终结器完成，则上面的代码将更可靠地激活此 MDA。  若要跟踪此类问题，可以在调试版本中将下面的代码添加到上面的方法的结尾处。  这样将有助于可靠地激活 MDA，不过它并未解决此类问题的根源。  
  
```  
GC.Collect();  
GC.WaitForPendingFinalizers();  
```  
  
## 解决方法  
 在关闭具有 <xref:System.IO.StreamWriter> 的实例的应用程序或任何代码块之前，确保调用 <xref:System.IO.StreamWriter> 的 <xref:System.IO.StreamWriter.Close%2A> 或 <xref:System.IO.StreamWriter.Flush%2A>。  达到此目的的最佳机制之一是用 C\# `using` 块（在 Visual Basic 中为 `Using`）创建该实例，这样将确保调用编写器的 <xref:System.IO.StreamWriter.Dispose%2A> 方法，从而正确关闭该实例。  
  
```  
using(StreamWriter sw = new StreamWriter("file.txt"))   
{  
    sw.WriteLine("Data");  
}  
```  
  
 下面的代码演示能达到相同效果的解决方案，不过它使用的是 `try/finally` 而不是 `using`。  
  
```  
StreamWriter sw;  
try   
{  
    sw = new StreamWriter("file.txt"));  
    sw.WriteLine("Data");  
}  
finally   
{  
    if (sw != null)  
        sw.Close();  
}  
```  
  
 如果不能使用这其中任一种方案（例如，如果 <xref:System.IO.StreamWriter> 存储在静态变量中，并且在其生存期结束时很难运行代码），那么在最后使用 <xref:System.IO.StreamWriter> 之后调用其上的 <xref:System.IO.StreamWriter.Flush%2A>，或者在第一次使用它之前将 <xref:System.IO.StreamWriter.AutoFlush%2A> 属性设置为 `true`，应该会避免此问题。  
  
```  
private static StreamWriter log;  
// static class constructor.  
static WriteToFile()   
{  
    StreamWriter sw = new StreamWriter("log.txt");  
    sw.AutoFlush = true;  
  
    // Publish the StreamWriter for other threads.  
    log = sw;  
}  
```  
  
## 对运行时的影响  
 此 MDA 对运行时没有影响。  
  
## Output  
 指示发生此冲突的消息。  
  
## 配置  
  
```  
<mdaConfig>  
  <assistants>  
    <streamWriterBufferedDataLost />  
  </assistants>  
</mdaConfig>  
```  
  
## 请参阅  
 <xref:System.IO.StreamWriter>   
 [Diagnosing Errors with Managed Debugging Assistants](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)