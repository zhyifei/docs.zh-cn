---
title: ref 返回值和 ref 局部变量（C# 指南）
description: 了解如何定义和使用 ref 返回值和 ref 局部变量
author: rpetrusha
ms.author: ronpet
ms.date: 04/04/2018
ms.openlocfilehash: a869cd50c5512c9893b6e5056aa58e1f92ee26f4
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43510560"
---
# <a name="ref-returns-and-ref-locals"></a><span data-ttu-id="1e82f-103">ref 返回值和局部变量</span><span class="sxs-lookup"><span data-stu-id="1e82f-103">Ref returns and ref locals</span></span>

<span data-ttu-id="1e82f-104">从 C# 7.0 开始，C# 支持引用返回值（ref 返回值）。</span><span class="sxs-lookup"><span data-stu-id="1e82f-104">Starting with C# 7.0, C# supports reference return values (ref returns).</span></span> <span data-ttu-id="1e82f-105">借助引用返回值，方法可以将对变量的引用（而不是值）返回给调用方。</span><span class="sxs-lookup"><span data-stu-id="1e82f-105">A reference return value allows a method to return a reference to a variable, rather than a value, back to a caller.</span></span> <span data-ttu-id="1e82f-106">然后，调用方可以选择将返回的变量视为按值返回或按引用返回。</span><span class="sxs-lookup"><span data-stu-id="1e82f-106">The caller can then choose to treat the returned variable as if it were returned by value or by reference.</span></span> <span data-ttu-id="1e82f-107">调用方可以新建称为“引用本地”的变量，其本身就是对返回值的引用。</span><span class="sxs-lookup"><span data-stu-id="1e82f-107">The caller can create a new variable that is itself a reference to the returned value, called a ref local.</span></span>

## <a name="what-is-a-reference-return-value"></a><span data-ttu-id="1e82f-108">什么是引用返回值？</span><span class="sxs-lookup"><span data-stu-id="1e82f-108">What is a reference return value?</span></span>

<span data-ttu-id="1e82f-109">绝大多数开发者都很熟悉将参数按引用传递给被调用的方法。</span><span class="sxs-lookup"><span data-stu-id="1e82f-109">Most developers are familiar with passing an argument to a called method *by reference*.</span></span> <span data-ttu-id="1e82f-110">已调用方法的参数列表包含以引用方式传递的变量。</span><span class="sxs-lookup"><span data-stu-id="1e82f-110">A called method's argument list includes a variable passed by reference.</span></span> <span data-ttu-id="1e82f-111">调用方会监测已调用方法对其值做出的任何更改。</span><span class="sxs-lookup"><span data-stu-id="1e82f-111">Any changes made to its value by the called method are observed by the caller.</span></span> <span data-ttu-id="1e82f-112">引用返回值是指，方法返回对某变量的引用（或别名）。</span><span class="sxs-lookup"><span data-stu-id="1e82f-112">A *reference return value* means that a method returns a *reference* (or an alias) to some variable.</span></span> <span data-ttu-id="1e82f-113">相应变量的作用域必须包括方法。</span><span class="sxs-lookup"><span data-stu-id="1e82f-113">That variable's scope must include the method.</span></span> <span data-ttu-id="1e82f-114">相应变量的生存期必须超过方法的返回值。</span><span class="sxs-lookup"><span data-stu-id="1e82f-114">That variable's lifetime must extend beyond the return of the method.</span></span> <span data-ttu-id="1e82f-115">调用方对方法的返回值进行的修改应用于方法返回的变量。</span><span class="sxs-lookup"><span data-stu-id="1e82f-115">Modifications to the method's return value by the caller are made to the variable that is returned by the method.</span></span>

<span data-ttu-id="1e82f-116">如果声明方法返回引用返回值，表明方法返回变量别名。</span><span class="sxs-lookup"><span data-stu-id="1e82f-116">Declaring that a method returns a *reference return value* indicates that the method returns an alias to a variable.</span></span> <span data-ttu-id="1e82f-117">这样做通常是为了让调用代码有权通过别名访问此变量（包括修改它）。</span><span class="sxs-lookup"><span data-stu-id="1e82f-117">The design intent is often that the calling code should have access to that variable through the alias, including to modify it.</span></span> <span data-ttu-id="1e82f-118">因此，方法的引用返回值不得包含返回类型 `void`。</span><span class="sxs-lookup"><span data-stu-id="1e82f-118">It follows that methods returning by reference can't have the return type `void`.</span></span>

