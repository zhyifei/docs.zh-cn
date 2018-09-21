---
title: 类 (F#)
description: '了解如何 F # 类是表示可以具有属性、 方法和事件的对象的类型。'
ms.date: 05/16/2016
ms.openlocfilehash: 71cd713d192d28565e879b79b2fc9e0530e5f841
ms.sourcegitcommit: dfb2a100cfb4d3902c042f17b3204f49bc7635e7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2018
ms.locfileid: "46493021"
---
# <a name="classes"></a><span data-ttu-id="08e99-103">类</span><span class="sxs-lookup"><span data-stu-id="08e99-103">Classes</span></span>

<span data-ttu-id="08e99-104">*类*是表示可以具有属性、 方法和事件的对象类型。</span><span class="sxs-lookup"><span data-stu-id="08e99-104">*Classes* are types that represent objects that can have properties, methods, and events.</span></span>

## <a name="syntax"></a><span data-ttu-id="08e99-105">语法</span><span class="sxs-lookup"><span data-stu-id="08e99-105">Syntax</span></span>

```fsharp
// Class definition:
type [access-modifier] type-name [type-params] [access-modifier] ( parameter-list ) [ as identifier ] =
[ class ]
[ inherit base-type-name(base-constructor-args) ]
[ let-bindings ]
[ do-bindings ]
member-list
...
[ end ]
// Mutually recursive class definitions:
type [access-modifier] type-name1 ...
and [access-modifier] type-name2 ...
...
```

## <a name="remarks"></a><span data-ttu-id="08e99-106">备注</span><span class="sxs-lookup"><span data-stu-id="08e99-106">Remarks</span></span>

<span data-ttu-id="08e99-107">类表示.NET 对象类型; 的基本说明此类是在 F # 中支持面向对象的编程的主要类型概念。</span><span class="sxs-lookup"><span data-stu-id="08e99-107">Classes represent the fundamental description of .NET object types; the class is the primary type concept that supports object-oriented programming in F#.</span></span>

<span data-ttu-id="08e99-108">在上述语法中，`type-name`是任何有效的标识符。</span><span class="sxs-lookup"><span data-stu-id="08e99-108">In the preceding syntax, the `type-name` is any valid identifier.</span></span> <span data-ttu-id="08e99-109">`type-params`介绍了可选的泛型类型参数。</span><span class="sxs-lookup"><span data-stu-id="08e99-109">The `type-params` describes optional generic type parameters.</span></span> <span data-ttu-id="08e99-110">它包含类型参数名称和括在尖括号中的约束 (`<`和`>`)。</span><span class="sxs-lookup"><span data-stu-id="08e99-110">It consists of type parameter names and constraints enclosed in angle brackets (`<` and `>`).</span></span> <span data-ttu-id="08e99-111">有关详细信息，请参阅[泛型](generics/index.md)并[约束](generics/constraints.md)。</span><span class="sxs-lookup"><span data-stu-id="08e99-111">For more information, see [Generics](generics/index.md) and [Constraints](generics/constraints.md).</span></span> <span data-ttu-id="08e99-112">`parameter-list`介绍构造函数参数。</span><span class="sxs-lookup"><span data-stu-id="08e99-112">The `parameter-list` describes constructor parameters.</span></span> <span data-ttu-id="08e99-113">第一个访问修饰符与类型;第二个与主构造函数。</span><span class="sxs-lookup"><span data-stu-id="08e99-113">The first access modifier pertains to the type; the second pertains to the primary constructor.</span></span> <span data-ttu-id="08e99-114">在这两种情况下，默认值是`public`。</span><span class="sxs-lookup"><span data-stu-id="08e99-114">In both cases, the default is `public`.</span></span>

<span data-ttu-id="08e99-115">使用指定的类的基类`inherit`关键字。</span><span class="sxs-lookup"><span data-stu-id="08e99-115">You specify the base class for a class by using the `inherit` keyword.</span></span> <span data-ttu-id="08e99-116">必须提供基类构造函数的参数，在括号中。</span><span class="sxs-lookup"><span data-stu-id="08e99-116">You must supply arguments, in parentheses, for the base class constructor.</span></span>

<span data-ttu-id="08e99-117">声明字段或函数值是通过使用该类的局部`let`绑定，并且必须遵循的一般规则`let`绑定。</span><span class="sxs-lookup"><span data-stu-id="08e99-117">You declare fields or function values that are local to the class by using `let` bindings, and you must follow the general rules for `let` bindings.</span></span> <span data-ttu-id="08e99-118">`do-bindings`部分包含用于构造对象时执行的代码。</span><span class="sxs-lookup"><span data-stu-id="08e99-118">The `do-bindings` section includes code to be executed upon object construction.</span></span>

<span data-ttu-id="08e99-119">`member-list`包含其他构造函数、 实例和静态方法声明、 接口声明、 抽象的绑定，以及属性和事件声明。</span><span class="sxs-lookup"><span data-stu-id="08e99-119">The `member-list` consists of additional constructors, instance and static method declarations, interface declarations, abstract bindings, and property and event declarations.</span></span> <span data-ttu-id="08e99-120">中介绍了这些[成员](members/index.md)。</span><span class="sxs-lookup"><span data-stu-id="08e99-120">These are described in [Members](members/index.md).</span></span>

<span data-ttu-id="08e99-121">`identifier` ，可使用可选`as`关键字会为命名实例变量或自我标识符，可用于在类型定义中引用的类型的实例。</span><span class="sxs-lookup"><span data-stu-id="08e99-121">The `identifier` that is used with the optional `as` keyword gives a name to the instance variable, or self identifier, which can be used in the type definition to refer to the instance of the type.</span></span> <span data-ttu-id="08e99-122">有关详细信息，请参阅本主题后面的部分自我标识符。</span><span class="sxs-lookup"><span data-stu-id="08e99-122">For more information, see the section Self Identifiers later in this topic.</span></span>

<span data-ttu-id="08e99-123">关键字`class`和`end`标记开头和末尾定义是可选的。</span><span class="sxs-lookup"><span data-stu-id="08e99-123">The keywords `class` and `end` that mark the start and end of the definition are optional.</span></span>

<span data-ttu-id="08e99-124">递归类型，它们是相互引用的类型，以及已加入的相互`and`一样相互递归函数是关键字。</span><span class="sxs-lookup"><span data-stu-id="08e99-124">Mutually recursive types, which are types that reference each other, are joined together with the `and` keyword just as mutually recursive functions are.</span></span> <span data-ttu-id="08e99-125">有关示例，请参阅部分相互递归类型。</span><span class="sxs-lookup"><span data-stu-id="08e99-125">For an example, see the section Mutually Recursive Types.</span></span>

## <a name="constructors"></a><span data-ttu-id="08e99-126">构造函数</span><span class="sxs-lookup"><span data-stu-id="08e99-126">Constructors</span></span>

<span data-ttu-id="08e99-127">构造函数是可创建类类型的实例的代码。</span><span class="sxs-lookup"><span data-stu-id="08e99-127">The constructor is code that creates an instance of the class type.</span></span> <span data-ttu-id="08e99-128">类构造函数在 F # 中工作方式略有不同，不同用其他.NET 语言。</span><span class="sxs-lookup"><span data-stu-id="08e99-128">Constructors for classes work somewhat differently in F# than they do in other .NET languages.</span></span> <span data-ttu-id="08e99-129">在 F # 类，存在始终是主构造函数中所述该形参的实参`parameter-list`后面的类型名称，其正文组成`let`(和`let rec`) 开头的类声明并绑定`do`遵循的绑定。</span><span class="sxs-lookup"><span data-stu-id="08e99-129">In an F# class, there is always a primary constructor whose arguments are described in the `parameter-list` that follows the type name, and whose body consists of the `let` (and `let rec`) bindings at the start of the class declaration and the `do` bindings that follow.</span></span> <span data-ttu-id="08e99-130">在主构造函数的参数是在类声明整个范围内。</span><span class="sxs-lookup"><span data-stu-id="08e99-130">The arguments of the primary constructor are in scope throughout the class declaration.</span></span>

<span data-ttu-id="08e99-131">可以使用添加其他构造函数`new`关键字添加成员，按如下所示：</span><span class="sxs-lookup"><span data-stu-id="08e99-131">You can add additional constructors by using the `new` keyword to add a member, as follows:</span></span>

<span data-ttu-id="08e99-132">`new`(`argument-list`) = `constructor-body`</span><span class="sxs-lookup"><span data-stu-id="08e99-132">`new`(`argument-list`) = `constructor-body`</span></span>

<span data-ttu-id="08e99-133">新的构造函数的主体必须调用主构造函数指定的类声明的顶部。</span><span class="sxs-lookup"><span data-stu-id="08e99-133">The body of the new constructor must invoke the primary constructor that is specified at the top of the class declaration.</span></span>

<span data-ttu-id="08e99-134">下面的示例说明了这一概念。</span><span class="sxs-lookup"><span data-stu-id="08e99-134">The following example illustrates this concept.</span></span> <span data-ttu-id="08e99-135">在下面的代码，`MyClass`具有两个构造函数，主构造函数采用两个参数和另一个构造函数不采用任何参数。</span><span class="sxs-lookup"><span data-stu-id="08e99-135">In the following code, `MyClass` has two constructors, a primary constructor that takes two arguments and another constructor that takes no arguments.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2401.fs)]

