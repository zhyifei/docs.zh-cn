---
title: "将 Windows 应用商店应用迁移到 .NET Native"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4153aa18-6f56-4a0a-865b-d3da743a1d05
caps.latest.revision: "29"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c4257876abeeccf762a7caa87f667468a16bba70
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="migrating-your-windows-store-app-to-net-native"></a><span data-ttu-id="b7d59-102">将 Windows 应用商店应用迁移到 .NET Native</span><span class="sxs-lookup"><span data-stu-id="b7d59-102">Migrating Your Windows Store App to .NET Native</span></span>
[!INCLUDE[net_native](../../../includes/net-native-md.md)]<span data-ttu-id="b7d59-103"> 对 Windows 应用商店中或开发者的计算机上的应用进行静态编译。</span><span class="sxs-lookup"><span data-stu-id="b7d59-103"> provides static compilation of apps in the Windows Store or on the developer’s computer.</span></span> <span data-ttu-id="b7d59-104">这不同于及时生成 (JIT) 编译器或 [本地映像生成器 (Ngen.exe)](../../../docs/framework/tools/ngen-exe-native-image-generator.md) 在该设备上为 Windows 应用商店应用执行的动态编译。</span><span class="sxs-lookup"><span data-stu-id="b7d59-104">This differs from the dynamic compilation performed for Windows Store apps by the just-in-time (JIT) compiler or the [Native Image Generator (Ngen.exe)](../../../docs/framework/tools/ngen-exe-native-image-generator.md) on the device.</span></span> <span data-ttu-id="b7d59-105">尽管存在不同， [!INCLUDE[net_native](../../../includes/net-native-md.md)] 尝试保持与 [.NET for Windows 应用商店应用](http://msdn.microsoft.com/library/windows/apps/br230302.aspx)的兼容。</span><span class="sxs-lookup"><span data-stu-id="b7d59-105">Despite the differences, [!INCLUDE[net_native](../../../includes/net-native-md.md)] tries to maintain compatibility with the [.NET for Windows Store apps](http://msdn.microsoft.com/library/windows/apps/br230302.aspx).</span></span> <span data-ttu-id="b7d59-106">通常，在 Windows 应用商店应用的 .NET 上可以运行的程序在 [!INCLUDE[net_native](../../../includes/net-native-md.md)]上也可以运行。</span><span class="sxs-lookup"><span data-stu-id="b7d59-106">For the most part, things that work on the .NET for Windows Store apps also work with [!INCLUDE[net_native](../../../includes/net-native-md.md)].</span></span>  <span data-ttu-id="b7d59-107">然而，在某些情况下，你可能会遇到行为变更。</span><span class="sxs-lookup"><span data-stu-id="b7d59-107">However, in some cases, you may encounter behavioral changes.</span></span> <span data-ttu-id="b7d59-108">本文档从以下方面讨论了 Windows 应用商店应用的标准 .NET 和 [!INCLUDE[net_native](../../../includes/net-native-md.md)] 之间的差异：</span><span class="sxs-lookup"><span data-stu-id="b7d59-108">This document discusses these differences between the standard .NET for Windows Store apps and [!INCLUDE[net_native](../../../includes/net-native-md.md)] in the following areas:</span></span>  
  
-   [<span data-ttu-id="b7d59-109">常规运行时差异</span><span class="sxs-lookup"><span data-stu-id="b7d59-109">General runtime differences</span></span>](#Runtime)  
  
-   [<span data-ttu-id="b7d59-110">动态编程差异</span><span class="sxs-lookup"><span data-stu-id="b7d59-110">Dynamic programming differences</span></span>](#Dynamic)  
  
-   [<span data-ttu-id="b7d59-111">其他与反射相关的差异</span><span class="sxs-lookup"><span data-stu-id="b7d59-111">Other reflection-related differences</span></span>](#Reflection)  
  
-   [<span data-ttu-id="b7d59-112">不受支持的方案和 API</span><span class="sxs-lookup"><span data-stu-id="b7d59-112">Unsupported scenarios and APIs</span></span>](#Unsupported)  
  
-   [<span data-ttu-id="b7d59-113">Visual Studio 差异</span><span class="sxs-lookup"><span data-stu-id="b7d59-113">Visual Studio differences</span></span>](#VS)  
  
<a name="Runtime"></a>   
## <a name="general-runtime-differences"></a><span data-ttu-id="b7d59-114">常规运行时差异</span><span class="sxs-lookup"><span data-stu-id="b7d59-114">General runtime differences</span></span>  
  
-   <span data-ttu-id="b7d59-115">当一个应用在公共语言运行时 (CLR) 上运行时，由 JIT 编译器引起的 <xref:System.TypeLoadException>等异常在受到 [!INCLUDE[net_native](../../../includes/net-native-md.md)]处理时通常会产生编译时间错误。</span><span class="sxs-lookup"><span data-stu-id="b7d59-115">Exceptions, such as <xref:System.TypeLoadException>, that are thrown by the JIT compiler when an app runs on the common language runtime (CLR) generally result in compile-time errors when processed by [!INCLUDE[net_native](../../../includes/net-native-md.md)].</span></span>  
  
-   <span data-ttu-id="b7d59-116">请勿从一个应用的 UI 线程调用 <xref:System.GC.WaitForPendingFinalizers%2A?displayProperty=nameWithType> 方法。</span><span class="sxs-lookup"><span data-stu-id="b7d59-116">Don't call the <xref:System.GC.WaitForPendingFinalizers%2A?displayProperty=nameWithType> method from an app's UI thread.</span></span> <span data-ttu-id="b7d59-117">这可能会导致 [!INCLUDE[net_native](../../../includes/net-native-md.md)]发生死锁。</span><span class="sxs-lookup"><span data-stu-id="b7d59-117">This can result in a deadlock on [!INCLUDE[net_native](../../../includes/net-native-md.md)].</span></span>  
  
-   <span data-ttu-id="b7d59-118">请勿依赖静态类构造函数调用排序。</span><span class="sxs-lookup"><span data-stu-id="b7d59-118">Don't rely on static class constructor invocation ordering.</span></span> <span data-ttu-id="b7d59-119">在 [!INCLUDE[net_native](../../../includes/net-native-md.md)]中，调用排序与标准运行时的排序不同。</span><span class="sxs-lookup"><span data-stu-id="b7d59-119">In [!INCLUDE[net_native](../../../includes/net-native-md.md)], the invocation order is different from the order on the standard runtime.</span></span> <span data-ttu-id="b7d59-120">（即使可以使用标准运行时，你也不应依赖静态类构造函数的执行顺序。）</span><span class="sxs-lookup"><span data-stu-id="b7d59-120">(Even with the standard runtime, you shouldn't rely on the order of execution of static class constructors.)</span></span>  
  
-   <span data-ttu-id="b7d59-121">不在任何线程上执行调用（例如， `while(true);`）的无线循环可能会使应用异常终止。</span><span class="sxs-lookup"><span data-stu-id="b7d59-121">Infinite looping without making a call (for example, `while(true);`) on any thread may bring the app to a halt.</span></span> <span data-ttu-id="b7d59-122">同样，长期或无限等待也可能使应用异常终止。</span><span class="sxs-lookup"><span data-stu-id="b7d59-122">Similarly, large or infinite waits may bring the app to a halt.</span></span>  
  
-   <span data-ttu-id="b7d59-123">某些泛型初始化循环不会引起 [!INCLUDE[net_native](../../../includes/net-native-md.md)]的异常。</span><span class="sxs-lookup"><span data-stu-id="b7d59-123">Certain generic initialization cycles don't throw exceptions in [!INCLUDE[net_native](../../../includes/net-native-md.md)].</span></span> <span data-ttu-id="b7d59-124">例如，以下代码导致标准 CLR 上 <xref:System.TypeLoadException> 发生了一个异常。</span><span class="sxs-lookup"><span data-stu-id="b7d59-124">For example, the following code throws a <xref:System.TypeLoadException> exception on the standard CLR.</span></span> <span data-ttu-id="b7d59-125">在 [!INCLUDE[net_native](../../../includes/net-native-md.md)]中，不会出现此问题。</span><span class="sxs-lookup"><span data-stu-id="b7d59-125">In [!INCLUDE[net_native](../../../includes/net-native-md.md)], it doesn't.</span></span>  
  
     [!code-csharp[ProjectN#8](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/compat1.cs#8)]  
  
-   <span data-ttu-id="b7d59-126">在某些情况下， [!INCLUDE[net_native](../../../includes/net-native-md.md)] 提供 .NET Framework 类库的不同实施。</span><span class="sxs-lookup"><span data-stu-id="b7d59-126">In some cases, [!INCLUDE[net_native](../../../includes/net-native-md.md)] provides different implementations of .NET Framework class libraries.</span></span> <span data-ttu-id="b7d59-127">从一个方法返回的对象总是实施返回类型的成员。</span><span class="sxs-lookup"><span data-stu-id="b7d59-127">An object returned from a method will always implement the members of the returned type.</span></span> <span data-ttu-id="b7d59-128">然而，由于它的后备实施是不同的，你可能无法像在其他 .NET Framework 平台上的操作一样将其转换到相同的类型集。</span><span class="sxs-lookup"><span data-stu-id="b7d59-128">However, since its backing implementation is different, you may not be able to cast it to the same set of types as you could on other .NET Framework platforms.</span></span> <span data-ttu-id="b7d59-129">例如，在某些情况下，你可能无法将 <xref:System.Collections.Generic.IEnumerable%601> 或 <xref:System.Reflection.TypeInfo.DeclaredMembers%2A?displayProperty=nameWithType> 等方法返回的 <xref:System.Reflection.TypeInfo.DeclaredProperties%2A?displayProperty=nameWithType> 界面对象转换为 `T[]`。</span><span class="sxs-lookup"><span data-stu-id="b7d59-129">For example, in some cases, you may not be able to cast the <xref:System.Collections.Generic.IEnumerable%601> interface object returned by methods such as <xref:System.Reflection.TypeInfo.DeclaredMembers%2A?displayProperty=nameWithType> or <xref:System.Reflection.TypeInfo.DeclaredProperties%2A?displayProperty=nameWithType> to `T[]`.</span></span>  
  
-   <span data-ttu-id="b7d59-130">Windows 应用商店应用的 .NET 上的 WinInet 缓存不是默认启用的，但在 [!INCLUDE[net_native](../../../includes/net-native-md.md)]上是默认启用的。</span><span class="sxs-lookup"><span data-stu-id="b7d59-130">The WinInet cache isn't enabled by default on .NET for Windows Store apps, but it is on [!INCLUDE[net_native](../../../includes/net-native-md.md)].</span></span> <span data-ttu-id="b7d59-131">这提高了性能但会影响工作集。</span><span class="sxs-lookup"><span data-stu-id="b7d59-131">This improves performance but has working set implications.</span></span> <span data-ttu-id="b7d59-132">开发者无需执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="b7d59-132">No developer action is necessary.</span></span>  
  
<a name="Dynamic"></a>   
## <a name="dynamic-programming-differences"></a><span data-ttu-id="b7d59-133">动态编程差异</span><span class="sxs-lookup"><span data-stu-id="b7d59-133">Dynamic programming differences</span></span>  
 [!INCLUDE[net_native](../../../includes/net-native-md.md)]<span data-ttu-id="b7d59-134"> 静态链接来自 .NET Framework 的代码，从而使应用本地代码实现最佳性能。</span><span class="sxs-lookup"><span data-stu-id="b7d59-134"> statically links in code from the .NET Framework to make the code app-local for maximum performance.</span></span> <span data-ttu-id="b7d59-135">然而，由于二进制大小必须保持较小，这就使得整个 .NET Framework 无法进入。</span><span class="sxs-lookup"><span data-stu-id="b7d59-135">However, binary sizes have to remain small, so the entire .NET Framework can't be brought in.</span></span> <span data-ttu-id="b7d59-136">[!INCLUDE[net_native](../../../includes/net-native-md.md)] 编译器通过使用一个将引用移动到未使用代码的依赖减压器来解决这个限制。</span><span class="sxs-lookup"><span data-stu-id="b7d59-136">The [!INCLUDE[net_native](../../../includes/net-native-md.md)] compiler resolves this limitation by using a dependency reducer that removes references to unused code.</span></span> <span data-ttu-id="b7d59-137">然而，如果该信息无法在编译时被静态推断出，则 [!INCLUDE[net_native](../../../includes/net-native-md.md)] 无法维持或生成某些类型信息和代码，但是在运行时可动态检索。</span><span class="sxs-lookup"><span data-stu-id="b7d59-137">However, [!INCLUDE[net_native](../../../includes/net-native-md.md)] might not maintain or generate some type information and code when that information can't be inferred statically at compile time, but instead is retrieved dynamically at runtime.</span></span>  
  
 [!INCLUDE[net_native](../../../includes/net-native-md.md)]<span data-ttu-id="b7d59-138"> 可启用反射和动态编程。</span><span class="sxs-lookup"><span data-stu-id="b7d59-138"> does enable reflection and dynamic programming.</span></span> <span data-ttu-id="b7d59-139">然而，并非所有类型都可以标记为反射，因为这会导致生成的代码太大（尤其因为 .NET Framework 中支持反射到公共 API）。</span><span class="sxs-lookup"><span data-stu-id="b7d59-139">However, not all types can be marked for reflection, because this would make the generated code size too large (especially because reflecting on public APIs in the .NET Framework is supported).</span></span> <span data-ttu-id="b7d59-140">[!INCLUDE[net_native](../../../includes/net-native-md.md)] 编译器会明智地选择哪些类型应该支持反射，并为只这些类型保存元数据和生成代码。</span><span class="sxs-lookup"><span data-stu-id="b7d59-140">The [!INCLUDE[net_native](../../../includes/net-native-md.md)] compiler makes smart choices about which types should support reflection, and it keeps the metadata and generates code only for those types.</span></span>  
  
 <span data-ttu-id="b7d59-141">例如，绑定数据需要一个应用能够将属性名映射到函数。</span><span class="sxs-lookup"><span data-stu-id="b7d59-141">For example, data binding requires an app to be able to map property names to functions.</span></span> <span data-ttu-id="b7d59-142">在 Windows 应用商店应用的 .NET 中，公共语言运行时自动使用反射来向托管类型和公开可用的本机类型提供该能力。</span><span class="sxs-lookup"><span data-stu-id="b7d59-142">In .NET for Windows Store apps, the common language runtime automatically uses reflection to provide this capability for managed types and publicly available native types.</span></span> <span data-ttu-id="b7d59-143">在 [!INCLUDE[net_native](../../../includes/net-native-md.md)]中，编译器会自动添加你要向其绑定数据的类型的元数据。</span><span class="sxs-lookup"><span data-stu-id="b7d59-143">In [!INCLUDE[net_native](../../../includes/net-native-md.md)], the compiler automatically includes metadata for types to which you bind data.</span></span>  
  
 <span data-ttu-id="b7d59-144">[!INCLUDE[net_native](../../../includes/net-native-md.md)] 编译器还可以处理运行时无需任何提示或指令的常用泛型类型，比如 <xref:System.Collections.Generic.List%601> 和 <xref:System.Collections.Generic.Dictionary%602>。</span><span class="sxs-lookup"><span data-stu-id="b7d59-144">The [!INCLUDE[net_native](../../../includes/net-native-md.md)] compiler can also handle commonly used generic types such as <xref:System.Collections.Generic.List%601> and <xref:System.Collections.Generic.Dictionary%602>, which work without requiring any hints or directives.</span></span> <span data-ttu-id="b7d59-145">[动态](~/docs/csharp/language-reference/keywords/dynamic.md) 关键字在某些限制内也受到支持。</span><span class="sxs-lookup"><span data-stu-id="b7d59-145">The [dynamic](~/docs/csharp/language-reference/keywords/dynamic.md) keyword is also supported within certain limits.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b7d59-146">在将你的应用转到 [!INCLUDE[net_native](../../../includes/net-native-md.md)]时，应彻底测试所有动态代码路径。</span><span class="sxs-lookup"><span data-stu-id="b7d59-146">You should test all dynamic code paths thoroughly when porting your app to [!INCLUDE[net_native](../../../includes/net-native-md.md)].</span></span>  
  
 <span data-ttu-id="b7d59-147">[!INCLUDE[net_native](../../../includes/net-native-md.md)] 的默认配置对大多数开发者已经足够使用，但是有些开发者可能会想通过使用运行时指令 (.rd.xml) 文件来微调配置。</span><span class="sxs-lookup"><span data-stu-id="b7d59-147">The default configuration for [!INCLUDE[net_native](../../../includes/net-native-md.md)] is sufficient for most developers, but some developers might want to fine- tune their configurations by using a runtime directives (.rd.xml) file.</span></span> <span data-ttu-id="b7d59-148">此外，在某些情况下， [!INCLUDE[net_native](../../../includes/net-native-md.md)] 编译器无法确定反射必须使用哪些元数据并依赖提示，尤其是在以下情况下：</span><span class="sxs-lookup"><span data-stu-id="b7d59-148">In addition, in some cases, the [!INCLUDE[net_native](../../../includes/net-native-md.md)] compiler is unable to determine which metadata must be available for reflection and relies on hints, particularly in the following cases:</span></span>  
  
-   <span data-ttu-id="b7d59-149"><xref:System.Type.MakeGenericType%2A?displayProperty=nameWithType> 和 <xref:System.Reflection.MethodInfo.MakeGenericMethod%2A?displayProperty=nameWithType> 等一些构造无法静态确定。</span><span class="sxs-lookup"><span data-stu-id="b7d59-149">Some constructs like <xref:System.Type.MakeGenericType%2A?displayProperty=nameWithType> and <xref:System.Reflection.MethodInfo.MakeGenericMethod%2A?displayProperty=nameWithType> can't be determined statically.</span></span>  
  
-   <span data-ttu-id="b7d59-150">因为编译器无法确定实例化，因此你想要反射到的泛型类型必须通过运行时指令来指定。</span><span class="sxs-lookup"><span data-stu-id="b7d59-150">Because the compiler can't determine the instantiations, a generic type that you want to reflect on has to be specified by runtime directives.</span></span> <span data-ttu-id="b7d59-151">这并不仅是因为所有的代码必须包含在内，还因为在泛型类型上的反射会形成一个无限循环（例如，当某泛型方法在某泛型类型上调用时）。</span><span class="sxs-lookup"><span data-stu-id="b7d59-151">This isn't just because all code must be included, but because reflection on generic types can form an infinite cycle (for example, when a generic method is invoked on a generic type).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b7d59-152">运行时指令是在运行时指令 (.rd.xml) 文件中定义的。</span><span class="sxs-lookup"><span data-stu-id="b7d59-152">Runtime directives are defined in a runtime directives (.rd.xml) file.</span></span> <span data-ttu-id="b7d59-153">有关使用此文件的常规信息，请参阅[入门](../../../docs/framework/net-native/getting-started-with-net-native.md)。</span><span class="sxs-lookup"><span data-stu-id="b7d59-153">For general information about using this file, see [Getting Started](../../../docs/framework/net-native/getting-started-with-net-native.md).</span></span> <span data-ttu-id="b7d59-154">有关运行时指令的信息，请参阅 [Runtime Directives (rd.xml) Configuration File Reference](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)。</span><span class="sxs-lookup"><span data-stu-id="b7d59-154">For information about the runtime directives, see [Runtime Directives (rd.xml) Configuration File Reference](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md).</span></span>  
  
 [!INCLUDE[net_native](../../../includes/net-native-md.md)]<span data-ttu-id="b7d59-155"> 也包括配置文件工具，可帮助开发者确定默认集合之外哪些类型应支持反射。</span><span class="sxs-lookup"><span data-stu-id="b7d59-155"> also includes profiling tools that help the developer determine which types outside the default set should support reflection.</span></span>  
  
<a name="Reflection"></a>   
## <a name="other-reflection-related-differences"></a><span data-ttu-id="b7d59-156">其他与反射相关的差异</span><span class="sxs-lookup"><span data-stu-id="b7d59-156">Other reflection-related differences</span></span>  
 <span data-ttu-id="b7d59-157">Windows 应用商店应用的 .NET 和 [!INCLUDE[net_native](../../../includes/net-native-md.md)]的行为上存在许多其他单独的与反射有关的差异。</span><span class="sxs-lookup"><span data-stu-id="b7d59-157">There are a number of other individual reflection-related differences in behavior between the .NET for Windows Store apps and [!INCLUDE[net_native](../../../includes/net-native-md.md)].</span></span>  
  
 <span data-ttu-id="b7d59-158">在 [!INCLUDE[net_native](../../../includes/net-native-md.md)]中：</span><span class="sxs-lookup"><span data-stu-id="b7d59-158">In [!INCLUDE[net_native](../../../includes/net-native-md.md)]:</span></span>  
  
-   <span data-ttu-id="b7d59-159">反射到 .NET Framework 类库中的类型和成员的私有反射不受支持。</span><span class="sxs-lookup"><span data-stu-id="b7d59-159">Private reflection over types and members in the .NET Framework class library is not supported.</span></span> <span data-ttu-id="b7d59-160">然而，你可以反射到自己的私有类型和成员以及第三方库的类型和成员。</span><span class="sxs-lookup"><span data-stu-id="b7d59-160">You can, however, reflect over your own private types and members, as well as types and members in third-party libraries.</span></span>  
  
-   <span data-ttu-id="b7d59-161"><xref:System.Reflection.ParameterInfo.HasDefaultValue%2A?displayProperty=nameWithType> 属性为表示返回值的 `false` 对象正确返回 <xref:System.Reflection.ParameterInfo>。</span><span class="sxs-lookup"><span data-stu-id="b7d59-161">The <xref:System.Reflection.ParameterInfo.HasDefaultValue%2A?displayProperty=nameWithType> property correctly returns `false` for a <xref:System.Reflection.ParameterInfo> object that represents a return value.</span></span> <span data-ttu-id="b7d59-162">在 Windows 应用商店应用的 .NET 中，它返回 `true`。</span><span class="sxs-lookup"><span data-stu-id="b7d59-162">In the .NET for Windows Store apps, it returns `true`.</span></span> <span data-ttu-id="b7d59-163">中间语言 (IL) 不直接支持此操作，且解释需要由语言来进行。</span><span class="sxs-lookup"><span data-stu-id="b7d59-163">Intermediate language (IL) doesn’t support this directly, and interpretation is left to the language.</span></span>  
  
-   <span data-ttu-id="b7d59-164">位于 <xref:System.RuntimeFieldHandle> 和 <xref:System.RuntimeMethodHandle> 结构上的公共成员不受支持。</span><span class="sxs-lookup"><span data-stu-id="b7d59-164">Public members on the <xref:System.RuntimeFieldHandle> and <xref:System.RuntimeMethodHandle> structures aren't supported.</span></span> <span data-ttu-id="b7d59-165">这些受到支持的类型仅用于 LINQ、表达式树和静态阵列初始化。</span><span class="sxs-lookup"><span data-stu-id="b7d59-165">These types are supported only for LINQ, expression trees, and static array initialization.</span></span>  
  
-   <span data-ttu-id="b7d59-166"><xref:System.Reflection.RuntimeReflectionExtensions.GetRuntimeProperties%2A?displayProperty=nameWithType> 和 <xref:System.Reflection.RuntimeReflectionExtensions.GetRuntimeEvents%2A?displayProperty=nameWithType> 在基类中包含隐藏成员，因此可能会在没有显示重写的情况下遭到重写。</span><span class="sxs-lookup"><span data-stu-id="b7d59-166"><xref:System.Reflection.RuntimeReflectionExtensions.GetRuntimeProperties%2A?displayProperty=nameWithType> and <xref:System.Reflection.RuntimeReflectionExtensions.GetRuntimeEvents%2A?displayProperty=nameWithType> include hidden members in base classes and thus may be overridden without explicit overrides.</span></span> <span data-ttu-id="b7d59-167">这也适用于其他 [RuntimeReflectionExtensions.GetRuntime*](http://msdn.microsoft.com/library/system.reflection.runtimereflectionextensions_methods.aspx) 方法。</span><span class="sxs-lookup"><span data-stu-id="b7d59-167">This is also true of other [RuntimeReflectionExtensions.GetRuntime*](http://msdn.microsoft.com/library/system.reflection.runtimereflectionextensions_methods.aspx) methods.</span></span>  
  
-   <span data-ttu-id="b7d59-168"><xref:System.Type.MakeArrayType%2A?displayProperty=nameWithType> 和 <xref:System.Type.MakeByRefType%2A?displayProperty=nameWithType> 在你试图创建特定组合（例如，ByRef 阵列）时不会发生故障。</span><span class="sxs-lookup"><span data-stu-id="b7d59-168"><xref:System.Type.MakeArrayType%2A?displayProperty=nameWithType> and <xref:System.Type.MakeByRefType%2A?displayProperty=nameWithType> don't fail when you try to create certain combinations (for example, an array of byrefs).</span></span>  
  
-   <span data-ttu-id="b7d59-169">你无法使用反射来调用具有指针参数的成员。</span><span class="sxs-lookup"><span data-stu-id="b7d59-169">You can't use reflection to invoke members that have pointer parameters.</span></span>  
  
-   <span data-ttu-id="b7d59-170">你无法使用反射来获取或设置一个指针字段。</span><span class="sxs-lookup"><span data-stu-id="b7d59-170">You can't use reflection to get or set a pointer field.</span></span>  
  
-   <span data-ttu-id="b7d59-171">当参数计数错误并且其中一个参数类型不正确， [!INCLUDE[net_native](../../../includes/net-native-md.md)] 会引起 <xref:System.ArgumentException> 而不是 <xref:System.Reflection.TargetParameterCountException>。</span><span class="sxs-lookup"><span data-stu-id="b7d59-171">When the argument count is wrong and the type of one of the arguments is incorrect, [!INCLUDE[net_native](../../../includes/net-native-md.md)] throws an <xref:System.ArgumentException> instead of a <xref:System.Reflection.TargetParameterCountException>.</span></span>  
  
-   <span data-ttu-id="b7d59-172">异常的二进制序列化通常不受支持。</span><span class="sxs-lookup"><span data-stu-id="b7d59-172">Binary serialization of exceptions is generally not supported.</span></span> <span data-ttu-id="b7d59-173">因此，不可序列化的对象可添加到 <xref:System.Exception.Data%2A?displayProperty=nameWithType> 字典。</span><span class="sxs-lookup"><span data-stu-id="b7d59-173">As a result, non-serializable objects can be added to the <xref:System.Exception.Data%2A?displayProperty=nameWithType> dictionary.</span></span>  
  
<a name="Unsupported"></a>   
## <a name="unsupported-scenarios-and-apis"></a><span data-ttu-id="b7d59-174">不受支持的方案和 API</span><span class="sxs-lookup"><span data-stu-id="b7d59-174">Unsupported scenarios and APIs</span></span>  
 <span data-ttu-id="b7d59-175">以下部分列出了不受一般开发支持的方案和 API、互操作以及 HTTPClient 和 Windows Communication Foundation (WCF) 等技术：</span><span class="sxs-lookup"><span data-stu-id="b7d59-175">The following sections list unsupported scenarios and APIs for general development, interop, and technologies such as HTTPClient and Windows Communication Foundation (WCF):</span></span>  
  
-   [<span data-ttu-id="b7d59-176">常规开发</span><span class="sxs-lookup"><span data-stu-id="b7d59-176">General development</span></span>](#General)  
  
-   [<span data-ttu-id="b7d59-177">HttpClient</span><span class="sxs-lookup"><span data-stu-id="b7d59-177">HttpClient</span></span>](#HttpClient)  
  
-   [<span data-ttu-id="b7d59-178">Interop</span><span class="sxs-lookup"><span data-stu-id="b7d59-178">Interop</span></span>](#Interop)  
  
-   [<span data-ttu-id="b7d59-179">不受支持的 API</span><span class="sxs-lookup"><span data-stu-id="b7d59-179">Unsupported APIs</span></span>](#APIs)  
  
<a name="General"></a>   
### <a name="general-development-differences"></a><span data-ttu-id="b7d59-180">常规开发差异</span><span class="sxs-lookup"><span data-stu-id="b7d59-180">General development differences</span></span>  
 <span data-ttu-id="b7d59-181">**值类型**</span><span class="sxs-lookup"><span data-stu-id="b7d59-181">**Value types**</span></span>  
  
-   <span data-ttu-id="b7d59-182">如果你替代了一个值类型的 <xref:System.ValueType.Equals%2A?displayProperty=nameWithType> 和 <xref:System.ValueType.GetHashCode%2A?displayProperty=nameWithType> 方法，请勿调用基类实施。</span><span class="sxs-lookup"><span data-stu-id="b7d59-182">If you override the <xref:System.ValueType.Equals%2A?displayProperty=nameWithType> and <xref:System.ValueType.GetHashCode%2A?displayProperty=nameWithType> methods for a value type, don't call the base class implementations.</span></span> <span data-ttu-id="b7d59-183">在 Windows 应用商店应用的 .NET 中，这些方法依赖反射。</span><span class="sxs-lookup"><span data-stu-id="b7d59-183">In .NET for Windows Store apps, these methods rely on reflection.</span></span> <span data-ttu-id="b7d59-184">在编译时间， [!INCLUDE[net_native](../../../includes/net-native-md.md)] 会生成一个不依赖运行时反射的实施。</span><span class="sxs-lookup"><span data-stu-id="b7d59-184">At compile time, [!INCLUDE[net_native](../../../includes/net-native-md.md)] generates an implementation that doesn't rely on runtime reflection.</span></span> <span data-ttu-id="b7d59-185">这表示如果你不替代这两种方法，它们会以预计的方式运行，因为 [!INCLUDE[net_native](../../../includes/net-native-md.md)] 会在编译时间生成该实施。</span><span class="sxs-lookup"><span data-stu-id="b7d59-185">This means that if you don't override these two methods, they will work as expected, because [!INCLUDE[net_native](../../../includes/net-native-md.md)] generates the implementation at compile time.</span></span> <span data-ttu-id="b7d59-186">然而，替代这些方法并调用基类实施会产生一个异常。</span><span class="sxs-lookup"><span data-stu-id="b7d59-186">However, overriding these methods but calling the base class implementation results in an exception.</span></span>  
  
-   <span data-ttu-id="b7d59-187">大于 1 MB 的值类型不受支持。</span><span class="sxs-lookup"><span data-stu-id="b7d59-187">Value types larger than one megabyte aren't supported.</span></span>  
  
-   <span data-ttu-id="b7d59-188">在 [!INCLUDE[net_native](../../../includes/net-native-md.md)]中，值类型不能拥有默认构造函数。</span><span class="sxs-lookup"><span data-stu-id="b7d59-188">Value types can't have a default constructor in [!INCLUDE[net_native](../../../includes/net-native-md.md)].</span></span> <span data-ttu-id="b7d59-189">（C# 和 Visual Basic 禁止值类型拥有默认构造函数。</span><span class="sxs-lookup"><span data-stu-id="b7d59-189">(C# and Visual Basic prohibit default constructors on value types.</span></span> <span data-ttu-id="b7d59-190">然而，这些可以在 IL 中进行创建。）</span><span class="sxs-lookup"><span data-stu-id="b7d59-190">However, these can be created in IL.)</span></span>  
  
 <span data-ttu-id="b7d59-191">**数组**</span><span class="sxs-lookup"><span data-stu-id="b7d59-191">**Arrays**</span></span>  
  
-   <span data-ttu-id="b7d59-192">界限低于零的阵列不受支持。</span><span class="sxs-lookup"><span data-stu-id="b7d59-192">Arrays with a lower bound other than zero aren't supported.</span></span> <span data-ttu-id="b7d59-193">通常，这些阵列是通过调用 <xref:System.Array.CreateInstance%28System.Type%2CSystem.Int32%5B%5D%2CSystem.Int32%5B%5D%29?displayProperty=nameWithType> 重载来创建的。</span><span class="sxs-lookup"><span data-stu-id="b7d59-193">Typically, these arrays are created by calling the <xref:System.Array.CreateInstance%28System.Type%2CSystem.Int32%5B%5D%2CSystem.Int32%5B%5D%29?displayProperty=nameWithType> overload.</span></span>  
  
-   <span data-ttu-id="b7d59-194">不支持动态创建多维阵列。</span><span class="sxs-lookup"><span data-stu-id="b7d59-194">Dynamic creation of multidimensional arrays isn't supported.</span></span> <span data-ttu-id="b7d59-195">此类阵列一般是通过调用包括 <xref:System.Array.CreateInstance%2A?displayProperty=nameWithType> 参数的 `lengths` 方法重载来创建，或通过调用 <xref:System.Type.MakeArrayType%28System.Int32%29?displayProperty=nameWithType> 方法来创建。</span><span class="sxs-lookup"><span data-stu-id="b7d59-195">Such arrays are typically created by calling an overload of the <xref:System.Array.CreateInstance%2A?displayProperty=nameWithType> method that includes a `lengths` parameter, or by calling the <xref:System.Type.MakeArrayType%28System.Int32%29?displayProperty=nameWithType> method.</span></span>  
  
-   <span data-ttu-id="b7d59-196">四维或更多维的多维阵列不受支持；因为它们的 <xref:System.Array.Rank%2A?displayProperty=nameWithType> 属性值是四或者更大。</span><span class="sxs-lookup"><span data-stu-id="b7d59-196">Multidimensional arrays that have four or more dimensions aren't supported; that is, their <xref:System.Array.Rank%2A?displayProperty=nameWithType> property value is four or greater.</span></span> <span data-ttu-id="b7d59-197">可使用 [交错阵列](~/docs/csharp/programming-guide/arrays/jagged-arrays.md) （阵列的阵列）。</span><span class="sxs-lookup"><span data-stu-id="b7d59-197">Use [jagged arrays](~/docs/csharp/programming-guide/arrays/jagged-arrays.md) (an array of arrays) instead.</span></span> <span data-ttu-id="b7d59-198">例如， `array[x,y,z]` 无效，但 `array[x][y][z]` 有效。</span><span class="sxs-lookup"><span data-stu-id="b7d59-198">For example, `array[x,y,z]` is invalid, but `array[x][y][z]` isn't.</span></span>  
  
-   <span data-ttu-id="b7d59-199">多维阵列的差异不受支持且会在运行时导致 <xref:System.InvalidCastException> 异常。</span><span class="sxs-lookup"><span data-stu-id="b7d59-199">Variance for multidimensional arrays isn't supported and causes an <xref:System.InvalidCastException> exception at run time.</span></span>  
  
 <span data-ttu-id="b7d59-200">**泛型**</span><span class="sxs-lookup"><span data-stu-id="b7d59-200">**Generics**</span></span>  
  
-   <span data-ttu-id="b7d59-201">无限泛型类型扩展会导致编译器错误。</span><span class="sxs-lookup"><span data-stu-id="b7d59-201">Infinite generic type expansion results in a compiler error.</span></span> <span data-ttu-id="b7d59-202">例如，该代码无法编译：</span><span class="sxs-lookup"><span data-stu-id="b7d59-202">For example, this code fails to compile:</span></span>  
  
     [!code-csharp[ProjectN#9](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/compat2.cs#9)]  
  
 <span data-ttu-id="b7d59-203">**指针**</span><span class="sxs-lookup"><span data-stu-id="b7d59-203">**Pointers**</span></span>  
  
-   <span data-ttu-id="b7d59-204">指针阵列不受支持。</span><span class="sxs-lookup"><span data-stu-id="b7d59-204">Arrays of pointers aren't supported.</span></span>  
  
-   <span data-ttu-id="b7d59-205">你无法使用反射来获取或设置一个指针字段。</span><span class="sxs-lookup"><span data-stu-id="b7d59-205">You can't use reflection to get or set a pointer field.</span></span>  
  
 <span data-ttu-id="b7d59-206">**序列化**</span><span class="sxs-lookup"><span data-stu-id="b7d59-206">**Serialization**</span></span>  
  
 <span data-ttu-id="b7d59-207"><xref:System.Runtime.Serialization.KnownTypeAttribute.%23ctor%28System.String%29> 特性不受支持。</span><span class="sxs-lookup"><span data-stu-id="b7d59-207">The <xref:System.Runtime.Serialization.KnownTypeAttribute.%23ctor%28System.String%29> attribute isn't supported.</span></span> <span data-ttu-id="b7d59-208">使用 <xref:System.Runtime.Serialization.KnownTypeAttribute.%23ctor%28System.Type%29> 特性。</span><span class="sxs-lookup"><span data-stu-id="b7d59-208">Use the <xref:System.Runtime.Serialization.KnownTypeAttribute.%23ctor%28System.Type%29> attribute instead.</span></span>  
  
 <span data-ttu-id="b7d59-209">**资源**</span><span class="sxs-lookup"><span data-stu-id="b7d59-209">**Resources**</span></span>  
  
 <span data-ttu-id="b7d59-210">不支持使用带 <xref:System.Diagnostics.Tracing.EventSource> 类的本地化资源。</span><span class="sxs-lookup"><span data-stu-id="b7d59-210">The use of localized resources with the <xref:System.Diagnostics.Tracing.EventSource> class isn't supported.</span></span> <span data-ttu-id="b7d59-211"><xref:System.Diagnostics.Tracing.EventSourceAttribute.LocalizationResources%2A?displayProperty=nameWithType> 属性无法定义本地化资源。</span><span class="sxs-lookup"><span data-stu-id="b7d59-211">The <xref:System.Diagnostics.Tracing.EventSourceAttribute.LocalizationResources%2A?displayProperty=nameWithType> property doesn't define localized resources.</span></span>  
  
 <span data-ttu-id="b7d59-212">**委托**</span><span class="sxs-lookup"><span data-stu-id="b7d59-212">**Delegates**</span></span>  
  
 <span data-ttu-id="b7d59-213">`Delegate.BeginInvoke` 和 `Delegate.EndInvoke` 不受支持。</span><span class="sxs-lookup"><span data-stu-id="b7d59-213">`Delegate.BeginInvoke` and `Delegate.EndInvoke` aren't supported.</span></span>  
  
 <span data-ttu-id="b7d59-214">**Async**</span><span class="sxs-lookup"><span data-stu-id="b7d59-214">**Async**</span></span>  
  
 <span data-ttu-id="b7d59-215">Task IAsync 的重载中的线程逻辑不受支持。</span><span class="sxs-lookup"><span data-stu-id="b7d59-215">Threading logic in overloads of Task IAsync isn't supported.</span></span>  
  
 <span data-ttu-id="b7d59-216">**各种 API**</span><span class="sxs-lookup"><span data-stu-id="b7d59-216">**Miscellaneous APIs**</span></span>  
  
-   <span data-ttu-id="b7d59-217">如果 <xref:System.Reflection.TypeInfo.GUID%2A?displayProperty=nameWithType> 特性未应用于类型，<xref:System.PlatformNotSupportedException> 属性就会导致 <xref:System.Runtime.InteropServices.GuidAttribute> 异常。</span><span class="sxs-lookup"><span data-stu-id="b7d59-217">The <xref:System.Reflection.TypeInfo.GUID%2A?displayProperty=nameWithType> property throws a <xref:System.PlatformNotSupportedException> exception if a <xref:System.Runtime.InteropServices.GuidAttribute> attribute isn't applied to the type.</span></span> <span data-ttu-id="b7d59-218">GUID 主要用于 COM 支持。</span><span class="sxs-lookup"><span data-stu-id="b7d59-218">The GUID is used primarily for COM support.</span></span>  
  
-   <span data-ttu-id="b7d59-219"><xref:System.DateTime.Parse%2A?displayProperty=nameWithType> 方法会正确解析包含 [!INCLUDE[net_native](../../../includes/net-native-md.md)] 中短日期的字符串。</span><span class="sxs-lookup"><span data-stu-id="b7d59-219">The <xref:System.DateTime.Parse%2A?displayProperty=nameWithType> method correctly parses strings that contain short dates in [!INCLUDE[net_native](../../../includes/net-native-md.md)].</span></span> <span data-ttu-id="b7d59-220">然而，它不会继续兼容 Microsoft 知识库文章 [KB2803771](http://support.microsoft.com/kb/2803771) 和 [KB2803755](http://support.microsoft.com/kb/2803755)中描述的日期和时间解析的变更。</span><span class="sxs-lookup"><span data-stu-id="b7d59-220">However, it doesn't maintain compatibility with the changes in date and time parsing described in the Microsoft Knowledge Base articles [KB2803771](http://support.microsoft.com/kb/2803771) and [KB2803755](http://support.microsoft.com/kb/2803755).</span></span>  
  
-   <span data-ttu-id="b7d59-221"><xref:System.Numerics.BigInteger.ToString%2A?displayProperty=nameWithType>`("E")`中正确地舍入[!INCLUDE[net_native](../../../includes/net-native-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="b7d59-221"><xref:System.Numerics.BigInteger.ToString%2A?displayProperty=nameWithType> `("E")` is correctly rounded in [!INCLUDE[net_native](../../../includes/net-native-md.md)].</span></span> <span data-ttu-id="b7d59-222">在某些版本的 CLR 中，结果字符串会缩短，而不是舍入。</span><span class="sxs-lookup"><span data-stu-id="b7d59-222">In some versions of the CLR, the result string is truncated instead of rounded.</span></span>  
  
<a name="HttpClient"></a>   
### <a name="httpclient-differences"></a><span data-ttu-id="b7d59-223">HttpClient 差异</span><span class="sxs-lookup"><span data-stu-id="b7d59-223">HttpClient differences</span></span>  
 <span data-ttu-id="b7d59-224">在 [!INCLUDE[net_native](../../../includes/net-native-md.md)]中， <xref:System.Net.Http.HttpClientHandler> 类在内部使用 WinINet（通过 [HttpBaseProtocolFilter](http://msdn.microsoft.com/library/windows/apps/windows.web.http.filters.httpbaseprotocolfilter.aspx) 类），而不使用标准 .NET for Windows 应用商店应用中使用的 <xref:System.Net.WebRequest> 和 <xref:System.Net.WebResponse> 类。</span><span class="sxs-lookup"><span data-stu-id="b7d59-224">In [!INCLUDE[net_native](../../../includes/net-native-md.md)], the <xref:System.Net.Http.HttpClientHandler> class internally uses WinINet (through the [HttpBaseProtocolFilter](http://msdn.microsoft.com/library/windows/apps/windows.web.http.filters.httpbaseprotocolfilter.aspx) class) instead of the <xref:System.Net.WebRequest> and <xref:System.Net.WebResponse> classes used in the standard .NET for Windows Store apps.</span></span>  <span data-ttu-id="b7d59-225">WinINet 并不支持 <xref:System.Net.Http.HttpClientHandler> 类支持的所有配置选项。</span><span class="sxs-lookup"><span data-stu-id="b7d59-225">WinINet doesn't support all the configuration options that the <xref:System.Net.Http.HttpClientHandler> class supports.</span></span>  <span data-ttu-id="b7d59-226">因此：</span><span class="sxs-lookup"><span data-stu-id="b7d59-226">As a result:</span></span>  
  
-   <span data-ttu-id="b7d59-227"><xref:System.Net.Http.HttpClientHandler> 上的某些能力属性在 `false` 会返回 [!INCLUDE[net_native](../../../includes/net-native-md.md)]，而它们在 Windows 应用商店应用的标准 .NET 中返回 `true` 。</span><span class="sxs-lookup"><span data-stu-id="b7d59-227">Some of the capability properties on <xref:System.Net.Http.HttpClientHandler> return `false` on [!INCLUDE[net_native](../../../includes/net-native-md.md)], whereas they return `true` in the standard .NET for Windows Store apps.</span></span>  
  
-   <span data-ttu-id="b7d59-228">某些配置属性 `get` 访问器始终在 [!INCLUDE[net_native](../../../includes/net-native-md.md)] 上返回固定值，而此固定值不同于 Windows 应用商店应用的 .NET 中的默认可配置值。</span><span class="sxs-lookup"><span data-stu-id="b7d59-228">Some of the configuration property `get` accessors always return a fixed value on [!INCLUDE[net_native](../../../includes/net-native-md.md)] that is different than the default configurable value in .NET for Windows Store apps.</span></span>  
  
 <span data-ttu-id="b7d59-229">某些额外的行为差异涵盖在以下子节中。</span><span class="sxs-lookup"><span data-stu-id="b7d59-229">Some additional behavior differences are covered in the following subsections.</span></span>  
  
 <span data-ttu-id="b7d59-230">**代理**</span><span class="sxs-lookup"><span data-stu-id="b7d59-230">**Proxy**</span></span>  
  
 <span data-ttu-id="b7d59-231">[HttpBaseProtocolFilter](http://msdn.microsoft.com/library/windows/apps/windows.web.http.filters.httpbaseprotocolfilter.aspx) 类不支持基于每个请求配置或重写代理。</span><span class="sxs-lookup"><span data-stu-id="b7d59-231">The [HttpBaseProtocolFilter](http://msdn.microsoft.com/library/windows/apps/windows.web.http.filters.httpbaseprotocolfilter.aspx) class doesn’t support configuring or overriding the proxy on a per-request basis.</span></span>  <span data-ttu-id="b7d59-232">这意味着 [!INCLUDE[net_native](../../../includes/net-native-md.md)] 上的所有请求都使用系统配置的代理服务器或没有代理服务器，具体取决于 <xref:System.Net.Http.HttpClientHandler.UseProxy%2A?displayProperty=nameWithType> 属性的值。</span><span class="sxs-lookup"><span data-stu-id="b7d59-232">This means that all requests on [!INCLUDE[net_native](../../../includes/net-native-md.md)] use the system-configured proxy server or no proxy server, depending on the value of the <xref:System.Net.Http.HttpClientHandler.UseProxy%2A?displayProperty=nameWithType> property.</span></span>  <span data-ttu-id="b7d59-233">在 Windows 应用商店应用的 .NET 中，代理服务器由 <xref:System.Net.Http.HttpClientHandler.Proxy%2A?displayProperty=nameWithType> 属性定义。</span><span class="sxs-lookup"><span data-stu-id="b7d59-233">In .NET for Windows Store apps, the proxy server is defined by the <xref:System.Net.Http.HttpClientHandler.Proxy%2A?displayProperty=nameWithType> property.</span></span>  <span data-ttu-id="b7d59-234">在 [!INCLUDE[net_native](../../../includes/net-native-md.md)] 上，如果将 <xref:System.Net.Http.HttpClientHandler.Proxy%2A?displayProperty=nameWithType> 值设置为 `null` 以外的值，将导致 <xref:System.PlatformNotSupportedException> 异常。</span><span class="sxs-lookup"><span data-stu-id="b7d59-234">On [!INCLUDE[net_native](../../../includes/net-native-md.md)], setting the <xref:System.Net.Http.HttpClientHandler.Proxy%2A?displayProperty=nameWithType> to a value other than `null` throws a <xref:System.PlatformNotSupportedException> exception.</span></span>  <span data-ttu-id="b7d59-235"><xref:System.Net.Http.HttpClientHandler.SupportsProxy%2A?displayProperty=nameWithType> 属性在 `false` 上返回 [!INCLUDE[net_native](../../../includes/net-native-md.md)]，而在 Windows 应用商店应用的标准 .NET Framework 中返回 `true`。</span><span class="sxs-lookup"><span data-stu-id="b7d59-235">The <xref:System.Net.Http.HttpClientHandler.SupportsProxy%2A?displayProperty=nameWithType> property returns `false` on [!INCLUDE[net_native](../../../includes/net-native-md.md)], whereas it returns `true` in the standard .NET Framework for Windows Store apps.</span></span>  
  
 <span data-ttu-id="b7d59-236">**自动重定向**</span><span class="sxs-lookup"><span data-stu-id="b7d59-236">**Automatic redirection**</span></span>  
  
 <span data-ttu-id="b7d59-237">[HttpBaseProtocolFilter](http://msdn.microsoft.com/library/windows/apps/windows.web.http.filters.httpbaseprotocolfilter.aspx) 类不允许配置自动重新定向的最大数目。</span><span class="sxs-lookup"><span data-stu-id="b7d59-237">The [HttpBaseProtocolFilter](http://msdn.microsoft.com/library/windows/apps/windows.web.http.filters.httpbaseprotocolfilter.aspx) class doesn't allow the maximum number of automatic redirections to be configured.</span></span>  <span data-ttu-id="b7d59-238">Windows 应用商店应用的标准 .NET 中 <xref:System.Net.Http.HttpClientHandler.MaxAutomaticRedirections%2A?displayProperty=nameWithType> 属性的值默认为 50，且可修改。</span><span class="sxs-lookup"><span data-stu-id="b7d59-238">The value of the <xref:System.Net.Http.HttpClientHandler.MaxAutomaticRedirections%2A?displayProperty=nameWithType> property is 50 by default in the standard .NET for Windows Store apps and can be modified.</span></span> <span data-ttu-id="b7d59-239">在 [!INCLUDE[net_native](../../../includes/net-native-md.md)]，此属性的值为 10，修改该值会导致 <xref:System.PlatformNotSupportedException> 异常。</span><span class="sxs-lookup"><span data-stu-id="b7d59-239">On [!INCLUDE[net_native](../../../includes/net-native-md.md)], the value of this property is 10, and trying to modify it throws a <xref:System.PlatformNotSupportedException> exception.</span></span>  <span data-ttu-id="b7d59-240"><xref:System.Net.Http.HttpClientHandler.SupportsRedirectConfiguration%2A?displayProperty=nameWithType> 属性在 `false` 上返回 [!INCLUDE[net_native](../../../includes/net-native-md.md)]，而在 Windows 应用商店应用的 .NET 中返回 `true`。</span><span class="sxs-lookup"><span data-stu-id="b7d59-240">The <xref:System.Net.Http.HttpClientHandler.SupportsRedirectConfiguration%2A?displayProperty=nameWithType> property returns `false` on [!INCLUDE[net_native](../../../includes/net-native-md.md)], whereas it returns `true` in .NET for Windows Store apps.</span></span>  
  
 <span data-ttu-id="b7d59-241">**自动解压缩**</span><span class="sxs-lookup"><span data-stu-id="b7d59-241">**Automatic decompression**</span></span>  
  
 <span data-ttu-id="b7d59-242">Windows 应用商店应用的 .NET 支持将 <xref:System.Net.Http.HttpClientHandler.AutomaticDecompression%2A?displayProperty=nameWithType> 属性设置为 <xref:System.Net.DecompressionMethods.Deflate>、<xref:System.Net.DecompressionMethods.GZip>（<xref:System.Net.DecompressionMethods.Deflate> 和 <xref:System.Net.DecompressionMethods.GZip> 都可以）或 <xref:System.Net.DecompressionMethods.None>。</span><span class="sxs-lookup"><span data-stu-id="b7d59-242">.NET for Windows Store apps allows you to set the <xref:System.Net.Http.HttpClientHandler.AutomaticDecompression%2A?displayProperty=nameWithType> property to <xref:System.Net.DecompressionMethods.Deflate>, <xref:System.Net.DecompressionMethods.GZip>, both <xref:System.Net.DecompressionMethods.Deflate> and <xref:System.Net.DecompressionMethods.GZip>, or <xref:System.Net.DecompressionMethods.None>.</span></span>  [!INCLUDE[net_native](../../../includes/net-native-md.md)]<span data-ttu-id="b7d59-243"> 仅支持 <xref:System.Net.DecompressionMethods.Deflate> 与 <xref:System.Net.DecompressionMethods.GZip>或 <xref:System.Net.DecompressionMethods.None>。</span><span class="sxs-lookup"><span data-stu-id="b7d59-243"> only supports <xref:System.Net.DecompressionMethods.Deflate> together with <xref:System.Net.DecompressionMethods.GZip>, or <xref:System.Net.DecompressionMethods.None>.</span></span>  <span data-ttu-id="b7d59-244">尝试仅将 <xref:System.Net.Http.HttpClientHandler.AutomaticDecompression%2A> 属性设置为 <xref:System.Net.DecompressionMethods.Deflate> 或 <xref:System.Net.DecompressionMethods.GZip> 会自动将其设置为 <xref:System.Net.DecompressionMethods.Deflate> 和 <xref:System.Net.DecompressionMethods.GZip>。</span><span class="sxs-lookup"><span data-stu-id="b7d59-244">Trying to set the <xref:System.Net.Http.HttpClientHandler.AutomaticDecompression%2A> property to either <xref:System.Net.DecompressionMethods.Deflate> or <xref:System.Net.DecompressionMethods.GZip> alone silently sets it to both <xref:System.Net.DecompressionMethods.Deflate> and <xref:System.Net.DecompressionMethods.GZip>.</span></span>  
  
 <span data-ttu-id="b7d59-245">**Cookie**</span><span class="sxs-lookup"><span data-stu-id="b7d59-245">**Cookies**</span></span>  
  
 <span data-ttu-id="b7d59-246">Cookie 处理由 <xref:System.Net.Http.HttpClient> 和 WinINet 同时执行。</span><span class="sxs-lookup"><span data-stu-id="b7d59-246">Cookie handling is performed simultaneously by <xref:System.Net.Http.HttpClient> and WinINet.</span></span>  <span data-ttu-id="b7d59-247">来自 <xref:System.Net.CookieContainer> 的 Cookies 与 WinINet cookie 缓存结合。</span><span class="sxs-lookup"><span data-stu-id="b7d59-247">Cookies from the <xref:System.Net.CookieContainer> are combined with cookies in the WinINet cookie cache.</span></span>  <span data-ttu-id="b7d59-248">从 <xref:System.Net.CookieContainer> 删除 cookie 可防止 <xref:System.Net.Http.HttpClient> 发送 cookie，但如果 cookie 已被 WinINet 检测到且 cookies 未被用户删除，则 WinINet 将会发送 cookie。</span><span class="sxs-lookup"><span data-stu-id="b7d59-248">Removing a cookie from <xref:System.Net.CookieContainer> prevents <xref:System.Net.Http.HttpClient> from sending the cookie, but if the cookie was already seen by WinINet, and cookies weren't deleted by the user, WinINet sends it.</span></span>  <span data-ttu-id="b7d59-249">无法通过编程的方式使用 <xref:System.Net.Http.HttpClient>、 <xref:System.Net.Http.HttpClientHandler>或 <xref:System.Net.CookieContainer> API 从 WinINet 中删除 cookie。</span><span class="sxs-lookup"><span data-stu-id="b7d59-249">It isn't possible to programmatically remove a cookie from WinINet by using the <xref:System.Net.Http.HttpClient>, <xref:System.Net.Http.HttpClientHandler>, or <xref:System.Net.CookieContainer> API.</span></span>  <span data-ttu-id="b7d59-250">将 <xref:System.Net.Http.HttpClientHandler.UseCookies%2A?displayProperty=nameWithType> 属性设置为 `false` 只会导致 <xref:System.Net.Http.HttpClient> 停止发送 cookies；WinINet 仍可能会在请求中包括 cookies。</span><span class="sxs-lookup"><span data-stu-id="b7d59-250">Setting the <xref:System.Net.Http.HttpClientHandler.UseCookies%2A?displayProperty=nameWithType> property to `false` causes only <xref:System.Net.Http.HttpClient> to stop sending cookies; WinINet might still include its cookies in the request.</span></span>  
  
 <span data-ttu-id="b7d59-251">**凭据**</span><span class="sxs-lookup"><span data-stu-id="b7d59-251">**Credentials**</span></span>  
  
 <span data-ttu-id="b7d59-252">在 Windows 应用商店应用的 .NET 中，<xref:System.Net.Http.HttpClientHandler.UseDefaultCredentials%2A?displayProperty=nameWithType> 和 <xref:System.Net.Http.HttpClientHandler.Credentials%2A?displayProperty=nameWithType> 属性独立工作。</span><span class="sxs-lookup"><span data-stu-id="b7d59-252">In .NET for Windows Store apps, the <xref:System.Net.Http.HttpClientHandler.UseDefaultCredentials%2A?displayProperty=nameWithType> and <xref:System.Net.Http.HttpClientHandler.Credentials%2A?displayProperty=nameWithType> properties work independently.</span></span>  <span data-ttu-id="b7d59-253">此外， <xref:System.Net.Http.HttpClientHandler.Credentials%2A> 属性接受实施 <xref:System.Net.ICredentials> 接口的任意对象。</span><span class="sxs-lookup"><span data-stu-id="b7d59-253">Additionally, the <xref:System.Net.Http.HttpClientHandler.Credentials%2A> property accepts any object that implements the <xref:System.Net.ICredentials> interface.</span></span>  <span data-ttu-id="b7d59-254">在 [!INCLUDE[net_native](../../../includes/net-native-md.md)]，设置 <xref:System.Net.Http.HttpClientHandler.UseDefaultCredentials%2A> 属性为 `true` 会导致 <xref:System.Net.Http.HttpClientHandler.Credentials%2A> 属性变为 `null`。</span><span class="sxs-lookup"><span data-stu-id="b7d59-254">In [!INCLUDE[net_native](../../../includes/net-native-md.md)], setting the <xref:System.Net.Http.HttpClientHandler.UseDefaultCredentials%2A> property to `true` causes the <xref:System.Net.Http.HttpClientHandler.Credentials%2A> property to become `null`.</span></span>  <span data-ttu-id="b7d59-255">此外， <xref:System.Net.Http.HttpClientHandler.Credentials%2A> 属性只能设置为 `null`、 <xref:System.Net.CredentialCache.DefaultCredentials%2A>或类型 <xref:System.Net.NetworkCredential>的对象。</span><span class="sxs-lookup"><span data-stu-id="b7d59-255">In addition, the <xref:System.Net.Http.HttpClientHandler.Credentials%2A> property can be set only to `null`, <xref:System.Net.CredentialCache.DefaultCredentials%2A>, or an object of type <xref:System.Net.NetworkCredential>.</span></span>  <span data-ttu-id="b7d59-256">将其他任意 <xref:System.Net.ICredentials> 对象（其中最常见的是 <xref:System.Net.CredentialCache>）分配至 <xref:System.Net.Http.HttpClientHandler.Credentials%2A> 属性都会导致 <xref:System.PlatformNotSupportedException>。</span><span class="sxs-lookup"><span data-stu-id="b7d59-256">Assigning any other <xref:System.Net.ICredentials> object, the most popular of which is <xref:System.Net.CredentialCache>, to the <xref:System.Net.Http.HttpClientHandler.Credentials%2A> property throws a <xref:System.PlatformNotSupportedException>.</span></span>  
  
 <span data-ttu-id="b7d59-257">**其他不受支持或不可配置的功能**</span><span class="sxs-lookup"><span data-stu-id="b7d59-257">**Other unsupported or unconfigurable features**</span></span>  
  
 <span data-ttu-id="b7d59-258">在 [!INCLUDE[net_native](../../../includes/net-native-md.md)]中：</span><span class="sxs-lookup"><span data-stu-id="b7d59-258">In [!INCLUDE[net_native](../../../includes/net-native-md.md)]:</span></span>  
  
-   <span data-ttu-id="b7d59-259"><xref:System.Net.Http.HttpClientHandler.ClientCertificateOptions%2A?displayProperty=nameWithType> 属性的值始终为 <xref:System.Net.Http.ClientCertificateOption.Automatic>。</span><span class="sxs-lookup"><span data-stu-id="b7d59-259">The value of the <xref:System.Net.Http.HttpClientHandler.ClientCertificateOptions%2A?displayProperty=nameWithType> property is always <xref:System.Net.Http.ClientCertificateOption.Automatic>.</span></span>  <span data-ttu-id="b7d59-260">在 Windows 应用商店应用的 .NET 中，默认为 <xref:System.Net.Http.ClientCertificateOption.Manual>。</span><span class="sxs-lookup"><span data-stu-id="b7d59-260">In .NET for Windows Store apps, the default is <xref:System.Net.Http.ClientCertificateOption.Manual>.</span></span>  
  
-   <span data-ttu-id="b7d59-261"><xref:System.Net.Http.HttpClientHandler.MaxRequestContentBufferSize%2A?displayProperty=nameWithType> 属性无法配置。</span><span class="sxs-lookup"><span data-stu-id="b7d59-261">The <xref:System.Net.Http.HttpClientHandler.MaxRequestContentBufferSize%2A?displayProperty=nameWithType> property isn't configurable.</span></span>  
  
-   <span data-ttu-id="b7d59-262"><xref:System.Net.Http.HttpClientHandler.PreAuthenticate%2A?displayProperty=nameWithType> 属性始终为 `true`。</span><span class="sxs-lookup"><span data-stu-id="b7d59-262">The <xref:System.Net.Http.HttpClientHandler.PreAuthenticate%2A?displayProperty=nameWithType> property is always `true`.</span></span>  <span data-ttu-id="b7d59-263">在 Windows 应用商店应用的 .NET 中，默认为 `false`。</span><span class="sxs-lookup"><span data-stu-id="b7d59-263">In .NET for Windows Store apps, the default is `false`.</span></span>  
  
-   <span data-ttu-id="b7d59-264">响应中的 `SetCookie2` 标题忽略为废弃。</span><span class="sxs-lookup"><span data-stu-id="b7d59-264">The `SetCookie2` header in responses is ignored as obsolete.</span></span>  
  
<a name="Interop"></a>   
### <a name="interop-differences"></a><span data-ttu-id="b7d59-265">互操作差异性</span><span class="sxs-lookup"><span data-stu-id="b7d59-265">Interop differences</span></span>  
 <span data-ttu-id="b7d59-266">**弃用的 API**</span><span class="sxs-lookup"><span data-stu-id="b7d59-266">**Deprecated APIs**</span></span>  
  
 <span data-ttu-id="b7d59-267">多个带有托管代码的不常使用的互操作性 API 已弃用。</span><span class="sxs-lookup"><span data-stu-id="b7d59-267">A number of infrequently used APIs for interoperability with managed code have been deprecated.</span></span> <span data-ttu-id="b7d59-268">与 [!INCLUDE[net_native](../../../includes/net-native-md.md)]共同使用时，这些 API 会引起 <xref:System.NotImplementedException> 或 <xref:System.PlatformNotSupportedException> 异常，或导致编译器错误。</span><span class="sxs-lookup"><span data-stu-id="b7d59-268">When used with [!INCLUDE[net_native](../../../includes/net-native-md.md)], these APIs may throw a <xref:System.NotImplementedException> or <xref:System.PlatformNotSupportedException> exception, or result in a compiler error.</span></span> <span data-ttu-id="b7d59-269">在 Windows 应用商店应用的 .NET 中，这些 API 标记为废弃，尽管调用这些 API 会生成编译器警告而非编译器错误。</span><span class="sxs-lookup"><span data-stu-id="b7d59-269">In .NET for Windows Store apps, these APIs are marked as obsolete, although calling them generates a compiler warning rather than a compiler error.</span></span>  
  
 <span data-ttu-id="b7d59-270">`VARIANT` 封送的废弃 API：</span><span class="sxs-lookup"><span data-stu-id="b7d59-270">Deprecated APIs for `VARIANT` marshaling:</span></span>  
  
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
  
 <span data-ttu-id="b7d59-271"><xref:System.Runtime.InteropServices.UnmanagedType.Struct?displayProperty=nameWithType>支持，但某些情况下，例如与一起使用时引发了异常[IDispatch](http://msdn.microsoft.com/library/windows/apps/ms221608.aspx)或 byref 变量。</span><span class="sxs-lookup"><span data-stu-id="b7d59-271"><xref:System.Runtime.InteropServices.UnmanagedType.Struct?displayProperty=nameWithType> is supported, but it throws an exception in some scenarios, such as when it is used with [IDispatch](http://msdn.microsoft.com/library/windows/apps/ms221608.aspx) or byref variants.</span></span>  
  
 <span data-ttu-id="b7d59-272">不推荐将 API 用于 [IDispatch](http://msdn.microsoft.com/library/windows/apps/ms221608.aspx) 支持：</span><span class="sxs-lookup"><span data-stu-id="b7d59-272">Deprecated APIs for [IDispatch](http://msdn.microsoft.com/library/windows/apps/ms221608.aspx) support:</span></span>  
  
|<span data-ttu-id="b7d59-273">类型</span><span class="sxs-lookup"><span data-stu-id="b7d59-273">Type</span></span>|<span data-ttu-id="b7d59-274">成员</span><span class="sxs-lookup"><span data-stu-id="b7d59-274">Member</span></span>|  
|----------|------------|  
|<xref:System.Runtime.InteropServices.ClassInterfaceType?displayProperty=nameWithType>|<xref:System.Runtime.InteropServices.ClassInterfaceType.AutoDispatch>|  
|<xref:System.Runtime.InteropServices.ClassInterfaceType?displayProperty=nameWithType>|<xref:System.Runtime.InteropServices.ClassInterfaceType.AutoDual>|  
|<xref:System.Runtime.InteropServices.ComDefaultInterfaceAttribute?displayProperty=nameWithType>|<span data-ttu-id="b7d59-275">特性不受支持</span><span class="sxs-lookup"><span data-stu-id="b7d59-275">Attribute isn't supported</span></span>|  
  
 <span data-ttu-id="b7d59-276">用于经典 COM 事件的弃用的 API：</span><span class="sxs-lookup"><span data-stu-id="b7d59-276">Deprecated APIs for classic COM events:</span></span>  
  
||  
|-|  
|<xref:System.Runtime.InteropServices.ComEventsHelper?displayProperty=nameWithType>|  
|<xref:System.Runtime.InteropServices.ComSourceInterfacesAttribute>|  
  
 <span data-ttu-id="b7d59-277"><xref:System.Runtime.InteropServices.ICustomQueryInterface?displayProperty=nameWithType> 接口中弃用的 API（在 [!INCLUDE[net_native](../../../includes/net-native-md.md)] 中不受支持）：</span><span class="sxs-lookup"><span data-stu-id="b7d59-277">Deprecated APIs in the <xref:System.Runtime.InteropServices.ICustomQueryInterface?displayProperty=nameWithType> interface, which isn't supported in [!INCLUDE[net_native](../../../includes/net-native-md.md)]:</span></span>  
  
|<span data-ttu-id="b7d59-278">类型</span><span class="sxs-lookup"><span data-stu-id="b7d59-278">Type</span></span>|<span data-ttu-id="b7d59-279">成员</span><span class="sxs-lookup"><span data-stu-id="b7d59-279">Member</span></span>|  
|----------|------------|  
|<xref:System.Runtime.InteropServices.ICustomQueryInterface?displayProperty=nameWithType>|<span data-ttu-id="b7d59-280">所有成员。</span><span class="sxs-lookup"><span data-stu-id="b7d59-280">All members.</span></span>|  
|<xref:System.Runtime.InteropServices.CustomQueryInterfaceMode?displayProperty=nameWithType>|<span data-ttu-id="b7d59-281">所有成员。</span><span class="sxs-lookup"><span data-stu-id="b7d59-281">All members.</span></span>|  
|<xref:System.Runtime.InteropServices.CustomQueryInterfaceResult?displayProperty=nameWithType>|<span data-ttu-id="b7d59-282">所有成员。</span><span class="sxs-lookup"><span data-stu-id="b7d59-282">All members.</span></span>|  
|<xref:System.Runtime.InteropServices.Marshal?displayProperty=nameWithType>|<xref:System.Runtime.InteropServices.Marshal.GetComInterfaceForObject%28System.Object%2CSystem.Type%2CSystem.Runtime.InteropServices.CustomQueryInterfaceMode%29?displayProperty=nameWithType>|  
  
 <span data-ttu-id="b7d59-283">其他不受支持的互操作性功能：</span><span class="sxs-lookup"><span data-stu-id="b7d59-283">Other unsupported interop features:</span></span>  
  
|<span data-ttu-id="b7d59-284">类型</span><span class="sxs-lookup"><span data-stu-id="b7d59-284">Type</span></span>|<span data-ttu-id="b7d59-285">成员</span><span class="sxs-lookup"><span data-stu-id="b7d59-285">Member</span></span>|  
|----------|------------|  
|<xref:System.Runtime.InteropServices.ICustomAdapter?displayProperty=nameWithType>|<span data-ttu-id="b7d59-286">所有成员。</span><span class="sxs-lookup"><span data-stu-id="b7d59-286">All members.</span></span>|  
|<xref:System.Runtime.InteropServices.SafeBuffer?displayProperty=nameWithType>|<span data-ttu-id="b7d59-287">所有成员。</span><span class="sxs-lookup"><span data-stu-id="b7d59-287">All members.</span></span>|  
|<xref:System.Runtime.InteropServices.UnmanagedType?displayProperty=nameWithType>|<xref:System.Runtime.InteropServices.UnmanagedType.Currency>|  
|<xref:System.Runtime.InteropServices.UnmanagedType?displayProperty=nameWithType>|<xref:System.Runtime.InteropServices.UnmanagedType.VBByRefStr>|  
|<xref:System.Runtime.InteropServices.UnmanagedType?displayProperty=nameWithType>|<xref:System.Runtime.InteropServices.UnmanagedType.AnsiBStr>|  
|<xref:System.Runtime.InteropServices.UnmanagedType?displayProperty=nameWithType>|<xref:System.Runtime.InteropServices.UnmanagedType.AsAny>|  
|<xref:System.Runtime.InteropServices.UnmanagedType?displayProperty=nameWithType>|<xref:System.Runtime.InteropServices.UnmanagedType.CustomMarshaler>|  
  
 <span data-ttu-id="b7d59-288">很少使用的封送 API：</span><span class="sxs-lookup"><span data-stu-id="b7d59-288">Rarely used marshalling APIs:</span></span>  
  
|<span data-ttu-id="b7d59-289">类型</span><span class="sxs-lookup"><span data-stu-id="b7d59-289">Type</span></span>|<span data-ttu-id="b7d59-290">成员</span><span class="sxs-lookup"><span data-stu-id="b7d59-290">Member</span></span>|  
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
  
 <span data-ttu-id="b7d59-291">**平台调用和 COM 互操作兼容性**</span><span class="sxs-lookup"><span data-stu-id="b7d59-291">**Platform invoke and COM interop compatibility**</span></span>  
  
 <span data-ttu-id="b7d59-292">大多数平台调用和 COM 互操作情景在 [!INCLUDE[net_native](../../../includes/net-native-md.md)]中仍受支持。</span><span class="sxs-lookup"><span data-stu-id="b7d59-292">Most platform invoke and COM interop scenarios are still supported in [!INCLUDE[net_native](../../../includes/net-native-md.md)].</span></span> <span data-ttu-id="b7d59-293">特别地，Windows Runtime (WinRT) API 的所有互操作和 Windows Runtime 所需的所有封送都受支持。</span><span class="sxs-lookup"><span data-stu-id="b7d59-293">In particular, all interoperability with Windows Runtime (WinRT) APIs and all marshaling required for the Windows Runtime is supported.</span></span> <span data-ttu-id="b7d59-294">这包括针对以下内容的封送支持：</span><span class="sxs-lookup"><span data-stu-id="b7d59-294">This includes marshaling support for:</span></span>  
  
-   <span data-ttu-id="b7d59-295">阵列（包括 <xref:System.Runtime.InteropServices.UnmanagedType.ByValArray?displayProperty=nameWithType>）</span><span class="sxs-lookup"><span data-stu-id="b7d59-295">Arrays (including <xref:System.Runtime.InteropServices.UnmanagedType.ByValArray?displayProperty=nameWithType>)</span></span>  
  
-   `BStr`  
  
-   <span data-ttu-id="b7d59-296">委托</span><span class="sxs-lookup"><span data-stu-id="b7d59-296">Delegates</span></span>  
  
-   <span data-ttu-id="b7d59-297">字符串（Unicode、Ansi 和 HSTRING）</span><span class="sxs-lookup"><span data-stu-id="b7d59-297">Strings (Unicode, Ansi, and HSTRING)</span></span>  
  
-   <span data-ttu-id="b7d59-298">结构（`byref` 和 `byval`）</span><span class="sxs-lookup"><span data-stu-id="b7d59-298">Structs (`byref` and `byval`)</span></span>  
  
-   <span data-ttu-id="b7d59-299">Unions</span><span class="sxs-lookup"><span data-stu-id="b7d59-299">Unions</span></span>  
  
-   <span data-ttu-id="b7d59-300">Win32 句柄</span><span class="sxs-lookup"><span data-stu-id="b7d59-300">Win32 handles</span></span>  
  
-   <span data-ttu-id="b7d59-301">所有 WinRT 构造</span><span class="sxs-lookup"><span data-stu-id="b7d59-301">All WinRT constructs</span></span>  
  
-   <span data-ttu-id="b7d59-302">部分支持封送变体类型。</span><span class="sxs-lookup"><span data-stu-id="b7d59-302">Partial support for marshaling variant types.</span></span> <span data-ttu-id="b7d59-303">以下内容受到支持：</span><span class="sxs-lookup"><span data-stu-id="b7d59-303">The following are supported:</span></span>  
  
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
  
    -   [<span data-ttu-id="b7d59-304">IUnknown</span><span class="sxs-lookup"><span data-stu-id="b7d59-304">IUnknown</span></span>](http://msdn.microsoft.com/library/windows/desktop/ms680509.aspx)  
  
 <span data-ttu-id="b7d59-305">然而， [!INCLUDE[net_native](../../../includes/net-native-md.md)] 不支持以下内容：</span><span class="sxs-lookup"><span data-stu-id="b7d59-305">However, [!INCLUDE[net_native](../../../includes/net-native-md.md)] doesn't support the following:</span></span>  
  
-   <span data-ttu-id="b7d59-306">使用经典 COM 事件</span><span class="sxs-lookup"><span data-stu-id="b7d59-306">Using classic COM events</span></span>  
  
-   <span data-ttu-id="b7d59-307">在托管类型上实施 <xref:System.Runtime.InteropServices.ICustomQueryInterface?displayProperty=nameWithType> 接口</span><span class="sxs-lookup"><span data-stu-id="b7d59-307">Implementing the <xref:System.Runtime.InteropServices.ICustomQueryInterface?displayProperty=nameWithType> interface on a managed type</span></span>  
  
-   <span data-ttu-id="b7d59-308">实现[IDispatch](http://msdn.microsoft.com/library/windows/apps/ms221608.aspx)通过托管类型上的接口<xref:System.Runtime.InteropServices.ComDefaultInterfaceAttribute?displayProperty=nameWithType>属性。</span><span class="sxs-lookup"><span data-stu-id="b7d59-308">Implementing the [IDispatch](http://msdn.microsoft.com/library/windows/apps/ms221608.aspx) interface on a managed type through the <xref:System.Runtime.InteropServices.ComDefaultInterfaceAttribute?displayProperty=nameWithType> attribute.</span></span> <span data-ttu-id="b7d59-309">然而，请注意你无法通过 `IDispatch`调用 COM 对象，而且你的托管对象无法实施 `IDispatch`。</span><span class="sxs-lookup"><span data-stu-id="b7d59-309">However, note that you can't call COM objects through `IDispatch`, and your managed object can't implement `IDispatch`.</span></span>  
  
 <span data-ttu-id="b7d59-310">使用反射来调用平台调用方法不受支持。</span><span class="sxs-lookup"><span data-stu-id="b7d59-310">Using reflection to invoke a platform invoke method isn't supported.</span></span> <span data-ttu-id="b7d59-311">你可以巧妙绕过这种限制，具体做法是将方法调用包装在另一种方法中，并使用反射调用包装方法。</span><span class="sxs-lookup"><span data-stu-id="b7d59-311">You can work around this limitation by wrapping the method call in another method and using reflection to call the wrapper instead.</span></span>  
  
<a name="APIs"></a>   
### <a name="other-differences-from-net-apis-for-windows-store-apps"></a><span data-ttu-id="b7d59-312">与 Windows 应用商店应用 .NET API 的其他差异</span><span class="sxs-lookup"><span data-stu-id="b7d59-312">Other differences from .NET APIs for Windows Store apps</span></span>  
 <span data-ttu-id="b7d59-313">这部分列出了 [!INCLUDE[net_native](../../../includes/net-native-md.md)]中不受支持的其余 API。</span><span class="sxs-lookup"><span data-stu-id="b7d59-313">This section lists the remaining APIs that aren't supported in [!INCLUDE[net_native](../../../includes/net-native-md.md)].</span></span> <span data-ttu-id="b7d59-314">最大一部分不受支持的 API 是 Windows Communication Foundation (WCF) API。</span><span class="sxs-lookup"><span data-stu-id="b7d59-314">The largest set of the unsupported APIs are Windows Communication Foundation (WCF) APIs.</span></span>  
  
 <span data-ttu-id="b7d59-315">**DataAnnotations (System.ComponentModel.DataAnnotations)**</span><span class="sxs-lookup"><span data-stu-id="b7d59-315">**DataAnnotations (System.ComponentModel.DataAnnotations)**</span></span>  
  
 <span data-ttu-id="b7d59-316"><xref:System.ComponentModel.DataAnnotations> 和 <xref:System.ComponentModel.DataAnnotations.Schema> 命名空间中的类型在 [!INCLUDE[net_native](../../../includes/net-native-md.md)]中不受支持。</span><span class="sxs-lookup"><span data-stu-id="b7d59-316">The types in the <xref:System.ComponentModel.DataAnnotations> and <xref:System.ComponentModel.DataAnnotations.Schema> namespaces aren't supported in [!INCLUDE[net_native](../../../includes/net-native-md.md)].</span></span> <span data-ttu-id="b7d59-317">这些包括 Windows 8 的 Windows 应用商店应用的 .NET 中出现的以下类型：</span><span class="sxs-lookup"><span data-stu-id="b7d59-317">These include the following types that are present in the .NET for Windows Store apps for Windows 8:</span></span>  
  
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
  
 <span data-ttu-id="b7d59-318">**Visual Basic**</span><span class="sxs-lookup"><span data-stu-id="b7d59-318">**Visual Basic**</span></span>  
  
 <span data-ttu-id="b7d59-319">Visual Basic 当前在 [!INCLUDE[net_native](../../../includes/net-native-md.md)]中不受支持。</span><span class="sxs-lookup"><span data-stu-id="b7d59-319">Visual Basic isn't currently supported in [!INCLUDE[net_native](../../../includes/net-native-md.md)].</span></span> <span data-ttu-id="b7d59-320"><xref:Microsoft.VisualBasic> 和 <xref:Microsoft.VisualBasic.CompilerServices> 命名空间中的以下类型在 [!INCLUDE[net_native](../../../includes/net-native-md.md)]中不受支持。</span><span class="sxs-lookup"><span data-stu-id="b7d59-320">The following types in the <xref:Microsoft.VisualBasic> and <xref:Microsoft.VisualBasic.CompilerServices> namespaces aren't available in [!INCLUDE[net_native](../../../includes/net-native-md.md)]:</span></span>  
  
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
  
 <span data-ttu-id="b7d59-321">**反射上下文（System.Reflection.Context 命名空间）**</span><span class="sxs-lookup"><span data-stu-id="b7d59-321">**Reflection Context (System.Reflection.Context namespace)**</span></span>  
  
 <span data-ttu-id="b7d59-322"><xref:System.Reflection.Context.CustomReflectionContext?displayProperty=nameWithType> 类在 [!INCLUDE[net_native](../../../includes/net-native-md.md)] 中不受支持。</span><span class="sxs-lookup"><span data-stu-id="b7d59-322">The <xref:System.Reflection.Context.CustomReflectionContext?displayProperty=nameWithType> class isn't supported in [!INCLUDE[net_native](../../../includes/net-native-md.md)].</span></span>  
  
 <span data-ttu-id="b7d59-323">**RTC (System.Net.Http.Rtc)**</span><span class="sxs-lookup"><span data-stu-id="b7d59-323">**RTC (System.Net.Http.Rtc)**</span></span>  
  
 <span data-ttu-id="b7d59-324"><xref:System.Net.Http.RtcRequestFactory?displayProperty=nameWithType> 类在 [!INCLUDE[net_native](../../../includes/net-native-md.md)] 中不受支持。</span><span class="sxs-lookup"><span data-stu-id="b7d59-324">The <xref:System.Net.Http.RtcRequestFactory?displayProperty=nameWithType> class isn't supported in [!INCLUDE[net_native](../../../includes/net-native-md.md)].</span></span>  
  
 <span data-ttu-id="b7d59-325">**Windows Communication Foundation (WCF) (System.ServiceModel.\*)**</span><span class="sxs-lookup"><span data-stu-id="b7d59-325">**Windows Communication Foundation (WCF) (System.ServiceModel.\*)**</span></span>  
  
 <span data-ttu-id="b7d59-326">[System.ServiceModel.* 命名空间](http://msdn.microsoft.com/library/gg145010.aspx) 中的类型在 [!INCLUDE[net_native](../../../includes/net-native-md.md)]中不受支持。</span><span class="sxs-lookup"><span data-stu-id="b7d59-326">The types in the [System.ServiceModel.* namespaces](http://msdn.microsoft.com/library/gg145010.aspx) aren't supported in [!INCLUDE[net_native](../../../includes/net-native-md.md)].</span></span> <span data-ttu-id="b7d59-327">这些包括以下类型：</span><span class="sxs-lookup"><span data-stu-id="b7d59-327">These includes the following types:</span></span>  
  
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
  
### <a name="differences-in-serializers"></a><span data-ttu-id="b7d59-328">序列化程序中的差异</span><span class="sxs-lookup"><span data-stu-id="b7d59-328">Differences in serializers</span></span>  
 <span data-ttu-id="b7d59-329">与 <xref:System.Runtime.Serialization.DataContractSerializer>、 <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>和 <xref:System.Xml.Serialization.XmlSerializer> 类的序列化和反序列化有关的以下差异：</span><span class="sxs-lookup"><span data-stu-id="b7d59-329">The following differences concern serialization and deserialization with the <xref:System.Runtime.Serialization.DataContractSerializer>, <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>, and <xref:System.Xml.Serialization.XmlSerializer> classes:</span></span>  
  
-   <span data-ttu-id="b7d59-330">在 [!INCLUDE[net_native](../../../includes/net-native-md.md)]中， <xref:System.Runtime.Serialization.DataContractSerializer> 和 <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> 无法序列化或反序列化一个派生类，其中此派生类具有一个非根序列化类型的基类成员。</span><span class="sxs-lookup"><span data-stu-id="b7d59-330">In [!INCLUDE[net_native](../../../includes/net-native-md.md)], <xref:System.Runtime.Serialization.DataContractSerializer> and <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> fail to serialize or deserialize a derived class that has a base class member whose type isn't a root serialization type.</span></span> <span data-ttu-id="b7d59-331">例如，在以下代码中，尝试序列化或反序列化 `Y` 会导致出现错误：</span><span class="sxs-lookup"><span data-stu-id="b7d59-331">For example, in the following code, trying to serialize or deserialize `Y` results in an error:</span></span>  
  
     [!code-csharp[ProjectN#10](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/compat3.cs#10)]  
  
     <span data-ttu-id="b7d59-332">类型 `InnerType` 对序列程序而言是未知的，因为基类的成员在序列化期间无法遍历。</span><span class="sxs-lookup"><span data-stu-id="b7d59-332">Type `InnerType` isn't known to the serializer, because the members of the base class aren't traversed during serialization.</span></span>  
  
-   <span data-ttu-id="b7d59-333"><xref:System.Runtime.Serialization.DataContractSerializer> 和 <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> 无法序列化实施 <xref:System.Collections.Generic.IEnumerable%601> 接口的类或结构。</span><span class="sxs-lookup"><span data-stu-id="b7d59-333"><xref:System.Runtime.Serialization.DataContractSerializer> and <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> fail to serialize a class or structure that implements the <xref:System.Collections.Generic.IEnumerable%601> interface.</span></span> <span data-ttu-id="b7d59-334">例如，以下类无法序列化或反序列化：</span><span class="sxs-lookup"><span data-stu-id="b7d59-334">For example, the following types fail to serialize or deserialize:</span></span>  
  
  
  
-   <span data-ttu-id="b7d59-335"><xref:System.Xml.Serialization.XmlSerializer> 无法序列化以下对象值，因为它不知道将序列化的对象的类型：</span><span class="sxs-lookup"><span data-stu-id="b7d59-335"><xref:System.Xml.Serialization.XmlSerializer> fails to serialize the following object value, because it doesn't know the exact type of the object to be serialized:</span></span>  
  
  
  
-   <span data-ttu-id="b7d59-336">如果将序列化的对象的类型是<xref:System.Xml.Serialization.XmlSerializer> ，则 <xref:System.Xml.XmlQualifiedName>无法序列化或反序列化。</span><span class="sxs-lookup"><span data-stu-id="b7d59-336"><xref:System.Xml.Serialization.XmlSerializer> fails to serialize or deserialize if the type of the serialized object is <xref:System.Xml.XmlQualifiedName>.</span></span>  
  
-   <span data-ttu-id="b7d59-337">所有序列程序（<xref:System.Runtime.Serialization.DataContractSerializer>、<xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> 和 <xref:System.Xml.Serialization.XmlSerializer>）都无法为 <xref:System.Xml.Linq.XElement?displayProperty=nameWithType> 类型或包含 <xref:System.Xml.Linq.XElement> 的类型生成序列代码。</span><span class="sxs-lookup"><span data-stu-id="b7d59-337">All serializers (<xref:System.Runtime.Serialization.DataContractSerializer>, <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>, and <xref:System.Xml.Serialization.XmlSerializer>) fail to generate serialization code for type <xref:System.Xml.Linq.XElement?displayProperty=nameWithType> or for a type that contains <xref:System.Xml.Linq.XElement>.</span></span> <span data-ttu-id="b7d59-338">它们会显示生成时间错误。</span><span class="sxs-lookup"><span data-stu-id="b7d59-338">They display build-time errors instead.</span></span>  
  
-   <span data-ttu-id="b7d59-339">以下序列化类型的构造函数无法保证按照预期工作：</span><span class="sxs-lookup"><span data-stu-id="b7d59-339">The following constructors of the serialization types aren't guaranteed to work as expected:</span></span>  
  
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
  
-   <span data-ttu-id="b7d59-340"><xref:System.Xml.Serialization.XmlSerializer> 无法为具有以下任意特性的方法的类型生成代码：</span><span class="sxs-lookup"><span data-stu-id="b7d59-340"><xref:System.Xml.Serialization.XmlSerializer> fails to generate code for a type that has methods attributed with any of the following attributes:</span></span>  
  
    -   <xref:System.Runtime.Serialization.OnSerializingAttribute>  
  
    -   <xref:System.Runtime.Serialization.OnSerializedAttribute>  
  
    -   <xref:System.Runtime.Serialization.OnDeserializingAttribute>  
  
    -   <xref:System.Runtime.Serialization.OnDeserializedAttribute>  
  
-   <span data-ttu-id="b7d59-341"><xref:System.Xml.Serialization.XmlSerializer> 不兼容 <xref:System.Xml.Serialization.IXmlSerializable> 自定义序列化接口。</span><span class="sxs-lookup"><span data-stu-id="b7d59-341"><xref:System.Xml.Serialization.XmlSerializer> doesn't honor the <xref:System.Xml.Serialization.IXmlSerializable> custom serialization interface.</span></span> <span data-ttu-id="b7d59-342">如果你的类实施此接口， <xref:System.Xml.Serialization.XmlSerializer> 会考虑普通旧 CLR 对象 (POCO) 类型并仅对其公共属性进行序列化。</span><span class="sxs-lookup"><span data-stu-id="b7d59-342">If you have a class that implements this interface, <xref:System.Xml.Serialization.XmlSerializer> considers the type a plain old CLR object (POCO) type and serializes only its public properties.</span></span>  
  
-   <span data-ttu-id="b7d59-343">对普通 <xref:System.Exception> 对象的序列化（如以下情况）对 <xref:System.Runtime.Serialization.DataContractSerializer> 和 <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>无效：</span><span class="sxs-lookup"><span data-stu-id="b7d59-343">Serializing a plain <xref:System.Exception> object, such as the following, doesn't work well with <xref:System.Runtime.Serialization.DataContractSerializer> and <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>:</span></span>  
  
  
  
<a name="VS"></a>   
## <a name="visual-studio-differences"></a><span data-ttu-id="b7d59-344">Visual Studio 差异</span><span class="sxs-lookup"><span data-stu-id="b7d59-344">Visual Studio differences</span></span>  
 <span data-ttu-id="b7d59-345">**异常和调试**</span><span class="sxs-lookup"><span data-stu-id="b7d59-345">**Exceptions and debugging**</span></span>  
  
 <span data-ttu-id="b7d59-346">如果你在运行通过调试程序中的 [!INCLUDE[net_native](../../../includes/net-native-md.md)] 编译的应用，则以下异常类型启用最可能的异常：</span><span class="sxs-lookup"><span data-stu-id="b7d59-346">When you're running apps compiled by using [!INCLUDE[net_native](../../../includes/net-native-md.md)] in the debugger, first-chance exceptions are enabled for the following exception types:</span></span>  
  
-   <xref:System.MemberAccessException>  
  
-   <xref:System.TypeAccessException>  
  
 <span data-ttu-id="b7d59-347">**构建应用**</span><span class="sxs-lookup"><span data-stu-id="b7d59-347">**Building apps**</span></span>  
  
 <span data-ttu-id="b7d59-348">使用 Visual Studio 默认使用的 x86 构建工具。</span><span class="sxs-lookup"><span data-stu-id="b7d59-348">Use the x86 build tools that are used by default by Visual Studio.</span></span> <span data-ttu-id="b7d59-349">我们不推荐使用 AMD64 MSBuild 工具（位置路径为 C:\Program Files (x86)\MSBuild\12.0\bin\amd64），因为这些工具会导致构建问题。</span><span class="sxs-lookup"><span data-stu-id="b7d59-349">We don't recommend using the AMD64 MSBuild tools, which are found in C:\Program Files (x86)\MSBuild\12.0\bin\amd64; these may create build problems.</span></span>  
  
 <span data-ttu-id="b7d59-350">**探查器**</span><span class="sxs-lookup"><span data-stu-id="b7d59-350">**Profilers**</span></span>  
  
-   <span data-ttu-id="b7d59-351">Visual Studio CPU 探查器和 XAML 内存探查器不会正确显示 Just-My-Code。</span><span class="sxs-lookup"><span data-stu-id="b7d59-351">The Visual Studio CPU Profiler and XAML Memory Profiler don't display Just-My-Code correctly.</span></span>  
  
-   <span data-ttu-id="b7d59-352">XAML 内存探查器不会精确显示托管的堆数据。</span><span class="sxs-lookup"><span data-stu-id="b7d59-352">The XAML Memory Profiler doesn't accurately display managed heap data.</span></span>  
  
-   <span data-ttu-id="b7d59-353">CPU 探查器不会正确区分模块和显示前缀的功能名。</span><span class="sxs-lookup"><span data-stu-id="b7d59-353">The CPU Profiler doesn't correctly identify modules, and displays prefixed function names.</span></span>  
  
 <span data-ttu-id="b7d59-354">**单元测试库项目**</span><span class="sxs-lookup"><span data-stu-id="b7d59-354">**Unit Test Library projects**</span></span>  
  
 <span data-ttu-id="b7d59-355">不支持启用 Windows 应用商店应用项目的单元测试库上的 [!INCLUDE[net_native](../../../includes/net-native-md.md)] ，因为这会导致项目无法构建。</span><span class="sxs-lookup"><span data-stu-id="b7d59-355">Enabling [!INCLUDE[net_native](../../../includes/net-native-md.md)] on a Unit Test Library for a Windows Store apps project isn't supported and causes the project to fail to build.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7d59-356">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b7d59-356">See Also</span></span>  
 [<span data-ttu-id="b7d59-357">入门</span><span class="sxs-lookup"><span data-stu-id="b7d59-357">Getting Started</span></span>](../../../docs/framework/net-native/getting-started-with-net-native.md)  
 [<span data-ttu-id="b7d59-358">运行时指令 (rd.xml) 配置文件参考</span><span class="sxs-lookup"><span data-stu-id="b7d59-358">Runtime Directives (rd.xml) Configuration File Reference</span></span>](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)  
 [<span data-ttu-id="b7d59-359">.NET for Windows Store 应用概述</span><span class="sxs-lookup"><span data-stu-id="b7d59-359">.NET For Windows Store apps overview</span></span>](http://msdn.microsoft.com/library/windows/apps/br230302.aspx)  
 [<span data-ttu-id="b7d59-360">.NET Framework 对 Windows 应用商店应用和 Windows 运行时的支持情况</span><span class="sxs-lookup"><span data-stu-id="b7d59-360">.NET Framework Support for Windows Store Apps and Windows Runtime</span></span>](../../../docs/standard/cross-platform/support-for-windows-store-apps-and-windows-runtime.md)
