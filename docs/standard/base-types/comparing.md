---
title: "比较字符串"
description: "比较字符串"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 07/26/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 920ee5e8-3d61-4941-b5af-fc50eaee427c
ms.translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: 47ee37886fa2662a89730e9d52ee04987e37da2f
ms.contentlocale: zh-cn
ms.lasthandoff: 03/02/2017

---

# <a name="comparing-strings"></a><span data-ttu-id="b2424-104">比较字符串</span><span class="sxs-lookup"><span data-stu-id="b2424-104">Comparing strings</span></span>

<span data-ttu-id="b2424-105">.NET 提供几种方法来比较字符串的值。</span><span class="sxs-lookup"><span data-stu-id="b2424-105">.NET provides several methods to compare the values of strings.</span></span> <span data-ttu-id="b2424-106">下表列出和描述值比较方法。</span><span class="sxs-lookup"><span data-stu-id="b2424-106">The following table lists and describes the value-comparison methods.</span></span>

<span data-ttu-id="b2424-107">方法名称</span><span class="sxs-lookup"><span data-stu-id="b2424-107">Method name</span></span> | <span data-ttu-id="b2424-108">使用</span><span class="sxs-lookup"><span data-stu-id="b2424-108">Use</span></span>
----------- | ---
<span data-ttu-id="b2424-109">[String.Compare](xref:System.String.Compare(System.String,System.Int32,System.String,System.Int32,System.Int32))</span><span class="sxs-lookup"><span data-stu-id="b2424-109">[String.Compare](xref:System.String.Compare(System.String,System.Int32,System.String,System.Int32,System.Int32))</span></span> | <span data-ttu-id="b2424-110">比较两个字符串的值。</span><span class="sxs-lookup"><span data-stu-id="b2424-110">Compares the values of two strings.</span></span> <span data-ttu-id="b2424-111">返回一个整数值。</span><span class="sxs-lookup"><span data-stu-id="b2424-111">Returns an integer value.</span></span>
<span data-ttu-id="b2424-112">[String.CompareOrdinal](xref:System.String.CompareOrdinal(System.String,System.Int32,System.String,System.Int32,System.Int32))</span><span class="sxs-lookup"><span data-stu-id="b2424-112">[String.CompareOrdinal](xref:System.String.CompareOrdinal(System.String,System.Int32,System.String,System.Int32,System.Int32))</span></span> | <span data-ttu-id="b2424-113">比较两个字符串的值而不考虑本地区域性。</span><span class="sxs-lookup"><span data-stu-id="b2424-113">Compares two strings without regard to local culture.</span></span> <span data-ttu-id="b2424-114">返回一个整数值。</span><span class="sxs-lookup"><span data-stu-id="b2424-114">Returns an integer value.</span></span>
<span data-ttu-id="b2424-115">[String.CompareTo](xref:System.String.CompareTo(System.String))</span><span class="sxs-lookup"><span data-stu-id="b2424-115">[String.CompareTo](xref:System.String.CompareTo(System.String))</span></span> | <span data-ttu-id="b2424-116">比较当前字符串对象和另一个字符串。</span><span class="sxs-lookup"><span data-stu-id="b2424-116">Compares the current string object to another string.</span></span> <span data-ttu-id="b2424-117">返回一个整数值。</span><span class="sxs-lookup"><span data-stu-id="b2424-117">Returns an integer value.</span></span>
<span data-ttu-id="b2424-118">[String.StartsWith](xref:System.String.StartsWith(System.String))</span><span class="sxs-lookup"><span data-stu-id="b2424-118">[String.StartsWith](xref:System.String.StartsWith(System.String))</span></span> | <span data-ttu-id="b2424-119">确定字符串是否以传递字的符串开头。</span><span class="sxs-lookup"><span data-stu-id="b2424-119">Determines whether a string begins with the string passed.</span></span> <span data-ttu-id="b2424-120">返回一个布尔值。</span><span class="sxs-lookup"><span data-stu-id="b2424-120">Returns a Boolean value.</span></span>
<span data-ttu-id="b2424-121">[String.EndsWith](xref:System.String.CompareTo(System.String))</span><span class="sxs-lookup"><span data-stu-id="b2424-121">[String.EndsWith](xref:System.String.CompareTo(System.String))</span></span> | <span data-ttu-id="b2424-122">确定字符串是否以传递的字符串结尾。</span><span class="sxs-lookup"><span data-stu-id="b2424-122">Determines whether a string ends with the string passed.</span></span> <span data-ttu-id="b2424-123">返回一个布尔值。</span><span class="sxs-lookup"><span data-stu-id="b2424-123">Returns a Boolean value.</span></span>
<span data-ttu-id="b2424-124">[String.Equals](xref:System.String.CompareTo(System.String))</span><span class="sxs-lookup"><span data-stu-id="b2424-124">[String.Equals](xref:System.String.CompareTo(System.String))</span></span> | <span data-ttu-id="b2424-125">确定两个字符串是否相同。</span><span class="sxs-lookup"><span data-stu-id="b2424-125">Determines whether two strings are the same.</span></span> <span data-ttu-id="b2424-126">返回一个布尔值。</span><span class="sxs-lookup"><span data-stu-id="b2424-126">Returns a Boolean value.</span></span>
<span data-ttu-id="b2424-127">[String.IndexOf](xref:System.String.IndexOf(System.Char))</span><span class="sxs-lookup"><span data-stu-id="b2424-127">[String.IndexOf](xref:System.String.IndexOf(System.Char))</span></span> | <span data-ttu-id="b2424-128">返回字符或字符串的索引位置，从正在检查的字符串的开头开始。</span><span class="sxs-lookup"><span data-stu-id="b2424-128">Returns the index position of a character or string, starting from the beginning of the string you are examining.</span></span> <span data-ttu-id="b2424-129">返回一个整数值。</span><span class="sxs-lookup"><span data-stu-id="b2424-129">Returns an integer value.</span></span>
<span data-ttu-id="b2424-130">[String.LastIndexOf](xref:System.String.LastIndexOf(System.Char))</span><span class="sxs-lookup"><span data-stu-id="b2424-130">[String.LastIndexOf](xref:System.String.LastIndexOf(System.Char))</span></span> | <span data-ttu-id="b2424-131">返回字符或字符串的索引位置，从正在检查的字符串的结尾开始。</span><span class="sxs-lookup"><span data-stu-id="b2424-131">Returns the index position of a character or string, starting from the end of the string you are examining.</span></span> <span data-ttu-id="b2424-132">返回一个整数值。</span><span class="sxs-lookup"><span data-stu-id="b2424-132">Returns an integer value.</span></span>

