---
title: 抽象类
description: 了解F#抽象类, 这些类使部分或全部成员未实现, 并表示一组不同的对象类型的常用功能。
ms.date: 05/16/2016
ms.openlocfilehash: a6bbfc23b858d5f3833f3f52b6dca46753080f03
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/30/2019
ms.locfileid: "68629677"
---
# <a name="abstract-classes"></a><span data-ttu-id="43162-103">抽象类</span><span class="sxs-lookup"><span data-stu-id="43162-103">Abstract Classes</span></span>

<span data-ttu-id="43162-104">*抽象类*是保留部分或全部成员未实现的类, 以便实现可由派生类提供。</span><span class="sxs-lookup"><span data-stu-id="43162-104">*Abstract classes* are classes that leave some or all members unimplemented, so that implementations can be provided by derived classes.</span></span>

## <a name="syntax"></a><span data-ttu-id="43162-105">语法</span><span class="sxs-lookup"><span data-stu-id="43162-105">Syntax</span></span>

```fsharp
// Abstract class syntax.
[<AbstractClass>]
type [ accessibility-modifier ] abstract-class-name =
[ inherit base-class-or-interface-name ]
[ abstract-member-declarations-and-member-definitions ]

// Abstract member syntax.
abstract member member-name : type-signature
```

## <a name="remarks"></a><span data-ttu-id="43162-106">备注</span><span class="sxs-lookup"><span data-stu-id="43162-106">Remarks</span></span>

<span data-ttu-id="43162-107">在面向对象的编程中, 抽象类用作层次结构的基类, 并表示一组不同的对象类型的常用功能。</span><span class="sxs-lookup"><span data-stu-id="43162-107">In object-oriented programming, an abstract class is used as a base class of a hierarchy, and represents common functionality of a diverse set of object types.</span></span> <span data-ttu-id="43162-108">顾名思义, 抽象类通常不直接与问题域中的具体实体直接对应。</span><span class="sxs-lookup"><span data-stu-id="43162-108">As the name "abstract" implies, abstract classes often do not correspond directly onto concrete entities in the problem domain.</span></span> <span data-ttu-id="43162-109">不过, 它们确实代表了许多不同的具体实体。</span><span class="sxs-lookup"><span data-stu-id="43162-109">However, they do represent what many different concrete entities have in common.</span></span>

<span data-ttu-id="43162-110">抽象类必须具有`AbstractClass`特性。</span><span class="sxs-lookup"><span data-stu-id="43162-110">Abstract classes must have the `AbstractClass` attribute.</span></span> <span data-ttu-id="43162-111">它们可以具有实现和未实现的成员。</span><span class="sxs-lookup"><span data-stu-id="43162-111">They can have implemented and unimplemented members.</span></span> <span data-ttu-id="43162-112">当应用于类时, 术语 "*抽象*" 的使用与其他 .net 语言相同;但是, 在应用于方法 (和属性) 时, 术语 "*抽象*" 的用法与在其他F# .net 语言中使用的方法稍有不同。</span><span class="sxs-lookup"><span data-stu-id="43162-112">The use of the term *abstract* when applied to a class is the same as in other .NET languages; however, the use of the term *abstract* when applied to methods (and properties) is a little different in F# from its use in other .NET languages.</span></span> <span data-ttu-id="43162-113">在F#中, 当使用`abstract`关键字标记方法时, 这表示成员在该类型的虚函数的内部表中具有一个称为*虚拟调度槽*的条目。</span><span class="sxs-lookup"><span data-stu-id="43162-113">In F#, when a method is marked with the `abstract` keyword, this indicates that a member has an entry, known as a *virtual dispatch slot*, in the internal table of virtual functions for that type.</span></span> <span data-ttu-id="43162-114">换句话说, 方法为虚方法, 但`virtual`该F#语言中未使用关键字。</span><span class="sxs-lookup"><span data-stu-id="43162-114">In other words, the method is virtual, although the `virtual` keyword is not used in the F# language.</span></span> <span data-ttu-id="43162-115">关键字`abstract`用于虚拟方法, 而不考虑是否实现方法。</span><span class="sxs-lookup"><span data-stu-id="43162-115">The keyword `abstract` is used on virtual methods regardless of whether the method is implemented.</span></span> <span data-ttu-id="43162-116">虚拟调度槽的声明独立于该调度槽的方法的定义。</span><span class="sxs-lookup"><span data-stu-id="43162-116">The declaration of a virtual dispatch slot is separate from the definition of a method for that dispatch slot.</span></span> <span data-ttu-id="43162-117">因此, 在F#其他 .net 语言中, 虚拟方法声明和定义的等效项是抽象方法声明和单独定义的组合, 其中包含`default`关键字或`override`关键字。</span><span class="sxs-lookup"><span data-stu-id="43162-117">Therefore, the F# equivalent of a virtual method declaration and definition in another .NET language is a combination of both an abstract method declaration and a separate definition, with either the `default` keyword or the `override` keyword.</span></span> <span data-ttu-id="43162-118">有关详细信息和示例, 请参阅[方法](./members/methods.md)。</span><span class="sxs-lookup"><span data-stu-id="43162-118">For more information and examples, see [Methods](./members/methods.md).</span></span>

