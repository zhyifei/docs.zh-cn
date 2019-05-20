---
title: 本机互操作性最佳做法 - .NET
description: 了解与 .NET 中的本机组件交互的最佳做法。
author: jkoritzinsky
ms.author: jekoritz
ms.date: 01/18/2019
ms.openlocfilehash: 09b25ed10958142f8eead6761f18bccbe2645448
ms.sourcegitcommit: ca2ca60e6f5ea327f164be7ce26d9599e0f85fe4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2019
ms.locfileid: "65063071"
---
# <a name="native-interoperability-best-practices"></a><span data-ttu-id="d6b4e-103">本机互操作性最佳做法</span><span class="sxs-lookup"><span data-stu-id="d6b4e-103">Native interoperability best practices</span></span>

<span data-ttu-id="d6b4e-104">.NET 提供了多种方式来自定义本机互操作性代码。</span><span class="sxs-lookup"><span data-stu-id="d6b4e-104">.NET gives you a variety of ways to customize your native interoperability code.</span></span> <span data-ttu-id="d6b4e-105">本文包括 Microsoft .NET 团队为实现本机互操作性而遵循的指南。</span><span class="sxs-lookup"><span data-stu-id="d6b4e-105">This article includes the guidance that Microsoft's .NET teams follow for native interoperability.</span></span>

## <a name="general-guidance"></a><span data-ttu-id="d6b4e-106">通用指南</span><span class="sxs-lookup"><span data-stu-id="d6b4e-106">General guidance</span></span>

<span data-ttu-id="d6b4e-107">本部分中的指南适用于所有互操作方案。</span><span class="sxs-lookup"><span data-stu-id="d6b4e-107">The guidance in this section applies to all interop scenarios.</span></span>

- <span data-ttu-id="d6b4e-108">✔️ 请务必对方法和参数使用同一命名和大小写以作为要调用的本机方法。</span><span class="sxs-lookup"><span data-stu-id="d6b4e-108">**✔️ DO** use the same naming and capitalization for your methods and parameters as the native method you want to call.</span></span>
- <span data-ttu-id="d6b4e-109">✔️ 请考虑对常数值使用同一命名和大小写。</span><span class="sxs-lookup"><span data-stu-id="d6b4e-109">**✔️ CONSIDER** using the same naming and capitalization for constant values.</span></span>
- <span data-ttu-id="d6b4e-110">✔️ 请务必使用映射到最接近本机类型的 .NET 类型。</span><span class="sxs-lookup"><span data-stu-id="d6b4e-110">**✔️ DO** use .NET types that map closest to the native type.</span></span> <span data-ttu-id="d6b4e-111">例如，在 C# 中，当本机类型为 `unsigned int` 时使用 `uint`。</span><span class="sxs-lookup"><span data-stu-id="d6b4e-111">For example, in C#, use `uint` when the native type is `unsigned int`.</span></span>
- <span data-ttu-id="d6b4e-112">✔️ 请务必在所需行为与默认行为不同时仅使用 `[In]` 和 `[Out]` 属性。</span><span class="sxs-lookup"><span data-stu-id="d6b4e-112">**✔️ DO** only use `[In]` and `[Out]` attributes when the behavior you want differs from the default behavior.</span></span>
- <span data-ttu-id="d6b4e-113">✔️ 请考虑使用 <xref:System.Buffers.ArrayPool%601?displayProperty=nameWithType> 汇集本机数组缓冲区。</span><span class="sxs-lookup"><span data-stu-id="d6b4e-113">**✔️ CONSIDER** using <xref:System.Buffers.ArrayPool%601?displayProperty=nameWithType> to pool your native array buffers.</span></span>
- <span data-ttu-id="d6b4e-114">✔️ 请考虑使用与本机库相同的名称和大小写包装类中的 P/Invoke 声明。</span><span class="sxs-lookup"><span data-stu-id="d6b4e-114">**✔️ CONSIDER** wrapping your P/Invoke declarations in a class with the same name and capitalization as your native library.</span></span>
  - <span data-ttu-id="d6b4e-115">这允许 `[DllImport]` 属性使用 C# `nameof` 语言功能传入本机库的名称，并确保本机库的名称拼写正确。</span><span class="sxs-lookup"><span data-stu-id="d6b4e-115">This allows your `[DllImport]` attributes to use the C# `nameof` language feature to pass in the name of the native library and ensure that you didn't misspell the name of the native library.</span></span>

## <a name="dllimport-attribute-settings"></a><span data-ttu-id="d6b4e-116">DllImport 属性设置</span><span class="sxs-lookup"><span data-stu-id="d6b4e-116">DllImport attribute settings</span></span>

