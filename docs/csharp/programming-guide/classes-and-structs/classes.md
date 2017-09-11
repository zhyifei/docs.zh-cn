---
title: "类（C# 编程指南）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- classes [C#]
- C# language, classes
ms.assetid: e8848524-7273-429f-8aba-c658d5eff5ad
caps.latest.revision: 40
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: eedb087f177b1bff6f4d4177cd56ac4cca016490
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="classes-c-programming-guide"></a><span data-ttu-id="5cbc7-102">类（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="5cbc7-102">Classes (C# Programming Guide)</span></span>
<span data-ttu-id="5cbc7-103">*类*属于构造，使用类，可以通过组合其他类型的变量、方法和事件创建自己的自定义类型。</span><span class="sxs-lookup"><span data-stu-id="5cbc7-103">A *class* is a construct that enables you to create your own custom types by grouping together variables of other types, methods and events.</span></span> <span data-ttu-id="5cbc7-104">类好比是蓝图。</span><span class="sxs-lookup"><span data-stu-id="5cbc7-104">A class is like a blueprint.</span></span> <span data-ttu-id="5cbc7-105">它定义类型的数据和行为。</span><span class="sxs-lookup"><span data-stu-id="5cbc7-105">It defines the data and behavior of a type.</span></span> <span data-ttu-id="5cbc7-106">如果类未声明为静态，客户端代码就可以通过创建分配给变量的*对象*或*实例*来使用该类。</span><span class="sxs-lookup"><span data-stu-id="5cbc7-106">If the class is not declared as static, client code can use it by creating *objects* or *instances* which are assigned to a variable.</span></span> <span data-ttu-id="5cbc7-107">变量会一直保留在内存中，直至对变量的所有引用超出范围为止。</span><span class="sxs-lookup"><span data-stu-id="5cbc7-107">The variable remains in memory until all references to it go out of scope.</span></span> <span data-ttu-id="5cbc7-108">超出范围时，CLR 将对其进行标记，以便用于垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="5cbc7-108">At that time, the CLR marks it as eligible for garbage collection.</span></span> <span data-ttu-id="5cbc7-109">如果类声明为[静态](../../../csharp/language-reference/keywords/static.md)，则内存中只有一个副本，且客户端代码只能通过类本身，而不是*实例变量*来访问它。</span><span class="sxs-lookup"><span data-stu-id="5cbc7-109">If the class is declared as [static](../../../csharp/language-reference/keywords/static.md), then only one copy exists in memory and client code can only access it through the class itself, not an *instance variable*.</span></span> <span data-ttu-id="5cbc7-110">有关详细信息，请参阅[静态类和静态类成员](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md)。</span><span class="sxs-lookup"><span data-stu-id="5cbc7-110">For more information, see [Static Classes and Static Class Members](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md).</span></span>  
  
 <span data-ttu-id="5cbc7-111">与结构不同，类支持*继承*，这是面向对象的编程的一个基本特点。</span><span class="sxs-lookup"><span data-stu-id="5cbc7-111">Unlike structs, classes support *inheritance*, a fundamental characteristic of object-oriented programming.</span></span> <span data-ttu-id="5cbc7-112">有关详细信息，请参阅[继承](../../../csharp/programming-guide/classes-and-structs/inheritance.md)。</span><span class="sxs-lookup"><span data-stu-id="5cbc7-112">For more information, see [Inheritance](../../../csharp/programming-guide/classes-and-structs/inheritance.md).</span></span>  
  
## <a name="declaring-classes"></a><span data-ttu-id="5cbc7-113">声明类</span><span class="sxs-lookup"><span data-stu-id="5cbc7-113">Declaring Classes</span></span>  
 <span data-ttu-id="5cbc7-114">使用 [class](../../../csharp/language-reference/keywords/class.md) 关键字可以声明类，如下例所示：</span><span class="sxs-lookup"><span data-stu-id="5cbc7-114">Classes are declared by using the [class](../../../csharp/language-reference/keywords/class.md) keyword, as shown in the following example:</span></span>  
  
 <span data-ttu-id="5cbc7-115">[!code-cs[csProgGuideObjects#79](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/classes_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="5cbc7-115">[!code-cs[csProgGuideObjects#79](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/classes_1.cs)]</span></span>  
  
 <span data-ttu-id="5cbc7-116">`class` 关键字前面是访问级别。</span><span class="sxs-lookup"><span data-stu-id="5cbc7-116">The `class` keyword is preceded by the access level.</span></span> <span data-ttu-id="5cbc7-117">由于在此例中使用 [public](../../../csharp/language-reference/keywords/public.md)，因此任何人都可以从此类创建对象。</span><span class="sxs-lookup"><span data-stu-id="5cbc7-117">Because [public](../../../csharp/language-reference/keywords/public.md) is used in this case, anyone can create objects from this class.</span></span> <span data-ttu-id="5cbc7-118">类的名称遵循 `class` 关键字。</span><span class="sxs-lookup"><span data-stu-id="5cbc7-118">The name of the class follows the `class` keyword.</span></span> <span data-ttu-id="5cbc7-119">定义的其余部分是类的主体，其中定义了行为和数据。</span><span class="sxs-lookup"><span data-stu-id="5cbc7-119">The remainder of the definition is the class body, where the behavior and data are defined.</span></span> <span data-ttu-id="5cbc7-120">类上的字段、属性、方法和事件统称为*类成员*。</span><span class="sxs-lookup"><span data-stu-id="5cbc7-120">Fields, properties, methods, and events on a class are collectively referred to as *class members*.</span></span>  
  
## <a name="creating-objects"></a><span data-ttu-id="5cbc7-121">创建对象</span><span class="sxs-lookup"><span data-stu-id="5cbc7-121">Creating Objects</span></span>  
 <span data-ttu-id="5cbc7-122">虽然它们有时可以互换使用，但类和对象是不同的概念。</span><span class="sxs-lookup"><span data-stu-id="5cbc7-122">Although they are sometimes used interchangeably, a class and an object are different things.</span></span> <span data-ttu-id="5cbc7-123">类定义对象类型，但不是对象本身。</span><span class="sxs-lookup"><span data-stu-id="5cbc7-123">A class defines a type of object, but it is not an object itself.</span></span> <span data-ttu-id="5cbc7-124">对象是基于类的具体实体，有时称为类的实例。</span><span class="sxs-lookup"><span data-stu-id="5cbc7-124">An object is a concrete entity based on a class, and is sometimes referred to as an instance of a class.</span></span>  
  
 <span data-ttu-id="5cbc7-125">可通过使用 [new](../../../csharp/language-reference/keywords/new.md) 关键字，后跟对象要基于的类的名称，来创建对象，如：</span><span class="sxs-lookup"><span data-stu-id="5cbc7-125">Objects can be created by using the [new](../../../csharp/language-reference/keywords/new.md) keyword followed by the name of the class that the object will be based on, like this:</span></span>  
  
 <span data-ttu-id="5cbc7-126">[!code-cs[csProgGuideObjects#80](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/classes_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="5cbc7-126">[!code-cs[csProgGuideObjects#80](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/classes_2.cs)]</span></span>  
  
 <span data-ttu-id="5cbc7-127">创建类的实例后，会将一个该对象的引用传递回程序员。</span><span class="sxs-lookup"><span data-stu-id="5cbc7-127">When an instance of a class is created, a reference to the object is passed back to the programmer.</span></span> <span data-ttu-id="5cbc7-128">在上一示例中，`object1` 是对基于 `Customer` 的对象的引用。</span><span class="sxs-lookup"><span data-stu-id="5cbc7-128">In the previous example, `object1` is a reference to an object that is based on `Customer`.</span></span> <span data-ttu-id="5cbc7-129">该引用指向新对象，但不包含对象数据本身。</span><span class="sxs-lookup"><span data-stu-id="5cbc7-129">This reference refers to the new object but does not contain the object data itself.</span></span> <span data-ttu-id="5cbc7-130">事实上，可以创建对象引用，而完全无需创建对象本身：</span><span class="sxs-lookup"><span data-stu-id="5cbc7-130">In fact, you can create an object reference without creating an object at all:</span></span>  
  
 <span data-ttu-id="5cbc7-131">[!code-cs[csProgGuideObjects#81](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/classes_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="5cbc7-131">[!code-cs[csProgGuideObjects#81](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/classes_3.cs)]</span></span>  
  
 <span data-ttu-id="5cbc7-132">不建议创建这样一个不引用对象的对象引用，因为尝试通过这类引用访问对象会在运行时失败。</span><span class="sxs-lookup"><span data-stu-id="5cbc7-132">We don't recommend creating object references such as this one that don't refer to an object because trying to access an object through such a reference will fail at run time.</span></span> <span data-ttu-id="5cbc7-133">但实际上可以使用这类引用来引用某个对象，方法是创建新对象，或者将其分配给现有对象，例如：</span><span class="sxs-lookup"><span data-stu-id="5cbc7-133">However, such a reference can be made to refer to an object, either by creating a new object, or by assigning it to an existing object, such as this:</span></span>  
  
 <span data-ttu-id="5cbc7-134">[!code-cs[csProgGuideObjects#82](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/classes_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="5cbc7-134">[!code-cs[csProgGuideObjects#82](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/classes_4.cs)]</span></span>  
  
 <span data-ttu-id="5cbc7-135">此代码创建指向同一对象的两个对象引用。</span><span class="sxs-lookup"><span data-stu-id="5cbc7-135">This code creates two object references that both refer to the same object.</span></span> <span data-ttu-id="5cbc7-136">因此，通过 `object3` 对对象所做的任何更改都将在以后使用 `object4` 时反映出来。</span><span class="sxs-lookup"><span data-stu-id="5cbc7-136">Therefore, any changes to the object made through `object3` will be reflected in subsequent uses of `object4`.</span></span> <span data-ttu-id="5cbc7-137">由于基于类的对象是通过引用来实现其引用的，因此类被称为引用类型。</span><span class="sxs-lookup"><span data-stu-id="5cbc7-137">Because objects that are based on classes are referred to by reference, classes are known as reference types.</span></span>  
  
## <a name="class-inheritance"></a><span data-ttu-id="5cbc7-138">类继承</span><span class="sxs-lookup"><span data-stu-id="5cbc7-138">Class Inheritance</span></span>  
 <span data-ttu-id="5cbc7-139">继承是通过使用*派生*来完成的，这意味着类是通过使用其数据和行为所派生自的*基类*来声明的。</span><span class="sxs-lookup"><span data-stu-id="5cbc7-139">Inheritance is accomplished by using a *derivation*, which means a class is declared by using a *base class* from which it inherits data and behavior.</span></span> <span data-ttu-id="5cbc7-140">基类通过在派生的类名称后面追加冒号和基类名称来指定，如：</span><span class="sxs-lookup"><span data-stu-id="5cbc7-140">A base class is specified by appending a colon and the name of the base class following the derived class name, like this:</span></span>  
  
 <span data-ttu-id="5cbc7-141">[!code-cs[csProgGuideObjects#83](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/classes_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="5cbc7-141">[!code-cs[csProgGuideObjects#83](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/classes_5.cs)]</span></span>  
  
 <span data-ttu-id="5cbc7-142">类声明基类时，会继承基类除构造函数外的所有成员。</span><span class="sxs-lookup"><span data-stu-id="5cbc7-142">When a class declares a base class, it inherits all the members of the base class except the constructors.</span></span>  
  
 <span data-ttu-id="5cbc7-143">与 C++ 不同，C# 中的类只能直接从基类继承。</span><span class="sxs-lookup"><span data-stu-id="5cbc7-143">Unlike C++, a class in C# can only directly inherit from one base class.</span></span> <span data-ttu-id="5cbc7-144">但是，因为基类本身可能继承自其他类，因此类可能间接继承多个基类。</span><span class="sxs-lookup"><span data-stu-id="5cbc7-144">However, because a base class may itself inherit from another class, a class may indirectly inherit multiple base classes.</span></span> <span data-ttu-id="5cbc7-145">此外，类还可以直接实现多个接口。</span><span class="sxs-lookup"><span data-stu-id="5cbc7-145">Furthermore, a class can directly implement more than one interface.</span></span> <span data-ttu-id="5cbc7-146">有关详细信息，请参阅[接口](../../../csharp/programming-guide/interfaces/index.md)。</span><span class="sxs-lookup"><span data-stu-id="5cbc7-146">For more information, see [Interfaces](../../../csharp/programming-guide/interfaces/index.md).</span></span>  
  
 <span data-ttu-id="5cbc7-147">类可以声明为 [abstract](../../../csharp/language-reference/keywords/abstract.md)（抽象）。</span><span class="sxs-lookup"><span data-stu-id="5cbc7-147">A class can be declared [abstract](../../../csharp/language-reference/keywords/abstract.md).</span></span> <span data-ttu-id="5cbc7-148">抽象类包含抽象方法，抽象方法包含签名定义但不包含实现。</span><span class="sxs-lookup"><span data-stu-id="5cbc7-148">An abstract class contains abstract methods that have a signature definition but no implementation.</span></span> <span data-ttu-id="5cbc7-149">抽象类不能实例化。</span><span class="sxs-lookup"><span data-stu-id="5cbc7-149">Abstract classes cannot be instantiated.</span></span> <span data-ttu-id="5cbc7-150">只能通过可实现抽象方法的派生类来使用该类。</span><span class="sxs-lookup"><span data-stu-id="5cbc7-150">They can only be used through derived classes that implement the abstract methods.</span></span> <span data-ttu-id="5cbc7-151">与此相反，[sealed](../../../csharp/language-reference/keywords/sealed.md)（密封）类不允许其他类继承。</span><span class="sxs-lookup"><span data-stu-id="5cbc7-151">By contrast, a [sealed](../../../csharp/language-reference/keywords/sealed.md) class does not allow other classes to derive from it.</span></span> <span data-ttu-id="5cbc7-152">有关详细信息，请参阅[抽象类、密封类及类成员](../../../csharp/programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md)。</span><span class="sxs-lookup"><span data-stu-id="5cbc7-152">For more information, see [Abstract and Sealed Classes and Class Members](../../../csharp/programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md).</span></span>  
  
 <span data-ttu-id="5cbc7-153">类定义可以在不同的源文件之间分割。</span><span class="sxs-lookup"><span data-stu-id="5cbc7-153">Class definitions can be split between different source files.</span></span> <span data-ttu-id="5cbc7-154">有关详细信息，请参阅[分部类和方法](../../../csharp/programming-guide/classes-and-structs/partial-classes-and-methods.md)。</span><span class="sxs-lookup"><span data-stu-id="5cbc7-154">For more information, see [Partial Classes and Methods](../../../csharp/programming-guide/classes-and-structs/partial-classes-and-methods.md).</span></span>  
  
## <a name="description"></a><span data-ttu-id="5cbc7-155">描述</span><span class="sxs-lookup"><span data-stu-id="5cbc7-155">Description</span></span>  
 <span data-ttu-id="5cbc7-156">下例定义了一个公共类，该类包含一个字段、一个方法和一个名为构造函数的特殊方法。</span><span class="sxs-lookup"><span data-stu-id="5cbc7-156">In the following example, a public class that contains a single field, a method, and a special method called a constructor is defined.</span></span> <span data-ttu-id="5cbc7-157">有关详细信息，请参阅[构造函数](../../../csharp/programming-guide/classes-and-structs/constructors.md)。</span><span class="sxs-lookup"><span data-stu-id="5cbc7-157">For more information, see [Constructors](../../../csharp/programming-guide/classes-and-structs/constructors.md).</span></span> <span data-ttu-id="5cbc7-158">然后使用 `new` 关键字实例化该类。</span><span class="sxs-lookup"><span data-stu-id="5cbc7-158">The class is then instantiated with the `new` keyword.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5cbc7-159">示例</span><span class="sxs-lookup"><span data-stu-id="5cbc7-159">Example</span></span>  
 <span data-ttu-id="5cbc7-160">[!code-cs[csProgGuideObjects#84](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/classes_6.cs)]</span><span class="sxs-lookup"><span data-stu-id="5cbc7-160">[!code-cs[csProgGuideObjects#84](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/classes_6.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="5cbc7-161">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="5cbc7-161">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="5cbc7-162">请参阅</span><span class="sxs-lookup"><span data-stu-id="5cbc7-162">See Also</span></span>  
 <span data-ttu-id="5cbc7-163">[C# 编程指南](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="5cbc7-163">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="5cbc7-164">[面向对象的编程](../concepts/object-oriented-programming.md) </span><span class="sxs-lookup"><span data-stu-id="5cbc7-164">[Object-Oriented Programming](../concepts/object-oriented-programming.md) </span></span>  
 <span data-ttu-id="5cbc7-165">[多形性](../../../csharp/programming-guide/classes-and-structs/polymorphism.md) </span><span class="sxs-lookup"><span data-stu-id="5cbc7-165">[Polymorphism](../../../csharp/programming-guide/classes-and-structs/polymorphism.md) </span></span>  
 <span data-ttu-id="5cbc7-166">[成员](../../../csharp/programming-guide/classes-and-structs/members.md) </span><span class="sxs-lookup"><span data-stu-id="5cbc7-166">[Members](../../../csharp/programming-guide/classes-and-structs/members.md) </span></span>  
 <span data-ttu-id="5cbc7-167">[方法](../../../csharp/programming-guide/classes-and-structs/methods.md) </span><span class="sxs-lookup"><span data-stu-id="5cbc7-167">[Methods](../../../csharp/programming-guide/classes-and-structs/methods.md) </span></span>  
 <span data-ttu-id="5cbc7-168">[构造函数](../../../csharp/programming-guide/classes-and-structs/constructors.md) </span><span class="sxs-lookup"><span data-stu-id="5cbc7-168">[Constructors](../../../csharp/programming-guide/classes-and-structs/constructors.md) </span></span>  
 <span data-ttu-id="5cbc7-169">[终结器](../../../csharp/programming-guide/classes-and-structs/destructors.md) </span><span class="sxs-lookup"><span data-stu-id="5cbc7-169">[Finalizers](../../../csharp/programming-guide/classes-and-structs/destructors.md) </span></span>  
 [<span data-ttu-id="5cbc7-170">对象</span><span class="sxs-lookup"><span data-stu-id="5cbc7-170">Objects</span></span>](../../../csharp/programming-guide/classes-and-structs/objects.md)

