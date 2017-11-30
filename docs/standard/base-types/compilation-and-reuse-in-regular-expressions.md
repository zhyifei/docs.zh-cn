---
title: "正则表达式中的编译和重复使用"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- parsing text with regular expressions, compilation
- searching with regular expressions, compilation
- .NET Framework regular expressions, engines
- .NET Framework regular expressions, compilation
- regular expressions, compilation
- compilation, regular expressions
- pattern-matching with regular expressions, compilation
- regular expressions, engines
ms.assetid: 182ec76d-5a01-4d73-996c-0b0d14fcea18
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 76acdf2d0d2f7805ec78ea44136bfc63441b9bc9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="compilation-and-reuse-in-regular-expressions"></a><span data-ttu-id="68f2c-102">正则表达式中的编译和重复使用</span><span class="sxs-lookup"><span data-stu-id="68f2c-102">Compilation and Reuse in Regular Expressions</span></span>
<span data-ttu-id="68f2c-103">通过了解正则表达式引擎编译表达式的方式以及正则表达式的缓存方式，可以优化大量使用正则表达式的应用程序的性能。</span><span class="sxs-lookup"><span data-stu-id="68f2c-103">You can optimize the performance of applications that make extensive use of regular expressions by understanding how the regular expression engine compiles expressions and by understanding how regular expressions are cached.</span></span> <span data-ttu-id="68f2c-104">本主题介绍编译和缓存。</span><span class="sxs-lookup"><span data-stu-id="68f2c-104">This topic discusses both compilation and caching.</span></span>  
  
## <a name="compiled-regular-expressions"></a><span data-ttu-id="68f2c-105">已编译的正则表达式</span><span class="sxs-lookup"><span data-stu-id="68f2c-105">Compiled Regular Expressions</span></span>  
 <span data-ttu-id="68f2c-106">默认情况下，正则表达式引擎将正则表达式编译成内部指令序列（这些指令序列是不同于 Microsoft 中间语言 (MSIL) 的高级代码）。</span><span class="sxs-lookup"><span data-stu-id="68f2c-106">By default, the regular expression engine compiles a regular expression to a sequence of internal instructions (these are high-level codes that are different from Microsoft intermediate language, or MSIL).</span></span> <span data-ttu-id="68f2c-107">当引擎执行正则表达式时，会解释内部代码。</span><span class="sxs-lookup"><span data-stu-id="68f2c-107">When the engine executes a regular expression, it interprets the internal codes.</span></span>  
  
 <span data-ttu-id="68f2c-108">如果<xref:System.Text.RegularExpressions.Regex>对象构造<xref:System.Text.RegularExpressions.RegexOptions.Compiled?displayProperty=nameWithType>选项，它将编译到显式的 MSIL 代码，而不是高级正则表达式内部说明的正则表达式。</span><span class="sxs-lookup"><span data-stu-id="68f2c-108">If a <xref:System.Text.RegularExpressions.Regex> object is constructed with the <xref:System.Text.RegularExpressions.RegexOptions.Compiled?displayProperty=nameWithType> option, it compiles the regular expression to explicit MSIL code instead of high-level regular expression internal instructions.</span></span> <span data-ttu-id="68f2c-109">这样，.NET 的实时 (JIT) 编译器便可以将表达式转换为本机代码以获得更高的性能。</span><span class="sxs-lookup"><span data-stu-id="68f2c-109">This allows .NET's just-in-time (JIT) compiler to convert the expression to native machine code for higher performance.</span></span>  
  
