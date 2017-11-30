---
title: "C# 数组 - C# 语言介绍"
description: "数组是对 C# 语言中的最基本集合类型"
keywords: ".NET, C#, 数组, 集合"
author: BillWagner
ms.author: wiwagn
ms.date: 08/10/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: a440704c-9e88-4c75-97dd-bfe30ca0fb97
ms.openlocfilehash: d7d5ae9f99ba1629a6f0aec57bebf74853cab27f
ms.sourcegitcommit: a19548e5167cbe7e9e58df4ffd8c3b23f17d5c7a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2017
---
# <a name="arrays"></a><span data-ttu-id="622e9-104">数组</span><span class="sxs-lookup"><span data-stu-id="622e9-104">Arrays</span></span>

<span data-ttu-id="622e9-105">***数组***是一种数据结构，其中包含许多通过计算索引访问的变量。</span><span class="sxs-lookup"><span data-stu-id="622e9-105">An ***array*** is a data structure that contains a number of variables that are accessed through computed indices.</span></span> <span data-ttu-id="622e9-106">数组中的变量（亦称为数组的***元素***）均为同一种类型，我们将这种类型称为数组的***元素类型***。</span><span class="sxs-lookup"><span data-stu-id="622e9-106">The variables contained in an array, also called the ***elements*** of the array, are all of the same type, and this type is called the ***element type*** of the array.</span></span>

<span data-ttu-id="622e9-107">数组类型是引用类型，声明数组变量只是为引用数组实例预留空间。</span><span class="sxs-lookup"><span data-stu-id="622e9-107">Array types are reference types, and the declaration of an array variable simply sets aside space for a reference to an array instance.</span></span> <span data-ttu-id="622e9-108">实际的数组实例是在运行时使用 new 运算符动态创建而成。</span><span class="sxs-lookup"><span data-stu-id="622e9-108">Actual array instances are created dynamically at runtime using the new operator.</span></span> <span data-ttu-id="622e9-109">new 运算指定了新数组实例的***长度***，然后在此实例的生存期内固定使用这个长度。</span><span class="sxs-lookup"><span data-stu-id="622e9-109">The new operation specifies the ***length*** of the new array instance, which is then fixed for the lifetime of the instance.</span></span> <span data-ttu-id="622e9-110">数组元素的索引介于 `0` 到 `Length - 1` 之间。</span><span class="sxs-lookup"><span data-stu-id="622e9-110">The indices of the elements of an array range from `0` to `Length - 1`.</span></span> <span data-ttu-id="622e9-111">`new` 运算符自动将数组元素初始化为其默认值（例如，所有数值类型的默认值为 0，所有引用类型的默认值为 `null`）。</span><span class="sxs-lookup"><span data-stu-id="622e9-111">The `new` operator automatically initializes the elements of an array to their default value, which, for example, is zero for all numeric types and `null` for all reference types.</span></span>

<span data-ttu-id="622e9-112">以下示例创建 `int` 元素数组，初始化此数组，然后打印输出此数组的内容。</span><span class="sxs-lookup"><span data-stu-id="622e9-112">The following example creates an array of `int` elements, initializes the array, and prints out the contents of the array.</span></span>

