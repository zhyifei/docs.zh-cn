---
title: 如何在 .NET Core 中使用和调试程序集可卸载性
description: 了解如何使用可回收的 AssemblyLoadContext 来加载和卸载托管程序集，以及如何调试可能阻止卸载成功的问题。
author: janvorli
ms.author: janvorli
ms.date: 02/05/2019
ms.openlocfilehash: a3ba2c2809aedd0af03ec965089f8779c430a335
ms.sourcegitcommit: 09d699aca28ae9723399bbd9d3d44aa0cbd3848d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/19/2019
ms.locfileid: "68671242"
---
# <a name="how-to-use-and-debug-assembly-unloadability-in-net-core"></a><span data-ttu-id="d1a0c-103">如何在 .NET Core 中使用和调试程序集可卸载性</span><span class="sxs-lookup"><span data-stu-id="d1a0c-103">How to use and debug assembly unloadability in .NET Core</span></span>

<span data-ttu-id="d1a0c-104">从 .NET Core 3.0 开始，支持加载和随后卸载一组程序集功能。</span><span class="sxs-lookup"><span data-stu-id="d1a0c-104">Starting with .NET Core 3.0, the ability to load and later unload a set of assemblies is supported.</span></span> <span data-ttu-id="d1a0c-105">在 .NET Framework 中，自定义应用域用于此目的，但 .NET Core 仅支持单个默认应用域。</span><span class="sxs-lookup"><span data-stu-id="d1a0c-105">In .NET Framework, custom app domains were used for this purpose, but .NET Core only supports a single default app domain.</span></span>

<span data-ttu-id="d1a0c-106">.NET Core 3.0 及更高版本支持通过 <xref:System.Runtime.Loader.AssemblyLoadContext> 进行卸载。</span><span class="sxs-lookup"><span data-stu-id="d1a0c-106">.NET Core 3.0 and later versions support unloadability through <xref:System.Runtime.Loader.AssemblyLoadContext>.</span></span> <span data-ttu-id="d1a0c-107">可将一组程序集加载到可回收的 `AssemblyLoadContext` 中，在其中执行方法或仅使用反射检查它们，最后卸载 `AssemblyLoadContext`。</span><span class="sxs-lookup"><span data-stu-id="d1a0c-107">You can load a set of assemblies into a collectible `AssemblyLoadContext`, execute methods in them or just inspect them using reflection, and finally unload the `AssemblyLoadContext`.</span></span> <span data-ttu-id="d1a0c-108">这会卸载加载到该 `AssemblyLoadContext` 中的程序集。</span><span class="sxs-lookup"><span data-stu-id="d1a0c-108">That unloads the assemblies loaded into that `AssemblyLoadContext`.</span></span>

<span data-ttu-id="d1a0c-109">使用 `AssemblyLoadContext` 和使用 AppDomain 进行卸载之间存在一个值得注意的差异。</span><span class="sxs-lookup"><span data-stu-id="d1a0c-109">There's one noteworthy difference between the unloading using `AssemblyLoadContext` and using AppDomains.</span></span> <span data-ttu-id="d1a0c-110">对于 Appdomain，卸载为强制执行。</span><span class="sxs-lookup"><span data-stu-id="d1a0c-110">With AppDomains, the unloading is forced.</span></span> <span data-ttu-id="d1a0c-111">在卸载时，目标 AppDomain 中运行的所有线程都将中止，目标 AppDomain 中创建的托管 COM 对象会被销毁等等。对于 `AssemblyLoadContext`，卸载是“协作式的”。</span><span class="sxs-lookup"><span data-stu-id="d1a0c-111">At the unload time, all threads running in the target AppDomain are aborted, managed COM objects created in the target AppDomain are destroyed, etc. With `AssemblyLoadContext`, the unload is "cooperative".</span></span> <span data-ttu-id="d1a0c-112">调用 <xref:System.Runtime.Loader.AssemblyLoadContext.Unload%2A?displayProperty=nameWithType> 方法只是为了启动卸载。</span><span class="sxs-lookup"><span data-stu-id="d1a0c-112">Calling the <xref:System.Runtime.Loader.AssemblyLoadContext.Unload%2A?displayProperty=nameWithType> method just initiates the unloading.</span></span> <span data-ttu-id="d1a0c-113">以下目标达成后，卸载完成：</span><span class="sxs-lookup"><span data-stu-id="d1a0c-113">The unloading finishes after:</span></span>