## <a name="let-and-do-bindings"></a><span data-ttu-id="08e99-136">let 和 do 绑定</span><span class="sxs-lookup"><span data-stu-id="08e99-136">let and do Bindings</span></span>

<span data-ttu-id="08e99-137">`let`和`do`类定义中的绑定窗体中的主类构造函数的正文，因此它们运行时创建的类实例。</span><span class="sxs-lookup"><span data-stu-id="08e99-137">The `let` and `do` bindings in a class definition form the body of the primary class constructor, and therefore they run whenever a class instance is created.</span></span> <span data-ttu-id="08e99-138">如果`let`绑定是一个函数，则将它编译为一个成员。</span><span class="sxs-lookup"><span data-stu-id="08e99-138">If a `let` binding is a function, then it is compiled into a member.</span></span> <span data-ttu-id="08e99-139">如果`let`绑定是一个值，不用于在任何函数或成员，则将它编译到一个变量中的本地构造函数。</span><span class="sxs-lookup"><span data-stu-id="08e99-139">If the `let` binding is a value that is not used in any function or member, then it is compiled into a variable that is local to the constructor.</span></span> <span data-ttu-id="08e99-140">否则，它被编译到类的字段。</span><span class="sxs-lookup"><span data-stu-id="08e99-140">Otherwise, it is compiled into a field of the class.</span></span> <span data-ttu-id="08e99-141">`do`遵循的表达式被编译到主构造函数和执行每个实例的初始化代码。</span><span class="sxs-lookup"><span data-stu-id="08e99-141">The `do` expressions that follow are compiled into the primary constructor and execute initialization code for every instance.</span></span> <span data-ttu-id="08e99-142">其他所有构造函数始终调用主构造函数，因为`let`绑定和`do`绑定始终执行而不考虑其调用构造函数。</span><span class="sxs-lookup"><span data-stu-id="08e99-142">Because any additional constructors always call the primary constructor, the `let` bindings and `do` bindings always execute regardless of which constructor is called.</span></span>

