---
title: 如何：使用模式匹配以及 is 和 as 运算符安全地进行强制转换
description: 了解如何使用模式匹配方法将变量安全地转换为其他类型。 可以使用模式匹配以及 is 和 as 运算符来安全地转换类型。
ms.date: 09/05/2018
helpviewer_keywords:
- cast operators [C#], as and is operators
- as operator [C#]
- is operator [C#]
ms.openlocfilehash: 88289099864293b3b19da62155d58ba4797948bd
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/08/2018
ms.locfileid: "44216168"
---
# <a name="how-to-safely-cast-by-using-pattern-matching-is-and-as-operators"></a><span data-ttu-id="25d4d-104">如何：使用模式匹配 is 和 as 运算符安全地进行强制转换</span><span class="sxs-lookup"><span data-stu-id="25d4d-104">How to: safely cast by using pattern matching is and as operators</span></span>

<span data-ttu-id="25d4d-105">由于是多态对象，基类类型的变量可以保存派生[类型](../programming-guide/types/index.md)。</span><span class="sxs-lookup"><span data-stu-id="25d4d-105">Because objects are polymorphic, it's possible for a variable of a base class type to hold a derived [type](../programming-guide/types/index.md).</span></span> <span data-ttu-id="25d4d-106">要访问派生类型的实例成员，必须将值[强制转换](../programming-guide/types/casting-and-type-conversions.md)回派生类型。</span><span class="sxs-lookup"><span data-stu-id="25d4d-106">To access the derived type's instance members, it's necessary to [cast](../programming-guide/types/casting-and-type-conversions.md) the value back to the derived type.</span></span> <span data-ttu-id="25d4d-107">但是，强制转换会引发 <xref:System.InvalidCastException> 风险。</span><span class="sxs-lookup"><span data-stu-id="25d4d-107">However, a cast creates the risk of throwing an <xref:System.InvalidCastException>.</span></span> <span data-ttu-id="25d4d-108">C# 提供[模式匹配](../pattern-matching.md)语句，该语句只有在成功时才会有条件地执行强制转换。</span><span class="sxs-lookup"><span data-stu-id="25d4d-108">C# provides [pattern matching](../pattern-matching.md) statements that perform a cast conditionally only when it will succeed.</span></span> <span data-ttu-id="25d4d-109">C# 还提供 [is](../language-reference/keywords/is.md) 和 [as](../language-reference/keywords/as.md) 运算符来测试值是否属于特定类型。</span><span class="sxs-lookup"><span data-stu-id="25d4d-109">C# also provides the [is](../language-reference/keywords/is.md) and [as](../language-reference/keywords/as.md) operators to test if a value is of a certain type.</span></span>

[!INCLUDE[interactive-note](~/includes/csharp-interactive-note.md)]

<span data-ttu-id="25d4d-110">下面的代码演示模式匹配 `is` 语句。</span><span class="sxs-lookup"><span data-stu-id="25d4d-110">The following code demonstrates the pattern matching `is` statement.</span></span> <span data-ttu-id="25d4d-111">它包含测试方法参数的方法，以确定它是否是一组可能的派生类型：</span><span class="sxs-lookup"><span data-stu-id="25d4d-111">It contains methods that test a method argument to determine if it is one of a possible set of derived types:</span></span>

[!code-csharp-interactive[Pattern matching is statement](../../../samples/snippets/csharp/how-to/safelycast/patternmatching/Program.cs#PatternMatchingIs)]

<span data-ttu-id="25d4d-112">前面的示例演示了模式匹配语法的一些功能。</span><span class="sxs-lookup"><span data-stu-id="25d4d-112">The preceding sample demonstrates a few features of pattern matching syntax.</span></span> <span data-ttu-id="25d4d-113">`if (a is Mammal m)` 和 `if (o is Mammal m)` 语句将测试与初始化赋值相结合。</span><span class="sxs-lookup"><span data-stu-id="25d4d-113">The `if (a is Mammal m)` and `if (o is Mammal m)` statements combine the test with an initialization assignment.</span></span> <span data-ttu-id="25d4d-114">只有在测试成功时才会进行赋值。</span><span class="sxs-lookup"><span data-stu-id="25d4d-114">TThe assignment occurs only when the test succeeds.</span></span> <span data-ttu-id="25d4d-115">变量 `m` 仅在已赋值的嵌入式 `if` 语句的范围内。</span><span class="sxs-lookup"><span data-stu-id="25d4d-115">The variable `m` is only in scope in the embedded `if` statement where it has been assigned.</span></span> <span data-ttu-id="25d4d-116">以后无法在同一方法中访问 `m`。</span><span class="sxs-lookup"><span data-stu-id="25d4d-116">You cannot access `m` later in the same method.</span></span> <span data-ttu-id="25d4d-117">在交互式窗口中尝试操作。</span><span class="sxs-lookup"><span data-stu-id="25d4d-117">Try it in the interactive window.</span></span>

<span data-ttu-id="25d4d-118">也可以使用同一语法来测试[可以为 null 的类型](../programming-guide/nullable-types/index.md)是否具有值，如以下示例代码所示：</span><span class="sxs-lookup"><span data-stu-id="25d4d-118">You can also use the same syntax for testing if a [nullable type](../programming-guide/nullable-types/index.md) has a value, as shown in the following sample code:</span></span>

[!code-csharp-interactive[Pattern matching with nullable types](../../../samples/snippets/csharp/how-to/safelycast/nullablepatternmatching/Program.cs#PatternMatchingNullable)]

<span data-ttu-id="25d4d-119">前面的示例演示了模式匹配用于转换的其他功能。</span><span class="sxs-lookup"><span data-stu-id="25d4d-119">The preceding sample demonstrates other features of pattern matching to use with conversions.</span></span> <span data-ttu-id="25d4d-120">可以通过专门检查 `null` 值来测试 NULL 模式的变量。</span><span class="sxs-lookup"><span data-stu-id="25d4d-120">You can test a variable for the null pattern by checking specifically for the `null` value.</span></span> <span data-ttu-id="25d4d-121">当变量的运行时值为 `null` 时，用于检查类型的 `is` 语句始终返回 `false`。</span><span class="sxs-lookup"><span data-stu-id="25d4d-121">When the runtime value of the variable is `null`, an `is` statement checking for a type always returns `false`.</span></span> <span data-ttu-id="25d4d-122">模式匹配 `is` 语句不允许可以为 null 值的类型，如 `int?` 或 `Nullable<int>`，但你可以测试任何其他值类型。</span><span class="sxs-lookup"><span data-stu-id="25d4d-122">The pattern matching `is` statement doesn't allow a nullable value type, such as `int?` or `Nullable<int>`, but you can test for any other value type.</span></span>

<span data-ttu-id="25d4d-123">前面的示例还演示如何在变量为其他类型的 `switch` 语句中使用模式匹配 `is` 表达式。</span><span class="sxs-lookup"><span data-stu-id="25d4d-123">The preceding sample also shows how you use the pattern matching `is` expression in a `switch` statement where the variable may be one of many different types.</span></span>

<span data-ttu-id="25d4d-124">如果想要测试变量是否为给定类型，但不将其分配给新变量，则可以对引用类型和可以为 null 的类型使用 `is` 和 `as` 运算符。</span><span class="sxs-lookup"><span data-stu-id="25d4d-124">If you want to test if a variable is a given type, but not assign it to a new variable, you can use the `is` and `as` operators for reference types and nullable types.</span></span> <span data-ttu-id="25d4d-125">以下代码演示如何在引入模式匹配以测试变量是否为给定类型前，使用 C# 语言中的 `is` 和 `as` 语句：</span><span class="sxs-lookup"><span data-stu-id="25d4d-125">The following code shows how to use the `is` and `as` statements that were part of the C# language before pattern matching was introduced to test if a variable is of a given type:</span></span>

[!code-csharp-interactive[testing variable types with the is and as statements](../../../samples/snippets/csharp/how-to/safelycast/asandis/Program.cs#IsAndAs)]

<span data-ttu-id="25d4d-126">正如你所看到的，将此代码与模式匹配代码进行比较，模式匹配语法通过在单个语句中结合测试和赋值来提供更强大的功能。</span><span class="sxs-lookup"><span data-stu-id="25d4d-126">As you can see by comparing this code with the pattern matching code, the pattern matching syntax provides more robust features by combining the test and the assignment in a single statement.</span></span> <span data-ttu-id="25d4d-127">尽量使用模式匹配语法。</span><span class="sxs-lookup"><span data-stu-id="25d4d-127">Use the pattern matching syntax whenever possible.</span></span>

<span data-ttu-id="25d4d-128">可通过查看 [GitHub 存储库](https://github.com/dotnet/samples/tree/master/snippets/csharp/how-to/safelycast)中的代码来尝试这些示例。</span><span class="sxs-lookup"><span data-stu-id="25d4d-128">You can try these samples by looking at the code in our [GitHub repository](https://github.com/dotnet/samples/tree/master/snippets/csharp/how-to/safelycast).</span></span> <span data-ttu-id="25d4d-129">也可以下载这些示例的 [zip 文件](https://github.com/dotnet/samples/raw/master/snippets/csharp/how-to/safelycast.zip)。</span><span class="sxs-lookup"><span data-stu-id="25d4d-129">Or you can download the samples [as a zip file](https://github.com/dotnet/samples/raw/master/snippets/csharp/how-to/safelycast.zip).</span></span>