## <a name="compare"></a><span data-ttu-id="b2424-133">比较</span><span class="sxs-lookup"><span data-stu-id="b2424-133">Compare</span></span>

<span data-ttu-id="b2424-134">静态 [String.Compare](xref:System.String.Compare(System.String,System.Int32,System.String,System.Int32,System.Int32)) 方法可以全面比较两个字符串。</span><span class="sxs-lookup"><span data-stu-id="b2424-134">The static [String.Compare](xref:System.String.Compare(System.String,System.Int32,System.String,System.Int32,System.Int32)) method provides a thorough way of comparing two strings.</span></span> <span data-ttu-id="b2424-135">此方法区分区域性。</span><span class="sxs-lookup"><span data-stu-id="b2424-135">This method is culturally aware.</span></span> <span data-ttu-id="b2424-136">你可以使用此函数比较两个字符串或两个字符串的子字符串。</span><span class="sxs-lookup"><span data-stu-id="b2424-136">You can use this function to compare two strings or substrings of two strings.</span></span> <span data-ttu-id="b2424-137">此外，还提供考虑或忽略大小写和区域性差别的重载。</span><span class="sxs-lookup"><span data-stu-id="b2424-137">Additionally, overloads are provided that regard or disregard case and cultural variance.</span></span> <span data-ttu-id="b2424-138">下表显示此方法可能返回三个整数值。</span><span class="sxs-lookup"><span data-stu-id="b2424-138">The following table shows the three integer values that this method might return.</span></span> 

