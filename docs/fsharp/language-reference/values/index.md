---
title: 值
description: 了解如何在值F#是具有特定类型的数量。
ms.date: 05/16/2016
ms.openlocfilehash: 5c1d4f1e59cbf092911d99a725654042bf3383b1
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/19/2018
ms.locfileid: "53611875"
---
# <a name="values"></a><span data-ttu-id="489ac-103">值</span><span class="sxs-lookup"><span data-stu-id="489ac-103">Values</span></span>

<span data-ttu-id="489ac-104">F# 形式的值是具有特定类型的数量；值可以是整数或浮点数、字符或文本、列表、序列、数组、元组、可区分联合、记录、类类型或函数值。</span><span class="sxs-lookup"><span data-stu-id="489ac-104">Values in F# are quantities that have a specific type; values can be integral or floating point numbers, characters or text, lists, sequences, arrays, tuples, discriminated unions, records, class types, or function values.</span></span>

## <a name="binding-a-value"></a><span data-ttu-id="489ac-105">绑定值</span><span class="sxs-lookup"><span data-stu-id="489ac-105">Binding a Value</span></span>

<span data-ttu-id="489ac-106">术语“绑定”意指将名称与定义关联。</span><span class="sxs-lookup"><span data-stu-id="489ac-106">The term *binding* means associating a name with a definition.</span></span> <span data-ttu-id="489ac-107">`let` 关键字将绑定值，如下例所示：</span><span class="sxs-lookup"><span data-stu-id="489ac-107">The `let` keyword binds a value, as in the following examples:</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet601.fs)]

<span data-ttu-id="489ac-108">值的类型根据定义推断得出。</span><span class="sxs-lookup"><span data-stu-id="489ac-108">The type of a value is inferred from the definition.</span></span> <span data-ttu-id="489ac-109">对于基元类型（例如整数或浮点数），类型由文本的类型确定。</span><span class="sxs-lookup"><span data-stu-id="489ac-109">For a primitive type, such as an integral or floating point number, the type is determined from the type of the literal.</span></span> <span data-ttu-id="489ac-110">因此，在前面的示例中，编译器将 `b` 的类型推断为 `unsigned int`，而将 `a` 的类型推断为 `int`。</span><span class="sxs-lookup"><span data-stu-id="489ac-110">Therefore, in the previous example, the compiler infers the type of `b` to be `unsigned int`, whereas the compiler infers the type of `a` to be `int`.</span></span> <span data-ttu-id="489ac-111">函数值的类型由函数体中的返回值确定。</span><span class="sxs-lookup"><span data-stu-id="489ac-111">The type of a function value is determined from the return value in the function body.</span></span> <span data-ttu-id="489ac-112">有关函数值类型的详细信息，请参阅[函数](../functions/index.md)。</span><span class="sxs-lookup"><span data-stu-id="489ac-112">For more information about function value types, see [Functions](../functions/index.md).</span></span> <span data-ttu-id="489ac-113">有关文本类型的详细信息，请参阅[文本](../literals.md)。</span><span class="sxs-lookup"><span data-stu-id="489ac-113">For more information about literal types, see [Literals](../literals.md).</span></span>

<span data-ttu-id="489ac-114">默认情况下，编译器不会发出诊断信息未使用的绑定。</span><span class="sxs-lookup"><span data-stu-id="489ac-114">The compiler does not issue diagnostics about unused bindings by default.</span></span> <span data-ttu-id="489ac-115">若要启用接收这些消息，警告 1182年项目文件中或调用编译器时 (请参阅`--warnon`下[编译器选项](../compiler-options.md))。</span><span class="sxs-lookup"><span data-stu-id="489ac-115">To receive these messages, enable warning 1182 in your project file or when invoking the compiler (see `--warnon` under [Compiler Options](../compiler-options.md)).</span></span>

## <a name="why-immutable"></a><span data-ttu-id="489ac-116">为何不可变？</span><span class="sxs-lookup"><span data-stu-id="489ac-116">Why Immutable?</span></span>