- <span data-ttu-id="d1a0c-114">没有线程将程序集中的方法加载到其调用堆栈上的 `AssemblyLoadContext` 中。</span><span class="sxs-lookup"><span data-stu-id="d1a0c-114">No threads have methods from the assemblies loaded into the `AssemblyLoadContext` on their call stacks.</span></span>
- <span data-ttu-id="d1a0c-115">程序集中的任何类型都不会加载到 `AssemblyLoadContext`，这些类型的实例以及 `AssemblyLoadContext` 外部的程序集本身由以下引用：</span><span class="sxs-lookup"><span data-stu-id="d1a0c-115">None of the types from the assemblies loaded into the `AssemblyLoadContext`, instances of those types and the assemblies themselves outside of the `AssemblyLoadContext` are referenced by:</span></span>
  - <span data-ttu-id="d1a0c-116">`AssemblyLoadContext` 外部的引用，弱引用（<xref:System.WeakReference> 或 <xref:System.WeakReference%601>）除外。</span><span class="sxs-lookup"><span data-stu-id="d1a0c-116">References outside of the `AssemblyLoadContext`, except of weak references (<xref:System.WeakReference> or <xref:System.WeakReference%601>).</span></span>
  - <span data-ttu-id="d1a0c-117">强 GC 句柄（<xref:System.Runtime.InteropServices.GCHandleType>.<xref:System.Runtime.InteropServices.GCHandleType.Normal></span><span class="sxs-lookup"><span data-stu-id="d1a0c-117">Strong GC handles (<xref:System.Runtime.InteropServices.GCHandleType>.<xref:System.Runtime.InteropServices.GCHandleType.Normal></span></span> <span data-ttu-id="d1a0c-118">或 <xref:System.Runtime.InteropServices.GCHandleType>.<xref:System.Runtime.InteropServices.GCHandleType.Pinned>），来自 `AssemblyLoadContext` 的内部和外部。</span><span class="sxs-lookup"><span data-stu-id="d1a0c-118">or <xref:System.Runtime.InteropServices.GCHandleType>.<xref:System.Runtime.InteropServices.GCHandleType.Pinned>) from both inside and outside of the `AssemblyLoadContext`.</span></span>

## <a name="using-collectible-assemblyloadcontext"></a><span data-ttu-id="d1a0c-119">使用可回收的 AssemblyLoadContext</span><span class="sxs-lookup"><span data-stu-id="d1a0c-119">Using collectible AssemblyLoadContext</span></span>

<span data-ttu-id="d1a0c-120">本部分包含详细的分步教程，其中演示了一种简单方法，可以将 .NET Core 应用程序加载到可回收的 `AssemblyLoadContext` 中，执行其入口点，然后将其卸载。</span><span class="sxs-lookup"><span data-stu-id="d1a0c-120">This section contains a detailed step-by-step tutorial that shows a simple way to load a .NET Core application into a collectible `AssemblyLoadContext`, execute its entry point, and then unload it.</span></span> <span data-ttu-id="d1a0c-121">可以在 <https://github.com/dotnet/samples/tree/master/core/tutorials/Unloading> 中找到完整示例。</span><span class="sxs-lookup"><span data-stu-id="d1a0c-121">You can find a complete sample at <https://github.com/dotnet/samples/tree/master/core/tutorials/Unloading>.</span></span>

### <a name="create-a-collectible-assemblyloadcontext"></a><span data-ttu-id="d1a0c-122">创建可回收的 AssemblyLoadContext</span><span class="sxs-lookup"><span data-stu-id="d1a0c-122">Create a collectible AssemblyLoadContext</span></span>

<span data-ttu-id="d1a0c-123">需要从 <xref:System.Runtime.Loader.AssemblyLoadContext> 派生类，并重载其 <xref:System.Runtime.Loader.AssemblyLoadContext.Load%2A?displayProperty=nameWithType> 方法。</span><span class="sxs-lookup"><span data-stu-id="d1a0c-123">You need to derive your class from the <xref:System.Runtime.Loader.AssemblyLoadContext> and overload its <xref:System.Runtime.Loader.AssemblyLoadContext.Load%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="d1a0c-124">该方法解析对所有程序集的引用，这些程序集是加载到该 `AssemblyLoadContext` 中的程序集的依赖项。</span><span class="sxs-lookup"><span data-stu-id="d1a0c-124">That method resolves references to all assemblies that are dependencies of assemblies loaded into that `AssemblyLoadContext`.</span></span>
<span data-ttu-id="d1a0c-125">以下代码是最简单的自定义 `AssemblyLoadContext` 示例：</span><span class="sxs-lookup"><span data-stu-id="d1a0c-125">The following code is an example of the simplest custom `AssemblyLoadContext`:</span></span>

