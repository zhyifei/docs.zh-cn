---
title: 指针类型（C# 编程指南）
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- unsafe code [C#], pointers
- pointers [C#]
ms.assetid: 3319faf9-336d-4148-9af2-1da2579cdd1e
caps.latest.revision: ''
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: fe7b926bdf9f662d25f2fe960b51fc8254b7aa3a
ms.sourcegitcommit: c883637b41ee028786edceece4fa872939d2e64c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/26/2018
---
# <a name="pointer-types-c-programming-guide"></a><span data-ttu-id="31da2-102">指针类型（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="31da2-102">Pointer types (C# Programming Guide)</span></span>
<span data-ttu-id="31da2-103">在不安全的上下文中，类型可以是指针类型、值类型或引用类型。</span><span class="sxs-lookup"><span data-stu-id="31da2-103">In an unsafe context, a type may be a pointer type, a value type, or a reference type.</span></span> <span data-ttu-id="31da2-104">指针类型声明采用下列形式之一：</span><span class="sxs-lookup"><span data-stu-id="31da2-104">A pointer type declaration takes one of the following forms:</span></span>  
  
```  
type* identifier;  
void* identifier; //allowed but not recommended  
```  
  
 <span data-ttu-id="31da2-105">以下任一类型均可为指针类型：</span><span class="sxs-lookup"><span data-stu-id="31da2-105">Any of the following types may be a pointer type:</span></span>  
  
-   <span data-ttu-id="31da2-106">[sbyte](../../../csharp/language-reference/keywords/sbyte.md)、[byte](../../../csharp/language-reference/keywords/byte.md)、[short](../../../csharp/language-reference/keywords/short.md)、[ushort](../../../csharp/language-reference/keywords/ushort.md)、[int](../../../csharp/language-reference/keywords/int.md)、[uint](../../../csharp/language-reference/keywords/uint.md)、[long](../../../csharp/language-reference/keywords/long.md)、[ulong](../../../csharp/language-reference/keywords/ulong.md)、[char](../../../csharp/language-reference/keywords/char.md)、[float](../../../csharp/language-reference/keywords/float.md)、[double](../../../csharp/language-reference/keywords/double.md)、[decimal](../../../csharp/language-reference/keywords/decimal.md) 或 [bool](../../../csharp/language-reference/keywords/bool.md)。</span><span class="sxs-lookup"><span data-stu-id="31da2-106">[sbyte](../../../csharp/language-reference/keywords/sbyte.md), [byte](../../../csharp/language-reference/keywords/byte.md), [short](../../../csharp/language-reference/keywords/short.md), [ushort](../../../csharp/language-reference/keywords/ushort.md), [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md), [ulong](../../../csharp/language-reference/keywords/ulong.md), [char](../../../csharp/language-reference/keywords/char.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md), [decimal](../../../csharp/language-reference/keywords/decimal.md), or [bool](../../../csharp/language-reference/keywords/bool.md).</span></span>  
  
-   <span data-ttu-id="31da2-107">任何[枚举](../../../csharp/language-reference/keywords/enum.md)类型。</span><span class="sxs-lookup"><span data-stu-id="31da2-107">Any [enum](../../../csharp/language-reference/keywords/enum.md) type.</span></span>  
  
-   <span data-ttu-id="31da2-108">任何指针类型。</span><span class="sxs-lookup"><span data-stu-id="31da2-108">Any pointer type.</span></span>  
  
-   <span data-ttu-id="31da2-109">任何仅包含非托管类型字段的用户定义的结构类型。</span><span class="sxs-lookup"><span data-stu-id="31da2-109">Any user-defined struct type that contains fields of unmanaged types only.</span></span>  
  
 <span data-ttu-id="31da2-110">指针类型不从[对象](../../../csharp/language-reference/keywords/object.md)继承，并且指针类型与 `object` 之间不存在转换。</span><span class="sxs-lookup"><span data-stu-id="31da2-110">Pointer types do not inherit from [object](../../../csharp/language-reference/keywords/object.md) and no conversions exist between pointer types and `object`.</span></span> <span data-ttu-id="31da2-111">此外，装箱和取消装箱不支持指针。</span><span class="sxs-lookup"><span data-stu-id="31da2-111">Also, boxing and unboxing do not support pointers.</span></span> <span data-ttu-id="31da2-112">但是，你可在不同的指针类型之间以及指针类型和整型之间进行转换。</span><span class="sxs-lookup"><span data-stu-id="31da2-112">However, you can convert between different pointer types and between pointer types and integral types.</span></span>  
  
 <span data-ttu-id="31da2-113">在同一个声明中声明多个指针时，星号 (\*) 仅与基础类型一起写入；而不是用作每个指针名称的前缀。</span><span class="sxs-lookup"><span data-stu-id="31da2-113">When you declare multiple pointers in the same declaration, the asterisk (\*) is written together with the underlying type only; it is not used as a prefix to each pointer name.</span></span> <span data-ttu-id="31da2-114">例如：</span><span class="sxs-lookup"><span data-stu-id="31da2-114">For example:</span></span>  
  
```  
int* p1, p2, p3;   // Ok  
int *p1, *p2, *p3;   // Invalid in C#  
```  
  
 <span data-ttu-id="31da2-115">指针不能指向引用或包含引用的[结构](../../../csharp/language-reference/keywords/struct.md)，因为无法对对象引用进行垃圾回收，即使有指针指向它也是如此。</span><span class="sxs-lookup"><span data-stu-id="31da2-115">A pointer cannot point to a reference or to a [struct](../../../csharp/language-reference/keywords/struct.md) that contains references, because an object reference can be garbage collected even if a pointer is pointing to it.</span></span> <span data-ttu-id="31da2-116">垃圾回收器并不跟踪是否有任何类型的指针指向对象。</span><span class="sxs-lookup"><span data-stu-id="31da2-116">The garbage collector does not keep track of whether an object is being pointed to by any pointer types.</span></span>  
  
 <span data-ttu-id="31da2-117">`myType*` 类型的指针变量的值为 `myType` 类型的变量的地址。</span><span class="sxs-lookup"><span data-stu-id="31da2-117">The value of the pointer variable of type `myType*` is the address of a variable of type `myType`.</span></span> <span data-ttu-id="31da2-118">下面是指针类型声明的示例：</span><span class="sxs-lookup"><span data-stu-id="31da2-118">The following are examples of pointer type declarations:</span></span>  
  
|<span data-ttu-id="31da2-119">示例</span><span class="sxs-lookup"><span data-stu-id="31da2-119">Example</span></span>|<span data-ttu-id="31da2-120">描述</span><span class="sxs-lookup"><span data-stu-id="31da2-120">Description</span></span>|  
|-------------|-----------------|  
|`int* p`|<span data-ttu-id="31da2-121">`p` 是指向整数的指针。</span><span class="sxs-lookup"><span data-stu-id="31da2-121">`p` is a pointer to an integer.</span></span>|  
|`int** p`|<span data-ttu-id="31da2-122">`p` 是指向整数的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="31da2-122">`p` is a pointer to a pointer to an integer.</span></span>|  
|`int*[] p`|<span data-ttu-id="31da2-123">`p` 是指向整数的指针的一维数组。</span><span class="sxs-lookup"><span data-stu-id="31da2-123">`p` is a single-dimensional array of pointers to integers.</span></span>|  
|`char* p`|<span data-ttu-id="31da2-124">`p` 是指向字符的指针。</span><span class="sxs-lookup"><span data-stu-id="31da2-124">`p` is a pointer to a char.</span></span>|  
|`void* p`|<span data-ttu-id="31da2-125">`p` 是指向未知类型的指针。</span><span class="sxs-lookup"><span data-stu-id="31da2-125">`p` is a pointer to an unknown type.</span></span>|  
  
 <span data-ttu-id="31da2-126">指针间接寻址运算符 \* 可用于访问位于指针变量所指向的位置的内容。</span><span class="sxs-lookup"><span data-stu-id="31da2-126">The pointer indirection operator \* can be used to access the contents at the location pointed to by the pointer variable.</span></span> <span data-ttu-id="31da2-127">例如，请考虑以下声明：</span><span class="sxs-lookup"><span data-stu-id="31da2-127">For example, consider the following declaration:</span></span>  
  
```  
int* myVariable;  
```  
  
 <span data-ttu-id="31da2-128">表达式 `*myVariable` 表示在 `int` 中包含的地址处找到的 `myVariable` 变量。</span><span class="sxs-lookup"><span data-stu-id="31da2-128">The expression `*myVariable` denotes the `int` variable found at the address contained in `myVariable`.</span></span>  
  
 <span data-ttu-id="31da2-129">[fixed 语句](../../../csharp/language-reference/keywords/fixed-statement.md)和[指针转换](../../../csharp/programming-guide/unsafe-code-pointers/pointer-conversions.md)主题中有几个指针示例。</span><span class="sxs-lookup"><span data-stu-id="31da2-129">There are several examples of pointers in the topics [fixed Statement](../../../csharp/language-reference/keywords/fixed-statement.md) and [Pointer Conversions](../../../csharp/programming-guide/unsafe-code-pointers/pointer-conversions.md).</span></span>  <span data-ttu-id="31da2-130">下面的示例显示需要 `unsafe` 关键字和 `fixed` 语句以及如何递增内部指针。</span><span class="sxs-lookup"><span data-stu-id="31da2-130">The following example shows the need for the `unsafe` keyword and the `fixed` statement, and how to increment an interior pointer.</span></span>  <span data-ttu-id="31da2-131">你可将此代码粘贴到控制台应用程序的 Main 函数中来运行它。</span><span class="sxs-lookup"><span data-stu-id="31da2-131">You can paste this code into the Main function of a console application to run it.</span></span> <span data-ttu-id="31da2-132">（记住在“项目设计器”中启用不安全代码；选择菜单栏上的“项目”、“属性”，然后选择“生成”选项卡中的“允许不安全代码”。）</span><span class="sxs-lookup"><span data-stu-id="31da2-132">(Remember to enable unsafe code in the **Project Designer**; choose **Project**, **Properties** on the menu bar, and then select **Allow unsafe code** in the **Build** tab.)</span></span>  
  
```  
// Normal pointer to an object.  
int[] a = new int[5] {10, 20, 30, 40, 50};  
// Must be in unsafe code to use interior pointers.  
unsafe  
{  
    // Must pin object on heap so that it doesn't move while using interior pointers.  
    fixed (int* p = &a[0])  
    {  
        // p is pinned as well as object, so create another pointer to show incrementing it.  
        int* p2 = p;  
        Console.WriteLine(*p2);  
        // Incrementing p2 bumps the pointer by four bytes due to its type ...  
        p2 += 1;  
        Console.WriteLine(*p2);  
        p2 += 1;  
        Console.WriteLine(*p2);  
        Console.WriteLine("--------");  
        Console.WriteLine(*p);  
        // Deferencing p and incrementing changes the value of a[0] ...  
        *p += 1;  
        Console.WriteLine(*p);  
        *p += 1;  
        Console.WriteLine(*p);  
    }  
}  
  
Console.WriteLine("--------");  
Console.WriteLine(a[0]);  
Console.ReadLine();  
  
// Output:  
//10  
//20  
//30  
//--------  
//10  
//11  
//12  
//--------  
//12  
```  
  
 <span data-ttu-id="31da2-133">你无法对 `void*` 类型的指针应用间接寻址运算符。</span><span class="sxs-lookup"><span data-stu-id="31da2-133">You cannot apply the indirection operator to a pointer of type `void*`.</span></span> <span data-ttu-id="31da2-134">但是，你可以使用强制转换将 void 指针转换为任何其他指针类型，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="31da2-134">However, you can use a cast to convert a void pointer to any other pointer type, and vice versa.</span></span>  
  
 <span data-ttu-id="31da2-135">指针可以为 `null`。</span><span class="sxs-lookup"><span data-stu-id="31da2-135">A pointer can be `null`.</span></span> <span data-ttu-id="31da2-136">将间接寻址运算符应用于 null 指针将导致由实现定义的行为。</span><span class="sxs-lookup"><span data-stu-id="31da2-136">Applying the indirection operator to a null pointer causes an implementation-defined behavior.</span></span>  
  
 <span data-ttu-id="31da2-137">请注意，在方法之间传递指针会导致未定义的行为。</span><span class="sxs-lookup"><span data-stu-id="31da2-137">Be aware that passing pointers between methods can cause undefined behavior.</span></span> <span data-ttu-id="31da2-138">考虑这种方法，该方法通过 `in`、`out` 或 `ref` 参数或作为函数结果返回一个指向局部变量的指针。</span><span class="sxs-lookup"><span data-stu-id="31da2-138">Consider a method that returns a pointer to a local variable through an `in`, `out` or `ref` parameter or as the function result.</span></span> <span data-ttu-id="31da2-139">如果已在固定块中设置指针，则它指向的变量不再是固定的。</span><span class="sxs-lookup"><span data-stu-id="31da2-139">If the pointer was set in a fixed block, the variable to which it points may no longer be fixed.</span></span>  
  
 <span data-ttu-id="31da2-140">下表列出了可在不安全的上下文中对指针执行的运算符和语句：</span><span class="sxs-lookup"><span data-stu-id="31da2-140">The following table lists the operators and statements that can operate on pointers in an unsafe context:</span></span>  
  
|<span data-ttu-id="31da2-141">运算符/语句</span><span class="sxs-lookup"><span data-stu-id="31da2-141">Operator/Statement</span></span>|<span data-ttu-id="31da2-142">使用</span><span class="sxs-lookup"><span data-stu-id="31da2-142">Use</span></span>|  
|-------------------------|---------|  
|*|<span data-ttu-id="31da2-143">执行指针间接寻址。</span><span class="sxs-lookup"><span data-stu-id="31da2-143">Performs pointer indirection.</span></span>|  
|->|<span data-ttu-id="31da2-144">通过指针访问结构的成员。</span><span class="sxs-lookup"><span data-stu-id="31da2-144">Accesses a member of a struct through a pointer.</span></span>|  
|<span data-ttu-id="31da2-145">[]</span><span class="sxs-lookup"><span data-stu-id="31da2-145">[]</span></span>|<span data-ttu-id="31da2-146">为指针建立索引。</span><span class="sxs-lookup"><span data-stu-id="31da2-146">Indexes a pointer.</span></span>|  
|`&`|<span data-ttu-id="31da2-147">获取变量的地址。</span><span class="sxs-lookup"><span data-stu-id="31da2-147">Obtains the address of a variable.</span></span>|  
|<span data-ttu-id="31da2-148">++ 和 --</span><span class="sxs-lookup"><span data-stu-id="31da2-148">++ and --</span></span>|<span data-ttu-id="31da2-149">递增和递减指针。</span><span class="sxs-lookup"><span data-stu-id="31da2-149">Increments and decrements pointers.</span></span>|  
|<span data-ttu-id="31da2-150">+ 和 -</span><span class="sxs-lookup"><span data-stu-id="31da2-150">+ and -</span></span>|<span data-ttu-id="31da2-151">执行指针算法。</span><span class="sxs-lookup"><span data-stu-id="31da2-151">Performs pointer arithmetic.</span></span>|  
|<span data-ttu-id="31da2-152">==、!=、\<、>、\<= 和 >=</span><span class="sxs-lookup"><span data-stu-id="31da2-152">==, !=, \<, >, \<=, and >=</span></span>|<span data-ttu-id="31da2-153">比较指针。</span><span class="sxs-lookup"><span data-stu-id="31da2-153">Compares pointers.</span></span>|  
|`stackalloc`|<span data-ttu-id="31da2-154">在堆栈上分配内存。</span><span class="sxs-lookup"><span data-stu-id="31da2-154">Allocates memory on the stack.</span></span>|  
|<span data-ttu-id="31da2-155">`fixed` 语句</span><span class="sxs-lookup"><span data-stu-id="31da2-155">`fixed` statement</span></span>|<span data-ttu-id="31da2-156">临时固定变量以便找到其地址。</span><span class="sxs-lookup"><span data-stu-id="31da2-156">Temporarily fixes a variable so that its address may be found.</span></span>|  
  
## <a name="c-language-specification"></a><span data-ttu-id="31da2-157">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="31da2-157">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="31da2-158">另请参阅</span><span class="sxs-lookup"><span data-stu-id="31da2-158">See Also</span></span>  
 [<span data-ttu-id="31da2-159">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="31da2-159">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="31da2-160">不安全代码和指针</span><span class="sxs-lookup"><span data-stu-id="31da2-160">Unsafe Code and Pointers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/index.md)  
 [<span data-ttu-id="31da2-161">指针转换</span><span class="sxs-lookup"><span data-stu-id="31da2-161">Pointer Conversions</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-conversions.md)  
 [<span data-ttu-id="31da2-162">指针表达式</span><span class="sxs-lookup"><span data-stu-id="31da2-162">Pointer Expressions</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)  
 [<span data-ttu-id="31da2-163">类型</span><span class="sxs-lookup"><span data-stu-id="31da2-163">Types</span></span>](../../../csharp/language-reference/keywords/types.md)  
 [<span data-ttu-id="31da2-164">不安全</span><span class="sxs-lookup"><span data-stu-id="31da2-164">unsafe</span></span>](../../../csharp/language-reference/keywords/unsafe.md)  
 [<span data-ttu-id="31da2-165">fixed 语句</span><span class="sxs-lookup"><span data-stu-id="31da2-165">fixed Statement</span></span>](../../../csharp/language-reference/keywords/fixed-statement.md)  
 [<span data-ttu-id="31da2-166">stackalloc</span><span class="sxs-lookup"><span data-stu-id="31da2-166">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)  
 [<span data-ttu-id="31da2-167">装箱和取消装箱</span><span class="sxs-lookup"><span data-stu-id="31da2-167">Boxing and Unboxing</span></span>](../../../csharp/programming-guide/types/boxing-and-unboxing.md)
