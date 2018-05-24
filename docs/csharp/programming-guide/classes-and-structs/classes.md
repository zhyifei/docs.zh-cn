---
title: 类（C# 编程指南）
description: 了解类类型及其创建方式
ms.date: 04/05/2018
helpviewer_keywords:
- classes [C#]
- C# language, classes
ms.assetid: e8848524-7273-429f-8aba-c658d5eff5ad
ms.openlocfilehash: 688736aa8556719789b02d7db25858f442b4309e
ms.sourcegitcommit: 895c7602386a6dfe7ca4facce3d965b27e5c6e87
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2018
---
# <a name="classes-c-programming-guide"></a><span data-ttu-id="ae130-103">类（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="ae130-103">Classes (C# Programming Guide)</span></span>
<span data-ttu-id="ae130-104">*类*属于构造，使用类，可以通过组合其他类型的变量、方法和事件创建自己的自定义类型。</span><span class="sxs-lookup"><span data-stu-id="ae130-104">A *class* is a construct that enables you to create your own custom types by grouping together variables of other types, methods and events.</span></span> <span data-ttu-id="ae130-105">类好比是蓝图。</span><span class="sxs-lookup"><span data-stu-id="ae130-105">A class is like a blueprint.</span></span> <span data-ttu-id="ae130-106">它定义类型的数据和行为。</span><span class="sxs-lookup"><span data-stu-id="ae130-106">It defines the data and behavior of a type.</span></span> <span data-ttu-id="ae130-107">如果类未声明为静态，客户端代码可以创建它的实例。</span><span class="sxs-lookup"><span data-stu-id="ae130-107">If the class is not declared as static, client code can create *instances* of it.</span></span> <span data-ttu-id="ae130-108">这些实例是分配给变量的对象。</span><span class="sxs-lookup"><span data-stu-id="ae130-108">These instances are *objects* which are assigned to a variable.</span></span> <span data-ttu-id="ae130-109">类实例会一直保留在内存中，直到对它的所有引用都不在作用域范围之内。</span><span class="sxs-lookup"><span data-stu-id="ae130-109">The instance of a class remains in memory until all references to it go out of scope.</span></span> <span data-ttu-id="ae130-110">超出范围时，CLR 将对其进行标记，以便用于垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="ae130-110">At that time, the CLR marks it as eligible for garbage collection.</span></span> <span data-ttu-id="ae130-111">如果类声明为[静态](../../../csharp/language-reference/keywords/static.md)，便无法创建实例，并且客户端代码只能通过类本身来访问它。</span><span class="sxs-lookup"><span data-stu-id="ae130-111">If the class is declared as [static](../../../csharp/language-reference/keywords/static.md), you cannot create instances, and client code can only access it through the class itself.</span></span> <span data-ttu-id="ae130-112">有关详细信息，请参阅[静态类和静态类成员](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md)。</span><span class="sxs-lookup"><span data-stu-id="ae130-112">For more information, see [Static Classes and Static Class Members](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md).</span></span>  

## <a name="reference-types"></a><span data-ttu-id="ae130-113">引用类型</span><span class="sxs-lookup"><span data-stu-id="ae130-113">Reference types</span></span>  
<span data-ttu-id="ae130-114">定义为[类](../../../csharp/language-reference/keywords/class.md)的一个类型是*引用类型*。</span><span class="sxs-lookup"><span data-stu-id="ae130-114">A type that is defined as a [class](../../../csharp/language-reference/keywords/class.md) is a *reference type*.</span></span> <span data-ttu-id="ae130-115">在运行时，如果声明引用类型的变量，此变量就会一直包含值 [null](../../../csharp/language-reference/keywords/null.md)，直到使用 [new](../../../csharp/language-reference/keywords/new.md) 运算符显式创建类实例，或直到为此变量分配已在其他位置创建的对象，如下面的示例所示：</span><span class="sxs-lookup"><span data-stu-id="ae130-115">At run time, when you declare a variable of a reference type, the variable contains the value [null](../../../csharp/language-reference/keywords/null.md) until you explicitly create an instance of the class by using the [new](../../../csharp/language-reference/keywords/new.md) operator, or assign it an object that has been created elsewhere, as shown in the following example:</span></span>

```csharp
MyClass mc = new MyClass();
MyClass mc2 = mc;
```

<span data-ttu-id="ae130-116">创建对象后，内存位于托管堆上，并且变量只保留对对象位置的引用。</span><span class="sxs-lookup"><span data-stu-id="ae130-116">When the object is created, the memory is allocated on the managed heap, and the variable holds only a reference to the location of the object.</span></span> <span data-ttu-id="ae130-117">当分配托管堆上的类型和由 CLR 的自动内存管理功能对其进行回收（称为*垃圾回收*）时，需要开销。</span><span class="sxs-lookup"><span data-stu-id="ae130-117">Types on the managed heap require overhead both when they are allocated and when they are reclaimed by the automatic memory management functionality of the CLR, which is known as *garbage collection*.</span></span> <span data-ttu-id="ae130-118">但是，垃圾回收已是高度优化，并且在大多数情况下，不会产生性能问题。</span><span class="sxs-lookup"><span data-stu-id="ae130-118">However, garbage collection is also highly optimized, and in most scenarios, it does not create a performance issue.</span></span> <span data-ttu-id="ae130-119">有关垃圾回收的详细信息，请参阅[自动内存管理和垃圾回收](../../../standard/garbage-collection/gc.md)。</span><span class="sxs-lookup"><span data-stu-id="ae130-119">For more information about garbage collection, see [Automatic memory management and garbage collection](../../../standard/garbage-collection/gc.md).</span></span>  
  
## <a name="declaring-classes"></a><span data-ttu-id="ae130-120">声明类</span><span class="sxs-lookup"><span data-stu-id="ae130-120">Declaring Classes</span></span>  
 <span data-ttu-id="ae130-121">使用 [class](../../../csharp/language-reference/keywords/class.md) 关键字可以声明类，如下例所示：</span><span class="sxs-lookup"><span data-stu-id="ae130-121">Classes are declared by using the [class](../../../csharp/language-reference/keywords/class.md) keyword, as shown in the following example:</span></span>

 ```csharp
 public class Customer
 {
    // Fields, properties, methods and events go here...
 }
```

 <span data-ttu-id="ae130-122">`class` 关键字前面是访问级别。</span><span class="sxs-lookup"><span data-stu-id="ae130-122">The `class` keyword is preceded by the access level.</span></span> <span data-ttu-id="ae130-123">因为此例中使用的是 [public](../../../csharp/language-reference/keywords/public.md)，所以任何人都可以创建此类的实例。</span><span class="sxs-lookup"><span data-stu-id="ae130-123">Because [public](../../../csharp/language-reference/keywords/public.md) is used in this case, anyone can create instances of this class.</span></span> <span data-ttu-id="ae130-124">类的名称遵循 `class` 关键字。</span><span class="sxs-lookup"><span data-stu-id="ae130-124">The name of the class follows the `class` keyword.</span></span> <span data-ttu-id="ae130-125">定义的其余部分是类的主体，其中定义了行为和数据。</span><span class="sxs-lookup"><span data-stu-id="ae130-125">The remainder of the definition is the class body, where the behavior and data are defined.</span></span> <span data-ttu-id="ae130-126">类上的字段、属性、方法和事件统称为*类成员*。</span><span class="sxs-lookup"><span data-stu-id="ae130-126">Fields, properties, methods, and events on a class are collectively referred to as *class members*.</span></span>  
  
## <a name="creating-objects"></a><span data-ttu-id="ae130-127">创建对象</span><span class="sxs-lookup"><span data-stu-id="ae130-127">Creating Objects</span></span>  
 <span data-ttu-id="ae130-128">虽然它们有时可以互换使用，但类和对象是不同的概念。</span><span class="sxs-lookup"><span data-stu-id="ae130-128">Although they are sometimes used interchangeably, a class and an object are different things.</span></span> <span data-ttu-id="ae130-129">类定义对象类型，但不是对象本身。</span><span class="sxs-lookup"><span data-stu-id="ae130-129">A class defines a type of object, but it is not an object itself.</span></span> <span data-ttu-id="ae130-130">对象是基于类的具体实体，有时称为类的实例。</span><span class="sxs-lookup"><span data-stu-id="ae130-130">An object is a concrete entity based on a class, and is sometimes referred to as an instance of a class.</span></span>  
  
 <span data-ttu-id="ae130-131">可通过使用 [new](../../../csharp/language-reference/keywords/new.md) 关键字，后跟对象要基于的类的名称，来创建对象，如：</span><span class="sxs-lookup"><span data-stu-id="ae130-131">Objects can be created by using the [new](../../../csharp/language-reference/keywords/new.md) keyword followed by the name of the class that the object will be based on, like this:</span></span>  

 ```csharp
 Customer object1 = new Customer();
 ```
  
 <span data-ttu-id="ae130-132">创建类的实例后，会将一个该对象的引用传递回程序员。</span><span class="sxs-lookup"><span data-stu-id="ae130-132">When an instance of a class is created, a reference to the object is passed back to the programmer.</span></span> <span data-ttu-id="ae130-133">在上一示例中，`object1` 是对基于 `Customer` 的对象的引用。</span><span class="sxs-lookup"><span data-stu-id="ae130-133">In the previous example, `object1` is a reference to an object that is based on `Customer`.</span></span> <span data-ttu-id="ae130-134">该引用指向新对象，但不包含对象数据本身。</span><span class="sxs-lookup"><span data-stu-id="ae130-134">This reference refers to the new object but does not contain the object data itself.</span></span> <span data-ttu-id="ae130-135">事实上，可以创建对象引用，而完全无需创建对象本身：</span><span class="sxs-lookup"><span data-stu-id="ae130-135">In fact, you can create an object reference without creating an object at all:</span></span>  
  
  ```csharp
  Customer object2;
  ```
  
 <span data-ttu-id="ae130-136">不建议创建这样一个不引用对象的对象引用，因为尝试通过这类引用访问对象会在运行时失败。</span><span class="sxs-lookup"><span data-stu-id="ae130-136">We don't recommend creating object references such as this one that don't refer to an object because trying to access an object through such a reference will fail at run time.</span></span> <span data-ttu-id="ae130-137">但实际上可以使用这类引用来引用某个对象，方法是创建新对象，或者将其分配给现有对象，例如：</span><span class="sxs-lookup"><span data-stu-id="ae130-137">However, such a reference can be made to refer to an object, either by creating a new object, or by assigning it to an existing object, such as this:</span></span>  

 ```csharp
 Customer object3 = new Customer();
 Customer object4 = object3;
 ```
  
 <span data-ttu-id="ae130-138">此代码创建指向同一对象的两个对象引用。</span><span class="sxs-lookup"><span data-stu-id="ae130-138">This code creates two object references that both refer to the same object.</span></span> <span data-ttu-id="ae130-139">因此，通过 `object3` 对对象做出的任何更改都会在后续使用 `object4` 时反映出来。</span><span class="sxs-lookup"><span data-stu-id="ae130-139">Therefore, any changes to the object made through `object3` are reflected in subsequent uses of `object4`.</span></span> <span data-ttu-id="ae130-140">由于基于类的对象是通过引用来实现其引用的，因此类被称为引用类型。</span><span class="sxs-lookup"><span data-stu-id="ae130-140">Because objects that are based on classes are referred to by reference, classes are known as reference types.</span></span>  
  
## <a name="class-inheritance"></a><span data-ttu-id="ae130-141">类继承</span><span class="sxs-lookup"><span data-stu-id="ae130-141">Class Inheritance</span></span>  

 <span data-ttu-id="ae130-142">类完全支持继承，这是面向对象的编程的基本特点。</span><span class="sxs-lookup"><span data-stu-id="ae130-142">Classes fully support *inheritance*, a fundamental characteristic of object-oriented programming.</span></span> <span data-ttu-id="ae130-143">创建类时，可以继承自其他任何未定义为 [sealed](../../../csharp/language-reference/keywords/sealed.md) 的接口或类，而且其他类也可以继承自你的类并重写类虚方法。</span><span class="sxs-lookup"><span data-stu-id="ae130-143">When you create a class, you can inherit from any other interface or class that is not defined as [sealed](../../../csharp/language-reference/keywords/sealed.md), and other classes can inherit from your class and override class virtual methods.</span></span>

 <span data-ttu-id="ae130-144">继承是通过使用*派生*来完成的，这意味着类是通过使用其数据和行为所派生自的*基类*来声明的。</span><span class="sxs-lookup"><span data-stu-id="ae130-144">Inheritance is accomplished by using a *derivation*, which means a class is declared by using a *base class* from which it inherits data and behavior.</span></span> <span data-ttu-id="ae130-145">基类通过在派生的类名称后面追加冒号和基类名称来指定，如：</span><span class="sxs-lookup"><span data-stu-id="ae130-145">A base class is specified by appending a colon and the name of the base class following the derived class name, like this:</span></span>  

 ```csharp
 public class Manager : Employee
 {
     // Employee fields, properties, methods and events are inherited
     // New Manager fields, properties, methods and events go here...
 }
 ```
  
 <span data-ttu-id="ae130-146">类声明基类时，会继承基类除构造函数外的所有成员。</span><span class="sxs-lookup"><span data-stu-id="ae130-146">When a class declares a base class, it inherits all the members of the base class except the constructors.</span></span> <span data-ttu-id="ae130-147">有关详细信息，请参阅[继承](../../../csharp/programming-guide/classes-and-structs/inheritance.md)。</span><span class="sxs-lookup"><span data-stu-id="ae130-147">For more information, see [Inheritance](../../../csharp/programming-guide/classes-and-structs/inheritance.md).</span></span>
  
 <span data-ttu-id="ae130-148">与 C++ 不同，C# 中的类只能直接从基类继承。</span><span class="sxs-lookup"><span data-stu-id="ae130-148">Unlike C++, a class in C# can only directly inherit from one base class.</span></span> <span data-ttu-id="ae130-149">但是，因为基类本身可能继承自其他类，因此类可能间接继承多个基类。</span><span class="sxs-lookup"><span data-stu-id="ae130-149">However, because a base class may itself inherit from another class, a class may indirectly inherit multiple base classes.</span></span> <span data-ttu-id="ae130-150">此外，类还可以直接实现多个接口。</span><span class="sxs-lookup"><span data-stu-id="ae130-150">Furthermore, a class can directly implement more than one interface.</span></span> <span data-ttu-id="ae130-151">有关详细信息，请参阅[接口](../../../csharp/programming-guide/interfaces/index.md)。</span><span class="sxs-lookup"><span data-stu-id="ae130-151">For more information, see [Interfaces](../../../csharp/programming-guide/interfaces/index.md).</span></span>  
  
 <span data-ttu-id="ae130-152">类可以声明为 [abstract](../../../csharp/language-reference/keywords/abstract.md)（抽象）。</span><span class="sxs-lookup"><span data-stu-id="ae130-152">A class can be declared [abstract](../../../csharp/language-reference/keywords/abstract.md).</span></span> <span data-ttu-id="ae130-153">抽象类包含抽象方法，抽象方法包含签名定义但不包含实现。</span><span class="sxs-lookup"><span data-stu-id="ae130-153">An abstract class contains abstract methods that have a signature definition but no implementation.</span></span> <span data-ttu-id="ae130-154">抽象类不能实例化。</span><span class="sxs-lookup"><span data-stu-id="ae130-154">Abstract classes cannot be instantiated.</span></span> <span data-ttu-id="ae130-155">只能通过可实现抽象方法的派生类来使用该类。</span><span class="sxs-lookup"><span data-stu-id="ae130-155">They can only be used through derived classes that implement the abstract methods.</span></span> <span data-ttu-id="ae130-156">与此相反，[sealed](../../../csharp/language-reference/keywords/sealed.md)（密封）类不允许其他类继承。</span><span class="sxs-lookup"><span data-stu-id="ae130-156">By contrast, a [sealed](../../../csharp/language-reference/keywords/sealed.md) class does not allow other classes to derive from it.</span></span> <span data-ttu-id="ae130-157">有关详细信息，请参阅[抽象类、密封类和类成员](../../../csharp/programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md)。</span><span class="sxs-lookup"><span data-stu-id="ae130-157">For more information, see [Abstract and Sealed Classes and Class Members](../../../csharp/programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md).</span></span>  
  
 <span data-ttu-id="ae130-158">类定义可以在不同的源文件之间分割。</span><span class="sxs-lookup"><span data-stu-id="ae130-158">Class definitions can be split between different source files.</span></span> <span data-ttu-id="ae130-159">有关详细信息，请参阅[分部类和方法](../../../csharp/programming-guide/classes-and-structs/partial-classes-and-methods.md)。</span><span class="sxs-lookup"><span data-stu-id="ae130-159">For more information, see [Partial Classes and Methods](../../../csharp/programming-guide/classes-and-structs/partial-classes-and-methods.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ae130-160">示例</span><span class="sxs-lookup"><span data-stu-id="ae130-160">Example</span></span>  
 <span data-ttu-id="ae130-161">以下示例定义了一个公共类，该类包含一个[自动实现的属性](auto-implemented-properties.md)、一个方法和一个名为构造函数的特殊方法。</span><span class="sxs-lookup"><span data-stu-id="ae130-161">The following example defines a public class that contains an [auto-implemented property](auto-implemented-properties.md), a method, and a special method called a constructor.</span></span> <span data-ttu-id="ae130-162">有关详细信息，请参阅[属性](properties.md)、[方法](methods.md)和[构造函数](constructors.md)主题。</span><span class="sxs-lookup"><span data-stu-id="ae130-162">For more information, see [Properties](properties.md), [Methods](methods.md), and [Constructors](constructors.md) topics.</span></span> <span data-ttu-id="ae130-163">然后使用 `new` 关键字实例化类的实例。</span><span class="sxs-lookup"><span data-stu-id="ae130-163">The instances of the class are then instantiated with the `new` keyword.</span></span>  
  
 [!code-csharp[Class Example](~/samples/snippets/csharp/programming-guide/classes-and-structs/class-example.cs)] 
  
## <a name="c-language-specification"></a><span data-ttu-id="ae130-164">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="ae130-164">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="ae130-165">请参阅</span><span class="sxs-lookup"><span data-stu-id="ae130-165">See Also</span></span>  
 [<span data-ttu-id="ae130-166">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="ae130-166">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="ae130-167">面向对象的编程</span><span class="sxs-lookup"><span data-stu-id="ae130-167">Object-Oriented Programming</span></span>](../concepts/object-oriented-programming.md)  
 [<span data-ttu-id="ae130-168">多态性</span><span class="sxs-lookup"><span data-stu-id="ae130-168">Polymorphism</span></span>](../../../csharp/programming-guide/classes-and-structs/polymorphism.md)  
 [<span data-ttu-id="ae130-169">成员</span><span class="sxs-lookup"><span data-stu-id="ae130-169">Members</span></span>](../../../csharp/programming-guide/classes-and-structs/members.md)  
 [<span data-ttu-id="ae130-170">方法</span><span class="sxs-lookup"><span data-stu-id="ae130-170">Methods</span></span>](../../../csharp/programming-guide/classes-and-structs/methods.md)  
 [<span data-ttu-id="ae130-171">构造函数</span><span class="sxs-lookup"><span data-stu-id="ae130-171">Constructors</span></span>](../../../csharp/programming-guide/classes-and-structs/constructors.md)  
 [<span data-ttu-id="ae130-172">终结器</span><span class="sxs-lookup"><span data-stu-id="ae130-172">Finalizers</span></span>](../../../csharp/programming-guide/classes-and-structs/destructors.md)  
 [<span data-ttu-id="ae130-173">对象</span><span class="sxs-lookup"><span data-stu-id="ae130-173">Objects</span></span>](../../../csharp/programming-guide/classes-and-structs/objects.md)
