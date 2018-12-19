---
title: 方法 - C# 编程指南
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- methods [C#]
- C# language, methods
ms.assetid: cc738f07-e8cd-4683-9585-9f40c0667c37
ms.openlocfilehash: df2d7837217f4267f95ed73948a4eb479cc035c1
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2018
ms.locfileid: "53244409"
---
# <a name="methods-c-programming-guide"></a><span data-ttu-id="9b91f-102">方法（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="9b91f-102">Methods (C# Programming Guide)</span></span>
<span data-ttu-id="9b91f-103">方法是包含一系列语句的代码块。</span><span class="sxs-lookup"><span data-stu-id="9b91f-103">A method is a code block that contains a series of statements.</span></span> <span data-ttu-id="9b91f-104">程序通过调用该方法并指定任何所需的方法参数使语句得以执行。</span><span class="sxs-lookup"><span data-stu-id="9b91f-104">A program causes the statements to be executed by calling the method and specifying any required method arguments.</span></span> <span data-ttu-id="9b91f-105">在 C# 中，每个执行的指令均在方法的上下文中执行。</span><span class="sxs-lookup"><span data-stu-id="9b91f-105">In C#, every executed instruction is performed in the context of a method.</span></span> <span data-ttu-id="9b91f-106">Main 方法是每个 C# 应用程序的入口点，并在启动程序时由公共语言运行时 (CLR) 调用。</span><span class="sxs-lookup"><span data-stu-id="9b91f-106">The Main method is the entry point for every C# application and it is called by the common language runtime (CLR) when the program is started.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9b91f-107">本主题讨论命名的方法。</span><span class="sxs-lookup"><span data-stu-id="9b91f-107">This topic discusses named methods.</span></span> <span data-ttu-id="9b91f-108">有关匿名函数的信息，请参阅[匿名函数](../../../csharp/programming-guide/statements-expressions-operators/anonymous-functions.md)。</span><span class="sxs-lookup"><span data-stu-id="9b91f-108">For information about anonymous functions, see [Anonymous Functions](../../../csharp/programming-guide/statements-expressions-operators/anonymous-functions.md).</span></span>  
  
## <a name="method-signatures"></a><span data-ttu-id="9b91f-109">方法签名</span><span class="sxs-lookup"><span data-stu-id="9b91f-109">Method Signatures</span></span>  
 <span data-ttu-id="9b91f-110">通过指定访问级别（如 [或](../../../csharp/language-reference/keywords/class.md) ）、可选修饰符（如 [或](../../../csharp/language-reference/keywords/struct.md) ）、返回值、方法的名称以及任何方法参数，在 `public` 类 `private`或 `abstract` 结构 `sealed`中声明方法。</span><span class="sxs-lookup"><span data-stu-id="9b91f-110">Methods are declared in a [class](../../../csharp/language-reference/keywords/class.md) or [struct](../../../csharp/language-reference/keywords/struct.md) by specifying the access level such as `public` or `private`, optional modifiers such as `abstract` or `sealed`, the return value, the name of the method, and any method parameters.</span></span> <span data-ttu-id="9b91f-111">这些部件一起构成方法的签名。</span><span class="sxs-lookup"><span data-stu-id="9b91f-111">These parts together are the signature of the method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9b91f-112">出于方法重载的目的，方法的返回类型不是方法签名的一部分。</span><span class="sxs-lookup"><span data-stu-id="9b91f-112">A return type of a method is not part of the signature of the method for the purposes of method overloading.</span></span> <span data-ttu-id="9b91f-113">但是在确定委托和它所指向的方法之间的兼容性时，它是方法签名的一部分。</span><span class="sxs-lookup"><span data-stu-id="9b91f-113">However, it is part of the signature of the method when determining the compatibility between a delegate and the method that it points to.</span></span>  
  
 <span data-ttu-id="9b91f-114">方法参数在括号内，并且用逗号分隔。</span><span class="sxs-lookup"><span data-stu-id="9b91f-114">Method parameters are enclosed in parentheses and are separated by commas.</span></span> <span data-ttu-id="9b91f-115">空括号指示方法不需要任何参数。</span><span class="sxs-lookup"><span data-stu-id="9b91f-115">Empty parentheses indicate that the method requires no parameters.</span></span> <span data-ttu-id="9b91f-116">此类包含四种方法：</span><span class="sxs-lookup"><span data-stu-id="9b91f-116">This class contains four methods:</span></span>  
  
 [!code-csharp[csProgGuideObjects#40](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/methods_1.cs)]  
  
## <a name="method-access"></a><span data-ttu-id="9b91f-117">方法访问</span><span class="sxs-lookup"><span data-stu-id="9b91f-117">Method Access</span></span>  
 <span data-ttu-id="9b91f-118">调用对象上的方法就像访问字段。</span><span class="sxs-lookup"><span data-stu-id="9b91f-118">Calling a method on an object is like accessing a field.</span></span> <span data-ttu-id="9b91f-119">在对象名之后添加一个句点、方法名和括号。</span><span class="sxs-lookup"><span data-stu-id="9b91f-119">After the object name, add a period, the name of the method, and parentheses.</span></span> <span data-ttu-id="9b91f-120">参数列在括号里，并且用逗号分隔。</span><span class="sxs-lookup"><span data-stu-id="9b91f-120">Arguments are listed within the parentheses, and are separated by commas.</span></span> <span data-ttu-id="9b91f-121">因此，可在以下示例中调用 `Motorcycle` 类的方法：</span><span class="sxs-lookup"><span data-stu-id="9b91f-121">The methods of the `Motorcycle` class can therefore be called as in the following example:</span></span>  
  
 [!code-csharp[csProgGuideObjects#41](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/methods_2.cs)]  
  
## <a name="method-parameters-vs-arguments"></a><span data-ttu-id="9b91f-122">方法参数与自变量</span><span class="sxs-lookup"><span data-stu-id="9b91f-122">Method Parameters vs. Arguments</span></span>  
 <span data-ttu-id="9b91f-123">该方法定义指定任何所需参数的名称和类型。</span><span class="sxs-lookup"><span data-stu-id="9b91f-123">The method definition specifies the names and types of any parameters that are required.</span></span> <span data-ttu-id="9b91f-124">调用代码调用该方法时，它为每个参数提供了称为参数的具体值。</span><span class="sxs-lookup"><span data-stu-id="9b91f-124">When calling code calls the method, it provides concrete values called arguments for each parameter.</span></span> <span data-ttu-id="9b91f-125">参数必须与参数类型兼容，但调用代码中使用的参数名（如果有）不需要与方法中定义的参数名相同。</span><span class="sxs-lookup"><span data-stu-id="9b91f-125">The arguments must be compatible with the parameter type but the argument name (if any) used in the calling code does not have to be the same as the parameter named defined in the method.</span></span> <span data-ttu-id="9b91f-126">例如:</span><span class="sxs-lookup"><span data-stu-id="9b91f-126">For example:</span></span>  
  
 [!code-csharp[csProgGuideObjects#74](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/methods_3.cs)]  
  
## <a name="passing-by-reference-vs-passing-by-value"></a><span data-ttu-id="9b91f-127">按引用传递与按值传递</span><span class="sxs-lookup"><span data-stu-id="9b91f-127">Passing by Reference vs. Passing by Value</span></span>  
 <span data-ttu-id="9b91f-128">默认情况下，值类型传递给方法时，传递的是副本而不是对象本身。</span><span class="sxs-lookup"><span data-stu-id="9b91f-128">By default, when a value type is passed to a method, a copy is passed instead of the object itself.</span></span> <span data-ttu-id="9b91f-129">因此，对参数的更改不会影响调用方法中的原始副本。</span><span class="sxs-lookup"><span data-stu-id="9b91f-129">Therefore, changes to the argument have no effect on the original copy in the calling method.</span></span> <span data-ttu-id="9b91f-130">可以使用 ref 关键字按引用传递值类型。</span><span class="sxs-lookup"><span data-stu-id="9b91f-130">You can pass a value-type by reference by using the ref keyword.</span></span> <span data-ttu-id="9b91f-131">有关详细信息，请参阅[传递值类型参数](../../../csharp/programming-guide/classes-and-structs/passing-value-type-parameters.md)。</span><span class="sxs-lookup"><span data-stu-id="9b91f-131">For more information, see [Passing Value-Type Parameters](../../../csharp/programming-guide/classes-and-structs/passing-value-type-parameters.md).</span></span> <span data-ttu-id="9b91f-132">有关内置值类型的列表，请参阅[值类型表](../../../csharp/language-reference/keywords/value-types-table.md)。</span><span class="sxs-lookup"><span data-stu-id="9b91f-132">For a list of built-in value types, see [Value Types Table](../../../csharp/language-reference/keywords/value-types-table.md).</span></span>  
  
 <span data-ttu-id="9b91f-133">引用类型的对象传递到方法中时，将传递对对象的引用。</span><span class="sxs-lookup"><span data-stu-id="9b91f-133">When an object of a reference type is passed to a method, a reference to the object is passed.</span></span> <span data-ttu-id="9b91f-134">也就是说，该方法接收的不是对象本身，而是指示该对象位置的参数。</span><span class="sxs-lookup"><span data-stu-id="9b91f-134">That is, the method receives not the object itself but an argument that indicates the location of the object.</span></span> <span data-ttu-id="9b91f-135">如果通过使用此引用更改对象的成员，即使是按值传递该对象，此更改也会反映在调用方法的参数中。</span><span class="sxs-lookup"><span data-stu-id="9b91f-135">If you change a member of the object by using this reference, the change is reflected in the argument in the calling method, even if you pass the object by value.</span></span>  
  
 <span data-ttu-id="9b91f-136">通过使用 `class` 关键字创建引用类型，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="9b91f-136">You create a reference type by using the `class` keyword, as the following example shows.</span></span>  
  
 [!code-csharp[csProgGuideObjects#42](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/methods_4.cs)]  
  
 <span data-ttu-id="9b91f-137">现在，如果将基于此类型的对象传递到方法，则将传递对对象的引用。</span><span class="sxs-lookup"><span data-stu-id="9b91f-137">Now, if you pass an object that is based on this type to a method, a reference to the object is passed.</span></span> <span data-ttu-id="9b91f-138">下面的示例将 `SampleRefType` 类型的对象传递到 `ModifyObject`方法。</span><span class="sxs-lookup"><span data-stu-id="9b91f-138">The following example passes an object of type `SampleRefType` to method `ModifyObject`.</span></span>  
  
 [!code-csharp[csProgGuideObjects#75](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/methods_5.cs)]  
  
 <span data-ttu-id="9b91f-139">该示例执行的内容实质上与先前示例相同，均按值将参数传递到方法。</span><span class="sxs-lookup"><span data-stu-id="9b91f-139">The example does essentially the same thing as the previous example in that it passes an argument by value to a method.</span></span> <span data-ttu-id="9b91f-140">但是因为使用了引用类型，结果有所不同。</span><span class="sxs-lookup"><span data-stu-id="9b91f-140">But, because a reference type is used, the result is different.</span></span> <span data-ttu-id="9b91f-141">`ModifyObject` 中所做的对形参 `value` 的 `obj`字段的修改，也会更改 `value` 方法中实参 `rt`的 `TestRefType` 字段。</span><span class="sxs-lookup"><span data-stu-id="9b91f-141">The modification that is made in `ModifyObject` to the `value` field of the parameter, `obj`, also changes the `value` field of the argument, `rt`, in the `TestRefType` method.</span></span> <span data-ttu-id="9b91f-142">`TestRefType` 方法显示 33 作为输出。</span><span class="sxs-lookup"><span data-stu-id="9b91f-142">The `TestRefType` method displays 33 as the output.</span></span>  
  
 <span data-ttu-id="9b91f-143">有关如何通过引用和值传递引用类型的详细信息，请参阅[传递引用类型参数](../../../csharp/programming-guide/classes-and-structs/passing-reference-type-parameters.md)和[引用类型](../../../csharp/language-reference/keywords/reference-types.md)。</span><span class="sxs-lookup"><span data-stu-id="9b91f-143">For more information about how to pass reference types by reference and by value, see [Passing Reference-Type Parameters](../../../csharp/programming-guide/classes-and-structs/passing-reference-type-parameters.md) and [Reference Types](../../../csharp/language-reference/keywords/reference-types.md).</span></span>  
  
## <a name="return-values"></a><span data-ttu-id="9b91f-144">返回值</span><span class="sxs-lookup"><span data-stu-id="9b91f-144">Return Values</span></span>  
<span data-ttu-id="9b91f-145">方法可以将值返回到调用方。</span><span class="sxs-lookup"><span data-stu-id="9b91f-145">Methods can return a value to the caller.</span></span> <span data-ttu-id="9b91f-146">如果列在方法名之前的返回类型不是 `void`，则该方法可通过使用 `return` 关键字返回值。</span><span class="sxs-lookup"><span data-stu-id="9b91f-146">If the return type, the type listed before the method name, is not `void`, the method can return the value by using the `return` keyword.</span></span> <span data-ttu-id="9b91f-147">带 `return` 关键字，后跟与返回类型匹配的值的语句将该值返回到方法调用方。</span><span class="sxs-lookup"><span data-stu-id="9b91f-147">A statement with the `return` keyword followed by a value that matches the return type will return that value to the method caller.</span></span> 

<span data-ttu-id="9b91f-148">值可以按值或[按引用](ref-returns.md)返回到调用方，以 C# 7.0 开头。</span><span class="sxs-lookup"><span data-stu-id="9b91f-148">The value can be returned to the caller by value or, starting with C# 7.0, [by reference](ref-returns.md).</span></span> <span data-ttu-id="9b91f-149">如果在方法签名中使用 `ref` 关键字且其跟随每个 `return` 关键字，值将按引用返回到调用方。</span><span class="sxs-lookup"><span data-stu-id="9b91f-149">Values are returned to the caller by reference if the `ref` keyword is used in the method signature and it follows each `return` keyword.</span></span> <span data-ttu-id="9b91f-150">例如，以下方法签名和返回语句指示该方法按对调用方的引用返回变量名 `estDistance`。</span><span class="sxs-lookup"><span data-stu-id="9b91f-150">For example, the following method signature and return statement indicate that the method returns a variable names `estDistance` by reference to the caller.</span></span>

```csharp
public ref double GetEstimatedDistance()
{
   return ref estDistance;
}
```

<span data-ttu-id="9b91f-151">`return` 关键字还会停止执行该方法。</span><span class="sxs-lookup"><span data-stu-id="9b91f-151">The `return` keyword also stops the execution of the method.</span></span> <span data-ttu-id="9b91f-152">如果返回类型为 `void`，没有值的 `return` 语句仍可用于停止执行该方法。</span><span class="sxs-lookup"><span data-stu-id="9b91f-152">If the return type is `void`, a `return` statement without a value is still useful to stop the execution of the method.</span></span> <span data-ttu-id="9b91f-153">没有 `return` 关键字，当方法到达代码块结尾时，将停止执行。</span><span class="sxs-lookup"><span data-stu-id="9b91f-153">Without the `return` keyword, the method will stop executing when it reaches the end of the code block.</span></span> <span data-ttu-id="9b91f-154">具有非空的返回类型的方法都需要使用 `return` 关键字来返回值。</span><span class="sxs-lookup"><span data-stu-id="9b91f-154">Methods with a non-void return type are required to use the `return` keyword to return a value.</span></span> <span data-ttu-id="9b91f-155">例如，这两种方法都使用 `return` 关键字来返回整数：</span><span class="sxs-lookup"><span data-stu-id="9b91f-155">For example, these two methods use the `return` keyword to return integers:</span></span>  
  
 [!code-csharp[csProgGuideObjects#44](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/methods_6.cs)]  
  
 <span data-ttu-id="9b91f-156">若要使用从方法返回的值，调用方法可以在相同类型的值足够的地方使用该方法调用本身。</span><span class="sxs-lookup"><span data-stu-id="9b91f-156">To use a value returned from a method, the calling method can use the method call itself anywhere a value of the same type would be sufficient.</span></span> <span data-ttu-id="9b91f-157">也可以将返回值分配给变量。</span><span class="sxs-lookup"><span data-stu-id="9b91f-157">You can also assign the return value to a variable.</span></span> <span data-ttu-id="9b91f-158">例如，以下两个代码示例实现了相同的目标：</span><span class="sxs-lookup"><span data-stu-id="9b91f-158">For example, the following two code examples accomplish the same goal:</span></span>  
  
 [!code-csharp[csProgGuideObjects#45](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/methods_7.cs)]  
  
 [!code-csharp[csProgGuideObjects#46](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/methods_8.cs)]  
  
 <span data-ttu-id="9b91f-159">在这种情况下，使用本地变量 `result`存储值是可选的。</span><span class="sxs-lookup"><span data-stu-id="9b91f-159">Using a local variable, in this case, `result`, to store a value is optional.</span></span> <span data-ttu-id="9b91f-160">此步骤可以帮助提高代码的可读性，或者如果需要存储该方法整个范围内自变量的原始值，则此步骤可能很有必要。</span><span class="sxs-lookup"><span data-stu-id="9b91f-160">It may help the readability of the code, or it may be necessary if you need to store the original value of the argument for the entire scope of the method.</span></span>  

<span data-ttu-id="9b91f-161">若要使用按引用从方法返回的值，必须声明 [ref local](ref-returns.md#ref-locals) 变量（如果想要修改其值）。</span><span class="sxs-lookup"><span data-stu-id="9b91f-161">To use a value returned by reference from a method, you must declare a [ref local](ref-returns.md#ref-locals) variable if you intend to modify its value.</span></span> <span data-ttu-id="9b91f-162">例如，如果 `Planet.GetEstimatedDistance` 方法按引用返回 <xref:System.Double> 值，则可以将其定义为具有如下所示代码的 ref local 变量：</span><span class="sxs-lookup"><span data-stu-id="9b91f-162">For example, if the `Planet.GetEstimatedDistance` method returns a <xref:System.Double> value by reference, you can define it as a ref local variable with code like the following:</span></span>

```csharp
ref int distance = plant 
```

<span data-ttu-id="9b91f-163">如果调用函数将数组传递到 `M`，则无需从修改数组内容的方法 `M` 返回多维数组。</span><span class="sxs-lookup"><span data-stu-id="9b91f-163">Returning a multi-dimensional array from a method, `M`, that modifies the array's contents is not necessary if the calling function passed the array into `M`.</span></span>  <span data-ttu-id="9b91f-164">你可能会从 `M` 返回生成的数组以获得值的良好样式或功能流，但这是不必要的，因为 C# 按值传递所有引用类型，且数组引用的值是指向数组的指针。</span><span class="sxs-lookup"><span data-stu-id="9b91f-164">You may return the resulting array from `M` for good style or functional flow of values, but it is not necessary because C# passes all reference types by value, and the value of an array reference is the pointer to the array.</span></span> <span data-ttu-id="9b91f-165">在方法 `M` 中，引用该数组的任何代码都能观察到数组内容的任何更改，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="9b91f-165">In the method `M`, any changes to the array's contents are observable by any code that has a reference to the array, as shown in the following example.</span></span>  
  
```csharp  
static void Main(string[] args)
{
    int[,] matrix = new int[2, 2];
    FillMatrix(matrix);
    // matrix is now full of -1
}

public static void FillMatrix(int[,] matrix)
{
    for (int i = 0; i < matrix.GetLength(0); i++)
    {
        for (int j = 0; j < matrix.GetLength(1); j++)
        {
            matrix[i, j] = -1;
        }
    }
}
```  
  
 <span data-ttu-id="9b91f-166">有关详细信息，请参阅 [return](../../../csharp/language-reference/keywords/return.md)。</span><span class="sxs-lookup"><span data-stu-id="9b91f-166">For more information, see [return](../../../csharp/language-reference/keywords/return.md).</span></span>  
  
## <a name="async-methods"></a><span data-ttu-id="9b91f-167">异步方法</span><span class="sxs-lookup"><span data-stu-id="9b91f-167">Async Methods</span></span>  
 <span data-ttu-id="9b91f-168">通过使用异步功能，你可以调用异步方法而无需使用显式回调，也不需要跨多个方法或 lambda 表达式来手动拆分代码。</span><span class="sxs-lookup"><span data-stu-id="9b91f-168">By using the async feature, you can invoke asynchronous methods without using explicit callbacks or manually splitting your code across multiple methods or lambda expressions.</span></span> 
  
 <span data-ttu-id="9b91f-169">如果用 [async](../../../csharp/language-reference/keywords/async.md) 修饰符标记方法，则可以使用该方法中的 [await](../../../csharp/language-reference/keywords/await.md) 运算符。</span><span class="sxs-lookup"><span data-stu-id="9b91f-169">If you mark a method with the [async](../../../csharp/language-reference/keywords/async.md) modifier, you can use the [await](../../../csharp/language-reference/keywords/await.md) operator in the method.</span></span> <span data-ttu-id="9b91f-170">当控件到达异步方法中的 await 表达式时，控件将返回到调用方，并在等待任务完成前，方法中进度将一直处于挂起状态。</span><span class="sxs-lookup"><span data-stu-id="9b91f-170">When control reaches an await expression in the async method, control returns to the caller, and progress in the method is suspended until the awaited task completes.</span></span> <span data-ttu-id="9b91f-171">任务完成后，可以在方法中恢复执行。</span><span class="sxs-lookup"><span data-stu-id="9b91f-171">When the task is complete, execution can resume in the method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9b91f-172">异步方法在遇到第一个尚未完成的 awaited 对象或到达异步方法的末尾时（以先发生者为准），将返回到调用方。</span><span class="sxs-lookup"><span data-stu-id="9b91f-172">An async method returns to the caller when either it encounters the first awaited object that’s not yet complete or it gets to the end of the async method, whichever occurs first.</span></span>  
  
 <span data-ttu-id="9b91f-173">异步方法可以具有 <xref:System.Threading.Tasks.Task%601>、 <xref:System.Threading.Tasks.Task>或 void 返回类型。</span><span class="sxs-lookup"><span data-stu-id="9b91f-173">An async method can have a return type of <xref:System.Threading.Tasks.Task%601>, <xref:System.Threading.Tasks.Task>, or void.</span></span> <span data-ttu-id="9b91f-174">Void 返回类型主要用于定义需要 void 返回类型的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="9b91f-174">The void return type is used primarily to define event handlers, where a void return type is required.</span></span> <span data-ttu-id="9b91f-175">无法等待返回 void 的异步方法，并且返回 void 方法的调用方无法捕获该方法引发的异常。</span><span class="sxs-lookup"><span data-stu-id="9b91f-175">An async method that returns void can't be awaited, and the caller of a void-returning method can't catch exceptions that the method throws.</span></span>  
  
 <span data-ttu-id="9b91f-176">在以下示例中， `DelayAsync` 是具有 <xref:System.Threading.Tasks.Task%601>返回类型的异步方法。</span><span class="sxs-lookup"><span data-stu-id="9b91f-176">In the following example, `DelayAsync` is an async method that has a return type of <xref:System.Threading.Tasks.Task%601>.</span></span> <span data-ttu-id="9b91f-177">`DelayAsync` 具有返回整数的 `return` 语句。</span><span class="sxs-lookup"><span data-stu-id="9b91f-177">`DelayAsync` has a `return` statement that returns an integer.</span></span> <span data-ttu-id="9b91f-178">因此， `DelayAsync` 的方法声明必须具有 `Task<int>`的返回类型。</span><span class="sxs-lookup"><span data-stu-id="9b91f-178">Therefore the method declaration of `DelayAsync` must have a return type of `Task<int>`.</span></span> <span data-ttu-id="9b91f-179">因为返回类型是 `Task<int>`， `await` 中 `DoSomethingAsync` 表达式的计算如以下语句所示得出整数： `int result = await delayTask`。</span><span class="sxs-lookup"><span data-stu-id="9b91f-179">Because the return type is `Task<int>`, the evaluation of the `await` expression in `DoSomethingAsync` produces an integer as the following statement demonstrates: `int result = await delayTask`.</span></span>  
  
 <span data-ttu-id="9b91f-180">`startButton_Click` 方法是具有 void 返回类型的异步方法的示例。</span><span class="sxs-lookup"><span data-stu-id="9b91f-180">The `startButton_Click` method is an example of an async method that has a return type of void.</span></span> <span data-ttu-id="9b91f-181">因为 `DoSomethingAsync` 是异步方法，调用 `DoSomethingAsync` 的任务必须等待，如以下语句所示： `await DoSomethingAsync();`。</span><span class="sxs-lookup"><span data-stu-id="9b91f-181">Because `DoSomethingAsync` is an async method, the task for the call to `DoSomethingAsync` must be awaited, as the following statement shows: `await DoSomethingAsync();`.</span></span> <span data-ttu-id="9b91f-182">`startButton_Click` 方法必须使用 `async` 修饰符进行定义，因为该方法具有 `await` 表达式。</span><span class="sxs-lookup"><span data-stu-id="9b91f-182">The `startButton_Click` method must be defined with the `async` modifier because the method has an `await` expression.</span></span>  
  
 [!code-csharp[csAsyncMethod#2](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/methods_9.cs)]  
  
 <span data-ttu-id="9b91f-183">异步方法不能声明任何 [ref](../../../csharp/language-reference/keywords/ref.md) 或 [out](../../../csharp/language-reference/keywords/out-parameter-modifier.md) 参数，但是可以调用具有这类参数的方法。</span><span class="sxs-lookup"><span data-stu-id="9b91f-183">An async method can't declare any [ref](../../../csharp/language-reference/keywords/ref.md) or [out](../../../csharp/language-reference/keywords/out-parameter-modifier.md) parameters, but it can call methods that have such parameters.</span></span>  
  
 <span data-ttu-id="9b91f-184">有关异步方法的详细信息，请参阅[使用 async 和 await 的异步编程](../../../csharp/programming-guide/concepts/async/index.md)、[异步程序中的控制流](../../../csharp/programming-guide/concepts/async/control-flow-in-async-programs.md)和[异步返回类型](../../../csharp/programming-guide/concepts/async/async-return-types.md)。</span><span class="sxs-lookup"><span data-stu-id="9b91f-184">For more information about async methods, see [Asynchronous Programming with async and await](../../../csharp/programming-guide/concepts/async/index.md), [Control Flow in Async Programs](../../../csharp/programming-guide/concepts/async/control-flow-in-async-programs.md), and [Async Return Types](../../../csharp/programming-guide/concepts/async/async-return-types.md).</span></span>  
  
## <a name="expression-body-definitions"></a><span data-ttu-id="9b91f-185">表达式主体定义</span><span class="sxs-lookup"><span data-stu-id="9b91f-185">Expression Body Definitions</span></span>  
 <span data-ttu-id="9b91f-186">具有立即仅返回表达式结果，或单个语句作为方法主题的方法定义很常见。</span><span class="sxs-lookup"><span data-stu-id="9b91f-186">It is common to have method definitions that simply return immediately with the result of an expression, or that have a single statement as the body of the method.</span></span>  <span data-ttu-id="9b91f-187">以下是使用 `=>`定义此类方法的语法快捷方式：</span><span class="sxs-lookup"><span data-stu-id="9b91f-187">There is a syntax shortcut for defining such methods using `=>`:</span></span>  
  
```csharp  
public Point Move(int dx, int dy) => new Point(x + dx, y + dy);   
public void Print() => Console.WriteLine(First + " " + Last);  
// Works with operators, properties, and indexers too.  
public static Complex operator +(Complex a, Complex b) => a.Add(b);  
public string Name => First + " " + Last;   
public Customer this[long id] => store.LookupCustomer(id);  
```  
  
 <span data-ttu-id="9b91f-188">如果该方法返回 `void` 或是异步方法，则该方法的主体必须是语句表达式（与 lambda 相同）。</span><span class="sxs-lookup"><span data-stu-id="9b91f-188">If the method returns `void` or is an async method, then the body of the method must be a statement expression (same as with lambdas).</span></span>  <span data-ttu-id="9b91f-189">对于属性和索引器，两者必须是只读的，并且不使用 `get` 访问器关键字。</span><span class="sxs-lookup"><span data-stu-id="9b91f-189">For properties and indexers, they must be read only, and you don't use the `get` accessor keyword.</span></span>  
  
## <a name="iterators"></a><span data-ttu-id="9b91f-190">Iterators</span><span class="sxs-lookup"><span data-stu-id="9b91f-190">Iterators</span></span>  
 <span data-ttu-id="9b91f-191">迭代器对集合执行自定义迭代，如列表或数组。</span><span class="sxs-lookup"><span data-stu-id="9b91f-191">An iterator performs a custom iteration over a collection, such as a list or an array.</span></span> <span data-ttu-id="9b91f-192">迭代器使用 [yield return](../../../csharp/language-reference/keywords/yield.md) 语句返回元素，每次返回一个。</span><span class="sxs-lookup"><span data-stu-id="9b91f-192">An iterator uses the [yield return](../../../csharp/language-reference/keywords/yield.md) statement to return each element one at a time.</span></span> <span data-ttu-id="9b91f-193">当 [yield return](../../../csharp/language-reference/keywords/yield.md) 语句到达时，将记住当前在代码中的位置。</span><span class="sxs-lookup"><span data-stu-id="9b91f-193">When a [yield return](../../../csharp/language-reference/keywords/yield.md) statement is reached, the current location in code is remembered.</span></span> <span data-ttu-id="9b91f-194">下次调用迭代器时，将从该位置重新开始执行。</span><span class="sxs-lookup"><span data-stu-id="9b91f-194">Execution is restarted from that location when the iterator is called the next time.</span></span>  
  
 <span data-ttu-id="9b91f-195">通过使用 [foreach](../../../csharp/language-reference/keywords/foreach-in.md) 语句从客户端代码调用迭代器。</span><span class="sxs-lookup"><span data-stu-id="9b91f-195">You call an iterator from client code by using a [foreach](../../../csharp/language-reference/keywords/foreach-in.md) statement.</span></span>  
  
 <span data-ttu-id="9b91f-196">迭代器的返回类型可以是 <xref:System.Collections.IEnumerable>、 <xref:System.Collections.Generic.IEnumerable%601>、 <xref:System.Collections.IEnumerator>或 <xref:System.Collections.Generic.IEnumerator%601>。</span><span class="sxs-lookup"><span data-stu-id="9b91f-196">The return type of an iterator can be <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, or <xref:System.Collections.Generic.IEnumerator%601>.</span></span>  
  
 <span data-ttu-id="9b91f-197">有关更多信息，请参见 [迭代器](../../../csharp/programming-guide/concepts/iterators.md)。</span><span class="sxs-lookup"><span data-stu-id="9b91f-197">For more information, see [Iterators](../../../csharp/programming-guide/concepts/iterators.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="9b91f-198">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="9b91f-198">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="9b91f-199">请参阅</span><span class="sxs-lookup"><span data-stu-id="9b91f-199">See Also</span></span>

- [<span data-ttu-id="9b91f-200">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="9b91f-200">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="9b91f-201">类和结构</span><span class="sxs-lookup"><span data-stu-id="9b91f-201">Classes and Structs</span></span>](index.md)  
- [<span data-ttu-id="9b91f-202">访问修饰符</span><span class="sxs-lookup"><span data-stu-id="9b91f-202">Access Modifiers</span></span>](access-modifiers.md)  
- [<span data-ttu-id="9b91f-203">静态类和静态类成员</span><span class="sxs-lookup"><span data-stu-id="9b91f-203">Static Classes and Static Class Members</span></span>](static-classes-and-static-class-members.md)  
- [<span data-ttu-id="9b91f-204">继承</span><span class="sxs-lookup"><span data-stu-id="9b91f-204">Inheritance</span></span>](inheritance.md)  
- [<span data-ttu-id="9b91f-205">抽象类、密封类及类成员</span><span class="sxs-lookup"><span data-stu-id="9b91f-205">Abstract and Sealed Classes and Class Members</span></span>](abstract-and-sealed-classes-and-class-members.md)  
- [<span data-ttu-id="9b91f-206">params</span><span class="sxs-lookup"><span data-stu-id="9b91f-206">params</span></span>](../../../csharp/language-reference/keywords/params.md)  
- [<span data-ttu-id="9b91f-207">return</span><span class="sxs-lookup"><span data-stu-id="9b91f-207">return</span></span>](../../../csharp/language-reference/keywords/return.md)  
- [<span data-ttu-id="9b91f-208">out</span><span class="sxs-lookup"><span data-stu-id="9b91f-208">out</span></span>](../../../csharp/language-reference/keywords/out.md)  
- [<span data-ttu-id="9b91f-209">ref</span><span class="sxs-lookup"><span data-stu-id="9b91f-209">ref</span></span>](../../../csharp/language-reference/keywords/ref.md)  
- [<span data-ttu-id="9b91f-210">传递参数</span><span class="sxs-lookup"><span data-stu-id="9b91f-210">Passing Parameters</span></span>](passing-parameters.md)
