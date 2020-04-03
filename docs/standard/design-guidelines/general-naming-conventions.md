---
title: 通用命名约定
ms.date: 10/22/2008
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
ms.openlocfilehash: ef4a8f571a67477739bbc59d3103ba78dea47177
ms.sourcegitcommit: 1c1a1f9ec0bd1efb3040d86a79f7ee94e207cca5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/03/2020
ms.locfileid: "80635922"
---
# <a name="general-naming-conventions"></a><span data-ttu-id="68b5c-102">通用命名约定</span><span class="sxs-lookup"><span data-stu-id="68b5c-102">General Naming Conventions</span></span>

<span data-ttu-id="68b5c-103">本节介绍与单词选择相关的一般命名约定、有关使用缩写和首字母缩略词的指南，以及如何避免使用特定于语言的名称的建议。</span><span class="sxs-lookup"><span data-stu-id="68b5c-103">This section describes general naming conventions that relate to word choice, guidelines on using abbreviations and acronyms, and recommendations on how to avoid using language-specific names.</span></span>

## <a name="word-choice"></a><span data-ttu-id="68b5c-104">字选择</span><span class="sxs-lookup"><span data-stu-id="68b5c-104">Word Choice</span></span>
 <span data-ttu-id="68b5c-105">✔️选择易于读的标识符名称。</span><span class="sxs-lookup"><span data-stu-id="68b5c-105">✔️ DO choose easily readable identifier names.</span></span>

 <span data-ttu-id="68b5c-106">例如，名为 的属性`HorizontalAlignment`比`AlignmentHorizontal`更具英语可读性。</span><span class="sxs-lookup"><span data-stu-id="68b5c-106">For example, a property named `HorizontalAlignment` is more English-readable than `AlignmentHorizontal`.</span></span>

 <span data-ttu-id="68b5c-107">✔️确实倾向于可读性而不是简洁性。</span><span class="sxs-lookup"><span data-stu-id="68b5c-107">✔️ DO favor readability over brevity.</span></span>

 <span data-ttu-id="68b5c-108">属性名称`CanScrollHorizontally`优于`ScrollableX`（对 X 轴的模糊引用）。</span><span class="sxs-lookup"><span data-stu-id="68b5c-108">The property name `CanScrollHorizontally` is better than `ScrollableX` (an obscure reference to the X-axis).</span></span>

 <span data-ttu-id="68b5c-109">❌请勿使用下划线、连字符或任何其他非字母数字字符。</span><span class="sxs-lookup"><span data-stu-id="68b5c-109">❌ DO NOT use underscores, hyphens, or any other nonalphanumeric characters.</span></span>

 <span data-ttu-id="68b5c-110">❌请勿使用匈牙利符号。</span><span class="sxs-lookup"><span data-stu-id="68b5c-110">❌ DO NOT use Hungarian notation.</span></span>

 <span data-ttu-id="68b5c-111">❌使用与广泛使用的编程语言的关键字冲突的标识符。</span><span class="sxs-lookup"><span data-stu-id="68b5c-111">❌ AVOID using identifiers that conflict with keywords of widely used programming languages.</span></span>

 <span data-ttu-id="68b5c-112">根据通用语言规范 （CLS） 的规则 4，所有兼容的语言都必须提供一种机制，允许访问使用该语言的关键字作为标识符的命名项。</span><span class="sxs-lookup"><span data-stu-id="68b5c-112">According to Rule 4 of the Common Language Specification (CLS), all compliant languages must provide a mechanism that allows access to named items that use a keyword of that language as an identifier.</span></span> <span data-ttu-id="68b5c-113">例如，在这种情况下，C# 使用 + 符号作为转义机制。</span><span class="sxs-lookup"><span data-stu-id="68b5c-113">C#, for example, uses the @ sign as an escape mechanism in this case.</span></span> <span data-ttu-id="68b5c-114">但是，最好避免使用常见关键字，因为使用具有转义序列的方法比没有它的方法要困难得多。</span><span class="sxs-lookup"><span data-stu-id="68b5c-114">However, it is still a good idea to avoid common keywords because it is much more difficult to use a method with the escape sequence than one without it.</span></span>

