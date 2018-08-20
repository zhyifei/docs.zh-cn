---
title: 通用命名约定
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- names [.NET Framework], conflicts
- type names, conflicts
- language-specific type names
- names [.NET Framework], about naming guidelines
- names [.NET Framework], abbreviations
- abbreviation naming guidelines
- acronym naming guidelines
- Hungarian notation
- names [.NET Framework], type names
- names [.NET Framework], acronyms
ms.assetid: d3a77ea1-75d2-4969-a8c3-3e1e3e1aaedc
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 207227b3e5c52b7c6e0f704543379874f3708c03
ms.sourcegitcommit: ceca5a1c027627abcca2767567703c3879f33325
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/23/2018
ms.locfileid: "36338099"
---
# <a name="general-naming-conventions"></a><span data-ttu-id="6fca1-102">通用命名约定</span><span class="sxs-lookup"><span data-stu-id="6fca1-102">General Naming Conventions</span></span>
<span data-ttu-id="6fca1-103">本部分介绍与单词选择相关的一般命名约定、缩略词和首字母缩写词的使用准则以及有关如何避免使用特定于语言的名称的建议。</span><span class="sxs-lookup"><span data-stu-id="6fca1-103">This section describes general naming conventions that relate to word choice, guidelines on using abbreviations and acronyms, and recommendations on how to avoid using language-specific names.</span></span>  
  
## <a name="word-choice"></a><span data-ttu-id="6fca1-104">选词</span><span class="sxs-lookup"><span data-stu-id="6fca1-104">Word Choice</span></span>  
 <span data-ttu-id="6fca1-105">**✓ 务必**选择易读的标识符名称。</span><span class="sxs-lookup"><span data-stu-id="6fca1-105">**✓ DO** choose easily readable identifier names.</span></span>  
  
 <span data-ttu-id="6fca1-106">例如，在英语中，属性名称 `HorizontalAlignment` 比 `AlignmentHorizontal` 更具可读性。</span><span class="sxs-lookup"><span data-stu-id="6fca1-106">For example, a property named `HorizontalAlignment` is more English-readable than `AlignmentHorizontal`.</span></span>  
  
 <span data-ttu-id="6fca1-107">**✓ 务必** 使可读性优先于简洁性。</span><span class="sxs-lookup"><span data-stu-id="6fca1-107">**✓ DO** favor readability over brevity.</span></span>  
  
 <span data-ttu-id="6fca1-108">属性名称 `CanScrollHorizontally` 优于 `ScrollableX`（对 x 轴的指代显得模糊）。</span><span class="sxs-lookup"><span data-stu-id="6fca1-108">The property name `CanScrollHorizontally` is better than `ScrollableX` (an obscure reference to the X-axis).</span></span>  
  
 <span data-ttu-id="6fca1-109">**X 不要**使用下划线、连字符或任何其他非字母数字字符。</span><span class="sxs-lookup"><span data-stu-id="6fca1-109">**X DO NOT** use underscores, hyphens, or any other nonalphanumeric characters.</span></span>  
  
 <span data-ttu-id="6fca1-110">**X 不要**使用匈牙利表示法。</span><span class="sxs-lookup"><span data-stu-id="6fca1-110">**X DO NOT** use Hungarian notation.</span></span>  
  
 <span data-ttu-id="6fca1-111">**X 避免**使用与广泛应用的编程语言关键字冲突的标识符。</span><span class="sxs-lookup"><span data-stu-id="6fca1-111">**X AVOID** using identifiers that conflict with keywords of widely used programming languages.</span></span>  
  
 <span data-ttu-id="6fca1-112">根据公共语言规范 (CLS) 规则 4，所有兼容语言均须提供一种机制，通过该机制能够访问将该语言的关键字用作标识符的命名项。</span><span class="sxs-lookup"><span data-stu-id="6fca1-112">According to Rule 4 of the Common Language Specification (CLS), all compliant languages must provide a mechanism that allows access to named items that use a keyword of that language as an identifier.</span></span> <span data-ttu-id="6fca1-113">例如，C# 使用 @ 符号作为转义机制。</span><span class="sxs-lookup"><span data-stu-id="6fca1-113">C#, for example, uses the @ sign as an escape mechanism in this case.</span></span> <span data-ttu-id="6fca1-114">但是，仍然建议避免使用常用关键字，因为使用应用转义序列的方法比使用不应用转译序列的方法要困难得多。</span><span class="sxs-lookup"><span data-stu-id="6fca1-114">However, it is still a good idea to avoid common keywords because it is much more difficult to use a method with the escape sequence than one without it.</span></span>  
  
