---
title: "缓解：新的 64 位 JIT 编译器"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- JIT compiler, 64-bit
- JIT compilation, 64-bit
- RyuJIT compiler
ms.assetid: 0332dabc-72c5-4bdc-8975-20d717802b17
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1ea1f5a832e2db63590fe5cbc3425078e17d3825
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="mitigation-new-64-bit-jit-compiler"></a><span data-ttu-id="e3d69-102">缓解：新的 64 位 JIT 编译器</span><span class="sxs-lookup"><span data-stu-id="e3d69-102">Mitigation: New 64-bit JIT Compiler</span></span>
<span data-ttu-id="e3d69-103">自 .NET Framework 4.6 起，运行时包括新版 64 位 JIT 编译器，用于执行实时编译。</span><span class="sxs-lookup"><span data-stu-id="e3d69-103">Starting with the .NET Framework 4.6, the runtime includes a new 64-bit JIT compiler for just-in-time compilation.</span></span> <span data-ttu-id="e3d69-104">此更改不会影响 32 位 JIT 编译器的编译。</span><span class="sxs-lookup"><span data-stu-id="e3d69-104">This change does not affect compilation with the  32-bit JIT compiler.</span></span>  
  
## <a name="unexpected-behavior-or-exceptions"></a><span data-ttu-id="e3d69-105">意外行为或异常</span><span class="sxs-lookup"><span data-stu-id="e3d69-105">Unexpected behavior or exceptions</span></span>  
 <span data-ttu-id="e3d69-106">在某些情况下，使用新版 64 位 JIT 编译器进行编译会导致运行时异常抛出，或导致执行旧版 64 位 JIT 编译器编译的代码时无法观察到的行为发生。</span><span class="sxs-lookup"><span data-stu-id="e3d69-106">In some cases, compilation with the new 64-bit JIT compiler results in a runtime exception or in behavior that is not observed when executing code compiled by the older 64-bit JIT compiler.</span></span> <span data-ttu-id="e3d69-107">已知差异如下：</span><span class="sxs-lookup"><span data-stu-id="e3d69-107">The known differences include the following:</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="e3d69-108">所有这些已知问题已在随 .NET Framework 4.6.2 一起发布的新版 64 位编译器中得到了解决。</span><span class="sxs-lookup"><span data-stu-id="e3d69-108">All of these known issues have been addressed in the new 64-bit compiler released with the .NET Framework 4.6.2.</span></span> <span data-ttu-id="e3d69-109">大多数问题也已在 Windows 更新随附的 .NET Framework 4.6 和 4.6.1 的服务版本中得到解决。</span><span class="sxs-lookup"><span data-stu-id="e3d69-109">Most have also been addressed in service releases of the .NET Framework 4.6 and 4.6.1 that are included with Windows Update.</span></span> <span data-ttu-id="e3d69-110">若要消除这些问题，请确保 Windows 是最新版本，或升级到 .NET Framework 4.6.2。</span><span class="sxs-lookup"><span data-stu-id="e3d69-110">You can eliminate these issues by ensuring that your version of Windows is up to date, or by upgrading to the .NET Framework 4.6.2.</span></span>  
  
-   <span data-ttu-id="e3d69-111">在某些情况下，在启用优化的发布版本中，取消装箱操作可能会引发 <xref:System.NullReferenceException>。</span><span class="sxs-lookup"><span data-stu-id="e3d69-111">Under certain conditions, an unboxing operation may throw a <xref:System.NullReferenceException> in Release builds with optimization turned on.</span></span>  
  
-   <span data-ttu-id="e3d69-112">在某些情况下，在大型方法主体中执行生产代码可能会引发 <xref:System.StackOverflowException>。</span><span class="sxs-lookup"><span data-stu-id="e3d69-112">In some cases, execution of production code in a large method body may throw a <xref:System.StackOverflowException>.</span></span>  
  
-   <span data-ttu-id="e3d69-113">在某些情况下，传递给方法的结构在发布版本中被视为引用类型，而不是值类型。</span><span class="sxs-lookup"><span data-stu-id="e3d69-113">Under certain conditions, structures passed to a method are treated as reference types rather than value types in Release builds.</span></span> <span data-ttu-id="e3d69-114">此问题的表现形式之一是，集合中各个项的显示顺序出现异常。</span><span class="sxs-lookup"><span data-stu-id="e3d69-114">One of the manifestations of this issue is that the individual items in a collection appear in an unexpected order.</span></span>  
  
-   <span data-ttu-id="e3d69-115">在某些情况下，如果启用了优化，无法正确比较 <xref:System.UInt16> 值与其高位集。</span><span class="sxs-lookup"><span data-stu-id="e3d69-115">Under certain conditions, the comparison of <xref:System.UInt16> values with their high bit set is incorrect if optimization is enabled.</span></span>  
  
