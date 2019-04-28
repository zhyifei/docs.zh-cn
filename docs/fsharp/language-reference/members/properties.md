---
title: 属性
description: 了解如何F#是表示与对象相关联的值的成员的属性。
ms.date: 05/16/2016
ms.openlocfilehash: bf605ee1135bd3b3561bde9a8ae66353497931b0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61666360"
---
# <a name="properties"></a><span data-ttu-id="49202-103">属性</span><span class="sxs-lookup"><span data-stu-id="49202-103">Properties</span></span>

<span data-ttu-id="49202-104">*属性*是表示与对象相关联的值的成员。</span><span class="sxs-lookup"><span data-stu-id="49202-104">*Properties* are members that represent values associated with an object.</span></span>

## <a name="syntax"></a><span data-ttu-id="49202-105">语法</span><span class="sxs-lookup"><span data-stu-id="49202-105">Syntax</span></span>

```fsharp
// Property that has both get and set defined.
[ attributes ]
[ static ] member [accessibility-modifier] [self-identifier.]PropertyName
with [accessibility-modifier] get() =
    get-function-body
and [accessibility-modifier] set parameter =
    set-function-body

// Alternative syntax for a property that has get and set.
[ attributes-for-get ]
[ static ] member [accessibility-modifier-for-get] [self-identifier.]PropertyName =
    get-function-body
[ attributes-for-set ]
[ static ] member [accessibility-modifier-for-set] [self-identifier.]PropertyName
with set parameter =
    set-function-body

// Property that has get only.
[ attributes ]
[ static ] member [accessibility-modifier] [self-identifier.]PropertyName =
    get-function-body

// Alternative syntax for property that has get only.
[ attributes ]
[ static ] member [accessibility-modifier] [self-identifier.]PropertyName
with get() =
    get-function-body

// Property that has set only.
[ attributes ]
[ static ] member [accessibility-modifier] [self-identifier.]PropertyName
with set parameter =
    set-function-body

// Automatically implemented properties.
[ attributes ]
[ static ] member val [accessibility-modifier] PropertyName = initialization-expression [ with get, set ]
```

## <a name="remarks"></a><span data-ttu-id="49202-106">备注</span><span class="sxs-lookup"><span data-stu-id="49202-106">Remarks</span></span>

<span data-ttu-id="49202-107">属性表示"具有"在面向对象的编程中，表示与对象实例，或对于静态属性，与类型相关联的数据的关系。</span><span class="sxs-lookup"><span data-stu-id="49202-107">Properties represent the "has a" relationship in object-oriented programming, representing data that is associated with object instances or, for static properties, with the type.</span></span>

<span data-ttu-id="49202-108">您可以声明两种方法，具体取决于是否想要显式指定 （也称为后备存储） 的基础值的属性，或如果想要允许编译器自动生成你的后备存储中的属性。</span><span class="sxs-lookup"><span data-stu-id="49202-108">You can declare properties in two ways, depending on whether you want to explicitly specify the underlying value (also called the backing store) for the property, or if you want to allow the compiler to automatically generate the backing store for you.</span></span> <span data-ttu-id="49202-109">通常情况下，您应使用更明确的方式在该属性具有重要的实现和自动的方式，只需为值或变量的简单包装器属性时。</span><span class="sxs-lookup"><span data-stu-id="49202-109">Generally, you should use the more explicit way if the property has a non-trivial implementation and the automatic way when the property is just a simple wrapper for a value or variable.</span></span> <span data-ttu-id="49202-110">若要显式声明的属性，使用`member`关键字。</span><span class="sxs-lookup"><span data-stu-id="49202-110">To declare a property explicitly, use the `member` keyword.</span></span> <span data-ttu-id="49202-111">此声明性语法后跟指定的语法`get`并`set`方法，也称为*访问器*。</span><span class="sxs-lookup"><span data-stu-id="49202-111">This declarative syntax is followed by the syntax that specifies the `get` and `set` methods, also named *accessors*.</span></span> <span data-ttu-id="49202-112">将各种形式的语法部分中所示的显式语法用于读/写和只读的只写属性。</span><span class="sxs-lookup"><span data-stu-id="49202-112">The various forms of the explicit syntax shown in the syntax section are used for read/write, read-only, and write-only properties.</span></span> <span data-ttu-id="49202-113">对于只读属性，只需定义`get`方法; 因此，对于只写属性，定义仅`set`方法。</span><span class="sxs-lookup"><span data-stu-id="49202-113">For read-only properties, you define only a `get` method; for write-only properties, define only a `set` method.</span></span> <span data-ttu-id="49202-114">请注意，当属性同时具有`get`和`set`访问器中，替代语法，可指定属性和是不同的每个访问器，如下面的代码中所示的可访问性修饰符。</span><span class="sxs-lookup"><span data-stu-id="49202-114">Note that when a property has both `get` and `set` accessors, the alternative syntax enables you to specify attributes and accessibility modifiers that are different for each accessor, as is shown in the following code.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3201.fs)]