<span data-ttu-id="489ac-117">不可变值是指在程序的整个执行过程中无法更改的值。</span><span class="sxs-lookup"><span data-stu-id="489ac-117">Immutable values are values that cannot be changed throughout the course of a program's execution.</span></span> <span data-ttu-id="489ac-118">如果习惯于使用 C++、Visual Basic 或 C# 之类的语言，可能会惊奇地发现，F# 认为不可变值最为重要，而不是可在程序执行过程中赋予新值的变量。</span><span class="sxs-lookup"><span data-stu-id="489ac-118">If you are used to languages such as C++, Visual Basic, or C#, you might find it surprising that F# puts primacy over immutable values rather than variables that can be assigned new values during the execution of a program.</span></span> <span data-ttu-id="489ac-119">不可变数据是函数编程中的一个重要元素。</span><span class="sxs-lookup"><span data-stu-id="489ac-119">Immutable data is an important element of functional programming.</span></span> <span data-ttu-id="489ac-120">在多线程环境中，可由许多不同线程更改的共享可变变量管理起来很困难。</span><span class="sxs-lookup"><span data-stu-id="489ac-120">In a multithreaded environment, shared mutable variables that can be changed by many different threads are difficult to manage.</span></span> <span data-ttu-id="489ac-121">此外，若使用可变变量，有时很难判断变量在传递到另一个函数时是否可更改。</span><span class="sxs-lookup"><span data-stu-id="489ac-121">Also, with mutable variables, it can sometimes be hard to tell if a variable might be changed when it is passed to another function.</span></span>

<span data-ttu-id="489ac-122">纯粹的函数语言中没有变量，函数的行为与数学函数的行为类似 - 常的严格。</span><span class="sxs-lookup"><span data-stu-id="489ac-122">In pure functional languages, there are no variables, and functions behave strictly as mathematical functions.</span></span> <span data-ttu-id="489ac-123">如果过程语言中的代码使用变量赋值来更改值，函数语言中的等效代码会有一个作为输入的不可变值、一个不可变函数以及作为输出的其他不可变值。</span><span class="sxs-lookup"><span data-stu-id="489ac-123">Where code in a procedural language uses a variable assignment to alter a value, the equivalent code in a functional language has an immutable value that is the input, an immutable function, and different immutable values as the output.</span></span> <span data-ttu-id="489ac-124">这种数学严格性实现了有关程序行为的更严格推理。</span><span class="sxs-lookup"><span data-stu-id="489ac-124">This mathematical strictness allows for tighter reasoning about the behavior of the program.</span></span> <span data-ttu-id="489ac-125">通过这种更严格的推理，编译器将能够更严格地检查代码，并更有效地进行优化，还可以让开发人员更轻松地理解和编写正确的代码。</span><span class="sxs-lookup"><span data-stu-id="489ac-125">This tighter reasoning is what enables compilers to check code more stringently and to optimize more effectively, and helps make it easier for developers to understand and write correct code.</span></span> <span data-ttu-id="489ac-126">因此，与普通的过程代码相比，函数代码可能更易于调试。</span><span class="sxs-lookup"><span data-stu-id="489ac-126">Functional code is therefore likely to be easier to debug than ordinary procedural code.</span></span>

<span data-ttu-id="489ac-127">F# 不是纯粹的函数语言，但它完全支持函数编程。</span><span class="sxs-lookup"><span data-stu-id="489ac-127">F# is not a pure functional language, yet it fully supports functional programming.</span></span> <span data-ttu-id="489ac-128">使用不可变值是一种很好的做法，因为这样做可以使代码从函数编程的一个重要方面中获益。</span><span class="sxs-lookup"><span data-stu-id="489ac-128">Using immutable values is a good practice because doing this allows your code to benefit from an important aspect of functional programming.</span></span>

## <a name="mutable-variables"></a><span data-ttu-id="489ac-129">可变变量</span><span class="sxs-lookup"><span data-stu-id="489ac-129">Mutable Variables</span></span>

