---
title: "一维数组（C# 编程指南）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- single-dimensional arrays [C#]
- arrays [C#], single-dimensional
ms.assetid: 2cec1196-1de0-49d2-baf2-c607c33310e8
caps.latest.revision: 18
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
ms.openlocfilehash: cc42640715274b89c4c4a12ced8c0ae6af603318
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="single-dimensional-arrays-c-programming-guide"></a><span data-ttu-id="94b8c-102">一维数组（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="94b8c-102">Single-Dimensional Arrays (C# Programming Guide)</span></span>
<span data-ttu-id="94b8c-103">可以声明五个整数的一维数组，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="94b8c-103">You can declare a single-dimensional array of five integers as shown in the following example:</span></span>  
  
 <span data-ttu-id="94b8c-104">[!code-cs[csProgGuideArrays#4](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="94b8c-104">[!code-cs[csProgGuideArrays#4](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_1.cs)]</span></span>  
  
 <span data-ttu-id="94b8c-105">此数组包含从 `array[0]` 到 `array[4]` 的元素。</span><span class="sxs-lookup"><span data-stu-id="94b8c-105">This array contains the elements from `array[0]` to `array[4]`.</span></span> <span data-ttu-id="94b8c-106">[new](../../../csharp/language-reference/keywords/new.md) 运算符用于创建数组并将数组元素初始化为其默认值。</span><span class="sxs-lookup"><span data-stu-id="94b8c-106">The [new](../../../csharp/language-reference/keywords/new.md) operator is used to create the array and initialize the array elements to their default values.</span></span> <span data-ttu-id="94b8c-107">在此示例中，所有数组元素都将被初始化为零。</span><span class="sxs-lookup"><span data-stu-id="94b8c-107">In this example, all the array elements are initialized to zero.</span></span>  
  
 <span data-ttu-id="94b8c-108">可使用相同方式声明存储字符串元素的数组。</span><span class="sxs-lookup"><span data-stu-id="94b8c-108">An array that stores string elements can be declared in the same way.</span></span> <span data-ttu-id="94b8c-109">例如: </span><span class="sxs-lookup"><span data-stu-id="94b8c-109">For example:</span></span>  
  
 <span data-ttu-id="94b8c-110">[!code-cs[csProgGuideArrays#5](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="94b8c-110">[!code-cs[csProgGuideArrays#5](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_2.cs)]</span></span>  
  
## <a name="array-initialization"></a><span data-ttu-id="94b8c-111">数组初始化</span><span class="sxs-lookup"><span data-stu-id="94b8c-111">Array Initialization</span></span>  
 <span data-ttu-id="94b8c-112">可以在声明时初始化数组，在这种情况下，无需秩说明符，因为它已由初始化列表中的元素数目提供。</span><span class="sxs-lookup"><span data-stu-id="94b8c-112">It is possible to initialize an array upon declaration, in which case, the rank specifier is not needed because it is already supplied by the number of elements in the initialization list.</span></span> <span data-ttu-id="94b8c-113">例如: </span><span class="sxs-lookup"><span data-stu-id="94b8c-113">For example:</span></span>  
  
 <span data-ttu-id="94b8c-114">[!code-cs[csProgGuideArrays#6](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="94b8c-114">[!code-cs[csProgGuideArrays#6](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_3.cs)]</span></span>  
  
 <span data-ttu-id="94b8c-115">可使用相同方式初始化字符串数组。</span><span class="sxs-lookup"><span data-stu-id="94b8c-115">A string array can be initialized in the same way.</span></span> <span data-ttu-id="94b8c-116">下面是一个字符串数组的声明，其中每个数组元素都由一天的名称初始化：</span><span class="sxs-lookup"><span data-stu-id="94b8c-116">The following is a declaration of a string array where each array element is initialized by a name of a day:</span></span>  
  
 <span data-ttu-id="94b8c-117">[!code-cs[csProgGuideArrays#7](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="94b8c-117">[!code-cs[csProgGuideArrays#7](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_4.cs)]</span></span>  
  
 <span data-ttu-id="94b8c-118">如果在声明时初始化数组，可以使用以下快捷方式：</span><span class="sxs-lookup"><span data-stu-id="94b8c-118">When you initialize an array upon declaration, you can use the following shortcuts:</span></span>  
  
 <span data-ttu-id="94b8c-119">[!code-cs[csProgGuideArrays#8](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="94b8c-119">[!code-cs[csProgGuideArrays#8](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_5.cs)]</span></span>  
  
 <span data-ttu-id="94b8c-120">可以在不初始化的情况下声明数组变量，但必须使用 `new` 运算符向此变量分配数组。</span><span class="sxs-lookup"><span data-stu-id="94b8c-120">It is possible to declare an array variable without initialization, but you must use the `new` operator when you assign an array to this variable.</span></span> <span data-ttu-id="94b8c-121">例如: </span><span class="sxs-lookup"><span data-stu-id="94b8c-121">For example:</span></span>  
  
 <span data-ttu-id="94b8c-122">[!code-cs[csProgGuideArrays#9](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_6.cs)]</span><span class="sxs-lookup"><span data-stu-id="94b8c-122">[!code-cs[csProgGuideArrays#9](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_6.cs)]</span></span>  
  
 <span data-ttu-id="94b8c-123">C# 3.0 引入了隐式类型化数组。</span><span class="sxs-lookup"><span data-stu-id="94b8c-123">C# 3.0 introduces implicitly typed arrays.</span></span> <span data-ttu-id="94b8c-124">有关详细信息，请参阅[隐式类型化数组](../../../csharp/programming-guide/arrays/implicitly-typed-arrays.md)。</span><span class="sxs-lookup"><span data-stu-id="94b8c-124">For more information, see [Implicitly Typed Arrays](../../../csharp/programming-guide/arrays/implicitly-typed-arrays.md).</span></span>  
  
## <a name="value-type-and-reference-type-arrays"></a><span data-ttu-id="94b8c-125">值类型和引用类型数组</span><span class="sxs-lookup"><span data-stu-id="94b8c-125">Value Type and Reference Type Arrays</span></span>  
 <span data-ttu-id="94b8c-126">请考虑以下数组声明：</span><span class="sxs-lookup"><span data-stu-id="94b8c-126">Consider the following array declaration:</span></span>  
  
 <span data-ttu-id="94b8c-127">[!code-cs[csProgGuideArrays#10](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_7.cs)]</span><span class="sxs-lookup"><span data-stu-id="94b8c-127">[!code-cs[csProgGuideArrays#10](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_7.cs)]</span></span>  
  
 <span data-ttu-id="94b8c-128">此语句的结果取决于 `SomeType` 是值类型还是引用类型。</span><span class="sxs-lookup"><span data-stu-id="94b8c-128">The result of this statement depends on whether `SomeType` is a value type or a reference type.</span></span> <span data-ttu-id="94b8c-129">如果它是值类型，该语句将创建一个 10 个元素的数组，其中每个元素的类型都为 `SomeType`。</span><span class="sxs-lookup"><span data-stu-id="94b8c-129">If it is a value type, the statement creates an array of 10 elements, each of which has the type `SomeType`.</span></span> <span data-ttu-id="94b8c-130">如果 `SomeType` 是引用类型，该语句将创建一个 10 个元素的数组，其中每个元素都将被初始化为空引用。</span><span class="sxs-lookup"><span data-stu-id="94b8c-130">If `SomeType` is a reference type, the statement creates an array of 10 elements, each of which is initialized to a null reference.</span></span>  
  
 <span data-ttu-id="94b8c-131">有关值类型和引用类型的详细信息，请参阅[类型](../../../csharp/language-reference/keywords/types.md)。</span><span class="sxs-lookup"><span data-stu-id="94b8c-131">For more information about value types and reference types, see [Types](../../../csharp/language-reference/keywords/types.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94b8c-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="94b8c-132">See Also</span></span>  
 <span data-ttu-id="94b8c-133"><xref:System.Array></span><span class="sxs-lookup"><span data-stu-id="94b8c-133"><xref:System.Array></span></span>   
 <span data-ttu-id="94b8c-134">[C# 编程指南](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="94b8c-134">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="94b8c-135">[数组](../../../csharp/programming-guide/arrays/index.md) </span><span class="sxs-lookup"><span data-stu-id="94b8c-135">[Arrays](../../../csharp/programming-guide/arrays/index.md) </span></span>  
 <span data-ttu-id="94b8c-136">[多维数组](../../../csharp/programming-guide/arrays/multidimensional-arrays.md) </span><span class="sxs-lookup"><span data-stu-id="94b8c-136">[Multidimensional Arrays](../../../csharp/programming-guide/arrays/multidimensional-arrays.md) </span></span>  
 [<span data-ttu-id="94b8c-137">交错数组</span><span class="sxs-lookup"><span data-stu-id="94b8c-137">Jagged Arrays</span></span>](../../../csharp/programming-guide/arrays/jagged-arrays.md)

