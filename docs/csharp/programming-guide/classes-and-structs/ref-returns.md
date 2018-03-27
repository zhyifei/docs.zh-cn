---
title: ref 返回值和 ref 局部变量（C# 指南）
description: 了解如何定义和使用 ref 返回值和 ref 局部变量
author: rpetrusha
ms.author: ronpet
ms.date: 01/23/2017
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.openlocfilehash: c37c6dd61ae02813bcc467982f3b175da9136e4a
ms.sourcegitcommit: c883637b41ee028786edceece4fa872939d2e64c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2018
---
# <a name="ref-returns-and-ref-locals"></a><span data-ttu-id="72793-103">ref 返回值和局部变量</span><span class="sxs-lookup"><span data-stu-id="72793-103">Ref returns and ref locals</span></span>

<span data-ttu-id="72793-104">从 C# 7 开始，C# 支持引用返回值（ref 返回值）。</span><span class="sxs-lookup"><span data-stu-id="72793-104">Starting with C# 7, C# supports reference return values (ref returns).</span></span> <span data-ttu-id="72793-105">借助引用返回值，方法可以将对变量的引用（而不是值）返回给调用方。</span><span class="sxs-lookup"><span data-stu-id="72793-105">A reference return value allows a method to return a reference to a variable, rather than a value, back to a caller.</span></span> <span data-ttu-id="72793-106">然后，调用方可以选择将返回的变量视为按值返回或按引用返回。</span><span class="sxs-lookup"><span data-stu-id="72793-106">The caller can then choose to treat the returned variable as if it were returned by value or by reference.</span></span> <span data-ttu-id="72793-107">调用方可以新建称为“引用本地”的变量，其本身就是对返回值的引用。</span><span class="sxs-lookup"><span data-stu-id="72793-107">The caller can create a new variable that is itself a reference to the returned value, called a ref local.</span></span>

## <a name="what-is-a-reference-return-value"></a><span data-ttu-id="72793-108">什么是引用返回值？</span><span class="sxs-lookup"><span data-stu-id="72793-108">What is a reference return value?</span></span>

<span data-ttu-id="72793-109">绝大多数开发者都很熟悉将参数按引用传递给被调用的方法。</span><span class="sxs-lookup"><span data-stu-id="72793-109">Most developers are familiar with passing an argument to a called method *by reference*.</span></span> <span data-ttu-id="72793-110">被调用方法的参数列表包括按引用传递的变量，并且被调用方法对值所做的任何更改均由调用方观察。</span><span class="sxs-lookup"><span data-stu-id="72793-110">A called method's argument list includes a variable passed by reference, and any changes made to its value by the called method are observed by the caller.</span></span> <span data-ttu-id="72793-111">“引用返回值”是指方法返回对某变量的引用（或别名），变量范围包括方法，且生存期必须长于方法的返回值。</span><span class="sxs-lookup"><span data-stu-id="72793-111">A *reference return value* means that a method returns a *reference* (or an alias) to some variable whose scope includes the method and whose lifetime must extend beyond the return of the method.</span></span> <span data-ttu-id="72793-112">调用方对方法的返回值进行的修改应用于方法返回的变量。</span><span class="sxs-lookup"><span data-stu-id="72793-112">Modifications to the method's return value by the caller are made to the variable that is returned by the method.</span></span>

<span data-ttu-id="72793-113">如果声明方法返回引用返回值，表明方法返回变量别名。</span><span class="sxs-lookup"><span data-stu-id="72793-113">Declaring that a method returns a *reference return value* indicates that the method returns an alias to a variable.</span></span> <span data-ttu-id="72793-114">这样做通常是为了让调用代码有权通过别名访问此变量（包括修改它）。</span><span class="sxs-lookup"><span data-stu-id="72793-114">The design intent is often that the calling code should have access to that variable through the alias, including to modify it.</span></span> <span data-ttu-id="72793-115">遵循的原则是，按引用返回变量的方法不能有返回类型 `void`。</span><span class="sxs-lookup"><span data-stu-id="72793-115">It follows that methods returning by reference cannot have the return type `void`.</span></span>

