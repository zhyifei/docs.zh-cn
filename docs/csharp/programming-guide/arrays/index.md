---
title: "数组（C# 编程指南）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- arrays [C#]
- C# language, arrays
ms.assetid: bb79bdde-e570-4c30-adb0-1dd5759ae041
caps.latest.revision: 33
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
ms.openlocfilehash: 1035caae15b64d1311305cfe4c1f1a74c80ed19a
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="arrays-c-programming-guide"></a><span data-ttu-id="f15fd-102">数组（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="f15fd-102">Arrays (C# Programming Guide)</span></span>
<span data-ttu-id="f15fd-103">可以将同一类型的多个变量存储在一个数组数据结构中。</span><span class="sxs-lookup"><span data-stu-id="f15fd-103">You can store multiple variables of the same type in an array data structure.</span></span> <span data-ttu-id="f15fd-104">通过指定数组的元素类型来声明数组。</span><span class="sxs-lookup"><span data-stu-id="f15fd-104">You declare an array by specifying the type of its elements.</span></span>  
  
 `type[] arrayName;`  
  
 <span data-ttu-id="f15fd-105">以下示例创建一维、多维和交错数组：</span><span class="sxs-lookup"><span data-stu-id="f15fd-105">The following examples create single-dimensional, multidimensional, and jagged arrays:</span></span>  
  
 <span data-ttu-id="f15fd-106">[!code-cs[csProgGuideArrays#1](../../../csharp/programming-guide/arrays/codesnippet/CSharp/index_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="f15fd-106">[!code-cs[csProgGuideArrays#1](../../../csharp/programming-guide/arrays/codesnippet/CSharp/index_1.cs)]</span></span>  
  
## <a name="array-overview"></a><span data-ttu-id="f15fd-107">数组概述</span><span class="sxs-lookup"><span data-stu-id="f15fd-107">Array Overview</span></span>  
 <span data-ttu-id="f15fd-108">数组具有以下属性：</span><span class="sxs-lookup"><span data-stu-id="f15fd-108">An array has the following properties:</span></span>  
  
-   <span data-ttu-id="f15fd-109">数组可以是[一维](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md)、[多维](../../../csharp/programming-guide/arrays/multidimensional-arrays.md)或[交错](../../../csharp/programming-guide/arrays/jagged-arrays.md)的。</span><span class="sxs-lookup"><span data-stu-id="f15fd-109">An array can be [Single-Dimensional](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md), [Multidimensional](../../../csharp/programming-guide/arrays/multidimensional-arrays.md) or [Jagged](../../../csharp/programming-guide/arrays/jagged-arrays.md).</span></span>  
  
-   <span data-ttu-id="f15fd-110">创建数组实例时，将建立纬度数量和每个纬度的长度。</span><span class="sxs-lookup"><span data-stu-id="f15fd-110">The number of dimensions and the length of each dimension are established when the array instance is created.</span></span> <span data-ttu-id="f15fd-111">这些值在实例的生存期内无法更改。</span><span class="sxs-lookup"><span data-stu-id="f15fd-111">These values can't be changed during the lifetime of the instance.</span></span>  
  
-   <span data-ttu-id="f15fd-112">数值数组元素的默认值设置为零，而引用元素设置为 null。</span><span class="sxs-lookup"><span data-stu-id="f15fd-112">The default values of numeric array elements are set to zero, and reference elements are set to null.</span></span>  
  
-   <span data-ttu-id="f15fd-113">交错数组是数组的数组，因此其元素为引用类型且被初始化为 `null`。</span><span class="sxs-lookup"><span data-stu-id="f15fd-113">A jagged array is an array of arrays, and therefore its elements are reference types and are initialized to `null`.</span></span>  
  
-   <span data-ttu-id="f15fd-114">数组从零开始编制索引：包含 `n` 元素的数组从 `0` 索引到 `n-1`。</span><span class="sxs-lookup"><span data-stu-id="f15fd-114">Arrays are zero indexed: an array with `n` elements is indexed from `0` to `n-1`.</span></span>  
  
-   <span data-ttu-id="f15fd-115">数组元素可以是任何类型，其中包括数组类型。</span><span class="sxs-lookup"><span data-stu-id="f15fd-115">Array elements can be of any type, including an array type.</span></span>  
  
-   <span data-ttu-id="f15fd-116">数组类型是从抽象的基类型 <xref:System.Array> 派生的[引用类型](../../../csharp/language-reference/keywords/reference-types.md)。</span><span class="sxs-lookup"><span data-stu-id="f15fd-116">Array types are [reference types](../../../csharp/language-reference/keywords/reference-types.md) derived from the abstract base type <xref:System.Array>.</span></span> <span data-ttu-id="f15fd-117">由于此类型实现 <xref:System.Collections.IEnumerable> 和 <xref:System.Collections.Generic.IEnumerable%601>，因此可以在 C# 中的所有数组上使用 [foreach](../../../csharp/language-reference/keywords/foreach-in.md) 迭代。</span><span class="sxs-lookup"><span data-stu-id="f15fd-117">Since this type implements <xref:System.Collections.IEnumerable> and <xref:System.Collections.Generic.IEnumerable%601>, you can use [foreach](../../../csharp/language-reference/keywords/foreach-in.md) iteration on all arrays in C#.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="f15fd-118">相关章节</span><span class="sxs-lookup"><span data-stu-id="f15fd-118">Related Sections</span></span>  
  
-   [<span data-ttu-id="f15fd-119">作为对象的数组</span><span class="sxs-lookup"><span data-stu-id="f15fd-119">Arrays as Objects</span></span>](../../../csharp/programming-guide/arrays/arrays-as-objects.md)  
  
-   [<span data-ttu-id="f15fd-120">对数组使用 foreach</span><span class="sxs-lookup"><span data-stu-id="f15fd-120">Using foreach with Arrays</span></span>](../../../csharp/programming-guide/arrays/using-foreach-with-arrays.md)  
  
-   [<span data-ttu-id="f15fd-121">将数组作为参数传递</span><span class="sxs-lookup"><span data-stu-id="f15fd-121">Passing Arrays as Arguments</span></span>](../../../csharp/programming-guide/arrays/passing-arrays-as-arguments.md)  
  
-   [<span data-ttu-id="f15fd-122">使用 ref 和 out 传递数组</span><span class="sxs-lookup"><span data-stu-id="f15fd-122">Passing Arrays Using ref and out</span></span>](../../../csharp/programming-guide/arrays/passing-arrays-using-ref-and-out.md)   
  
## <a name="c-language-specification"></a><span data-ttu-id="f15fd-123">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="f15fd-123">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f15fd-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="f15fd-124">See Also</span></span>  
 <span data-ttu-id="f15fd-125">[C# 编程指南](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="f15fd-125">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="f15fd-126">[集合](http://msdn.microsoft.com/library/e76533a9-5033-4a0b-b003-9c2be60d185b) </span><span class="sxs-lookup"><span data-stu-id="f15fd-126">[Collections](http://msdn.microsoft.com/library/e76533a9-5033-4a0b-b003-9c2be60d185b) </span></span>  
 [<span data-ttu-id="f15fd-127">数组集合类型</span><span class="sxs-lookup"><span data-stu-id="f15fd-127">Array Collection Type</span></span>](http://msdn.microsoft.com/en-us/8a9964de-8941-47b1-a3cf-a01bc88db9e8)

