---
title: "如何：使用正则表达式搜索字符串（C# 编程指南）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- searching strings [C#]
- strings [C#], searching with RegEx
ms.assetid: dcab2150-a4a2-4fe4-87e3-83b83b58d84a
caps.latest.revision: 19
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: fb05d1702c75be8fd224ee0f34d7d8d3fe71f207
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-search-strings-using-regular-expressions-c-programming-guide"></a><span data-ttu-id="0f21e-102">如何：使用正则表达式搜索字符串（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="0f21e-102">How to: Search Strings Using Regular Expressions (C# Programming Guide)</span></span>
<span data-ttu-id="0f21e-103"><xref:System.Text.RegularExpressions.Regex?displayProperty=fullName> 类可用于搜索字符串。</span><span class="sxs-lookup"><span data-stu-id="0f21e-103">The <xref:System.Text.RegularExpressions.Regex?displayProperty=fullName> class can be used to search strings.</span></span> <span data-ttu-id="0f21e-104">从简单搜索到充分利用正则表达式，搜索可以采用不同的复杂模式。</span><span class="sxs-lookup"><span data-stu-id="0f21e-104">These searches can range in complexity from very simple to making full use of regular expressions.</span></span> <span data-ttu-id="0f21e-105">以下是使用 <xref:System.Text.RegularExpressions.Regex> 类执行字符串搜索的两个示例。</span><span class="sxs-lookup"><span data-stu-id="0f21e-105">The following are two examples of string searching by using the <xref:System.Text.RegularExpressions.Regex> class.</span></span> <span data-ttu-id="0f21e-106">有关详细信息，请参阅 [.NET Framework 正则表达式](https://msdn.microsoft.com/library/hs600312)。</span><span class="sxs-lookup"><span data-stu-id="0f21e-106">For more information, see [.NET Framework Regular Expressions](https://msdn.microsoft.com/library/hs600312).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0f21e-107">示例</span><span class="sxs-lookup"><span data-stu-id="0f21e-107">Example</span></span>  
 <span data-ttu-id="0f21e-108">以下代码是一个控制台应用程序，用于在数组中执行不区分大小写的简单字符串搜索。</span><span class="sxs-lookup"><span data-stu-id="0f21e-108">The following code is a console application that performs a simple case-insensitive search of the strings in an array.</span></span> <span data-ttu-id="0f21e-109">静态方法 <xref:System.Text.RegularExpressions.Regex.IsMatch%2A?displayProperty=fullName> 执行已给定要搜索的字符串和包含搜索模式的字符串的搜索。</span><span class="sxs-lookup"><span data-stu-id="0f21e-109">The static method <xref:System.Text.RegularExpressions.Regex.IsMatch%2A?displayProperty=fullName> performs the search given the string to search and a string that contains the search pattern.</span></span> <span data-ttu-id="0f21e-110">在这种情况下，第三个参数将用于指示应忽略大小写。</span><span class="sxs-lookup"><span data-stu-id="0f21e-110">In this case, a third argument is used to indicate that case should be ignored.</span></span> <span data-ttu-id="0f21e-111">有关更多信息，请参见<xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName>。</span><span class="sxs-lookup"><span data-stu-id="0f21e-111">For more information, see <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName>.</span></span>  
  
 <span data-ttu-id="0f21e-112">[!code-cs[csProgGuideStrings#17](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-search-strings-using-regular-expressions_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="0f21e-112">[!code-cs[csProgGuideStrings#17](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-search-strings-using-regular-expressions_1.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="0f21e-113">示例</span><span class="sxs-lookup"><span data-stu-id="0f21e-113">Example</span></span>  
 <span data-ttu-id="0f21e-114">以下代码是一个控制台应用程序，可使用正则表达式验证数组中每个字符串的格式。</span><span class="sxs-lookup"><span data-stu-id="0f21e-114">The following code is a console application that uses regular expressions to validate the format of each string in an array.</span></span> <span data-ttu-id="0f21e-115">验证要求每个字符串采用电话号码的形式：用短划线分隔成三组数字，前两组包含 3 个数字，而第三组包含 4 个数字。</span><span class="sxs-lookup"><span data-stu-id="0f21e-115">The validation requires that each string take the form of a telephone number in which three groups of digits are separated by dashes, the first two groups contain three digits, and the third group contains four digits.</span></span> <span data-ttu-id="0f21e-116">使用正则表达式 `^\\d{3}-\\d{3}-\\d{4}$` 可以实现此操作。</span><span class="sxs-lookup"><span data-stu-id="0f21e-116">This is done by using the regular expression `^\\d{3}-\\d{3}-\\d{4}$`.</span></span> <span data-ttu-id="0f21e-117">有关更多信息，请参见[正则表达式语言 - 快速参考](http://msdn.microsoft.com/library/930653a6-95d2-4697-9d5a-52d11bb6fd4c)。</span><span class="sxs-lookup"><span data-stu-id="0f21e-117">For more information, see [Regular Expression Language - Quick Reference](http://msdn.microsoft.com/library/930653a6-95d2-4697-9d5a-52d11bb6fd4c).</span></span>  
  
 <span data-ttu-id="0f21e-118">[!code-cs[csProgGuideStrings#18](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-search-strings-using-regular-expressions_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="0f21e-118">[!code-cs[csProgGuideStrings#18](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-search-strings-using-regular-expressions_2.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f21e-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0f21e-119">See Also</span></span>  
 <span data-ttu-id="0f21e-120"><xref:System.Text.RegularExpressions.Regex?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="0f21e-120"><xref:System.Text.RegularExpressions.Regex?displayProperty=fullName></span></span>   
 <span data-ttu-id="0f21e-121">[C# 编程指南](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="0f21e-121">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="0f21e-122">[字符串](../../../csharp/programming-guide/strings/index.md) </span><span class="sxs-lookup"><span data-stu-id="0f21e-122">[Strings](../../../csharp/programming-guide/strings/index.md) </span></span>  
 <span data-ttu-id="0f21e-123">[.NET Framework 正则表达式](https://msdn.microsoft.com/library/hs600312) </span><span class="sxs-lookup"><span data-stu-id="0f21e-123">[.NET Framework Regular Expressions](https://msdn.microsoft.com/library/hs600312) </span></span>  
 [<span data-ttu-id="0f21e-124">正则表达式语言 - 快速参考</span><span class="sxs-lookup"><span data-stu-id="0f21e-124">Regular Expression Language - Quick Reference</span></span>](http://msdn.microsoft.com/library/930653a6-95d2-4697-9d5a-52d11bb6fd4c)

