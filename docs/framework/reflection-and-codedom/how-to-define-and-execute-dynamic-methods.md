---
title: "如何：定义和执行动态方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- reflection emit, dynamic methods
- dynamic methods
ms.assetid: 07d08a99-62c5-4254-bce2-2a75e55a18ab
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0b7384f625a6d1609294297645bebc335e72d1e8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-define-and-execute-dynamic-methods"></a><span data-ttu-id="1ea21-102">如何：定义和执行动态方法</span><span class="sxs-lookup"><span data-stu-id="1ea21-102">How to: Define and Execute Dynamic Methods</span></span>
<span data-ttu-id="1ea21-103">以下过程介绍如何定义和执行简单的动态方法和绑定到类实例的动态方法。</span><span class="sxs-lookup"><span data-stu-id="1ea21-103">The following procedures show how to define and execute a simple dynamic method and a dynamic method bound to an instance of a class.</span></span> <span data-ttu-id="1ea21-104">有关动态方法的更多信息，请参阅 <xref:System.Reflection.Emit.DynamicMethod> 类和[反射发出动态方法应用场景](http://msdn.microsoft.com/en-us/7c27ea3d-0f24-4bf3-8ceb-f49d33faca5e)。</span><span class="sxs-lookup"><span data-stu-id="1ea21-104">For more information on dynamic methods, see the <xref:System.Reflection.Emit.DynamicMethod> class and [Reflection Emit Dynamic Method Scenarios](http://msdn.microsoft.com/en-us/7c27ea3d-0f24-4bf3-8ceb-f49d33faca5e).</span></span>  
  
### <a name="to-define-and-execute-a-dynamic-method"></a><span data-ttu-id="1ea21-105">定义和执行动态方法</span><span class="sxs-lookup"><span data-stu-id="1ea21-105">To define and execute a dynamic method</span></span>  
  
1.  <span data-ttu-id="1ea21-106">声明用于执行方法的委托类型。</span><span class="sxs-lookup"><span data-stu-id="1ea21-106">Declare a delegate type to execute the method.</span></span> <span data-ttu-id="1ea21-107">考虑使用泛型委托，将需要声明的委托类型数降到最低。</span><span class="sxs-lookup"><span data-stu-id="1ea21-107">Consider using a generic delegate to minimize the number of delegate types you need to declare.</span></span> <span data-ttu-id="1ea21-108">以下代码声明两种可用于 `SquareIt` 方法的委托类型，其中一个是泛型。</span><span class="sxs-lookup"><span data-stu-id="1ea21-108">The following code declares two delegate types that could be used for the `SquareIt` method, and one of them is generic.</span></span>  
  
     [!code-cpp[DynamicMethodHowTo#2](../../../samples/snippets/cpp/VS_Snippets_CLR/DynamicMethodHowTo/cpp/source.cpp#2)]
     [!code-csharp[DynamicMethodHowTo#2](../../../samples/snippets/csharp/VS_Snippets_CLR/DynamicMethodHowTo/cs/source.cs#2)]
     [!code-vb[DynamicMethodHowTo#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/DynamicMethodHowTo/vb/source.vb#2)]  
  
2.  <span data-ttu-id="1ea21-109">创建用于为动态方法指定参数类型的数组。</span><span class="sxs-lookup"><span data-stu-id="1ea21-109">Create an array that specifies the parameter types for the dynamic method.</span></span> <span data-ttu-id="1ea21-110">在此示例中，唯一的参数为 `int`（在 Visual Basic 中为 `Integer`），所以数组只有一个元素。</span><span class="sxs-lookup"><span data-stu-id="1ea21-110">In this example, the only parameter is an `int` (`Integer` in Visual Basic), so the array has only one element.</span></span>  
  
     [!code-cpp[DynamicMethodHowTo#3](../../../samples/snippets/cpp/VS_Snippets_CLR/DynamicMethodHowTo/cpp/source.cpp#3)]
     [!code-csharp[DynamicMethodHowTo#3](../../../samples/snippets/csharp/VS_Snippets_CLR/DynamicMethodHowTo/cs/source.cs#3)]
     [!code-vb[DynamicMethodHowTo#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/DynamicMethodHowTo/vb/source.vb#3)]  
  
3.  <span data-ttu-id="1ea21-111">创建 <xref:System.Reflection.Emit.DynamicMethod>。</span><span class="sxs-lookup"><span data-stu-id="1ea21-111">Create a <xref:System.Reflection.Emit.DynamicMethod>.</span></span> <span data-ttu-id="1ea21-112">在此示例中，该方法命名为 `SquareIt`。</span><span class="sxs-lookup"><span data-stu-id="1ea21-112">In this example the method is named `SquareIt`.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="1ea21-113">不需要为动态方法命名，并且不能通过名称调用它们。</span><span class="sxs-lookup"><span data-stu-id="1ea21-113">It is not necessary to give dynamic methods names, and they cannot be invoked by name.</span></span> <span data-ttu-id="1ea21-114">多个动态方法可以具有相同的名称。</span><span class="sxs-lookup"><span data-stu-id="1ea21-114">Multiple dynamic methods can have the same name.</span></span> <span data-ttu-id="1ea21-115">但是，名称将在调用堆栈中显示并且可用于调试。</span><span class="sxs-lookup"><span data-stu-id="1ea21-115">However, the name appears in call stacks and can be useful for debugging.</span></span>  
  
     <span data-ttu-id="1ea21-116">返回值的类型指定为 `long`。</span><span class="sxs-lookup"><span data-stu-id="1ea21-116">The type of the return value is specified as `long`.</span></span> <span data-ttu-id="1ea21-117">该方法与包含 `Example` 类的模块关联，该类包含代码示例。</span><span class="sxs-lookup"><span data-stu-id="1ea21-117">The method is associated with the module that contains the `Example` class, which contains the example code.</span></span> <span data-ttu-id="1ea21-118">可以指定任何加载的模块。</span><span class="sxs-lookup"><span data-stu-id="1ea21-118">Any loaded module could be specified.</span></span> <span data-ttu-id="1ea21-119">动态方法的行为类似于模块级的 `static` 方法（在 Visual Basic 中为 `Shared`）。</span><span class="sxs-lookup"><span data-stu-id="1ea21-119">The dynamic method acts like a module-level `static` method (`Shared` in Visual Basic).</span></span>  
  
     [!code-cpp[DynamicMethodHowTo#4](../../../samples/snippets/cpp/VS_Snippets_CLR/DynamicMethodHowTo/cpp/source.cpp#4)]
     [!code-csharp[DynamicMethodHowTo#4](../../../samples/snippets/csharp/VS_Snippets_CLR/DynamicMethodHowTo/cs/source.cs#4)]
     [!code-vb[DynamicMethodHowTo#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/DynamicMethodHowTo/vb/source.vb#4)]  
  
4.  <span data-ttu-id="1ea21-120">发出方法主体。</span><span class="sxs-lookup"><span data-stu-id="1ea21-120">Emit the method body.</span></span> <span data-ttu-id="1ea21-121">在此示例中，使用 <xref:System.Reflection.Emit.ILGenerator> 对象发出 Microsoft 中间语言 (MSIL)。</span><span class="sxs-lookup"><span data-stu-id="1ea21-121">In this example, an <xref:System.Reflection.Emit.ILGenerator> object is used to emit the Microsoft intermediate language (MSIL).</span></span> <span data-ttu-id="1ea21-122">也可以结合使用 <xref:System.Reflection.Emit.DynamicILInfo> 对象与非托管代码生成器，发出 <xref:System.Reflection.Emit.DynamicMethod> 的方法主体。</span><span class="sxs-lookup"><span data-stu-id="1ea21-122">Alternatively, a <xref:System.Reflection.Emit.DynamicILInfo> object can be used in conjunction with unmanaged code generators to emit the method body for a <xref:System.Reflection.Emit.DynamicMethod>.</span></span>  
  
     <span data-ttu-id="1ea21-123">此示例中的 MSIL 将该参数（一个 `int`）加载到堆栈上，将其转换为 `long`，复制 `long`，然后将这两个数字相乘。</span><span class="sxs-lookup"><span data-stu-id="1ea21-123">The MSIL in this example loads the argument, which is an `int`, onto the stack, converts it to a `long`, duplicates the `long`, and multiplies the two numbers.</span></span> <span data-ttu-id="1ea21-124">这会将平方结果保留在堆栈中，方法只需返回即可。</span><span class="sxs-lookup"><span data-stu-id="1ea21-124">This leaves the squared result on the stack, and all the method has to do is return.</span></span>  
  
     [!code-cpp[DynamicMethodHowTo#5](../../../samples/snippets/cpp/VS_Snippets_CLR/DynamicMethodHowTo/cpp/source.cpp#5)]
     [!code-csharp[DynamicMethodHowTo#5](../../../samples/snippets/csharp/VS_Snippets_CLR/DynamicMethodHowTo/cs/source.cs#5)]
     [!code-vb[DynamicMethodHowTo#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/DynamicMethodHowTo/vb/source.vb#5)]  
  
5.  <span data-ttu-id="1ea21-125">通过调用 <xref:System.Reflection.Emit.DynamicMethod.CreateDelegate%2A> 方法创建表示动态方法的委托（在步骤 1 中声明）的实例。</span><span class="sxs-lookup"><span data-stu-id="1ea21-125">Create an instance of the delegate (declared in step 1) that represents the dynamic method by calling the <xref:System.Reflection.Emit.DynamicMethod.CreateDelegate%2A> method.</span></span> <span data-ttu-id="1ea21-126">创建委托即完成该方法，任何更改方法的进一步尝试（例如，添加更多 MSIL）都将被忽略。</span><span class="sxs-lookup"><span data-stu-id="1ea21-126">Creating the delegate completes the method, and any further attempts to change the method — for example, adding more MSIL — are ignored.</span></span> <span data-ttu-id="1ea21-127">以下代码使用泛型委托创建委托并调用它。</span><span class="sxs-lookup"><span data-stu-id="1ea21-127">The following code creates the delegate and invokes it, using a generic delegate.</span></span>  
  
     [!code-cpp[DynamicMethodHowTo#6](../../../samples/snippets/cpp/VS_Snippets_CLR/DynamicMethodHowTo/cpp/source.cpp#6)]
     [!code-csharp[DynamicMethodHowTo#6](../../../samples/snippets/csharp/VS_Snippets_CLR/DynamicMethodHowTo/cs/source.cs#6)]
     [!code-vb[DynamicMethodHowTo#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/DynamicMethodHowTo/vb/source.vb#6)]  
  
### <a name="to-define-and-execute-a-dynamic-method-that-is-bound-to-an-object"></a><span data-ttu-id="1ea21-128">定义和执行绑定到对象的动态方法</span><span class="sxs-lookup"><span data-stu-id="1ea21-128">To define and execute a dynamic method that is bound to an object</span></span>  
  
1.  <span data-ttu-id="1ea21-129">声明用于执行方法的委托类型。</span><span class="sxs-lookup"><span data-stu-id="1ea21-129">Declare a delegate type to execute the method.</span></span> <span data-ttu-id="1ea21-130">考虑使用泛型委托，将需要声明的委托类型数降到最低。</span><span class="sxs-lookup"><span data-stu-id="1ea21-130">Consider using a generic delegate to minimize the number of delegate types you need to declare.</span></span> <span data-ttu-id="1ea21-131">以下代码声明一个泛型委托类型，可使用该类型执行任何具有一个参数和一个返回值的方法，如果委托绑定到对象，则该类型也可以执行具有两个参数和一个返回值的方法。</span><span class="sxs-lookup"><span data-stu-id="1ea21-131">The following code declares a generic delegate type that can be used to execute any method with one parameter and a return value, or a method with two parameters and a return value if the delegate is bound to an object.</span></span>  
  
     [!code-cpp[DynamicMethodHowTo#12](../../../samples/snippets/cpp/VS_Snippets_CLR/DynamicMethodHowTo/cpp/source.cpp#12)]
     [!code-csharp[DynamicMethodHowTo#12](../../../samples/snippets/csharp/VS_Snippets_CLR/DynamicMethodHowTo/cs/source.cs#12)]
     [!code-vb[DynamicMethodHowTo#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/DynamicMethodHowTo/vb/source.vb#12)]  
  
2.  <span data-ttu-id="1ea21-132">创建用于为动态方法指定参数类型的数组。</span><span class="sxs-lookup"><span data-stu-id="1ea21-132">Create an array that specifies the parameter types for the dynamic method.</span></span> <span data-ttu-id="1ea21-133">如果表示方法的委托要绑定到对象，则第一个参数必须与委托绑定到的类型相匹配。</span><span class="sxs-lookup"><span data-stu-id="1ea21-133">If the delegate representing the method is to be bound to an object, the first parameter must match the type the delegate is bound to.</span></span> <span data-ttu-id="1ea21-134">在此示例中，存在两个参数，分别属于 `Example` 和 `int`（在 Visual Basic 中为 `Integer`）类型。</span><span class="sxs-lookup"><span data-stu-id="1ea21-134">In this example, there are two parameters, of type `Example` and type `int` (`Integer` in Visual Basic).</span></span>  
  
     [!code-cpp[DynamicMethodHowTo#13](../../../samples/snippets/cpp/VS_Snippets_CLR/DynamicMethodHowTo/cpp/source.cpp#13)]
     [!code-csharp[DynamicMethodHowTo#13](../../../samples/snippets/csharp/VS_Snippets_CLR/DynamicMethodHowTo/cs/source.cs#13)]
     [!code-vb[DynamicMethodHowTo#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR/DynamicMethodHowTo/vb/source.vb#13)]  
  
3.  <span data-ttu-id="1ea21-135">创建 <xref:System.Reflection.Emit.DynamicMethod>。</span><span class="sxs-lookup"><span data-stu-id="1ea21-135">Create a <xref:System.Reflection.Emit.DynamicMethod>.</span></span> <span data-ttu-id="1ea21-136">在此示例中，方法没有名称。</span><span class="sxs-lookup"><span data-stu-id="1ea21-136">In this example the method has no name.</span></span> <span data-ttu-id="1ea21-137">返回值的类型指定为 `int`（在 Visual Basic 中为 `Integer`）。</span><span class="sxs-lookup"><span data-stu-id="1ea21-137">The type of the return value is specified as `int` (`Integer` in Visual Basic).</span></span> <span data-ttu-id="1ea21-138">该方法可以访问 `Example` 类的私有成员和受保护成员。</span><span class="sxs-lookup"><span data-stu-id="1ea21-138">The method has access to the private and protected members of the `Example` class.</span></span>  
  
     [!code-cpp[DynamicMethodHowTo#14](../../../samples/snippets/cpp/VS_Snippets_CLR/DynamicMethodHowTo/cpp/source.cpp#14)]
     [!code-csharp[DynamicMethodHowTo#14](../../../samples/snippets/csharp/VS_Snippets_CLR/DynamicMethodHowTo/cs/source.cs#14)]
     [!code-vb[DynamicMethodHowTo#14](../../../samples/snippets/visualbasic/VS_Snippets_CLR/DynamicMethodHowTo/vb/source.vb#14)]  
  
4.  <span data-ttu-id="1ea21-139">发出方法主体。</span><span class="sxs-lookup"><span data-stu-id="1ea21-139">Emit the method body.</span></span> <span data-ttu-id="1ea21-140">在此示例中，使用 <xref:System.Reflection.Emit.ILGenerator> 对象发出 Microsoft 中间语言 (MSIL)。</span><span class="sxs-lookup"><span data-stu-id="1ea21-140">In this example, an <xref:System.Reflection.Emit.ILGenerator> object is used to emit the Microsoft intermediate language (MSIL).</span></span> <span data-ttu-id="1ea21-141">也可以结合使用 <xref:System.Reflection.Emit.DynamicILInfo> 对象与非托管代码生成器，发出 <xref:System.Reflection.Emit.DynamicMethod> 的方法主体。</span><span class="sxs-lookup"><span data-stu-id="1ea21-141">Alternatively, a <xref:System.Reflection.Emit.DynamicILInfo> object can be used in conjunction with unmanaged code generators to emit the method body for a <xref:System.Reflection.Emit.DynamicMethod>.</span></span>  
  
     <span data-ttu-id="1ea21-142">此示例中的 MSIL 加载第一个参数（一个 `Example` 类的实例），然后使用该参数加载类型 `int` 的专用实例字段的值。</span><span class="sxs-lookup"><span data-stu-id="1ea21-142">The MSIL in this example loads the first argument, which is an instance of the `Example` class, and uses it to load the value of a private instance field of type `int`.</span></span> <span data-ttu-id="1ea21-143">然后加载第二个参数，并将两个数相乘。</span><span class="sxs-lookup"><span data-stu-id="1ea21-143">The second argument is loaded, and the two numbers are multiplied.</span></span> <span data-ttu-id="1ea21-144">如果结果大于 `int`，将截断该值且丢弃最高有效位。</span><span class="sxs-lookup"><span data-stu-id="1ea21-144">If the result is larger than `int`, the value is truncated and the most significant bits are discarded.</span></span> <span data-ttu-id="1ea21-145">该方法返回，返回值保留在堆栈中。</span><span class="sxs-lookup"><span data-stu-id="1ea21-145">The method returns, with the return value on the stack.</span></span>  
  
     [!code-cpp[DynamicMethodHowTo#15](../../../samples/snippets/cpp/VS_Snippets_CLR/DynamicMethodHowTo/cpp/source.cpp#15)]
     [!code-csharp[DynamicMethodHowTo#15](../../../samples/snippets/csharp/VS_Snippets_CLR/DynamicMethodHowTo/cs/source.cs#15)]
     [!code-vb[DynamicMethodHowTo#15](../../../samples/snippets/visualbasic/VS_Snippets_CLR/DynamicMethodHowTo/vb/source.vb#15)]  
  
5.  <span data-ttu-id="1ea21-146">通过调用 <xref:System.Reflection.Emit.DynamicMethod.CreateDelegate%28System.Type%2CSystem.Object%29> 方法重载创建表示动态方法的委托（在步骤 1 中声明）的实例。</span><span class="sxs-lookup"><span data-stu-id="1ea21-146">Create an instance of the delegate (declared in step 1) that represents the dynamic method by calling the <xref:System.Reflection.Emit.DynamicMethod.CreateDelegate%28System.Type%2CSystem.Object%29> method overload.</span></span> <span data-ttu-id="1ea21-147">创建委托即完成该方法，任何更改方法的进一步尝试（例如，添加更多 MSIL）都将被忽略。</span><span class="sxs-lookup"><span data-stu-id="1ea21-147">Creating the delegate completes the method, and any further attempts to change the method — for example, adding more MSIL — are ignored.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="1ea21-148">可以多次调用 <xref:System.Reflection.Emit.DynamicMethod.CreateDelegate%2A> 方法，创建绑定到目标类型的其他实例的委托。</span><span class="sxs-lookup"><span data-stu-id="1ea21-148">You can call the <xref:System.Reflection.Emit.DynamicMethod.CreateDelegate%2A> method multiple times to create delegates bound to other instances of the target type.</span></span>  
  
     <span data-ttu-id="1ea21-149">以下代码将该方法绑定到 `Example` 类的一个新实例，该类的专用测试字段设置为 42。</span><span class="sxs-lookup"><span data-stu-id="1ea21-149">The following code binds the method to a new instance of the `Example` class whose private test field is set to 42.</span></span> <span data-ttu-id="1ea21-150">也就是说，每次调用委托时，都会将 `Example` 的实例传递给该方法的第一个参数。</span><span class="sxs-lookup"><span data-stu-id="1ea21-150">That is, each time the delegate is invoked the instance of `Example` is passed to the first parameter of the method.</span></span>  
  
     <span data-ttu-id="1ea21-151">使用委托 `OneParameter` 的原因是该方法的第一个参数始终会接收 `Example` 的实例。</span><span class="sxs-lookup"><span data-stu-id="1ea21-151">The delegate `OneParameter` is used because the first parameter of the method always receives the instance of `Example`.</span></span> <span data-ttu-id="1ea21-152">调用委托时，只需要使用第二个参数。</span><span class="sxs-lookup"><span data-stu-id="1ea21-152">When the delegate is invoked, only the second parameter is required.</span></span>  
  
     [!code-cpp[DynamicMethodHowTo#16](../../../samples/snippets/cpp/VS_Snippets_CLR/DynamicMethodHowTo/cpp/source.cpp#16)]
     [!code-csharp[DynamicMethodHowTo#16](../../../samples/snippets/csharp/VS_Snippets_CLR/DynamicMethodHowTo/cs/source.cs#16)]
     [!code-vb[DynamicMethodHowTo#16](../../../samples/snippets/visualbasic/VS_Snippets_CLR/DynamicMethodHowTo/vb/source.vb#16)]  
  
## <a name="example"></a><span data-ttu-id="1ea21-153">示例</span><span class="sxs-lookup"><span data-stu-id="1ea21-153">Example</span></span>  
 <span data-ttu-id="1ea21-154">以下代码示例演示一个简单的动态方法和一个绑定到类实例的动态方法。</span><span class="sxs-lookup"><span data-stu-id="1ea21-154">The following code example demonstrates a simple dynamic method and a dynamic method bound to an instance of a class.</span></span>  
  
 <span data-ttu-id="1ea21-155">简单动态方法具有一个 32 位整数参数，返回该整数的 64 位平方。</span><span class="sxs-lookup"><span data-stu-id="1ea21-155">The simple dynamic method takes one argument, a 32-bit integer, and returns the 64-bit square of that integer.</span></span> <span data-ttu-id="1ea21-156">使用泛型委托来调用该方法。</span><span class="sxs-lookup"><span data-stu-id="1ea21-156">A generic delegate is used to invoke the method.</span></span>  
  
 <span data-ttu-id="1ea21-157">第二个动态方法有两个参数，分别属于 `Example` 和 `int`（在 Visual Basic 中为 `Integer`）类型。</span><span class="sxs-lookup"><span data-stu-id="1ea21-157">The second dynamic method has two parameters, of type `Example` and type `int` (`Integer` in Visual Basic).</span></span> <span data-ttu-id="1ea21-158">创建动态方法后，将使用具有一个 `int` 类型参数的泛型委托将其绑定到 `Example` 的实例。</span><span class="sxs-lookup"><span data-stu-id="1ea21-158">When the dynamic method has been created, it is bound to an instance of `Example`, using a generic delegate that has one argument of type `int`.</span></span> <span data-ttu-id="1ea21-159">该委托没有 `Example` 类型的参数，因为方法的第一个参数始终接收 `Example` 的绑定实例。</span><span class="sxs-lookup"><span data-stu-id="1ea21-159">The delegate does not have an argument of type `Example` because the first parameter of the method always receives the bound instance of `Example`.</span></span> <span data-ttu-id="1ea21-160">调用委托时，只提供 `int` 参数。</span><span class="sxs-lookup"><span data-stu-id="1ea21-160">When the delegate is invoked, only the `int` argument is supplied.</span></span> <span data-ttu-id="1ea21-161">此动态方法访问 `Example` 类的专用字段，并返回专用字段和 `int` 参数的乘积。</span><span class="sxs-lookup"><span data-stu-id="1ea21-161">This dynamic method accesses a private field of the `Example` class and returns the product of the private field and the `int` argument.</span></span>  
  
 <span data-ttu-id="1ea21-162">该代码示例定义可用于执行方法的委托。</span><span class="sxs-lookup"><span data-stu-id="1ea21-162">The code example defines delegates that can be used to execute the methods.</span></span>  
  
 [!code-cpp[DynamicMethodHowTo#1](../../../samples/snippets/cpp/VS_Snippets_CLR/DynamicMethodHowTo/cpp/source.cpp#1)]
 [!code-csharp[DynamicMethodHowTo#1](../../../samples/snippets/csharp/VS_Snippets_CLR/DynamicMethodHowTo/cs/source.cs#1)]
 [!code-vb[DynamicMethodHowTo#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/DynamicMethodHowTo/vb/source.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="1ea21-163">编译代码</span><span class="sxs-lookup"><span data-stu-id="1ea21-163">Compiling the Code</span></span>  
  
-   <span data-ttu-id="1ea21-164">代码包含编译所需的 C# `using` 语句（在 Visual Basic 中为 `Imports`）。</span><span class="sxs-lookup"><span data-stu-id="1ea21-164">The code contains the C# `using` statements (`Imports` in Visual Basic) necessary for compilation.</span></span>  
  
-   <span data-ttu-id="1ea21-165">不需要其他程序集引用。</span><span class="sxs-lookup"><span data-stu-id="1ea21-165">No additional assembly references are required.</span></span>  
  
-   <span data-ttu-id="1ea21-166">使用 csc.exe、vbc.exe 或 cl.exe 在命令行编译代码。</span><span class="sxs-lookup"><span data-stu-id="1ea21-166">Compile the code at the command line using csc.exe, vbc.exe, or cl.exe.</span></span> <span data-ttu-id="1ea21-167">若要在 Visual Studio 中编译代码，请将代码置于控制台应用程序项目模板中。</span><span class="sxs-lookup"><span data-stu-id="1ea21-167">To compile the code in Visual Studio, place it in a console application project template.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ea21-168">请参阅</span><span class="sxs-lookup"><span data-stu-id="1ea21-168">See Also</span></span>  
 <xref:System.Reflection.Emit.DynamicMethod>  
 [<span data-ttu-id="1ea21-169">使用反射发出</span><span class="sxs-lookup"><span data-stu-id="1ea21-169">Using Reflection Emit</span></span>](http://msdn.microsoft.com/en-us/ccc6540d-0e2c-4d89-b456-eb7353f9e9ac)  
 [<span data-ttu-id="1ea21-170">反射发出动态方法应用场景</span><span class="sxs-lookup"><span data-stu-id="1ea21-170">Reflection Emit Dynamic Method Scenarios</span></span>](http://msdn.microsoft.com/en-us/7c27ea3d-0f24-4bf3-8ceb-f49d33faca5e)
