---
title: 抽象类
description: 了解如何F#抽象类，这将部分或全部成员未实现和表示的一组不同的对象类型的常见功能。
ms.date: 05/16/2016
ms.openlocfilehash: fecd3b2d550c6b8f59fa614f5d00c5f730a4896a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61772770"
---
# <a name="abstract-classes"></a><span data-ttu-id="50fd7-103">抽象类</span><span class="sxs-lookup"><span data-stu-id="50fd7-103">Abstract Classes</span></span>

<span data-ttu-id="50fd7-104">*抽象类*是留部分或全部成员未实现，以便可以由派生类提供实现的类。</span><span class="sxs-lookup"><span data-stu-id="50fd7-104">*Abstract classes* are classes that leave some or all members unimplemented, so that implementations can be provided by derived classes.</span></span>

## <a name="syntax"></a><span data-ttu-id="50fd7-105">语法</span><span class="sxs-lookup"><span data-stu-id="50fd7-105">Syntax</span></span>

```fsharp
// Abstract class syntax.
[<AbstractClass>]
type [ accessibility-modifier ] abstract-class-name =
[ inherit base-class-or-interface-name ]
[ abstract-member-declarations-and-member-definitions ]

// Abstract member syntax.
abstract member member-name : type-signature
```

## <a name="remarks"></a><span data-ttu-id="50fd7-106">备注</span><span class="sxs-lookup"><span data-stu-id="50fd7-106">Remarks</span></span>

<span data-ttu-id="50fd7-107">在面向对象的编程中，抽象类用作基类的层次结构中，并表示一组不同的对象类型的常见功能。</span><span class="sxs-lookup"><span data-stu-id="50fd7-107">In object-oriented programming, an abstract class is used as a base class of a hierarchy, and represents common functionality of a diverse set of object types.</span></span> <span data-ttu-id="50fd7-108">正如所示名称"抽象"，抽象类通常并不对应直接到问题域中的具体实体上。</span><span class="sxs-lookup"><span data-stu-id="50fd7-108">As the name "abstract" implies, abstract classes often do not correspond directly onto concrete entities in the problem domain.</span></span> <span data-ttu-id="50fd7-109">但是，它们代表多个不同的具体实体具有共同点。</span><span class="sxs-lookup"><span data-stu-id="50fd7-109">However, they do represent what many different concrete entities have in common.</span></span>

<span data-ttu-id="50fd7-110">抽象类必须具有`AbstractClass`属性。</span><span class="sxs-lookup"><span data-stu-id="50fd7-110">Abstract classes must have the `AbstractClass` attribute.</span></span> <span data-ttu-id="50fd7-111">它们可以实现和尚未实现的成员。</span><span class="sxs-lookup"><span data-stu-id="50fd7-111">They can have implemented and unimplemented members.</span></span> <span data-ttu-id="50fd7-112">使用术语*抽象*时应用于类是与其他.NET 语言; 中的相同但是，使用术语*抽象*时应用于方法 （和属性） 是稍有不同在F#从在其他.NET 语言中使用。</span><span class="sxs-lookup"><span data-stu-id="50fd7-112">The use of the term *abstract* when applied to a class is the same as in other .NET languages; however, the use of the term *abstract* when applied to methods (and properties) is a little different in F# from its use in other .NET languages.</span></span> <span data-ttu-id="50fd7-113">在F#，当方法标有`abstract`关键字，这指示成员具有一个项，称为*虚拟调度槽*，该类型的虚函数的内部表中。</span><span class="sxs-lookup"><span data-stu-id="50fd7-113">In F#, when a method is marked with the `abstract` keyword, this indicates that a member has an entry, known as a *virtual dispatch slot*, in the internal table of virtual functions for that type.</span></span> <span data-ttu-id="50fd7-114">换而言之，方法是虚拟的尽管`virtual`中未使用关键字F#语言。</span><span class="sxs-lookup"><span data-stu-id="50fd7-114">In other words, the method is virtual, although the `virtual` keyword is not used in the F# language.</span></span> <span data-ttu-id="50fd7-115">关键字`abstract`虚拟方法，而不考虑是否实现该方法上使用。</span><span class="sxs-lookup"><span data-stu-id="50fd7-115">The keyword `abstract` is used on virtual methods regardless of whether the method is implemented.</span></span> <span data-ttu-id="50fd7-116">虚拟调度槽的声明是独立于为该调度槽方法的定义。</span><span class="sxs-lookup"><span data-stu-id="50fd7-116">The declaration of a virtual dispatch slot is separate from the definition of a method for that dispatch slot.</span></span> <span data-ttu-id="50fd7-117">因此，F#虚方法声明和定义另一种.NET 语言中的等效项是抽象方法声明和使用的单独定义的组合`default`关键字或`override`关键字。</span><span class="sxs-lookup"><span data-stu-id="50fd7-117">Therefore, the F# equivalent of a virtual method declaration and definition in another .NET language is a combination of both an abstract method declaration and a separate definition, with either the `default` keyword or the `override` keyword.</span></span> <span data-ttu-id="50fd7-118">有关详细信息和示例，请参阅[方法](members/methods.md)。</span><span class="sxs-lookup"><span data-stu-id="50fd7-118">For more information and examples, see [Methods](members/methods.md).</span></span>