## <a name="using-abbreviations-and-acronyms"></a><span data-ttu-id="68b5c-115">使用缩写和缩略词</span><span class="sxs-lookup"><span data-stu-id="68b5c-115">Using Abbreviations and Acronyms</span></span>
 <span data-ttu-id="68b5c-116">❌请勿将缩写或缩略用作标识符名称的一部分。</span><span class="sxs-lookup"><span data-stu-id="68b5c-116">❌ DO NOT use abbreviations or contractions as part of identifier names.</span></span>

 <span data-ttu-id="68b5c-117">例如，使用`GetWindow`而不是`GetWin`。</span><span class="sxs-lookup"><span data-stu-id="68b5c-117">For example, use `GetWindow` rather than `GetWin`.</span></span>

 <span data-ttu-id="68b5c-118">❌不要使用任何未被广泛接受的首字母缩略词，即使它们是，也不得在必要时使用。</span><span class="sxs-lookup"><span data-stu-id="68b5c-118">❌ DO NOT use any acronyms that are not widely accepted, and even if they are, only when necessary.</span></span>

## <a name="avoiding-language-specific-names"></a><span data-ttu-id="68b5c-119">避免特定于语言的名称</span><span class="sxs-lookup"><span data-stu-id="68b5c-119">Avoiding Language-Specific Names</span></span>
 <span data-ttu-id="68b5c-120">✔️使用语义上有趣的名称，而不是特定于语言的关键字来输入类型名称。</span><span class="sxs-lookup"><span data-stu-id="68b5c-120">✔️ DO use semantically interesting names rather than language-specific keywords for type names.</span></span>

 <span data-ttu-id="68b5c-121">例如，`GetLength`比`GetInt`越好的名称。</span><span class="sxs-lookup"><span data-stu-id="68b5c-121">For example, `GetLength` is a better name than `GetInt`.</span></span>

 <span data-ttu-id="68b5c-122">✔️ DO 使用泛型 CLR 类型名称，而不是特定于语言的名称，在标识符在其类型之外没有语义含义的极少数情况下。</span><span class="sxs-lookup"><span data-stu-id="68b5c-122">✔️ DO use a generic CLR type name, rather than a language-specific name, in the rare cases when an identifier has no semantic meaning beyond its type.</span></span>

 <span data-ttu-id="68b5c-123">例如，转换<xref:System.Int64>到 的方法应命名为`ToInt64`，而不是`ToLong`（因为<xref:System.Int64>是特定于 C# 的别名`long`的 CLR 名称）。</span><span class="sxs-lookup"><span data-stu-id="68b5c-123">For example, a method converting to <xref:System.Int64> should be named `ToInt64`, not `ToLong` (because <xref:System.Int64> is a CLR name for the C#-specific alias `long`).</span></span> <span data-ttu-id="68b5c-124">下表使用 CLR 类型名称（以及 C#、Visual Basic 和C++的相应类型名称）提供了几种基本数据类型。</span><span class="sxs-lookup"><span data-stu-id="68b5c-124">The following table presents several base data types using the CLR type names (as well as the corresponding type names for C#, Visual Basic, and C++).</span></span>

