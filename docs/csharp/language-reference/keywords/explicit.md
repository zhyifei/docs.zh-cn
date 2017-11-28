---
title: "explicit（C# 参考）"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- explicit_CSharpKeyword
- explicit
helpviewer_keywords: explicit keyword [C#]
ms.assetid: cfb8f42a-e411-4db2-af9b-796b05644846
caps.latest.revision: "21"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 2661f46d79b13808bfb169bfbfffc1a17b866b2b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="explicit-c-reference"></a><span data-ttu-id="75251-102">explicit（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="75251-102">explicit (C# Reference)</span></span>
<span data-ttu-id="75251-103">`explicit` 关键字声明必须通过转换来调用的用户定义的类型转换运算符。</span><span class="sxs-lookup"><span data-stu-id="75251-103">The `explicit` keyword declares a user-defined type conversion operator that must be invoked with a cast.</span></span> <span data-ttu-id="75251-104">例如，此运算符将名为华氏度的类转换为名为摄氏度的类：</span><span class="sxs-lookup"><span data-stu-id="75251-104">For example, this operator converts from a class called Fahrenheit to a class called Celsius:</span></span>  
  
 [!code-csharp[csrefKeywordsConversion#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/explicit_1.cs)]  
  
 <span data-ttu-id="75251-105">可用如下方式调用此转换运算符：</span><span class="sxs-lookup"><span data-stu-id="75251-105">This conversion operator can be invoked like this:</span></span>  
  
 [!code-csharp[csrefKeywordsConversion#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/explicit_2.cs)]  
  
 <span data-ttu-id="75251-106">此转换运算符从源类型转换为目标类型。</span><span class="sxs-lookup"><span data-stu-id="75251-106">The conversion operator converts from a source type to a target type.</span></span> <span data-ttu-id="75251-107">源类型提供转换运算符。</span><span class="sxs-lookup"><span data-stu-id="75251-107">The source type provides the conversion operator.</span></span> <span data-ttu-id="75251-108">不同于隐式转换，显式转换运算符必须通过转换的方式来调用。</span><span class="sxs-lookup"><span data-stu-id="75251-108">Unlike implicit conversion, explicit conversion operators must be invoked by means of a cast.</span></span> <span data-ttu-id="75251-109">如果转换操作会导致异常或丢失信息，则应将其标记为 `explicit`。</span><span class="sxs-lookup"><span data-stu-id="75251-109">If a conversion operation can cause exceptions or lose information, you should mark it `explicit`.</span></span> <span data-ttu-id="75251-110">这可阻止编译器静默调用可能产生意外后果的转换操作。</span><span class="sxs-lookup"><span data-stu-id="75251-110">This prevents the compiler from silently invoking the conversion operation with possibly unforeseen consequences.</span></span>  
  
 <span data-ttu-id="75251-111">省略转换将导致编译时错误 CS0266。</span><span class="sxs-lookup"><span data-stu-id="75251-111">Omitting the cast results in compile-time error CS0266.</span></span>  
  
 <span data-ttu-id="75251-112">有关详细信息，请参阅[使用转换运算符](../../../csharp/programming-guide/statements-expressions-operators/using-conversion-operators.md)。</span><span class="sxs-lookup"><span data-stu-id="75251-112">For more information, see [Using Conversion Operators](../../../csharp/programming-guide/statements-expressions-operators/using-conversion-operators.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="75251-113">示例</span><span class="sxs-lookup"><span data-stu-id="75251-113">Example</span></span>  
 <span data-ttu-id="75251-114">下面的示例提供了 `Fahrenheit` 和 `Celsius` 类，其中每个类均提供转换为其他类的显式转换运算符。</span><span class="sxs-lookup"><span data-stu-id="75251-114">The following example provides a `Fahrenheit` and a `Celsius` class, each of which provides an explicit conversion operator to the other class.</span></span>  
  
 [!code-csharp[csrefKeywordsConversion#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/explicit_3.cs)]  
  
## <a name="example"></a><span data-ttu-id="75251-115">示例</span><span class="sxs-lookup"><span data-stu-id="75251-115">Example</span></span>  
 <span data-ttu-id="75251-116">下面的示例定义结构 `Digit`，它表示单个的十进制数字。</span><span class="sxs-lookup"><span data-stu-id="75251-116">The following example defines a struct, `Digit`, that represents a single decimal digit.</span></span> <span data-ttu-id="75251-117">将运算符定义为从 `byte` 到 `Digit` 的转换，但由于并非所有字节都可转换为 `Digit`，因此该转换为显式。</span><span class="sxs-lookup"><span data-stu-id="75251-117">An operator is defined for conversions from `byte` to `Digit`, but because not all bytes can be converted to a `Digit`, the conversion is explicit.</span></span>  
  
 [!code-csharp[csrefKeywordsConversion#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/explicit_4.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="75251-118">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="75251-118">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="75251-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="75251-119">See Also</span></span>  
 [<span data-ttu-id="75251-120">C# 参考</span><span class="sxs-lookup"><span data-stu-id="75251-120">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="75251-121">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="75251-121">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="75251-122">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="75251-122">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="75251-123">implicit</span><span class="sxs-lookup"><span data-stu-id="75251-123">implicit</span></span>](../../../csharp/language-reference/keywords/implicit.md)  
 [<span data-ttu-id="75251-124">运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="75251-124">operator (C# Reference)</span></span>](../../../csharp/language-reference/keywords/operator.md)  
 [<span data-ttu-id="75251-125">如何：在结构之间实现用户定义的转换</span><span class="sxs-lookup"><span data-stu-id="75251-125">How to: Implement User-Defined Conversions Between Structs</span></span>](../../../csharp/programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)  
 <span data-ttu-id="75251-126">[Chained user-defined explicit conversions in C#](http://go.microsoft.com/fwlink/?LinkId=112384)（C# 中链接在一起的用户定义的显式转换）</span><span class="sxs-lookup"><span data-stu-id="75251-126">[Chained user-defined explicit conversions in C#](http://go.microsoft.com/fwlink/?LinkId=112384)</span></span>