<span data-ttu-id="b2424-139">返回值</span><span class="sxs-lookup"><span data-stu-id="b2424-139">Return value</span></span> | <span data-ttu-id="b2424-140">条件</span><span class="sxs-lookup"><span data-stu-id="b2424-140">Condition</span></span>
------------ | ---------
<span data-ttu-id="b2424-141">负整数</span><span class="sxs-lookup"><span data-stu-id="b2424-141">A negative integer</span></span> | <span data-ttu-id="b2424-142">在排序顺序中，第一个字符串在第二个字符串之前，或者第一个字符串为 `null`。</span><span class="sxs-lookup"><span data-stu-id="b2424-142">The first string precedes the second string in the sort order, or the first string is `null`.</span></span>
<span data-ttu-id="b2424-143">0</span><span class="sxs-lookup"><span data-stu-id="b2424-143">0</span></span> | <span data-ttu-id="b2424-144">第一个字符串和第二个字符串相等，或者两个字符串均为 `null`。</span><span class="sxs-lookup"><span data-stu-id="b2424-144">The first string and the second string are equal, or both strings are `null`.</span></span>
<span data-ttu-id="b2424-145">正整数或 1</span><span class="sxs-lookup"><span data-stu-id="b2424-145">A positive integer, or 1</span></span> | <span data-ttu-id="b2424-146">在排序顺序中，第一个字符串在第二个字符串之后，或者第二个字符串为 null。</span><span class="sxs-lookup"><span data-stu-id="b2424-146">The first string follows the second string in the sort order, or the second string is null.</span></span>
 
> [!IMPORTANT]
> <span data-ttu-id="b2424-147">[String.Compare](xref:System.String.Compare(System.String,System.Int32,System.String,System.Int32,System.Int32)) 方法主要用于对字符串进行排序。</span><span class="sxs-lookup"><span data-stu-id="b2424-147">The [String.Compare](xref:System.String.Compare(System.String,System.Int32,System.String,System.Int32,System.Int32)) method is primarily intended for use when ordering or sorting strings.</span></span> <span data-ttu-id="b2424-148">不应使用 [String.Compare](xref:System.String.Compare(System.String,System.Int32,System.String,System.Int32,System.Int32)) 方法来测试相等性（即，显式查找返回值 0 而不考虑一个字符串是否小于或大于另一个）。</span><span class="sxs-lookup"><span data-stu-id="b2424-148">You should not use the [String.Compare](xref:System.String.Compare(System.String,System.Int32,System.String,System.Int32,System.Int32)) method to test for equality (that is, to explicitly look for a return value of 0 with no regard for whether one string is less than or greater than the other).</span></span> <span data-ttu-id="b2424-149">若要确定两个字符串是否相等，请使用 [String.Equals(String, String, StringComparison)](xref:System.String.Equals(System.String,System.String,System.StringComparison)) 方法。</span><span class="sxs-lookup"><span data-stu-id="b2424-149">Instead, to determine whether two strings are equal, use the [String.Equals(String, String, StringComparison)](xref:System.String.Equals(System.String,System.String,System.StringComparison)) method.</span></span>

<span data-ttu-id="b2424-150">下面的示例使用 [String.Compare](xref:System.String.Compare(System.String,System.Int32,System.String,System.Int32,System.Int32)) 方法来确定两个字符串的相对值。</span><span class="sxs-lookup"><span data-stu-id="b2424-150">The following example uses the [String.Compare](xref:System.String.Compare(System.String,System.Int32,System.String,System.Int32,System.Int32)) method to determine the relative values of two strings.</span></span>

```csharp
string string1 = "Hello World!";
Console.WriteLine(String.Compare(string1, "Hello World?"));
```

```vb
Dim string1 As String = "Hello World!"
Console.WriteLine(String.Compare(string1, "Hello World?"))
```

<span data-ttu-id="b2424-151">此示例向控制台显示 `-1`。</span><span class="sxs-lookup"><span data-stu-id="b2424-151">This example displays `-1` to the console.</span></span>