<span data-ttu-id="08e99-143">创建的字段`let`绑定可以访问在整个方法和类的属性; 但是，它们不能从访问静态方法，即使这些静态方法采用实例变量作为参数。</span><span class="sxs-lookup"><span data-stu-id="08e99-143">Fields that are created by `let` bindings can be accessed throughout the methods and properties of the class; however, they cannot be accessed from static methods, even if the static methods take an instance variable as a parameter.</span></span> <span data-ttu-id="08e99-144">它们不能通过使用自我标识符，如果存在访问。</span><span class="sxs-lookup"><span data-stu-id="08e99-144">They cannot be accessed by using the self identifier, if one exists.</span></span>

## <a name="self-identifiers"></a><span data-ttu-id="08e99-145">自我标识符</span><span class="sxs-lookup"><span data-stu-id="08e99-145">Self Identifiers</span></span>

<span data-ttu-id="08e99-146">一个*自我标识符*是表示当前实例的名称。</span><span class="sxs-lookup"><span data-stu-id="08e99-146">A *self identifier* is a name that represents the current instance.</span></span> <span data-ttu-id="08e99-147">自我标识符类似于`this`C# 或 c + + 中的关键字或`Me`在 Visual Basic 中。</span><span class="sxs-lookup"><span data-stu-id="08e99-147">Self identifiers resemble the `this` keyword in C# or C++ or `Me` in Visual Basic.</span></span> <span data-ttu-id="08e99-148">您可以在两种不同的方式，具体取决于是否想要在作用域为整个类定义或只是单个方法中的自助标识符定义自我标识符。</span><span class="sxs-lookup"><span data-stu-id="08e99-148">You can define a self identifier in two different ways, depending on whether you want the self identifier to be in scope for the whole class definition or just for an individual method.</span></span>

