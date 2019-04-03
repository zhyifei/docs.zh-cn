---
title: 内存<T>和跨度<T>使用准则
ms.date: 10/01/2018
helpviewer_keywords:
- Memory&lt;T&gt; and Span&lt;T&gt; best practices
- using Memory&lt;T&gt; and Span&lt;T&gt;
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e942b3f6f6572c05d42a0267f98e6c876a113616
ms.sourcegitcommit: 8258515adc6c37ab6278e5a3d102d593246f8672
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "58504335"
---
# <a name="memoryt-and-spant-usage-guidelines"></a><span data-ttu-id="11e06-102">内存\<T> 和跨度\<T> 使用准则</span><span class="sxs-lookup"><span data-stu-id="11e06-102">Memory\<T> and Span\<T> usage guidelines</span></span>

<span data-ttu-id="11e06-103">.NET Core 包括多个表示内存的任意连续区域的类型。</span><span class="sxs-lookup"><span data-stu-id="11e06-103">.NET Core includes a number of types that represent an arbitrary contiguous region of memory.</span></span> <span data-ttu-id="11e06-104">.NET Core 2.0 引入了 <xref:System.Span%601> 和 <xref:System.ReadOnlySpan%601>，它们是可由托管或非托管内存提供支持的轻量级内存缓冲区。</span><span class="sxs-lookup"><span data-stu-id="11e06-104">.NET Core 2.0 introduced <xref:System.Span%601> and <xref:System.ReadOnlySpan%601>, which are lightweight memory buffers that can be backed by managed or unmanaged memory.</span></span> <span data-ttu-id="11e06-105">由于这些类型可以存储在堆栈上，因此它们不适用于多种方案，包括异步方法调用。</span><span class="sxs-lookup"><span data-stu-id="11e06-105">Because these types can be stored on the stack, they are unsuitable for a number of scenarios, including asynchronous method calls.</span></span> <span data-ttu-id="11e06-106">.NET Core 2.1 添加了其他一些类型，包括 <xref:System.Memory%601>、<xref:System.ReadOnlyMemory%601>、<xref:System.Buffers.IMemoryOwner%601> 和 <xref:System.Buffers.MemoryPool%601>。</span><span class="sxs-lookup"><span data-stu-id="11e06-106">.NET Core 2.1 adds a number of additional types, including <xref:System.Memory%601>, <xref:System.ReadOnlyMemory%601>, <xref:System.Buffers.IMemoryOwner%601>, and <xref:System.Buffers.MemoryPool%601>.</span></span> <span data-ttu-id="11e06-107">与 <xref:System.Span%601> 相同，<xref:System.Memory%601> 及其相关类型可以由托管和非托管内存提供支持。</span><span class="sxs-lookup"><span data-stu-id="11e06-107">Like <xref:System.Span%601>, <xref:System.Memory%601> and its related types can be backed by both managed and unmanaged memory.</span></span> <span data-ttu-id="11e06-108">与 <xref:System.Span%601> 不同，<xref:System.Memory%601> 只能存储在托管堆上。</span><span class="sxs-lookup"><span data-stu-id="11e06-108">Unlike <xref:System.Span%601>, <xref:System.Memory%601> can only be stored on the managed heap.</span></span>

<span data-ttu-id="11e06-109"><xref:System.Span%601> 和 <xref:System.Memory%601> 都是可用于管道的结构化数据的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="11e06-109">Both <xref:System.Span%601> and <xref:System.Memory%601> are buffers of structured data that can be used in pipelines.</span></span> <span data-ttu-id="11e06-110">也就是说，它们设计的目的是将某些或所有数据有效地传递到管道中的组件，这些组件可以对其进行处理并（可选）修改缓冲区。</span><span class="sxs-lookup"><span data-stu-id="11e06-110">That is, they are designed so that some or all of the data can be efficiently passed to components in the pipeline, which can process them and optionally modify the buffer.</span></span> <span data-ttu-id="11e06-111">由于 <xref:System.Memory%601> 及其相关类型可由多个组件或多个线程访问，因此开发人员必须遵循一些标准使用准则才能生成可靠的代码。</span><span class="sxs-lookup"><span data-stu-id="11e06-111">Because <xref:System.Memory%601> and its related types can be accessed by multiple components or by multiple threads, it's important that developers follow some standard usage guidelines to produce robust code.</span></span>

## <a name="owners-consumers-and-lifetime-management"></a><span data-ttu-id="11e06-112">所有者、使用者和生存期管理</span><span class="sxs-lookup"><span data-stu-id="11e06-112">Owners, consumers, and lifetime management</span></span>

<span data-ttu-id="11e06-113">由于可以在各个 API 之间传送缓冲区，以及由于缓冲区有时可以从多个线程进行访问，因此请务必考虑生存期管理。</span><span class="sxs-lookup"><span data-stu-id="11e06-113">Since buffers can be passed around between APIs, and since buffers can sometimes be accessed from multiple threads, it's important to consider lifetime management.</span></span> <span data-ttu-id="11e06-114">下面介绍三个核心概念：</span><span class="sxs-lookup"><span data-stu-id="11e06-114">There are three core concepts:</span></span>

- <span data-ttu-id="11e06-115">**所有权**。</span><span class="sxs-lookup"><span data-stu-id="11e06-115">**Ownership**.</span></span> <span data-ttu-id="11e06-116">缓冲区实例的所有者负责生存期管理，包括在不再使用缓冲区时将其销毁。</span><span class="sxs-lookup"><span data-stu-id="11e06-116">The owner of a buffer instance is responsible for lifetime management, including destroying the buffer when it's no longer in use.</span></span> <span data-ttu-id="11e06-117">所有缓冲区都拥有一个所有者。</span><span class="sxs-lookup"><span data-stu-id="11e06-117">All buffers have a single owner.</span></span> <span data-ttu-id="11e06-118">通常，所有者是创建缓冲区或从工厂接收缓冲区的组件。</span><span class="sxs-lookup"><span data-stu-id="11e06-118">Generally the owner is the component that created the buffer or that received the buffer from a factory.</span></span> <span data-ttu-id="11e06-119">所有权也可以转让；组件 A 可以将缓冲区的控制权转让给组件 B，此时组件 A 就无法再使用该缓冲区，组件 B 将负责在不再使用缓冲区时将其销毁。</span><span class="sxs-lookup"><span data-stu-id="11e06-119">Ownership can also be transferred; **Component-A** can relinquish control of the buffer to **Component-B**, at which point **Component-A** may no longer use the buffer, and **Component-B** becomes responsible for destroying the buffer when it's no longer in use.</span></span>