<span data-ttu-id="49202-115">对于读/写属性，同时具有`get`并`set`方法，则的顺序`get`和`set`可以反转。</span><span class="sxs-lookup"><span data-stu-id="49202-115">For read/write properties, which have both a `get` and `set` method, the order of `get` and `set` can be reversed.</span></span> <span data-ttu-id="49202-116">或者，可以提供有关所示的语法`get`仅为所示的语法和`set`仅而不是使用组合的语法。</span><span class="sxs-lookup"><span data-stu-id="49202-116">Alternatively, you can provide the syntax shown for `get` only and the syntax shown for `set` only instead of using the combined syntax.</span></span> <span data-ttu-id="49202-117">执行此操作可以更轻松地注释掉单个`get`或`set`方法时，如果这是你可能需要执行操作。</span><span class="sxs-lookup"><span data-stu-id="49202-117">Doing this makes it easier to comment out the individual `get` or `set` method, if that is something you might need to do.</span></span> <span data-ttu-id="49202-118">以下方法来使用组合的语法如以下代码所示。</span><span class="sxs-lookup"><span data-stu-id="49202-118">This alternative to using the combined syntax is shown in the following code.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3203.fs)]

<span data-ttu-id="49202-119">私有值属性的数据调用该保留*后备存储*。</span><span class="sxs-lookup"><span data-stu-id="49202-119">Private values that hold the data for properties are called *backing stores*.</span></span> <span data-ttu-id="49202-120">若要让编译器自动创建的后备存储，请使用关键字`member val`，省略自我标识符，然后提供用于初始化该属性的表达式。</span><span class="sxs-lookup"><span data-stu-id="49202-120">To have the compiler create the backing store automatically, use the keywords `member val`, omit the self-identifier, then provide an expression to initialize the property.</span></span> <span data-ttu-id="49202-121">如果该属性是可变的包括`with get, set`。</span><span class="sxs-lookup"><span data-stu-id="49202-121">If the property is to be mutable, include `with get, set`.</span></span> <span data-ttu-id="49202-122">例如，以下类类型包括两个自动实现的属性。</span><span class="sxs-lookup"><span data-stu-id="49202-122">For example, the following class type includes two automatically implemented properties.</span></span> <span data-ttu-id="49202-123">`Property1` 是只读的同时初始化为提供给主构造函数的参数和`Property2`是初始化为空字符串可设置属性：</span><span class="sxs-lookup"><span data-stu-id="49202-123">`Property1` is read-only and is initialized to the argument provided to the primary constructor, and `Property2` is a settable property initialized to an empty string:</span></span>

```fsharp
type MyClass(property1 : int) =
member val Property1 = property1
member val Property2 = "" with get, set
```