<span data-ttu-id="08e99-149">若要定义整个类自我标识符，请使用`as`构造函数参数的右括号后的关键字列表，并指定标识符名称。</span><span class="sxs-lookup"><span data-stu-id="08e99-149">To define a self identifier for the whole class, use the `as` keyword after the closing parentheses of the constructor parameter list, and specify the identifier name.</span></span>

<span data-ttu-id="08e99-150">若要定义的自我标识符只是一种方法，提供在成员声明中，只需在方法名称和句点 （.） 作为分隔符之前的自我标识符。</span><span class="sxs-lookup"><span data-stu-id="08e99-150">To define a self identifier for just one method, provide the self identifier in the member declaration, just before the method name and a period (.) as a separator.</span></span>

<span data-ttu-id="08e99-151">下面的代码示例说明了创建自我标识符的两种方法。</span><span class="sxs-lookup"><span data-stu-id="08e99-151">The following code example illustrates the two ways to create a self identifier.</span></span> <span data-ttu-id="08e99-152">在第一行`as`关键字用于定义自我标识符。</span><span class="sxs-lookup"><span data-stu-id="08e99-152">In the first line, the `as` keyword is used to define the self identifier.</span></span> <span data-ttu-id="08e99-153">在第五个行中，标识符`this`用于定义其作用域仅限于方法自我标识符`PrintMessage`。</span><span class="sxs-lookup"><span data-stu-id="08e99-153">In the fifth line, the identifier `this` is used to define a self identifier whose scope is restricted to the method `PrintMessage`.</span></span>

```fsharp
type MyClass2(dataIn) as self =
    let data = dataIn
    do
        self.PrintMessage()
    member this.PrintMessage() =
        printf "Creating MyClass2 with Data %d" data
```

<span data-ttu-id="08e99-154">与在其他.NET 语言中，您可以命名自我标识符随意;您不限于名称如`self`， `Me`，或`this`。</span><span class="sxs-lookup"><span data-stu-id="08e99-154">Unlike in other .NET languages, you can name the self identifier however you want; you are not restricted to names such as `self`, `Me`, or `this`.</span></span>

<span data-ttu-id="08e99-155">使用声明的自我标识符`as`关键字未初始化之前后`let`会执行绑定。</span><span class="sxs-lookup"><span data-stu-id="08e99-155">The self identifier that is declared with the `as` keyword is not initialized until after the `let` bindings are executed.</span></span> <span data-ttu-id="08e99-156">因此，它不能用在`let`绑定。</span><span class="sxs-lookup"><span data-stu-id="08e99-156">Therefore, it cannot be used in the `let` bindings.</span></span> <span data-ttu-id="08e99-157">可以使用中的自我标识符`do`绑定部分。</span><span class="sxs-lookup"><span data-stu-id="08e99-157">You can use the self identifier in the `do` bindings section.</span></span>