## <a name="compareordinal"></a><span data-ttu-id="b2424-152">CompareOrdinal</span><span class="sxs-lookup"><span data-stu-id="b2424-152">CompareOrdinal</span></span>

<span data-ttu-id="b2424-153">[String.CompareOrdinal](xref:System.String.CompareOrdinal(System.String,System.Int32,System.String,System.Int32,System.Int32)) 方法比较两个字符串对象而不考虑本地区域性。</span><span class="sxs-lookup"><span data-stu-id="b2424-153">The [String.CompareOrdinal](xref:System.String.CompareOrdinal(System.String,System.Int32,System.String,System.Int32,System.Int32)) method compares two string objects without considering the local culture.</span></span> <span data-ttu-id="b2424-154">此方法的返回值与上表中 `Compare` 方法返回的值相同。</span><span class="sxs-lookup"><span data-stu-id="b2424-154">The return values of this method are identical to the values returned by the `Compare` method in the previous table.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b2424-155">[String.CompareOrdinal](xref:System.String.CompareOrdinal(System.String,System.Int32,System.String,System.Int32,System.Int32)) 方法主要用于对字符串进行排序。</span><span class="sxs-lookup"><span data-stu-id="b2424-155">The [String.CompareOrdinal](xref:System.String.CompareOrdinal(System.String,System.Int32,System.String,System.Int32,System.Int32)) method is primarily intended for use when ordering or sorting strings.</span></span> <span data-ttu-id="b2424-156">不应使用 [String.CompareOrdinal](xref:System.String.CompareOrdinal(System.String,System.Int32,System.String,System.Int32,System.Int32)) 方法来测试相等性（即，显式查找返回值 0 而不考虑一个字符串是否小于或大于另一个）。</span><span class="sxs-lookup"><span data-stu-id="b2424-156">You should not use the [String.CompareOrdinal](xref:System.String.CompareOrdinal(System.String,System.Int32,System.String,System.Int32,System.Int32)) method to test for equality (that is, to explicitly look for a return value of 0 with no regard for whether one string is less than or greater than the other).</span></span> <span data-ttu-id="b2424-157">若要确定两个字符串是否相等，请使用 [String.Equals(String, String, StringComparison)](xref:System.String.Equals(System.String,System.String,System.StringComparison)) 方法。</span><span class="sxs-lookup"><span data-stu-id="b2424-157">Instead, to determine whether two strings are equal, use the [String.Equals(String, String, StringComparison)](xref:System.String.Equals(System.String,System.String,System.StringComparison)) method.</span></span>

<span data-ttu-id="b2424-158">下面的示例使用 `CompareOrdinal` 方法来比较两个字符串的值。</span><span class="sxs-lookup"><span data-stu-id="b2424-158">The following example uses the `CompareOrdinal` method to compare the values of two strings.</span></span>

```csharp
string string1 = "Hello World!";
Console.WriteLine(String.CompareOrdinal(string1, "hello world!"));
```

```vb
Dim string1 As String = "Hello World!"
Console.WriteLine(String.CompareOrdinal(string1, "hello world!"))
```

<span data-ttu-id="b2424-159">此示例向控制台显示 `-32`。</span><span class="sxs-lookup"><span data-stu-id="b2424-159">This example displays `-32` to the console.</span></span>

## <a name="compareto"></a><span data-ttu-id="b2424-160">CompareTo</span><span class="sxs-lookup"><span data-stu-id="b2424-160">CompareTo</span></span>

