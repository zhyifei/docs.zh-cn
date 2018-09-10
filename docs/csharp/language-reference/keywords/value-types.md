---
title: 值类型（C# 参考）
ms.date: 07/20/2015
f1_keywords:
- cs.valuetypes
helpviewer_keywords:
- value types [C#]
- types [C#], value types
- C# language, value types
ms.assetid: 471eb994-2958-49d5-a6be-19b4313f80a3
ms.openlocfilehash: 3bbaea9247d975c27ed6f49dedb749312f675296
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43526458"
---
# <a name="value-types-c-reference"></a><span data-ttu-id="3acc2-102">值类型（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="3acc2-102">Value Types (C# Reference)</span></span>
<span data-ttu-id="3acc2-103">值类型包含两个主要类别：</span><span class="sxs-lookup"><span data-stu-id="3acc2-103">The value types consist of two main categories:</span></span>  
  
-   [<span data-ttu-id="3acc2-104">结构</span><span class="sxs-lookup"><span data-stu-id="3acc2-104">Structs</span></span>](../../../csharp/language-reference/keywords/struct.md)  
  
-   [<span data-ttu-id="3acc2-105">枚举</span><span class="sxs-lookup"><span data-stu-id="3acc2-105">Enumerations</span></span>](../../../csharp/language-reference/keywords/enum.md)  
  
 <span data-ttu-id="3acc2-106">结构分为以下类别：</span><span class="sxs-lookup"><span data-stu-id="3acc2-106">Structs fall into these categories:</span></span>  
  
-   <span data-ttu-id="3acc2-107">数值类型</span><span class="sxs-lookup"><span data-stu-id="3acc2-107">Numeric types</span></span>  
  
    -   [<span data-ttu-id="3acc2-108">整型类型</span><span class="sxs-lookup"><span data-stu-id="3acc2-108">Integral types</span></span>](../../../csharp/language-reference/keywords/integral-types-table.md)  
  
    -   [<span data-ttu-id="3acc2-109">浮点类型</span><span class="sxs-lookup"><span data-stu-id="3acc2-109">Floating-point types</span></span>](../../../csharp/language-reference/keywords/floating-point-types-table.md)  
  
-   [<span data-ttu-id="3acc2-110">bool</span><span class="sxs-lookup"><span data-stu-id="3acc2-110">bool</span></span>](../../../csharp/language-reference/keywords/bool.md)  
  
-   <span data-ttu-id="3acc2-111">用户定义的结构。</span><span class="sxs-lookup"><span data-stu-id="3acc2-111">User defined structs.</span></span>  
  
## <a name="main-features-of-value-types"></a><span data-ttu-id="3acc2-112">值类型的主要功能</span><span class="sxs-lookup"><span data-stu-id="3acc2-112">Main Features of Value Types</span></span>  
 <span data-ttu-id="3acc2-113">直接基于值类型的变量包含值。</span><span class="sxs-lookup"><span data-stu-id="3acc2-113">Variables that are based on value types directly contain values.</span></span> <span data-ttu-id="3acc2-114">将一个值类型变量分配给另一个值类型变量将复制包含的值。</span><span class="sxs-lookup"><span data-stu-id="3acc2-114">Assigning one value type variable to another copies the contained value.</span></span> <span data-ttu-id="3acc2-115">这不同于分配引用类型变量，后者复制对对象的引用，但不复制对象本身。</span><span class="sxs-lookup"><span data-stu-id="3acc2-115">This differs from the assignment of reference type variables, which copies a reference to the object but not the object itself.</span></span>  
  
 <span data-ttu-id="3acc2-116">所有值类型都隐式派生自 <xref:System.ValueType?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="3acc2-116">All value types are derived implicitly from the <xref:System.ValueType?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="3acc2-117">与引用类型不同，不能从值类型派生新类型。</span><span class="sxs-lookup"><span data-stu-id="3acc2-117">Unlike with reference types, you cannot derive a new type from a value type.</span></span> <span data-ttu-id="3acc2-118">但是，与引用类型一样，结构可以实现接口。</span><span class="sxs-lookup"><span data-stu-id="3acc2-118">However, like reference types, structs can implement interfaces.</span></span>  
  
 <span data-ttu-id="3acc2-119">与引用类型不同，值类型不能包含 `null` 值。</span><span class="sxs-lookup"><span data-stu-id="3acc2-119">Unlike reference types, a value type cannot contain the `null` value.</span></span> <span data-ttu-id="3acc2-120">但是，[可以为 null 的类型](../../../csharp/programming-guide/nullable-types/index.md)功能允许将值类型分配给 `null`。</span><span class="sxs-lookup"><span data-stu-id="3acc2-120">However, the [nullable types](../../../csharp/programming-guide/nullable-types/index.md) feature does allow for value types to be assigned to `null`.</span></span>  
  
 <span data-ttu-id="3acc2-121">每个值类型都具有一个初始化该类型的默认值的隐式默认构造函数。</span><span class="sxs-lookup"><span data-stu-id="3acc2-121">Each value type has an implicit default constructor that initializes the default value of that type.</span></span> <span data-ttu-id="3acc2-122">有关值类型的默认值的信息，请参阅[默认值表](../../../csharp/language-reference/keywords/default-values-table.md)。</span><span class="sxs-lookup"><span data-stu-id="3acc2-122">For information about default values of value types, see [Default Values Table](../../../csharp/language-reference/keywords/default-values-table.md).</span></span>  
  
## <a name="main-features-of-simple-types"></a><span data-ttu-id="3acc2-123">简单类型的主要功能</span><span class="sxs-lookup"><span data-stu-id="3acc2-123">Main Features of Simple Types</span></span>  
 <span data-ttu-id="3acc2-124">所有简单类型（在 C# 语言中必不可少）都是 .NET Framework 系统类型的别名。</span><span class="sxs-lookup"><span data-stu-id="3acc2-124">All of the simple types -- those integral to the C# language -- are aliases of the .NET Framework System types.</span></span> <span data-ttu-id="3acc2-125">例如， [int](../../../csharp/language-reference/keywords/int.md) 是 <xref:System.Int32?displayProperty=nameWithType> 的别名。</span><span class="sxs-lookup"><span data-stu-id="3acc2-125">For example, [int](../../../csharp/language-reference/keywords/int.md) is an alias of <xref:System.Int32?displayProperty=nameWithType>.</span></span> <span data-ttu-id="3acc2-126">有关别名的完整列表，请参阅[内置类型表](../../../csharp/language-reference/keywords/built-in-types-table.md)。</span><span class="sxs-lookup"><span data-stu-id="3acc2-126">For a complete list of aliases, see [Built-In Types Table](../../../csharp/language-reference/keywords/built-in-types-table.md).</span></span>  
  
 <span data-ttu-id="3acc2-127">其操作数都是简单类型常数的常量表达式在编译时进行评估。</span><span class="sxs-lookup"><span data-stu-id="3acc2-127">Constant expressions, whose operands are all simple type constants, are evaluated at compilation time.</span></span>  
  
 <span data-ttu-id="3acc2-128">可以使用文本初始化简单类型。</span><span class="sxs-lookup"><span data-stu-id="3acc2-128">Simple types can be initialized by using literals.</span></span> <span data-ttu-id="3acc2-129">例如，“A”是类型 `char` 的文本，2001 是类型 `int` 的文本。</span><span class="sxs-lookup"><span data-stu-id="3acc2-129">For example, 'A' is a literal of the type `char` and 2001 is a literal of the type `int`.</span></span>  
  
## <a name="initializing-value-types"></a><span data-ttu-id="3acc2-130">初始化值类型</span><span class="sxs-lookup"><span data-stu-id="3acc2-130">Initializing Value Types</span></span>  
 <span data-ttu-id="3acc2-131">在使用 C# 中的本地变量之前，必须对其进行初始化。</span><span class="sxs-lookup"><span data-stu-id="3acc2-131">Local variables in C# must be initialized before they are used.</span></span> <span data-ttu-id="3acc2-132">例如，可以声明未初始化的本地变量，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="3acc2-132">For example, you might declare a local variable without initialization as in the following example:</span></span>  
  
```csharp  
int myInt;  
```  
  
 <span data-ttu-id="3acc2-133">在未初始化之前，无法使用。</span><span class="sxs-lookup"><span data-stu-id="3acc2-133">You cannot use it before you initialize it.</span></span> <span data-ttu-id="3acc2-134">可以使用以下语句将其初始化：</span><span class="sxs-lookup"><span data-stu-id="3acc2-134">You can initialize it using the following statement:</span></span>  
  
```csharp  
myInt = new int();  // Invoke default constructor for int type.  
```  
  
 <span data-ttu-id="3acc2-135">此语句等效于以下语句：</span><span class="sxs-lookup"><span data-stu-id="3acc2-135">This statement is equivalent to the following statement:</span></span>  
  
```csharp  
myInt = 0;         // Assign an initial value, 0 in this example.  
```  
  
 <span data-ttu-id="3acc2-136">当然，可以在同一语句中进行声明和初始化，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="3acc2-136">You can, of course, have the declaration and the initialization in the same statement as in the following examples:</span></span>  
  
```csharp  
int myInt = new int();  
```  
  
 <span data-ttu-id="3acc2-137">- 或 -</span><span class="sxs-lookup"><span data-stu-id="3acc2-137">–or–</span></span>  
  
```csharp  
int myInt = 0;  
```  
  
 <span data-ttu-id="3acc2-138">使用 [new](../../../csharp/language-reference/keywords/new.md) 运算符将调用特定类型的默认构造函数，并向变量赋予默认值。</span><span class="sxs-lookup"><span data-stu-id="3acc2-138">Using the [new](../../../csharp/language-reference/keywords/new.md) operator calls the default constructor of the specific type and assigns the default value to the variable.</span></span> <span data-ttu-id="3acc2-139">在前面的示例中，默认构造函数将值 `0` 赋予了 `myInt`。</span><span class="sxs-lookup"><span data-stu-id="3acc2-139">In the preceding example, the default constructor assigned the value `0` to `myInt`.</span></span> <span data-ttu-id="3acc2-140">有关通过调用默认构造函数所赋予的值的详细信息，请参阅[默认值表](../../../csharp/language-reference/keywords/default-values-table.md)。</span><span class="sxs-lookup"><span data-stu-id="3acc2-140">For more information about values assigned by calling default constructors, see [Default Values Table](../../../csharp/language-reference/keywords/default-values-table.md).</span></span>  
  
 <span data-ttu-id="3acc2-141">对于用户定义类型，请使用 [new](../../../csharp/language-reference/keywords/new.md) 调用默认构造函数。</span><span class="sxs-lookup"><span data-stu-id="3acc2-141">With user-defined types, use [new](../../../csharp/language-reference/keywords/new.md) to invoke the default constructor.</span></span> <span data-ttu-id="3acc2-142">例如，以下语句调用 `Point` 结构的默认构造函数：</span><span class="sxs-lookup"><span data-stu-id="3acc2-142">For example, the following statement invokes the default constructor of the `Point` struct:</span></span>  
  
```csharp  
Point p = new Point(); // Invoke default constructor for the struct.  
```  
  
 <span data-ttu-id="3acc2-143">进行此调用后，该结构被视为已明确赋值；即，它的所有成员都被初始化为其默认值。</span><span class="sxs-lookup"><span data-stu-id="3acc2-143">After this call, the struct is considered to be definitely assigned; that is, all its members are initialized to their default values.</span></span>  
  
 <span data-ttu-id="3acc2-144">有关 new 运算符的详细信息，请参阅 [new](../../../csharp/language-reference/keywords/new.md)。</span><span class="sxs-lookup"><span data-stu-id="3acc2-144">For more information about the new operator, see [new](../../../csharp/language-reference/keywords/new.md).</span></span>  
  
 <span data-ttu-id="3acc2-145">有关设置数值类型的输出格式的信息，请参阅[设置数值结果表的格式](../../../csharp/language-reference/keywords/formatting-numeric-results-table.md)。</span><span class="sxs-lookup"><span data-stu-id="3acc2-145">For information about formatting the output of numeric types, see [Formatting Numeric Results Table](../../../csharp/language-reference/keywords/formatting-numeric-results-table.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3acc2-146">请参阅</span><span class="sxs-lookup"><span data-stu-id="3acc2-146">See Also</span></span>

- [<span data-ttu-id="3acc2-147">C# 参考</span><span class="sxs-lookup"><span data-stu-id="3acc2-147">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="3acc2-148">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="3acc2-148">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="3acc2-149">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="3acc2-149">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
- [<span data-ttu-id="3acc2-150">类型</span><span class="sxs-lookup"><span data-stu-id="3acc2-150">Types</span></span>](../../../csharp/language-reference/keywords/types.md)  
- [<span data-ttu-id="3acc2-151">类型参考表</span><span class="sxs-lookup"><span data-stu-id="3acc2-151">Reference Tables for Types</span></span>](../../../csharp/language-reference/keywords/reference-tables-for-types.md)  
- [<span data-ttu-id="3acc2-152">引用类型</span><span class="sxs-lookup"><span data-stu-id="3acc2-152">Reference Types</span></span>](../../../csharp/language-reference/keywords/reference-types.md)  
- [<span data-ttu-id="3acc2-153">可以为 null 的类型</span><span class="sxs-lookup"><span data-stu-id="3acc2-153">Nullable types</span></span>](../../programming-guide/nullable-types/index.md)  