## <a name="generic-type-parameters"></a><span data-ttu-id="08e99-158">泛型类型参数</span><span class="sxs-lookup"><span data-stu-id="08e99-158">Generic Type Parameters</span></span>

<span data-ttu-id="08e99-159">在尖括号中指定泛型类型参数 (`<`和`>`)，在标识符后跟可用一个单引号的窗体中。</span><span class="sxs-lookup"><span data-stu-id="08e99-159">Generic type parameters are specified in angle brackets (`<` and `>`), in the form of a single quotation mark followed by an identifier.</span></span> <span data-ttu-id="08e99-160">由逗号分隔多个泛型类型参数。</span><span class="sxs-lookup"><span data-stu-id="08e99-160">Multiple generic type parameters are separated by commas.</span></span> <span data-ttu-id="08e99-161">泛型类型参数是在整个声明范围内。</span><span class="sxs-lookup"><span data-stu-id="08e99-161">The generic type parameter is in scope throughout the declaration.</span></span> <span data-ttu-id="08e99-162">下面的代码示例演示如何指定泛型类型参数。</span><span class="sxs-lookup"><span data-stu-id="08e99-162">The following code example shows how to specify generic type parameters.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2403.fs)]

<span data-ttu-id="08e99-163">使用类型时，会被推断类型参数。</span><span class="sxs-lookup"><span data-stu-id="08e99-163">Type arguments are inferred when the type is used.</span></span> <span data-ttu-id="08e99-164">在下面的代码中，推断出的类型是元组序列。</span><span class="sxs-lookup"><span data-stu-id="08e99-164">In the following code, the inferred type is a sequence of tuples.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet24031.fs)]

## <a name="specifying-inheritance"></a><span data-ttu-id="08e99-165">指定继承</span><span class="sxs-lookup"><span data-stu-id="08e99-165">Specifying Inheritance</span></span>

<span data-ttu-id="08e99-166">`inherit`子句标识直接基类，如果有的话。</span><span class="sxs-lookup"><span data-stu-id="08e99-166">The `inherit` clause identifies the direct base class, if there is one.</span></span> <span data-ttu-id="08e99-167">在 F # 中，允许仅一个直接基类。</span><span class="sxs-lookup"><span data-stu-id="08e99-167">In F#, only one direct base class is allowed.</span></span> <span data-ttu-id="08e99-168">一个类实现的接口不会考虑基类。</span><span class="sxs-lookup"><span data-stu-id="08e99-168">Interfaces that a class implements are not considered base classes.</span></span> <span data-ttu-id="08e99-169">接口中讨论[接口](Interfaces.md)主题。</span><span class="sxs-lookup"><span data-stu-id="08e99-169">Interfaces are discussed in the [Interfaces](Interfaces.md) topic.</span></span>

<span data-ttu-id="08e99-170">您可以访问的方法和属性的基类派生类中使用的语言关键字`base`作为标识符后, 跟一个句点 （.） 和成员的名称。</span><span class="sxs-lookup"><span data-stu-id="08e99-170">You can access the methods and properties of the base class from the derived class by using the language keyword `base` as an identifier, followed by a period (.) and the name of the member.</span></span>

<span data-ttu-id="08e99-171">有关详细信息，请参阅[继承](inheritance.md)。</span><span class="sxs-lookup"><span data-stu-id="08e99-171">For more information, see [Inheritance](inheritance.md).</span></span>

## <a name="members-section"></a><span data-ttu-id="08e99-172">成员部分</span><span class="sxs-lookup"><span data-stu-id="08e99-172">Members Section</span></span>

<span data-ttu-id="08e99-173">可以在本部分中定义静态或实例方法、 属性、 接口实现、 抽象成员，事件声明和其他构造函数。</span><span class="sxs-lookup"><span data-stu-id="08e99-173">You can define static or instance methods, properties, interface implementations, abstract members, event declarations, and additional constructors in this section.</span></span> <span data-ttu-id="08e99-174">允许和执行操作的绑定不能出现在本部分中。</span><span class="sxs-lookup"><span data-stu-id="08e99-174">Let and do bindings cannot appear in this section.</span></span> <span data-ttu-id="08e99-175">成员可以添加到不同的 F # 类型除了类之外，因为它们在单独主题中，讨论[成员](members/index.md)。</span><span class="sxs-lookup"><span data-stu-id="08e99-175">Because members can be added to a variety of F# types in addition to classes, they are discussed in a separate topic, [Members](members/index.md).</span></span>