<span data-ttu-id="49202-124">自动实现的属性是一种类型，初始化的一部分，因此它们必须包含在任何其他成员定义之前就像`let`绑定和`do`类型定义中的绑定。</span><span class="sxs-lookup"><span data-stu-id="49202-124">Automatically implemented properties are part of the initialization of a type, so they must be included before any other member definitions, just like `let` bindings and `do` bindings in a type definition.</span></span> <span data-ttu-id="49202-125">请注意在初始化时和每次访问该属性时不仅计算初始化自动实现的属性表达式。</span><span class="sxs-lookup"><span data-stu-id="49202-125">Note that the expression that initializes an automatically implemented property is only evaluated upon initialization, and not every time the property is accessed.</span></span> <span data-ttu-id="49202-126">此行为是属性的与显式实现的行为不同。</span><span class="sxs-lookup"><span data-stu-id="49202-126">This behavior is in contrast to the behavior of an explicitly implemented property.</span></span> <span data-ttu-id="49202-127">这实际上意味着，用于初始化这些属性的代码将添加到类的构造函数。</span><span class="sxs-lookup"><span data-stu-id="49202-127">What this effectively means is that the code to initialize these properties is added to the constructor of a class.</span></span> <span data-ttu-id="49202-128">请考虑下面显示了这种差异的代码：</span><span class="sxs-lookup"><span data-stu-id="49202-128">Consider the following code that shows this difference:</span></span>

```fsharp
type MyClass() =
    let random  = new System.Random()
    member val AutoProperty = random.Next() with get, set
    member this.ExplicitProperty = random.Next()

let class1 = new MyClass()

printfn "class1.AutoProperty = %d" class1.AutoProperty
printfn "class1.AutoProperty = %d" class1.AutoProperty
printfn "class1.ExplicitProperty = %d" class1.ExplicitProperty
printfn "class1.ExplicitProperty = %d" class1.ExplicitProperty
```

<span data-ttu-id="49202-129">**输出**</span><span class="sxs-lookup"><span data-stu-id="49202-129">**Output**</span></span>

```
class1.AutoProperty = 1853799794
class1.AutoProperty = 1853799794
class1.ExplicitProperty = 978922705
class1.ExplicitProperty = 1131210765
```

<span data-ttu-id="49202-130">上述代码的输出显示，AutoProperty 的值是不变时重复调用而 ExplicitProperty 更改每次调用它。</span><span class="sxs-lookup"><span data-stu-id="49202-130">The output of the preceding code shows that the value of AutoProperty is unchanged when called repeatedly, whereas the ExplicitProperty changes each time it is called.</span></span> <span data-ttu-id="49202-131">本示例演示自动实现属性的表达式不计算每个时间，是因为是显式的属性的 getter 方法。</span><span class="sxs-lookup"><span data-stu-id="49202-131">This demonstrates that the expression for an automatically implemented property is not evaluated each time, as is the getter method for the explicit property.</span></span>

>[!WARNING]
><span data-ttu-id="49202-132">有一些库，如实体框架 (`System.Data.Entity`)，可以在不很好地配合初始化自动实现的属性的基类构造函数中执行自定义操作。</span><span class="sxs-lookup"><span data-stu-id="49202-132">There are some libraries, such as the Entity Framework (`System.Data.Entity`) that perform custom operations in base class constructors that don't work well with the initialization of automatically implemented properties.</span></span> <span data-ttu-id="49202-133">在这些情况下，请尝试使用显式属性。</span><span class="sxs-lookup"><span data-stu-id="49202-133">In those cases, try using explicit properties.</span></span>

<span data-ttu-id="49202-134">属性可以是类、 结构、 可区分的联合、 记录、 接口和类型扩展的成员，也可以在对象表达式中定义。</span><span class="sxs-lookup"><span data-stu-id="49202-134">Properties can be members of classes, structures, discriminated unions, records, interfaces, and type extensions and can also be defined in object expressions.</span></span>