<span data-ttu-id="b2424-161">[String.CompareTo](xref:System.String.CompareTo(System.String)) 方法比较当前字符串对象封装到另一个字符串或对象的字符串。</span><span class="sxs-lookup"><span data-stu-id="b2424-161">The [String.CompareTo](xref:System.String.CompareTo(System.String)) method compares the string that the current string object encapsulates to another string or object.</span></span> <span data-ttu-id="b2424-162">此方法的返回值与上表中 `String.Compare` 方法返回的值相同。</span><span class="sxs-lookup"><span data-stu-id="b2424-162">The return values of this method are identical to the values returned by the `String.Compare` method in the previous table.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b2424-163">[String.CompareTo](xref:System.String.CompareTo(System.String)) 方法主要用于对字符串进行排序。</span><span class="sxs-lookup"><span data-stu-id="b2424-163">The [String.CompareTo](xref:System.String.CompareTo(System.String)) method is primarily intended for use when ordering or sorting strings.</span></span> <span data-ttu-id="b2424-164">不应使用 [String.CompareTo](xref:System.String.CompareTo(System.String)) 方法来测试相等性（即，显式查找返回值 0 而不考虑一个字符串是否小于或大于另一个）。</span><span class="sxs-lookup"><span data-stu-id="b2424-164">You should not use the [String.CompareTo](xref:System.String.CompareTo(System.String)) method to test for equality (that is, to explicitly look for a return value of 0 with no regard for whether one string is less than or greater than the other).</span></span> <span data-ttu-id="b2424-165">若要确定两个字符串是否相等，请使用 [String.Equals(String, String, StringComparison)](xref:System.String.Equals(System.String,System.String,System.StringComparison)) 方法。</span><span class="sxs-lookup"><span data-stu-id="b2424-165">Instead, to determine whether two strings are equal, use the [String.Equals(String, String, StringComparison)](xref:System.String.Equals(System.String,System.String,System.StringComparison)) method.</span></span>

<span data-ttu-id="b2424-166">下面的示例使用 `String.CompareTo` 方法来比较 `string1` 对象和 `string2` 对象。</span><span class="sxs-lookup"><span data-stu-id="b2424-166">The following example uses the `String.CompareTo` method to compare the `string1` object to the `string2` object.</span></span>

```csharp
string string1 = "Hello World";
string string2 = "Hello World!";
int MyInt = string1.CompareTo(string2);
Console.WriteLine( MyInt );
```

```vb
Dim string1 As String = "Hello World"
Dim string2 As String = "Hello World!"
Dim MyInt As Integer = string1.CompareTo(string2)
Console.WriteLine(MyInt)
```

<span data-ttu-id="b2424-167">此示例向控制台显示 `-1`。</span><span class="sxs-lookup"><span data-stu-id="b2424-167">This example displays `-1` to the console.</span></span>

## <a name="equals"></a><span data-ttu-id="b2424-168">Equals</span><span class="sxs-lookup"><span data-stu-id="b2424-168">Equals</span></span>

<span data-ttu-id="b2424-169">[String.Equals](xref:System.String.CompareTo(System.String)) 方法能够轻松确定两个字符串是否相等。</span><span class="sxs-lookup"><span data-stu-id="b2424-169">The [String.Equals](xref:System.String.CompareTo(System.String)) method can easily determine if two strings are the same.</span></span> <span data-ttu-id="b2424-170">这个区分大小写的方法返回 `true` 或 `false` 布尔值。</span><span class="sxs-lookup"><span data-stu-id="b2424-170">This case-sensitive method returns a `true` or `false` Boolean value.</span></span> <span data-ttu-id="b2424-171">它可以在现有类中使用，如下一个示例所示。</span><span class="sxs-lookup"><span data-stu-id="b2424-171">It can be used from an existing class, as illustrated in the next example.</span></span> <span data-ttu-id="b2424-172">下面的示例使用 `Equals` 方法来确定一个字符串对象是否包含短语“Hello World”。</span><span class="sxs-lookup"><span data-stu-id="b2424-172">The following example uses the `Equals` method to determine whether a string object contains the phrase "Hello World".</span></span>

```csharp
string string1 = "Hello World";
Console.WriteLine(string1.Equals("Hello World"));
```

```vb
Dim string1 As String = "Hello World"
Console.WriteLine(string1.Equals("Hello World"))
```

<span data-ttu-id="b2424-173">此示例向控制台显示 `true`。</span><span class="sxs-lookup"><span data-stu-id="b2424-173">This example displays `true` to the console.</span></span>

