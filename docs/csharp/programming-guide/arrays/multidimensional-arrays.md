---
title: 多维数组（C# 编程指南）
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [C#], multidimensional
- multidimensional arrays [C#]
ms.assetid: 020ce02e-7dff-4273-8e53-bf0b33747232
ms.openlocfilehash: a1d7a0a014c330682316e869f6727082fa3b31ef
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/24/2018
ms.locfileid: "47027076"
---
# <a name="multidimensional-arrays-c-programming-guide"></a><span data-ttu-id="13bac-102">多维数组（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="13bac-102">Multidimensional Arrays (C# Programming Guide)</span></span>

<span data-ttu-id="13bac-103">数组可具有多个维度。</span><span class="sxs-lookup"><span data-stu-id="13bac-103">Arrays can have more than one dimension.</span></span> <span data-ttu-id="13bac-104">例如，以下声明创建一个具有四行两列的二维数组。</span><span class="sxs-lookup"><span data-stu-id="13bac-104">For example, the following declaration creates a two-dimensional array of four rows and two columns.</span></span>  
  
 [!code-csharp[csProgGuideArrays#11](../../../csharp/programming-guide/arrays/codesnippet/CSharp/multidimensional-arrays_1.cs)]  
  
 <span data-ttu-id="13bac-105">以下声明创建一个具有三个维度（4、2 和 3）的数组。</span><span class="sxs-lookup"><span data-stu-id="13bac-105">The following declaration creates an array of three dimensions, 4, 2, and 3.</span></span>  
  
 [!code-csharp[csProgGuideArrays#12](../../../csharp/programming-guide/arrays/codesnippet/CSharp/multidimensional-arrays_2.cs)]  
  
## <a name="array-initialization"></a><span data-ttu-id="13bac-106">数组初始化</span><span class="sxs-lookup"><span data-stu-id="13bac-106">Array Initialization</span></span>

 <span data-ttu-id="13bac-107">声明后即可初始化数组，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="13bac-107">You can initialize the array upon declaration, as is shown in the following example.</span></span>  
  
 [!code-csharp[csProgGuideArrays#13](../../../csharp/programming-guide/arrays/codesnippet/CSharp/multidimensional-arrays_3.cs)]  
  
 <span data-ttu-id="13bac-108">还可在不指定秩的情况下初始化数组。</span><span class="sxs-lookup"><span data-stu-id="13bac-108">You also can initialize the array without specifying the rank.</span></span>  
  
 [!code-csharp[csProgGuideArrays#14](../../../csharp/programming-guide/arrays/codesnippet/CSharp/multidimensional-arrays_4.cs)]  
  
 <span data-ttu-id="13bac-109">如果选择在不初始化的情况下声明数组变量，则必须使用 `new` 运算符将数组赋予变量。</span><span class="sxs-lookup"><span data-stu-id="13bac-109">If you choose to declare an array variable without initialization, you must use the `new` operator to assign an array to the variable.</span></span> <span data-ttu-id="13bac-110">`new` 的用法如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="13bac-110">The use of `new` is shown in the following example.</span></span>  
  
 [!code-csharp[csProgGuideArrays#15](../../../csharp/programming-guide/arrays/codesnippet/CSharp/multidimensional-arrays_5.cs)]  
  
 <span data-ttu-id="13bac-111">以下示例将值赋予特定的数组元素。</span><span class="sxs-lookup"><span data-stu-id="13bac-111">The following example assigns a value to a particular array element.</span></span>  
  
 [!code-csharp[csProgGuideArrays#16](../../../csharp/programming-guide/arrays/codesnippet/CSharp/multidimensional-arrays_6.cs)]  
  
 <span data-ttu-id="13bac-112">同样，以下示例将获取特定数组元素的值并将其赋予变量 `elementValue`。</span><span class="sxs-lookup"><span data-stu-id="13bac-112">Similarly, the following example gets the value of a particular array element and assigns it to variable `elementValue`.</span></span>  
  
 [!code-csharp[csProgGuideArrays#42](../../../csharp/programming-guide/arrays/codesnippet/CSharp/multidimensional-arrays_7.cs)]  
  
 <span data-ttu-id="13bac-113">以下代码示例将数组元素初始化为默认值（交错数组除外）。</span><span class="sxs-lookup"><span data-stu-id="13bac-113">The following code example initializes the array elements to default values (except for jagged arrays).</span></span>  
  
 [!code-csharp[csProgGuideArrays#17](../../../csharp/programming-guide/arrays/codesnippet/CSharp/multidimensional-arrays_8.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="13bac-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="13bac-114">See Also</span></span>

- [<span data-ttu-id="13bac-115">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="13bac-115">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="13bac-116">数组</span><span class="sxs-lookup"><span data-stu-id="13bac-116">Arrays</span></span>](../../../csharp/programming-guide/arrays/index.md)  
- [<span data-ttu-id="13bac-117">一维数组</span><span class="sxs-lookup"><span data-stu-id="13bac-117">Single-Dimensional Arrays</span></span>](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md)  
- [<span data-ttu-id="13bac-118">交错数组</span><span class="sxs-lookup"><span data-stu-id="13bac-118">Jagged Arrays</span></span>](../../../csharp/programming-guide/arrays/jagged-arrays.md)
