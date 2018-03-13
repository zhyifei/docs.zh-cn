---
title: "C# 类和对象 - C# 语言介绍"
description: "刚开始接触 C#？ 请阅读这篇概述类、对象和继承的文章"
keywords: ".NET, C#, 类, 实例, 对象, 继承, 多形性"
author: BillWagner
ms.author: wiwagn
ms.date: 08/10/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 63a89bde-0f05-4bc4-b0cd-4f693854f0cd
ms.openlocfilehash: 97559a6e7b24f4a61b49dd4f050747a6d0ccbda0
ms.sourcegitcommit: d95a91d685565f4d95c8773b558752864a6a3d7e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2018
---
# <a name="classes-and-objects"></a><span data-ttu-id="9e78d-105">类和对象</span><span class="sxs-lookup"><span data-stu-id="9e78d-105">Classes and objects</span></span>

<span data-ttu-id="9e78d-106">*类*是最基本的 C# 类型。</span><span class="sxs-lookup"><span data-stu-id="9e78d-106">*Classes* are the most fundamental of C#’s types.</span></span> <span data-ttu-id="9e78d-107">类是一种数据结构，可在一个单元中就将状态（字段）和操作（方法和其他函数成员）结合起来。</span><span class="sxs-lookup"><span data-stu-id="9e78d-107">A class is a data structure that combines state (fields) and actions (methods and other function members) in a single unit.</span></span> <span data-ttu-id="9e78d-108">类为动态创建的类*实例*（亦称为“*对象*”）提供了定义。</span><span class="sxs-lookup"><span data-stu-id="9e78d-108">A class provides a definition for dynamically created *instances* of the class, also known as *objects*.</span></span> <span data-ttu-id="9e78d-109">类支持*继承*和*多形性*，即*派生类*可以扩展和专门针对*基类*的机制。</span><span class="sxs-lookup"><span data-stu-id="9e78d-109">Classes support *inheritance* and *polymorphism*, mechanisms whereby *derived classes* can extend and specialize *base classes*.</span></span>

<span data-ttu-id="9e78d-110">新类使用类声明进行创建。</span><span class="sxs-lookup"><span data-stu-id="9e78d-110">New classes are created using class declarations.</span></span> <span data-ttu-id="9e78d-111">类声明的开头是标头，指定了类的特性和修饰符、类名、基类（若指定）以及类实现的接口。</span><span class="sxs-lookup"><span data-stu-id="9e78d-111">A class declaration starts with a header that specifies the attributes and modifiers of the class, the name of the class, the base class (if given), and the interfaces implemented by the class.</span></span> <span data-ttu-id="9e78d-112">标头后面是类主体，由在分隔符 `{` 和 `}` 内编写的成员声明列表组成。</span><span class="sxs-lookup"><span data-stu-id="9e78d-112">The header is followed by the class body, which consists of a list of member declarations written between the delimiters `{` and `}`.</span></span>

<span data-ttu-id="9e78d-113">以下是简单类 `Point` 的声明：</span><span class="sxs-lookup"><span data-stu-id="9e78d-113">The following is a declaration of a simple class named `Point`:</span></span>

