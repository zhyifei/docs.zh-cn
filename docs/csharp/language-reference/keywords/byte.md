---
title: byte（C# 参考）
ms.date: 03/14/2017
f1_keywords:
- byte
- byte_CSharpKeyword
helpviewer_keywords:
- byte keyword [C#]
ms.assetid: 111f1db9-ca32-4f0e-b497-4783517eda47
ms.openlocfilehash: 28acbe67b85637550fdb1f5e290a9abb60bf5c65
ms.sourcegitcommit: f9e38d31288fe5962e6be5b0cc286da633482873
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37027884"
---
# <a name="byte-c-reference"></a><span data-ttu-id="e69a9-102">byte（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="e69a9-102">byte (C# Reference)</span></span>

<span data-ttu-id="e69a9-103">`byte` 表示存储下表所示值的整型类型。</span><span class="sxs-lookup"><span data-stu-id="e69a9-103">`byte` denotes an integral type that stores values as indicated in the following table.</span></span>  
  
|<span data-ttu-id="e69a9-104">类型</span><span class="sxs-lookup"><span data-stu-id="e69a9-104">Type</span></span>|<span data-ttu-id="e69a9-105">范围</span><span class="sxs-lookup"><span data-stu-id="e69a9-105">Range</span></span>|<span data-ttu-id="e69a9-106">大小</span><span class="sxs-lookup"><span data-stu-id="e69a9-106">Size</span></span>|<span data-ttu-id="e69a9-107">.NET 类型</span><span class="sxs-lookup"><span data-stu-id="e69a9-107">.NET type</span></span>|  
|----------|-----------|----------|-------------------------|  
|`byte`|<span data-ttu-id="e69a9-108">0 到 255</span><span class="sxs-lookup"><span data-stu-id="e69a9-108">0 to 255</span></span>|<span data-ttu-id="e69a9-109">无符号的 8 位整数</span><span class="sxs-lookup"><span data-stu-id="e69a9-109">Unsigned 8-bit integer</span></span>|<xref:System.Byte?displayProperty=nameWithType>|  
  
## <a name="literals"></a><span data-ttu-id="e69a9-110">文本</span><span class="sxs-lookup"><span data-stu-id="e69a9-110">Literals</span></span>  

 <span data-ttu-id="e69a9-111">可以通过为其分配十进制文本、十六进制文本或（从 C# 7.0 开始）二进制文本来声明和初始化 `byte` 变量。</span><span class="sxs-lookup"><span data-stu-id="e69a9-111">You can declare and initialize a `byte` variable by assigning a decimal literal, a hexadecimal literal, or (starting with C# 7.0) a binary literal to it.</span></span> <span data-ttu-id="e69a9-112">如果整数文本在 `byte` 范围之外（即，如果它小于 <xref:System.Byte.MinValue?displayProperty=nameWithType> 或大于 <xref:System.Byte.MaxValue?displayProperty=nameWithType>），会发生编译错误。</span><span class="sxs-lookup"><span data-stu-id="e69a9-112">If the integer literal is outside the range of `byte` (that is, if it is less than <xref:System.Byte.MinValue?displayProperty=nameWithType> or greater than <xref:System.Byte.MaxValue?displayProperty=nameWithType>), a compilation error occurs.</span></span>

<span data-ttu-id="e69a9-113">在以下示例中，等于 201、表示为十进制、十六进制和二进制文本的整数从 [int](../../../csharp/language-reference/keywords/int.md) 隐式转换为 `byte` 值。</span><span class="sxs-lookup"><span data-stu-id="e69a9-113">In the following example, integers equal to 201 that are represented as decimal, hexadecimal, and binary literals are implicitly converted from [int](../../../csharp/language-reference/keywords/int.md) to `byte` values.</span></span>    
  
[!code-csharp[Byte](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#Byte)]  

> [!NOTE] 
> <span data-ttu-id="e69a9-114">使用前缀 `0x` 或 `0X` 表示十六进制文本，使用前缀 `0b` 或 `0B` 表示二进制文本。</span><span class="sxs-lookup"><span data-stu-id="e69a9-114">You use the prefix `0x` or `0X` to denote a hexadecimal literal and the prefix `0b` or `0B` to denote a binary literal.</span></span> <span data-ttu-id="e69a9-115">十进制文本没有前缀。</span><span class="sxs-lookup"><span data-stu-id="e69a9-115">Decimal literals have no prefix.</span></span>

<span data-ttu-id="e69a9-116">从 C# 7.0 开始，添加了一些功能以增强可读性。</span><span class="sxs-lookup"><span data-stu-id="e69a9-116">Starting with C# 7.0, a couple of features have been added to enhance readability.</span></span> 
 - <span data-ttu-id="e69a9-117">C# 7.0 允许将下划线字符 (`_`) 用作数字分隔符。</span><span class="sxs-lookup"><span data-stu-id="e69a9-117">C# 7.0 allows the usage of the underscore character, `_`, as a digit separator.</span></span>
 - <span data-ttu-id="e69a9-118">C# 7.2 允许将 `_` 用作二进制或十六进制文本的数字分隔符，位于前缀之后。</span><span class="sxs-lookup"><span data-stu-id="e69a9-118">C# 7.2 allows `_` to be used as a digit separator for a binary or hexadecimal literal, after the prefix.</span></span> <span data-ttu-id="e69a9-119">十进制文本不能够有前导下划线。</span><span class="sxs-lookup"><span data-stu-id="e69a9-119">A decimal literal isn't permitted to have a leading underscore.</span></span>

<span data-ttu-id="e69a9-120">下面是一些示例。</span><span class="sxs-lookup"><span data-stu-id="e69a9-120">Some examples are shown below.</span></span>

[!code-csharp[Byte](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#ByteS)]  
 
## <a name="conversions"></a><span data-ttu-id="e69a9-121">转换</span><span class="sxs-lookup"><span data-stu-id="e69a9-121">Conversions</span></span>  
 <span data-ttu-id="e69a9-122">存在从 `byte` 到 [short](../../../csharp/language-reference/keywords/short.md)、[ushort](../../../csharp/language-reference/keywords/ushort.md)、[int](../../../csharp/language-reference/keywords/int.md)、[uint](../../../csharp/language-reference/keywords/uint.md)、[long](../../../csharp/language-reference/keywords/long.md)、[ulong](../../../csharp/language-reference/keywords/ulong.md)、[float](../../../csharp/language-reference/keywords/float.md)、[double](../../../csharp/language-reference/keywords/double.md) 或 [decimal](../../../csharp/language-reference/keywords/decimal.md) 的预定义隐式转换。</span><span class="sxs-lookup"><span data-stu-id="e69a9-122">There is a predefined implicit conversion from `byte` to [short](../../../csharp/language-reference/keywords/short.md), [ushort](../../../csharp/language-reference/keywords/ushort.md), [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md), [ulong](../../../csharp/language-reference/keywords/ulong.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md), or [decimal](../../../csharp/language-reference/keywords/decimal.md).</span></span>  
  
 <span data-ttu-id="e69a9-123">不可将大存储大小的非文本数字类型隐式转换为 `byte`。</span><span class="sxs-lookup"><span data-stu-id="e69a9-123">You cannot implicitly convert non-literal numeric types of larger storage size to `byte`.</span></span> <span data-ttu-id="e69a9-124">有关整型类型存储大小的详细信息，请参阅[整型类型表](../../../csharp/language-reference/keywords/integral-types-table.md)。</span><span class="sxs-lookup"><span data-stu-id="e69a9-124">For more information on the storage sizes of integral types, see [Integral Types Table](../../../csharp/language-reference/keywords/integral-types-table.md).</span></span> <span data-ttu-id="e69a9-125">以下面两个 `byte` 变量 `x` 和 `y` 为例：</span><span class="sxs-lookup"><span data-stu-id="e69a9-125">Consider, for example, the following two `byte` variables `x` and `y`:</span></span>  
  
```csharp  
byte x = 10, y = 20;  
```  
  
 <span data-ttu-id="e69a9-126">以下赋值语句将产生一个编译器错误，原因是赋值运算符右侧的算术表达式在默认情况下的计算结果为 `int` 类型。</span><span class="sxs-lookup"><span data-stu-id="e69a9-126">The following assignment statement will produce a compilation error, because the arithmetic expression on the right-hand side of the assignment operator evaluates to `int` by default.</span></span>  
  
```csharp  
// Error: conversion from int to byte:  
byte z = x + y;  
```  
  
 <span data-ttu-id="e69a9-127">若要解决此问题，请使用强制转换：</span><span class="sxs-lookup"><span data-stu-id="e69a9-127">To fix this problem, use a cast:</span></span>  
  
```csharp  
// OK: explicit conversion:  
byte z = (byte)(x + y);  
```  
  
 <span data-ttu-id="e69a9-128">但是，在目标变量具有相同或更大的存储大小时，也可以使用下列语句：</span><span class="sxs-lookup"><span data-stu-id="e69a9-128">It is possible though, to use the following statements where the destination variable has the same storage size or a larger storage size:</span></span>  
  
```csharp  
int x = 10, y = 20;  
int m = x + y;  
long n = x + y;  
```  
  
 <span data-ttu-id="e69a9-129">此外，不存在从浮点类型到 `byte` 类型的隐式转换。</span><span class="sxs-lookup"><span data-stu-id="e69a9-129">Also, there is no implicit conversion from floating-point types to `byte`.</span></span> <span data-ttu-id="e69a9-130">例如，除非使用显式强制转换，否则以下语句将生成编译器错误：</span><span class="sxs-lookup"><span data-stu-id="e69a9-130">For example, the following statement generates a compiler error unless an explicit cast is used:</span></span>  
  
```csharp  
// Error: no implicit conversion from double:  
byte x = 3.0;   
// OK: explicit conversion:  
byte y = (byte)3.0;  
```  
  
 <span data-ttu-id="e69a9-131">在调用重载方法时，必须使用转换。</span><span class="sxs-lookup"><span data-stu-id="e69a9-131">When calling overloaded methods, a cast must be used.</span></span> <span data-ttu-id="e69a9-132">以下面使用 `byte` 和 [int](../../../csharp/language-reference/keywords/int.md) 参数的重载方法为例：</span><span class="sxs-lookup"><span data-stu-id="e69a9-132">Consider, for example, the following overloaded methods that use `byte` and [int](../../../csharp/language-reference/keywords/int.md) parameters:</span></span>  
  
```csharp  
public static void SampleMethod(int i) {}  
public static void SampleMethod(byte b) {}  
```  
  
 <span data-ttu-id="e69a9-133">使用 `byte` 强制转换可保证调用正确的类型，例如：</span><span class="sxs-lookup"><span data-stu-id="e69a9-133">Using the `byte` cast guarantees that the correct type is called, for example:</span></span>  
  
```csharp  
// Calling the method with the int parameter:  
SampleMethod(5);  
// Calling the method with the byte parameter:  
SampleMethod((byte)5);  
```  
  
 <span data-ttu-id="e69a9-134">有关兼用浮点类型和整型类型的算术表达式的信息，请参阅 [float](../../../csharp/language-reference/keywords/float.md) 和 [double](../../../csharp/language-reference/keywords/double.md)。</span><span class="sxs-lookup"><span data-stu-id="e69a9-134">For information on arithmetic expressions with mixed floating-point types and integral types, see [float](../../../csharp/language-reference/keywords/float.md) and [double](../../../csharp/language-reference/keywords/double.md).</span></span>  
  
 <span data-ttu-id="e69a9-135">有关隐式数值转换规则的详细信息，请参阅[隐式数值转换表](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)。</span><span class="sxs-lookup"><span data-stu-id="e69a9-135">For more information on implicit numeric conversion rules, see the [Implicit Numeric Conversions Table](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="e69a9-136">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="e69a9-136">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e69a9-137">请参阅</span><span class="sxs-lookup"><span data-stu-id="e69a9-137">See Also</span></span>  
 <xref:System.Byte>  
 [<span data-ttu-id="e69a9-138">C# 参考</span><span class="sxs-lookup"><span data-stu-id="e69a9-138">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="e69a9-139">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="e69a9-139">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="e69a9-140">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="e69a9-140">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="e69a9-141">整型表</span><span class="sxs-lookup"><span data-stu-id="e69a9-141">Integral Types Table</span></span>](../../../csharp/language-reference/keywords/integral-types-table.md)  
 [<span data-ttu-id="e69a9-142">内置类型表</span><span class="sxs-lookup"><span data-stu-id="e69a9-142">Built-In Types Table</span></span>](../../../csharp/language-reference/keywords/built-in-types-table.md)  
 [<span data-ttu-id="e69a9-143">隐式数值转换表</span><span class="sxs-lookup"><span data-stu-id="e69a9-143">Implicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)  
 [<span data-ttu-id="e69a9-144">显式数值转换表</span><span class="sxs-lookup"><span data-stu-id="e69a9-144">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)