## <a name="mutually-recursive-types"></a><span data-ttu-id="08e99-176">相互递归类型</span><span class="sxs-lookup"><span data-stu-id="08e99-176">Mutually Recursive Types</span></span>

<span data-ttu-id="08e99-177">在定义以循环方式相互引用的类型时，您将排列在一起的类型定义通过使用`and`关键字。</span><span class="sxs-lookup"><span data-stu-id="08e99-177">When you define types that reference each other in a circular way, you string together the type definitions by using the `and` keyword.</span></span> <span data-ttu-id="08e99-178">`and`关键字将替换`type`上除外，如下所示的第一个定义的关键字。</span><span class="sxs-lookup"><span data-stu-id="08e99-178">The `and` keyword replaces the `type` keyword on all except the first definition, as follows.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2404.fs)]

<span data-ttu-id="08e99-179">输出是当前目录中的所有文件的列表。</span><span class="sxs-lookup"><span data-stu-id="08e99-179">The output is a list of all the files in the current directory.</span></span>

## <a name="when-to-use-classes-unions-records-and-structures"></a><span data-ttu-id="08e99-180">何时使用类、 联合、 记录和结构</span><span class="sxs-lookup"><span data-stu-id="08e99-180">When to Use Classes, Unions, Records, and Structures</span></span>

<span data-ttu-id="08e99-181">给定类型可供选择的多样性，需要充分了解什么每种类型专为以选择特定的情况下的相应类型。</span><span class="sxs-lookup"><span data-stu-id="08e99-181">Given the variety of types to choose from, you need to have a good understanding of what each type is designed for to select the appropriate type for a particular situation.</span></span> <span data-ttu-id="08e99-182">类旨在供在面向对象的编程上下文中使用。</span><span class="sxs-lookup"><span data-stu-id="08e99-182">Classes are designed for use in object-oriented programming contexts.</span></span> <span data-ttu-id="08e99-183">面向对象的编程是为.NET Framework 编写的应用程序中使用的主流模式。</span><span class="sxs-lookup"><span data-stu-id="08e99-183">Object-oriented programming is the dominant paradigm used in applications that are written for the .NET Framework.</span></span> <span data-ttu-id="08e99-184">如果 F # 代码必须与.NET Framework 或另一个面向对象的库，密切合作，尤其是当您必须扩展从诸如 UI 库之类的面向对象的类型系统，类可能适用。</span><span class="sxs-lookup"><span data-stu-id="08e99-184">If your F# code has to work closely with the .NET Framework or another object-oriented library, and especially if you have to extend from an object-oriented type system such as a UI library, classes are probably appropriate.</span></span>

<span data-ttu-id="08e99-185">如果您不紧密地与代码交互操作的面向对象的或者您编写的是自包含且因此频繁交互，面向对象的代码从受保护的代码，您应该考虑使用记录和可区分联合。</span><span class="sxs-lookup"><span data-stu-id="08e99-185">If you are not interoperating closely with object-oriented code, or if you are writing code that is self-contained and therefore protected from frequent interaction with object-oriented code, you should consider using records and discriminated unions.</span></span> <span data-ttu-id="08e99-186">单一的精心构思的可区分的联合，以及合适的模式匹配的代码中，通常可用作对象层次结构的更简单的替代。</span><span class="sxs-lookup"><span data-stu-id="08e99-186">A single, well thought–out discriminated union, together with appropriate pattern matching code, can often be used as a simpler alternative to an object hierarchy.</span></span> <span data-ttu-id="08e99-187">有关可区分联合的详细信息，请参阅[可区分联合](discriminated-unions.md)。</span><span class="sxs-lookup"><span data-stu-id="08e99-187">For more information about discriminated unions, see [Discriminated Unions](discriminated-unions.md).</span></span>