<span data-ttu-id="43162-119">仅当存在已声明但未定义的抽象方法时, 才会将类视为抽象方法。</span><span class="sxs-lookup"><span data-stu-id="43162-119">A class is considered abstract only if there are abstract methods that are declared but not defined.</span></span> <span data-ttu-id="43162-120">因此, 具有抽象方法的类不一定是抽象类。</span><span class="sxs-lookup"><span data-stu-id="43162-120">Therefore, classes that have abstract methods are not necessarily abstract classes.</span></span> <span data-ttu-id="43162-121">除非类具有未定义的抽象方法, 否则不使用**AbstractClass**特性。</span><span class="sxs-lookup"><span data-stu-id="43162-121">Unless a class has undefined abstract methods, do not use the **AbstractClass** attribute.</span></span>

<span data-ttu-id="43162-122">在前面的语法中, 可*访问性修饰符*可以`private`是`internal` `public`或。</span><span class="sxs-lookup"><span data-stu-id="43162-122">In the previous syntax, *accessibility-modifier* can be `public`, `private` or `internal`.</span></span> <span data-ttu-id="43162-123">有关详细信息，请参阅[访问控制](access-control.md)。</span><span class="sxs-lookup"><span data-stu-id="43162-123">For more information, see [Access Control](access-control.md).</span></span>

<span data-ttu-id="43162-124">与其他类型一样, 抽象类可以具有基类和一个或多个基接口。</span><span class="sxs-lookup"><span data-stu-id="43162-124">As with other types, abstract classes can have a base class and one or more base interfaces.</span></span> <span data-ttu-id="43162-125">每个基类或接口都显示在单独的行上, `inherit`并带有关键字。</span><span class="sxs-lookup"><span data-stu-id="43162-125">Each base class or interface appears on a separate line together with the `inherit` keyword.</span></span>

<span data-ttu-id="43162-126">抽象类的类型定义可包含完全定义的成员, 但它还可以包含抽象成员。</span><span class="sxs-lookup"><span data-stu-id="43162-126">The type definition of an abstract class can contain fully defined members, but it can also contain abstract members.</span></span> <span data-ttu-id="43162-127">在前面的语法中, 将单独显示抽象成员的语法。</span><span class="sxs-lookup"><span data-stu-id="43162-127">The syntax for abstract members is shown separately in the previous syntax.</span></span> <span data-ttu-id="43162-128">在此语法中, 成员的*类型签名*是一个列表, 其中包含按顺序排列的参数类型和返回类型 (根据适用`->`于扩充和元`*`组参数的适当标记和/或标记分隔)。</span><span class="sxs-lookup"><span data-stu-id="43162-128">In this syntax, the *type signature* of a member is a list that contains the parameter types in order and the return types, separated by `->` tokens and/or `*` tokens as appropriate for curried and tupled parameters.</span></span> <span data-ttu-id="43162-129">抽象成员类型签名的语法与签名文件中使用的语法相同, 并且在 Visual Studio Code 编辑器中由 IntelliSense 显示。</span><span class="sxs-lookup"><span data-stu-id="43162-129">The syntax for abstract member type signatures is the same as that used in signature files and that shown by IntelliSense in the Visual Studio Code Editor.</span></span>

