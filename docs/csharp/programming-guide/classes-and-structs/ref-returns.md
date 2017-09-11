---
title: "ref 返回值和 ref 局部变量（C# 指南）"
description: "了解如何定义和使用 ref 返回值和 ref 局部变量"
author: rpetrusha
ms.author: ronpet
ms.date: 05/30/2017
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 18cf7a4b-29f0-4b14-85b8-80af754aabd8
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 753c620e1352dfc5fc57c380c66479c8e2d9b0ee
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="ref-returns-and-ref-locals"></a><span data-ttu-id="21b39-103">ref 返回值和局部变量</span><span class="sxs-lookup"><span data-stu-id="21b39-103">Ref returns and ref locals</span></span>

<span data-ttu-id="21b39-104">从 C# 7 开始，C# 支持引用返回值（ref 返回值）。</span><span class="sxs-lookup"><span data-stu-id="21b39-104">Starting with C# 7, C# supports reference return values (ref returns).</span></span> <span data-ttu-id="21b39-105">引用返回值允许方法将对象的引用（而不是值）返回给调用方。</span><span class="sxs-lookup"><span data-stu-id="21b39-105">A reference return value allows a method to return a reference to an object, rather than a value, back to a caller.</span></span> <span data-ttu-id="21b39-106">然后，调用方可以选择将返回的对象视为按值返回或按引用返回。</span><span class="sxs-lookup"><span data-stu-id="21b39-106">The caller can then choose to treat the returned object returned as if it were returned by value or by reference.</span></span> <span data-ttu-id="21b39-107">如果按引用返回的值被调用方处理为引用（而非值），则该值即为 ref 局部变量。</span><span class="sxs-lookup"><span data-stu-id="21b39-107">A value returned by reference that the caller handles as a reference rather than a value is a ref local).</span></span>

## <a name="what-is-a-reference-return-value"></a><span data-ttu-id="21b39-108">什么是引用返回值？</span><span class="sxs-lookup"><span data-stu-id="21b39-108">What is a reference return value?</span></span>

<span data-ttu-id="21b39-109">绝大多数开发者都很熟悉将参数按引用传递给被调用的方法。</span><span class="sxs-lookup"><span data-stu-id="21b39-109">Most developers are familiar with passing an argument to a called method *by reference*.</span></span> <span data-ttu-id="21b39-110">被调用方法的参数列表包括按引用传递的值，并且被调用方法对值所做的任何更改均返回给调用方。</span><span class="sxs-lookup"><span data-stu-id="21b39-110">A called method's argument list includes a value passed by reference, and any changes made to its value by the called method are returned to the caller.</span></span> <span data-ttu-id="21b39-111">引用返回值则恰巧相反：</span><span class="sxs-lookup"><span data-stu-id="21b39-111">A *reference return value* is the opposite:</span></span>

- <span data-ttu-id="21b39-112">被调用方法的返回值（而非被传递给它的参数）是一个引用。</span><span class="sxs-lookup"><span data-stu-id="21b39-112">The called method's return value, rather than an argument passed to it, is a reference.</span></span>

- <span data-ttu-id="21b39-113">调用方（而非被调用的方法）可以修改由方法返回的值。</span><span class="sxs-lookup"><span data-stu-id="21b39-113">The caller, rather than the called method, can modify the value returned by the method.</span></span>

- <span data-ttu-id="21b39-114">不是参数的修改反映在调用方上对象的状态中，而是调用方对方法返回值的修改反映在其方法被调用的对象的状态中。</span><span class="sxs-lookup"><span data-stu-id="21b39-114">Instead of modifications to the argument that are reflected in state of the object on the caller, modifications to the method's return value by the caller are reflected in the state of the object whose method was called.</span></span>

<span data-ttu-id="21b39-115">引用返回值可生成更紧凑的代码，并允许对象仅公开个别数据项，例如对调用方有用的数组元素。</span><span class="sxs-lookup"><span data-stu-id="21b39-115">Reference return values can produce more compact code, as well as allow an object to expose only the individual data items, such as an array element, that are of interest to the caller.</span></span> <span data-ttu-id="21b39-116">这可以降低调用方无意间修改对象状态的风险。</span><span class="sxs-lookup"><span data-stu-id="21b39-116">This reduces the likelihood that the caller will inadvertently modify the object's state.</span></span>

<span data-ttu-id="21b39-117">对于能作为引用返回值被方法返回的值，这里还存在一些限制。</span><span class="sxs-lookup"><span data-stu-id="21b39-117">There are some restrictions on the value that a method can return as a reference return value.</span></span> <span data-ttu-id="21b39-118">这些方法包括：</span><span class="sxs-lookup"><span data-stu-id="21b39-118">These include:</span></span>

