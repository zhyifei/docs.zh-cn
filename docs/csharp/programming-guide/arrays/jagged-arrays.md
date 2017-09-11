---
title: "交错数组（C# 编程指南）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- jagged arrays [C#]
- arrays [C#], jagged
ms.assetid: 537c65a6-0e0a-4a00-a2b8-086f38519c70
caps.latest.revision: 24
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
ms.openlocfilehash: cb6c0823af37924235dba7daa20e607cb8402a79
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="jagged-arrays-c-programming-guide"></a><span data-ttu-id="8cc7b-102">交错数组（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="8cc7b-102">Jagged Arrays (C# Programming Guide)</span></span>
<span data-ttu-id="8cc7b-103">交错数组是元素为数组的数组。</span><span class="sxs-lookup"><span data-stu-id="8cc7b-103">A jagged array is an array whose elements are arrays.</span></span> <span data-ttu-id="8cc7b-104">交错数组元素的维度和大小可以不同。</span><span class="sxs-lookup"><span data-stu-id="8cc7b-104">The elements of a jagged array can be of different dimensions and sizes.</span></span> <span data-ttu-id="8cc7b-105">交错数组有时称为“数组的数组”。</span><span class="sxs-lookup"><span data-stu-id="8cc7b-105">A jagged array is sometimes called an "array of arrays."</span></span> <span data-ttu-id="8cc7b-106">以下示例说明如何声明、初始化和访问交错数组。</span><span class="sxs-lookup"><span data-stu-id="8cc7b-106">The following examples show how to declare, initialize, and access jagged arrays.</span></span>  
  
 <span data-ttu-id="8cc7b-107">下面声明一个具有三个元素的一维数组，其中每个元素都是一维整数数组：</span><span class="sxs-lookup"><span data-stu-id="8cc7b-107">The following is a declaration of a single-dimensional array that has three elements, each of which is a single-dimensional array of integers:</span></span>  
  
 <span data-ttu-id="8cc7b-108">[!code-cs[csProgGuideArrays#19](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="8cc7b-108">[!code-cs[csProgGuideArrays#19](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_1.cs)]</span></span>  
  
 <span data-ttu-id="8cc7b-109">必须初始化 `jaggedArray` 的元素后才可使用它。</span><span class="sxs-lookup"><span data-stu-id="8cc7b-109">Before you can use `jaggedArray`, its elements must be initialized.</span></span> <span data-ttu-id="8cc7b-110">可按下方操作初始化元素：</span><span class="sxs-lookup"><span data-stu-id="8cc7b-110">You can initialize the elements like this:</span></span>  
  
 <span data-ttu-id="8cc7b-111">[!code-cs[csProgGuideArrays#20](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="8cc7b-111">[!code-cs[csProgGuideArrays#20](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_2.cs)]</span></span>  
  
 <span data-ttu-id="8cc7b-112">每个元素都是一维整数数组。</span><span class="sxs-lookup"><span data-stu-id="8cc7b-112">Each of the elements is a single-dimensional array of integers.</span></span> <span data-ttu-id="8cc7b-113">第一个元素是由 5 个整数组成的数组，第二个是由 4 个整数组成的数组，而第三个是由 2 个整数组成的数组。</span><span class="sxs-lookup"><span data-stu-id="8cc7b-113">The first element is an array of 5 integers, the second is an array of 4 integers, and the third is an array of 2 integers.</span></span>  
  
 <span data-ttu-id="8cc7b-114">也可使用初始化表达式通过值来填充数组元素，这种情况下不需要数组大小。</span><span class="sxs-lookup"><span data-stu-id="8cc7b-114">It is also possible to use initializers to fill the array elements with values, in which case you do not need the array size.</span></span> <span data-ttu-id="8cc7b-115">例如: </span><span class="sxs-lookup"><span data-stu-id="8cc7b-115">For example:</span></span>  
  
 <span data-ttu-id="8cc7b-116">[!code-cs[csProgGuideArrays#21](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="8cc7b-116">[!code-cs[csProgGuideArrays#21](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_3.cs)]</span></span>  
  
 <span data-ttu-id="8cc7b-117">还可在声明数组时将其初始化，如：</span><span class="sxs-lookup"><span data-stu-id="8cc7b-117">You can also initialize the array upon declaration like this:</span></span>  
  
 <span data-ttu-id="8cc7b-118">[!code-cs[csProgGuideArrays#22](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="8cc7b-118">[!code-cs[csProgGuideArrays#22](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_4.cs)]</span></span>  
  
 <span data-ttu-id="8cc7b-119">可以使用下面的缩写形式。</span><span class="sxs-lookup"><span data-stu-id="8cc7b-119">You can use the following shorthand form.</span></span> <span data-ttu-id="8cc7b-120">请注意：不能从元素初始化中省略 `new` 运算符，因为不存在元素的默认初始化：</span><span class="sxs-lookup"><span data-stu-id="8cc7b-120">Notice that you cannot omit the `new` operator from the elements initialization because there is no default initialization for the elements:</span></span>  
  
 <span data-ttu-id="8cc7b-121">[!code-cs[csProgGuideArrays#23](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="8cc7b-121">[!code-cs[csProgGuideArrays#23](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_5.cs)]</span></span>  
  
 <span data-ttu-id="8cc7b-122">交错数组是数组的数组，因此其元素为引用类型且被初始化为 `null`。</span><span class="sxs-lookup"><span data-stu-id="8cc7b-122">A jagged array is an array of arrays, and therefore its elements are reference types and are initialized to `null`.</span></span>  
  
 <span data-ttu-id="8cc7b-123">可以如下例所示访问个别数组元素：</span><span class="sxs-lookup"><span data-stu-id="8cc7b-123">You can access individual array elements like these examples:</span></span>  
  
 <span data-ttu-id="8cc7b-124">[!code-cs[csProgGuideArrays#24](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_6.cs)]</span><span class="sxs-lookup"><span data-stu-id="8cc7b-124">[!code-cs[csProgGuideArrays#24](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_6.cs)]</span></span>  
  
 <span data-ttu-id="8cc7b-125">可以混合使用交错数组和多维数组。</span><span class="sxs-lookup"><span data-stu-id="8cc7b-125">It is possible to mix jagged and multidimensional arrays.</span></span> <span data-ttu-id="8cc7b-126">下面声明和初始化一个包含大小不同的三个二维数组元素的一维交错数组。</span><span class="sxs-lookup"><span data-stu-id="8cc7b-126">The following is a declaration and initialization of a single-dimensional jagged array that contains three two-dimensional array elements of different sizes.</span></span> <span data-ttu-id="8cc7b-127">有关二维数组的详细信息，请参阅[多维数组](../../../csharp/programming-guide/arrays/multidimensional-arrays.md)。</span><span class="sxs-lookup"><span data-stu-id="8cc7b-127">For more information about two-dimensional arrays, see [Multidimensional Arrays](../../../csharp/programming-guide/arrays/multidimensional-arrays.md).</span></span>  
  
 <span data-ttu-id="8cc7b-128">[!code-cs[csProgGuideArrays#25](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_7.cs)]</span><span class="sxs-lookup"><span data-stu-id="8cc7b-128">[!code-cs[csProgGuideArrays#25](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_7.cs)]</span></span>  
  
 <span data-ttu-id="8cc7b-129">可以如本例所示访问个别元素，示例显示第一个数组的元素 `[1,0]` 的值（值为 `5`）：</span><span class="sxs-lookup"><span data-stu-id="8cc7b-129">You can access individual elements as shown in this example, which displays the value of the element `[1,0]` of the first array (value `5`):</span></span>  
  
 <span data-ttu-id="8cc7b-130">[!code-cs[csProgGuideArrays#26](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_8.cs)]</span><span class="sxs-lookup"><span data-stu-id="8cc7b-130">[!code-cs[csProgGuideArrays#26](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_8.cs)]</span></span>  
  
 <span data-ttu-id="8cc7b-131">方法 `Length` 返回包含在交错数组中的数组的数目。</span><span class="sxs-lookup"><span data-stu-id="8cc7b-131">The method `Length` returns the number of arrays contained in the jagged array.</span></span> <span data-ttu-id="8cc7b-132">例如，假定已声明了前一个数组，则此行：</span><span class="sxs-lookup"><span data-stu-id="8cc7b-132">For example, assuming you have declared the previous array, this line:</span></span>  
  
 <span data-ttu-id="8cc7b-133">[!code-cs[csProgGuideArrays#27](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_9.cs)]</span><span class="sxs-lookup"><span data-stu-id="8cc7b-133">[!code-cs[csProgGuideArrays#27](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_9.cs)]</span></span>  
  
 <span data-ttu-id="8cc7b-134">返回值 3。</span><span class="sxs-lookup"><span data-stu-id="8cc7b-134">returns a value of 3.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8cc7b-135">示例</span><span class="sxs-lookup"><span data-stu-id="8cc7b-135">Example</span></span>  
 <span data-ttu-id="8cc7b-136">本例生成一个数组，该数组的元素为数组自身。</span><span class="sxs-lookup"><span data-stu-id="8cc7b-136">This example builds an array whose elements are themselves arrays.</span></span> <span data-ttu-id="8cc7b-137">每一个数组元素都有不同的大小。</span><span class="sxs-lookup"><span data-stu-id="8cc7b-137">Each one of the array elements has a different size.</span></span>  
  
 <span data-ttu-id="8cc7b-138">[!code-cs[csProgGuideArrays#18](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_10.cs)]</span><span class="sxs-lookup"><span data-stu-id="8cc7b-138">[!code-cs[csProgGuideArrays#18](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_10.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8cc7b-139">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8cc7b-139">See Also</span></span>  
 <span data-ttu-id="8cc7b-140"><xref:System.Array></span><span class="sxs-lookup"><span data-stu-id="8cc7b-140"><xref:System.Array></span></span>   
 <span data-ttu-id="8cc7b-141">[C# 编程指南](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="8cc7b-141">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="8cc7b-142">[数组](../../../csharp/programming-guide/arrays/index.md) </span><span class="sxs-lookup"><span data-stu-id="8cc7b-142">[Arrays](../../../csharp/programming-guide/arrays/index.md) </span></span>  
 <span data-ttu-id="8cc7b-143">[一维数组](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md) </span><span class="sxs-lookup"><span data-stu-id="8cc7b-143">[Single-Dimensional Arrays](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md) </span></span>  
 [<span data-ttu-id="8cc7b-144">多维数组</span><span class="sxs-lookup"><span data-stu-id="8cc7b-144">Multidimensional Arrays</span></span>](../../../csharp/programming-guide/arrays/multidimensional-arrays.md)