-   <span data-ttu-id="e3d69-116">在某些情况下，尤其是在初始化数组值时，通过 <xref:System.Reflection.Emit.OpCodes.Initblk?displayProperty=nameWithType> IL 指令执行的内存初始化可能会使用不正确的值初始化内存。</span><span class="sxs-lookup"><span data-stu-id="e3d69-116">Under certain conditions, particularly when initializing array values, memory initialization by the <xref:System.Reflection.Emit.OpCodes.Initblk?displayProperty=nameWithType> IL instruction may initialize memory with an incorrect value.</span></span> <span data-ttu-id="e3d69-117">这可能会导致未经处理的异常抛出或输出不正确。</span><span class="sxs-lookup"><span data-stu-id="e3d69-117">This can result either in an unhandled exception or incorrect output.</span></span>  
  
-   <span data-ttu-id="e3d69-118">在某些极少数情况下，如果启用了编译器优化，条件位测试可能会返回错误的 <xref:System.Boolean> 值或引发异常。</span><span class="sxs-lookup"><span data-stu-id="e3d69-118">Under certain rare conditions, a conditional bit test can return the incorrect <xref:System.Boolean> value or throw an exception if compiler optimizations are enabled.</span></span>  
  
-   <span data-ttu-id="e3d69-119">在某些情况下，如果 `if` 语句用于在进入 `try` 块之前和从 `try` 块中退出之前测试条件，且在 `catch` 或 `finally` 块中计算的条件相同，那么新版 64 位 JIT 编译器会在优化代码时从 `catch` 或 `finally` 块中删除 `if` 条件。</span><span class="sxs-lookup"><span data-stu-id="e3d69-119">Under certain conditions, if an `if` statement is used to test for a condition before entering  a `try` block and in the exit from the `try` block, and the same condition is evaluated in the `catch` or `finally` block, the new 64-bit JIT compiler removes the `if` condition from the `catch` or `finally` block when it optimizes code.</span></span> <span data-ttu-id="e3d69-120">因此，`catch` 或 `finally` 块中的 `if` 语句代码会无条件地执行。</span><span class="sxs-lookup"><span data-stu-id="e3d69-120">As a result, code inside the `if` statement in the `catch` or `finally` block is executed unconditionally.</span></span>  
  
<a name="General"></a>   
## <a name="mitigation-of-known-issues"></a><span data-ttu-id="e3d69-121">已知问题的缓解措施</span><span class="sxs-lookup"><span data-stu-id="e3d69-121">Mitigation of known issues</span></span>  
 <span data-ttu-id="e3d69-122">如果遇到上面列出的问题，可以通过执行下列任一操作来解决：</span><span class="sxs-lookup"><span data-stu-id="e3d69-122">If you encounter the issues listed above, you can address them by doing any of the following:</span></span>  
  
-   <span data-ttu-id="e3d69-123">升级到 .NET Framework 4.6.2。</span><span class="sxs-lookup"><span data-stu-id="e3d69-123">Upgrade to the .NET Framework 4.6.2.</span></span> <span data-ttu-id="e3d69-124">.NET Framework 4.6.2 随附的新版 64 位编译器解决了上面列出的所有已知问题。</span><span class="sxs-lookup"><span data-stu-id="e3d69-124">The new 64-bit compiler included with the .NET Framework 4.6.2 addresses each of these known issues.</span></span>  
  
-   <span data-ttu-id="e3d69-125">运行 Windows 更新，以确保 Windows 是最新版本。</span><span class="sxs-lookup"><span data-stu-id="e3d69-125">Ensure that your version of Windows is up to date by running Windows Update.</span></span> <span data-ttu-id="e3d69-126">.NET Framework 4.6 和 4.6.1 服务更新可解决以上问题，取消装箱操作中的 <xref:System.NullReferenceException> 除外。</span><span class="sxs-lookup"><span data-stu-id="e3d69-126">Service updates to the .NET Framework 4.6 and 4.6.1 address each of these issues except the <xref:System.NullReferenceException> in an unboxing operation.</span></span>  
  