<span data-ttu-id="1e82f-119">对于方法能以引用返回值的形式返回的表达式，存在一些限制。</span><span class="sxs-lookup"><span data-stu-id="1e82f-119">There are some restrictions on the expression that a method can return as a reference return value.</span></span> <span data-ttu-id="1e82f-120">具体限制包括：</span><span class="sxs-lookup"><span data-stu-id="1e82f-120">Restrictions include:</span></span>

- <span data-ttu-id="1e82f-121">返回值的生存期必须长于方法执行时间。</span><span class="sxs-lookup"><span data-stu-id="1e82f-121">The return value must have a lifetime that extends beyond the execution of the method.</span></span> <span data-ttu-id="1e82f-122">换言之，它不能是返回自身的方法中的本地变量。</span><span class="sxs-lookup"><span data-stu-id="1e82f-122">In other words, it cannot be a local variable in the method that returns it.</span></span> <span data-ttu-id="1e82f-123">它可以是实例或类的静态字段，也可是传递给方法的参数。</span><span class="sxs-lookup"><span data-stu-id="1e82f-123">It can be an instance or static field of a class, or it can be an argument passed to the method.</span></span> <span data-ttu-id="1e82f-124">尝试返回局部变量将生成编译器错误 CS8168：“无法按引用返回局部 "obj"，因为它不是 ref 局部变量”。</span><span class="sxs-lookup"><span data-stu-id="1e82f-124">Attempting to return a local variable generates compiler error CS8168, "Cannot return local 'obj' by reference because it is not a ref local."</span></span>

- <span data-ttu-id="1e82f-125">返回值不得为文本 `null`。</span><span class="sxs-lookup"><span data-stu-id="1e82f-125">The return value cannot be the literal `null`.</span></span> <span data-ttu-id="1e82f-126">返回 `null` 会生成编译器错误 CS8156“无法在此上下文中使用表达式，因为它可能不是以引用方式返回”。</span><span class="sxs-lookup"><span data-stu-id="1e82f-126">Returning `null` generates compiler error CS8156, "An expression cannot be used in this context because it may not be returned by reference."</span></span>

   <span data-ttu-id="1e82f-127">使用引用返回值的方法可以返回值当前为 null（未实例化）或[可以为 null 的类型](../nullable-types/index.md)的变量别名。</span><span class="sxs-lookup"><span data-stu-id="1e82f-127">A method with a ref return can return an alias to a variable whose value is currently the null (uninstantiated) value or a [nullable type](../nullable-types/index.md) for a value type.</span></span>
 
- <span data-ttu-id="1e82f-128">返回值不得为常量、枚举成员、通过属性的按值返回值或 `class`/`struct` 方法。</span><span class="sxs-lookup"><span data-stu-id="1e82f-128">The return value cannot be a constant, an enumeration member, the by-value return value from a property, or a method of a `class` or `struct`.</span></span> <span data-ttu-id="1e82f-129">违反此规则会生成编译器错误 CS8156“无法在此上下文中使用表达式，因为它可能不是以引用方式返回”。</span><span class="sxs-lookup"><span data-stu-id="1e82f-129">Violating this rule generates compiler error CS8156, "An expression cannot be used in this context because it may not be returned by reference."</span></span>

<span data-ttu-id="1e82f-130">此外，禁止对异步方法使用引用返回值。</span><span class="sxs-lookup"><span data-stu-id="1e82f-130">In addition, reference return values are not allowed on async methods.</span></span> <span data-ttu-id="1e82f-131">异步方法可能会在执行尚未完成时就返回值，尽管返回值仍未知。</span><span class="sxs-lookup"><span data-stu-id="1e82f-131">An asynchronous method may return before it has finished execution, while its return value is still unknown.</span></span>
 
## <a name="defining-a-ref-return-value"></a><span data-ttu-id="1e82f-132">定义 ref 返回值</span><span class="sxs-lookup"><span data-stu-id="1e82f-132">Defining a ref return value</span></span>

<span data-ttu-id="1e82f-133">返回引用返回值的方法必须满足以下两个条件：</span><span class="sxs-lookup"><span data-stu-id="1e82f-133">A method that returns a *reference return value* must satisfy the following two conditions:</span></span>