<span data-ttu-id="68f2c-110">但是，生成的 MSIL 不能卸载。</span><span class="sxs-lookup"><span data-stu-id="68f2c-110">However, generated MSIL cannot be unloaded.</span></span> <span data-ttu-id="68f2c-111">卸载代码的唯一方法是卸载整个应用程序域（即，卸载应用程序的所有代码）。</span><span class="sxs-lookup"><span data-stu-id="68f2c-111">The only way to unload code is to unload an entire application domain (that is, to unload all of your application's code.).</span></span> <span data-ttu-id="68f2c-112">实际上，正则表达式编译与后<xref:System.Text.RegularExpressions.RegexOptions.Compiled?displayProperty=nameWithType>选项时，永远不会释放已编译的表达式中，使用的资源，即使正则表达式由<xref:System.Text.RegularExpressions.Regex>本身发布到的垃圾回收的对象。</span><span class="sxs-lookup"><span data-stu-id="68f2c-112">Effectively, once a regular expression is compiled with the <xref:System.Text.RegularExpressions.RegexOptions.Compiled?displayProperty=nameWithType> option,   never releases the resources used by the compiled expression, even if the regular expression was created by a <xref:System.Text.RegularExpressions.Regex> object that is itself released to garbage collection.</span></span>  
  
 <span data-ttu-id="68f2c-113">您必须小心地将其限制的不同使用编译的正则表达式的数目<xref:System.Text.RegularExpressions.RegexOptions.Compiled?displayProperty=nameWithType>选项，以避免消耗太多资源。</span><span class="sxs-lookup"><span data-stu-id="68f2c-113">You must be careful to limit the number of different regular expressions you compile with the <xref:System.Text.RegularExpressions.RegexOptions.Compiled?displayProperty=nameWithType> option to avoid consuming too many resources.</span></span> <span data-ttu-id="68f2c-114">如果应用程序必须使用较大数量或极大数量的正则表达式，应该解释每个表达式，而不要编译它们。</span><span class="sxs-lookup"><span data-stu-id="68f2c-114">If an application must use a large or unbounded number of regular expressions, each expression should be interpreted, not compiled.</span></span> <span data-ttu-id="68f2c-115">但是，如果重复使用少量的正则表达式，它们应使用编译<xref:System.Text.RegularExpressions.RegexOptions.Compiled?displayProperty=nameWithType>以提高性能。</span><span class="sxs-lookup"><span data-stu-id="68f2c-115">However, if a small number of regular expressions are used repeatedly, they should be compiled with <xref:System.Text.RegularExpressions.RegexOptions.Compiled?displayProperty=nameWithType> for better performance.</span></span> <span data-ttu-id="68f2c-116">一种替代方法是使用预编译的正则表达式。</span><span class="sxs-lookup"><span data-stu-id="68f2c-116">An alternative is to use precompiled regular expressions.</span></span> <span data-ttu-id="68f2c-117">你可以通过编译为可重用 DLL 将表达式的所有<xref:System.Text.RegularExpressions.Regex.CompileToAssembly%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="68f2c-117">You can compile all of your expressions into a reusable DLL by using the <xref:System.Text.RegularExpressions.Regex.CompileToAssembly%2A> method.</span></span> <span data-ttu-id="68f2c-118">这样就避免了需要在运行时编译并同时仍可受益的已编译的正则表达式的速度。</span><span class="sxs-lookup"><span data-stu-id="68f2c-118">This avoids the need to compile at runtime while still benefiting from the speed of compiled regular expressions.</span></span>  
  
## <a name="the-regular-expressions-cache"></a><span data-ttu-id="68f2c-119">正则表达式缓存</span><span class="sxs-lookup"><span data-stu-id="68f2c-119">The Regular Expressions Cache</span></span>  
 <span data-ttu-id="68f2c-120">为了提高性能，正则表达式引擎为已编译的正则表达式维护了一个应用程序范围的缓存。</span><span class="sxs-lookup"><span data-stu-id="68f2c-120">To improve performance, the regular expression engine maintains an application-wide cache of compiled regular expressions.</span></span> <span data-ttu-id="68f2c-121">该缓存只存储静态方法调用中使用的正则表达式模式。</span><span class="sxs-lookup"><span data-stu-id="68f2c-121">The cache stores regular expression patterns that are used only in static method calls.</span></span> <span data-ttu-id="68f2c-122">（不缓存提供给实例方法的正则表达式模式。）这样，在每次使用正则表达式时，就无需将正则表达式重新分析成高级字节代码。</span><span class="sxs-lookup"><span data-stu-id="68f2c-122">(Regular expression patterns supplied to instance methods are not cached.) This avoids the need to reparse an expression into high-level byte code each time it is used.</span></span>  
  
 <span data-ttu-id="68f2c-123">值确定的缓存的正则表达式的最大数目`static`(`Shared`在 Visual Basic 中)<xref:System.Text.RegularExpressions.Regex.CacheSize%2A?displayProperty=nameWithType>属性。</span><span class="sxs-lookup"><span data-stu-id="68f2c-123">The maximum number of cached regular expressions is determined by the value of the `static` (`Shared` in Visual Basic) <xref:System.Text.RegularExpressions.Regex.CacheSize%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="68f2c-124">默认情况下，正则表达式引擎最多可缓存 15 个已编译的正则表达式。</span><span class="sxs-lookup"><span data-stu-id="68f2c-124">By default, the regular expression engine caches up to 15 compiled regular expressions.</span></span> <span data-ttu-id="68f2c-125">如果已编译正则表达式的数目超过缓存大小，则丢弃最早使用的正则表达式并缓存新的正则表达式。</span><span class="sxs-lookup"><span data-stu-id="68f2c-125">If the number of compiled regular expressions exceeds the cache size, the least recently used regular expression is discarded and the new regular expression is cached.</span></span>  
  
 <span data-ttu-id="68f2c-126">应用程序可通过以下两种方式之一来利用预编译的正则表达式：</span><span class="sxs-lookup"><span data-stu-id="68f2c-126">Your application can take advantage of precompiled regular expressions in one of the following two ways:</span></span>  
  
-   <span data-ttu-id="68f2c-127">通过使用的静态方法<xref:System.Text.RegularExpressions.Regex>对象来定义正则表达式。</span><span class="sxs-lookup"><span data-stu-id="68f2c-127">By using a static method of the <xref:System.Text.RegularExpressions.Regex> object to define the regular expression.</span></span> <span data-ttu-id="68f2c-128">如果要使用的正则表达式模式已在其他静态方法调用中定义，则正则表达式引擎将从缓存中检索该模式。</span><span class="sxs-lookup"><span data-stu-id="68f2c-128">If you are using a regular expression pattern that has already been defined in another static method call, the regular expression engine will retrieve it from the cache.</span></span> <span data-ttu-id="68f2c-129">如果不是这样，则引擎将编译正则表达式并将其添加到缓存中。</span><span class="sxs-lookup"><span data-stu-id="68f2c-129">If not, the engine will compile the regular expression and add it to the cache.</span></span>  
  
-   <span data-ttu-id="68f2c-130">通过重用现有<xref:System.Text.RegularExpressions.Regex>对象，只要需要其正则表达式模式。</span><span class="sxs-lookup"><span data-stu-id="68f2c-130">By reusing an existing <xref:System.Text.RegularExpressions.Regex> object as long as its regular expression pattern is needed.</span></span>  
  
 <span data-ttu-id="68f2c-131">由于对象实例化和正则表达式编译、 创建和快速销毁大量的系统开销<xref:System.Text.RegularExpressions.Regex>对象是一个代价很高的过程。</span><span class="sxs-lookup"><span data-stu-id="68f2c-131">Because of the overhead of object instantiation and regular expression compilation, creating and rapidly destroying numerous <xref:System.Text.RegularExpressions.Regex> objects is a very expensive process.</span></span> <span data-ttu-id="68f2c-132">对于使用大量不同的正则表达式的应用程序，你可以通过使用为静态的调用来优化性能`Regex`方法并尽量增加正则表达式缓存的大小。</span><span class="sxs-lookup"><span data-stu-id="68f2c-132">For applications that use a large number of different regular expressions, you can optimize performance by using calls to static `Regex` methods and possibly by increasing the size of the regular expression cache.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68f2c-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="68f2c-133">See Also</span></span>  
 [<span data-ttu-id="68f2c-134">.NET 正则表达式</span><span class="sxs-lookup"><span data-stu-id="68f2c-134">.NET Regular Expressions</span></span>](../../../docs/standard/base-types/regular-expressions.md)