| <span data-ttu-id="d6b4e-117">设置</span><span class="sxs-lookup"><span data-stu-id="d6b4e-117">Setting</span></span> | <span data-ttu-id="d6b4e-118">默认</span><span class="sxs-lookup"><span data-stu-id="d6b4e-118">Default</span></span> | <span data-ttu-id="d6b4e-119">建议</span><span class="sxs-lookup"><span data-stu-id="d6b4e-119">Recommendation</span></span> | <span data-ttu-id="d6b4e-120">详细信息</span><span class="sxs-lookup"><span data-stu-id="d6b4e-120">Details</span></span> |
|---------|---------|----------------|---------|
| <xref:System.Runtime.InteropServices.DllImportAttribute.PreserveSig>   | `true` |  <span data-ttu-id="d6b4e-121">保留默认设置</span><span class="sxs-lookup"><span data-stu-id="d6b4e-121">keep default</span></span>  | <span data-ttu-id="d6b4e-122">将其显式设置为 False 时，失败的 HRESULT 返回值将变为异常（因此，定义中的返回值将变为 Null）。</span><span class="sxs-lookup"><span data-stu-id="d6b4e-122">When this is explicitly set to false, failed HRESULT return values will be turned into exceptions (and the return value in the definition becomes null as a result).</span></span>|
| <xref:System.Runtime.InteropServices.DllImportAttribute.SetLastError> | `false`  | <span data-ttu-id="d6b4e-123">取决于 API</span><span class="sxs-lookup"><span data-stu-id="d6b4e-123">depends on the API</span></span>  | <span data-ttu-id="d6b4e-124">如果 API 使用 GetLastError，并使用 Marshal.GetLastWin32Error 获取值，则将其设置为 True。</span><span class="sxs-lookup"><span data-stu-id="d6b4e-124">Set this to true if the API uses GetLastError and use Marshal.GetLastWin32Error to get the value.</span></span> <span data-ttu-id="d6b4e-125">如果 API 设置一个表示其有错误的条件，则在进行其他调用之前获取错误以避免无意覆盖该错误。</span><span class="sxs-lookup"><span data-stu-id="d6b4e-125">If the API sets a condition that says it has an error, get the error before making other calls to avoid inadvertently having it overwritten.</span></span>|
| <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet> | <span data-ttu-id="d6b4e-126">`CharSet.None`，这会退回到 `CharSet.Ansi` 行为</span><span class="sxs-lookup"><span data-stu-id="d6b4e-126">`CharSet.None`, which falls back to `CharSet.Ansi` behavior</span></span>  | <span data-ttu-id="d6b4e-127">定义中存在字符串或字符时显式使用 `CharSet.Unicode` 或 `CharSet.Ansi`</span><span class="sxs-lookup"><span data-stu-id="d6b4e-127">Explicitly  use `CharSet.Unicode` or `CharSet.Ansi` when strings or characters are present in the definition</span></span> | <span data-ttu-id="d6b4e-128">这将指定字符串的封送行为以及为 `false` 时 `ExactSpelling` 的操作。</span><span class="sxs-lookup"><span data-stu-id="d6b4e-128">This specifies marshaling behavior of strings and what `ExactSpelling` does when `false`.</span></span> <span data-ttu-id="d6b4e-129">请注意，`CharSet.Ansi` 在 Unix 上实际为 UTF8。</span><span class="sxs-lookup"><span data-stu-id="d6b4e-129">Note that `CharSet.Ansi` is actually UTF8 on Unix.</span></span> <span data-ttu-id="d6b4e-130">大部分时间，Windows 使用 Unicode，而 Unix 使用 UTF8。</span><span class="sxs-lookup"><span data-stu-id="d6b4e-130">_Most_ of the time Windows uses Unicode while Unix uses UTF8.</span></span> <span data-ttu-id="d6b4e-131">有关更多信息，请查看[有关字符集的文档](./charset.md)。</span><span class="sxs-lookup"><span data-stu-id="d6b4e-131">See more information on the [documentation on charsets](./charset.md).</span></span> |
| <xref:System.Runtime.InteropServices.DllImportAttribute.ExactSpelling> | `false` | `true`             | <span data-ttu-id="d6b4e-132">将其设置为 True 并在运行时获得些许性能优势不会查找后缀为“A”或“W”的备用函数名称，具体取决于 `CharSet` 设置的值（“A”用于 `CharSet.Ansi`，“W”用于 `CharSet.Unicode`）。</span><span class="sxs-lookup"><span data-stu-id="d6b4e-132">Set this to true and gain a slight perf benefit as the runtime will not look for alternate function names with either an "A" or "W" suffix depending on the value of the `CharSet` setting ("A" for `CharSet.Ansi` and "W" for `CharSet.Unicode`).</span></span> |

## <a name="string-parameters"></a><span data-ttu-id="d6b4e-133">字符串参数</span><span class="sxs-lookup"><span data-stu-id="d6b4e-133">String parameters</span></span>

<span data-ttu-id="d6b4e-134">当字符集为 Unicode 或参数显式标记为 `[MarshalAs(UnmanagedType.LPWSTR)]`，并且通过值（不是 `ref` 或 `out`）传递字符串时，将固定该字符串并直接由本机代码使用（而非复制）。</span><span class="sxs-lookup"><span data-stu-id="d6b4e-134">When the CharSet is Unicode or the argument is explicitly marked as `[MarshalAs(UnmanagedType.LPWSTR)]` _and_ the string is passed by value (not `ref` or `out`), the string will be pinned and used directly by native code (rather than copied).</span></span>

<span data-ttu-id="d6b4e-135">除非明确想要对字符串进行 ANSI 处理，否则请务必将 `[DllImport]` 标记为 `Charset.Unicode`。</span><span class="sxs-lookup"><span data-stu-id="d6b4e-135">Remember to mark the `[DllImport]` as `Charset.Unicode` unless you explicitly want ANSI treatment of your strings.</span></span>

<span data-ttu-id="d6b4e-136">❌ 请勿使用 `[Out] string` 参数。</span><span class="sxs-lookup"><span data-stu-id="d6b4e-136">**❌ DO NOT** use `[Out] string` parameters.</span></span> <span data-ttu-id="d6b4e-137">如果该字符串为暂存的字符串，则通过包含 `[Out]` 属性的值传递的字符串参数可能使运行时变得不稳定。</span><span class="sxs-lookup"><span data-stu-id="d6b4e-137">String parameters passed by value with the `[Out]` attribute can destabilize the runtime if the string is an interned string.</span></span> <span data-ttu-id="d6b4e-138">请在 <xref:System.String.Intern%2A?displayProperty=nameWithType> 的文档中查看有关字符串暂存的详细信息。</span><span class="sxs-lookup"><span data-stu-id="d6b4e-138">See more information about string interning in the documentation for <xref:System.String.Intern%2A?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="d6b4e-139">❌ 避免使用 `StringBuilder` 参数。</span><span class="sxs-lookup"><span data-stu-id="d6b4e-139">**❌ AVOID** `StringBuilder` parameters.</span></span> <span data-ttu-id="d6b4e-140">`StringBuilder` 封送*始终*创建本机缓冲区副本。</span><span class="sxs-lookup"><span data-stu-id="d6b4e-140">`StringBuilder` marshaling *always* creates a native buffer copy.</span></span> <span data-ttu-id="d6b4e-141">因此，该操作的效率可能非常低。</span><span class="sxs-lookup"><span data-stu-id="d6b4e-141">As such, it can be extremely inefficient.</span></span> <span data-ttu-id="d6b4e-142">采取调用带有字符串的 Windows API 的典型方案：</span><span class="sxs-lookup"><span data-stu-id="d6b4e-142">Take the typical scenario of calling a Windows API that takes a string:</span></span>