<span data-ttu-id="50fd7-119">一个类都被视为仅当存在的抽象方法声明但未定义的抽象。</span><span class="sxs-lookup"><span data-stu-id="50fd7-119">A class is considered abstract only if there are abstract methods that are declared but not defined.</span></span> <span data-ttu-id="50fd7-120">因此，具有抽象方法的类不一定是抽象类。</span><span class="sxs-lookup"><span data-stu-id="50fd7-120">Therefore, classes that have abstract methods are not necessarily abstract classes.</span></span> <span data-ttu-id="50fd7-121">除非类有未定义的抽象方法，否则不要使用**AbstractClass**属性。</span><span class="sxs-lookup"><span data-stu-id="50fd7-121">Unless a class has undefined abstract methods, do not use the **AbstractClass** attribute.</span></span>

<span data-ttu-id="50fd7-122">在上述语法中，*可访问性修饰符*可以是`public`，`private`或`internal`。</span><span class="sxs-lookup"><span data-stu-id="50fd7-122">In the previous syntax, *accessibility-modifier* can be `public`, `private` or `internal`.</span></span> <span data-ttu-id="50fd7-123">有关详细信息，请参阅[访问控制](access-control.md)。</span><span class="sxs-lookup"><span data-stu-id="50fd7-123">For more information, see [Access Control](access-control.md).</span></span>

<span data-ttu-id="50fd7-124">与其他类型一样，抽象类可以具有一个基类和一个或多个基接口。</span><span class="sxs-lookup"><span data-stu-id="50fd7-124">As with other types, abstract classes can have a base class and one or more base interfaces.</span></span> <span data-ttu-id="50fd7-125">每个基类或接口显示在单独的行一起使用`inherit`关键字。</span><span class="sxs-lookup"><span data-stu-id="50fd7-125">Each base class or interface appears on a separate line together with the `inherit` keyword.</span></span>

<span data-ttu-id="50fd7-126">一个抽象类的类型定义可以包含完全定义的成员，但它也可以包含抽象成员。</span><span class="sxs-lookup"><span data-stu-id="50fd7-126">The type definition of an abstract class can contain fully defined members, but it can also contain abstract members.</span></span> <span data-ttu-id="50fd7-127">抽象成员的语法是单独显示在前面的语法。</span><span class="sxs-lookup"><span data-stu-id="50fd7-127">The syntax for abstract members is shown separately in the previous syntax.</span></span> <span data-ttu-id="50fd7-128">在此语法中，*类型签名*的成员一个列表，其中包含的参数顺序和返回类型，类型分隔`->`令牌和/或`*`令牌作为相应的科里化和元组形式参数。</span><span class="sxs-lookup"><span data-stu-id="50fd7-128">In this syntax, the *type signature* of a member is a list that contains the parameter types in order and the return types, separated by `->` tokens and/or `*` tokens as appropriate for curried and tupled parameters.</span></span> <span data-ttu-id="50fd7-129">抽象成员类型签名的语法是在签名文件中使用和 intellisense Visual Studio 代码编辑器中显示的相同。</span><span class="sxs-lookup"><span data-stu-id="50fd7-129">The syntax for abstract member type signatures is the same as that used in signature files and that shown by IntelliSense in the Visual Studio Code Editor.</span></span>