- <span data-ttu-id="21b39-119">返回值不可为 `void`。</span><span class="sxs-lookup"><span data-stu-id="21b39-119">The return value cannot be `void`.</span></span> <span data-ttu-id="21b39-120">尝试使用 `void` 定义方法时，引用返回值将生成编译器错误 CS1547：“关键字 "void" 不能在此上下文中使用”。</span><span class="sxs-lookup"><span data-stu-id="21b39-120">Attempting to define a method with a `void` reference return value generates compiler error CS1547, "Keyword 'void' cannot be used in this context."</span></span>
 
- <span data-ttu-id="21b39-121">返回值不能是返回该值的方法中的局部变量；其范围必须超越返回它的方法。</span><span class="sxs-lookup"><span data-stu-id="21b39-121">The return value cannot be a local variable in the method that returns it; it must have a scope that is outside the method that returns it.</span></span> <span data-ttu-id="21b39-122">它可以是实例或类的静态字段，也可是传递给方法的参数。</span><span class="sxs-lookup"><span data-stu-id="21b39-122">It can be an instance or static field of a class, or it can be an argument passed to the method.</span></span> <span data-ttu-id="21b39-123">尝试返回局部变量将生成编译器错误 CS8168：“无法按引用返回局部 "obj"，因为它不是 ref 局部变量”。</span><span class="sxs-lookup"><span data-stu-id="21b39-123">Attempting to return a local variable generates compiler error CS8168, "Cannot return local 'obj' by reference because it is not a ref local."</span></span>

- <span data-ttu-id="21b39-124">返回值不可为 `null`。</span><span class="sxs-lookup"><span data-stu-id="21b39-124">The return value cannot be a `null`.</span></span> <span data-ttu-id="21b39-125">尝试返回 `null` 将生成编译器错误 CS8156：“无法在此上下文中使用表达式，因为它可能没有按引用返回”。</span><span class="sxs-lookup"><span data-stu-id="21b39-125">Attempting to return `null` generates compiler error CS8156, "An expression cannot be used in this context because it may not be returned by reference."</span></span>

   <span data-ttu-id="21b39-126">如果包含 ref 返回值的方法需要返回 null 值，则可为引用类型返回 null（未实例化）值，或为值类型返回[可以为 null 的类型](../nullable-types/index.md)。</span><span class="sxs-lookup"><span data-stu-id="21b39-126">If a method with a ref return needs to return a null value, you can either return a null (uninstantiated) value for a reference type or a [nullable type](../nullable-types/index.md) for a value type.</span></span>
 
- <span data-ttu-id="21b39-127">返回值不能为常数或枚举成员，也不能是 `class` 或 `struct` 的属性。</span><span class="sxs-lookup"><span data-stu-id="21b39-127">The return value cannot be a constant, an enumeration member, or a property of a `class` or `struct`.</span></span> <span data-ttu-id="21b39-128">尝试返回它们将生成编译器错误 CS8156：“无法在此上下文中使用表达式，因为它可能没有按引用返回”。</span><span class="sxs-lookup"><span data-stu-id="21b39-128">Attempting to return these generates compiler error CS8156, "An expression cannot be used in this context because it may not be returned by reference."</span></span>

<span data-ttu-id="21b39-129">此外，由于异步方法可能在完成执行前就返回，且已知其返回值，因此不允许在 `async` 方法中使用引用返回值。</span><span class="sxs-lookup"><span data-stu-id="21b39-129">In addition, because an asynchronous method may return before it has finished execution and its return value is known, reference return values are not allowed on `async` methods.</span></span>
 
## <a name="defining-a-ref-return-value"></a><span data-ttu-id="21b39-130">定义 ref 返回值</span><span class="sxs-lookup"><span data-stu-id="21b39-130">Defining a ref return value</span></span>

<span data-ttu-id="21b39-131">通过向方法签名的返回类型添加 [ref](../../language-reference/keywords/ref.md) 关键字来定义 ref 返回值。</span><span class="sxs-lookup"><span data-stu-id="21b39-131">You define a ref return value by adding the [ref](../../language-reference/keywords/ref.md) keyword to the return type of the method signature.</span></span> <span data-ttu-id="21b39-132">例如下列签名表示，`GetContactInformation` 属性将对 `Person` 对象的引用返回给调用方：</span><span class="sxs-lookup"><span data-stu-id="21b39-132">For example, the following signature indicates that the `GetContactInformation` property returns a reference to a `Person` object to the caller:</span></span>

```csharp
public ref Person GetContactInformation(string fname, string lname);
```

