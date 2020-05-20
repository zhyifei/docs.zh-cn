---
title: 数组 - C# 编程指南
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [C#]
- C# language, arrays
ms.assetid: bb79bdde-e570-4c30-adb0-1dd5759ae041
ms.openlocfilehash: bbabc84c144e5b3415c19f346b890782e251662c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2020
ms.locfileid: "75715056"
---
# <a name="arrays-c-programming-guide"></a><span data-ttu-id="3b115-102">数组（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="3b115-102">Arrays (C# Programming Guide)</span></span>

<span data-ttu-id="3b115-103">可以将同一类型的多个变量存储在一个数组数据结构中。</span><span class="sxs-lookup"><span data-stu-id="3b115-103">You can store multiple variables of the same type in an array data structure.</span></span> <span data-ttu-id="3b115-104">通过指定数组的元素类型来声明数组。</span><span class="sxs-lookup"><span data-stu-id="3b115-104">You declare an array by specifying the type of its elements.</span></span> <span data-ttu-id="3b115-105">如果希望数组存储任意类型的元素，可将其类型指定为 `object`。</span><span class="sxs-lookup"><span data-stu-id="3b115-105">If you want the array to store elements of any type, you can specify `object` as its type.</span></span> <span data-ttu-id="3b115-106">在 C# 的统一类型系统中，所有类型（预定义类型、用户定义类型、引用类型和值类型）都是直接或间接从 <xref:System.Object> 继承的。</span><span class="sxs-lookup"><span data-stu-id="3b115-106">In the unified type system of C#, all types, predefined and user-defined, reference types and value types, inherit directly or indirectly from <xref:System.Object>.</span></span>

```csharp
type[] arrayName;
```

## <a name="example"></a><span data-ttu-id="3b115-107">示例</span><span class="sxs-lookup"><span data-stu-id="3b115-107">Example</span></span>

<span data-ttu-id="3b115-108">下面的示例创建一维数组、多维数组和交错数组：</span><span class="sxs-lookup"><span data-stu-id="3b115-108">The following example creates single-dimensional, multidimensional, and jagged arrays:</span></span>

[!code-csharp[csProgGuideArrays#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#1)]

## <a name="array-overview"></a><span data-ttu-id="3b115-109">数组概述</span><span class="sxs-lookup"><span data-stu-id="3b115-109">Array overview</span></span>

<span data-ttu-id="3b115-110">数组具有以下属性：</span><span class="sxs-lookup"><span data-stu-id="3b115-110">An array has the following properties:</span></span>

- <span data-ttu-id="3b115-111">数组可以是[一维](single-dimensional-arrays.md)、[多维](multidimensional-arrays.md)或[交错](jagged-arrays.md)的。</span><span class="sxs-lookup"><span data-stu-id="3b115-111">An array can be [Single-Dimensional](single-dimensional-arrays.md), [Multidimensional](multidimensional-arrays.md) or [Jagged](jagged-arrays.md).</span></span>
- <span data-ttu-id="3b115-112">创建数组实例时，将建立纬度数量和每个纬度的长度。</span><span class="sxs-lookup"><span data-stu-id="3b115-112">The number of dimensions and the length of each dimension are established when the array instance is created.</span></span> <span data-ttu-id="3b115-113">这些值在实例的生存期内无法更改。</span><span class="sxs-lookup"><span data-stu-id="3b115-113">These values can't be changed during the lifetime of the instance.</span></span>
- <span data-ttu-id="3b115-114">数值数组元素的默认值设置为零，而引用元素设置为 null。</span><span class="sxs-lookup"><span data-stu-id="3b115-114">The default values of numeric array elements are set to zero, and reference elements are set to null.</span></span>
- <span data-ttu-id="3b115-115">交错数组是数组的数组，因此其元素为引用类型且被初始化为 `null`。</span><span class="sxs-lookup"><span data-stu-id="3b115-115">A jagged array is an array of arrays, and therefore its elements are reference types and are initialized to `null`.</span></span>
- <span data-ttu-id="3b115-116">数组从零开始编制索引：包含 `n` 元素的数组从 `0` 索引到 `n-1`。</span><span class="sxs-lookup"><span data-stu-id="3b115-116">Arrays are zero indexed: an array with `n` elements is indexed from `0` to `n-1`.</span></span>
- <span data-ttu-id="3b115-117">数组元素可以是任何类型，其中包括数组类型。</span><span class="sxs-lookup"><span data-stu-id="3b115-117">Array elements can be of any type, including an array type.</span></span>
- <span data-ttu-id="3b115-118">数组类型是从抽象的基类型 <xref:System.Array> 派生的[引用类型](../../language-reference/keywords/reference-types.md)。</span><span class="sxs-lookup"><span data-stu-id="3b115-118">Array types are [reference types](../../language-reference/keywords/reference-types.md) derived from the abstract base type <xref:System.Array>.</span></span> <span data-ttu-id="3b115-119">由于此类型实现 <xref:System.Collections.IEnumerable> 和 <xref:System.Collections.Generic.IEnumerable%601>，因此可以在 C# 中的所有数组上使用 [foreach](../../language-reference/keywords/foreach-in.md) 迭代。</span><span class="sxs-lookup"><span data-stu-id="3b115-119">Since this type implements <xref:System.Collections.IEnumerable> and <xref:System.Collections.Generic.IEnumerable%601>, you can use [foreach](../../language-reference/keywords/foreach-in.md) iteration on all arrays in C#.</span></span>

## <a name="related-sections"></a><span data-ttu-id="3b115-120">相关章节</span><span class="sxs-lookup"><span data-stu-id="3b115-120">Related sections</span></span>

- [<span data-ttu-id="3b115-121">作为对象的数组</span><span class="sxs-lookup"><span data-stu-id="3b115-121">Arrays as Objects</span></span>](arrays-as-objects.md)
- [<span data-ttu-id="3b115-122">对数组使用 foreach</span><span class="sxs-lookup"><span data-stu-id="3b115-122">Using foreach with Arrays</span></span>](using-foreach-with-arrays.md)
- [<span data-ttu-id="3b115-123">将数组作为参数传递</span><span class="sxs-lookup"><span data-stu-id="3b115-123">Passing Arrays as Arguments</span></span>](passing-arrays-as-arguments.md)

## <a name="c-language-specification"></a><span data-ttu-id="3b115-124">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="3b115-124">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="3b115-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3b115-125">See also</span></span>

- [<span data-ttu-id="3b115-126">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="3b115-126">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="3b115-127">集合</span><span class="sxs-lookup"><span data-stu-id="3b115-127">Collections</span></span>](../concepts/collections.md)
