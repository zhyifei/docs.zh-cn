---
title: "long（C# 参考）"
ms.date: 2017-03-14
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- long_CSharpKeyword
- long
dev_langs:
- CSharp
helpviewer_keywords:
- long keyword [C#]
ms.assetid: f9b24319-1f39-48be-a42b-d528ee28a7fd
caps.latest.revision: 17
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
ms.openlocfilehash: 5f7d2d6a3d5781b4e120b8399c7206d4429dd98e
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="long-c-reference"></a><span data-ttu-id="4f2e4-102">long（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="4f2e4-102">long (C# Reference)</span></span>

<span data-ttu-id="4f2e4-103">`long` 表示一种整型类型，该类型根据下表显示的大小和范围存储值。</span><span class="sxs-lookup"><span data-stu-id="4f2e4-103">`long` denotes an integral type that stores values according to the size and range shown in the following table.</span></span>  
  
|<span data-ttu-id="4f2e4-104">类型</span><span class="sxs-lookup"><span data-stu-id="4f2e4-104">Type</span></span>|<span data-ttu-id="4f2e4-105">范围</span><span class="sxs-lookup"><span data-stu-id="4f2e4-105">Range</span></span>|<span data-ttu-id="4f2e4-106">大小</span><span class="sxs-lookup"><span data-stu-id="4f2e4-106">Size</span></span>|<span data-ttu-id="4f2e4-107">.NET Framework 类型</span><span class="sxs-lookup"><span data-stu-id="4f2e4-107">.NET Framework type</span></span>|  
|----------|-----------|----------|-------------------------|  
|`long`|<span data-ttu-id="4f2e4-108">-9,223,372,036,854,775,808 到 9,223,372,036,854,775,807</span><span class="sxs-lookup"><span data-stu-id="4f2e4-108">-9,223,372,036,854,775,808 to 9,223,372,036,854,775,807</span></span>|<span data-ttu-id="4f2e4-109">64 位带符号整数</span><span class="sxs-lookup"><span data-stu-id="4f2e4-109">Signed 64-bit integer</span></span>|<xref:System.Int64?displayProperty=fullName>|  
  
## <a name="literals"></a><span data-ttu-id="4f2e4-110">文本</span><span class="sxs-lookup"><span data-stu-id="4f2e4-110">Literals</span></span> 

<span data-ttu-id="4f2e4-111">可以通过为其分配十进制文本、十六进制文本或（从 C# 7 开始）二进制文本来声明和初始化 `long` 变量。</span><span class="sxs-lookup"><span data-stu-id="4f2e4-111">You can declare and initialize a `long` variable by assigning a decimal literal, a hexadecimal literal, or (starting with C# 7) a binary literal to it.</span></span> 

<span data-ttu-id="4f2e4-112">在以下示例中，表示为十进制、十六进制和二进制文本的等于 4,294,967,296 的整数被分配给 `long` 值。</span><span class="sxs-lookup"><span data-stu-id="4f2e4-112">In the following example, integers equal to 4,294,967,296 that are represented as decimal, hexadecimal, and binary literals are assigned to `long` values.</span></span>  
  
<span data-ttu-id="4f2e4-113">[!code-cs[long](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#Long)]</span><span class="sxs-lookup"><span data-stu-id="4f2e4-113">[!code-cs[long](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#Long)]</span></span>  

> [!NOTE] 
> <span data-ttu-id="4f2e4-114">使用前缀 `0x` 或 `0X` 表示十六进制文本，使用前缀 `0b` 或 `0B` 表示二进制文本。</span><span class="sxs-lookup"><span data-stu-id="4f2e4-114">You use the prefix `0x` or `0X` to denote a hexadecimal literal and the prefix `0b` or `0B` to denote a binary literal.</span></span> <span data-ttu-id="4f2e4-115">十进制文本没有前缀。</span><span class="sxs-lookup"><span data-stu-id="4f2e4-115">Decimal literals have no prefix.</span></span> 

<span data-ttu-id="4f2e4-116">从 C# 7 开始，还可以使用下划线字符 `_` 作为数字分隔符，以增强可读性，如下例所示。</span><span class="sxs-lookup"><span data-stu-id="4f2e4-116">Starting with C# 7, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

<span data-ttu-id="4f2e4-117">[!code-cs[long](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#LongS)]</span><span class="sxs-lookup"><span data-stu-id="4f2e4-117">[!code-cs[long](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#LongS)]</span></span>  
 
 <span data-ttu-id="4f2e4-118">整数文本还可包含表示类型的后缀。</span><span class="sxs-lookup"><span data-stu-id="4f2e4-118">Integer literals can also include a suffix that denotes the type.</span></span> <span data-ttu-id="4f2e4-119">后缀 `L` 表示 `long`。</span><span class="sxs-lookup"><span data-stu-id="4f2e4-119">The suffix `L` denotes a `long`.</span></span> <span data-ttu-id="4f2e4-120">以下示例使用 `L` 后缀来表示长整型：</span><span class="sxs-lookup"><span data-stu-id="4f2e4-120">The following example uses the `L` suffix to denote a long integer:</span></span>
 
```csharp
long value = 4294967296L;  
```  

> [!NOTE]
>  <span data-ttu-id="4f2e4-121">也可用小写字母“l”作后缀。</span><span class="sxs-lookup"><span data-stu-id="4f2e4-121">You can also use the lowercase letter "l" as a suffix.</span></span> <span data-ttu-id="4f2e4-122">但是，字母“l”容易与数字“1”混淆，因此会生成编译器警告。</span><span class="sxs-lookup"><span data-stu-id="4f2e4-122">However, this generates a compiler warning because the letter "l" is easily confused with the digit "1."</span></span> <span data-ttu-id="4f2e4-123">为清楚起见，请使用“L”。</span><span class="sxs-lookup"><span data-stu-id="4f2e4-123">Use "L" for clarity.</span></span>  
  
 <span data-ttu-id="4f2e4-124">使用后缀 `L` 时，将根据整数的大小确定它的类型是 `long` 还是 [ulong](../../../csharp/language-reference/keywords/ulong.md)。</span><span class="sxs-lookup"><span data-stu-id="4f2e4-124">When you use the suffix `L`, the type of the literal integer is determined to be either `long` or [ulong](../../../csharp/language-reference/keywords/ulong.md), depending on its size.</span></span> <span data-ttu-id="4f2e4-125">在此例中，它是 `long`，因为它小于 [ulong](../../../csharp/language-reference/keywords/ulong.md) 的范围的下限。</span><span class="sxs-lookup"><span data-stu-id="4f2e4-125">In this case, it is `long` because it less than the range of [ulong](../../../csharp/language-reference/keywords/ulong.md).</span></span>  
  
 <span data-ttu-id="4f2e4-126">此后缀常用于调用重载方法。</span><span class="sxs-lookup"><span data-stu-id="4f2e4-126">A common use of the suffix is to call overloaded methods.</span></span> <span data-ttu-id="4f2e4-127">例如，以下重载方法具有 `long` 和 [int](../../../csharp/language-reference/keywords/int.md) 类型的参数：</span><span class="sxs-lookup"><span data-stu-id="4f2e4-127">For example, the following overloaded methods have parameters of type `long` and [int](../../../csharp/language-reference/keywords/int.md):</span></span>  
  
```csharp
public static void SampleMethod(int i) {}  
public static void SampleMethod(long l) {}  
```  
  
 <span data-ttu-id="4f2e4-128">`L` 后缀可确保调用正确的重载：</span><span class="sxs-lookup"><span data-stu-id="4f2e4-128">The `L` suffix guarantees that the correct overload is called:</span></span>  
  
```csharp  
SampleMethod(5);    // Calls the method with the int parameter  
SampleMethod(5L);   // Calls the method with the long parameter  
```  
<span data-ttu-id="4f2e4-129">如果整数文本没有后缀，则其类型为以下类型中可表示其值的第一个类型：</span><span class="sxs-lookup"><span data-stu-id="4f2e4-129">If an integer literal has no suffix, its type is the first of the following types in which its value can be represented:</span></span> 

1. [<span data-ttu-id="4f2e4-130">int</span><span class="sxs-lookup"><span data-stu-id="4f2e4-130">int</span></span>](int.md)
2. [<span data-ttu-id="4f2e4-131">uint</span><span class="sxs-lookup"><span data-stu-id="4f2e4-131">uint</span></span>](../../../csharp/language-reference/keywords/uint.md)
3. `long`
4. [<span data-ttu-id="4f2e4-132">ulong</span><span class="sxs-lookup"><span data-stu-id="4f2e4-132">ulong</span></span>](../../../csharp/language-reference/keywords/ulong.md) 

<span data-ttu-id="4f2e4-133">上例中的文本 4294967296 是 `long` 类型，因为它超出了 [uint](../../../csharp/language-reference/keywords/uint.md) 的范围（有关整型类型的存储大小，请参阅[整型类型表](../../../csharp/language-reference/keywords/integral-types-table.md)）。</span><span class="sxs-lookup"><span data-stu-id="4f2e4-133">The literal 4294967296 in the previous examples is of type `long`, because it exceeds the range of [uint](../../../csharp/language-reference/keywords/uint.md) (see [Integral Types Table](../../../csharp/language-reference/keywords/integral-types-table.md) for the storage sizes of integral types).</span></span>  
  
 <span data-ttu-id="4f2e4-134">如果在同一个表达式中同时使用 `long` 类型和其他整型类型，表达式的计算结果为 `long`（在关系表达式或布尔表达式中为 [bool](../../../csharp/language-reference/keywords/bool.md)）类型。</span><span class="sxs-lookup"><span data-stu-id="4f2e4-134">If you use the `long` type with other integral types in the same expression, the expression is evaluated as `long` (or [bool](../../../csharp/language-reference/keywords/bool.md) in the case of relational or Boolean expressions).</span></span> <span data-ttu-id="4f2e4-135">例如，下列表达式计算为 `long`：</span><span class="sxs-lookup"><span data-stu-id="4f2e4-135">For example, the following expression evaluates as `long`:</span></span>  
  
```csharp  
898L + 88  
```  
  
 <span data-ttu-id="4f2e4-136">有关兼用浮点类型和整型类型的算术表达式的信息，请参阅 [float](../../../csharp/language-reference/keywords/float.md) 和 [double](../../../csharp/language-reference/keywords/double.md)。</span><span class="sxs-lookup"><span data-stu-id="4f2e4-136">For information on arithmetic expressions with mixed floating-point types and integral types, see [float](../../../csharp/language-reference/keywords/float.md) and [double](../../../csharp/language-reference/keywords/double.md).</span></span>  
  
## <a name="conversions"></a><span data-ttu-id="4f2e4-137">转换</span><span class="sxs-lookup"><span data-stu-id="4f2e4-137">Conversions</span></span>  
 <span data-ttu-id="4f2e4-138">存在从 `long` 到 [float](../../../csharp/language-reference/keywords/float.md)、[double](../../../csharp/language-reference/keywords/double.md) 或 [decimal](../../../csharp/language-reference/keywords/decimal.md) 的预定义隐式转换。</span><span class="sxs-lookup"><span data-stu-id="4f2e4-138">There is a predefined implicit conversion from `long` to [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md), or [decimal](../../../csharp/language-reference/keywords/decimal.md).</span></span> <span data-ttu-id="4f2e4-139">其他情况下必须使用强制转换。</span><span class="sxs-lookup"><span data-stu-id="4f2e4-139">Otherwise a cast must be used.</span></span> <span data-ttu-id="4f2e4-140">例如，如果不使用显式强制转换，以下语句会生成编译错误：</span><span class="sxs-lookup"><span data-stu-id="4f2e4-140">For example, the following statement will produce a compilation error without an explicit cast:</span></span>  
  
```csharp  
int x = 8L;        // Error: no implicit conversion from long to int  
int x = (int)8L;   // OK: explicit conversion to int  
```  
  
 <span data-ttu-id="4f2e4-141">存在从 [sbyte](../../../csharp/language-reference/keywords/sbyte.md)、[byte](../../../csharp/language-reference/keywords/byte.md)、[short](../../../csharp/language-reference/keywords/short.md)、[ushort](../../../csharp/language-reference/keywords/ushort.md)、[int](../../../csharp/language-reference/keywords/int.md)、[uint](../../../csharp/language-reference/keywords/uint.md) 或 [char](../../../csharp/language-reference/keywords/char.md) 到 `long` 的预定义隐式转换。</span><span class="sxs-lookup"><span data-stu-id="4f2e4-141">There is a predefined implicit conversion from [sbyte](../../../csharp/language-reference/keywords/sbyte.md), [byte](../../../csharp/language-reference/keywords/byte.md), [short](../../../csharp/language-reference/keywords/short.md), [ushort](../../../csharp/language-reference/keywords/ushort.md), [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), or [char](../../../csharp/language-reference/keywords/char.md) to `long`.</span></span>  
  
 <span data-ttu-id="4f2e4-142">另请注意，不存在从浮点类型到 `long` 类型的隐式转换。</span><span class="sxs-lookup"><span data-stu-id="4f2e4-142">Notice also that there is no implicit conversion from floating-point types to `long`.</span></span> <span data-ttu-id="4f2e4-143">例如，除非使用显式强制转换，否则以下语句将生成编译器错误：</span><span class="sxs-lookup"><span data-stu-id="4f2e4-143">For example, the following statement generates a compiler error unless an explicit cast is used:</span></span>  
  
```csharp  
long x = 3.0;         // Error: no implicit conversion from double  
long y = (long)3.0;   // OK: explicit conversion  
```  
  
## <a name="c-language-specification"></a><span data-ttu-id="4f2e4-144">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="4f2e4-144">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="4f2e4-145">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4f2e4-145">See Also</span></span>  
 <span data-ttu-id="4f2e4-146"><xref:System.Int64></span><span class="sxs-lookup"><span data-stu-id="4f2e4-146"><xref:System.Int64></span></span>   
 <span data-ttu-id="4f2e4-147">[C# 参考](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="4f2e4-147">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="4f2e4-148">[C# 编程指南](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="4f2e4-148">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="4f2e4-149">[C# 关键字](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="4f2e4-149">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="4f2e4-150">[整型类型表](../../../csharp/language-reference/keywords/integral-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="4f2e4-150">[Integral Types Table](../../../csharp/language-reference/keywords/integral-types-table.md) </span></span>  
 <span data-ttu-id="4f2e4-151">[内置类型表](../../../csharp/language-reference/keywords/built-in-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="4f2e4-151">[Built-In Types Table](../../../csharp/language-reference/keywords/built-in-types-table.md) </span></span>  
 <span data-ttu-id="4f2e4-152">[隐式数值转换表](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md) </span><span class="sxs-lookup"><span data-stu-id="4f2e4-152">[Implicit Numeric Conversions Table](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md) </span></span>  
 [<span data-ttu-id="4f2e4-153">显式数值转换表</span><span class="sxs-lookup"><span data-stu-id="4f2e4-153">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)

