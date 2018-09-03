---
title: short（C# 参考）
ms.date: 03/14/2017
f1_keywords:
- short
- short_CSharpKeyword
helpviewer_keywords:
- short keyword [C#]
ms.assetid: 04c10688-e51a-4a87-bfec-83f7fb42ff11
ms.openlocfilehash: f402b9d2d62bcc3ba265755d59a657b88c197482
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2018
ms.locfileid: "43468561"
---
# <a name="short-c-reference"></a><span data-ttu-id="4fb28-102">short（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="4fb28-102">short (C# Reference)</span></span>

<span data-ttu-id="4fb28-103">`short` 表示一种整数数据类型，该类型根据下表显示的大小和范围存储值。</span><span class="sxs-lookup"><span data-stu-id="4fb28-103">`short` denotes an integral data type that stores values according to the size and range shown in the following table.</span></span>  
  
|<span data-ttu-id="4fb28-104">类型</span><span class="sxs-lookup"><span data-stu-id="4fb28-104">Type</span></span>|<span data-ttu-id="4fb28-105">范围</span><span class="sxs-lookup"><span data-stu-id="4fb28-105">Range</span></span>|<span data-ttu-id="4fb28-106">大小</span><span class="sxs-lookup"><span data-stu-id="4fb28-106">Size</span></span>|<span data-ttu-id="4fb28-107">.NET 类型</span><span class="sxs-lookup"><span data-stu-id="4fb28-107">.NET type</span></span>|  
|----------|-----------|----------|-------------------------|  
|`short`|<span data-ttu-id="4fb28-108">-32,768 到 32,767</span><span class="sxs-lookup"><span data-stu-id="4fb28-108">-32,768 to 32,767</span></span>|<span data-ttu-id="4fb28-109">有符号 16 位整数</span><span class="sxs-lookup"><span data-stu-id="4fb28-109">Signed 16-bit integer</span></span>|<xref:System.Int16?displayProperty=nameWithType>|  
  
## <a name="literals"></a><span data-ttu-id="4fb28-110">文本</span><span class="sxs-lookup"><span data-stu-id="4fb28-110">Literals</span></span>  

<span data-ttu-id="4fb28-111">可以通过为其分配十进制文本、十六进制文本或（从 C# 7.0 开始）二进制文本来声明和初始化 `short` 变量。</span><span class="sxs-lookup"><span data-stu-id="4fb28-111">You can declare and initialize a `short` variable by assigning a decimal literal, a hexadecimal literal, or (starting with C# 7.0) a binary literal to it.</span></span>  <span data-ttu-id="4fb28-112">如果整数文本在 `short` 范围之外（即，如果它小于 <xref:System.Int16.MinValue?displayProperty=nameWithType> 或大于 <xref:System.Int16.MaxValue?displayProperty=nameWithType>），会发生编译错误。</span><span class="sxs-lookup"><span data-stu-id="4fb28-112">If the integer literal is outside the range of `short` (that is, if it is less than <xref:System.Int16.MinValue?displayProperty=nameWithType> or greater than <xref:System.Int16.MaxValue?displayProperty=nameWithType>), a compilation error occurs.</span></span> 

<span data-ttu-id="4fb28-113">在以下示例中，等于 1,034、表示为十进制、十六进制和二进制文本的整数从 [int](../../../csharp/language-reference/keywords/int.md) 隐式转换为 `short` 值。</span><span class="sxs-lookup"><span data-stu-id="4fb28-113">In the following example, integers equal to 1,034 that are represented as decimal, hexadecimal, and binary literals are implicitly converted from [int](../../../csharp/language-reference/keywords/int.md) to `short` values.</span></span>  
  
[!code-csharp[Short](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#Short)]  

> [!NOTE] 
> <span data-ttu-id="4fb28-114">使用前缀 `0x` 或 `0X` 表示十六进制文本，使用前缀 `0b` 或 `0B` 表示二进制文本。</span><span class="sxs-lookup"><span data-stu-id="4fb28-114">You use the prefix `0x` or `0X` to denote a hexadecimal literal and the prefix `0b` or `0B` to denote a binary literal.</span></span> <span data-ttu-id="4fb28-115">十进制文本没有前缀。</span><span class="sxs-lookup"><span data-stu-id="4fb28-115">Decimal literals have no prefix.</span></span>

<span data-ttu-id="4fb28-116">从 C# 7.0 开始，添加了一些功能以增强可读性。</span><span class="sxs-lookup"><span data-stu-id="4fb28-116">Starting with C# 7.0, a couple of features have been added to enhance readability.</span></span> 
 - <span data-ttu-id="4fb28-117">C# 7.0 允许将下划线字符 (`_`) 用作数字分隔符。</span><span class="sxs-lookup"><span data-stu-id="4fb28-117">C# 7.0 allows the usage of the underscore character, `_`, as a digit separator.</span></span>
 - <span data-ttu-id="4fb28-118">C# 7.2 允许将 `_` 用作二进制或十六进制文本的数字分隔符，位于前缀之后。</span><span class="sxs-lookup"><span data-stu-id="4fb28-118">C# 7.2 allows `_` to be used as a digit separator for a binary or hexadecimal literal, after the prefix.</span></span> <span data-ttu-id="4fb28-119">十进制文本不能够有前导下划线。</span><span class="sxs-lookup"><span data-stu-id="4fb28-119">A decimal literal isn't permitted to have a leading underscore.</span></span>

<span data-ttu-id="4fb28-120">下面是一些示例。</span><span class="sxs-lookup"><span data-stu-id="4fb28-120">Some examples are shown below.</span></span>

[!code-csharp[Short](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#ShortS)]  
 
## <a name="compiler-overload-resolution"></a><span data-ttu-id="4fb28-121">编译器重载解析</span><span class="sxs-lookup"><span data-stu-id="4fb28-121">Compiler overload resolution</span></span>

 <span data-ttu-id="4fb28-122">调用重载方法时必须使用强制转换。</span><span class="sxs-lookup"><span data-stu-id="4fb28-122">A cast must be used when calling overloaded methods.</span></span> <span data-ttu-id="4fb28-123">以下面使用 `short` 和 [int](../../../csharp/language-reference/keywords/int.md) 参数的重载方法为例：</span><span class="sxs-lookup"><span data-stu-id="4fb28-123">Consider, for example, the following overloaded methods that use `short` and [int](../../../csharp/language-reference/keywords/int.md) parameters:</span></span>  
  
```csharp  
public static void SampleMethod(int i) {}  
public static void SampleMethod(short s) {}  
```  
  
 <span data-ttu-id="4fb28-124">使用 `short` 强制转换可保证调用正确的类型，例如：</span><span class="sxs-lookup"><span data-stu-id="4fb28-124">Using the `short` cast guarantees that the correct type is called, for example:</span></span>  
  
```csharp  
SampleMethod(5);         // Calling the method with the int parameter  
SampleMethod((short)5);  // Calling the method with the short parameter  
```  
  
## <a name="conversions"></a><span data-ttu-id="4fb28-125">转换</span><span class="sxs-lookup"><span data-stu-id="4fb28-125">Conversions</span></span>  

 <span data-ttu-id="4fb28-126">存在从 `short` 到 [int](../../../csharp/language-reference/keywords/int.md)、[long](../../../csharp/language-reference/keywords/long.md)、[float](../../../csharp/language-reference/keywords/float.md)、[double](../../../csharp/language-reference/keywords/double.md) 或 [decimal](../../../csharp/language-reference/keywords/decimal.md) 的预定义隐式转换。</span><span class="sxs-lookup"><span data-stu-id="4fb28-126">There is a predefined implicit conversion from `short` to [int](../../../csharp/language-reference/keywords/int.md), [long](../../../csharp/language-reference/keywords/long.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md), or [decimal](../../../csharp/language-reference/keywords/decimal.md).</span></span>  
  
 <span data-ttu-id="4fb28-127">不能将存储大小更大的非文本数值类型隐式转换为 `short` 类型（有关整型类型的存储大小的信息，请参阅[整型类型表](../../../csharp/language-reference/keywords/integral-types-table.md)）。</span><span class="sxs-lookup"><span data-stu-id="4fb28-127">You cannot implicitly convert nonliteral numeric types of larger storage size to `short` (see [Integral Types Table](../../../csharp/language-reference/keywords/integral-types-table.md) for the storage sizes of integral types).</span></span> <span data-ttu-id="4fb28-128">以下面两个 `short` 变量 `x` 和 `y` 为例：</span><span class="sxs-lookup"><span data-stu-id="4fb28-128">Consider, for example, the following two `short` variables `x` and `y`:</span></span>  
  
```csharp  
short x = 5, y = 12;  
```  
  
 <span data-ttu-id="4fb28-129">以下赋值语句将产生一个编译器错误，原因是赋值运算符右侧的算术表达式的计算结果默认为 [int](../../../csharp/language-reference/keywords/int.md) 类型。</span><span class="sxs-lookup"><span data-stu-id="4fb28-129">The following assignment statement produces a compilation error because the arithmetic expression on the right-hand side of the assignment operator evaluates to [int](../../../csharp/language-reference/keywords/int.md) by default.</span></span>  
  
```csharp
short z  = x + y;        // Compiler error CS0266: no conversion from int to short
```

 <span data-ttu-id="4fb28-130">若要解决此问题，请使用强制转换：</span><span class="sxs-lookup"><span data-stu-id="4fb28-130">To fix this problem, use a cast:</span></span>  
  
```csharp
short z  = (short)(x + y);   // Explicit conversion
```
  
 <span data-ttu-id="4fb28-131">在目标变量具有相同或更大的存储大小时，还可以使用下列语句：</span><span class="sxs-lookup"><span data-stu-id="4fb28-131">It is also possible to use the following statements, where the destination variable has the same storage size or a larger storage size:</span></span>  
  
```csharp  
int m = x + y;  
long n = x + y;  
```  
  
 <span data-ttu-id="4fb28-132">不存在从浮点型到 `short` 类型的隐式转换。</span><span class="sxs-lookup"><span data-stu-id="4fb28-132">There is no implicit conversion from floating-point types to `short`.</span></span> <span data-ttu-id="4fb28-133">例如，除非使用显式强制转换，否则以下语句将生成编译器错误：</span><span class="sxs-lookup"><span data-stu-id="4fb28-133">For example, the following statement generates a compiler error unless an explicit cast is used:</span></span>  
  
```csharp  
short x = 3.0;          // Error: no implicit conversion from double  
short y = (short)3.0;   // OK: explicit conversion  
```  
  
 <span data-ttu-id="4fb28-134">有关兼用浮点类型和整型类型的算术表达式的信息，请参阅 [float](../../../csharp/language-reference/keywords/float.md) 和 [double](../../../csharp/language-reference/keywords/double.md)。</span><span class="sxs-lookup"><span data-stu-id="4fb28-134">For information on arithmetic expressions with mixed floating-point types and integral types, see [float](../../../csharp/language-reference/keywords/float.md) and [double](../../../csharp/language-reference/keywords/double.md).</span></span>  
  
 <span data-ttu-id="4fb28-135">有关隐式数值转换规则的详细信息，请参阅[隐式数值转换表](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)。</span><span class="sxs-lookup"><span data-stu-id="4fb28-135">For more information on implicit numeric conversion rules, see the [Implicit Numeric Conversions Table](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="4fb28-136">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="4fb28-136">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="4fb28-137">请参阅</span><span class="sxs-lookup"><span data-stu-id="4fb28-137">See Also</span></span>

- <xref:System.Int16>  
- [<span data-ttu-id="4fb28-138">C# 参考</span><span class="sxs-lookup"><span data-stu-id="4fb28-138">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="4fb28-139">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="4fb28-139">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="4fb28-140">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="4fb28-140">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
- [<span data-ttu-id="4fb28-141">整型表</span><span class="sxs-lookup"><span data-stu-id="4fb28-141">Integral Types Table</span></span>](../../../csharp/language-reference/keywords/integral-types-table.md)  
- [<span data-ttu-id="4fb28-142">内置类型表</span><span class="sxs-lookup"><span data-stu-id="4fb28-142">Built-In Types Table</span></span>](../../../csharp/language-reference/keywords/built-in-types-table.md)  
- [<span data-ttu-id="4fb28-143">隐式数值转换表</span><span class="sxs-lookup"><span data-stu-id="4fb28-143">Implicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)  
- [<span data-ttu-id="4fb28-144">显式数值转换表</span><span class="sxs-lookup"><span data-stu-id="4fb28-144">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)
