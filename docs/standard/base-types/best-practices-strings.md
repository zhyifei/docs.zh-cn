---
title: "有关使用字符串的最佳实践"
description: "有关使用字符串的最佳实践"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
manager: wpickett
ms.date: 07/26/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: b3cefaa4-0a3f-4a96-aba9-1de30fb07c29
ms.translationtype: Human Translation
ms.sourcegitcommit: b20713600d7c3ddc31be5885733a1e8910ede8c6
ms.openlocfilehash: 3efd30bade564fe1b7dbf93237a9ff40c58c5f1e
ms.contentlocale: zh-cn
ms.lasthandoff: 11/05/2016

---

# <a name="best-practices-for-using-strings"></a><span data-ttu-id="a1639-104">有关使用字符串的最佳实践</span><span class="sxs-lookup"><span data-stu-id="a1639-104">Best practices for using strings</span></span>

<span data-ttu-id="a1639-105">.NET 为开发本地化和全球化应用程序提供广泛支持，在执行排序和显示字符串等常见操作时，轻松应用当前区域性或特定区域性的约定。</span><span class="sxs-lookup"><span data-stu-id="a1639-105">.NET provides extensive support for developing localized and globalized applications, and makes it easy to apply the conventions of either the current culture or a specific culture when performing common operations such as sorting and displaying strings.</span></span> <span data-ttu-id="a1639-106">但排序或比较字符串并不总是区分区域性的操作。</span><span class="sxs-lookup"><span data-stu-id="a1639-106">But sorting or comparing strings is not always a culture-sensitive operation.</span></span> <span data-ttu-id="a1639-107">例如，对于应用程序内部使用的字符串，通常应该跨所有区域性以相同的方式对其进行处理。</span><span class="sxs-lookup"><span data-stu-id="a1639-107">For example, strings that are used internally by an application typically should be handled identically across all cultures.</span></span> <span data-ttu-id="a1639-108">如果将 XML 标记、HTML 标记、用户名、文件路径和系统对象名称等与区域性无关的字符串数据解释为区分区域性，则应用程序代码会遭遇细微的错误、不佳的性能，在某些情况下，还会遭遇安全性问题。</span><span class="sxs-lookup"><span data-stu-id="a1639-108">When culturally independent string data, such as XML tags, HTML tags, user names, file paths, and the names of system objects, are interpreted as if they were culture-sensitive, application code can be subject to subtle bugs, poor performance, and, in some cases, security issues.</span></span>

<span data-ttu-id="a1639-109">本文介绍 .NET 中的字符串排序、比较和大小写方法，针对如何选择适当的字符串处理方法提出建议，并提供有关字符串处理方法的其他信息。</span><span class="sxs-lookup"><span data-stu-id="a1639-109">This article examines the string sorting, comparison, and casing methods in .NET, presents recommendations for selecting an appropriate string-handling method, and provides additional information about string-handling methods.</span></span> <span data-ttu-id="a1639-110">它还讨论如何处理数据格式（如数字数据以及日期和时间数据）以用于显示和存储。</span><span class="sxs-lookup"><span data-stu-id="a1639-110">It also examines how formatted data, such as numeric data and date and time data, is handled for display and for storage.</span></span> 

<span data-ttu-id="a1639-111">本文包含以下各节：</span><span class="sxs-lookup"><span data-stu-id="a1639-111">This article contains the following sections:</span></span>

