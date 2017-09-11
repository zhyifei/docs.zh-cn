---
title: "接口（C# 编程指南）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- interfaces [C#]
- C# language, interfaces
ms.assetid: 2feda177-ce11-432d-81b4-d50f5f35fd37
caps.latest.revision: 45
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
ms.openlocfilehash: 0552cea71f66ba8c299b1706cab6778c9e3367c9
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="interfaces-c-programming-guide"></a><span data-ttu-id="519ed-102">接口（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="519ed-102">Interfaces (C# Programming Guide)</span></span>
<span data-ttu-id="519ed-103">接口包含[类](../../../csharp/language-reference/keywords/class.md)或[结构](../../../csharp/language-reference/keywords/struct.md)可以实现的一组相关功能的定义。</span><span class="sxs-lookup"><span data-stu-id="519ed-103">An interface contains definitions for a group of related functionalities that a [class](../../../csharp/language-reference/keywords/class.md) or a [struct](../../../csharp/language-reference/keywords/struct.md) can implement.</span></span>  
  
 <span data-ttu-id="519ed-104">例如，使用接口可以在类中包括来自多个源的行为。</span><span class="sxs-lookup"><span data-stu-id="519ed-104">By using interfaces, you can, for example, include behavior from multiple sources in a class.</span></span> <span data-ttu-id="519ed-105">该功能在 C# 中十分重要，因为该语言不支持类的多重继承。</span><span class="sxs-lookup"><span data-stu-id="519ed-105">That capability is important in C# because the language doesn't support multiple inheritance of classes.</span></span> <span data-ttu-id="519ed-106">此外，如果要模拟结构的继承，也必须使用接口，因为它们无法实际从另一个结构或类继承。</span><span class="sxs-lookup"><span data-stu-id="519ed-106">In addition, you must use an interface if you want to simulate inheritance for structs, because they can't actually inherit from another struct or class.</span></span>  
  
 <span data-ttu-id="519ed-107">可使用 [interface](../../../csharp/language-reference/keywords/interface.md) 关键字定义接口，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="519ed-107">You define an interface by using the [interface](../../../csharp/language-reference/keywords/interface.md) keyword, as the following example shows.</span></span>  
  
 <span data-ttu-id="519ed-108">[!code-cs[csProgGuideInheritance#47](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/interfaces_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="519ed-108">[!code-cs[csProgGuideInheritance#47](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/interfaces_1.cs)]</span></span>  
  
 <span data-ttu-id="519ed-109">实现 <xref:System.IEquatable%601> 接口的任何类或结构都必须包含与该接口指定的签名匹配的 <xref:System.IEquatable%601.Equals%2A> 方法的定义。</span><span class="sxs-lookup"><span data-stu-id="519ed-109">Any class or struct that implements the <xref:System.IEquatable%601> interface must contain a definition for an <xref:System.IEquatable%601.Equals%2A> method that matches the signature that the interface specifies.</span></span> <span data-ttu-id="519ed-110">因此，可以依靠实现 `IEquatable<T>` 的类来包含 `Equals` 方法，类的实例可以通过该方法确定它是否等于相同类的另一个实例。</span><span class="sxs-lookup"><span data-stu-id="519ed-110">As a result, you can count on a class that implements `IEquatable<T>` to contain an `Equals` method with which an instance of the class can determine whether it's equal to another instance of the same class.</span></span>  
  
 <span data-ttu-id="519ed-111">`IEquatable<T>` 的定义不为 `Equals` 提供实现。</span><span class="sxs-lookup"><span data-stu-id="519ed-111">The definition of `IEquatable<T>` doesn’t provide an implementation for `Equals`.</span></span> <span data-ttu-id="519ed-112">该接口仅定义签名。</span><span class="sxs-lookup"><span data-stu-id="519ed-112">The interface defines only the signature.</span></span> <span data-ttu-id="519ed-113">这样，C# 中的接口便类似于其中所有方法都是抽象方法的抽象类。</span><span class="sxs-lookup"><span data-stu-id="519ed-113">In that way, an interface in C# is similar to an abstract class in which all the methods are abstract.</span></span> <span data-ttu-id="519ed-114">但是，类或结构可以实现多个接口，但是类只能继承单个类（抽象或不抽象）。</span><span class="sxs-lookup"><span data-stu-id="519ed-114">However, a class or struct can implement multiple interfaces, but a class can inherit only a single class, abstract or not.</span></span> <span data-ttu-id="519ed-115">因此，使用接口可以在类中包括来自多个源的行为。</span><span class="sxs-lookup"><span data-stu-id="519ed-115">Therefore, by using interfaces, you can include behavior from multiple sources in a class.</span></span>  
  
 <span data-ttu-id="519ed-116">有关抽象类的详细信息，请参阅[抽象类、密封类及类成员](../../../csharp/programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md)。</span><span class="sxs-lookup"><span data-stu-id="519ed-116">For more information about abstract classes, see [Abstract and Sealed Classes and Class Members](../../../csharp/programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md).</span></span>  
  
 <span data-ttu-id="519ed-117">接口可以包含方法、属性、事件、索引器或这四种成员类型的任意组合。</span><span class="sxs-lookup"><span data-stu-id="519ed-117">Interfaces can contain methods, properties, events, indexers, or any combination of those four member types.</span></span> <span data-ttu-id="519ed-118">有关示例的链接，请参阅[相关部分](../../../csharp/programming-guide/interfaces/index.md#BKMK_RelatedSections)。</span><span class="sxs-lookup"><span data-stu-id="519ed-118">For links to examples, see [Related Sections](../../../csharp/programming-guide/interfaces/index.md#BKMK_RelatedSections).</span></span> <span data-ttu-id="519ed-119">接口不能包含常量、字段、运算符、实例构造函数、终结器或类型。</span><span class="sxs-lookup"><span data-stu-id="519ed-119">An interface can't contain constants, fields, operators, instance constructors, finalizers, or types.</span></span> <span data-ttu-id="519ed-120">接口成员会自动成为公共成员，不能包含任何访问修饰符。</span><span class="sxs-lookup"><span data-stu-id="519ed-120">Interface members are automatically public, and they can't include any access modifiers.</span></span> <span data-ttu-id="519ed-121">成员也不能是[静态](../../../csharp/language-reference/keywords/static.md)成员。</span><span class="sxs-lookup"><span data-stu-id="519ed-121">Members also can't be [static](../../../csharp/language-reference/keywords/static.md).</span></span>  
  
 <span data-ttu-id="519ed-122">若要实现接口成员，实现类的对应成员必须是公共、非静态，并且具有与接口成员相同的名称和签名。</span><span class="sxs-lookup"><span data-stu-id="519ed-122">To implement an interface member, the corresponding member of the implementing class must be public, non-static, and have the same name and signature as the interface member.</span></span>  
  
 <span data-ttu-id="519ed-123">当类或结构实现接口时，类或结构必须为该接口定义的所有成员提供实现。</span><span class="sxs-lookup"><span data-stu-id="519ed-123">When a class or struct implements an interface, the class or struct must provide an implementation for all of the members that the interface defines.</span></span> <span data-ttu-id="519ed-124">接口本身不提供类或结构可以通过继承基类功能的方式来继承的任何功能。</span><span class="sxs-lookup"><span data-stu-id="519ed-124">The interface itself provides no functionality that a class or struct can inherit in the way that it can inherit base class functionality.</span></span> <span data-ttu-id="519ed-125">但是，如果基类实现接口，则从基类派生的任何类都会继承该实现。</span><span class="sxs-lookup"><span data-stu-id="519ed-125">However, if a base class implements an interface, any class that's derived from the base class inherits that implementation.</span></span>  
  
 <span data-ttu-id="519ed-126">下面的示例展示了 IEquatable<T\> 接口的实现代码。</span><span class="sxs-lookup"><span data-stu-id="519ed-126">The following example shows an implementation of the IEquatable<T\> interface.</span></span> <span data-ttu-id="519ed-127">实现类 `Car` 必须提供 <xref:System.IEquatable%601.Equals%2A> 方法的实现。</span><span class="sxs-lookup"><span data-stu-id="519ed-127">The implementing class, `Car`, must provide an implementation of the <xref:System.IEquatable%601.Equals%2A> method.</span></span>  
  
 <span data-ttu-id="519ed-128">[!code-cs[csProgGuideInheritance#48](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/interfaces_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="519ed-128">[!code-cs[csProgGuideInheritance#48](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/interfaces_2.cs)]</span></span>  
  
 <span data-ttu-id="519ed-129">类的属性和索引器可以为接口中定义的属性或索引器定义额外的访问器。</span><span class="sxs-lookup"><span data-stu-id="519ed-129">Properties and indexers of a class can define extra accessors for a property or indexer that's defined in an interface.</span></span> <span data-ttu-id="519ed-130">例如，接口可能会声明包含 [get](../../../csharp/language-reference/keywords/get.md) 取值函数的属性。</span><span class="sxs-lookup"><span data-stu-id="519ed-130">For example, an interface might declare a property that has a [get](../../../csharp/language-reference/keywords/get.md) accessor.</span></span> <span data-ttu-id="519ed-131">实现此接口的类可以声明包含 `get` 和 [set](../../../csharp/language-reference/keywords/set.md) 取值函数的同一属性。</span><span class="sxs-lookup"><span data-stu-id="519ed-131">The class that implements the interface can declare the same property with both a `get` and [set](../../../csharp/language-reference/keywords/set.md) accessor.</span></span> <span data-ttu-id="519ed-132">但是，如果属性或索引器使用显式实现，则访问器必须匹配。</span><span class="sxs-lookup"><span data-stu-id="519ed-132">However, if the property or indexer uses explicit implementation, the accessors must match.</span></span> <span data-ttu-id="519ed-133">有关显式实现的详细信息，请参阅[显式接口实现](../../../csharp/programming-guide/interfaces/explicit-interface-implementation.md)和[接口属性](../../../csharp/programming-guide/classes-and-structs/interface-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="519ed-133">For more information about explicit implementation, see [Explicit Interface Implementation](../../../csharp/programming-guide/interfaces/explicit-interface-implementation.md) and [Interface Properties](../../../csharp/programming-guide/classes-and-structs/interface-properties.md).</span></span>  
  
 <span data-ttu-id="519ed-134">接口可以实现其他接口。</span><span class="sxs-lookup"><span data-stu-id="519ed-134">Interfaces can implement other interfaces.</span></span> <span data-ttu-id="519ed-135">类可能通过它继承的基类或通过其他接口实现的接口来多次包含某个接口。</span><span class="sxs-lookup"><span data-stu-id="519ed-135">A class might include an interface multiple times through base classes that it inherits or through interfaces that other interfaces implement.</span></span> <span data-ttu-id="519ed-136">但是，类只能提供接口的实现一次，并且仅当类将接口作为类定义的一部分 (`class ClassName : InterfaceName`) 进行声明时才能提供。</span><span class="sxs-lookup"><span data-stu-id="519ed-136">However, the class can provide an implementation of an interface only one time and only if the class declares the interface as part of the definition of the class (`class ClassName : InterfaceName`).</span></span> <span data-ttu-id="519ed-137">如果由于继承实现接口的基类而继承了接口，则基类会提供接口的成员的实现。</span><span class="sxs-lookup"><span data-stu-id="519ed-137">If the interface is inherited because you inherited a base class that implements the interface, the base class provides the implementation of the members of the interface.</span></span> <span data-ttu-id="519ed-138">但是，派生类可以重新实现接口成员，而不是使用继承的实现。</span><span class="sxs-lookup"><span data-stu-id="519ed-138">However, the derived class can reimplement the interface members instead of using the inherited implementation.</span></span>  
  
 <span data-ttu-id="519ed-139">基类还可以使用虚拟成员实现接口成员。</span><span class="sxs-lookup"><span data-stu-id="519ed-139">A base class can also implement interface members by using virtual members.</span></span> <span data-ttu-id="519ed-140">在这种情况下，派生类可以通过重写虚拟成员来更改接口行为。</span><span class="sxs-lookup"><span data-stu-id="519ed-140">In that case, a derived class can change the interface behavior by overriding the virtual members.</span></span> <span data-ttu-id="519ed-141">有关虚拟成员的详细信息，请参阅[多形性](../../../csharp/programming-guide/classes-and-structs/polymorphism.md)。</span><span class="sxs-lookup"><span data-stu-id="519ed-141">For more information about virtual members, see [Polymorphism](../../../csharp/programming-guide/classes-and-structs/polymorphism.md).</span></span>  
  
## <a name="interfaces-summary"></a><span data-ttu-id="519ed-142">接口摘要</span><span class="sxs-lookup"><span data-stu-id="519ed-142">Interfaces Summary</span></span>  
 <span data-ttu-id="519ed-143">接口具有以下属性：</span><span class="sxs-lookup"><span data-stu-id="519ed-143">An interface has the following properties:</span></span>  
  
-   <span data-ttu-id="519ed-144">接口类似于抽象基类。</span><span class="sxs-lookup"><span data-stu-id="519ed-144">An interface is like an abstract base class.</span></span> <span data-ttu-id="519ed-145">实现接口的任何类或结构都必须实现其所有成员。</span><span class="sxs-lookup"><span data-stu-id="519ed-145">Any class or struct that implements the interface must implement all its members.</span></span>  
  
-   <span data-ttu-id="519ed-146">接口无法直接进行实例化。</span><span class="sxs-lookup"><span data-stu-id="519ed-146">An interface can't be instantiated directly.</span></span> <span data-ttu-id="519ed-147">其成员由实现接口的任何类或结构来实现。</span><span class="sxs-lookup"><span data-stu-id="519ed-147">Its members are implemented by any class or struct that implements the interface.</span></span>  
  
-   <span data-ttu-id="519ed-148">接口可以包含事件、索引器、方法和属性。</span><span class="sxs-lookup"><span data-stu-id="519ed-148">Interfaces can contain events, indexers, methods, and properties.</span></span>  
  
-   <span data-ttu-id="519ed-149">接口不包含方法的实现。</span><span class="sxs-lookup"><span data-stu-id="519ed-149">Interfaces contain no implementation of methods.</span></span>  
  
-   <span data-ttu-id="519ed-150">一个类或结构可以实现多个接口。</span><span class="sxs-lookup"><span data-stu-id="519ed-150">A class or struct can implement multiple interfaces.</span></span> <span data-ttu-id="519ed-151">一个类可以继承一个基类，还可实现一个或多个接口。</span><span class="sxs-lookup"><span data-stu-id="519ed-151">A class can inherit a base class and also implement one or more interfaces.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="519ed-152">本节内容</span><span class="sxs-lookup"><span data-stu-id="519ed-152">In This Section</span></span>  
 [<span data-ttu-id="519ed-153">显式接口实现</span><span class="sxs-lookup"><span data-stu-id="519ed-153">Explicit Interface Implementation</span></span>](../../../csharp/programming-guide/interfaces/explicit-interface-implementation.md)  
 <span data-ttu-id="519ed-154">说明如何创建特定于接口的类成员。</span><span class="sxs-lookup"><span data-stu-id="519ed-154">Explains how to create a class member that’s specific to an interface.</span></span>  
  
 [<span data-ttu-id="519ed-155">如何：显式实现接口成员</span><span class="sxs-lookup"><span data-stu-id="519ed-155">How to: Explicitly Implement Interface Members</span></span>](../../../csharp/programming-guide/interfaces/how-to-explicitly-implement-interface-members.md)  
 <span data-ttu-id="519ed-156">提供有关如何显式实现接口的成员的示例。</span><span class="sxs-lookup"><span data-stu-id="519ed-156">Provides an example of how to explicitly implement members of interfaces.</span></span>  
  
 [<span data-ttu-id="519ed-157">如何：显式实现两个接口的成员</span><span class="sxs-lookup"><span data-stu-id="519ed-157">How to: Explicitly Implement Members of Two Interfaces</span></span>](../../../csharp/programming-guide/interfaces/how-to-explicitly-implement-members-of-two-interfaces.md)  
 <span data-ttu-id="519ed-158">提供有关如何使用继承显式实现接口的成员的示例。</span><span class="sxs-lookup"><span data-stu-id="519ed-158">Provides an example of how to explicitly implement members of interfaces with inheritance.</span></span>  
  
##  <span data-ttu-id="519ed-159"><a name="BKMK_RelatedSections"></a>相关部分</span><span class="sxs-lookup"><span data-stu-id="519ed-159"><a name="BKMK_RelatedSections"></a> Related Sections</span></span>  
  
-   [<span data-ttu-id="519ed-160">接口属性</span><span class="sxs-lookup"><span data-stu-id="519ed-160">Interface Properties</span></span>](../../../csharp/programming-guide/classes-and-structs/interface-properties.md)  
  
-   [<span data-ttu-id="519ed-161">接口中的索引器</span><span class="sxs-lookup"><span data-stu-id="519ed-161">Indexers in Interfaces</span></span>](../../../csharp/programming-guide/indexers/indexers-in-interfaces.md)  
  
-   [<span data-ttu-id="519ed-162">如何：实现接口事件</span><span class="sxs-lookup"><span data-stu-id="519ed-162">How to:  Implement Interface Events</span></span>](../../../csharp/programming-guide/events/how-to-implement-interface-events.md)  
  
-   [<span data-ttu-id="519ed-163">类和结构</span><span class="sxs-lookup"><span data-stu-id="519ed-163">Classes and Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/index.md)  
  
-   [<span data-ttu-id="519ed-164">继承</span><span class="sxs-lookup"><span data-stu-id="519ed-164">Inheritance</span></span>](../../../csharp/programming-guide/classes-and-structs/inheritance.md)  
  
-   [<span data-ttu-id="519ed-165">方法</span><span class="sxs-lookup"><span data-stu-id="519ed-165">Methods</span></span>](../../../csharp/programming-guide/classes-and-structs/methods.md)  
  
-   [<span data-ttu-id="519ed-166">多态性</span><span class="sxs-lookup"><span data-stu-id="519ed-166">Polymorphism</span></span>](../../../csharp/programming-guide/classes-and-structs/polymorphism.md)  
  
-   [<span data-ttu-id="519ed-167">抽象类、密封类及类成员</span><span class="sxs-lookup"><span data-stu-id="519ed-167">Abstract and Sealed Classes and Class Members</span></span>](../../../csharp/programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md)  
  
-   [<span data-ttu-id="519ed-168">属性</span><span class="sxs-lookup"><span data-stu-id="519ed-168">Properties</span></span>](../../../csharp/programming-guide/classes-and-structs/properties.md)  
  
-   [<span data-ttu-id="519ed-169">事件</span><span class="sxs-lookup"><span data-stu-id="519ed-169">Events</span></span>](../../../csharp/programming-guide/events/index.md)  
  
-   [<span data-ttu-id="519ed-170">索引器</span><span class="sxs-lookup"><span data-stu-id="519ed-170">Indexers</span></span>](../../../csharp/programming-guide/indexers/index.md)  
  
## <a name="featured-book-chapter"></a><span data-ttu-id="519ed-171">重要章节</span><span class="sxs-lookup"><span data-stu-id="519ed-171">Featured Book Chapter</span></span>  
 <span data-ttu-id="519ed-172">[学习 C# 3.0：掌握 C# 3.0 的基础知识](http://msdn.microsoft.com/library/orm-9780596521066-01.aspx)中的[接口](http://msdn.microsoft.com/library/orm-9780596521066-01-13.aspx)</span><span class="sxs-lookup"><span data-stu-id="519ed-172">[Interfaces](http://msdn.microsoft.com/library/orm-9780596521066-01-13.aspx) in [Learning C# 3.0: Master the Fundamentals of C# 3.0](http://msdn.microsoft.com/library/orm-9780596521066-01.aspx)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="519ed-173">另请参阅</span><span class="sxs-lookup"><span data-stu-id="519ed-173">See Also</span></span>  
 <span data-ttu-id="519ed-174">[C# 编程指南](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="519ed-174">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="519ed-175">继承</span><span class="sxs-lookup"><span data-stu-id="519ed-175">Inheritance</span></span>](../../../csharp/programming-guide/classes-and-structs/inheritance.md)