<span data-ttu-id="72793-116">对于方法能以引用返回值的形式返回的表达式，存在一些限制。</span><span class="sxs-lookup"><span data-stu-id="72793-116">There are some restrictions on the expression that a method can return as a reference return value.</span></span> <span data-ttu-id="72793-117">这些方法包括：</span><span class="sxs-lookup"><span data-stu-id="72793-117">These include:</span></span>

- <span data-ttu-id="72793-118">返回值的生存期必须长于方法执行时间。</span><span class="sxs-lookup"><span data-stu-id="72793-118">The return value must have a lifetime that extends beyond the execution of the method.</span></span> <span data-ttu-id="72793-119">换言之，它不能是返回自身的方法中的本地变量。</span><span class="sxs-lookup"><span data-stu-id="72793-119">In other words, it cannot be a local variable in the method that returns it.</span></span> <span data-ttu-id="72793-120">它可以是实例或类的静态字段，也可是传递给方法的参数。</span><span class="sxs-lookup"><span data-stu-id="72793-120">It can be an instance or static field of a class, or it can be an argument passed to the method.</span></span> <span data-ttu-id="72793-121">尝试返回局部变量将生成编译器错误 CS8168：“无法按引用返回局部 "obj"，因为它不是 ref 局部变量”。</span><span class="sxs-lookup"><span data-stu-id="72793-121">Attempting to return a local variable generates compiler error CS8168, "Cannot return local 'obj' by reference because it is not a ref local."</span></span>

- <span data-ttu-id="72793-122">返回值不得为文本 `null`。</span><span class="sxs-lookup"><span data-stu-id="72793-122">The return value cannot be the literal `null`.</span></span> <span data-ttu-id="72793-123">尝试返回 `null` 将生成编译器错误 CS8156：“无法在此上下文中使用表达式，因为它可能没有按引用返回”。</span><span class="sxs-lookup"><span data-stu-id="72793-123">Attempting to return `null` generates compiler error CS8156, "An expression cannot be used in this context because it may not be returned by reference."</span></span>

   <span data-ttu-id="72793-124">使用引用返回值的方法可以返回值当前为 null（未实例化）或[可以为 null 的类型](../nullable-types/index.md)的变量别名。</span><span class="sxs-lookup"><span data-stu-id="72793-124">A method with a ref return can return an alias to a variable whose value is currently the null (uninstantiated) value or a [nullable type](../nullable-types/index.md) for a value type.</span></span>
 
- <span data-ttu-id="72793-125">返回值不得为常量、枚举成员、通过属性的按值返回值或 `class`/`struct` 方法。</span><span class="sxs-lookup"><span data-stu-id="72793-125">The return value cannot be a constant, an enumeration member, the by-value return value from a property, or a method of a `class` or `struct`.</span></span> <span data-ttu-id="72793-126">尝试返回它们将生成编译器错误 CS8156：“无法在此上下文中使用表达式，因为它可能没有按引用返回”。</span><span class="sxs-lookup"><span data-stu-id="72793-126">Attempting to return these generates compiler error CS8156, "An expression cannot be used in this context because it may not be returned by reference."</span></span>

<span data-ttu-id="72793-127">此外，由于异步方法可能在完成执行前就返回，虽然它的返回值仍未知，但也不允许对异步方法使用引用返回值。</span><span class="sxs-lookup"><span data-stu-id="72793-127">In addition, because an asynchronous method may return before it has finished execution, while its return value is still unknown, reference return values are not allowed on async methods.</span></span>
 
## <a name="defining-a-ref-return-value"></a><span data-ttu-id="72793-128">定义 ref 返回值</span><span class="sxs-lookup"><span data-stu-id="72793-128">Defining a ref return value</span></span>

