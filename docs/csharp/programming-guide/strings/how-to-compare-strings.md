---
title: "如何：比较字符串（C# 编程指南）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- strings [C#], comparison
- comparing strings [C#]
ms.assetid: e1268e28-ee98-4695-98e9-92280f1c33c0
caps.latest.revision: 23
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 494b9ef1a1e6c8958dd3df2edb44debf32690eeb
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-compare-strings-c-programming-guide"></a><span data-ttu-id="4704d-102">如何：比较字符串（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="4704d-102">How to: Compare Strings (C# Programming Guide)</span></span>
<span data-ttu-id="4704d-103">比较字符串时，产生的结果会是一个字符串大于或小于另一个字符串，或者两个字符串相等。</span><span class="sxs-lookup"><span data-stu-id="4704d-103">When you compare strings, you are producing a result that says one string is greater than or less than the other, or that the two strings are equal.</span></span> <span data-ttu-id="4704d-104">根据执行的是序号比较还是区分区域性比较，确定结果时依据的规则会有所不同。</span><span class="sxs-lookup"><span data-stu-id="4704d-104">The rules by which the result is determined are different depending on whether you are performing *ordinal comparison* or *culture-sensitive comparison*.</span></span> <span data-ttu-id="4704d-105">请务必对特定任务使用正确的比较类型。</span><span class="sxs-lookup"><span data-stu-id="4704d-105">It is important to use the correct kind of comparison for the specific task.</span></span>  
  
 <span data-ttu-id="4704d-106">需要对两个字符串的值进行比较或排序而不需要考虑语言惯例时，请使用基本的序号比较。</span><span class="sxs-lookup"><span data-stu-id="4704d-106">Use basic ordinal comparisons when you have to compare or sort the values of two strings without regard to linguistic conventions.</span></span> <span data-ttu-id="4704d-107">基本的序号比较 (`System.StringComparison.Ordinal`) 区分大小写，这意味着两个字符串的字符必须完全匹配：“and”不等于“And”或“AND”。</span><span class="sxs-lookup"><span data-stu-id="4704d-107">A basic ordinal comparison (`System.StringComparison.Ordinal`) is case-sensitive, which means that the two strings must match character for character: "and" does not equal "And" or "AND".</span></span> <span data-ttu-id="4704d-108">常用的变量有 `System.StringComparison.OrdinalIgnoreCase`，其可匹配“and”、“And”和“AND”。</span><span class="sxs-lookup"><span data-stu-id="4704d-108">A frequently-used variation is `System.StringComparison.OrdinalIgnoreCase`, which will match "and", "And", and "AND".</span></span> <span data-ttu-id="4704d-109">`StringComparison.OrdinalIgnoreCase` 常用于比较文件名、路径名和网络路径，以及其值不随用户计算机的区域设置的更改而变化的任何其他字符串。</span><span class="sxs-lookup"><span data-stu-id="4704d-109">`StringComparison.OrdinalIgnoreCase` is often used to compare file names, path names, network paths, and any other string whose value does not change based on the locale of the user's computer.</span></span> <span data-ttu-id="4704d-110">有关详细信息，请参阅<xref:System.StringComparison?displayProperty=fullName>。</span><span class="sxs-lookup"><span data-stu-id="4704d-110">For more information, see <xref:System.StringComparison?displayProperty=fullName>.</span></span>  
  
 <span data-ttu-id="4704d-111">区分区域性比较通常用于对最终用户输入的字符串进行比较和排序，因为这些字符串的字符和排序约定可能因用户计算机的区域设置而异。</span><span class="sxs-lookup"><span data-stu-id="4704d-111">Culture-sensitive comparisons are typically used to compare and sort strings that are input by end users, because the characters and sorting conventions of these strings might vary depending on the locale of the user's computer.</span></span> <span data-ttu-id="4704d-112">即使是包含相同字符的字符串，也可能因当前线程的区域性而具有不同的排序。</span><span class="sxs-lookup"><span data-stu-id="4704d-112">Even strings that contain identical characters might sort differently depending on the culture of the current thread.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4704d-113">比较字符串时，使用的方法应显式指定要执行的比较类型。</span><span class="sxs-lookup"><span data-stu-id="4704d-113">When you compare strings, you should use the methods that explicitly specify what kind of comparison you intend to perform.</span></span> <span data-ttu-id="4704d-114">这可增强代码的可维护性和可读性。</span><span class="sxs-lookup"><span data-stu-id="4704d-114">This makes your code much more maintainable and readable.</span></span> <span data-ttu-id="4704d-115">应尽可能使用具有 <xref:System.StringComparison> 枚举参数的 <xref:System.String?displayProperty=fullName> 和 <xref:System.Array?displayProperty=fullName> 类的方法重载，以便可以指定要执行的比较类型。</span><span class="sxs-lookup"><span data-stu-id="4704d-115">Whenever possible, use the overloads of the methods of the <xref:System.String?displayProperty=fullName> and <xref:System.Array?displayProperty=fullName> classes that take a <xref:System.StringComparison> enumeration parameter, so that you can specify which type of comparison to perform.</span></span> <span data-ttu-id="4704d-116">比较字符串时，最好避免使用 `==` 和 `!=` 运算符。</span><span class="sxs-lookup"><span data-stu-id="4704d-116">It is best to avoid using the `==` and `!=` operators when you compare strings.</span></span> <span data-ttu-id="4704d-117">此外，还应避免使用 <xref:System.String.CompareTo%2A?displayProperty=fullName> 实例方法，因为这些重载没有 <xref:System.StringComparison>。</span><span class="sxs-lookup"><span data-stu-id="4704d-117">Also, avoid using the <xref:System.String.CompareTo%2A?displayProperty=fullName> instance methods because none of the overloads takes a <xref:System.StringComparison>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4704d-118">示例</span><span class="sxs-lookup"><span data-stu-id="4704d-118">Example</span></span>  
 <span data-ttu-id="4704d-119">下例演示了如何正确比较其值不随用户计算机的区域设置的改变而变化的字符串。</span><span class="sxs-lookup"><span data-stu-id="4704d-119">The following example shows how to correctly compare strings whose values will not change based on the locale of the user's computer.</span></span> <span data-ttu-id="4704d-120">此外，此示例还演示了 C# 中的字符串集中功能。</span><span class="sxs-lookup"><span data-stu-id="4704d-120">In addition, it also demonstrates the *string interning* feature of C#.</span></span> <span data-ttu-id="4704d-121">如果程序声明了 2 个或多个相同的字符串变量，则编译器会将其存储在同一位置。</span><span class="sxs-lookup"><span data-stu-id="4704d-121">When a program declares two or more identical string variables, the compiler stores them all in the same location.</span></span> <span data-ttu-id="4704d-122">通过调用 <xref:System.Object.ReferenceEquals%2A> 方法，可以看到这两个字符串实际上引用的是内存中的同一对象。</span><span class="sxs-lookup"><span data-stu-id="4704d-122">By calling the <xref:System.Object.ReferenceEquals%2A> method, you can see that the two strings actually refer to the same object in memory.</span></span> <span data-ttu-id="4704d-123">使用 <xref:System.String.Copy%2A?displayProperty=fullName> 方法可避免集中，如下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="4704d-123">Use the <xref:System.String.Copy%2A?displayProperty=fullName> method to avoid interning, as shown in the example.</span></span>  
  
 <span data-ttu-id="4704d-124">[!code-cs[csProgGuideStrings#11](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-compare-strings_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="4704d-124">[!code-cs[csProgGuideStrings#11](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-compare-strings_1.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="4704d-125">示例</span><span class="sxs-lookup"><span data-stu-id="4704d-125">Example</span></span>  
 <span data-ttu-id="4704d-126">下面的示例演示了如何通过首选方式比较字符串，该首选方式使用具有 <xref:System.StringComparison> 枚举的 <xref:System.String?displayProperty=fullName> 方法。</span><span class="sxs-lookup"><span data-stu-id="4704d-126">The following example shows how to compare strings the preferred way by using the <xref:System.String?displayProperty=fullName> methods that take a <xref:System.StringComparison> enumeration.</span></span> <span data-ttu-id="4704d-127">请注意，此处没有使用 <xref:System.String.CompareTo%2A?displayProperty=fullName> 实例方法，因为这些重载没有 <xref:System.StringComparison>。</span><span class="sxs-lookup"><span data-stu-id="4704d-127">Note that the <xref:System.String.CompareTo%2A?displayProperty=fullName> instance methods are not used here, because none of the overloads takes a <xref:System.StringComparison>.</span></span>  
  
 <span data-ttu-id="4704d-128">[!code-cs[csProgGuideStrings#31](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-compare-strings_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="4704d-128">[!code-cs[csProgGuideStrings#31](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-compare-strings_2.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="4704d-129">示例</span><span class="sxs-lookup"><span data-stu-id="4704d-129">Example</span></span>  
 <span data-ttu-id="4704d-130">下面的示例演示了如何使用具有 <xref:System.StringComparer?displayProperty=fullName> 参数的静态 <xref:System.Array> 方法以区分区域性的方式对数组中的字符串进行排序和搜索。</span><span class="sxs-lookup"><span data-stu-id="4704d-130">The following example shows how to sort and search for strings in an array in a culture-sensitive manner by using the static <xref:System.Array> methods that take a <xref:System.StringComparer?displayProperty=fullName> parameter.</span></span>  
  
 <span data-ttu-id="4704d-131">[!code-cs[csProgGuideStrings#32](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-compare-strings_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="4704d-131">[!code-cs[csProgGuideStrings#32](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-compare-strings_3.cs)]</span></span>  
  
 <span data-ttu-id="4704d-132">元素或键的类型为 `string` 时，<xref:System.Collections.Hashtable?displayProperty=fullName>、<xref:System.Collections.Generic.Dictionary%602?displayProperty=fullName> 和 <xref:System.Collections.Generic.List%601?displayProperty=fullName> 等集合类的构造函数具有 <xref:System.StringComparer?displayProperty=fullName> 参数。</span><span class="sxs-lookup"><span data-stu-id="4704d-132">Collection classes such as <xref:System.Collections.Hashtable?displayProperty=fullName>, <xref:System.Collections.Generic.Dictionary%602?displayProperty=fullName>, and <xref:System.Collections.Generic.List%601?displayProperty=fullName> have constructors that take a <xref:System.StringComparer?displayProperty=fullName> parameter when the type of the elements or keys is `string`.</span></span> <span data-ttu-id="4704d-133">通常，应尽可能使用这些构造函数，并指定 `Ordinal` 或 `OrdinalIgnoreCase`。</span><span class="sxs-lookup"><span data-stu-id="4704d-133">In general, you should use these constructors whenever possible, and specify either `Ordinal` or `OrdinalIgnoreCase`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4704d-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4704d-134">See Also</span></span>  
 <span data-ttu-id="4704d-135"><xref:System.Globalization.CultureInfo?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="4704d-135"><xref:System.Globalization.CultureInfo?displayProperty=fullName></span></span>   
 <span data-ttu-id="4704d-136"><xref:System.StringComparer?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="4704d-136"><xref:System.StringComparer?displayProperty=fullName></span></span>   
 <span data-ttu-id="4704d-137">[字符串](../../../csharp/programming-guide/strings/index.md) </span><span class="sxs-lookup"><span data-stu-id="4704d-137">[Strings](../../../csharp/programming-guide/strings/index.md) </span></span>  
 <span data-ttu-id="4704d-138">[比较字符串](../../../standard/base-types/comparing.md) </span><span class="sxs-lookup"><span data-stu-id="4704d-138">[Comparing Strings](../../../standard/base-types/comparing.md) </span></span>  
 [<span data-ttu-id="4704d-139">对应用程序进行全球化和本地化</span><span class="sxs-lookup"><span data-stu-id="4704d-139">Globalizing and Localizing Applications</span></span>](/visualstudio/ide/globalizing-and-localizing-applications)