- <span data-ttu-id="1e82f-134">方法签名在返回类型前面有 [ref](../../language-reference/keywords/ref.md) 关键字。</span><span class="sxs-lookup"><span data-stu-id="1e82f-134">The method signature includes the [ref](../../language-reference/keywords/ref.md) keyword in front of the return type.</span></span>
- <span data-ttu-id="1e82f-135">方法主体中的每个 [return](../../language-reference/keywords/return.md) 语句都在返回实例的名称前面有 [ref](../../language-reference/keywords/ref.md) 关键字。</span><span class="sxs-lookup"><span data-stu-id="1e82f-135">Each [return](../../language-reference/keywords/return.md) statement in the method body includes the [ref](../../language-reference/keywords/ref.md) keyword in front of the name of the returned instance.</span></span>

<span data-ttu-id="1e82f-136">下面的示例方法满足这些条件，且返回对名为 `p` 的 `Person` 对象的引用：</span><span class="sxs-lookup"><span data-stu-id="1e82f-136">The following example shows a method that satisfies those conditions and returns a reference to a `Person` object named `p`:</span></span>

```csharp
public ref Person GetContactInformation(string fname, string lname)
{
    // ...method implementation...
    return ref p;
}
```

## <a name="consuming-a-ref-return-value"></a><span data-ttu-id="1e82f-137">使用 ref 返回值</span><span class="sxs-lookup"><span data-stu-id="1e82f-137">Consuming a ref return value</span></span>

<span data-ttu-id="1e82f-138">引用返回值是被调用方法范围中另一个变量的别名。</span><span class="sxs-lookup"><span data-stu-id="1e82f-138">The ref return value is an alias to another variable in the called method's scope.</span></span> <span data-ttu-id="1e82f-139">可以将引用返回值的所有使用都解释为，使用它取别名的变量：</span><span class="sxs-lookup"><span data-stu-id="1e82f-139">You can interpret any use of the ref return as using the variable it aliases:</span></span>

