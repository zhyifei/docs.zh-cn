---
title: 一维数组 - C# 编程指南
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- single-dimensional arrays [C#]
- arrays [C#], single-dimensional
ms.assetid: 2cec1196-1de0-49d2-baf2-c607c33310e8
ms.openlocfilehash: 5559acd162b26a94b009ec21691d1501c90db290
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/01/2019
ms.locfileid: "73419527"
---
# <a name="single-dimensional-arrays-c-programming-guide"></a><span data-ttu-id="e8bf5-102">一维数组（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="e8bf5-102">Single-Dimensional Arrays (C# Programming Guide)</span></span>

<span data-ttu-id="e8bf5-103">可以声明五个整数的一维数组，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="e8bf5-103">You can declare a single-dimensional array of five integers as shown in the following example:</span></span>  
  
 [!code-csharp[csProgGuideArrays#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#4)]  
  
 <span data-ttu-id="e8bf5-104">此数组包含从 `array[0]` 到 `array[4]` 的元素。</span><span class="sxs-lookup"><span data-stu-id="e8bf5-104">This array contains the elements from `array[0]` to `array[4]`.</span></span> <span data-ttu-id="e8bf5-105">[new](../../language-reference/operators/new-operator.md) 运算符用于创建数组并将数组元素初始化为其默认值。</span><span class="sxs-lookup"><span data-stu-id="e8bf5-105">The [new](../../language-reference/operators/new-operator.md) operator is used to create the array and initialize the array elements to their default values.</span></span> <span data-ttu-id="e8bf5-106">在此示例中，所有数组元素都将被初始化为零。</span><span class="sxs-lookup"><span data-stu-id="e8bf5-106">In this example, all the array elements are initialized to zero.</span></span>  
  
 <span data-ttu-id="e8bf5-107">可使用相同方式声明存储字符串元素的数组。</span><span class="sxs-lookup"><span data-stu-id="e8bf5-107">An array that stores string elements can be declared in the same way.</span></span> <span data-ttu-id="e8bf5-108">例如:</span><span class="sxs-lookup"><span data-stu-id="e8bf5-108">For example:</span></span>  
  
 [!code-csharp[csProgGuideArrays#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#5)]  
  
## <a name="array-initialization"></a><span data-ttu-id="e8bf5-109">数组初始化</span><span class="sxs-lookup"><span data-stu-id="e8bf5-109">Array Initialization</span></span>

 <span data-ttu-id="e8bf5-110">可以在声明时初始化数组，在这种情况下，无需长度说明符，因为它已由初始化列表中的元素数目提供。</span><span class="sxs-lookup"><span data-stu-id="e8bf5-110">It is possible to initialize an array upon declaration, in which case, the length specifier is not needed because it is already supplied by the number of elements in the initialization list.</span></span> <span data-ttu-id="e8bf5-111">例如:</span><span class="sxs-lookup"><span data-stu-id="e8bf5-111">For example:</span></span>  
  
 [!code-csharp[csProgGuideArrays#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#6)]  
  
 <span data-ttu-id="e8bf5-112">可使用相同方式初始化字符串数组。</span><span class="sxs-lookup"><span data-stu-id="e8bf5-112">A string array can be initialized in the same way.</span></span> <span data-ttu-id="e8bf5-113">下面是一个字符串数组的声明，其中每个数组元素都由一天的名称初始化：</span><span class="sxs-lookup"><span data-stu-id="e8bf5-113">The following is a declaration of a string array where each array element is initialized by a name of a day:</span></span>  
 
 ```csharp
 string[] weekDays = new string[] { "Sun", "Mon", "Tue", "Wed", "Thu", "Fri", "Sat" };
 ```
  
 <span data-ttu-id="e8bf5-114">如果在声明时初始化数组，可以使用以下快捷方式：</span><span class="sxs-lookup"><span data-stu-id="e8bf5-114">When you initialize an array upon declaration, you can use the following shortcuts:</span></span>  
  
 [!code-csharp[csProgGuideArrays#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#8)]  
  
 <span data-ttu-id="e8bf5-115">可以在不初始化的情况下声明数组变量，但必须使用 `new` 运算符向此变量分配数组。</span><span class="sxs-lookup"><span data-stu-id="e8bf5-115">It is possible to declare an array variable without initialization, but you must use the `new` operator when you assign an array to this variable.</span></span> <span data-ttu-id="e8bf5-116">例如:</span><span class="sxs-lookup"><span data-stu-id="e8bf5-116">For example:</span></span>  
  
 [!code-csharp[csProgGuideArrays#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#9)]  
  
 <span data-ttu-id="e8bf5-117">C# 3.0 引入了隐式类型化数组。</span><span class="sxs-lookup"><span data-stu-id="e8bf5-117">C# 3.0 introduces implicitly typed arrays.</span></span> <span data-ttu-id="e8bf5-118">有关详细信息，请参阅[隐式类型化数组](./implicitly-typed-arrays.md)。</span><span class="sxs-lookup"><span data-stu-id="e8bf5-118">For more information, see [Implicitly Typed Arrays](./implicitly-typed-arrays.md).</span></span>  
  
## <a name="value-type-and-reference-type-arrays"></a><span data-ttu-id="e8bf5-119">值类型和引用类型数组</span><span class="sxs-lookup"><span data-stu-id="e8bf5-119">Value Type and Reference Type Arrays</span></span>

 <span data-ttu-id="e8bf5-120">请考虑以下数组声明：</span><span class="sxs-lookup"><span data-stu-id="e8bf5-120">Consider the following array declaration:</span></span>  
  
 [!code-csharp[csProgGuideArrays#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#10)]  
  
 <span data-ttu-id="e8bf5-121">此语句的结果取决于 `SomeType` 是值类型还是引用类型。</span><span class="sxs-lookup"><span data-stu-id="e8bf5-121">The result of this statement depends on whether `SomeType` is a value type or a reference type.</span></span> <span data-ttu-id="e8bf5-122">如果它是值类型，该语句将创建一个 10 个元素的数组，其中每个元素的类型都为 `SomeType`。</span><span class="sxs-lookup"><span data-stu-id="e8bf5-122">If it is a value type, the statement creates an array of 10 elements, each of which has the type `SomeType`.</span></span> <span data-ttu-id="e8bf5-123">如果 `SomeType` 是引用类型，该语句将创建一个 10 个元素的数组，其中每个元素都将被初始化为空引用。</span><span class="sxs-lookup"><span data-stu-id="e8bf5-123">If `SomeType` is a reference type, the statement creates an array of 10 elements, each of which is initialized to a null reference.</span></span>  
  
 <span data-ttu-id="e8bf5-124">有关值类型和引用类型的详细信息，请参阅[类型](/dotnet/csharp/language-reference/keywords)。</span><span class="sxs-lookup"><span data-stu-id="e8bf5-124">For more information about value types and reference types, see [Types](/dotnet/csharp/language-reference/keywords).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8bf5-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="e8bf5-125">See also</span></span>

- <xref:System.Array>
- [<span data-ttu-id="e8bf5-126">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="e8bf5-126">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="e8bf5-127">数组</span><span class="sxs-lookup"><span data-stu-id="e8bf5-127">Arrays</span></span>](./index.md)
- [<span data-ttu-id="e8bf5-128">多维数组</span><span class="sxs-lookup"><span data-stu-id="e8bf5-128">Multidimensional Arrays</span></span>](./multidimensional-arrays.md)
- [<span data-ttu-id="e8bf5-129">交错数组</span><span class="sxs-lookup"><span data-stu-id="e8bf5-129">Jagged Arrays</span></span>](./jagged-arrays.md)