<span data-ttu-id="21b39-133">此外，方法正文中每个 [return](../../language-reference/keywords/return.md) 语句所返回对象的名称前面须有 [ref](../../language-reference/keywords/ref.md) 关键字。</span><span class="sxs-lookup"><span data-stu-id="21b39-133">In addition, the name of the object returned by each [return](../../language-reference/keywords/return.md) statement in the method body must be preceded by the [ref](../../language-reference/keywords/ref.md) keyword.</span></span> <span data-ttu-id="21b39-134">例如，下列 `return` 语句按引用返回名为 `p` 的 `Person` 对象：</span><span class="sxs-lookup"><span data-stu-id="21b39-134">For example, the following `return` statement returns a `Person` object named `p` by reference:</span></span>

```csharp
return ref p;
```

## <a name="consuming-a-ref-return-value"></a><span data-ttu-id="21b39-135">使用 ref 返回值</span><span class="sxs-lookup"><span data-stu-id="21b39-135">Consuming a ref return value</span></span>

<span data-ttu-id="21b39-136">调用方可通过以下任一方式来处理 ref 返回值：</span><span class="sxs-lookup"><span data-stu-id="21b39-136">A caller can handle a ref return value in either of two ways:</span></span>

- <span data-ttu-id="21b39-137">作为从方法中按值返回的普通值。</span><span class="sxs-lookup"><span data-stu-id="21b39-137">As an ordinary value returned by value from a method.</span></span> <span data-ttu-id="21b39-138">调用方可选择忽略返回值是引用返回值。</span><span class="sxs-lookup"><span data-stu-id="21b39-138">The caller can choose to ignore that the return value is a reference return value.</span></span> <span data-ttu-id="21b39-139">在这种情况中，对方法调用所返回的值进行的任何更改都不会反映在被调用类型的状态中。</span><span class="sxs-lookup"><span data-stu-id="21b39-139">In this case, any changes made to the value returned by the method call are not reflected in the state of the called type.</span></span> <span data-ttu-id="21b39-140">如果返回的值是一个值类型，对方法调用所返回的值进行的任何更改都不会反映在被调用类型的状态中。</span><span class="sxs-lookup"><span data-stu-id="21b39-140">If the returned value is a value type, any changes made to the value returned by the method call are not reflected in the state of the called type.</span></span>

