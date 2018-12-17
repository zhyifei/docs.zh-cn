---
title: 指针类型 - C# 编程指南
ms.custom: seodec18
ms.date: 04/20/2018
helpviewer_keywords:
- unsafe code [C#], pointers
- pointers [C#]
ms.openlocfilehash: 5474d179005742c610d29ccd9dac7bf1dc94c9d2
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2018
ms.locfileid: "53239404"
---
# <a name="pointer-types-c-programming-guide"></a><span data-ttu-id="bdef5-102">指针类型（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="bdef5-102">Pointer types (C# Programming Guide)</span></span>

<span data-ttu-id="bdef5-103">在不安全的上下文中，类型可以是指针类型、值类型或引用类型。</span><span class="sxs-lookup"><span data-stu-id="bdef5-103">In an unsafe context, a type may be a pointer type, a value type, or a reference type.</span></span> <span data-ttu-id="bdef5-104">指针类型声明采用下列形式之一：</span><span class="sxs-lookup"><span data-stu-id="bdef5-104">A pointer type declaration takes one of the following forms:</span></span>

``` csharp
type* identifier;
void* identifier; //allowed but not recommended
```

<span data-ttu-id="bdef5-105">在指针类型中的 `*` 之前指定的类型被称为“referent 类型”。</span><span class="sxs-lookup"><span data-stu-id="bdef5-105">The type specified before the `*` in a pointer type is called the **referent type**.</span></span> <span data-ttu-id="bdef5-106">以下任一类型均可为 referent 类型：</span><span class="sxs-lookup"><span data-stu-id="bdef5-106">Any of the following types may be a referent type:</span></span>

- <span data-ttu-id="bdef5-107">任何整型类型：[sbyte](../../language-reference/keywords/sbyte.md)、[byte](../../language-reference/keywords/byte.md)、[short](../../language-reference/keywords/short.md)、[ushort](../../language-reference/keywords/ushort.md)、[int](../../language-reference/keywords/int.md)、[uint](../../language-reference/keywords/uint.md)、[long](../../language-reference/keywords/long.md)、[ulong](../../language-reference/keywords/ulong.md)。</span><span class="sxs-lookup"><span data-stu-id="bdef5-107">Any integral type: [sbyte](../../language-reference/keywords/sbyte.md), [byte](../../language-reference/keywords/byte.md), [short](../../language-reference/keywords/short.md), [ushort](../../language-reference/keywords/ushort.md), [int](../../language-reference/keywords/int.md), [uint](../../language-reference/keywords/uint.md), [long](../../language-reference/keywords/long.md), [ulong](../../language-reference/keywords/ulong.md).</span></span>
- <span data-ttu-id="bdef5-108">任何浮点类型：[浮点](../../language-reference/keywords/float.md)、[双精度](../../language-reference/keywords/double.md)。</span><span class="sxs-lookup"><span data-stu-id="bdef5-108">Any floating-point type: [float](../../language-reference/keywords/float.md), [double](../../language-reference/keywords/double.md).</span></span>
- <span data-ttu-id="bdef5-109">[字符](../../language-reference/keywords/char.md)。</span><span class="sxs-lookup"><span data-stu-id="bdef5-109">[char](../../language-reference/keywords/char.md).</span></span>
- <span data-ttu-id="bdef5-110">[布尔型](../../language-reference/keywords/bool.md)。</span><span class="sxs-lookup"><span data-stu-id="bdef5-110">[bool](../../language-reference/keywords/bool.md).</span></span>
- <span data-ttu-id="bdef5-111">[小数](../../language-reference/keywords/decimal.md)。</span><span class="sxs-lookup"><span data-stu-id="bdef5-111">[decimal](../../language-reference/keywords/decimal.md).</span></span>
- <span data-ttu-id="bdef5-112">任何[枚举](../../language-reference/keywords/enum.md)类型。</span><span class="sxs-lookup"><span data-stu-id="bdef5-112">Any [enum](../../language-reference/keywords/enum.md) type.</span></span>
- <span data-ttu-id="bdef5-113">任何指针类型。</span><span class="sxs-lookup"><span data-stu-id="bdef5-113">Any pointer type.</span></span> <span data-ttu-id="bdef5-114">这允许如 `void**` 的表达式。</span><span class="sxs-lookup"><span data-stu-id="bdef5-114">This allows expressions such as `void**`.</span></span>
- <span data-ttu-id="bdef5-115">任何仅包含非托管类型字段的用户定义的结构类型。</span><span class="sxs-lookup"><span data-stu-id="bdef5-115">Any user-defined struct type that contains fields of unmanaged types only.</span></span>

<span data-ttu-id="bdef5-116">指针类型不从[对象](../../language-reference/keywords/object.md)继承，并且指针类型与 `object` 之间不存在转换。</span><span class="sxs-lookup"><span data-stu-id="bdef5-116">Pointer types do not inherit from [object](../../language-reference/keywords/object.md) and no conversions exist between pointer types and `object`.</span></span> <span data-ttu-id="bdef5-117">此外，装箱和取消装箱不支持指针。</span><span class="sxs-lookup"><span data-stu-id="bdef5-117">Also, boxing and unboxing do not support pointers.</span></span> <span data-ttu-id="bdef5-118">但是，你可在不同的指针类型之间以及指针类型和整型之间进行转换。</span><span class="sxs-lookup"><span data-stu-id="bdef5-118">However, you can convert between different pointer types and between pointer types and integral types.</span></span>

<span data-ttu-id="bdef5-119">在同一个声明中声明多个指针时，星号 (\*) 仅与基础类型一起写入；而不是用作每个指针名称的前缀。</span><span class="sxs-lookup"><span data-stu-id="bdef5-119">When you declare multiple pointers in the same declaration, the asterisk (\*) is written together with the underlying type only; it is not used as a prefix to each pointer name.</span></span> <span data-ttu-id="bdef5-120">例如:</span><span class="sxs-lookup"><span data-stu-id="bdef5-120">For example:</span></span>

```csharp
int* p1, p2, p3;   // Ok
int *p1, *p2, *p3;   // Invalid in C#
```

<span data-ttu-id="bdef5-121">指针不能指向引用或包含引用的[结构](../../language-reference/keywords/struct.md)，因为无法对对象引用进行垃圾回收，即使有指针指向它也是如此。</span><span class="sxs-lookup"><span data-stu-id="bdef5-121">A pointer cannot point to a reference or to a [struct](../../language-reference/keywords/struct.md) that contains references, because an object reference can be garbage collected even if a pointer is pointing to it.</span></span> <span data-ttu-id="bdef5-122">垃圾回收器并不跟踪是否有任何类型的指针指向对象。</span><span class="sxs-lookup"><span data-stu-id="bdef5-122">The garbage collector does not keep track of whether an object is being pointed to by any pointer types.</span></span>

<span data-ttu-id="bdef5-123">`myType*` 类型的指针变量的值为 `myType` 类型的变量的地址。</span><span class="sxs-lookup"><span data-stu-id="bdef5-123">The value of the pointer variable of type `myType*` is the address of a variable of type `myType`.</span></span> <span data-ttu-id="bdef5-124">下面是指针类型声明的示例：</span><span class="sxs-lookup"><span data-stu-id="bdef5-124">The following are examples of pointer type declarations:</span></span>

|<span data-ttu-id="bdef5-125">示例</span><span class="sxs-lookup"><span data-stu-id="bdef5-125">Example</span></span>|<span data-ttu-id="bdef5-126">说明</span><span class="sxs-lookup"><span data-stu-id="bdef5-126">Description</span></span>|
|-------------|-----------------|
|`int* p`|<span data-ttu-id="bdef5-127">`p` 是指向整数的指针。</span><span class="sxs-lookup"><span data-stu-id="bdef5-127">`p` is a pointer to an integer.</span></span>|
|`int** p`|<span data-ttu-id="bdef5-128">`p` 是指向整数的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="bdef5-128">`p` is a pointer to a pointer to an integer.</span></span>|
|`int*[] p`|<span data-ttu-id="bdef5-129">`p` 是指向整数的指针的一维数组。</span><span class="sxs-lookup"><span data-stu-id="bdef5-129">`p` is a single-dimensional array of pointers to integers.</span></span>|
|`char* p`|<span data-ttu-id="bdef5-130">`p` 是指向字符的指针。</span><span class="sxs-lookup"><span data-stu-id="bdef5-130">`p` is a pointer to a char.</span></span>|
|`void* p`|<span data-ttu-id="bdef5-131">`p` 是指向未知类型的指针。</span><span class="sxs-lookup"><span data-stu-id="bdef5-131">`p` is a pointer to an unknown type.</span></span>|

<span data-ttu-id="bdef5-132">指针间接寻址运算符 \* 可用于访问位于指针变量所指向的位置的内容。</span><span class="sxs-lookup"><span data-stu-id="bdef5-132">The pointer indirection operator \* can be used to access the contents at the location pointed to by the pointer variable.</span></span> <span data-ttu-id="bdef5-133">例如，请考虑以下声明：</span><span class="sxs-lookup"><span data-stu-id="bdef5-133">For example, consider the following declaration:</span></span>

```csharp
int* myVariable;
```

<span data-ttu-id="bdef5-134">表达式 `*myVariable` 表示在 `int` 中包含的地址处找到的 `myVariable` 变量。</span><span class="sxs-lookup"><span data-stu-id="bdef5-134">The expression `*myVariable` denotes the `int` variable found at the address contained in `myVariable`.</span></span>

<span data-ttu-id="bdef5-135">[fixed 语句](../../language-reference/keywords/fixed-statement.md)和[指针转换](../../programming-guide/unsafe-code-pointers/pointer-conversions.md)主题中有几个指针示例。</span><span class="sxs-lookup"><span data-stu-id="bdef5-135">There are several examples of pointers in the topics [fixed Statement](../../language-reference/keywords/fixed-statement.md) and [Pointer Conversions](../../programming-guide/unsafe-code-pointers/pointer-conversions.md).</span></span> <span data-ttu-id="bdef5-136">下面的示例使用 `unsafe` 关键字和 `fixed` 语句，并显示如何递增内部指针。</span><span class="sxs-lookup"><span data-stu-id="bdef5-136">The following example uses the `unsafe` keyword and the `fixed` statement, and shows how to increment an interior pointer.</span></span>  <span data-ttu-id="bdef5-137">你可将此代码粘贴到控制台应用程序的 Main 函数中来运行它。</span><span class="sxs-lookup"><span data-stu-id="bdef5-137">You can paste this code into the Main function of a console application to run it.</span></span> <span data-ttu-id="bdef5-138">这些示例必须使用 [-unsafe](../../language-reference/compiler-options/unsafe-compiler-option.md) 编译器选项集进行编译。</span><span class="sxs-lookup"><span data-stu-id="bdef5-138">These examples must be compiled with the [-unsafe](../../language-reference/compiler-options/unsafe-compiler-option.md) compiler option set.</span></span>

[!code-csharp[Using pointer types](../../../../samples/snippets/csharp/keywords/FixedKeywordExamples.cs#5)]

<span data-ttu-id="bdef5-139">你无法对 `void*` 类型的指针应用间接寻址运算符。</span><span class="sxs-lookup"><span data-stu-id="bdef5-139">You cannot apply the indirection operator to a pointer of type `void*`.</span></span> <span data-ttu-id="bdef5-140">但是，你可以使用强制转换将 void 指针转换为任何其他指针类型，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="bdef5-140">However, you can use a cast to convert a void pointer to any other pointer type, and vice versa.</span></span>

<span data-ttu-id="bdef5-141">指针可以为 `null`。</span><span class="sxs-lookup"><span data-stu-id="bdef5-141">A pointer can be `null`.</span></span> <span data-ttu-id="bdef5-142">将间接寻址运算符应用于 null 指针将导致由实现定义的行为。</span><span class="sxs-lookup"><span data-stu-id="bdef5-142">Applying the indirection operator to a null pointer causes an implementation-defined behavior.</span></span>

<span data-ttu-id="bdef5-143">在方法之间传递指针会导致未定义的行为。</span><span class="sxs-lookup"><span data-stu-id="bdef5-143">Passing pointers between methods can cause undefined behavior.</span></span> <span data-ttu-id="bdef5-144">考虑这种方法，该方法通过 `in`、`out` 或 `ref` 参数或作为函数结果返回一个指向局部变量的指针。</span><span class="sxs-lookup"><span data-stu-id="bdef5-144">Consider a method that returns a pointer to a local variable through an `in`, `out`, or `ref` parameter or as the function result.</span></span> <span data-ttu-id="bdef5-145">如果已在固定块中设置指针，则它指向的变量不再是固定的。</span><span class="sxs-lookup"><span data-stu-id="bdef5-145">If the pointer was set in a fixed block, the variable to which it points may no longer be fixed.</span></span>

<span data-ttu-id="bdef5-146">下表列出了可在不安全的上下文中对指针执行的运算符和语句：</span><span class="sxs-lookup"><span data-stu-id="bdef5-146">The following table lists the operators and statements that can operate on pointers in an unsafe context:</span></span>

|<span data-ttu-id="bdef5-147">运算符/语句</span><span class="sxs-lookup"><span data-stu-id="bdef5-147">Operator/Statement</span></span>|<span data-ttu-id="bdef5-148">使用</span><span class="sxs-lookup"><span data-stu-id="bdef5-148">Use</span></span>|
|-------------------------|---------|
|*|<span data-ttu-id="bdef5-149">执行指针间接寻址。</span><span class="sxs-lookup"><span data-stu-id="bdef5-149">Performs pointer indirection.</span></span>|
|->|<span data-ttu-id="bdef5-150">通过指针访问结构的成员。</span><span class="sxs-lookup"><span data-stu-id="bdef5-150">Accesses a member of a struct through a pointer.</span></span>|
|<span data-ttu-id="bdef5-151">[]</span><span class="sxs-lookup"><span data-stu-id="bdef5-151">[]</span></span>|<span data-ttu-id="bdef5-152">为指针建立索引。</span><span class="sxs-lookup"><span data-stu-id="bdef5-152">Indexes a pointer.</span></span>|
|`&`|<span data-ttu-id="bdef5-153">获取变量的地址。</span><span class="sxs-lookup"><span data-stu-id="bdef5-153">Obtains the address of a variable.</span></span>|
|<span data-ttu-id="bdef5-154">++ 和 --</span><span class="sxs-lookup"><span data-stu-id="bdef5-154">++ and --</span></span>|<span data-ttu-id="bdef5-155">递增和递减指针。</span><span class="sxs-lookup"><span data-stu-id="bdef5-155">Increments and decrements pointers.</span></span>|
|<span data-ttu-id="bdef5-156">+ 和 -</span><span class="sxs-lookup"><span data-stu-id="bdef5-156">+ and -</span></span>|<span data-ttu-id="bdef5-157">执行指针算法。</span><span class="sxs-lookup"><span data-stu-id="bdef5-157">Performs pointer arithmetic.</span></span>|
|<span data-ttu-id="bdef5-158">==、!=、\<、>、\<= 和 >=</span><span class="sxs-lookup"><span data-stu-id="bdef5-158">==, !=, \<, >, \<=, and >=</span></span>|<span data-ttu-id="bdef5-159">比较指针。</span><span class="sxs-lookup"><span data-stu-id="bdef5-159">Compares pointers.</span></span>|
|`stackalloc`|<span data-ttu-id="bdef5-160">在堆栈上分配内存。</span><span class="sxs-lookup"><span data-stu-id="bdef5-160">Allocates memory on the stack.</span></span>|
|<span data-ttu-id="bdef5-161">`fixed` 语句</span><span class="sxs-lookup"><span data-stu-id="bdef5-161">`fixed` statement</span></span>|<span data-ttu-id="bdef5-162">临时固定变量以便找到其地址。</span><span class="sxs-lookup"><span data-stu-id="bdef5-162">Temporarily fixes a variable so that its address may be found.</span></span>|

## <a name="c-language-specification"></a><span data-ttu-id="bdef5-163">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="bdef5-163">C# Language Specification</span></span>

 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="bdef5-164">请参阅</span><span class="sxs-lookup"><span data-stu-id="bdef5-164">See Also</span></span>

- [<span data-ttu-id="bdef5-165">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="bdef5-165">C# Programming Guide</span></span>](../index.md)  
- [<span data-ttu-id="bdef5-166">不安全代码和指针</span><span class="sxs-lookup"><span data-stu-id="bdef5-166">Unsafe Code and Pointers</span></span>](index.md)  
- [<span data-ttu-id="bdef5-167">指针转换</span><span class="sxs-lookup"><span data-stu-id="bdef5-167">Pointer Conversions</span></span>](pointer-conversions.md)  
- [<span data-ttu-id="bdef5-168">指针表达式</span><span class="sxs-lookup"><span data-stu-id="bdef5-168">Pointer Expressions</span></span>](pointer-expressions.md)  
- [<span data-ttu-id="bdef5-169">类型</span><span class="sxs-lookup"><span data-stu-id="bdef5-169">Types</span></span>](../../language-reference/keywords/types.md)  
- [<span data-ttu-id="bdef5-170">unsafe</span><span class="sxs-lookup"><span data-stu-id="bdef5-170">unsafe</span></span>](../../language-reference/keywords/unsafe.md)  
- [<span data-ttu-id="bdef5-171">fixed 语句</span><span class="sxs-lookup"><span data-stu-id="bdef5-171">fixed Statement</span></span>](../../language-reference/keywords/fixed-statement.md)  
- [<span data-ttu-id="bdef5-172">stackalloc</span><span class="sxs-lookup"><span data-stu-id="bdef5-172">stackalloc</span></span>](../../language-reference/keywords/stackalloc.md)  
- [<span data-ttu-id="bdef5-173">装箱和取消装箱</span><span class="sxs-lookup"><span data-stu-id="bdef5-173">Boxing and Unboxing</span></span>](../types/boxing-and-unboxing.md)