<span data-ttu-id="08e99-188">记录具有的优点是比类更简单，但记录将不适用时的一种类型的需求超过可完成的简单性。</span><span class="sxs-lookup"><span data-stu-id="08e99-188">Records have the advantage of being simpler than classes, but records are not appropriate when the demands of a type exceed what can be accomplished with their simplicity.</span></span> <span data-ttu-id="08e99-189">记录是基本上简单值的聚合，而无需单独的构造函数可以执行自定义操作的、 不包含隐藏字段，且无继承或接口实现。</span><span class="sxs-lookup"><span data-stu-id="08e99-189">Records are basically simple aggregates of values, without separate constructors that can perform custom actions, without hidden fields, and without inheritance or interface implementations.</span></span> <span data-ttu-id="08e99-190">虽然属性和方法等的成员可以添加到记录，以使其行为更复杂，存储在一条记录中的字段仍是值的简单聚合。</span><span class="sxs-lookup"><span data-stu-id="08e99-190">Although members such as properties and methods can be added to records to make their behavior more complex, the fields stored in a record are still a simple aggregate of values.</span></span> <span data-ttu-id="08e99-191">有关记录的详细信息，请参阅[记录](records.md)。</span><span class="sxs-lookup"><span data-stu-id="08e99-191">For more information about records, see [Records](records.md).</span></span>

<span data-ttu-id="08e99-192">结构也是有用的少量聚合数据，但它们不同于类和记录，它们是.NET 值类型。</span><span class="sxs-lookup"><span data-stu-id="08e99-192">Structures are also useful for small aggregates of data, but they differ from classes and records in that they are .NET value types.</span></span> <span data-ttu-id="08e99-193">类和记录是.NET 引用类型。</span><span class="sxs-lookup"><span data-stu-id="08e99-193">Classes and records are .NET reference types.</span></span> <span data-ttu-id="08e99-194">值类型和引用类型的语义不同，是按值传递值类型。</span><span class="sxs-lookup"><span data-stu-id="08e99-194">The semantics of value types and reference types are different in that value types are passed by value.</span></span> <span data-ttu-id="08e99-195">这意味着它们进行复制时作为参数传递或从函数返回位的位。</span><span class="sxs-lookup"><span data-stu-id="08e99-195">This means that they are copied bit for bit when they are passed as a parameter or returned from a function.</span></span> <span data-ttu-id="08e99-196">它们是也存储在堆栈上或者，如果将其用作字段，则嵌入在父对象而不是存储在堆上其自己单独的位置。</span><span class="sxs-lookup"><span data-stu-id="08e99-196">They are also stored on the stack or, if they are used as a field, embedded inside the parent object instead of stored in their own separate location on the heap.</span></span> <span data-ttu-id="08e99-197">因此，结构是适用于经常访问的数据访问堆的系统开销问题时。</span><span class="sxs-lookup"><span data-stu-id="08e99-197">Therefore, structures are appropriate for frequently accessed data when the overhead of accessing the heap is a problem.</span></span> <span data-ttu-id="08e99-198">有关结构的详细信息，请参阅[结构](structures.md)。</span><span class="sxs-lookup"><span data-stu-id="08e99-198">For more information about structures, see [Structures](structures.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="08e99-199">请参阅</span><span class="sxs-lookup"><span data-stu-id="08e99-199">See also</span></span>

- [<span data-ttu-id="08e99-200">F# 语言参考</span><span class="sxs-lookup"><span data-stu-id="08e99-200">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="08e99-201">成员</span><span class="sxs-lookup"><span data-stu-id="08e99-201">Members</span></span>](members/index.md)
- [<span data-ttu-id="08e99-202">继承</span><span class="sxs-lookup"><span data-stu-id="08e99-202">Inheritance</span></span>](inheritance.md)
- [<span data-ttu-id="08e99-203">接口</span><span class="sxs-lookup"><span data-stu-id="08e99-203">Interfaces</span></span>](interfaces.md)
