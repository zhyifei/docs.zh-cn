---
title: 如何：在十六进制字符串与数值类型之间转换（C# 编程指南）
ms.date: 07/20/2015
helpviewer_keywords:
- hexadecimal strings [C#], converting to numeric type
- conversions [C#], hexidecimal strings
- strings [C#], converting hexadecimal strings
- hexadecimal strings [C#]
ms.assetid: 7115c49f-7d1d-40c3-8bd9-aae0cc1d46b6
ms.openlocfilehash: 0f7502bc0f14c85d207c313646f26c7787bd46b3
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/03/2018
ms.locfileid: "43484082"
---
# <a name="how-to-convert-between-hexadecimal-strings-and-numeric-types-c-programming-guide"></a><span data-ttu-id="2a11e-102">如何：在十六进制字符串与数值类型之间转换（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="2a11e-102">How to: Convert Between Hexadecimal Strings and Numeric Types (C# Programming Guide)</span></span>
<span data-ttu-id="2a11e-103">以下示例演示如何执行下列任务：</span><span class="sxs-lookup"><span data-stu-id="2a11e-103">These examples show you how to perform the following tasks:</span></span>  
  
-   <span data-ttu-id="2a11e-104">获取[字符串](../../../csharp/language-reference/keywords/string.md)中每个字符的十六进制值。</span><span class="sxs-lookup"><span data-stu-id="2a11e-104">Obtain the hexadecimal value of each character in a [string](../../../csharp/language-reference/keywords/string.md).</span></span>  
  
-   <span data-ttu-id="2a11e-105">获取与十六进制字符串中的每个值对应的 [char](../../../csharp/language-reference/keywords/char.md)。</span><span class="sxs-lookup"><span data-stu-id="2a11e-105">Obtain the [char](../../../csharp/language-reference/keywords/char.md) that corresponds to each value in a hexadecimal string.</span></span>  
  
-   <span data-ttu-id="2a11e-106">将十六进制 `string` 转换为 [int](../../../csharp/language-reference/keywords/int.md)。</span><span class="sxs-lookup"><span data-stu-id="2a11e-106">Convert a hexadecimal `string` to an [int](../../../csharp/language-reference/keywords/int.md).</span></span>  
  
-   <span data-ttu-id="2a11e-107">将十六进制 `string` 转换为 [float](../../../csharp/language-reference/keywords/float.md)。</span><span class="sxs-lookup"><span data-stu-id="2a11e-107">Convert a hexadecimal `string` to a [float](../../../csharp/language-reference/keywords/float.md).</span></span>  
  
-   <span data-ttu-id="2a11e-108">将[字节](../../../csharp/language-reference/keywords/byte.md)数组转换为十六进制 `string`。</span><span class="sxs-lookup"><span data-stu-id="2a11e-108">Convert a [byte](../../../csharp/language-reference/keywords/byte.md) array to a hexadecimal `string`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2a11e-109">示例</span><span class="sxs-lookup"><span data-stu-id="2a11e-109">Example</span></span>  
 <span data-ttu-id="2a11e-110">此示例输出 `string` 中每个字符的十六进制值。</span><span class="sxs-lookup"><span data-stu-id="2a11e-110">This example outputs the hexadecimal value of each character in a `string`.</span></span> <span data-ttu-id="2a11e-111">首先，将 `string` 分析为字符数组。</span><span class="sxs-lookup"><span data-stu-id="2a11e-111">First it parses the `string` to an array of characters.</span></span> <span data-ttu-id="2a11e-112">然后，对每个字符调用 <xref:System.Convert.ToInt32%28System.Char%29>获取相应的数值。</span><span class="sxs-lookup"><span data-stu-id="2a11e-112">Then it calls <xref:System.Convert.ToInt32%28System.Char%29> on each character to obtain its numeric value.</span></span> <span data-ttu-id="2a11e-113">最后，在 `string` 中将数字的格式设置为十六进制表示形式。</span><span class="sxs-lookup"><span data-stu-id="2a11e-113">Finally, it formats the number as its hexadecimal representation in a `string`.</span></span>  
  
 [!code-csharp[csProgGuideTypes#30](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-between-hexadecimal-strings-and-numeric-types_1.cs)]  
  
## <a name="example"></a><span data-ttu-id="2a11e-114">示例</span><span class="sxs-lookup"><span data-stu-id="2a11e-114">Example</span></span>  
 <span data-ttu-id="2a11e-115">此示例分析十六进制值的 `string` 并输出对应于每个十六进制值的字符。</span><span class="sxs-lookup"><span data-stu-id="2a11e-115">This example parses a `string` of hexadecimal values and outputs the character corresponding to each hexadecimal value.</span></span> <span data-ttu-id="2a11e-116">首先，调用 [Split(Char\[\])](xref:System.String.Split(System.Char[])) 方法以获取每个十六进制值作为数组中的单个 `string`。</span><span class="sxs-lookup"><span data-stu-id="2a11e-116">First it calls the [Split(Char\[\])](xref:System.String.Split(System.Char[])) method to obtain each hexadecimal value as an individual `string` in an array.</span></span> <span data-ttu-id="2a11e-117">然后，调用 <xref:System.Convert.ToInt32%28System.String%2CSystem.Int32%29>将十六进制值转换为表示为 [int](../../../csharp/language-reference/keywords/int.md) 的十进制值。示例中演示了 2 种不同方法，用于获取对应于该字符代码的字符。</span><span class="sxs-lookup"><span data-stu-id="2a11e-117">Then it calls <xref:System.Convert.ToInt32%28System.String%2CSystem.Int32%29> to convert the hexadecimal value to a decimal value represented as an [int](../../../csharp/language-reference/keywords/int.md). It shows two different ways to obtain the character corresponding to that character code.</span></span> <span data-ttu-id="2a11e-118">第 1 种方法是使用 <xref:System.Char.ConvertFromUtf32%28System.Int32%29>，它将对应于整型参数的字符作为 `string` 返回。</span><span class="sxs-lookup"><span data-stu-id="2a11e-118">The first technique uses <xref:System.Char.ConvertFromUtf32%28System.Int32%29>, which returns the character corresponding to the integer argument as a `string`.</span></span> <span data-ttu-id="2a11e-119">第 2 种方法是将 `int` 显式转换为 [char](../../../csharp/language-reference/keywords/char.md)。</span><span class="sxs-lookup"><span data-stu-id="2a11e-119">The second technique explicitly casts the `int` to a [char](../../../csharp/language-reference/keywords/char.md).</span></span>  
  
 [!code-csharp[csProgGuideTypes#31](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-between-hexadecimal-strings-and-numeric-types_2.cs)]  
  
## <a name="example"></a><span data-ttu-id="2a11e-120">示例</span><span class="sxs-lookup"><span data-stu-id="2a11e-120">Example</span></span>  
 <span data-ttu-id="2a11e-121">此示例演示了将十六进制 `string` 转换为整数的另一种方法，即调用 <xref:System.Int32.Parse%28System.String%2CSystem.Globalization.NumberStyles%29> 方法。</span><span class="sxs-lookup"><span data-stu-id="2a11e-121">This example shows another way to convert a hexadecimal `string` to an integer, by calling the <xref:System.Int32.Parse%28System.String%2CSystem.Globalization.NumberStyles%29> method.</span></span>  
  
 [!code-csharp[csProgGuideTypes#32](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-between-hexadecimal-strings-and-numeric-types_3.cs)]  
  
## <a name="example"></a><span data-ttu-id="2a11e-122">示例</span><span class="sxs-lookup"><span data-stu-id="2a11e-122">Example</span></span>  
 <span data-ttu-id="2a11e-123">下面的示例演示了如何使用 <xref:System.BitConverter?displayProperty=nameWithType> 类和 <xref:System.UInt32.Parse%2A?displayProperty=nameWithType> 方法将十六进制 `string` 转换为 [float](../../../csharp/language-reference/keywords/float.md)。</span><span class="sxs-lookup"><span data-stu-id="2a11e-123">The following example shows how to convert a hexadecimal `string` to a [float](../../../csharp/language-reference/keywords/float.md) by using the <xref:System.BitConverter?displayProperty=nameWithType> class and the <xref:System.UInt32.Parse%2A?displayProperty=nameWithType> method.</span></span>  
  
 [!code-csharp[csProgGuideTypes#39](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-between-hexadecimal-strings-and-numeric-types_4.cs)]  
  
## <a name="example"></a><span data-ttu-id="2a11e-124">示例</span><span class="sxs-lookup"><span data-stu-id="2a11e-124">Example</span></span>  
 <span data-ttu-id="2a11e-125">下面的示例演示了如何使用 <xref:System.BitConverter?displayProperty=nameWithType> 类将[字节](../../../csharp/language-reference/keywords/byte.md)数组转换为十六进制字符串。</span><span class="sxs-lookup"><span data-stu-id="2a11e-125">The following example shows how to convert a [byte](../../../csharp/language-reference/keywords/byte.md) array to a hexadecimal string by using the <xref:System.BitConverter?displayProperty=nameWithType> class.</span></span>  
  
 [!code-csharp[csProgGuideTypes#38](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-between-hexadecimal-strings-and-numeric-types_5.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="2a11e-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="2a11e-126">See Also</span></span>  
 [<span data-ttu-id="2a11e-127">标准数字格式字符串</span><span class="sxs-lookup"><span data-stu-id="2a11e-127">Standard Numeric Format Strings</span></span>](../../../standard/base-types/standard-numeric-format-strings.md)  
 [<span data-ttu-id="2a11e-128">类型</span><span class="sxs-lookup"><span data-stu-id="2a11e-128">Types</span></span>](../../../csharp/programming-guide/types/index.md)  
 [<span data-ttu-id="2a11e-129">如何：确定字符串是否表示数值</span><span class="sxs-lookup"><span data-stu-id="2a11e-129">How to: Determine Whether a String Represents a Numeric Value</span></span>](../../../csharp/programming-guide/strings/how-to-determine-whether-a-string-represents-a-numeric-value.md)