[!code-csharp[PointClass](../../../samples/snippets/csharp/tour/classes-and-objects/Point.cs#L3-L11)]

<span data-ttu-id="9e78d-114">类实例是使用 `new` 运算符进行创建，此运算符为新实例分配内存，调用构造函数来初始化实例，并返回对实例的引用。</span><span class="sxs-lookup"><span data-stu-id="9e78d-114">Instances of classes are created using the `new` operator, which allocates memory for a new instance, invokes a constructor to initialize the instance, and returns a reference to the instance.</span></span> <span data-ttu-id="9e78d-115">以下语句创建两个 Point 对象，并将对这些对象的引用存储在两个变量中：</span><span class="sxs-lookup"><span data-stu-id="9e78d-115">The following statements create two Point objects and store references to those objects in two variables:</span></span>

[!code-csharp[PointExample](../../../samples/snippets/csharp/tour/classes-and-objects/Program.cs#L9-L10)]

<span data-ttu-id="9e78d-116">当无法再访问对象时，对象占用的内存会被自动回收。</span><span class="sxs-lookup"><span data-stu-id="9e78d-116">The memory occupied by an object is automatically reclaimed when the object is no longer reachable.</span></span> <span data-ttu-id="9e78d-117">既没必要，也无法在 C# 中显式解除分配对象。</span><span class="sxs-lookup"><span data-stu-id="9e78d-117">It is neither necessary nor possible to explicitly deallocate objects in C#.</span></span>

## <a name="members"></a><span data-ttu-id="9e78d-118">成员</span><span class="sxs-lookup"><span data-stu-id="9e78d-118">Members</span></span>

<span data-ttu-id="9e78d-119">类成员要么是静态成员，要么是实例成员。</span><span class="sxs-lookup"><span data-stu-id="9e78d-119">The members of a class are either static members or instance members.</span></span> <span data-ttu-id="9e78d-120">静态成员属于类，而实例成员则属于对象（类实例）。</span><span class="sxs-lookup"><span data-stu-id="9e78d-120">Static members belong to classes, and instance members belong to objects (instances of classes).</span></span>

<span data-ttu-id="9e78d-121">下面概述了类可以包含的成员类型。</span><span class="sxs-lookup"><span data-stu-id="9e78d-121">The following provides an overview of the kinds of members a class can contain.</span></span>

* <span data-ttu-id="9e78d-122">常量</span><span class="sxs-lookup"><span data-stu-id="9e78d-122">Constants</span></span>
    - <span data-ttu-id="9e78d-123">与类相关联的常量值</span><span class="sxs-lookup"><span data-stu-id="9e78d-123">Constant values associated with the class</span></span>
* <span data-ttu-id="9e78d-124">字段</span><span class="sxs-lookup"><span data-stu-id="9e78d-124">Fields</span></span>
    - <span data-ttu-id="9e78d-125">类的常量</span><span class="sxs-lookup"><span data-stu-id="9e78d-125">Variables of the class</span></span>
* <span data-ttu-id="9e78d-126">方法</span><span class="sxs-lookup"><span data-stu-id="9e78d-126">Methods</span></span>
    - <span data-ttu-id="9e78d-127">类可以执行的计算和操作</span><span class="sxs-lookup"><span data-stu-id="9e78d-127">Computations and actions that can be performed by the class</span></span>
* <span data-ttu-id="9e78d-128">属性</span><span class="sxs-lookup"><span data-stu-id="9e78d-128">Properties</span></span>
    - <span data-ttu-id="9e78d-129">与读取和写入类的已命名属性相关联的操作</span><span class="sxs-lookup"><span data-stu-id="9e78d-129">Actions associated with reading and writing named properties of the class</span></span>
* <span data-ttu-id="9e78d-130">索引器</span><span class="sxs-lookup"><span data-stu-id="9e78d-130">Indexers</span></span>
    - <span data-ttu-id="9e78d-131">与将类实例编入索引（像处理数组一样）相关联的操作</span><span class="sxs-lookup"><span data-stu-id="9e78d-131">Actions associated with indexing instances of the class like an array</span></span>
* <span data-ttu-id="9e78d-132">事件</span><span class="sxs-lookup"><span data-stu-id="9e78d-132">Events</span></span>
    - <span data-ttu-id="9e78d-133">类可以生成的通知</span><span class="sxs-lookup"><span data-stu-id="9e78d-133">Notifications that can be generated by the class</span></span>
* <span data-ttu-id="9e78d-134">运算符</span><span class="sxs-lookup"><span data-stu-id="9e78d-134">Operators</span></span>
    - <span data-ttu-id="9e78d-135">类支持的转换和表达式运算符</span><span class="sxs-lookup"><span data-stu-id="9e78d-135">Conversions and expression operators supported by the class</span></span>
* <span data-ttu-id="9e78d-136">构造函数</span><span class="sxs-lookup"><span data-stu-id="9e78d-136">Constructors</span></span>
    - <span data-ttu-id="9e78d-137">初始化类实例或类本身所需的操作</span><span class="sxs-lookup"><span data-stu-id="9e78d-137">Actions required to initialize instances of the class or the class itself</span></span>
* <span data-ttu-id="9e78d-138">终结器</span><span class="sxs-lookup"><span data-stu-id="9e78d-138">Finalizers</span></span>
    - <span data-ttu-id="9e78d-139">永久放弃类实例前要执行的操作</span><span class="sxs-lookup"><span data-stu-id="9e78d-139">Actions to perform before instances of the class are permanently discarded</span></span>
* <span data-ttu-id="9e78d-140">类型</span><span class="sxs-lookup"><span data-stu-id="9e78d-140">Types</span></span>
    - <span data-ttu-id="9e78d-141">类声明的嵌套类型</span><span class="sxs-lookup"><span data-stu-id="9e78d-141">Nested types declared by the class</span></span>

## <a name="accessibility"></a><span data-ttu-id="9e78d-142">可访问性</span><span class="sxs-lookup"><span data-stu-id="9e78d-142">Accessibility</span></span>

<span data-ttu-id="9e78d-143">每个类成员都有关联的可访问性，用于控制能够访问成员的程序文本区域。</span><span class="sxs-lookup"><span data-stu-id="9e78d-143">Each member of a class has an associated accessibility, which controls the regions of program text that are able to access the member.</span></span> <span data-ttu-id="9e78d-144">可访问性有五种可能的形式。</span><span class="sxs-lookup"><span data-stu-id="9e78d-144">There are five possible forms of accessibility.</span></span> <span data-ttu-id="9e78d-145">总结如下。</span><span class="sxs-lookup"><span data-stu-id="9e78d-145">These are summarized below.</span></span>

* `public`
    - <span data-ttu-id="9e78d-146">访问不受限</span><span class="sxs-lookup"><span data-stu-id="9e78d-146">Access not limited</span></span>
* `protected`
    - <span data-ttu-id="9e78d-147">只能访问此类或派生自此类的类</span><span class="sxs-lookup"><span data-stu-id="9e78d-147">Access limited to this class or classes derived from this class</span></span>
* `internal`
    - <span data-ttu-id="9e78d-148">访问限于当前程序集（.exe、.dll 等）</span><span class="sxs-lookup"><span data-stu-id="9e78d-148">Access limited to the current assembly (.exe, .dll, etc.)</span></span>
* `protected internal`
    - <span data-ttu-id="9e78d-149">访问限于包含类或派生自包含类的类</span><span class="sxs-lookup"><span data-stu-id="9e78d-149">Access limited to the containing class or classes derived from the containing class</span></span>
* `private`
    - <span data-ttu-id="9e78d-150">只能访问此类</span><span class="sxs-lookup"><span data-stu-id="9e78d-150">Access limited to this class</span></span>
* `private protected`
    - <span data-ttu-id="9e78d-151">访问限于同一程序集中的包含类或派生自包含类的类</span><span class="sxs-lookup"><span data-stu-id="9e78d-151">Access limited to the containing class or classes derived from the containing type within the same assembly</span></span>

## <a name="type-parameters"></a><span data-ttu-id="9e78d-152">类型参数</span><span class="sxs-lookup"><span data-stu-id="9e78d-152">Type parameters</span></span>

<span data-ttu-id="9e78d-153">类定义可能会按如下方式指定一组类型参数：在类名后面用尖括号括住类型参数名称列表。</span><span class="sxs-lookup"><span data-stu-id="9e78d-153">A class definition may specify a set of type parameters by following the class name with angle brackets enclosing a list of type parameter names.</span></span> <span data-ttu-id="9e78d-154">然后，可以在类声明的主体中使用类型参数来定义类成员。</span><span class="sxs-lookup"><span data-stu-id="9e78d-154">The type parameters can then be used in the body of the class declarations to define the members of the class.</span></span> <span data-ttu-id="9e78d-155">在以下示例中，`Pair` 的类型参数是 `TFirst` 和 `TSecond`：</span><span class="sxs-lookup"><span data-stu-id="9e78d-155">In the following example, the type parameters of `Pair` are `TFirst` and `TSecond`:</span></span>

[!code-csharp[Pair](../../../samples/snippets/csharp/tour/classes-and-objects/Pair.cs#L3-L7)]

<span data-ttu-id="9e78d-156">声明为需要使用类型参数的类类型被称为*泛型类类型*。</span><span class="sxs-lookup"><span data-stu-id="9e78d-156">A class type that is declared to take type parameters is called a *generic class type*.</span></span> <span data-ttu-id="9e78d-157">结构、接口和委托类型也可以是泛型。</span><span class="sxs-lookup"><span data-stu-id="9e78d-157">Struct, interface and delegate types can also be generic.</span></span>
<span data-ttu-id="9e78d-158">使用泛型类时，必须为每个类型参数提供类型自变量：</span><span class="sxs-lookup"><span data-stu-id="9e78d-158">When the generic class is used, type arguments must be provided for each of the type parameters:</span></span>

[!code-csharp[PairExample](../../../samples/snippets/csharp/tour/classes-and-objects/Program.cs#L15-L17)]

<span data-ttu-id="9e78d-159">包含类型自变量的泛型类型（如上面的 `Pair<int,string>`）被称为*构造泛型类型*。</span><span class="sxs-lookup"><span data-stu-id="9e78d-159">A generic type with type arguments provided, like `Pair<int,string>` above, is called a *constructed type*.</span></span>

## <a name="base-classes"></a><span data-ttu-id="9e78d-160">基类</span><span class="sxs-lookup"><span data-stu-id="9e78d-160">Base classes</span></span>

<span data-ttu-id="9e78d-161">类声明可能会按如下方式指定基类：在类名和类型参数后面编写冒号和基类名。</span><span class="sxs-lookup"><span data-stu-id="9e78d-161">A class declaration may specify a base class by following the class name and type parameters with a colon and the name of the base class.</span></span> <span data-ttu-id="9e78d-162">省略基类规范与从 `object` 类型派生相同。</span><span class="sxs-lookup"><span data-stu-id="9e78d-162">Omitting a base class specification is the same as deriving from type `object`.</span></span> <span data-ttu-id="9e78d-163">在以下示例中，`Point3D` 的基类是 `Point`，`Point` 的基类是 `object`：</span><span class="sxs-lookup"><span data-stu-id="9e78d-163">In the following example, the base class of `Point3D` is `Point`, and the base class of `Point` is `object`:</span></span>

[!code-csharp[Point3DClass](../../../samples/snippets/csharp/tour/classes-and-objects/Point.cs#L3-L20)]

<span data-ttu-id="9e78d-164">类继承其基类的成员。</span><span class="sxs-lookup"><span data-stu-id="9e78d-164">A class inherits the members of its base class.</span></span> <span data-ttu-id="9e78d-165">继承是指隐式包含其基类的所有成员的类，实例和静态构造函数以及基类的终结器除外。</span><span class="sxs-lookup"><span data-stu-id="9e78d-165">Inheritance means that a class implicitly contains all members of its base class, except for the instance and static constructors, and the finalizers of the base class.</span></span> <span data-ttu-id="9e78d-166">派生类可以其继承的类添加新成员，但无法删除继承成员的定义。</span><span class="sxs-lookup"><span data-stu-id="9e78d-166">A derived class can add new members to those it inherits, but it cannot remove the definition of an inherited member.</span></span> <span data-ttu-id="9e78d-167">在上面的示例中，`Point3D` 从 `Point` 继承了 `x` 和 `y` 字段，每个 `Point3D` 实例均包含三个字段（`x`、`y` 和 `z`）。</span><span class="sxs-lookup"><span data-stu-id="9e78d-167">In the previous example, `Point3D` inherits the `x` and `y` fields from `Point`, and every `Point3D` instance contains three fields, `x`, `y`, and `z`.</span></span>

<span data-ttu-id="9e78d-168">可以将类类型隐式转换成其任意基类类型。</span><span class="sxs-lookup"><span data-stu-id="9e78d-168">An implicit conversion exists from a class type to any of its base class types.</span></span> <span data-ttu-id="9e78d-169">因此，类类型的变量可以引用相应类的实例或任意派生类的实例。</span><span class="sxs-lookup"><span data-stu-id="9e78d-169">Therefore, a variable of a class type can reference an instance of that class or an instance of any derived class.</span></span> <span data-ttu-id="9e78d-170">例如，类声明如上，`Point` 类型的变量可以引用 `Point` 或 `Point3D`：</span><span class="sxs-lookup"><span data-stu-id="9e78d-170">For example, given the previous class declarations, a variable of type `Point` can reference either a `Point` or a `Point3D`:</span></span>

[!code-csharp[Point3DExample](../../../samples/snippets/csharp/tour/classes-and-objects/Program.cs#L22-L23)]

## <a name="fields"></a><span data-ttu-id="9e78d-171">字段</span><span class="sxs-lookup"><span data-stu-id="9e78d-171">Fields</span></span>

<span data-ttu-id="9e78d-172">*字段*是与类或类实例相关联的变量。</span><span class="sxs-lookup"><span data-stu-id="9e78d-172">A *field* is a variable that is associated with a class or with an instance of a class.</span></span>

<span data-ttu-id="9e78d-173">使用静态修饰符声明的字段定义的是静态字段。</span><span class="sxs-lookup"><span data-stu-id="9e78d-173">A field declared with the static modifier defines a static field.</span></span> <span data-ttu-id="9e78d-174">静态字段只指明一个存储位置。</span><span class="sxs-lookup"><span data-stu-id="9e78d-174">A static field identifies exactly one storage location.</span></span> <span data-ttu-id="9e78d-175">无论创建多少个类实例，永远只有一个静态字段副本。</span><span class="sxs-lookup"><span data-stu-id="9e78d-175">No matter how many instances of a class are created, there is only ever one copy of a static field.</span></span>

<span data-ttu-id="9e78d-176">不使用静态修饰符声明的字段定义的是实例字段。</span><span class="sxs-lookup"><span data-stu-id="9e78d-176">A field declared without the static modifier defines an instance field.</span></span> <span data-ttu-id="9e78d-177">每个类实例均包含相应类的所有实例字段的单独副本。</span><span class="sxs-lookup"><span data-stu-id="9e78d-177">Every instance of a class contains a separate copy of all the instance fields of that class.</span></span>

<span data-ttu-id="9e78d-178">在以下示例中，每个 `Color` 类实例均包含 `r`、`g` 和 `b` 实例字段的单独副本，但分别只包含 `Black`、`White`、`Red`、`Green` 和 `Blue` 静态字段的一个副本：</span><span class="sxs-lookup"><span data-stu-id="9e78d-178">In the following example, each instance of the `Color` class has a separate copy of the `r`, `g`, and `b` instance fields, but there is only one copy of the `Black`, `White`, `Red`, `Green`, and `Blue` static fields:</span></span>

[!code-csharp[ColorClass](../../../samples/snippets/csharp/tour/classes-and-objects/Color.cs#L3-L17)]

<span data-ttu-id="9e78d-179">如上面的示例所示，可以使用 `readonly` 修饰符声明*只读字段*。</span><span class="sxs-lookup"><span data-stu-id="9e78d-179">As shown in the previous example, *read-only fields* may be declared with a `readonly` modifier.</span></span> <span data-ttu-id="9e78d-180">只能在字段声明期间或在同一个类的构造函数中向 `readonly` 字段赋值。</span><span class="sxs-lookup"><span data-stu-id="9e78d-180">Assignment to a `readonly` field can only occur as part of the field’s declaration or in a constructor in the same class.</span></span>

## <a name="methods"></a><span data-ttu-id="9e78d-181">方法</span><span class="sxs-lookup"><span data-stu-id="9e78d-181">Methods</span></span>

<span data-ttu-id="9e78d-182">*方法*是实现对象或类可执行的计算或操作的成员。</span><span class="sxs-lookup"><span data-stu-id="9e78d-182">A *method* is a member that implements a computation or action that can be performed by an object or class.</span></span> <span data-ttu-id="9e78d-183">*静态方法*是通过类进行访问。</span><span class="sxs-lookup"><span data-stu-id="9e78d-183">*Static methods* are accessed through the class.</span></span> <span data-ttu-id="9e78d-184">*实例方法*是通过类实例进行访问。</span><span class="sxs-lookup"><span data-stu-id="9e78d-184">*Instance methods* are accessed through instances of the class.</span></span>

<span data-ttu-id="9e78d-185">方法可能具有*参数*列表，用于表示传递给方法的值或变量引用；并具有*返回类型*，用于指定方法计算并返回的值的类型。</span><span class="sxs-lookup"><span data-stu-id="9e78d-185">Methods may have a list of *parameters*, which represent values or variable references passed to the method, and a *return type*, which specifies the type of the value computed and returned by the method.</span></span> <span data-ttu-id="9e78d-186">如果方法未返回值，则其返回类型为 `void`。</span><span class="sxs-lookup"><span data-stu-id="9e78d-186">A method’s return type is `void` if it does not return a value.</span></span>

<span data-ttu-id="9e78d-187">方法可能也包含一组类型参数，必须在调用方法时指定类型自变量，这一点与类型一样。</span><span class="sxs-lookup"><span data-stu-id="9e78d-187">Like types, methods may also have a set of type parameters, for which type arguments must be specified when the method is called.</span></span> <span data-ttu-id="9e78d-188">与类型不同的是，通常可以根据方法调用的自变量推断出类型自变量，无需显式指定。</span><span class="sxs-lookup"><span data-stu-id="9e78d-188">Unlike types, the type arguments can often be inferred from the arguments of a method call and need not be explicitly given.</span></span>

<span data-ttu-id="9e78d-189">在声明方法的类中，方法的*签名*必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="9e78d-189">The *signature* of a method must be unique in the class in which the method is declared.</span></span> <span data-ttu-id="9e78d-190">方法签名包含方法名称、类型参数数量及其参数的数量、修饰符和类型。</span><span class="sxs-lookup"><span data-stu-id="9e78d-190">The signature of a method consists of the name of the method, the number of type parameters and the number, modifiers, and types of its parameters.</span></span> <span data-ttu-id="9e78d-191">方法签名不包含返回类型。</span><span class="sxs-lookup"><span data-stu-id="9e78d-191">The signature of a method does not include the return type.</span></span>

### <a name="parameters"></a><span data-ttu-id="9e78d-192">参数</span><span class="sxs-lookup"><span data-stu-id="9e78d-192">Parameters</span></span>

<span data-ttu-id="9e78d-193">参数用于将值或变量引用传递给方法。</span><span class="sxs-lookup"><span data-stu-id="9e78d-193">Parameters are used to pass values or variable references to methods.</span></span> <span data-ttu-id="9e78d-194">方法参数从调用方法时指定的*自变量*中获取其实际值。</span><span class="sxs-lookup"><span data-stu-id="9e78d-194">The parameters of a method get their actual values from the *arguments* that are specified when the method is invoked.</span></span> <span data-ttu-id="9e78d-195">有四类参数：值参数、引用参数、输出参数和参数数组。</span><span class="sxs-lookup"><span data-stu-id="9e78d-195">There are four kinds of parameters: value parameters, reference parameters, output parameters, and parameter arrays.</span></span>

<span data-ttu-id="9e78d-196">值参数用于传递输入自变量。</span><span class="sxs-lookup"><span data-stu-id="9e78d-196">A *value parameter* is used for passing input arguments.</span></span> <span data-ttu-id="9e78d-197">值参数对应于局部变量，从为其传递的自变量中获取初始值。</span><span class="sxs-lookup"><span data-stu-id="9e78d-197">A value parameter corresponds to a local variable that gets its initial value from the argument that was passed for the parameter.</span></span> <span data-ttu-id="9e78d-198">修改值参数不会影响为其传递的自变量。</span><span class="sxs-lookup"><span data-stu-id="9e78d-198">Modifications to a value parameter do not affect the argument that was passed for the parameter.</span></span> 

<span data-ttu-id="9e78d-199">可以指定默认值，从而省略相应的自变量，这样值参数就是可选的。</span><span class="sxs-lookup"><span data-stu-id="9e78d-199">Value parameters can be optional, by specifying a default value so that corresponding arguments can be omitted.</span></span>

<span data-ttu-id="9e78d-200">引用参数用于按引用传递自变量。</span><span class="sxs-lookup"><span data-stu-id="9e78d-200">A *reference parameter* is used for passing arguments by reference.</span></span> <span data-ttu-id="9e78d-201">为引用参数传递的自变量必须是具有明确值的变量，并且在方法执行期间，引用参数指明的存储位置与自变量相同。</span><span class="sxs-lookup"><span data-stu-id="9e78d-201">The argument passed for a reference parameter must be a variable with a definite value, and during execution of the method, the reference parameter represents the same storage location as the argument variable.</span></span> <span data-ttu-id="9e78d-202">引用参数使用 `ref` 修饰符进行声明。</span><span class="sxs-lookup"><span data-stu-id="9e78d-202">A reference parameter is declared with the `ref` modifier.</span></span> <span data-ttu-id="9e78d-203">下面的示例展示了如何使用 `ref` 参数。</span><span class="sxs-lookup"><span data-stu-id="9e78d-203">The following example shows the use of `ref` parameters.</span></span>

[!code-csharp[swapExample](../../../samples/snippets/csharp/tour/classes-and-objects/RefExample.cs#L3-L18)]

<span data-ttu-id="9e78d-204">输出参数用于按引用传递自变量。</span><span class="sxs-lookup"><span data-stu-id="9e78d-204">An *output parameter* is used for passing arguments by reference.</span></span> <span data-ttu-id="9e78d-205">输出参数与引用参数类似，不同之处在于，不要求向调用方提供的自变量显式赋值。</span><span class="sxs-lookup"><span data-stu-id="9e78d-205">It's similar to a reference parameter, except that it doesn't require that you explicitly assign a value to the caller-provided argument.</span></span> <span data-ttu-id="9e78d-206">输出参数使用 `out` 修饰符进行声明。</span><span class="sxs-lookup"><span data-stu-id="9e78d-206">An output parameter is declared with the `out` modifier.</span></span> <span data-ttu-id="9e78d-207">下面的示例演示如何通过 C# 7 中引入的语法使用 `out` 参数。</span><span class="sxs-lookup"><span data-stu-id="9e78d-207">The following example shows the use of `out` parameters using the syntax introduced in C# 7.</span></span>

[!code-csharp[OutExample](../../../samples/snippets/csharp/tour/classes-and-objects/OutExample.cs#L3-L17)]

<span data-ttu-id="9e78d-208">*参数数组*允许向方法传递数量不定的自变量。</span><span class="sxs-lookup"><span data-stu-id="9e78d-208">A *parameter array* permits a variable number of arguments to be passed to a method.</span></span> <span data-ttu-id="9e78d-209">参数数组使用 `params` 修饰符进行声明。</span><span class="sxs-lookup"><span data-stu-id="9e78d-209">A parameter array is declared with the `params` modifier.</span></span> <span data-ttu-id="9e78d-210">参数数组只能是方法的最后一个参数，且参数数组的类型必须是一维数组类型。</span><span class="sxs-lookup"><span data-stu-id="9e78d-210">Only the last parameter of a method can be a parameter array, and the type of a parameter array must be a single-dimensional array type.</span></span> <span data-ttu-id="9e78d-211"><xref:System.Console?displayProperty=nameWithType> 类的 Write 和 WriteLine 方法是参数数组用法的典型示例。</span><span class="sxs-lookup"><span data-stu-id="9e78d-211">The Write and WriteLine methods of the <xref:System.Console?displayProperty=nameWithType> class are good examples of parameter array usage.</span></span> <span data-ttu-id="9e78d-212">它们的声明方式如下。</span><span class="sxs-lookup"><span data-stu-id="9e78d-212">They are declared as follows.</span></span>

[!code-csharp[ConsoleExample](../../../samples/snippets/csharp/tour/classes-and-objects/Program.cs#L78-L83)]

<span data-ttu-id="9e78d-213">在使用参数数组的方法中，参数数组的行为与数组类型的常规参数完全相同。</span><span class="sxs-lookup"><span data-stu-id="9e78d-213">Within a method that uses a parameter array, the parameter array behaves exactly like a regular parameter of an array type.</span></span> <span data-ttu-id="9e78d-214">不过，在调用包含参数数组的方法时，要么可以传递参数数组类型的一个自变量，要么可以传递参数数组的元素类型的任意数量自变量。</span><span class="sxs-lookup"><span data-stu-id="9e78d-214">However, in an invocation of a method with a parameter array, it is possible to pass either a single argument of the parameter array type or any number of arguments of the element type of the parameter array.</span></span> <span data-ttu-id="9e78d-215">在后一种情况中，数组实例会自动创建，并初始化为包含给定的自变量。</span><span class="sxs-lookup"><span data-stu-id="9e78d-215">In the latter case, an array instance is automatically created and initialized with the given arguments.</span></span> <span data-ttu-id="9e78d-216">以下示例：</span><span class="sxs-lookup"><span data-stu-id="9e78d-216">This example</span></span>

[!code-csharp[StringFormat](../../../samples/snippets/csharp/tour/classes-and-objects/Program.cs#L55-L55)]

<span data-ttu-id="9e78d-217">等同于编写以下代码：</span><span class="sxs-lookup"><span data-stu-id="9e78d-217">is equivalent to writing the following.</span></span>

[!code-csharp[StringFormat2](../../../samples/snippets/csharp/tour/classes-and-objects/Program.cs#L30-L35)]

### <a name="method-body-and-local-variables"></a><span data-ttu-id="9e78d-218">方法主体和局部变量</span><span class="sxs-lookup"><span data-stu-id="9e78d-218">Method body and local variables</span></span>

<span data-ttu-id="9e78d-219">方法主体指定了在调用方法时执行的语句。</span><span class="sxs-lookup"><span data-stu-id="9e78d-219">A method’s body specifies the statements to execute when the method is invoked.</span></span>

<span data-ttu-id="9e78d-220">方法主体可以声明特定于方法调用的变量。</span><span class="sxs-lookup"><span data-stu-id="9e78d-220">A method body can declare variables that are specific to the invocation of the method.</span></span> <span data-ttu-id="9e78d-221">此类变量称为*局部变量*。</span><span class="sxs-lookup"><span data-stu-id="9e78d-221">Such variables are called *local variables*.</span></span> <span data-ttu-id="9e78d-222">局部变量声明指定了类型名称、变量名称以及可能的初始值。</span><span class="sxs-lookup"><span data-stu-id="9e78d-222">A local variable declaration specifies a type name, a variable name, and possibly an initial value.</span></span> <span data-ttu-id="9e78d-223">下面的示例声明了初始值为零的局部变量 `i` 和无初始值的局部变量 `j`。</span><span class="sxs-lookup"><span data-stu-id="9e78d-223">The following example declares a local variable `i` with an initial value of zero and a local variable `j` with no initial value.</span></span>

[!code-csharp[Squares](../../../samples/snippets/csharp/tour/classes-and-objects/Squares.cs#L3-L17)]

<span data-ttu-id="9e78d-224">C# 要求必须先*明确赋值*局部变量，然后才能获取其值。</span><span class="sxs-lookup"><span data-stu-id="9e78d-224">C# requires a local variable to be *definitely assigned* before its value can be obtained.</span></span> <span data-ttu-id="9e78d-225">例如，如果上面的 `i` 声明未包含初始值，那么编译器会在后面使用 `i` 时报告错误，因为在后面使用时 `i` 不会在程序中进行明确赋值。</span><span class="sxs-lookup"><span data-stu-id="9e78d-225">For example, if the declaration of the previous `i` did not include an initial value, the compiler would report an error for the subsequent usages of `i` because `i` would not be definitely assigned at those points in the program.</span></span>

<span data-ttu-id="9e78d-226">方法可以使用 `return` 语句将控制权返回给调用方。</span><span class="sxs-lookup"><span data-stu-id="9e78d-226">A method can use `return` statements to return control to its caller.</span></span> <span data-ttu-id="9e78d-227">在返回 `void` 的方法中，`return` 语句无法指定表达式。</span><span class="sxs-lookup"><span data-stu-id="9e78d-227">In a method returning `void`, `return` statements cannot specify an expression.</span></span> <span data-ttu-id="9e78d-228">在不返回 void 的方法中，`return` 语句必须包括用于计算返回值的表达式。</span><span class="sxs-lookup"><span data-stu-id="9e78d-228">In a method returning non-void, `return` statements must include an expression that computes the return value.</span></span>

### <a name="static-and-instance-methods"></a><span data-ttu-id="9e78d-229">静态和实例方法</span><span class="sxs-lookup"><span data-stu-id="9e78d-229">Static and instance methods</span></span>

<span data-ttu-id="9e78d-230">使用静态修饰符声明的方法是*静态方法*。</span><span class="sxs-lookup"><span data-stu-id="9e78d-230">A method declared with a static modifier is a *static method*.</span></span> <span data-ttu-id="9e78d-231">静态方法不对特定的实例起作用，只能直接访问静态成员。</span><span class="sxs-lookup"><span data-stu-id="9e78d-231">A static method does not operate on a specific instance and can only directly access static members.</span></span>

<span data-ttu-id="9e78d-232">不使用静态修饰符声明的方法是*实例方法*。</span><span class="sxs-lookup"><span data-stu-id="9e78d-232">A method declared without a static modifier is an *instance method*.</span></span> <span data-ttu-id="9e78d-233">实例方法对特定的实例起作用，并能够访问静态和实例成员。</span><span class="sxs-lookup"><span data-stu-id="9e78d-233">An instance method operates on a specific instance and can access both static and instance members.</span></span> <span data-ttu-id="9e78d-234">其中调用实例方法的实例可以作为 `this` 显式访问。</span><span class="sxs-lookup"><span data-stu-id="9e78d-234">The instance on which an instance method was invoked can be explicitly accessed as `this`.</span></span> <span data-ttu-id="9e78d-235">在静态方法中引用 `this` 会生成错误。</span><span class="sxs-lookup"><span data-stu-id="9e78d-235">It is an error to refer to `this` in a static method.</span></span>

<span data-ttu-id="9e78d-236">以下 `Entity` 类包含静态和实例成员。</span><span class="sxs-lookup"><span data-stu-id="9e78d-236">The following `Entity` class has both static and instance members.</span></span>

[!code-csharp[Entity](../../../samples/snippets/csharp/tour/classes-and-objects/Entity.cs#L16-L36)]

<span data-ttu-id="9e78d-237">每个 `Entity` 实例均有一个序列号（很可能包含此处未显示的其他一些信息）。</span><span class="sxs-lookup"><span data-stu-id="9e78d-237">Each `Entity` instance contains a serial number (and presumably some other information that is not shown here).</span></span> <span data-ttu-id="9e78d-238">`Entity` 构造函数（类似于实例方法）将新实例初始化为包含下一个可用的序列号。</span><span class="sxs-lookup"><span data-stu-id="9e78d-238">The `Entity` constructor (which is like an instance method) initializes the new instance with the next available serial number.</span></span> <span data-ttu-id="9e78d-239">由于构造函数是实例成员，因此可以访问 `serialNo` 实例字段和 `nextSerialNo` 静态字段。</span><span class="sxs-lookup"><span data-stu-id="9e78d-239">Because the constructor is an instance member, it is permitted to access both the `serialNo` instance field and the `nextSerialNo` static field.</span></span>

<span data-ttu-id="9e78d-240">`GetNextSerialNo` 和 `SetNextSerialNo` 静态方法可以访问 `nextSerialNo` 静态字段，但如果直接访问 `serialNo` 实例字段，则会生成错误。</span><span class="sxs-lookup"><span data-stu-id="9e78d-240">The `GetNextSerialNo` and `SetNextSerialNo` static methods can access the `nextSerialNo` static field, but it would be an error for them to directly access the `serialNo` instance field.</span></span>

<span data-ttu-id="9e78d-241">下面的示例展示了如何使用 Entity 类。</span><span class="sxs-lookup"><span data-stu-id="9e78d-241">The following example shows the use of the Entity class.</span></span>

[!code-csharp[EntityExample](../../../samples/snippets/csharp/tour/classes-and-objects/Entity.cs#L3-L15)]

<span data-ttu-id="9e78d-242">请注意，`SetNextSerialNo` 和 `GetNextSerialNo` 静态方法是在类中调用，而 `GetSerialNo` 实例方法则是在类实例中调用。</span><span class="sxs-lookup"><span data-stu-id="9e78d-242">Note that the `SetNextSerialNo` and `GetNextSerialNo` static methods are invoked on the class whereas the `GetSerialNo` instance method is invoked on instances of the class.</span></span>

### <a name="virtual-override-and-abstract-methods"></a><span data-ttu-id="9e78d-243">虚方法、重写方法和抽象方法</span><span class="sxs-lookup"><span data-stu-id="9e78d-243">Virtual, override, and abstract methods</span></span>

<span data-ttu-id="9e78d-244">如果实例方法声明中有 `virtual` 修饰符，可以将实例方法称为“*虚方法*”。</span><span class="sxs-lookup"><span data-stu-id="9e78d-244">When an instance method declaration includes a `virtual` modifier, the method is said to be a *virtual method*.</span></span> <span data-ttu-id="9e78d-245">如果没有 virtual 修饰符，可以将实例方法称为“*非虚方法*”。</span><span class="sxs-lookup"><span data-stu-id="9e78d-245">When no virtual modifier is present, the method is said to be a *nonvirtual method*.</span></span>

<span data-ttu-id="9e78d-246">调用虚方法时，为其调用方法的实例的*运行时类型*决定了要调用的实际方法实现代码。</span><span class="sxs-lookup"><span data-stu-id="9e78d-246">When a virtual method is invoked, the *run-time type* of the instance for which that invocation takes place determines the actual method implementation to invoke.</span></span> <span data-ttu-id="9e78d-247">调用非虚方法时，实例的*编译时类型*是决定性因素。</span><span class="sxs-lookup"><span data-stu-id="9e78d-247">In a nonvirtual method invocation, the *compile-time type* of the instance is the determining factor.</span></span>

<span data-ttu-id="9e78d-248">可以在派生类中*重写*虚方法。</span><span class="sxs-lookup"><span data-stu-id="9e78d-248">A virtual method can be *overridden* in a derived class.</span></span> <span data-ttu-id="9e78d-249">如果实例方法声明中有 override 修饰符，那么实例方法可以重写签名相同的继承虚方法。</span><span class="sxs-lookup"><span data-stu-id="9e78d-249">When an instance method declaration includes an override modifier, the method overrides an inherited virtual method with the same signature.</span></span> <span data-ttu-id="9e78d-250">但如果虚方法声明中引入新方法，重写方法声明通过提供相应方法的新实现代码，专门针对现有的继承虚方法。</span><span class="sxs-lookup"><span data-stu-id="9e78d-250">Whereas a virtual method declaration introduces a new method, an override method declaration specializes an existing inherited virtual method by providing a new implementation of that method.</span></span>

<span data-ttu-id="9e78d-251">*抽象方法*是没有实现代码的虚方法。</span><span class="sxs-lookup"><span data-stu-id="9e78d-251">An *abstract method* is a virtual method with no implementation.</span></span> <span data-ttu-id="9e78d-252">抽象方法使用 abstract 修饰符进行声明，只能在同样声明了 abstract 的类中使用。</span><span class="sxs-lookup"><span data-stu-id="9e78d-252">An abstract method is declared with the abstract modifier and is permitted only in a class that is also declared abstract.</span></span> <span data-ttu-id="9e78d-253">必须在所有非抽象派生类中重写抽象方法。</span><span class="sxs-lookup"><span data-stu-id="9e78d-253">An abstract method must be overridden in every non-abstract derived class.</span></span>

<span data-ttu-id="9e78d-254">下面的示例声明了一个抽象类 `Expression`，用于表示表达式树节点；还声明了三个派生类（`Constant`、`VariableReference` 和 `Operation`），用于实现常量、变量引用和算术运算的表达式树节点。</span><span class="sxs-lookup"><span data-stu-id="9e78d-254">The following example declares an abstract class, `Expression`, which represents an expression tree node, and three derived classes, `Constant`, `VariableReference`, and `Operation`, which implement expression tree nodes for constants, variable references, and arithmetic operations.</span></span> <span data-ttu-id="9e78d-255">（这与表达式树类型相似，但不能与之混淆）。</span><span class="sxs-lookup"><span data-stu-id="9e78d-255">(This is similar to, but not to be confused with the expression tree types).</span></span>

[!code-csharp[ExpressionClass](../../../samples/snippets/csharp/tour/classes-and-objects/Expressions.cs#L3-L61)]

<span data-ttu-id="9e78d-256">上面的四个类可用于进行算术表达式建模。</span><span class="sxs-lookup"><span data-stu-id="9e78d-256">The previous four classes can be used to model arithmetic expressions.</span></span> <span data-ttu-id="9e78d-257">例如，使用这些类的实例，可以按如下方式表示表达式 `x + 3`。</span><span class="sxs-lookup"><span data-stu-id="9e78d-257">For example, using instances of these classes, the expression `x + 3` can be represented as follows.</span></span>

[!code-csharp[ExpressionExample](../../../samples/snippets/csharp/tour/classes-and-objects/Program.cs#L40-L43)]

<span data-ttu-id="9e78d-258">调用 `Expression` 实例的 `Evaluate` 方法可以计算给定的表达式并生成 `double` 值。</span><span class="sxs-lookup"><span data-stu-id="9e78d-258">The `Evaluate` method of an `Expression` instance is invoked to evaluate the given expression and produce a `double` value.</span></span> <span data-ttu-id="9e78d-259">此方法需要使用自变量 `Dictionary`，其中包含变量名称（作为项键）和值（作为项值）。</span><span class="sxs-lookup"><span data-stu-id="9e78d-259">The method takes a `Dictionary` argument that contains variable names (as keys of the entries) and values (as values of the entries).</span></span> <span data-ttu-id="9e78d-260">因为 `Evaluate` 是一个抽象方法，因此派生自 `Expression` 的非抽象类必须替代 `Evaluate`。</span><span class="sxs-lookup"><span data-stu-id="9e78d-260">Because `Evaluate` is an abstract method, non-abstract classes derived from `Expression` must override `Evaluate`.</span></span>

<span data-ttu-id="9e78d-261">`Constant` 的 `Evaluate` 实现代码只返回存储的常量。</span><span class="sxs-lookup"><span data-stu-id="9e78d-261">A `Constant`'s implementation of `Evaluate` simply returns the stored constant.</span></span> <span data-ttu-id="9e78d-262">`VariableReference` 实现代码查找字典中的变量名称，并返回结果值。</span><span class="sxs-lookup"><span data-stu-id="9e78d-262">A `VariableReference`'s implementation looks up the variable name in the dictionary and returns the resulting value.</span></span> <span data-ttu-id="9e78d-263">`Operation` 实现代码先计算左右操作数（以递归方式调用其 `Evaluate` 方法），然后执行给定的算术运算。</span><span class="sxs-lookup"><span data-stu-id="9e78d-263">An `Operation`'s implementation first evaluates the left and right operands (by recursively invoking their `Evaluate` methods) and then performs the given arithmetic operation.</span></span>

<span data-ttu-id="9e78d-264">以下程序使用 `Expression` 类根据不同的 `x` 和 `y` 值计算表达式 `x * (y + 2)`。</span><span class="sxs-lookup"><span data-stu-id="9e78d-264">The following program uses the `Expression` classes to evaluate the expression `x * (y + 2)` for different values of `x` and `y`.</span></span>

[!code-csharp[ExpressionUsage](../../../samples/snippets/csharp/tour/classes-and-objects/Expressions.cs#L66-L89)]

### <a name="method-overloading"></a><span data-ttu-id="9e78d-265">方法重载</span><span class="sxs-lookup"><span data-stu-id="9e78d-265">Method overloading</span></span>

<span data-ttu-id="9e78d-266">借助方法*重载*，同一类中可以有多个同名的方法，只要这些方法具有唯一签名即可。</span><span class="sxs-lookup"><span data-stu-id="9e78d-266">Method *overloading* permits multiple methods in the same class to have the same name as long as they have unique signatures.</span></span> <span data-ttu-id="9e78d-267">编译如何调用重载的方法时，编译器使用*重载决策*来确定要调用的特定方法。</span><span class="sxs-lookup"><span data-stu-id="9e78d-267">When compiling an invocation of an overloaded method, the compiler uses *overload resolution* to determine the specific method to invoke.</span></span> <span data-ttu-id="9e78d-268">重载决策查找与自变量最匹配的方法；如果找不到最佳匹配项，则会报告错误。</span><span class="sxs-lookup"><span data-stu-id="9e78d-268">Overload resolution finds the one method that best matches the arguments or reports an error if no single best match can be found.</span></span> <span data-ttu-id="9e78d-269">下面的示例展示了重载决策的实际工作方式。</span><span class="sxs-lookup"><span data-stu-id="9e78d-269">The following example shows overload resolution in effect.</span></span> <span data-ttu-id="9e78d-270">`Main` 方法中每个调用的注释指明了实际调用的方法。</span><span class="sxs-lookup"><span data-stu-id="9e78d-270">The comment for each invocation in the `Main` method shows which method is actually invoked.</span></span>

[!code-csharp[OverloadUsage](../../../samples/snippets/csharp/tour/classes-and-objects/Overloading.cs#L3-L41)]

<span data-ttu-id="9e78d-271">如示例所示，可以随时将自变量显式转换成确切的参数类型，并/或显式提供类型自变量，从而选择特定的方法。</span><span class="sxs-lookup"><span data-stu-id="9e78d-271">As shown by the example, a particular method can always be selected by explicitly casting the arguments to the exact parameter types and/or explicitly supplying type arguments.</span></span>

## <a name="other-function-members"></a><span data-ttu-id="9e78d-272">其他函数成员</span><span class="sxs-lookup"><span data-stu-id="9e78d-272">Other function members</span></span>

<span data-ttu-id="9e78d-273">包含可执行代码的成员统称为类的*函数成员*。</span><span class="sxs-lookup"><span data-stu-id="9e78d-273">Members that contain executable code are collectively known as the *function members* of a class.</span></span> <span data-ttu-id="9e78d-274">上一部分介绍了作为主要函数成员类型的方法。</span><span class="sxs-lookup"><span data-stu-id="9e78d-274">The preceding section describes methods, which are the primary kind of function members.</span></span> <span data-ttu-id="9e78d-275">此部分将介绍 C# 支持的其他类型函数成员：构造函数、属性、索引器、事件、运算符和终结器。</span><span class="sxs-lookup"><span data-stu-id="9e78d-275">This section describes the other kinds of function members supported by C#: constructors, properties, indexers, events, operators, and finalizers.</span></span>

<span data-ttu-id="9e78d-276">下面的示例展示了 List<T> 泛型类，用于实现对象的可扩充列表。</span><span class="sxs-lookup"><span data-stu-id="9e78d-276">The following shows a generic class called List<T>, which implements a growable list of objects.</span></span> <span data-ttu-id="9e78d-277">此类包含最常见类型函数成员的多个示例。</span><span class="sxs-lookup"><span data-stu-id="9e78d-277">The class contains several examples of the most common kinds of function members.</span></span>

[!code-csharp[ListClass](../../../samples/snippets/csharp/tour/classes-and-objects/ListBasedExamples.cs#L4-L89)]

### <a name="constructors"></a><span data-ttu-id="9e78d-278">构造函数</span><span class="sxs-lookup"><span data-stu-id="9e78d-278">Constructors</span></span>

<span data-ttu-id="9e78d-279">C# 支持实例和静态构造函数。</span><span class="sxs-lookup"><span data-stu-id="9e78d-279">C# supports both instance and static constructors.</span></span> <span data-ttu-id="9e78d-280">*实例构造函数*是实现初始化类实例所需执行的操作的成员。</span><span class="sxs-lookup"><span data-stu-id="9e78d-280">An *instance constructor* is a member that implements the actions required to initialize an instance of a class.</span></span> <span data-ttu-id="9e78d-281">*静态构造函数*是实现在首次加载类时初始化类本身所需执行的操作的成员。</span><span class="sxs-lookup"><span data-stu-id="9e78d-281">A *static constructor* is a member that implements the actions required to initialize a class itself when it is first loaded.</span></span>

<span data-ttu-id="9e78d-282">构造函数的声明方式与方法一样，都没有返回类型，且与所含类同名。</span><span class="sxs-lookup"><span data-stu-id="9e78d-282">A constructor is declared like a method with no return type and the same name as the containing class.</span></span> <span data-ttu-id="9e78d-283">如果构造函数声明包含静态修饰符，则声明的是静态构造函数。</span><span class="sxs-lookup"><span data-stu-id="9e78d-283">If a constructor declaration includes a static modifier, it declares a static constructor.</span></span> <span data-ttu-id="9e78d-284">否则，声明的是实例构造函数。</span><span class="sxs-lookup"><span data-stu-id="9e78d-284">Otherwise, it declares an instance constructor.</span></span>

<span data-ttu-id="9e78d-285">实例构造函数可以重载，并能包含可选参数。</span><span class="sxs-lookup"><span data-stu-id="9e78d-285">Instance constructors can be overloaded, and can have optional parameters.</span></span> <span data-ttu-id="9e78d-286">例如，`List<T>` 类声明两个实例构造函数：一个没有参数，另一个需要使用 `int` 参数。</span><span class="sxs-lookup"><span data-stu-id="9e78d-286">For example, the `List<T>` class declares two instance constructors, one with no parameters and one that takes an `int` parameter.</span></span> <span data-ttu-id="9e78d-287">实例构造函数使用 `new` 运算符进行调用。</span><span class="sxs-lookup"><span data-stu-id="9e78d-287">Instance constructors are invoked using the `new` operator.</span></span> <span data-ttu-id="9e78d-288">下面的语句使用包含和不包含可选自变量的 `List` 类构造函数来分配两个 `List<string>` 实例。</span><span class="sxs-lookup"><span data-stu-id="9e78d-288">The following statements allocate two `List<string>` instances using the constructor of the `List` class with and without the optional argument.</span></span>

[!code-csharp[ListExample1](../../../samples/snippets/csharp/tour/classes-and-objects/ListBasedExamples.cs#L95-L96)]

<span data-ttu-id="9e78d-289">与其他成员不同，实例构造函数不能被继承，且类中只能包含实际已声明的实例构造函数。</span><span class="sxs-lookup"><span data-stu-id="9e78d-289">Unlike other members, instance constructors are not inherited, and a class has no instance constructors other than those actually declared in the class.</span></span> <span data-ttu-id="9e78d-290">如果没有为类提供实例构造函数，则会自动提供不含参数的空实例构造函数。</span><span class="sxs-lookup"><span data-stu-id="9e78d-290">If no instance constructor is supplied for a class, then an empty one with no parameters is automatically provided.</span></span>

### <a name="properties"></a><span data-ttu-id="9e78d-291">属性</span><span class="sxs-lookup"><span data-stu-id="9e78d-291">Properties</span></span>

<span data-ttu-id="9e78d-292">*属性*是字段的自然扩展。</span><span class="sxs-lookup"><span data-stu-id="9e78d-292">*Properties* are a natural extension of fields.</span></span> <span data-ttu-id="9e78d-293">两者都是包含关联类型的已命名成员，用于访问字段和属性的语法也是一样的。</span><span class="sxs-lookup"><span data-stu-id="9e78d-293">Both are named members with associated types, and the syntax for accessing fields and properties is the same.</span></span> <span data-ttu-id="9e78d-294">不过，与字段不同的是，属性不指明存储位置。</span><span class="sxs-lookup"><span data-stu-id="9e78d-294">However, unlike fields, properties do not denote storage locations.</span></span> <span data-ttu-id="9e78d-295">相反，属性包含*访问器*，用于指定在读取或写入属性值时要执行的语句。</span><span class="sxs-lookup"><span data-stu-id="9e78d-295">Instead, properties have *accessors* that specify the statements to be executed when their values are read or written.</span></span>

<span data-ttu-id="9e78d-296">属性的声明方式与字段类似，不同之处在于，属性声明以在分隔符 `{` 和 `}` 内写入的 get 访问器和/或 set 访问器结束，而不是以分号结束。</span><span class="sxs-lookup"><span data-stu-id="9e78d-296">A property is declared like a field, except that the declaration ends with a get accessor and/or a set accessor written between the delimiters `{` and `}` instead of ending in a semicolon.</span></span> <span data-ttu-id="9e78d-297">同时包含 get 访问器和 set 访问器的属性是*读写属性*，仅包含 get 访问器的属性是*只读属性*，仅包含 set 访问器的属性是*只写属性*。</span><span class="sxs-lookup"><span data-stu-id="9e78d-297">A property that has both a get accessor and a set accessor is a *read-write property*, a property that has only a get accessor is a *read-only property*, and a property that has only a set accessor is a *write-only property*.</span></span>

<span data-ttu-id="9e78d-298">get 访问器对应于包含属性类型的返回值的无参数方法。</span><span class="sxs-lookup"><span data-stu-id="9e78d-298">A get accessor corresponds to a parameterless method with a return value of the property type.</span></span> <span data-ttu-id="9e78d-299">如果在表达式中引用属性，除了作为赋值目标以外，调用的属性 get 访问器还可用于计算属性值。</span><span class="sxs-lookup"><span data-stu-id="9e78d-299">Except as the target of an assignment, when a property is referenced in an expression, the get accessor of the property is invoked to compute the value of the property.</span></span>

<span data-ttu-id="9e78d-300">set 访问器对应于包含一个名为 value 的参数但不含返回类型的方法。</span><span class="sxs-lookup"><span data-stu-id="9e78d-300">A set accessor corresponds to a method with a single parameter named value and no return type.</span></span> <span data-ttu-id="9e78d-301">如果将属性引用为赋值目标或 ++/-- 的操作数，将调用 set 访问器（由自变量提供新值）。</span><span class="sxs-lookup"><span data-stu-id="9e78d-301">When a property is referenced as the target of an assignment or as the operand of ++ or --, the set accessor is invoked with an argument that provides the new value.</span></span>

<span data-ttu-id="9e78d-302">`List<T>` 类声明以下两个属性：Count 和 Capacity（分别是只读和只写属性）。</span><span class="sxs-lookup"><span data-stu-id="9e78d-302">The `List<T>` class declares two properties, Count and Capacity, which are read-only and read-write, respectively.</span></span> <span data-ttu-id="9e78d-303">下面的示例展示了如何使用这些属性。</span><span class="sxs-lookup"><span data-stu-id="9e78d-303">The following is an example of use of these properties.</span></span>

[!code-csharp[ListExample2](../../../samples/snippets/csharp/tour/classes-and-objects/ListBasedExamples.cs#L101-L104)]

<span data-ttu-id="9e78d-304">类似于字段和方法，C# 支持实例属性和静态属性。</span><span class="sxs-lookup"><span data-stu-id="9e78d-304">Similar to fields and methods, C# supports both instance properties and static properties.</span></span> <span data-ttu-id="9e78d-305">静态属性使用静态修饰符进行声明，而实例属性则不使用静态修饰符进行声明。</span><span class="sxs-lookup"><span data-stu-id="9e78d-305">Static properties are declared with the static modifier, and instance properties are declared without it.</span></span>

<span data-ttu-id="9e78d-306">属性的访问器可以是虚的。</span><span class="sxs-lookup"><span data-stu-id="9e78d-306">The accessor(s) of a property can be virtual.</span></span> <span data-ttu-id="9e78d-307">如果属性声明包含 `virtual`、`abstract` 或 `override` 修饰符，则适用于属性的访问器。</span><span class="sxs-lookup"><span data-stu-id="9e78d-307">When a property declaration includes a `virtual`, `abstract`, or `override` modifier, it applies to the accessor(s) of the property.</span></span>

### <a name="indexers"></a><span data-ttu-id="9e78d-308">索引器</span><span class="sxs-lookup"><span data-stu-id="9e78d-308">Indexers</span></span>

<span data-ttu-id="9e78d-309">借助*索引器*成员，可以将对象编入索引（像处理数组一样）。</span><span class="sxs-lookup"><span data-stu-id="9e78d-309">An *indexer* is a member that enables objects to be indexed in the same way as an array.</span></span> <span data-ttu-id="9e78d-310">索引器的声明方式与属性类似，不同之处在于，索引器成员名称格式为后跟分隔符 `[` 和 `]`，其中写入参数列表。</span><span class="sxs-lookup"><span data-stu-id="9e78d-310">An indexer is declared like a property except that the name of the member is this followed by a parameter list written between the delimiters `[` and `]`.</span></span> <span data-ttu-id="9e78d-311">这些参数在索引器的访问器中可用。</span><span class="sxs-lookup"><span data-stu-id="9e78d-311">The parameters are available in the accessor(s) of the indexer.</span></span> <span data-ttu-id="9e78d-312">类似于属性，索引器分为读写、只读和只写索引器，且索引器的访问器可以是虚的。</span><span class="sxs-lookup"><span data-stu-id="9e78d-312">Similar to properties, indexers can be read-write, read-only, and write-only, and the accessor(s) of an indexer can be virtual.</span></span>

<span data-ttu-id="9e78d-313">`List` 类声明一个需要使用 `int` 参数的读写索引器。</span><span class="sxs-lookup"><span data-stu-id="9e78d-313">The `List` class declares a single read-write indexer that takes an `int` parameter.</span></span> <span data-ttu-id="9e78d-314">借助索引器，可以使用 `int` 值将 `List` 实例编入索引。</span><span class="sxs-lookup"><span data-stu-id="9e78d-314">The indexer makes it possible to index `List` instances with `int` values.</span></span> <span data-ttu-id="9e78d-315">例如:</span><span class="sxs-lookup"><span data-stu-id="9e78d-315">For example:</span></span>

[!code-csharp[ListExample3](../../../samples/snippets/csharp/tour/classes-and-objects/ListBasedExamples.cs#L109-L117)]

<span data-ttu-id="9e78d-316">索引器可以进行重载。也就是说，类可以声明多个索引器，只要其参数的数量或类型不同即可。</span><span class="sxs-lookup"><span data-stu-id="9e78d-316">Indexers can be overloaded, meaning that a class can declare multiple indexers as long as the number or types of their parameters differ.</span></span>

### <a name="events"></a><span data-ttu-id="9e78d-317">事件</span><span class="sxs-lookup"><span data-stu-id="9e78d-317">Events</span></span>

<span data-ttu-id="9e78d-318">借助*事件*成员，类或对象可以提供通知。</span><span class="sxs-lookup"><span data-stu-id="9e78d-318">An *event* is a member that enables a class or object to provide notifications.</span></span> <span data-ttu-id="9e78d-319">事件的声明方式与字段类似，不同之处在于，事件声明包括事件关键字，且类型必须是委托类型。</span><span class="sxs-lookup"><span data-stu-id="9e78d-319">An event is declared like a field except that the declaration includes an event keyword and the type must be a delegate type.</span></span>

<span data-ttu-id="9e78d-320">在声明事件成员的类中，事件的行为与委托类型的字段完全相同（前提是事件不是抽象的，且不声明访问器）。</span><span class="sxs-lookup"><span data-stu-id="9e78d-320">Within a class that declares an event member, the event behaves just like a field of a delegate type (provided the event is not abstract and does not declare accessors).</span></span> <span data-ttu-id="9e78d-321">字段存储对委托的引用，委托表示已添加到事件的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="9e78d-321">The field stores a reference to a delegate that represents the event handlers that have been added to the event.</span></span> <span data-ttu-id="9e78d-322">如果没有任何事件处理程序，则字段为 `null`。</span><span class="sxs-lookup"><span data-stu-id="9e78d-322">If no event handlers are present, the field is `null`.</span></span>

<span data-ttu-id="9e78d-323">`List<T>` 类声明一个 `Changed` 事件成员，指明已向列表添加了新项。</span><span class="sxs-lookup"><span data-stu-id="9e78d-323">The `List<T>` class declares a single event member called `Changed`, which indicates that a new item has been added to the list.</span></span> <span data-ttu-id="9e78d-324">Changed 事件由 `OnChanged` 虚方法引发，此方法会先检查事件是否是 `null`（即不含任何处理程序）。</span><span class="sxs-lookup"><span data-stu-id="9e78d-324">The Changed event is raised by the `OnChanged` virtual method, which first checks whether the event is `null` (meaning that no handlers are present).</span></span> <span data-ttu-id="9e78d-325">引发事件的概念恰恰等同于调用由事件表示的委托，因此，没有用于引发事件的特殊语言构造。</span><span class="sxs-lookup"><span data-stu-id="9e78d-325">The notion of raising an event is precisely equivalent to invoking the delegate represented by the event—thus, there are no special language constructs for raising events.</span></span>

<span data-ttu-id="9e78d-326">客户端通过*事件处理程序*响应事件。</span><span class="sxs-lookup"><span data-stu-id="9e78d-326">Clients react to events through *event handlers*.</span></span> <span data-ttu-id="9e78d-327">使用 `+=` 和 `-=` 运算符分别可以附加和删除事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="9e78d-327">Event handlers are attached using the `+=` operator and removed using the `-=` operator.</span></span> <span data-ttu-id="9e78d-328">下面的示例展示了如何向 `List<string>` 的 `Changed` 事件附加事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="9e78d-328">The following example attaches an event handler to the `Changed` event of a `List<string>`.</span></span>

[!code-csharp[EventExample](../../../samples/snippets/csharp/tour/classes-and-objects/ListBasedExamples.cs#L132-L148)]

<span data-ttu-id="9e78d-329">对于需要控制事件的基础存储的高级方案，事件声明可以显式提供 `add` 和 `remove` 访问器，这在某种程度上与属性的 `set` 访问器类似。</span><span class="sxs-lookup"><span data-stu-id="9e78d-329">For advanced scenarios where control of the underlying storage of an event is desired, an event declaration can explicitly provide `add` and `remove` accessors, which are somewhat similar to the `set` accessor of a property.</span></span>

### <a name="operators"></a><span data-ttu-id="9e78d-330">运算符</span><span class="sxs-lookup"><span data-stu-id="9e78d-330">Operators</span></span>

<span data-ttu-id="9e78d-331">*运算符*是定义向类实例应用特定表达式运算符的含义的成员。</span><span class="sxs-lookup"><span data-stu-id="9e78d-331">An *operator* is a member that defines the meaning of applying a particular expression operator to instances of a class.</span></span> <span data-ttu-id="9e78d-332">可以定义三种类型的运算符：一元运算符、二元运算符和转换运算符。</span><span class="sxs-lookup"><span data-stu-id="9e78d-332">Three kinds of operators can be defined: unary operators, binary operators, and conversion operators.</span></span> <span data-ttu-id="9e78d-333">所有运算符都必须声明为 `public` 和 `static`。</span><span class="sxs-lookup"><span data-stu-id="9e78d-333">All operators must be declared as `public` and `static`.</span></span>

<span data-ttu-id="9e78d-334">`List<T>` 类声明两个运算符（`operator ==` 和 `operator !=`），因此定义了向 `List` 实例应用这些运算符的表达式的新含义。</span><span class="sxs-lookup"><span data-stu-id="9e78d-334">The `List<T>` class declares two operators, `operator ==` and `operator !=`, and thus gives new meaning to expressions that apply those operators to `List` instances.</span></span> <span data-ttu-id="9e78d-335">具体而言，这些运算符定义的是两个 `List<T>` 实例的相等性（使用其 Equals 方法比较所包含的每个对象）。</span><span class="sxs-lookup"><span data-stu-id="9e78d-335">Specifically, the operators define equality of two `List<T>` instances as comparing each of the contained objects using their Equals methods.</span></span> <span data-ttu-id="9e78d-336">下面的示例展示了如何使用 `==` 运算符比较两个 `List<int>` 实例。</span><span class="sxs-lookup"><span data-stu-id="9e78d-336">The following example uses the `==` operator to compare two `List<int>` instances.</span></span>

[!code-csharp[OperatorExample](../../../samples/snippets/csharp/tour/classes-and-objects/ListBasedExamples.cs#L121-L129)]

<span data-ttu-id="9e78d-337">第一个 `Console.WriteLine` 输出 `True`，因为两个列表包含的对象不仅数量相同，而且值和顺序也相同。</span><span class="sxs-lookup"><span data-stu-id="9e78d-337">The first `Console.WriteLine` outputs `True` because the two lists contain the same number of objects with the same values in the same order.</span></span> <span data-ttu-id="9e78d-338">如果 `List<T>` 未定义 `operator ==`，那么第一个 `Console.WriteLine` 会输出 `False`，因为 `a` 和 `b` 引用不同的 `List<int>` 实例。</span><span class="sxs-lookup"><span data-stu-id="9e78d-338">Had `List<T>` not defined `operator ==`, the first `Console.WriteLine` would have output `False` because `a` and `b` reference different `List<int>` instances.</span></span>

### <a name="finalizers"></a><span data-ttu-id="9e78d-339">终结器</span><span class="sxs-lookup"><span data-stu-id="9e78d-339">Finalizers</span></span>

<span data-ttu-id="9e78d-340">*终结器*是实现完成类实例所需的操作的成员。</span><span class="sxs-lookup"><span data-stu-id="9e78d-340">A *finalizer* is a member that implements the actions required to finalize an instance of a class.</span></span> <span data-ttu-id="9e78d-341">终结器既不能包含参数和可访问性修饰符，也不能进行显式调用。</span><span class="sxs-lookup"><span data-stu-id="9e78d-341">Finalizers cannot have parameters, they cannot have accessibility modifiers, and they cannot be invoked explicitly.</span></span> <span data-ttu-id="9e78d-342">实例的终结器在垃圾回收期间自动调用。</span><span class="sxs-lookup"><span data-stu-id="9e78d-342">The finalizer for an instance is invoked automatically during garbage collection.</span></span>

<span data-ttu-id="9e78d-343">垃圾回收器在决定何时收集对象和运行终结器时有很大自由度。</span><span class="sxs-lookup"><span data-stu-id="9e78d-343">The garbage collector is allowed wide latitude in deciding when to collect objects and run finalizers.</span></span> <span data-ttu-id="9e78d-344">具体来说，终结器的调用时间具有不确定性，可以在任意线程上执行终结器。</span><span class="sxs-lookup"><span data-stu-id="9e78d-344">Specifically, the timing of finalizer invocations is not deterministic, and finalizers may be executed on any thread.</span></span> <span data-ttu-id="9e78d-345">因为这样或那样的原因，只有在没有其他可行的解决方案时，类才能实现终结器。</span><span class="sxs-lookup"><span data-stu-id="9e78d-345">For these and other reasons, classes should implement finalizers only when no other solutions are feasible.</span></span>

<span data-ttu-id="9e78d-346">处理对象析构的更好方法是使用 `using` 语句。</span><span class="sxs-lookup"><span data-stu-id="9e78d-346">The `using` statement provides a better approach to object destruction.</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="9e78d-347">[上一页](statements.md)
[下一页](structs.md)</span><span class="sxs-lookup"><span data-stu-id="9e78d-347">[Previous](statements.md)
[Next](structs.md)</span></span>