<span data-ttu-id="49202-135">特性可以应用于属性。</span><span class="sxs-lookup"><span data-stu-id="49202-135">Attributes can be applied to properties.</span></span> <span data-ttu-id="49202-136">若要将属性应用于属性，请在单独的行的属性前面写入属性。</span><span class="sxs-lookup"><span data-stu-id="49202-136">To apply an attribute to a property, write the attribute on a separate line before the property.</span></span> <span data-ttu-id="49202-137">有关更多信息，请参阅[特性](../attributes.md)。</span><span class="sxs-lookup"><span data-stu-id="49202-137">For more information, see [Attributes](../attributes.md).</span></span>

<span data-ttu-id="49202-138">默认情况下，属性是公共的。</span><span class="sxs-lookup"><span data-stu-id="49202-138">By default, properties are public.</span></span> <span data-ttu-id="49202-139">可访问性修饰符还可以应用于属性。</span><span class="sxs-lookup"><span data-stu-id="49202-139">Accessibility modifiers can also be applied to properties.</span></span> <span data-ttu-id="49202-140">若要应用可访问性修饰符，如果将其添加的属性名称之前它旨在应用于两个`get`和`set`方法; 将其之前添加`get`和`set`如果不同的可访问性是关键字所需的每个访问器。</span><span class="sxs-lookup"><span data-stu-id="49202-140">To apply an accessibility modifier, add it immediately before the name of the property if it is meant to apply to both the `get` and `set` methods; add it before the `get` and `set` keywords if different accessibility is required for each accessor.</span></span> <span data-ttu-id="49202-141">*可访问性修饰符*可以是以下之一： `public`， `private`， `internal`。</span><span class="sxs-lookup"><span data-stu-id="49202-141">The *accessibility-modifier* can be one of the following: `public`, `private`, `internal`.</span></span> <span data-ttu-id="49202-142">有关详细信息，请参阅[访问控制](../access-control.md)。</span><span class="sxs-lookup"><span data-stu-id="49202-142">For more information, see [Access Control](../access-control.md).</span></span>

<span data-ttu-id="49202-143">每次访问属性时都会执行属性实现。</span><span class="sxs-lookup"><span data-stu-id="49202-143">Property implementations are executed each time a property is accessed.</span></span>

## <a name="static-and-instance-properties"></a><span data-ttu-id="49202-144">静态和实例属性</span><span class="sxs-lookup"><span data-stu-id="49202-144">Static and Instance Properties</span></span>

<span data-ttu-id="49202-145">属性可以是静态或实例属性。</span><span class="sxs-lookup"><span data-stu-id="49202-145">Properties can be static or instance properties.</span></span> <span data-ttu-id="49202-146">静态属性可以调用没有实例和用于与不具有单个对象的类型相关联的值。</span><span class="sxs-lookup"><span data-stu-id="49202-146">Static properties can be invoked without an instance and are used for values associated with the type, not with individual objects.</span></span> <span data-ttu-id="49202-147">对于静态属性，省略自我标识符。</span><span class="sxs-lookup"><span data-stu-id="49202-147">For static properties, omit the self-identifier.</span></span> <span data-ttu-id="49202-148">对于实例属性需要自我标识符。</span><span class="sxs-lookup"><span data-stu-id="49202-148">The self-identifier is required for instance properties.</span></span>

<span data-ttu-id="49202-149">以下的静态属性定义基于一个方案使用的静态字段`myStaticValue`，它是属性的后备存储。</span><span class="sxs-lookup"><span data-stu-id="49202-149">The following static property definition is based on a scenario in which you have a static field `myStaticValue` that is the backing store for the property.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3204.fs)]