|<span data-ttu-id="68b5c-125">C#</span><span class="sxs-lookup"><span data-stu-id="68b5c-125">C#</span></span>|<span data-ttu-id="68b5c-126">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="68b5c-126">Visual Basic</span></span>|<span data-ttu-id="68b5c-127">C++</span><span class="sxs-lookup"><span data-stu-id="68b5c-127">C++</span></span>|<span data-ttu-id="68b5c-128">CLR</span><span class="sxs-lookup"><span data-stu-id="68b5c-128">CLR</span></span>|
|---------|------------------|-----------|---------|
|<span data-ttu-id="68b5c-129">sbyte </span><span class="sxs-lookup"><span data-stu-id="68b5c-129">**sbyte**</span></span>|<span data-ttu-id="68b5c-130">**SByte**</span><span class="sxs-lookup"><span data-stu-id="68b5c-130">**SByte**</span></span>|<span data-ttu-id="68b5c-131">**char**</span><span class="sxs-lookup"><span data-stu-id="68b5c-131">**char**</span></span>|<span data-ttu-id="68b5c-132">**SByte**</span><span class="sxs-lookup"><span data-stu-id="68b5c-132">**SByte**</span></span>|
|<span data-ttu-id="68b5c-133">byte </span><span class="sxs-lookup"><span data-stu-id="68b5c-133">**byte**</span></span>|<span data-ttu-id="68b5c-134">**Byte**</span><span class="sxs-lookup"><span data-stu-id="68b5c-134">**Byte**</span></span>|<span data-ttu-id="68b5c-135">**unsigned char**</span><span class="sxs-lookup"><span data-stu-id="68b5c-135">**unsigned char**</span></span>|<span data-ttu-id="68b5c-136">**Byte**</span><span class="sxs-lookup"><span data-stu-id="68b5c-136">**Byte**</span></span>|
|<span data-ttu-id="68b5c-137">**short**</span><span class="sxs-lookup"><span data-stu-id="68b5c-137">**short**</span></span>|<span data-ttu-id="68b5c-138">**短**</span><span class="sxs-lookup"><span data-stu-id="68b5c-138">**Short**</span></span>|<span data-ttu-id="68b5c-139">**short**</span><span class="sxs-lookup"><span data-stu-id="68b5c-139">**short**</span></span>|<span data-ttu-id="68b5c-140">**Int16**</span><span class="sxs-lookup"><span data-stu-id="68b5c-140">**Int16**</span></span>|
|<span data-ttu-id="68b5c-141">**ushort**</span><span class="sxs-lookup"><span data-stu-id="68b5c-141">**ushort**</span></span>|<span data-ttu-id="68b5c-142">**UInt16**</span><span class="sxs-lookup"><span data-stu-id="68b5c-142">**UInt16**</span></span>|<span data-ttu-id="68b5c-143">**unsigned short**</span><span class="sxs-lookup"><span data-stu-id="68b5c-143">**unsigned short**</span></span>|<span data-ttu-id="68b5c-144">**UInt16**</span><span class="sxs-lookup"><span data-stu-id="68b5c-144">**UInt16**</span></span>|
|<span data-ttu-id="68b5c-145">**Int**</span><span class="sxs-lookup"><span data-stu-id="68b5c-145">**int**</span></span>|<span data-ttu-id="68b5c-146">**整数**</span><span class="sxs-lookup"><span data-stu-id="68b5c-146">**Integer**</span></span>|<span data-ttu-id="68b5c-147">**Int**</span><span class="sxs-lookup"><span data-stu-id="68b5c-147">**int**</span></span>|<span data-ttu-id="68b5c-148">**Int32**</span><span class="sxs-lookup"><span data-stu-id="68b5c-148">**Int32**</span></span>|
|<span data-ttu-id="68b5c-149">**uint**</span><span class="sxs-lookup"><span data-stu-id="68b5c-149">**uint**</span></span>|<span data-ttu-id="68b5c-150">**UInt32**</span><span class="sxs-lookup"><span data-stu-id="68b5c-150">**UInt32**</span></span>|<span data-ttu-id="68b5c-151">**unsigned int**</span><span class="sxs-lookup"><span data-stu-id="68b5c-151">**unsigned int**</span></span>|<span data-ttu-id="68b5c-152">**UInt32**</span><span class="sxs-lookup"><span data-stu-id="68b5c-152">**UInt32**</span></span>|
|<span data-ttu-id="68b5c-153">**长**</span><span class="sxs-lookup"><span data-stu-id="68b5c-153">**long**</span></span>|<span data-ttu-id="68b5c-154">**Long**</span><span class="sxs-lookup"><span data-stu-id="68b5c-154">**Long**</span></span>|<span data-ttu-id="68b5c-155">**__int64**</span><span class="sxs-lookup"><span data-stu-id="68b5c-155">**__int64**</span></span>|<span data-ttu-id="68b5c-156">**Int64**</span><span class="sxs-lookup"><span data-stu-id="68b5c-156">**Int64**</span></span>|
|<span data-ttu-id="68b5c-157">**乌龙**</span><span class="sxs-lookup"><span data-stu-id="68b5c-157">**ulong**</span></span>|<span data-ttu-id="68b5c-158">**UInt64**</span><span class="sxs-lookup"><span data-stu-id="68b5c-158">**UInt64**</span></span>|<span data-ttu-id="68b5c-159">unsigned __int64\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="68b5c-159">**unsigned __int64**</span></span>|<span data-ttu-id="68b5c-160">**UInt64**</span><span class="sxs-lookup"><span data-stu-id="68b5c-160">**UInt64**</span></span>|
|<span data-ttu-id="68b5c-161">**浮动**</span><span class="sxs-lookup"><span data-stu-id="68b5c-161">**float**</span></span>|<span data-ttu-id="68b5c-162">**单精度**</span><span class="sxs-lookup"><span data-stu-id="68b5c-162">**Single**</span></span>|<span data-ttu-id="68b5c-163">**浮动**</span><span class="sxs-lookup"><span data-stu-id="68b5c-163">**float**</span></span>|<span data-ttu-id="68b5c-164">**单精度**</span><span class="sxs-lookup"><span data-stu-id="68b5c-164">**Single**</span></span>|
|<span data-ttu-id="68b5c-165">**double**</span><span class="sxs-lookup"><span data-stu-id="68b5c-165">**double**</span></span>|<span data-ttu-id="68b5c-166">**双精度**</span><span class="sxs-lookup"><span data-stu-id="68b5c-166">**Double**</span></span>|<span data-ttu-id="68b5c-167">**double**</span><span class="sxs-lookup"><span data-stu-id="68b5c-167">**double**</span></span>|<span data-ttu-id="68b5c-168">**双精度**</span><span class="sxs-lookup"><span data-stu-id="68b5c-168">**Double**</span></span>|
|<span data-ttu-id="68b5c-169">**bool**</span><span class="sxs-lookup"><span data-stu-id="68b5c-169">**bool**</span></span>|<span data-ttu-id="68b5c-170">**布尔值**</span><span class="sxs-lookup"><span data-stu-id="68b5c-170">**Boolean**</span></span>|<span data-ttu-id="68b5c-171">**bool**</span><span class="sxs-lookup"><span data-stu-id="68b5c-171">**bool**</span></span>|<span data-ttu-id="68b5c-172">**布尔值**</span><span class="sxs-lookup"><span data-stu-id="68b5c-172">**Boolean**</span></span>|
|<span data-ttu-id="68b5c-173">**char**</span><span class="sxs-lookup"><span data-stu-id="68b5c-173">**char**</span></span>|<span data-ttu-id="68b5c-174">**Char**</span><span class="sxs-lookup"><span data-stu-id="68b5c-174">**Char**</span></span>|<span data-ttu-id="68b5c-175">**wchar_t**</span><span class="sxs-lookup"><span data-stu-id="68b5c-175">**wchar_t**</span></span>|<span data-ttu-id="68b5c-176">**Char**</span><span class="sxs-lookup"><span data-stu-id="68b5c-176">**Char**</span></span>|
|<span data-ttu-id="68b5c-177">**string**</span><span class="sxs-lookup"><span data-stu-id="68b5c-177">**string**</span></span>|<span data-ttu-id="68b5c-178">**字符串**</span><span class="sxs-lookup"><span data-stu-id="68b5c-178">**String**</span></span>|<span data-ttu-id="68b5c-179">**字符串**</span><span class="sxs-lookup"><span data-stu-id="68b5c-179">**String**</span></span>|<span data-ttu-id="68b5c-180">**字符串**</span><span class="sxs-lookup"><span data-stu-id="68b5c-180">**String**</span></span>|
|<span data-ttu-id="68b5c-181">**对象**</span><span class="sxs-lookup"><span data-stu-id="68b5c-181">**object**</span></span>|<span data-ttu-id="68b5c-182">**Object**</span><span class="sxs-lookup"><span data-stu-id="68b5c-182">**Object**</span></span>|<span data-ttu-id="68b5c-183">**Object**</span><span class="sxs-lookup"><span data-stu-id="68b5c-183">**Object**</span></span>|<span data-ttu-id="68b5c-184">**Object**</span><span class="sxs-lookup"><span data-stu-id="68b5c-184">**Object**</span></span>|

 <span data-ttu-id="68b5c-185">✔️ DO 使用公共名称，如`value``item`或 ，而不是重复类型名称，在标识符没有语义含义且参数类型并不重要的罕见情况下。</span><span class="sxs-lookup"><span data-stu-id="68b5c-185">✔️ DO  use a common name, such as `value` or `item`, rather than repeating the type name, in the rare cases when an identifier has no semantic meaning and the type of the parameter is not important.</span></span>

