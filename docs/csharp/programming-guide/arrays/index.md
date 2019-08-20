---
title: 数组 - C# 编程指南
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [C#]
- C# language, arrays
ms.assetid: bb79bdde-e570-4c30-adb0-1dd5759ae041
ms.openlocfilehash: 24c6d54c3fe92ada661e732adec582e87ab62417
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/19/2019
ms.locfileid: "69597527"
---
# <a name="arrays-c-programming-guide"></a><span data-ttu-id="bd381-102">数组（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="bd381-102">Arrays (C# Programming Guide)</span></span>

<span data-ttu-id="bd381-103">可以将同一类型的多个变量存储在一个数组数据结构中。</span><span class="sxs-lookup"><span data-stu-id="bd381-103">You can store multiple variables of the same type in an array data structure.</span></span> <span data-ttu-id="bd381-104">通过指定数组的元素类型来声明数组。</span><span class="sxs-lookup"><span data-stu-id="bd381-104">You declare an array by specifying the type of its elements.</span></span>  
  
 `type[] arrayName;`  
  
 <span data-ttu-id="bd381-105">下面的示例创建一维数组、多维数组和交错数组：</span><span class="sxs-lookup"><span data-stu-id="bd381-105">The following example creates single-dimensional, multidimensional, and jagged arrays:</span></span>  
  
 [!code-csharp[csProgGuideArrays#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#1)]  
  
## <a name="array-overview"></a><span data-ttu-id="bd381-106">数组概述</span><span class="sxs-lookup"><span data-stu-id="bd381-106">Array Overview</span></span>

 <span data-ttu-id="bd381-107">数组具有以下属性：</span><span class="sxs-lookup"><span data-stu-id="bd381-107">An array has the following properties:</span></span>  
  
- <span data-ttu-id="bd381-108">数组可以是[一维](./single-dimensional-arrays.md)、[多维](./multidimensional-arrays.md)或[交错](./jagged-arrays.md)的。</span><span class="sxs-lookup"><span data-stu-id="bd381-108">An array can be [Single-Dimensional](./single-dimensional-arrays.md), [Multidimensional](./multidimensional-arrays.md) or [Jagged](./jagged-arrays.md).</span></span>  
  
- <span data-ttu-id="bd381-109">创建数组实例时，将建立纬度数量和每个纬度的长度。</span><span class="sxs-lookup"><span data-stu-id="bd381-109">The number of dimensions and the length of each dimension are established when the array instance is created.</span></span> <span data-ttu-id="bd381-110">这些值在实例的生存期内无法更改。</span><span class="sxs-lookup"><span data-stu-id="bd381-110">These values can't be changed during the lifetime of the instance.</span></span>  
  
- <span data-ttu-id="bd381-111">数值数组元素的默认值设置为零，而引用元素设置为 null。</span><span class="sxs-lookup"><span data-stu-id="bd381-111">The default values of numeric array elements are set to zero, and reference elements are set to null.</span></span>  
  
- <span data-ttu-id="bd381-112">交错数组是数组的数组，因此其元素为引用类型且被初始化为 `null`。</span><span class="sxs-lookup"><span data-stu-id="bd381-112">A jagged array is an array of arrays, and therefore its elements are reference types and are initialized to `null`.</span></span>  
  
- <span data-ttu-id="bd381-113">数组从零开始编制索引：包含 `n` 元素的数组从 `0` 索引到 `n-1`。</span><span class="sxs-lookup"><span data-stu-id="bd381-113">Arrays are zero indexed: an array with `n` elements is indexed from `0` to `n-1`.</span></span>  
  
- <span data-ttu-id="bd381-114">数组元素可以是任何类型，其中包括数组类型。</span><span class="sxs-lookup"><span data-stu-id="bd381-114">Array elements can be of any type, including an array type.</span></span>  
  
- <span data-ttu-id="bd381-115">数组类型是从抽象的基类型 <xref:System.Array> 派生的[引用类型](../../language-reference/keywords/reference-types.md)。</span><span class="sxs-lookup"><span data-stu-id="bd381-115">Array types are [reference types](../../language-reference/keywords/reference-types.md) derived from the abstract base type <xref:System.Array>.</span></span> <span data-ttu-id="bd381-116">由于此类型实现 <xref:System.Collections.IEnumerable> 和 <xref:System.Collections.Generic.IEnumerable%601>，因此可以在 C# 中的所有数组上使用 [foreach](../../language-reference/keywords/foreach-in.md) 迭代。</span><span class="sxs-lookup"><span data-stu-id="bd381-116">Since this type implements <xref:System.Collections.IEnumerable> and <xref:System.Collections.Generic.IEnumerable%601>, you can use [foreach](../../language-reference/keywords/foreach-in.md) iteration on all arrays in C#.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="bd381-117">相关章节</span><span class="sxs-lookup"><span data-stu-id="bd381-117">Related Sections</span></span>  
  
- [<span data-ttu-id="bd381-118">作为对象的数组</span><span class="sxs-lookup"><span data-stu-id="bd381-118">Arrays as Objects</span></span>](./arrays-as-objects.md)  
  
- [<span data-ttu-id="bd381-119">对数组使用 foreach</span><span class="sxs-lookup"><span data-stu-id="bd381-119">Using foreach with Arrays</span></span>](./using-foreach-with-arrays.md)  
  
- [<span data-ttu-id="bd381-120">将数组作为参数传递</span><span class="sxs-lookup"><span data-stu-id="bd381-120">Passing Arrays as Arguments</span></span>](./passing-arrays-as-arguments.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="bd381-121">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="bd381-121">C# Language Specification</span></span>

 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="bd381-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="bd381-122">See also</span></span>

- [<span data-ttu-id="bd381-123">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="bd381-123">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="bd381-124">集合</span><span class="sxs-lookup"><span data-stu-id="bd381-124">Collections</span></span>](../concepts/collections.md)
