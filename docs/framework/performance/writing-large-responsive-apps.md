---
title: 编写大型的响应式 .NET Framework 应用
ms.date: 03/30/2017
ms.assetid: 123457ac-4223-4273-bb58-3bc0e4957e9d
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 846d41c31687df98b019f103e42cf586a23d8ff1
ms.sourcegitcommit: 43924acbdbb3981d103e11049bbe460457d42073
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/23/2018
---
# <a name="writing-large-responsive-net-framework-apps"></a><span data-ttu-id="1c0b9-102">编写大型的响应式 .NET Framework 应用</span><span class="sxs-lookup"><span data-stu-id="1c0b9-102">Writing Large, Responsive .NET Framework Apps</span></span>
<span data-ttu-id="1c0b9-103">本文提供用于改进大型 .NET Framework 应用或处理大量数据（如文件或数据库）的应用的性能的提示。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-103">This article provides tips for improving the performance of large .NET Framework apps, or apps that process a large amount of data such as files or databases.</span></span> <span data-ttu-id="1c0b9-104">这些提示来自在托管代码中重写的 C# 和 Visual Basic 编译器，并且本文包括来自 C# 编译器的几个真实示例。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-104">These tips come from rewriting the C# and Visual Basic compilers in managed code, and this article includes several real examples from the C# compiler.</span></span>  
  
 <span data-ttu-id="1c0b9-105">.NET Framework 构建应用的效率极高。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-105">The .NET Framework is highly productive for building apps.</span></span>  <span data-ttu-id="1c0b9-106">功能强大且安全的语言以及丰富的库集合使应用构建富有成果。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-106">Powerful and safe languages and a rich collection of libraries make app building highly fruitful.</span></span>  <span data-ttu-id="1c0b9-107">然而，伴随高效率而来的是责任问题。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-107">However, with great productivity comes responsibility.</span></span>  <span data-ttu-id="1c0b9-108">你应该使用 .NET Framework 的所有功能，但随时准备在需要时调整你的代码性能。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-108">You should use all the power of the .NET Framework, but be prepared to tune your code’s performance when needed.</span></span>  
  