<span data-ttu-id="49202-150">属性也可以是数组一样，在这种情况下调用它们*索引属性*。</span><span class="sxs-lookup"><span data-stu-id="49202-150">Properties can also be array-like, in which case they are called *indexed properties*.</span></span> <span data-ttu-id="49202-151">有关详细信息，请参阅[索引化属性](indexed-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="49202-151">For more information, see [Indexed Properties](indexed-properties.md).</span></span>

## <a name="type-annotation-for-properties"></a><span data-ttu-id="49202-152">属性的类型批注</span><span class="sxs-lookup"><span data-stu-id="49202-152">Type Annotation for Properties</span></span>

<span data-ttu-id="49202-153">在许多情况下，编译器有足够的信息来推断从后备存储的类型属性的类型，但您可以通过添加类型注释来显式设置的类型。</span><span class="sxs-lookup"><span data-stu-id="49202-153">In many cases, the compiler has enough information to infer the type of a property from the type of the backing store, but you can set the type explicitly by adding a type annotation.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3205.fs)]

## <a name="using-property-set-accessors"></a><span data-ttu-id="49202-154">使用属性 set 访问器</span><span class="sxs-lookup"><span data-stu-id="49202-154">Using Property set Accessors</span></span>

<span data-ttu-id="49202-155">您可以设置提供的属性`set`访问器使用`<-`运算符。</span><span class="sxs-lookup"><span data-stu-id="49202-155">You can set properties that provide `set` accessors by using the `<-` operator.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3206.fs)]

<span data-ttu-id="49202-156">输出是**20**。</span><span class="sxs-lookup"><span data-stu-id="49202-156">The output is **20**.</span></span>

## <a name="abstract-properties"></a><span data-ttu-id="49202-157">抽象属性</span><span class="sxs-lookup"><span data-stu-id="49202-157">Abstract Properties</span></span>

<span data-ttu-id="49202-158">属性可以是抽象的。</span><span class="sxs-lookup"><span data-stu-id="49202-158">Properties can be abstract.</span></span> <span data-ttu-id="49202-159">与方法一样，`abstract`只是与属性关联的虚拟调度意味着。</span><span class="sxs-lookup"><span data-stu-id="49202-159">As with methods, `abstract` just means that there is a virtual dispatch associated with the property.</span></span> <span data-ttu-id="49202-160">抽象属性可以是真正抽象的也就是说，无需在同一个类中定义。</span><span class="sxs-lookup"><span data-stu-id="49202-160">Abstract properties can be truly abstract, that is, without a definition in the same class.</span></span> <span data-ttu-id="49202-161">因此，包含此类属性的类是一个抽象类。</span><span class="sxs-lookup"><span data-stu-id="49202-161">The class that contains such a property is therefore an abstract class.</span></span> <span data-ttu-id="49202-162">或者，抽象可能只是意味着一个属性是虚拟的并在这种情况下，定义必须位于同一个类。</span><span class="sxs-lookup"><span data-stu-id="49202-162">Alternatively, abstract can just mean that a property is virtual, and in that case, a definition must be present in the same class.</span></span> <span data-ttu-id="49202-163">请注意，抽象属性不能为私有，并且有一个访问器是抽象的其他必须也是抽象的。</span><span class="sxs-lookup"><span data-stu-id="49202-163">Note that abstract properties must not be private, and if one accessor is abstract, the other must also be abstract.</span></span> <span data-ttu-id="49202-164">有关抽象类的详细信息，请参阅[抽象类](../abstract-classes.md)。</span><span class="sxs-lookup"><span data-stu-id="49202-164">For more information about abstract classes, see [Abstract Classes](../abstract-classes.md).</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3207.fs)]

## <a name="see-also"></a><span data-ttu-id="49202-165">请参阅</span><span class="sxs-lookup"><span data-stu-id="49202-165">See also</span></span>

- [<span data-ttu-id="49202-166">成员</span><span class="sxs-lookup"><span data-stu-id="49202-166">Members</span></span>](index.md)
- [<span data-ttu-id="49202-167">方法</span><span class="sxs-lookup"><span data-stu-id="49202-167">Methods</span></span>](methods.md)