1. <span data-ttu-id="d6b4e-143">创建所需容量的 SB（分配托管容量）**{1}**</span><span class="sxs-lookup"><span data-stu-id="d6b4e-143">Create a SB of the desired capacity (allocates managed capacity) **{1}**</span></span>
2. <span data-ttu-id="d6b4e-144">调用</span><span class="sxs-lookup"><span data-stu-id="d6b4e-144">Invoke</span></span>
   1. <span data-ttu-id="d6b4e-145">分配本机缓冲区 **{2}**</span><span class="sxs-lookup"><span data-stu-id="d6b4e-145">Allocates a native buffer **{2}**</span></span>  
   2. <span data-ttu-id="d6b4e-146">如果为 `[In]`（`StringBuilder` 参数的默认值），则复制内容</span><span class="sxs-lookup"><span data-stu-id="d6b4e-146">Copies the contents if `[In]` _(the default for a `StringBuilder` parameter)_</span></span>  
   3. <span data-ttu-id="d6b4e-147">如果为 `[Out]` {3}_（也是 `StringBuilder` 的默认值）_，则将本机缓冲区复制到新分配的托管数组中</span><span class="sxs-lookup"><span data-stu-id="d6b4e-147">Copies the native buffer into a newly allocated managed array if `[Out]` **{3}** _(also the default for `StringBuilder`)_</span></span>  
3. <span data-ttu-id="d6b4e-148">`ToString()` 分配其他托管数组 {4}</span><span class="sxs-lookup"><span data-stu-id="d6b4e-148">`ToString()` allocates yet another managed array **{4}**</span></span>

<span data-ttu-id="d6b4e-149">这是 {4} 分配，可从本机代码中获取字符串。</span><span class="sxs-lookup"><span data-stu-id="d6b4e-149">That is *{4}* allocations to get a string out of native code.</span></span> <span data-ttu-id="d6b4e-150">可用来限制此操作的最佳方法是在其他调用中重用 `StringBuilder`，但这仍只能保存 1 个分配。</span><span class="sxs-lookup"><span data-stu-id="d6b4e-150">The best you can do to limit this is to reuse the `StringBuilder` in another call but this still only saves *1* allocation.</span></span> <span data-ttu-id="d6b4e-151">最好从 `ArrayPool` 使用并缓存字符缓冲区 - 然后可以在后续调用中直接获得 `ToString()` 的分配。</span><span class="sxs-lookup"><span data-stu-id="d6b4e-151">It's much better to use and cache a character buffer from `ArrayPool`- you can then get down to just the allocation for the `ToString()` on subsequent calls.</span></span>

<span data-ttu-id="d6b4e-152">`StringBuilder` 的另一个问题是它始终会将返回缓冲区备份复制到第一个 Null。</span><span class="sxs-lookup"><span data-stu-id="d6b4e-152">The other issue with `StringBuilder` is that it always copies the return buffer back up to the first null.</span></span> <span data-ttu-id="d6b4e-153">如果传递的返回字符串未终止或为双 Null 终止字符串，则 P/Invoke 很可能不正确。</span><span class="sxs-lookup"><span data-stu-id="d6b4e-153">If the passed back string isn't terminated or is a double-null-terminated string, your P/Invoke is incorrect at best.</span></span>

<span data-ttu-id="d6b4e-154">如果使用 `StringBuilder`，则最后一个问题是容量确实不会包括隐藏的 Null，该值始终计入互操作。</span><span class="sxs-lookup"><span data-stu-id="d6b4e-154">If you *do* use `StringBuilder`, one last gotcha is that the capacity does **not** include a hidden null, which is always accounted for in interop.</span></span> <span data-ttu-id="d6b4e-155">人们常常会犯这个错误，因为大多数 API 希望缓冲区的大小包括 Null。</span><span class="sxs-lookup"><span data-stu-id="d6b4e-155">It's common for people to get this wrong as most APIs want the size of the buffer *including* the null.</span></span> <span data-ttu-id="d6b4e-156">这可能会导致产生浪费/不必要的分配。</span><span class="sxs-lookup"><span data-stu-id="d6b4e-156">This can result in wasted/unnecessary allocations.</span></span> <span data-ttu-id="d6b4e-157">此外，此问题会阻止运行时通过优化 `StringBuilder` 封送来最大限度地减少副本。</span><span class="sxs-lookup"><span data-stu-id="d6b4e-157">Additionally, this gotcha prevents the runtime from optimizing `StringBuilder` marshaling to minimize copies.</span></span>

<span data-ttu-id="d6b4e-158">✔️ 请考虑使用 `ArrayPool` 中的 `char[]`。</span><span class="sxs-lookup"><span data-stu-id="d6b4e-158">**✔️ CONSIDER** using `char[]`s from an `ArrayPool`.</span></span>

