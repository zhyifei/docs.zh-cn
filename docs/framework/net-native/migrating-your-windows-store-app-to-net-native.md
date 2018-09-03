---
title: 将 Windows 应用商店应用迁移到 .NET Native
ms.date: 03/30/2017
ms.assetid: 4153aa18-6f56-4a0a-865b-d3da743a1d05
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3909855db109938794fad3e0afc99d492009b81c
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2018
ms.locfileid: "43461782"
---
# <a name="migrating-your-windows-store-app-to-net-native"></a><span data-ttu-id="80736-102">将 Windows 应用商店应用迁移到 .NET Native</span><span class="sxs-lookup"><span data-stu-id="80736-102">Migrating Your Windows Store App to .NET Native</span></span>
<span data-ttu-id="80736-103">.NET 本机提供应用在 Windows 应用商店中或开发人员的计算机上的静态的编译。</span><span class="sxs-lookup"><span data-stu-id="80736-103">.NET Native provides static compilation of apps in the Windows Store or on the developer’s computer.</span></span> <span data-ttu-id="80736-104">这不同于及时生成 (JIT) 编译器或 [本地映像生成器 (Ngen.exe)](../../../docs/framework/tools/ngen-exe-native-image-generator.md) 在该设备上为 Windows 应用商店应用执行的动态编译。</span><span class="sxs-lookup"><span data-stu-id="80736-104">This differs from the dynamic compilation performed for Windows Store apps by the just-in-time (JIT) compiler or the [Native Image Generator (Ngen.exe)](../../../docs/framework/tools/ngen-exe-native-image-generator.md) on the device.</span></span> <span data-ttu-id="80736-105">尽管存在不同，.NET Native 尝试保持与兼容性[.NET for Windows Store 应用](https://msdn.microsoft.com/library/windows/apps/br230302.aspx)。</span><span class="sxs-lookup"><span data-stu-id="80736-105">Despite the differences, .NET Native tries to maintain compatibility with the [.NET for Windows Store apps](https://msdn.microsoft.com/library/windows/apps/br230302.aspx).</span></span> <span data-ttu-id="80736-106">大多数情况下，用于.NET for Windows Store 应用的内容也适用于.NET Native。</span><span class="sxs-lookup"><span data-stu-id="80736-106">For the most part, things that work on the .NET for Windows Store apps also work with .NET Native.</span></span>  <span data-ttu-id="80736-107">然而，在某些情况下，你可能会遇到行为变更。</span><span class="sxs-lookup"><span data-stu-id="80736-107">However, in some cases, you may encounter behavioral changes.</span></span> <span data-ttu-id="80736-108">本文档介绍了以下几个方面之间的标准.NET for Windows Store 应用和.NET Native 的这些差异：</span><span class="sxs-lookup"><span data-stu-id="80736-108">This document discusses these differences between the standard .NET for Windows Store apps and .NET Native in the following areas:</span></span>  
  
-   [<span data-ttu-id="80736-109">常规运行时差异</span><span class="sxs-lookup"><span data-stu-id="80736-109">General runtime differences</span></span>](#Runtime)  
  
-   [<span data-ttu-id="80736-110">动态编程差异</span><span class="sxs-lookup"><span data-stu-id="80736-110">Dynamic programming differences</span></span>](#Dynamic)  
  
-   [<span data-ttu-id="80736-111">其他与反射相关的差异</span><span class="sxs-lookup"><span data-stu-id="80736-111">Other reflection-related differences</span></span>](#Reflection)  
  
-   [<span data-ttu-id="80736-112">不受支持的方案和 API</span><span class="sxs-lookup"><span data-stu-id="80736-112">Unsupported scenarios and APIs</span></span>](#Unsupported)  
  
-   [<span data-ttu-id="80736-113">Visual Studio 差异</span><span class="sxs-lookup"><span data-stu-id="80736-113">Visual Studio differences</span></span>](#VS)  
  
<a name="Runtime"></a>   
## <a name="general-runtime-differences"></a><span data-ttu-id="80736-114">常规运行时差异</span><span class="sxs-lookup"><span data-stu-id="80736-114">General runtime differences</span></span>  
  
-   <span data-ttu-id="80736-115">异常，如<xref:System.TypeLoadException>，所引发的 JIT 编译器的常见应用程序运行时语言运行时 (CLR) 通常会导致编译时错误时由.NET Native 处理。</span><span class="sxs-lookup"><span data-stu-id="80736-115">Exceptions, such as <xref:System.TypeLoadException>, that are thrown by the JIT compiler when an app runs on the common language runtime (CLR) generally result in compile-time errors when processed by .NET Native.</span></span>  
  
-   <span data-ttu-id="80736-116">请勿从一个应用的 UI 线程调用 <xref:System.GC.WaitForPendingFinalizers%2A?displayProperty=nameWithType> 方法。</span><span class="sxs-lookup"><span data-stu-id="80736-116">Don't call the <xref:System.GC.WaitForPendingFinalizers%2A?displayProperty=nameWithType> method from an app's UI thread.</span></span> <span data-ttu-id="80736-117">这可能导致死锁在.NET Native 上。</span><span class="sxs-lookup"><span data-stu-id="80736-117">This can result in a deadlock on .NET Native.</span></span>  
  
-   <span data-ttu-id="80736-118">请勿依赖静态类构造函数调用排序。</span><span class="sxs-lookup"><span data-stu-id="80736-118">Don't rely on static class constructor invocation ordering.</span></span> <span data-ttu-id="80736-119">在.NET Native 的调用顺序是从与标准运行时的顺序不同。</span><span class="sxs-lookup"><span data-stu-id="80736-119">In .NET Native, the invocation order is different from the order on the standard runtime.</span></span> <span data-ttu-id="80736-120">（即使可以使用标准运行时，你也不应依赖静态类构造函数的执行顺序。）</span><span class="sxs-lookup"><span data-stu-id="80736-120">(Even with the standard runtime, you shouldn't rely on the order of execution of static class constructors.)</span></span>  
  
-   <span data-ttu-id="80736-121">不在任何线程上执行调用（例如， `while(true);`）的无线循环可能会使应用异常终止。</span><span class="sxs-lookup"><span data-stu-id="80736-121">Infinite looping without making a call (for example, `while(true);`) on any thread may bring the app to a halt.</span></span> <span data-ttu-id="80736-122">同样，长期或无限等待也可能使应用异常终止。</span><span class="sxs-lookup"><span data-stu-id="80736-122">Similarly, large or infinite waits may bring the app to a halt.</span></span>  
  
-   <span data-ttu-id="80736-123">在.NET Native，某些泛型初始化循环不引发异常。</span><span class="sxs-lookup"><span data-stu-id="80736-123">Certain generic initialization cycles don't throw exceptions in .NET Native.</span></span> <span data-ttu-id="80736-124">例如，以下代码导致标准 CLR 上 <xref:System.TypeLoadException> 发生了一个异常。</span><span class="sxs-lookup"><span data-stu-id="80736-124">For example, the following code throws a <xref:System.TypeLoadException> exception on the standard CLR.</span></span> <span data-ttu-id="80736-125">在.NET Native，它不会。</span><span class="sxs-lookup"><span data-stu-id="80736-125">In .NET Native, it doesn't.</span></span>  
  
     [!code-csharp[ProjectN#8](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/compat1.cs#8)]  
  
-   <span data-ttu-id="80736-126">在某些情况下，.NET 本机提供.NET Framework 类库的不同的实现。</span><span class="sxs-lookup"><span data-stu-id="80736-126">In some cases, .NET Native provides different implementations of .NET Framework class libraries.</span></span> <span data-ttu-id="80736-127">从一个方法返回的对象总是实施返回类型的成员。</span><span class="sxs-lookup"><span data-stu-id="80736-127">An object returned from a method will always implement the members of the returned type.</span></span> <span data-ttu-id="80736-128">然而，由于它的后备实施是不同的，你可能无法像在其他 .NET Framework 平台上的操作一样将其转换到相同的类型集。</span><span class="sxs-lookup"><span data-stu-id="80736-128">However, since its backing implementation is different, you may not be able to cast it to the same set of types as you could on other .NET Framework platforms.</span></span> <span data-ttu-id="80736-129">例如，在某些情况下，你可能无法将 <xref:System.Collections.Generic.IEnumerable%601> 或 <xref:System.Reflection.TypeInfo.DeclaredMembers%2A?displayProperty=nameWithType> 等方法返回的 <xref:System.Reflection.TypeInfo.DeclaredProperties%2A?displayProperty=nameWithType> 界面对象转换为 `T[]`。</span><span class="sxs-lookup"><span data-stu-id="80736-129">For example, in some cases, you may not be able to cast the <xref:System.Collections.Generic.IEnumerable%601> interface object returned by methods such as <xref:System.Reflection.TypeInfo.DeclaredMembers%2A?displayProperty=nameWithType> or <xref:System.Reflection.TypeInfo.DeclaredProperties%2A?displayProperty=nameWithType> to `T[]`.</span></span>  
  
-   <span data-ttu-id="80736-130">WinInet 缓存未启用.NET for Windows Store 应用，默认情况下，但它是在.NET Native 上。</span><span class="sxs-lookup"><span data-stu-id="80736-130">The WinInet cache isn't enabled by default on .NET for Windows Store apps, but it is on .NET Native.</span></span> <span data-ttu-id="80736-131">这提高了性能但会影响工作集。</span><span class="sxs-lookup"><span data-stu-id="80736-131">This improves performance but has working set implications.</span></span> <span data-ttu-id="80736-132">开发者无需执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="80736-132">No developer action is necessary.</span></span>  
  
<a name="Dynamic"></a>   
## <a name="dynamic-programming-differences"></a><span data-ttu-id="80736-133">动态编程差异</span><span class="sxs-lookup"><span data-stu-id="80736-133">Dynamic programming differences</span></span>  
 <span data-ttu-id="80736-134">.NET 本机静态链接在代码中从.NET Framework，才能使应用程序本地的最大性能的代码。</span><span class="sxs-lookup"><span data-stu-id="80736-134">.NET Native statically links in code from the .NET Framework to make the code app-local for maximum performance.</span></span> <span data-ttu-id="80736-135">然而，由于二进制大小必须保持较小，这就使得整个 .NET Framework 无法进入。</span><span class="sxs-lookup"><span data-stu-id="80736-135">However, binary sizes have to remain small, so the entire .NET Framework can't be brought in.</span></span> <span data-ttu-id="80736-136">.NET Native 编译器通过使用将删除对未使用的代码引用的依赖减压器来解决此限制。</span><span class="sxs-lookup"><span data-stu-id="80736-136">The .NET Native compiler resolves this limitation by using a dependency reducer that removes references to unused code.</span></span> <span data-ttu-id="80736-137">但是，.NET Native 可能无法维持或生成某些类型信息和代码时该信息不能在编译时静态推断，但改为在运行时动态检索。</span><span class="sxs-lookup"><span data-stu-id="80736-137">However, .NET Native might not maintain or generate some type information and code when that information can't be inferred statically at compile time, but instead is retrieved dynamically at runtime.</span></span>  
  
 <span data-ttu-id="80736-138">.NET native 可启用反射和动态编程。</span><span class="sxs-lookup"><span data-stu-id="80736-138">.NET Native does enable reflection and dynamic programming.</span></span> <span data-ttu-id="80736-139">然而，并非所有类型都可以标记为反射，因为这会导致生成的代码太大（尤其因为 .NET Framework 中支持反射到公共 API）。</span><span class="sxs-lookup"><span data-stu-id="80736-139">However, not all types can be marked for reflection, because this would make the generated code size too large (especially because reflecting on public APIs in the .NET Framework is supported).</span></span> <span data-ttu-id="80736-140">.NET Native 编译器会明智地选择哪些类型应该支持反射，以及它保存元数据，并仅为这些类型生成代码。</span><span class="sxs-lookup"><span data-stu-id="80736-140">The .NET Native compiler makes smart choices about which types should support reflection, and it keeps the metadata and generates code only for those types.</span></span>  
  
 <span data-ttu-id="80736-141">例如，绑定数据需要一个应用能够将属性名映射到函数。</span><span class="sxs-lookup"><span data-stu-id="80736-141">For example, data binding requires an app to be able to map property names to functions.</span></span> <span data-ttu-id="80736-142">在 Windows 应用商店应用的 .NET 中，公共语言运行时自动使用反射来向托管类型和公开可用的本机类型提供该能力。</span><span class="sxs-lookup"><span data-stu-id="80736-142">In .NET for Windows Store apps, the common language runtime automatically uses reflection to provide this capability for managed types and publicly available native types.</span></span> <span data-ttu-id="80736-143">在.NET Native 编译器会自动包括类型将数据绑定到的元的数据。</span><span class="sxs-lookup"><span data-stu-id="80736-143">In .NET Native, the compiler automatically includes metadata for types to which you bind data.</span></span>  
  
 <span data-ttu-id="80736-144">.NET Native 编译器还可以处理通常使用的泛型类型如<xref:System.Collections.Generic.List%601>和<xref:System.Collections.Generic.Dictionary%602>，该运行时无需任何提示或指令。</span><span class="sxs-lookup"><span data-stu-id="80736-144">The .NET Native compiler can also handle commonly used generic types such as <xref:System.Collections.Generic.List%601> and <xref:System.Collections.Generic.Dictionary%602>, which work without requiring any hints or directives.</span></span> <span data-ttu-id="80736-145">[动态](~/docs/csharp/language-reference/keywords/dynamic.md) 关键字在某些限制内也受到支持。</span><span class="sxs-lookup"><span data-stu-id="80736-145">The [dynamic](~/docs/csharp/language-reference/keywords/dynamic.md) keyword is also supported within certain limits.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="80736-146">将应用移植到.NET Native 时，应全面测试所有动态代码路径。</span><span class="sxs-lookup"><span data-stu-id="80736-146">You should test all dynamic code paths thoroughly when porting your app to .NET Native.</span></span>  
  
 <span data-ttu-id="80736-147">.NET Native 的默认配置足以满足大多数开发人员，但某些开发人员可能想要微调其配置使用运行时指令 (。 rd.xml) 文件。</span><span class="sxs-lookup"><span data-stu-id="80736-147">The default configuration for .NET Native is sufficient for most developers, but some developers might want to fine- tune their configurations by using a runtime directives (.rd.xml) file.</span></span> <span data-ttu-id="80736-148">此外，在某些情况下，.NET Native 编译器不能确定哪些元数据必须是可用于反射，并依赖提示，尤其是在以下情况下：</span><span class="sxs-lookup"><span data-stu-id="80736-148">In addition, in some cases, the .NET Native compiler is unable to determine which metadata must be available for reflection and relies on hints, particularly in the following cases:</span></span>  
  
-   <span data-ttu-id="80736-149"><xref:System.Type.MakeGenericType%2A?displayProperty=nameWithType> 和 <xref:System.Reflection.MethodInfo.MakeGenericMethod%2A?displayProperty=nameWithType> 等一些构造无法静态确定。</span><span class="sxs-lookup"><span data-stu-id="80736-149">Some constructs like <xref:System.Type.MakeGenericType%2A?displayProperty=nameWithType> and <xref:System.Reflection.MethodInfo.MakeGenericMethod%2A?displayProperty=nameWithType> can't be determined statically.</span></span>  
  
-   <span data-ttu-id="80736-150">因为编译器无法确定实例化，因此你想要反射到的泛型类型必须通过运行时指令来指定。</span><span class="sxs-lookup"><span data-stu-id="80736-150">Because the compiler can't determine the instantiations, a generic type that you want to reflect on has to be specified by runtime directives.</span></span> <span data-ttu-id="80736-151">这并不仅是因为所有的代码必须包含在内，还因为在泛型类型上的反射会形成一个无限循环（例如，当某泛型方法在某泛型类型上调用时）。</span><span class="sxs-lookup"><span data-stu-id="80736-151">This isn't just because all code must be included, but because reflection on generic types can form an infinite cycle (for example, when a generic method is invoked on a generic type).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="80736-152">运行时指令是在运行时指令 (.rd.xml) 文件中定义的。</span><span class="sxs-lookup"><span data-stu-id="80736-152">Runtime directives are defined in a runtime directives (.rd.xml) file.</span></span> <span data-ttu-id="80736-153">有关使用此文件的常规信息，请参阅[入门](../../../docs/framework/net-native/getting-started-with-net-native.md)。</span><span class="sxs-lookup"><span data-stu-id="80736-153">For general information about using this file, see [Getting Started](../../../docs/framework/net-native/getting-started-with-net-native.md).</span></span> <span data-ttu-id="80736-154">有关运行时指令的信息，请参阅 [Runtime Directives (rd.xml) Configuration File Reference](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)。</span><span class="sxs-lookup"><span data-stu-id="80736-154">For information about the runtime directives, see [Runtime Directives (rd.xml) Configuration File Reference](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md).</span></span>  
  
 <span data-ttu-id="80736-155">.NET native 还包括分析工具，可帮助开发人员确定默认集合之外哪些类型应支持反射。</span><span class="sxs-lookup"><span data-stu-id="80736-155">.NET Native also includes profiling tools that help the developer determine which types outside the default set should support reflection.</span></span>  
  
<a name="Reflection"></a>   
## <a name="other-reflection-related-differences"></a><span data-ttu-id="80736-156">其他与反射相关的差异</span><span class="sxs-lookup"><span data-stu-id="80736-156">Other reflection-related differences</span></span>  
 <span data-ttu-id="80736-157">有多种其他单独的与反射相关行为差异的适用于 Windows 应用商店应用和.NET Native。</span><span class="sxs-lookup"><span data-stu-id="80736-157">There are a number of other individual reflection-related differences in behavior between the .NET for Windows Store apps and .NET Native.</span></span>  
  
 <span data-ttu-id="80736-158">.NET 本机：</span><span class="sxs-lookup"><span data-stu-id="80736-158">In .NET Native:</span></span>  
  
-   <span data-ttu-id="80736-159">反射到 .NET Framework 类库中的类型和成员的私有反射不受支持。</span><span class="sxs-lookup"><span data-stu-id="80736-159">Private reflection over types and members in the .NET Framework class library is not supported.</span></span> <span data-ttu-id="80736-160">然而，你可以反射到自己的私有类型和成员以及第三方库的类型和成员。</span><span class="sxs-lookup"><span data-stu-id="80736-160">You can, however, reflect over your own private types and members, as well as types and members in third-party libraries.</span></span>  
  
-   <span data-ttu-id="80736-161"><xref:System.Reflection.ParameterInfo.HasDefaultValue%2A?displayProperty=nameWithType> 属性为表示返回值的 `false` 对象正确返回 <xref:System.Reflection.ParameterInfo>。</span><span class="sxs-lookup"><span data-stu-id="80736-161">The <xref:System.Reflection.ParameterInfo.HasDefaultValue%2A?displayProperty=nameWithType> property correctly returns `false` for a <xref:System.Reflection.ParameterInfo> object that represents a return value.</span></span> <span data-ttu-id="80736-162">在 Windows 应用商店应用的 .NET 中，它返回 `true`。</span><span class="sxs-lookup"><span data-stu-id="80736-162">In the .NET for Windows Store apps, it returns `true`.</span></span> <span data-ttu-id="80736-163">中间语言 (IL) 不直接支持此操作，且解释需要由语言来进行。</span><span class="sxs-lookup"><span data-stu-id="80736-163">Intermediate language (IL) doesn’t support this directly, and interpretation is left to the language.</span></span>  
  
-   <span data-ttu-id="80736-164">位于 <xref:System.RuntimeFieldHandle> 和 <xref:System.RuntimeMethodHandle> 结构上的公共成员不受支持。</span><span class="sxs-lookup"><span data-stu-id="80736-164">Public members on the <xref:System.RuntimeFieldHandle> and <xref:System.RuntimeMethodHandle> structures aren't supported.</span></span> <span data-ttu-id="80736-165">这些受到支持的类型仅用于 LINQ、表达式树和静态阵列初始化。</span><span class="sxs-lookup"><span data-stu-id="80736-165">These types are supported only for LINQ, expression trees, and static array initialization.</span></span>  
  
-   <span data-ttu-id="80736-166"><xref:System.Reflection.RuntimeReflectionExtensions.GetRuntimeProperties%2A?displayProperty=nameWithType> 和 <xref:System.Reflection.RuntimeReflectionExtensions.GetRuntimeEvents%2A?displayProperty=nameWithType> 在基类中包含隐藏成员，因此可能会在没有显示重写的情况下遭到重写。</span><span class="sxs-lookup"><span data-stu-id="80736-166"><xref:System.Reflection.RuntimeReflectionExtensions.GetRuntimeProperties%2A?displayProperty=nameWithType> and <xref:System.Reflection.RuntimeReflectionExtensions.GetRuntimeEvents%2A?displayProperty=nameWithType> include hidden members in base classes and thus may be overridden without explicit overrides.</span></span> <span data-ttu-id="80736-167">这也是如此的其他[runtimereflectionextensions.getruntime \*](https://msdn.microsoft.com/library/system.reflection.runtimereflectionextensions_methods.aspx)方法。</span><span class="sxs-lookup"><span data-stu-id="80736-167">This is also true of other [RuntimeReflectionExtensions.GetRuntime\*](https://msdn.microsoft.com/library/system.reflection.runtimereflectionextensions_methods.aspx) methods.</span></span>  
  
-   <span data-ttu-id="80736-168"><xref:System.Type.MakeArrayType%2A?displayProperty=nameWithType> 和 <xref:System.Type.MakeByRefType%2A?displayProperty=nameWithType> 在你试图创建特定组合（例如，ByRef 阵列）时不会发生故障。</span><span class="sxs-lookup"><span data-stu-id="80736-168"><xref:System.Type.MakeArrayType%2A?displayProperty=nameWithType> and <xref:System.Type.MakeByRefType%2A?displayProperty=nameWithType> don't fail when you try to create certain combinations (for example, an array of byrefs).</span></span>  
  
-   <span data-ttu-id="80736-169">你无法使用反射来调用具有指针参数的成员。</span><span class="sxs-lookup"><span data-stu-id="80736-169">You can't use reflection to invoke members that have pointer parameters.</span></span>  
  
-   <span data-ttu-id="80736-170">你无法使用反射来获取或设置一个指针字段。</span><span class="sxs-lookup"><span data-stu-id="80736-170">You can't use reflection to get or set a pointer field.</span></span>  
  
-   <span data-ttu-id="80736-171">当参数计数错误并且其中一个参数的类型不正确时，.NET Native 将引发<xref:System.ArgumentException>而不是<xref:System.Reflection.TargetParameterCountException>。</span><span class="sxs-lookup"><span data-stu-id="80736-171">When the argument count is wrong and the type of one of the arguments is incorrect, .NET Native throws an <xref:System.ArgumentException> instead of a <xref:System.Reflection.TargetParameterCountException>.</span></span>  
  
-   <span data-ttu-id="80736-172">异常的二进制序列化通常不受支持。</span><span class="sxs-lookup"><span data-stu-id="80736-172">Binary serialization of exceptions is generally not supported.</span></span> <span data-ttu-id="80736-173">因此，不可序列化的对象可添加到 <xref:System.Exception.Data%2A?displayProperty=nameWithType> 字典。</span><span class="sxs-lookup"><span data-stu-id="80736-173">As a result, non-serializable objects can be added to the <xref:System.Exception.Data%2A?displayProperty=nameWithType> dictionary.</span></span>  
  
<a name="Unsupported"></a>   
## <a name="unsupported-scenarios-and-apis"></a><span data-ttu-id="80736-174">不受支持的方案和 API</span><span class="sxs-lookup"><span data-stu-id="80736-174">Unsupported scenarios and APIs</span></span>  
 <span data-ttu-id="80736-175">以下部分列出了不受一般开发支持的方案和 API、互操作以及 HTTPClient 和 Windows Communication Foundation (WCF) 等技术：</span><span class="sxs-lookup"><span data-stu-id="80736-175">The following sections list unsupported scenarios and APIs for general development, interop, and technologies such as HTTPClient and Windows Communication Foundation (WCF):</span></span>  
  
-   [<span data-ttu-id="80736-176">常规开发</span><span class="sxs-lookup"><span data-stu-id="80736-176">General development</span></span>](#General)  
  
-   [<span data-ttu-id="80736-177">HttpClient</span><span class="sxs-lookup"><span data-stu-id="80736-177">HttpClient</span></span>](#HttpClient)  
  
-   [<span data-ttu-id="80736-178">Interop</span><span class="sxs-lookup"><span data-stu-id="80736-178">Interop</span></span>](#Interop)  
  
-   [<span data-ttu-id="80736-179">不受支持的 API</span><span class="sxs-lookup"><span data-stu-id="80736-179">Unsupported APIs</span></span>](#APIs)  
  
<a name="General"></a>   
### <a name="general-development-differences"></a><span data-ttu-id="80736-180">常规开发差异</span><span class="sxs-lookup"><span data-stu-id="80736-180">General development differences</span></span>  
 <span data-ttu-id="80736-181">**值类型**</span><span class="sxs-lookup"><span data-stu-id="80736-181">**Value types**</span></span>  
  
-   <span data-ttu-id="80736-182">如果你替代了一个值类型的 <xref:System.ValueType.Equals%2A?displayProperty=nameWithType> 和 <xref:System.ValueType.GetHashCode%2A?displayProperty=nameWithType> 方法，请勿调用基类实施。</span><span class="sxs-lookup"><span data-stu-id="80736-182">If you override the <xref:System.ValueType.Equals%2A?displayProperty=nameWithType> and <xref:System.ValueType.GetHashCode%2A?displayProperty=nameWithType> methods for a value type, don't call the base class implementations.</span></span> <span data-ttu-id="80736-183">在 Windows 应用商店应用的 .NET 中，这些方法依赖反射。</span><span class="sxs-lookup"><span data-stu-id="80736-183">In .NET for Windows Store apps, these methods rely on reflection.</span></span> <span data-ttu-id="80736-184">在编译时，.NET Native 生成不依赖于运行时反射的实现。</span><span class="sxs-lookup"><span data-stu-id="80736-184">At compile time, .NET Native generates an implementation that doesn't rely on runtime reflection.</span></span> <span data-ttu-id="80736-185">这意味着，如果不替代这两种方法，它们将按预期方式工作，因为.NET Native 生成在编译时实现。</span><span class="sxs-lookup"><span data-stu-id="80736-185">This means that if you don't override these two methods, they will work as expected, because .NET Native generates the implementation at compile time.</span></span> <span data-ttu-id="80736-186">然而，替代这些方法并调用基类实施会产生一个异常。</span><span class="sxs-lookup"><span data-stu-id="80736-186">However, overriding these methods but calling the base class implementation results in an exception.</span></span>  
  
-   <span data-ttu-id="80736-187">大于 1 MB 的值类型不受支持。</span><span class="sxs-lookup"><span data-stu-id="80736-187">Value types larger than one megabyte aren't supported.</span></span>  
  
-   <span data-ttu-id="80736-188">在.NET Native，值类型不能具有默认构造函数。</span><span class="sxs-lookup"><span data-stu-id="80736-188">Value types can't have a default constructor in .NET Native.</span></span> <span data-ttu-id="80736-189">（C# 和 Visual Basic 禁止值类型拥有默认构造函数。</span><span class="sxs-lookup"><span data-stu-id="80736-189">(C# and Visual Basic prohibit default constructors on value types.</span></span> <span data-ttu-id="80736-190">然而，这些可以在 IL 中进行创建。）</span><span class="sxs-lookup"><span data-stu-id="80736-190">However, these can be created in IL.)</span></span>  
  
 <span data-ttu-id="80736-191">**数组**</span><span class="sxs-lookup"><span data-stu-id="80736-191">**Arrays**</span></span>  
  
-   <span data-ttu-id="80736-192">界限低于零的阵列不受支持。</span><span class="sxs-lookup"><span data-stu-id="80736-192">Arrays with a lower bound other than zero aren't supported.</span></span> <span data-ttu-id="80736-193">通常，这些阵列是通过调用 <xref:System.Array.CreateInstance%28System.Type%2CSystem.Int32%5B%5D%2CSystem.Int32%5B%5D%29?displayProperty=nameWithType> 重载来创建的。</span><span class="sxs-lookup"><span data-stu-id="80736-193">Typically, these arrays are created by calling the <xref:System.Array.CreateInstance%28System.Type%2CSystem.Int32%5B%5D%2CSystem.Int32%5B%5D%29?displayProperty=nameWithType> overload.</span></span>  
  
-   <span data-ttu-id="80736-194">不支持动态创建多维阵列。</span><span class="sxs-lookup"><span data-stu-id="80736-194">Dynamic creation of multidimensional arrays isn't supported.</span></span> <span data-ttu-id="80736-195">此类阵列一般是通过调用包括 <xref:System.Array.CreateInstance%2A?displayProperty=nameWithType> 参数的 `lengths` 方法重载来创建，或通过调用 <xref:System.Type.MakeArrayType%28System.Int32%29?displayProperty=nameWithType> 方法来创建。</span><span class="sxs-lookup"><span data-stu-id="80736-195">Such arrays are typically created by calling an overload of the <xref:System.Array.CreateInstance%2A?displayProperty=nameWithType> method that includes a `lengths` parameter, or by calling the <xref:System.Type.MakeArrayType%28System.Int32%29?displayProperty=nameWithType> method.</span></span>  
  
-   <span data-ttu-id="80736-196">四维或更多维的多维阵列不受支持；因为它们的 <xref:System.Array.Rank%2A?displayProperty=nameWithType> 属性值是四或者更大。</span><span class="sxs-lookup"><span data-stu-id="80736-196">Multidimensional arrays that have four or more dimensions aren't supported; that is, their <xref:System.Array.Rank%2A?displayProperty=nameWithType> property value is four or greater.</span></span> <span data-ttu-id="80736-197">可使用 [交错阵列](~/docs/csharp/programming-guide/arrays/jagged-arrays.md) （阵列的阵列）。</span><span class="sxs-lookup"><span data-stu-id="80736-197">Use [jagged arrays](~/docs/csharp/programming-guide/arrays/jagged-arrays.md) (an array of arrays) instead.</span></span> <span data-ttu-id="80736-198">例如， `array[x,y,z]` 无效，但 `array[x][y][z]` 有效。</span><span class="sxs-lookup"><span data-stu-id="80736-198">For example, `array[x,y,z]` is invalid, but `array[x][y][z]` isn't.</span></span>  
  
-   <span data-ttu-id="80736-199">多维阵列的差异不受支持且会在运行时导致 <xref:System.InvalidCastException> 异常。</span><span class="sxs-lookup"><span data-stu-id="80736-199">Variance for multidimensional arrays isn't supported and causes an <xref:System.InvalidCastException> exception at run time.</span></span>  
  
 <span data-ttu-id="80736-200">**泛型**</span><span class="sxs-lookup"><span data-stu-id="80736-200">**Generics**</span></span>  
  
-   <span data-ttu-id="80736-201">无限泛型类型扩展会导致编译器错误。</span><span class="sxs-lookup"><span data-stu-id="80736-201">Infinite generic type expansion results in a compiler error.</span></span> <span data-ttu-id="80736-202">例如，该代码无法编译：</span><span class="sxs-lookup"><span data-stu-id="80736-202">For example, this code fails to compile:</span></span>  
  
     [!code-csharp[ProjectN#9](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/compat2.cs#9)]  
  
 <span data-ttu-id="80736-203">**指针**</span><span class="sxs-lookup"><span data-stu-id="80736-203">**Pointers**</span></span>  
  
-   <span data-ttu-id="80736-204">指针阵列不受支持。</span><span class="sxs-lookup"><span data-stu-id="80736-204">Arrays of pointers aren't supported.</span></span>  
  
-   <span data-ttu-id="80736-205">你无法使用反射来获取或设置一个指针字段。</span><span class="sxs-lookup"><span data-stu-id="80736-205">You can't use reflection to get or set a pointer field.</span></span>  
  
 <span data-ttu-id="80736-206">**序列化**</span><span class="sxs-lookup"><span data-stu-id="80736-206">**Serialization**</span></span>  
  
 <span data-ttu-id="80736-207"><xref:System.Runtime.Serialization.KnownTypeAttribute.%23ctor%28System.String%29> 特性不受支持。</span><span class="sxs-lookup"><span data-stu-id="80736-207">The <xref:System.Runtime.Serialization.KnownTypeAttribute.%23ctor%28System.String%29> attribute isn't supported.</span></span> <span data-ttu-id="80736-208">使用 <xref:System.Runtime.Serialization.KnownTypeAttribute.%23ctor%28System.Type%29> 特性。</span><span class="sxs-lookup"><span data-stu-id="80736-208">Use the <xref:System.Runtime.Serialization.KnownTypeAttribute.%23ctor%28System.Type%29> attribute instead.</span></span>  
  
 <span data-ttu-id="80736-209">**资源**</span><span class="sxs-lookup"><span data-stu-id="80736-209">**Resources**</span></span>  
  
 <span data-ttu-id="80736-210">不支持使用带 <xref:System.Diagnostics.Tracing.EventSource> 类的本地化资源。</span><span class="sxs-lookup"><span data-stu-id="80736-210">The use of localized resources with the <xref:System.Diagnostics.Tracing.EventSource> class isn't supported.</span></span> <span data-ttu-id="80736-211"><xref:System.Diagnostics.Tracing.EventSourceAttribute.LocalizationResources%2A?displayProperty=nameWithType> 属性无法定义本地化资源。</span><span class="sxs-lookup"><span data-stu-id="80736-211">The <xref:System.Diagnostics.Tracing.EventSourceAttribute.LocalizationResources%2A?displayProperty=nameWithType> property doesn't define localized resources.</span></span>  
  
 <span data-ttu-id="80736-212">**委托**</span><span class="sxs-lookup"><span data-stu-id="80736-212">**Delegates**</span></span>  
  
 <span data-ttu-id="80736-213">`Delegate.BeginInvoke` 和 `Delegate.EndInvoke` 不受支持。</span><span class="sxs-lookup"><span data-stu-id="80736-213">`Delegate.BeginInvoke` and `Delegate.EndInvoke` aren't supported.</span></span>  
  
 <span data-ttu-id="80736-214">**其他 API**</span><span class="sxs-lookup"><span data-stu-id="80736-214">**Miscellaneous APIs**</span></span>  
  
-   <span data-ttu-id="80736-215">如果 <xref:System.Reflection.TypeInfo.GUID%2A?displayProperty=nameWithType> 特性未应用于类型，<xref:System.PlatformNotSupportedException> 属性就会导致 <xref:System.Runtime.InteropServices.GuidAttribute> 异常。</span><span class="sxs-lookup"><span data-stu-id="80736-215">The <xref:System.Reflection.TypeInfo.GUID%2A?displayProperty=nameWithType> property throws a <xref:System.PlatformNotSupportedException> exception if a <xref:System.Runtime.InteropServices.GuidAttribute> attribute isn't applied to the type.</span></span> <span data-ttu-id="80736-216">GUID 主要用于 COM 支持。</span><span class="sxs-lookup"><span data-stu-id="80736-216">The GUID is used primarily for COM support.</span></span>  
  
-   <span data-ttu-id="80736-217"><xref:System.DateTime.Parse%2A?displayProperty=nameWithType>方法会正确解析包含在.NET Native 的短日期的字符串。</span><span class="sxs-lookup"><span data-stu-id="80736-217">The <xref:System.DateTime.Parse%2A?displayProperty=nameWithType> method correctly parses strings that contain short dates in .NET Native.</span></span> <span data-ttu-id="80736-218">但是，它不会继续兼容性的更改日期和时间来分析在 Microsoft 知识库文章中所述[KB2803771](https://support.microsoft.com/kb/2803771)并[KB2803755](https://support.microsoft.com/kb/2803755)。</span><span class="sxs-lookup"><span data-stu-id="80736-218">However, it doesn't maintain compatibility with the changes in date and time parsing described in the Microsoft Knowledge Base articles [KB2803771](https://support.microsoft.com/kb/2803771) and [KB2803755](https://support.microsoft.com/kb/2803755).</span></span>  
  
-   <span data-ttu-id="80736-219"><xref:System.Numerics.BigInteger.ToString%2A?displayProperty=nameWithType> `("E")` 正确舍入中.NET Native。</span><span class="sxs-lookup"><span data-stu-id="80736-219"><xref:System.Numerics.BigInteger.ToString%2A?displayProperty=nameWithType> `("E")` is correctly rounded in .NET Native.</span></span> <span data-ttu-id="80736-220">在某些版本的 CLR 中，结果字符串会缩短，而不是舍入。</span><span class="sxs-lookup"><span data-stu-id="80736-220">In some versions of the CLR, the result string is truncated instead of rounded.</span></span>  
  
<a name="HttpClient"></a>   
### <a name="httpclient-differences"></a><span data-ttu-id="80736-221">HttpClient 差异</span><span class="sxs-lookup"><span data-stu-id="80736-221">HttpClient differences</span></span>  
 <span data-ttu-id="80736-222">在.NET Native<xref:System.Net.Http.HttpClientHandler>类在内部使用 WinINet (通过[HttpBaseProtocolFilter](https://msdn.microsoft.com/library/windows/apps/windows.web.http.filters.httpbaseprotocolfilter.aspx)类) 而不是<xref:System.Net.WebRequest>和<xref:System.Net.WebResponse>标准.NET for Windows Store 应用中使用的类。</span><span class="sxs-lookup"><span data-stu-id="80736-222">In .NET Native, the <xref:System.Net.Http.HttpClientHandler> class internally uses WinINet (through the [HttpBaseProtocolFilter](https://msdn.microsoft.com/library/windows/apps/windows.web.http.filters.httpbaseprotocolfilter.aspx) class) instead of the <xref:System.Net.WebRequest> and <xref:System.Net.WebResponse> classes used in the standard .NET for Windows Store apps.</span></span>  <span data-ttu-id="80736-223">WinINet 并不支持 <xref:System.Net.Http.HttpClientHandler> 类支持的所有配置选项。</span><span class="sxs-lookup"><span data-stu-id="80736-223">WinINet doesn't support all the configuration options that the <xref:System.Net.Http.HttpClientHandler> class supports.</span></span>  <span data-ttu-id="80736-224">因此：</span><span class="sxs-lookup"><span data-stu-id="80736-224">As a result:</span></span>  
  
-   <span data-ttu-id="80736-225">某些能力属性在<xref:System.Net.Http.HttpClientHandler>返回`false`有关.NET Native，而它们返回`true`标准.NET for Windows Store 应用中。</span><span class="sxs-lookup"><span data-stu-id="80736-225">Some of the capability properties on <xref:System.Net.Http.HttpClientHandler> return `false` on .NET Native, whereas they return `true` in the standard .NET for Windows Store apps.</span></span>  
  
-   <span data-ttu-id="80736-226">某些配置属性`get`上.NET Native 不同于.NET 的 Windows 应用商店应用中的默认可配置值的访问器都始终返回固定的值。</span><span class="sxs-lookup"><span data-stu-id="80736-226">Some of the configuration property `get` accessors always return a fixed value on .NET Native that is different than the default configurable value in .NET for Windows Store apps.</span></span>  
  
 <span data-ttu-id="80736-227">某些额外的行为差异涵盖在以下子节中。</span><span class="sxs-lookup"><span data-stu-id="80736-227">Some additional behavior differences are covered in the following subsections.</span></span>  
  
 <span data-ttu-id="80736-228">**代理**</span><span class="sxs-lookup"><span data-stu-id="80736-228">**Proxy**</span></span>  
  
 <span data-ttu-id="80736-229">[HttpBaseProtocolFilter](https://msdn.microsoft.com/library/windows/apps/windows.web.http.filters.httpbaseprotocolfilter.aspx)类不支持配置或重写基于每个请求的代理。</span><span class="sxs-lookup"><span data-stu-id="80736-229">The [HttpBaseProtocolFilter](https://msdn.microsoft.com/library/windows/apps/windows.web.http.filters.httpbaseprotocolfilter.aspx) class doesn’t support configuring or overriding the proxy on a per-request basis.</span></span>  <span data-ttu-id="80736-230">这意味着.NET Native 上的所有请求都使用的系统配置的代理服务器或未使用代理服务器，具体取决于值<xref:System.Net.Http.HttpClientHandler.UseProxy%2A?displayProperty=nameWithType>属性。</span><span class="sxs-lookup"><span data-stu-id="80736-230">This means that all requests on .NET Native use the system-configured proxy server or no proxy server, depending on the value of the <xref:System.Net.Http.HttpClientHandler.UseProxy%2A?displayProperty=nameWithType> property.</span></span>  <span data-ttu-id="80736-231">在 Windows 应用商店应用的 .NET 中，代理服务器由 <xref:System.Net.Http.HttpClientHandler.Proxy%2A?displayProperty=nameWithType> 属性定义。</span><span class="sxs-lookup"><span data-stu-id="80736-231">In .NET for Windows Store apps, the proxy server is defined by the <xref:System.Net.Http.HttpClientHandler.Proxy%2A?displayProperty=nameWithType> property.</span></span>  <span data-ttu-id="80736-232">有关.NET Native，设置<xref:System.Net.Http.HttpClientHandler.Proxy%2A?displayProperty=nameWithType>以外的值为`null`引发<xref:System.PlatformNotSupportedException>异常。</span><span class="sxs-lookup"><span data-stu-id="80736-232">On .NET Native, setting the <xref:System.Net.Http.HttpClientHandler.Proxy%2A?displayProperty=nameWithType> to a value other than `null` throws a <xref:System.PlatformNotSupportedException> exception.</span></span>  <span data-ttu-id="80736-233"><xref:System.Net.Http.HttpClientHandler.SupportsProxy%2A?displayProperty=nameWithType>属性返回`false`有关.NET Native，而它返回`true`标准的.NET Framework for Windows Store 应用中。</span><span class="sxs-lookup"><span data-stu-id="80736-233">The <xref:System.Net.Http.HttpClientHandler.SupportsProxy%2A?displayProperty=nameWithType> property returns `false` on .NET Native, whereas it returns `true` in the standard .NET Framework for Windows Store apps.</span></span>  
  
 <span data-ttu-id="80736-234">**自动重定向**</span><span class="sxs-lookup"><span data-stu-id="80736-234">**Automatic redirection**</span></span>  
  
 <span data-ttu-id="80736-235">[HttpBaseProtocolFilter](https://msdn.microsoft.com/library/windows/apps/windows.web.http.filters.httpbaseprotocolfilter.aspx)类不允许配置自动重新定向的最大数目。</span><span class="sxs-lookup"><span data-stu-id="80736-235">The [HttpBaseProtocolFilter](https://msdn.microsoft.com/library/windows/apps/windows.web.http.filters.httpbaseprotocolfilter.aspx) class doesn't allow the maximum number of automatic redirections to be configured.</span></span>  <span data-ttu-id="80736-236">Windows 应用商店应用的标准 .NET 中 <xref:System.Net.Http.HttpClientHandler.MaxAutomaticRedirections%2A?displayProperty=nameWithType> 属性的值默认为 50，且可修改。</span><span class="sxs-lookup"><span data-stu-id="80736-236">The value of the <xref:System.Net.Http.HttpClientHandler.MaxAutomaticRedirections%2A?displayProperty=nameWithType> property is 50 by default in the standard .NET for Windows Store apps and can be modified.</span></span> <span data-ttu-id="80736-237">有关.NET Native，此属性的值为 10，若要对其进行修改，则会引发<xref:System.PlatformNotSupportedException>异常。</span><span class="sxs-lookup"><span data-stu-id="80736-237">On .NET Native, the value of this property is 10, and trying to modify it throws a <xref:System.PlatformNotSupportedException> exception.</span></span>  <span data-ttu-id="80736-238"><xref:System.Net.Http.HttpClientHandler.SupportsRedirectConfiguration%2A?displayProperty=nameWithType>属性返回`false`有关.NET Native，而它返回`true`.NET for Windows Store 应用中。</span><span class="sxs-lookup"><span data-stu-id="80736-238">The <xref:System.Net.Http.HttpClientHandler.SupportsRedirectConfiguration%2A?displayProperty=nameWithType> property returns `false` on .NET Native, whereas it returns `true` in .NET for Windows Store apps.</span></span>  
  
 <span data-ttu-id="80736-239">**自动解压缩**</span><span class="sxs-lookup"><span data-stu-id="80736-239">**Automatic decompression**</span></span>  
  
 <span data-ttu-id="80736-240">Windows 应用商店应用的 .NET 支持将 <xref:System.Net.Http.HttpClientHandler.AutomaticDecompression%2A?displayProperty=nameWithType> 属性设置为 <xref:System.Net.DecompressionMethods.Deflate>、<xref:System.Net.DecompressionMethods.GZip>（<xref:System.Net.DecompressionMethods.Deflate> 和 <xref:System.Net.DecompressionMethods.GZip> 都可以）或 <xref:System.Net.DecompressionMethods.None>。</span><span class="sxs-lookup"><span data-stu-id="80736-240">.NET for Windows Store apps allows you to set the <xref:System.Net.Http.HttpClientHandler.AutomaticDecompression%2A?displayProperty=nameWithType> property to <xref:System.Net.DecompressionMethods.Deflate>, <xref:System.Net.DecompressionMethods.GZip>, both <xref:System.Net.DecompressionMethods.Deflate> and <xref:System.Net.DecompressionMethods.GZip>, or <xref:System.Net.DecompressionMethods.None>.</span></span>  <span data-ttu-id="80736-241">.NET 本机仅支持<xref:System.Net.DecompressionMethods.Deflate>连同<xref:System.Net.DecompressionMethods.GZip>，或<xref:System.Net.DecompressionMethods.None>。</span><span class="sxs-lookup"><span data-stu-id="80736-241">.NET Native only supports <xref:System.Net.DecompressionMethods.Deflate> together with <xref:System.Net.DecompressionMethods.GZip>, or <xref:System.Net.DecompressionMethods.None>.</span></span>  <span data-ttu-id="80736-242">尝试仅将 <xref:System.Net.Http.HttpClientHandler.AutomaticDecompression%2A> 属性设置为 <xref:System.Net.DecompressionMethods.Deflate> 或 <xref:System.Net.DecompressionMethods.GZip> 会自动将其设置为 <xref:System.Net.DecompressionMethods.Deflate> 和 <xref:System.Net.DecompressionMethods.GZip>。</span><span class="sxs-lookup"><span data-stu-id="80736-242">Trying to set the <xref:System.Net.Http.HttpClientHandler.AutomaticDecompression%2A> property to either <xref:System.Net.DecompressionMethods.Deflate> or <xref:System.Net.DecompressionMethods.GZip> alone silently sets it to both <xref:System.Net.DecompressionMethods.Deflate> and <xref:System.Net.DecompressionMethods.GZip>.</span></span>  
  
 <span data-ttu-id="80736-243">**Cookie**</span><span class="sxs-lookup"><span data-stu-id="80736-243">**Cookies**</span></span>  
  
 <span data-ttu-id="80736-244">Cookie 处理由 <xref:System.Net.Http.HttpClient> 和 WinINet 同时执行。</span><span class="sxs-lookup"><span data-stu-id="80736-244">Cookie handling is performed simultaneously by <xref:System.Net.Http.HttpClient> and WinINet.</span></span>  <span data-ttu-id="80736-245">来自 <xref:System.Net.CookieContainer> 的 Cookies 与 WinINet cookie 缓存结合。</span><span class="sxs-lookup"><span data-stu-id="80736-245">Cookies from the <xref:System.Net.CookieContainer> are combined with cookies in the WinINet cookie cache.</span></span>  <span data-ttu-id="80736-246">从 <xref:System.Net.CookieContainer> 删除 cookie 可防止 <xref:System.Net.Http.HttpClient> 发送 cookie，但如果 cookie 已被 WinINet 检测到且 cookies 未被用户删除，则 WinINet 将会发送 cookie。</span><span class="sxs-lookup"><span data-stu-id="80736-246">Removing a cookie from <xref:System.Net.CookieContainer> prevents <xref:System.Net.Http.HttpClient> from sending the cookie, but if the cookie was already seen by WinINet, and cookies weren't deleted by the user, WinINet sends it.</span></span>  <span data-ttu-id="80736-247">无法通过编程的方式使用 <xref:System.Net.Http.HttpClient>、 <xref:System.Net.Http.HttpClientHandler>或 <xref:System.Net.CookieContainer> API 从 WinINet 中删除 cookie。</span><span class="sxs-lookup"><span data-stu-id="80736-247">It isn't possible to programmatically remove a cookie from WinINet by using the <xref:System.Net.Http.HttpClient>, <xref:System.Net.Http.HttpClientHandler>, or <xref:System.Net.CookieContainer> API.</span></span>  <span data-ttu-id="80736-248">将 <xref:System.Net.Http.HttpClientHandler.UseCookies%2A?displayProperty=nameWithType> 属性设置为 `false` 只会导致 <xref:System.Net.Http.HttpClient> 停止发送 cookies；WinINet 仍可能会在请求中包括 cookies。</span><span class="sxs-lookup"><span data-stu-id="80736-248">Setting the <xref:System.Net.Http.HttpClientHandler.UseCookies%2A?displayProperty=nameWithType> property to `false` causes only <xref:System.Net.Http.HttpClient> to stop sending cookies; WinINet might still include its cookies in the request.</span></span>  
  
 <span data-ttu-id="80736-249">**凭据**</span><span class="sxs-lookup"><span data-stu-id="80736-249">**Credentials**</span></span>  
  
 <span data-ttu-id="80736-250">在 Windows 应用商店应用的 .NET 中，<xref:System.Net.Http.HttpClientHandler.UseDefaultCredentials%2A?displayProperty=nameWithType> 和 <xref:System.Net.Http.HttpClientHandler.Credentials%2A?displayProperty=nameWithType> 属性独立工作。</span><span class="sxs-lookup"><span data-stu-id="80736-250">In .NET for Windows Store apps, the <xref:System.Net.Http.HttpClientHandler.UseDefaultCredentials%2A?displayProperty=nameWithType> and <xref:System.Net.Http.HttpClientHandler.Credentials%2A?displayProperty=nameWithType> properties work independently.</span></span>  <span data-ttu-id="80736-251">此外， <xref:System.Net.Http.HttpClientHandler.Credentials%2A> 属性接受实施 <xref:System.Net.ICredentials> 接口的任意对象。</span><span class="sxs-lookup"><span data-stu-id="80736-251">Additionally, the <xref:System.Net.Http.HttpClientHandler.Credentials%2A> property accepts any object that implements the <xref:System.Net.ICredentials> interface.</span></span>  <span data-ttu-id="80736-252">在.NET Native，设置<xref:System.Net.Http.HttpClientHandler.UseDefaultCredentials%2A>属性设置为`true`会导致<xref:System.Net.Http.HttpClientHandler.Credentials%2A>属性是否变为`null`。</span><span class="sxs-lookup"><span data-stu-id="80736-252">In .NET Native, setting the <xref:System.Net.Http.HttpClientHandler.UseDefaultCredentials%2A> property to `true` causes the <xref:System.Net.Http.HttpClientHandler.Credentials%2A> property to become `null`.</span></span>  <span data-ttu-id="80736-253">此外， <xref:System.Net.Http.HttpClientHandler.Credentials%2A> 属性只能设置为 `null`、 <xref:System.Net.CredentialCache.DefaultCredentials%2A>或类型 <xref:System.Net.NetworkCredential>的对象。</span><span class="sxs-lookup"><span data-stu-id="80736-253">In addition, the <xref:System.Net.Http.HttpClientHandler.Credentials%2A> property can be set only to `null`, <xref:System.Net.CredentialCache.DefaultCredentials%2A>, or an object of type <xref:System.Net.NetworkCredential>.</span></span>  <span data-ttu-id="80736-254">将其他任意 <xref:System.Net.ICredentials> 对象（其中最常见的是 <xref:System.Net.CredentialCache>）分配至 <xref:System.Net.Http.HttpClientHandler.Credentials%2A> 属性都会导致 <xref:System.PlatformNotSupportedException>。</span><span class="sxs-lookup"><span data-stu-id="80736-254">Assigning any other <xref:System.Net.ICredentials> object, the most popular of which is <xref:System.Net.CredentialCache>, to the <xref:System.Net.Http.HttpClientHandler.Credentials%2A> property throws a <xref:System.PlatformNotSupportedException>.</span></span>  
  
 <span data-ttu-id="80736-255">**其他不受支持或不可配置的功能**</span><span class="sxs-lookup"><span data-stu-id="80736-255">**Other unsupported or unconfigurable features**</span></span>  
  
 <span data-ttu-id="80736-256">.NET 本机：</span><span class="sxs-lookup"><span data-stu-id="80736-256">In .NET Native:</span></span>  
  
-   <span data-ttu-id="80736-257"><xref:System.Net.Http.HttpClientHandler.ClientCertificateOptions%2A?displayProperty=nameWithType> 属性的值始终为 <xref:System.Net.Http.ClientCertificateOption.Automatic>。</span><span class="sxs-lookup"><span data-stu-id="80736-257">The value of the <xref:System.Net.Http.HttpClientHandler.ClientCertificateOptions%2A?displayProperty=nameWithType> property is always <xref:System.Net.Http.ClientCertificateOption.Automatic>.</span></span>  <span data-ttu-id="80736-258">在 Windows 应用商店应用的 .NET 中，默认为 <xref:System.Net.Http.ClientCertificateOption.Manual>。</span><span class="sxs-lookup"><span data-stu-id="80736-258">In .NET for Windows Store apps, the default is <xref:System.Net.Http.ClientCertificateOption.Manual>.</span></span>  
  
-   <span data-ttu-id="80736-259"><xref:System.Net.Http.HttpClientHandler.MaxRequestContentBufferSize%2A?displayProperty=nameWithType> 属性无法配置。</span><span class="sxs-lookup"><span data-stu-id="80736-259">The <xref:System.Net.Http.HttpClientHandler.MaxRequestContentBufferSize%2A?displayProperty=nameWithType> property isn't configurable.</span></span>  
  
-   <span data-ttu-id="80736-260"><xref:System.Net.Http.HttpClientHandler.PreAuthenticate%2A?displayProperty=nameWithType> 属性始终为 `true`。</span><span class="sxs-lookup"><span data-stu-id="80736-260">The <xref:System.Net.Http.HttpClientHandler.PreAuthenticate%2A?displayProperty=nameWithType> property is always `true`.</span></span>  <span data-ttu-id="80736-261">在 Windows 应用商店应用的 .NET 中，默认为 `false`。</span><span class="sxs-lookup"><span data-stu-id="80736-261">In .NET for Windows Store apps, the default is `false`.</span></span>  
  
-   <span data-ttu-id="80736-262">响应中的 `SetCookie2` 标题忽略为废弃。</span><span class="sxs-lookup"><span data-stu-id="80736-262">The `SetCookie2` header in responses is ignored as obsolete.</span></span>  
  
<a name="Interop"></a>   
### <a name="interop-differences"></a><span data-ttu-id="80736-263">互操作差异性</span><span class="sxs-lookup"><span data-stu-id="80736-263">Interop differences</span></span>  
 <span data-ttu-id="80736-264">**弃用的 API**</span><span class="sxs-lookup"><span data-stu-id="80736-264">**Deprecated APIs**</span></span>  
  
 <span data-ttu-id="80736-265">多个带有托管代码的不常使用的互操作性 API 已弃用。</span><span class="sxs-lookup"><span data-stu-id="80736-265">A number of infrequently used APIs for interoperability with managed code have been deprecated.</span></span> <span data-ttu-id="80736-266">这些 Api 与.NET Native 一起使用时, 可能会引发<xref:System.NotImplementedException>或<xref:System.PlatformNotSupportedException>异常或导致编译器错误。</span><span class="sxs-lookup"><span data-stu-id="80736-266">When used with .NET Native, these APIs may throw a <xref:System.NotImplementedException> or <xref:System.PlatformNotSupportedException> exception, or result in a compiler error.</span></span> <span data-ttu-id="80736-267">在 Windows 应用商店应用的 .NET 中，这些 API 标记为废弃，尽管调用这些 API 会生成编译器警告而非编译器错误。</span><span class="sxs-lookup"><span data-stu-id="80736-267">In .NET for Windows Store apps, these APIs are marked as obsolete, although calling them generates a compiler warning rather than a compiler error.</span></span>  
  
 <span data-ttu-id="80736-268">`VARIANT` 封送的废弃 API：</span><span class="sxs-lookup"><span data-stu-id="80736-268">Deprecated APIs for `VARIANT` marshaling:</span></span>  
  
||  
|-|  
|<xref:System.Runtime.InteropServices.BStrWrapper?displayProperty=nameWithType>|  
|<xref:System.Runtime.InteropServices.CurrencyWrapper?displayProperty=nameWithType>|  
|<xref:System.Runtime.InteropServices.DispatchWrapper?displayProperty=nameWithType>|  
|<xref:System.Runtime.InteropServices.ErrorWrapper?displayProperty=nameWithType>|  
|<xref:System.Runtime.InteropServices.UnknownWrapper?displayProperty=nameWithType>|  
|<xref:System.Runtime.InteropServices.VariantWrapper?displayProperty=nameWithType>|  
|<xref:System.Runtime.InteropServices.UnmanagedType.IDispatch?displayProperty=nameWithType>|  
|<xref:System.Runtime.InteropServices.UnmanagedType.SafeArray?displayProperty=nameWithType>|  
|<xref:System.Runtime.InteropServices.VarEnum?displayProperty=nameWithType>|  
  
 <span data-ttu-id="80736-269"><xref:System.Runtime.InteropServices.UnmanagedType.Struct?displayProperty=nameWithType> 受支持，但在某些情况下，例如，当与使用会引发异常[IDispatch](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/nn-oaidl-idispatch)或 byref 变量。</span><span class="sxs-lookup"><span data-stu-id="80736-269"><xref:System.Runtime.InteropServices.UnmanagedType.Struct?displayProperty=nameWithType> is supported, but it throws an exception in some scenarios, such as when it is used with [IDispatch](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/nn-oaidl-idispatch) or byref variants.</span></span>  
  
 <span data-ttu-id="80736-270">已弃用的 Api [IDispatch](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/nn-oaidl-idispatch)支持：</span><span class="sxs-lookup"><span data-stu-id="80736-270">Deprecated APIs for [IDispatch](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/nn-oaidl-idispatch) support:</span></span>  
  
|<span data-ttu-id="80736-271">类型</span><span class="sxs-lookup"><span data-stu-id="80736-271">Type</span></span>|<span data-ttu-id="80736-272">成员</span><span class="sxs-lookup"><span data-stu-id="80736-272">Member</span></span>|  
|----------|------------|  
|<xref:System.Runtime.InteropServices.ClassInterfaceType?displayProperty=nameWithType>|<xref:System.Runtime.InteropServices.ClassInterfaceType.AutoDispatch>|  
|<xref:System.Runtime.InteropServices.ClassInterfaceType?displayProperty=nameWithType>|<xref:System.Runtime.InteropServices.ClassInterfaceType.AutoDual>|  
|<xref:System.Runtime.InteropServices.ComDefaultInterfaceAttribute?displayProperty=nameWithType>|<span data-ttu-id="80736-273">特性不受支持</span><span class="sxs-lookup"><span data-stu-id="80736-273">Attribute isn't supported</span></span>|  
  
 <span data-ttu-id="80736-274">用于经典 COM 事件的弃用的 API：</span><span class="sxs-lookup"><span data-stu-id="80736-274">Deprecated APIs for classic COM events:</span></span>  
  
||  
|-|  
|<xref:System.Runtime.InteropServices.ComEventsHelper?displayProperty=nameWithType>|  
|<xref:System.Runtime.InteropServices.ComSourceInterfacesAttribute>|  
  
 <span data-ttu-id="80736-275">已弃用的 Api 中的<xref:System.Runtime.InteropServices.ICustomQueryInterface?displayProperty=nameWithType>接口，在.NET Native 中不受支持：</span><span class="sxs-lookup"><span data-stu-id="80736-275">Deprecated APIs in the <xref:System.Runtime.InteropServices.ICustomQueryInterface?displayProperty=nameWithType> interface, which isn't supported in .NET Native:</span></span>  
  
|<span data-ttu-id="80736-276">类型</span><span class="sxs-lookup"><span data-stu-id="80736-276">Type</span></span>|<span data-ttu-id="80736-277">成员</span><span class="sxs-lookup"><span data-stu-id="80736-277">Member</span></span>|  
|----------|------------|  
|<xref:System.Runtime.InteropServices.ICustomQueryInterface?displayProperty=nameWithType>|<span data-ttu-id="80736-278">所有成员。</span><span class="sxs-lookup"><span data-stu-id="80736-278">All members.</span></span>|  
|<xref:System.Runtime.InteropServices.CustomQueryInterfaceMode?displayProperty=nameWithType>|<span data-ttu-id="80736-279">所有成员。</span><span class="sxs-lookup"><span data-stu-id="80736-279">All members.</span></span>|  
|<xref:System.Runtime.InteropServices.CustomQueryInterfaceResult?displayProperty=nameWithType>|<span data-ttu-id="80736-280">所有成员。</span><span class="sxs-lookup"><span data-stu-id="80736-280">All members.</span></span>|  
|<xref:System.Runtime.InteropServices.Marshal?displayProperty=nameWithType>|<xref:System.Runtime.InteropServices.Marshal.GetComInterfaceForObject%28System.Object%2CSystem.Type%2CSystem.Runtime.InteropServices.CustomQueryInterfaceMode%29?displayProperty=nameWithType>|  
  
 <span data-ttu-id="80736-281">其他不受支持的互操作性功能：</span><span class="sxs-lookup"><span data-stu-id="80736-281">Other unsupported interop features:</span></span>  
  
|<span data-ttu-id="80736-282">类型</span><span class="sxs-lookup"><span data-stu-id="80736-282">Type</span></span>|<span data-ttu-id="80736-283">成员</span><span class="sxs-lookup"><span data-stu-id="80736-283">Member</span></span>|  
|----------|------------|  
|<xref:System.Runtime.InteropServices.ICustomAdapter?displayProperty=nameWithType>|<span data-ttu-id="80736-284">所有成员。</span><span class="sxs-lookup"><span data-stu-id="80736-284">All members.</span></span>|  
|<xref:System.Runtime.InteropServices.SafeBuffer?displayProperty=nameWithType>|<span data-ttu-id="80736-285">所有成员。</span><span class="sxs-lookup"><span data-stu-id="80736-285">All members.</span></span>|  
|<xref:System.Runtime.InteropServices.UnmanagedType?displayProperty=nameWithType>|<xref:System.Runtime.InteropServices.UnmanagedType.Currency>|  
|<xref:System.Runtime.InteropServices.UnmanagedType?displayProperty=nameWithType>|<xref:System.Runtime.InteropServices.UnmanagedType.VBByRefStr>|  
|<xref:System.Runtime.InteropServices.UnmanagedType?displayProperty=nameWithType>|<xref:System.Runtime.InteropServices.UnmanagedType.AnsiBStr>|  
|<xref:System.Runtime.InteropServices.UnmanagedType?displayProperty=nameWithType>|<xref:System.Runtime.InteropServices.UnmanagedType.AsAny>|  
|<xref:System.Runtime.InteropServices.UnmanagedType?displayProperty=nameWithType>|<xref:System.Runtime.InteropServices.UnmanagedType.CustomMarshaler>|  
  
 <span data-ttu-id="80736-286">很少使用的封送 API：</span><span class="sxs-lookup"><span data-stu-id="80736-286">Rarely used marshalling APIs:</span></span>  
  
|<span data-ttu-id="80736-287">类型</span><span class="sxs-lookup"><span data-stu-id="80736-287">Type</span></span>|<span data-ttu-id="80736-288">成员</span><span class="sxs-lookup"><span data-stu-id="80736-288">Member</span></span>|  
|----------|------------|  
|<xref:System.Runtime.InteropServices.Marshal?displayProperty=nameWithType>|<xref:System.Runtime.InteropServices.Marshal.ReadByte%28System.Object%2CSystem.Int32%29>|  
|<xref:System.Runtime.InteropServices.Marshal?displayProperty=nameWithType>|<xref:System.Runtime.InteropServices.Marshal.ReadInt16%28System.Object%2CSystem.Int32%29>|  
|<xref:System.Runtime.InteropServices.Marshal?displayProperty=nameWithType>|<xref:System.Runtime.InteropServices.Marshal.ReadInt32%28System.Object%2CSystem.Int32%29>|  
|<xref:System.Runtime.InteropServices.Marshal?displayProperty=nameWithType>|<xref:System.Runtime.InteropServices.Marshal.ReadInt64%28System.Object%2CSystem.Int32%29>|  
|<xref:System.Runtime.InteropServices.Marshal?displayProperty=nameWithType>|<xref:System.Runtime.InteropServices.Marshal.ReadIntPtr%28System.Object%2CSystem.Int32%29>|  
|<xref:System.Runtime.InteropServices.Marshal?displayProperty=nameWithType>|<xref:System.Runtime.InteropServices.Marshal.WriteByte%28System.Object%2CSystem.Int32%2CSystem.Byte%29>|  
|<xref:System.Runtime.InteropServices.Marshal?displayProperty=nameWithType>|<xref:System.Runtime.InteropServices.Marshal.WriteInt16%28System.Object%2CSystem.Int32%2CSystem.Int16%29>|  
|<xref:System.Runtime.InteropServices.Marshal?displayProperty=nameWithType>|<xref:System.Runtime.InteropServices.Marshal.WriteInt32%28System.Object%2CSystem.Int32%2CSystem.Int32%29>|  
|<xref:System.Runtime.InteropServices.Marshal?displayProperty=nameWithType>|<xref:System.Runtime.InteropServices.Marshal.WriteInt64%28System.Object%2CSystem.Int32%2CSystem.Int64%29>|  
|<xref:System.Runtime.InteropServices.Marshal?displayProperty=nameWithType>|<xref:System.Runtime.InteropServices.Marshal.WriteIntPtr%28System.Object%2CSystem.Int32%2CSystem.IntPtr%29>|  
  
 <span data-ttu-id="80736-289">**平台调用和 COM 互操作兼容性**</span><span class="sxs-lookup"><span data-stu-id="80736-289">**Platform invoke and COM interop compatibility**</span></span>  
  
 <span data-ttu-id="80736-290">大多数平台调用和 COM 互操作方案中.NET Native 仍受支持。</span><span class="sxs-lookup"><span data-stu-id="80736-290">Most platform invoke and COM interop scenarios are still supported in .NET Native.</span></span> <span data-ttu-id="80736-291">特别地，Windows Runtime (WinRT) API 的所有互操作和 Windows Runtime 所需的所有封送都受支持。</span><span class="sxs-lookup"><span data-stu-id="80736-291">In particular, all interoperability with Windows Runtime (WinRT) APIs and all marshaling required for the Windows Runtime is supported.</span></span> <span data-ttu-id="80736-292">这包括针对以下内容的封送支持：</span><span class="sxs-lookup"><span data-stu-id="80736-292">This includes marshaling support for:</span></span>  
  
-   <span data-ttu-id="80736-293">阵列（包括 <xref:System.Runtime.InteropServices.UnmanagedType.ByValArray?displayProperty=nameWithType>）</span><span class="sxs-lookup"><span data-stu-id="80736-293">Arrays (including <xref:System.Runtime.InteropServices.UnmanagedType.ByValArray?displayProperty=nameWithType>)</span></span>  
  
-   `BStr`  
  
-   <span data-ttu-id="80736-294">委托</span><span class="sxs-lookup"><span data-stu-id="80736-294">Delegates</span></span>  
  
-   <span data-ttu-id="80736-295">字符串（Unicode、Ansi 和 HSTRING）</span><span class="sxs-lookup"><span data-stu-id="80736-295">Strings (Unicode, Ansi, and HSTRING)</span></span>  
  
-   <span data-ttu-id="80736-296">结构（`byref` 和 `byval`）</span><span class="sxs-lookup"><span data-stu-id="80736-296">Structs (`byref` and `byval`)</span></span>  
  
-   <span data-ttu-id="80736-297">Unions</span><span class="sxs-lookup"><span data-stu-id="80736-297">Unions</span></span>  
  
-   <span data-ttu-id="80736-298">Win32 句柄</span><span class="sxs-lookup"><span data-stu-id="80736-298">Win32 handles</span></span>  
  
-   <span data-ttu-id="80736-299">所有 WinRT 构造</span><span class="sxs-lookup"><span data-stu-id="80736-299">All WinRT constructs</span></span>  
  
-   <span data-ttu-id="80736-300">部分支持封送变体类型。</span><span class="sxs-lookup"><span data-stu-id="80736-300">Partial support for marshaling variant types.</span></span> <span data-ttu-id="80736-301">以下内容受到支持：</span><span class="sxs-lookup"><span data-stu-id="80736-301">The following are supported:</span></span>  
  
    -   <xref:System.Boolean>  
  
    -   <xref:System.Byte>  
  
    -   <xref:System.Decimal>  
  
    -   <xref:System.Double>  
  
    -   <xref:System.Int16>  
  
    -   <xref:System.Int32>  
  
    -   <xref:System.Int64>  
  
    -   <xref:System.SByte>  
  
    -   <xref:System.Single>  
  
    -   <xref:System.UInt16>  
  
    -   <xref:System.UInt32>  
  
    -   <xref:System.UInt64>  
  
    -   `BStr`  
  
    -   [<span data-ttu-id="80736-302">IUnknown</span><span class="sxs-lookup"><span data-stu-id="80736-302">IUnknown</span></span>](/windows/desktop/api/unknwn/nn-unknwn-iunknown)  
  
 <span data-ttu-id="80736-303">但是，.NET 本机不支持以下功能：</span><span class="sxs-lookup"><span data-stu-id="80736-303">However, .NET Native doesn't support the following:</span></span>  
  
-   <span data-ttu-id="80736-304">使用经典 COM 事件</span><span class="sxs-lookup"><span data-stu-id="80736-304">Using classic COM events</span></span>  
  
-   <span data-ttu-id="80736-305">在托管类型上实施 <xref:System.Runtime.InteropServices.ICustomQueryInterface?displayProperty=nameWithType> 接口</span><span class="sxs-lookup"><span data-stu-id="80736-305">Implementing the <xref:System.Runtime.InteropServices.ICustomQueryInterface?displayProperty=nameWithType> interface on a managed type</span></span>  
  
-   <span data-ttu-id="80736-306">实现[IDispatch](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/nn-oaidl-idispatch)上的托管类型通过接口<xref:System.Runtime.InteropServices.ComDefaultInterfaceAttribute?displayProperty=nameWithType>属性。</span><span class="sxs-lookup"><span data-stu-id="80736-306">Implementing the [IDispatch](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/nn-oaidl-idispatch) interface on a managed type through the <xref:System.Runtime.InteropServices.ComDefaultInterfaceAttribute?displayProperty=nameWithType> attribute.</span></span> <span data-ttu-id="80736-307">然而，请注意你无法通过 `IDispatch`调用 COM 对象，而且你的托管对象无法实施 `IDispatch`。</span><span class="sxs-lookup"><span data-stu-id="80736-307">However, note that you can't call COM objects through `IDispatch`, and your managed object can't implement `IDispatch`.</span></span>  
  
 <span data-ttu-id="80736-308">使用反射来调用平台调用方法不受支持。</span><span class="sxs-lookup"><span data-stu-id="80736-308">Using reflection to invoke a platform invoke method isn't supported.</span></span> <span data-ttu-id="80736-309">你可以巧妙绕过这种限制，具体做法是将方法调用包装在另一种方法中，并使用反射调用包装方法。</span><span class="sxs-lookup"><span data-stu-id="80736-309">You can work around this limitation by wrapping the method call in another method and using reflection to call the wrapper instead.</span></span>  
  
<a name="APIs"></a>   
### <a name="other-differences-from-net-apis-for-windows-store-apps"></a><span data-ttu-id="80736-310">与 Windows 应用商店应用 .NET API 的其他差异</span><span class="sxs-lookup"><span data-stu-id="80736-310">Other differences from .NET APIs for Windows Store apps</span></span>  
 <span data-ttu-id="80736-311">本部分列出了.NET Native 中不支持的其余 Api。</span><span class="sxs-lookup"><span data-stu-id="80736-311">This section lists the remaining APIs that aren't supported in .NET Native.</span></span> <span data-ttu-id="80736-312">最大一部分不受支持的 API 是 Windows Communication Foundation (WCF) API。</span><span class="sxs-lookup"><span data-stu-id="80736-312">The largest set of the unsupported APIs are Windows Communication Foundation (WCF) APIs.</span></span>  
  
 <span data-ttu-id="80736-313">**DataAnnotations (System.ComponentModel.DataAnnotations)**</span><span class="sxs-lookup"><span data-stu-id="80736-313">**DataAnnotations (System.ComponentModel.DataAnnotations)**</span></span>  
  
 <span data-ttu-id="80736-314">中的类型<xref:System.ComponentModel.DataAnnotations>和<xref:System.ComponentModel.DataAnnotations.Schema>中.NET 本机不支持命名空间。</span><span class="sxs-lookup"><span data-stu-id="80736-314">The types in the <xref:System.ComponentModel.DataAnnotations> and <xref:System.ComponentModel.DataAnnotations.Schema> namespaces aren't supported in .NET Native.</span></span> <span data-ttu-id="80736-315">这些包括 Windows 8 的 Windows 应用商店应用的 .NET 中出现的以下类型：</span><span class="sxs-lookup"><span data-stu-id="80736-315">These include the following types that are present in the .NET for Windows Store apps for Windows 8:</span></span>  
  
||  
|-|  
|<xref:System.ComponentModel.DataAnnotations.AssociationAttribute?displayProperty=nameWithType>|  
|<xref:System.ComponentModel.DataAnnotations.ConcurrencyCheckAttribute?displayProperty=nameWithType>|  
|<xref:System.ComponentModel.DataAnnotations.CustomValidationAttribute?displayProperty=nameWithType>|  
|<xref:System.ComponentModel.DataAnnotations.DataType?displayProperty=nameWithType>|  
|<xref:System.ComponentModel.DataAnnotations.DataTypeAttribute?displayProperty=nameWithType>|  
|<xref:System.ComponentModel.DataAnnotations.DisplayAttribute?displayProperty=nameWithType>|  
|<xref:System.ComponentModel.DataAnnotations.DisplayColumnAttribute?displayProperty=nameWithType>|  
|<xref:System.ComponentModel.DataAnnotations.DisplayFormatAttribute>|  
|<xref:System.ComponentModel.DataAnnotations.EditableAttribute>|  
|<xref:System.ComponentModel.DataAnnotations.EnumDataTypeAttribute>|  
|<xref:System.ComponentModel.DataAnnotations.FilterUIHintAttribute?displayProperty=nameWithType>|  
|<xref:System.ComponentModel.DataAnnotations.KeyAttribute?displayProperty=nameWithType>|  
|<xref:System.ComponentModel.DataAnnotations.RangeAttribute?displayProperty=nameWithType>|  
|<xref:System.ComponentModel.DataAnnotations.RegularExpressionAttribute?displayProperty=nameWithType>|  
|<xref:System.ComponentModel.DataAnnotations.RequiredAttribute?displayProperty=nameWithType>|  
|<xref:System.ComponentModel.DataAnnotations.StringLengthAttribute?displayProperty=nameWithType>|  
|<xref:System.ComponentModel.DataAnnotations.TimestampAttribute?displayProperty=nameWithType>|  
|<xref:System.ComponentModel.DataAnnotations.UIHintAttribute?displayProperty=nameWithType>|  
|<xref:System.ComponentModel.DataAnnotations.ValidationAttribute?displayProperty=nameWithType>|  
|<xref:System.ComponentModel.DataAnnotations.ValidationContext?displayProperty=nameWithType>|  
|<xref:System.ComponentModel.DataAnnotations.ValidationException?displayProperty=nameWithType>|  
|<xref:System.ComponentModel.DataAnnotations.ValidationResult?displayProperty=nameWithType>|  
|<xref:System.ComponentModel.DataAnnotations.Validator?displayProperty=nameWithType>|  
|<xref:System.ComponentModel.DataAnnotations.Schema.DatabaseGeneratedAttribute?displayProperty=nameWithType>|  
|<xref:System.ComponentModel.DataAnnotations.Schema.DatabaseGeneratedOption?displayProperty=nameWithType>|  
  
 <span data-ttu-id="80736-316">**Visual Basic**</span><span class="sxs-lookup"><span data-stu-id="80736-316">**Visual Basic**</span></span>  
  
 <span data-ttu-id="80736-317">Visual Basic 当前不支持在.NET Native。</span><span class="sxs-lookup"><span data-stu-id="80736-317">Visual Basic isn't currently supported in .NET Native.</span></span> <span data-ttu-id="80736-318">中的以下类型<xref:Microsoft.VisualBasic>和<xref:Microsoft.VisualBasic.CompilerServices>命名空间中不可用.NET Native:</span><span class="sxs-lookup"><span data-stu-id="80736-318">The following types in the <xref:Microsoft.VisualBasic> and <xref:Microsoft.VisualBasic.CompilerServices> namespaces aren't available in .NET Native:</span></span>  
  
||  
|-|  
|<xref:Microsoft.VisualBasic.CallType?displayProperty=nameWithType>|  
|<xref:Microsoft.VisualBasic.Constants?displayProperty=nameWithType>|  
|<xref:Microsoft.VisualBasic.HideModuleNameAttribute?displayProperty=nameWithType>|  
|<xref:Microsoft.VisualBasic.Strings?displayProperty=nameWithType>|  
|<xref:Microsoft.VisualBasic.CompilerServices.Conversions?displayProperty=nameWithType>|  
|<xref:Microsoft.VisualBasic.CompilerServices.DesignerGeneratedAttribute?displayProperty=nameWithType>|  
|<xref:Microsoft.VisualBasic.CompilerServices.IncompleteInitialization?displayProperty=nameWithType>|  
|<xref:Microsoft.VisualBasic.CompilerServices.NewLateBinding?displayProperty=nameWithType>|  
|<xref:Microsoft.VisualBasic.CompilerServices.ObjectFlowControl?displayProperty=nameWithType>|  
|<xref:Microsoft.VisualBasic.CompilerServices.ObjectFlowControl.ForLoopControl?displayProperty=nameWithType>|  
|<xref:Microsoft.VisualBasic.CompilerServices.Operators?displayProperty=nameWithType>|  
|<xref:Microsoft.VisualBasic.CompilerServices.OptionCompareAttribute?displayProperty=nameWithType>|  
|<xref:Microsoft.VisualBasic.CompilerServices.OptionTextAttribute?displayProperty=nameWithType>|  
|<xref:Microsoft.VisualBasic.CompilerServices.ProjectData?displayProperty=nameWithType>|  
|<xref:Microsoft.VisualBasic.CompilerServices.StandardModuleAttribute?displayProperty=nameWithType>|  
|<xref:Microsoft.VisualBasic.CompilerServices.StaticLocalInitFlag?displayProperty=nameWithType>|  
|<xref:Microsoft.VisualBasic.CompilerServices.Utils?displayProperty=nameWithType>|  
  
 <span data-ttu-id="80736-319">**反射上下文（System.Reflection.Context 命名空间）**</span><span class="sxs-lookup"><span data-stu-id="80736-319">**Reflection Context (System.Reflection.Context namespace)**</span></span>  
  
 <span data-ttu-id="80736-320"><xref:System.Reflection.Context.CustomReflectionContext?displayProperty=nameWithType>类不支持在.NET Native。</span><span class="sxs-lookup"><span data-stu-id="80736-320">The <xref:System.Reflection.Context.CustomReflectionContext?displayProperty=nameWithType> class isn't supported in .NET Native.</span></span>  
  
 <span data-ttu-id="80736-321">**RTC (System.Net.Http.Rtc)**</span><span class="sxs-lookup"><span data-stu-id="80736-321">**RTC (System.Net.Http.Rtc)**</span></span>  
  
 <span data-ttu-id="80736-322"><xref:System.Net.Http.RtcRequestFactory?displayProperty=nameWithType>类不支持在.NET Native。</span><span class="sxs-lookup"><span data-stu-id="80736-322">The <xref:System.Net.Http.RtcRequestFactory?displayProperty=nameWithType> class isn't supported in .NET Native.</span></span>  
  
 <span data-ttu-id="80736-323">**Windows Communication Foundation (WCF) (System.ServiceModel.\*)**</span><span class="sxs-lookup"><span data-stu-id="80736-323">**Windows Communication Foundation (WCF) (System.ServiceModel.\*)**</span></span>  
  
 <span data-ttu-id="80736-324">中的类型[system.servicemodel.\* 命名空间](https://msdn.microsoft.com/library/gg145010.aspx)中.NET Native 不受支持。</span><span class="sxs-lookup"><span data-stu-id="80736-324">The types in the [System.ServiceModel.\* namespaces](https://msdn.microsoft.com/library/gg145010.aspx) aren't supported in .NET Native.</span></span> <span data-ttu-id="80736-325">这些包括以下类型：</span><span class="sxs-lookup"><span data-stu-id="80736-325">These includes the following types:</span></span>  
  
||  
|-|  
|<xref:System.ServiceModel.ActionNotSupportedException?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.BasicHttpBinding?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.BasicHttpMessageCredentialType?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.BasicHttpSecurity?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.BasicHttpSecurityMode?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.CallbackBehaviorAttribute?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.ChannelFactory?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.ChannelFactory%601?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.ClientBase%601?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.ClientBase%601.BeginOperationDelegate?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.ClientBase%601.ChannelBase%601?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.ClientBase%601.EndOperationDelegate?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.ClientBase%601.InvokeAsyncCompletedEventArgs?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.CommunicationException?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.CommunicationObjectAbortedException?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.CommunicationObjectFaultedException?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.CommunicationState?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.DataContractFormatAttribute?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.DnsEndpointIdentity?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.DuplexChannelFactory%601?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.DuplexClientBase%601?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.EndpointAddress?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.EndpointAddressBuilder?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.EndpointIdentity?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.EndpointNotFoundException?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.EnvelopeVersion?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.ExceptionDetail?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.FaultCode?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.FaultContractAttribute?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.FaultException?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.FaultException%601?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.FaultReason?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.FaultReasonText?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.HttpBindingBase?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.HttpClientCredentialType?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.HttpTransportSecurity?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.IClientChannel?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.ICommunicationObject?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.IContextChannel?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.IDefaultCommunicationTimeouts?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.IExtensibleObject%601?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.IExtension%601?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.IExtensionCollection%601?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.InstanceContext?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.InvalidMessageContractException?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.MessageBodyMemberAttribute?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.MessageContractAttribute?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.MessageContractMemberAttribute?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.MessageCredentialType?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.MessageHeader%601?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.MessageHeaderException?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.MessageParameterAttribute?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.MessageSecurityOverTcp?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.MessageSecurityVersion?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.NetHttpBinding?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.NetHttpMessageEncoding?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.NetTcpBinding?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.NetTcpSecurity?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.OperationContext?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.OperationContextScope?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.OperationContractAttribute?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.OperationFormatStyle?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.ProtocolException?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.QuotaExceededException?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.SecurityMode?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.ServerTooBusyException?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.ServiceActivationException?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.ServiceContractAttribute?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.ServiceKnownTypeAttribute?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.SpnEndpointIdentity?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.TcpClientCredentialType?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.TcpTransportSecurity?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.TransferMode?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.UnknownMessageReceivedEventArgs?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.UpnEndpointIdentity?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.XmlSerializerFormatAttribute?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.AddressHeader?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.AddressHeaderCollection?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.AddressingVersion?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.ChannelManagerBase?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.ChannelParameterCollection?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.CommunicationObject?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.CompressionFormat?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.ConnectionOrientedTransportBindingElement?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.CustomBinding?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.FaultConverter?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.HttpRequestMessageProperty?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.HttpResponseMessageProperty?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.HttpsTransportBindingElement?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.HttpTransportBindingElement?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.IChannel?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.IChannelFactory?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.IChannelFactory%601?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.IDuplexChannel?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.IDuplexSession?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.IDuplexSessionChannel?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.IHttpCookieContainerManager?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.IInputChannel?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.IInputSession?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.IInputSessionChannel?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.IMessageProperty?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.IOutputChannel?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.IOutputSession?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.IOutputSessionChannel?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.IRequestChannel?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.IRequestSessionChannel?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.ISession?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.ISessionChannel%601?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.LocalClientSecuritySettings?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.Message?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.MessageBuffer?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.MessageEncoder?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.MessageEncoderFactory?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.MessageEncodingBindingElement?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.MessageFault?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.MessageHeader?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.MessageHeaderInfo?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.MessageHeaders?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.MessageProperties?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.MessageState?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.MessageVersion?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.RequestContext?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.SecurityBindingElement?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.SecurityHeaderLayout?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.TcpConnectionPoolSettings?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.TcpTransportBindingElement?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.TransportBindingElement?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.TransportSecurityBindingElement?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.WebSocketTransportSettings?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.WebSocketTransportUsage?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Channels.WindowsStreamSecurityBindingElement?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Description.ClientCredentials?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Description.ContractDescription?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Description.FaultDescription?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Description.FaultDescriptionCollection?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Description.IContractBehavior?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Description.IEndpointBehavior?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Description.IOperationBehavior?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Description.MessageBodyDescription?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Description.MessageDescription?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Description.MessageDescriptionCollection?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Description.MessageDirection?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Description.MessageHeaderDescription?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Description.MessageHeaderDescriptionCollection?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Description.MessagePartDescription?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Description.MessagePartDescriptionCollection?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Description.MessagePropertyDescription?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Description.MessagePropertyDescriptionCollection?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Description.OperationDescription?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Description.OperationDescriptionCollection?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Description.ServiceEndpoint?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Dispatcher.ClientOperation?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Dispatcher.ClientRuntime?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Dispatcher.DispatchOperation?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Dispatcher.DispatchRuntime?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Dispatcher.EndpointDispatcher?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Dispatcher.IClientMessageFormatter?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Dispatcher.IClientMessageInspector?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Dispatcher.IClientOperationSelector?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Dispatcher.IParameterInspector?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Security.BasicSecurityProfileVersion?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Security.HttpDigestClientCredential?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Security.MessageSecurityException?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Security.SecureConversationVersion?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Security.SecurityAccessDeniedException?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Security.SecurityPolicyVersion?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Security.SecurityVersion?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Security.TrustVersion?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Security.UserNamePasswordClientCredential?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Security.WindowsClientCredential?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Security.Tokens.SecureConversationSecurityTokenParameters?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Security.Tokens.SecurityTokenParameters?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Security.Tokens.SupportingTokenParameters?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Security.Tokens.UserNameSecurityTokenParameters?displayProperty=nameWithType>|  
  
### <a name="differences-in-serializers"></a><span data-ttu-id="80736-326">序列化程序中的差异</span><span class="sxs-lookup"><span data-stu-id="80736-326">Differences in serializers</span></span>  
 <span data-ttu-id="80736-327">与 <xref:System.Runtime.Serialization.DataContractSerializer>、 <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>和 <xref:System.Xml.Serialization.XmlSerializer> 类的序列化和反序列化有关的以下差异：</span><span class="sxs-lookup"><span data-stu-id="80736-327">The following differences concern serialization and deserialization with the <xref:System.Runtime.Serialization.DataContractSerializer>, <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>, and <xref:System.Xml.Serialization.XmlSerializer> classes:</span></span>  
  
-   <span data-ttu-id="80736-328">在.NET Native<xref:System.Runtime.Serialization.DataContractSerializer>和<xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>无法序列化或反序列化具有其类型不是根序列化类型的基类成员的派生的类。</span><span class="sxs-lookup"><span data-stu-id="80736-328">In .NET Native, <xref:System.Runtime.Serialization.DataContractSerializer> and <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> fail to serialize or deserialize a derived class that has a base class member whose type isn't a root serialization type.</span></span> <span data-ttu-id="80736-329">例如，在以下代码中，尝试序列化或反序列化 `Y` 会导致出现错误：</span><span class="sxs-lookup"><span data-stu-id="80736-329">For example, in the following code, trying to serialize or deserialize `Y` results in an error:</span></span>  
  
     [!code-csharp[ProjectN#10](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/compat3.cs#10)]  
  
     <span data-ttu-id="80736-330">类型 `InnerType` 对序列程序而言是未知的，因为基类的成员在序列化期间无法遍历。</span><span class="sxs-lookup"><span data-stu-id="80736-330">Type `InnerType` isn't known to the serializer, because the members of the base class aren't traversed during serialization.</span></span>  
  
-   <span data-ttu-id="80736-331"><xref:System.Runtime.Serialization.DataContractSerializer> 和 <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> 无法序列化实施 <xref:System.Collections.Generic.IEnumerable%601> 接口的类或结构。</span><span class="sxs-lookup"><span data-stu-id="80736-331"><xref:System.Runtime.Serialization.DataContractSerializer> and <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> fail to serialize a class or structure that implements the <xref:System.Collections.Generic.IEnumerable%601> interface.</span></span> <span data-ttu-id="80736-332">例如，以下类无法序列化或反序列化：</span><span class="sxs-lookup"><span data-stu-id="80736-332">For example, the following types fail to serialize or deserialize:</span></span>  
  
  
  
-   <span data-ttu-id="80736-333"><xref:System.Xml.Serialization.XmlSerializer> 无法序列化以下对象值，因为它不知道将序列化的对象的类型：</span><span class="sxs-lookup"><span data-stu-id="80736-333"><xref:System.Xml.Serialization.XmlSerializer> fails to serialize the following object value, because it doesn't know the exact type of the object to be serialized:</span></span>  
  
  
  
-   <span data-ttu-id="80736-334">如果将序列化的对象的类型是<xref:System.Xml.Serialization.XmlSerializer> ，则 <xref:System.Xml.XmlQualifiedName>无法序列化或反序列化。</span><span class="sxs-lookup"><span data-stu-id="80736-334"><xref:System.Xml.Serialization.XmlSerializer> fails to serialize or deserialize if the type of the serialized object is <xref:System.Xml.XmlQualifiedName>.</span></span>  
  
-   <span data-ttu-id="80736-335">所有序列程序（<xref:System.Runtime.Serialization.DataContractSerializer>、<xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> 和 <xref:System.Xml.Serialization.XmlSerializer>）都无法为 <xref:System.Xml.Linq.XElement?displayProperty=nameWithType> 类型或包含 <xref:System.Xml.Linq.XElement> 的类型生成序列代码。</span><span class="sxs-lookup"><span data-stu-id="80736-335">All serializers (<xref:System.Runtime.Serialization.DataContractSerializer>, <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>, and <xref:System.Xml.Serialization.XmlSerializer>) fail to generate serialization code for type <xref:System.Xml.Linq.XElement?displayProperty=nameWithType> or for a type that contains <xref:System.Xml.Linq.XElement>.</span></span> <span data-ttu-id="80736-336">它们会显示生成时间错误。</span><span class="sxs-lookup"><span data-stu-id="80736-336">They display build-time errors instead.</span></span>  
  
-   <span data-ttu-id="80736-337">以下序列化类型的构造函数无法保证按照预期工作：</span><span class="sxs-lookup"><span data-stu-id="80736-337">The following constructors of the serialization types aren't guaranteed to work as expected:</span></span>  
  
    -   <xref:System.Runtime.Serialization.DataContractSerializer.%23ctor%28System.Type%2CSystem.Collections.Generic.IEnumerable%7BSystem.Type%7D%29?displayProperty=nameWithType>  
  
    -   <xref:System.Runtime.Serialization.DataContractSerializer.%23ctor%28System.Type%2CSystem.Runtime.Serialization.DataContractSerializerSettings%29?displayProperty=nameWithType>  
  
    -   <xref:System.Runtime.Serialization.DataContractSerializer.%23ctor%28System.Type%2CSystem.String%2CSystem.String%2CSystem.Collections.Generic.IEnumerable%7BSystem.Type%7D%29?displayProperty=nameWithType>  
  
    -   <xref:System.Runtime.Serialization.DataContractSerializer.%23ctor%28System.Type%2CSystem.Xml.XmlDictionaryString%2CSystem.Xml.XmlDictionaryString%2CSystem.Collections.Generic.IEnumerable%7BSystem.Type%7D%29?displayProperty=nameWithType>  
  
    -   <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.%23ctor%28System.Type%2CSystem.Runtime.Serialization.Json.DataContractJsonSerializerSettings%29?displayProperty=nameWithType>  
  
    -   <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.%23ctor%28System.Type%2CSystem.Collections.Generic.IEnumerable%7BSystem.Type%7D%29?displayProperty=nameWithType>  
  
    -   <xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Type%2CSystem.String%29?displayProperty=nameWithType>  
  
    -   <xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Type%2CSystem.Type%5B%5D%29?displayProperty=nameWithType>  
  
    -   <xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Type%2CSystem.Xml.Serialization.XmlAttributeOverrides%29?displayProperty=nameWithType>  
  
    -   <xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Type%2CSystem.Xml.Serialization.XmlRootAttribute%29?displayProperty=nameWithType>  
  
    -   <xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Type%2CSystem.Xml.Serialization.XmlAttributeOverrides%2CSystem.Type%5B%5D%2CSystem.Xml.Serialization.XmlRootAttribute%2CSystem.String%29?displayProperty=nameWithType>  
  
-   <span data-ttu-id="80736-338"><xref:System.Xml.Serialization.XmlSerializer> 无法为具有以下任意特性的方法的类型生成代码：</span><span class="sxs-lookup"><span data-stu-id="80736-338"><xref:System.Xml.Serialization.XmlSerializer> fails to generate code for a type that has methods attributed with any of the following attributes:</span></span>  
  
    -   <xref:System.Runtime.Serialization.OnSerializingAttribute>  
  
    -   <xref:System.Runtime.Serialization.OnSerializedAttribute>  
  
    -   <xref:System.Runtime.Serialization.OnDeserializingAttribute>  
  
    -   <xref:System.Runtime.Serialization.OnDeserializedAttribute>  
  
-   <span data-ttu-id="80736-339"><xref:System.Xml.Serialization.XmlSerializer> 不兼容 <xref:System.Xml.Serialization.IXmlSerializable> 自定义序列化接口。</span><span class="sxs-lookup"><span data-stu-id="80736-339"><xref:System.Xml.Serialization.XmlSerializer> doesn't honor the <xref:System.Xml.Serialization.IXmlSerializable> custom serialization interface.</span></span> <span data-ttu-id="80736-340">如果你的类实施此接口， <xref:System.Xml.Serialization.XmlSerializer> 会考虑普通旧 CLR 对象 (POCO) 类型并仅对其公共属性进行序列化。</span><span class="sxs-lookup"><span data-stu-id="80736-340">If you have a class that implements this interface, <xref:System.Xml.Serialization.XmlSerializer> considers the type a plain old CLR object (POCO) type and serializes only its public properties.</span></span>  
  
-   <span data-ttu-id="80736-341">对普通 <xref:System.Exception> 对象的序列化（如以下情况）对 <xref:System.Runtime.Serialization.DataContractSerializer> 和 <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>无效：</span><span class="sxs-lookup"><span data-stu-id="80736-341">Serializing a plain <xref:System.Exception> object, such as the following, doesn't work well with <xref:System.Runtime.Serialization.DataContractSerializer> and <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>:</span></span>  
  
  
  
<a name="VS"></a>   
## <a name="visual-studio-differences"></a><span data-ttu-id="80736-342">Visual Studio 差异</span><span class="sxs-lookup"><span data-stu-id="80736-342">Visual Studio differences</span></span>  
 <span data-ttu-id="80736-343">**异常和调试**</span><span class="sxs-lookup"><span data-stu-id="80736-343">**Exceptions and debugging**</span></span>  
  
 <span data-ttu-id="80736-344">运行在调试器中使用.NET Native 编译应用时，以下异常类型启用最可能异常：</span><span class="sxs-lookup"><span data-stu-id="80736-344">When you're running apps compiled by using .NET Native in the debugger, first-chance exceptions are enabled for the following exception types:</span></span>  
  
-   <xref:System.MemberAccessException>  
  
-   <xref:System.TypeAccessException>  
  
 <span data-ttu-id="80736-345">**构建应用**</span><span class="sxs-lookup"><span data-stu-id="80736-345">**Building apps**</span></span>  
  
 <span data-ttu-id="80736-346">使用 Visual Studio 默认使用的 x86 构建工具。</span><span class="sxs-lookup"><span data-stu-id="80736-346">Use the x86 build tools that are used by default by Visual Studio.</span></span> <span data-ttu-id="80736-347">我们不推荐使用 AMD64 MSBuild 工具（位置路径为 C:\Program Files (x86)\MSBuild\12.0\bin\amd64），因为这些工具会导致构建问题。</span><span class="sxs-lookup"><span data-stu-id="80736-347">We don't recommend using the AMD64 MSBuild tools, which are found in C:\Program Files (x86)\MSBuild\12.0\bin\amd64; these may create build problems.</span></span>  
  
 <span data-ttu-id="80736-348">**探查器**</span><span class="sxs-lookup"><span data-stu-id="80736-348">**Profilers**</span></span>  
  
-   <span data-ttu-id="80736-349">Visual Studio CPU 探查器和 XAML 内存探查器不会正确显示 Just-My-Code。</span><span class="sxs-lookup"><span data-stu-id="80736-349">The Visual Studio CPU Profiler and XAML Memory Profiler don't display Just-My-Code correctly.</span></span>  
  
-   <span data-ttu-id="80736-350">XAML 内存探查器不会精确显示托管的堆数据。</span><span class="sxs-lookup"><span data-stu-id="80736-350">The XAML Memory Profiler doesn't accurately display managed heap data.</span></span>  
  
-   <span data-ttu-id="80736-351">CPU 探查器不会正确区分模块和显示前缀的功能名。</span><span class="sxs-lookup"><span data-stu-id="80736-351">The CPU Profiler doesn't correctly identify modules, and displays prefixed function names.</span></span>  
  
 <span data-ttu-id="80736-352">**单元测试库项目**</span><span class="sxs-lookup"><span data-stu-id="80736-352">**Unit Test Library projects**</span></span>  
  
 <span data-ttu-id="80736-353">启用.NET Native 上的 Windows 应用商店应用项目单元测试库不支持，并且会导致项目无法生成。</span><span class="sxs-lookup"><span data-stu-id="80736-353">Enabling .NET Native on a Unit Test Library for a Windows Store apps project isn't supported and causes the project to fail to build.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80736-354">请参阅</span><span class="sxs-lookup"><span data-stu-id="80736-354">See Also</span></span>  
 [<span data-ttu-id="80736-355">入门</span><span class="sxs-lookup"><span data-stu-id="80736-355">Getting Started</span></span>](../../../docs/framework/net-native/getting-started-with-net-native.md)  
 [<span data-ttu-id="80736-356">运行时指令 (rd.xml) 配置文件参考</span><span class="sxs-lookup"><span data-stu-id="80736-356">Runtime Directives (rd.xml) Configuration File Reference</span></span>](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)  
 [<span data-ttu-id="80736-357">.NET for Windows Store 应用概述</span><span class="sxs-lookup"><span data-stu-id="80736-357">.NET For Windows Store apps overview</span></span>](https://msdn.microsoft.com/library/windows/apps/br230302.aspx)  
 [<span data-ttu-id="80736-358">.NET Framework 对 Windows 应用商店应用和 Windows 运行时的支持情况</span><span class="sxs-lookup"><span data-stu-id="80736-358">.NET Framework Support for Windows Store Apps and Windows Runtime</span></span>](../../../docs/standard/cross-platform/support-for-windows-store-apps-and-windows-runtime.md)
