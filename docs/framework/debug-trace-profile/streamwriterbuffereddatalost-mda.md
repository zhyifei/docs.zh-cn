---
title: streamWriterBufferedDataLost MDA
ms.date: 03/30/2017
helpviewer_keywords:
- StreamWriter class, data buffering problems
- managed debugging assistants (MDAs), StreamWriter data buffering
- buffers, StreamWriter problems
- MDAs (managed debugging assistants), StreamWriter data buffering
- StreamWriter buffered data lost
- data buffering problems
- streamWriterBufferedDataLost MDA
ms.assetid: 6e5c07be-bc5b-437a-8398-8779e23126ab
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e20502cfd64e7e4e40bee0b815729e914c3dd4a2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54553706"
---
# <a name="streamwriterbuffereddatalost-mda"></a><span data-ttu-id="92995-102">streamWriterBufferedDataLost MDA</span><span class="sxs-lookup"><span data-stu-id="92995-102">streamWriterBufferedDataLost MDA</span></span>
<span data-ttu-id="92995-103">写入 <xref:System.IO.StreamWriter> 时，将激活 `streamWriterBufferedDataLost` 托管调试助手 (MDA)，但随后，在销毁 <xref:System.IO.StreamWriter> 的实例前不再调用 <xref:System.IO.StreamWriter.Flush%2A> 或 <xref:System.IO.StreamWriter.Close%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="92995-103">The `streamWriterBufferedDataLost` managed debugging assistant (MDA) is activated when a <xref:System.IO.StreamWriter> is written to, but the <xref:System.IO.StreamWriter.Flush%2A> or <xref:System.IO.StreamWriter.Close%2A> method is not subsequently called before the instance of the <xref:System.IO.StreamWriter> is destroyed.</span></span> <span data-ttu-id="92995-104">启用此 MDA 时，运行时确定 <xref:System.IO.StreamWriter> 内是否仍然有任何缓冲数据。</span><span class="sxs-lookup"><span data-stu-id="92995-104">When this MDA is enabled, the runtime determines whether any buffered data still exists within the <xref:System.IO.StreamWriter>.</span></span> <span data-ttu-id="92995-105">如果缓冲数据确实存在，则将激活 MDA。</span><span class="sxs-lookup"><span data-stu-id="92995-105">If buffered data does exist, the MDA is activated.</span></span> <span data-ttu-id="92995-106">调用 <xref:System.GC.Collect%2A> 和 <xref:System.GC.WaitForPendingFinalizers%2A> 方法可以强制运行终结器。</span><span class="sxs-lookup"><span data-stu-id="92995-106">Calling the <xref:System.GC.Collect%2A> and <xref:System.GC.WaitForPendingFinalizers%2A> methods can force finalizers to run.</span></span> <span data-ttu-id="92995-107">否则，终结器将似乎在任意时刻运行，并且在进程退出时可能根本没有运行。</span><span class="sxs-lookup"><span data-stu-id="92995-107">Finalizers will otherwise run at seemingly arbitrary times, and possibly not at all on process exit.</span></span> <span data-ttu-id="92995-108">在启用了此 MDA 的情况下显式运行终结器将有助于更可靠地重现此类问题。</span><span class="sxs-lookup"><span data-stu-id="92995-108">Explicitly running finalizers with this MDA enabled will help to more reliably reproduce this type of problem.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="92995-109">症状</span><span class="sxs-lookup"><span data-stu-id="92995-109">Symptoms</span></span>  
 <span data-ttu-id="92995-110"><xref:System.IO.StreamWriter> 不会将最后 1-4 KB 的数据写入文件。</span><span class="sxs-lookup"><span data-stu-id="92995-110">A <xref:System.IO.StreamWriter> does not write the last 1–4 KB of data to a file.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="92995-111">原因</span><span class="sxs-lookup"><span data-stu-id="92995-111">Cause</span></span>  
 <span data-ttu-id="92995-112"><xref:System.IO.StreamWriter> 内部缓冲数据，这要求调用 <xref:System.IO.StreamWriter.Close%2A> 或 <xref:System.IO.StreamWriter.Flush%2A> 方法将缓冲数据写入基础数据存储。</span><span class="sxs-lookup"><span data-stu-id="92995-112">The <xref:System.IO.StreamWriter> buffers data internally, which requires that the <xref:System.IO.StreamWriter.Close%2A> or <xref:System.IO.StreamWriter.Flush%2A> method be called to write the buffered data to the underlying data store.</span></span> <span data-ttu-id="92995-113">如果没有恰当调用 <xref:System.IO.StreamWriter.Close%2A> 或 <xref:System.IO.StreamWriter.Flush%2A>，则可能未按预期方式写入 <xref:System.IO.StreamWriter> 实例中缓冲的数据。</span><span class="sxs-lookup"><span data-stu-id="92995-113">If <xref:System.IO.StreamWriter.Close%2A> or <xref:System.IO.StreamWriter.Flush%2A> is not appropriately called, data buffered in the <xref:System.IO.StreamWriter> instance might not be written as expected.</span></span>  
  
 <span data-ttu-id="92995-114">以下示例为此 MDA 应捕获的编写欠佳的代码。</span><span class="sxs-lookup"><span data-stu-id="92995-114">The following is an example of poorly written code that this MDA should catch.</span></span>  
  
