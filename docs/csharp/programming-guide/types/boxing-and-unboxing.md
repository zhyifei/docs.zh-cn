---
title: "装箱和取消装箱（C# 编程指南）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- cs.boxing
dev_langs:
- CSharp
helpviewer_keywords:
- C# language, boxing
- C# language, unboxing
- unboxing [C#]
- boxing [C#]
ms.assetid: 8da9bbf4-bce9-4b08-b2e5-f64c11c56514
caps.latest.revision: 34
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: c783ac60735ba25db2736bd9469063c0897be22f
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="boxing-and-unboxing-c-programming-guide"></a><span data-ttu-id="531d7-102">装箱和取消装箱（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="531d7-102">Boxing and Unboxing (C# Programming Guide)</span></span>
<span data-ttu-id="531d7-103">装箱是将[值类型](../../../csharp/language-reference/keywords/value-types.md)转换为 `object` 类型或由此值类型实现的任何接口类型的过程。</span><span class="sxs-lookup"><span data-stu-id="531d7-103">Boxing is the process of converting a [value type](../../../csharp/language-reference/keywords/value-types.md) to the type `object` or to any interface type implemented by this value type.</span></span> <span data-ttu-id="531d7-104">当 CLR 对值类型进行装箱时，会将该值包装到 System.Object 内部，再将后者存储在托管堆上。</span><span class="sxs-lookup"><span data-stu-id="531d7-104">When the CLR boxes a value type, it wraps the value inside a System.Object and stores it on the managed heap.</span></span> <span data-ttu-id="531d7-105">取消装箱将从对象中提取值类型。</span><span class="sxs-lookup"><span data-stu-id="531d7-105">Unboxing extracts the value type from the object.</span></span> <span data-ttu-id="531d7-106">装箱是隐式的；取消装箱是显式的。</span><span class="sxs-lookup"><span data-stu-id="531d7-106">Boxing is implicit; unboxing is explicit.</span></span> <span data-ttu-id="531d7-107">装箱和取消装箱的概念是类型系统 C# 统一视图的基础，其中任一类型的值都被视为一个对象。</span><span class="sxs-lookup"><span data-stu-id="531d7-107">The concept of boxing and unboxing underlies the C# unified view of the type system in which a value of any type can be treated as an object.</span></span>  
  
 <span data-ttu-id="531d7-108">下例将整型变量 `i` 进行了装箱并分配给对象 `o`。</span><span class="sxs-lookup"><span data-stu-id="531d7-108">In the following example, the integer variable `i` is *boxed* and assigned to object `o`.</span></span>  
  
 <span data-ttu-id="531d7-109">[!code-cs[csProgGuideTypes#14](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/boxing-and-unboxing_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="531d7-109">[!code-cs[csProgGuideTypes#14](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/boxing-and-unboxing_1.cs)]</span></span>  
  
 <span data-ttu-id="531d7-110">然后，可以将对象 `o` 取消装箱并分配给整型变量 `i`：</span><span class="sxs-lookup"><span data-stu-id="531d7-110">The object `o` can then be unboxed and assigned to integer variable `i`:</span></span>  
  
 <span data-ttu-id="531d7-111">[!code-cs[csProgGuideTypes#15](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/boxing-and-unboxing_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="531d7-111">[!code-cs[csProgGuideTypes#15](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/boxing-and-unboxing_2.cs)]</span></span>  
  
 <span data-ttu-id="531d7-112">以下示例演示如何在 C# 中使用装箱。</span><span class="sxs-lookup"><span data-stu-id="531d7-112">The following examples illustrate how boxing is used in C#.</span></span>  
  
 <span data-ttu-id="531d7-113">[!code-cs[csProgGuideTypes#47](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/boxing-and-unboxing_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="531d7-113">[!code-cs[csProgGuideTypes#47](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/boxing-and-unboxing_3.cs)]</span></span>  
  
## <a name="performance"></a><span data-ttu-id="531d7-114">性能</span><span class="sxs-lookup"><span data-stu-id="531d7-114">Performance</span></span>  
 <span data-ttu-id="531d7-115">相对于简单的赋值而言，装箱和取消装箱过程需要进行大量的计算。</span><span class="sxs-lookup"><span data-stu-id="531d7-115">In relation to simple assignments, boxing and unboxing are computationally expensive processes.</span></span> <span data-ttu-id="531d7-116">对值类型进行装箱时，必须分配并构造一个新对象。</span><span class="sxs-lookup"><span data-stu-id="531d7-116">When a value type is boxed, a new object must be allocated and constructed.</span></span> <span data-ttu-id="531d7-117">取消装箱所需的强制转换也需要进行大量的计算，只是程度较轻。</span><span class="sxs-lookup"><span data-stu-id="531d7-117">To a lesser degree, the cast required for unboxing is also expensive computationally.</span></span> <span data-ttu-id="531d7-118">有关更多信息，请参阅[性能](https://msdn.microsoft.com/library/ms173196(VS.110).aspx)。</span><span class="sxs-lookup"><span data-stu-id="531d7-118">For more information, see [Performance](https://msdn.microsoft.com/library/ms173196(VS.110).aspx).</span></span>  
  
## <a name="boxing"></a><span data-ttu-id="531d7-119">装箱</span><span class="sxs-lookup"><span data-stu-id="531d7-119">Boxing</span></span>  
 <span data-ttu-id="531d7-120">装箱用于在垃圾回收堆中存储值类型。</span><span class="sxs-lookup"><span data-stu-id="531d7-120">Boxing is used to store value types in the garbage-collected heap.</span></span> <span data-ttu-id="531d7-121">装箱是[值类型](../../../csharp/language-reference/keywords/value-types.md)到 `object` 类型或到此值类型所实现的任何接口类型的隐式转换。</span><span class="sxs-lookup"><span data-stu-id="531d7-121">Boxing is an implicit conversion of a [value type](../../../csharp/language-reference/keywords/value-types.md) to the type `object` or to any interface type implemented by this value type.</span></span> <span data-ttu-id="531d7-122">对值类型装箱会在堆中分配一个对象实例，并将该值复制到新的对象中。</span><span class="sxs-lookup"><span data-stu-id="531d7-122">Boxing a value type allocates an object instance on the heap and copies the value into the new object.</span></span>  
  
 <span data-ttu-id="531d7-123">请看以下值类型变量的声明：</span><span class="sxs-lookup"><span data-stu-id="531d7-123">Consider the following declaration of a value-type variable:</span></span>  
  
 <span data-ttu-id="531d7-124">[!code-cs[csProgGuideTypes#17](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/boxing-and-unboxing_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="531d7-124">[!code-cs[csProgGuideTypes#17](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/boxing-and-unboxing_4.cs)]</span></span>  
  
 <span data-ttu-id="531d7-125">以下语句对变量 `i` 隐式应用了装箱操作：</span><span class="sxs-lookup"><span data-stu-id="531d7-125">The following statement implicitly applies the boxing operation on the variable `i`:</span></span>  
  
 <span data-ttu-id="531d7-126">[!code-cs[csProgGuideTypes#18](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/boxing-and-unboxing_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="531d7-126">[!code-cs[csProgGuideTypes#18](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/boxing-and-unboxing_5.cs)]</span></span>  
  
 <span data-ttu-id="531d7-127">此语句的结果是在堆栈上创建对象引用 `o`，而在堆上则引用 `int` 类型的值。</span><span class="sxs-lookup"><span data-stu-id="531d7-127">The result of this statement is creating an object reference `o`, on the stack, that references a value of the type `int`, on the heap.</span></span> <span data-ttu-id="531d7-128">该值是赋给变量 `i` 的值类型值的一个副本。</span><span class="sxs-lookup"><span data-stu-id="531d7-128">This value is a copy of the value-type value assigned to the variable `i`.</span></span> <span data-ttu-id="531d7-129">下图说明了两个变量 `i` 和 `o` 之间的差异。</span><span class="sxs-lookup"><span data-stu-id="531d7-129">The difference between the two variables, `i` and `o`, is illustrated in the following figure.</span></span>  
  
 <span data-ttu-id="531d7-130">![装箱转换图](../../../csharp/programming-guide/types/media/vcboxingconversion.gif "vcBoxingConversion")</span><span class="sxs-lookup"><span data-stu-id="531d7-130">![BoxingConversion graphic](../../../csharp/programming-guide/types/media/vcboxingconversion.gif "vcBoxingConversion")</span></span>  
<span data-ttu-id="531d7-131">装箱转换</span><span class="sxs-lookup"><span data-stu-id="531d7-131">Boxing Conversion</span></span>  
  
 <span data-ttu-id="531d7-132">还可以像下面的示例一样执行显式装箱，但显式装箱从来不是必需的：</span><span class="sxs-lookup"><span data-stu-id="531d7-132">It is also possible to perform the boxing explicitly as in the following example, but explicit boxing is never required:</span></span>  
  
 <span data-ttu-id="531d7-133">[!code-cs[csProgGuideTypes#19](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/boxing-and-unboxing_6.cs)]</span><span class="sxs-lookup"><span data-stu-id="531d7-133">[!code-cs[csProgGuideTypes#19](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/boxing-and-unboxing_6.cs)]</span></span>  
  
## <a name="description"></a><span data-ttu-id="531d7-134">描述</span><span class="sxs-lookup"><span data-stu-id="531d7-134">Description</span></span>  
 <span data-ttu-id="531d7-135">此示例使用装箱将整型变量 `i` 转换为对象 `o`。</span><span class="sxs-lookup"><span data-stu-id="531d7-135">This example converts an integer variable `i` to an object `o` by using boxing.</span></span> <span data-ttu-id="531d7-136">这样一来，存储在变量 `i` 中的值就从 `123` 更改为 `456`。</span><span class="sxs-lookup"><span data-stu-id="531d7-136">Then, the value stored in the variable `i` is changed from `123` to `456`.</span></span> <span data-ttu-id="531d7-137">该示例表明原始值类型和装箱的对象使用不同的内存位置，因此能够存储不同的值。</span><span class="sxs-lookup"><span data-stu-id="531d7-137">The example shows that the original value type and the boxed object use separate memory locations, and therefore can store different values.</span></span>  
  
## <a name="example"></a><span data-ttu-id="531d7-138">示例</span><span class="sxs-lookup"><span data-stu-id="531d7-138">Example</span></span>  
 <span data-ttu-id="531d7-139">[!code-cs[csProgGuideTypes#16](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/boxing-and-unboxing_7.cs)]</span><span class="sxs-lookup"><span data-stu-id="531d7-139">[!code-cs[csProgGuideTypes#16](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/boxing-and-unboxing_7.cs)]</span></span>  
  
## <a name="unboxing"></a><span data-ttu-id="531d7-140">取消装箱</span><span class="sxs-lookup"><span data-stu-id="531d7-140">Unboxing</span></span>  
 <span data-ttu-id="531d7-141">取消装箱是从 `object` 类型到[值类型](../../../csharp/language-reference/keywords/value-types.md)或从接口类型到实现该接口的值类型的显式转换。</span><span class="sxs-lookup"><span data-stu-id="531d7-141">Unboxing is an explicit conversion from the type `object` to a [value type](../../../csharp/language-reference/keywords/value-types.md) or from an interface type to a value type that implements the interface.</span></span> <span data-ttu-id="531d7-142">取消装箱操作包括：</span><span class="sxs-lookup"><span data-stu-id="531d7-142">An unboxing operation consists of:</span></span>  
  
-   <span data-ttu-id="531d7-143">检查对象实例，以确保它是给定值类型的装箱值。</span><span class="sxs-lookup"><span data-stu-id="531d7-143">Checking the object instance to make sure that it is a boxed value of the given value type.</span></span>  
  
-   <span data-ttu-id="531d7-144">将该值从实例复制到值类型变量中。</span><span class="sxs-lookup"><span data-stu-id="531d7-144">Copying the value from the instance into the value-type variable.</span></span>  
  
 <span data-ttu-id="531d7-145">下面的语句演示装箱和取消装箱两种操作：</span><span class="sxs-lookup"><span data-stu-id="531d7-145">The following statements demonstrate both boxing and unboxing operations:</span></span>  
  
 <span data-ttu-id="531d7-146">[!code-cs[csProgGuideTypes#21](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/boxing-and-unboxing_8.cs)]</span><span class="sxs-lookup"><span data-stu-id="531d7-146">[!code-cs[csProgGuideTypes#21](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/boxing-and-unboxing_8.cs)]</span></span>  
  
 <span data-ttu-id="531d7-147">下图演示上述语句的结果。</span><span class="sxs-lookup"><span data-stu-id="531d7-147">The following figure demonstrates the result of the previous statements.</span></span>  
  
 <span data-ttu-id="531d7-148">![取消装箱转换图](../../../csharp/programming-guide/types/media/vcunboxingconversion.gif "vcUnBoxingConversion")</span><span class="sxs-lookup"><span data-stu-id="531d7-148">![UnBoxing Conversion graphic](../../../csharp/programming-guide/types/media/vcunboxingconversion.gif "vcUnBoxingConversion")</span></span>  
<span data-ttu-id="531d7-149">取消装箱转换</span><span class="sxs-lookup"><span data-stu-id="531d7-149">Unboxing Conversion</span></span>  
  
 <span data-ttu-id="531d7-150">要在运行时成功取消装箱值类型，被取消装箱的项必须是对一个对象的引用，该对象是先前通过装箱该值类型的实例创建的。</span><span class="sxs-lookup"><span data-stu-id="531d7-150">For the unboxing of value types to succeed at run time, the item being unboxed must be a reference to an object that was previously created by boxing an instance of that value type.</span></span> <span data-ttu-id="531d7-151">尝试取消装箱 `null` 会导致 <xref:System.NullReferenceException>。</span><span class="sxs-lookup"><span data-stu-id="531d7-151">Attempting to unbox `null` causes a <xref:System.NullReferenceException>.</span></span> <span data-ttu-id="531d7-152">尝试取消装箱对不兼容值类型的引用会导致 <xref:System.InvalidCastException>。</span><span class="sxs-lookup"><span data-stu-id="531d7-152">Attempting to unbox a reference to an incompatible value type causes an <xref:System.InvalidCastException>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="531d7-153">示例</span><span class="sxs-lookup"><span data-stu-id="531d7-153">Example</span></span>  
 <span data-ttu-id="531d7-154">下面的示例演示无效的取消装箱及引发的 `InvalidCastException`。</span><span class="sxs-lookup"><span data-stu-id="531d7-154">The following example demonstrates a case of invalid unboxing and the resulting `InvalidCastException`.</span></span> <span data-ttu-id="531d7-155">使用 `try` 和 `catch`，在发生错误时显示错误信息。</span><span class="sxs-lookup"><span data-stu-id="531d7-155">Using `try` and `catch`, an error message is displayed when the error occurs.</span></span>  
  
 <span data-ttu-id="531d7-156">[!code-cs[csProgGuideTypes#20](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/boxing-and-unboxing_9.cs)]</span><span class="sxs-lookup"><span data-stu-id="531d7-156">[!code-cs[csProgGuideTypes#20](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/boxing-and-unboxing_9.cs)]</span></span>  
  
 <span data-ttu-id="531d7-157">此程序输出：</span><span class="sxs-lookup"><span data-stu-id="531d7-157">This program outputs:</span></span>  
  
 `Specified cast is not valid. Error: Incorrect unboxing.`  
  
 <span data-ttu-id="531d7-158">如果将下列语句：</span><span class="sxs-lookup"><span data-stu-id="531d7-158">If you change the statement:</span></span>  
  
```  
int j = (short) o;  
```  
  
 <span data-ttu-id="531d7-159">更改为：</span><span class="sxs-lookup"><span data-stu-id="531d7-159">to:</span></span>  
  
```  
int j = (int) o;  
```  
  
 <span data-ttu-id="531d7-160">将执行转换，并将得到以下输出：</span><span class="sxs-lookup"><span data-stu-id="531d7-160">the conversion will be performed, and you will get the output:</span></span>  
  
 `Unboxing OK.`  
  
## <a name="c-language-specification"></a><span data-ttu-id="531d7-161">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="531d7-161">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="related-sections"></a><span data-ttu-id="531d7-162">相关章节</span><span class="sxs-lookup"><span data-stu-id="531d7-162">Related Sections</span></span>  
 <span data-ttu-id="531d7-163">更多相关信息：</span><span class="sxs-lookup"><span data-stu-id="531d7-163">For more information:</span></span>  
  
-   [<span data-ttu-id="531d7-164">引用类型</span><span class="sxs-lookup"><span data-stu-id="531d7-164">Reference Types</span></span>](../../../csharp/language-reference/keywords/reference-types.md)  
  
-   [<span data-ttu-id="531d7-165">值类型</span><span class="sxs-lookup"><span data-stu-id="531d7-165">Value Types</span></span>](../../../csharp/language-reference/keywords/value-types.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="531d7-166">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="531d7-166">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="531d7-167">另请参阅</span><span class="sxs-lookup"><span data-stu-id="531d7-167">See Also</span></span>  
 [<span data-ttu-id="531d7-168">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="531d7-168">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)