## <a name="why-the-new-compiler-performance-applies-to-your-app"></a><span data-ttu-id="1c0b9-109">为什么新的编译器性能适用于你的应用</span><span class="sxs-lookup"><span data-stu-id="1c0b9-109">Why the new compiler performance applies to your app</span></span>  
 <span data-ttu-id="1c0b9-110">.NET Compiler Platform ("Roslyn") 团队在托管代码中重写了 C# 和 Visual Basic 编译器，以提供新的 API 来建模和分析代码、构建工具，并在 Visual Studio 中实现更丰富、代码识别的体验。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-110">The .NET Compiler Platform ("Roslyn") team rewrote the C# and Visual Basic compilers in managed code to provide new APIs for modeling and analyzing code, building tools, and enabling much richer, code-aware experiences in Visual Studio.</span></span>  <span data-ttu-id="1c0b9-111">重写编译器和在新编译器上构建 Visual Studio 体验揭示了实用的性能见解，该见解适用于任何大型 .NET Framework 应用或任何用于处理大量数据的应用。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-111">Rewriting the compilers and building Visual Studio experiences on the new compilers revealed useful performance insights that are applicable to any large .NET Framework app or any app that processes a lot of data.</span></span>  <span data-ttu-id="1c0b9-112">要利用来自 C# 编译器的见解和示例，你并不需要了解编译器本身。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-112">You don't need to know about compilers to take advantage of the insights and examples from the C# compiler.</span></span>  
  
 <span data-ttu-id="1c0b9-113">Visual Studio 使用编译器 API 来构建所有用户喜爱的 IntelliSense 功能，例如标识符和关键字着色、语法完成列表、错误的波形曲线、参数提示、代码问题报告以及代码操作。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-113">Visual Studio uses the compiler APIs to build all the IntelliSense features that users love, such as colorization of identifiers and keywords, syntax completion lists, squiggles for errors, parameter tips, code issues, and code actions.</span></span>  <span data-ttu-id="1c0b9-114">Visual Studio 可在开发人员键入和更改他们的代码时提供这种帮助，并且 Visual Studio 必须在编译器不断建模开发人员编辑的代码时保持响应。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-114">Visual Studio provides this help while developers are typing and changing their code, and Visual Studio must remain responsive while the compiler continually models the code developers edit.</span></span>  
  
 <span data-ttu-id="1c0b9-115">当你的最终用户与你的应用交互时，他们期望应用能够响应。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-115">When your end users interact with your app, they expect it to be responsive.</span></span>  <span data-ttu-id="1c0b9-116">永远不应阻止键入或命令处理。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-116">Typing or command handling should never be blocked.</span></span>  <span data-ttu-id="1c0b9-117">帮助应该迅速弹出，如果用户继续键入则帮助应中止。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-117">Help should pop up quickly or give up if the user continues typing.</span></span>  <span data-ttu-id="1c0b9-118">你的应用应该避免通过使应用感觉迟钝的长计算阻止 UI 线程。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-118">Your app should avoid blocking the UI thread with long computations that make the app feel sluggish.</span></span>  
  
 <span data-ttu-id="1c0b9-119">有关 Roslyn 编译器的详细信息，请访问[dotnet/roslyn](https://github.com/dotnet/roslyn) GitHub 上的存储库。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-119">For more information about Roslyn compilers, visit the [dotnet/roslyn](https://github.com/dotnet/roslyn) repo on GitHub.</span></span>
 <!-- TODO: replace with link to Roslyn conceptual docs once that's published -->
  
## <a name="just-the-facts"></a><span data-ttu-id="1c0b9-120">事实小结</span><span class="sxs-lookup"><span data-stu-id="1c0b9-120">Just the Facts</span></span>  
 <span data-ttu-id="1c0b9-121">在优化性能和创建响应性 .NET Framework 应用时，请考虑以下事实。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-121">Consider these facts when tuning performance and creating responsive .NET Framework apps.</span></span>  
  
### <a name="fact-1-dont-prematurely-optimize"></a><span data-ttu-id="1c0b9-122">事实 1：切勿过早优化</span><span class="sxs-lookup"><span data-stu-id="1c0b9-122">Fact 1: Don’t prematurely optimize</span></span>  
 <span data-ttu-id="1c0b9-123">编写比实际需要更为复杂的代码，将产生维护、调试和改进成本。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-123">Writing code that is more complex than it needs to be incurs maintenance, debugging, and polishing costs.</span></span>  <span data-ttu-id="1c0b9-124">有经验的程序员对如何解决编码问题并编写出更高效的代码有一个直观的把握。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-124">Experienced programmers have an intuitive grasp of how to solve coding problems and write more efficient code.</span></span>  <span data-ttu-id="1c0b9-125">然而，有时他们过早地优化了代码。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-125">However, they sometimes prematurely optimize their code.</span></span>  <span data-ttu-id="1c0b9-126">例如，当一个简单的数组就足够的时候，他们却使用哈希表或使用可能泄漏内存的复杂缓存，而不是简单地重新计算值。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-126">For example, they use a hash table when a simple array would suffice, or use complicated caching that may leak memory instead of simply recomputing values.</span></span>  <span data-ttu-id="1c0b9-127">即使你是一个有经验的程序员，当你发现问题时，应该测试性能并分析你的代码。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-127">Even if you’re an experience programmer, you should test for performance and analyze your code when you find issues.</span></span>  
  
### <a name="fact-2-if-youre-not-measuring-youre-guessing"></a><span data-ttu-id="1c0b9-128">事实 2：若不测量，便只是猜测</span><span class="sxs-lookup"><span data-stu-id="1c0b9-128">Fact 2: If you’re not measuring, you’re guessing</span></span>  
 <span data-ttu-id="1c0b9-129">配置文件和度量不会撒谎。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-129">Profiles and measurements don’t lie.</span></span>  <span data-ttu-id="1c0b9-130">配置文件向你显示 CPU 是否已满或者你是否在磁盘 I/O 上受阻。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-130">Profiles show you whether the CPU is fully loaded or whether you’re blocked on disk I/O.</span></span>  <span data-ttu-id="1c0b9-131">配置文件可告知正在分配的内存类型和大小，以及 CPU 是否在[垃圾回收](../../../docs/standard/garbage-collection/index.md) (GC) 中花费了大量的时间。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-131">Profiles tell you what kind and how much memory you’re allocating and whether your CPU is spending a lot of time in [garbage collection](../../../docs/standard/garbage-collection/index.md) (GC).</span></span>  
  
 <span data-ttu-id="1c0b9-132">你应该为应用中的关键客户体验或方案设定性能目标，并编写测试来测量性能。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-132">You should set performance goals for key customer experiences or scenarios in your app and write tests to measure performance.</span></span>  <span data-ttu-id="1c0b9-133">应用科学的方法调查失败的测试：使用配置文件来指导你、假设有可能是什么问题，并用利用试验或代码更改来测试你的假设。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-133">Investigate failing tests by applying the scientific method: use profiles to guide you, hypothesize what the issue might be, and test your hypothesis with an experiment or code change.</span></span>  <span data-ttu-id="1c0b9-134">使用定期测试建立一段时间内的基线性能测量，以便你可以隔离导致性能衰退的更改。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-134">Establish baseline performance measurements over time with regular testing, so you can isolate changes that cause regressions in performance.</span></span>  <span data-ttu-id="1c0b9-135">通过以严格的方式处理性能工作，你可以避免将时间浪费在不需要的代码更新上。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-135">By approaching performance work in a rigorous way, you’ll avoid wasting time with code updates you don’t need.</span></span>  
  
### <a name="fact-3-good-tools-make-all-the-difference"></a><span data-ttu-id="1c0b9-136">事实 3：好的工具将使一切大不相同</span><span class="sxs-lookup"><span data-stu-id="1c0b9-136">Fact 3: Good tools make all the difference</span></span>  
 <span data-ttu-id="1c0b9-137">好的工具可以让你快速深入地了解最大的性能问题（CPU、内存或磁盘）并帮助你找到导致那些瓶颈的代码。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-137">Good tools let you drill quickly into the biggest performance issues (CPU, memory, or disk) and help you locate the code that causes those bottlenecks.</span></span>  <span data-ttu-id="1c0b9-138">Microsoft 提供多种性能工具，如 [Visual Studio 探查器](/visualstudio/profiling/beginners-guide-to-performance-profiling)、[Windows Phone 分析工具](http://msdn.microsoft.com/library/e67e3199-ea43-4d14-ab7e-f7f19266253f)和 [PerfView](http://www.microsoft.com/download/details.aspx?id=28567)。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-138">Microsoft ships a variety of performance tools such as [Visual Studio Profiler](/visualstudio/profiling/beginners-guide-to-performance-profiling), [Windows Phone Analysis Tool](http://msdn.microsoft.com/library/e67e3199-ea43-4d14-ab7e-f7f19266253f), and [PerfView](http://www.microsoft.com/download/details.aspx?id=28567).</span></span>  
  
 <span data-ttu-id="1c0b9-139">PerfView 是一个免费且功能极为强大的工具，它可以帮助你专注于深层问题，如磁盘 I/O、GC 事件和内存。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-139">PerfView is a free and amazingly powerful tool that helps you focus on deep issues such as disk I/O, GC events, and memory.</span></span>  <span data-ttu-id="1c0b9-140">可以捕获与性能相关的 [Windows 事件跟踪](../../../docs/framework/wcf/samples/etw-tracing.md) (ETW) 事件，并很轻松地查看每个应用、每个进程、每个堆栈和每个线程信息。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-140">You can capture performance-related [Event Tracing for Windows](../../../docs/framework/wcf/samples/etw-tracing.md) (ETW) events and view easily per app, per process, per stack, and per thread information.</span></span>  <span data-ttu-id="1c0b9-141">PerfView 向你显示应用分配了多少内存以及分配了何种内存，并显示哪些函数或调用堆栈提供了内存分配以及他们提供了多少。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-141">PerfView shows you how much and what kind of memory your app allocates, and which functions or call stacks contribute how much to the memory allocations.</span></span> <span data-ttu-id="1c0b9-142">有关详细信息，请参见丰富的帮助主题、演示以及工具随附的视频（如第 9 频道上的 [PerfView 教程](http://channel9.msdn.com/Series/PerfView-Tutorial)）。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-142">For details, see the rich help topics, demos, and videos included with the tool (such as the [PerfView tutorials](http://channel9.msdn.com/Series/PerfView-Tutorial) on Channel 9).</span></span>  
  
### <a name="fact-4-its-all-about-allocations"></a><span data-ttu-id="1c0b9-143">事实 4：一切皆与分配有关</span><span class="sxs-lookup"><span data-stu-id="1c0b9-143">Fact 4: It’s all about allocations</span></span>  
 <span data-ttu-id="1c0b9-144">你可能会认为构建一个响应性 .NET Framework 应用只与算法（如使用快速排序，而不是气泡排序）相关，但事实并非如此。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-144">You might think that building a responsive .NET Framework app is all about algorithms, such as using quick sort instead of bubble sort, but that's not the case.</span></span>  <span data-ttu-id="1c0b9-145">构建一个响应性应用的最关键因素是分配内存，尤其是当你的应用非常大或需要处理大量数据的时候。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-145">The biggest factor in building a responsive app is allocating memory, especially when your app is very large or processes large amounts of data.</span></span>  
  
 <span data-ttu-id="1c0b9-146">几乎所有使用新编译器 API 来构建响应性 IDE 体验的工作，均涉及到避免分配和管理缓存策略。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-146">Almost all the work to build responsive IDE experiences with the new compiler APIs involved avoiding allocations and managing caching strategies.</span></span>  <span data-ttu-id="1c0b9-147">PerfView 跟踪显示新的 C# 和 Visual Basic 编译器的性能很少受 CPU 约束。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-147">PerfView traces show that the performance of the new C# and Visual Basic compilers is rarely CPU bound.</span></span>  <span data-ttu-id="1c0b9-148">在读取数十万行或数百万行的代码、读取元数据或发出生成的代码时，编译器可能会受 I/O 约束。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-148">The compilers can be I/O bound when reading hundreds of thousands or millions of lines of code, reading metadata, or emitting generated code.</span></span>  <span data-ttu-id="1c0b9-149">所有 UI 线程延迟几乎都是由垃圾回收造成的。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-149">The UI thread delays are nearly all due to garbage collection.</span></span>  <span data-ttu-id="1c0b9-150">.NET Framework GC 的性能经过高度优化，能够在执行应用代码的同时，并行完成其大部分工作。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-150">The .NET Framework GC is highly tuned for performance and does much of its work concurrently while app code executes.</span></span>  <span data-ttu-id="1c0b9-151">但是，单个分配可能会触发昂贵的 [gen2](../../../docs/standard/garbage-collection/fundamentals.md) 回收，从而停止所有线程。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-151">However, a single allocation can trigger an expensive [gen2](../../../docs/standard/garbage-collection/fundamentals.md) collection, stopping all threads.</span></span>  
  
## <a name="common-allocations-and-examples"></a><span data-ttu-id="1c0b9-152">常见的分配和示例</span><span class="sxs-lookup"><span data-stu-id="1c0b9-152">Common allocations and examples</span></span>  
 <span data-ttu-id="1c0b9-153">本部分中的示例表达式具有看起来较小的隐藏分配。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-153">The example expressions in this section have hidden allocations that appear small.</span></span>  <span data-ttu-id="1c0b9-154">但是，如果一个大型应用执行表达式足够多次数，表达式可以产生数百个 MB，甚至 GB 的分配。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-154">However, if a large app executes the expressions enough times, they can causes hundreds of megabytes, even gigabytes, of allocations.</span></span>  <span data-ttu-id="1c0b9-155">例如，一分钟的测试以模拟开发人员在编辑器中键入分配的内存（以 GB 为单位），并带领性能团队专注于键入方案。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-155">For example, one-minute tests that simulated a developer’s typing in the editor allocated gigabytes of memory and led the performance team to focus on typing scenarios.</span></span>  
  
### <a name="boxing"></a><span data-ttu-id="1c0b9-156">装箱</span><span class="sxs-lookup"><span data-stu-id="1c0b9-156">Boxing</span></span>  
 <span data-ttu-id="1c0b9-157">当通常存在于堆栈或数据结构中的值类型包装在一个对象中时，[装箱](~/docs/csharp/programming-guide/types/boxing-and-unboxing.md)便会发生。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-157">[Boxing](~/docs/csharp/programming-guide/types/boxing-and-unboxing.md) occurs when value types that normally live on the stack or in data structures are wrapped in an object.</span></span>  <span data-ttu-id="1c0b9-158">即，你分配一个对象以保存数据，然后将一个指针返回到该对象。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-158">That is, you allocate an object to hold the data, and then return a pointer to the object.</span></span>  <span data-ttu-id="1c0b9-159">.NET Framework 有时由于方法的签名或存储位置的类型而装箱值。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-159">The .NET Framework sometimes boxes values due to the signature of a method or the type of a storage location.</span></span>  <span data-ttu-id="1c0b9-160">在一个对象中包装值类型导致内存分配。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-160">Wrapping a value type in an object causes memory allocation.</span></span>  <span data-ttu-id="1c0b9-161">许多装箱操作可以向你的应用提供分配（以 MB 或 GB 为单位），这意味着你的应用将产生更多的 GC。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-161">Many boxing operations can contribute megabytes or gigabytes of allocations to your app, which means that your app will cause more GCs.</span></span> <span data-ttu-id="1c0b9-162">.NET Framework 和语言编译器应尽可能地避免装箱，但有时它会在最不经意的时候发生。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-162">The .NET Framework and the language compilers avoid boxing when possible, but sometimes it happens when you least expect it.</span></span>  
  
 <span data-ttu-id="1c0b9-163">若要查看 PerfView 中的装箱，打开跟踪，并在你的应用的进程名称（请记住，PerfView 报告所有进程）下查看 GC Heap Alloc Stack。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-163">To see boxing in PerfView, open a trace and look at GC Heap Alloc Stacks under your app’s process name (remember, PerfView reports on all processes).</span></span>  <span data-ttu-id="1c0b9-164">如果你在分配下看到类似于 <xref:System.Int32?displayProperty=nameWithType> 和 <xref:System.Char?displayProperty=nameWithType> 的类型，即表示你正在装箱值类型。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-164">If you see types like <xref:System.Int32?displayProperty=nameWithType> and <xref:System.Char?displayProperty=nameWithType> under allocations, you are boxing value types.</span></span>  <span data-ttu-id="1c0b9-165">选择这些类型中一个，将显示它们在其中装箱的堆栈和函数。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-165">Choosing one of these types will show the stacks and functions in which they are boxed.</span></span>  
  
 <span data-ttu-id="1c0b9-166">**示例 1：字符串方法和值类型参数**</span><span class="sxs-lookup"><span data-stu-id="1c0b9-166">**Example 1: string methods and value type arguments**</span></span>  
  
 <span data-ttu-id="1c0b9-167">此示例代码演示了潜在不必要的和过度的装箱：</span><span class="sxs-lookup"><span data-stu-id="1c0b9-167">This sample code illustrates potentially unnecessary and excessive boxing:</span></span>  
  
```csharp  
public class Logger  
{  
    public static void WriteLine(string s) { /*...*/ }  
}  
  
public class BoxingExample  
{  
    public void Log(int id, int size)  
    {  
        var s = string.Format("{0}:{1}", id, size);  
        Logger.WriteLine(s);  
    }  
}  
```  
  
 <span data-ttu-id="1c0b9-168">此代码提供登录功能，因此应用可以经常（可能是几百万次）调用 `Log` 函数。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-168">This code provides logging functionality, so an app may call the `Log` function frequently, maybe millions of times.</span></span>  <span data-ttu-id="1c0b9-169">问题在于对 `string.Format` 的调用解析为 <xref:System.String.Format%28System.String%2CSystem.Object%2CSystem.Object%29> 重载。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-169">The problem is that the call to `string.Format` resolves to the <xref:System.String.Format%28System.String%2CSystem.Object%2CSystem.Object%29> overload.</span></span>  
  
 <span data-ttu-id="1c0b9-170">此重载需要 .NET Framework 来将 `int` 值装箱到对象中，并将这些值传递到此方法调用。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-170">This overload requires the .NET Framework to box the `int` values into objects to pass them to this method call.</span></span>  <span data-ttu-id="1c0b9-171">部分修复是指调用 `id.ToString()` 和 `size.ToString()` 并且将所有字符串（这些字符串是对象）传递到 `string.Format` 调用。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-171">A partial fix is to call `id.ToString()` and `size.ToString()` and pass all strings (which are objects) to the `string.Format` call.</span></span>  <span data-ttu-id="1c0b9-172">调用 `ToString()` 将分配一个字符串，但该分配无论如何都将在 `string.Format` 内部发生。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-172">Calling `ToString()` does allocate a string, but that allocation will happen anyway inside `string.Format`.</span></span>  
  
 <span data-ttu-id="1c0b9-173">你可能会认为对 `string.Format` 的这种基本调用只是字符串串联，因此你可能会改为编写此代码：</span><span class="sxs-lookup"><span data-stu-id="1c0b9-173">You might consider that this basic call to `string.Format` is just string concatenation, so you might write this code instead:</span></span>  
  
```csharp  
var s = id.ToString() + ':' + size.ToString();  
```  
  
 <span data-ttu-id="1c0b9-174">然而，该行代码因编译为 <xref:System.String.Concat%28System.Object%2CSystem.Object%2CSystem.Object%29> 而引入了装箱分配。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-174">However, that line of code introduces a boxing allocation because it compiles to <xref:System.String.Concat%28System.Object%2CSystem.Object%2CSystem.Object%29>.</span></span>  <span data-ttu-id="1c0b9-175">.NET Framework 必须装箱字符文本以调用 `Concat`</span><span class="sxs-lookup"><span data-stu-id="1c0b9-175">The .NET Framework must box the character literal to invoke `Concat`</span></span>  
  
 <span data-ttu-id="1c0b9-176">**示例 1 的修复**</span><span class="sxs-lookup"><span data-stu-id="1c0b9-176">**Fix for example 1**</span></span>  
  
 <span data-ttu-id="1c0b9-177">完整的修复很简单。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-177">The complete fix is simple.</span></span>  <span data-ttu-id="1c0b9-178">只需将字符文本替换为字符串文本即可，由于字符串已经是对象了，因此这样不会导致装箱：</span><span class="sxs-lookup"><span data-stu-id="1c0b9-178">Just replace the character literal with a string literal, which incurs no boxing because strings are already objects:</span></span>  
  
```csharp  
var s = id.ToString() + ":" + size.ToString();  
```  
  
 <span data-ttu-id="1c0b9-179">**示例 2：枚举装箱**</span><span class="sxs-lookup"><span data-stu-id="1c0b9-179">**Example 2: enum boxing**</span></span>  
  
 <span data-ttu-id="1c0b9-180">由于常使用枚举类型，尤其是在字典查找操作中，此示例是导致新的 C# 和 Visual Basic 编译器中出现大量分配的原因。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-180">This example was responsible for a huge amount of allocation in the new C# and Visual Basic compilers due to frequent use of enumeration types, especially in dictionary lookup operations.</span></span>  
  
```csharp  
public enum Color  
{  
    Red, Green, Blue  
}  
  
public class BoxingExample  
{  
    private string name;  
    private Color color;  
    public override int GetHashCode()  
    {  
        return name.GetHashCode() ^ color.GetHashCode();  
    }  
}  
```  
  
 <span data-ttu-id="1c0b9-181">此问题很微妙。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-181">This problem is very subtle.</span></span>  <span data-ttu-id="1c0b9-182">PerfView 会将此报告为 <xref:System.Enum.GetHashCode> 装箱，因为该方法出于实现的原因对枚举类型的根本表现形式进行装箱。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-182">PerfView would report this as <xref:System.Enum.GetHashCode> boxing because the method boxes the underlying representation of the enumeration type, for implementation reasons.</span></span>  <span data-ttu-id="1c0b9-183">如果在 PerfView 中仔细查看，你可能会看到对 <xref:System.Enum.GetHashCode> 的每个调用都存在两个装箱分配。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-183">If you look closely in PerfView, you may see two boxing allocations for each call to <xref:System.Enum.GetHashCode>.</span></span>   <span data-ttu-id="1c0b9-184">编译器插入一个，而 .NET Framework 插入另一个。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-184">The compiler inserts one, and the .NET Framework inserts the other.</span></span>  
  
 <span data-ttu-id="1c0b9-185">**示例 2 的修复**</span><span class="sxs-lookup"><span data-stu-id="1c0b9-185">**Fix for example 2**</span></span>  
  
 <span data-ttu-id="1c0b9-186">在调用 <xref:System.Enum.GetHashCode> 前，你可以通过强制转换为基础表现形式，轻松避免这两个分配：</span><span class="sxs-lookup"><span data-stu-id="1c0b9-186">You can easily avoid both allocations by casting to the underlying representation before calling <xref:System.Enum.GetHashCode>:</span></span>  
  
```csharp  
((int)color).GetHashCode()  
```  
  
 <span data-ttu-id="1c0b9-187">枚举类型上另一种常见的装箱源是 <xref:System.Enum.HasFlag%28System.Enum%29?displayProperty=nameWithType> 方法。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-187">Another common source of boxing on enumeration types is the <xref:System.Enum.HasFlag%28System.Enum%29?displayProperty=nameWithType> method.</span></span>  <span data-ttu-id="1c0b9-188">传递到 <xref:System.Enum.HasFlag%28System.Enum%29> 的参数必须进行装箱。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-188">The argument passed to <xref:System.Enum.HasFlag%28System.Enum%29> has to be boxed.</span></span>  <span data-ttu-id="1c0b9-189">大多数情况下，将对 <xref:System.Enum.HasFlag%28System.Enum%29?displayProperty=nameWithType> 的调用替换为按位测试更简单并且无需分配。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-189">In most cases, replacing calls to <xref:System.Enum.HasFlag%28System.Enum%29?displayProperty=nameWithType> with a bitwise test is simpler and allocation-free.</span></span>  
  
 <span data-ttu-id="1c0b9-190">请记住第一个性能事实（即，切勿过早优化），不要以这种方式开始重写你所有的代码。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-190">Keep the first performance fact in mind (that is, don’t prematurely optimize) and don’t start rewriting all your code in this way.</span></span>    <span data-ttu-id="1c0b9-191">请留意这些装箱成本，但仅在分析完应用并找到热点后才更改你的代码。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-191">Be aware of these boxing costs, but change your code only after profiling your app and finding the hot spots.</span></span>  
  
### <a name="strings"></a><span data-ttu-id="1c0b9-192">字符串</span><span class="sxs-lookup"><span data-stu-id="1c0b9-192">Strings</span></span>  
 <span data-ttu-id="1c0b9-193">字符串操作是产生分配的最主要原因之一，并且它们经常出现在 PerfView 前五大分配之中。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-193">String manipulations are some of the biggest culprits for allocations, and they often show up in PerfView in the top five allocations.</span></span>  <span data-ttu-id="1c0b9-194">程序将字符串用于序列化、JSON 和 REST API。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-194">Programs use strings for serialization, JSON, and REST APIs.</span></span>  <span data-ttu-id="1c0b9-195">当你无法使用枚举类型时，可以将字符串用作编程常量与系统进行互操作。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-195">You can use strings as programmatic constants for interoperating with systems when you can’t use enumeration types.</span></span>  <span data-ttu-id="1c0b9-196">当你的分析显示字符串极为影响性能时，则查找对 <xref:System.String> 方法的调用，如 <xref:System.String.Format%2A>、<xref:System.String.Concat%2A>、<xref:System.String.Split%2A>、<xref:System.String.Join%2A> 和 <xref:System.String.Substring%2A> 等。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-196">When your profiling shows that strings are highly affecting performance, look for calls to <xref:System.String> methods such as <xref:System.String.Format%2A>, <xref:System.String.Concat%2A>, <xref:System.String.Split%2A>, <xref:System.String.Join%2A>, <xref:System.String.Substring%2A>, and so on.</span></span>  <span data-ttu-id="1c0b9-197">使用 <xref:System.Text.StringBuilder> 来避免创建从多个片段创建字符串的成本能够到帮助作用，但即使是分配 <xref:System.Text.StringBuilder> 对象也可能会变成需要你管理的瓶颈。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-197">Using <xref:System.Text.StringBuilder> to avoid the cost of creating one string from many pieces helps, but even allocating the <xref:System.Text.StringBuilder> object might become a bottleneck that you need to manage.</span></span>  
  
 <span data-ttu-id="1c0b9-198">**示例 3：字符串操作**</span><span class="sxs-lookup"><span data-stu-id="1c0b9-198">**Example 3: string operations**</span></span>  
  
 <span data-ttu-id="1c0b9-199">C# 编译器具有此编写格式化 XML 文档注释的文本的代码：</span><span class="sxs-lookup"><span data-stu-id="1c0b9-199">The C# compiler had this code that writes the text of a formatted XML doc comment:</span></span>  
  
```csharp  
public void WriteFormattedDocComment(string text)  
{  
    string[] lines = text.Split(new[] { "\r\n", "\r", "\n" },  
                                StringSplitOptions.None);  
    int numLines = lines.Length;  
    bool skipSpace = true;  
    if (lines[0].TrimStart().StartsWith("///"))  
    {  
        for (int i = 0; i < numLines; i++)  
        {  
            string trimmed = lines[i].TrimStart();  
            if (trimmed.Length < 4 || !char.IsWhiteSpace(trimmed[3]))  
            {  
                skipSpace = false;  
                break;  
            }  
        }  
        int substringStart = skipSpace ? 4 : 3;  
        for (int i = 0; i < numLines; i++)  
            WriteLine(lines[i].TrimStart().Substring(substringStart));  
    }  
    else { /* ... */ }  
```  
  
 <span data-ttu-id="1c0b9-200">你可以看到此代码执行了很多字符串操作。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-200">You can see that this code does a lot of string manipulation.</span></span>  <span data-ttu-id="1c0b9-201">该代码使用库方法将行拆分为单独的字符串，以修整空格、检查参数 `text` 是否为 XML 文档注释，并且从行提取子字符串。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-201">The code uses library methods to split lines into separate strings, to trim white space, to check whether the argument `text` is an XML documentation comment, and to extract substrings from lines.</span></span>  
  
 <span data-ttu-id="1c0b9-202">在 `WriteFormattedDocComment` 中的第一行上，`text.Split` 调用将分配一个新的三元素数组作为每次调用的参数。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-202">On the first line inside `WriteFormattedDocComment`, the `text.Split` call allocates a new three-element array as the argument every time it’s called.</span></span>  <span data-ttu-id="1c0b9-203">每次编译器都必须发出代码以分配此数组。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-203">The compiler has to emit code to allocate this array each time.</span></span>  <span data-ttu-id="1c0b9-204">那是因为编译器不知道 <xref:System.String.Split%2A> 是否将数组存储在了一个该数组可能已由其他代码修改的位置，这样将影响后续对 `WriteFormattedDocComment` 的调用。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-204">That’s because the compiler doesn’t know if <xref:System.String.Split%2A> stores the array somewhere where the array might be modified by other code, which would affect later calls to `WriteFormattedDocComment`.</span></span>  <span data-ttu-id="1c0b9-205">对 <xref:System.String.Split%2A> 的调用还会为 `text` 中的每一行分配一个字符串，并分配其他内存以执行操作。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-205">The call to <xref:System.String.Split%2A> also allocates a string for every line in `text` and allocates other memory to perform the operation.</span></span>  
  
 <span data-ttu-id="1c0b9-206">`WriteFormattedDocComment` 具有对 <xref:System.String.TrimStart%2A> 方法的三个调用。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-206">`WriteFormattedDocComment` has three calls to the <xref:System.String.TrimStart%2A> method.</span></span>  <span data-ttu-id="1c0b9-207">其中两个调用在复制工作和分配的内循环中。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-207">Two are in inner loops that duplicate work and allocations.</span></span>  <span data-ttu-id="1c0b9-208">更糟的是，在没有实参的情况下调用 <xref:System.String.TrimStart%2A> 方法，除了分配字符串结果外，还将分配一个空数组（用于 `params` 形参）。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-208">To make matters worse, calling the <xref:System.String.TrimStart%2A> method with no arguments allocates an empty array (for the `params` parameter) in addition to the string result.</span></span>  
  
 <span data-ttu-id="1c0b9-209">最后，存在一个对 <xref:System.String.Substring%2A> 方法的调用，这通常会分配一个新字符串。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-209">Lastly, there is a call to the <xref:System.String.Substring%2A> method, which usually allocates a new string.</span></span>  
  
 <span data-ttu-id="1c0b9-210">**示例 3 的修复**</span><span class="sxs-lookup"><span data-stu-id="1c0b9-210">**Fix for example 3**</span></span>  
  
 <span data-ttu-id="1c0b9-211">不同于以前的示例，略微编辑无法修复这些分配。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-211">Unlike the earlier examples, small edits cannot fix these allocations.</span></span>  <span data-ttu-id="1c0b9-212">你需要返回一步、查看该问题，然后采用不同的方法处理它。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-212">You need to step back, look at the problem, and approach it differently.</span></span>  <span data-ttu-id="1c0b9-213">例如，你将注意到 `WriteFormattedDocComment()` 的参数是一个包含该方法所需全部信息的字符串，因此该代码可以执行更多索引而不是分配很多部分字符串。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-213">For example, you'll notice that the argument to `WriteFormattedDocComment()` is a string that has all the information that the method needs, so the code could do more indexing instead of allocating many partial strings.</span></span>  
  
 <span data-ttu-id="1c0b9-214">编译器的性能团队使用如下代码处理所有这些分配：</span><span class="sxs-lookup"><span data-stu-id="1c0b9-214">The compiler’s performance team tackled all these allocations with code like this:</span></span>  
  
```csharp  
private int IndexOfFirstNonWhiteSpaceChar(string text, int start) {  
    while (start < text.Length && char.IsWhiteSpace(text[start])) start++;  
    return start;  
}  
  
private bool TrimmedStringStartsWith(string text, int start, string prefix) {  
    start = IndexOfFirstNonWhiteSpaceChar(text, start);  
    int len = text.Length - start;  
    if (len < prefix.Length) return false;  
    for (int i = 0; i < len; i++)  
    {  
        if (prefix[i] != text[start + i]) return false;  
    }  
    return true;  
}  
  
// etc...  
```  
  
 <span data-ttu-id="1c0b9-215">`WriteFormattedDocComment()` 的第一个版本分配了一个数组、多个子字符串、一个修整的子字符串和一个空 `params` 数组。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-215">The first version of `WriteFormattedDocComment()` allocated an array, several substrings, and a trimmed substring along with an empty `params` array.</span></span>  <span data-ttu-id="1c0b9-216">它还针对 `"///"` 进行检查。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-216">It also checked for `"///"`.</span></span>  <span data-ttu-id="1c0b9-217">修改后的代码仅使用索引且不执行分配。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-217">The revised code uses only indexing and allocates nothing.</span></span>  <span data-ttu-id="1c0b9-218">它查找不是空格的第一个字符，然后逐字符检查字符串是否以 `"///"` 开头。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-218">It finds the first character that is not white space, and then checks character by character to see if the string starts with `"///"`.</span></span>  <span data-ttu-id="1c0b9-219">新代码使用 `IndexOfFirstNonWhiteSpaceChar` 而不是 <xref:System.String.TrimStart%2A> 以返回出现非空白字符的第一个索引（在指定的开始索引后）。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-219">The new code uses `IndexOfFirstNonWhiteSpaceChar` instead of <xref:System.String.TrimStart%2A> to return the first index (after a specified start index) where a non-whitespace character occurs.</span></span>  <span data-ttu-id="1c0b9-220">修复并不完整，但你可以看到如何为完整解决方案应用类似的修复。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-220">The fix is not complete, but you can see how to apply similar fixes for a complete solution.</span></span>  <span data-ttu-id="1c0b9-221">通过在整个代码中应用此方法，你可以删除 `WriteFormattedDocComment()` 中的所有分配。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-221">By applying this approach throughout the code, you can remove all allocations in `WriteFormattedDocComment()`.</span></span>  
  
 <span data-ttu-id="1c0b9-222">**示例 4：StringBuilder**</span><span class="sxs-lookup"><span data-stu-id="1c0b9-222">**Example 4: StringBuilder**</span></span>  
  
 <span data-ttu-id="1c0b9-223">此示例使用 <xref:System.Text.StringBuilder> 对象。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-223">This example uses a <xref:System.Text.StringBuilder> object.</span></span>  <span data-ttu-id="1c0b9-224">以下函数生成泛型类型的完整类型名称：</span><span class="sxs-lookup"><span data-stu-id="1c0b9-224">The following function generates a full type name for generic types:</span></span>  
  
```csharp  
public class Example  
{  
    // Constructs a name like "SomeType<T1, T2, T3>"  
    public string GenerateFullTypeName(string name, int arity)  
    {  
        StringBuilder sb = new StringBuilder();  
  
        sb.Append(name);  
        if (arity != 0)  
        {  
            sb.Append("<");  
            for (int i = 1; i < arity; i++)  
            {  
                sb.Append("T"); sb.Append(i.ToString()); sb.Append(", ");  
            }  
            sb.Append("T"); sb.Append(i.ToString()); sb.Append(">");  
        }  
  
        return sb.ToString();  
    }  
}  
```  
  
 <span data-ttu-id="1c0b9-225">关注的焦点在创建新 <xref:System.Text.StringBuilder> 实例的行上。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-225">The focus is on the line that creates a new <xref:System.Text.StringBuilder> instance.</span></span>  <span data-ttu-id="1c0b9-226">该代码导致针对 `sb.ToString()` 的分配和 <xref:System.Text.StringBuilder> 实现中的内部分配，但如果你想要字符串结果，则无法控制那些分配。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-226">The code causes an allocation for `sb.ToString()` and internal allocations within the <xref:System.Text.StringBuilder> implementation, but you cannot control those allocations if you want the string result.</span></span>  
  
 <span data-ttu-id="1c0b9-227">**示例 4 的修复**</span><span class="sxs-lookup"><span data-stu-id="1c0b9-227">**Fix for example 4**</span></span>  
  
 <span data-ttu-id="1c0b9-228">若要修复 `StringBuilder` 对象分配，则缓存该对象。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-228">To fix the `StringBuilder` object allocation, cache the  object.</span></span>  <span data-ttu-id="1c0b9-229">即使是缓存可能丢弃的单个实例，也可以显著提高性能。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-229">Even caching a single instance that might get thrown away can improve performance significantly.</span></span>  <span data-ttu-id="1c0b9-230">这是该函数的新实现，省去所有的代码，除了新的第一行和最后一行：</span><span class="sxs-lookup"><span data-stu-id="1c0b9-230">This is the function’s new implementation, omitting all the code except for the new first and last lines:</span></span>  
  
```csharp  
// Constructs a name like "MyType<T1, T2, T3>"  
public string GenerateFullTypeName(string name, int arity)  
{  
    StringBuilder sb = AcquireBuilder();  
    /* Use sb as before */  
    return GetStringAndReleaseBuilder(sb);  
}  
```  
  
 <span data-ttu-id="1c0b9-231">重要部分是新 `AcquireBuilder()` 和 `GetStringAndReleaseBuilder()` 函数：</span><span class="sxs-lookup"><span data-stu-id="1c0b9-231">The key parts are the new `AcquireBuilder()` and `GetStringAndReleaseBuilder()` functions:</span></span>  
  
```csharp  
[ThreadStatic]  
private static StringBuilder cachedStringBuilder;  
  
private static StringBuilder AcquireBuilder()  
{  
    StringBuilder result = cachedStringBuilder;  
    if (result == null)  
    {  
        return new StringBuilder();  
    }  
    result.Clear();  
    cachedStringBuilder = null;  
    return result;  
}  
  
private static string GetStringAndReleaseBuilder(StringBuilder sb)  
{  
    string result = sb.ToString();  
    cachedStringBuilder = sb;  
    return result;  
}  
```  
  
 <span data-ttu-id="1c0b9-232">由于新编译器使用线程处理，这些实现使用线程静态字段（<xref:System.ThreadStaticAttribute> 特性）来缓存 <xref:System.Text.StringBuilder>，并且你有可能可以放弃 `ThreadStatic` 声明。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-232">Because the new compilers use threading, these implementations use a thread-static field (<xref:System.ThreadStaticAttribute> attribute) to cache the <xref:System.Text.StringBuilder>, and you likely can forgo the `ThreadStatic` declaration.</span></span>  <span data-ttu-id="1c0b9-233">线程静态字段为执行此代码的每个线程保存一个唯一值。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-233">The thread-static field holds a unique value for each thread that executes this code.</span></span>  
  
 <span data-ttu-id="1c0b9-234">在清除该值并设置字段或缓存为 null 后，`AcquireBuilder()` 将返回缓存的 <xref:System.Text.StringBuilder> 实例（如果存在）。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-234">`AcquireBuilder()` returns the cached <xref:System.Text.StringBuilder> instance if there is one, after clearing it and setting the field or cache to null.</span></span>  <span data-ttu-id="1c0b9-235">否则，`AcquireBuilder()` 将创建一个新的实例并返回它，同时保留该字段或将缓存设置为 null。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-235">Otherwise, `AcquireBuilder()` creates a new instance and returns it, leaving the field or cache set to null.</span></span>  
  
 <span data-ttu-id="1c0b9-236">当你已完成 <xref:System.Text.StringBuilder> 时，调用 `GetStringAndReleaseBuilder()` 以获取字符串结果、将 <xref:System.Text.StringBuilder> 实例保存在字段或缓存中，然后返回该结果。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-236">When you’re done with <xref:System.Text.StringBuilder> , you call `GetStringAndReleaseBuilder()` to get the string result, save the <xref:System.Text.StringBuilder> instance in the field or cache, and then return the result.</span></span>  <span data-ttu-id="1c0b9-237">执行可以重新进入此代码并创建多个 <xref:System.Text.StringBuilder> 对象（尽管这种情况很少发生）。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-237">It is possible for execution to re-enter this code and to create multiple <xref:System.Text.StringBuilder> objects (although that rarely happens).</span></span>  <span data-ttu-id="1c0b9-238">该代码仅保存最后释放的 <xref:System.Text.StringBuilder> 实例以供稍后使用。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-238">The code saves only the last released <xref:System.Text.StringBuilder> instance for later use.</span></span>  <span data-ttu-id="1c0b9-239">这个简单的缓存策略可在新的编译器中显著减少分配。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-239">This simple caching strategy significantly reduced allocations in the new compilers.</span></span>  <span data-ttu-id="1c0b9-240">部分 .NET Framework 和 MSBuild ("MSBuild") 使用类似的技术以提高性能。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-240">Parts of the .NET Framework and MSBuild ("MSBuild") use a similar technique to improve performance.</span></span>  
  
 <span data-ttu-id="1c0b9-241">这个简单的缓存策略符合良好的缓存设计要求，因为它具有大小上限。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-241">This simple caching strategy adheres to good cache design because it has a size cap.</span></span>  <span data-ttu-id="1c0b9-242">然而，现在存在比原来更多的代码，这意味着更多的维护成本。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-242">However, there is more code now than in the original, which means more maintenance costs.</span></span>  <span data-ttu-id="1c0b9-243">仅当你发现了性能问题时，并且 PerfView 已显示 <xref:System.Text.StringBuilder> 分配是一个重要的参与者，才应采用该缓存策略。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-243">You should adopt the caching strategy only if you’ve found a performance problem, and PerfView has shown that <xref:System.Text.StringBuilder> allocations are a significant contributor.</span></span>  
  
### <a name="linq-and-lambdas"></a><span data-ttu-id="1c0b9-244">LINQ 和 lambda</span><span class="sxs-lookup"><span data-stu-id="1c0b9-244">LINQ and lambdas</span></span>  
 <span data-ttu-id="1c0b9-245">使用语言集成查询 (LINQ) 和 Lambda 表达式是一个使用高效率功能的出色示例，如果代码对性能有显著的影响，你以后可能会发现需要重写这些功能。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-245">Using Language-Integrated Query (LINQ) and lambda expressions is a great example of using productive features that you might later find you need to rewrite if the code becomes a significant impact on performance.</span></span>  
  
 <span data-ttu-id="1c0b9-246">**示例 5：Lambda、List\<T> 和 IEnumerable\<T>**</span><span class="sxs-lookup"><span data-stu-id="1c0b9-246">**Example 5: Lambdas, List\<T>, and IEnumerable\<T>**</span></span>  
  
 <span data-ttu-id="1c0b9-247">此示例使用 [LINQ 和功能性代码](http://blogs.msdn.com/b/charlie/archive/2007/01/26/anders-hejlsberg-on-linq-and-functional-programming.aspx)在编译器模型中查找符号，给定的名称字符串为：</span><span class="sxs-lookup"><span data-stu-id="1c0b9-247">This example uses [LINQ and functional style code](http://blogs.msdn.com/b/charlie/archive/2007/01/26/anders-hejlsberg-on-linq-and-functional-programming.aspx) to find a symbol in the compiler’s model, given a name string:</span></span>  
  
```csharp  
class Symbol {  
    public string Name { get; private set; }  
    /*...*/  
}  
  
class Compiler {  
    private List<Symbol> symbols;  
    public Symbol FindMatchingSymbol(string name)  
    {  
        return symbols.FirstOrDefault(s => s.Name == name);  
    }  
}  
```  
  
 <span data-ttu-id="1c0b9-248">该新编译器和构建于其上的 IDE 体验极为频繁地调用 `FindMatchingSymbol()`，并且此函数的单行代码上有多个隐藏的分配。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-248">The new compiler and the IDE experiences built on it call `FindMatchingSymbol()` very frequently, and there are several hidden allocations in this function’s single line of code.</span></span>  <span data-ttu-id="1c0b9-249">若要检查那些分配，首先将该函数的单行代码拆分成两行：</span><span class="sxs-lookup"><span data-stu-id="1c0b9-249">To examine those allocations, first split the function’s single line of code into two lines:</span></span>  
  
```csharp  
Func<Symbol, bool> predicate = s => s.Name == name;  
     return symbols.FirstOrDefault(predicate);  
```  
  
 <span data-ttu-id="1c0b9-250">第一行中，[Lambda 表达式](~/docs/csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)`s => s.Name == name`[封盖](http://blogs.msdn.com/b/ericlippert/archive/2003/09/17/53028.aspx)本地变量 `name`。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-250">In the first line, the [lambda expression](~/docs/csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)`s => s.Name == name`[closes over](http://blogs.msdn.com/b/ericlippert/archive/2003/09/17/53028.aspx) the local variable `name`.</span></span>  <span data-ttu-id="1c0b9-251">这意味着除了针对 `predicate` 所保存的 [委托](~/docs/csharp/language-reference/keywords/delegate.md)分配对象以外，该代码分配了静态类以保存捕获 `name` 的值的环境。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-251">This means that in addition to allocating an object for the [delegate](~/docs/csharp/language-reference/keywords/delegate.md) that `predicate` holds, the code allocates a static class to hold the environment that captures the value of `name`.</span></span>  <span data-ttu-id="1c0b9-252">编译器生成的代码如下所示：</span><span class="sxs-lookup"><span data-stu-id="1c0b9-252">The compiler generates code like the following:</span></span>  
  
```csharp  
// Compiler-generated class to hold environment state for lambda  
private class Lambda1Environment  
{  
    public string capturedName;  
    public bool Evaluate(Symbol s)  
    {  
        return s.Name == this.capturedName;  
    }  
}  
  
// Expanded Func<Symbol, bool> predicate = s => s.Name == name;  
Lambda1Environment l = new Lambda1Environment() { capturedName = name };  
var predicate = new Func<Symbol, bool>(l.Evaluate);  
```  
  
 <span data-ttu-id="1c0b9-253">这两个 `new` 分配（一个用于环境类，另一个用于委托）现在是显式的。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-253">The two `new` allocations (one for the environment class and one for the delegate) are explicit now.</span></span>  
  
 <span data-ttu-id="1c0b9-254">现在查看对 `FirstOrDefault` 的调用。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-254">Now look at the call to `FirstOrDefault`.</span></span> <span data-ttu-id="1c0b9-255"><xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> 类型上的此扩展方法也会导致分配。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-255">This extension method on the <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> type incurs an allocation too.</span></span>  <span data-ttu-id="1c0b9-256">因为 `FirstOrDefault` 采用 <xref:System.Collections.Generic.IEnumerable%601> 对象作为它的第一个参数，你可以将调用扩展到以下代码（略微简化以便讨论）：</span><span class="sxs-lookup"><span data-stu-id="1c0b9-256">Because `FirstOrDefault` takes an <xref:System.Collections.Generic.IEnumerable%601> object as its first argument, you can expand the call to the following code (simplified a bit for discussion):</span></span>  
  
```csharp  
// Expanded return symbols.FirstOrDefault(predicate) ...  
     IEnumerable<Symbol> enumerable = symbols;  
     IEnumerator<Symbol> enumerator = enumerable.GetEnumerator();  
     while(enumerator.MoveNext())  
     {  
         if (predicate(enumerator.Current))  
             return enumerator.Current;  
     }  
     return default(Symbol);  
```  
  
 <span data-ttu-id="1c0b9-257">`symbols` 变量具有类型 <xref:System.Collections.Generic.List%601>。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-257">The `symbols` variable has type <xref:System.Collections.Generic.List%601>.</span></span>  <span data-ttu-id="1c0b9-258"><xref:System.Collections.Generic.List%601> 集合类型实现 <xref:System.Collections.Generic.IEnumerable%601> 并且巧妙地定义了一个 <xref:System.Collections.Generic.IEnumerator%601> 使用 <xref:System.Collections.Generic.List%601> 实现的枚举器（`struct` 接口）。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-258">The <xref:System.Collections.Generic.List%601> collection type implements <xref:System.Collections.Generic.IEnumerable%601> and cleverly defines an enumerator (<xref:System.Collections.Generic.IEnumerator%601> interface) that <xref:System.Collections.Generic.List%601> implements with a `struct`.</span></span>  <span data-ttu-id="1c0b9-259">使用结构而不是类意味着你通常避免任何堆分配，而后者可能会影响垃圾回收性能。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-259">Using a structure instead of a class means that you usually avoid any heap allocations, which, in turn, can affect garbage collection performance.</span></span>  <span data-ttu-id="1c0b9-260">枚举器通常与语言的 `foreach` 循环结合使用，该循环使用枚举器结构，因为它是在调用堆栈上返回的。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-260">Enumerators are typically used with the language’s `foreach` loop, which uses the enumerator structure as it is returned on the call stack.</span></span>  <span data-ttu-id="1c0b9-261">递增调用堆栈指针从而为对象腾出空间，不会像堆分配那样影响 GC。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-261">Incrementing the call stack pointer to make room for an object does not affect GC the way a heap allocation does.</span></span>  
  
 <span data-ttu-id="1c0b9-262">对于扩展的 `FirstOrDefault` 调用，代码需要在一个 `GetEnumerator()` 上调用 <xref:System.Collections.Generic.IEnumerable%601>。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-262">In the case of the expanded `FirstOrDefault` call, the code needs to call `GetEnumerator()` on an <xref:System.Collections.Generic.IEnumerable%601>.</span></span>  <span data-ttu-id="1c0b9-263">将 `symbols` 分配到类型 `enumerable` 的 `IEnumerable<Symbol>` 变量失去了实际对象是一个 <xref:System.Collections.Generic.List%601> 的信息。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-263">Assigning `symbols` to the `enumerable` variable of type `IEnumerable<Symbol>` loses the information that the actual object is a <xref:System.Collections.Generic.List%601>.</span></span>  <span data-ttu-id="1c0b9-264">这意味着当代码使用 `enumerable.GetEnumerator()` 获取枚举器时，.NET Framework 必须装箱返回的结构以将其分配到 `enumerator` 变量。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-264">This means that when the code fetches the enumerator with `enumerable.GetEnumerator()`, the .NET Framework has to box the returned structure to assign it to the `enumerator` variable.</span></span>  
  
 <span data-ttu-id="1c0b9-265">**示例 5 的修复**</span><span class="sxs-lookup"><span data-stu-id="1c0b9-265">**Fix for example 5**</span></span>  
  
 <span data-ttu-id="1c0b9-266">修复方法是以下列方式重写 `FindMatchingSymbol`，将它的单行代码替换为仍旧简洁、容易阅读和理解且易于维护的六行代码：</span><span class="sxs-lookup"><span data-stu-id="1c0b9-266">The fix is to rewrite `FindMatchingSymbol` as follows, replacing its single line of code with six lines of code that are still concise, easy to read and understand, and easy to maintain:</span></span>  
  
```csharp  
public Symbol FindMatchingSymbol(string name)  
    {  
        foreach (Symbol s in symbols)  
        {  
            if (s.Name == name)  
                return s;  
        }  
        return null;  
    }  
```  
  
 <span data-ttu-id="1c0b9-267">此代码不使用 LINQ 扩展方法、lambda 或枚举器，并且它不会导致分配。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-267">This code doesn’t use LINQ extension methods, lambdas, or enumerators, and it incurs no allocations.</span></span>  <span data-ttu-id="1c0b9-268">不存在分配，因为编译器可以理解 `symbols` 集合是一个 <xref:System.Collections.Generic.List%601> 并且可以使用正确的类型将结果枚举器（一个结构）绑定到本地变量，从而避免装箱。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-268">There are no allocations because the compiler can see that the `symbols` collection is a <xref:System.Collections.Generic.List%601> and can bind the resulting enumerator (a structure) to a local variable with the right type to avoid boxing.</span></span>  <span data-ttu-id="1c0b9-269">此函数的原始版本是展示 C# 表现力以及 .NET Framework 工作效率的出色示例。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-269">The original version of this function was a great example of the expressive power of C# and the productivity of the .NET Framework.</span></span>  <span data-ttu-id="1c0b9-270">这种新的并且更有效的版本保留了那些品质，且未添加任何用于维护的复杂代码。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-270">This new and more efficient version preserves those qualities without adding any complex code to maintain.</span></span>  
  
### <a name="async-method-caching"></a><span data-ttu-id="1c0b9-271">异步方法缓存</span><span class="sxs-lookup"><span data-stu-id="1c0b9-271">Async method caching</span></span>  
 <span data-ttu-id="1c0b9-272">下一个示例显示当尝试在[异步](http://msdn.microsoft.com/library/db854f91-ccef-4035-ae4d-0911fde808c7)方法中使用缓存结果时，将遇到的一个常见问题。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-272">The next example shows a common problem when you try to use cached results in an [async](http://msdn.microsoft.com/library/db854f91-ccef-4035-ae4d-0911fde808c7) method.</span></span>  
  
 <span data-ttu-id="1c0b9-273">**示例 6：在异步方法中缓存**</span><span class="sxs-lookup"><span data-stu-id="1c0b9-273">**Example 6: caching in async methods**</span></span>  
  
 <span data-ttu-id="1c0b9-274">在新的 C# 和 Visual Basic 编译器上构建的 Visual Studio IDE 功能频繁地提取语法树，并且编译器在执行此操作时使用异步来保持 Visual Studio 的响应性。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-274">The Visual Studio IDE features built on the new C# and Visual Basic compilers frequently fetch syntax trees, and the compilers use async when doing so to keep Visual Studio responsive.</span></span>  <span data-ttu-id="1c0b9-275">以下是你可以编写的、用于获取语法树的该代码的第一个版本：</span><span class="sxs-lookup"><span data-stu-id="1c0b9-275">Here’s the first version of the code you might write to get a syntax tree:</span></span>  
  
```csharp  
class SyntaxTree { /*...*/ }  
  
class Parser { /*...*/  
    public SyntaxTree Syntax { get; }  
    public Task ParseSourceCode() { /*...*/ }  
}  
  
class Compilation { /*...*/  
    public async Task<SyntaxTree> GetSyntaxTreeAsync()  
    {  
        var parser = new Parser(); // allocation  
        await parser.ParseSourceCode(); // expensive  
        return parser.Syntax;  
    }  
}  
```  
  
 <span data-ttu-id="1c0b9-276">你可以看到调用 `GetSyntaxTreeAsync()` 实例化了一个 `Parser`，分析了该代码，然后返回一个 <xref:System.Threading.Tasks.Task> 对象 `Task<SyntaxTree>`。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-276">You can see that calling `GetSyntaxTreeAsync()` instantiates a `Parser`, parses the code, and then returns a <xref:System.Threading.Tasks.Task> object, `Task<SyntaxTree>`.</span></span>  <span data-ttu-id="1c0b9-277">成本高的部分是分配 `Parser` 实例和分析代码。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-277">The expensive part is allocating the `Parser` instance and parsing the code.</span></span>  <span data-ttu-id="1c0b9-278">该函数返回了一个 <xref:System.Threading.Tasks.Task> 以便调用方可以等待分析工作并释放 UI 线程以响应用户输入。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-278">The function returns a <xref:System.Threading.Tasks.Task> so that callers can await the parsing work and free the UI thread to be responsive to user input.</span></span>  
  
 <span data-ttu-id="1c0b9-279">多个 Visual Studio 功能可能会尝试获取相同的语法树，因此你可以编写以下代码以缓存分析结果，从而节省时间和分配。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-279">Several Visual Studio features might try to get the same syntax tree, so you might write the following code to cache the parsing result to save time and allocations.</span></span>  <span data-ttu-id="1c0b9-280">但是，此代码导致了一个分配：</span><span class="sxs-lookup"><span data-stu-id="1c0b9-280">However, this code incurs an allocation:</span></span>  
  
```csharp  
class Compilation { /*...*/  
  
    private SyntaxTree cachedResult;  
  
    public async Task<SyntaxTree> GetSyntaxTreeAsync()  
    {  
        if (this.cachedResult == null)  
        {  
            var parser = new Parser(); // allocation  
            await parser.ParseSourceCode(); // expensive  
            this.cachedResult = parser.Syntax;  
        }  
        return this.cachedResult;  
    }  
}  
```  
  
 <span data-ttu-id="1c0b9-281">你看到使用缓存的新代码具有一个命名为 `SyntaxTree` 的 `cachedResult` 字段。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-281">You see that the new code with caching has a `SyntaxTree` field named `cachedResult`.</span></span>  <span data-ttu-id="1c0b9-282">当此字段是 null 时，`GetSyntaxTreeAsync()` 奏效并且将结果保存在缓存中。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-282">When this field is null, `GetSyntaxTreeAsync()` does the work and saves the result in the cache.</span></span>  <span data-ttu-id="1c0b9-283">`GetSyntaxTreeAsync()` 返回 `SyntaxTree` 对象。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-283">`GetSyntaxTreeAsync()` returns the `SyntaxTree` object.</span></span>  <span data-ttu-id="1c0b9-284">问题在于当你具有一个类型为 `async` 的 `Task<SyntaxTree>` 函数时，并且你返回类型为 `SyntaxTree` 的值，编译器发出代码来分配保存结果的任务（通过使用 `Task<SyntaxTree>.FromResult()`）。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-284">The problem is that when you have an `async` function of type `Task<SyntaxTree>`, and you return a value of type `SyntaxTree`, the compiler emits code to allocate a Task to hold the result (by using `Task<SyntaxTree>.FromResult()`).</span></span>  <span data-ttu-id="1c0b9-285">任务标记为已完成，并且结果立即可用。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-285">The Task is marked as completed, and the result is immediately available.</span></span>  <span data-ttu-id="1c0b9-286">在新编译器的代码中，已经完成的 <xref:System.Threading.Tasks.Task> 对象频繁地发生，以至于修复这些分配显著地提高了响应能力。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-286">In the code for the new compilers, <xref:System.Threading.Tasks.Task> objects that were already completed occurred so often that fixing these allocations improved responsiveness noticeably.</span></span>  
  
 <span data-ttu-id="1c0b9-287">**示例 6 的修复**</span><span class="sxs-lookup"><span data-stu-id="1c0b9-287">**Fix for example 6**</span></span>  
  
 <span data-ttu-id="1c0b9-288">若要删除已完成<xref:System.Threading.Tasks.Task>分配，你可以缓存已完成的结果的任务对象：</span><span class="sxs-lookup"><span data-stu-id="1c0b9-288">To remove the completed <xref:System.Threading.Tasks.Task> allocation, you can cache the Task object with the completed result:</span></span>  
  
```csharp  
class Compilation { /*...*/  
  
    private Task<SyntaxTree> cachedResult;  
  
    public Task<SyntaxTree> GetSyntaxTreeAsync()  
    {  
        return this.cachedResult ??   
               (this.cachedResult = GetSyntaxTreeUncachedAsync());  
    }  
  
    private async Task<SyntaxTree> GetSyntaxTreeUncachedAsync()  
    {  
        var parser = new Parser(); // allocation  
        await parser.ParseSourceCode(); // expensive  
        return parser.Syntax;  
    }  
}  
```  
  
 <span data-ttu-id="1c0b9-289">此代码将 `cachedResult` 的类型更改为 `Task<SyntaxTree>` 并且使用一个 `async` 保存来自 `GetSyntaxTreeAsync()` 原始代码的帮助程序函数。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-289">This code changes the type of `cachedResult` to `Task<SyntaxTree>` and employs an `async` helper function that holds the original code from `GetSyntaxTreeAsync()`.</span></span>  <span data-ttu-id="1c0b9-290">如果 `GetSyntaxTreeAsync()` 不为 null，它现在使用 [null 合并运算符](../../csharp/language-reference/operators/null-coalescing-operator.md)来返回 `cachedResult`。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-290">`GetSyntaxTreeAsync()` now uses the [null coalescing operator](../../csharp/language-reference/operators/null-coalescing-operator.md) to return `cachedResult` if it isn't null.</span></span>  <span data-ttu-id="1c0b9-291">如果 `cachedResult` 为 null，则 `GetSyntaxTreeAsync()` 调用 `GetSyntaxTreeUncachedAsync()` 并且缓存结果。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-291">If `cachedResult` is null, then `GetSyntaxTreeAsync()` calls `GetSyntaxTreeUncachedAsync()` and caches the result.</span></span>  <span data-ttu-id="1c0b9-292">请注意，`GetSyntaxTreeAsync()` 不会像代码通常所做的那样等待对 `GetSyntaxTreeUncachedAsync()` 的调用。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-292">Notice that `GetSyntaxTreeAsync()` doesn’t await the call to `GetSyntaxTreeUncachedAsync()` as the code would normally.</span></span>  <span data-ttu-id="1c0b9-293">不使用 await 意味着当 `GetSyntaxTreeUncachedAsync()` 返回它的 <xref:System.Threading.Tasks.Task> 对象时，`GetSyntaxTreeAsync()` 立即返回 <xref:System.Threading.Tasks.Task>。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-293">Not using await means that when `GetSyntaxTreeUncachedAsync()` returns its <xref:System.Threading.Tasks.Task> object, `GetSyntaxTreeAsync()` immediately returns the <xref:System.Threading.Tasks.Task>.</span></span>  <span data-ttu-id="1c0b9-294">现在，缓存的结果是 <xref:System.Threading.Tasks.Task>，因此不存在用于返回缓存结果的分配。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-294">Now, the cached result is a <xref:System.Threading.Tasks.Task>, so there are no allocations to return the cached result.</span></span>  
  
### <a name="additional-considerations"></a><span data-ttu-id="1c0b9-295">其他注意事项</span><span class="sxs-lookup"><span data-stu-id="1c0b9-295">Additional considerations</span></span>  
 <span data-ttu-id="1c0b9-296">以下是有关大型应用或处理大量数据的应用中潜在问题的几个要点。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-296">Here are a few more points about potential problems in large apps or apps that process a lot of data.</span></span>  
  
 <span data-ttu-id="1c0b9-297">**字典**</span><span class="sxs-lookup"><span data-stu-id="1c0b9-297">**Dictionaries**</span></span>  
  
 <span data-ttu-id="1c0b9-298">字典在许多程序中普遍使用，此外字典非常方便且在本质上是高效的。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-298">Dictionaries are used ubiquitously in many programs, and though dictionaries are very convenient and inherently efficient.</span></span>  <span data-ttu-id="1c0b9-299">但是，它们经常使用不当。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-299">However, they’re often used inappropriately.</span></span>  <span data-ttu-id="1c0b9-300">在 Visual Studio 和新编译器中，分析表明许多字典包含单个元素或为空。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-300">In Visual Studio and the new compilers, analysis shows that many of the dictionaries contained a single element or were empty.</span></span>  <span data-ttu-id="1c0b9-301">一个空 <xref:System.Collections.Generic.Dictionary%602> 具有十个字段并且在 x86 计算机的堆上占用 48 个字节。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-301">An empty <xref:System.Collections.Generic.Dictionary%602> has ten fields and occupies 48 bytes on the heap on an x86 machine.</span></span>  <span data-ttu-id="1c0b9-302">当你需要一个使用常量时间查找的映射或关联数据结构时，字典是很有效的。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-302">Dictionaries are great when you need a mapping or associative data structure with constant-time lookup.</span></span>  <span data-ttu-id="1c0b9-303">然而，当你只有几个元素时，使用字典便浪费了大量的空间。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-303">However, when you have only a few elements, you waste a lot of space by using a dictionary.</span></span>  <span data-ttu-id="1c0b9-304">相反，你可以采用迭代方式查找一个 `List<KeyValuePair\<K,V>>`，速度一样快。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-304">Instead, for example, you could iteratively look through a `List<KeyValuePair\<K,V>>`, just as fast.</span></span>  <span data-ttu-id="1c0b9-305">如果你使用字典只是为了用数据加载它，然后从中读取（一个非常常用的模式），则使用附带 N(log(N)) 查找的排序数组可能差不多快，具体取决于你所使用的元素的数目。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-305">If you use a dictionary only to load it with data and then read from it (a very common pattern), using a sorted array with an N(log(N)) lookup might be nearly as fast, depending on the number of elements you're using.</span></span>  
  
 <span data-ttu-id="1c0b9-306">**类与结构**</span><span class="sxs-lookup"><span data-stu-id="1c0b9-306">**Classes vs. structures**</span></span>  
  
 <span data-ttu-id="1c0b9-307">在某种程度上，类和结构为优化你的应用提供了一个经典的空间/时间权衡。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-307">In a way, classes and structures provide a classic space/time tradeoff for tuning your apps.</span></span>  <span data-ttu-id="1c0b9-308">即使类不具有字段，它们也会在 x86 计算机上产生 12 个字节的开销，但是你可以通过便宜的方法绕过它们，因为只需要一个指针来引用类的实例。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-308">Classes incur 12 bytes of overhead on an x86 machine even if they have no fields, but they are inexpensive to pass around because it only takes a pointer to refer to a class instance.</span></span>  <span data-ttu-id="1c0b9-309">如果不对结构进行装箱，它们不会产生任何堆分配，但是当你将大型结构作为函数参数或返回值传递时，CPU 需要一定时间来以原子方式复制结构的所有数据成员。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-309">Structures incur no heap allocations if they aren’t boxed, but when you pass large structures as function arguments or return values, it takes CPU time to atomically copy all the data members of the structures.</span></span>  <span data-ttu-id="1c0b9-310">注意对返回结构的属性的重复调用，并且将属性的值缓存在一个局部变量中，以避免过度的数据复制。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-310">Watch out for repeated calls to properties that return structures, and cache the property’s value in a local variable to avoid excessive data copying.</span></span>  
  
 <span data-ttu-id="1c0b9-311">**缓存**</span><span class="sxs-lookup"><span data-stu-id="1c0b9-311">**Caches**</span></span>  
  
 <span data-ttu-id="1c0b9-312">一个常用的性能技巧是缓存结果。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-312">A common performance trick is to cache results.</span></span>  <span data-ttu-id="1c0b9-313">然而，没有大小上限或处置策略的缓存可能是一个内存泄漏。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-313">However, a cache without a size cap or disposal policy can be a memory leak.</span></span>  <span data-ttu-id="1c0b9-314">当处理大量数据时，如果你在缓存中保存大量内存，可能会导致垃圾回收覆盖缓存查找带来的好处。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-314">When processing large amounts of data, if you hold on to a lot of memory in caches, you can cause garbage collection to override the benefits of your cached lookups.</span></span>  
  
 <span data-ttu-id="1c0b9-315">在本文中，我们讨论了你应该如何注意可能会影响你的应用响应能力的性能瓶颈征兆，对于大型系统或处理大量数据的系统尤为如此。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-315">In this article, we discussed how you should be aware of performance bottleneck symptoms that can affect your app's responsiveness, especially for large systems or systems that process a large amount of data.</span></span> <span data-ttu-id="1c0b9-316">常见的原因包括装箱、字符串操作、LINQ 和 lambda、异步方法中的缓存、没有大小限制或处置策略的缓存、不恰当的字典使用以及来回传递结构。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-316">Common culprits include boxing, string manipulations, LINQ and lambda, caching in async methods, caching without a size limit or disposal policy, inappropriate use of dictionaries, and passing around structures.</span></span>  <span data-ttu-id="1c0b9-317">请记住优化应用的四个事实：</span><span class="sxs-lookup"><span data-stu-id="1c0b9-317">Keep in mind the four facts for tuning your apps:</span></span>  
  
-   <span data-ttu-id="1c0b9-318">切勿过早地优化 – 保持高效并在你发现问题时优化应用。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-318">Don’t prematurely optimize – be productive and tune your app when you spot problems.</span></span>  
  
-   <span data-ttu-id="1c0b9-319">配置文件不会撒谎 – 若不测量，便只是猜测。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-319">Profiles don’t lie – you’re guessing if you’re not measuring.</span></span>  
  
-   <span data-ttu-id="1c0b9-320">好的工具将使一切大不相同 – 下载 PerfView 并且试用。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-320">Good tools make all the difference – download PerfView and try it out.</span></span>  
  
-   <span data-ttu-id="1c0b9-321">一切皆与分配有关 – 这就是编译器平台团队花大部分时间改进新编译器性能的原因所在。</span><span class="sxs-lookup"><span data-stu-id="1c0b9-321">It's all about allocations – that is where the compiler platform team spent most of their time improving the performance of the new compilers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c0b9-322">请参阅</span><span class="sxs-lookup"><span data-stu-id="1c0b9-322">See Also</span></span>  
 [<span data-ttu-id="1c0b9-323">本主题的演示文稿的视频</span><span class="sxs-lookup"><span data-stu-id="1c0b9-323">Video of presentation of this topic</span></span>](http://channel9.msdn.com/Events/TechEd/NorthAmerica/2013/DEV-B333)  
 [<span data-ttu-id="1c0b9-324">性能分析初学者指南</span><span class="sxs-lookup"><span data-stu-id="1c0b9-324">Beginners Guide to Performance Profiling</span></span>](/visualstudio/profiling/beginners-guide-to-performance-profiling)  
 [<span data-ttu-id="1c0b9-325">性能</span><span class="sxs-lookup"><span data-stu-id="1c0b9-325">Performance</span></span>](../../../docs/framework/performance/index.md)  
 [<span data-ttu-id="1c0b9-326">.NET 性能提示</span><span class="sxs-lookup"><span data-stu-id="1c0b9-326">.NET Performance Tips</span></span>](http://msdn.microsoft.com/library/ms973839.aspx)  
 [<span data-ttu-id="1c0b9-327">Windows Phone 性能分析工具</span><span class="sxs-lookup"><span data-stu-id="1c0b9-327">Windows Phone Performance Analysis Tool</span></span>](http://msdn.microsoft.com/magazine/hh781024.aspx)  
 [<span data-ttu-id="1c0b9-328">查找与 Visual Studio 探查器的应用程序瓶颈</span><span class="sxs-lookup"><span data-stu-id="1c0b9-328">Find Application Bottlenecks with Visual Studio Profiler</span></span>](http://msdn.microsoft.com/magazine/cc337887.aspx)  
 [<span data-ttu-id="1c0b9-329">通道 9 PerfView 教程</span><span class="sxs-lookup"><span data-stu-id="1c0b9-329">Channel 9 PerfView tutorials</span></span>](http://channel9.msdn.com/Series/PerfView-Tutorial)  
 [<span data-ttu-id="1c0b9-330">高级性能提示</span><span class="sxs-lookup"><span data-stu-id="1c0b9-330">High-level Performance Tips</span></span>](http://curah.microsoft.com/4604/improving-your-net-apps-startup-performance)  
 [<span data-ttu-id="1c0b9-331">在 GitHub 上的 dotnet/roslyn 存储库</span><span class="sxs-lookup"><span data-stu-id="1c0b9-331">dotnet/roslyn repo on GitHub</span></span>](https://github.com/dotnet/roslyn)