```csharp  
// Poorly written code.  
void Write()   
{  
    StreamWriter sw = new StreamWriter("file.txt");  
    sw.WriteLine("Data");  
    // Problem: forgot to close the StreamWriter.  
}  
```  
  
 <span data-ttu-id="92995-115">如果触发垃圾回收，则上述代码将更可靠地激活此 MDA，然后暂停，直到终结器完成操作。</span><span class="sxs-lookup"><span data-stu-id="92995-115">The preceding code will activate this MDA more reliably if a garbage collection is triggered and then suspended until finalizers have finished.</span></span> <span data-ttu-id="92995-116">要追踪此类问题，可在调试版本中将以下代码添加到上述方法的末尾。</span><span class="sxs-lookup"><span data-stu-id="92995-116">To track down this type of problem, you can add the following code to the end of the preceding method in a debug build.</span></span> <span data-ttu-id="92995-117">这将有助于稳定地激活 MDA，但当然，这不能解决问题的根源。</span><span class="sxs-lookup"><span data-stu-id="92995-117">This will help to reliably activate the MDA, but of course it does not fix the cause of the problem.</span></span>  
  
```csharp
GC.Collect();  
GC.WaitForPendingFinalizers();  
```  
  
## <a name="resolution"></a><span data-ttu-id="92995-118">解决方法</span><span class="sxs-lookup"><span data-stu-id="92995-118">Resolution</span></span>  
 <span data-ttu-id="92995-119">在关闭应用程序或具有 <xref:System.IO.StreamWriter> 实例的代码块之前，请确保在 <xref:System.IO.StreamWriter> 上调用 <xref:System.IO.StreamWriter.Close%2A> 或 <xref:System.IO.StreamWriter.Flush%2A>。</span><span class="sxs-lookup"><span data-stu-id="92995-119">Make sure you call <xref:System.IO.StreamWriter.Close%2A> or <xref:System.IO.StreamWriter.Flush%2A> on the <xref:System.IO.StreamWriter> before closing an application or any code block that has an instance of a <xref:System.IO.StreamWriter>.</span></span> <span data-ttu-id="92995-120">实现此操作的最佳机制之一是使用 C# `using` 块（Visual Basic 中为 `Using`）创建实例，这将确保调用编写器的 <xref:System.IO.StreamWriter.Dispose%2A> 方法，从而正确关闭实例。</span><span class="sxs-lookup"><span data-stu-id="92995-120">One of the best mechanisms for achieving this is creating the instance with a C# `using` block (`Using` in Visual Basic), which will ensure the <xref:System.IO.StreamWriter.Dispose%2A> method for the writer is invoked, resulting in the instance being correctly closed.</span></span>  
  
```csharp
using(StreamWriter sw = new StreamWriter("file.txt"))   
{  
    sw.WriteLine("Data");  
}  
```  
  
 <span data-ttu-id="92995-121">以下代码显示使用 `try/finally`而非 `using`）的相同解决方案。</span><span class="sxs-lookup"><span data-stu-id="92995-121">The following code shows the same solution, using `try/finally` instead of `using`.</span></span>  
  
```csharp
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
  
 <span data-ttu-id="92995-122">如果这两个解决方案都不能使用（例如，如果 <xref:System.IO.StreamWriter> 存储在静态变量中，并且无法在其生命周期结束时轻松运行代码），则通过以下方式避免此问题：在最后一次使用 <xref:System.IO.StreamWriter> 上的 <xref:System.IO.StreamWriter.Flush%2A> 之后调用它，或者将 <xref:System.IO.StreamWriter.AutoFlush%2A> 属性设置为 `true`。</span><span class="sxs-lookup"><span data-stu-id="92995-122">If neither of these solutions can be used (for example, if a <xref:System.IO.StreamWriter> is stored in a static variable and you cannot easily run code at the end of its lifetime), then calling <xref:System.IO.StreamWriter.Flush%2A> on the <xref:System.IO.StreamWriter> after its last use or setting the <xref:System.IO.StreamWriter.AutoFlush%2A> property to `true` before its first use should avoid this problem.</span></span>  
  
```csharp
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
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="92995-123">对运行时的影响</span><span class="sxs-lookup"><span data-stu-id="92995-123">Effect on the Runtime</span></span>  
 <span data-ttu-id="92995-124">此 MDA 对运行时无任何影响。</span><span class="sxs-lookup"><span data-stu-id="92995-124">This MDA has no effect on the runtime.</span></span>  
  
## <a name="output"></a><span data-ttu-id="92995-125">输出</span><span class="sxs-lookup"><span data-stu-id="92995-125">Output</span></span>  
 <span data-ttu-id="92995-126">指示发生了此冲突的消息。</span><span class="sxs-lookup"><span data-stu-id="92995-126">A message indicating that this violation occurred.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="92995-127">配置</span><span class="sxs-lookup"><span data-stu-id="92995-127">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <streamWriterBufferedDataLost />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="92995-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="92995-128">See also</span></span>
- <xref:System.IO.StreamWriter>
- [<span data-ttu-id="92995-129">使用托管调试助手诊断错误</span><span class="sxs-lookup"><span data-stu-id="92995-129">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