<span data-ttu-id="b2424-174">此方法还可作为静态方法使用。</span><span class="sxs-lookup"><span data-stu-id="b2424-174">This method can also be used as a static method.</span></span> <span data-ttu-id="b2424-175">以下示例使用静态方法比较两个字符串对象。</span><span class="sxs-lookup"><span data-stu-id="b2424-175">The following example compares two string objects using a static method.</span></span>

```csharp
string string1 = "Hello World";
string string2 = "Hello World";
Console.WriteLine(String.Equals(string1, string2));
```

```vb
Dim string1 As String = "Hello World"
Dim string2 As String = "Hello World"
Console.WriteLine(String.Equals(string1, string2))
```

<span data-ttu-id="b2424-176">此示例向控制台显示 `true`。</span><span class="sxs-lookup"><span data-stu-id="b2424-176">This example displays `true` to the console.</span></span>

## <a name="startswith-and-endswith"></a><span data-ttu-id="b2424-177">StartsWith 和 EndsWith</span><span class="sxs-lookup"><span data-stu-id="b2424-177">StartsWith and EndsWith</span></span>

<span data-ttu-id="b2424-178">可以使用 [String.StartsWith](xref:System.String.StartsWith(System.String)) 方法来确定一个字符串对象是否与另一个字符串以相同字符开头。</span><span class="sxs-lookup"><span data-stu-id="b2424-178">You can use the [String.StartsWith](xref:System.String.StartsWith(System.String)) method to determine whether a string object begins with the same characters that encompass another string.</span></span> <span data-ttu-id="b2424-179">如果当前字符串对象以传递的字符串开头，这个区分大小写的方法将返回 `true`，否则返回 `false`。</span><span class="sxs-lookup"><span data-stu-id="b2424-179">This case-sensitive method returns `true` if the current string object begins with the passed string and `false` if it does not.</span></span> <span data-ttu-id="b2424-180">以下示例使用此方法来确定一个字符串对象是否以“Hello”开头。</span><span class="sxs-lookup"><span data-stu-id="b2424-180">The following example uses this method to determine if a string object begins with "Hello".</span></span>

```csharp
string string1 = "Hello World";
Console.WriteLine(string1.StartsWith("Hello"));
```

```vb
Dim string1 As String = "Hello World!"
Console.WriteLine(string1.StartsWith("Hello"))
```

<span data-ttu-id="b2424-181">此示例向控制台显示 `true`。</span><span class="sxs-lookup"><span data-stu-id="b2424-181">This example displays `true` to the console.</span></span>

<span data-ttu-id="b2424-182">[String.EndsWith](xref:System.String.CompareTo(System.String)) 方法比较传递的字符串和当前字符串对象末尾的字符。</span><span class="sxs-lookup"><span data-stu-id="b2424-182">The [String.EndsWith](xref:System.String.CompareTo(System.String)) method compares a passed string to the characters that exist at the end of the current string object.</span></span> <span data-ttu-id="b2424-183">它也返回一个布尔值。</span><span class="sxs-lookup"><span data-stu-id="b2424-183">It also returns a Boolean value.</span></span> <span data-ttu-id="b2424-184">下面的示例使用 `EndsWith` 方法检查字符串的末尾。</span><span class="sxs-lookup"><span data-stu-id="b2424-184">The following example checks the end of a string using the `EndsWith` method.</span></span>

```csharp
string string1 = "Hello World";
Console.WriteLine(string1.EndsWith("Hello"));
```

```vb
Dim string1 As String = "Hello World!"
Console.WriteLine(string1.EndsWith("Hello"))
```

<span data-ttu-id="b2424-185">此示例向控制台显示 `false`。</span><span class="sxs-lookup"><span data-stu-id="b2424-185">This example displays `false` to the console.</span></span>

## <a name="indexof-and-lastindexof"></a><span data-ttu-id="b2424-186">IndexOf 和 LastIndexOf</span><span class="sxs-lookup"><span data-stu-id="b2424-186">IndexOf and LastIndexOf</span></span>

