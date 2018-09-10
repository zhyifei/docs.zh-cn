---
title: 使用构造函数（C# 编程指南）
ms.date: 07/20/2015
helpviewer_keywords:
- constructors [C#], about constructors
ms.assetid: 464253b2-fd5d-469a-836d-df0fdf2a43f7
ms.openlocfilehash: b19676b2549bbb54af7fb1d72ff0e98352c61383
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43529015"
---
# <a name="using-constructors-c-programming-guide"></a><span data-ttu-id="4af43-102">使用构造函数（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="4af43-102">Using Constructors (C# Programming Guide)</span></span>
<span data-ttu-id="4af43-103">创建[类](../../../csharp/language-reference/keywords/class.md)或[结构](../../../csharp/language-reference/keywords/struct.md)时，将会调用其构造函数。</span><span class="sxs-lookup"><span data-stu-id="4af43-103">When a [class](../../../csharp/language-reference/keywords/class.md) or [struct](../../../csharp/language-reference/keywords/struct.md) is created, its constructor is called.</span></span> <span data-ttu-id="4af43-104">构造函数与该类或结构具有相同名称，并且通常初始化新对象的数据成员。</span><span class="sxs-lookup"><span data-stu-id="4af43-104">Constructors have the same name as the class or struct, and they usually initialize the data members of the new object.</span></span>  
  
 <span data-ttu-id="4af43-105">在下面的示例中，通过使用简单构造函数定义了一个名为 `Taxi` 的类。</span><span class="sxs-lookup"><span data-stu-id="4af43-105">In the following example, a class named `Taxi` is defined by using a simple constructor.</span></span> <span data-ttu-id="4af43-106">然后使用 [new](../../../csharp/language-reference/keywords/new.md) 运算符对该类进行实例化。</span><span class="sxs-lookup"><span data-stu-id="4af43-106">This class is then instantiated with the [new](../../../csharp/language-reference/keywords/new.md) operator.</span></span> <span data-ttu-id="4af43-107">在为新对象分配内存之后，`new` 运算符立即调用 `Taxi` 构造函数。</span><span class="sxs-lookup"><span data-stu-id="4af43-107">The `Taxi` constructor is invoked by the `new` operator immediately after memory is allocated for the new object.</span></span>  
  
 [!code-csharp[csProgGuideObjects#53](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-constructors_1.cs)]  
  
 <span data-ttu-id="4af43-108">不带任何参数的构造函数称为“默认构造函数”。</span><span class="sxs-lookup"><span data-stu-id="4af43-108">A constructor that takes no parameters is called a *default constructor*.</span></span> <span data-ttu-id="4af43-109">每当使用 `new` 运算符实例化对象且不为 `new` 提供任何参数时，会调用默认构造函数。</span><span class="sxs-lookup"><span data-stu-id="4af43-109">Default constructors are invoked whenever an object is instantiated by using the `new` operator and no arguments are provided to `new`.</span></span> <span data-ttu-id="4af43-110">有关详细信息，请参阅[实例构造函数](../../../csharp/programming-guide/classes-and-structs/instance-constructors.md)。</span><span class="sxs-lookup"><span data-stu-id="4af43-110">For more information, see [Instance Constructors](../../../csharp/programming-guide/classes-and-structs/instance-constructors.md).</span></span>  
  
 <span data-ttu-id="4af43-111">除非类是[静态](../../../csharp/language-reference/keywords/static.md)的，否则 C# 编译器将为无构造函数的类提供一个公共的默认构造函数，以便该类可以实例化。</span><span class="sxs-lookup"><span data-stu-id="4af43-111">Unless the class is [static](../../../csharp/language-reference/keywords/static.md), classes without constructors are given a public default constructor by the C# compiler in order to enable class instantiation.</span></span> <span data-ttu-id="4af43-112">有关详细信息，请参阅[静态类和静态类成员](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md)。</span><span class="sxs-lookup"><span data-stu-id="4af43-112">For more information, see [Static Classes and Static Class Members](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md).</span></span>  
  
 <span data-ttu-id="4af43-113">通过将构造函数设置为私有构造函数，可以阻止类被实例化，如下所示：</span><span class="sxs-lookup"><span data-stu-id="4af43-113">You can prevent a class from being instantiated by making the constructor private, as follows:</span></span>  
  
 [!code-csharp[csProgGuideObjects#11](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-constructors_2.cs)]  
  
 <span data-ttu-id="4af43-114">有关详细信息，请参阅[私有构造函数](../../../csharp/programming-guide/classes-and-structs/private-constructors.md)。</span><span class="sxs-lookup"><span data-stu-id="4af43-114">For more information, see [Private Constructors](../../../csharp/programming-guide/classes-and-structs/private-constructors.md).</span></span>  
  
 <span data-ttu-id="4af43-115">[结构](../../../csharp/language-reference/keywords/struct.md)类型的构造函数与类的构造函数类似，但是 `structs` 不能包含显式默认构造函数，因为编译器将自动提供一个显式默认构造函数。</span><span class="sxs-lookup"><span data-stu-id="4af43-115">Constructors for [struct](../../../csharp/language-reference/keywords/struct.md) types resemble class constructors, but `structs` cannot contain an explicit default constructor because one is provided automatically by the compiler.</span></span> <span data-ttu-id="4af43-116">此构造函数会将 `struct` 中的每个字段初始化为默认值。</span><span class="sxs-lookup"><span data-stu-id="4af43-116">This constructor initializes each field in the `struct` to the default values.</span></span> <span data-ttu-id="4af43-117">有关详细信息，请参阅[默认值表](../../../csharp/language-reference/keywords/default-values-table.md)。</span><span class="sxs-lookup"><span data-stu-id="4af43-117">For more information, see [Default Values Table](../../../csharp/language-reference/keywords/default-values-table.md).</span></span> <span data-ttu-id="4af43-118">但是，只有使用 `new` 实例化 `struct` 时，才会调用此默认构造函数。</span><span class="sxs-lookup"><span data-stu-id="4af43-118">However, this default constructor is only invoked if the `struct` is instantiated with `new`.</span></span> <span data-ttu-id="4af43-119">例如，下面的代码使用 <xref:System.Int32> 的默认构造函数，因此可确保整数已初始化：</span><span class="sxs-lookup"><span data-stu-id="4af43-119">For example, this code uses the default constructor for <xref:System.Int32>, so that you are assured that the integer is initialized:</span></span>  
  
```csharp  
int i = new int();  
Console.WriteLine(i);  
```  
  
 <span data-ttu-id="4af43-120">但是，下面的代码会导致编译器错误，因为它不使用 `new`，而且尝试使用尚未初始化的对象：</span><span class="sxs-lookup"><span data-stu-id="4af43-120">The following code, however, causes a compiler error because it does not use `new`, and because it tries to use an object that has not been initialized:</span></span>  
  
```  
int i;  
Console.WriteLine(i);  
```  
  
 <span data-ttu-id="4af43-121">或者，可将基于 `structs` 的对象（包括所有内置数值类型）初始化或赋值后使用，如下面的示例所示：</span><span class="sxs-lookup"><span data-stu-id="4af43-121">Alternatively, objects based on `structs` (including all built-in numeric types) can be initialized or assigned and then used as in the following example:</span></span>  
  
```  
int a = 44;  // Initialize the value type...  
int b;  
b = 33;      // Or assign it before using it.  
Console.WriteLine("{0}, {1}", a, b);  
```  
  
 <span data-ttu-id="4af43-122">因此不需要调用值类型的默认构造函数。</span><span class="sxs-lookup"><span data-stu-id="4af43-122">So calling the default constructor for a value type is not required.</span></span>  
  
 <span data-ttu-id="4af43-123">两个类和 `structs` 都可以定义带参数的构造函数。</span><span class="sxs-lookup"><span data-stu-id="4af43-123">Both classes and `structs` can define constructors that take parameters.</span></span> <span data-ttu-id="4af43-124">必须通过 `new` 语句或 [base](../../../csharp/language-reference/keywords/base.md) 语句调用带参数的构造函数。</span><span class="sxs-lookup"><span data-stu-id="4af43-124">Constructors that take parameters must be called through a `new` statement or a [base](../../../csharp/language-reference/keywords/base.md) statement.</span></span> <span data-ttu-id="4af43-125">类和 `structs` 还可以定义多个构造函数，并且二者均不需要定义默认构造函数。</span><span class="sxs-lookup"><span data-stu-id="4af43-125">Classes and `structs` can also define multiple constructors, and neither is required to define a default constructor.</span></span> <span data-ttu-id="4af43-126">例如:</span><span class="sxs-lookup"><span data-stu-id="4af43-126">For example:</span></span>  
  
 [!code-csharp[csProgGuideObjects#54](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-constructors_3.cs)]  
  
 <span data-ttu-id="4af43-127">可使用下面任一语句创建此类：</span><span class="sxs-lookup"><span data-stu-id="4af43-127">This class can be created by using either of the following statements:</span></span>  
  
 [!code-csharp[csProgGuideObjects#55](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-constructors_4.cs)]  
  
 <span data-ttu-id="4af43-128">构造函数可以使用 `base` 关键字调用基类的构造函数。</span><span class="sxs-lookup"><span data-stu-id="4af43-128">A constructor can use the `base` keyword to call the constructor of a base class.</span></span> <span data-ttu-id="4af43-129">例如:</span><span class="sxs-lookup"><span data-stu-id="4af43-129">For example:</span></span>  
  
 [!code-csharp[csProgGuideObjects#56](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-constructors_5.cs)]  
  
 <span data-ttu-id="4af43-130">在此示例中，在执行构造函数块之前调用基类的构造函数。</span><span class="sxs-lookup"><span data-stu-id="4af43-130">In this example, the constructor for the base class is called before the block for the constructor is executed.</span></span> <span data-ttu-id="4af43-131">`base` 关键字可带参数使用，也可不带参数使用。</span><span class="sxs-lookup"><span data-stu-id="4af43-131">The `base` keyword can be used with or without parameters.</span></span> <span data-ttu-id="4af43-132">构造函数的任何参数都可用作 `base` 的参数，或用作表达式的一部分。</span><span class="sxs-lookup"><span data-stu-id="4af43-132">Any parameters to the constructor can be used as parameters to `base`, or as part of an expression.</span></span> <span data-ttu-id="4af43-133">有关详细信息，请参阅 [base](../../../csharp/language-reference/keywords/base.md)。</span><span class="sxs-lookup"><span data-stu-id="4af43-133">For more information, see [base](../../../csharp/language-reference/keywords/base.md).</span></span>  
  
 <span data-ttu-id="4af43-134">在派生类中，如果不使用 `base` 关键字来显式调用基类构造函数，则将隐式调用默认构造函数（若有）。</span><span class="sxs-lookup"><span data-stu-id="4af43-134">In a derived class, if a base-class constructor is not called explicitly by using the `base` keyword, the default constructor, if there is one, is called implicitly.</span></span> <span data-ttu-id="4af43-135">这意味着下面的构造函数声明等效：</span><span class="sxs-lookup"><span data-stu-id="4af43-135">This means that the following constructor declarations are effectively the same:</span></span>  
  
 [!code-csharp[csProgGuideObjects#58](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-constructors_6.cs)]  
  
 [!code-csharp[csProgGuideObjects#57](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-constructors_7.cs)]  
  
 <span data-ttu-id="4af43-136">如果基类没有提供默认构造函数，派生类必须使用 `base` 显式调用基类构造函数。</span><span class="sxs-lookup"><span data-stu-id="4af43-136">If a base class does not offer a default constructor, the derived class must make an explicit call to a base constructor by using `base`.</span></span>  
  
 <span data-ttu-id="4af43-137">构造函数可以使用 [this](../../../csharp/language-reference/keywords/this.md) 关键字调用同一对象中的另一构造函数。</span><span class="sxs-lookup"><span data-stu-id="4af43-137">A constructor can invoke another constructor in the same object by using the [this](../../../csharp/language-reference/keywords/this.md) keyword.</span></span> <span data-ttu-id="4af43-138">和 `base` 一样，`this` 可带参数使用也可不带参数使用，构造函数中的任何参数都可用作 `this` 的参数，或者用作表达式的一部分。</span><span class="sxs-lookup"><span data-stu-id="4af43-138">Like `base`, `this` can be used with or without parameters, and any parameters in the constructor are available as parameters to `this`, or as part of an expression.</span></span> <span data-ttu-id="4af43-139">例如，可以使用 `this` 重写前一示例中的第二个构造函数：</span><span class="sxs-lookup"><span data-stu-id="4af43-139">For example, the second constructor in the previous example can be rewritten using `this`:</span></span>  
  
 [!code-csharp[csProgGuideObjects#59](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-constructors_8.cs)]  
  
 <span data-ttu-id="4af43-140">上一示例中使用 `this` 关键字会导致此构造函数被调用：</span><span class="sxs-lookup"><span data-stu-id="4af43-140">The use of the `this` keyword in the previous example causes this constructor to be called:</span></span>  
  
 [!code-csharp[csProgGuideObjects#60](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-constructors_9.cs)]  
  
 <span data-ttu-id="4af43-141">可以将构造函数标记为[public](../../../csharp/language-reference/keywords/public.md)、[private](../../../csharp/language-reference/keywords/private.md)、[protected](../../../csharp/language-reference/keywords/protected.md)、[internal](../../../csharp/language-reference/keywords/internal.md)、[protected internal](../../../csharp/language-reference/keywords/protected-internal.md) 或 [private protected](../../../csharp/language-reference/keywords/private-protected.md)。</span><span class="sxs-lookup"><span data-stu-id="4af43-141">Constructors can be marked as [public](../../../csharp/language-reference/keywords/public.md), [private](../../../csharp/language-reference/keywords/private.md), [protected](../../../csharp/language-reference/keywords/protected.md), [internal](../../../csharp/language-reference/keywords/internal.md), [protected internal](../../../csharp/language-reference/keywords/protected-internal.md) or [private protected](../../../csharp/language-reference/keywords/private-protected.md).</span></span> <span data-ttu-id="4af43-142">这些访问修饰符定义类的用户构造该类的方式。</span><span class="sxs-lookup"><span data-stu-id="4af43-142">These access modifiers define how users of the class can construct the class.</span></span> <span data-ttu-id="4af43-143">有关详细信息，请参阅[访问修饰符](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)。</span><span class="sxs-lookup"><span data-stu-id="4af43-143">For more information, see [Access Modifiers](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).</span></span>  
  
 <span data-ttu-id="4af43-144">可使用 [static](../../../csharp/language-reference/keywords/static.md) 关键字将构造函数声明为静态构造函数。</span><span class="sxs-lookup"><span data-stu-id="4af43-144">A constructor can be declared static by using the [static](../../../csharp/language-reference/keywords/static.md) keyword.</span></span> <span data-ttu-id="4af43-145">在访问任何静态字段之前，都将自动调用静态构造函数，它们通常用于初始化静态类成员。</span><span class="sxs-lookup"><span data-stu-id="4af43-145">Static constructors are called automatically, immediately before any static fields are accessed, and are generally used to initialize static class members.</span></span> <span data-ttu-id="4af43-146">有关详细信息，请参阅[静态构造函数](../../../csharp/programming-guide/classes-and-structs/static-constructors.md)。</span><span class="sxs-lookup"><span data-stu-id="4af43-146">For more information, see [Static Constructors](../../../csharp/programming-guide/classes-and-structs/static-constructors.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="4af43-147">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="4af43-147">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="4af43-148">请参阅</span><span class="sxs-lookup"><span data-stu-id="4af43-148">See Also</span></span>

- [<span data-ttu-id="4af43-149">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="4af43-149">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="4af43-150">类和结构</span><span class="sxs-lookup"><span data-stu-id="4af43-150">Classes and Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/index.md)  
- [<span data-ttu-id="4af43-151">构造函数</span><span class="sxs-lookup"><span data-stu-id="4af43-151">Constructors</span></span>](../../../csharp/programming-guide/classes-and-structs/constructors.md)  
- [<span data-ttu-id="4af43-152">终结器</span><span class="sxs-lookup"><span data-stu-id="4af43-152">Finalizers</span></span>](../../../csharp/programming-guide/classes-and-structs/destructors.md)