- <span data-ttu-id="11e06-120">**使用**。</span><span class="sxs-lookup"><span data-stu-id="11e06-120">**Consumption**.</span></span> <span data-ttu-id="11e06-121">允许缓冲区实例的使用者通过从中读取并可能写入其中来使用缓冲区实例。</span><span class="sxs-lookup"><span data-stu-id="11e06-121">The consumer of a buffer instance is allowed to use the buffer instance by reading from it and possibly writing to it.</span></span> <span data-ttu-id="11e06-122">缓冲区一次可以拥有一个使用者，除非提供了某些外部同步机制。</span><span class="sxs-lookup"><span data-stu-id="11e06-122">Buffers can have one consumer at a time unless some external synchronization mechanism is provided.</span></span> <span data-ttu-id="11e06-123">请注意，缓冲区的当前使用者不一定是缓冲区的所有者。</span><span class="sxs-lookup"><span data-stu-id="11e06-123">Note that the active consumer of a buffer isn't necessarily the buffer's owner.</span></span>

- <span data-ttu-id="11e06-124">**租用**。</span><span class="sxs-lookup"><span data-stu-id="11e06-124">**Lease**.</span></span> <span data-ttu-id="11e06-125">租用是允许特定组件成为缓冲区使用者的时长。</span><span class="sxs-lookup"><span data-stu-id="11e06-125">The lease is the length of time that a particular component is allowed to be the consumer of the buffer.</span></span>

<span data-ttu-id="11e06-126">以下伪代码示例阐释了这三个概念。</span><span class="sxs-lookup"><span data-stu-id="11e06-126">The following pseudo-code example illustrates these three concepts.</span></span> <span data-ttu-id="11e06-127">它包括实例化类型为 <xref:System.Char> 的 <xref:System.Memory%601> 缓冲区的 `Main` 方法，调用 `WriteInt32ToBuffer` 方法以将整数的字符串表示形式写入缓冲区，然后调用 `DisplayBufferToConsole` 方法以显示缓冲区的值。</span><span class="sxs-lookup"><span data-stu-id="11e06-127">It includes a `Main` method that instantiates a <xref:System.Memory%601> buffer of type <xref:System.Char>, calls the `WriteInt32ToBuffer` method to write the string representation of an integer to the buffer, and then calls the `DisplayBufferToConsole` method to display the value of the buffer.</span></span>

```csharp
using System;

class Program
{
    // Write 'value' as a human-readable string to the output buffer.
    void WriteInt32ToBuffer(int value, Buffer buffer);

    // Display the contents of the buffer to the console.
    void DisplayBufferToConsole(Buffer buffer);

    // Application code
    static void Main()
    {
        var buffer = CreateBuffer();
        try
        {
            int value = Int32.Parse(Console.ReadLine());
            WriteInt32ToBuffer(value, buffer);
            DisplayBufferToConsole(buffer);
        }
        finally
        {
            buffer.Destroy();
        }
    }
}
```

<span data-ttu-id="11e06-128">`Main` 方法创建缓冲区（在此示例中为 <xref:System.Span%601> 实例），因此它是其所有者。</span><span class="sxs-lookup"><span data-stu-id="11e06-128">The `Main` method creates the buffer (in this case an <xref:System.Span%601> instance) and so is its owner.</span></span> <span data-ttu-id="11e06-129">因此，`Main` 将负责在不再使用缓冲区时将其销毁。</span><span class="sxs-lookup"><span data-stu-id="11e06-129">Therefore, `Main` is responsible for destroying the buffer when it's no longer in use.</span></span> <span data-ttu-id="11e06-130">这是通过调用缓冲区的 <xref:System.Span%601.Clear?displayProperty=nameWithType> 方法完成的。</span><span class="sxs-lookup"><span data-stu-id="11e06-130">It does this by calling the buffer's <xref:System.Span%601.Clear?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="11e06-131">（此处的 <xref:System.Span%601.Clear> 方法实际上会清除缓冲区的内存；<xref:System.Span%601> 结构实际上没有销毁缓冲区的方法。）</span><span class="sxs-lookup"><span data-stu-id="11e06-131">(The <xref:System.Span%601.Clear> method here actually clears the buffer's memory; the <xref:System.Span%601> structure doesn't actually have a method that destroys the buffer.)</span></span>

<span data-ttu-id="11e06-132">缓冲区有两个使用者：`WriteInt32ToBuffer` 和 `DisplayBufferToConsole`。</span><span class="sxs-lookup"><span data-stu-id="11e06-132">The buffer has two consumers, `WriteInt32ToBuffer` and `DisplayBufferToConsole`.</span></span> <span data-ttu-id="11e06-133">一次只能有一个使用者（先是 `WriteInt32ToBuffer`，然后是 `DisplayBufferToConsole`），这两个使用者都不拥有缓冲区。</span><span class="sxs-lookup"><span data-stu-id="11e06-133">There is only one consumer at a time (first `WriteInt32ToBuffer`, then `DisplayBufferToConsole`), and neither of the consumers owns the buffer.</span></span> <span data-ttu-id="11e06-134">另请注意，此上下文中的“使用者”并不意味着以只读形式查看缓冲区；如果提供了以读/写形式查看缓冲区的权限，则使用者可以像 `WriteInt32ToBuffer` 那样修改缓冲区的内容。</span><span class="sxs-lookup"><span data-stu-id="11e06-134">Note also that "consumer" in this context doesn't imply a read-only view of the buffer; consumers can modify the buffer's contents, as `WriteInt32ToBuffer` does, if given a read/write view of the buffer.</span></span>

<span data-ttu-id="11e06-135">`WriteInt32ToBuffer` 方法在方法调用的开始时间和方法返回的时间之间会租用（可以使用）缓冲区。</span><span class="sxs-lookup"><span data-stu-id="11e06-135">The `WriteInt32ToBuffer` method has a lease on (can consume) the buffer between the start of the method call and the time the method returns.</span></span> <span data-ttu-id="11e06-136">同样，`DisplayBufferToConsole` 在执行时会租用缓冲区，回退该方法时将解除租用。</span><span class="sxs-lookup"><span data-stu-id="11e06-136">Similarly, `DisplayBufferToConsole` has a lease on the buffer while it's executing, and the lease is released when the method unwinds.</span></span> <span data-ttu-id="11e06-137">（没有用于租用管理的 API；“租用”是概念性内容。）</span><span class="sxs-lookup"><span data-stu-id="11e06-137">(There is no API for lease management; a "lease" is a conceptual matter.)</span></span>