- <span data-ttu-id="21b39-141">作为引用返回值。</span><span class="sxs-lookup"><span data-stu-id="21b39-141">As a reference return value.</span></span> <span data-ttu-id="21b39-142">调用方必须定义作为 [ref 局部变量](#ref-local)被赋予引用返回值的变量，且对方法调用所返回的值进行的任何更改都将反映在被调用类型的状态中。</span><span class="sxs-lookup"><span data-stu-id="21b39-142">The caller must define the variable to which the reference return value is assigned as a [ref local](#ref-local), and any changes to the value returned by the method call are reflected in the state of the called type.</span></span> 

## <a name="ref-locals"></a><span data-ttu-id="21b39-143">ref 局部变量</span><span class="sxs-lookup"><span data-stu-id="21b39-143">Ref locals</span></span>

<span data-ttu-id="21b39-144">若要将引用返回值作为引用来处理，调用方必须使用 `ref` 关键字将值声明为 ref 局部变量。</span><span class="sxs-lookup"><span data-stu-id="21b39-144">To handle the reference return value as a reference, the caller must declare the value to be a *ref local* by using the `ref` keyword.</span></span> <span data-ttu-id="21b39-145">例如，如果 `Person.GetContactInfomation` 方法所返回的值被作为引用（而非值）来使用，则方法调用将显示为：</span><span class="sxs-lookup"><span data-stu-id="21b39-145">For example, if the value returned by the `Person.GetContactInfomation` method is to be consumed as a reference rather than a value, the method call appears as:</span></span>

```csharp
ref Person p = ref contacts.GetContactInformation("Brandie", "Best");
```

<span data-ttu-id="21b39-146">注意，请同时在局部变量声明前和方法调用前使用 `ref` 关键字。</span><span class="sxs-lookup"><span data-stu-id="21b39-146">Note that the `ref` keyword is used both before the local variable declaration *and* before the method call.</span></span> <span data-ttu-id="21b39-147">无法同时将 `ref` 关键字包含在变量声明和赋值将导致编译器错误 CS8172：“无法使用值对按引用变量进行初始化”。</span><span class="sxs-lookup"><span data-stu-id="21b39-147">Failure to include both `ref` keywords in the variable declaration and assignment results in compiler error CS8172, "Cannot initialize a by-reference variable with a value."</span></span> 
 
<span data-ttu-id="21b39-148">对方法所返回的 `Person` 对象的后续更改将反映在 `contacts` 对象中。</span><span class="sxs-lookup"><span data-stu-id="21b39-148">Subsequent changes to the `Person` object returned by the method are reflected in the `contacts` object.</span></span>

<span data-ttu-id="21b39-149">如果未使用 `ref` 关键字将 `p` 定义为 ref 局部变量，则调用方对 `p` 所做的任何更改都不会反映在 `contacts` 对象中。</span><span class="sxs-lookup"><span data-stu-id="21b39-149">If `p` is not defined as a ref local by using the `ref` keyword, any changes made to `p` by the caller are not reflected in the `contacts` object.</span></span>
 
## <a name="ref-returns-and-ref-locals-an-example"></a><span data-ttu-id="21b39-150">ref 返回结果和 ref 局部变量：示例</span><span class="sxs-lookup"><span data-stu-id="21b39-150">Ref returns and ref locals: an example</span></span>

<span data-ttu-id="21b39-151">下列示例定义存储整数值数组的 `NumberStore` 类。</span><span class="sxs-lookup"><span data-stu-id="21b39-151">The following example defines a `NumberStore` class that stores an array of integer values.</span></span> <span data-ttu-id="21b39-152">`FindNumber` 方法按引用返回第一个大于或等于作为参数传递的数字的数字。</span><span class="sxs-lookup"><span data-stu-id="21b39-152">The `FindNumber` method returns by reference the first number that is greater than or equal to the number passed as an argument.</span></span> <span data-ttu-id="21b39-153">如果没有大于或等于该参数的数字，则方法返回索引 0 中的数字。</span><span class="sxs-lookup"><span data-stu-id="21b39-153">If no number is greater than or equal to the argument, the method returns the number in index 0.</span></span> 

<span data-ttu-id="21b39-154">[!CODE-cs[ref-returns](../../../../samples/snippets/csharp/programming-guide/ref-returns/ref-returns1.cs#1)]</span><span class="sxs-lookup"><span data-stu-id="21b39-154">[!CODE-cs[ref-returns](../../../../samples/snippets/csharp/programming-guide/ref-returns/ref-returns1.cs#1)]</span></span>

<span data-ttu-id="21b39-155">下列示例调用 `NumberStore.FindNumber` 方法来检索大于或等于 16 的第一个值。</span><span class="sxs-lookup"><span data-stu-id="21b39-155">The following example calls the `NumberStore.FindNumber` method to retrieve the first value that is greater than or equal to 16.</span></span> <span data-ttu-id="21b39-156">然后，调用方将该方法返回的值加倍。</span><span class="sxs-lookup"><span data-stu-id="21b39-156">The caller then doubles the value returned by the method.</span></span> <span data-ttu-id="21b39-157">如示例中的输出所示，此更改将反映在 `NumberStore` 实例的数组元素的值中。</span><span class="sxs-lookup"><span data-stu-id="21b39-157">As the output from the example shows, this change is reflected in the value of the array elements of the `NumberStore` instance.</span></span>

<span data-ttu-id="21b39-158">[!CODE-cs[ref-returns](../../../../samples/snippets/csharp/programming-guide/ref-returns/ref-returns1.cs#2)]</span><span class="sxs-lookup"><span data-stu-id="21b39-158">[!CODE-cs[ref-returns](../../../../samples/snippets/csharp/programming-guide/ref-returns/ref-returns1.cs#2)]</span></span>

<span data-ttu-id="21b39-159">在不支持引用返回值的情况下，此类操作通常通过返回数组元素的索引和它的值来执行。</span><span class="sxs-lookup"><span data-stu-id="21b39-159">Without support for reference return values, such an operation is usually performed by returning the index of the array element along with its value.</span></span> <span data-ttu-id="21b39-160">然后，调用方可使用此索引修改单个方法调用中的值。</span><span class="sxs-lookup"><span data-stu-id="21b39-160">The caller can then use this index to modify the value in a separate method call.</span></span> <span data-ttu-id="21b39-161">但调用方也可修改要访问的索引，还可修改其他数组值。</span><span class="sxs-lookup"><span data-stu-id="21b39-161">However, the caller can also modify the index to access and possibly modify other array values.</span></span>  
 
## <a name="see-also"></a><span data-ttu-id="21b39-162">另请参阅</span><span class="sxs-lookup"><span data-stu-id="21b39-162">See also</span></span>

[<span data-ttu-id="21b39-163">ref 关键字</span><span class="sxs-lookup"><span data-stu-id="21b39-163">ref keyword</span></span>](../../language-reference/keywords/ref.md)

