---
title: 常量（C# 编程指南）
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, constants
- constants [C#]
ms.assetid: 1fb39621-1738-49b1-a1b3-8587f109123f
ms.openlocfilehash: 90423c868ca303f8e94c16f44bc5e0b23615fc17
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33314052"
---
# <a name="constants-c-programming-guide"></a><span data-ttu-id="fad7e-102">常量（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="fad7e-102">Constants (C# Programming Guide)</span></span>
<span data-ttu-id="fad7e-103">常量是不可变的值，在编译时是已知的，在程序的生命周期内不会改变。</span><span class="sxs-lookup"><span data-stu-id="fad7e-103">Constants are immutable values which are known at compile time and do not change for the life of the program.</span></span> <span data-ttu-id="fad7e-104">常量使用 [const](../../../csharp/language-reference/keywords/const.md) 修饰符声明。</span><span class="sxs-lookup"><span data-stu-id="fad7e-104">Constants are declared with the [const](../../../csharp/language-reference/keywords/const.md) modifier.</span></span> <span data-ttu-id="fad7e-105">仅 C# 内置类型（不包括 <xref:System.Object?displayProperty=nameWithType>）可声明为 `const`。</span><span class="sxs-lookup"><span data-stu-id="fad7e-105">Only the C# built-in types (excluding <xref:System.Object?displayProperty=nameWithType>) may be declared as `const`.</span></span> <span data-ttu-id="fad7e-106">有关内置类型的列表，请参阅[内置类型表](../../../csharp/language-reference/keywords/built-in-types-table.md)。</span><span class="sxs-lookup"><span data-stu-id="fad7e-106">For a list of the built-in types, see [Built-In Types Table](../../../csharp/language-reference/keywords/built-in-types-table.md).</span></span> <span data-ttu-id="fad7e-107">用户定义的类型（包括类、结构和数组）不能为 `const`。</span><span class="sxs-lookup"><span data-stu-id="fad7e-107">User-defined types, including classes, structs, and arrays, cannot be `const`.</span></span> <span data-ttu-id="fad7e-108">使用 [readonly](../../../csharp/language-reference/keywords/readonly.md) 修饰符创建在运行时一次性（例如在构造函数中）初始化的类、结构或数组，此后不能更改。</span><span class="sxs-lookup"><span data-stu-id="fad7e-108">Use the [readonly](../../../csharp/language-reference/keywords/readonly.md) modifier to create a class, struct, or array that is initialized one time at runtime (for example in a constructor) and thereafter cannot be changed.</span></span>  
  
 <span data-ttu-id="fad7e-109">C# 不支持 `const` 方法、属性或事件。</span><span class="sxs-lookup"><span data-stu-id="fad7e-109">C# does not support `const` methods, properties, or events.</span></span>  
  
 <span data-ttu-id="fad7e-110">枚举类型使你能够为整数内置类型定义命名常量（例如 `int`、`uint`、`long` 等）。</span><span class="sxs-lookup"><span data-stu-id="fad7e-110">The enum type enables you to define named constants for integral built-in types (for example `int`, `uint`, `long`, and so on).</span></span> <span data-ttu-id="fad7e-111">有关详细信息，请参阅[枚举](../../../csharp/language-reference/keywords/enum.md)。</span><span class="sxs-lookup"><span data-stu-id="fad7e-111">For more information, see [enum](../../../csharp/language-reference/keywords/enum.md).</span></span>  
  
 <span data-ttu-id="fad7e-112">常量在声明时必须初始化。</span><span class="sxs-lookup"><span data-stu-id="fad7e-112">Constants must be initialized as they are declared.</span></span> <span data-ttu-id="fad7e-113">例如:</span><span class="sxs-lookup"><span data-stu-id="fad7e-113">For example:</span></span>  
  
 [!code-csharp[csProgGuideObjects#64](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/constants_1.cs)]  
  
 <span data-ttu-id="fad7e-114">在此示例中，常量 `months` 始终为 12，即使类本身也无法更改它。</span><span class="sxs-lookup"><span data-stu-id="fad7e-114">In this example, the constant `months` is always 12, and it cannot be changed even by the class itself.</span></span> <span data-ttu-id="fad7e-115">实际上，当编译器遇到 C# 源代码中的常量标识符（例如，`months`）时，它直接将文本值替换到它生成的中间语言 (IL) 代码中。</span><span class="sxs-lookup"><span data-stu-id="fad7e-115">In fact, when the compiler encounters a constant identifier in C# source code (for example, `months`), it substitutes the literal value directly into the intermediate language (IL) code that it produces.</span></span> <span data-ttu-id="fad7e-116">因为运行时没有与常量相关联的变量地址，所以 `const` 字段不能通过引用传递，并且不能在表达式中显示为左值。</span><span class="sxs-lookup"><span data-stu-id="fad7e-116">Because there is no variable address associated with a constant at run time, `const` fields cannot be passed by reference and cannot appear as an l-value in an expression.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fad7e-117">引用其他代码（如 DLL）中定义的常量值时要格外小心。</span><span class="sxs-lookup"><span data-stu-id="fad7e-117">Use caution when you refer to constant values defined in other code such as DLLs.</span></span> <span data-ttu-id="fad7e-118">如果新版本的 DLL 定义了新的常量值，则程序仍将保留旧的文本值，直到根据新版本重新编译。</span><span class="sxs-lookup"><span data-stu-id="fad7e-118">If a new version of the DLL defines a new value for the constant, your program will still hold the old literal value until it is recompiled against the new version.</span></span>  
  
 <span data-ttu-id="fad7e-119">可以同时声明多个同一类型的常量，例如：</span><span class="sxs-lookup"><span data-stu-id="fad7e-119">Multiple constants of the same type can be declared at the same time, for example:</span></span>  
  
 [!code-csharp[csProgGuideObjects#65](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/constants_2.cs)]  
  
 <span data-ttu-id="fad7e-120">如果不创建循环引用，则用于初始化常量的表达式可以引用另一个常量。</span><span class="sxs-lookup"><span data-stu-id="fad7e-120">The expression that is used to initialize a constant can refer to another constant if it does not create a circular reference.</span></span> <span data-ttu-id="fad7e-121">例如:</span><span class="sxs-lookup"><span data-stu-id="fad7e-121">For example:</span></span>  
  
 [!code-csharp[csProgGuideObjects#66](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/constants_3.cs)]  
  
 <span data-ttu-id="fad7e-122">可以将常量标记为[public](../../../csharp/language-reference/keywords/public.md)、[private](../../../csharp/language-reference/keywords/private.md)、[protected](../../../csharp/language-reference/keywords/protected.md)、[internal](../../../csharp/language-reference/keywords/internal.md)、[protected internal](../../../csharp/language-reference/keywords/protected-internal.md) 或 [private protected](../../../csharp/language-reference/keywords/private-protected.md)。</span><span class="sxs-lookup"><span data-stu-id="fad7e-122">Constants can be marked as [public](../../../csharp/language-reference/keywords/public.md), [private](../../../csharp/language-reference/keywords/private.md), [protected](../../../csharp/language-reference/keywords/protected.md), [internal](../../../csharp/language-reference/keywords/internal.md), [protected internal](../../../csharp/language-reference/keywords/protected-internal.md) or [private protected](../../../csharp/language-reference/keywords/private-protected.md).</span></span> <span data-ttu-id="fad7e-123">这些访问修饰符定义该类的用户访问该常量的方式。</span><span class="sxs-lookup"><span data-stu-id="fad7e-123">These access modifiers define how users of the class can access the constant.</span></span> <span data-ttu-id="fad7e-124">有关详细信息，请参阅[访问修饰符](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)。</span><span class="sxs-lookup"><span data-stu-id="fad7e-124">For more information, see [Access Modifiers](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).</span></span>  
  
 <span data-ttu-id="fad7e-125">常量是作为[静态](../../../csharp/language-reference/keywords/static.md)字段访问的，因为常量的值对于该类型的所有实例都是相同的。</span><span class="sxs-lookup"><span data-stu-id="fad7e-125">Constants are accessed as if they were [static](../../../csharp/language-reference/keywords/static.md) fields because the value of the constant is the same for all instances of the type.</span></span> <span data-ttu-id="fad7e-126">不使用 `static` 关键字来声明这些常量。</span><span class="sxs-lookup"><span data-stu-id="fad7e-126">You do not use the `static` keyword to declare them.</span></span> <span data-ttu-id="fad7e-127">不在定义常量的类中的表达式必须使用类名、句点和常量名称来访问该常量。</span><span class="sxs-lookup"><span data-stu-id="fad7e-127">Expressions that are not in the class that defines the constant must use the class name, a period, and the name of the constant to access the constant.</span></span> <span data-ttu-id="fad7e-128">例如:</span><span class="sxs-lookup"><span data-stu-id="fad7e-128">For example:</span></span>  
  
 [!code-csharp[csProgGuideObjects#67](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/constants_4.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="fad7e-129">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="fad7e-129">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="fad7e-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="fad7e-130">See Also</span></span>  
 [<span data-ttu-id="fad7e-131">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="fad7e-131">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="fad7e-132">类和结构</span><span class="sxs-lookup"><span data-stu-id="fad7e-132">Classes and Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/index.md)  
 [<span data-ttu-id="fad7e-133">属性</span><span class="sxs-lookup"><span data-stu-id="fad7e-133">Properties</span></span>](../../../csharp/programming-guide/classes-and-structs/properties.md)  
 [<span data-ttu-id="fad7e-134">类型</span><span class="sxs-lookup"><span data-stu-id="fad7e-134">Types</span></span>](../../../csharp/programming-guide/types/index.md)  
 [<span data-ttu-id="fad7e-135">readonly</span><span class="sxs-lookup"><span data-stu-id="fad7e-135">readonly</span></span>](../../../csharp/language-reference/keywords/readonly.md)  
 [<span data-ttu-id="fad7e-136">C# 不变性第一部分：不变性类型</span><span class="sxs-lookup"><span data-stu-id="fad7e-136">Immutability in C# Part One: Kinds of Immutability</span></span>](https://blogs.msdn.microsoft.com/ericlippert/2007/11/13/immutability-in-c-part-one-kinds-of-immutability)