[!code-csharp[ArraySample](../../../samples/snippets/csharp/tour/arrays/Program.cs#L3-L18)]

<span data-ttu-id="622e9-113">上面的示例创建***一维数组***，并对其执行运算。</span><span class="sxs-lookup"><span data-stu-id="622e9-113">This example creates and operates on a ***single-dimensional array***.</span></span> <span data-ttu-id="622e9-114">C# 还支持***多维数组***。</span><span class="sxs-lookup"><span data-stu-id="622e9-114">C# also supports ***multi-dimensional arrays***.</span></span> <span data-ttu-id="622e9-115">数组类型的维数（亦称为数组类型的***秩***）是 1 与数组类型方括号内的逗号数量相加的结果。</span><span class="sxs-lookup"><span data-stu-id="622e9-115">The number of dimensions of an array type, also known as the ***rank*** of the array type, is one plus the number of commas written between the square brackets of the array type.</span></span> <span data-ttu-id="622e9-116">以下示例分别分配一维、二维、三维数组。</span><span class="sxs-lookup"><span data-stu-id="622e9-116">The following example allocates a single-dimensional, a two-dimensional, and a three-dimensional array, respectively.</span></span>

[!code-csharp[ArrayRank](../../../samples/snippets/csharp/tour/arrays/Program.cs#L24-L26)]

<span data-ttu-id="622e9-117">`a1` 数组包含 10 个元素，`a2` 数组包含 50 个元素 (10 × 5)，`a3` 数组包含 100 个元素 (10 × 5 × 2)。</span><span class="sxs-lookup"><span data-stu-id="622e9-117">The `a1` array contains 10 elements, the `a2` array contains 50 (10 × 5) elements, and the `a3` array contains 100 (10 × 5 × 2) elements.</span></span>
<span data-ttu-id="622e9-118">数组的元素类型可以是任意类型（包括数组类型）。</span><span class="sxs-lookup"><span data-stu-id="622e9-118">The element type of an array can be any type, including an array type.</span></span> <span data-ttu-id="622e9-119">包含数组类型元素的数组有时称为***交错数组***，因为元素数组的长度不必全都一样。</span><span class="sxs-lookup"><span data-stu-id="622e9-119">An array with elements of an array type is sometimes called a ***jagged array*** because the lengths of the element arrays do not all have to be the same.</span></span> <span data-ttu-id="622e9-120">以下示例分配由 `int` 数组构成的数组：</span><span class="sxs-lookup"><span data-stu-id="622e9-120">The following example allocates an array of arrays of `int`:</span></span>

[!code-csharp[ArrayAllocation](../../../samples/snippets/csharp/tour/arrays/Program.cs#L31-L34)]

<span data-ttu-id="622e9-121">第一行创建包含三个元素的数组，每个元素都是 `int[]` 类型，并且初始值均为 `null`。</span><span class="sxs-lookup"><span data-stu-id="622e9-121">The first line creates an array with three elements, each of type `int[]` and each with an initial value of `null`.</span></span> <span data-ttu-id="622e9-122">后面的代码行将这三个元素初始化为引用长度不同的各个数组实例。</span><span class="sxs-lookup"><span data-stu-id="622e9-122">The subsequent lines then initialize the three elements with references to individual array instances of varying lengths.</span></span>

<span data-ttu-id="622e9-123">通过 new 运算符，可以使用***数组初始值设定项***（在分隔符 `{` 和 `}` 内编写的表达式列表）指定数组元素的初始值。</span><span class="sxs-lookup"><span data-stu-id="622e9-123">The new operator permits the initial values of the array elements to be specified using an ***array initializer***, which is a list of expressions written between the delimiters `{` and `}`.</span></span> <span data-ttu-id="622e9-124">以下示例分配 `int[]`，并将其初始化为包含三个元素。</span><span class="sxs-lookup"><span data-stu-id="622e9-124">The following example allocates and initializes an `int[]` with three elements.</span></span>

[!code-csharp[ArrayInitialization](../../../samples/snippets/csharp/tour/arrays/Program.cs#L39-L39)]

<span data-ttu-id="622e9-125">请注意，可从 { 和 } 内的表达式数量推断出数组的长度。</span><span class="sxs-lookup"><span data-stu-id="622e9-125">Note that the length of the array is inferred from the number of expressions between { and }.</span></span> <span data-ttu-id="622e9-126">局部变量和字段声明可以进一步缩短，这样就不用重新声明数组类型了。</span><span class="sxs-lookup"><span data-stu-id="622e9-126">Local variable and field declarations can be shortened further such that the array type does not have to be restated.</span></span>

[!code-csharp[ArrayInitialization](../../../samples/snippets/csharp/tour/arrays/Program.cs#L44-L44)]

<span data-ttu-id="622e9-127">以上两个示例等同于以下示例：</span><span class="sxs-lookup"><span data-stu-id="622e9-127">Both of the previous examples are equivalent to the following:</span></span>

[!code-csharp[ArrayAssignment](../../../samples/snippets/csharp/tour/arrays/Program.cs#L49-L53)]

>[!div class="step-by-step"]
<span data-ttu-id="622e9-128">[上一页](structs.md)
[下一页](interfaces.md)</span><span class="sxs-lookup"><span data-stu-id="622e9-128">[Previous](structs.md)
[Next](interfaces.md)</span></span>
