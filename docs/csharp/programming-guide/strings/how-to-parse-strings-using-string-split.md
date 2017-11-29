---
title: "如何：使用 String.Split 分析字符串（C# 编程指南）"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- splitting strings [C#]
- Split method [C#]
- strings [C#], splitting
- parse strings
ms.assetid: 729c2923-4169-41c6-9c90-ef176c1e2953
caps.latest.revision: "17"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 7b97d1d89a4c74a4c759d1ed41a0bc2476b3b07a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-parse-strings-using-stringsplit-c-programming-guide"></a><span data-ttu-id="6d02a-102">如何：使用 String.Split 分析字符串（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="6d02a-102">How to: Parse Strings Using String.Split (C# Programming Guide)</span></span>
<span data-ttu-id="6d02a-103">以下代码示例说明如何使用 <xref:System.String.Split%2A?displayProperty=nameWithType> 方法分析字符串。</span><span class="sxs-lookup"><span data-stu-id="6d02a-103">The following code example demonstrates how a string can be parsed using the <xref:System.String.Split%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="6d02a-104">作为输入， <xref:System.String.Split%2A> 采用一个指示哪些字符分隔目标字符串的兴趣子字符串的字符数组。</span><span class="sxs-lookup"><span data-stu-id="6d02a-104">As input, <xref:System.String.Split%2A> takes an array of characters that indicate which characters separate interesting sub strings of the target string.</span></span>  <span data-ttu-id="6d02a-105">函数返回子字符串数组。</span><span class="sxs-lookup"><span data-stu-id="6d02a-105">The function returns an array of the sub strings.</span></span>  
  
 <span data-ttu-id="6d02a-106">此示例使用空格、逗号、句点、冒号和制表符，所有内容均在包含这些分隔字符的数组中传递到 <xref:System.String.Split%2A>。</span><span class="sxs-lookup"><span data-stu-id="6d02a-106">This example uses spaces, commas, periods, colons, and tabs, all passed in an array containing these separating characters to <xref:System.String.Split%2A>.</span></span>  <span data-ttu-id="6d02a-107">目标字符串句子中每个单词均单独从所得字符串数组中显示。</span><span class="sxs-lookup"><span data-stu-id="6d02a-107">Each word in the target string's sentence displays separately from the resulting array of strings.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6d02a-108">示例</span><span class="sxs-lookup"><span data-stu-id="6d02a-108">Example</span></span>  
 [!code-csharp[csProgGuideStrings#16](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-parse-strings-using-string-split_1.cs)]  
  
## <a name="example"></a><span data-ttu-id="6d02a-109">示例</span><span class="sxs-lookup"><span data-stu-id="6d02a-109">Example</span></span>  
 <span data-ttu-id="6d02a-110">默认情况下，当两个分隔字符连续出现在目标字符串时 String.Split 返回空字符串。</span><span class="sxs-lookup"><span data-stu-id="6d02a-110">By default, String.Split returns empty strings when two separating characters appear contiguously in the target string.</span></span>  <span data-ttu-id="6d02a-111">你可以传递可选 StringSplitOptions.RemoveEmptyEntries 参数来排除输出中的任何空字符串。</span><span class="sxs-lookup"><span data-stu-id="6d02a-111">You can pass an optional StringSplitOptions.RemoveEmptyEntries parameter to exclude any empty strings in the output.</span></span>  
  
 <span data-ttu-id="6d02a-112">String.Split 可采用字符串数组（充当用于分析目标字符串的分隔符的字符序列，而非单个字符）。</span><span class="sxs-lookup"><span data-stu-id="6d02a-112">String.Split can take an array of strings (character sequences that act as separators for parsing the target string, instead of single characters).</span></span>  
  
```csharp  
class TestStringSplit  
{  
    static void Main()  
    {  
        string[] separatingChars = { "<<", "..." };  
  
        string text = "one<<two......three<four";  
        System.Console.WriteLine("Original text: '{0}'", text);  
  
        string[] words = text.Split(separatingChars, System.StringSplitOptions.RemoveEmptyEntries );  
        System.Console.WriteLine("{0} substrings in text:", words.Length);  
  
        foreach (string s in words)  
        {  
            System.Console.WriteLine(s);  
        }  
  
        // Keep the console window open in debug mode.  
        System.Console.WriteLine("Press any key to exit.");  
        System.Console.ReadKey();  
    }  
}  
/* Output:  
    Original text: 'one<<two......three<four'  
    3 words in text:  
    one  
    two  
    three<four  
*/  
```  
  
## <a name="see-also"></a><span data-ttu-id="6d02a-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6d02a-113">See Also</span></span>  
 [<span data-ttu-id="6d02a-114">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="6d02a-114">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="6d02a-115">字符串</span><span class="sxs-lookup"><span data-stu-id="6d02a-115">Strings</span></span>](../../../csharp/programming-guide/strings/index.md)  
 [<span data-ttu-id="6d02a-116">.NET Framework 正则表达式</span><span class="sxs-lookup"><span data-stu-id="6d02a-116">.NET Framework Regular Expressions</span></span>](https://msdn.microsoft.com/library/hs600312)
