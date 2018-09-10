---
title: bool 关键字（C# 参考）
ms.date: 07/20/2015
f1_keywords:
- bool_CSharpKeyword
- bool
helpviewer_keywords:
- bool keyword [C#]
ms.assetid: 551cfe35-2632-4343-af49-33ad12da08e2
ms.openlocfilehash: 2041182dffa0330ea601b30e047c0b09731618f2
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2018
ms.locfileid: "44042395"
---
# <a name="bool-c-reference"></a><span data-ttu-id="444c8-102">bool（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="444c8-102">bool (C# Reference)</span></span>

<span data-ttu-id="444c8-103">`bool` 关键字是 <xref:System.Boolean?displayProperty=nameWithType> 的别名。</span><span class="sxs-lookup"><span data-stu-id="444c8-103">The `bool` keyword is an alias of <xref:System.Boolean?displayProperty=nameWithType>.</span></span> <span data-ttu-id="444c8-104">它用于声明变量来存储布尔值 [true](../../../csharp/language-reference/keywords/true.md) 和 [false](../../../csharp/language-reference/keywords/false.md)。</span><span class="sxs-lookup"><span data-stu-id="444c8-104">It is used to declare variables to store the Boolean values, [true](../../../csharp/language-reference/keywords/true.md) and [false](../../../csharp/language-reference/keywords/false.md).</span></span>

> [!NOTE]
> <span data-ttu-id="444c8-105">如果需要一个也可以有 `null` 值的布尔型变量，请使用 `bool?`。</span><span class="sxs-lookup"><span data-stu-id="444c8-105">If you require a Boolean variable that can also have a value of `null`, use `bool?`.</span></span> <span data-ttu-id="444c8-106">有关详细信息，请参阅[可以为 null 的类型](../../../csharp/programming-guide/nullable-types/index.md)。</span><span class="sxs-lookup"><span data-stu-id="444c8-106">For more information, see [Nullable Types](../../../csharp/programming-guide/nullable-types/index.md).</span></span>

## <a name="literals"></a><span data-ttu-id="444c8-107">文本</span><span class="sxs-lookup"><span data-stu-id="444c8-107">Literals</span></span>

<span data-ttu-id="444c8-108">可将布尔值赋给 `bool` 变量。</span><span class="sxs-lookup"><span data-stu-id="444c8-108">You can assign a Boolean value to a `bool` variable.</span></span> <span data-ttu-id="444c8-109">也可以将计算结果为 `bool` 类型的表达式赋给 `bool` 变量。</span><span class="sxs-lookup"><span data-stu-id="444c8-109">You can also assign an expression that evaluates to `bool` to a `bool` variable.</span></span>

[!code-csharp[csrefKeywordsTypes#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#1)]

<span data-ttu-id="444c8-110">`bool` 变量的默认值为 `false`。</span><span class="sxs-lookup"><span data-stu-id="444c8-110">The default value of a `bool` variable is `false`.</span></span> <span data-ttu-id="444c8-111">`bool?` 变量的默认值为 `null`。</span><span class="sxs-lookup"><span data-stu-id="444c8-111">The default value of a `bool?` variable is `null`.</span></span>

## <a name="conversions"></a><span data-ttu-id="444c8-112">转换</span><span class="sxs-lookup"><span data-stu-id="444c8-112">Conversions</span></span>

<span data-ttu-id="444c8-113">在 C++ 中，`bool` 类型的值可转换为 `int` 类型的值；也就是说，`false` 等效于零值，而 `true` 等效于非零值。</span><span class="sxs-lookup"><span data-stu-id="444c8-113">In C++, a value of type `bool` can be converted to a value of type `int`; in other words, `false` is equivalent to zero and `true` is equivalent to nonzero values.</span></span> <span data-ttu-id="444c8-114">在 C# 中，不存在 `bool` 类型与其他类型之间的相互转换。</span><span class="sxs-lookup"><span data-stu-id="444c8-114">In C#, there is no conversion between the `bool` type and other types.</span></span> <span data-ttu-id="444c8-115">例如，下面的 `if` 语句在 C# 中无效：</span><span class="sxs-lookup"><span data-stu-id="444c8-115">For example, the following `if` statement is invalid in C#:</span></span>

[!code-csharp[csrefKeywordsTypes#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#2)]

<span data-ttu-id="444c8-116">若要测试 `int` 类型的变量，必须将该变量与一个值（例如零）进行显式比较，如下所示：</span><span class="sxs-lookup"><span data-stu-id="444c8-116">To test a variable of the type `int`, you have to explicitly compare it to a value, such as zero, as follows:</span></span>

[!code-csharp[csrefKeywordsTypes#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#3)]

## <a name="example"></a><span data-ttu-id="444c8-117">示例</span><span class="sxs-lookup"><span data-stu-id="444c8-117">Example</span></span>

<span data-ttu-id="444c8-118">在此例中，你通过键盘输入一个字符，然后程序检查输入的字符是否是一个字母。</span><span class="sxs-lookup"><span data-stu-id="444c8-118">In this example, you enter a character from the keyboard and the program checks if the input character is a letter.</span></span> <span data-ttu-id="444c8-119">如果字符是一个字母，则程序检查它是大写还是小写。</span><span class="sxs-lookup"><span data-stu-id="444c8-119">If it is a letter, it checks if it is lowercase or uppercase.</span></span> <span data-ttu-id="444c8-120">执行这些检查使用的是 <xref:System.Char.IsLetter%2A> 和 <xref:System.Char.IsLower%2A>，二者均返回 `bool` 类型：</span><span class="sxs-lookup"><span data-stu-id="444c8-120">These checks are performed with the <xref:System.Char.IsLetter%2A>, and <xref:System.Char.IsLower%2A>, both of which return the `bool` type:</span></span>

[!code-csharp[csrefKeywordsTypes#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#4)]

## <a name="c-language-specification"></a><span data-ttu-id="444c8-121">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="444c8-121">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="444c8-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="444c8-122">See also</span></span>

- [<span data-ttu-id="444c8-123">C# 参考</span><span class="sxs-lookup"><span data-stu-id="444c8-123">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="444c8-124">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="444c8-124">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="444c8-125">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="444c8-125">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
- [<span data-ttu-id="444c8-126">整型表</span><span class="sxs-lookup"><span data-stu-id="444c8-126">Integral Types Table</span></span>](../../../csharp/language-reference/keywords/integral-types-table.md)  
- [<span data-ttu-id="444c8-127">内置类型表</span><span class="sxs-lookup"><span data-stu-id="444c8-127">Built-In Types Table</span></span>](../../../csharp/language-reference/keywords/built-in-types-table.md)  
- [<span data-ttu-id="444c8-128">隐式数值转换表</span><span class="sxs-lookup"><span data-stu-id="444c8-128">Implicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)  
- [<span data-ttu-id="444c8-129">显式数值转换表</span><span class="sxs-lookup"><span data-stu-id="444c8-129">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)  