---
title: 强制转换和类型转换（C# 编程指南）
ms.date: 07/20/2015
helpviewer_keywords:
- type conversion [C#]
- data type conversion [C#]
- numeric conversions [C#]
- conversions [C#], type
- casting [C#]
- converting types [C#]
ms.assetid: 568df58a-d292-4b55-93ba-601578722878
ms.openlocfilehash: 0c17fc89d93bdbb01bdef7935e72f8a7d96b0a55
ms.sourcegitcommit: 70c76a12449439bac0f7a359866be5a0311ce960
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/27/2018
ms.locfileid: "39296138"
---
# <a name="casting-and-type-conversions-c-programming-guide"></a><span data-ttu-id="b5794-102">强制转换和类型转换（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="b5794-102">Casting and Type Conversions (C# Programming Guide)</span></span>
<span data-ttu-id="b5794-103">由于 C# 是在编译时静态类型化的，因此变量在声明后就无法再次声明，或者无法用于存储其他类型的值，除非该类型可以转换为变量的类型。</span><span class="sxs-lookup"><span data-stu-id="b5794-103">Because C# is statically-typed at compile time, after a variable is declared, it cannot be declared again or used to store values of another type unless that type is convertible to the variable's type.</span></span> <span data-ttu-id="b5794-104">例如，不存在从整数到任意字符串的转换。</span><span class="sxs-lookup"><span data-stu-id="b5794-104">For example, there is no conversion from an integer to any arbitrary string.</span></span> <span data-ttu-id="b5794-105">因此，在将 `i` 声明为整数后，无法将字符串“Hello”赋予它，如下面的代码中所示。</span><span class="sxs-lookup"><span data-stu-id="b5794-105">Therefore, after you declare `i` as an integer, you cannot assign the string "Hello" to it, as is shown in the following code.</span></span>  
  
```csharp  
int i;  
i = "Hello"; // Error: "Cannot implicitly convert type 'string' to 'int'"  
```  
  
 <span data-ttu-id="b5794-106">但有时可能需要将值复制到其他类型的变量或方法参数中。</span><span class="sxs-lookup"><span data-stu-id="b5794-106">However, you might sometimes need to copy a value into a variable or method parameter of another type.</span></span> <span data-ttu-id="b5794-107">例如，可能需要将一个整数变量传递给参数类型化为 `double` 的方法。</span><span class="sxs-lookup"><span data-stu-id="b5794-107">For example, you might have an integer variable that you need to pass to a method whose parameter is typed as `double`.</span></span> <span data-ttu-id="b5794-108">或者可能需要将类变量分配给接口类型的变量。</span><span class="sxs-lookup"><span data-stu-id="b5794-108">Or you might need to assign a class variable to a variable of an interface type.</span></span> <span data-ttu-id="b5794-109">这些类型的操作称为类型转换。</span><span class="sxs-lookup"><span data-stu-id="b5794-109">These kinds of operations are called *type conversions*.</span></span> <span data-ttu-id="b5794-110">在 C# 中，可以执行以下几种类型的转换：</span><span class="sxs-lookup"><span data-stu-id="b5794-110">In C#, you can perform the following kinds of conversions:</span></span>  
  
-   <span data-ttu-id="b5794-111">**隐式转换**：由于该转换是一种类型安全的转换，不会导致数据丢失，因此不需要任何特殊的语法。</span><span class="sxs-lookup"><span data-stu-id="b5794-111">**Implicit conversions**: No special syntax is required because the conversion is type safe and no data will be lost.</span></span> <span data-ttu-id="b5794-112">示例包括从较小整数类型到较大整数类型的转换以及从派生类到基类的转换。</span><span class="sxs-lookup"><span data-stu-id="b5794-112">Examples include conversions from smaller to larger integral types, and conversions from derived classes to base classes.</span></span>  
  
-   <span data-ttu-id="b5794-113">**显式转换（强制转换）**：显式转换需要强制转换运算符。</span><span class="sxs-lookup"><span data-stu-id="b5794-113">**Explicit conversions (casts)**: Explicit conversions require a cast operator.</span></span> <span data-ttu-id="b5794-114">在转换中可能丢失信息时或在出于其他原因转换可能不成功时，必须进行强制转换。</span><span class="sxs-lookup"><span data-stu-id="b5794-114">Casting is required when information might be lost in the conversion, or when the conversion might not succeed for other reasons.</span></span>  <span data-ttu-id="b5794-115">典型的示例包括从数值到精度较低或范围较小的类型的转换和从基类实例到派生类的转换。</span><span class="sxs-lookup"><span data-stu-id="b5794-115">Typical examples include numeric conversion to a type that has less precision or a smaller range, and conversion of a base-class instance to a derived class.</span></span>  
  
-   <span data-ttu-id="b5794-116">**用户定义的转换**：可以定义一些特殊的方法来执行用户定义的转换，使不具有基类和派生类关系的自定义类型之间可以显式和隐式转换。</span><span class="sxs-lookup"><span data-stu-id="b5794-116">**User-defined conversions**: User-defined conversions are performed by special methods that you can define to enable explicit and implicit conversions between custom types that do not have a base class–derived class relationship.</span></span> <span data-ttu-id="b5794-117">有关详细信息，请参阅[转换运算符](../../../csharp/programming-guide/statements-expressions-operators/conversion-operators.md)。</span><span class="sxs-lookup"><span data-stu-id="b5794-117">For more information, see [Conversion Operators](../../../csharp/programming-guide/statements-expressions-operators/conversion-operators.md).</span></span>  
  
-   <span data-ttu-id="b5794-118">**使用帮助程序类进行转换**：若要在非兼容类型之间转换（例如整数和 <xref:System.DateTime?displayProperty=nameWithType> 对象之间，或十六进制字符串和字节数组之间），可使用 <xref:System.BitConverter?displayProperty=nameWithType> 类、<xref:System.Convert?displayProperty=nameWithType> 类和内置数值类型的 `Parse` 方法（例如 <xref:System.Int32.Parse%2A?displayProperty=nameWithType>）。</span><span class="sxs-lookup"><span data-stu-id="b5794-118">**Conversions with helper classes**: To convert between non-compatible types, such as integers and <xref:System.DateTime?displayProperty=nameWithType> objects, or hexadecimal strings and byte arrays, you can use the <xref:System.BitConverter?displayProperty=nameWithType> class, the <xref:System.Convert?displayProperty=nameWithType> class, and the `Parse` methods of the built-in numeric types, such as <xref:System.Int32.Parse%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="b5794-119">有关详细信息，请参见[如何：将字节数组转换为 int](../../../csharp/programming-guide/types/how-to-convert-a-byte-array-to-an-int.md)、[如何：将字符串转换为数字](../../../csharp/programming-guide/types/how-to-convert-a-string-to-a-number.md)和[如何：在十六进制字符串与数值类型之间转换](../../../csharp/programming-guide/types/how-to-convert-between-hexadecimal-strings-and-numeric-types.md)。</span><span class="sxs-lookup"><span data-stu-id="b5794-119">For more information, see [How to: Convert a byte Array to an int](../../../csharp/programming-guide/types/how-to-convert-a-byte-array-to-an-int.md), [How to: Convert a String to a Number](../../../csharp/programming-guide/types/how-to-convert-a-string-to-a-number.md), and [How to: Convert Between Hexadecimal Strings and Numeric Types](../../../csharp/programming-guide/types/how-to-convert-between-hexadecimal-strings-and-numeric-types.md).</span></span>  
  
## <a name="implicit-conversions"></a><span data-ttu-id="b5794-120">隐式转换</span><span class="sxs-lookup"><span data-stu-id="b5794-120">Implicit Conversions</span></span>  
 <span data-ttu-id="b5794-121">对于内置数值类型，如果要存储的值无需截断或四舍五入即可适应变量，则可以进行隐式转换。</span><span class="sxs-lookup"><span data-stu-id="b5794-121">For built-in numeric types, an implicit conversion can be made when the value to be stored can fit into the variable without being truncated or rounded off.</span></span> <span data-ttu-id="b5794-122">例如，[long](../../../csharp/language-reference/keywords/long.md) 类型的变量（8 字节整数）能够存储 [int](../../../csharp/language-reference/keywords/int.md)（在 32 位计算机上为 4 字节）可存储的任何值。</span><span class="sxs-lookup"><span data-stu-id="b5794-122">For example, a variable of type [long](../../../csharp/language-reference/keywords/long.md) (8 byte integer) can store any value that an [int](../../../csharp/language-reference/keywords/int.md) (4 bytes on a 32-bit computer) can store.</span></span> <span data-ttu-id="b5794-123">在下面的示例中，编译器先将右侧的值隐式转换为 `long` 类型，再将它赋给 `bigNum`。</span><span class="sxs-lookup"><span data-stu-id="b5794-123">In the following example, the compiler implicitly converts the value on the right to a type `long` before assigning it to `bigNum`.</span></span>  
  
 [!code-csharp[csProgGuideTypes#34](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/casting-and-type-conversions_1.cs)]  
  
 <span data-ttu-id="b5794-124">有关所有隐式数值转换的完整列表，请参阅[隐式数值转换表](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)。</span><span class="sxs-lookup"><span data-stu-id="b5794-124">For a complete list of all implicit numeric conversions, see [Implicit Numeric Conversions Table](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).</span></span>  
  
 <span data-ttu-id="b5794-125">对于引用类型，隐式转换始终存在于从一个类转换为该类的任何一个直接或间接的基类或接口的情况。</span><span class="sxs-lookup"><span data-stu-id="b5794-125">For reference types, an implicit conversion always exists from a class to any one of its direct or indirect base classes or interfaces.</span></span> <span data-ttu-id="b5794-126">由于派生类始终包含基类的所有成员，因此不必使用任何特殊语法。</span><span class="sxs-lookup"><span data-stu-id="b5794-126">No special syntax is necessary because a derived class always contains all the members of a base class.</span></span>  
  
```  
Derived d = new Derived();  
Base b = d; // Always OK.  
```  
  
## <a name="explicit-conversions"></a><span data-ttu-id="b5794-127">显式转换</span><span class="sxs-lookup"><span data-stu-id="b5794-127">Explicit Conversions</span></span>  
 <span data-ttu-id="b5794-128">但是，如果进行转换可能会导致信息丢失，则编译器会要求执行显式转换，显式转换也称为强制转换。</span><span class="sxs-lookup"><span data-stu-id="b5794-128">However, if a conversion cannot be made without a risk of losing information, the compiler requires that you perform an explicit conversion, which is called a *cast*.</span></span> <span data-ttu-id="b5794-129">强制转换是显式告知编译器你打算进行转换且你知道可能会发生数据丢失的一种方式。</span><span class="sxs-lookup"><span data-stu-id="b5794-129">A cast is a way of explicitly informing the compiler that you intend to make the conversion and that you are aware that data loss might occur.</span></span> <span data-ttu-id="b5794-130">若要执行强制转换，请在要转换的值或变量前面的括号中指定要强制转换到的类型。</span><span class="sxs-lookup"><span data-stu-id="b5794-130">To perform a cast, specify the type that you are casting to in parentheses in front of the value or variable to be converted.</span></span> <span data-ttu-id="b5794-131">下面的程序将 [double](../../../csharp/language-reference/keywords/double.md) 强制转换为 [int](../../../csharp/language-reference/keywords/int.md)。如不强制转换则该程序不会进行编译。</span><span class="sxs-lookup"><span data-stu-id="b5794-131">The following program casts a [double](../../../csharp/language-reference/keywords/double.md) to an [int](../../../csharp/language-reference/keywords/int.md). The program will not compile without the cast.</span></span>  
  
 [!code-csharp[csProgGuideTypes#2](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/casting-and-type-conversions_2.cs)]  
  
 <span data-ttu-id="b5794-132">有关支持的显式数值转换的列表，请参阅[显式数值转换表](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)。</span><span class="sxs-lookup"><span data-stu-id="b5794-132">For a list of the explicit numeric conversions that are allowed, see [Explicit Numeric Conversions Table](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md).</span></span>  
  
 <span data-ttu-id="b5794-133">对于引用类型，如果需要从基类型转换为派生类型，则必须进行显式强制转换：</span><span class="sxs-lookup"><span data-stu-id="b5794-133">For reference types, an explicit cast is required if you need to convert from a base type to a derived type:</span></span>  
  
```csharp  
// Create a new derived type.  
Giraffe g = new Giraffe();  
  
// Implicit conversion to base type is safe.  
Animal a = g;  
  
// Explicit conversion is required to cast back  
// to derived type. Note: This will compile but will  
// throw an exception at run time if the right-side  
// object is not in fact a Giraffe.  
Giraffe g2 = (Giraffe) a;  
```  
  
 <span data-ttu-id="b5794-134">引用类型之间的强制转换操作不会更改基础对象的运行时类型；它只更改用作对该对象引用的值的类型。</span><span class="sxs-lookup"><span data-stu-id="b5794-134">A cast operation between reference types does not change the run-time type of the underlying object; it only changes the type of the value that is being used as a reference to that object.</span></span> <span data-ttu-id="b5794-135">有关详细信息，请参阅[多形性](../../../csharp/programming-guide/classes-and-structs/polymorphism.md)。</span><span class="sxs-lookup"><span data-stu-id="b5794-135">For more information, see [Polymorphism](../../../csharp/programming-guide/classes-and-structs/polymorphism.md).</span></span>  
  
## <a name="type-conversion-exceptions-at-run-time"></a><span data-ttu-id="b5794-136">运行时的类型转换异常</span><span class="sxs-lookup"><span data-stu-id="b5794-136">Type Conversion Exceptions at Run Time</span></span>  
 <span data-ttu-id="b5794-137">在某些引用类型转换中，编译器无法确定强制转换是否会有效。</span><span class="sxs-lookup"><span data-stu-id="b5794-137">In some reference type conversions, the compiler cannot determine whether a cast will be valid.</span></span> <span data-ttu-id="b5794-138">正确进行编译的强制转换操作有可能在运行时失败。</span><span class="sxs-lookup"><span data-stu-id="b5794-138">It is possible for a cast operation that compiles correctly to fail at run time.</span></span> <span data-ttu-id="b5794-139">如下面的示例所示，类型转换在运行时失败将导致引发 <xref:System.InvalidCastException>。</span><span class="sxs-lookup"><span data-stu-id="b5794-139">As shown in the following example, a type cast that fails at run time will cause an <xref:System.InvalidCastException> to be thrown.</span></span>  
  
 [!code-csharp[csProgGuideTypes#41](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/casting-and-type-conversions_3.cs)]  
  
 <span data-ttu-id="b5794-140">C# 提供 [is](../../../csharp/language-reference/keywords/is.md) 和 [as](../../../csharp/language-reference/keywords/as.md) 运算符，使你可以在实际执行强制转换之前测试兼容性。</span><span class="sxs-lookup"><span data-stu-id="b5794-140">C# provides the [is](../../../csharp/language-reference/keywords/is.md) and [as](../../../csharp/language-reference/keywords/as.md) operators to enable you to test for compatibility before actually performing a cast.</span></span> <span data-ttu-id="b5794-141">有关详细信息，请参阅[如何：使用 as 和 is 运算符安全地进行强制转换](../../../csharp/programming-guide/types/how-to-safely-cast-by-using-as-and-is-operators.md)。</span><span class="sxs-lookup"><span data-stu-id="b5794-141">For more information, see [How to: Safely Cast by Using as and is Operators](../../../csharp/programming-guide/types/how-to-safely-cast-by-using-as-and-is-operators.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="b5794-142">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="b5794-142">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  

## <a name="see-also"></a><span data-ttu-id="b5794-143">请参阅</span><span class="sxs-lookup"><span data-stu-id="b5794-143">See Also</span></span>  
 [<span data-ttu-id="b5794-144">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="b5794-144">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="b5794-145">类型</span><span class="sxs-lookup"><span data-stu-id="b5794-145">Types</span></span>](../../../csharp/programming-guide/types/index.md)  
 [<span data-ttu-id="b5794-146">() 运算符</span><span class="sxs-lookup"><span data-stu-id="b5794-146">() Operator</span></span>](../../../csharp/language-reference/operators/invocation-operator.md)  
 [<span data-ttu-id="b5794-147">explicit</span><span class="sxs-lookup"><span data-stu-id="b5794-147">explicit</span></span>](../../../csharp/language-reference/keywords/explicit.md)  
 [<span data-ttu-id="b5794-148">implicit</span><span class="sxs-lookup"><span data-stu-id="b5794-148">implicit</span></span>](../../../csharp/language-reference/keywords/implicit.md)  
 [<span data-ttu-id="b5794-149">转换运算符</span><span class="sxs-lookup"><span data-stu-id="b5794-149">Conversion Operators</span></span>](../../../csharp/programming-guide/statements-expressions-operators/conversion-operators.md)  
 [<span data-ttu-id="b5794-150">通用类型转换</span><span class="sxs-lookup"><span data-stu-id="b5794-150">Generalized Type Conversion</span></span>](http://msdn.microsoft.com/library/49253ae6-7657-4810-82ab-1176a6feeada)  
 [<span data-ttu-id="b5794-151">导出类型转换</span><span class="sxs-lookup"><span data-stu-id="b5794-151">Exported Type Conversion</span></span>](http://msdn.microsoft.com/library/1dfe55f4-07a2-4b61-aabf-a8cf65783a6b)  
 [<span data-ttu-id="b5794-152">如何：将字符串转换为数字</span><span class="sxs-lookup"><span data-stu-id="b5794-152">How to: Convert a String to a Number</span></span>](../../../csharp/programming-guide/types/how-to-convert-a-string-to-a-number.md)
