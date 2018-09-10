---
title: explicit 关键字（C# 参考）
ms.date: 08/24/2018
f1_keywords:
- explicit_CSharpKeyword
- explicit
helpviewer_keywords:
- explicit keyword [C#]
ms.assetid: cfb8f42a-e411-4db2-af9b-796b05644846
ms.openlocfilehash: 3567a2c5aa549aa3141ed59c3e93e7b07975da70
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43525456"
---
# <a name="explicit-c-reference"></a><span data-ttu-id="fe2c1-102">explicit（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="fe2c1-102">explicit (C# Reference)</span></span>

<span data-ttu-id="fe2c1-103">`explicit` 关键字声明必须通过转换来调用的用户定义的类型转换运算符。</span><span class="sxs-lookup"><span data-stu-id="fe2c1-103">The `explicit` keyword declares a user-defined type conversion operator that must be invoked with a cast.</span></span>

<span data-ttu-id="fe2c1-104">以下示例定义从 `Fahrenheit` 类转换为 `Celsius` 类的运算符。</span><span class="sxs-lookup"><span data-stu-id="fe2c1-104">The following example defines the operator that converts from a `Fahrenheit` class to a `Celsius` class.</span></span> <span data-ttu-id="fe2c1-105">必须在 `Fahrenheit` 类或 `Celsius` 类中定义运算符：</span><span class="sxs-lookup"><span data-stu-id="fe2c1-105">The operator must be defined either inside a `Fahrenheit` class or a `Celsius` class:</span></span>

[!code-csharp[csrefKeywordsConversion#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsConversion/CS/csrefKeywordsConversion.cs#2)]

<span data-ttu-id="fe2c1-106">如以下示例所示，使用强制转换调用定义的转换运算符：</span><span class="sxs-lookup"><span data-stu-id="fe2c1-106">You invoke the defined conversion operator with a cast, as the following example shows:</span></span>

[!code-csharp[csrefKeywordsConversion#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsConversion/CS/csrefKeywordsConversion.cs#3)]

<span data-ttu-id="fe2c1-107">此转换运算符从源类型转换为目标类型。</span><span class="sxs-lookup"><span data-stu-id="fe2c1-107">The conversion operator converts from a source type to a target type.</span></span> <span data-ttu-id="fe2c1-108">源类型提供转换运算符。</span><span class="sxs-lookup"><span data-stu-id="fe2c1-108">The source type provides the conversion operator.</span></span> <span data-ttu-id="fe2c1-109">不同于隐式转换，显式转换运算符必须通过转换的方式来调用。</span><span class="sxs-lookup"><span data-stu-id="fe2c1-109">Unlike implicit conversion, explicit conversion operators must be invoked by means of a cast.</span></span> <span data-ttu-id="fe2c1-110">如果转换操作会导致异常或丢失信息，则应将其标记为 `explicit`。</span><span class="sxs-lookup"><span data-stu-id="fe2c1-110">If a conversion operation can cause exceptions or lose information, you should mark it `explicit`.</span></span> <span data-ttu-id="fe2c1-111">这可阻止编译器静默调用可能产生意外后果的转换操作。</span><span class="sxs-lookup"><span data-stu-id="fe2c1-111">This prevents the compiler from silently invoking the conversion operation with possibly unforeseen consequences.</span></span>

<span data-ttu-id="fe2c1-112">省略转换将导致编译时错误 CS0266。</span><span class="sxs-lookup"><span data-stu-id="fe2c1-112">Omitting the cast results in compile-time error CS0266.</span></span>

<span data-ttu-id="fe2c1-113">有关详细信息，请参阅[使用转换运算符](../../programming-guide/statements-expressions-operators/using-conversion-operators.md)。</span><span class="sxs-lookup"><span data-stu-id="fe2c1-113">For more information, see [Using Conversion Operators](../../programming-guide/statements-expressions-operators/using-conversion-operators.md).</span></span>

## <a name="example"></a><span data-ttu-id="fe2c1-114">示例</span><span class="sxs-lookup"><span data-stu-id="fe2c1-114">Example</span></span>

<span data-ttu-id="fe2c1-115">下面的示例提供了 `Fahrenheit` 和 `Celsius` 类，其中每个类均提供转换为其他类的显式转换运算符。</span><span class="sxs-lookup"><span data-stu-id="fe2c1-115">The following example provides a `Fahrenheit` and a `Celsius` class, each of which provides an explicit conversion operator to the other class.</span></span>

[!code-csharp[csrefKeywordsConversion#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsConversion/CS/csrefKeywordsConversion.cs#1)]

## <a name="example"></a><span data-ttu-id="fe2c1-116">示例</span><span class="sxs-lookup"><span data-stu-id="fe2c1-116">Example</span></span>

<span data-ttu-id="fe2c1-117">下面的示例定义结构 `Digit`，它表示单个的十进制数字。</span><span class="sxs-lookup"><span data-stu-id="fe2c1-117">The following example defines a struct, `Digit`, that represents a single decimal digit.</span></span> <span data-ttu-id="fe2c1-118">将运算符定义为从 `byte` 到 `Digit` 的转换，但由于并非所有字节都可转换为 `Digit`，因此该转换为显式。</span><span class="sxs-lookup"><span data-stu-id="fe2c1-118">An operator is defined for conversions from `byte` to `Digit`, but because not all bytes can be converted to a `Digit`, the conversion is explicit.</span></span>

[!code-csharp[csrefKeywordsConversion#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsConversion/CS/csrefKeywordsConversion.cs#4)]

## <a name="c-language-specification"></a><span data-ttu-id="fe2c1-119">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="fe2c1-119">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="fe2c1-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="fe2c1-120">See also</span></span>

- [<span data-ttu-id="fe2c1-121">C# 参考</span><span class="sxs-lookup"><span data-stu-id="fe2c1-121">C# Reference</span></span>](../index.md)  
- [<span data-ttu-id="fe2c1-122">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="fe2c1-122">C# Programming Guide</span></span>](../../programming-guide/index.md)  
- [<span data-ttu-id="fe2c1-123">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="fe2c1-123">C# Keywords</span></span>](index.md)  
- [<span data-ttu-id="fe2c1-124">implicit</span><span class="sxs-lookup"><span data-stu-id="fe2c1-124">implicit</span></span>](implicit.md)  
- [<span data-ttu-id="fe2c1-125">运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="fe2c1-125">operator (C# Reference)</span></span>](operator.md)  
- [<span data-ttu-id="fe2c1-126">如何：在结构之间实现用户定义的转换</span><span class="sxs-lookup"><span data-stu-id="fe2c1-126">How to: Implement User-Defined Conversions Between Structs</span></span>](../../programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)  
- <span data-ttu-id="fe2c1-127">[Chained user-defined explicit conversions in C#](https://blogs.msdn.microsoft.com/ericlippert/2007/04/16/chained-user-defined-explicit-conversions-in-c/)（C# 中链接在一起的用户定义的显式转换）</span><span class="sxs-lookup"><span data-stu-id="fe2c1-127">[Chained user-defined explicit conversions in C#](https://blogs.msdn.microsoft.com/ericlippert/2007/04/16/chained-user-defined-explicit-conversions-in-c/)</span></span>  