## <a name="using-abbreviations-and-acronyms"></a><span data-ttu-id="6fca1-115">使用缩写和首字母缩写词</span><span class="sxs-lookup"><span data-stu-id="6fca1-115">Using Abbreviations and Acronyms</span></span>  
 <span data-ttu-id="6fca1-116">**X 不要**在标识符名称中使用缩写形式或缩略形式。</span><span class="sxs-lookup"><span data-stu-id="6fca1-116">**X DO NOT** use abbreviations or contractions as part of identifier names.</span></span>  
  
 <span data-ttu-id="6fca1-117">例如，使用`GetWindow`而非`GetWin`。</span><span class="sxs-lookup"><span data-stu-id="6fca1-117">For example, use `GetWindow` rather than `GetWin`.</span></span>  
  
 <span data-ttu-id="6fca1-118">**X 不要**使用任何不常用的首字母缩写形式，即使是常用形式，也应只在必要时使用。</span><span class="sxs-lookup"><span data-stu-id="6fca1-118">**X DO NOT** use any acronyms that are not widely accepted, and even if they are, only when necessary.</span></span>  
  
## <a name="avoiding-language-specific-names"></a><span data-ttu-id="6fca1-119">避免特定于语言的名称</span><span class="sxs-lookup"><span data-stu-id="6fca1-119">Avoiding Language-Specific Names</span></span>  
 <span data-ttu-id="6fca1-120">**✓ 务必**使用在语义上有意义的名称而不是特定于语言的关键字作为类型名称。</span><span class="sxs-lookup"><span data-stu-id="6fca1-120">**✓ DO** use semantically interesting names rather than language-specific keywords for type names.</span></span>  
  
 <span data-ttu-id="6fca1-121">例如，`GetLength`是更好的名称比`GetInt`。</span><span class="sxs-lookup"><span data-stu-id="6fca1-121">For example, `GetLength` is a better name than `GetInt`.</span></span>  
  
 <span data-ttu-id="6fca1-122">**✓ 务必**在标识符不具有超出其类型以外的语义时（这是极少见的情况），使用泛型 CLR 类型名称，而不是特定于语言的名称。</span><span class="sxs-lookup"><span data-stu-id="6fca1-122">**✓ DO** use a generic CLR type name, rather than a language-specific name, in the rare cases when an identifier has no semantic meaning beyond its type.</span></span>  
  
 <span data-ttu-id="6fca1-123">例如，转换为 <xref:System.Int64> 的方法应命名为 `ToInt64`，而不是 `ToLong`（因为 <xref:System.Int64> 是特定于 C# 的别名 `long` 的 CLR 名称）。</span><span class="sxs-lookup"><span data-stu-id="6fca1-123">For example, a method converting to <xref:System.Int64> should be named `ToInt64`, not `ToLong` (because <xref:System.Int64> is a CLR name for the C#-specific alias `long`).</span></span> <span data-ttu-id="6fca1-124">下表列出了几种使用 CLR 类型名称（以及 C#、Visual Basic 和 C++ 的对应类型名称）的基本数据类型。</span><span class="sxs-lookup"><span data-stu-id="6fca1-124">The following table presents several base data types using the CLR type names (as well as the corresponding type names for C#, Visual Basic, and C++).</span></span>  
  
