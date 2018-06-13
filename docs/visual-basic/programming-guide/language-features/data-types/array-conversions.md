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
ms.openlocfilehash: a179b7cf5b82132db88fb5412f0ca4be207f0987
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33651461"
---
# <a name="array-conversions-visual-basic"></a><span data-ttu-id="5fc62-102">数组转换 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5fc62-102">Array Conversions (Visual Basic)</span></span>
<span data-ttu-id="5fc62-103">可以将数组类型转换为另一个数组类型，但必须满足以下条件：</span><span class="sxs-lookup"><span data-stu-id="5fc62-103">You can convert an array type to a different array type provided you meet the following conditions:</span></span>  
  
-   <span data-ttu-id="5fc62-104">**秩相等。**</span><span class="sxs-lookup"><span data-stu-id="5fc62-104">**Equal Rank.**</span></span> <span data-ttu-id="5fc62-105">两个数组的秩必须相同，即，它们必须具有相同数量的维度。</span><span class="sxs-lookup"><span data-stu-id="5fc62-105">The ranks of the two arrays must be the same, that is, they must have the same number of dimensions.</span></span> <span data-ttu-id="5fc62-106">但是，不需要的相应维度的长度相同。</span><span class="sxs-lookup"><span data-stu-id="5fc62-106">However, the lengths of the respective dimensions do not need to be the same.</span></span>  
  
-   <span data-ttu-id="5fc62-107">**元素数据类型。**</span><span class="sxs-lookup"><span data-stu-id="5fc62-107">**Element Data Type.**</span></span> <span data-ttu-id="5fc62-108">这两个数组的元素的数据类型必须是引用类型。</span><span class="sxs-lookup"><span data-stu-id="5fc62-108">The data types of the elements of both arrays must be reference types.</span></span> <span data-ttu-id="5fc62-109">你不能转换`Integer`数组到`Long`数组，或者甚至到`Object`，因为涉及至少一个值类型数组。</span><span class="sxs-lookup"><span data-stu-id="5fc62-109">You cannot convert an `Integer` array to a `Long` array, or even to an `Object` array, because at least one value type is involved.</span></span> <span data-ttu-id="5fc62-110">有关详细信息，请参阅[值类型和引用类型](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)。</span><span class="sxs-lookup"><span data-stu-id="5fc62-110">For more information, see [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md).</span></span>  
  
-   <span data-ttu-id="5fc62-111">**Convertibility。**</span><span class="sxs-lookup"><span data-stu-id="5fc62-111">**Convertibility.**</span></span> <span data-ttu-id="5fc62-112">扩大或收缩转换，转换时，必须能够之间的两个数组的元素类型。</span><span class="sxs-lookup"><span data-stu-id="5fc62-112">A conversion, either widening or narrowing, must be possible between the element types of the two arrays.</span></span> <span data-ttu-id="5fc62-113">符合此要求的一个示例是尝试的转换之间`String`数组和数组的类派生自<xref:System.Attribute?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="5fc62-113">An example that fails this requirement is an attempted conversion between a `String` array and an array of a class derived from <xref:System.Attribute?displayProperty=nameWithType>.</span></span> <span data-ttu-id="5fc62-114">这两种类型将执行任何操作具有共同的且它们之间不存在的任何类型转换。</span><span class="sxs-lookup"><span data-stu-id="5fc62-114">These two types have nothing in common, and no conversion of any kind exists between them.</span></span>  
  
 <span data-ttu-id="5fc62-115">到另一个数组类型的转换是扩大转换或收缩具体取决于是否扩大或收缩的相应元素的转换。</span><span class="sxs-lookup"><span data-stu-id="5fc62-115">A conversion of one array type to another is widening or narrowing depending on whether the conversion of the respective elements is widening or narrowing.</span></span> <span data-ttu-id="5fc62-116">有关详细信息，请参阅 [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)。</span><span class="sxs-lookup"><span data-stu-id="5fc62-116">For more information, see [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).</span></span>  
  
