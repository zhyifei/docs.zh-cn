---
title: long（C# 参考）
ms.date: 03/14/2017
f1_keywords:
- long_CSharpKeyword
- long
helpviewer_keywords:
- long keyword [C#]
ms.assetid: f9b24319-1f39-48be-a42b-d528ee28a7fd
ms.openlocfilehash: 106b832801a373ca387be455ef1c0df4233621d0
ms.sourcegitcommit: f9e38d31288fe5962e6be5b0cc286da633482873
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37027819"
---
# <a name="long-c-reference"></a><span data-ttu-id="52d67-102">long（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="52d67-102">long (C# Reference)</span></span>

<span data-ttu-id="52d67-103">`long` 表示一种整型类型，该类型根据下表显示的大小和范围存储值。</span><span class="sxs-lookup"><span data-stu-id="52d67-103">`long` denotes an integral type that stores values according to the size and range shown in the following table.</span></span>  
  
|<span data-ttu-id="52d67-104">类型</span><span class="sxs-lookup"><span data-stu-id="52d67-104">Type</span></span>|<span data-ttu-id="52d67-105">范围</span><span class="sxs-lookup"><span data-stu-id="52d67-105">Range</span></span>|<span data-ttu-id="52d67-106">大小</span><span class="sxs-lookup"><span data-stu-id="52d67-106">Size</span></span>|<span data-ttu-id="52d67-107">.NET 类型</span><span class="sxs-lookup"><span data-stu-id="52d67-107">.NET type</span></span>|  
|----------|-----------|----------|-------------------------|  
|`long`|<span data-ttu-id="52d67-108">-9,223,372,036,854,775,808 到 9,223,372,036,854,775,807</span><span class="sxs-lookup"><span data-stu-id="52d67-108">-9,223,372,036,854,775,808 to 9,223,372,036,854,775,807</span></span>|<span data-ttu-id="52d67-109">64 位带符号整数</span><span class="sxs-lookup"><span data-stu-id="52d67-109">Signed 64-bit integer</span></span>|<xref:System.Int64?displayProperty=nameWithType>|  
  
## <a name="literals"></a><span data-ttu-id="52d67-110">文本</span><span class="sxs-lookup"><span data-stu-id="52d67-110">Literals</span></span> 

<span data-ttu-id="52d67-111">可以通过为其分配十进制文本、十六进制文本或（从 C# 7.0 开始）二进制文本来声明和初始化 `long` 变量。</span><span class="sxs-lookup"><span data-stu-id="52d67-111">You can declare and initialize a `long` variable by assigning a decimal literal, a hexadecimal literal, or (starting with C# 7.0) a binary literal to it.</span></span> 

<span data-ttu-id="52d67-112">在以下示例中，表示为十进制、十六进制和二进制文本的等于 4,294,967,296 的整数被分配给 `long` 值。</span><span class="sxs-lookup"><span data-stu-id="52d67-112">In the following example, integers equal to 4,294,967,296 that are represented as decimal, hexadecimal, and binary literals are assigned to `long` values.</span></span>  
  
[!code-csharp[long](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#Long)]  

> [!NOTE] 
> <span data-ttu-id="52d67-113">使用前缀 `0x` 或 `0X` 表示十六进制文本，使用前缀 `0b` 或 `0B` 表示二进制文本。</span><span class="sxs-lookup"><span data-stu-id="52d67-113">You use the prefix `0x` or `0X` to denote a hexadecimal literal and the prefix `0b` or `0B` to denote a binary literal.</span></span> <span data-ttu-id="52d67-114">十进制文本没有前缀。</span><span class="sxs-lookup"><span data-stu-id="52d67-114">Decimal literals have no prefix.</span></span> 

<span data-ttu-id="52d67-115">从 C# 7.0 开始，添加了一些功能以增强可读性。</span><span class="sxs-lookup"><span data-stu-id="52d67-115">Starting with C# 7.0, a couple of features have been added to enhance readability.</span></span> 
 - <span data-ttu-id="52d67-116">C# 7.0 允许将下划线字符 (`_`) 用作数字分隔符。</span><span class="sxs-lookup"><span data-stu-id="52d67-116">C# 7.0 allows the usage of the underscore character, `_`, as a digit separator.</span></span>
 - <span data-ttu-id="52d67-117">C# 7.2 允许将 `_` 用作二进制或十六进制文本的数字分隔符，位于前缀之后。</span><span class="sxs-lookup"><span data-stu-id="52d67-117">C# 7.2 allows `_` to be used as a digit separator for a binary or hexadecimal literal, after the prefix.</span></span> <span data-ttu-id="52d67-118">十进制文本不能够有前导下划线。</span><span class="sxs-lookup"><span data-stu-id="52d67-118">A decimal literal isn't permitted to have a leading underscore.</span></span>

<span data-ttu-id="52d67-119">下面是一些示例。</span><span class="sxs-lookup"><span data-stu-id="52d67-119">Some examples are shown below.</span></span>

[!code-csharp[long](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#LongS)]  
 
 <span data-ttu-id="52d67-120">整数文本还可包含表示类型的后缀。</span><span class="sxs-lookup"><span data-stu-id="52d67-120">Integer literals can also include a suffix that denotes the type.</span></span> <span data-ttu-id="52d67-121">后缀 `L` 表示 `long`。</span><span class="sxs-lookup"><span data-stu-id="52d67-121">The suffix `L` denotes a `long`.</span></span> <span data-ttu-id="52d67-122">以下示例使用 `L` 后缀来表示长整型：</span><span class="sxs-lookup"><span data-stu-id="52d67-122">The following example uses the `L` suffix to denote a long integer:</span></span>
 
```csharp
long value = 4294967296L;  
```  

> [!NOTE]
>  <span data-ttu-id="52d67-123">也可用小写字母“l”作后缀。</span><span class="sxs-lookup"><span data-stu-id="52d67-123">You can also use the lowercase letter "l" as a suffix.</span></span> <span data-ttu-id="52d67-124">但是，字母“l”容易与数字“1”混淆，因此会生成编译器警告。</span><span class="sxs-lookup"><span data-stu-id="52d67-124">However, this generates a compiler warning because the letter "l" is easily confused with the digit "1."</span></span> <span data-ttu-id="52d67-125">为清楚起见，请使用“L”。</span><span class="sxs-lookup"><span data-stu-id="52d67-125">Use "L" for clarity.</span></span>  
  
 <span data-ttu-id="52d67-126">使用后缀 `L` 时，将根据整数的大小确定它的类型是 `long` 还是 [ulong](../../../csharp/language-reference/keywords/ulong.md)。</span><span class="sxs-lookup"><span data-stu-id="52d67-126">When you use the suffix `L`, the type of the literal integer is determined to be either `long` or [ulong](../../../csharp/language-reference/keywords/ulong.md), depending on its size.</span></span> <span data-ttu-id="52d67-127">在此例中，它是 `long`，因为它小于 [ulong](../../../csharp/language-reference/keywords/ulong.md) 的范围的下限。</span><span class="sxs-lookup"><span data-stu-id="52d67-127">In this case, it is `long` because it less than the range of [ulong](../../../csharp/language-reference/keywords/ulong.md).</span></span>  
  
 <span data-ttu-id="52d67-128">此后缀常用于调用重载方法。</span><span class="sxs-lookup"><span data-stu-id="52d67-128">A common use of the suffix is to call overloaded methods.</span></span> <span data-ttu-id="52d67-129">例如，以下重载方法具有 `long` 和 [int](../../../csharp/language-reference/keywords/int.md) 类型的参数：</span><span class="sxs-lookup"><span data-stu-id="52d67-129">For example, the following overloaded methods have parameters of type `long` and [int](../../../csharp/language-reference/keywords/int.md):</span></span>  
  
```csharp
public static void SampleMethod(int i) {}  
public static void SampleMethod(long l) {}  
```  
  
 <span data-ttu-id="52d67-130">`L` 后缀可确保调用正确的重载：</span><span class="sxs-lookup"><span data-stu-id="52d67-130">The `L` suffix guarantees that the correct overload is called:</span></span>  
  
```csharp  
SampleMethod(5);    // Calls the method with the int parameter  
SampleMethod(5L);   // Calls the method with the long parameter  
```  
<span data-ttu-id="52d67-131">如果整数文本没有后缀，则其类型为以下类型中可表示其值的第一个类型：</span><span class="sxs-lookup"><span data-stu-id="52d67-131">If an integer literal has no suffix, its type is the first of the following types in which its value can be represented:</span></span> 

1. [<span data-ttu-id="52d67-132">int</span><span class="sxs-lookup"><span data-stu-id="52d67-132">int</span></span>](int.md)
2. [<span data-ttu-id="52d67-133">uint</span><span class="sxs-lookup"><span data-stu-id="52d67-133">uint</span></span>](../../../csharp/language-reference/keywords/uint.md)
3. `long`
4. [<span data-ttu-id="52d67-134">ulong</span><span class="sxs-lookup"><span data-stu-id="52d67-134">ulong</span></span>](../../../csharp/language-reference/keywords/ulong.md) 

<span data-ttu-id="52d67-135">上例中的文本 4294967296 是 `long` 类型，因为它超出了 [uint](../../../csharp/language-reference/keywords/uint.md) 的范围（有关整型类型的存储大小，请参阅[整型类型表](../../../csharp/language-reference/keywords/integral-types-table.md)）。</span><span class="sxs-lookup"><span data-stu-id="52d67-135">The literal 4294967296 in the previous examples is of type `long`, because it exceeds the range of [uint](../../../csharp/language-reference/keywords/uint.md) (see [Integral Types Table](../../../csharp/language-reference/keywords/integral-types-table.md) for the storage sizes of integral types).</span></span>  
  
 <span data-ttu-id="52d67-136">如果在同一个表达式中同时使用 `long` 类型和其他整型类型，表达式的计算结果为 `long`（在关系表达式或布尔表达式中为 [bool](../../../csharp/language-reference/keywords/bool.md)）类型。</span><span class="sxs-lookup"><span data-stu-id="52d67-136">If you use the `long` type with other integral types in the same expression, the expression is evaluated as `long` (or [bool](../../../csharp/language-reference/keywords/bool.md) in the case of relational or Boolean expressions).</span></span> <span data-ttu-id="52d67-137">例如，下列表达式计算为 `long`：</span><span class="sxs-lookup"><span data-stu-id="52d67-137">For example, the following expression evaluates as `long`:</span></span>  
  
```csharp  
898L + 88  
```  
  
 <span data-ttu-id="52d67-138">有关兼用浮点类型和整型类型的算术表达式的信息，请参阅 [float](../../../csharp/language-reference/keywords/float.md) 和 [double](../../../csharp/language-reference/keywords/double.md)。</span><span class="sxs-lookup"><span data-stu-id="52d67-138">For information on arithmetic expressions with mixed floating-point types and integral types, see [float](../../../csharp/language-reference/keywords/float.md) and [double](../../../csharp/language-reference/keywords/double.md).</span></span>  
  
## <a name="conversions"></a><span data-ttu-id="52d67-139">转换</span><span class="sxs-lookup"><span data-stu-id="52d67-139">Conversions</span></span>  
 <span data-ttu-id="52d67-140">存在从 `long` 到 [float](../../../csharp/language-reference/keywords/float.md)、[double](../../../csharp/language-reference/keywords/double.md) 或 [decimal](../../../csharp/language-reference/keywords/decimal.md) 的预定义隐式转换。</span><span class="sxs-lookup"><span data-stu-id="52d67-140">There is a predefined implicit conversion from `long` to [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md), or [decimal](../../../csharp/language-reference/keywords/decimal.md).</span></span> <span data-ttu-id="52d67-141">其他情况下必须使用强制转换。</span><span class="sxs-lookup"><span data-stu-id="52d67-141">Otherwise a cast must be used.</span></span> <span data-ttu-id="52d67-142">例如，如果不使用显式强制转换，以下语句会生成编译错误：</span><span class="sxs-lookup"><span data-stu-id="52d67-142">For example, the following statement will produce a compilation error without an explicit cast:</span></span>  
  
```csharp  
int x = 8L;        // Error: no implicit conversion from long to int  
int x = (int)8L;   // OK: explicit conversion to int  
```  
  
 <span data-ttu-id="52d67-143">存在从 [sbyte](../../../csharp/language-reference/keywords/sbyte.md)、[byte](../../../csharp/language-reference/keywords/byte.md)、[short](../../../csharp/language-reference/keywords/short.md)、[ushort](../../../csharp/language-reference/keywords/ushort.md)、[int](../../../csharp/language-reference/keywords/int.md)、[uint](../../../csharp/language-reference/keywords/uint.md) 或 [char](../../../csharp/language-reference/keywords/char.md) 到 `long` 的预定义隐式转换。</span><span class="sxs-lookup"><span data-stu-id="52d67-143">There is a predefined implicit conversion from [sbyte](../../../csharp/language-reference/keywords/sbyte.md), [byte](../../../csharp/language-reference/keywords/byte.md), [short](../../../csharp/language-reference/keywords/short.md), [ushort](../../../csharp/language-reference/keywords/ushort.md), [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), or [char](../../../csharp/language-reference/keywords/char.md) to `long`.</span></span>  
  
 <span data-ttu-id="52d67-144">另请注意，不存在从浮点类型到 `long` 类型的隐式转换。</span><span class="sxs-lookup"><span data-stu-id="52d67-144">Notice also that there is no implicit conversion from floating-point types to `long`.</span></span> <span data-ttu-id="52d67-145">例如，除非使用显式强制转换，否则以下语句将生成编译器错误：</span><span class="sxs-lookup"><span data-stu-id="52d67-145">For example, the following statement generates a compiler error unless an explicit cast is used:</span></span>  
  
```csharp  
long x = 3.0;         // Error: no implicit conversion from double  
long y = (long)3.0;   // OK: explicit conversion  
```  
  
## <a name="c-language-specification"></a><span data-ttu-id="52d67-146">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="52d67-146">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="52d67-147">请参阅</span><span class="sxs-lookup"><span data-stu-id="52d67-147">See Also</span></span>  
 <xref:System.Int64>  
 [<span data-ttu-id="52d67-148">C# 参考</span><span class="sxs-lookup"><span data-stu-id="52d67-148">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="52d67-149">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="52d67-149">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="52d67-150">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="52d67-150">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="52d67-151">整型表</span><span class="sxs-lookup"><span data-stu-id="52d67-151">Integral Types Table</span></span>](../../../csharp/language-reference/keywords/integral-types-table.md)  
 [<span data-ttu-id="52d67-152">内置类型表</span><span class="sxs-lookup"><span data-stu-id="52d67-152">Built-In Types Table</span></span>](../../../csharp/language-reference/keywords/built-in-types-table.md)  
 [<span data-ttu-id="52d67-153">隐式数值转换表</span><span class="sxs-lookup"><span data-stu-id="52d67-153">Implicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)  
 [<span data-ttu-id="52d67-154">显式数值转换表</span><span class="sxs-lookup"><span data-stu-id="52d67-154">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)