|<span data-ttu-id="6fca1-125">C#</span><span class="sxs-lookup"><span data-stu-id="6fca1-125">C#</span></span>|<span data-ttu-id="6fca1-126">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6fca1-126">Visual Basic</span></span>|<span data-ttu-id="6fca1-127">C++</span><span class="sxs-lookup"><span data-stu-id="6fca1-127">C++</span></span>|<span data-ttu-id="6fca1-128">CLR</span><span class="sxs-lookup"><span data-stu-id="6fca1-128">CLR</span></span>|  
|---------|------------------|-----------|---------|  
|<span data-ttu-id="6fca1-129">**sbyte**</span><span class="sxs-lookup"><span data-stu-id="6fca1-129">**sbyte**</span></span>|<span data-ttu-id="6fca1-130">**SByte**</span><span class="sxs-lookup"><span data-stu-id="6fca1-130">**SByte**</span></span>|<span data-ttu-id="6fca1-131">**char**</span><span class="sxs-lookup"><span data-stu-id="6fca1-131">**char**</span></span>|<span data-ttu-id="6fca1-132">**SByte**</span><span class="sxs-lookup"><span data-stu-id="6fca1-132">**SByte**</span></span>|  
|<span data-ttu-id="6fca1-133">**byte**</span><span class="sxs-lookup"><span data-stu-id="6fca1-133">**byte**</span></span>|<span data-ttu-id="6fca1-134">**Byte**</span><span class="sxs-lookup"><span data-stu-id="6fca1-134">**Byte**</span></span>|<span data-ttu-id="6fca1-135">**unsigned char**</span><span class="sxs-lookup"><span data-stu-id="6fca1-135">**unsigned char**</span></span>|<span data-ttu-id="6fca1-136">**Byte**</span><span class="sxs-lookup"><span data-stu-id="6fca1-136">**Byte**</span></span>|  
|<span data-ttu-id="6fca1-137">**short**</span><span class="sxs-lookup"><span data-stu-id="6fca1-137">**short**</span></span>|<span data-ttu-id="6fca1-138">**Short**</span><span class="sxs-lookup"><span data-stu-id="6fca1-138">**Short**</span></span>|<span data-ttu-id="6fca1-139">**short**</span><span class="sxs-lookup"><span data-stu-id="6fca1-139">**short**</span></span>|<span data-ttu-id="6fca1-140">**Int16**</span><span class="sxs-lookup"><span data-stu-id="6fca1-140">**Int16**</span></span>|  
|<span data-ttu-id="6fca1-141">**ushort**</span><span class="sxs-lookup"><span data-stu-id="6fca1-141">**ushort**</span></span>|<span data-ttu-id="6fca1-142">**UInt16**</span><span class="sxs-lookup"><span data-stu-id="6fca1-142">**UInt16**</span></span>|<span data-ttu-id="6fca1-143">**unsigned short**</span><span class="sxs-lookup"><span data-stu-id="6fca1-143">**unsigned short**</span></span>|<span data-ttu-id="6fca1-144">**UInt16**</span><span class="sxs-lookup"><span data-stu-id="6fca1-144">**UInt16**</span></span>|  
|<span data-ttu-id="6fca1-145">**int**</span><span class="sxs-lookup"><span data-stu-id="6fca1-145">**int**</span></span>|<span data-ttu-id="6fca1-146">**Integer**</span><span class="sxs-lookup"><span data-stu-id="6fca1-146">**Integer**</span></span>|<span data-ttu-id="6fca1-147">**int**</span><span class="sxs-lookup"><span data-stu-id="6fca1-147">**int**</span></span>|<span data-ttu-id="6fca1-148">**Int32**</span><span class="sxs-lookup"><span data-stu-id="6fca1-148">**Int32**</span></span>|  
|<span data-ttu-id="6fca1-149">**uint**</span><span class="sxs-lookup"><span data-stu-id="6fca1-149">**uint**</span></span>|<span data-ttu-id="6fca1-150">**UInt32**</span><span class="sxs-lookup"><span data-stu-id="6fca1-150">**UInt32**</span></span>|<span data-ttu-id="6fca1-151">**unsigned int**</span><span class="sxs-lookup"><span data-stu-id="6fca1-151">**unsigned int**</span></span>|<span data-ttu-id="6fca1-152">**UInt32**</span><span class="sxs-lookup"><span data-stu-id="6fca1-152">**UInt32**</span></span>|  
|<span data-ttu-id="6fca1-153">**long**</span><span class="sxs-lookup"><span data-stu-id="6fca1-153">**long**</span></span>|<span data-ttu-id="6fca1-154">**Long**</span><span class="sxs-lookup"><span data-stu-id="6fca1-154">**Long**</span></span>|<span data-ttu-id="6fca1-155">**__int64**</span><span class="sxs-lookup"><span data-stu-id="6fca1-155">**__int64**</span></span>|<span data-ttu-id="6fca1-156">**Int64**</span><span class="sxs-lookup"><span data-stu-id="6fca1-156">**Int64**</span></span>|  
|<span data-ttu-id="6fca1-157">**ulong**</span><span class="sxs-lookup"><span data-stu-id="6fca1-157">**ulong**</span></span>|<span data-ttu-id="6fca1-158">**UInt64**</span><span class="sxs-lookup"><span data-stu-id="6fca1-158">**UInt64**</span></span>|<span data-ttu-id="6fca1-159">unsigned __int64</span><span class="sxs-lookup"><span data-stu-id="6fca1-159">**unsigned __int64**</span></span>|<span data-ttu-id="6fca1-160">**UInt64**</span><span class="sxs-lookup"><span data-stu-id="6fca1-160">**UInt64**</span></span>|  
|<span data-ttu-id="6fca1-161">**float**</span><span class="sxs-lookup"><span data-stu-id="6fca1-161">**float**</span></span>|<span data-ttu-id="6fca1-162">**单精度**</span><span class="sxs-lookup"><span data-stu-id="6fca1-162">**Single**</span></span>|<span data-ttu-id="6fca1-163">**float**</span><span class="sxs-lookup"><span data-stu-id="6fca1-163">**float**</span></span>|<span data-ttu-id="6fca1-164">**单精度**</span><span class="sxs-lookup"><span data-stu-id="6fca1-164">**Single**</span></span>|  
|<span data-ttu-id="6fca1-165">**double**</span><span class="sxs-lookup"><span data-stu-id="6fca1-165">**double**</span></span>|<span data-ttu-id="6fca1-166">**双精度**</span><span class="sxs-lookup"><span data-stu-id="6fca1-166">**Double**</span></span>|<span data-ttu-id="6fca1-167">**double**</span><span class="sxs-lookup"><span data-stu-id="6fca1-167">**double**</span></span>|<span data-ttu-id="6fca1-168">**双精度**</span><span class="sxs-lookup"><span data-stu-id="6fca1-168">**Double**</span></span>|  
|<span data-ttu-id="6fca1-169">**bool**</span><span class="sxs-lookup"><span data-stu-id="6fca1-169">**bool**</span></span>|<span data-ttu-id="6fca1-170">**布尔值**</span><span class="sxs-lookup"><span data-stu-id="6fca1-170">**Boolean**</span></span>|<span data-ttu-id="6fca1-171">**bool**</span><span class="sxs-lookup"><span data-stu-id="6fca1-171">**bool**</span></span>|<span data-ttu-id="6fca1-172">**布尔值**</span><span class="sxs-lookup"><span data-stu-id="6fca1-172">**Boolean**</span></span>|  
|<span data-ttu-id="6fca1-173">**char**</span><span class="sxs-lookup"><span data-stu-id="6fca1-173">**char**</span></span>|<span data-ttu-id="6fca1-174">**Char**</span><span class="sxs-lookup"><span data-stu-id="6fca1-174">**Char**</span></span>|<span data-ttu-id="6fca1-175">**wchar_t**</span><span class="sxs-lookup"><span data-stu-id="6fca1-175">**wchar_t**</span></span>|<span data-ttu-id="6fca1-176">**Char**</span><span class="sxs-lookup"><span data-stu-id="6fca1-176">**Char**</span></span>|  
|<span data-ttu-id="6fca1-177">**string**</span><span class="sxs-lookup"><span data-stu-id="6fca1-177">**string**</span></span>|<span data-ttu-id="6fca1-178">**字符串**</span><span class="sxs-lookup"><span data-stu-id="6fca1-178">**String**</span></span>|<span data-ttu-id="6fca1-179">**字符串**</span><span class="sxs-lookup"><span data-stu-id="6fca1-179">**String**</span></span>|<span data-ttu-id="6fca1-180">**字符串**</span><span class="sxs-lookup"><span data-stu-id="6fca1-180">**String**</span></span>|  
|<span data-ttu-id="6fca1-181">**object**</span><span class="sxs-lookup"><span data-stu-id="6fca1-181">**object**</span></span>|<span data-ttu-id="6fca1-182">**对象**</span><span class="sxs-lookup"><span data-stu-id="6fca1-182">**Object**</span></span>|<span data-ttu-id="6fca1-183">**对象**</span><span class="sxs-lookup"><span data-stu-id="6fca1-183">**Object**</span></span>|<span data-ttu-id="6fca1-184">**对象**</span><span class="sxs-lookup"><span data-stu-id="6fca1-184">**Object**</span></span>|  
  
 <span data-ttu-id="6fca1-185">**✓ 务必**在标识符不具有语义含义且参数类型不重要时（这是极少见的情况），使用常用名称，例如 `value` 或 `item`，而不是重复使用类型名称。</span><span class="sxs-lookup"><span data-stu-id="6fca1-185">**✓ DO**  use a common name, such as `value` or `item`, rather than repeating the type name, in the rare cases when an identifier has no semantic meaning and the type of the parameter is not important.</span></span>  
  