-   <span data-ttu-id="e3d69-127">使用旧版 64 位 JIT 编译器进行编译。</span><span class="sxs-lookup"><span data-stu-id="e3d69-127">Compile with the older 64-bit JIT compiler.</span></span> <span data-ttu-id="e3d69-128">请参阅[其他问题的缓解措施](#Other)部分，详细了解如何执行此操作。</span><span class="sxs-lookup"><span data-stu-id="e3d69-128">See the [Mitigation of other issues](#Other) section for more information on how to do this.</span></span>  
  
<a name="Other"></a>   
## <a name="mitigation-of-other-issues"></a><span data-ttu-id="e3d69-129">其他问题的缓解措施</span><span class="sxs-lookup"><span data-stu-id="e3d69-129">Mitigation of other issues</span></span>  
 <span data-ttu-id="e3d69-130">如果遇到的是旧版和新版 64 位 JIT 编译器编译的代码的其他任何行为差异，或是使用新版 64 位 JIT 编译器编译的应用程序的调试和发布版本的其他任何行为差异，可以使用旧版 64 位 JIT 编译器编译应用程序，具体操作如下：</span><span class="sxs-lookup"><span data-stu-id="e3d69-130">If you encounter any other difference in behavior between code compiled with the older 64-bit compiler and the new 64-bit JIT compiler, or between the debug and release versions of your app that are both compiled with the new 64-bit JIT compiler, you can do the following to compile your app with the older 64-bit JIT compiler:</span></span>  
  
-   <span data-ttu-id="e3d69-131">对于每个应用程序，可以将 [\<useLegacyJit>](../../../docs/framework/configure-apps/file-schema/runtime/uselegacyjit-element.md) 元素添加到应用程序的配置文件中。</span><span class="sxs-lookup"><span data-stu-id="e3d69-131">On a per-application basis, you can add the [\<useLegacyJit>](../../../docs/framework/configure-apps/file-schema/runtime/uselegacyjit-element.md) element to your application's configuration file.</span></span> <span data-ttu-id="e3d69-132">下面的代码禁用新版 64 位 JIT 编译器，改用旧版 64 位 JIT 编译器进行编译。</span><span class="sxs-lookup"><span data-stu-id="e3d69-132">The following disables compilation with the new 64-bit JIT compiler and instead uses the legacy 64-bit JIT compiler.</span></span>  
  
    ```xml  
    <?xml version ="1.0"?>  
    <configuration>  
        <runtime>  
           <useLegacyJit enabled="1" />  
        </runtime>  
    </configuration>  
    ```  
  
-   <span data-ttu-id="e3d69-133">对于每个用户，可以将名为 `useLegacyJit` 的 `REG_DWORD` 值添加到注册表的 `HKEY_CURRENT_USER\SOFTWARE\Microsoft\.NETFramework` 密钥中。</span><span class="sxs-lookup"><span data-stu-id="e3d69-133">On a per-user basis, you can add a `REG_DWORD` value named `useLegacyJit` to the `HKEY_CURRENT_USER\SOFTWARE\Microsoft\.NETFramework` key of the registry.</span></span> <span data-ttu-id="e3d69-134">如果值为 1，可以启用旧版 64 位 JIT 编译器；如果值为 0，可以禁用旧版编译器，启用新版 64 位 JIT 编译器。</span><span class="sxs-lookup"><span data-stu-id="e3d69-134">A value of 1 enables the legacy 64-bit JIT compiler; a value of 0 disables it and enables the new 64-bit JIT compiler.</span></span>  
  
-   <span data-ttu-id="e3d69-135">对于每台计算机，可以将名为 `useLegacyJit` 的 `REG_DWORD` 值添加到注册表的 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework` 密钥中。</span><span class="sxs-lookup"><span data-stu-id="e3d69-135">On a per-machine basis, you can add a `REG_DWORD` value named `useLegacyJit` to the `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework` key of the registry.</span></span> <span data-ttu-id="e3d69-136">如果值为 1，可以启用旧版 64 位 JIT 编译器；如果值为 0，可以禁用旧版编译器，启用新版 64 位 JIT 编译器。</span><span class="sxs-lookup"><span data-stu-id="e3d69-136">A value of 1 enables the legacy 64-bit JIT compiler; a value of 0 disables it and enables the new 64-bit JIT compiler.</span></span>  
  
 <span data-ttu-id="e3d69-137">还可以在 [Microsoft Connect](https://connect.microsoft.com/VisualStudio) 上报告 bug，告诉我们你遇到的问题。</span><span class="sxs-lookup"><span data-stu-id="e3d69-137">You can also let us know about the problem by reporting a bug on [Microsoft Connect](https://connect.microsoft.com/VisualStudio).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3d69-138">请参阅</span><span class="sxs-lookup"><span data-stu-id="e3d69-138">See Also</span></span>  
 [<span data-ttu-id="e3d69-139">运行时更改</span><span class="sxs-lookup"><span data-stu-id="e3d69-139">Runtime Changes</span></span>](../../../docs/framework/migration-guide/runtime-changes-in-the-net-framework-4-6.md)  
 [<span data-ttu-id="e3d69-140">\<useLegacyJit> 元素</span><span class="sxs-lookup"><span data-stu-id="e3d69-140">\<useLegacyJit> Element</span></span>](../../../docs/framework/configure-apps/file-schema/runtime/uselegacyjit-element.md)