<span data-ttu-id="489ac-130">可使用关键字 `mutable` 指定可以更改的变量。</span><span class="sxs-lookup"><span data-stu-id="489ac-130">You can use the keyword `mutable` to specify a variable that can be changed.</span></span> <span data-ttu-id="489ac-131">F# 中的可变变量范围通常有限，要么是类型字段形式，要么是本地值形式。</span><span class="sxs-lookup"><span data-stu-id="489ac-131">Mutable variables in F# should generally have a limited scope, either as a field of a type or as a local value.</span></span> <span data-ttu-id="489ac-132">具有有限范围的可变值更易于控制，并且被错误修改的可能性也更小。</span><span class="sxs-lookup"><span data-stu-id="489ac-132">Mutable variables with a limited scope are easier to control and are less likely to be modified in incorrect ways.</span></span>

<span data-ttu-id="489ac-133">可以使用 `let` 关键字，采用像定义值一样的方式将初始值赋给可变变量。</span><span class="sxs-lookup"><span data-stu-id="489ac-133">You can assign an initial value to a mutable variable by using the `let` keyword in the same way as you would define a value.</span></span> <span data-ttu-id="489ac-134">但区别在于，随后可以使用 `<-` 运算符将新值赋给可变变量，如下例所示。</span><span class="sxs-lookup"><span data-stu-id="489ac-134">However, the difference is that you can subsequently assign new values to mutable variables by using the `<-` operator, as in the following example.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet602.fs)]

<span data-ttu-id="489ac-135">标记的值`mutable`可能会自动提升为`'a ref`如果捕获闭包，包括创建闭包，如的窗体`seq`生成器。</span><span class="sxs-lookup"><span data-stu-id="489ac-135">Values marked `mutable` may be automatically promoted to `'a ref` if captured by a closure, including forms that create closures, such as `seq` builders.</span></span> <span data-ttu-id="489ac-136">如果你想要在发生这种情况时收到通知，启用警告 3180 项目文件中或调用编译器时。</span><span class="sxs-lookup"><span data-stu-id="489ac-136">If you wish to be notified when this occurs, enable warning 3180 in your project file or when invoking the compiler.</span></span>

## <a name="related-topics"></a><span data-ttu-id="489ac-137">相关主题</span><span class="sxs-lookup"><span data-stu-id="489ac-137">Related Topics</span></span>

|<span data-ttu-id="489ac-138">标题</span><span class="sxs-lookup"><span data-stu-id="489ac-138">Title</span></span>|<span data-ttu-id="489ac-139">描述</span><span class="sxs-lookup"><span data-stu-id="489ac-139">Description</span></span>|
|-----|-----------|
|[<span data-ttu-id="489ac-140">let 绑定</span><span class="sxs-lookup"><span data-stu-id="489ac-140">let Bindings</span></span>](../functions/let-bindings.md)|<span data-ttu-id="489ac-141">提供有关使用信息`let`关键字将绑定到值和函数的名称。</span><span class="sxs-lookup"><span data-stu-id="489ac-141">Provides information about using the `let` keyword to bind names to values and functions.</span></span>|
|[<span data-ttu-id="489ac-142">函数</span><span class="sxs-lookup"><span data-stu-id="489ac-142">Functions</span></span>](../functions/index.md)|<span data-ttu-id="489ac-143">提供 F# 中函数的概述。</span><span class="sxs-lookup"><span data-stu-id="489ac-143">Provides an overview of functions in F#.</span></span>|

## <a name="see-also"></a><span data-ttu-id="489ac-144">请参阅</span><span class="sxs-lookup"><span data-stu-id="489ac-144">See also</span></span>

- [<span data-ttu-id="489ac-145">Null 值</span><span class="sxs-lookup"><span data-stu-id="489ac-145">Null Values</span></span>](null-Values.md)
- [<span data-ttu-id="489ac-146">F# 语言参考</span><span class="sxs-lookup"><span data-stu-id="489ac-146">F# Language Reference</span></span>](../index.md)