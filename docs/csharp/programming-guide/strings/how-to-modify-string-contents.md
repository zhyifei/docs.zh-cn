---
title: "如何：修改字符串内容（C# 编程指南）"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords: strings [C#], modifying
ms.assetid: b6c20bba-ce22-43d7-ad1b-5ce65f714055
caps.latest.revision: "16"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: b0810d5722c2c32f7884187bb2e3fc5a039825c9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-modify-string-contents-c-programming-guide"></a><span data-ttu-id="d9678-102">如何：修改字符串内容（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="d9678-102">How to: Modify String Contents (C# Programming Guide)</span></span>
<span data-ttu-id="d9678-103">由于字符串是不可变的，因此创建字符串对象后，（在不使用不安全代码的情况下）便不能再修改其值。</span><span class="sxs-lookup"><span data-stu-id="d9678-103">Because strings are *immutable*, it is not possible (without using unsafe code) to modify the value of a string object after it has been created.</span></span> <span data-ttu-id="d9678-104">但是，可通过多种方法修改字符串的值并将结果存储到新的字符串对象。</span><span class="sxs-lookup"><span data-stu-id="d9678-104">However, there are many ways to modify the value of a string and store the result in a new string object.</span></span> <span data-ttu-id="d9678-105"><xref:System.String?displayProperty=nameWithType> 类提供作用于输入字符串并返回新字符串对象的方法。</span><span class="sxs-lookup"><span data-stu-id="d9678-105">The <xref:System.String?displayProperty=nameWithType> class provides methods that operate on an input string and return a new string object.</span></span> <span data-ttu-id="d9678-106">在很多情况下，可以将新对象赋予保留原始字符串的变量。</span><span class="sxs-lookup"><span data-stu-id="d9678-106">In many cases, you can assign the new object to the variable that held the original string.</span></span> <span data-ttu-id="d9678-107"><xref:System.Text.RegularExpressions.Regex?displayProperty=nameWithType> 类提供其他一些以类似方式工作的方法。</span><span class="sxs-lookup"><span data-stu-id="d9678-107">The <xref:System.Text.RegularExpressions.Regex?displayProperty=nameWithType> class provides additional methods that work in a similar manner.</span></span> <span data-ttu-id="d9678-108"><xref:System.Text.StringBuilder?displayProperty=nameWithType> 类提供一个可“就地”修改的字符缓冲区。</span><span class="sxs-lookup"><span data-stu-id="d9678-108">The <xref:System.Text.StringBuilder?displayProperty=nameWithType> class provides a character buffer that you can modify "in-place."</span></span> <span data-ttu-id="d9678-109">调用 <xref:System.Text.StringBuilder.ToString%2A?displayProperty=nameWithType> 方法可创建包含该缓冲区的当前内容的新字符串对象。</span><span class="sxs-lookup"><span data-stu-id="d9678-109">You call the <xref:System.Text.StringBuilder.ToString%2A?displayProperty=nameWithType> method to create a new string object that contains the current contents of the buffer.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d9678-110">示例</span><span class="sxs-lookup"><span data-stu-id="d9678-110">Example</span></span>  
 <span data-ttu-id="d9678-111">以下示例演示替换或删除指定字符串中的子字符串的各种方法。</span><span class="sxs-lookup"><span data-stu-id="d9678-111">The following example shows various ways to replace or remove substrings in a specified string.</span></span>  
  
 [!code-csharp[csProgGuideStrings#28](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-modify-string-contents_1.cs)]  
  
## <a name="example"></a><span data-ttu-id="d9678-112">示例</span><span class="sxs-lookup"><span data-stu-id="d9678-112">Example</span></span>  
 <span data-ttu-id="d9678-113">若要使用数组表示法访问字符串中的各个字符，可以使用 <xref:System.Text.StringBuilder> 对象，该对象重载 `[]` 运算符，提供对其内部字符缓冲区的访问。</span><span class="sxs-lookup"><span data-stu-id="d9678-113">To access the individual characters in a string by using array notation, you can use the <xref:System.Text.StringBuilder> object, which overloads the `[]` operator to provide access to its internal character buffer.</span></span> <span data-ttu-id="d9678-114">也可以使用 <xref:System.String.ToCharArray%2A> 方法将该字符串转换为字符数组。</span><span class="sxs-lookup"><span data-stu-id="d9678-114">You can also convert the string to an array of chars by using the <xref:System.String.ToCharArray%2A> method.</span></span> <span data-ttu-id="d9678-115">以下示例使用 `ToCharArray` 创建该数组。</span><span class="sxs-lookup"><span data-stu-id="d9678-115">The following example uses `ToCharArray` to create the array.</span></span> <span data-ttu-id="d9678-116">然后修改此数组中的某些元素。</span><span class="sxs-lookup"><span data-stu-id="d9678-116">Some elements of this array are then modified.</span></span> <span data-ttu-id="d9678-117">之后再调用采用字符数组作为输入参数的字符串构造函数，创建新字符串。</span><span class="sxs-lookup"><span data-stu-id="d9678-117">A string constructor that takes a char array as an input parameter is then called to create a new string.</span></span>  
  
 [!code-csharp[csProgGuideStrings#24](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-modify-string-contents_2.cs)]  
  
## <a name="example"></a><span data-ttu-id="d9678-118">示例</span><span class="sxs-lookup"><span data-stu-id="d9678-118">Example</span></span>  
 <span data-ttu-id="d9678-119">以下示例针对的是某些非常罕见的情况，在这些情况下，建议使用不安全代码以类似于 C 样式字符数组的方式就地修改字符串。</span><span class="sxs-lookup"><span data-stu-id="d9678-119">The following example is provided for those very rare situations in which you may want to modify a string in-place by using unsafe code in a manner similar to C-style char arrays.</span></span> <span data-ttu-id="d9678-120">此示例演示如何使用 fixed 关键字“就地”访问各个字符。</span><span class="sxs-lookup"><span data-stu-id="d9678-120">The example shows how to access the individual characters "in-place" by using the fixed keyword.</span></span> <span data-ttu-id="d9678-121">此外还演示对字符串进行不安全操作可能产生的一个副作用，此副作用是由于 C# 编译器在内部存储（暂存）字符串的方式而导致的。</span><span class="sxs-lookup"><span data-stu-id="d9678-121">It also demonstrates one possible side effect of unsafe operations on strings that results from the way that the C# compiler stores (interns) strings internally.</span></span> <span data-ttu-id="d9678-122">通常，除非绝对必要，否则不应使用这种方法。</span><span class="sxs-lookup"><span data-stu-id="d9678-122">In general, you should not use this technique unless it is absolutely necessary.</span></span>  
  
 [!code-csharp[csProgGuideStrings#29](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-modify-string-contents_3.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="d9678-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d9678-123">See Also</span></span>  
 [<span data-ttu-id="d9678-124">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="d9678-124">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="d9678-125">字符串</span><span class="sxs-lookup"><span data-stu-id="d9678-125">Strings</span></span>](../../../csharp/programming-guide/strings/index.md)