- <span data-ttu-id="1e82f-140">分配值时，就是将值分配到它取别名的变量。</span><span class="sxs-lookup"><span data-stu-id="1e82f-140">When you assign its value, you are assigning a value to the variable it aliases.</span></span>
- <span data-ttu-id="1e82f-141">读取值时，就是读取它取别名的变量的值。</span><span class="sxs-lookup"><span data-stu-id="1e82f-141">When you read its value, you are reading the value of the variable it aliases.</span></span>
- <span data-ttu-id="1e82f-142">如果以引用方式返回它，就是返回对相同变量所取的别名。</span><span class="sxs-lookup"><span data-stu-id="1e82f-142">If you return it *by reference*, you are returning an alias to that same variable.</span></span>
- <span data-ttu-id="1e82f-143">如果以引用方式将它传递到另一个方法，就是传递对它取别名的变量的引用。</span><span class="sxs-lookup"><span data-stu-id="1e82f-143">If you pass it to another method *by reference*, you are passing a reference to the variable it aliases.</span></span>
- <span data-ttu-id="1e82f-144">如果返回[引用本地](#ref-local)别名，就是返回相同变量的新别名。</span><span class="sxs-lookup"><span data-stu-id="1e82f-144">When you make a [ref local](#ref-local) alias, you make a new alias to the same variable.</span></span>


## <a name="ref-locals"></a><span data-ttu-id="1e82f-145">ref 局部变量</span><span class="sxs-lookup"><span data-stu-id="1e82f-145">Ref locals</span></span>

<span data-ttu-id="1e82f-146">假设 `GetContactInformation` 方法声明为引用返回：</span><span class="sxs-lookup"><span data-stu-id="1e82f-146">Assume the `GetContactInformation` method is declared as a ref return:</span></span>

```csharp
public ref Person GetContactInformation(string fname, string lname)
```

<span data-ttu-id="1e82f-147">按值分配会读取变量值，并将它分配给新变量：</span><span class="sxs-lookup"><span data-stu-id="1e82f-147">A by-value assignment reads the value of a variable and assigns it to a new variable:</span></span>

```csharp
Person p = contacts.GetContactInformation("Brandie", "Best");
```

<span data-ttu-id="1e82f-148">上面的分配将 `p` 声明为本地变量。</span><span class="sxs-lookup"><span data-stu-id="1e82f-148">The preceding assignment declares `p` as a local variable.</span></span> <span data-ttu-id="1e82f-149">它的初始值是通过读取 `GetContactInformation` 返回的值进行复制。</span><span class="sxs-lookup"><span data-stu-id="1e82f-149">Its initial value is copied from reading the value returned by `GetContactInformation`.</span></span> <span data-ttu-id="1e82f-150">之后对 `p` 的任何分配都不会更改 `GetContactInformation` 返回的变量值。</span><span class="sxs-lookup"><span data-stu-id="1e82f-150">Any future assignments to `p` will not change the value of the variable returned by `GetContactInformation`.</span></span> <span data-ttu-id="1e82f-151">变量 `p` 不再是返回的变量的别名。</span><span class="sxs-lookup"><span data-stu-id="1e82f-151">The variable `p` is no longer an alias to the variable returned.</span></span>

<span data-ttu-id="1e82f-152">声明引用本地变量，复制原始值的别名。</span><span class="sxs-lookup"><span data-stu-id="1e82f-152">You declare a *ref local* variable to copy the alias to the original value.</span></span> <span data-ttu-id="1e82f-153">在下面的分配中，`p` 是从 `GetContactInformation` 返回的变量的别名。</span><span class="sxs-lookup"><span data-stu-id="1e82f-153">In the following assignment, `p` is an alias to the variable returned from `GetContactInformation`.</span></span>

```csharp
ref Person p = ref contacts.GetContactInformation("Brandie", "Best");
```

<span data-ttu-id="1e82f-154">后续使用 `p` 等同于使用 `GetContactInformation` 返回的变量，因为 `p` 是此变量的别名。</span><span class="sxs-lookup"><span data-stu-id="1e82f-154">Subsequent usage of `p` is the same as using the variable returned by `GetContactInformation` because `p` is an alias for that variable.</span></span> <span data-ttu-id="1e82f-155">对 `p` 所做的更改也会更改从 `GetContactInformation` 返回的变量。</span><span class="sxs-lookup"><span data-stu-id="1e82f-155">Changes to `p` also change the variable returned from `GetContactInformation`.</span></span>

<span data-ttu-id="1e82f-156">`ref` 关键字用于局部变量声明前面和方法调用前面。</span><span class="sxs-lookup"><span data-stu-id="1e82f-156">The `ref` keyword is used both before the local variable declaration *and* before the method call.</span></span> 

<span data-ttu-id="1e82f-157">可通过相同方式按引用访问值。</span><span class="sxs-lookup"><span data-stu-id="1e82f-157">You can access a value by reference in the same way.</span></span> <span data-ttu-id="1e82f-158">在某些情况下，按引用访问值可避免潜在的高开销复制操作，从而提高性能。</span><span class="sxs-lookup"><span data-stu-id="1e82f-158">In some cases, accessing a value by reference increases performance by avoiding a potentially expensive copy operation.</span></span> <span data-ttu-id="1e82f-159">例如，以下语句显示用户可如何定义一个用于引用值的 ref 局部变量值。</span><span class="sxs-lookup"><span data-stu-id="1e82f-159">For example, the following statement shows how one can define a ref local value that is used to reference a value.</span></span>

```csharp
ref VeryLargeStruct reflocal = ref veryLargeStruct;
```

<span data-ttu-id="1e82f-160">`ref` 关键字用于局部变量声明前面和第二个示例中的值前面。</span><span class="sxs-lookup"><span data-stu-id="1e82f-160">The `ref` keyword is used both before the local variable declaration *and* before the value in the second example.</span></span> <span data-ttu-id="1e82f-161">在这两个示例中，如果无法同时将 `ref` 关键字包含在变量声明和赋值中，则会导致编译器错误 CS8172：“无法使用值对按引用变量进行初始化”。</span><span class="sxs-lookup"><span data-stu-id="1e82f-161">Failure to include both `ref` keywords in the variable declaration and assignment in both examples results in compiler error CS8172, "Cannot initialize a by-reference variable with a value."</span></span> 

<span data-ttu-id="1e82f-162">在低于 C# 7.3 的版本中，无法将 ref 局部变量重新分配为，在初始化后引用其他存储。</span><span class="sxs-lookup"><span data-stu-id="1e82f-162">Prior to C# 7.3, ref local variables couldn't be reassigned to refer to different storage after being initialized.</span></span> <span data-ttu-id="1e82f-163">此限制已取消。</span><span class="sxs-lookup"><span data-stu-id="1e82f-163">That restriction has been removed.</span></span> <span data-ttu-id="1e82f-164">下面的示例展示了如何重新分配：</span><span class="sxs-lookup"><span data-stu-id="1e82f-164">The following example shows a reassignment:</span></span>

```csharp
ref VeryLargeStruct reflocal = ref veryLargeStruct; // initialization
refLocal = ref anotherVeryLargeStruct; // reassigned, refLocal refers to different storage.
```

 <span data-ttu-id="1e82f-165">Ref 局部变量仍必须在声明时进行初始化。</span><span class="sxs-lookup"><span data-stu-id="1e82f-165">Ref local variables must still be initialized when they are declared.</span></span>

## <a name="ref-returns-and-ref-locals-an-example"></a><span data-ttu-id="1e82f-166">ref 返回结果和 ref 局部变量：示例</span><span class="sxs-lookup"><span data-stu-id="1e82f-166">Ref returns and ref locals: an example</span></span>

<span data-ttu-id="1e82f-167">下列示例定义存储整数值数组的 `NumberStore` 类。</span><span class="sxs-lookup"><span data-stu-id="1e82f-167">The following example defines a `NumberStore` class that stores an array of integer values.</span></span> <span data-ttu-id="1e82f-168">`FindNumber` 方法按引用返回第一个大于或等于作为参数传递的数字的数字。</span><span class="sxs-lookup"><span data-stu-id="1e82f-168">The `FindNumber` method returns by reference the first number that is greater than or equal to the number passed as an argument.</span></span> <span data-ttu-id="1e82f-169">如果没有大于或等于该参数的数字，则方法返回索引 0 中的数字。</span><span class="sxs-lookup"><span data-stu-id="1e82f-169">If no number is greater than or equal to the argument, the method returns the number in index 0.</span></span> 

[!code-csharp[ref-returns](../../../../samples/snippets/csharp/programming-guide/ref-returns/NumberStore.cs#1)]

<span data-ttu-id="1e82f-170">下列示例调用 `NumberStore.FindNumber` 方法来检索大于或等于 16 的第一个值。</span><span class="sxs-lookup"><span data-stu-id="1e82f-170">The following example calls the `NumberStore.FindNumber` method to retrieve the first value that is greater than or equal to 16.</span></span> <span data-ttu-id="1e82f-171">然后，调用方将该方法返回的值加倍。</span><span class="sxs-lookup"><span data-stu-id="1e82f-171">The caller then doubles the value returned by the method.</span></span> <span data-ttu-id="1e82f-172">示例输出表明，`NumberStore` 实例的数组元素值反映了更改。</span><span class="sxs-lookup"><span data-stu-id="1e82f-172">The output from the example shows the change reflected in the value of the array elements of the `NumberStore` instance.</span></span>

[!code-csharp[ref-returns](../../../../samples/snippets/csharp/programming-guide/ref-returns/NumberStore.cs#2)]

<span data-ttu-id="1e82f-173">如果引用返回值不受支持，需要通过返回数组元素及其值的索引来执行此类操作。</span><span class="sxs-lookup"><span data-stu-id="1e82f-173">Without support for reference return values, such an operation is performed by returning the index of the array element along with its value.</span></span> <span data-ttu-id="1e82f-174">然后，调用方可使用此索引修改单个方法调用中的值。</span><span class="sxs-lookup"><span data-stu-id="1e82f-174">The caller can then use this index to modify the value in a separate method call.</span></span> <span data-ttu-id="1e82f-175">但调用方也可修改要访问的索引，还可修改其他数组值。</span><span class="sxs-lookup"><span data-stu-id="1e82f-175">However, the caller can also modify the index to access and possibly modify other array values.</span></span>  

<span data-ttu-id="1e82f-176">下面的示例展示了如何在高于 C# 7.3 的版本中将 `FindNumber` 方法重写为使用 ref 局部重新分配：</span><span class="sxs-lookup"><span data-stu-id="1e82f-176">The following example shows how the `FindNumber` method could be rewritten after C# 7.3 to use ref local reassignment:</span></span>

[!code-csharp[ref-returns](../../../../samples/snippets/csharp/programming-guide/ref-returns/NumberStoreUpdated.cs#1)]

<span data-ttu-id="1e82f-177">如果查找的数字更接近数组末尾，这第二个版本就更高效且序列更长。</span><span class="sxs-lookup"><span data-stu-id="1e82f-177">This second version is more efficient with longer sequences in scenarios where the number sought is closer to the end of the array.</span></span>

## <a name="see-also"></a><span data-ttu-id="1e82f-178">请参阅</span><span class="sxs-lookup"><span data-stu-id="1e82f-178">See Also</span></span>

- [<span data-ttu-id="1e82f-179">ref 关键字</span><span class="sxs-lookup"><span data-stu-id="1e82f-179">ref keyword</span></span>](../../language-reference/keywords/ref.md)  
- [<span data-ttu-id="1e82f-180">具有值类型的引用语义</span><span class="sxs-lookup"><span data-stu-id="1e82f-180">Reference Semantics with Value Types</span></span>](../../../csharp/reference-semantics-with-value-types.md)
