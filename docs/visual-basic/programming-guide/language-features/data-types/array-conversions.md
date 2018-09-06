---
title: 数组转换 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [Visual Basic], converting type
- type conversion [Visual Basic], arrays
- conversions [Visual Basic], type
- arrays [Visual Basic], data types
- conversions [Visual Basic], data type
- object arrays [Visual Basic], converting type
- data type conversion [Visual Basic], array conversions
- conversions [Visual Basic], array types
- object arrays
ms.assetid: fceff7d2-a1b7-44c7-b9aa-8bd831d8a444
ms.openlocfilehash: 93e6365a70f52f730b016cd4d4ac9382baeeba55
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/05/2018
ms.locfileid: "43784870"
---
# <a name="array-conversions-visual-basic"></a><span data-ttu-id="35214-102">数组转换 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="35214-102">Array Conversions (Visual Basic)</span></span>
<span data-ttu-id="35214-103">可以将数组类型转换为另一个数组类型，但必须满足以下条件：</span><span class="sxs-lookup"><span data-stu-id="35214-103">You can convert an array type to a different array type provided you meet the following conditions:</span></span>  
  
-   <span data-ttu-id="35214-104">**秩相等。**</span><span class="sxs-lookup"><span data-stu-id="35214-104">**Equal Rank.**</span></span> <span data-ttu-id="35214-105">两个数组的秩必须相同，即，它们必须具有相同数量的维度。</span><span class="sxs-lookup"><span data-stu-id="35214-105">The ranks of the two arrays must be the same, that is, they must have the same number of dimensions.</span></span> <span data-ttu-id="35214-106">但是，不需要的相应维度的长度相同。</span><span class="sxs-lookup"><span data-stu-id="35214-106">However, the lengths of the respective dimensions do not need to be the same.</span></span>  
  
-   <span data-ttu-id="35214-107">**元素数据类型。**</span><span class="sxs-lookup"><span data-stu-id="35214-107">**Element Data Type.**</span></span> <span data-ttu-id="35214-108">这两个数组的元素的数据类型必须是引用类型。</span><span class="sxs-lookup"><span data-stu-id="35214-108">The data types of the elements of both arrays must be reference types.</span></span> <span data-ttu-id="35214-109">你不能转换`Integer`到数组`Long`数组，或者甚至到`Object`，因为涉及至少一个值类型数组。</span><span class="sxs-lookup"><span data-stu-id="35214-109">You cannot convert an `Integer` array to a `Long` array, or even to an `Object` array, because at least one value type is involved.</span></span> <span data-ttu-id="35214-110">有关详细信息，请参阅[值类型和引用类型](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)。</span><span class="sxs-lookup"><span data-stu-id="35214-110">For more information, see [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md).</span></span>  
  
-   <span data-ttu-id="35214-111">**支持。**</span><span class="sxs-lookup"><span data-stu-id="35214-111">**Convertibility.**</span></span> <span data-ttu-id="35214-112">扩大或收缩转换时，必须是两个数组的元素类型之间可能的。</span><span class="sxs-lookup"><span data-stu-id="35214-112">A conversion, either widening or narrowing, must be possible between the element types of the two arrays.</span></span> <span data-ttu-id="35214-113">符合此要求的一个示例是之间尝试执行的转换`String`数组和数组的类派生自<xref:System.Attribute?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="35214-113">An example that fails this requirement is an attempted conversion between a `String` array and an array of a class derived from <xref:System.Attribute?displayProperty=nameWithType>.</span></span> <span data-ttu-id="35214-114">这两种类型迥然不同，并且它们之间不存在任何类型的转换。</span><span class="sxs-lookup"><span data-stu-id="35214-114">These two types have nothing in common, and no conversion of any kind exists between them.</span></span>  
  
 <span data-ttu-id="35214-115">一个数组类型转换为另一个是扩大转换或收缩具体取决于是否扩大或收缩的相应元素的转换。</span><span class="sxs-lookup"><span data-stu-id="35214-115">A conversion of one array type to another is widening or narrowing depending on whether the conversion of the respective elements is widening or narrowing.</span></span> <span data-ttu-id="35214-116">有关详细信息，请参阅 [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)。</span><span class="sxs-lookup"><span data-stu-id="35214-116">For more information, see [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).</span></span>  
  
