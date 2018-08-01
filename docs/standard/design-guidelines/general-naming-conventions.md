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
# <a name="general-naming-conventions"></a><span data-ttu-id="aef3c-102">通用命名约定</span><span class="sxs-lookup"><span data-stu-id="aef3c-102">General Naming Conventions</span></span>
<span data-ttu-id="aef3c-103">本部分介绍与单词选择相关的一般命名约定、缩略词和首字母缩写词的使用准则以及有关如何避免使用特定于语言的名称的建议。</span><span class="sxs-lookup"><span data-stu-id="aef3c-103">This section describes general naming conventions that relate to word choice, guidelines on using abbreviations and acronyms, and recommendations on how to avoid using language-specific names.</span></span>  
  
## <a name="word-choice"></a><span data-ttu-id="aef3c-104">选词</span><span class="sxs-lookup"><span data-stu-id="aef3c-104">Word Choice</span></span>  
 <span data-ttu-id="aef3c-105">**✓ DO** 选择易读的标识符名称。</span><span class="sxs-lookup"><span data-stu-id="aef3c-105">**✓ DO** choose easily readable identifier names.</span></span>  
  
 <span data-ttu-id="aef3c-106">例如，名为的属性`HorizontalAlignment`是英语-可读性比`AlignmentHorizontal`。</span><span class="sxs-lookup"><span data-stu-id="aef3c-106">For example, a property named `HorizontalAlignment` is more English-readable than `AlignmentHorizontal`.</span></span>  
  
 <span data-ttu-id="aef3c-107">**✓ DO** 可读性比简洁性更。</span><span class="sxs-lookup"><span data-stu-id="aef3c-107">**✓ DO** favor readability over brevity.</span></span>  
  
 <span data-ttu-id="aef3c-108">属性名称`CanScrollHorizontally`优于`ScrollableX`（对 x 轴的晦涩引用）。</span><span class="sxs-lookup"><span data-stu-id="aef3c-108">The property name `CanScrollHorizontally` is better than `ScrollableX` (an obscure reference to the X-axis).</span></span>  
  
 <span data-ttu-id="aef3c-109">**X DO NOT** 使用下划线、 连字符或任何其他非字母数字字符。</span><span class="sxs-lookup"><span data-stu-id="aef3c-109">**X DO NOT** use underscores, hyphens, or any other nonalphanumeric characters.</span></span>  
  
 <span data-ttu-id="aef3c-110">**X DO NOT** 使用匈牙利语表示法。</span><span class="sxs-lookup"><span data-stu-id="aef3c-110">**X DO NOT** use Hungarian notation.</span></span>  
  
 <span data-ttu-id="aef3c-111">**X AVOID** 使用广泛与关键字冲突的标识符使用编程语言。</span><span class="sxs-lookup"><span data-stu-id="aef3c-111">**X AVOID** using identifiers that conflict with keywords of widely used programming languages.</span></span>  
  
 <span data-ttu-id="aef3c-112">根据规则 4 的公共语言规范 (CLS)，所有符合语言必须提供一种机制，允许访问将该语言关键字用作标识符的命名项。</span><span class="sxs-lookup"><span data-stu-id="aef3c-112">According to Rule 4 of the Common Language Specification (CLS), all compliant languages must provide a mechanism that allows access to named items that use a keyword of that language as an identifier.</span></span> <span data-ttu-id="aef3c-113">C# 中，例如，使用 @ 符号作为转义机制在此情况下。</span><span class="sxs-lookup"><span data-stu-id="aef3c-113">C#, for example, uses the @ sign as an escape mechanism in this case.</span></span> <span data-ttu-id="aef3c-114">但是，它仍是一个好办法避免常见的关键字，因为它是要使用的方法与另一个没有它比转义序列困难得多。</span><span class="sxs-lookup"><span data-stu-id="aef3c-114">However, it is still a good idea to avoid common keywords because it is much more difficult to use a method with the escape sequence than one without it.</span></span>  
  