<span data-ttu-id="72793-129">通过向方法签名的返回类型添加 [ref](../../language-reference/keywords/ref.md) 关键字来定义 ref 返回值。</span><span class="sxs-lookup"><span data-stu-id="72793-129">You define a ref return value by adding the [ref](../../language-reference/keywords/ref.md) keyword to the return type of the method signature.</span></span> <span data-ttu-id="72793-130">例如下列签名表示，`GetContactInformation` 属性将对 `Person` 对象的引用返回给调用方：</span><span class="sxs-lookup"><span data-stu-id="72793-130">For example, the following signature indicates that the `GetContactInformation` property returns a reference to a `Person` object to the caller:</span></span>

```csharp
public ref Person GetContactInformation(string fname, string lname);
```

<span data-ttu-id="72793-131">此外，方法正文中每个 [return](../../language-reference/keywords/return.md) 语句所返回对象的名称前面须有 [ref](../../language-reference/keywords/ref.md) 关键字。</span><span class="sxs-lookup"><span data-stu-id="72793-131">In addition, the name of the object returned by each [return](../../language-reference/keywords/return.md) statement in the method body must be preceded by the [ref](../../language-reference/keywords/ref.md) keyword.</span></span> <span data-ttu-id="72793-132">例如，下面的 `return` 语句返回对 `Person` 对象的引用 `p`：</span><span class="sxs-lookup"><span data-stu-id="72793-132">For example, the following `return` statement returns a reference to a `Person` object named `p`:</span></span>

```csharp
return ref p;
```

## <a name="consuming-a-ref-return-value"></a><span data-ttu-id="72793-133">使用 ref 返回值</span><span class="sxs-lookup"><span data-stu-id="72793-133">Consuming a ref return value</span></span>

<span data-ttu-id="72793-134">引用返回值是被调用方法范围中另一个变量的别名。</span><span class="sxs-lookup"><span data-stu-id="72793-134">The ref return value is an alias to another variable in the called method's scope.</span></span> <span data-ttu-id="72793-135">可以将引用返回值的所有使用都解释为，使用它取别名的变量：</span><span class="sxs-lookup"><span data-stu-id="72793-135">You can interpret any use of the ref return as using the variable it aliases:</span></span>