<span data-ttu-id="d6b4e-159">有关字符串封送的详细信息，请参阅[字符串的默认封送](../../framework/interop/default-marshaling-for-strings.md)和[自定义字符串封送](customize-parameter-marshaling.md#customizing-string-parameters)。</span><span class="sxs-lookup"><span data-stu-id="d6b4e-159">For more information on string marshaling, see [Default Marshaling for Strings](../../framework/interop/default-marshaling-for-strings.md) and [Customizing string marshaling](customize-parameter-marshaling.md#customizing-string-parameters).</span></span>

> <span data-ttu-id="d6b4e-160">__Windows 特定__</span><span class="sxs-lookup"><span data-stu-id="d6b4e-160">__Windows Specific__</span></span>  
> <span data-ttu-id="d6b4e-161">对于 `[Out]` 字符串，CLR 将默认使用 `CoTaskMemFree` 来释放字符串，或对于标记为 `UnmanagedType.BSTR` 的字符串，使用 `SysStringFree`。</span><span class="sxs-lookup"><span data-stu-id="d6b4e-161">For `[Out]` strings the CLR will use `CoTaskMemFree` by default to free strings or `SysStringFree` for strings that are marked as `UnmanagedType.BSTR`.</span></span>  
<span data-ttu-id="d6b4e-162">**对于具有输出字符串缓冲区的大多数 API：**</span><span class="sxs-lookup"><span data-stu-id="d6b4e-162">**For most APIs with an output string buffer:**</span></span>  
> <span data-ttu-id="d6b4e-163">传入的字符计数必须包括 Null。</span><span class="sxs-lookup"><span data-stu-id="d6b4e-163">The passed in character count must include the null.</span></span> <span data-ttu-id="d6b4e-164">如果返回的值小于传入的字符计数，则调用成功，并且该值是不带尾随 Null 的字符数。</span><span class="sxs-lookup"><span data-stu-id="d6b4e-164">If the returned value is less than the passed in character count the call has succeeded and the value is the number of characters *without* the trailing null.</span></span> <span data-ttu-id="d6b4e-165">否则，该计数是包括 Null 字符的缓冲区的所需大小。</span><span class="sxs-lookup"><span data-stu-id="d6b4e-165">Otherwise the count is the required size of the buffer *including* the null character.</span></span>  
> - <span data-ttu-id="d6b4e-166">传入 5 个，获取 4 个：字符串包含 4 个字符，带有尾随 Null。</span><span class="sxs-lookup"><span data-stu-id="d6b4e-166">Pass in 5, get 4: The string is 4 characters long with a trailing null.</span></span>
> - <span data-ttu-id="d6b4e-167">传入 5 个，获取 6 个：字符串包含 5 个字符，需要包含 6 个字符的缓冲区来保存 Null。</span><span class="sxs-lookup"><span data-stu-id="d6b4e-167">Pass in 5, get 6: The string is 5 characters long, need a 6 character buffer to hold the null.</span></span>  
> [<span data-ttu-id="d6b4e-168">字符串的 Windows 数据类型</span><span class="sxs-lookup"><span data-stu-id="d6b4e-168">Windows Data Types for Strings</span></span>](/windows/desktop/Intl/windows-data-types-for-strings)

## <a name="boolean-parameters-and-fields"></a><span data-ttu-id="d6b4e-169">布尔参数和字段</span><span class="sxs-lookup"><span data-stu-id="d6b4e-169">Boolean parameters and fields</span></span>

<span data-ttu-id="d6b4e-170">布尔值很容易混淆。</span><span class="sxs-lookup"><span data-stu-id="d6b4e-170">Booleans are easy to mess up.</span></span> <span data-ttu-id="d6b4e-171">默认情况下，将 .NET `bool` 封送到 Windows `BOOL`，它在其中为包含 4 个字节的值。</span><span class="sxs-lookup"><span data-stu-id="d6b4e-171">By default, a .NET `bool` is marshaled to a Windows `BOOL`, where it's a 4-byte value.</span></span> <span data-ttu-id="d6b4e-172">但是，C 和 C++ 中的 `_Bool` 和 `bool` 类型是单字节。</span><span class="sxs-lookup"><span data-stu-id="d6b4e-172">However, the `_Bool`, and `bool` types in C and C++ are a *single* byte.</span></span> <span data-ttu-id="d6b4e-173">这可能会导致难以跟踪 bug，因为一半的返回值将被丢弃，这样可能只会更改结果。</span><span class="sxs-lookup"><span data-stu-id="d6b4e-173">This can lead to hard to track down bugs as half the return value will be discarded, which will only *potentially* change the result.</span></span> <span data-ttu-id="d6b4e-174">有关将 .NET `bool` 值封送到 C 或 C++ `bool` 类型的详细信息，请参阅有关[自定义布尔字段封送](customize-struct-marshaling.md#customizing-boolean-field-marshaling)的文档。</span><span class="sxs-lookup"><span data-stu-id="d6b4e-174">For more for information on marshaling .NET `bool` values to C or C++ `bool` types, see the documentation on [customizing boolean field marshaling](customize-struct-marshaling.md#customizing-boolean-field-marshaling).</span></span>

## <a name="guids"></a><span data-ttu-id="d6b4e-175">GUID</span><span class="sxs-lookup"><span data-stu-id="d6b4e-175">GUIDs</span></span>

<span data-ttu-id="d6b4e-176">GUID 可在签名中直接使用。</span><span class="sxs-lookup"><span data-stu-id="d6b4e-176">GUIDs are usable directly in signatures.</span></span> <span data-ttu-id="d6b4e-177">许多 Windows API 使用 `GUID&` 类型别名（例如，`REFIID`）。</span><span class="sxs-lookup"><span data-stu-id="d6b4e-177">Many Windows APIs take `GUID&` type aliases like `REFIID`.</span></span> <span data-ttu-id="d6b4e-178">通过引用传递时，可以通过 `ref` 或使用 `[MarshalAs(UnmanagedType.LPStruct)]` 属性传递。</span><span class="sxs-lookup"><span data-stu-id="d6b4e-178">When passed by ref, they can either be passed by `ref` or with the `[MarshalAs(UnmanagedType.LPStruct)]` attribute.</span></span>

| <span data-ttu-id="d6b4e-179">GUID</span><span class="sxs-lookup"><span data-stu-id="d6b4e-179">GUID</span></span> | <span data-ttu-id="d6b4e-180">通过引用传递的 GUID</span><span class="sxs-lookup"><span data-stu-id="d6b4e-180">By-ref GUID</span></span> |
|------|-------------|
| `KNOWNFOLDERID` | `REFKNOWNFOLDERID` |

<span data-ttu-id="d6b4e-181">❌ 请勿对除 `ref` GUID 参数以外的任何参数使用 `[MarshalAs(UnmanagedType.LPStruct)]`。</span><span class="sxs-lookup"><span data-stu-id="d6b4e-181">**❌ DO NOT** Use `[MarshalAs(UnmanagedType.LPStruct)]` for anything other than `ref` GUID parameters.</span></span>

## <a name="blittable-types"></a><span data-ttu-id="d6b4e-182">Blittable 类型</span><span class="sxs-lookup"><span data-stu-id="d6b4e-182">Blittable types</span></span>

<span data-ttu-id="d6b4e-183">Blittable 类型是托管代码和本机代码中具有相同位级别表示形式的类型。</span><span class="sxs-lookup"><span data-stu-id="d6b4e-183">Blittable types are types that have the same bit-level representation in managed and native code.</span></span> <span data-ttu-id="d6b4e-184">因此，无需将这些类型转换为其他格式即可往返本机代码进行封送，而且由于这样可以提高性能，应首选这些类型。</span><span class="sxs-lookup"><span data-stu-id="d6b4e-184">As such they do not need to be converted to another format to be marshaled to and from native code, and as this improves performance they should be preferred.</span></span>

<span data-ttu-id="d6b4e-185">**：**</span><span class="sxs-lookup"><span data-stu-id="d6b4e-185">**Blittable types:**</span></span>

- <span data-ttu-id="d6b4e-186">`byte`, `sbyte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `single`, `double`</span><span class="sxs-lookup"><span data-stu-id="d6b4e-186">`byte`, `sbyte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `single`, `double`</span></span>
- <span data-ttu-id="d6b4e-187">Blittable 类型的非嵌套一维数组（例如，`int[]`）</span><span class="sxs-lookup"><span data-stu-id="d6b4e-187">non-nested one-dimensional arrays of blittable types (for example, `int[]`)</span></span>
- <span data-ttu-id="d6b4e-188">具有实例字段只有 blittable 值类型的固定布局的结构和类</span><span class="sxs-lookup"><span data-stu-id="d6b4e-188">structs and classes with fixed layout that only have blittable value types for instance fields</span></span>
  - <span data-ttu-id="d6b4e-189">固定的布局需要 `[StructLayout(LayoutKind.Sequential)]` 或 `[StructLayout(LayoutKind.Explicit)]`</span><span class="sxs-lookup"><span data-stu-id="d6b4e-189">fixed layout requires `[StructLayout(LayoutKind.Sequential)]` or `[StructLayout(LayoutKind.Explicit)]`</span></span>
  - <span data-ttu-id="d6b4e-190">默认情况下结构为 `LayoutKind.Sequential`，类为 `LayoutKind.Auto`</span><span class="sxs-lookup"><span data-stu-id="d6b4e-190">structs are `LayoutKind.Sequential` by default, classes are `LayoutKind.Auto`</span></span>

<span data-ttu-id="d6b4e-191">**不是 blittable：**</span><span class="sxs-lookup"><span data-stu-id="d6b4e-191">**NOT blittable:**</span></span>

- `bool`

<span data-ttu-id="d6b4e-192">**有时为 blittable：**</span><span class="sxs-lookup"><span data-stu-id="d6b4e-192">**SOMETIMES blittable:**</span></span>

- <span data-ttu-id="d6b4e-193">`char`， `string`</span><span class="sxs-lookup"><span data-stu-id="d6b4e-193">`char`, `string`</span></span>

<span data-ttu-id="d6b4e-194">通过引用传递 blittable 类型时，这些类型只会被封送处理程序固定，而不会复制到中间缓冲区。</span><span class="sxs-lookup"><span data-stu-id="d6b4e-194">When blittable types are passed by reference, they're simply pinned by the marshaller instead of being copied to an intermediate buffer.</span></span> <span data-ttu-id="d6b4e-195">（类在本质上通过引用传递，结构在与 `ref` 或 `out` 结合使用时会通过引用传递。）</span><span class="sxs-lookup"><span data-stu-id="d6b4e-195">(Classes are inherently passed by reference, structs are passed by reference when used with `ref` or `out`.)</span></span>

<span data-ttu-id="d6b4e-196">如果 `char` 位于一维数组中，或者如果它是包含使用 `CharSet = CharSet.Unicode` 的 `[StructLayout]` 显式标记的类型的一部分，则该类型为 blittable。</span><span class="sxs-lookup"><span data-stu-id="d6b4e-196">`char` is blittable in a one-dimensional array **or** if it's part of a type that contains it's explicitly marked with `[StructLayout]` with `CharSet = CharSet.Unicode`.</span></span>

```csharp
[StructLayout(LayoutKind.Sequential, CharSet = CharSet.Unicode)]
public struct UnicodeCharStruct
{
    public char c;
}
```

<span data-ttu-id="d6b4e-197">如果 `string` 不包含在其他类型中，并且作为使用 `[MarshalAs(UnmanagedType.LPWStr)]` 标记的参数传递或 `[DllImport]` 已设置 `CharSet = CharSet.Unicode`，则该类型为 blittable。</span><span class="sxs-lookup"><span data-stu-id="d6b4e-197">`string` is blittable if it isn't contained in another type and it's being passed as an argument that is marked with `[MarshalAs(UnmanagedType.LPWStr)]` or the `[DllImport]` has `CharSet = CharSet.Unicode` set.</span></span>

<span data-ttu-id="d6b4e-198">可以通过尝试创建固定的 `GCHandle` 来查看类型是否为 blittable。</span><span class="sxs-lookup"><span data-stu-id="d6b4e-198">You can see if a type is blittable by attempting to create a pinned `GCHandle`.</span></span> <span data-ttu-id="d6b4e-199">如果该类型不是字符串或被视为 blittable，则 `GCHandle.Alloc` 将引发 `ArgumentException`。</span><span class="sxs-lookup"><span data-stu-id="d6b4e-199">If the type isn't a string or considered blittable, `GCHandle.Alloc` will throw an `ArgumentException`.</span></span>

<span data-ttu-id="d6b4e-200">✔️ 尽可能使结构为 blittable。</span><span class="sxs-lookup"><span data-stu-id="d6b4e-200">**✔️ DO** make your structures blittable when possible.</span></span>

<span data-ttu-id="d6b4e-201">有关详细信息，请参见:</span><span class="sxs-lookup"><span data-stu-id="d6b4e-201">For more information, see:</span></span>

- [<span data-ttu-id="d6b4e-202">可直接复制到本机结构中的类型和非直接复制到本机结构中的类型</span><span class="sxs-lookup"><span data-stu-id="d6b4e-202">Blittable and Non-Blittable Types</span></span>](../../framework/interop/blittable-and-non-blittable-types.md)  
- [<span data-ttu-id="d6b4e-203">类型封送</span><span class="sxs-lookup"><span data-stu-id="d6b4e-203">Type Marshaling</span></span>](type-marshaling.md)

## <a name="keeping-managed-objects-alive"></a><span data-ttu-id="d6b4e-204">使托管对象保持活动状态</span><span class="sxs-lookup"><span data-stu-id="d6b4e-204">Keeping managed objects alive</span></span>

<span data-ttu-id="d6b4e-205">`GC.KeepAlive()` 将确保对象保持在作用域内，直到采用 KeepAlive 方法。</span><span class="sxs-lookup"><span data-stu-id="d6b4e-205">`GC.KeepAlive()` will ensure an object stays in scope until the KeepAlive method is hit.</span></span>

<span data-ttu-id="d6b4e-206">[`HandleRef`](xref:System.Runtime.InteropServices.HandleRef) 允许封送处理程序在 P/Invoke 的持续时间内使对象保持活动状态。</span><span class="sxs-lookup"><span data-stu-id="d6b4e-206">[`HandleRef`](xref:System.Runtime.InteropServices.HandleRef) allows the marshaller to keep an object alive for the duration of a P/Invoke.</span></span> <span data-ttu-id="d6b4e-207">方法签名中可以使用该类型，而不是 `IntPtr`。</span><span class="sxs-lookup"><span data-stu-id="d6b4e-207">It can be used instead of `IntPtr` in method signatures.</span></span> <span data-ttu-id="d6b4e-208">`SafeHandle` 可有效地替换此类，应改为使用此类型。</span><span class="sxs-lookup"><span data-stu-id="d6b4e-208">`SafeHandle` effectively replaces this class and should be used instead.</span></span>

<span data-ttu-id="d6b4e-209">[`GCHandle`](xref:System.Runtime.InteropServices.GCHandle) 允许固定托管对象和获取指向该类型的本机指针。</span><span class="sxs-lookup"><span data-stu-id="d6b4e-209">[`GCHandle`](xref:System.Runtime.InteropServices.GCHandle) allows pinning a managed object and getting the native pointer to it.</span></span> <span data-ttu-id="d6b4e-210">基本模式是：</span><span class="sxs-lookup"><span data-stu-id="d6b4e-210">The basic pattern is:</span></span>  

```csharp
GCHandle handle = GCHandle.Alloc(obj, GCHandleType.Pinned);
IntPtr ptr = handle.AddrOfPinnedObject();
handle.Free();
```

<span data-ttu-id="d6b4e-211">固定不是 `GCHandle` 的默认设置。</span><span class="sxs-lookup"><span data-stu-id="d6b4e-211">Pinning isn't the default for `GCHandle`.</span></span> <span data-ttu-id="d6b4e-212">其他主要模式是通过本机代码将引用传递到托管对象并返回到托管代码（通常使用回调）。</span><span class="sxs-lookup"><span data-stu-id="d6b4e-212">The other major pattern is for passing a reference to a managed object through native code and back to managed code, usually with a callback.</span></span> <span data-ttu-id="d6b4e-213">模式如下：</span><span class="sxs-lookup"><span data-stu-id="d6b4e-213">Here is the pattern:</span></span>

```csharp
GCHandle handle = GCHandle.Alloc(obj);
SomeNativeEnumerator(callbackDelegate, GCHandle.ToIntPtr(handle));

// In the callback
GCHandle handle = GCHandle.FromIntPtr(param);
object managedObject = handle.Target;

// After the last callback
handle.Free();
```

<span data-ttu-id="d6b4e-214">请务必注意需要显式释放 `GCHandle` 以避免内存泄漏。</span><span class="sxs-lookup"><span data-stu-id="d6b4e-214">Don't forget that `GCHandle` needs to be explicitly freed to avoid memory leaks.</span></span>

## <a name="common-windows-data-types"></a><span data-ttu-id="d6b4e-215">常见的 Windows 数据类型</span><span class="sxs-lookup"><span data-stu-id="d6b4e-215">Common Windows data types</span></span>

<span data-ttu-id="d6b4e-216">下面是 Windows API 中常用的数据类型列表以及调用 Windows 代码时要使用的 C# 类型。</span><span class="sxs-lookup"><span data-stu-id="d6b4e-216">Here is a list of data types commonly used in Windows APIs and which C# types to use when calling into the Windows code.</span></span>

<span data-ttu-id="d6b4e-217">以下类型在 32 位和 64 位 Windows 上具有相同大小，而不管其名称为何。</span><span class="sxs-lookup"><span data-stu-id="d6b4e-217">The following types are the same size on 32-bit and 64-bit Windows, despite their names.</span></span>

| <span data-ttu-id="d6b4e-218">宽度</span><span class="sxs-lookup"><span data-stu-id="d6b4e-218">Width</span></span> | <span data-ttu-id="d6b4e-219">Windows</span><span class="sxs-lookup"><span data-stu-id="d6b4e-219">Windows</span></span>          | <span data-ttu-id="d6b4e-220">C (Windows)</span><span class="sxs-lookup"><span data-stu-id="d6b4e-220">C (Windows)</span></span>          | <span data-ttu-id="d6b4e-221">C#</span><span class="sxs-lookup"><span data-stu-id="d6b4e-221">C#</span></span>       | <span data-ttu-id="d6b4e-222">替代项</span><span class="sxs-lookup"><span data-stu-id="d6b4e-222">Alternative</span></span>                          |
|:------|:-----------------|:---------------------|:---------|:-------------------------------------|
| <span data-ttu-id="d6b4e-223">32</span><span class="sxs-lookup"><span data-stu-id="d6b4e-223">32</span></span>    | `BOOL`           | `int`                | `int`    | `bool`                               |
| <span data-ttu-id="d6b4e-224">8</span><span class="sxs-lookup"><span data-stu-id="d6b4e-224">8</span></span>     | `BOOLEAN`        | `unsigned char`      | `byte`   | `[MarshalAs(UnmanagedType.U1)] bool` |
| <span data-ttu-id="d6b4e-225">8</span><span class="sxs-lookup"><span data-stu-id="d6b4e-225">8</span></span>     | `BYTE`           | `unsigned char`      | `byte`   |                                      |
| <span data-ttu-id="d6b4e-226">8</span><span class="sxs-lookup"><span data-stu-id="d6b4e-226">8</span></span>     | `CHAR`           | `char`               | `sbyte`  |                                      |
| <span data-ttu-id="d6b4e-227">8</span><span class="sxs-lookup"><span data-stu-id="d6b4e-227">8</span></span>     | `UCHAR`          | `unsigned char`      | `byte`   |                                      |
| <span data-ttu-id="d6b4e-228">16</span><span class="sxs-lookup"><span data-stu-id="d6b4e-228">16</span></span>    | `SHORT`          | `short`              | `short`  |                                      |
| <span data-ttu-id="d6b4e-229">16</span><span class="sxs-lookup"><span data-stu-id="d6b4e-229">16</span></span>    | `CSHORT`         | `short`              | `short`  |                                      |
| <span data-ttu-id="d6b4e-230">16</span><span class="sxs-lookup"><span data-stu-id="d6b4e-230">16</span></span>    | `USHORT`         | `unsigned short`     | `ushort` |                                      |
| <span data-ttu-id="d6b4e-231">16</span><span class="sxs-lookup"><span data-stu-id="d6b4e-231">16</span></span>    | `WORD`           | `unsigned short`     | `ushort` |                                      |
| <span data-ttu-id="d6b4e-232">16</span><span class="sxs-lookup"><span data-stu-id="d6b4e-232">16</span></span>    | `ATOM`           | `unsigned short`     | `ushort` |                                      |
| <span data-ttu-id="d6b4e-233">32</span><span class="sxs-lookup"><span data-stu-id="d6b4e-233">32</span></span>    | `INT`            | `int`                | `int`    |                                      |
| <span data-ttu-id="d6b4e-234">32</span><span class="sxs-lookup"><span data-stu-id="d6b4e-234">32</span></span>    | `LONG`           | `long`               | `int`    |                                      |
| <span data-ttu-id="d6b4e-235">32</span><span class="sxs-lookup"><span data-stu-id="d6b4e-235">32</span></span>    | `ULONG`          | `unsigned long`      | `uint`   |                                      |
| <span data-ttu-id="d6b4e-236">32</span><span class="sxs-lookup"><span data-stu-id="d6b4e-236">32</span></span>    | `DWORD`          | `unsigned long`      | `uint`   |                                      |
| <span data-ttu-id="d6b4e-237">64</span><span class="sxs-lookup"><span data-stu-id="d6b4e-237">64</span></span>    | `QWORD`          | `long long`          | `long`   |                                      |
| <span data-ttu-id="d6b4e-238">64</span><span class="sxs-lookup"><span data-stu-id="d6b4e-238">64</span></span>    | `LARGE_INTEGER`  | `long long`          | `long`   |                                      |
| <span data-ttu-id="d6b4e-239">64</span><span class="sxs-lookup"><span data-stu-id="d6b4e-239">64</span></span>    | `LONGLONG`       | `long long`          | `long`   |                                      |
| <span data-ttu-id="d6b4e-240">64</span><span class="sxs-lookup"><span data-stu-id="d6b4e-240">64</span></span>    | `ULONGLONG`      | `unsigned long long` | `ulong`  |                                      |
| <span data-ttu-id="d6b4e-241">64</span><span class="sxs-lookup"><span data-stu-id="d6b4e-241">64</span></span>    | `ULARGE_INTEGER` | `unsigned long long` | `ulong`  |                                      |
| <span data-ttu-id="d6b4e-242">32</span><span class="sxs-lookup"><span data-stu-id="d6b4e-242">32</span></span>    | `HRESULT`        | `long`               | `int`    |                                      |
| <span data-ttu-id="d6b4e-243">32</span><span class="sxs-lookup"><span data-stu-id="d6b4e-243">32</span></span>    | `NTSTATUS`       | `long`               | `int`    |                                      |

<span data-ttu-id="d6b4e-244">以下类型（指针）遵循平台的宽度。</span><span class="sxs-lookup"><span data-stu-id="d6b4e-244">The following types, being pointers, do follow the width of the platform.</span></span> <span data-ttu-id="d6b4e-245">对其使用 `IntPtr`/`UIntPtr`。</span><span class="sxs-lookup"><span data-stu-id="d6b4e-245">Use `IntPtr`/`UIntPtr` for these.</span></span>

| <span data-ttu-id="d6b4e-246">已签名的指针类型（使用 `IntPtr`）</span><span class="sxs-lookup"><span data-stu-id="d6b4e-246">Signed Pointer Types (use `IntPtr`)</span></span> | <span data-ttu-id="d6b4e-247">未签名的指针类型（使用 `UIntPtr`）</span><span class="sxs-lookup"><span data-stu-id="d6b4e-247">Unsigned Pointer Types (use `UIntPtr`)</span></span> |
|:------------------------------------|:---------------------------------------|
| `HANDLE`                            | `WPARAM`                               |
| `HWND`                              | `UINT_PTR`                             |
| `HINSTANCE`                         | `ULONG_PTR`                            |
| `LPARAM`                            | `SIZE_T`                               |
| `LRESULT`                           |                                        |
| `LONG_PTR`                          |                                        |
| `INT_PTR`                           |                                        |

<span data-ttu-id="d6b4e-248">Windows `PVOID`，这是一个 C `void*`，可以作为 `IntPtr` 或 `UIntPtr` 进行封送，但在可能的情况下更倾向于 `void*`。</span><span class="sxs-lookup"><span data-stu-id="d6b4e-248">A Windows `PVOID` which is a C `void*` can be marshaled as either `IntPtr` or `UIntPtr`, but prefer `void*` when possible.</span></span>

[<span data-ttu-id="d6b4e-249">Windows 数据类型</span><span class="sxs-lookup"><span data-stu-id="d6b4e-249">Windows Data Types</span></span>](/windows/desktop/WinProg/windows-data-types)

[<span data-ttu-id="d6b4e-250">数据类型范围</span><span class="sxs-lookup"><span data-stu-id="d6b4e-250">Data Type Ranges</span></span>](/cpp/cpp/data-type-ranges)

## <a name="structs"></a><span data-ttu-id="d6b4e-251">结构</span><span class="sxs-lookup"><span data-stu-id="d6b4e-251">Structs</span></span>

<span data-ttu-id="d6b4e-252">托管结构是在堆栈上创建的，在返回方法之前不会将其删除。</span><span class="sxs-lookup"><span data-stu-id="d6b4e-252">Managed structs are created on the stack and aren't removed until the method returns.</span></span> <span data-ttu-id="d6b4e-253">按照定义，它们是“固定的”（不会被 GC 移动）。</span><span class="sxs-lookup"><span data-stu-id="d6b4e-253">By definition then, they are "pinned" (it won't get moved by the GC).</span></span> <span data-ttu-id="d6b4e-254">如果本机代码不会在当前方法末尾之外使用指针，则也可以使用不安全代码块中的地址。</span><span class="sxs-lookup"><span data-stu-id="d6b4e-254">You can also simply take the address in unsafe code blocks if native code won't use the pointer past the end of the current method.</span></span>

