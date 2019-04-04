---
title: 接口 - C# 编程指南
ms.custom: seodec18
ms.date: 08/21/2018
helpviewer_keywords:
- interfaces [C#]
- C# language, interfaces
ms.assetid: 2feda177-ce11-432d-81b4-d50f5f35fd37
ms.openlocfilehash: 330e4e8b36f03b028786920422cd325b31d814e0
ms.sourcegitcommit: e994e47d3582bf09ae487ecbd53c0dac30aebaf7
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/20/2019
ms.locfileid: "58262413"
---
# <a name="interfaces-c-programming-guide"></a><span data-ttu-id="828b5-102">接口（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="828b5-102">Interfaces (C# Programming Guide)</span></span>

<span data-ttu-id="828b5-103">接口包含[类](../../language-reference/keywords/class.md)或[结构](../../language-reference/keywords/struct.md)可以实现的一组相关功能的定义。</span><span class="sxs-lookup"><span data-stu-id="828b5-103">An interface contains definitions for a group of related functionalities that a [class](../../language-reference/keywords/class.md) or a [struct](../../language-reference/keywords/struct.md) can implement.</span></span>
  
<span data-ttu-id="828b5-104">例如，使用接口可以在类中包括来自多个源的行为。</span><span class="sxs-lookup"><span data-stu-id="828b5-104">By using interfaces, you can, for example, include behavior from multiple sources in a class.</span></span> <span data-ttu-id="828b5-105">该功能在 C# 中十分重要，因为该语言不支持类的多重继承。</span><span class="sxs-lookup"><span data-stu-id="828b5-105">That capability is important in C# because the language doesn't support multiple inheritance of classes.</span></span> <span data-ttu-id="828b5-106">此外，如果要模拟结构的继承，也必须使用接口，因为它们无法实际从另一个结构或类继承。</span><span class="sxs-lookup"><span data-stu-id="828b5-106">In addition, you must use an interface if you want to simulate inheritance for structs, because they can't actually inherit from another struct or class.</span></span>  
  
<span data-ttu-id="828b5-107">可使用 [interface](../../language-reference/keywords/interface.md) 关键字定义接口。</span><span class="sxs-lookup"><span data-stu-id="828b5-107">You define an interface by using the [interface](../../language-reference/keywords/interface.md) keyword.</span></span> <span data-ttu-id="828b5-108">如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="828b5-108">as the following example shows.</span></span>  
  
 [!code-csharp[csProgGuideInheritance#47](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#47)]  

<span data-ttu-id="828b5-109">结构名称必须是有效的 C# [标识符名称](../inside-a-program/identifier-names.md)。</span><span class="sxs-lookup"><span data-stu-id="828b5-109">The name of the struct must be a valid C# [identifier name](../inside-a-program/identifier-names.md).</span></span> <span data-ttu-id="828b5-110">按照约定，接口名称以大写字母 `I` 开头。</span><span class="sxs-lookup"><span data-stu-id="828b5-110">By convention, interface names begin with a capital `I`.</span></span>

<span data-ttu-id="828b5-111">实现 <xref:System.IEquatable%601> 接口的任何类或结构都必须包含与该接口指定的签名匹配的 <xref:System.IEquatable%601.Equals%2A> 方法的定义。</span><span class="sxs-lookup"><span data-stu-id="828b5-111">Any class or struct that implements the <xref:System.IEquatable%601> interface must contain a definition for an <xref:System.IEquatable%601.Equals%2A> method that matches the signature that the interface specifies.</span></span> <span data-ttu-id="828b5-112">因此，可以依靠实现 `IEquatable<T>` 的类来包含 `Equals` 方法，类的实例可以通过该方法确定它是否等于相同类的另一个实例。</span><span class="sxs-lookup"><span data-stu-id="828b5-112">As a result, you can count on a class that implements `IEquatable<T>` to contain an `Equals` method with which an instance of the class can determine whether it's equal to another instance of the same class.</span></span>  
  
<span data-ttu-id="828b5-113">`IEquatable<T>` 的定义不为 `Equals` 提供实现。</span><span class="sxs-lookup"><span data-stu-id="828b5-113">The definition of `IEquatable<T>` doesn’t provide an implementation for `Equals`.</span></span> <span data-ttu-id="828b5-114">该接口仅定义签名。</span><span class="sxs-lookup"><span data-stu-id="828b5-114">The interface defines only the signature.</span></span> <span data-ttu-id="828b5-115">这样，C# 中的接口便类似于其中所有方法都是抽象方法的抽象类。</span><span class="sxs-lookup"><span data-stu-id="828b5-115">In that way, an interface in C# is similar to an abstract class in which all the methods are abstract.</span></span> <span data-ttu-id="828b5-116">但是，类或结构可以实现多个接口，但是类只能继承单个类（抽象或不抽象）。</span><span class="sxs-lookup"><span data-stu-id="828b5-116">However, a class or struct can implement multiple interfaces, but a class can inherit only a single class, abstract or not.</span></span>
  
<span data-ttu-id="828b5-117">有关抽象类的详细信息，请参阅[抽象类、密封类及类成员](../classes-and-structs/abstract-and-sealed-classes-and-class-members.md)。</span><span class="sxs-lookup"><span data-stu-id="828b5-117">For more information about abstract classes, see [Abstract and Sealed Classes and Class Members](../classes-and-structs/abstract-and-sealed-classes-and-class-members.md).</span></span>  
  
<span data-ttu-id="828b5-118">接口可以包含方法、属性、事件、索引器或这四种成员类型的任意组合。</span><span class="sxs-lookup"><span data-stu-id="828b5-118">Interfaces can contain methods, properties, events, indexers, or any combination of those four member types.</span></span> <span data-ttu-id="828b5-119">有关示例的链接，请参阅[相关部分](../interfaces/index.md#BKMK_RelatedSections)。</span><span class="sxs-lookup"><span data-stu-id="828b5-119">For links to examples, see [Related Sections](../interfaces/index.md#BKMK_RelatedSections).</span></span> <span data-ttu-id="828b5-120">接口不能包含常量、字段、运算符、实例构造函数、终结器或类型。</span><span class="sxs-lookup"><span data-stu-id="828b5-120">An interface can't contain constants, fields, operators, instance constructors, finalizers, or types.</span></span> <span data-ttu-id="828b5-121">接口成员会自动成为公共成员，不能包含任何访问修饰符。</span><span class="sxs-lookup"><span data-stu-id="828b5-121">Interface members are automatically public, and they can't include any access modifiers.</span></span> <span data-ttu-id="828b5-122">成员也不能是[静态](../../language-reference/keywords/static.md)成员。</span><span class="sxs-lookup"><span data-stu-id="828b5-122">Members also can't be [static](../../language-reference/keywords/static.md).</span></span>  
  
<span data-ttu-id="828b5-123">若要实现接口成员，实现类的对应成员必须是公共、非静态，并且具有与接口成员相同的名称和签名。</span><span class="sxs-lookup"><span data-stu-id="828b5-123">To implement an interface member, the corresponding member of the implementing class must be public, non-static, and have the same name and signature as the interface member.</span></span>  
  
<span data-ttu-id="828b5-124">当类或结构实现接口时，类或结构必须为该接口定义的所有成员提供实现。</span><span class="sxs-lookup"><span data-stu-id="828b5-124">When a class or struct implements an interface, the class or struct must provide an implementation for all of the members that the interface defines.</span></span> <span data-ttu-id="828b5-125">接口本身不提供类或结构可以通过继承基类功能的方式来继承的任何功能。</span><span class="sxs-lookup"><span data-stu-id="828b5-125">The interface itself provides no functionality that a class or struct can inherit in the way that it can inherit base class functionality.</span></span> <span data-ttu-id="828b5-126">但是，如果基类实现接口，则从基类派生的任何类都会继承该实现。</span><span class="sxs-lookup"><span data-stu-id="828b5-126">However, if a base class implements an interface, any class that's derived from the base class inherits that implementation.</span></span>  
  
<span data-ttu-id="828b5-127">下面的示例演示 <xref:System.IEquatable%601> 接口的实现。</span><span class="sxs-lookup"><span data-stu-id="828b5-127">The following example shows an implementation of the <xref:System.IEquatable%601> interface.</span></span> <span data-ttu-id="828b5-128">实现类 `Car` 必须提供 <xref:System.IEquatable%601.Equals%2A> 方法的实现。</span><span class="sxs-lookup"><span data-stu-id="828b5-128">The implementing class, `Car`, must provide an implementation of the <xref:System.IEquatable%601.Equals%2A> method.</span></span>  
  
 [!code-csharp[csProgGuideInheritance#48](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#48)]  
  
<span data-ttu-id="828b5-129">类的属性和索引器可以为接口中定义的属性或索引器定义额外的访问器。</span><span class="sxs-lookup"><span data-stu-id="828b5-129">Properties and indexers of a class can define extra accessors for a property or indexer that's defined in an interface.</span></span> <span data-ttu-id="828b5-130">例如，接口可能会声明包含 [get](../../language-reference/keywords/get.md) 取值函数的属性。</span><span class="sxs-lookup"><span data-stu-id="828b5-130">For example, an interface might declare a property that has a [get](../../language-reference/keywords/get.md) accessor.</span></span> <span data-ttu-id="828b5-131">实现此接口的类可以声明包含 `get` 和 [set](../../language-reference/keywords/set.md) 取值函数的同一属性。</span><span class="sxs-lookup"><span data-stu-id="828b5-131">The class that implements the interface can declare the same property with both a `get` and [set](../../language-reference/keywords/set.md) accessor.</span></span> <span data-ttu-id="828b5-132">但是，如果属性或索引器使用显式实现，则访问器必须匹配。</span><span class="sxs-lookup"><span data-stu-id="828b5-132">However, if the property or indexer uses explicit implementation, the accessors must match.</span></span> <span data-ttu-id="828b5-133">有关显式实现的详细信息，请参阅[显式接口实现](explicit-interface-implementation.md)和[接口属性](../classes-and-structs/interface-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="828b5-133">For more information about explicit implementation, see [Explicit Interface Implementation](explicit-interface-implementation.md) and [Interface Properties](../classes-and-structs/interface-properties.md).</span></span>  

<span data-ttu-id="828b5-134">接口可以从其他接口继承。</span><span class="sxs-lookup"><span data-stu-id="828b5-134">Interfaces can inherit from other interfaces.</span></span> <span data-ttu-id="828b5-135">类可能通过它继承的基类或通过其他接口继承的接口来多次包含某个接口。</span><span class="sxs-lookup"><span data-stu-id="828b5-135">A class might include an interface multiple times through base classes that it inherits or through interfaces that other interfaces inherit.</span></span> <span data-ttu-id="828b5-136">但是，类只能提供接口的实现一次，并且仅当类将接口作为类定义的一部分 (`class ClassName : InterfaceName`) 进行声明时才能提供。</span><span class="sxs-lookup"><span data-stu-id="828b5-136">However, the class can provide an implementation of an interface only one time and only if the class declares the interface as part of the definition of the class (`class ClassName : InterfaceName`).</span></span> <span data-ttu-id="828b5-137">如果由于继承实现接口的基类而继承了接口，则基类会提供接口的成员的实现。</span><span class="sxs-lookup"><span data-stu-id="828b5-137">If the interface is inherited because you inherited a base class that implements the interface, the base class provides the implementation of the members of the interface.</span></span> <span data-ttu-id="828b5-138">但是，派生类可以重新实现任何虚拟接口成员，而不是使用继承的实现。</span><span class="sxs-lookup"><span data-stu-id="828b5-138">However, the derived class can reimplement any virtual interface members instead of using the inherited implementation.</span></span>  
  
<span data-ttu-id="828b5-139">基类还可以使用虚拟成员实现接口成员。</span><span class="sxs-lookup"><span data-stu-id="828b5-139">A base class can also implement interface members by using virtual members.</span></span> <span data-ttu-id="828b5-140">在这种情况下，派生类可以通过重写虚拟成员来更改接口行为。</span><span class="sxs-lookup"><span data-stu-id="828b5-140">In that case, a derived class can change the interface behavior by overriding the virtual members.</span></span> <span data-ttu-id="828b5-141">有关虚拟成员的详细信息，请参阅[多态性](../classes-and-structs/polymorphism.md)。</span><span class="sxs-lookup"><span data-stu-id="828b5-141">For more information about virtual members, see [Polymorphism](../classes-and-structs/polymorphism.md).</span></span>  
  
## <a name="interfaces-summary"></a><span data-ttu-id="828b5-142">接口摘要</span><span class="sxs-lookup"><span data-stu-id="828b5-142">Interfaces summary</span></span>

<span data-ttu-id="828b5-143">接口具有以下属性：</span><span class="sxs-lookup"><span data-stu-id="828b5-143">An interface has the following properties:</span></span>  

- <span data-ttu-id="828b5-144">接口类似于只有抽象成员的抽象基类。</span><span class="sxs-lookup"><span data-stu-id="828b5-144">An interface is like an abstract base class with only abstract members.</span></span> <span data-ttu-id="828b5-145">实现接口的任何类或结构都必须实现其所有成员。</span><span class="sxs-lookup"><span data-stu-id="828b5-145">Any class or struct that implements the interface must implement all its members.</span></span>
- <span data-ttu-id="828b5-146">接口无法直接进行实例化。</span><span class="sxs-lookup"><span data-stu-id="828b5-146">An interface can't be instantiated directly.</span></span> <span data-ttu-id="828b5-147">其成员由实现接口的任何类或结构来实现。</span><span class="sxs-lookup"><span data-stu-id="828b5-147">Its members are implemented by any class or struct that implements the interface.</span></span>
- <span data-ttu-id="828b5-148">接口可以包含事件、索引器、方法和属性。</span><span class="sxs-lookup"><span data-stu-id="828b5-148">Interfaces can contain events, indexers, methods, and properties.</span></span>
- <span data-ttu-id="828b5-149">接口不包含方法的实现。</span><span class="sxs-lookup"><span data-stu-id="828b5-149">Interfaces contain no implementation of methods.</span></span>
- <span data-ttu-id="828b5-150">一个类或结构可以实现多个接口。</span><span class="sxs-lookup"><span data-stu-id="828b5-150">A class or struct can implement multiple interfaces.</span></span> <span data-ttu-id="828b5-151">一个类可以继承一个基类，还可实现一个或多个接口。</span><span class="sxs-lookup"><span data-stu-id="828b5-151">A class can inherit a base class and also implement one or more interfaces.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="828b5-152">本节内容</span><span class="sxs-lookup"><span data-stu-id="828b5-152">In this section</span></span>

[<span data-ttu-id="828b5-153">显式接口实现</span><span class="sxs-lookup"><span data-stu-id="828b5-153">Explicit Interface Implementation</span></span>](explicit-interface-implementation.md)  
 <span data-ttu-id="828b5-154">说明如何创建特定于接口的类成员。</span><span class="sxs-lookup"><span data-stu-id="828b5-154">Explains how to create a class member that’s specific to an interface.</span></span>  
  
 [<span data-ttu-id="828b5-155">如何：显式实现接口成员</span><span class="sxs-lookup"><span data-stu-id="828b5-155">How to: Explicitly Implement Interface Members</span></span>](how-to-explicitly-implement-interface-members.md)  
 <span data-ttu-id="828b5-156">提供有关如何显式实现接口的成员的示例。</span><span class="sxs-lookup"><span data-stu-id="828b5-156">Provides an example of how to explicitly implement members of interfaces.</span></span>  
  
 [<span data-ttu-id="828b5-157">如何：显式实现两个接口的成员</span><span class="sxs-lookup"><span data-stu-id="828b5-157">How to: Explicitly Implement Members of Two Interfaces</span></span>](how-to-explicitly-implement-members-of-two-interfaces.md)  
 <span data-ttu-id="828b5-158">提供有关如何使用继承显式实现接口的成员的示例。</span><span class="sxs-lookup"><span data-stu-id="828b5-158">Provides an example of how to explicitly implement members of interfaces with inheritance.</span></span>  
  
## <a name="BKMK_RelatedSections"></a><span data-ttu-id="828b5-159">相关部分</span><span class="sxs-lookup"><span data-stu-id="828b5-159">Related Sections</span></span>

- [<span data-ttu-id="828b5-160">接口属性</span><span class="sxs-lookup"><span data-stu-id="828b5-160">Interface Properties</span></span>](../classes-and-structs/interface-properties.md)  
- [<span data-ttu-id="828b5-161">接口中的索引器</span><span class="sxs-lookup"><span data-stu-id="828b5-161">Indexers in Interfaces</span></span>](../indexers/indexers-in-interfaces.md)  
- [<span data-ttu-id="828b5-162">如何：实现接口事件</span><span class="sxs-lookup"><span data-stu-id="828b5-162">How to:  Implement Interface Events</span></span>](../events/how-to-implement-interface-events.md)  
- [<span data-ttu-id="828b5-163">类和结构</span><span class="sxs-lookup"><span data-stu-id="828b5-163">Classes and Structs</span></span>](../classes-and-structs/index.md)  
- [<span data-ttu-id="828b5-164">继承</span><span class="sxs-lookup"><span data-stu-id="828b5-164">Inheritance</span></span>](../classes-and-structs/inheritance.md)  
- [<span data-ttu-id="828b5-165">方法</span><span class="sxs-lookup"><span data-stu-id="828b5-165">Methods</span></span>](../classes-and-structs/methods.md)  
- [<span data-ttu-id="828b5-166">多态性</span><span class="sxs-lookup"><span data-stu-id="828b5-166">Polymorphism</span></span>](../classes-and-structs/polymorphism.md)  
- [<span data-ttu-id="828b5-167">抽象类、密封类及类成员</span><span class="sxs-lookup"><span data-stu-id="828b5-167">Abstract and Sealed Classes and Class Members</span></span>](../classes-and-structs/abstract-and-sealed-classes-and-class-members.md)  
- [<span data-ttu-id="828b5-168">属性</span><span class="sxs-lookup"><span data-stu-id="828b5-168">Properties</span></span>](../classes-and-structs/properties.md)  
- [<span data-ttu-id="828b5-169">事件</span><span class="sxs-lookup"><span data-stu-id="828b5-169">Events</span></span>](../events/index.md)  
- [<span data-ttu-id="828b5-170">索引器</span><span class="sxs-lookup"><span data-stu-id="828b5-170">Indexers</span></span>](../indexers/index.md)  
  
## <a name="featured-book-chapter"></a><span data-ttu-id="828b5-171">重要章节</span><span class="sxs-lookup"><span data-stu-id="828b5-171">featured book chapter</span></span>

<span data-ttu-id="828b5-172">[学习 C# 3.0：掌握 C# 3.0 基础知识](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff652493%28v%253dorm.10%29)中的[接口](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff652489%28v%3Dorm.10%29)</span><span class="sxs-lookup"><span data-stu-id="828b5-172">[Interfaces](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff652489%28v%3Dorm.10%29) in [Learning C# 3.0: Master the Fundamentals of C# 3.0](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff652493%28v%253dorm.10%29)</span></span>

## <a name="see-also"></a><span data-ttu-id="828b5-173">请参阅</span><span class="sxs-lookup"><span data-stu-id="828b5-173">See also</span></span>

- [<span data-ttu-id="828b5-174">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="828b5-174">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="828b5-175">继承</span><span class="sxs-lookup"><span data-stu-id="828b5-175">Inheritance</span></span>](../classes-and-structs/inheritance.md)
- [<span data-ttu-id="828b5-176">标识符名称</span><span class="sxs-lookup"><span data-stu-id="828b5-176">Identifier names</span></span>](../inside-a-program/identifier-names.md)