[!code-csharp[Simple custom AssemblyLoadContext](~/samples/snippets/standard/assembly/unloading/simple_example.cs#1)]

<span data-ttu-id="d1a0c-126">如你所见，`Load` 方法返回 `null`。</span><span class="sxs-lookup"><span data-stu-id="d1a0c-126">As you can see, the `Load` method returns `null`.</span></span> <span data-ttu-id="d1a0c-127">这意味着所有依赖项程序集都会加载到默认上下文中，而新上下文仅包含显式加载到其中的程序集。</span><span class="sxs-lookup"><span data-stu-id="d1a0c-127">That means that all the dependency assemblies are loaded into the default context, and the new context contains only the assemblies explicitly loaded into it.</span></span>

<span data-ttu-id="d1a0c-128">若要在 `AssemblyLoadContext` 中加载部分或全部依赖项，可以在 `Load` 方法中使用 `AssemblyDependencyResolver`。</span><span class="sxs-lookup"><span data-stu-id="d1a0c-128">If you want to load some or all of the dependencies into the `AssemblyLoadContext` too, you can use the `AssemblyDependencyResolver` in the `Load` method.</span></span> <span data-ttu-id="d1a0c-129">`AssemblyDependencyResolver` 使用加载到上下文中的主程序集目录中包含的 .deps.json 文件并使用该目录中的程序集文件将程序集名称解析为绝对程序集文件路径  。</span><span class="sxs-lookup"><span data-stu-id="d1a0c-129">The `AssemblyDependencyResolver` resolves the assembly names to absolute assembly file paths using the *.deps.json* file contained in the directory of the main assembly loaded into the context and using assembly files in that directory.</span></span>

[!code-csharp[Advanced custom AssemblyLoadContext](~/samples/snippets/standard/assembly/unloading/complex_assemblyloadcontext.cs)]

### <a name="use-a-custom-collectible-assemblyloadcontext"></a><span data-ttu-id="d1a0c-130">使用自定义且可回收的 AssemblyLoadContext</span><span class="sxs-lookup"><span data-stu-id="d1a0c-130">Use a custom collectible AssemblyLoadContext</span></span>

<span data-ttu-id="d1a0c-131">本部分假定使用的是 `TestAssemblyLoadContext` 的较简单版本。</span><span class="sxs-lookup"><span data-stu-id="d1a0c-131">This section assumes the simpler version of the `TestAssemblyLoadContext` is being used.</span></span>

<span data-ttu-id="d1a0c-132">可以创建自定义 `AssemblyLoadContext` 实例并将程序集加载到其中，如下所示：</span><span class="sxs-lookup"><span data-stu-id="d1a0c-132">You can create an instance of the custom `AssemblyLoadContext` and load an assembly into it as follows:</span></span>

[!code-csharp[Part 1](~/samples/snippets/standard/assembly/unloading/simple_example.cs#3)]

<span data-ttu-id="d1a0c-133">对于已加载的程序集引用的每个程序集，将调用 `TestAssemblyLoadContext.Load` 方法，这样 `TestAssemblyLoadContext` 可以决定从何处获取程序集。</span><span class="sxs-lookup"><span data-stu-id="d1a0c-133">For each of the assemblies referenced by the loaded assembly, the `TestAssemblyLoadContext.Load` method is called so that the `TestAssemblyLoadContext` can decide where to get the assembly from.</span></span> <span data-ttu-id="d1a0c-134">在示例中，它返回 `null` 以指示它应从运行时默认加载程序集的位置加载到默认上下文中。</span><span class="sxs-lookup"><span data-stu-id="d1a0c-134">In our case, it returns `null` to indicate that it should be loaded into the default context from locations that the runtime uses to load assemblies by default.</span></span>

<span data-ttu-id="d1a0c-135">现在程序集已加载，可从中执行方法。</span><span class="sxs-lookup"><span data-stu-id="d1a0c-135">Now that an assembly was loaded, you can execute a method from it.</span></span> <span data-ttu-id="d1a0c-136">运行 `Main` 方法：</span><span class="sxs-lookup"><span data-stu-id="d1a0c-136">Run the `Main` method:</span></span>

[!code-csharp[Part 2](~/samples/snippets/standard/assembly/unloading/simple_example.cs#4)]

<span data-ttu-id="d1a0c-137">在 `Main` 方法返回后，可通过在自定义 `AssemblyLoadContext` 上调用 `Unload` 方法或删除对 `AssemblyLoadContext` 的引用来启动卸载：</span><span class="sxs-lookup"><span data-stu-id="d1a0c-137">After the `Main` method returns, you can initiate unloading by either calling the `Unload` method on the custom `AssemblyLoadContext` or getting rid of the reference you have to the `AssemblyLoadContext`:</span></span>

[!code-csharp[Part 3](~/samples/snippets/standard/assembly/unloading/simple_example.cs#5)]

<span data-ttu-id="d1a0c-138">这足以卸载测试程序集。</span><span class="sxs-lookup"><span data-stu-id="d1a0c-138">This is sufficient to unload the test assembly.</span></span> <span data-ttu-id="d1a0c-139">将所有上述内容放入单独的非可内联方法中，以确保 `TestAssemblyLoadContext``Assembly` 和 `MethodInfo` (`Assembly.EntryPoint`) 无法通过堆栈槽引用（实际或 JIT 引入的本地变量）保持活动状态。</span><span class="sxs-lookup"><span data-stu-id="d1a0c-139">Let's actually put all of this into a separate non-inlineable method to ensure that the `TestAssemblyLoadContext`, `Assembly`, and `MethodInfo` (the `Assembly.EntryPoint`) can't be kept alive by stack slot references (real- or JIT-introduced locals).</span></span> <span data-ttu-id="d1a0c-140">这可以使 `TestAssemblyLoadContext` 保持活动状态并阻止其卸载。</span><span class="sxs-lookup"><span data-stu-id="d1a0c-140">That could keep the `TestAssemblyLoadContext` alive and prevent the unload.</span></span>

<span data-ttu-id="d1a0c-141">此外，返回对 `AssemblyLoadContext` 的弱引用，以便之后可以使用它来检测卸载是否已完成。</span><span class="sxs-lookup"><span data-stu-id="d1a0c-141">Also, return a weak reference to the `AssemblyLoadContext` so that you can use it later to detect unload completion.</span></span>

[!code-csharp[Part 4](~/samples/snippets/standard/assembly/unloading/simple_example.cs#2)]

<span data-ttu-id="d1a0c-142">现在，可运行此函数以加载、执行和卸载程序集。</span><span class="sxs-lookup"><span data-stu-id="d1a0c-142">Now you can run this function to load, execute, and unload the assembly.</span></span>

[!code-csharp[Part 5](~/samples/snippets/standard/assembly/unloading/simple_example.cs#6)]

<span data-ttu-id="d1a0c-143">但是，卸载不会立即完成。</span><span class="sxs-lookup"><span data-stu-id="d1a0c-143">However, the unload doesn't complete immediately.</span></span> <span data-ttu-id="d1a0c-144">如上所述，它依赖于 GC 来收集测试程序集中的所有对象。</span><span class="sxs-lookup"><span data-stu-id="d1a0c-144">As previously mentioned, it relies on the GC to collect all the objects from the test assembly.</span></span> <span data-ttu-id="d1a0c-145">在许多情况下，没有必要等待卸载完成。</span><span class="sxs-lookup"><span data-stu-id="d1a0c-145">In many cases, it isn't necessary to wait for the unload completion.</span></span> <span data-ttu-id="d1a0c-146">但是，某些情况下，了解卸载已经完成非常有用。</span><span class="sxs-lookup"><span data-stu-id="d1a0c-146">However, there are cases where it's useful to know that the unload has finished.</span></span> <span data-ttu-id="d1a0c-147">例如，你可能希望删除从磁盘加载到自定义 `AssemblyLoadContext` 中的程序集文件。</span><span class="sxs-lookup"><span data-stu-id="d1a0c-147">For example, you may want to delete the assembly file that was loaded into the custom `AssemblyLoadContext` from disk.</span></span> <span data-ttu-id="d1a0c-148">在这种情况下，可以使用以下代码片段。</span><span class="sxs-lookup"><span data-stu-id="d1a0c-148">In such a case, the following code snippet can be used.</span></span> <span data-ttu-id="d1a0c-149">它会触发 GC 并等待循环中挂起的终结器，直到自定义 `AssemblyLoadContext` 的弱引用被设置为 `null`，表示已收集目标对象。</span><span class="sxs-lookup"><span data-stu-id="d1a0c-149">It triggers a GC and waits for pending finalizers in a loop until the weak reference to the custom `AssemblyLoadContext` is set to `null`, indicating the target object was collected.</span></span> <span data-ttu-id="d1a0c-150">请注意，在大多数情况下，只需要通过循环传递一次。</span><span class="sxs-lookup"><span data-stu-id="d1a0c-150">Note that in most cases, just one pass through the loop is required.</span></span> <span data-ttu-id="d1a0c-151">但对于更复杂的情况，由 `AssemblyLoadContext` 中运行的代码所创建的对象具有终结器，则可能需要更多传递。</span><span class="sxs-lookup"><span data-stu-id="d1a0c-151">However, for more complex cases where objects created by the code running in the `AssemblyLoadContext` have finalizers, more passes may be needed.</span></span>

[!code-csharp[Part 6](~/samples/snippets/standard/assembly/unloading/simple_example.cs#7)]

### <a name="the-unloading-event"></a><span data-ttu-id="d1a0c-152">卸载事件</span><span class="sxs-lookup"><span data-stu-id="d1a0c-152">The Unloading event</span></span>

<span data-ttu-id="d1a0c-153">某些情况下，加载到自定义 `AssemblyLoadContext` 中的代码可能需要在启动卸载时执行一些清理。</span><span class="sxs-lookup"><span data-stu-id="d1a0c-153">In some cases, it may be necessary for the code loaded into a custom `AssemblyLoadContext` to perform some cleanup when the unloading is initiated.</span></span> <span data-ttu-id="d1a0c-154">例如，可能需要停止线程、清理某些强 GC 句柄等。在这种情况下可以使用 `Unloading` 事件。</span><span class="sxs-lookup"><span data-stu-id="d1a0c-154">For example, it may need to stop threads, clean up some strong GC handles, etc. The `Unloading` event can be used in such cases.</span></span> <span data-ttu-id="d1a0c-155">执行必要清理的处理程序可与此事件挂钩。</span><span class="sxs-lookup"><span data-stu-id="d1a0c-155">A handler that performs the necessary cleanup can be hooked to this event.</span></span>

### <a name="troubleshoot-unloadability-issues"></a><span data-ttu-id="d1a0c-156">解决可卸载性问题</span><span class="sxs-lookup"><span data-stu-id="d1a0c-156">Troubleshoot unloadability issues</span></span>

<span data-ttu-id="d1a0c-157">由于卸载的协作性质，很容易忘记使内容在可回收的 `AssemblyLoadContext` 中保持活动状态并阻止卸载的引用。</span><span class="sxs-lookup"><span data-stu-id="d1a0c-157">Due to the cooperative nature of the unloading, it's easy to forget about references keeping the stuff in a collectible `AssemblyLoadContext` alive and preventing unload.</span></span> <span data-ttu-id="d1a0c-158">以下是可以包含引用内容（其中一些不明显）的摘要：</span><span class="sxs-lookup"><span data-stu-id="d1a0c-158">Here is a summary of things (some of them non-obvious) that can hold the references:</span></span>

- <span data-ttu-id="d1a0c-159">保存于可回收的 `AssemblyLoadContext` 外部、存储在堆栈槽或处理器寄存器（由用户代码显式创建或由 JIT 隐式创建的方法本地变量）中的常规引用、静态变量或强/固定 GC 句柄以及以可传递的方式指向：</span><span class="sxs-lookup"><span data-stu-id="d1a0c-159">Regular references held from outside of the collectible `AssemblyLoadContext`, stored in a stack slot or a processor register (method locals, either explicitly created by the user code or implicitly by the JIT), a static variable or a strong / pinning GC handle, and transitively pointing to:</span></span>
  - <span data-ttu-id="d1a0c-160">加载到可回收的 `AssemblyLoadContext` 中的程序集。</span><span class="sxs-lookup"><span data-stu-id="d1a0c-160">An assembly loaded into the collectible `AssemblyLoadContext`.</span></span>
  - <span data-ttu-id="d1a0c-161">此类程序集中的类型。</span><span class="sxs-lookup"><span data-stu-id="d1a0c-161">A type from such an assembly.</span></span>
  - <span data-ttu-id="d1a0c-162">此类程序集中的类型的实例。</span><span class="sxs-lookup"><span data-stu-id="d1a0c-162">An instance of a type from such an assembly.</span></span>
- <span data-ttu-id="d1a0c-163">从加载到可回收的 `AssemblyLoadContext` 程序集中运行代码的线程。</span><span class="sxs-lookup"><span data-stu-id="d1a0c-163">Threads running code from an assembly loaded into the collectible `AssemblyLoadContext`.</span></span>
- <span data-ttu-id="d1a0c-164">在可回收的 `AssemblyLoadContext` 中创建的自定义非可回收 `AssemblyLoadContext` 类型的实例</span><span class="sxs-lookup"><span data-stu-id="d1a0c-164">Instances of custom non-collectible `AssemblyLoadContext` types created inside of the collectible `AssemblyLoadContext`</span></span>
- <span data-ttu-id="d1a0c-165">将回调设置为自定义 `AssemblyLoadContext` 中的方法的挂起 <xref:System.Threading.RegisteredWaitHandle> 实例</span><span class="sxs-lookup"><span data-stu-id="d1a0c-165">Pending <xref:System.Threading.RegisteredWaitHandle> instances with callbacks set to methods in the custom `AssemblyLoadContext`</span></span>

<span data-ttu-id="d1a0c-166">查找堆栈槽/处理器寄存器根对象的提示：</span><span class="sxs-lookup"><span data-stu-id="d1a0c-166">Hints to find stack slot / processor register rooting an object:</span></span>

- <span data-ttu-id="d1a0c-167">即使没有用户创建的本地变量，也可以通过直接将函数调用结果传递给另一个函数来创建根。</span><span class="sxs-lookup"><span data-stu-id="d1a0c-167">Passing function call results directly to another function may create a root even though there is no user-created local variable.</span></span>
- <span data-ttu-id="d1a0c-168">如果在方法中随时都可以获得对象的引用，则 JIT 可能决定将引用保留在堆栈槽/处理器寄存器中，只要它在当前函数中有所需要。</span><span class="sxs-lookup"><span data-stu-id="d1a0c-168">If a reference to an object was available at any point in a method, the JIT might have decided to keep the reference in a stack slot / processor register for as long as it wants in the current function.</span></span>

## <a name="debug-unloading-issues"></a><span data-ttu-id="d1a0c-169">调试卸载问题</span><span class="sxs-lookup"><span data-stu-id="d1a0c-169">Debug unloading issues</span></span>

<span data-ttu-id="d1a0c-170">调试卸载问题可能比较繁琐。</span><span class="sxs-lookup"><span data-stu-id="d1a0c-170">Debugging issues with unloading can be tedious.</span></span> <span data-ttu-id="d1a0c-171">你可能会遇到这样的情况：你不知道哪些内容可以使 `AssemblyLoadContext` 保持活动状态，但卸载会失败。</span><span class="sxs-lookup"><span data-stu-id="d1a0c-171">You can get into situations where you don't know what can be holding an `AssemblyLoadContext` alive, but the unload fails.</span></span>
<span data-ttu-id="d1a0c-172">帮助解决此问题的最佳武器是带有 SOS 插件的 WinDbg（Unix 上的 LLDB）。</span><span class="sxs-lookup"><span data-stu-id="d1a0c-172">The best weapon to help with that is WinDbg (LLDB on Unix) with the SOS plugin.</span></span> <span data-ttu-id="d1a0c-173">需要查找哪些内容使属于特定 `AssemblyLoadContext` 的 `LoaderAllocator` 保持活动状态。</span><span class="sxs-lookup"><span data-stu-id="d1a0c-173">You need to find what's keeping a `LoaderAllocator` belonging to the specific `AssemblyLoadContext` alive.</span></span>
<span data-ttu-id="d1a0c-174">此插件可让你查看 GC 堆对象、其层次结构和根。</span><span class="sxs-lookup"><span data-stu-id="d1a0c-174">This plugin allows you to look at GC heap objects, their hierarchies, and roots.</span></span>
<span data-ttu-id="d1a0c-175">若要将插件加载到调试器中，请在调试器命令行中输入以下命令：</span><span class="sxs-lookup"><span data-stu-id="d1a0c-175">To load the plugin into the debugger, enter the following command in the debugger command line:</span></span>

<span data-ttu-id="d1a0c-176">在 WinDbg（似乎 WinDbg 在进入 .NET Core 应用程序时会自动执行此操作）中：</span><span class="sxs-lookup"><span data-stu-id="d1a0c-176">In WinDbg (it seems WinDbg does that automatically when breaking into .NET Core application):</span></span>

```console
.loadby sos coreclr
```

<span data-ttu-id="d1a0c-177">在 LLDB 中：</span><span class="sxs-lookup"><span data-stu-id="d1a0c-177">In LLDB:</span></span>

```console
plugin load /path/to/libsosplugin.so
```

<span data-ttu-id="d1a0c-178">尝试调试卸载时出现问题的示例程序。</span><span class="sxs-lookup"><span data-stu-id="d1a0c-178">Let's try to debug an example program that has problems with unloading.</span></span> <span data-ttu-id="d1a0c-179">源代码包含在以下内容中。</span><span class="sxs-lookup"><span data-stu-id="d1a0c-179">Source code is included below.</span></span> <span data-ttu-id="d1a0c-180">在 WinDbg 下运行它时，程序将在尝试检查卸载是否成功后立即进入调试器。</span><span class="sxs-lookup"><span data-stu-id="d1a0c-180">When you run it under WinDbg, the program breaks into the debugger right after attempting to check for the unload success.</span></span> <span data-ttu-id="d1a0c-181">然后即可开始查找原因。</span><span class="sxs-lookup"><span data-stu-id="d1a0c-181">You can then start looking for the culprits.</span></span>

<span data-ttu-id="d1a0c-182">请注意，如果使用 Unix 上的 LLDB 进行调试，则以下示例中的 SOS 命令没有在它们前面的 `!`。</span><span class="sxs-lookup"><span data-stu-id="d1a0c-182">Note that if you debug using LLDB on Unix, the SOS commands in the following examples don't have the `!` in front of them.</span></span>

```console
!dumpheap -type LoaderAllocator
```

<span data-ttu-id="d1a0c-183">此命令转储类型名称包含 GC 堆中的 `LoaderAllocator` 的所有对象。</span><span class="sxs-lookup"><span data-stu-id="d1a0c-183">This command dumps all objects with a type name containing `LoaderAllocator` that are in the GC heap.</span></span> <span data-ttu-id="d1a0c-184">下面是一个示例：</span><span class="sxs-lookup"><span data-stu-id="d1a0c-184">Here is an example:</span></span>

```console
         Address               MT     Size
000002b78000ce40 00007ffadc93a288       48     
000002b78000ceb0 00007ffadc93a218       24     

Statistics:
              MT    Count    TotalSize Class Name
00007ffadc93a218        1           24 System.Reflection.LoaderAllocatorScout
00007ffadc93a288        1           48 System.Reflection.LoaderAllocator
Total 2 objects
```

<span data-ttu-id="d1a0c-185">在下面的“Statistics:”部分中，检查属于 `System.Reflection.LoaderAllocator` 的 `MT` (`MethodTable`)，这是我们关注的对象。</span><span class="sxs-lookup"><span data-stu-id="d1a0c-185">In the "Statistics:" part below, check the `MT` (`MethodTable`) belonging to the `System.Reflection.LoaderAllocator`, which is the object we care about.</span></span> <span data-ttu-id="d1a0c-186">然后在开头的列表中，查找 `MT` 匹配该条目的条目，并获取对象本身的地址。</span><span class="sxs-lookup"><span data-stu-id="d1a0c-186">Then in the list at the beginning, find the entry with `MT` matching that one and get the address of the object itself.</span></span> <span data-ttu-id="d1a0c-187">在示例中，其为“000002b78000ce40”</span><span class="sxs-lookup"><span data-stu-id="d1a0c-187">In our case, it is "000002b78000ce40"</span></span>

<span data-ttu-id="d1a0c-188">现在我们知道了 `LoaderAllocator` 对象的地址，可使用另一个命令来查找其 GC 根</span><span class="sxs-lookup"><span data-stu-id="d1a0c-188">Now that we know the address of the `LoaderAllocator` object, we can use another command to find its GC roots</span></span>

```console
!gcroot -all 0x000002b78000ce40 
```

<span data-ttu-id="d1a0c-189">此命令转储通向 `LoaderAllocator` 实例的对象引用链。</span><span class="sxs-lookup"><span data-stu-id="d1a0c-189">This command dumps the chain of object references that lead to the `LoaderAllocator` instance.</span></span> <span data-ttu-id="d1a0c-190">该列表以根（使 `LoaderAllocator` 保持活动状态的实体）开头，因此为正在调试的问题的核心。</span><span class="sxs-lookup"><span data-stu-id="d1a0c-190">The list starts with the root, which is the entity that keeps our `LoaderAllocator` alive and thus is the core of the problem you're debugging.</span></span> <span data-ttu-id="d1a0c-191">根可以是堆栈槽、处理器寄存器、GC 句柄或静态变量。</span><span class="sxs-lookup"><span data-stu-id="d1a0c-191">The root can be a stack slot, a processor register, a GC handle, or a static variable.</span></span>

<span data-ttu-id="d1a0c-192">以下是 `gcroot` 命令输出的示例：</span><span class="sxs-lookup"><span data-stu-id="d1a0c-192">Here is an example of the output of the `gcroot` command:</span></span>

```console
Thread 4ac:
    000000cf9499dd20 00007ffa7d0236bc example.Program.Main(System.String[]) [E:\unloadability\example\Program.cs @ 70]
        rbp-20: 000000cf9499dd90
            ->  000002b78000d328 System.Reflection.RuntimeMethodInfo
            ->  000002b78000d1f8 System.RuntimeType+RuntimeTypeCache
            ->  000002b78000d1d0 System.RuntimeType
            ->  000002b78000ce40 System.Reflection.LoaderAllocator

HandleTable:
    000002b7f8a81198 (strong handle)
    -> 000002b78000d948 test.Test
    -> 000002b78000ce40 System.Reflection.LoaderAllocator

    000002b7f8a815f8 (pinned handle)
    -> 000002b790001038 System.Object[]
    -> 000002b78000d390 example.TestInfo
    -> 000002b78000d328 System.Reflection.RuntimeMethodInfo
    -> 000002b78000d1f8 System.RuntimeType+RuntimeTypeCache
    -> 000002b78000d1d0 System.RuntimeType
    -> 000002b78000ce40 System.Reflection.LoaderAllocator

Found 3 roots.
```

<span data-ttu-id="d1a0c-193">现在需要确定根所在的位置以便对其进行修复。</span><span class="sxs-lookup"><span data-stu-id="d1a0c-193">Now you need to figure out where the root is located so you can fix it.</span></span> <span data-ttu-id="d1a0c-194">最简单的情况是根为堆栈槽或处理器寄存器。</span><span class="sxs-lookup"><span data-stu-id="d1a0c-194">The easiest case is when the root is a stack slot or a processor register.</span></span> <span data-ttu-id="d1a0c-195">在这种情况下，`gcroot` 会显示其框架包含根的函数的名称以及执行该函数的线程。</span><span class="sxs-lookup"><span data-stu-id="d1a0c-195">In that case, the `gcroot` shows you the name of the function whose frame contains the root and the thread executing that function.</span></span> <span data-ttu-id="d1a0c-196">困难的情况是根为静态变量或 GC 句柄。</span><span class="sxs-lookup"><span data-stu-id="d1a0c-196">The difficult case is when the root is a static variable or a GC handle.</span></span> 

<span data-ttu-id="d1a0c-197">在上面的示例中，第一个根为 `System.Reflection.RuntimeMethodInfo` 类型的本地变量，存储在函数 `example.Program.Main(System.String[])` 的框架中，地址为 `rbp-20`（`rbp` 意为处理器寄存器 `rbp`，-20 意为该寄存器的十六进制偏移量）。</span><span class="sxs-lookup"><span data-stu-id="d1a0c-197">In the previous example, the first root is a local of type `System.Reflection.RuntimeMethodInfo` stored in the frame of the function `example.Program.Main(System.String[])` at address `rbp-20` (`rbp` is the processor register `rbp` and -20 is a hexadecimal offset from that register).</span></span>

<span data-ttu-id="d1a0c-198">第二个根为普通（强）`GCHandle`，其包含对 `test.Test` 类实例的引用。</span><span class="sxs-lookup"><span data-stu-id="d1a0c-198">The second root is a normal (strong) `GCHandle` that holds a reference to an instance of the `test.Test` class.</span></span> 

<span data-ttu-id="d1a0c-199">第三个根为固定的 `GCHandle`。</span><span class="sxs-lookup"><span data-stu-id="d1a0c-199">The third root is a pinned `GCHandle`.</span></span> <span data-ttu-id="d1a0c-200">此变量实际上是一个静态变量。</span><span class="sxs-lookup"><span data-stu-id="d1a0c-200">This one is actually a static variable.</span></span> <span data-ttu-id="d1a0c-201">遗憾的是，无法进行澄清。</span><span class="sxs-lookup"><span data-stu-id="d1a0c-201">Unfortunately, there is no way to tell.</span></span> <span data-ttu-id="d1a0c-202">引用类型的静态变量存储在内部运行时结构中的托管对象数组中。</span><span class="sxs-lookup"><span data-stu-id="d1a0c-202">Statics for reference types are stored in a managed object array in internal runtime structures.</span></span>

<span data-ttu-id="d1a0c-203">另一种可阻止卸载 `AssemblyLoadContext` 的情况为，线程具有来源于加载到其堆栈上的 `AssemblyLoadContext` 程序集的方法框架。</span><span class="sxs-lookup"><span data-stu-id="d1a0c-203">Another case that can prevent unloading of an `AssemblyLoadContext` is when a thread has a frame of a method from an assembly loaded into the `AssemblyLoadContext` on its stack.</span></span> <span data-ttu-id="d1a0c-204">可通过转储所有线程的托管调用堆栈进行检查：</span><span class="sxs-lookup"><span data-stu-id="d1a0c-204">You can check that by dumping managed call stacks of all threads:</span></span>

```console
~*e !clrstack
```

<span data-ttu-id="d1a0c-205">此命令表示“将 `!clrstack` 命令应用于所有线程”。</span><span class="sxs-lookup"><span data-stu-id="d1a0c-205">The command means "apply to all threads the `!clrstack` command".</span></span> <span data-ttu-id="d1a0c-206">以下是此示例中该命令的输出。</span><span class="sxs-lookup"><span data-stu-id="d1a0c-206">The following is the output of that command for the example.</span></span> <span data-ttu-id="d1a0c-207">遗憾的是，Unix 上的 LLDB 无法将命令应用于所有线程，因此，需要手动切换线程并重复 `clrstack` 命令。</span><span class="sxs-lookup"><span data-stu-id="d1a0c-207">Unfortunately, LLDB on Unix doesn't have any way to apply a command to all threads, so you'll need to resort to manually switching threads and repeating the `clrstack` command.</span></span>
<span data-ttu-id="d1a0c-208">忽略调试器显示“无法审核托管堆栈”的所有线程。</span><span class="sxs-lookup"><span data-stu-id="d1a0c-208">Ignore all threads where the debugger says "Unable to walk the managed stack."</span></span>

```console
OS Thread Id: 0x6ba8 (0)
        Child SP               IP Call Site
0000001fc697d5c8 00007ffb50d9de12 [HelperMethodFrame: 0000001fc697d5c8] System.Diagnostics.Debugger.BreakInternal()
0000001fc697d6d0 00007ffa864765fa System.Diagnostics.Debugger.Break()
0000001fc697d700 00007ffa864736bc example.Program.Main(System.String[]) [E:\unloadability\example\Program.cs @ 70]
0000001fc697d998 00007ffae5fdc1e3 [GCFrame: 0000001fc697d998] 
0000001fc697df28 00007ffae5fdc1e3 [GCFrame: 0000001fc697df28] 
OS Thread Id: 0x2ae4 (1)
Unable to walk the managed stack. The current thread is likely not a 
managed thread. You can run !threads to get a list of managed threads in
the process
Failed to start stack walk: 80070057
OS Thread Id: 0x61a4 (2)
Unable to walk the managed stack. The current thread is likely not a 
managed thread. You can run !threads to get a list of managed threads in
the process
Failed to start stack walk: 80070057
OS Thread Id: 0x7fdc (3)
Unable to walk the managed stack. The current thread is likely not a 
managed thread. You can run !threads to get a list of managed threads in
the process
Failed to start stack walk: 80070057
OS Thread Id: 0x5390 (4)
Unable to walk the managed stack. The current thread is likely not a 
managed thread. You can run !threads to get a list of managed threads in
the process
Failed to start stack walk: 80070057
OS Thread Id: 0x5ec8 (5)
        Child SP               IP Call Site
0000001fc70ff6e0 00007ffb5437f6e4 [DebuggerU2MCatchHandlerFrame: 0000001fc70ff6e0] 
OS Thread Id: 0x4624 (6)
        Child SP               IP Call Site
GetFrameContext failed: 1
0000000000000000 0000000000000000 
OS Thread Id: 0x60bc (7)
        Child SP               IP Call Site
0000001fc727f158 00007ffb5437fce4 [HelperMethodFrame: 0000001fc727f158] System.Threading.Thread.SleepInternal(Int32)
0000001fc727f260 00007ffb37ea7c2b System.Threading.Thread.Sleep(Int32)
0000001fc727f290 00007ffa865005b3 test.Program.ThreadProc() [E:\unloadability\test\Program.cs @ 17]
0000001fc727f2c0 00007ffb37ea6a5b System.Threading.Thread.ThreadMain_ThreadStart()
0000001fc727f2f0 00007ffadbc4cbe3 System.Threading.ExecutionContext.RunInternal(System.Threading.ExecutionContext, System.Threading.ContextCallback, System.Object)
0000001fc727f568 00007ffae5fdc1e3 [GCFrame: 0000001fc727f568] 
0000001fc727f7f0 00007ffae5fdc1e3 [DebuggerU2MCatchHandlerFrame: 0000001fc727f7f0] 

```

<span data-ttu-id="d1a0c-209">如你所见，最后一个线程具有 `test.Program.ThreadProc()`。</span><span class="sxs-lookup"><span data-stu-id="d1a0c-209">As you can see, the last thread has `test.Program.ThreadProc()`.</span></span> <span data-ttu-id="d1a0c-210">这是从加载到 `AssemblyLoadContext` 的程序集中的函数，因此它使 `AssemblyLoadContext` 保持活动状态。</span><span class="sxs-lookup"><span data-stu-id="d1a0c-210">This is a function from the assembly loaded into the `AssemblyLoadContext`, and so it keeps the `AssemblyLoadContext` alive.</span></span>

## <a name="example-source-with-unloadability-issues"></a><span data-ttu-id="d1a0c-211">具有可卸载性问题的示例源</span><span class="sxs-lookup"><span data-stu-id="d1a0c-211">Example source with unloadability issues</span></span>

<span data-ttu-id="d1a0c-212">上面的调试示例中使用了以下代码。</span><span class="sxs-lookup"><span data-stu-id="d1a0c-212">The following code is used in the previous debugging example.</span></span>

### <a name="main-testing-program"></a><span data-ttu-id="d1a0c-213">主要测试程序</span><span class="sxs-lookup"><span data-stu-id="d1a0c-213">Main testing program</span></span>

[!code-csharp[Main testing program](~/samples/snippets/standard/assembly/unloading/unloadability_issues_example_main.cs)]

## <a name="program-loaded-into-the-testassemblyloadcontext"></a><span data-ttu-id="d1a0c-214">程序已加载到 TestAssemblyLoadContext 中</span><span class="sxs-lookup"><span data-stu-id="d1a0c-214">Program loaded into the TestAssemblyLoadContext</span></span>

<span data-ttu-id="d1a0c-215">以下代码表示传递给主测试程序中的 `ExecuteAndUnload` 方法的 `test.dll`。</span><span class="sxs-lookup"><span data-stu-id="d1a0c-215">The following code represents the `test.dll` passed to the `ExecuteAndUnload` method in the main testing program.</span></span>

[!code-csharp[Program loaded into the TestAssemblyLoadContext](~/samples/snippets/standard/assembly/unloading/unloadability_issues_example_test.cs)]