## <a name="conversion-to-an-object-array"></a><span data-ttu-id="5fc62-117">一个对象数组转换</span><span class="sxs-lookup"><span data-stu-id="5fc62-117">Conversion to an Object Array</span></span>  
 <span data-ttu-id="5fc62-118">当声明`Object`但不初始化该值，其元素类型的数组是`Object`，只要它保持未初始化。</span><span class="sxs-lookup"><span data-stu-id="5fc62-118">When you declare an `Object` array without initializing it, its element type is `Object` as long as it remains uninitialized.</span></span> <span data-ttu-id="5fc62-119">当你将其设置为特定类的数组时，它将采用此类的类型。</span><span class="sxs-lookup"><span data-stu-id="5fc62-119">When you set it to an array of a specific class, it takes on the type of that class.</span></span> <span data-ttu-id="5fc62-120">但是，其基础类型仍是`Object`，随后可以将其设置为一个不相关的类的另一个数组。</span><span class="sxs-lookup"><span data-stu-id="5fc62-120">However, its underlying type is still `Object`, and you can subsequently set it to another array of an unrelated class.</span></span> <span data-ttu-id="5fc62-121">因为所有类都派生自`Object`，你可以将从任何类的数组的元素类型更改为任何其他类。</span><span class="sxs-lookup"><span data-stu-id="5fc62-121">Since all classes derive from `Object`, you can change the array's element type from any class to any other class.</span></span>  
  
 <span data-ttu-id="5fc62-122">在下面的示例中，类型之间不存在转换`student`和`String`，但同时派生自`Object`，因此所有分配都都有效。</span><span class="sxs-lookup"><span data-stu-id="5fc62-122">In the following example, no conversion exists between types `student` and `String`, but both derive from `Object`, so all assignments are valid.</span></span>  
  
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
  
### <a name="underlying-type-of-an-array"></a><span data-ttu-id="5fc62-123">基础类型的数组</span><span class="sxs-lookup"><span data-stu-id="5fc62-123">Underlying Type of an Array</span></span>  
 <span data-ttu-id="5fc62-124">如果你最初声明与一个特定类的数组，其基础的元素类型是此类。</span><span class="sxs-lookup"><span data-stu-id="5fc62-124">If you originally declare an array with a specific class, its underlying element type is that class.</span></span> <span data-ttu-id="5fc62-125">如果你随后将其设置为另一个类的数组，必须有两个类之间的转换。</span><span class="sxs-lookup"><span data-stu-id="5fc62-125">If you subsequently set it to an array of another class, there must be a conversion between the two classes.</span></span>  
  
 <span data-ttu-id="5fc62-126">在下面的示例中，`students`是`student`数组。</span><span class="sxs-lookup"><span data-stu-id="5fc62-126">In the following example, `students` is a `student` array.</span></span> <span data-ttu-id="5fc62-127">由于之间不存在转换`String`和`student`，最后一个语句将失败。</span><span class="sxs-lookup"><span data-stu-id="5fc62-127">Since no conversion exists between `String` and `student`, the last statement fails.</span></span>  
  
```  
Dim students() As student  
Dim names() As String = New String(3) {"Name0", "Name1", "Name2", "Name3"}  
students = New Student(3) {}  
' The following statement fails at compile time.  
students = names  
```  
  
## <a name="see-also"></a><span data-ttu-id="5fc62-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="5fc62-128">See Also</span></span>  
 [<span data-ttu-id="5fc62-129">数据类型</span><span class="sxs-lookup"><span data-stu-id="5fc62-129">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 [<span data-ttu-id="5fc62-130">在 Visual Basic 中的类型转换</span><span class="sxs-lookup"><span data-stu-id="5fc62-130">Type Conversions in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)  
 [<span data-ttu-id="5fc62-131">隐式转换和显式转换</span><span class="sxs-lookup"><span data-stu-id="5fc62-131">Implicit and Explicit Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)  
 [<span data-ttu-id="5fc62-132">字符串和其他类型之间的转换</span><span class="sxs-lookup"><span data-stu-id="5fc62-132">Conversions Between Strings and Other Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/conversions-between-strings-and-other-types.md)  
 [<span data-ttu-id="5fc62-133">如何： 将对象转换为在 Visual Basic 中的另一种类型</span><span class="sxs-lookup"><span data-stu-id="5fc62-133">How to: Convert an Object to Another Type in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-convert-an-object-to-another-type.md)  
 [<span data-ttu-id="5fc62-134">数据类型</span><span class="sxs-lookup"><span data-stu-id="5fc62-134">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [<span data-ttu-id="5fc62-135">类型转换函数</span><span class="sxs-lookup"><span data-stu-id="5fc62-135">Type Conversion Functions</span></span>](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [<span data-ttu-id="5fc62-136">数组</span><span class="sxs-lookup"><span data-stu-id="5fc62-136">Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/index.md)