<span data-ttu-id="50fd7-130">下面的代码演示一个抽象类形状，它具有两个非抽象派生的类，正方形和圆。</span><span class="sxs-lookup"><span data-stu-id="50fd7-130">The following code illustrates an abstract class Shape, which has two non-abstract derived classes, Square and Circle.</span></span> <span data-ttu-id="50fd7-131">该示例演示如何使用抽象类、 方法和属性。</span><span class="sxs-lookup"><span data-stu-id="50fd7-131">The example shows how to use abstract classes, methods, and properties.</span></span> <span data-ttu-id="50fd7-132">在示例中，抽象类形状表示的具体实体圆形和正方形的常用元素。</span><span class="sxs-lookup"><span data-stu-id="50fd7-132">In the example, the abstract class Shape represents the common elements of the concrete entities circle and square.</span></span> <span data-ttu-id="50fd7-133">（在二维坐标系统） 的所有形状的常见功能都抽象到 Shape 类： 网格、 旋转的角度和面积和周长属性上的位置。</span><span class="sxs-lookup"><span data-stu-id="50fd7-133">The common features of all shapes (in a two-dimensional coordinate system) are abstracted out into the Shape class: the position on the grid, an angle of rotation, and the area and perimeter properties.</span></span> <span data-ttu-id="50fd7-134">这些可以重写，但位置，其中各个形状不能更改的行为除外。</span><span class="sxs-lookup"><span data-stu-id="50fd7-134">These can be overridden, except for position, the behavior of which individual shapes cannot change.</span></span>

<span data-ttu-id="50fd7-135">旋转方法可以重写的如下所示圆形类中，由于其对称性是固定的旋转。</span><span class="sxs-lookup"><span data-stu-id="50fd7-135">The rotation method can be overridden, as in the Circle class, which is rotation invariant because of its symmetry.</span></span> <span data-ttu-id="50fd7-136">因此在圆形类中，旋转方法被替换为不执行任何操作的方法。</span><span class="sxs-lookup"><span data-stu-id="50fd7-136">So in the Circle class, the rotation method is replaced by a method that does nothing.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2901.fs)]

<span data-ttu-id="50fd7-137">**输出：**</span><span class="sxs-lookup"><span data-stu-id="50fd7-137">**Output:**</span></span>

```
Perimeter of square with side length 10.000000 is 40.000000
Circumference of circle with radius 5.000000 is 31.415927
Area of Square: 100.000000
Area of Circle: 78.539816
```

## <a name="see-also"></a><span data-ttu-id="50fd7-138">请参阅</span><span class="sxs-lookup"><span data-stu-id="50fd7-138">See also</span></span>

- [<span data-ttu-id="50fd7-139">类</span><span class="sxs-lookup"><span data-stu-id="50fd7-139">Classes</span></span>](classes.md)
- [<span data-ttu-id="50fd7-140">成员</span><span class="sxs-lookup"><span data-stu-id="50fd7-140">Members</span></span>](members/index.md)
- [<span data-ttu-id="50fd7-141">方法</span><span class="sxs-lookup"><span data-stu-id="50fd7-141">Methods</span></span>](members/methods.md)
- [<span data-ttu-id="50fd7-142">属性</span><span class="sxs-lookup"><span data-stu-id="50fd7-142">Properties</span></span>](members/Properties.md)