- <span data-ttu-id="72793-136">分配值时，就是将值分配到它取别名的变量。</span><span class="sxs-lookup"><span data-stu-id="72793-136">When you assign its value, you are assigning a value to the variable it aliases.</span></span>
- <span data-ttu-id="72793-137">读取值时，就是读取它取别名的变量的值。</span><span class="sxs-lookup"><span data-stu-id="72793-137">When you read its value, you are reading the value of the variable it aliases.</span></span>
- <span data-ttu-id="72793-138">如果按引用返回它，就是返回相同变量的别名。</span><span class="sxs-lookup"><span data-stu-id="72793-138">If you return it *by reference* you are returning an alias to that same variable.</span></span>
- <span data-ttu-id="72793-139">如果按引用将它传递到另一个方法，就是传递对它取别名的变量的引用。</span><span class="sxs-lookup"><span data-stu-id="72793-139">If you pass it to another method *by reference* you are passing a reference to the variable it aliases.</span></span>
- <span data-ttu-id="72793-140">如果返回[引用本地](#ref-local)别名，就是返回相同变量的新别名。</span><span class="sxs-lookup"><span data-stu-id="72793-140">When you make a [ref local](#ref-local) alias, you make a new alias to the same variable.</span></span>


## <a name="ref-locals"></a><span data-ttu-id="72793-141">ref 局部变量</span><span class="sxs-lookup"><span data-stu-id="72793-141">Ref locals</span></span>

<span data-ttu-id="72793-142">假设 `GetContactInformation` 方法声明为引用返回：</span><span class="sxs-lookup"><span data-stu-id="72793-142">Assume the `GetContactInformation` method is declared as a ref return:</span></span>

```csharp
public ref Person GetContactInformation(string fname, string lname)
```

<span data-ttu-id="72793-143">按值分配会读取变量值，并将它分配给新变量：</span><span class="sxs-lookup"><span data-stu-id="72793-143">A by-value assignment reads the value of a variable and assigns it to a new variable:</span></span>

```csharp
Person p = contacts.GetContactInformation("Brandie", "Best");
```

<span data-ttu-id="72793-144">上面的分配将 `p` 声明为本地变量。</span><span class="sxs-lookup"><span data-stu-id="72793-144">The preceding assignment declares `p` as a local variable.</span></span> <span data-ttu-id="72793-145">它的初始值是通过读取 `GetContactInformation` 返回的值进行复制。</span><span class="sxs-lookup"><span data-stu-id="72793-145">Its initial value is copied from reading the value returned by `GetContactInformation`.</span></span> <span data-ttu-id="72793-146">之后对 `p` 的任何分配都不会更改 `GetContactInformation` 返回的变量值。</span><span class="sxs-lookup"><span data-stu-id="72793-146">Any future assignments to `p` will not change the value of the variable returned by `GetContactInformation`.</span></span> <span data-ttu-id="72793-147">变量 `p` 不再是返回的变量的别名。</span><span class="sxs-lookup"><span data-stu-id="72793-147">The variable `p` is no longer an alias to the variable returned.</span></span>

<span data-ttu-id="72793-148">声明引用本地变量，复制原始值的别名。</span><span class="sxs-lookup"><span data-stu-id="72793-148">You declare a *ref local* variable to copy the alias to the original value.</span></span> <span data-ttu-id="72793-149">在下面的分配中，`p` 是从 `GetContactInformation` 返回的变量的别名。</span><span class="sxs-lookup"><span data-stu-id="72793-149">In the following assignment, `p` is an alias to the variable returned from `GetContactInformation`.</span></span>

```csharp
ref Person p = ref contacts.GetContactInformation("Brandie", "Best");
```

<span data-ttu-id="72793-150">后续使用 `p` 等同于使用 `GetContactInformation` 返回的变量，因为 `p` 是此变量的别名。</span><span class="sxs-lookup"><span data-stu-id="72793-150">Subsequent usage of `p` is the same as using the variable returned by `GetContactInformation` because `p` is an alias for that variable.</span></span> <span data-ttu-id="72793-151">对 `p` 所做的更改也会更改从 `GetContactInformation` 返回的变量。</span><span class="sxs-lookup"><span data-stu-id="72793-151">Changes to `p` also change the variable returned from `GetContactInformation`.</span></span>

<span data-ttu-id="72793-152">注意，请同时在局部变量声明前和方法调用前使用 `ref` 关键字。</span><span class="sxs-lookup"><span data-stu-id="72793-152">Note that the `ref` keyword is used both before the local variable declaration *and* before the method call.</span></span> 

<span data-ttu-id="72793-153">可通过相同方式按引用访问值。</span><span class="sxs-lookup"><span data-stu-id="72793-153">You can access a value by reference in the same way.</span></span> <span data-ttu-id="72793-154">在某些情况下，按引用访问值可避免潜在的高开销复制操作，从而提高性能。</span><span class="sxs-lookup"><span data-stu-id="72793-154">In some cases, accessing a value by reference increases performance by avoiding a potentially expensive copy operation.</span></span> <span data-ttu-id="72793-155">例如，以下语句显示用户可如何定义一个用于引用值的 ref 局部变量值。</span><span class="sxs-lookup"><span data-stu-id="72793-155">For example, the following statement shows how one can define a ref local value that is used to reference a value.</span></span>

```csharp
ref VeryLargeStruct reflocal = ref veryLargeStruct;
```

<span data-ttu-id="72793-156">注意，请同时在局部变量声明前和第二个示例中的值前使用 `ref` 关键字。</span><span class="sxs-lookup"><span data-stu-id="72793-156">Note that the `ref` keyword is used both before the local variable declaration *and* before the value in the second example.</span></span> <span data-ttu-id="72793-157">在这两个示例中，如果无法同时将 `ref` 关键字包含在变量声明和赋值中，则会导致编译器错误 CS8172：“无法使用值对按引用变量进行初始化”。</span><span class="sxs-lookup"><span data-stu-id="72793-157">Failure to include both `ref` keywords in the variable declaration and assignment in both examples results in compiler error CS8172, "Cannot initialize a by-reference variable with a value."</span></span> 
 
## <a name="ref-returns-and-ref-locals-an-example"></a><span data-ttu-id="72793-158">ref 返回结果和 ref 局部变量：示例</span><span class="sxs-lookup"><span data-stu-id="72793-158">Ref returns and ref locals: an example</span></span>

<span data-ttu-id="72793-159">下列示例定义存储整数值数组的 `NumberStore` 类。</span><span class="sxs-lookup"><span data-stu-id="72793-159">The following example defines a `NumberStore` class that stores an array of integer values.</span></span> <span data-ttu-id="72793-160">`FindNumber` 方法按引用返回第一个大于或等于作为参数传递的数字的数字。</span><span class="sxs-lookup"><span data-stu-id="72793-160">The `FindNumber` method returns by reference the first number that is greater than or equal to the number passed as an argument.</span></span> <span data-ttu-id="72793-161">如果没有大于或等于该参数的数字，则方法返回索引 0 中的数字。</span><span class="sxs-lookup"><span data-stu-id="72793-161">If no number is greater than or equal to the argument, the method returns the number in index 0.</span></span> 

[!code-csharp[ref-returns](../../../../samples/snippets/csharp/programming-guide/ref-returns/ref-returns1.cs#1)]

<span data-ttu-id="72793-162">下列示例调用 `NumberStore.FindNumber` 方法来检索大于或等于 16 的第一个值。</span><span class="sxs-lookup"><span data-stu-id="72793-162">The following example calls the `NumberStore.FindNumber` method to retrieve the first value that is greater than or equal to 16.</span></span> <span data-ttu-id="72793-163">然后，调用方将该方法返回的值加倍。</span><span class="sxs-lookup"><span data-stu-id="72793-163">The caller then doubles the value returned by the method.</span></span> <span data-ttu-id="72793-164">如示例中的输出所示，此更改将反映在 `NumberStore` 实例的数组元素的值中。</span><span class="sxs-lookup"><span data-stu-id="72793-164">As the output from the example shows, this change is reflected in the value of the array elements of the `NumberStore` instance.</span></span>

[!code-csharp[ref-returns](../../../../samples/snippets/csharp/programming-guide/ref-returns/ref-returns1.cs#2)]

<span data-ttu-id="72793-165">在不支持引用返回值的情况下，此类操作通常通过返回数组元素的索引和它的值来执行。</span><span class="sxs-lookup"><span data-stu-id="72793-165">Without support for reference return values, such an operation is usually performed by returning the index of the array element along with its value.</span></span> <span data-ttu-id="72793-166">然后，调用方可使用此索引修改单个方法调用中的值。</span><span class="sxs-lookup"><span data-stu-id="72793-166">The caller can then use this index to modify the value in a separate method call.</span></span> <span data-ttu-id="72793-167">但调用方也可修改要访问的索引，还可修改其他数组值。</span><span class="sxs-lookup"><span data-stu-id="72793-167">However, the caller can also modify the index to access and possibly modify other array values.</span></span>  
 
## <a name="see-also"></a><span data-ttu-id="72793-168">请参阅</span><span class="sxs-lookup"><span data-stu-id="72793-168">See also</span></span>

[<span data-ttu-id="72793-169">ref 关键字</span><span class="sxs-lookup"><span data-stu-id="72793-169">ref keyword</span></span>](../../language-reference/keywords/ref.md)  
[<span data-ttu-id="72793-170">具有值类型的引用语义</span><span class="sxs-lookup"><span data-stu-id="72793-170">Reference Semantics with Value Types</span></span>](../../../csharp/reference-semantics-with-value-types.md)
