---
title: "如何：将字符串转换为数字（C# 编程指南）"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- conversions [C#]
- conversions [C#], string to int
- converting strings to int [C#]
- strings [C#], converting to int
ms.assetid: 467b9979-86ee-4afd-b734-30299cda91e3
caps.latest.revision: "34"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 3dc67bc2f25bba14df0e3ce6859bb8bc9094871c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-convert-a-string-to-a-number-c-programming-guide"></a><span data-ttu-id="d9574-102">如何：将字符串转换为数字（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="d9574-102">How to: Convert a String to a Number (C# Programming Guide)</span></span>
<span data-ttu-id="d9574-103">可以使用 <xref:System.Convert> 类中的方法或使用各种数值类型（int、long、float 等）中的 `TryParse` 方法将[字符串](../../../csharp/language-reference/keywords/string.md)转换为数字。</span><span class="sxs-lookup"><span data-stu-id="d9574-103">You can convert a [string](../../../csharp/language-reference/keywords/string.md) to a number by using methods in the <xref:System.Convert> class or by using the `TryParse` method found on the various numeric types (int, long, float, etc.).</span></span>  
  
 <span data-ttu-id="d9574-104">如果你具有字符串，则调用 `TryParse` 方法（例如 `int.TryParse("11")`）会稍微更加高效且简单。</span><span class="sxs-lookup"><span data-stu-id="d9574-104">If you have a string, it is slightly more efficient and straightforward to call a `TryParse` method (for example, `int.TryParse("11")`).</span></span>  <span data-ttu-id="d9574-105">使用 `Convert` 方法对于实现 <xref:System.IConvertible> 的常规对象更有用。</span><span class="sxs-lookup"><span data-stu-id="d9574-105">Using a `Convert` method is more useful for general objects that implement <xref:System.IConvertible>.</span></span>  
  
 <span data-ttu-id="d9574-106">可以对预期字符串会包含的数值类型（如 <xref:System.Int32?displayProperty=nameWithType> 类型）使用 `Parse` 或 `TryParse` 方法。</span><span class="sxs-lookup"><span data-stu-id="d9574-106">You can use `Parse` or `TryParse` methods on the numeric type you expect the string contains, such as the <xref:System.Int32?displayProperty=nameWithType> type.</span></span>  <span data-ttu-id="d9574-107"><xref:System.Convert.ToUInt32%2A?displayProperty=nameWithType> 方法在内部使用 <xref:System.Int32.Parse%2A>。</span><span class="sxs-lookup"><span data-stu-id="d9574-107">The <xref:System.Convert.ToUInt32%2A?displayProperty=nameWithType> method uses <xref:System.Int32.Parse%2A> internally.</span></span>  <span data-ttu-id="d9574-108">如果字符串的格式无效，则 `Parse` 会引发异常，而 `TryParse` 会返回 [false](../../../csharp/language-reference/keywords/false.md)。</span><span class="sxs-lookup"><span data-stu-id="d9574-108">If the string is not in a valid format, `Parse` throws an exception whereas `TryParse` returns [false](../../../csharp/language-reference/keywords/false.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d9574-109">示例</span><span class="sxs-lookup"><span data-stu-id="d9574-109">Example</span></span>  
 <span data-ttu-id="d9574-110">`Parse` 和 `TryParse` 方法会忽略字符串开头和末尾的空格，但所有其他字符必须是组成合适数值类型（int、long、ulong、float、decimal 等）的字符。</span><span class="sxs-lookup"><span data-stu-id="d9574-110">The `Parse` and `TryParse` methods ignore whitespace at the beginning and at the end of the string, but all other characters must be characters that form the appropriate numeric type (int, long, ulong, float, decimal, etc.).</span></span>  <span data-ttu-id="d9574-111">组成数字的字符中的任何空格都会导致错误。</span><span class="sxs-lookup"><span data-stu-id="d9574-111">Any whitespace within the characters that form the number cause an error.</span></span>  <span data-ttu-id="d9574-112">例如，可以使用 `decimal.TryParse` 分析“10”、“10.3”、“  10  ”，但不能使用此方法分析从“10X”、“1 0”（注意空格）、“10 .3”（注意空格）、“10e1”（`float.TryParse` 在此处适用）等中分析出 10。</span><span class="sxs-lookup"><span data-stu-id="d9574-112">For example, you can use `decimal.TryParse` to parse "10", "10.3", "  10  ", but you cannot use this method to parse 10 from "10X", "1 0" (note space), "10 .3" (note space), "10e1" (`float.TryParse` works here), and so on.</span></span>  
  
 <span data-ttu-id="d9574-113">下面的示例演示了对 `Parse` 和 `TryParse` 的成功调用和不成功的调用。</span><span class="sxs-lookup"><span data-stu-id="d9574-113">The examples below demonstrate both successful and unsuccessful calls to `Parse` and `TryParse`.</span></span>  
  
 [!code-csharp[csProgGuideTypes#5555](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-string-to-a-number_1.cs)]  
[!code-csharp[csProgGuideTypes#25](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-string-to-a-number_2.cs)]  
[!code-csharp[csProgGuideTypes#26](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-string-to-a-number_3.cs)]  
[!code-csharp[csProgGuideTypes#27](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-string-to-a-number_4.cs)]  
[!code-csharp[csProgGuideTypes#28](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-string-to-a-number_5.cs)]  
[!code-csharp[csProgGuideTypes#100](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-string-to-a-number_6.cs)]  
  
## <a name="example"></a><span data-ttu-id="d9574-114">示例</span><span class="sxs-lookup"><span data-stu-id="d9574-114">Example</span></span>  
 <span data-ttu-id="d9574-115">下表列出了 <xref:System.Convert> 类中可使用的一些方法。</span><span class="sxs-lookup"><span data-stu-id="d9574-115">The following table lists some of the methods from the <xref:System.Convert> class that you can use.</span></span>  
  
|<span data-ttu-id="d9574-116">数值类型</span><span class="sxs-lookup"><span data-stu-id="d9574-116">Numeric Type</span></span>|<span data-ttu-id="d9574-117">方法</span><span class="sxs-lookup"><span data-stu-id="d9574-117">Method</span></span>|  
|------------------|------------|  
|`decimal`|<xref:System.Convert.ToDecimal%28System.String%29>|  
|`float`|<xref:System.Convert.ToSingle%28System.String%29>|  
|`double`|<xref:System.Convert.ToDouble%28System.String%29>|  
|`short`|<xref:System.Convert.ToInt16%28System.String%29>|  
|`int`|<xref:System.Convert.ToInt32%28System.String%29>|  
|`long`|<xref:System.Convert.ToInt64%28System.String%29>|  
|`ushort`|<xref:System.Convert.ToUInt16%28System.String%29>|  
|`uint`|<xref:System.Convert.ToUInt32%28System.String%29>|  
|`ulong`|<xref:System.Convert.ToUInt64%28System.String%29>|  
  
 <span data-ttu-id="d9574-118">此示例调用 <xref:System.Convert.ToInt32%28System.String%29?displayProperty=nameWithType> 方法将输入的 [string](../../../csharp/language-reference/keywords/string.md) 转换为 [int](../../../csharp/language-reference/keywords/int.md)。</span><span class="sxs-lookup"><span data-stu-id="d9574-118">This example calls the <xref:System.Convert.ToInt32%28System.String%29?displayProperty=nameWithType> method to convert an input [string](../../../csharp/language-reference/keywords/string.md) to an [int](../../../csharp/language-reference/keywords/int.md) .</span></span> <span data-ttu-id="d9574-119">代码将捕获此方法可能引发的最常见的两个异常：<xref:System.FormatException> 和 <xref:System.OverflowException>。</span><span class="sxs-lookup"><span data-stu-id="d9574-119">The code catches the two most common exceptions that can be thrown by this method, <xref:System.FormatException> and <xref:System.OverflowException>.</span></span> <span data-ttu-id="d9574-120">如果该数字可以递增而不溢出整数存储位置，则程序使结果加上 1 并打印输出。</span><span class="sxs-lookup"><span data-stu-id="d9574-120">If the number can be incremented without overflowing the integer storage location, the program adds 1 to the result and prints the output.</span></span>  
  
 [!code-csharp[csProgGuideTypes#5555](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-string-to-a-number_1.cs)]  
[!code-csharp[csProgGuideTypes#24](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-string-to-a-number_7.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="d9574-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d9574-121">See Also</span></span>  
 [<span data-ttu-id="d9574-122">类型</span><span class="sxs-lookup"><span data-stu-id="d9574-122">Types</span></span>](../../../csharp/programming-guide/types/index.md)  
 [<span data-ttu-id="d9574-123">如何：确定字符串是否表示数值</span><span class="sxs-lookup"><span data-stu-id="d9574-123">How to: Determine Whether a String Represents a Numeric Value</span></span>](../../../csharp/programming-guide/strings/how-to-determine-whether-a-string-represents-a-numeric-value.md)  
 [<span data-ttu-id="d9574-124">.NET Framework 4 格式设置实用工具</span><span class="sxs-lookup"><span data-stu-id="d9574-124">.NET Framework 4 Formatting Utility</span></span>](http://code.msdn.microsoft.com/NET-Framework-4-Formatting-9c4dae8d)