## <a name="conversion-to-an-object-array"></a><span data-ttu-id="35214-117">转换为对象数组</span><span class="sxs-lookup"><span data-stu-id="35214-117">Conversion to an Object Array</span></span>  
 <span data-ttu-id="35214-118">当你声明`Object`而无需初始化它，其元素类型的数组是`Object`，只要它保持未初始化。</span><span class="sxs-lookup"><span data-stu-id="35214-118">When you declare an `Object` array without initializing it, its element type is `Object` as long as it remains uninitialized.</span></span> <span data-ttu-id="35214-119">当将其设置为特定类的数组时，它将采用该类的类型。</span><span class="sxs-lookup"><span data-stu-id="35214-119">When you set it to an array of a specific class, it takes on the type of that class.</span></span> <span data-ttu-id="35214-120">但是，其基础类型仍是`Object`，随后可以将其设置为一个不相关的类的另一个数组。</span><span class="sxs-lookup"><span data-stu-id="35214-120">However, its underlying type is still `Object`, and you can subsequently set it to another array of an unrelated class.</span></span> <span data-ttu-id="35214-121">由于所有类都派生自`Object`，可以从任何类更改数组的元素类型，与其他任何类。</span><span class="sxs-lookup"><span data-stu-id="35214-121">Since all classes derive from `Object`, you can change the array's element type from any class to any other class.</span></span>  
  
 <span data-ttu-id="35214-122">在以下示例中，不存在转换类型之间`student`并`String`，但同时派生`Object`，因此，所有分配都都有效。</span><span class="sxs-lookup"><span data-stu-id="35214-122">In the following example, no conversion exists between types `student` and `String`, but both derive from `Object`, so all assignments are valid.</span></span>  
  
```  
' Assume student has already been defined as a class.  
Dim testArray() As Object  
' testArray is still an Object array at this point.  
Dim names() As String = New String(3) {"Name0", "Name1", "Name2", "Name3"}  
testArray = New student(3) {}  
' testArray is now of type student().  
testArray = names  
' testArray is now a String array.  
```  
  
### <a name="underlying-type-of-an-array"></a><span data-ttu-id="35214-123">数组的基础类型。</span><span class="sxs-lookup"><span data-stu-id="35214-123">Underlying Type of an Array</span></span>  
 <span data-ttu-id="35214-124">如果您最初声明具有特定类的数组，其基础的元素类型是该类。</span><span class="sxs-lookup"><span data-stu-id="35214-124">If you originally declare an array with a specific class, its underlying element type is that class.</span></span> <span data-ttu-id="35214-125">如果您随后将其设置到另一个类的一个数组，必须有两个类之间的转换。</span><span class="sxs-lookup"><span data-stu-id="35214-125">If you subsequently set it to an array of another class, there must be a conversion between the two classes.</span></span>  
  
 <span data-ttu-id="35214-126">在以下示例中，`students`是`student`数组。</span><span class="sxs-lookup"><span data-stu-id="35214-126">In the following example, `students` is a `student` array.</span></span> <span data-ttu-id="35214-127">由于不存在转换之间`String`和`student`，最后一个语句将失败。</span><span class="sxs-lookup"><span data-stu-id="35214-127">Since no conversion exists between `String` and `student`, the last statement fails.</span></span>  
  
```  
Dim students() As student  
Dim names() As String = New String(3) {"Name0", "Name1", "Name2", "Name3"}  
students = New Student(3) {}  
' The following statement fails at compile time.  
students = names  
```  
  
## <a name="see-also"></a><span data-ttu-id="35214-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="35214-128">See Also</span></span>  
 [<span data-ttu-id="35214-129">数据类型</span><span class="sxs-lookup"><span data-stu-id="35214-129">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 [<span data-ttu-id="35214-130">在 Visual Basic 中的类型转换</span><span class="sxs-lookup"><span data-stu-id="35214-130">Type Conversions in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)  
 [<span data-ttu-id="35214-131">隐式转换和显式转换</span><span class="sxs-lookup"><span data-stu-id="35214-131">Implicit and Explicit Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)  
 [<span data-ttu-id="35214-132">字符串和其他类型之间的转换</span><span class="sxs-lookup"><span data-stu-id="35214-132">Conversions Between Strings and Other Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/conversions-between-strings-and-other-types.md)  
 [<span data-ttu-id="35214-133">如何： 将对象转换为 Visual Basic 中的另一种类型</span><span class="sxs-lookup"><span data-stu-id="35214-133">How to: Convert an Object to Another Type in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-convert-an-object-to-another-type.md)  
 [<span data-ttu-id="35214-134">数据类型</span><span class="sxs-lookup"><span data-stu-id="35214-134">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/index.md)  
 [<span data-ttu-id="35214-135">类型转换函数</span><span class="sxs-lookup"><span data-stu-id="35214-135">Type Conversion Functions</span></span>](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [<span data-ttu-id="35214-136">数组</span><span class="sxs-lookup"><span data-stu-id="35214-136">Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/index.md)