## <a name="using-abbreviations-and-acronyms"></a><span data-ttu-id="aef3c-115">使用缩写和首字母缩写词</span><span class="sxs-lookup"><span data-stu-id="aef3c-115">Using Abbreviations and Acronyms</span></span>  
 <span data-ttu-id="aef3c-116">**X DO NOT** 缩写用作标识符名称的一部分。</span><span class="sxs-lookup"><span data-stu-id="aef3c-116">**X DO NOT** use abbreviations or contractions as part of identifier names.</span></span>  
  
 <span data-ttu-id="aef3c-117">例如，使用`GetWindow`而非`GetWin`。</span><span class="sxs-lookup"><span data-stu-id="aef3c-117">For example, use `GetWindow` rather than `GetWin`.</span></span>  
  
 <span data-ttu-id="aef3c-118">**X DO NOT** 使用并不被广泛接受，即使它们是，仅在必要时任何首字母缩写词。</span><span class="sxs-lookup"><span data-stu-id="aef3c-118">**X DO NOT** use any acronyms that are not widely accepted, and even if they are, only when necessary.</span></span>  
  
## <a name="avoiding-language-specific-names"></a><span data-ttu-id="aef3c-119">避免特定于语言的名称</span><span class="sxs-lookup"><span data-stu-id="aef3c-119">Avoiding Language-Specific Names</span></span>  
 <span data-ttu-id="aef3c-120">**✓ DO** 使用类型名称在语义上是有意义的名称，而不是特定于语言的关键字。</span><span class="sxs-lookup"><span data-stu-id="aef3c-120">**✓ DO** use semantically interesting names rather than language-specific keywords for type names.</span></span>  
  
 <span data-ttu-id="aef3c-121">例如，`GetLength`是更好的名称比`GetInt`。</span><span class="sxs-lookup"><span data-stu-id="aef3c-121">For example, `GetLength` is a better name than `GetInt`.</span></span>  
  
 <span data-ttu-id="aef3c-122">**✓ DO** 在极少数情况下在标识符的语义含义仅限于其类型中使用泛型的 CLR 类型名称，而不是使用语言特定的名称。</span><span class="sxs-lookup"><span data-stu-id="aef3c-122">**✓ DO** use a generic CLR type name, rather than a language-specific name, in the rare cases when an identifier has no semantic meaning beyond its type.</span></span>  
  
 <span data-ttu-id="aef3c-123">例如，将转换为方法<xref:System.Int64>应该被命名为`ToInt64`，而不`ToLong`(因为<xref:System.Int64>是 C# 的 CLR 名称-特定别名`long`)。</span><span class="sxs-lookup"><span data-stu-id="aef3c-123">For example, a method converting to <xref:System.Int64> should be named `ToInt64`, not `ToLong` (because <xref:System.Int64> is a CLR name for the C#-specific alias `long`).</span></span> <span data-ttu-id="aef3c-124">下表列出了几种使用 CLR 类型名称 （以及相应的类型名称为 C#、 Visual Basic 和 c + +） 的基本数据类型。</span><span class="sxs-lookup"><span data-stu-id="aef3c-124">The following table presents several base data types using the CLR type names (as well as the corresponding type names for C#, Visual Basic, and C++).</span></span>  
  
|<span data-ttu-id="aef3c-125">C#</span><span class="sxs-lookup"><span data-stu-id="aef3c-125">C#</span></span>|<span data-ttu-id="aef3c-126">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="aef3c-126">Visual Basic</span></span>|<span data-ttu-id="aef3c-127">C++</span><span class="sxs-lookup"><span data-stu-id="aef3c-127">C++</span></span>|<span data-ttu-id="aef3c-128">CLR</span><span class="sxs-lookup"><span data-stu-id="aef3c-128">CLR</span></span>|  
|---------|------------------|-----------|---------|  
|<span data-ttu-id="aef3c-129">**sbyte**</span><span class="sxs-lookup"><span data-stu-id="aef3c-129">**sbyte**</span></span>|<span data-ttu-id="aef3c-130">**SByte**</span><span class="sxs-lookup"><span data-stu-id="aef3c-130">**SByte**</span></span>|<span data-ttu-id="aef3c-131">**char**</span><span class="sxs-lookup"><span data-stu-id="aef3c-131">**char**</span></span>|<span data-ttu-id="aef3c-132">**SByte**</span><span class="sxs-lookup"><span data-stu-id="aef3c-132">**SByte**</span></span>|  
|<span data-ttu-id="aef3c-133">**byte**</span><span class="sxs-lookup"><span data-stu-id="aef3c-133">**byte**</span></span>|<span data-ttu-id="aef3c-134">**Byte**</span><span class="sxs-lookup"><span data-stu-id="aef3c-134">**Byte**</span></span>|<span data-ttu-id="aef3c-135">**unsigned char**</span><span class="sxs-lookup"><span data-stu-id="aef3c-135">**unsigned char**</span></span>|<span data-ttu-id="aef3c-136">**Byte**</span><span class="sxs-lookup"><span data-stu-id="aef3c-136">**Byte**</span></span>|  
|<span data-ttu-id="aef3c-137">**short**</span><span class="sxs-lookup"><span data-stu-id="aef3c-137">**short**</span></span>|<span data-ttu-id="aef3c-138">**Short**</span><span class="sxs-lookup"><span data-stu-id="aef3c-138">**Short**</span></span>|<span data-ttu-id="aef3c-139">**short**</span><span class="sxs-lookup"><span data-stu-id="aef3c-139">**short**</span></span>|<span data-ttu-id="aef3c-140">**Int16**</span><span class="sxs-lookup"><span data-stu-id="aef3c-140">**Int16**</span></span>|  
|<span data-ttu-id="aef3c-141">**ushort**</span><span class="sxs-lookup"><span data-stu-id="aef3c-141">**ushort**</span></span>|<span data-ttu-id="aef3c-142">**UInt16**</span><span class="sxs-lookup"><span data-stu-id="aef3c-142">**UInt16**</span></span>|<span data-ttu-id="aef3c-143">**unsigned short**</span><span class="sxs-lookup"><span data-stu-id="aef3c-143">**unsigned short**</span></span>|<span data-ttu-id="aef3c-144">**UInt16**</span><span class="sxs-lookup"><span data-stu-id="aef3c-144">**UInt16**</span></span>|  
|<span data-ttu-id="aef3c-145">**int**</span><span class="sxs-lookup"><span data-stu-id="aef3c-145">**int**</span></span>|<span data-ttu-id="aef3c-146">**Integer**</span><span class="sxs-lookup"><span data-stu-id="aef3c-146">**Integer**</span></span>|<span data-ttu-id="aef3c-147">**int**</span><span class="sxs-lookup"><span data-stu-id="aef3c-147">**int**</span></span>|<span data-ttu-id="aef3c-148">**Int32**</span><span class="sxs-lookup"><span data-stu-id="aef3c-148">**Int32**</span></span>|  
|<span data-ttu-id="aef3c-149">**uint**</span><span class="sxs-lookup"><span data-stu-id="aef3c-149">**uint**</span></span>|<span data-ttu-id="aef3c-150">**UInt32**</span><span class="sxs-lookup"><span data-stu-id="aef3c-150">**UInt32**</span></span>|<span data-ttu-id="aef3c-151">**unsigned int**</span><span class="sxs-lookup"><span data-stu-id="aef3c-151">**unsigned int**</span></span>|<span data-ttu-id="aef3c-152">**UInt32**</span><span class="sxs-lookup"><span data-stu-id="aef3c-152">**UInt32**</span></span>|  
|<span data-ttu-id="aef3c-153">**long**</span><span class="sxs-lookup"><span data-stu-id="aef3c-153">**long**</span></span>|<span data-ttu-id="aef3c-154">**Long**</span><span class="sxs-lookup"><span data-stu-id="aef3c-154">**Long**</span></span>|<span data-ttu-id="aef3c-155">**__int64**</span><span class="sxs-lookup"><span data-stu-id="aef3c-155">**__int64**</span></span>|<span data-ttu-id="aef3c-156">**Int64**</span><span class="sxs-lookup"><span data-stu-id="aef3c-156">**Int64**</span></span>|  
|<span data-ttu-id="aef3c-157">**ulong**</span><span class="sxs-lookup"><span data-stu-id="aef3c-157">**ulong**</span></span>|<span data-ttu-id="aef3c-158">**UInt64**</span><span class="sxs-lookup"><span data-stu-id="aef3c-158">**UInt64**</span></span>|<span data-ttu-id="aef3c-159">unsigned __int64</span><span class="sxs-lookup"><span data-stu-id="aef3c-159">**unsigned __int64**</span></span>|<span data-ttu-id="aef3c-160">**UInt64**</span><span class="sxs-lookup"><span data-stu-id="aef3c-160">**UInt64**</span></span>|  
|<span data-ttu-id="aef3c-161">**float**</span><span class="sxs-lookup"><span data-stu-id="aef3c-161">**float**</span></span>|<span data-ttu-id="aef3c-162">**单精度**</span><span class="sxs-lookup"><span data-stu-id="aef3c-162">**Single**</span></span>|<span data-ttu-id="aef3c-163">**float**</span><span class="sxs-lookup"><span data-stu-id="aef3c-163">**float**</span></span>|<span data-ttu-id="aef3c-164">**单精度**</span><span class="sxs-lookup"><span data-stu-id="aef3c-164">**Single**</span></span>|  
|<span data-ttu-id="aef3c-165">**double**</span><span class="sxs-lookup"><span data-stu-id="aef3c-165">**double**</span></span>|<span data-ttu-id="aef3c-166">**双精度**</span><span class="sxs-lookup"><span data-stu-id="aef3c-166">**Double**</span></span>|<span data-ttu-id="aef3c-167">**double**</span><span class="sxs-lookup"><span data-stu-id="aef3c-167">**double**</span></span>|<span data-ttu-id="aef3c-168">**双精度**</span><span class="sxs-lookup"><span data-stu-id="aef3c-168">**Double**</span></span>|  
|<span data-ttu-id="aef3c-169">**bool**</span><span class="sxs-lookup"><span data-stu-id="aef3c-169">**bool**</span></span>|<span data-ttu-id="aef3c-170">**布尔值**</span><span class="sxs-lookup"><span data-stu-id="aef3c-170">**Boolean**</span></span>|<span data-ttu-id="aef3c-171">**bool**</span><span class="sxs-lookup"><span data-stu-id="aef3c-171">**bool**</span></span>|<span data-ttu-id="aef3c-172">**布尔值**</span><span class="sxs-lookup"><span data-stu-id="aef3c-172">**Boolean**</span></span>|  
|<span data-ttu-id="aef3c-173">**char**</span><span class="sxs-lookup"><span data-stu-id="aef3c-173">**char**</span></span>|<span data-ttu-id="aef3c-174">**Char**</span><span class="sxs-lookup"><span data-stu-id="aef3c-174">**Char**</span></span>|<span data-ttu-id="aef3c-175">**wchar_t**</span><span class="sxs-lookup"><span data-stu-id="aef3c-175">**wchar_t**</span></span>|<span data-ttu-id="aef3c-176">**Char**</span><span class="sxs-lookup"><span data-stu-id="aef3c-176">**Char**</span></span>|  
|<span data-ttu-id="aef3c-177">**string**</span><span class="sxs-lookup"><span data-stu-id="aef3c-177">**string**</span></span>|<span data-ttu-id="aef3c-178">**字符串**</span><span class="sxs-lookup"><span data-stu-id="aef3c-178">**String**</span></span>|<span data-ttu-id="aef3c-179">**字符串**</span><span class="sxs-lookup"><span data-stu-id="aef3c-179">**String**</span></span>|<span data-ttu-id="aef3c-180">**字符串**</span><span class="sxs-lookup"><span data-stu-id="aef3c-180">**String**</span></span>|  
|<span data-ttu-id="aef3c-181">**object**</span><span class="sxs-lookup"><span data-stu-id="aef3c-181">**object**</span></span>|<span data-ttu-id="aef3c-182">**对象**</span><span class="sxs-lookup"><span data-stu-id="aef3c-182">**Object**</span></span>|<span data-ttu-id="aef3c-183">**对象**</span><span class="sxs-lookup"><span data-stu-id="aef3c-183">**Object**</span></span>|<span data-ttu-id="aef3c-184">**对象**</span><span class="sxs-lookup"><span data-stu-id="aef3c-184">**Object**</span></span>|  
  
 <span data-ttu-id="aef3c-185">**✓ DO** 使用公用名，如`value`或`item`，而不是重复的类型名称，在极少数的情况下当的标识符具有任何语义含义和参数的类型并不重要。</span><span class="sxs-lookup"><span data-stu-id="aef3c-185">**✓ DO**  use a common name, such as `value` or `item`, rather than repeating the type name, in the rare cases when an identifier has no semantic meaning and the type of the parameter is not important.</span></span>  
  
## <a name="naming-new-versions-of-existing-apis"></a><span data-ttu-id="aef3c-186">命名新版本的现有的 Api</span><span class="sxs-lookup"><span data-stu-id="aef3c-186">Naming New Versions of Existing APIs</span></span>  
 <span data-ttu-id="aef3c-187">**✓ DO** 时创建的现有 API 的新版本使用类似于旧 API 的名称。</span><span class="sxs-lookup"><span data-stu-id="aef3c-187">**✓ DO** use a name similar to the old API when creating new versions of an existing API.</span></span>  
  
 <span data-ttu-id="aef3c-188">这有助于突出显示 Api 之间的关系。</span><span class="sxs-lookup"><span data-stu-id="aef3c-188">This helps to highlight the relationship between the APIs.</span></span>  
  
 <span data-ttu-id="aef3c-189">**✓ DO** 喜欢添加一个后缀，而不是以指示现有 API 的新版本的前缀。</span><span class="sxs-lookup"><span data-stu-id="aef3c-189">**✓ DO** prefer adding a suffix rather than a prefix to indicate a new version of an existing API.</span></span>  
  
 <span data-ttu-id="aef3c-190">这将帮助发现浏览文档，或使用 IntelliSense。</span><span class="sxs-lookup"><span data-stu-id="aef3c-190">This will assist discovery when browsing documentation, or using IntelliSense.</span></span> <span data-ttu-id="aef3c-191">将新的 Api，接近组织旧版本的 API，因为大多数浏览器和 IntelliSense 按字母顺序显示标识符。</span><span class="sxs-lookup"><span data-stu-id="aef3c-191">The old version of the API will be organized close to the new APIs, because most browsers and IntelliSense show identifiers in alphabetical order.</span></span>  
  
 <span data-ttu-id="aef3c-192">**✓ CONSIDER** 使用全新，但有意义标识符，而不添加一个后缀或前缀。</span><span class="sxs-lookup"><span data-stu-id="aef3c-192">**✓ CONSIDER** using a brand new, but meaningful identifier, instead of adding a suffix or a prefix.</span></span>  
  
 <span data-ttu-id="aef3c-193">**✓ DO** 使用数字后缀指示新版本的现有 API，特别是当 API 的现有名称是 （即，如果它是一种行业标准） 有意义的唯一名称，而且如果添加任何有意义后缀 （或更改名称） 不是应用程序ropriate 选项。</span><span class="sxs-lookup"><span data-stu-id="aef3c-193">**✓ DO** use a numeric suffix to indicate a new version of an existing API, particularly if the existing name of the API is the only name that makes sense (i.e., if it is an industry standard) and if adding any meaningful suffix (or changing the name) is not an appropriate option.</span></span>  
  
 <span data-ttu-id="aef3c-194">**X DO NOT** 使用"Ex"（或类似） 的标识符，以区别于相同的 API 的早期版本的后缀。</span><span class="sxs-lookup"><span data-stu-id="aef3c-194">**X DO NOT** use the "Ex" (or a similar) suffix for an identifier to distinguish it from an earlier version of the same API.</span></span>  
  
 <span data-ttu-id="aef3c-195">**✓ DO** 引入 api，而不是一个 32 位整数的 64 位整数 （长整型） 上运行的版本时，使用"64"后缀。</span><span class="sxs-lookup"><span data-stu-id="aef3c-195">**✓ DO** use the "64" suffix when introducing versions of APIs that operate on a 64-bit integer (a long integer) instead of a 32-bit integer.</span></span> <span data-ttu-id="aef3c-196">只需现有的 32 位 API 存在; 时采用此方法不执行操作的使用仅 64 位版本的全新 Api。</span><span class="sxs-lookup"><span data-stu-id="aef3c-196">You only need to take this approach when the existing 32-bit API exists; don’t do it for brand new APIs with only a 64-bit version.</span></span>  
  
 <span data-ttu-id="aef3c-197">*部分 © 2005年，2009 Microsoft Corporation。保留所有权利。*</span><span class="sxs-lookup"><span data-stu-id="aef3c-197">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="aef3c-198">*通过从皮尔逊教育版，Inc.的权限重新打印[Framework 设计准则： 约定、 语法和可重用.NET 库，版本 2 的模式](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)通过 Krzysztof Cwalina 和 Brad Abrams，发布 2008 年 10 月 22，通过Microsoft Windows 开发系列的一部分的 Addison Wesley Professional。*</span><span class="sxs-lookup"><span data-stu-id="aef3c-198">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aef3c-199">请参阅</span><span class="sxs-lookup"><span data-stu-id="aef3c-199">See Also</span></span>  
 [<span data-ttu-id="aef3c-200">框架设计指南</span><span class="sxs-lookup"><span data-stu-id="aef3c-200">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
 [<span data-ttu-id="aef3c-201">命名规则</span><span class="sxs-lookup"><span data-stu-id="aef3c-201">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)