## <a name="memoryt-and-the-ownerconsumer-model"></a><span data-ttu-id="11e06-138">内存\<T> 和所有者/使用者模型</span><span class="sxs-lookup"><span data-stu-id="11e06-138">Memory\<T> and the owner/consumer model</span></span>

<span data-ttu-id="11e06-139">如[所有者、使用者和生存期管理](#owners-consumers-and-lifetime-management)部分中指出，缓冲区始终都有一个所有者。</span><span class="sxs-lookup"><span data-stu-id="11e06-139">As the [Owners, consumers, and lifetime management](#owners-consumers-and-lifetime-management) section notes, a buffer always has an owner.</span></span> <span data-ttu-id="11e06-140">.NET Core 支持以下两种所有权模型：</span><span class="sxs-lookup"><span data-stu-id="11e06-140">.NET Core supports two ownership models:</span></span>

- <span data-ttu-id="11e06-141">支持单个所有权的模型。</span><span class="sxs-lookup"><span data-stu-id="11e06-141">A model that supports single ownership.</span></span> <span data-ttu-id="11e06-142">缓冲区在其整个生存期内拥有单个所有者。</span><span class="sxs-lookup"><span data-stu-id="11e06-142">A buffer has a single owner for its entire lifetime.</span></span>

- <span data-ttu-id="11e06-143">支持所有权转让的模型。</span><span class="sxs-lookup"><span data-stu-id="11e06-143">A model that supports ownership transfer.</span></span> <span data-ttu-id="11e06-144">缓冲区的所有权可以从其原始所有者（其创建者）转让给其他组件，该组件随后将负责缓冲区的生存期管理。</span><span class="sxs-lookup"><span data-stu-id="11e06-144">Ownership of a buffer can be transferred from its original owner (its creator) to another component, which then becomes responsible for the buffer's lifetime management.</span></span> <span data-ttu-id="11e06-145">该所有者可以反过来将所有权转让给其他组件等。</span><span class="sxs-lookup"><span data-stu-id="11e06-145">That owner can in turn transfer ownership to another component, and so on.</span></span>

<span data-ttu-id="11e06-146">使用 <xref:System.Buffers.IMemoryOwner%601?displayProperty=nameWithType> 接口显式管理缓冲区的所有权。</span><span class="sxs-lookup"><span data-stu-id="11e06-146">You use the <xref:System.Buffers.IMemoryOwner%601?displayProperty=nameWithType> interface to explicitly manage the ownership of a buffer.</span></span> <span data-ttu-id="11e06-147"><xref:System.Buffers.IMemoryOwner%601> 支持两种所有权模型。</span><span class="sxs-lookup"><span data-stu-id="11e06-147"><xref:System.Buffers.IMemoryOwner%601> supports both ownership models.</span></span> <span data-ttu-id="11e06-148">具有 <xref:System.Buffers.IMemoryOwner%601> 引用的组件拥有缓冲区。</span><span class="sxs-lookup"><span data-stu-id="11e06-148">The component that has an <xref:System.Buffers.IMemoryOwner%601> reference owns the buffer.</span></span> <span data-ttu-id="11e06-149">以下示例使用 <xref:System.Buffers.IMemoryOwner%601?> 实例反映 <xref:System.Memory%601> 缓冲区的所有权。</span><span class="sxs-lookup"><span data-stu-id="11e06-149">The following example uses an <xref:System.Buffers.IMemoryOwner%601?> instance to reflect the ownership of an <xref:System.Memory%601> buffer.</span></span>

[!code-csharp[ownership](~/samples/snippets/standard/buffers/memory-t/owner/owner.cs)]

<span data-ttu-id="11e06-150">也可以使用 [`using`](~/docs/csharp/language-reference/keywords/using-statement.md) 编写此示例：</span><span class="sxs-lookup"><span data-stu-id="11e06-150">We can also write this example with the [`using`](~/docs/csharp/language-reference/keywords/using-statement.md):</span></span>

[!code-csharp[ownership-using](~/samples/snippets/standard/buffers/memory-t/owner-using/owner-using.cs)]

<span data-ttu-id="11e06-151">在此代码中：</span><span class="sxs-lookup"><span data-stu-id="11e06-151">In this code:</span></span>

- <span data-ttu-id="11e06-152">`Main` 方法保留对 <xref:System.Buffers.IMemoryOwner%601> 实例的引用，因此 `Main` 方法是缓冲区的所有者。</span><span class="sxs-lookup"><span data-stu-id="11e06-152">The `Main` method holds the reference to the <xref:System.Buffers.IMemoryOwner%601> instance, so the `Main` method is the owner of the buffer.</span></span>

- <span data-ttu-id="11e06-153">`WriteInt32ToBuffer` 和 `DisplayBufferToConsole` 方法接受 xref:System.Memory%601> 作为公共 API。</span><span class="sxs-lookup"><span data-stu-id="11e06-153">The `WriteInt32ToBuffer` and `DisplayBufferToConsole` methods accept xref:System.Memory%601> as a public API.</span></span> <span data-ttu-id="11e06-154">因此，它们是缓冲区的使用者。</span><span class="sxs-lookup"><span data-stu-id="11e06-154">Therefore, they are consumers of the buffer.</span></span> <span data-ttu-id="11e06-155">并且它们一次仅使用一个。</span><span class="sxs-lookup"><span data-stu-id="11e06-155">And they only consume it one at a time.</span></span>

<span data-ttu-id="11e06-156">尽管 `WriteInt32ToBuffer` 方法用于将值写入缓冲区，但 `DisplayBufferToConsole` 方法并不如此。</span><span class="sxs-lookup"><span data-stu-id="11e06-156">Although the `WriteInt32ToBuffer` method is intended to write a value to the buffer, the `DisplayBufferToConsole` method isn't.</span></span> <span data-ttu-id="11e06-157">若要反映此情况，可以接受类型为 <xref:System.ReadOnlyMemory%601> 的参数。</span><span class="sxs-lookup"><span data-stu-id="11e06-157">To reflect this, it could have accepted an argument of type <xref:System.ReadOnlyMemory%601>.</span></span> <span data-ttu-id="11e06-158">有关 <xref:System.ReadOnlyMemory%601> 的其他信息，请参阅[规则 2：如果缓冲区应为只读，则使用 ReadOnlySpan\<T> 或 ReadOnlyMemory\<T>](#rule-2)。</span><span class="sxs-lookup"><span data-stu-id="11e06-158">For additional information on <xref:System.ReadOnlyMemory%601>, see [Rule #2: Use ReadOnlySpan\<T> or ReadOnlyMemory\<T> if the buffer should be read-only](#rule-2).</span></span>

### <a name="ownerless-memoryt-instances"></a><span data-ttu-id="11e06-159">“无所有者”内存\<T> 实例</span><span class="sxs-lookup"><span data-stu-id="11e06-159">"Ownerless" Memory\<T> instances</span></span>

<span data-ttu-id="11e06-160">无需使用 <xref:System.Buffers.IMemoryOwner%601> 即可创建 <xref:System.Memory%601> 实例。</span><span class="sxs-lookup"><span data-stu-id="11e06-160">You can create a <xref:System.Memory%601> instance without using <xref:System.Buffers.IMemoryOwner%601>.</span></span> <span data-ttu-id="11e06-161">在这种情况下，缓冲区的所有权是隐式的而不是显式的，并且仅支持单所有者模型。</span><span class="sxs-lookup"><span data-stu-id="11e06-161">In this case, ownership of the buffer is implicit rather than explicit, and only the single-owner model is supported.</span></span> <span data-ttu-id="11e06-162">可以通过以下方式达到此目的：</span><span class="sxs-lookup"><span data-stu-id="11e06-162">You can do this by:</span></span>

- <span data-ttu-id="11e06-163">直接调用 <xref:System.Memory%601> 构造函数之一，传入 `T[]`，如下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="11e06-163">Calling one of the  <xref:System.Memory%601> constructors directly, passing in a `T[]`, as the following example does.</span></span>

- <span data-ttu-id="11e06-164">调用 [String.AsMemory](xref:System.MemoryExtensions.AsMemory(System.String)) 扩展方法以生成 `ReadOnlyMemory<char>` 实例。</span><span class="sxs-lookup"><span data-stu-id="11e06-164">Calling the [String.AsMemory](xref:System.MemoryExtensions.AsMemory(System.String)) extension method to produce a `ReadOnlyMemory<char>` instance.</span></span>

[!code-csharp[ownerless-memory](~/samples/snippets/standard/buffers/memory-t/ownerless/ownerless.cs)]

<span data-ttu-id="11e06-165">最初创建 <xref:System.Memory%601> 实例的方法是缓冲区的隐式所有者。</span><span class="sxs-lookup"><span data-stu-id="11e06-165">The method that initially creates the <xref:System.Memory%601> instance is the implicit owner of the buffer.</span></span> <span data-ttu-id="11e06-166">无法将所有权转让给任何其他组件，因为没有 <xref:System.Buffers.IMemoryOwner%601> 实例可用于进行转让。</span><span class="sxs-lookup"><span data-stu-id="11e06-166">Ownership cannot be transferred to any other component because there is no <xref:System.Buffers.IMemoryOwner%601> instance to facilitate the transfer.</span></span> <span data-ttu-id="11e06-167">（或者，也可以假设运行时的垃圾回收器拥有缓冲区，而所有方法仅使用缓冲区。）</span><span class="sxs-lookup"><span data-stu-id="11e06-167">(As an alternative, you can also imagine that the runtime's garbage collector owns the buffer, and all methods just consume the buffer.)</span></span>

## <a name="usage-guidelines"></a><span data-ttu-id="11e06-168">使用准则</span><span class="sxs-lookup"><span data-stu-id="11e06-168">Usage guidelines</span></span>

<span data-ttu-id="11e06-169">由于拥有内存块，但打算传递到多个组件，因此其中一些组件可能会同时在特定的内存块上运行，请务必建立使用 <xref:System.Memory%601> 和 <xref:System.Span%601> 的准则。</span><span class="sxs-lookup"><span data-stu-id="11e06-169">Because a memory block is owned but is intended to be passed to multiple components, some of which may operate upon a particular memory block simultaneously, it is important to establish guidelines for using both <xref:System.Memory%601> and <xref:System.Span%601>.</span></span>  <span data-ttu-id="11e06-170">准则是必需的，因为：</span><span class="sxs-lookup"><span data-stu-id="11e06-170">Guidelines are necessary because:</span></span>

- <span data-ttu-id="11e06-171">组件可以在内存块的所有者发布内存块之后保留对该内存块的引用。</span><span class="sxs-lookup"><span data-stu-id="11e06-171">It is possible for a component to retain a reference to a memory block after its owner has released it.</span></span>

- <span data-ttu-id="11e06-172">组件可以同时在运行其他组件的缓冲区上运行，在该过程中会损坏缓冲区中的数据。</span><span class="sxs-lookup"><span data-stu-id="11e06-172">It is possible for a component to operate on a buffer at the same time that another component is operating on it, in the process corrupting the data in the buffer.</span></span>

- <span data-ttu-id="11e06-173">虽然 <xref:System.Span%601> 的堆栈分配特性优化了性能并使 <xref:System.Span%601> 成为在内存块上运行的首选类型，但它也使 <xref:System.Span%601> 必须遵循一些主要限制的约束。</span><span class="sxs-lookup"><span data-stu-id="11e06-173">While the stack-allocated nature of <xref:System.Span%601> optimizes performance and makes <xref:System.Span%601> the preferred type for operating on a memory block, it also subjects <xref:System.Span%601> to some major restrictions restrictions.</span></span> <span data-ttu-id="11e06-174">请务必了解何时使用 <xref:System.Span%601> 以及何时使用 <xref:System.Memory%601>。</span><span class="sxs-lookup"><span data-stu-id="11e06-174">It is important to know when to use a <xref:System.Span%601> and when to use <xref:System.Memory%601>.</span></span>

<span data-ttu-id="11e06-175">下面介绍成功使用 <xref:System.Memory%601> 及其相关类型的建议。</span><span class="sxs-lookup"><span data-stu-id="11e06-175">The following are our recommendations for successfully using <xref:System.Memory%601> and its related types.</span></span> <span data-ttu-id="11e06-176">请注意，除非另有明确说明，否则适用于 <xref:System.Memory%601> 和 <xref:System.Span%601> 的指南也适用于 <xref:System.ReadOnlyMemory%601> 和 <xref:System.ReadOnlySpan%601>。</span><span class="sxs-lookup"><span data-stu-id="11e06-176">Note that guidance that applies to <xref:System.Memory%601> and <xref:System.Span%601> also applies to <xref:System.ReadOnlyMemory%601> and <xref:System.ReadOnlySpan%601> unless we explicitly note otherwise.</span></span>

<span data-ttu-id="11e06-177">**规则 1：对于同步 API，如有可能，请使用跨度\<T>（而不是内存\<T>）作为参数。**</span><span class="sxs-lookup"><span data-stu-id="11e06-177">**Rule #1: For a synchronous API, use Span\<T> instead of Memory\<T> as a parameter if possible.**</span></span>

<span data-ttu-id="11e06-178"><xref:System.Span%601> 比 <xref:System.Memory%601> 更通用，可以表示更多种类的连续内存缓冲区。</span><span class="sxs-lookup"><span data-stu-id="11e06-178"><xref:System.Span%601> is more versatile than <xref:System.Memory%601> and can represent a wider variety of contiguous memory buffers.</span></span> <span data-ttu-id="11e06-179"><xref:System.Span%601> 还提供比 <xref:System.Memory%601>> 更好的性能。</span><span class="sxs-lookup"><span data-stu-id="11e06-179"><xref:System.Span%601> also offers better performance than <xref:System.Memory%601>>.</span></span> <span data-ttu-id="11e06-180">最后，尽管无法进行跨度\<T> 到内存\<T> 的转换，但可以使用 <xref:System.Memory%601.Span?displayProperty=nameWithType> 属性将 <xref:System.Memory%601> 实例转换为 <xref:System.Span%601>。</span><span class="sxs-lookup"><span data-stu-id="11e06-180">Finally, you can use the <xref:System.Memory%601.Span?displayProperty=nameWithType> property to convert a <xref:System.Memory%601> instance to a <xref:System.Span%601>, although Span\<T>-to-Memory\<T> conversion isn't possible.</span></span> <span data-ttu-id="11e06-181">因此，如果调用方恰好具有 <xref:System.Memory%601> 实例，则它们不管怎样都可以使用 <xref:System.Span%601> 参数调用你的方法。</span><span class="sxs-lookup"><span data-stu-id="11e06-181">So if your callers happen to have a <xref:System.Memory%601> instance, they'll be able to call your methods with <xref:System.Span%601> parameters anyway.</span></span>

<span data-ttu-id="11e06-182">使用类型为 <xref:System.Span%601>（而不是类型为 <xref:System.Memory%601>）的参数还可以帮助你编写正确的使用方法实现。</span><span class="sxs-lookup"><span data-stu-id="11e06-182">Using a parameter of type <xref:System.Span%601> instead of type <xref:System.Memory%601> also helps you write a correct consuming method implementation.</span></span> <span data-ttu-id="11e06-183">你将自动进行编译时检查，以确保不尝试访问方法租用之外的缓冲区（后续部分将对此进行详细介绍）。</span><span class="sxs-lookup"><span data-stu-id="11e06-183">You'll automatically get compile-time checks to ensure that you're not attempting to access the buffer beyond your method's lease (more on this later).</span></span>

<span data-ttu-id="11e06-184">有时，必须使用 <xref:System.Memory%601> 参数（而不是 <xref:System.Span%601> 参数），即使完全同步也是如此。</span><span class="sxs-lookup"><span data-stu-id="11e06-184">Sometimes, you'll have to use a <xref:System.Memory%601> parameter instead of a <xref:System.Span%601> parameter, even if you're fully synchronous.</span></span> <span data-ttu-id="11e06-185">所依赖的 API 可能仅接受 <xref:System.Memory%601> 参数。</span><span class="sxs-lookup"><span data-stu-id="11e06-185">Perhaps an API that you depend accepts only <xref:System.Memory%601> arguments.</span></span> <span data-ttu-id="11e06-186">这没有问题，但应注意同步使用 <xref:System.Memory%601> 时所涉及的权衡取舍。</span><span class="sxs-lookup"><span data-stu-id="11e06-186">This is fine, but be aware of the tradeoffs involved when using <xref:System.Memory%601> synchronously.</span></span>

<a name="rule-2" />

<span data-ttu-id="11e06-187">**规则 2：如果缓冲区应为只读，则使用 ReadOnlySpan\<T> 或 ReadOnlyMemory\<T>。**</span><span class="sxs-lookup"><span data-stu-id="11e06-187">**Rule #2: Use ReadOnlySpan\<T> or ReadOnlyMemory\<T> if the buffer should be read-only.**</span></span>

<span data-ttu-id="11e06-188">在前面的示例中，`DisplayBufferToConsole` 方法仅从缓冲区读取；它不会修改缓冲区的内容。</span><span class="sxs-lookup"><span data-stu-id="11e06-188">In the earlier examples, the `DisplayBufferToConsole` method only reads from the buffer; it doesn't modify the contents of the buffer.</span></span> <span data-ttu-id="11e06-189">方法签名应进行如下更改。</span><span class="sxs-lookup"><span data-stu-id="11e06-189">The method signature should be changed to the following.</span></span>

```csharp
void DisplayBufferToConsole(ReadOnlyMemory<char> buffer);
```

<span data-ttu-id="11e06-190">事实上，如果我们结合使用此规则和规则 1，我们可以做得更好，并按如下所示重写方法签名：</span><span class="sxs-lookup"><span data-stu-id="11e06-190">In fact, if we combine this rule and Rule #1, we can do even better and rewrite the method signature as follows:</span></span>

```csharp
void DisplayBufferToConsole(ReadOnlySpan<char> buffer);
```

<span data-ttu-id="11e06-191">`DisplayBufferToConsole` 方法现在几乎适用于每一个能够想到的缓冲区类型：`T[]`，使用 [stackalloc](~/docs/csharp/language-reference/keywords/stackalloc.md) 分配的存储等。</span><span class="sxs-lookup"><span data-stu-id="11e06-191">The `DisplayBufferToConsole` method now works with virtually every buffer type imaginable: `T[]`, storage allocated with [stackalloc](~/docs/csharp/language-reference/keywords/stackalloc.md), and so on.</span></span> <span data-ttu-id="11e06-192">甚至可以向其直接传递 <xref:System.String>！</span><span class="sxs-lookup"><span data-stu-id="11e06-192">You can even pass a <xref:System.String> directly into it!</span></span>

<span data-ttu-id="11e06-193">**规则 3：如果方法接受内存\<T> 并返回 `void`，则在方法返回之后不得使用内存\<T> 实例。**</span><span class="sxs-lookup"><span data-stu-id="11e06-193">**Rule #3: If your method accepts Memory\<T> and returns `void`, you must not use the Memory\<T> instance after your method returns.**</span></span>

<span data-ttu-id="11e06-194">这与前面提到的“租用”概念相关。</span><span class="sxs-lookup"><span data-stu-id="11e06-194">This relates to the "lease" concept mentioned earlier.</span></span> <span data-ttu-id="11e06-195">返回 void 的方法对 <xref:System.Memory%601> 实例的租用将在进入该方法时开始，并在退出该方法时结束。</span><span class="sxs-lookup"><span data-stu-id="11e06-195">A void-returning method's lease on the <xref:System.Memory%601> instance begins when the method is entered, and it ends when the method exits.</span></span> <span data-ttu-id="11e06-196">请考虑以下示例，该示例会基于控制台中的输入在循环中调用 `Log`。</span><span class="sxs-lookup"><span data-stu-id="11e06-196">Consider the following example, which calls `Log` in a loop based on input from the console.</span></span>

[!code-csharp[void-returning](~/samples/snippets/standard/buffers/memory-t/void-returning/void-returning.cs#1)]

<span data-ttu-id="11e06-197">如果 `Log` 是完全同步的方法，则此代码将按预期运行，因为在任何给定时间只有一个活动的内存实例使用者。</span><span class="sxs-lookup"><span data-stu-id="11e06-197">If `Log` is a fully synchronous method, this code will behave as expected because there is only one active consumer of the memory instance at any given time.</span></span>
<span data-ttu-id="11e06-198">但请假设 `Log` 具有此实现。</span><span class="sxs-lookup"><span data-stu-id="11e06-198">But imagine instead that `Log` has this implementation.</span></span>

```csharp
// !!! INCORRECT IMPLEMENTATION !!!
static void Log(ReadOnlyMemory<char> message)
{
    // Run in background so that we don't block the main thread while performing IO.
    Task.Run(() =>
    {
        StreamWriter sw = File.AppendText(@".\input-numbers.dat");
        sw.WriteLine(message);
    });
}
```

<span data-ttu-id="11e06-199">在此实现中，`Log` 违反了其租用，因为它在返回原始方法之后仍尝试在后台使用 <xref:System.Memory%601> 示例。</span><span class="sxs-lookup"><span data-stu-id="11e06-199">In this implementation, `Log` violates its lease because it still attempts to use the <xref:System.Memory%601> instance in the background after the original method has returned.</span></span> <span data-ttu-id="11e06-200">`Main` 方法可能会在 `Log` 尝试从缓冲区进行读取时更改缓冲区，这可能导致数据损坏。</span><span class="sxs-lookup"><span data-stu-id="11e06-200">The `Main` method could mutate the buffer while `Log` attempts to read from it, which could result in data corruption.</span></span>

<span data-ttu-id="11e06-201">有多种方法可解决此问题：</span><span class="sxs-lookup"><span data-stu-id="11e06-201">There are several ways to resolve this:</span></span>

- <span data-ttu-id="11e06-202">`Log` 方法可以按 `Log` 方法的以下实现所示返回 <xref:System.Threading.Tasks.Task>，而不是 `void`。</span><span class="sxs-lookup"><span data-stu-id="11e06-202">The `Log` method can return a <xref:System.Threading.Tasks.Task> instead of `void`, as the following implementation of the `Log` method does.</span></span>

   [!code-csharp[task-returning](~/samples/snippets/standard/buffers/memory-t/task-returning2/task-returning2.cs#1)]

- <span data-ttu-id="11e06-203">可以改为按如下所示实现 `Log`：</span><span class="sxs-lookup"><span data-stu-id="11e06-203">`Log` can instead be implemented as follows:</span></span>

   [!code-csharp[defensive-copy](~/samples/snippets/standard/buffers/memory-t/task-returning/task-returning.cs#1)]

<span data-ttu-id="11e06-204">**规则 4：如果方法接受内存\<T> 并返回某个任务，则在该任务转换为终止状态之后不得使用内存\<T> 实例。**</span><span class="sxs-lookup"><span data-stu-id="11e06-204">**Rule #4: If your method accepts a Memory\<T> and returns a Task, you must not use the Memory\<T> instance after the Task transitions to a terminal state.**</span></span>

<span data-ttu-id="11e06-205">这只是规则 3 的异步变体。</span><span class="sxs-lookup"><span data-stu-id="11e06-205">This is just the async variant of Rule #3.</span></span> <span data-ttu-id="11e06-206">可以按如下所示编写前面示例中的 `Log` 方法以遵守此规则：</span><span class="sxs-lookup"><span data-stu-id="11e06-206">The `Log` method from the earlier example can be written as follows to comply with this rule:</span></span>

[!code-csharp[task-returning-async](~/samples/snippets/standard/buffers/memory-t/void-returning-async/void-returning-async.cs#1)]

<span data-ttu-id="11e06-207">此处的“终止状态”表示任务转换为已完成、已出错或已取消状态。</span><span class="sxs-lookup"><span data-stu-id="11e06-207">Here, "terminal state" means that the task transitions to a completed, faulted, or canceled state.</span></span> <span data-ttu-id="11e06-208">换而言之，“终止状态”表示“导致等待引发或继续执行的任何状态”。</span><span class="sxs-lookup"><span data-stu-id="11e06-208">In other words, "terminal state" means "anything that would cause await to throw or to continue execution."</span></span>

<span data-ttu-id="11e06-209">此指南适用于返回 <xref:System.Threading.Tasks.Task>、<xref:System.Threading.Tasks.Task%601>、<xref:System.Threading.Tasks.ValueTask%601> 或任何类似类型的方法。</span><span class="sxs-lookup"><span data-stu-id="11e06-209">This guidance applies to methods that return <xref:System.Threading.Tasks.Task>, <xref:System.Threading.Tasks.Task%601>, <xref:System.Threading.Tasks.ValueTask%601>, or any similar type.</span></span>

<span data-ttu-id="11e06-210">**规则 5：如果构造函数接受内存\<T> 作为参数，则假定构造对象上的实例方法是内存\<T> 实例的使用者。**</span><span class="sxs-lookup"><span data-stu-id="11e06-210">**Rule #5: If your constructor accepts Memory\<T> as a parameter, instance methods on the constructed object are assumed to be consumers of the Memory\<T> instance.**</span></span>

<span data-ttu-id="11e06-211">请看下面的示例：</span><span class="sxs-lookup"><span data-stu-id="11e06-211">Consider the following example:</span></span>

```csharp
class OddValueExtractor
{
    public OddValueExtractor(ReadOnlyMemory<int> input);
    public bool TryReadNextOddValue(out int value);
}

void PrintAllOddValues(ReadOnlyMemory<int> input)
{
    var extractor = new OddValueExtractor(input);
    while (extractor.TryReadNextOddValue(out int value))
    {
      Console.WriteLine(value);
    }
}
```

<span data-ttu-id="11e06-212">此处的 `OddValueExtractor` 构造函数接受 `ReadOnlyMemory<int>` 作为构造函数参数，因此构造函数本身是 `ReadOnlyMemory<int>` 实例的使用者，并且返回值上的所有实例方法也是原始 `ReadOnlyMemory<int>` 实例的使用者。</span><span class="sxs-lookup"><span data-stu-id="11e06-212">Here, the `OddValueExtractor` constructor accepts a `ReadOnlyMemory<int>` as a constructor parameter, so the constructor itself is a consumer of the `ReadOnlyMemory<int>` instance, and all instance methods on the returned value are also consumers of the original `ReadOnlyMemory<int>` instance.</span></span> <span data-ttu-id="11e06-213">这意味着 `TryReadNextOddValue` 使用 `ReadOnlyMemory<int>` 实例，即使该实例未直接传递到 `TryReadNextOddValue` 方法也是如此。</span><span class="sxs-lookup"><span data-stu-id="11e06-213">This means that `TryReadNextOddValue` consumes the `ReadOnlyMemory<int>` instance, even though the instance isn't passed directly to the `TryReadNextOddValue` method.</span></span>

<span data-ttu-id="11e06-214">**规则 6：如果类型具有可设置的内存\<T> 类型的属性（或等效实例方法），则假定该对象上的实例方法是内存\<T> 实例的使用者。**</span><span class="sxs-lookup"><span data-stu-id="11e06-214">**Rule #6: If you have a settable Memory\<T>-typed property (or an equivalent instance method) on your type, instance methods on that object are assumed to be consumers of the Memory\<T> instance.**</span></span>

<span data-ttu-id="11e06-215">这实际上只是规则 5 的变体。</span><span class="sxs-lookup"><span data-stu-id="11e06-215">This is really just a variant of Rule #5.</span></span> <span data-ttu-id="11e06-216">存在此规则的原因是假定属性 setter 或等效方法捕获并保留其输入，因此同一对象上的实例方法可能会使用已捕获状态。</span><span class="sxs-lookup"><span data-stu-id="11e06-216">This rule exists because property setters or equivalent methods are assumed to capture and persist their inputs, so instance methods on the same object may utilize the captured state.</span></span>

<span data-ttu-id="11e06-217">下面的示例将触发以下规则：</span><span class="sxs-lookup"><span data-stu-id="11e06-217">The following example triggers this rule:</span></span>

```csharp
class Person
{
    // Settable property.
    public Memory<char> FirstName { get; set; }

    // alternatively, equivalent "setter" method
    public SetFirstName(Memory<char> value);

    // alternatively, a public settable field
    public Memory<char> FirstName;
}
```

<span data-ttu-id="11e06-218">**规则 7：如果具有 IMemoryOwner\<T> 引用，则必须在某些时候对其进行处理或转让其所有权（但不同时执行两个操作）。**</span><span class="sxs-lookup"><span data-stu-id="11e06-218">**Rule #7: If you have an IMemoryOwner\<T> reference, you must at some point dispose of it or transfer its ownership (but not both).**</span></span>

<span data-ttu-id="11e06-219">由于 <xref:System.Memory%601> 实例可能由托管或非托管内存提供支持，因此在对 <xref:System.Memory%601> 实例执行的工作完成之后，所有者必须调用 <xref:System.Buffers.MemoryPool%601.Dispose%2A?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="11e06-219">Since a <xref:System.Memory%601> instance may be backed by either managed or unmanaged memory, the owner must call <xref:System.Buffers.MemoryPool%601.Dispose%2A?displayProperty=nameWithType> when work performed on the <xref:System.Memory%601> instance is complete.</span></span> <span data-ttu-id="11e06-220">此外，所有者可能会将 <xref:System.Buffers.IMemoryOwner%601> 实例的所有权转让给其他组件，同时获取组件将负责在适当时间调用 <xref:System.Buffers.MemoryPool%601.Dispose%2A?displayProperty=nameWithType>（稍后将对此进行详细介绍）。</span><span class="sxs-lookup"><span data-stu-id="11e06-220">Alternatively, the owner may transfer ownership of the <xref:System.Buffers.IMemoryOwner%601> instance to a different component, at which point the acquiring component becomes responsible for calling <xref:System.Buffers.MemoryPool%601.Dispose%2A?displayProperty=nameWithType> at the appropriate time (more on this later).</span></span>

<span data-ttu-id="11e06-221">调用 <xref:System.Buffers.MemoryPool%601.Dispose%2A> 方法失败可能会导致非托管内存泄漏或其他性能降低。</span><span class="sxs-lookup"><span data-stu-id="11e06-221">Failure to call the <xref:System.Buffers.MemoryPool%601.Dispose%2A> method may lead to unmanaged memory leaks or other performance degradation.</span></span>

<span data-ttu-id="11e06-222">此规则也适用于调用工厂方法（如 <xref:System.Buffers.MemoryPool%601.Rent%2A?displayProperty=nameWithType>）的代码。</span><span class="sxs-lookup"><span data-stu-id="11e06-222">This rule also applies to code that calls factory methods like <xref:System.Buffers.MemoryPool%601.Rent%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="11e06-223">调用方将成为返回的 <xref:System.Buffers.IMemoryOwner%601> 的所有者，并负责在完成后处理实例。</span><span class="sxs-lookup"><span data-stu-id="11e06-223">The caller becomes the owner of the returned <xref:System.Buffers.IMemoryOwner%601> and is responsible for disposing of the instance when finished.</span></span>

<span data-ttu-id="11e06-224">**规则 8：如果 API 接口中具有 IMemoryOwner\<T> 参数，即表示你接受该实例的所有权。**</span><span class="sxs-lookup"><span data-stu-id="11e06-224">**Rule #8: If you have an IMemoryOwner\<T> parameter in your API surface, you are accepting ownership of that instance.**</span></span>

<span data-ttu-id="11e06-225">接受此类型的实例表示组件打算获取此实例的所有权。</span><span class="sxs-lookup"><span data-stu-id="11e06-225">Accepting an instance of this type signals that your component intends to take ownership of this instance.</span></span> <span data-ttu-id="11e06-226">组件将负责根据规则 7 进行正确处理。</span><span class="sxs-lookup"><span data-stu-id="11e06-226">Your component becomes responsible for proper disposal according to Rule #7.</span></span>

<span data-ttu-id="11e06-227">在方法调用完成后，将 <xref:System.Buffers.IMemoryOwner%601> 实例的所有权转让给其他组件的任何组件应不再使用该实例。</span><span class="sxs-lookup"><span data-stu-id="11e06-227">Any component that transfers ownership of the <xref:System.Buffers.IMemoryOwner%601> instance to a different component should no longer use that instance after the method call completes.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="11e06-228">如果构造函数接受 <xref:System.Buffers.IMemoryOwner%601> 作为参数，则其类型应实现 <xref:System.IDisposable>，并且 <xref:System.IDisposable.Dispose%2A> 方法应调用 <xref:System.Buffers.MemoryPool%601.Dispose%2A?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="11e06-228">If your constructor accepts <xref:System.Buffers.IMemoryOwner%601> as a parameter, its type should implement <xref:System.IDisposable>, and your <xref:System.IDisposable.Dispose%2A> method should call <xref:System.Buffers.MemoryPool%601.Dispose%2A?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="11e06-229">**规则 9：如果正在包装同步 P/Invoke 方法，则 API 应接受跨度\<T> 作为参数。**</span><span class="sxs-lookup"><span data-stu-id="11e06-229">**Rule #9: If you're wrapping a synchronous p/invoke method, your API should accept Span\<T> as a parameter.**</span></span>

<span data-ttu-id="11e06-230">根据规则 1，<xref:System.Span%601> 通常是用于同步 API 的正确类型。</span><span class="sxs-lookup"><span data-stu-id="11e06-230">According to Rule #1, <xref:System.Span%601> is generally the correct type to use for synchronous APIs.</span></span> <span data-ttu-id="11e06-231">可以通过 [`fixed`](~/docs/csharp/language-reference/keywords/fixed-statement.md) 关键字固定 <xref:System.Span%601>\<T> 实例，如下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="11e06-231">You can pin <xref:System.Span%601>\<T> instances via the [`fixed`](~/docs/csharp/language-reference/keywords/fixed-statement.md) keyword, as in the following example.</span></span>

```csharp
using System.Runtime.InteropServices;

[DllImport(...)]
private static extern unsafe int ExportedMethod(byte* pbData, int cbData);

public unsafe int ManagedWrapper(Span<byte> data)
{
    fixed (byte* pbData = &MemoryMarshal.GetReference(data))
    {
        int retVal = ExportedMethod(pbData, data.Length);

        /* error checking retVal goes here */

        return retVal;
    }
}
```

<span data-ttu-id="11e06-232">在上一示例中，如果输入跨度为空，则 `pbData` 可以为 Null。</span><span class="sxs-lookup"><span data-stu-id="11e06-232">In the previous example, `pbData` can be null if, for example, the input span is empty.</span></span> <span data-ttu-id="11e06-233">如果导出的方法绝对需要 `pbData` 为非 Null，即使 `cbData` 为 0，则可以按如下所示实现该方法：</span><span class="sxs-lookup"><span data-stu-id="11e06-233">If the exported method absolutely requires that `pbData` be non-null, even if `cbData` is 0, the method can be implemented as follows:</span></span>

```csharp
public unsafe int ManagedWrapper(Span<byte> data)
{
    fixed (byte* pbData = &MemoryMarshal.GetReference(data))
    {
        byte dummy = 0;
        int retVal = ExportedMethod((pbData != null) ? pbData : &dummy, data.Length);

        /* error checking retVal goes here */

        return retVal;
    }
}
```

<span data-ttu-id="11e06-234">**规则 10：如果正在包装异步 P/Invoke 方法，则 API 应接受内存\<T> 作为参数。**</span><span class="sxs-lookup"><span data-stu-id="11e06-234">**Rule #10: If you're wrapping an asynchronous p/invoke method, your API should accept Memory\<T> as a parameter.**</span></span>

<span data-ttu-id="11e06-235">由于不能在异步操作中使用 [`fixed`](~/docs/csharp/language-reference/keywords/fixed-statement.md) 关键字，因此使用 <xref:System.Memory%601.Pin%2A?displayProperty=nameWithType> 方法固定 <xref:System.Memory%601> 实例，无论该实例表示的连续内存类型为何。</span><span class="sxs-lookup"><span data-stu-id="11e06-235">Since you cannot use the [`fixed`](~/docs/csharp/language-reference/keywords/fixed-statement.md) keyword across asynchronous operations, you use the <xref:System.Memory%601.Pin%2A?displayProperty=nameWithType> method to pin <xref:System.Memory%601> instances, regardless of the kind of contiguous memory the instance represents.</span></span> <span data-ttu-id="11e06-236">下面的示例演示了如何使用此 API 执行异步 P/Invoke 调用。</span><span class="sxs-lookup"><span data-stu-id="11e06-236">The following example shows how to use this API to perform an asynchronous p/invoke call.</span></span>

```csharp
using System.Runtime.InteropServices;

[UnmanagedFunctionPointer(...)]
private delegate void OnCompletedCallback(IntPtr state, int result);

[DllImport(...)]
private static extern unsafe int ExportedAsyncMethod(byte* pbData, int cbData, IntPtr pState, IntPtr lpfnOnCompletedCallback);

private static readonly IntPtr _callbackPtr = GetCompletionCallbackPointer();

public unsafe Task<int> ManagedWrapperAsync(Memory<byte> data)
{
    // setup
    var tcs = new TaskCompletionSource<int>();
    var state = new MyCompletedCallbackState
    {
        Tcs = tcs
    };
    var pState = (IntPtr)GCHandle.Alloc(state);

    var memoryHandle = data.Pin();
    state.MemoryHandle = memoryHandle;

    // make the call
    int result;
    try
    {
        result = ExportedAsyncMethod((byte*)memoryHandle.Pointer, data.Length, pState, _callbackPtr);
    }
    catch
    {
        ((GCHandle)pState).Free(); // cleanup since callback won't be invoked
        memoryHandle.Dispose();
        throw;
    }

    if (result != PENDING)
    {
        // Operation completed synchronously; invoke callback manually
        // for result processing and cleanup.
        MyCompletedCallbackImplementation(pState, result);
    }

    return tcs.Task;
}

private static void MyCompletedCallbackImplementation(IntPtr state, int result)
{
    GCHandle handle = (GCHandle)state;
    var actualState = (MyCompletedCallbackState)state;
    handle.Free();
    actualState.MemoryHandle.Dispose();

    /* error checking result goes here */

    if (error)
    {
        actualState.Tcs.SetException(...);
    }
    else
    {
        actualState.Tcs.SetResult(result);
    }
}

private static IntPtr GetCompletionCallbackPointer()
{
    OnCompletedCallback callback = MyCompletedCallbackImplementation;
    GCHandle.Alloc(callback); // keep alive for lifetime of application
    return Marshal.GetFunctionPointerForDelegate(callback);
}

private class MyCompletedCallbackState
{
    public TaskCompletionSource<int> Tcs;
    public MemoryHandle MemoryHandle;
}
```

## <a name="see-also"></a><span data-ttu-id="11e06-237">请参阅</span><span class="sxs-lookup"><span data-stu-id="11e06-237">See also</span></span>

- <xref:System.Memory%601?displayProperty=nameWithType>
- <xref:System.Buffers.IMemoryOwner%601?displayProperty=nameWithType>
- <xref:System.Span%601?displayProperty=nameWithType>