## <a name="naming-new-versions-of-existing-apis"></a><span data-ttu-id="6fca1-186">为现有 API 的新版本命名</span><span class="sxs-lookup"><span data-stu-id="6fca1-186">Naming New Versions of Existing APIs</span></span>  
 <span data-ttu-id="6fca1-187">**✓ 务必**在创建现有 API 的新版本时，使用与旧 API 类似的名称。</span><span class="sxs-lookup"><span data-stu-id="6fca1-187">**✓ DO** use a name similar to the old API when creating new versions of an existing API.</span></span>  
  
 <span data-ttu-id="6fca1-188">这有助于体现 API 之间的关系。</span><span class="sxs-lookup"><span data-stu-id="6fca1-188">This helps to highlight the relationship between the APIs.</span></span>  
  
 <span data-ttu-id="6fca1-189">**✓ 务必**优先使用后缀而不是前缀来指示现有 API 的新版本。</span><span class="sxs-lookup"><span data-stu-id="6fca1-189">**✓ DO** prefer adding a suffix rather than a prefix to indicate a new version of an existing API.</span></span>  
  
 <span data-ttu-id="6fca1-190">这有助于在浏览文档或使用 IntelliSense 时更易发现所需内容。</span><span class="sxs-lookup"><span data-stu-id="6fca1-190">This will assist discovery when browsing documentation, or using IntelliSense.</span></span> <span data-ttu-id="6fca1-191">旧版 API 的组织方式与新版 API 接近，因为大多数浏览器和 IntelliSense 都按字母顺序显示标识符。</span><span class="sxs-lookup"><span data-stu-id="6fca1-191">The old version of the API will be organized close to the new APIs, because most browsers and IntelliSense show identifiers in alphabetical order.</span></span>  
  
 <span data-ttu-id="6fca1-192">**✓ CONSIDER** 使用全新，但有意义标识符，而不添加一个后缀或前缀。</span><span class="sxs-lookup"><span data-stu-id="6fca1-192">**✓ CONSIDER** using a brand new, but meaningful identifier, instead of adding a suffix or a prefix.</span></span>  
  
 <span data-ttu-id="6fca1-193">**✓ DO** 使用数字后缀指示新版本的现有 API，特别是当 API 的现有名称是 （即，如果它是一种行业标准） 有意义的唯一名称，而且如果添加任何有意义后缀 （或更改名称） 不是应用程序ropriate 选项。</span><span class="sxs-lookup"><span data-stu-id="6fca1-193">**✓ DO** use a numeric suffix to indicate a new version of an existing API, particularly if the existing name of the API is the only name that makes sense (i.e., if it is an industry standard) and if adding any meaningful suffix (or changing the name) is not an appropriate option.</span></span>  
  
 <span data-ttu-id="6fca1-194">**X DO NOT** 使用"Ex"（或类似） 的标识符，以区别于相同的 API 的早期版本的后缀。</span><span class="sxs-lookup"><span data-stu-id="6fca1-194">**X DO NOT** use the "Ex" (or a similar) suffix for an identifier to distinguish it from an earlier version of the same API.</span></span>  
  
 <span data-ttu-id="6fca1-195">**✓ DO** 引入 api，而不是一个 32 位整数的 64 位整数 （长整型） 上运行的版本时，使用"64"后缀。</span><span class="sxs-lookup"><span data-stu-id="6fca1-195">**✓ DO** use the "64" suffix when introducing versions of APIs that operate on a 64-bit integer (a long integer) instead of a 32-bit integer.</span></span> <span data-ttu-id="6fca1-196">只需现有的 32 位 API 存在; 时采用此方法不执行操作的使用仅 64 位版本的全新 Api。</span><span class="sxs-lookup"><span data-stu-id="6fca1-196">You only need to take this approach when the existing 32-bit API exists; don’t do it for brand new APIs with only a 64-bit version.</span></span>  
  
 <span data-ttu-id="6fca1-197">*部分 © 2005年，2009 Microsoft Corporation。保留所有权利。*</span><span class="sxs-lookup"><span data-stu-id="6fca1-197">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="6fca1-198">*通过从皮尔逊教育版，Inc.的权限重新打印[Framework 设计准则： 约定、 语法和可重用.NET 库，版本 2 的模式](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)通过 Krzysztof Cwalina 和 Brad Abrams，发布 2008 年 10 月 22，通过Microsoft Windows 开发系列的一部分的 Addison Wesley Professional。*</span><span class="sxs-lookup"><span data-stu-id="6fca1-198">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6fca1-199">请参阅</span><span class="sxs-lookup"><span data-stu-id="6fca1-199">See Also</span></span>  
 [<span data-ttu-id="6fca1-200">框架设计指南</span><span class="sxs-lookup"><span data-stu-id="6fca1-200">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
 [<span data-ttu-id="6fca1-201">命名规则</span><span class="sxs-lookup"><span data-stu-id="6fca1-201">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)
