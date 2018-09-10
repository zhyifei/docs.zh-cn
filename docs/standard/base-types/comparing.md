---
title: 比较 .NET 中的字符串
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- value comparisons of strings
- LastIndexOf method
- CompareTo method
- IndexOf method
- Compare method
- strings [.NET Framework], comparing
- CompareOrdinal method
- EndsWith method
- Equals method
- StartsWith method
ms.assetid: 977dc094-fe19-4955-98ec-d2294d04a4ba
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b1fa907be4571e0a5f95ab798210bedb154e9170
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2018
ms.locfileid: "44264670"
---
# <a name="comparing-strings-in-net"></a><span data-ttu-id="3cd01-102">比较 .NET 中的字符串</span><span class="sxs-lookup"><span data-stu-id="3cd01-102">Comparing Strings in .NET</span></span>
<span data-ttu-id="3cd01-103">.NET 提供几种方法来比较字符串的值。</span><span class="sxs-lookup"><span data-stu-id="3cd01-103">.NET provides several methods to compare the values of strings.</span></span> <span data-ttu-id="3cd01-104">下表列出和描述值比较方法。</span><span class="sxs-lookup"><span data-stu-id="3cd01-104">The following table lists and describes the value-comparison methods.</span></span>  
  
|<span data-ttu-id="3cd01-105">方法名称</span><span class="sxs-lookup"><span data-stu-id="3cd01-105">Method name</span></span>|<span data-ttu-id="3cd01-106">使用</span><span class="sxs-lookup"><span data-stu-id="3cd01-106">Use</span></span>|  
|-----------------|---------|  
|<xref:System.String.Compare%2A?displayProperty=nameWithType>|<span data-ttu-id="3cd01-107">比较两个字符串的值。</span><span class="sxs-lookup"><span data-stu-id="3cd01-107">Compares the values of two strings.</span></span> <span data-ttu-id="3cd01-108">返回一个整数值。</span><span class="sxs-lookup"><span data-stu-id="3cd01-108">Returns an integer value.</span></span>|  
|<xref:System.String.CompareOrdinal%2A?displayProperty=nameWithType>|<span data-ttu-id="3cd01-109">比较两个字符串的值而不考虑本地区域性。</span><span class="sxs-lookup"><span data-stu-id="3cd01-109">Compares two strings without regard to local culture.</span></span> <span data-ttu-id="3cd01-110">返回一个整数值。</span><span class="sxs-lookup"><span data-stu-id="3cd01-110">Returns an integer value.</span></span>|  
|<xref:System.String.CompareTo%2A?displayProperty=nameWithType>|<span data-ttu-id="3cd01-111">比较当前字符串对象和另一个字符串。</span><span class="sxs-lookup"><span data-stu-id="3cd01-111">Compares the current string object to another string.</span></span> <span data-ttu-id="3cd01-112">返回一个整数值。</span><span class="sxs-lookup"><span data-stu-id="3cd01-112">Returns an integer value.</span></span>|  
|<xref:System.String.StartsWith%2A?displayProperty=nameWithType>|<span data-ttu-id="3cd01-113">确定字符串是否以传递字的符串开头。</span><span class="sxs-lookup"><span data-stu-id="3cd01-113">Determines whether a string begins with the string passed.</span></span> <span data-ttu-id="3cd01-114">返回一个布尔值。</span><span class="sxs-lookup"><span data-stu-id="3cd01-114">Returns a Boolean value.</span></span>|  
|<xref:System.String.EndsWith%2A?displayProperty=nameWithType>|<span data-ttu-id="3cd01-115">确定字符串是否以传递的字符串结尾。</span><span class="sxs-lookup"><span data-stu-id="3cd01-115">Determines whether a string ends with the string passed.</span></span> <span data-ttu-id="3cd01-116">返回一个布尔值。</span><span class="sxs-lookup"><span data-stu-id="3cd01-116">Returns a Boolean value.</span></span>|  
|<xref:System.String.Equals%2A?displayProperty=nameWithType>|<span data-ttu-id="3cd01-117">确定两个字符串是否相同。</span><span class="sxs-lookup"><span data-stu-id="3cd01-117">Determines whether two strings are the same.</span></span> <span data-ttu-id="3cd01-118">返回一个布尔值。</span><span class="sxs-lookup"><span data-stu-id="3cd01-118">Returns a Boolean value.</span></span>|  
|<xref:System.String.IndexOf%2A?displayProperty=nameWithType>|<span data-ttu-id="3cd01-119">返回字符或字符串的索引位置，从正在检查的字符串的开头开始。</span><span class="sxs-lookup"><span data-stu-id="3cd01-119">Returns the index position of a character or string, starting from the beginning of the string you are examining.</span></span> <span data-ttu-id="3cd01-120">返回一个整数值。</span><span class="sxs-lookup"><span data-stu-id="3cd01-120">Returns an integer value.</span></span>|  
|<xref:System.String.LastIndexOf%2A?displayProperty=nameWithType>|<span data-ttu-id="3cd01-121">返回字符或字符串的索引位置，从正在检查的字符串的结尾开始。</span><span class="sxs-lookup"><span data-stu-id="3cd01-121">Returns the index position of a character or string, starting from the end of the string you are examining.</span></span> <span data-ttu-id="3cd01-122">返回一个整数值。</span><span class="sxs-lookup"><span data-stu-id="3cd01-122">Returns an integer value.</span></span>|  
  
