---
title: "使用构造函数（C# 编程指南）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- constructors [C#], about constructors
ms.assetid: 464253b2-fd5d-469a-836d-df0fdf2a43f7
caps.latest.revision: 26
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
ms.openlocfilehash: 75b55fde2fbd1697aed7eb0665a571c63b9b0b42
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="using-constructors-c-programming-guide"></a><span data-ttu-id="6fc3c-102">使用构造函数（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="6fc3c-102">Using Constructors (C# Programming Guide)</span></span>
<span data-ttu-id="6fc3c-103">创建[类](../../../csharp/language-reference/keywords/class.md)或[结构](../../../csharp/language-reference/keywords/struct.md)时，将会调用其构造函数。</span><span class="sxs-lookup"><span data-stu-id="6fc3c-103">When a [class](../../../csharp/language-reference/keywords/class.md) or [struct](../../../csharp/language-reference/keywords/struct.md) is created, its constructor is called.</span></span> <span data-ttu-id="6fc3c-104">构造函数与该类或结构具有相同名称，并且通常初始化新对象的数据成员。</span><span class="sxs-lookup"><span data-stu-id="6fc3c-104">Constructors have the same name as the class or struct, and they usually initialize the data members of the new object.</span></span>  
  
 <span data-ttu-id="6fc3c-105">在下面的示例中，通过使用简单构造函数定义了一个名为 `Taxi` 的类。</span><span class="sxs-lookup"><span data-stu-id="6fc3c-105">In the following example, a class named `Taxi` is defined by using a simple constructor.</span></span> <span data-ttu-id="6fc3c-106">然后使用 [new](../../../csharp/language-reference/keywords/new.md) 运算符对该类进行实例化。</span><span class="sxs-lookup"><span data-stu-id="6fc3c-106">This class is then instantiated with the [new](../../../csharp/language-reference/keywords/new.md) operator.</span></span> <span data-ttu-id="6fc3c-107">在为新对象分配内存之后，`new` 运算符立即调用 `Taxi` 构造函数。</span><span class="sxs-lookup"><span data-stu-id="6fc3c-107">The `Taxi` constructor is invoked by the `new` operator immediately after memory is allocated for the new object.</span></span>  
  
 <span data-ttu-id="6fc3c-108">[!code-cs[csProgGuideObjects#53](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-constructors_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="6fc3c-108">[!code-cs[csProgGuideObjects#53](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-constructors_1.cs)]</span></span>  
  
 <span data-ttu-id="6fc3c-109">不带任何参数的构造函数称为“默认构造函数”。</span><span class="sxs-lookup"><span data-stu-id="6fc3c-109">A constructor that takes no parameters is called a *default constructor*.</span></span> <span data-ttu-id="6fc3c-110">每当使用 `new` 运算符实例化对象且不为 `new` 提供任何参数时，会调用默认构造函数。</span><span class="sxs-lookup"><span data-stu-id="6fc3c-110">Default constructors are invoked whenever an object is instantiated by using the `new` operator and no arguments are provided to `new`.</span></span> <span data-ttu-id="6fc3c-111">有关详细信息，请参阅[实例构造函数](../../../csharp/programming-guide/classes-and-structs/instance-constructors.md)。</span><span class="sxs-lookup"><span data-stu-id="6fc3c-111">For more information, see [Instance Constructors](../../../csharp/programming-guide/classes-and-structs/instance-constructors.md).</span></span>  
  
 <span data-ttu-id="6fc3c-112">除非类是[静态](../../../csharp/language-reference/keywords/static.md)的，否则 C# 编译器将为无构造函数的类提供一个公共的默认构造函数，以便该类可以实例化。</span><span class="sxs-lookup"><span data-stu-id="6fc3c-112">Unless the class is [static](../../../csharp/language-reference/keywords/static.md), classes without constructors are given a public default constructor by the C# compiler in order to enable class instantiation.</span></span> <span data-ttu-id="6fc3c-113">有关详细信息，请参阅[静态类和静态类成员](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md)。</span><span class="sxs-lookup"><span data-stu-id="6fc3c-113">For more information, see [Static Classes and Static Class Members](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md).</span></span>  
  
 <span data-ttu-id="6fc3c-114">通过将构造函数设置为私有构造函数，可以阻止类被实例化，如下所示：</span><span class="sxs-lookup"><span data-stu-id="6fc3c-114">You can prevent a class from being instantiated by making the constructor private, as follows:</span></span>  
  
 <span data-ttu-id="6fc3c-115">[!code-cs[csProgGuideObjects#11](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-constructors_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="6fc3c-115">[!code-cs[csProgGuideObjects#11](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-constructors_2.cs)]</span></span>  
  
 <span data-ttu-id="6fc3c-116">有关详细信息，请参阅[私有构造函数](../../../csharp/programming-guide/classes-and-structs/private-constructors.md)。</span><span class="sxs-lookup"><span data-stu-id="6fc3c-116">For more information, see [Private Constructors](../../../csharp/programming-guide/classes-and-structs/private-constructors.md).</span></span>  
  
 <span data-ttu-id="6fc3c-117">[结构](../../../csharp/language-reference/keywords/struct.md)类型的构造函数与类的构造函数类似，但是 `structs` 不能包含显式默认构造函数，因为编译器将自动提供一个显式默认构造函数。</span><span class="sxs-lookup"><span data-stu-id="6fc3c-117">Constructors for [struct](../../../csharp/language-reference/keywords/struct.md) types resemble class constructors, but `structs` cannot contain an explicit default constructor because one is provided automatically by the compiler.</span></span> <span data-ttu-id="6fc3c-118">此构造函数会将 `struct` 中的每个字段初始化为默认值。</span><span class="sxs-lookup"><span data-stu-id="6fc3c-118">This constructor initializes each field in the `struct` to the default values.</span></span> <span data-ttu-id="6fc3c-119">有关详细信息，请参阅[默认值表](../../../csharp/language-reference/keywords/default-values-table.md)。</span><span class="sxs-lookup"><span data-stu-id="6fc3c-119">For more information, see [Default Values Table](../../../csharp/language-reference/keywords/default-values-table.md).</span></span> <span data-ttu-id="6fc3c-120">但是，只有使用 `new` 实例化 `struct` 时，才会调用此默认构造函数。</span><span class="sxs-lookup"><span data-stu-id="6fc3c-120">However, this default constructor is only invoked if the `struct` is instantiated with `new`.</span></span> <span data-ttu-id="6fc3c-121">例如，下面的代码使用 <xref:System.Int32> 的默认构造函数，因此可确保整数已初始化：</span><span class="sxs-lookup"><span data-stu-id="6fc3c-121">For example, this code uses the default constructor for <xref:System.Int32>, so that you are assured that the integer is initialized:</span></span>  
  
```  
int i = new int();  
Console.WriteLine(i);  
```  
  
 <span data-ttu-id="6fc3c-122">但是，下面的代码会导致编译器错误，因为它不使用 `new`，而且尝试使用尚未初始化的对象：</span><span class="sxs-lookup"><span data-stu-id="6fc3c-122">The following code, however, causes a compiler error because it does not use `new`, and because it tries to use an object that has not been initialized:</span></span>  
  
```  
int i;  
Console.WriteLine(i);  
```  
  
 <span data-ttu-id="6fc3c-123">或者，可将基于 `structs` 的对象（包括所有内置数值类型）初始化或赋值后使用，如下面的示例所示：</span><span class="sxs-lookup"><span data-stu-id="6fc3c-123">Alternatively, objects based on `structs` (including all built-in numeric types) can be initialized or assigned and then used as in the following example:</span></span>  
  
```  
int a = 44;  // Initialize the value type...  
int b;  
b = 33;      // Or assign it before using it.  
Console.WriteLine("{0}, {1}", a, b);  
```  
  
 <span data-ttu-id="6fc3c-124">因此不需要调用值类型的默认构造函数。</span><span class="sxs-lookup"><span data-stu-id="6fc3c-124">So calling the default constructor for a value type is not required.</span></span>  
  
 <span data-ttu-id="6fc3c-125">两个类和 `structs` 都可以定义带参数的构造函数。</span><span class="sxs-lookup"><span data-stu-id="6fc3c-125">Both classes and `structs` can define constructors that take parameters.</span></span> <span data-ttu-id="6fc3c-126">必须通过 `new` 语句或 [base](../../../csharp/language-reference/keywords/base.md) 语句调用带参数的构造函数。</span><span class="sxs-lookup"><span data-stu-id="6fc3c-126">Constructors that take parameters must be called through a `new` statement or a [base](../../../csharp/language-reference/keywords/base.md) statement.</span></span> <span data-ttu-id="6fc3c-127">类和 `structs` 还可以定义多个构造函数，并且二者均不需要定义默认构造函数。</span><span class="sxs-lookup"><span data-stu-id="6fc3c-127">Classes and `structs` can also define multiple constructors, and neither is required to define a default constructor.</span></span> <span data-ttu-id="6fc3c-128">例如: </span><span class="sxs-lookup"><span data-stu-id="6fc3c-128">For example:</span></span>  
  
 <span data-ttu-id="6fc3c-129">[!code-cs[csProgGuideObjects#54](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-constructors_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="6fc3c-129">[!code-cs[csProgGuideObjects#54](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-constructors_3.cs)]</span></span>  
  
 <span data-ttu-id="6fc3c-130">可使用下面任一语句创建此类：</span><span class="sxs-lookup"><span data-stu-id="6fc3c-130">This class can be created by using either of the following statements:</span></span>  
  
 <span data-ttu-id="6fc3c-131">[!code-cs[csProgGuideObjects#55](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-constructors_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="6fc3c-131">[!code-cs[csProgGuideObjects#55](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-constructors_4.cs)]</span></span>  
  
 <span data-ttu-id="6fc3c-132">构造函数可以使用 `base` 关键字调用基类的构造函数。</span><span class="sxs-lookup"><span data-stu-id="6fc3c-132">A constructor can use the `base` keyword to call the constructor of a base class.</span></span> <span data-ttu-id="6fc3c-133">例如: </span><span class="sxs-lookup"><span data-stu-id="6fc3c-133">For example:</span></span>  
  
 <span data-ttu-id="6fc3c-134">[!code-cs[csProgGuideObjects#56](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-constructors_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="6fc3c-134">[!code-cs[csProgGuideObjects#56](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-constructors_5.cs)]</span></span>  
  
 <span data-ttu-id="6fc3c-135">在此示例中，在执行构造函数块之前调用基类的构造函数。</span><span class="sxs-lookup"><span data-stu-id="6fc3c-135">In this example, the constructor for the base class is called before the block for the constructor is executed.</span></span> <span data-ttu-id="6fc3c-136">`base` 关键字可带参数使用，也可不带参数使用。</span><span class="sxs-lookup"><span data-stu-id="6fc3c-136">The `base` keyword can be used with or without parameters.</span></span> <span data-ttu-id="6fc3c-137">构造函数的任何参数都可用作 `base` 的参数，或用作表达式的一部分。</span><span class="sxs-lookup"><span data-stu-id="6fc3c-137">Any parameters to the constructor can be used as parameters to `base`, or as part of an expression.</span></span> <span data-ttu-id="6fc3c-138">有关详细信息，请参阅 [base](../../../csharp/language-reference/keywords/base.md)。</span><span class="sxs-lookup"><span data-stu-id="6fc3c-138">For more information, see [base](../../../csharp/language-reference/keywords/base.md).</span></span>  
  
 <span data-ttu-id="6fc3c-139">在派生类中，如果不使用 `base` 关键字来显式调用基类构造函数，则将隐式调用默认构造函数（若有）。</span><span class="sxs-lookup"><span data-stu-id="6fc3c-139">In a derived class, if a base-class constructor is not called explicitly by using the `base` keyword, the default constructor, if there is one, is called implicitly.</span></span> <span data-ttu-id="6fc3c-140">这意味着下面的构造函数声明等效：</span><span class="sxs-lookup"><span data-stu-id="6fc3c-140">This means that the following constructor declarations are effectively the same:</span></span>  
  
 <span data-ttu-id="6fc3c-141">[!code-cs[csProgGuideObjects#58](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-constructors_6.cs)]</span><span class="sxs-lookup"><span data-stu-id="6fc3c-141">[!code-cs[csProgGuideObjects#58](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-constructors_6.cs)]</span></span>  
  
 <span data-ttu-id="6fc3c-142">[!code-cs[csProgGuideObjects#57](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-constructors_7.cs)]</span><span class="sxs-lookup"><span data-stu-id="6fc3c-142">[!code-cs[csProgGuideObjects#57](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-constructors_7.cs)]</span></span>  
  
 <span data-ttu-id="6fc3c-143">如果基类没有提供默认构造函数，派生类必须使用 `base` 显式调用基类构造函数。</span><span class="sxs-lookup"><span data-stu-id="6fc3c-143">If a base class does not offer a default constructor, the derived class must make an explicit call to a base constructor by using `base`.</span></span>  
  
 <span data-ttu-id="6fc3c-144">构造函数可以使用 [this](../../../csharp/language-reference/keywords/this.md) 关键字调用同一对象中的另一构造函数。</span><span class="sxs-lookup"><span data-stu-id="6fc3c-144">A constructor can invoke another constructor in the same object by using the [this](../../../csharp/language-reference/keywords/this.md) keyword.</span></span> <span data-ttu-id="6fc3c-145">和 `base` 一样，`this` 可带参数使用也可不带参数使用，构造函数中的任何参数都可用作 `this` 的参数，或者用作表达式的一部分。</span><span class="sxs-lookup"><span data-stu-id="6fc3c-145">Like `base`, `this` can be used with or without parameters, and any parameters in the constructor are available as parameters to `this`, or as part of an expression.</span></span> <span data-ttu-id="6fc3c-146">例如，可以使用 `this` 重写前一示例中的第二个构造函数：</span><span class="sxs-lookup"><span data-stu-id="6fc3c-146">For example, the second constructor in the previous example can be rewritten using `this`:</span></span>  
  
 <span data-ttu-id="6fc3c-147">[!code-cs[csProgGuideObjects#59](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-constructors_8.cs)]</span><span class="sxs-lookup"><span data-stu-id="6fc3c-147">[!code-cs[csProgGuideObjects#59](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-constructors_8.cs)]</span></span>  
  
 <span data-ttu-id="6fc3c-148">上一示例中使用 `this` 关键字会导致此构造函数被调用：</span><span class="sxs-lookup"><span data-stu-id="6fc3c-148">The use of the `this` keyword in the previous example causes this constructor to be called:</span></span>  
  
 <span data-ttu-id="6fc3c-149">[!code-cs[csProgGuideObjects#60](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-constructors_9.cs)]</span><span class="sxs-lookup"><span data-stu-id="6fc3c-149">[!code-cs[csProgGuideObjects#60](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-constructors_9.cs)]</span></span>  
  
 <span data-ttu-id="6fc3c-150">可以将构造函数标记为[公共](../../../csharp/language-reference/keywords/public.md)、[专用](../../../csharp/language-reference/keywords/private.md)、[受保护](../../../csharp/language-reference/keywords/protected.md)、[内部](../../../csharp/language-reference/keywords/internal.md)或 `protected internal`。</span><span class="sxs-lookup"><span data-stu-id="6fc3c-150">Constructors can be marked as [public](../../../csharp/language-reference/keywords/public.md), [private](../../../csharp/language-reference/keywords/private.md), [protected](../../../csharp/language-reference/keywords/protected.md), [internal](../../../csharp/language-reference/keywords/internal.md), or `protected internal`.</span></span> <span data-ttu-id="6fc3c-151">这些访问修饰符定义类的用户构造该类的方式。</span><span class="sxs-lookup"><span data-stu-id="6fc3c-151">These access modifiers define how users of the class can construct the class.</span></span> <span data-ttu-id="6fc3c-152">有关详细信息，请参阅[访问修饰符](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)。</span><span class="sxs-lookup"><span data-stu-id="6fc3c-152">For more information, see [Access Modifiers](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).</span></span>  
  
 <span data-ttu-id="6fc3c-153">可使用 [static](../../../csharp/language-reference/keywords/static.md) 关键字将构造函数声明为静态构造函数。</span><span class="sxs-lookup"><span data-stu-id="6fc3c-153">A constructor can be declared static by using the [static](../../../csharp/language-reference/keywords/static.md) keyword.</span></span> <span data-ttu-id="6fc3c-154">在访问任何静态字段之前，都将自动调用静态构造函数，它们通常用于初始化静态类成员。</span><span class="sxs-lookup"><span data-stu-id="6fc3c-154">Static constructors are called automatically, immediately before any static fields are accessed, and are generally used to initialize static class members.</span></span> <span data-ttu-id="6fc3c-155">有关详细信息，请参阅[静态构造函数](../../../csharp/programming-guide/classes-and-structs/static-constructors.md)。</span><span class="sxs-lookup"><span data-stu-id="6fc3c-155">For more information, see [Static Constructors](../../../csharp/programming-guide/classes-and-structs/static-constructors.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="6fc3c-156">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="6fc3c-156">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="6fc3c-157">请参阅</span><span class="sxs-lookup"><span data-stu-id="6fc3c-157">See Also</span></span>  
 <span data-ttu-id="6fc3c-158">[C# 编程指南](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="6fc3c-158">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="6fc3c-159">[类和结构](../../../csharp/programming-guide/classes-and-structs/index.md) </span><span class="sxs-lookup"><span data-stu-id="6fc3c-159">[Classes and Structs](../../../csharp/programming-guide/classes-and-structs/index.md) </span></span>  
 <span data-ttu-id="6fc3c-160">[构造函数](../../../csharp/programming-guide/classes-and-structs/constructors.md) </span><span class="sxs-lookup"><span data-stu-id="6fc3c-160">[Constructors](../../../csharp/programming-guide/classes-and-structs/constructors.md) </span></span>  
 [<span data-ttu-id="6fc3c-161">终结器</span><span class="sxs-lookup"><span data-stu-id="6fc3c-161">Finalizers</span></span>](../../../csharp/programming-guide/classes-and-structs/destructors.md)