<span data-ttu-id="b2424-187">可以使用 [String.IndexOf](xref:System.String.IndexOf(System.Char)) 方法来确定特定字符在字符串中的第一个匹配项的位置。</span><span class="sxs-lookup"><span data-stu-id="b2424-187">You can use the [String.IndexOf](xref:System.String.IndexOf(System.Char)) method to determine the position of the first occurrence of a particular character within a string.</span></span> <span data-ttu-id="b2424-188">这个区分大小写的方法使用从零开始的索引从字符串的开头开始计数，并返回所传递字符的位置。</span><span class="sxs-lookup"><span data-stu-id="b2424-188">This case-sensitive method starts counting from the beginning of a string and returns the position of a passed character using a zero-based index.</span></span> <span data-ttu-id="b2424-189">如果无法找到该字符，则返回值 –1。</span><span class="sxs-lookup"><span data-stu-id="b2424-189">If the character cannot be found, a value of –1 is returned.</span></span>

<span data-ttu-id="b2424-190">下面的示例使用 `IndexOf` 方法搜索字符“`l`”在字符串中的第一个匹配项。</span><span class="sxs-lookup"><span data-stu-id="b2424-190">The following example uses the `IndexOf` method to search for the first occurrence of the '`l`' character in a string.</span></span>

```csharp
string string1 = "Hello World";
Console.WriteLine(string1.IndexOf('l'));
```

```vb
Dim string1 As String = "Hello World!"
Console.WriteLine(string1.IndexOf("l"))
```

<span data-ttu-id="b2424-191">此示例向控制台显示 `2`。</span><span class="sxs-lookup"><span data-stu-id="b2424-191">This example displays `2` to the console.</span></span>

<span data-ttu-id="b2424-192">[String.LastIndexOf](xref:System.String.LastIndexOf(System.Char)) 方法类似于 `String.IndexOf` 方法，但它返回特定字符在字符串中的最后一个匹配项的位置。</span><span class="sxs-lookup"><span data-stu-id="b2424-192">The [String.LastIndexOf](xref:System.String.LastIndexOf(System.Char)) method is similar to the `String.IndexOf` method except that it returns the position of the last occurrence of a particular character within a string.</span></span> <span data-ttu-id="b2424-193">它不区分大小写，并且使用从零开始的索引。</span><span class="sxs-lookup"><span data-stu-id="b2424-193">It is case-sensitive and uses a zero-based index.</span></span> 

<span data-ttu-id="b2424-194">下面的示例使用 `LastIndexOf` 方法搜索字符“`l`”在字符串中的最后一个匹配项。</span><span class="sxs-lookup"><span data-stu-id="b2424-194">The following example uses the `LastIndexOf` method to search for the last occurrence of the '`l`' character in a string.</span></span>

```csharp
string string1 = "Hello World";
Console.WriteLine(string1.LastIndexOf('l'));
```

```vb
Dim string1 As String = "Hello World!"
Console.WriteLine(string1.LastIndexOf("l"))
```

<span data-ttu-id="b2424-195">此示例向控制台显示 `9`。</span><span class="sxs-lookup"><span data-stu-id="b2424-195">This example displays `9` to the console.</span></span>

<span data-ttu-id="b2424-196">与 [String.Remove](xref:System.String.Remove(System.Int32)) 方法结合使用时，这两种方法都很有用。</span><span class="sxs-lookup"><span data-stu-id="b2424-196">Both methods are useful when used in conjunction with the [String.Remove](xref:System.String.Remove(System.Int32)) method.</span></span> <span data-ttu-id="b2424-197">可以使用 `IndexOf` 或 `LastIndexOf` 方法来检索字符的位置，然后将该位置提供给 `Remove method` 方法，移除字符或以该字符开头的单词。</span><span class="sxs-lookup"><span data-stu-id="b2424-197">You can use either the `IndexOf` or `LastIndexOf` methods to retrieve the position of a character, and then supply that position to the `Remove method` in order to remove a character or a word that begins with that character.</span></span>

## <a name="see-also"></a><span data-ttu-id="b2424-198">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b2424-198">See Also</span></span>

[<span data-ttu-id="b2424-199">基本字符串操作</span><span class="sxs-lookup"><span data-stu-id="b2424-199">Basic string operations</span></span>](basic-string-operations.md)