## <a name="compare"></a><span data-ttu-id="3cd01-123">比较</span><span class="sxs-lookup"><span data-stu-id="3cd01-123">Compare</span></span>  
 <span data-ttu-id="3cd01-124">静态 <xref:System.String.Compare%2A?displayProperty=nameWithType> 方法可以全面比较两个字符串。</span><span class="sxs-lookup"><span data-stu-id="3cd01-124">The static <xref:System.String.Compare%2A?displayProperty=nameWithType> method provides a thorough way of comparing two strings.</span></span> <span data-ttu-id="3cd01-125">此方法区分区域性。</span><span class="sxs-lookup"><span data-stu-id="3cd01-125">This method is culturally aware.</span></span> <span data-ttu-id="3cd01-126">你可以使用此函数比较两个字符串或两个字符串的子字符串。</span><span class="sxs-lookup"><span data-stu-id="3cd01-126">You can use this function to compare two strings or substrings of two strings.</span></span> <span data-ttu-id="3cd01-127">此外，还提供考虑或忽略大小写和区域性差别的重载。</span><span class="sxs-lookup"><span data-stu-id="3cd01-127">Additionally, overloads are provided that regard or disregard case and cultural variance.</span></span> <span data-ttu-id="3cd01-128">下表显示此方法可能返回三个整数值。</span><span class="sxs-lookup"><span data-stu-id="3cd01-128">The following table shows the three integer values that this method might return.</span></span>  
  