* [<span data-ttu-id="a1639-112">对字符串用法的建议</span><span class="sxs-lookup"><span data-stu-id="a1639-112">Recommendations for string usage</span></span>](#recommendations-for-string-usage)

* [<span data-ttu-id="a1639-113">显式指定字符串比较</span><span class="sxs-lookup"><span data-stu-id="a1639-113">Specifying string comparisons explicitly</span></span>](#specifying-string-comparisons-explicitly)

* [<span data-ttu-id="a1639-114">字符串比较的详细信息</span><span class="sxs-lookup"><span data-stu-id="a1639-114">The details of string comparison</span></span>](#the-details-of-string-comparison)

* [<span data-ttu-id="a1639-115">为方法调用选择 StringComparison 成员</span><span class="sxs-lookup"><span data-stu-id="a1639-115">Choosing a StringComparison member for your method call</span></span>](#choosing-a-stringcomparison-member-for-your-method-call)

* [<span data-ttu-id="a1639-116">常见的字符串比较方法</span><span class="sxs-lookup"><span data-stu-id="a1639-116">Common string comparison methods</span></span>](#common-string-comparison-methods)

* [<span data-ttu-id="a1639-117">间接执行字符串比较的方法</span><span class="sxs-lookup"><span data-stu-id="a1639-117">Methods that perform string comparison indirectly</span></span>](#methods-that-perform-string-comparison-indirectly)

* [<span data-ttu-id="a1639-118">显示和保存有格式的数据</span><span class="sxs-lookup"><span data-stu-id="a1639-118">Displaying and persisting formatted data</span></span>](#displaying-and-persisting-formatted-data)

## <a name="recommendations-for-string-usage"></a><span data-ttu-id="a1639-119">对字符串用法的建议</span><span class="sxs-lookup"><span data-stu-id="a1639-119">Recommendations for string usage</span></span>

<span data-ttu-id="a1639-120">使用 .NET 进行开发时，请遵循以下简要建议使用字符串：</span><span class="sxs-lookup"><span data-stu-id="a1639-120">When you develop with .NET, follow these simple recommendations when you use strings:</span></span> 

* <span data-ttu-id="a1639-121">使用为字符串操作显式指定字符串比较规则的重载。</span><span class="sxs-lookup"><span data-stu-id="a1639-121">Use overloads that explicitly specify the string comparison rules for string operations.</span></span> <span data-ttu-id="a1639-122">通常情况下，这涉及调用具有 [StringComparison](xref:System.StringComparison) 类型的参数的方法重载。</span><span class="sxs-lookup"><span data-stu-id="a1639-122">Typically, this involves calling a method overload that has a parameter of type [StringComparison](xref:System.StringComparison).</span></span>

* <span data-ttu-id="a1639-123">使用 [StringComparison.Ordinal](xref:System.StringComparison.Ordinal) 或 [StringComparison.OrdinalIgnoreCase](xref:System.StringComparison.OrdinalIgnoreCase) 进行比较，并以此作为匹配区域性不明确的字符串的安全默认设置。</span><span class="sxs-lookup"><span data-stu-id="a1639-123">Use [StringComparison.Ordinal](xref:System.StringComparison.Ordinal) or [StringComparison.OrdinalIgnoreCase](xref:System.StringComparison.OrdinalIgnoreCase) for comparisons as your safe default for culture-agnostic string matching.</span></span>

* <span data-ttu-id="a1639-124">将比较与 [StringComparison.Ordinal](xref:System.StringComparison.Ordinal) 或 [StringComparison.OrdinalIgnoreCase](xref:System.StringComparison.OrdinalIgnoreCase) 配合使用，获取更好的性能。</span><span class="sxs-lookup"><span data-stu-id="a1639-124">Use comparisons with [StringComparison.Ordinal](xref:System.StringComparison.Ordinal) or [StringComparison.OrdinalIgnoreCase](xref:System.StringComparison.OrdinalIgnoreCase) for better performance.</span></span>

* <span data-ttu-id="a1639-125">向用户显示输出时，使用基于 [StringComparison.CurrentCulture](xref:System.StringComparison.CurrentCulture) 的字符串操作。</span><span class="sxs-lookup"><span data-stu-id="a1639-125">Use string operations that are based on [StringComparison.CurrentCulture](xref:System.StringComparison.CurrentCulture) when you display output to the user.</span></span>

* <span data-ttu-id="a1639-126">当进行与语言（例如，符号）无关的比较时，使用非语言的 [StringComparison.Ordinal](xref:System.StringComparison.Ordinal) 或 [StringComparison.OrdinalIgnoreCase](xref:System.StringComparison.OrdinalIgnoreCase) 值，而不使用基于 [CultureInfo.InvariantCulture](xref:System.Globalization.CultureInfo.InvariantCulture) 的字符串操作。</span><span class="sxs-lookup"><span data-stu-id="a1639-126">Use the non-linguistic [StringComparison.Ordinal](xref:System.StringComparison.Ordinal) or [StringComparison.OrdinalIgnoreCase](xref:System.StringComparison.OrdinalIgnoreCase) values instead of string operations based on [CultureInfo.InvariantCulture](xref:System.Globalization.CultureInfo.InvariantCulture) when the comparison is linguistically irrelevant (symbolic, for example).</span></span>

* <span data-ttu-id="a1639-127">在规范化要比较的字符串时，使用 [String.ToUpperInvariant](xref:System.String.ToUpperInvariant) 方法而不是 [String.ToLowerInvariant](xref:System.String.ToLowerInvariant) 方法。</span><span class="sxs-lookup"><span data-stu-id="a1639-127">Use the [String.ToUpperInvariant](xref:System.String.ToUpperInvariant) method instead of the [String.ToLowerInvariant](xref:System.String.ToLowerInvariant) method when you normalize strings for comparison.</span></span>

* <span data-ttu-id="a1639-128">使用 [String](xref:System.String) `Equals` 方法的重载来测试两个字符串是否相等。</span><span class="sxs-lookup"><span data-stu-id="a1639-128">Use an overload of the [String](xref:System.String) `Equals` method to test whether two strings are equal.</span></span>

* <span data-ttu-id="a1639-129">使用 [String](xref:System.String) `Compare` 和 [String.CompareTo](xref:System.String.CompareTo(System.String)) 方法可对字符串进行排序，而不是检查字符串是否相等。</span><span class="sxs-lookup"><span data-stu-id="a1639-129">Use an overload of the [String](xref:System.String) `Compare` and [String.CompareTo](xref:System.String.CompareTo(System.String)) methods to sort strings, not to check for equality.</span></span>

* <span data-ttu-id="a1639-130">在用户界面，使用区分区域性的格式显示非字符串数据，如数字和日期。</span><span class="sxs-lookup"><span data-stu-id="a1639-130">Use culture-sensitive formatting to display non-string data, such as numbers and dates, in a user interface.</span></span> <span data-ttu-id="a1639-131">使用格式以固定区域性使非字符串数据显示为字符串形式。</span><span class="sxs-lookup"><span data-stu-id="a1639-131">Use formatting with the invariant culture to persist non-string data in string form.</span></span>

<span data-ttu-id="a1639-132">使用字符串时，请避免采用以下做法：</span><span class="sxs-lookup"><span data-stu-id="a1639-132">Avoid the following practices when you use strings:</span></span>

* <span data-ttu-id="a1639-133">不要使用未显式或隐式为字符串操作指定字符串比较规则的重载。</span><span class="sxs-lookup"><span data-stu-id="a1639-133">Do not use overloads that do not explicitly or implicitly specify the string comparison rules for string operations.</span></span> 

* <span data-ttu-id="a1639-134">不要使用 [String](xref:System.String) `Compare` 或 [String.CompareTo](xref:System.String.CompareTo(System.String)) 方法的重载和用于确定两个字符串是否相等的返回值为 0 的测试。</span><span class="sxs-lookup"><span data-stu-id="a1639-134">Do not use an overload of the [String](xref:System.String) `Compare` or [String.CompareTo](xref:System.String.CompareTo(System.String)) methods and test for a return value of zero to determine whether two strings are equal.</span></span>

* <span data-ttu-id="a1639-135">不要使用区分区域性格式以字符串形式来保存数值数据或日期和时间数据。</span><span class="sxs-lookup"><span data-stu-id="a1639-135">Do not use culture-sensitive formatting to persist numeric data or date and time data in string form.</span></span>

## <a name="specifying-string-comparisons-explicitly"></a><span data-ttu-id="a1639-136">显式指定字符串比较</span><span class="sxs-lookup"><span data-stu-id="a1639-136">Specifying string comparisons explicitly</span></span>

<span data-ttu-id="a1639-137">重载 .NET 中大部分字符串操作方法。</span><span class="sxs-lookup"><span data-stu-id="a1639-137">Most of the string manipulation methods in .NET are overloaded.</span></span> <span data-ttu-id="a1639-138">通常，一个或多个重载会接受默认设置，然而其他重载则不接受默认设置，而是定义比较或操作字符串的精确方式。</span><span class="sxs-lookup"><span data-stu-id="a1639-138">Typically, one or more overloads accept default settings, whereas others accept no defaults and instead define the precise way in which strings are to be compared or manipulated.</span></span> <span data-ttu-id="a1639-139">大多数不依赖于默认设置的方法都包含 [StringComparison](xref:System.StringComparison) 类型的参数，该参数是按区域性和大小写为字符串比较显式指定规则的枚举。</span><span class="sxs-lookup"><span data-stu-id="a1639-139">Most of the methods that do not rely on defaults include a parameter of type [StringComparison](xref:System.StringComparison), which is an enumeration that explicitly specifies rules for string comparison by culture and case.</span></span> <span data-ttu-id="a1639-140">下表描述 [StringComparison](xref:System.StringComparison) 枚举成员。</span><span class="sxs-lookup"><span data-stu-id="a1639-140">The following table describes the [StringComparison](xref:System.StringComparison) enumeration members.</span></span> 

<span data-ttu-id="a1639-141">StringComparison 成员</span><span class="sxs-lookup"><span data-stu-id="a1639-141">StringComparison member</span></span> | <span data-ttu-id="a1639-142">描述</span><span class="sxs-lookup"><span data-stu-id="a1639-142">Description</span></span>
----------------------- | -----------
[<span data-ttu-id="a1639-143">StringComparison.CurrentCulture</span><span class="sxs-lookup"><span data-stu-id="a1639-143">StringComparison.CurrentCulture</span></span>](xref:System.StringComparison.CurrentCulture) | <span data-ttu-id="a1639-144">使用当前区域性执行区分大小写的比较。</span><span class="sxs-lookup"><span data-stu-id="a1639-144">Performs a case-sensitive comparison using the current culture.</span></span>
[<span data-ttu-id="a1639-145">CurrentCultureIgnoreCase</span><span class="sxs-lookup"><span data-stu-id="a1639-145">CurrentCultureIgnoreCase</span></span>](xref:System.StringComparison.CurrentCultureIgnoreCase) | <span data-ttu-id="a1639-146">使用当前区域性执行不区分大小写的比较。</span><span class="sxs-lookup"><span data-stu-id="a1639-146">Performs a case-insensitive comparison using the current culture.</span></span>
[<span data-ttu-id="a1639-147">StringComparison.Ordinal</span><span class="sxs-lookup"><span data-stu-id="a1639-147">StringComparison.Ordinal</span></span>](xref:System.StringComparison.Ordinal) | <span data-ttu-id="a1639-148">执行序号比较。</span><span class="sxs-lookup"><span data-stu-id="a1639-148">Performs an ordinal comparison.</span></span>
[<span data-ttu-id="a1639-149">StringComparison.OrdinalIgnoreCase</span><span class="sxs-lookup"><span data-stu-id="a1639-149">StringComparison.OrdinalIgnoreCase</span></span>](xref:System.StringComparison.OrdinalIgnoreCase) | <span data-ttu-id="a1639-150">执行不区分大小写的序号比较。</span><span class="sxs-lookup"><span data-stu-id="a1639-150">Performs a case-insensitive ordinal comparison.</span></span>

<span data-ttu-id="a1639-151">例如，[String](xref:System.String) `IndexOf` 方法（它返回 [String](xref:System.String) 对象中与某字符或字符串匹配的子字符串的索引）具有九种重载：</span><span class="sxs-lookup"><span data-stu-id="a1639-151">For example, the [String](xref:System.String) `IndexOf` method, which returns the index of a substring in a [String](xref:System.String) object that matches either a character or a string, has nine overloads:</span></span>

* <span data-ttu-id="a1639-152">默认情况下，[IndexOf(Char)](xref:System.String.IndexOf(System.Char))、[IndexOf(Char, Int32)](xref:System.String.IndexOf(System.Char,System.Int32)) 和 [IndexOf(Char, Int32, Int32)](xref:System.String.IndexOf(System.Char,System.Int32,System.Int32)) 对字符串中的字符执行序号（区分大小写但不区分区域性的）搜索。</span><span class="sxs-lookup"><span data-stu-id="a1639-152">[IndexOf(Char)](xref:System.String.IndexOf(System.Char)), [IndexOf(Char, Int32)](xref:System.String.IndexOf(System.Char,System.Int32)), and [IndexOf(Char, Int32, Int32)](xref:System.String.IndexOf(System.Char,System.Int32,System.Int32)), which by default perform an ordinal (case-sensitive and culture-insensitive) search for a character in the string.</span></span>

* <span data-ttu-id="a1639-153">默认情况下，[IndexOf(String)](xref:System.String.IndexOf(System.String))、[IndexOf(String, Int32)](xref:System.String.IndexOf(System.String,System.Int32)) 和 [IndexOf(String, Int32, Int32)](xref:System.String.IndexOf(System.String,System.Int32,System.Int32)) 对字符串中的子字符串执行区分大小写且区分区域性的搜索。</span><span class="sxs-lookup"><span data-stu-id="a1639-153">[IndexOf(String)](xref:System.String.IndexOf(System.String)), [IndexOf(String, Int32)](xref:System.String.IndexOf(System.String,System.Int32)), and [IndexOf(String, Int32, Int32)](xref:System.String.IndexOf(System.String,System.Int32,System.Int32)), which by default perform a case-sensitive and culture-sensitive search for a substring in the string.</span></span>

* <span data-ttu-id="a1639-154">[IndexOf(String, StringComparison)](xref:System.String.IndexOf(System.String,System.StringComparison))、[IndexOf(String, Int32, StringComparison)](xref:System.String.IndexOf(System.String,System.Int32,System.StringComparison)) 和 [IndexOf(String, Int32, Int32, StringComparison)](xref:System.String.IndexOf(System.String,System.Int32,System.Int32,System.StringComparison))，其中包含 StringComparison 类型的参数，该类型允许指定比较形式。</span><span class="sxs-lookup"><span data-stu-id="a1639-154">[IndexOf(String, StringComparison)](xref:System.String.IndexOf(System.String,System.StringComparison)), [IndexOf(String, Int32, StringComparison)](xref:System.String.IndexOf(System.String,System.Int32,System.StringComparison)), and [IndexOf(String, Int32, Int32, StringComparison)](xref:System.String.IndexOf(System.String,System.Int32,System.Int32,System.StringComparison)), which include a parameter of type StringComparison that allows the form of the comparison to be specified.</span></span>

<span data-ttu-id="a1639-155">我们建议选择不使用默认值的重载，原因如下：</span><span class="sxs-lookup"><span data-stu-id="a1639-155">We recommend that you select an overload that does not use default values, for the following reasons:</span></span>

* <span data-ttu-id="a1639-156">具有默认参数的一些重载（在字符串实例中搜索 [Char](xref:System.Char) 的重载）执行序号比较，而其他重载（在字符串实例中搜索字符串的重载）执行的是区分区域性的比较。</span><span class="sxs-lookup"><span data-stu-id="a1639-156">Some overloads with default parameters (those that search for a [Char](xref:System.Char) in the string instance) perform an ordinal comparison, whereas others (those that search for a string in the string instance) are culture-sensitive.</span></span> <span data-ttu-id="a1639-157">要记住哪种方法使用哪个默认值并非易事，并很容易混淆重载。</span><span class="sxs-lookup"><span data-stu-id="a1639-157">It is difficult to remember which method uses which default value, and easy to confuse the overloads.</span></span>

* <span data-ttu-id="a1639-158">依赖于方法调用默认值的代码的意图并不清楚。</span><span class="sxs-lookup"><span data-stu-id="a1639-158">The intent of the code that relies on default values for method calls is not clear.</span></span> <span data-ttu-id="a1639-159">在下面依赖于默认值的示例中，很难了解开发人员对两个字符串的实际意图是执行序号比较还是语言比较，或 `protocol` 和“http”之间存在的大小写差异是否会导致相等性测试返回 `false`。</span><span class="sxs-lookup"><span data-stu-id="a1639-159">In the following example, which relies on defaults, it is difficult to know whether the developer actually intended an ordinal or a linguistic comparison of two strings, or whether a case difference between `protocol` and "http" might cause the test for equality to return `false`.</span></span>

  ```csharp
  string protocol = GetProtocol(url);       
  if (String.Equals(protocol, "http", StringComparison.OrdinalIgnoreCase)) {
     // ...Code to handle HTTP protocol.
  }
  else {
     throw new InvalidOperationException();
  }
  ```

  ```vb
  Dim protocol As String = GetProtocol(url)       
  If String.Equals(protocol, "http") Then
    ' ...Code to handle HTTP protocol.
  Else
     Throw New InvalidOperationException()
  End If
  ```

<span data-ttu-id="a1639-160">一般情况下，我们建议调用不依赖于默认设置的方法，因为这会明确代码的意图。</span><span class="sxs-lookup"><span data-stu-id="a1639-160">In general, we recommend that you call a method that does not rely on defaults, because it makes the intent of the code unambiguous.</span></span> <span data-ttu-id="a1639-161">这进而使代码更具可读性且更易于调试和维护。</span><span class="sxs-lookup"><span data-stu-id="a1639-161">This, in turn, makes the code more readable and easier to debug and maintain.</span></span> <span data-ttu-id="a1639-162">下面的示例解决了前面示例中提出的问题。</span><span class="sxs-lookup"><span data-stu-id="a1639-162">The following example addresses the questions raised about the previous example.</span></span> <span data-ttu-id="a1639-163">使用序号比较并且忽略大小写差异。</span><span class="sxs-lookup"><span data-stu-id="a1639-163">It makes it clear that ordinal comparison is used and that differences in case are ignored.</span></span> 

```csharp
string protocol = GetProtocol(url);       
if (String.Equals(protocol, "http", StringComparison.OrdinalIgnoreCase)) {
   // ...Code to handle HTTP protocol.
}
else {
   throw new InvalidOperationException();
}
```

```vb
Dim protocol As String = GetProtocol(url)       
If String.Equals(protocol, "http", StringComparison.OrdinalIgnoreCase) Then
   ' ...Code to handle HTTP protocol.
Else
   Throw New InvalidOperationException()
End If
```

## <a name="the-details-of-string-comparison"></a><span data-ttu-id="a1639-164">字符串比较的详细信息</span><span class="sxs-lookup"><span data-stu-id="a1639-164">The details of string comparison</span></span>

<span data-ttu-id="a1639-165">字符串比较是许多字符串相关操作的核心，特别是排序和相等性测试操作。</span><span class="sxs-lookup"><span data-stu-id="a1639-165">String comparison is the heart of many string-related operations, particularly sorting and testing for equality.</span></span> <span data-ttu-id="a1639-166">字符串以确定的顺序进行排序：如果在排序的字符串列表中，“my”出现在“string”之前，则“my”必定小于或等于“string”。</span><span class="sxs-lookup"><span data-stu-id="a1639-166">Strings sort in a determined order: If "my" appears before "string" in a sorted list of strings, "my" must compare less than or equal to "string".</span></span> <span data-ttu-id="a1639-167">此外，比较可隐式确定相等性。</span><span class="sxs-lookup"><span data-stu-id="a1639-167">Additionally, comparison implicitly defines equality.</span></span> <span data-ttu-id="a1639-168">对于认为是相等的字符串，比较操作将返回零。</span><span class="sxs-lookup"><span data-stu-id="a1639-168">The comparison operation returns zero for strings it deems equal.</span></span> <span data-ttu-id="a1639-169">对此很好的解释是两个字符串都不小于对方。</span><span class="sxs-lookup"><span data-stu-id="a1639-169">A good interpretation is that neither string is less than the other.</span></span> <span data-ttu-id="a1639-170">涉及到字符串的最有意义的操作包括这些步骤中的一个或两个步骤：与另一个字符串进行比较和执行明确的排序操作。</span><span class="sxs-lookup"><span data-stu-id="a1639-170">Most meaningful operations involving strings include one or both of these procedures: comparing with another string, and executing a well-defined sort operation.</span></span>

<span data-ttu-id="a1639-171">但是，评估两个字符串的相等性或排序顺序不会生成一个正确的结果；其结果取决于用于比较这两个字符串的条件。</span><span class="sxs-lookup"><span data-stu-id="a1639-171">However, evaluating two strings for equality or sort order does not yield a single, correct result; the outcome depends on the criteria used to compare the strings.</span></span> <span data-ttu-id="a1639-172">特别是，序号或基于当前区域性或固定区域性（基于英语语言的区域设置不明确的区域性）的大小写和排序约定的字符串比较可能会产生不同的结果。</span><span class="sxs-lookup"><span data-stu-id="a1639-172">In particular, string comparisons that are ordinal or that are based on the casing and sorting conventions of the current culture or the invariant culture (a locale-agnostic culture based on the English language) may produce different results.</span></span>

### <a name="string-comparisons-that-use-the-current-culture"></a><span data-ttu-id="a1639-173">使用当前区域性的字符串比较</span><span class="sxs-lookup"><span data-stu-id="a1639-173">String comparisons that use the current culture</span></span>

<span data-ttu-id="a1639-174">一个条件涉及在比较字符串时使用当前区域性的约定。</span><span class="sxs-lookup"><span data-stu-id="a1639-174">One criterion involves using the conventions of the current culture when comparing strings.</span></span> <span data-ttu-id="a1639-175">基于当前区域性的比较使用线程的当前区域性或区域设置。</span><span class="sxs-lookup"><span data-stu-id="a1639-175">Comparisons that are based on the current culture use the thread's current culture or locale.</span></span> <span data-ttu-id="a1639-176">当数据与语言相关并反映区分区域性的用户交互时，应始终使用基于当前区域性的比较。</span><span class="sxs-lookup"><span data-stu-id="a1639-176">You should always use comparisons that are based on the current culture when data is linguistically relevant, and when it reflects culture-sensitive user interaction.</span></span> 

<span data-ttu-id="a1639-177">但是，当区域性发生更改时，.NET 中的比较和大小写行为也发生更改。</span><span class="sxs-lookup"><span data-stu-id="a1639-177">However, comparison and casing behavior in .NET changes when the culture changes.</span></span> <span data-ttu-id="a1639-178">如果执行应用程序的计算机与用于开发该应用程序的计算机具有不同的区域性，或者执行线程改变它的区域性，则会发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="a1639-178">This happens when an application executes on a computer that has a different culture than the computer on which the application was developed, or when the executing thread changes its culture.</span></span> <span data-ttu-id="a1639-179">此行为是有意而为之的，但许多开发人员不易察觉此行为。</span><span class="sxs-lookup"><span data-stu-id="a1639-179">This behavior is intentional, but it remains non-obvious to many developers.</span></span> <span data-ttu-id="a1639-180">下面的示例说明了美国英语（“en-US”）与瑞典语（“sv-SE”）区域性在排序顺序中的差异。</span><span class="sxs-lookup"><span data-stu-id="a1639-180">The following example illustrates differences in sort order between the U.S. English ("en-US") and Swedish ("sv-SE") cultures.</span></span> <span data-ttu-id="a1639-181">请注意，单词“ångström”、“Windows”和“Visual Studio”将出现在已排序的字符串数组的不同位置。</span><span class="sxs-lookup"><span data-stu-id="a1639-181">Note that the words "ångström", "Windows", and "Visual Studio" appear in different positions in the sorted string arrays.</span></span>

```csharp
using System;
using System.Globalization;
using System.Threading;

public class Example
{
   public static void Main()
   {
      string[] values= { "able", "ångström", "apple", "Æble", 
                         "Windows", "Visual Studio" };
      Array.Sort(values);
      DisplayArray(values);

      // Change culture to Swedish (Sweden).
      string originalCulture = CultureInfo.CurrentCulture.Name;
      Thread.CurrentThread.CurrentCulture = new CultureInfo("sv-SE");
      Array.Sort(values);
      DisplayArray(values);

      // Restore the original culture.
      Thread.CurrentThread.CurrentCulture = new CultureInfo(originalCulture);
    }

    private static void DisplayArray(string[] values)
    {
      Console.WriteLine("Sorting using the {0} culture:",  
                        CultureInfo.CurrentCulture.Name);
      foreach (string value in values)
         Console.WriteLine("   {0}", value);

      Console.WriteLine();
    }
}
// The example displays the following output:
//       Sorting using the en-US culture:
//          able
//          Æble
//          ångström
//          apple
//          Visual Studio
//          Windows
//       
//       Sorting using the sv-SE culture:
//          able
//          Æble
//          apple
//          Windows
//          Visual Studio
//          ångström
```

```vb
Imports System.Globalization
Imports System.Threading

Module Example
   Public Sub Main()
      Dim values() As String = { "able", "ångström", "apple", _
                                 "Æble", "Windows", "Visual Studio" }
      Array.Sort(values)
      DisplayArray(values)

      ' Change culture to Swedish (Sweden).
      Dim originalCulture As String = CultureInfo.CurrentCulture.Name
      Thread.CurrentThread.CurrentCulture = New CultureInfo("sv-SE")
      Array.Sort(values)
      DisplayArray(values)

      ' Restore the original culture.
      Thread.CurrentThread.CurrentCulture = New CultureInfo(originalCulture)
    End Sub

    Private Sub DisplayArray(values() As String)
      Console.WRiteLine("Sorting using the {0} culture:", _ 
                        CultureInfo.CurrentCulture.Name)
      For Each value As String In values
         Console.WriteLine("   {0}", value)
      Next
      Console.WriteLine()   
    End Sub
End Module
' The example displays the following output:
'       Sorting using the en-US culture:
'          able
'          Æble
'          ångström
'          apple
'          Visual Studio
'          Windows
'       
'       Sorting using the sv-SE culture:
'          able
'          Æble
'          apple
'          Windows
'          Visual Studio
'          ångström
```

<span data-ttu-id="a1639-182">使用当前区域性的不区分大小写比较和区分区域性的比较是相同的，只不过前者忽略由线程的当前区域性指示的大小写。</span><span class="sxs-lookup"><span data-stu-id="a1639-182">Case-insensitive comparisons that use the current culture are the same as culture-sensitive comparisons, except that they ignore case as dictated by the thread's current culture.</span></span> <span data-ttu-id="a1639-183">这种情况也可表明它的排序顺序。</span><span class="sxs-lookup"><span data-stu-id="a1639-183">This behavior may manifest itself in sort orders as well.</span></span> 

<span data-ttu-id="a1639-184">以下方法默认利用使用当前区域性语义的比较：</span><span class="sxs-lookup"><span data-stu-id="a1639-184">Comparisons that use current culture semantics are the default for the following methods:</span></span>

* <span data-ttu-id="a1639-185">不包含 [StringComparison](xref:System.StringComparison) 参数的 [String](xref:System.String) `Compare` 重载。</span><span class="sxs-lookup"><span data-stu-id="a1639-185">[String](xref:System.String) `Compare` overloads that do not include a [StringComparison](xref:System.StringComparison) parameter.</span></span>

* <span data-ttu-id="a1639-186">[String.CompareTo](xref:System.String.CompareTo(System.String)) 重载。</span><span class="sxs-lookup"><span data-stu-id="a1639-186">[String.CompareTo](xref:System.String.CompareTo(System.String)) overloads.</span></span>

* <span data-ttu-id="a1639-187">默认的 [String.StartsWith(String)](xref:System.String.StartsWith(System.String)) 方法。</span><span class="sxs-lookup"><span data-stu-id="a1639-187">The default [String.StartsWith(String)](xref:System.String.StartsWith(System.String)) method.</span></span> 

* <span data-ttu-id="a1639-188">默认的 [String.EndsWith(String)](xref:System.String.EndsWith(System.String)) 方法。</span><span class="sxs-lookup"><span data-stu-id="a1639-188">The default [String.EndsWith(String)](xref:System.String.EndsWith(System.String)) method.</span></span>

* <span data-ttu-id="a1639-189">接受 [String](xref:System.String) 作为搜索参数且不包含 [StringComparison](xref:System.StringComparison) 参数的 [String](xref:System.String) `IndexOf` 重载。</span><span class="sxs-lookup"><span data-stu-id="a1639-189">[String](xref:System.String) `IndexOf` overloads that accept a [String](xref:System.String) as a search parameter and that do not have a [StringComparison](xref:System.StringComparison) parameter.</span></span>

* <span data-ttu-id="a1639-190">接受 [String](xref:System.String) 作为搜索参数且不包含 [StringComparison](xref:System.StringComparison) 参数的 [String](xref:System.String) `LastIndexOf` 重载。</span><span class="sxs-lookup"><span data-stu-id="a1639-190">[String](xref:System.String) `LastIndexOf` overloads that accept a [String](xref:System.String) as a search parameter and that do not have a [StringComparison](xref:System.StringComparison) parameter.</span></span>

<span data-ttu-id="a1639-191">总之，我们建议调用包含 [StringComparison](xref:System.StringComparison) 参数的重载，明确方法调用的意图。</span><span class="sxs-lookup"><span data-stu-id="a1639-191">In any case, we recommend that you call an overload that has a [StringComparison](xref:System.StringComparison) parameter to make the intent of the method call clear.</span></span> 

<span data-ttu-id="a1639-192">当从语言角度解释非语言的字符串数据，或利用其他区域性的约定解释某个特定区域性中的字符串时，则会发生或大或小的错误。</span><span class="sxs-lookup"><span data-stu-id="a1639-192">Subtle and not so subtle bugs can emerge when non-linguistic string data is interpreted linguistically, or when string data from a particular culture is interpreted using the conventions of another culture.</span></span> <span data-ttu-id="a1639-193">土耳其语 I 问题便是一个规范示例。</span><span class="sxs-lookup"><span data-stu-id="a1639-193">The canonical example is the Turkish-I problem.</span></span>

<span data-ttu-id="a1639-194">对于几乎所有拉丁字母来讲（包括美国英语），字符“i”(\u0069) 是字符“I”(\u0049) 的小写形式。</span><span class="sxs-lookup"><span data-stu-id="a1639-194">For nearly all Latin alphabets, including U.S. English, the character "i" (\u0069) is the lowercase version of the character "I" (\u0049).</span></span> <span data-ttu-id="a1639-195">此大小写规则快速成为在此类区域性中编程的人员的默认设置。</span><span class="sxs-lookup"><span data-stu-id="a1639-195">This casing rule quickly becomes the default for someone programming in such a culture.</span></span> <span data-ttu-id="a1639-196">但是，土耳其语（“tr-TR”）字母表中包含一个“带有点的 I”的字符“İ”(\u0130)，该字符是“i”的大写形式。</span><span class="sxs-lookup"><span data-stu-id="a1639-196">However, the Turkish ("tr-TR") alphabet includes an "I with a dot" character "İ" (\u0130), which is the capital version of "i".</span></span> <span data-ttu-id="a1639-197">土耳其语还包括一个小写“不带点的 i”字符，即为“ı”(\u0131)，该字符的大写形式为“I”。</span><span class="sxs-lookup"><span data-stu-id="a1639-197">Turkish also includes a lowercase "i without a dot" character, "ı" (\u0131), which capitalizes to "I".</span></span> <span data-ttu-id="a1639-198">阿塞拜疆语（“az”）区域也会出现这种情况。</span><span class="sxs-lookup"><span data-stu-id="a1639-198">This behavior occurs in the Azerbaijani ("az") culture as well.</span></span>

<span data-ttu-id="a1639-199">因此，关于将“i”变为大写或将“I”变为小写的假设并非在所有区域性中都是有效的。</span><span class="sxs-lookup"><span data-stu-id="a1639-199">Therefore, assumptions made about capitalizing "i" or lowercasing "I" are not valid among all cultures.</span></span> <span data-ttu-id="a1639-200">如果为字符串比较例程使用默认重载，则它们可能会因区域性不同而异。</span><span class="sxs-lookup"><span data-stu-id="a1639-200">If you use the default overloads for string comparison routines, they will be subject to variance between cultures.</span></span> <span data-ttu-id="a1639-201">如果对非语言的数据进行比较，使用默认重载会产生不良后果，如以下对字符串“file”和“FILE”执行不区分大小写的比较尝试所示。</span><span class="sxs-lookup"><span data-stu-id="a1639-201">If the data to be compared is non-linguistic, using the default overloads can produce undesirable results, as the following attempt to perform a case-insensitive comparison of the strings "file" and "FILE" illustrates.</span></span>

```csharp
using System;
using System.Globalization;
using System.Threading;

public class Example
{
   public static void Main()
   {
      string fileUrl = "file";
      Thread.CurrentThread.CurrentCulture = new CultureInfo("en-US");
      Console.WriteLine("Culture = {0}",
                        Thread.CurrentThread.CurrentCulture.DisplayName);
      Console.WriteLine("(file == FILE) = {0}", 
                       fileUrl.StartsWith("FILE", true, null));
      Console.WriteLine();

      Thread.CurrentThread.CurrentCulture = new CultureInfo("tr-TR");
      Console.WriteLine("Culture = {0}",
                        Thread.CurrentThread.CurrentCulture.DisplayName);
      Console.WriteLine("(file == FILE) = {0}", 
                        fileUrl.StartsWith("FILE", true, null));
   }
}
// The example displays the following output:
//       Culture = English (United States)
//       (file == FILE) = True
//       
//       Culture = Turkish (Turkey)
//       (file == FILE) = False
```

```vb
Imports System.Globalization
Imports System.Threading

Module Example
   Public Sub Main()
      Dim fileUrl = "file"
      Thread.CurrentThread.CurrentCulture = New CultureInfo("en-US")
      Console.WriteLine("Culture = {0}", _
                        Thread.CurrentThread.CurrentCulture.DisplayName)
      Console.WriteLine("(file == FILE) = {0}", _ 
                       fileUrl.StartsWith("FILE", True, Nothing))
      Console.WriteLine()

      Thread.CurrentThread.CurrentCulture = New CultureInfo("tr-TR")
      Console.WriteLine("Culture = {0}", _
                        Thread.CurrentThread.CurrentCulture.DisplayName)
      Console.WriteLine("(file == FILE) = {0}", _ 
                        fileUrl.StartsWith("FILE", True, Nothing))
   End Sub
End Module
' The example displays the following output:
'       Culture = English (United States)
'       (file == FILE) = True
'       
'       Culture = Turkish (Turkey)
'       (file == FILE) = False
```

<span data-ttu-id="a1639-202">如果无意中在安全敏感设置中使用了区域性，则此比较会导致发生重大问题，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="a1639-202">This comparison could cause significant problems if the culture is inadvertently used in security-sensitive settings, as in the following example.</span></span> <span data-ttu-id="a1639-203">如果当前区域性为美国英语，则 `IsFileURI("file:")` 等方法调用将返回 `true`；但如果当前区域性为土耳其语，则将返回 `false`。</span><span class="sxs-lookup"><span data-stu-id="a1639-203">A method call such as `IsFileURI("file:")` returns `true` if the current culture is U.S. English, but `false` if the current culture is Turkish.</span></span> <span data-ttu-id="a1639-204">因此，在土耳其语系统中，有人可能会避开阻止访问以“FILE:”开头的不区分大小写的安全措施。</span><span class="sxs-lookup"><span data-stu-id="a1639-204">Thus, on Turkish systems, someone could circumvent security measures that block access to case-insensitive URIs that begin with "FILE:".</span></span>

```csharp
public static bool IsFileURI(String path) 
{
   return path.StartsWith("FILE:", true, null);
}
```

```vb
Public Shared Function IsFileURI(path As String) As Boolean 
   Return path.StartsWith("FILE:", True, Nothing)
End Function
```

<span data-ttu-id="a1639-205">在这种情况下，由于“file:”会被解释为非语言的、不区分区域性的标识符，因此应按照下面的示例所示编写代码。</span><span class="sxs-lookup"><span data-stu-id="a1639-205">In this case, because "file:" is meant to be interpreted as a non-linguistic, culture-insensitive identifier, the code should instead be written as shown in the following example.</span></span>

```csharp
public static bool IsFileURI(string path) 
{
   return path.StartsWith("FILE:", StringComparison.OrdinalIgnoreCase);
}
```

```vb
Public Shared Function IsFileURI(path As String) As Boolean 
    Return path.StartsWith("FILE:", StringComparison.OrdinalIgnoreCase)
End Function
```

## <a name="ordinal-string-operations"></a><span data-ttu-id="a1639-206">序号字符串操作</span><span class="sxs-lookup"><span data-stu-id="a1639-206">Ordinal String Operations</span></span>

<span data-ttu-id="a1639-207">在方法调用中指定 [StringComparison.Ordinal](xref:System.StringComparison.Ordinal) 或 [StringComparison.OrdinalIgnoreCase](xref:System.StringComparison.OrdinalIgnoreCase) 值表示非语言比较，这种比较忽略了自然语言的特性。</span><span class="sxs-lookup"><span data-stu-id="a1639-207">Specifying the [StringComparison.Ordinal](xref:System.StringComparison.Ordinal) or [StringComparison.OrdinalIgnoreCase](xref:System.StringComparison.OrdinalIgnoreCase) value in a method call signifies a non-linguistic comparison in which the features of natural languages are ignored.</span></span> <span data-ttu-id="a1639-208">利用 [StringComparison](xref:System.StringComparison) 值调用的方法将字符串操作决策建立在简单的字节比较的基础之上，而不是按区域性参数化的大小写或相等表。</span><span class="sxs-lookup"><span data-stu-id="a1639-208">Methods that are invoked with these [StringComparison](xref:System.StringComparison) values base string operation decisions on simple byte comparisons instead of casing or equivalence tables that are parameterized by culture.</span></span> <span data-ttu-id="a1639-209">在大多数情况下，这种方法最符合字符串的预期解释，并使代码更快更可靠。</span><span class="sxs-lookup"><span data-stu-id="a1639-209">In most cases, this approach best fits the intended interpretation of strings while making code faster and more reliable.</span></span> 

<span data-ttu-id="a1639-210">序号比较就是字符串比较，在这种比较中，将比较每个字符串中的每个字节且不进行语言解释；例如，“windows”不匹配“Windows”。</span><span class="sxs-lookup"><span data-stu-id="a1639-210">Ordinal comparisons are string comparisons in which each byte of each string is compared without linguistic interpretation; for example, "windows" does not match "Windows".</span></span> <span data-ttu-id="a1639-211">当上下文指示应完全匹配字符串或要求保守匹配策略时，请使用这种比较。</span><span class="sxs-lookup"><span data-stu-id="a1639-211">Use this comparison when the context dictates that strings should be matched exactly or demands conservative matching policy.</span></span> <span data-ttu-id="a1639-212">此外，序号比较是最快的比较操作，因为它在确定结果时不应用任何语言规则。</span><span class="sxs-lookup"><span data-stu-id="a1639-212">Additionally, ordinal comparison is the fastest comparison operation because it applies no linguistic rules when determining a result.</span></span>

<span data-ttu-id="a1639-213">.NET 中的字符串可以包括嵌入的空字符。</span><span class="sxs-lookup"><span data-stu-id="a1639-213">Strings in .NET can contain embedded null characters.</span></span> <span data-ttu-id="a1639-214">序号比较与区分区域性的比较（包括使用固定区域性的比较）之间最明显的区别之一是对字符串中嵌入的空字符的处理方式。</span><span class="sxs-lookup"><span data-stu-id="a1639-214">One of the clearest differences between ordinal and culture-sensitive comparison (including comparisons that use the invariant culture) concerns the handling of embedded null characters in a string.</span></span> <span data-ttu-id="a1639-215">当使用 [String](xref:System.String) `Compare` 和 [String](xref:System.String) `Equals` 方法执行区分区域性的比较（包括使用固定区域性的比较）时，将忽略这些字符。</span><span class="sxs-lookup"><span data-stu-id="a1639-215">These characters are ignored when you use the [String](xref:System.String) `Compare` and [String](xref:System.String) `Equals` methods to perform culture-sensitive comparisons (including comparisons that use the invariant culture).</span></span> <span data-ttu-id="a1639-216">因此，在区分区域性的比较中，包含嵌入的空字符的字符串可视为等于不包含空字符的字符串。</span><span class="sxs-lookup"><span data-stu-id="a1639-216">As a result, in culture-sensitive comparisons, strings that contain embedded null characters can be considered equal to strings that do not.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="a1639-217">尽管字符串比较方法忽略嵌入的空字符，但是 [String.Contains](xref:System.String.Contains(System.String))、[String.EndsWith](xref:System.String.EndsWith(System.String))、[String.IndexOf](xref:System.String.IndexOf(System.Char))、[String.LastIndexOf](xref:System.String.LastIndexOf(System.String)) 和 [String.StartsWith](xref:System.String.StartsWith(System.String)) 等字符串搜索方法并不会忽略这些字符。</span><span class="sxs-lookup"><span data-stu-id="a1639-217">Although string comparison methods disregard embedded null characters, string search methods such as [String.Contains](xref:System.String.Contains(System.String)), [String.EndsWith](xref:System.String.EndsWith(System.String)), [String.IndexOf](xref:System.String.IndexOf(System.Char)), [String.LastIndexOf](xref:System.String.LastIndexOf(System.String)), and [String.StartsWith](xref:System.String.StartsWith(System.String)) do not.</span></span> 

<span data-ttu-id="a1639-218">下面的示例对字符串“Aa”与在“A”和“a”之间嵌入了多个空字符的相似字符串进行区分区域性的比较，并显示如何将这两个字符串视为相等的字符串。</span><span class="sxs-lookup"><span data-stu-id="a1639-218">The following example performs a culture-sensitive comparison of the string "Aa" with a similar string that contains several embedded null characters between "A" and "a", and shows how the two strings are considered equal.</span></span> 

```csharp
using System;

public class Example
{
   public static void Main()
   {
      string str1 = "Aa";
      string str2 = "A" + new String('\u0000', 3) + "a";
      Console.WriteLine("Comparing '{0}' ({1}) and '{2}' ({3}):", 
                        str1, ShowBytes(str1), str2, ShowBytes(str2));
      Console.WriteLine("   With String.Compare:");
      Console.WriteLine("      Current Culture: {0}", 
                        String.Compare(str1, str2, StringComparison.CurrentCulture));
      Console.WriteLine("      Invariant Culture: {0}", 
                        String.Compare(str1, str2, StringComparison.InvariantCulture));

      Console.WriteLine("   With String.Equals:");
      Console.WriteLine("      Current Culture: {0}", 
                        String.Equals(str1, str2, StringComparison.CurrentCulture));
      Console.WriteLine("      Invariant Culture: {0}", 
                        String.Equals(str1, str2, StringComparison.InvariantCulture));
   }

   private static string ShowBytes(string str)
   {
      string hexString = String.Empty;
      for (int ctr = 0; ctr < str.Length; ctr++)
      {
         string result = String.Empty;
         result = Convert.ToInt32(str[ctr]).ToString("X4");
         result = " " + result.Substring(0,2) + " " + result.Substring(2, 2);
         hexString += result;
      }
      return hexString.Trim();
   }
}
// The example displays the following output:
//    Comparing 'Aa' (00 41 00 61) and 'A   a' (00 41 00 00 00 00 00 00 00 61):
//       With String.Compare:
//          Current Culture: 0
//          Invariant Culture: 0
//       With String.Equals:
//          Current Culture: True
//          Invariant Culture: True
```

```vb
Module Example
   Public Sub Main()
      Dim str1 As String = "Aa"
      Dim str2 As String = "A" + New String(Convert.ToChar(0), 3) + "a"
      Console.WriteLine("Comparing '{0}' ({1}) and '{2}' ({3}):", _
                        str1, ShowBytes(str1), str2, ShowBytes(str2))
      Console.WriteLine("   With String.Compare:")
      Console.WriteLine("      Current Culture: {0}", _
                        String.Compare(str1, str2, StringComparison.CurrentCulture))
      Console.WriteLine("      Invariant Culture: {0}", _
                        String.Compare(str1, str2, StringComparison.InvariantCulture))

      Console.WriteLine("   With String.Equals:")
      Console.WriteLine("      Current Culture: {0}", _
                        String.Equals(str1, str2, StringComparison.CurrentCulture))
      Console.WriteLine("      Invariant Culture: {0}", _
                        String.Equals(str1, str2, StringComparison.InvariantCulture))
   End Sub

   Private Function ShowBytes(str As String) As String
      Dim hexString As String = String.Empty
      For ctr As Integer = 0 To str.Length - 1
         Dim result As String = String.Empty
         result = Convert.ToInt32(str.Chars(ctr)).ToString("X4")
         result = " " + result.Substring(0,2) + " " + result.Substring(2, 2)
         hexString += result
      Next
      Return hexString.Trim()
   End Function
End Module
```

<span data-ttu-id="a1639-219">但是，当使用序号比较时，这两个字符串不会视为相等，如下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="a1639-219">However, the strings are not considered equal when you use ordinal comparison, as the following example shows.</span></span>

```csharp
Console.WriteLine("Comparing '{0}' ({1}) and '{2}' ({3}):", 
                  str1, ShowBytes(str1), str2, ShowBytes(str2));
Console.WriteLine("   With String.Compare:");
Console.WriteLine("      Ordinal: {0}", 
                  String.Compare(str1, str2, StringComparison.Ordinal));

Console.WriteLine("   With String.Equals:");
Console.WriteLine("      Ordinal: {0}", 
                  String.Equals(str1, str2, StringComparison.Ordinal));
// The example displays the following output:
//    Comparing 'Aa' (00 41 00 61) and 'A   a' (00 41 00 00 00 00 00 00 00 61):
//       With String.Compare:
//          Ordinal: 97
//       With String.Equals:
//          Ordinal: False
```

```vb
Console.WriteLine("Comparing '{0}' ({1}) and '{2}' ({3}):", _
                  str1, ShowBytes(str1), str2, ShowBytes(str2))
Console.WriteLine("   With String.Compare:")
Console.WriteLine("      Ordinal: {0}", _
                  String.Compare(str1, str2, StringComparison.Ordinal))

Console.WriteLine("   With String.Equals:")
Console.WriteLine("      Ordinal: {0}", _
                  String.Equals(str1, str2, StringComparison.Ordinal))
' The example displays the following output:
'    Comparing 'Aa' (00 41 00 61) and 'A   a' (00 41 00 00 00 00 00 00 00 61):
'       With String.Compare:
'          Ordinal: 97
'       With String.Equals:
'          Ordinal: False
```

<span data-ttu-id="a1639-220">不区分大小写的序号比较是第二种最保守的方法。</span><span class="sxs-lookup"><span data-stu-id="a1639-220">Case-insensitive ordinal comparisons are the next most conservative approach.</span></span> <span data-ttu-id="a1639-221">这些比较会忽略大多数的大小写；例如，“windows”会匹配“Windows”。</span><span class="sxs-lookup"><span data-stu-id="a1639-221">These comparisons ignore most casing; for example, "windows" matches "Windows".</span></span> <span data-ttu-id="a1639-222">在处理 ASCII 字符时，此策略等同于 [StringComparison.Ordinal](xref:System.StringComparison.Ordinal)，只不过它会忽略常用的 ASCII 大小写。</span><span class="sxs-lookup"><span data-stu-id="a1639-222">When dealing with ASCII characters, this policy is equivalent to [StringComparison.Ordinal](xref:System.StringComparison.Ordinal), except that it ignores the usual ASCII casing.</span></span> <span data-ttu-id="a1639-223">因此，[A, Z] (\u0041-\u005A) 中的任何字符都会匹配 [a,z] (\u0061-\007A) 中的相应字符。</span><span class="sxs-lookup"><span data-stu-id="a1639-223">Therefore, any character in [A, Z] (\u0041-\u005A) matches the corresponding character in [a,z] (\u0061-\007A).</span></span> <span data-ttu-id="a1639-224">超出 ASCII 范围的大小写使用固定区域性的表。</span><span class="sxs-lookup"><span data-stu-id="a1639-224">Casing outside the ASCII range uses the invariant culture's tables.</span></span> <span data-ttu-id="a1639-225">因此，下面的比较：</span><span class="sxs-lookup"><span data-stu-id="a1639-225">Therefore, the following comparison:</span></span>

```csharp
String.Compare(strA, strB, StringComparison.OrdinalIgnoreCase);
```

```vb
String.Compare(strA, strB, StringComparison.OrdinalIgnoreCase)
```

<span data-ttu-id="a1639-226">等效于（但会更快）这种比较：</span><span class="sxs-lookup"><span data-stu-id="a1639-226">is equivalent to (but faster than) this comparison:</span></span> 

```csharp
String.Compare(strA.ToUpperInvariant(), strB.ToUpperInvariant(), 
               StringComparison.Ordinal);
```

```vb
String.Compare(strA.ToUpperInvariant(), strB.ToUpperInvariant(), 
               StringComparison.Ordinal)
```

<span data-ttu-id="a1639-227">这些比较仍非常快。</span><span class="sxs-lookup"><span data-stu-id="a1639-227">These comparisons are still very fast.</span></span>

<span data-ttu-id="a1639-228">[StringComparison.Ordinal](xref:System.StringComparison.Ordinal) 和 [StringComparison.OrdinalIgnoreCase](xref:System.StringComparison.OrdinalIgnoreCase) 均直接使用二进制值并最适合匹配。</span><span class="sxs-lookup"><span data-stu-id="a1639-228">Both [StringComparison.Ordinal](xref:System.StringComparison.Ordinal) and [StringComparison.OrdinalIgnoreCase](xref:System.StringComparison.OrdinalIgnoreCase) use the binary values directly, and are best suited for matching.</span></span> <span data-ttu-id="a1639-229">当不确定比较设置时，请使用这两个值中的其中一个。</span><span class="sxs-lookup"><span data-stu-id="a1639-229">When you are not sure about your comparison settings, use one of these two values.</span></span> <span data-ttu-id="a1639-230">不过，由于它们执行逐字节比较，因此不会按照语言排序顺序（如英语词典）进行排序，而是按照二进制排序顺序。</span><span class="sxs-lookup"><span data-stu-id="a1639-230">However, because they perform a byte-by-byte comparison, they do not sort by a linguistic sort order (like an English dictionary) but by a binary sort order.</span></span> <span data-ttu-id="a1639-231">如果向用户显示结果，则在大多数上下文中结果都看上去不正常。</span><span class="sxs-lookup"><span data-stu-id="a1639-231">The results may look odd in most contexts if displayed to users.</span></span>

<span data-ttu-id="a1639-232">序号语义是不包含 [StringComparison](xref:System.StringComparison) 自变量（包括相等运算符）的 [String](xref:System.String) `Equals` 重载的默认项。</span><span class="sxs-lookup"><span data-stu-id="a1639-232">Ordinal semantics are the default for [String](xref:System.String) `Equals` overloads that do not include a [StringComparison](xref:System.StringComparison) argument (including the equality operator).</span></span> <span data-ttu-id="a1639-233">总之，我们建议调用包含 [StringComparison](xref:System.StringComparison) 参数的重载。</span><span class="sxs-lookup"><span data-stu-id="a1639-233">In any case, we recommend that you call an overload that has a [StringComparison](xref:System.StringComparison) parameter.</span></span>

### <a name="string-operations-that-use-the-invariant-culture"></a><span data-ttu-id="a1639-234">使用固定区域性的字符串操作</span><span class="sxs-lookup"><span data-stu-id="a1639-234">String operations that use the invariant culture</span></span>

<span data-ttu-id="a1639-235">具有固定区域性的比较使用由静态 [CultureInfo.InvariantCulture](xref:System.Globalization.CultureInfo.InvariantCulture) 属性返回的 [CompareInfo](xref:System.Globalization.CompareInfo) 属性。</span><span class="sxs-lookup"><span data-stu-id="a1639-235">Comparisons with the invariant culture use the [CompareInfo](xref:System.Globalization.CompareInfo) property returned by the static [CultureInfo.InvariantCulture](xref:System.Globalization.CultureInfo.InvariantCulture) property.</span></span> <span data-ttu-id="a1639-236">此行为在所有系统中都相同；它会将其范围外的任何字符转换为其认为等效的固定字符。</span><span class="sxs-lookup"><span data-stu-id="a1639-236">This behavior is the same on all systems; it translates any characters outside its range into what it believes are equivalent invariant characters.</span></span> <span data-ttu-id="a1639-237">此策略对于在各个区域性中维护一组字符串行为很有用，但经常产生意外的结果。</span><span class="sxs-lookup"><span data-stu-id="a1639-237">This policy can be useful for maintaining one set of string behavior across cultures, but it often provides unexpected results.</span></span>

<span data-ttu-id="a1639-238">具有固定区域性的不区分大小写的比较也使用由静态 [CultureInfo.InvariantCulture](xref:System.Globalization.CultureInfo.InvariantCulture) 属性返回的静态 [CompareInfo](xref:System.Globalization.CompareInfo) 属性以获取比较信息。</span><span class="sxs-lookup"><span data-stu-id="a1639-238">Case-insensitive comparisons with the invariant culture use the static [CompareInfo](xref:System.Globalization.CompareInfo) property returned by the static [CultureInfo.InvariantCulture](xref:System.Globalization.CultureInfo.InvariantCulture) property for comparison information as well.</span></span> <span data-ttu-id="a1639-239">所转换字符中的任何大小写差异都将被忽略。</span><span class="sxs-lookup"><span data-stu-id="a1639-239">Any case differences among these translated characters are ignored.</span></span>

<span data-ttu-id="a1639-240">[CultureInfo.InvariantCulture](xref:System.Globalization.CultureInfo.InvariantCulture) 对象使 [String](xref:System.String) `Compare` 方法将一组特定的字符解释为等效字符。</span><span class="sxs-lookup"><span data-stu-id="a1639-240">The [CultureInfo.InvariantCulture](xref:System.Globalization.CultureInfo.InvariantCulture) object makes a [String](xref:System.String) `Compare` method interpret certain sets of characters as equivalent.</span></span> <span data-ttu-id="a1639-241">例如，下面的等效字符在固定区域性中是有效的：</span><span class="sxs-lookup"><span data-stu-id="a1639-241">For example, the following equivalence is valid under the invariant culture:</span></span>

<span data-ttu-id="a1639-242">InvariantCulture：a + ̊ = å</span><span class="sxs-lookup"><span data-stu-id="a1639-242">InvariantCulture: a + ̊ = å</span></span>

<span data-ttu-id="a1639-243">当 A 字符的小写拉丁字母“a”(\u0061) 位于字符 "+ " ̊" (\u030a) 组合圆圈旁边，则产生上方带有圆圈的小写拉丁字母“å”(\u00e5)。</span><span class="sxs-lookup"><span data-stu-id="a1639-243">The latin small lette A character "a" (\u0061), when it is next to the combining ring above character "+ " ̊" (\u030a), is interpreted as the latin small letter A with ring above character "å" (\u00e5).</span></span> <span data-ttu-id="a1639-244">如下面的示例所示，此行为不同于序号比较。</span><span class="sxs-lookup"><span data-stu-id="a1639-244">As the following example shows, this behavior differs from ordinal comparison.</span></span>

```csharp
string separated = "\u0061\u030a";
string combined = "\u00e5";

Console.WriteLine("Equal sort weight of {0} and {1} using InvariantCulture: {2}",
                  separated, combined, 
                  String.Compare(separated, combined, 
                                 StringComparison.InvariantCulture) == 0);

Console.WriteLine("Equal sort weight of {0} and {1} using Ordinal: {2}",
                  separated, combined,
                  String.Compare(separated, combined, 
                                 StringComparison.Ordinal) == 0);
// The example displays the following output:
//    Equal sort weight of a° and å using InvariantCulture: True
//    Equal sort weight of a° and å using Ordinal: False 
```

```vb
Dim separated As String = ChrW(&h61) + ChrW(&h30a)
Dim combined As String = ChrW(&he5)

Console.WriteLine("Equal sort weight of {0} and {1} using InvariantCulture: {2}", _
                  separated, combined, _
                  String.Compare(separated, combined, _ 
                                 StringComparison.InvariantCulture) = 0)

Console.WriteLine("Equal sort weight of {0} and {1} using Ordinal: {2}", _
                  separated, combined, _
                  String.Compare(separated, combined, _
                                 StringComparison.Ordinal) = 0)
' The example displays the following output:
'    Equal sort weight of a° and å using InvariantCulture: True
'    Equal sort weight of a° and å using Ordinal: False
```

<span data-ttu-id="a1639-245">当解释其中出现如“å”组合的文件名称、cookie 或其他内容时，序号比较仍会提供最透明和最合适的行为。</span><span class="sxs-lookup"><span data-stu-id="a1639-245">When interpreting file names, cookies, or anything else where a combination such as "å" can appear, ordinal comparisons still offer the most transparent and fitting behavior.</span></span>

<span data-ttu-id="a1639-246">总的来说，固定区域性具有极少的对比较有用的属性。</span><span class="sxs-lookup"><span data-stu-id="a1639-246">On balance, the invariant culture has very few properties that make it useful for comparison.</span></span> <span data-ttu-id="a1639-247">它会以与语言相关的方式执行比较，使其无法保证完整的符号等效性，但它并不是任何区域性中显示的选择。</span><span class="sxs-lookup"><span data-stu-id="a1639-247">It does comparison in a linguistically relevant manner, which prevents it from guaranteeing full symbolic equivalence, but it is not the choice for display in any culture.</span></span> <span data-ttu-id="a1639-248">例如，如果应用程序附带包含用于显示的已排序标识符列表的大型数据文件，则添加到此列表将需要使用固定条件样式排序插入。</span><span class="sxs-lookup"><span data-stu-id="a1639-248">For example, if a large data file that contains a list of sorted identifiers for display accompanies an application, adding to this list would require an insertion with invariant-style sorting.</span></span>

## <a name="choosing-a-stringcomparison-member-for-your-method-call"></a><span data-ttu-id="a1639-249">为方法调用选择 StringComparison 成员</span><span class="sxs-lookup"><span data-stu-id="a1639-249">Choosing a StringComparison member for your method call</span></span>

<span data-ttu-id="a1639-250">下表概述了从语义字符串上下文到 [StringComparison](xref:System.StringComparison) 枚举成员的映射。</span><span class="sxs-lookup"><span data-stu-id="a1639-250">The following table outlines the mapping from semantic string context to a [StringComparison](xref:System.StringComparison) enumeration member.</span></span>

<span data-ttu-id="a1639-251">数据</span><span class="sxs-lookup"><span data-stu-id="a1639-251">Data</span></span> | <span data-ttu-id="a1639-252">行为</span><span class="sxs-lookup"><span data-stu-id="a1639-252">Behavior</span></span> | <span data-ttu-id="a1639-253">相应的 System.StringComparison 值</span><span class="sxs-lookup"><span data-stu-id="a1639-253">Corresponding System.StringComparison value</span></span>
---- | -------- | -------------------------------------------
<span data-ttu-id="a1639-254">区分大小写的内部标识符、区分大小写的标准标识符（例如 XML 和 HTTP），或者区分大小写的安全相关设置。</span><span class="sxs-lookup"><span data-stu-id="a1639-254">Case-sensitive internal identifiers, case-sensitive identifiers in standards such as XML and HTTP, or case-sensitive security-related settings.</span></span> | <span data-ttu-id="a1639-255">字节完全匹配的非语言标识符。</span><span class="sxs-lookup"><span data-stu-id="a1639-255">A non-linguistic identifier, where bytes match exactly.</span></span> | [<span data-ttu-id="a1639-256">StringComparison.Ordinal</span><span class="sxs-lookup"><span data-stu-id="a1639-256">StringComparison.Ordinal</span></span>](xref:System.StringComparison.Ordinal)
<span data-ttu-id="a1639-257">不区分大小写的内部标识符、不区分大小写的标准标识符（例如 XML 和 HTTP）、文件路径、注册表项和值、环境变量、资源标识符（例如，句柄名称）或不区分大小写的安全相关设置。</span><span class="sxs-lookup"><span data-stu-id="a1639-257">Case-insensitive internal identifiers, case-insensitive identifiers in standards such as XML and HTTP, file paths, registry keys and values, environment variables, resource identifiers (for example, handle names), or case-insensitive security-related settings.</span></span> | <span data-ttu-id="a1639-258">字节完全匹配的非语言标识符。</span><span class="sxs-lookup"><span data-stu-id="a1639-258">A non-linguistic identifier, where case is irrelevant.</span></span> | [<span data-ttu-id="a1639-259">StringComparison.OrdinalIgnoreCase</span><span class="sxs-lookup"><span data-stu-id="a1639-259">StringComparison.OrdinalIgnoreCase</span></span>](xref:System.StringComparison.OrdinalIgnoreCase)
<span data-ttu-id="a1639-260">向用户显示的数据或大多数用户输入。</span><span class="sxs-lookup"><span data-stu-id="a1639-260">Data displayed to the user or most user input.</span></span> | <span data-ttu-id="a1639-261">需要本地语言自定义的数据。</span><span class="sxs-lookup"><span data-stu-id="a1639-261">Data that requires local linguistic customs.</span></span> | <span data-ttu-id="a1639-262">[StringComparison.CurrentCulture](xref:System.StringComparison.CurrentCulture) 或 [CurrentCultureIgnoreCase](xref:System.StringComparison.CurrentCultureIgnoreCase)</span><span class="sxs-lookup"><span data-stu-id="a1639-262">[StringComparison.CurrentCulture](xref:System.StringComparison.CurrentCulture) or [CurrentCultureIgnoreCase](xref:System.StringComparison.CurrentCultureIgnoreCase)</span></span>

## <a name="common-string-comparison-methods"></a><span data-ttu-id="a1639-263">常见的字符串比较方法</span><span class="sxs-lookup"><span data-stu-id="a1639-263">Common string comparison methods</span></span>

<span data-ttu-id="a1639-264">以下各节介绍最常用于执行字符串比较的方法。</span><span class="sxs-lookup"><span data-stu-id="a1639-264">The following sections describe the methods that are most commonly used for string comparison.</span></span>

### <a name="stringcompare"></a><span data-ttu-id="a1639-265">String.Compare</span><span class="sxs-lookup"><span data-stu-id="a1639-265">String.Compare</span></span>

<span data-ttu-id="a1639-266">默认解释：[StringComparison.CurrentCulture](xref:System.StringComparison.CurrentCulture)。</span><span class="sxs-lookup"><span data-stu-id="a1639-266">Default interpretation: [StringComparison.CurrentCulture](xref:System.StringComparison.CurrentCulture).</span></span>

<span data-ttu-id="a1639-267">作为字符串解释最核心的操作，应根据当前区域性检查这些方法调用的所有实例来确定是否应该从区域性（符号）解释或分离字符串。</span><span class="sxs-lookup"><span data-stu-id="a1639-267">As the operation most central to string interpretation, all instances of these method calls should be examined to determine whether strings should be interpreted according to the current culture, or dissociated from the culture (symbolically).</span></span> <span data-ttu-id="a1639-268">通常情况下，采用后者，并且应改用 [StringComparison.Ordinal](xref:System.StringComparison.Ordinal) 比较。</span><span class="sxs-lookup"><span data-stu-id="a1639-268">Typically, it is the latter, and a [StringComparison.Ordinal](xref:System.StringComparison.Ordinal) comparison should be used instead.</span></span>

<span data-ttu-id="a1639-269">[CultureInfo.CompareInfo](xref:System.Globalization.CultureInfo.CompareInfo) 属性返回的 [System.Globalization.CompareInfo](xref:System.Globalization.CompareInfo) 类也包括利用 [CompareOptions](xref:System.Globalization.CompareOptions) 标记枚举的方式提供大量匹配选项（序号、忽略空白、忽略假名类型等）的 [Compare](xref:System.Globalization.CompareInfo.Compare(System.String,System.Int32,System.String,System.Int32,System.Globalization.CompareOptions)) 方法。</span><span class="sxs-lookup"><span data-stu-id="a1639-269">The [System.Globalization.CompareInfo](xref:System.Globalization.CompareInfo) class, which is returned by the [CultureInfo.CompareInfo](xref:System.Globalization.CultureInfo.CompareInfo) property, also includes a [Compare](xref:System.Globalization.CompareInfo.Compare(System.String,System.Int32,System.String,System.Int32,System.Globalization.CompareOptions)) method that provides a large number of matching options (ordinal, ignoring white space, ignoring kana type, and so on) by means of the [CompareOptions](xref:System.Globalization.CompareOptions) flag enumeration.</span></span> 

### <a name="stringcompareto"></a><span data-ttu-id="a1639-270">String.CompareTo</span><span class="sxs-lookup"><span data-stu-id="a1639-270">String.CompareTo</span></span>

<span data-ttu-id="a1639-271">默认解释：[StringComparison.CurrentCulture](xref:System.StringComparison.CurrentCulture)。</span><span class="sxs-lookup"><span data-stu-id="a1639-271">Default interpretation: [StringComparison.CurrentCulture](xref:System.StringComparison.CurrentCulture).</span></span>

<span data-ttu-id="a1639-272">此方法当前不提供指定 [StringComparison](xref:System.StringComparison) 类型的重载。</span><span class="sxs-lookup"><span data-stu-id="a1639-272">This method does not currently offer an overload that specifies a [StringComparison](xref:System.StringComparison) type.</span></span> <span data-ttu-id="a1639-273">通常可以将此方法转换为建议的 [String.Compare(String, String, StringComparison)](xref:System.String.Compare(System.String,System.String,System.StringComparison)) 形式。</span><span class="sxs-lookup"><span data-stu-id="a1639-273">It is usually possible to convert this method to the recommended [String.Compare(String, String, StringComparison)](xref:System.String.Compare(System.String,System.String,System.StringComparison)) form.</span></span>

<span data-ttu-id="a1639-274">实现 [IComparable](xref:System.IComparable) 和 [IComparable&lt;T&gt;](xref:System.IComparable%601) 接口的类型实现此方法。</span><span class="sxs-lookup"><span data-stu-id="a1639-274">Types that implement the [IComparable](xref:System.IComparable) and [IComparable&lt;T&gt;](xref:System.IComparable%601) interfaces implement this method.</span></span> <span data-ttu-id="a1639-275">由于它不提供 [StringComparison](xref:System.StringComparison) 参数选项，因此实现类型经常使用户在其构造函数中指定 [StringComparer](xref:System.StringComparer)。</span><span class="sxs-lookup"><span data-stu-id="a1639-275">Because it does not offer the option of a [StringComparison](xref:System.StringComparison) parameter, implementing types often let the user specify a [StringComparer](xref:System.StringComparer) in their constructor.</span></span> <span data-ttu-id="a1639-276">下面的示例定义 `FileName` 类，其类构造函数包含 [StringComparer](xref:System.StringComparer) 参数。</span><span class="sxs-lookup"><span data-stu-id="a1639-276">The following example defines a `FileName` class whose class constructor includes a [StringComparer](xref:System.StringComparer) parameter.</span></span> <span data-ttu-id="a1639-277">然后，此 [StringComparer](xref:System.StringComparer) 对象将在 `FileName.CompareTo` 方法中使用。</span><span class="sxs-lookup"><span data-stu-id="a1639-277">This [StringComparer](xref:System.StringComparer) object is then used in the `FileName.CompareTo` method.</span></span>

```csharp
using System;

public class FileName : IComparable
{
   string fname;
   StringComparer comparer; 

   public FileName(string name, StringComparer comparer)
   {
      if (String.IsNullOrEmpty(name))
         throw new ArgumentNullException("name");

      this.fname = name;

      if (comparer != null)
         this.comparer = comparer;
      else
         this.comparer = StringComparer.OrdinalIgnoreCase;
   }

   public string Name
   {
      get { return fname; }
   }

   public int CompareTo(object obj)
   {
      if (obj == null) return 1;

      if (! (obj is FileName))
         return comparer.Compare(this.fname, obj.ToString());
      else
         return comparer.Compare(this.fname, ((FileName) obj).Name);
   }
}
```

```vb
Public Class FileName : Implements IComparable
   Dim fname As String
   Dim comparer As StringComparer 

   Public Sub New(name As String, comparer As StringComparer)
      If String.IsNullOrEmpty(name) Then
         Throw New ArgumentNullException("name")
      End If

      Me.fname = name

      If comparer IsNot Nothing Then
         Me.comparer = comparer
      Else
         Me.comparer = StringComparer.OrdinalIgnoreCase
      End If      
   End Sub

   Public ReadOnly Property Name As String
      Get
         Return fname
      End Get   
   End Property

   Public Function CompareTo(obj As Object) As Integer _
          Implements IComparable.CompareTo
      If obj Is Nothing Then Return 1

      If Not TypeOf obj Is FileName Then
         obj = obj.ToString()
      Else
         obj = CType(obj, FileName).Name
      End If         
      Return comparer.Compare(Me.fname, obj)
   End Function
End Class
```

### <a name="stringequals"></a><span data-ttu-id="a1639-278">String.Equals</span><span class="sxs-lookup"><span data-stu-id="a1639-278">String.Equals</span></span>

<span data-ttu-id="a1639-279">默认解释：[StringComparison.Ordinal](xref:System.StringComparison.Ordinal)。</span><span class="sxs-lookup"><span data-stu-id="a1639-279">Default interpretation: [StringComparison.Ordinal](xref:System.StringComparison.Ordinal).</span></span>

<span data-ttu-id="a1639-280">[String](xref:System.String) 类可通过调用静态或实例 `Equals` 方法重载或使用静态相等运算符，测试是否相等。</span><span class="sxs-lookup"><span data-stu-id="a1639-280">The [String](xref:System.String) class lets you test for equality by calling either the static or instance `Equals` method overloads, or by using the static equality operator.</span></span> <span data-ttu-id="a1639-281">默认情况下，重载和运算符使用序号比较。</span><span class="sxs-lookup"><span data-stu-id="a1639-281">The overloads and operator use ordinal comparison by default.</span></span> <span data-ttu-id="a1639-282">但是，我们仍然建议调用显式指定 [StringComparison](xref:System.StringComparison) 类型的重载，即使想要执行序号比较；这将更轻松地搜索特定字符串解释的代码。</span><span class="sxs-lookup"><span data-stu-id="a1639-282">However, we still recommend that you call an overload that explicitly specifies the [StringComparison](xref:System.StringComparison) type even if you want to perform an ordinal comparison; this makes it easier to search code for a certain string interpretation.</span></span> 

### <a name="stringtoupper-and-stringtolower"></a><span data-ttu-id="a1639-283">String.ToUpper 和 String.ToLower</span><span class="sxs-lookup"><span data-stu-id="a1639-283">String.ToUpper and String.ToLower</span></span>

<span data-ttu-id="a1639-284">默认解释：[StringComparison.CurrentCulture](xref:System.StringComparison.CurrentCulture)。</span><span class="sxs-lookup"><span data-stu-id="a1639-284">Default interpretation: [StringComparison.CurrentCulture](xref:System.StringComparison.CurrentCulture).</span></span>

<span data-ttu-id="a1639-285">应谨慎使用这些方法，因为将字符串强制为大写或小写经常用作在不考虑大小写的情况下比较字符串的较小规范化。</span><span class="sxs-lookup"><span data-stu-id="a1639-285">You should be careful when you use these methods, because forcing a string to a uppercase or lowercase is often used as a small normalization for comparing strings regardless of case.</span></span> <span data-ttu-id="a1639-286">如果是这样，请考虑使用不区分大小写的比较。</span><span class="sxs-lookup"><span data-stu-id="a1639-286">If so, consider using a case-insensitive comparison.</span></span> 

<span data-ttu-id="a1639-287">还可以使用 [String.ToUpperInvariant](xref:System.String.ToUpperInvariant) 和 [String.ToLowerInvariant](xref:System.String.ToLowerInvariant) 方法。</span><span class="sxs-lookup"><span data-stu-id="a1639-287">The [String.ToUpperInvariant](xref:System.String.ToUpperInvariant) and [String.ToLowerInvariant](xref:System.String.ToLowerInvariant) methods are also available.</span></span> <span data-ttu-id="a1639-288">[ToUpperInvariant](xref:System.String.ToUpperInvariant) 是规范化大小写的标准方式。</span><span class="sxs-lookup"><span data-stu-id="a1639-288">[ToUpperInvariant](xref:System.String.ToUpperInvariant) is the standard way to normalize case.</span></span> <span data-ttu-id="a1639-289">使用 [StringComparison.OrdinalIgnoreCase](xref:System.StringComparison.OrdinalIgnoreCase) 进行的比较在行为上是两个调用的组合：对两个字符串自变量调用 [ToUpperInvariant](xref:System.String.ToUpperInvariant)，使用 [StringComparison.Ordinal](xref:System.StringComparison.Ordinal) 执行比较。</span><span class="sxs-lookup"><span data-stu-id="a1639-289">Comparisons made using [StringComparison.OrdinalIgnoreCase](xref:System.StringComparison.OrdinalIgnoreCase) are behaviorally the composition of two calls: calling [ToUpperInvariant](xref:System.String.ToUpperInvariant) on both string arguments, and doing a comparison using [StringComparison.Ordinal](xref:System.StringComparison.Ordinal).</span></span>

<span data-ttu-id="a1639-290">通过向方法传递表示区域性的 [CultureInfo](xref:System.Globalization.CultureInfo) 对象，重载也已可用于转换该特性区域性中的大写和小写字母。</span><span class="sxs-lookup"><span data-stu-id="a1639-290">Overloads are also available for converting to uppercase and lowercase in a specific culture, by passing a [CultureInfo](xref:System.Globalization.CultureInfo) object that represents that culture to the method.</span></span>

### <a name="chartoupper-and-chartolower"></a><span data-ttu-id="a1639-291">Char.ToUpper 和 Char.ToLower</span><span class="sxs-lookup"><span data-stu-id="a1639-291">Char.ToUpper and Char.ToLower</span></span>

<span data-ttu-id="a1639-292">默认解释：[StringComparison.CurrentCulture](xref:System.StringComparison.CurrentCulture)。</span><span class="sxs-lookup"><span data-stu-id="a1639-292">Default interpretation: [StringComparison.CurrentCulture](xref:System.StringComparison.CurrentCulture).</span></span>

<span data-ttu-id="a1639-293">这些方法的工作原理类似于上一节中所述的 [String.ToUpper](xref:System.String.ToUpper) 和 [String.ToLower](xref:System.String.ToLower) 方法。</span><span class="sxs-lookup"><span data-stu-id="a1639-293">These methods work similarly to the [String.ToUpper](xref:System.String.ToUpper) and [String.ToLower](xref:System.String.ToLower) methods described in the previous section.</span></span>

### <a name="stringstartswith-and-stringendswith"></a><span data-ttu-id="a1639-294">String.StartsWith 和 String.EndsWith</span><span class="sxs-lookup"><span data-stu-id="a1639-294">String.StartsWith and String.EndsWith</span></span>

<span data-ttu-id="a1639-295">默认解释：[StringComparison.CurrentCulture](xref:System.StringComparison.CurrentCulture)。</span><span class="sxs-lookup"><span data-stu-id="a1639-295">Default interpretation: [StringComparison.CurrentCulture](xref:System.StringComparison.CurrentCulture).</span></span>

<span data-ttu-id="a1639-296">默认情况下，这两种方法执行区分区域性的比较。</span><span class="sxs-lookup"><span data-stu-id="a1639-296">By default, both of these methods perform a culture-sensitive comparison.</span></span>

### <a name="stringindexof-and-stringlastindexof"></a><span data-ttu-id="a1639-297">String.IndexOf 和 String.LastIndexOf</span><span class="sxs-lookup"><span data-stu-id="a1639-297">String.IndexOf and String.LastIndexOf</span></span>

<span data-ttu-id="a1639-298">默认解释：[StringComparison.CurrentCulture](xref:System.StringComparison.CurrentCulture)。</span><span class="sxs-lookup"><span data-stu-id="a1639-298">Default interpretation: [StringComparison.CurrentCulture](xref:System.StringComparison.CurrentCulture).</span></span>

<span data-ttu-id="a1639-299">这些方法的默认重载如何执行比较方面缺乏一致性。</span><span class="sxs-lookup"><span data-stu-id="a1639-299">There is a lack of consistency in how the default overloads of these methods perform comparisons.</span></span> <span data-ttu-id="a1639-300">包含 [Char](xref:System.Char) 参数的所有 [String](xref:System.String) `IndexOf` 和 [String](xref:System.String) `LastIndexOf` 方法都执行序号比较，但是包含 [String](xref:System.String) 参数的默认 [String](xref:System.String) `IndexOf` 和 [String`](xref:System.String) `LastIndexOf\` 方法都执行区分区域性的比较。</span><span class="sxs-lookup"><span data-stu-id="a1639-300">All [String](xref:System.String) `IndexOf` and [String](xref:System.String) `LastIndexOf` methods that include a [Char](xref:System.Char) parameter perform an ordinal comparison, but the default [String](xref:System.String) `IndexOf` and [String`](xref:System.String) `LastIndexOf\` methods that include a [String](xref:System.String) parameter perform a culture-sensitive comparison.</span></span> 

<span data-ttu-id="a1639-301">如果调用 ` `IndexOf` or `LastIndexOf\` 方法并向其传递一个字符串以在当前实例中查找，那么我们建议调用显式指定 [StringComparison](xref:System.StringComparison) 类型的重载。</span><span class="sxs-lookup"><span data-stu-id="a1639-301">If you call ` `IndexOf` or `LastIndexOf\` method and pass it a string to locate in the current instance, we recommend that you call an overload that explicitly specifies the [StringComparison](xref:System.StringComparison) type.</span></span> <span data-ttu-id="a1639-302">包括 [Char](xref:System.Char) 自变量的重载不允许指定 [StringComparison](xref:System.StringComparison) 类型。</span><span class="sxs-lookup"><span data-stu-id="a1639-302">The overloads that include a [Char](xref:System.Char) argument do not allow you to specify a [StringComparison](xref:System.StringComparison) type.</span></span>

## <a name="methods-that-perform-string-comparison-indirectly"></a><span data-ttu-id="a1639-303">间接执行字符串比较的方法</span><span class="sxs-lookup"><span data-stu-id="a1639-303">Methods that perform string comparison indirectly</span></span>

<span data-ttu-id="a1639-304">将字符串比较作为核心操作的一些非字符串方法使用 [StringComparer](xref:System.StringComparer) 类型。</span><span class="sxs-lookup"><span data-stu-id="a1639-304">Some non-string methods that have string comparison as a central operation use the [StringComparer](xref:System.StringComparer) type.</span></span> <span data-ttu-id="a1639-305">[StringComparer](xref:System.StringComparer) 类包含四个返回 [StringComparer](xref:System.StringComparer) 实例的静态属性，这些实例的 `Compare` 方法可执行以下类型的字符串比较：</span><span class="sxs-lookup"><span data-stu-id="a1639-305">The [StringComparer](xref:System.StringComparer) class includes four static properties that return [StringComparer](xref:System.StringComparer) instances whose `Compare` methods perform the following types of string comparisons:</span></span>

* <span data-ttu-id="a1639-306">使用当前区域性的区分区域性的字符串比较。</span><span class="sxs-lookup"><span data-stu-id="a1639-306">Culture-sensitive string comparisons using the current culture.</span></span> <span data-ttu-id="a1639-307">此 [StringComparer](xref:System.StringComparer) 对象由 [StringComparer.CurrentCulture](xref:System.StringComparer.CurrentCulture) 属性返回。</span><span class="sxs-lookup"><span data-stu-id="a1639-307">This [StringComparer](xref:System.StringComparer) object is returned by the [StringComparer.CurrentCulture](xref:System.StringComparer.CurrentCulture) property.</span></span>

* <span data-ttu-id="a1639-308">使用当前区域性的不区分区域性的比较。</span><span class="sxs-lookup"><span data-stu-id="a1639-308">Case-insensitive comparisons using the current culture.</span></span> <span data-ttu-id="a1639-309">此 [StringComparer](xref:System.StringComparer) 对象由 [StringComparer.CurrentCultureIgnoreCase](xref:System.StringComparer.CurrentCultureIgnoreCase) 属性返回。</span><span class="sxs-lookup"><span data-stu-id="a1639-309">This [StringComparer](xref:System.StringComparer) object is returned by the [StringComparer.CurrentCultureIgnoreCase](xref:System.StringComparer.CurrentCultureIgnoreCase) property.</span></span>

* <span data-ttu-id="a1639-310">序号比较。</span><span class="sxs-lookup"><span data-stu-id="a1639-310">Ordinal comparison.</span></span> <span data-ttu-id="a1639-311">此 [StringComparer](xref:System.StringComparer) 对象由 [StringComparer.Ordinal](xref:System.StringComparer.Ordinal) 属性返回。</span><span class="sxs-lookup"><span data-stu-id="a1639-311">This [StringComparer](xref:System.StringComparer) object is returned by the [StringComparer.Ordinal](xref:System.StringComparer.Ordinal) property.</span></span> 

* <span data-ttu-id="a1639-312">不区分大小写的序号比较。</span><span class="sxs-lookup"><span data-stu-id="a1639-312">Case-insensitive ordinal comparison.</span></span> <span data-ttu-id="a1639-313">此 [StringComparer](xref:System.StringComparer) 对象由 [StringComparer.OrdinalIgnoreCase](xref:System.StringComparer.OrdinalIgnoreCase) 属性返回。</span><span class="sxs-lookup"><span data-stu-id="a1639-313">This [StringComparer](xref:System.StringComparer) object is returned by the [StringComparer.OrdinalIgnoreCase](xref:System.StringComparer.OrdinalIgnoreCase) property.</span></span>

### <a name="arraysort-and-arraybinarysearch"></a><span data-ttu-id="a1639-314">Array.Sort 和 Array.BinarySearch</span><span class="sxs-lookup"><span data-stu-id="a1639-314">Array.Sort and Array.BinarySearch</span></span>

<span data-ttu-id="a1639-315">默认解释：[StringComparison.CurrentCulture](xref:System.StringComparison.CurrentCulture)。</span><span class="sxs-lookup"><span data-stu-id="a1639-315">Default interpretation: [StringComparison.CurrentCulture](xref:System.StringComparison.CurrentCulture).</span></span>

<span data-ttu-id="a1639-316">当在集合中存储任何数据，或将持久数据从文件或数据库中读取到集合中时，切换当前区域性可能会使集合中的固定条件无效。</span><span class="sxs-lookup"><span data-stu-id="a1639-316">When you store any data in a collection, or read persisted data from a file or database into a collection, switching the current culture can invalidate the invariants in the collection.</span></span> <span data-ttu-id="a1639-317">[Array.BinarySearch](xref:System.Array.BinarySearch(System.Array,System.Object)) 方法假定已对数组中要搜索的元素排序。</span><span class="sxs-lookup"><span data-stu-id="a1639-317">The [Array.BinarySearch](xref:System.Array.BinarySearch(System.Array,System.Object)) method assumes that the elements in the array to be searched are already sorted.</span></span> <span data-ttu-id="a1639-318">若要对数组中的任何字符串元素进行排序，[Array.Sort](xref:System.Array.Sort(System.Array)) 方法会调用 [String] `Compare` 方法以对各个元素进行排序。</span><span class="sxs-lookup"><span data-stu-id="a1639-318">To sort any string element in the array, the [Array.Sort](xref:System.Array.Sort(System.Array)) method calls the [String] `Compare` method to order individual elements.</span></span> <span data-ttu-id="a1639-319">如果对数组进行排序和搜索其内容的时间范围内区域性发生变化，那么使用区分区域性的比较器会很危险。</span><span class="sxs-lookup"><span data-stu-id="a1639-319">Using a culture-sensitive comparer can be dangerous if the culture changes between the time that the array is sorted and its contents are searched.</span></span> <span data-ttu-id="a1639-320">例如，在下面的代码中，在由 `Thread.CurrentThread.CurrentCulture` 属性提供的比较器中进行存储和检索操作。</span><span class="sxs-lookup"><span data-stu-id="a1639-320">For example, in the following code, storage and retrieval operate on the comparer that is provided implicitly by the `Thread.CurrentThread.CurrentCulture` property.</span></span> <span data-ttu-id="a1639-321">如果在调用 `StoreNames` 和 `DoesNameExist` 之间更改了区域性（尤其是数组内容保存在两个方法调用之间的某个位置），那么二进制搜索可能会失败。</span><span class="sxs-lookup"><span data-stu-id="a1639-321">If the culture can change between the calls to `StoreNames` and `DoesNameExist`, and especially if the array contents are persisted somewhere between the two method calls, the binary search may fail.</span></span> 

```csharp
// Incorrect.
string []storedNames;

public void StoreNames(string [] names)
{
   int index = 0;
   storedNames = new string[names.Length];

   foreach (string name in names)
   {
      this.storedNames[index++] = name;
   }

   Array.Sort(names); // Line A.
}

public bool DoesNameExist(string name)
{
   return (Array.BinarySearch(this.storedNames, name) >= 0);  // Line B.
}
```

```vb
' Incorrect.
Dim storedNames() As String

Public Sub StoreNames(names() As String)
   Dim index As Integer = 0
   ReDim storedNames(names.Length - 1)

   For Each name As String In names
      Me.storedNames(index) = name
      index+= 1
   Next

   Array.Sort(names)          ' Line A.
End Sub

Public Function DoesNameExist(name As String) As Boolean
   Return Array.BinarySearch(Me.storedNames, name) >= 0      ' Line B.
End Function
```

<span data-ttu-id="a1639-322">建议的变体将显示在下面使用相同序号（不区分区域性）比较方法进行排序并搜索数组的示例中。</span><span class="sxs-lookup"><span data-stu-id="a1639-322">A recommended variation appears in the following example, which uses the same ordinal (culture-insensitive) comparison method both to sort and to search the array.</span></span> <span data-ttu-id="a1639-323">在这两个示例中，更改代码会反映在标记 `Line A` 和 `Line B` 的代码行中。</span><span class="sxs-lookup"><span data-stu-id="a1639-323">The change code is reflected in the lines labeled `Line A` and `Line B` in the two examples.</span></span>

```csharp
// Correct.
string []storedNames;

public void StoreNames(string [] names)
{
   int index = 0;
   storedNames = new string[names.Length];

   foreach (string name in names)
   {
      this.storedNames[index++] = name;
   }

   Array.Sort(names, StringComparer.Ordinal);  // Line A.
}

public bool DoesNameExist(string name)
{
   return (Array.BinarySearch(this.storedNames, name, StringComparer.Ordinal) >= 0);  // Line B.
}
```

```vb
' Correct.
Dim storedNames() As String

Public Sub StoreNames(names() As String)
   Dim index As Integer = 0
   ReDim storedNames(names.Length - 1)

   For Each name As String In names
      Me.storedNames(index) = name
      index+= 1
   Next

   Array.Sort(names, StringComparer.Ordinal)           ' Line A.
End Sub

Public Function DoesNameExist(name As String) As Boolean
   Return Array.BinarySearch(Me.storedNames, name, StringComparer.Ordinal) >= 0      ' Line B.
End Function
```

<span data-ttu-id="a1639-324">如果此数据永久保留并跨区域性移动，并且使用排序来向用户显示此数据，则可以考虑使用 `StringComparison.InvariantCulture`，其语言操作可获得更好的用户输出且不受区域性更改的影响。</span><span class="sxs-lookup"><span data-stu-id="a1639-324">If this data is persisted and moved across cultures, and sorting is used to present this data to the user, you might consider using `StringComparison.InvariantCulture`, which operates linguistically for better user output but is unaffected by changes in culture.</span></span> <span data-ttu-id="a1639-325">下面的示例修改了前面两个示例，使用固定区域性对数组进行排序和搜索。</span><span class="sxs-lookup"><span data-stu-id="a1639-325">The following example modifies the two previous examples to use the invariant culture for sorting and searching the array.</span></span>

```csharp
// Correct.
string []storedNames;

public void StoreNames(string [] names)
{
   int index = 0;
   storedNames = new string[names.Length];

   foreach (string name in names)
   {
      this.storedNames[index++] = name;
   }

   Array.Sort(names, StringComparer.InvariantCulture);  // Line A.
}

public bool DoesNameExist(string name)
{
   return (Array.BinarySearch(this.storedNames, name, StringComparer.InvariantCulture) >= 0);  // Line B.
}
```

```vb
' Correct.
Dim storedNames() As String

Public Sub StoreNames(names() As String)
   Dim index As Integer = 0
   ReDim storedNames(names.Length - 1)

   For Each name As String In names
      Me.storedNames(index) = name
      index+= 1
   Next

   Array.Sort(names, StringComparer.InvariantCulture)           ' Line A.
End Sub

Public Function DoesNameExist(name As String) As Boolean
   Return Array.BinarySearch(Me.storedNames, name, StringComparer.InvariantCulture) >= 0      ' Line B.
End Function
```

### <a name="collections-example-hashtable-constructor"></a><span data-ttu-id="a1639-326">集合示例：Hashtable 构造函数</span><span class="sxs-lookup"><span data-stu-id="a1639-326">Collections Example: Hashtable Constructor</span></span>

<span data-ttu-id="a1639-327">哈希字符串提供了第二个运算示例，该运算受比较字符串的方式影响。</span><span class="sxs-lookup"><span data-stu-id="a1639-327">Hashing strings provides a second example of an operation that is affected by the way in which strings are compared.</span></span> 

<span data-ttu-id="a1639-328">下面的示例实例化 [Hashtable](xref:System.Collections.Hashtable) 对象，方法是向其传递由 [StringComparer.OrdinalIgnoreCase](xref:System.StringComparer.OrdinalIgnoreCase) 属性返回的 [StringComparer](xref:System.StringComparer) 对象。</span><span class="sxs-lookup"><span data-stu-id="a1639-328">The following example instantiates a [Hashtable](xref:System.Collections.Hashtable) object by passing it the [StringComparer](xref:System.StringComparer) object that is returned by the [StringComparer.OrdinalIgnoreCase](xref:System.StringComparer.OrdinalIgnoreCase) property.</span></span> <span data-ttu-id="a1639-329">由于派生自 [StringComparer](xref:System.StringComparer) 的类 [StringComparer](xref:System.StringComparer) 实现 [IEqualityComparer](xref:System.Collections.IEqualityComparer) 接口，其 [GetHashCode](xref:System.Collections.IEqualityComparer) 方法用于计算哈希表中的字符串的哈希代码。</span><span class="sxs-lookup"><span data-stu-id="a1639-329">Because a class [StringComparer](xref:System.StringComparer) that is derived from [StringComparer](xref:System.StringComparer) implements the [IEqualityComparer](xref:System.Collections.IEqualityComparer) interface, its [GetHashCode](xref:System.Collections.IEqualityComparer) method is used to compute the hash code of strings in the hash table.</span></span>

```csharp
const int initialTableCapacity = 100;
Hashtable h;

public void PopulateFileTable(string directory)
{
   h = new Hashtable(initialTableCapacity, 
                     StringComparer.OrdinalIgnoreCase);

   foreach (string file in Directory.GetFiles(directory))
         h.Add(file, File.GetCreationTime(file));
}

public void PrintCreationTime(string targetFile)
{
   Object dt = h[targetFile];
   if (dt != null)
   {
      Console.WriteLine("File {0} was created at time {1}.",
         targetFile, 
         (DateTime) dt);
   }
   else
   {
      Console.WriteLine("File {0} does not exist.", targetFile);
   }
}
```

```vb
Const initialTableCapacity As Integer = 100
Dim h As Hashtable

Public Sub PopulateFileTable(dir As String)
   h = New Hashtable(initialTableCapacity, _
                     StringComparer.OrdinalIgnoreCase)

   For Each filename As String In Directory.GetFiles(dir)
      h.Add(filename, File.GetCreationTime(filename))
   Next                        
End Sub

Public Sub PrintCreationTime(targetFile As String)
   Dim dt As Object = h(targetFile)
   If dt IsNot Nothing Then
      Console.WriteLine("File {0} was created at {1}.", _
         targetFile, _
         CDate(dt))
   Else
      Console.WriteLine("File {0} does not exist.", targetFile)
   End If
End Sub  
```

## <a name="displaying-and-persisting-formatted-data"></a><span data-ttu-id="a1639-330">显示和保存有格式的数据</span><span class="sxs-lookup"><span data-stu-id="a1639-330">Displaying and persisting formatted data</span></span>

<span data-ttu-id="a1639-331">当给用户显示非字符串数据（如数字、日期和时间）时，使用用户的区域性设置来格式化他们。</span><span class="sxs-lookup"><span data-stu-id="a1639-331">When you display non-string data such as numbers and dates and times to users, format them by using the user's cultural settings.</span></span> <span data-ttu-id="a1639-332">默认情况下，数值类型和日期时间类型的 [String.Format](xref:System.String.Format(System.IFormatProvider,System.String,System.Object)) 方法和 `ToString` 方法使用当前线程区域性来执行格式设置操作。</span><span class="sxs-lookup"><span data-stu-id="a1639-332">By default, the [String.Format](xref:System.String.Format(System.IFormatProvider,System.String,System.Object)) method and the `ToString` methods of the numeric types and the date and time types use the current thread culture for formatting operations.</span></span> <span data-ttu-id="a1639-333">为了显式指定格式设置方法应使用当前区域性，可以调用包含 provider 参数的格式设置方法的重载（例如 [String.Format(IFormatProvider, String, Object[])](xref:System.String.Format(System.IFormatProvider,System.String,System.Object)) 或 [DateTime.ToString(IFormatProvider)](xref:System.DateTime.ToString(System.IFormatProvider))），然后向其传递 [CultureInfo.CurrentCulture](xref:System.Globalization.CultureInfo.CurrentCulture) 属性。</span><span class="sxs-lookup"><span data-stu-id="a1639-333">To explicitly specify that the formatting method should use the current culture, you can call an overload of a formatting method that has a provider parameter, such as [String.Format(IFormatProvider, String, Object[])](xref:System.String.Format(System.IFormatProvider,System.String,System.Object)) or [DateTime.ToString(IFormatProvider)](xref:System.DateTime.ToString(System.IFormatProvider)), and pass it the [CultureInfo.CurrentCulture](xref:System.Globalization.CultureInfo.CurrentCulture) property.</span></span> 

<span data-ttu-id="a1639-334">您可以保留非字符串数据作为二进制数据或作为格式化数据。</span><span class="sxs-lookup"><span data-stu-id="a1639-334">You can persist non-string data either as binary data or as formatted data.</span></span> <span data-ttu-id="a1639-335">如果选择将其保存为格式化数据，应调用包括 *provider* 参数的格式设置方法重载，并向其传递 [CultureInfo.InvariantCulture](xref:System.Globalization.CultureInfo.InvariantCulture) 属性。</span><span class="sxs-lookup"><span data-stu-id="a1639-335">If you choose to save it as formatted data, you should call a formatting method overload that includes a *provider* parameter and pass it the [CultureInfo.InvariantCulture](xref:System.Globalization.CultureInfo.InvariantCulture) property.</span></span> <span data-ttu-id="a1639-336">固定区域性为独立于区域性和计算机的格式化数据提供一致的格式。</span><span class="sxs-lookup"><span data-stu-id="a1639-336">The invariant culture provides a consistent format for formatted data that is independent of culture and machine.</span></span> <span data-ttu-id="a1639-337">相反，使用区域性而非固定区域性进行格式化的持久性数据具有许多限制：</span><span class="sxs-lookup"><span data-stu-id="a1639-337">In contrast, persisting data that is formatted by using cultures other than the invariant culture has a number of limitations:</span></span> 

* <span data-ttu-id="a1639-338">如果在具有不同区域性的系统上检索数据，或者如果当前系统用户更改当前区域性或者尝试检索数据时，该数据可能不可用。</span><span class="sxs-lookup"><span data-stu-id="a1639-338">The data is likely to be unusable if it is retrieved on a system that has a different culture, or if the user of the current system changes the current culture and tries to retrieve the data.</span></span> 

* <span data-ttu-id="a1639-339">特定计算机上的区域性属性可能与标准值不同。</span><span class="sxs-lookup"><span data-stu-id="a1639-339">The properties of a culture on a specific computer can differ from standard values.</span></span> <span data-ttu-id="a1639-340">任何时候，用户都可以自定义区分区域性的显示设置。</span><span class="sxs-lookup"><span data-stu-id="a1639-340">At any time, a user can customize culture-sensitive display settings.</span></span> <span data-ttu-id="a1639-341">因此，在系统保存的格式化数据在用户自定义区域性设置之后可能无法读取。</span><span class="sxs-lookup"><span data-stu-id="a1639-341">Because of this, formatted data that is saved on a system may not be readable after the user customizes cultural settings.</span></span> <span data-ttu-id="a1639-342">格式化数据在计算机之间移植可能会受到更多的限制。</span><span class="sxs-lookup"><span data-stu-id="a1639-342">The portability of formatted data across computers is likely to be even more limited.</span></span> 

* <span data-ttu-id="a1639-343">管理数值或日期时间格式的国际、区域或国家标准会随着时间发生更改，这些更改会合并到操作系统更新中。</span><span class="sxs-lookup"><span data-stu-id="a1639-343">International, regional, or national standards that govern the formatting of numbers or dates and times change over time, and these changes are incorporated into operating system updates.</span></span> <span data-ttu-id="a1639-344">在格式设置约定更改时，将无法读取使用以前的约定格式化的数据。</span><span class="sxs-lookup"><span data-stu-id="a1639-344">When formatting conventions change, data that was formatted by using the previous conventions may become unreadable.</span></span> 

<span data-ttu-id="a1639-345">下面的示例演示了使用区分区域性格式设置进行持久化数据导致的有限可移植性。</span><span class="sxs-lookup"><span data-stu-id="a1639-345">The following example illustrates the limited portability that results from using culture-sensitive formatting to persist data.</span></span> <span data-ttu-id="a1639-346">该示例将日期和时间数组值保存到文件中。</span><span class="sxs-lookup"><span data-stu-id="a1639-346">The example saves an array of date and time values to a file.</span></span> <span data-ttu-id="a1639-347">这些数据通过使用英语（美国）区域性约定进行格式化。</span><span class="sxs-lookup"><span data-stu-id="a1639-347">These are formatted by using the conventions of the English (United States) culture.</span></span> <span data-ttu-id="a1639-348">在应用程序将当前线程区域性更改为法语（瑞士）后，它尝试使用当前区域性的格式设置约定来读取保存的值。</span><span class="sxs-lookup"><span data-stu-id="a1639-348">After the application changes the current thread culture to French (Switzerland), it tries to read the saved values by using the formatting conventions of the current culture.</span></span> <span data-ttu-id="a1639-349">尝试读取两个数据条目时引发 [FormatException](xref:System.FormatException) 异常，现在日期数组包含相当于 [MinValue](xref:System.DateTime.MinValue) 的两个错误元素。</span><span class="sxs-lookup"><span data-stu-id="a1639-349">The attempt to read two of the data items throws a [FormatException](xref:System.FormatException) exception, and the array of dates now contains two incorrect elements that are equal to [MinValue](xref:System.DateTime.MinValue).</span></span> 

```csharp
using System;
using System.Globalization;
using System.IO;
using System.Text;
using System.Threading;

public class Example
{
   private static string filename = @".\dates.dat";

   public static void Main()
   {
      DateTime[] dates = { new DateTime(1758, 5, 6, 21, 26, 0), 
                           new DateTime(1818, 5, 5, 7, 19, 0), 
                           new DateTime(1870, 4, 22, 23, 54, 0),  
                           new DateTime(1890, 9, 8, 6, 47, 0), 
                           new DateTime(1905, 2, 18, 15, 12, 0) }; 
      // Write the data to a file using the current culture.
      WriteData(dates);
      // Change the current culture.
      Thread.CurrentThread.CurrentCulture = CultureInfo.CreateSpecificCulture("fr-CH");
      // Read the data using the current culture.
      DateTime[] newDates = ReadData();
      foreach (var newDate in newDates)
         Console.WriteLine(newDate.ToString("g"));
   }

   private static void WriteData(DateTime[] dates) 
   {
      StreamWriter sw = new StreamWriter(filename, false, Encoding.UTF8);    
      for (int ctr = 0; ctr < dates.Length; ctr++) {
         sw.Write("{0}", dates[ctr].ToString("g", CultureInfo.CurrentCulture));
         if (ctr < dates.Length - 1) sw.Write("|");   
      }      
      sw.Close();
   }

   private static DateTime[] ReadData() 
   {
      bool exceptionOccurred = false;

      // Read file contents as a single string, then split it.
      StreamReader sr = new StreamReader(filename, Encoding.UTF8);
      string output = sr.ReadToEnd();
      sr.Close();   

      string[] values = output.Split( new char[] { '|' } );
      DateTime[] newDates = new DateTime[values.Length]; 
      for (int ctr = 0; ctr < values.Length; ctr++) {
         try {
            newDates[ctr] = DateTime.Parse(values[ctr], CultureInfo.CurrentCulture);
         }
         catch (FormatException) {
            Console.WriteLine("Failed to parse {0}", values[ctr]);
            exceptionOccurred = true;
         }
      }      
      if (exceptionOccurred) Console.WriteLine();
      return newDates;
   }
}
// The example displays the following output:
//       Failed to parse 4/22/1870 11:54 PM
//       Failed to parse 2/18/1905 3:12 PM
//       
//       05.06.1758 21:26
//       05.05.1818 07:19
//       01.01.0001 00:00
//       09.08.1890 06:47
//       01.01.0001 00:00
//       01.01.0001 00:00
```

```vb
Imports System.Globalization
Imports System.IO
Imports System.Text
Imports System.Threading

Module Example
   Private filename As String = ".\dates.dat"

   Public Sub Main()
      Dim dates() As Date = { #5/6/1758 9:26PM#, #5/5/1818 7:19AM#, _ 
                              #4/22/1870 11:54PM#, #9/8/1890 6:47AM#, _ 
                              #2/18/1905 3:12PM# }
      ' Write the data to a file using the current culture.
      WriteData(dates)
      ' Change the current culture.
      Thread.CurrentThread.CurrentCulture = CultureInfo.CreateSpecificCulture("fr-CH")
      ' Read the data using the current culture.
      Dim newDates() As Date = ReadData()
      For Each newDate In newDates
         Console.WriteLine(newDate.ToString("g"))
      Next
   End Sub

   Private Sub WriteData(dates() As Date)
      Dim sw As New StreamWriter(filename, False, Encoding.Utf8)    
      For ctr As Integer = 0 To dates.Length - 1
         sw.Write("{0}", dates(ctr).ToString("g", CultureInfo.CurrentCulture))
         If ctr < dates.Length - 1 Then sw.Write("|")   
      Next      
      sw.Close()
   End Sub

   Private Function ReadData() As Date()
      Dim exceptionOccurred As Boolean = False

      ' Read file contents as a single string, then split it.
      Dim sr As New StreamReader(filename, Encoding.Utf8)
      Dim output As String = sr.ReadToEnd()
      sr.Close()   

      Dim values() As String = output.Split( {"|"c } )
      Dim newDates(values.Length - 1) As Date 
      For ctr As Integer = 0 To values.Length - 1
         Try
            newDates(ctr) = DateTime.Parse(values(ctr), CultureInfo.CurrentCulture)
         Catch e As FormatException
            Console.WriteLine("Failed to parse {0}", values(ctr))
            exceptionOccurred = True
         End Try
      Next      
      If exceptionOccurred Then Console.WriteLine()
      Return newDates
   End Function
End Module
' The example displays the following output:
'       Failed to parse 4/22/1870 11:54 PM
'       Failed to parse 2/18/1905 3:12 PM
'       
'       05.06.1758 21:26
'       05.05.1818 07:19
'       01.01.0001 00:00
'       09.08.1890 06:47
'       01.01.0001 00:00
'       01.01.0001 00:00
'
```

<span data-ttu-id="a1639-350">然而，如果在 [DateTime.ToString(String, IFormatProvider)](xref:System.DateTime.ToString(System.String,System.IFormatProvider)) 和 [DateTime.Parse(String, IFormatProvider)](xref:System.DateTime.Parse(System.String,System.IFormatProvider)) 调用中使用 [CultureInfo.InvariantCulture](xref:System.Globalization.CultureInfo.InvariantCulture) 替换 [CultureInfo.CurrentCulture](xref:System.Globalization.CultureInfo.CurrentCulture) 属性，则持久化的日期时间数据会成功恢复，如下方输出所示。</span><span class="sxs-lookup"><span data-stu-id="a1639-350">However, if you replace the [CultureInfo.CurrentCulture](xref:System.Globalization.CultureInfo.CurrentCulture) property with [CultureInfo.InvariantCulture](xref:System.Globalization.CultureInfo.InvariantCulture) in the calls to [DateTime.ToString(String, IFormatProvider)](xref:System.DateTime.ToString(System.String,System.IFormatProvider)) and [DateTime.Parse(String, IFormatProvider)](xref:System.DateTime.Parse(System.String,System.IFormatProvider)), the persisted date and time data is successfully restored, as the following output shows.</span></span>

```
// 06.05.1758 21:26
// 05.05.1818 07:19
// 22.04.1870 23:54
// 08.09.1890 06:47
// 18.02.1905 15:12
```

## <a name="see-also"></a><span data-ttu-id="a1639-351">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a1639-351">See also</span></span>

[<span data-ttu-id="a1639-352">操作字符串</span><span class="sxs-lookup"><span data-stu-id="a1639-352">Manipulating strings</span></span>](manipulating-strings.md)