## <a name="naming-new-versions-of-existing-apis"></a><span data-ttu-id="68b5c-186">命名现有 API 的新版本</span><span class="sxs-lookup"><span data-stu-id="68b5c-186">Naming New Versions of Existing APIs</span></span>
 <span data-ttu-id="68b5c-187">✔️在现有 API 的新版本创建时，请使用与旧 API 类似的名称。</span><span class="sxs-lookup"><span data-stu-id="68b5c-187">✔️ DO use a name similar to the old API when creating new versions of an existing API.</span></span>

 <span data-ttu-id="68b5c-188">这有助于突出显示 API 之间的关系。</span><span class="sxs-lookup"><span data-stu-id="68b5c-188">This helps to highlight the relationship between the APIs.</span></span>

 <span data-ttu-id="68b5c-189">✔️喜欢添加后缀而不是前缀来指示现有 API 的新版本。</span><span class="sxs-lookup"><span data-stu-id="68b5c-189">✔️ DO prefer adding a suffix rather than a prefix to indicate a new version of an existing API.</span></span>

 <span data-ttu-id="68b5c-190">这将有助于在浏览文档或使用 IntelliSense 时发现。</span><span class="sxs-lookup"><span data-stu-id="68b5c-190">This will assist discovery when browsing documentation, or using IntelliSense.</span></span> <span data-ttu-id="68b5c-191">API 的旧版本将组织在新 API 附近，因为大多数浏览器和 IntelliSense 都按字母顺序显示标识符。</span><span class="sxs-lookup"><span data-stu-id="68b5c-191">The old version of the API will be organized close to the new APIs, because most browsers and IntelliSense show identifiers in alphabetical order.</span></span>

 <span data-ttu-id="68b5c-192">✔️考虑使用全新但有意义的标识符，而不是添加后缀或前缀。</span><span class="sxs-lookup"><span data-stu-id="68b5c-192">✔️ CONSIDER using a brand new, but meaningful identifier, instead of adding a suffix or a prefix.</span></span>

 <span data-ttu-id="68b5c-193">✔️使用数字后缀来指示现有 API 的新版本，特别是如果 API 的现有名称是唯一有意义的名称（即，如果它是行业标准），并且添加任何有意义的后缀（或更改名称）不是适当的选项。</span><span class="sxs-lookup"><span data-stu-id="68b5c-193">✔️ DO use a numeric suffix to indicate a new version of an existing API, particularly if the existing name of the API is the only name that makes sense (i.e., if it is an industry standard) and if adding any meaningful suffix (or changing the name) is not an appropriate option.</span></span>

 <span data-ttu-id="68b5c-194">❌请勿使用标识符的"Ex"（或类似）后缀来区分它与同一 API 的早期版本。</span><span class="sxs-lookup"><span data-stu-id="68b5c-194">❌ DO NOT use the "Ex" (or a similar) suffix for an identifier to distinguish it from an earlier version of the same API.</span></span>

 <span data-ttu-id="68b5c-195">✔️在引入使用 64 位整数（长整数）而不是 32 位整数的 API 版本时，请使用"64"后缀。</span><span class="sxs-lookup"><span data-stu-id="68b5c-195">✔️ DO use the "64" suffix when introducing versions of APIs that operate on a 64-bit integer (a long integer) instead of a 32-bit integer.</span></span> <span data-ttu-id="68b5c-196">仅当存在现有的 32 位 API 时，才需要采用此方法;不要为只有 64 位版本的全新 API 执行此操作。</span><span class="sxs-lookup"><span data-stu-id="68b5c-196">You only need to take this approach when the existing 32-bit API exists; don't do it for brand new APIs with only a 64-bit version.</span></span>

 <span data-ttu-id="68b5c-197">*部分&copy;2005， 2009 微软公司.保留所有权利。*</span><span class="sxs-lookup"><span data-stu-id="68b5c-197">*Portions &copy; 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="68b5c-198">*经 Pearson 教育公司许可，从[框架设计指南：可重用的约定、习语和模式 .NET 库重新打印，第二版](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)由 Krzysztof Cwalina 和 Brad Abrams 出版，由艾迪森-韦斯利专业公司作为微软 Windows 开发系列的一部分于 2008 年 10 月 22 日出版。*</span><span class="sxs-lookup"><span data-stu-id="68b5c-198">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="68b5c-199">请参阅</span><span class="sxs-lookup"><span data-stu-id="68b5c-199">See also</span></span>

- [<span data-ttu-id="68b5c-200">框架设计准则</span><span class="sxs-lookup"><span data-stu-id="68b5c-200">Framework design guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="68b5c-201">命名指南</span><span class="sxs-lookup"><span data-stu-id="68b5c-201">Naming guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)
- [<span data-ttu-id="68b5c-202">EditorConfig 适用的 .NET 命名约定</span><span class="sxs-lookup"><span data-stu-id="68b5c-202">.NET naming conventions for EditorConfig</span></span>](/visualstudio/ide/editorconfig-naming-conventions)