|<span data-ttu-id="3cd01-129">返回值</span><span class="sxs-lookup"><span data-stu-id="3cd01-129">Return value</span></span>|<span data-ttu-id="3cd01-130">条件</span><span class="sxs-lookup"><span data-stu-id="3cd01-130">Condition</span></span>|  
|------------------|---------------|  
|<span data-ttu-id="3cd01-131">负整数</span><span class="sxs-lookup"><span data-stu-id="3cd01-131">A negative integer</span></span>|<span data-ttu-id="3cd01-132">在排序顺序中，第一个字符串在第二个字符串之前。</span><span class="sxs-lookup"><span data-stu-id="3cd01-132">The first string precedes the second string in the sort order.</span></span><br /><br /> <span data-ttu-id="3cd01-133">或</span><span class="sxs-lookup"><span data-stu-id="3cd01-133">-or-</span></span><br /><br /> <span data-ttu-id="3cd01-134">第一个字符串是 `null`。</span><span class="sxs-lookup"><span data-stu-id="3cd01-134">The first string is `null`.</span></span>|  
|<span data-ttu-id="3cd01-135">0</span><span class="sxs-lookup"><span data-stu-id="3cd01-135">0</span></span>|<span data-ttu-id="3cd01-136">第一个字符串和第二个字符串相等。</span><span class="sxs-lookup"><span data-stu-id="3cd01-136">The first string and the second string are equal.</span></span><br /><br /> <span data-ttu-id="3cd01-137">或</span><span class="sxs-lookup"><span data-stu-id="3cd01-137">-or-</span></span><br /><br /> <span data-ttu-id="3cd01-138">两个字符串都是 `null`。</span><span class="sxs-lookup"><span data-stu-id="3cd01-138">Both strings are `null`.</span></span>|  
|<span data-ttu-id="3cd01-139">正整数</span><span class="sxs-lookup"><span data-stu-id="3cd01-139">A positive integer</span></span><br /><br /> <span data-ttu-id="3cd01-140">或</span><span class="sxs-lookup"><span data-stu-id="3cd01-140">-or-</span></span><br /><br /> <span data-ttu-id="3cd01-141">1</span><span class="sxs-lookup"><span data-stu-id="3cd01-141">1</span></span>|<span data-ttu-id="3cd01-142">在排序顺序中，第一个字符串在第二个字符串之后。</span><span class="sxs-lookup"><span data-stu-id="3cd01-142">The first string follows the second string in the sort order.</span></span><br /><br /> <span data-ttu-id="3cd01-143">或</span><span class="sxs-lookup"><span data-stu-id="3cd01-143">-or-</span></span><br /><br /> <span data-ttu-id="3cd01-144">第二个字符串是 `null`。</span><span class="sxs-lookup"><span data-stu-id="3cd01-144">The second string is `null`.</span></span>|  
  