<span data-ttu-id="d6b4e-255">Blittable 结构的性能更好，因为它们可以由封送层直接使用。</span><span class="sxs-lookup"><span data-stu-id="d6b4e-255">Blittable structs are much more performant as they can simply be used directly by the marshaling layer.</span></span> <span data-ttu-id="d6b4e-256">尝试使结构为 blittable（例如，避免 `bool`）。</span><span class="sxs-lookup"><span data-stu-id="d6b4e-256">Try to make structs blittable (for example, avoid `bool`).</span></span> <span data-ttu-id="d6b4e-257">有关详细信息，请参阅 [Blittable 类型](#blittable-types)部分。</span><span class="sxs-lookup"><span data-stu-id="d6b4e-257">For more information, see the [Blittable Types](#blittable-types) section.</span></span>

<span data-ttu-id="d6b4e-258">如果结构为 blittable，请使用 `sizeof()` 而不是 `Marshal.SizeOf<MyStruct>()`，以获得更好的性能。</span><span class="sxs-lookup"><span data-stu-id="d6b4e-258">*If* the struct is blittable, use `sizeof()` instead of `Marshal.SizeOf<MyStruct>()` for better performance.</span></span> <span data-ttu-id="d6b4e-259">如上所述，可以通过尝试创建固定的 `GCHandle` 来验证该类型是否为 blittable。</span><span class="sxs-lookup"><span data-stu-id="d6b4e-259">As mentioned above, you can validate that the type is blittable by attempting to create a pinned `GCHandle`.</span></span> <span data-ttu-id="d6b4e-260">如果该类型不是字符串或被视为 blittable，则 `GCHandle.Alloc` 将引发 `ArgumentException`。</span><span class="sxs-lookup"><span data-stu-id="d6b4e-260">If the type is not a string or considered blittable, `GCHandle.Alloc` will throw an `ArgumentException`.</span></span>

<span data-ttu-id="d6b4e-261">指向定义中的结构的指针必须通过 `ref` 传递或使用 `unsafe` 和 `*`。</span><span class="sxs-lookup"><span data-stu-id="d6b4e-261">Pointers to structs in definitions must either be passed by `ref` or use `unsafe` and `*`.</span></span>

<span data-ttu-id="d6b4e-262">✔️ 请尽可能将托管结构与官方平台文档或标题中使用的形状和名称匹配。</span><span class="sxs-lookup"><span data-stu-id="d6b4e-262">**✔️ DO** match the managed struct as closely as possible to the shape and names that are used in the official platform documentation or header.</span></span>

<span data-ttu-id="d6b4e-263">✔️ 请务必使用 C# `sizeof()` 而不是 blittable 结构的 `Marshal.SizeOf<MyStruct>()`，以提高性能。</span><span class="sxs-lookup"><span data-stu-id="d6b4e-263">**✔️ DO** use the C# `sizeof()` instead of `Marshal.SizeOf<MyStruct>()` for blittable structures to improve performance.</span></span>

<span data-ttu-id="d6b4e-264">`INT_PTR Reserved1[2]` 等数组必须封送到两个 `IntPtr` 字段（`Reserved1a` 和 `Reserved1b`）。</span><span class="sxs-lookup"><span data-stu-id="d6b4e-264">An array like `INT_PTR Reserved1[2]` has to be marshaled to two `IntPtr` fields, `Reserved1a` and `Reserved1b`.</span></span> <span data-ttu-id="d6b4e-265">当本机数组为基元类型时，可以使用 `fixed` 关键字更明确地进行编写。</span><span class="sxs-lookup"><span data-stu-id="d6b4e-265">When the native array is a primitive type, we can use the `fixed` keyword to write it a little more cleanly.</span></span> <span data-ttu-id="d6b4e-266">例如，`SYSTEM_PROCESS_INFORMATION` 在本机标头中类似如下内容：</span><span class="sxs-lookup"><span data-stu-id="d6b4e-266">For example, `SYSTEM_PROCESS_INFORMATION` looks like this in the native header:</span></span>

```c
typedef struct _SYSTEM_PROCESS_INFORMATION {
    ULONG NextEntryOffset;
    ULONG NumberOfThreads;
    BYTE Reserved1[48];
    UNICODE_STRING ImageName;
...
} SYSTEM_PROCESS_INFORMATION
```

<span data-ttu-id="d6b4e-267">可以在 C# 中编写如下内容：</span><span class="sxs-lookup"><span data-stu-id="d6b4e-267">In C#, we can write it like this:</span></span>

```csharp
internal unsafe struct SYSTEM_PROCESS_INFORMATION
{
    internal uint NextEntryOffset;
    internal uint NumberOfThreads;
    private fixed byte Reserved1[48];
    internal Interop.UNICODE_STRING ImageName;
    ...
}
```

<span data-ttu-id="d6b4e-268">但是，固定的缓冲区有一些问题。</span><span class="sxs-lookup"><span data-stu-id="d6b4e-268">However, there are some gotchas with fixed buffers.</span></span> <span data-ttu-id="d6b4e-269">非 blittable 类型的固定缓冲区不会正确封送，因此，就地数组需要扩大到多个单独字段。</span><span class="sxs-lookup"><span data-stu-id="d6b4e-269">Fixed buffers of non-blittable types won't be correctly marshaled, so the in-place array needs to be expanded out to multiple individual fields.</span></span> <span data-ttu-id="d6b4e-270">此外，在早于 3.0 的 .NET Framework 和 .NET Core 中，如果包含固定缓冲区字段的结构嵌套在非 blittable 结构中，则不会将固定缓冲区字段正确封送到本机代码。</span><span class="sxs-lookup"><span data-stu-id="d6b4e-270">Additionally, in .NET Framework and .NET Core before 3.0, if a struct containing a fixed buffer field is nested within a non-blittable struct, the fixed buffer field won't be correctly marshaled to native code.</span></span>
