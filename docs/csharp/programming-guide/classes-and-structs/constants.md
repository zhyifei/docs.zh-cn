---
title: "常量（C# 编程指南）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- C# language, constants
- constants [C#]
ms.assetid: 1fb39621-1738-49b1-a1b3-8587f109123f
caps.latest.revision: 24
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
ms.openlocfilehash: 85273420e9e0dbf4b8f24568d97be127c85d5f42
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="constants-c-programming-guide"></a><span data-ttu-id="ed7c6-102">常量（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="ed7c6-102">Constants (C# Programming Guide)</span></span>
<span data-ttu-id="ed7c6-103">常量是不可变的值，在编译时是已知的，在程序的生命周期内不会改变。</span><span class="sxs-lookup"><span data-stu-id="ed7c6-103">Constants are immutable values which are known at compile time and do not change for the life of the program.</span></span> <span data-ttu-id="ed7c6-104">常量使用 [const](../../../csharp/language-reference/keywords/const.md) 修饰符声明。</span><span class="sxs-lookup"><span data-stu-id="ed7c6-104">Constants are declared with the [const](../../../csharp/language-reference/keywords/const.md) modifier.</span></span> <span data-ttu-id="ed7c6-105">仅 C# 内置类型（不包括 <xref:System.Object?displayProperty=fullName>）可声明为 `const`。</span><span class="sxs-lookup"><span data-stu-id="ed7c6-105">Only the C# built-in types (excluding <xref:System.Object?displayProperty=fullName>) may be declared as `const`.</span></span> <span data-ttu-id="ed7c6-106">有关内置类型的列表，请参阅[内置类型表](../../../csharp/language-reference/keywords/built-in-types-table.md)。</span><span class="sxs-lookup"><span data-stu-id="ed7c6-106">For a list of the built-in types, see [Built-In Types Table](../../../csharp/language-reference/keywords/built-in-types-table.md).</span></span> <span data-ttu-id="ed7c6-107">用户定义的类型（包括类、结构和数组）不能为 `const`。</span><span class="sxs-lookup"><span data-stu-id="ed7c6-107">User-defined types, including classes, structs, and arrays, cannot be `const`.</span></span> <span data-ttu-id="ed7c6-108">使用 [readonly](../../../csharp/language-reference/keywords/readonly.md) 修饰符创建在运行时一次性（例如在构造函数中）初始化的类、结构或数组，此后不能更改。</span><span class="sxs-lookup"><span data-stu-id="ed7c6-108">Use the [readonly](../../../csharp/language-reference/keywords/readonly.md) modifier to create a class, struct, or array that is initialized one time at runtime (for example in a constructor) and thereafter cannot be changed.</span></span>  
  
 <span data-ttu-id="ed7c6-109">C# 不支持 `const` 方法、属性或事件。</span><span class="sxs-lookup"><span data-stu-id="ed7c6-109">C# does not support `const` methods, properties, or events.</span></span>  
  
 <span data-ttu-id="ed7c6-110">枚举类型使你能够为整数内置类型定义命名常量（例如 `int`、`uint`、`long` 等）。</span><span class="sxs-lookup"><span data-stu-id="ed7c6-110">The enum type enables you to define named constants for integral built-in types (for example `int`, `uint`, `long`, and so on).</span></span> <span data-ttu-id="ed7c6-111">有关详细信息，请参阅[枚举](../../../csharp/language-reference/keywords/enum.md)。</span><span class="sxs-lookup"><span data-stu-id="ed7c6-111">For more information, see [enum](../../../csharp/language-reference/keywords/enum.md).</span></span>  
  
 <span data-ttu-id="ed7c6-112">常量在声明时必须初始化。</span><span class="sxs-lookup"><span data-stu-id="ed7c6-112">Constants must be initialized as they are declared.</span></span> <span data-ttu-id="ed7c6-113">例如：</span><span class="sxs-lookup"><span data-stu-id="ed7c6-113">For example:</span></span>  
  
 <span data-ttu-id="ed7c6-114">[!code-cs[csProgGuideObjects#64](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/constants_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="ed7c6-114">[!code-cs[csProgGuideObjects#64](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/constants_1.cs)]</span></span>  
  
 <span data-ttu-id="ed7c6-115">在此示例中，常量 `months` 始终为 12，即使类本身也无法更改它。</span><span class="sxs-lookup"><span data-stu-id="ed7c6-115">In this example, the constant `months` is always 12, and it cannot be changed even by the class itself.</span></span> <span data-ttu-id="ed7c6-116">实际上，当编译器遇到 C# 源代码中的常量标识符（例如，`months`）时，它直接将文本值替换到它生成的中间语言 (IL) 代码中。</span><span class="sxs-lookup"><span data-stu-id="ed7c6-116">In fact, when the compiler encounters a constant identifier in C# source code (for example, `months`), it substitutes the literal value directly into the intermediate language (IL) code that it produces.</span></span> <span data-ttu-id="ed7c6-117">因为运行时没有与常量相关联的变量地址，所以 `const` 字段不能通过引用传递，并且不能在表达式中显示为左值。</span><span class="sxs-lookup"><span data-stu-id="ed7c6-117">Because there is no variable address associated with a constant at run time, `const` fields cannot be passed by reference and cannot appear as an l-value in an expression.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ed7c6-118">引用其他代码（如 DLL）中定义的常量值时要格外小心。</span><span class="sxs-lookup"><span data-stu-id="ed7c6-118">Use caution when you refer to constant values defined in other code such as DLLs.</span></span> <span data-ttu-id="ed7c6-119">如果新版本的 DLL 定义了新的常量值，则程序仍将保留旧的文本值，直到根据新版本重新编译。</span><span class="sxs-lookup"><span data-stu-id="ed7c6-119">If a new version of the DLL defines a new value for the constant, your program will still hold the old literal value until it is recompiled against the new version.</span></span>  
  
 <span data-ttu-id="ed7c6-120">可以同时声明多个同一类型的常量，例如：</span><span class="sxs-lookup"><span data-stu-id="ed7c6-120">Multiple constants of the same type can be declared at the same time, for example:</span></span>  
  
 <span data-ttu-id="ed7c6-121">[!code-cs[csProgGuideObjects#65](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/constants_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="ed7c6-121">[!code-cs[csProgGuideObjects#65](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/constants_2.cs)]</span></span>  
  
 <span data-ttu-id="ed7c6-122">如果不创建循环引用，则用于初始化常量的表达式可以引用另一个常量。</span><span class="sxs-lookup"><span data-stu-id="ed7c6-122">The expression that is used to initialize a constant can refer to another constant if it does not create a circular reference.</span></span> <span data-ttu-id="ed7c6-123">例如：</span><span class="sxs-lookup"><span data-stu-id="ed7c6-123">For example:</span></span>  
  
 <span data-ttu-id="ed7c6-124">[!code-cs[csProgGuideObjects#66](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/constants_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="ed7c6-124">[!code-cs[csProgGuideObjects#66](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/constants_3.cs)]</span></span>  
  
 <span data-ttu-id="ed7c6-125">可以将常量标记为[公共](../../../csharp/language-reference/keywords/public.md)、[专用](../../../csharp/language-reference/keywords/private.md)、[受保护](../../../csharp/language-reference/keywords/protected.md)、[内部](../../../csharp/language-reference/keywords/internal.md)或 `protected internal`。</span><span class="sxs-lookup"><span data-stu-id="ed7c6-125">Constants can be marked as [public](../../../csharp/language-reference/keywords/public.md), [private](../../../csharp/language-reference/keywords/private.md), [protected](../../../csharp/language-reference/keywords/protected.md), [internal](../../../csharp/language-reference/keywords/internal.md), or `protected internal`.</span></span> <span data-ttu-id="ed7c6-126">这些访问修饰符定义该类的用户访问该常量的方式。</span><span class="sxs-lookup"><span data-stu-id="ed7c6-126">These access modifiers define how users of the class can access the constant.</span></span> <span data-ttu-id="ed7c6-127">有关详细信息，请参阅[访问修饰符](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)。</span><span class="sxs-lookup"><span data-stu-id="ed7c6-127">For more information, see [Access Modifiers](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).</span></span>  
  
 <span data-ttu-id="ed7c6-128">常量是作为[静态](../../../csharp/language-reference/keywords/static.md)字段访问的，因为常量的值对于该类型的所有实例都是相同的。</span><span class="sxs-lookup"><span data-stu-id="ed7c6-128">Constants are accessed as if they were [static](../../../csharp/language-reference/keywords/static.md) fields because the value of the constant is the same for all instances of the type.</span></span> <span data-ttu-id="ed7c6-129">不使用 `static` 关键字来声明这些常量。</span><span class="sxs-lookup"><span data-stu-id="ed7c6-129">You do not use the `static` keyword to declare them.</span></span> <span data-ttu-id="ed7c6-130">不在定义常量的类中的表达式必须使用类名、句点和常量名称来访问该常量。</span><span class="sxs-lookup"><span data-stu-id="ed7c6-130">Expressions that are not in the class that defines the constant must use the class name, a period, and the name of the constant to access the constant.</span></span> <span data-ttu-id="ed7c6-131">例如: </span><span class="sxs-lookup"><span data-stu-id="ed7c6-131">For example:</span></span>  
  
 <span data-ttu-id="ed7c6-132">[!code-cs[csProgGuideObjects#67](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/constants_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="ed7c6-132">[!code-cs[csProgGuideObjects#67](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/constants_4.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="ed7c6-133">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="ed7c6-133">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="ed7c6-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="ed7c6-134">See Also</span></span>  
 <span data-ttu-id="ed7c6-135">[C# 编程指南](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="ed7c6-135">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="ed7c6-136">[类和结构](../../../csharp/programming-guide/classes-and-structs/index.md) </span><span class="sxs-lookup"><span data-stu-id="ed7c6-136">[Classes and Structs](../../../csharp/programming-guide/classes-and-structs/index.md) </span></span>  
 <span data-ttu-id="ed7c6-137">[属性](../../../csharp/programming-guide/classes-and-structs/properties.md) </span><span class="sxs-lookup"><span data-stu-id="ed7c6-137">[Properties](../../../csharp/programming-guide/classes-and-structs/properties.md) </span></span>  
 <span data-ttu-id="ed7c6-138">[类型](../../../csharp/programming-guide/types/index.md) </span><span class="sxs-lookup"><span data-stu-id="ed7c6-138">[Types](../../../csharp/programming-guide/types/index.md) </span></span>  
 <span data-ttu-id="ed7c6-139">[readonly](../../../csharp/language-reference/keywords/readonly.md) </span><span class="sxs-lookup"><span data-stu-id="ed7c6-139">[readonly](../../../csharp/language-reference/keywords/readonly.md) </span></span>  
 [<span data-ttu-id="ed7c6-140">C# 不变性第一部分：不变性类型</span><span class="sxs-lookup"><span data-stu-id="ed7c6-140">Immutability in C# Part One: Kinds of Immutability</span></span>](http://go.microsoft.com/fwlink/?LinkId=112379)