> [!IMPORTANT]
>  <span data-ttu-id="3cd01-145"><xref:System.String.Compare%2A?displayProperty=nameWithType> 方法主要用于对字符串进行排序。</span><span class="sxs-lookup"><span data-stu-id="3cd01-145">The <xref:System.String.Compare%2A?displayProperty=nameWithType> method is primarily intended for use when ordering or sorting strings.</span></span> <span data-ttu-id="3cd01-146">不应使用 <xref:System.String.Compare%2A?displayProperty=nameWithType> 方法来测试相等性（即，显式查找返回值 0 而不考虑一个字符串是否小于或大于另一个）。</span><span class="sxs-lookup"><span data-stu-id="3cd01-146">You should not use the <xref:System.String.Compare%2A?displayProperty=nameWithType> method to test for equality (that is, to explicitly look for a return value of 0 with no regard for whether one string is less than or greater than the other).</span></span> <span data-ttu-id="3cd01-147">相反，若要确定两个字符串是否相等，请使用 <xref:System.String.Equals%28System.String%2CSystem.String%2CSystem.StringComparison%29?displayProperty=nameWithType> 方法。</span><span class="sxs-lookup"><span data-stu-id="3cd01-147">Instead, to determine whether two strings are equal, use the <xref:System.String.Equals%28System.String%2CSystem.String%2CSystem.StringComparison%29?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="3cd01-148">下面的示例使用 <xref:System.String.Compare%2A?displayProperty=nameWithType> 方法来确定两个字符串的相对值。</span><span class="sxs-lookup"><span data-stu-id="3cd01-148">The following example uses the <xref:System.String.Compare%2A?displayProperty=nameWithType> method to determine the relative values of two strings.</span></span>  
  
 [!code-cpp[Conceptual.String.BasicOps#6](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/compare.cpp#6)]
 [!code-csharp[Conceptual.String.BasicOps#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/compare.cs#6)]
 [!code-vb[Conceptual.String.BasicOps#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/compare.vb#6)]  
  
 <span data-ttu-id="3cd01-149">此示例向控制台显示 `-1` 。</span><span class="sxs-lookup"><span data-stu-id="3cd01-149">This example displays `-1` to the console.</span></span>  
  
 <span data-ttu-id="3cd01-150">前面的示例默认区分区域性。</span><span class="sxs-lookup"><span data-stu-id="3cd01-150">The preceding example is culture-sensitive by default.</span></span> <span data-ttu-id="3cd01-151">若要执行非区域性敏感型字符串比较，请使用 <xref:System.String.Compare%2A?displayProperty=nameWithType> 方法重载，这样就可以提供区域性参数，指定要使用的区域性。</span><span class="sxs-lookup"><span data-stu-id="3cd01-151">To perform a culture-insensitive string comparison, use an overload of the <xref:System.String.Compare%2A?displayProperty=nameWithType> method that allows you to specify the culture to use by supplying a *culture* parameter.</span></span> <span data-ttu-id="3cd01-152">有关展示了如何使用 <xref:System.String.Compare%2A?displayProperty=nameWithType> 方法执行非区域性敏感型比较的示例，请参阅[执行非区域性敏感型字符串比较](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-comparisons.md)。</span><span class="sxs-lookup"><span data-stu-id="3cd01-152">For an example that demonstrates how to use the <xref:System.String.Compare%2A?displayProperty=nameWithType> method to perform a culture-insensitive comparison, see [Performing Culture-Insensitive String Comparisons](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-comparisons.md).</span></span>  
  
## <a name="compareordinal"></a><span data-ttu-id="3cd01-153">CompareOrdinal</span><span class="sxs-lookup"><span data-stu-id="3cd01-153">CompareOrdinal</span></span>  
 <span data-ttu-id="3cd01-154"><xref:System.String.CompareOrdinal%2A?displayProperty=nameWithType> 方法比较两个字符串对象而不考虑本地区域性。</span><span class="sxs-lookup"><span data-stu-id="3cd01-154">The <xref:System.String.CompareOrdinal%2A?displayProperty=nameWithType> method compares two string objects without considering the local culture.</span></span> <span data-ttu-id="3cd01-155">此方法的返回值与上表中 **Compare** 方法返回的值相等。</span><span class="sxs-lookup"><span data-stu-id="3cd01-155">The return values of this method are identical to the values returned by the **Compare** method in the previous table.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="3cd01-156"><xref:System.String.CompareOrdinal%2A?displayProperty=nameWithType> 方法主要用于对字符串进行排序。</span><span class="sxs-lookup"><span data-stu-id="3cd01-156">The <xref:System.String.CompareOrdinal%2A?displayProperty=nameWithType> method is primarily intended for use when ordering or sorting strings.</span></span> <span data-ttu-id="3cd01-157">不应使用 <xref:System.String.CompareOrdinal%2A?displayProperty=nameWithType> 方法来测试相等性（即，显式查找返回值 0 而不考虑一个字符串是否小于或大于另一个）。</span><span class="sxs-lookup"><span data-stu-id="3cd01-157">You should not use the <xref:System.String.CompareOrdinal%2A?displayProperty=nameWithType> method to test for equality (that is, to explicitly look for a return value of 0 with no regard for whether one string is less than or greater than the other).</span></span> <span data-ttu-id="3cd01-158">相反，若要确定两个字符串是否相等，请使用 <xref:System.String.Equals%28System.String%2CSystem.String%2CSystem.StringComparison%29?displayProperty=nameWithType> 方法。</span><span class="sxs-lookup"><span data-stu-id="3cd01-158">Instead, to determine whether two strings are equal, use the <xref:System.String.Equals%28System.String%2CSystem.String%2CSystem.StringComparison%29?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="3cd01-159">以下示例使用 **CompareOrdinal** 方法来比较两个字符串的值。</span><span class="sxs-lookup"><span data-stu-id="3cd01-159">The following example uses the **CompareOrdinal** method to compare the values of two strings.</span></span>  
  
 [!code-cpp[Conceptual.String.BasicOps#7](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/compare.cpp#7)]
 [!code-csharp[Conceptual.String.BasicOps#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/compare.cs#7)]
 [!code-vb[Conceptual.String.BasicOps#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/compare.vb#7)]  
  
 <span data-ttu-id="3cd01-160">此示例向控制台显示 `-32` 。</span><span class="sxs-lookup"><span data-stu-id="3cd01-160">This example displays `-32` to the console.</span></span>  
  
## <a name="compareto"></a><span data-ttu-id="3cd01-161">CompareTo</span><span class="sxs-lookup"><span data-stu-id="3cd01-161">CompareTo</span></span>  
 <span data-ttu-id="3cd01-162"><xref:System.String.CompareTo%2A?displayProperty=nameWithType> 方法比较当前字符串对象封装到另一个字符串或对象的字符串。</span><span class="sxs-lookup"><span data-stu-id="3cd01-162">The <xref:System.String.CompareTo%2A?displayProperty=nameWithType> method compares the string that the current string object encapsulates to another string or object.</span></span> <span data-ttu-id="3cd01-163">此方法的返回值与上表中 <xref:System.String.Compare%2A?displayProperty=nameWithType> 方法返回的值相同。</span><span class="sxs-lookup"><span data-stu-id="3cd01-163">The return values of this method are identical to the values returned by the <xref:System.String.Compare%2A?displayProperty=nameWithType> method in the previous table.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="3cd01-164"><xref:System.String.CompareTo%2A?displayProperty=nameWithType> 方法主要用于对字符串进行排序。</span><span class="sxs-lookup"><span data-stu-id="3cd01-164">The <xref:System.String.CompareTo%2A?displayProperty=nameWithType> method is primarily intended for use when ordering or sorting strings.</span></span> <span data-ttu-id="3cd01-165">不应使用 <xref:System.String.CompareTo%2A?displayProperty=nameWithType> 方法来测试相等性（即，显式查找返回值 0 而不考虑一个字符串是否小于或大于另一个）。</span><span class="sxs-lookup"><span data-stu-id="3cd01-165">You should not use the <xref:System.String.CompareTo%2A?displayProperty=nameWithType> method to test for equality (that is, to explicitly look for a return value of 0 with no regard for whether one string is less than or greater than the other).</span></span> <span data-ttu-id="3cd01-166">相反，若要确定两个字符串是否相等，请使用 <xref:System.String.Equals%28System.String%2CSystem.String%2CSystem.StringComparison%29?displayProperty=nameWithType> 方法。</span><span class="sxs-lookup"><span data-stu-id="3cd01-166">Instead, to determine whether two strings are equal, use the <xref:System.String.Equals%28System.String%2CSystem.String%2CSystem.StringComparison%29?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="3cd01-167">下面的示例使用 <xref:System.String.CompareTo%2A?displayProperty=nameWithType> 方法来比较 `string1` 对象和 `string2` 对象。</span><span class="sxs-lookup"><span data-stu-id="3cd01-167">The following example uses the <xref:System.String.CompareTo%2A?displayProperty=nameWithType> method to compare the `string1` object to the `string2` object.</span></span>  
  
 [!code-cpp[Conceptual.String.BasicOps#8](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/compare.cpp#8)]
 [!code-csharp[Conceptual.String.BasicOps#8](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/compare.cs#8)]
 [!code-vb[Conceptual.String.BasicOps#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/compare.vb#8)]  
  
 <span data-ttu-id="3cd01-168">此示例向控制台显示 `-1` 。</span><span class="sxs-lookup"><span data-stu-id="3cd01-168">This example displays `-1` to the console.</span></span>  
  
 <span data-ttu-id="3cd01-169"><xref:System.String.CompareTo%2A?displayProperty=nameWithType> 方法的所有重载都默认执行区分大小写的区域性敏感型比较。</span><span class="sxs-lookup"><span data-stu-id="3cd01-169">All overloads of the <xref:System.String.CompareTo%2A?displayProperty=nameWithType> method perform culture-sensitive and case-sensitive comparisons by default.</span></span> <span data-ttu-id="3cd01-170">此方法不提供任何允许执行不区分区域性的比较的重载。</span><span class="sxs-lookup"><span data-stu-id="3cd01-170">No overloads of this method are provided that allow you to perform a culture-insensitive comparison.</span></span> <span data-ttu-id="3cd01-171">为了代码清楚起见，建议改用 String.Compare 方法，同时指定 <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=nameWithType> 执行区域性敏感型操作，或指定 <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType> 执行非区域性敏感型操作。</span><span class="sxs-lookup"><span data-stu-id="3cd01-171">For code clarity, we recommend that you use the **String.Compare** method instead, specifying <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=nameWithType> for culture-sensitive operations or <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType> for culture-insensitive operations.</span></span> <span data-ttu-id="3cd01-172">有关演示如何使用 **String.Compare** 方法来执行区分和不区分区域性的比较的示例，请参阅 [执行不区分区域性的字符串比较](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-comparisons.md)。</span><span class="sxs-lookup"><span data-stu-id="3cd01-172">For examples that demonstrate how to use the **String.Compare** method to perform both culture-sensitive and culture-insensitive comparisons, see [Performing Culture-Insensitive String Comparisons](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-comparisons.md).</span></span>  
  
## <a name="equals"></a><span data-ttu-id="3cd01-173">Equals</span><span class="sxs-lookup"><span data-stu-id="3cd01-173">Equals</span></span>  
 <span data-ttu-id="3cd01-174">**String.Equals** 方法能够轻松确定两个字符串是否相等。</span><span class="sxs-lookup"><span data-stu-id="3cd01-174">The **String.Equals** method can easily determine if two strings are the same.</span></span> <span data-ttu-id="3cd01-175">这个区分大小写的方法返回 **true** 或 **false** 布尔值。</span><span class="sxs-lookup"><span data-stu-id="3cd01-175">This case-sensitive method returns a **true** or **false** Boolean value.</span></span> <span data-ttu-id="3cd01-176">它可以在现有类中使用，如下一个示例所示。</span><span class="sxs-lookup"><span data-stu-id="3cd01-176">It can be used from an existing class, as illustrated in the next example.</span></span> <span data-ttu-id="3cd01-177">以下示例使用 **Equals** 方法来确定一个字符串对象是否包含短语“Hello World”。</span><span class="sxs-lookup"><span data-stu-id="3cd01-177">The following example uses the **Equals** method to determine whether a string object contains the phrase "Hello World".</span></span>  
  
 [!code-cpp[Conceptual.String.BasicOps#9](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/compare.cpp#9)]
 [!code-csharp[Conceptual.String.BasicOps#9](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/compare.cs#9)]
 [!code-vb[Conceptual.String.BasicOps#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/compare.vb#9)]  
  
 <span data-ttu-id="3cd01-178">此示例向控制台显示 `True` 。</span><span class="sxs-lookup"><span data-stu-id="3cd01-178">This example displays `True` to the console.</span></span>  
  
 <span data-ttu-id="3cd01-179">此方法还可作为静态方法使用。</span><span class="sxs-lookup"><span data-stu-id="3cd01-179">This method can also be used as a static method.</span></span> <span data-ttu-id="3cd01-180">以下示例使用静态方法比较两个字符串对象。</span><span class="sxs-lookup"><span data-stu-id="3cd01-180">The following example compares two string objects using a static method.</span></span>  
  
 [!code-cpp[Conceptual.String.BasicOps#10](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/compare.cpp#10)]
 [!code-csharp[Conceptual.String.BasicOps#10](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/compare.cs#10)]
 [!code-vb[Conceptual.String.BasicOps#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/compare.vb#10)]  
  
 <span data-ttu-id="3cd01-181">此示例向控制台显示 `True` 。</span><span class="sxs-lookup"><span data-stu-id="3cd01-181">This example displays `True` to the console.</span></span>  
  
## <a name="startswith-and-endswith"></a><span data-ttu-id="3cd01-182">StartsWith 和 EndsWith</span><span class="sxs-lookup"><span data-stu-id="3cd01-182">StartsWith and EndsWith</span></span>  
 <span data-ttu-id="3cd01-183">可以使用 **String.StartsWith** 方法来确定一个字符串对象是否与另一个字符串以相同字符开头。</span><span class="sxs-lookup"><span data-stu-id="3cd01-183">You can use the **String.StartsWith** method to determine whether a string object begins with the same characters that encompass another string.</span></span> <span data-ttu-id="3cd01-184">如果当前字符串对象以传递的字符串开头，这个区分大小写的方法将返回 **true** ，否则返回 **false** 。</span><span class="sxs-lookup"><span data-stu-id="3cd01-184">This case-sensitive method returns **true** if the current string object begins with the passed string and **false** if it does not.</span></span> <span data-ttu-id="3cd01-185">以下示例使用此方法来确定一个字符串对象是否以“Hello”开头。</span><span class="sxs-lookup"><span data-stu-id="3cd01-185">The following example uses this method to determine if a string object begins with "Hello".</span></span>  
  
 [!code-cpp[Conceptual.String.BasicOps#11](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/compare.cpp#11)]
 [!code-csharp[Conceptual.String.BasicOps#11](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/compare.cs#11)]
 [!code-vb[Conceptual.String.BasicOps#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/compare.vb#11)]  
  
 <span data-ttu-id="3cd01-186">此示例向控制台显示 `True` 。</span><span class="sxs-lookup"><span data-stu-id="3cd01-186">This example displays `True` to the console.</span></span>  
  
 <span data-ttu-id="3cd01-187">**String.EndsWith** 方法比较传递的字符串和当前字符串对象末尾的字符。</span><span class="sxs-lookup"><span data-stu-id="3cd01-187">The **String.EndsWith** method compares a passed string to the characters that exist at the end of the current string object.</span></span> <span data-ttu-id="3cd01-188">它也返回一个布尔值。</span><span class="sxs-lookup"><span data-stu-id="3cd01-188">It also returns a Boolean value.</span></span> <span data-ttu-id="3cd01-189">以下示例使用 **EndsWith** 方法检查字符串的末尾。</span><span class="sxs-lookup"><span data-stu-id="3cd01-189">The following example checks the end of a string using the **EndsWith** method.</span></span>  
  
 [!code-cpp[Conceptual.String.BasicOps#12](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/compare.cpp#12)]
 [!code-csharp[Conceptual.String.BasicOps#12](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/compare.cs#12)]
 [!code-vb[Conceptual.String.BasicOps#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/compare.vb#12)]  
  
 <span data-ttu-id="3cd01-190">此示例向控制台显示 `False` 。</span><span class="sxs-lookup"><span data-stu-id="3cd01-190">This example displays `False` to the console.</span></span>  
  
## <a name="indexof-and-lastindexof"></a><span data-ttu-id="3cd01-191">IndexOf 和 LastIndexOf</span><span class="sxs-lookup"><span data-stu-id="3cd01-191">IndexOf and LastIndexOf</span></span>  
 <span data-ttu-id="3cd01-192">可以使用 **String.IndexOf** 方法来确定特定字符在字符串中的第一个匹配项的位置。</span><span class="sxs-lookup"><span data-stu-id="3cd01-192">You can use the **String.IndexOf** method to determine the position of the first occurrence of a particular character within a string.</span></span> <span data-ttu-id="3cd01-193">这个区分大小写的方法使用从零开始的索引从字符串的开头开始计数，并返回所传递字符的位置。</span><span class="sxs-lookup"><span data-stu-id="3cd01-193">This case-sensitive method starts counting from the beginning of a string and returns the position of a passed character using a zero-based index.</span></span> <span data-ttu-id="3cd01-194">如果无法找到该字符，则返回值 –1。</span><span class="sxs-lookup"><span data-stu-id="3cd01-194">If the character cannot be found, a value of –1 is returned.</span></span>  
  
 <span data-ttu-id="3cd01-195">以下示例使用 **IndexOf** 方法搜索字符“`l`”在字符串中的第一个匹配项。</span><span class="sxs-lookup"><span data-stu-id="3cd01-195">The following example uses the **IndexOf** method to search for the first occurrence of the '`l`' character in a string.</span></span>  
  
 [!code-cpp[Conceptual.String.BasicOps#13](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/compare.cpp#13)]
 [!code-csharp[Conceptual.String.BasicOps#13](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/compare.cs#13)]
 [!code-vb[Conceptual.String.BasicOps#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/compare.vb#13)]  
  
 <span data-ttu-id="3cd01-196">此示例向控制台显示 `2` 。</span><span class="sxs-lookup"><span data-stu-id="3cd01-196">This example displays `2` to the console.</span></span>  
  
 <span data-ttu-id="3cd01-197">**String.LastIndexOf** 方法类似于 **String.IndexOf** 方法，但它返回特定字符在字符串中的最后一个匹配项的位置。</span><span class="sxs-lookup"><span data-stu-id="3cd01-197">The **String.LastIndexOf** method is similar to the **String.IndexOf** method except that it returns the position of the last occurrence of a particular character within a string.</span></span> <span data-ttu-id="3cd01-198">它不区分大小写，并且使用从零开始的索引。</span><span class="sxs-lookup"><span data-stu-id="3cd01-198">It is case-sensitive and uses a zero-based index.</span></span>  
  
 <span data-ttu-id="3cd01-199">以下示例使用 **LastIndexOf** 方法搜索字符“`l`”在字符串中的最后一个匹配项。</span><span class="sxs-lookup"><span data-stu-id="3cd01-199">The following example uses the **LastIndexOf** method to search for the last occurrence of the '`l`' character in a string.</span></span>  
  
 [!code-cpp[Conceptual.String.BasicOps#14](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/compare.cpp#14)]
 [!code-csharp[Conceptual.String.BasicOps#14](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/compare.cs#14)]
 [!code-vb[Conceptual.String.BasicOps#14](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/compare.vb#14)]  
  
 <span data-ttu-id="3cd01-200">此示例向控制台显示 `9` 。</span><span class="sxs-lookup"><span data-stu-id="3cd01-200">This example displays `9` to the console.</span></span>  
  
 <span data-ttu-id="3cd01-201">与 **String.Remove** 方法结合使用时，这两种方法都很有用。</span><span class="sxs-lookup"><span data-stu-id="3cd01-201">Both methods are useful when used in conjunction with the **String.Remove** method.</span></span> <span data-ttu-id="3cd01-202">可以使用 **IndexOf** 或 **LastIndexOf** 方法来检索字符的位置，然后将该位置提供给 **Remove** 方法，以删除字符或以该字符开头的单词。</span><span class="sxs-lookup"><span data-stu-id="3cd01-202">You can use either the **IndexOf** or **LastIndexOf** methods to retrieve the position of a character, and then supply that position to the **Remove** method in order to remove a character or a word that begins with that character.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3cd01-203">请参阅</span><span class="sxs-lookup"><span data-stu-id="3cd01-203">See also</span></span>

- [<span data-ttu-id="3cd01-204">基本字符串操作</span><span class="sxs-lookup"><span data-stu-id="3cd01-204">Basic String Operations</span></span>](../../../docs/standard/base-types/basic-string-operations.md)  
- [<span data-ttu-id="3cd01-205">执行不区分区域性的字符串操作</span><span class="sxs-lookup"><span data-stu-id="3cd01-205">Performing Culture-Insensitive String Operations</span></span>](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations.md)
- [<span data-ttu-id="3cd01-206">排序权重表</span><span class="sxs-lookup"><span data-stu-id="3cd01-206">Sorting Weight Tables</span></span>](https://www.microsoft.com/en-us/download/details.aspx?id=10921)