<span data-ttu-id="43162-130">下面的代码演示一个抽象类形状, 它具有两个非抽象的派生类 (正方形和圆圈)。</span><span class="sxs-lookup"><span data-stu-id="43162-130">The following code illustrates an abstract class Shape, which has two non-abstract derived classes, Square and Circle.</span></span> <span data-ttu-id="43162-131">该示例演示如何使用抽象类、方法和属性。</span><span class="sxs-lookup"><span data-stu-id="43162-131">The example shows how to use abstract classes, methods, and properties.</span></span> <span data-ttu-id="43162-132">在此示例中, 抽象类形状表示具体实体 circle 和正方形的公共元素。</span><span class="sxs-lookup"><span data-stu-id="43162-132">In the example, the abstract class Shape represents the common elements of the concrete entities circle and square.</span></span> <span data-ttu-id="43162-133">所有形状 (在二维坐标系统中) 的常见功能都抽象到 Shape 类中: 网格上的位置、旋转角度以及区域和外围属性。</span><span class="sxs-lookup"><span data-stu-id="43162-133">The common features of all shapes (in a two-dimensional coordinate system) are abstracted out into the Shape class: the position on the grid, an angle of rotation, and the area and perimeter properties.</span></span> <span data-ttu-id="43162-134">它们可以重写, 但位置除外, 不能更改各个形状的行为。</span><span class="sxs-lookup"><span data-stu-id="43162-134">These can be overridden, except for position, the behavior of which individual shapes cannot change.</span></span>

<span data-ttu-id="43162-135">旋转方法可以重写, 就像在 Circle 类中一样, 因为它是对称的, 所以旋转固定。</span><span class="sxs-lookup"><span data-stu-id="43162-135">The rotation method can be overridden, as in the Circle class, which is rotation invariant because of its symmetry.</span></span> <span data-ttu-id="43162-136">因此在 Circle 类中, 旋转方法替换为不执行任何操作的方法。</span><span class="sxs-lookup"><span data-stu-id="43162-136">So in the Circle class, the rotation method is replaced by a method that does nothing.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2901.fs)]

<span data-ttu-id="43162-137">**输出：**</span><span class="sxs-lookup"><span data-stu-id="43162-137">**Output:**</span></span>

```
Perimeter of square with side length 10.000000 is 40.000000
Circumference of circle with radius 5.000000 is 31.415927
Area of Square: 100.000000
Area of Circle: 78.539816
```

## <a name="see-also"></a><span data-ttu-id="43162-138">请参阅</span><span class="sxs-lookup"><span data-stu-id="43162-138">See also</span></span>

- [<span data-ttu-id="43162-139">类</span><span class="sxs-lookup"><span data-stu-id="43162-139">Classes</span></span>](classes.md)
- [<span data-ttu-id="43162-140">成员</span><span class="sxs-lookup"><span data-stu-id="43162-140">Members</span></span>](./members/index.md)
- [<span data-ttu-id="43162-141">方法</span><span class="sxs-lookup"><span data-stu-id="43162-141">Methods</span></span>](./members/methods.md)
- [<span data-ttu-id="43162-142">属性</span><span class="sxs-lookup"><span data-stu-id="43162-142">Properties</span></span>](./members/Properties.md)
