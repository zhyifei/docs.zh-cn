---
title: "抽象类、密封类及类成员（C# 编程指南）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- abstract classes [C#]
- sealed classes [C#]
- C# language, abstract classes
- C# language, sealed
ms.assetid: 99aa52f7-b435-43f9-936e-2470af734c4e
caps.latest.revision: 14
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
ms.openlocfilehash: 0788ea0778b3f8b846231fc2408938b2236314c9
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="abstract-and-sealed-classes-and-class-members-c-programming-guide"></a><span data-ttu-id="94865-102">抽象类、密封类及类成员（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="94865-102">Abstract and Sealed Classes and Class Members (C# Programming Guide)</span></span>
<span data-ttu-id="94865-103">使用 [abstract](../../../csharp/language-reference/keywords/abstract.md) 关键字可以创建不完整且必须在派生类中实现的类和 [class](../../../csharp/language-reference/keywords/class.md) 成员。</span><span class="sxs-lookup"><span data-stu-id="94865-103">The [abstract](../../../csharp/language-reference/keywords/abstract.md) keyword enables you to create classes and [class](../../../csharp/language-reference/keywords/class.md) members that are incomplete and must be implemented in a derived class.</span></span>  
  
 <span data-ttu-id="94865-104">使用 [sealed](../../../csharp/language-reference/keywords/sealed.md) 关键字可以防止继承以前标记为 [virtual](../../../csharp/language-reference/keywords/virtual.md) 的类或某些类成员。</span><span class="sxs-lookup"><span data-stu-id="94865-104">The [sealed](../../../csharp/language-reference/keywords/sealed.md) keyword enables you to prevent the inheritance of a class or certain class members that were previously marked [virtual](../../../csharp/language-reference/keywords/virtual.md).</span></span>  
  
## <a name="abstract-classes-and-class-members"></a><span data-ttu-id="94865-105">抽象类和类成员</span><span class="sxs-lookup"><span data-stu-id="94865-105">Abstract Classes and Class Members</span></span>  
 <span data-ttu-id="94865-106">通过在类定义前面放置关键字 `abstract`，可以将类声明为抽象类。</span><span class="sxs-lookup"><span data-stu-id="94865-106">Classes can be declared as abstract by putting the keyword `abstract` before the class definition.</span></span> <span data-ttu-id="94865-107">例如: </span><span class="sxs-lookup"><span data-stu-id="94865-107">For example:</span></span>  
  
 <span data-ttu-id="94865-108">[!code-cs[csProgGuideInheritance#13](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/abstract-and-sealed-classes-and-class-members_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="94865-108">[!code-cs[csProgGuideInheritance#13](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/abstract-and-sealed-classes-and-class-members_1.cs)]</span></span>  
  
 <span data-ttu-id="94865-109">抽象类不能实例化。</span><span class="sxs-lookup"><span data-stu-id="94865-109">An abstract class cannot be instantiated.</span></span> <span data-ttu-id="94865-110">抽象类的用途是提供一个可供多个派生类共享的通用基类定义。</span><span class="sxs-lookup"><span data-stu-id="94865-110">The purpose of an abstract class is to provide a common definition of a base class that multiple derived classes can share.</span></span> <span data-ttu-id="94865-111">例如，类库可以定义一个抽象类，将其用作多个类库函数的参数，并要求使用该库的程序员通过创建派生类来提供自己的类实现。</span><span class="sxs-lookup"><span data-stu-id="94865-111">For example, a class library may define an abstract class that is used as a parameter to many of its functions, and require programmers using that library to provide their own implementation of the class by creating a derived class.</span></span>  
  
 <span data-ttu-id="94865-112">抽象类也可以定义抽象方法。</span><span class="sxs-lookup"><span data-stu-id="94865-112">Abstract classes may also define abstract methods.</span></span> <span data-ttu-id="94865-113">方法是将关键字 `abstract` 添加到方法的返回类型的前面。</span><span class="sxs-lookup"><span data-stu-id="94865-113">This is accomplished by adding the keyword `abstract` before the return type of the method.</span></span> <span data-ttu-id="94865-114">例如: </span><span class="sxs-lookup"><span data-stu-id="94865-114">For example:</span></span>  
  
 <span data-ttu-id="94865-115">[!code-cs[csProgGuideInheritance#14](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/abstract-and-sealed-classes-and-class-members_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="94865-115">[!code-cs[csProgGuideInheritance#14](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/abstract-and-sealed-classes-and-class-members_2.cs)]</span></span>  
  
 <span data-ttu-id="94865-116">抽象方法没有实现，所以方法定义后面是分号，而不是常规的方法块。</span><span class="sxs-lookup"><span data-stu-id="94865-116">Abstract methods have no implementation, so the method definition is followed by a semicolon instead of a normal method block.</span></span> <span data-ttu-id="94865-117">抽象类的派生类必须实现所有抽象方法。</span><span class="sxs-lookup"><span data-stu-id="94865-117">Derived classes of the abstract class must implement all abstract methods.</span></span> <span data-ttu-id="94865-118">当抽象类从基类继承虚方法时，抽象类可以使用抽象方法重写该虚方法。</span><span class="sxs-lookup"><span data-stu-id="94865-118">When an abstract class inherits a virtual method from a base class, the abstract class can override the virtual method with an abstract method.</span></span> <span data-ttu-id="94865-119">例如: </span><span class="sxs-lookup"><span data-stu-id="94865-119">For example:</span></span>  
  
 <span data-ttu-id="94865-120">[!code-cs[csProgGuideInheritance#15](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/abstract-and-sealed-classes-and-class-members_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="94865-120">[!code-cs[csProgGuideInheritance#15](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/abstract-and-sealed-classes-and-class-members_3.cs)]</span></span>  
  
 <span data-ttu-id="94865-121">如果将 `virtual` 方法声明为 `abstract`，则该方法对于从抽象类继承的所有类而言仍然是虚方法。</span><span class="sxs-lookup"><span data-stu-id="94865-121">If a `virtual` method is declared `abstract`, it is still virtual to any class inheriting from the abstract class.</span></span> <span data-ttu-id="94865-122">继承抽象方法的类无法访问方法的原始实现，因此在上一示例中，类 F 上的 `DoWork` 无法调用类 D 上的 `DoWork`。通过这种方式，抽象类可强制派生类向虚拟方法提供新的方法实现。</span><span class="sxs-lookup"><span data-stu-id="94865-122">A class inheriting an abstract method cannot access the original implementation of the method—in the previous example, `DoWork` on class F cannot call `DoWork` on class D. In this way, an abstract class can force derived classes to provide new method implementations for virtual methods.</span></span>  
  
## <a name="sealed-classes-and-class-members"></a><span data-ttu-id="94865-123">密封类和类成员</span><span class="sxs-lookup"><span data-stu-id="94865-123">Sealed Classes and Class Members</span></span>  
 <span data-ttu-id="94865-124">通过在类定义前面放置关键字 `sealed`，可以将类声明为[密封类](../../../csharp/language-reference/keywords/sealed.md)。</span><span class="sxs-lookup"><span data-stu-id="94865-124">Classes can be declared as [sealed](../../../csharp/language-reference/keywords/sealed.md) by putting the keyword `sealed` before the class definition.</span></span> <span data-ttu-id="94865-125">例如: </span><span class="sxs-lookup"><span data-stu-id="94865-125">For example:</span></span>  
  
 <span data-ttu-id="94865-126">[!code-cs[csProgGuideInheritance#16](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/abstract-and-sealed-classes-and-class-members_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="94865-126">[!code-cs[csProgGuideInheritance#16](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/abstract-and-sealed-classes-and-class-members_4.cs)]</span></span>  
  
 <span data-ttu-id="94865-127">密封类不能用作基类。</span><span class="sxs-lookup"><span data-stu-id="94865-127">A sealed class cannot be used as a base class.</span></span> <span data-ttu-id="94865-128">因此，它也不能是抽象类。</span><span class="sxs-lookup"><span data-stu-id="94865-128">For this reason, it cannot also be an abstract class.</span></span> <span data-ttu-id="94865-129">密封类禁止派生。</span><span class="sxs-lookup"><span data-stu-id="94865-129">Sealed classes prevent derivation.</span></span> <span data-ttu-id="94865-130">由于密封类从不用作基类，所以有些运行时优化可以略微提高密封类成员的调用速度。</span><span class="sxs-lookup"><span data-stu-id="94865-130">Because they can never be used as a base class, some run-time optimizations can make calling sealed class members slightly faster.</span></span>  
  
 <span data-ttu-id="94865-131">在对基类的虚成员进行重写的派生类上，方法、索引器、属性或事件可以将该成员声明为密封成员。</span><span class="sxs-lookup"><span data-stu-id="94865-131">A method, indexer, property, or event, on a derived class that is overriding a virtual member of the base class can declare that member as sealed.</span></span> <span data-ttu-id="94865-132">在用于以后的派生类时，这将取消成员的虚效果。</span><span class="sxs-lookup"><span data-stu-id="94865-132">This negates the virtual aspect of the member for any further derived class.</span></span> <span data-ttu-id="94865-133">方法是在类成员声明中将 `sealed` 关键字置于 [override](../../../csharp/language-reference/keywords/override.md) 关键字前面。</span><span class="sxs-lookup"><span data-stu-id="94865-133">This is accomplished by putting the `sealed` keyword before the [override](../../../csharp/language-reference/keywords/override.md) keyword in the class member declaration.</span></span> <span data-ttu-id="94865-134">例如: </span><span class="sxs-lookup"><span data-stu-id="94865-134">For example:</span></span>  
  
 <span data-ttu-id="94865-135">[!code-cs[csProgGuideInheritance#17](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/abstract-and-sealed-classes-and-class-members_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="94865-135">[!code-cs[csProgGuideInheritance#17](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/abstract-and-sealed-classes-and-class-members_5.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94865-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="94865-136">See Also</span></span>  
 <span data-ttu-id="94865-137">[C# 编程指南](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="94865-137">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="94865-138">[类和结构](../../../csharp/programming-guide/classes-and-structs/index.md) </span><span class="sxs-lookup"><span data-stu-id="94865-138">[Classes and Structs](../../../csharp/programming-guide/classes-and-structs/index.md) </span></span>  
 <span data-ttu-id="94865-139">[继承](../../../csharp/programming-guide/classes-and-structs/inheritance.md) </span><span class="sxs-lookup"><span data-stu-id="94865-139">[Inheritance](../../../csharp/programming-guide/classes-and-structs/inheritance.md) </span></span>  
 <span data-ttu-id="94865-140">[方法](../../../csharp/programming-guide/classes-and-structs/methods.md) </span><span class="sxs-lookup"><span data-stu-id="94865-140">[Methods](../../../csharp/programming-guide/classes-and-structs/methods.md) </span></span>  
 <span data-ttu-id="94865-141">[字段](../../../csharp/programming-guide/classes-and-structs/fields.md) </span><span class="sxs-lookup"><span data-stu-id="94865-141">[Fields](../../../csharp/programming-guide/classes-and-structs/fields.md) </span></span>  
 [<span data-ttu-id="94865-142">如何：定义抽象属性</span><span class="sxs-lookup"><span data-stu-id="94865-142">How to: Define Abstract Properties</span></span>](../../../csharp/programming-guide/classes-and-structs/how-to-define-abstract-properties.md)

