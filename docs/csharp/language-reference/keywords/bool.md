---
title: bool 关键字 - C# 参考
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- bool_CSharpKeyword
- bool
helpviewer_keywords:
- bool keyword [C#]
ms.assetid: 551cfe35-2632-4343-af49-33ad12da08e2
ms.openlocfilehash: d87da29872582e9c0d47a6c999312ce88252a5cc
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59334167"
---
# <a name="bool-c-reference"></a><span data-ttu-id="5528f-102">bool（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="5528f-102">bool (C# Reference)</span></span>

<span data-ttu-id="5528f-103">`bool` 关键字是 <xref:System.Boolean?displayProperty=nameWithType> 的别名。</span><span class="sxs-lookup"><span data-stu-id="5528f-103">The `bool` keyword is an alias of <xref:System.Boolean?displayProperty=nameWithType>.</span></span> <span data-ttu-id="5528f-104">它用于声明变量来存储布尔值：[true](true-literal.md) 和 [false](false-literal.md)。</span><span class="sxs-lookup"><span data-stu-id="5528f-104">It is used to declare variables to store the Boolean values: [true](true-literal.md) and [false](false-literal.md).</span></span>

> [!NOTE]
> <span data-ttu-id="5528f-105">如需支持三值逻辑（例如，在使用支持三值布尔类型的数据库时），请使用 `bool?` 类型。</span><span class="sxs-lookup"><span data-stu-id="5528f-105">Use the `bool?` type, if you need to support the three-valued logic, for example, when you work with databases that support a three-valued Boolean type.</span></span> <span data-ttu-id="5528f-106">对于 `bool?` 操作数，预定义的 `&` 和 `|` 运算符支持三值逻辑。</span><span class="sxs-lookup"><span data-stu-id="5528f-106">For the `bool?` operands, the predefined `&` and `|` operators support the three-valued logic.</span></span> <span data-ttu-id="5528f-107">有关详细信息，请参阅[布尔逻辑运算符](../operators/boolean-logical-operators.md)一文的[可以为 null 的布尔逻辑运算符](../operators/boolean-logical-operators.md#nullable-boolean-logical-operators)部分。</span><span class="sxs-lookup"><span data-stu-id="5528f-107">For more information, see the [Nullable Boolean logical operators](../operators/boolean-logical-operators.md#nullable-boolean-logical-operators) section of the [Boolean logical operators](../operators/boolean-logical-operators.md) article.</span></span>

## <a name="literals"></a><span data-ttu-id="5528f-108">文本</span><span class="sxs-lookup"><span data-stu-id="5528f-108">Literals</span></span>

<span data-ttu-id="5528f-109">可将布尔值赋给 `bool` 变量。</span><span class="sxs-lookup"><span data-stu-id="5528f-109">You can assign a Boolean value to a `bool` variable.</span></span> <span data-ttu-id="5528f-110">也可以将计算结果为 `bool` 类型的表达式赋给 `bool` 变量。</span><span class="sxs-lookup"><span data-stu-id="5528f-110">You can also assign an expression that evaluates to `bool` to a `bool` variable.</span></span>

[!code-csharp[csrefKeywordsTypes#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#1)]

<span data-ttu-id="5528f-111">`bool` 变量的默认值为 `false`。</span><span class="sxs-lookup"><span data-stu-id="5528f-111">The default value of a `bool` variable is `false`.</span></span> <span data-ttu-id="5528f-112">`bool?` 变量的默认值为 `null`。</span><span class="sxs-lookup"><span data-stu-id="5528f-112">The default value of a `bool?` variable is `null`.</span></span>

## <a name="conversions"></a><span data-ttu-id="5528f-113">转换</span><span class="sxs-lookup"><span data-stu-id="5528f-113">Conversions</span></span>

<span data-ttu-id="5528f-114">在 C++ 中，`bool` 类型的值可转换为 `int` 类型的值；也就是说，`false` 等效于零值，而 `true` 等效于非零值。</span><span class="sxs-lookup"><span data-stu-id="5528f-114">In C++, a value of type `bool` can be converted to a value of type `int`; in other words, `false` is equivalent to zero and `true` is equivalent to nonzero values.</span></span> <span data-ttu-id="5528f-115">在 C# 中，不存在 `bool` 类型与其他类型之间的相互转换。</span><span class="sxs-lookup"><span data-stu-id="5528f-115">In C#, there is no conversion between the `bool` type and other types.</span></span> <span data-ttu-id="5528f-116">例如，下面的 `if` 语句在 C# 中无效：</span><span class="sxs-lookup"><span data-stu-id="5528f-116">For example, the following `if` statement is invalid in C#:</span></span>

[!code-csharp[csrefKeywordsTypes#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#2)]

<span data-ttu-id="5528f-117">若要测试 `int` 类型的变量，必须将该变量与一个值（例如零）进行显式比较，如下所示：</span><span class="sxs-lookup"><span data-stu-id="5528f-117">To test a variable of the type `int`, you have to explicitly compare it to a value, such as zero, as follows:</span></span>

[!code-csharp[csrefKeywordsTypes#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#3)]

## <a name="example"></a><span data-ttu-id="5528f-118">示例</span><span class="sxs-lookup"><span data-stu-id="5528f-118">Example</span></span>

<span data-ttu-id="5528f-119">在此例中，你通过键盘输入一个字符，然后程序检查输入的字符是否是一个字母。</span><span class="sxs-lookup"><span data-stu-id="5528f-119">In this example, you enter a character from the keyboard and the program checks if the input character is a letter.</span></span> <span data-ttu-id="5528f-120">如果字符是一个字母，则程序检查它是大写还是小写。</span><span class="sxs-lookup"><span data-stu-id="5528f-120">If it is a letter, it checks if it is lowercase or uppercase.</span></span> <span data-ttu-id="5528f-121">执行这些检查使用的是 <xref:System.Char.IsLetter%2A> 和 <xref:System.Char.IsLower%2A>，二者均返回 `bool` 类型：</span><span class="sxs-lookup"><span data-stu-id="5528f-121">These checks are performed with the <xref:System.Char.IsLetter%2A>, and <xref:System.Char.IsLower%2A>, both of which return the `bool` type:</span></span>

[!code-csharp[csrefKeywordsTypes#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#4)]

## <a name="c-language-specification"></a><span data-ttu-id="5528f-122">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="5528f-122">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="5528f-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="5528f-123">See also</span></span>

- [<span data-ttu-id="5528f-124">C# 参考</span><span class="sxs-lookup"><span data-stu-id="5528f-124">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="5528f-125">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="5528f-125">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="5528f-126">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="5528f-126">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)
- [<span data-ttu-id="5528f-127">整型表</span><span class="sxs-lookup"><span data-stu-id="5528f-127">Integral Types Table</span></span>](../../../csharp/language-reference/keywords/integral-types-table.md)
- [<span data-ttu-id="5528f-128">内置类型表</span><span class="sxs-lookup"><span data-stu-id="5528f-128">Built-In Types Table</span></span>](../../../csharp/language-reference/keywords/built-in-types-table.md)
- [<span data-ttu-id="5528f-129">隐式数值转换表</span><span class="sxs-lookup"><span data-stu-id="5528f-129">Implicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)
- [<span data-ttu-id="5528f-130">显式数值转换表</span><span class="sxs-lookup"><span data-stu-id="5528f-130">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)
