---
title: 使用模式匹配功能来扩展数据类型
description: 本高级教程展示了如何使用模式匹配技术，通过单独创建的数据和算法来创建功能。
ms.date: 03/13/2019
ms.custom: mvc
ms.openlocfilehash: 58e4a9175752c7845507f48a3684747092dc609a
ms.sourcegitcommit: 4735bb7741555bcb870d7b42964d3774f4897a6e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/30/2019
ms.locfileid: "66378073"
---
# <a name="tutorial-using-pattern-matching-features-to-extend-data-types"></a><span data-ttu-id="62c10-103">教程：使用模式匹配功能来扩展数据类型</span><span class="sxs-lookup"><span data-stu-id="62c10-103">Tutorial: Using pattern matching features to extend data types</span></span>

<span data-ttu-id="62c10-104">C# 7 引入了基本模式匹配功能。</span><span class="sxs-lookup"><span data-stu-id="62c10-104">C# 7 introduced basic pattern matching features.</span></span> <span data-ttu-id="62c10-105">C# 8 通过新增表达式和模式，扩展了这些功能。</span><span class="sxs-lookup"><span data-stu-id="62c10-105">Those features are extended in C# 8 with new expressions and patterns.</span></span> <span data-ttu-id="62c10-106">可以编写行为类似于扩展其他库中可能有的类型的功能。</span><span class="sxs-lookup"><span data-stu-id="62c10-106">You can write functionality that behaves as though you extended types that may be in other libraries.</span></span> <span data-ttu-id="62c10-107">模式的另一个用途是，创建应用程序需要的功能，但此功能不是要扩展的类型的基本功能。</span><span class="sxs-lookup"><span data-stu-id="62c10-107">Another use for patterns is to create functionality your application requires that isn't a fundamental feature of the type being extended.</span></span>

<span data-ttu-id="62c10-108">在本教程中，你将了解：</span><span class="sxs-lookup"><span data-stu-id="62c10-108">In this tutorial, you'll learn how to:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="62c10-109">识别应使用模式匹配的情况。</span><span class="sxs-lookup"><span data-stu-id="62c10-109">Recognize situations where pattern matching should be used.</span></span>
> * <span data-ttu-id="62c10-110">使用模式匹配表达式来实现基于类型和属性值的行为。</span><span class="sxs-lookup"><span data-stu-id="62c10-110">Use pattern matching expressions to implement behavior based on types and property values.</span></span>
> * <span data-ttu-id="62c10-111">结合使用模式匹配和其他方法来创建完整算法。</span><span class="sxs-lookup"><span data-stu-id="62c10-111">Combine pattern matching with other techniques to create complete algorithms.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="62c10-112">系统必备</span><span class="sxs-lookup"><span data-stu-id="62c10-112">Prerequisites</span></span>

<span data-ttu-id="62c10-113">需要将计算机设置为运行 .NET Core（包括 C# 8.0 预览版编译器）。</span><span class="sxs-lookup"><span data-stu-id="62c10-113">You'll need to set up your machine to run .NET Core, including the C# 8.0 preview compiler.</span></span> <span data-ttu-id="62c10-114">最新 [Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) 或最新 [.NET Core 3.0 预览版](https://dotnet.microsoft.com/download/dotnet-core/3.0)随附 C# 8 预览版编译器。</span><span class="sxs-lookup"><span data-stu-id="62c10-114">The C# 8 preview compiler is available with the latest [Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019), or the latest [.NET Core 3.0 preview](https://dotnet.microsoft.com/download/dotnet-core/3.0).</span></span>

<span data-ttu-id="62c10-115">本教程假设你熟悉 C# 和 .NET，包括 Visual Studio 或 .NET Core CLI。</span><span class="sxs-lookup"><span data-stu-id="62c10-115">This tutorial assumes you're familiar with C# and .NET, including either Visual Studio or the .NET Core CLI.</span></span>

## <a name="scenarios-for-pattern-matching"></a><span data-ttu-id="62c10-116">模式匹配方案</span><span class="sxs-lookup"><span data-stu-id="62c10-116">Scenarios for pattern matching</span></span>

<span data-ttu-id="62c10-117">新式开发通常包括从多个源集成数据，并在一个整体应用程序中呈现以相应数据为依据的信息和见解。</span><span class="sxs-lookup"><span data-stu-id="62c10-117">Modern development often includes integrating data from multiple sources and presenting information and insights from that data in a single cohesive application.</span></span> <span data-ttu-id="62c10-118">你和你的团队无法控制或访问表示传入数据的所有类型。</span><span class="sxs-lookup"><span data-stu-id="62c10-118">You and your team won't have control or access for all the types that represent the incoming data.</span></span>

<span data-ttu-id="62c10-119">面向对象的经典设计要求，在应用程序中创建表示多个数据源中的所有数据类型的类型。</span><span class="sxs-lookup"><span data-stu-id="62c10-119">The classic object-oriented design would call for creating types in your application that represent each data type from those multiple data sources.</span></span> <span data-ttu-id="62c10-120">然后，应用程序便能处理这些新类型、生成继承层次结构、创建虚拟方法并实现抽象。</span><span class="sxs-lookup"><span data-stu-id="62c10-120">Then, your application would work with those new types, build inheritance hierarchies, create virtual methods, and implement abstractions.</span></span> <span data-ttu-id="62c10-121">这些技术起作用，而且有时候是最佳工具。</span><span class="sxs-lookup"><span data-stu-id="62c10-121">Those techniques work, and sometimes they are the best tools.</span></span> <span data-ttu-id="62c10-122">不过，在其他时候，你可以编写更少的代码。</span><span class="sxs-lookup"><span data-stu-id="62c10-122">Other times you can write less code.</span></span> <span data-ttu-id="62c10-123">可使用将数据与管理相应数据的操作分离开来的技术，编写更明确的代码。</span><span class="sxs-lookup"><span data-stu-id="62c10-123">You can write more clear code using techniques that separate the data from the operations that manipulate that data.</span></span>

<span data-ttu-id="62c10-124">在本教程中，你将创建并探索从一个方案的多个外部源中提取传入数据的应用程序。</span><span class="sxs-lookup"><span data-stu-id="62c10-124">In this tutorial, you'll create and explore an application that takes incoming data from several external sources for a single scenario.</span></span> <span data-ttu-id="62c10-125">你将看到，模式匹配  如何通过原始系统中没有的方式高效地使用和处理相应数据。</span><span class="sxs-lookup"><span data-stu-id="62c10-125">You'll see how **pattern matching** provides an efficient way to consume and process that data in ways that weren't part of the original system.</span></span>

<span data-ttu-id="62c10-126">假设某大都市区通过通行费和高峰时段定价来管理交通。</span><span class="sxs-lookup"><span data-stu-id="62c10-126">Consider a major metropolitan area that is using tolls and peak time pricing to manage traffic.</span></span> <span data-ttu-id="62c10-127">你编写的应用程序根据车辆类型来计算车辆通行费。</span><span class="sxs-lookup"><span data-stu-id="62c10-127">You write an application that calculates tolls for a vehicle based on its type.</span></span> <span data-ttu-id="62c10-128">后续增强功能包括，定价因车内乘客数而异。</span><span class="sxs-lookup"><span data-stu-id="62c10-128">Later enhancements incorporate pricing based on the number of occupants in the vehicle.</span></span> <span data-ttu-id="62c10-129">进一步增强功能包括，定价因时间和周几而异。</span><span class="sxs-lookup"><span data-stu-id="62c10-129">Further enhancements add pricing based on the time and the day of the week.</span></span>

<span data-ttu-id="62c10-130">通过上述简要说明，你可能已快速勾勒出用于对此系统进行建模的对象层次结构。</span><span class="sxs-lookup"><span data-stu-id="62c10-130">From that brief description, you may have quickly sketched out an object hierarchy to model this system.</span></span> <span data-ttu-id="62c10-131">不过，数据来自多个源，如其他车辆注册管理系统。</span><span class="sxs-lookup"><span data-stu-id="62c10-131">However, your data is coming from multiple sources like other vehicle registration management systems.</span></span> <span data-ttu-id="62c10-132">这些系统提供不同的类来对相应数据进行建模，而你连可使用的一个对象模型都没有。</span><span class="sxs-lookup"><span data-stu-id="62c10-132">These systems provide different classes to model that data and you don't have a single object model you can use.</span></span> <span data-ttu-id="62c10-133">在本教程中，你将使用这些简化后的类，对这些外部系统中的车辆数据进行建模，如下面的代码所示：</span><span class="sxs-lookup"><span data-stu-id="62c10-133">In this tutorial, you'll use these simplified classes to model for the vehicle data from these external systems, as shown in the following code:</span></span>

[!code-csharp[ExternalSystems](~/samples/csharp/tutorials/patterns/start/toll-calculator/ExternalSystems.cs)]

<span data-ttu-id="62c10-134">若要下载起始代码，可以访问 [dotnet/samples](https://github.com/dotnet/samples/tree/master/csharp/tutorials/patterns/start) GitHub 存储库。</span><span class="sxs-lookup"><span data-stu-id="62c10-134">You can download the starter code from the [dotnet/samples](https://github.com/dotnet/samples/tree/master/csharp/tutorials/patterns/start) GitHub repository.</span></span> <span data-ttu-id="62c10-135">可以看到，车辆类来自不同的系统，且位于不同的命名空间中。</span><span class="sxs-lookup"><span data-stu-id="62c10-135">You can see that the vehicle classes are from different systems, and are in different namespaces.</span></span> <span data-ttu-id="62c10-136">没有常见基类，可利用的 `System.Object` 除外。</span><span class="sxs-lookup"><span data-stu-id="62c10-136">No common base class, other than `System.Object` can be leveraged.</span></span>

## <a name="pattern-matching-designs"></a><span data-ttu-id="62c10-137">模式匹配设计</span><span class="sxs-lookup"><span data-stu-id="62c10-137">Pattern matching designs</span></span>

<span data-ttu-id="62c10-138">本教程中使用的方案重点介绍了非常适合适用模式匹配解决的问题类型：</span><span class="sxs-lookup"><span data-stu-id="62c10-138">The scenario used in this tutorial highlights the kinds of problems that pattern matching is well-suited to solve:</span></span>

- <span data-ttu-id="62c10-139">需要使用的对象不在匹配目标的对象层次结构中。</span><span class="sxs-lookup"><span data-stu-id="62c10-139">The objects you need to work with aren't in an object hierarchy that matches your goals.</span></span> <span data-ttu-id="62c10-140">可能要使用属于不相关系统的类。</span><span class="sxs-lookup"><span data-stu-id="62c10-140">You may be working with classes that are part of unrelated systems.</span></span>
- <span data-ttu-id="62c10-141">要添加的功能不属于这些类的核心抽象。</span><span class="sxs-lookup"><span data-stu-id="62c10-141">The functionality you're adding isn't part of the core abstraction for these classes.</span></span> <span data-ttu-id="62c10-142">车辆通行费因不同车辆类型而异  ，但通行费不是车辆的核心功能。</span><span class="sxs-lookup"><span data-stu-id="62c10-142">The toll paid by a vehicle *changes* for different types of vehicles, but the toll isn't a core function of the vehicle.</span></span>

<span data-ttu-id="62c10-143">如果不一起描述数据形状  和对相应数据执行的操作  ，C# 中的模式匹配功能可以简化这一切。</span><span class="sxs-lookup"><span data-stu-id="62c10-143">When the *shape* of the data and the *operations* on that data are not described together, the pattern matching features in C# make it easier to work with.</span></span>

## <a name="implement-the-basic-toll-calculations"></a><span data-ttu-id="62c10-144">实现基本通行费计算</span><span class="sxs-lookup"><span data-stu-id="62c10-144">Implement the basic toll calculations</span></span>

<span data-ttu-id="62c10-145">最基本的通行费计算仅依赖车辆类型：</span><span class="sxs-lookup"><span data-stu-id="62c10-145">The most basic toll calculation relies only on the vehicle type:</span></span>

- <span data-ttu-id="62c10-146">`Car` 的通行费为 2.00 美元。</span><span class="sxs-lookup"><span data-stu-id="62c10-146">A `Car` is $2.00.</span></span>
- <span data-ttu-id="62c10-147">`Taxi` 的通行费为 3.50 美元。</span><span class="sxs-lookup"><span data-stu-id="62c10-147">A `Taxi` is $3.50.</span></span>
- <span data-ttu-id="62c10-148">`Bus` 的通行费为 5.00 美元。</span><span class="sxs-lookup"><span data-stu-id="62c10-148">A `Bus` is $5.00.</span></span>
- <span data-ttu-id="62c10-149">`DeliveryTruck` 的通行费为 10.00 美元</span><span class="sxs-lookup"><span data-stu-id="62c10-149">A `DeliveryTruck` is $10.00</span></span>

<span data-ttu-id="62c10-150">新建 `TollCalculator` 类，并对车辆类型实现模式匹配，以获取通行费金额。</span><span class="sxs-lookup"><span data-stu-id="62c10-150">Create a new `TollCalculator` class, and implement pattern matching on the vehicle type to get the toll amount.</span></span> <span data-ttu-id="62c10-151">以下代码显示了 `TollCalculator` 的初始实现。</span><span class="sxs-lookup"><span data-stu-id="62c10-151">The following code shows the initial implementation of the `TollCalculator`.</span></span>

```csharp
using System;
using CommercialRegistration;
using ConsumerVehicleRegistration;
using LiveryRegistration;

namespace toll_calculator
{
    public class TollCalculator
    {
        public decimal CalculateToll(object vehicle) =>
            vehicle switch
        {
            Car c           => 2.00m,
            Taxi t          => 3.50m,
            Bus b           => 5.00m,
            DeliveryTruck t => 10.00m,
            { }             => throw new ArgumentException(message: "Not a known vehicle type", paramName: nameof(vehicle)),
            null            => throw new ArgumentNullException(nameof(vehicle))
        };
    }
}
```

<span data-ttu-id="62c10-152">上面的代码使用测试类型模式  的 switch 表达式  （与 [`switch`](../language-reference/keywords/switch.md) 语句不同）。</span><span class="sxs-lookup"><span data-stu-id="62c10-152">The preceding code uses a **switch expression** (not the same as a [`switch`](../language-reference/keywords/switch.md) statement) that tests the **type pattern**.</span></span> <span data-ttu-id="62c10-153">switch 表达式  以变量（上面代码中的 `vehicle`）开头，后跟 `switch` 关键字。</span><span class="sxs-lookup"><span data-stu-id="62c10-153">A **switch expression** begins with the variable, `vehicle` in the preceding code, followed by the `switch` keyword.</span></span> <span data-ttu-id="62c10-154">接下来是大括号内的所有 switch 臂  。</span><span class="sxs-lookup"><span data-stu-id="62c10-154">Next comes all the **switch arms** inside curly braces.</span></span> <span data-ttu-id="62c10-155">`switch` 表达式对 `switch` 语句周围的语法进行了其他优化。</span><span class="sxs-lookup"><span data-stu-id="62c10-155">The `switch` expression makes other refinements to the syntax that surrounds the `switch` statement.</span></span> <span data-ttu-id="62c10-156">不仅省略了 `case` 关键字，还让每个臂的结果成为表达式。</span><span class="sxs-lookup"><span data-stu-id="62c10-156">The `case` keyword is omitted, and the result of each arm is an expression.</span></span> <span data-ttu-id="62c10-157">最后两个臂展示了一种新语言功能。</span><span class="sxs-lookup"><span data-stu-id="62c10-157">The last two arms show a new language feature.</span></span> <span data-ttu-id="62c10-158">`{ }` 子句匹配与之前的臂不匹配的任何非 null 对象。</span><span class="sxs-lookup"><span data-stu-id="62c10-158">The `{ }` case matches any non-null object that didn't match an earlier arm.</span></span> <span data-ttu-id="62c10-159">此臂捕获传递到这个方法的所有不正确类型。</span><span class="sxs-lookup"><span data-stu-id="62c10-159">This arm catches any incorrect types passed to this method.</span></span>  <span data-ttu-id="62c10-160">`{ }` 事例必须遵循每种车辆类型的情况。</span><span class="sxs-lookup"><span data-stu-id="62c10-160">The `{ }` case must follow the cases for each vehicle type.</span></span> <span data-ttu-id="62c10-161">如果订单被撤销，则 `{ }` 事例优先。</span><span class="sxs-lookup"><span data-stu-id="62c10-161">If the order were reversed, the `{ }` case would take precedence.</span></span> <span data-ttu-id="62c10-162">最后，`null` 模式检测何时将 `null` 传递给此方法。</span><span class="sxs-lookup"><span data-stu-id="62c10-162">Finally, the `null` pattern detects when a `null` is passed to this method.</span></span> <span data-ttu-id="62c10-163">`null` 模式可以是最后一个，因为其他类型模式仅匹配正确类型的非 null 对象。</span><span class="sxs-lookup"><span data-stu-id="62c10-163">The `null` pattern can be last because the other type patterns match only a non-null object of the correct type.</span></span>

<span data-ttu-id="62c10-164">可使用 `Program.cs` 中的以下代码来测试上面的代码：</span><span class="sxs-lookup"><span data-stu-id="62c10-164">You can test this code using the following code in `Program.cs`:</span></span>

```csharp
using System;
using CommercialRegistration;
using ConsumerVehicleRegistration;
using LiveryRegistration;

namespace toll_calculator
{
    class Program
    {
        static void Main(string[] args)
        {
            var tollCalc = new TollCalculator();

            var car = new Car();
            var taxi = new Taxi();
            var bus = new Bus();
            var truck = new DeliveryTruck();

            Console.WriteLine($"The toll for a car is {tollCalc.CalculateToll(car)}");
            Console.WriteLine($"The toll for a taxi is {tollCalc.CalculateToll(taxi)}");
            Console.WriteLine($"The toll for a bus is {tollCalc.CalculateToll(bus)}");
            Console.WriteLine($"The toll for a truck is {tollCalc.CalculateToll(truck)}");

            try
            {
                tollCalc.CalculateToll("this will fail");
            }
            catch (ArgumentException e)
            {
                Console.WriteLine("Caught an argument exception when using the wrong type");
            }
            try
            {
                tollCalc.CalculateToll(null);
            }
            catch (ArgumentNullException e)
            {
                Console.WriteLine("Caught an argument exception when using null");
            }
        }
    }
}
```

<span data-ttu-id="62c10-165">此代码虽然包含在初学者项目中，但已被注释掉。删除注释即可测试已编写的代码。</span><span class="sxs-lookup"><span data-stu-id="62c10-165">That code is included in the starter project, but is commented out. Remove the comments, and you can test what you've written.</span></span>

<span data-ttu-id="62c10-166">你正开始了解，模式如何有助于创建将代码和数据分离开来的算法。</span><span class="sxs-lookup"><span data-stu-id="62c10-166">You're starting to see how patterns can help you create algorithms where the code and the data are separate.</span></span> <span data-ttu-id="62c10-167">`switch` 表达式测试类型，并根据结果生成不同的值。</span><span class="sxs-lookup"><span data-stu-id="62c10-167">The `switch` expression tests the type and produces different values based on the results.</span></span> <span data-ttu-id="62c10-168">这仅仅是开始。</span><span class="sxs-lookup"><span data-stu-id="62c10-168">That's only the beginning.</span></span>

## <a name="add-occupancy-pricing"></a><span data-ttu-id="62c10-169">添加因乘客数而异的定价</span><span class="sxs-lookup"><span data-stu-id="62c10-169">Add occupancy pricing</span></span>

<span data-ttu-id="62c10-170">通行费收取机构希望鼓励车辆以最大载客量出行。</span><span class="sxs-lookup"><span data-stu-id="62c10-170">The toll authority wants to encourage vehicles to travel at maximum capacity.</span></span> <span data-ttu-id="62c10-171">他们已决定，对乘客数较少的车辆收取更多费用，并通过更低定价来鼓励车辆乘客满员：</span><span class="sxs-lookup"><span data-stu-id="62c10-171">They've decided to charge more when vehicles have fewer passengers, and encourage full vehicles by offering lower pricing:</span></span>

- <span data-ttu-id="62c10-172">没有乘客的汽车和出租车需额外支付 0.50 美元。</span><span class="sxs-lookup"><span data-stu-id="62c10-172">Cars and taxis with no passengers pay an extra $0.50.</span></span>
- <span data-ttu-id="62c10-173">载有两名乘客的汽车和出租车可享受 0.50 美元折扣。</span><span class="sxs-lookup"><span data-stu-id="62c10-173">Cars and taxis with two passengers get a 0.50 discount.</span></span>
- <span data-ttu-id="62c10-174">载有三名或更多乘客的汽车和出租车可享受 1.00 美元折扣。</span><span class="sxs-lookup"><span data-stu-id="62c10-174">Cars and taxis with three or more passengers get a $1.00 discount.</span></span>
- <span data-ttu-id="62c10-175">乘客数不到满载量 50% 的巴士需额外支付 2.00 美元。</span><span class="sxs-lookup"><span data-stu-id="62c10-175">Buses that are less than 50% full pay an extra $2.00.</span></span>
- <span data-ttu-id="62c10-176">乘客数超过满载量 90% 的巴士可享受 1.00 美元折扣。</span><span class="sxs-lookup"><span data-stu-id="62c10-176">Buses that are more than 90% full get a $1.00 discount.</span></span>

<span data-ttu-id="62c10-177">可使用属性模式  在同一 switch 表达式中实现这些规则。</span><span class="sxs-lookup"><span data-stu-id="62c10-177">These rules can be implemented using the **property pattern** in the same switch expression.</span></span> <span data-ttu-id="62c10-178">属性模式在类型已确定后检查对象的属性。</span><span class="sxs-lookup"><span data-stu-id="62c10-178">The property pattern examines properties of the object once the type has been determined.</span></span> <span data-ttu-id="62c10-179">`Car` 的一个子句扩展为四个不同的子句：</span><span class="sxs-lookup"><span data-stu-id="62c10-179">The single case for a `Car` expands to four different cases:</span></span>

```csharp
vehicle switch
{
    Car { Passengers: 0}        => 2.00m + 0.50m,
    Car { Passengers: 1 }       => 2.0m,
    Car { Passengers: 2}        => 2.0m - 0.50m,
    Car c                       => 2.00m - 1.0m,

    // ...
};
```

<span data-ttu-id="62c10-180">前三个子句测试类型 `Car`，然后检查 `Passengers` 属性的值。</span><span class="sxs-lookup"><span data-stu-id="62c10-180">The first three cases test the type as a `Car`, then check the value of the `Passengers` property.</span></span> <span data-ttu-id="62c10-181">如果两个条件都匹配，系统便会计算并返回相应表达式。</span><span class="sxs-lookup"><span data-stu-id="62c10-181">If both match, that expression is evaluated and returned.</span></span>

<span data-ttu-id="62c10-182">还可以类似方式扩展出租车的子句：</span><span class="sxs-lookup"><span data-stu-id="62c10-182">You would also expand the cases for taxis in a similar manner:</span></span>

```csharp
vehicle switch
{
    // ...

    Taxi { Fares: 0}  => 3.50m + 1.00m,
    Taxi { Fares: 1 } => 3.50m,
    Taxi { Fares: 2}  => 3.50m - 0.50m,
    Taxi t            => 3.50m - 1.00m,

    // ...
};
```

<span data-ttu-id="62c10-183">在上面的示例中，最后一个子句省略了 `when` 子句。</span><span class="sxs-lookup"><span data-stu-id="62c10-183">In the preceding example, the `when` clause was omitted on the final case.</span></span>

<span data-ttu-id="62c10-184">接下来，通过扩展巴士的子句来实现载客量规则，如下面的示例所示：</span><span class="sxs-lookup"><span data-stu-id="62c10-184">Next, implement the occupancy rules by expanding the cases for buses, as shown in the following example:</span></span>

```csharp
vehicle switch
{
    // ...

    Bus b when ((double)b.Riders / (double)b.Capacity) < 0.50 => 5.00m + 2.00m,
    Bus b when ((double)b.Riders / (double)b.Capacity) > 0.90 => 5.00m - 1.00m,
    Bus b => 5.00m,

    // ...
};
```

<span data-ttu-id="62c10-185">通行费收取机构并不关注运货卡车中的乘客数。</span><span class="sxs-lookup"><span data-stu-id="62c10-185">The toll authority isn't concerned with the number of passengers in the delivery trucks.</span></span> <span data-ttu-id="62c10-186">相反，他们根据运货卡车的重量级别收取更多费用。</span><span class="sxs-lookup"><span data-stu-id="62c10-186">Instead, they charge more based on the weight class of the trucks.</span></span> <span data-ttu-id="62c10-187">超过 5000 磅的运货卡车需额外支付 5.00 美元。</span><span class="sxs-lookup"><span data-stu-id="62c10-187">Trucks over 5000 lbs are charged an extra $5.00.</span></span> <span data-ttu-id="62c10-188">3000 磅以下的轻型卡车可享受 2.00 美元折扣。</span><span class="sxs-lookup"><span data-stu-id="62c10-188">Light trucks under 3000 lbs are given a $2.00 discount.</span></span> <span data-ttu-id="62c10-189">此规则通过以下代码实现：</span><span class="sxs-lookup"><span data-stu-id="62c10-189">That rule is implemented with the following code:</span></span>

```csharp
vehicle switch
{
    // ...

    DeliveryTruck t when (t.GrossWeightClass > 5000) => 10.00m + 5.00m,
    DeliveryTruck t when (t.GrossWeightClass < 3000) => 10.00m - 2.00m,
    DeliveryTruck t => 10.00m,
};
```

<span data-ttu-id="62c10-190">以上代码展示了 switch 臂的 `when` 子句。</span><span class="sxs-lookup"><span data-stu-id="62c10-190">The preceding code shows the `when` clause of a switch arm.</span></span> <span data-ttu-id="62c10-191">`when` 子句用于对属性测试条件（相等性除外）。</span><span class="sxs-lookup"><span data-stu-id="62c10-191">You use the `when` clause to test conditions other than equality on a property.</span></span> <span data-ttu-id="62c10-192">完成后的方法如下所示：</span><span class="sxs-lookup"><span data-stu-id="62c10-192">When you've finished, you'll have a method that looks much like the following:</span></span>

```csharp
vehicle switch
{
    Car { Passengers: 0}        => 2.00m + 0.50m,
    Car { Passengers: 1}        => 2.0m,
    Car { Passengers: 2}        => 2.0m - 0.50m,
    Car c                       => 2.00m - 1.0m,

    Taxi { Fares: 0}  => 3.50m + 1.00m,
    Taxi { Fares: 1 } => 3.50m,
    Taxi { Fares: 2}  => 3.50m - 0.50m,
    Taxi t            => 3.50m - 1.00m,

    Bus b when ((double)b.Riders / (double)b.Capacity) < 0.50 => 5.00m + 2.00m,
    Bus b when ((double)b.Riders / (double)b.Capacity) > 0.90 => 5.00m - 1.00m,
    Bus b => 5.00m,

    DeliveryTruck t when (t.GrossWeightClass > 5000) => 10.00m + 5.00m,
    DeliveryTruck t when (t.GrossWeightClass < 3000) => 10.00m - 2.00m,
    DeliveryTruck t => 10.00m,
};
```

<span data-ttu-id="62c10-193">其中许多 switch 臂都是递归模式  示例。</span><span class="sxs-lookup"><span data-stu-id="62c10-193">Many of these switch arms are examples of **recursive patterns**.</span></span> <span data-ttu-id="62c10-194">例如，`Car { Passengers: 1}` 表明属性模式内有常量模式。</span><span class="sxs-lookup"><span data-stu-id="62c10-194">For example, `Car { Passengers: 1}` shows a constant pattern inside a property pattern.</span></span>

<span data-ttu-id="62c10-195">可使用嵌套的 switch 来减少此代码中重复的地方。</span><span class="sxs-lookup"><span data-stu-id="62c10-195">You can make this code less repetitive by using nested switches.</span></span> <span data-ttu-id="62c10-196">在上面的示例中，`Car` 和 `Taxi` 都有四个不同的臂。</span><span class="sxs-lookup"><span data-stu-id="62c10-196">The `Car` and `Taxi` both have four different arms in the preceding examples.</span></span> <span data-ttu-id="62c10-197">在这两种情况下，可以创建向属性模式馈送数据的类型模式。</span><span class="sxs-lookup"><span data-stu-id="62c10-197">In both cases, you can create a type pattern that feeds into a property pattern.</span></span> <span data-ttu-id="62c10-198">下面的代码展示了这项技术：</span><span class="sxs-lookup"><span data-stu-id="62c10-198">This technique is shown in the following code:</span></span>

```csharp
public decimal CalculateToll(object vehicle) =>
    vehicle switch
    {
        Car c => c.Passengers switch
        {
            0 => 2.00m + 0.5m,
            1 => 2.0m,
            2 => 2.0m - 0.5m,
            _ => 2.00m - 1.0m
        },

        Taxi t => t.Fares switch
        {
            0 => 3.50m + 1.00m,
            1 => 3.50m,
            2 => 3.50m - 0.50m,
            _ => 3.50m - 1.00m
        },

        Bus b when ((double)b.Riders / (double)b.Capacity) < 0.50 => 5.00m + 2.00m,
        Bus b when ((double)b.Riders / (double)b.Capacity) > 0.90 => 5.00m - 1.00m,
        Bus b => 5.00m,

        DeliveryTruck t when (t.GrossWeightClass > 5000) => 10.00m + 5.00m,
        DeliveryTruck t when (t.GrossWeightClass < 3000) => 10.00m - 2.00m,
        DeliveryTruck t => 10.00m,

        { }  => throw new ArgumentException(message: "Not a known vehicle type", paramName: nameof(vehicle)),
        null => throw new ArgumentNullException(nameof(vehicle))
    };
```

<span data-ttu-id="62c10-199">在上面的示例中，使用递归表达式意味着不用重复包含测试属性值的子臂的 `Car` 和 `Taxi` 臂。</span><span class="sxs-lookup"><span data-stu-id="62c10-199">In the preceding sample, using a recursive expression means you don't repeat the `Car` and `Taxi` arms containing child arms that test the property value.</span></span> <span data-ttu-id="62c10-200">此技术不适用于 `Bus` 和 `DeliveryTruck` 臂，因为这些臂测试的是属性范围，而不是离散值。</span><span class="sxs-lookup"><span data-stu-id="62c10-200">This technique isn't used for the `Bus` and `DeliveryTruck` arms because those arms are testing ranges for the property, not discrete values.</span></span>

## <a name="add-peak-pricing"></a><span data-ttu-id="62c10-201">添加高峰时段定价</span><span class="sxs-lookup"><span data-stu-id="62c10-201">Add peak pricing</span></span>

<span data-ttu-id="62c10-202">对于最后一个功能，通行费收取机构希望添加有时效性的高峰时段定价。</span><span class="sxs-lookup"><span data-stu-id="62c10-202">For the final feature, the toll authority wants to add time sensitive peak pricing.</span></span> <span data-ttu-id="62c10-203">在早晚高峰时段，通行费翻倍。</span><span class="sxs-lookup"><span data-stu-id="62c10-203">During the morning and evening rush hours, the tolls are doubled.</span></span> <span data-ttu-id="62c10-204">此规则只影响一个方向的交通：早高峰时段入城和晚高峰时段出城。</span><span class="sxs-lookup"><span data-stu-id="62c10-204">That rule only affects traffic in one direction: inbound to the city in the morning, and outbound in the evening rush hour.</span></span> <span data-ttu-id="62c10-205">在工作日的其他时段，通行费增加 50%。</span><span class="sxs-lookup"><span data-stu-id="62c10-205">During other times during the workday, tolls increase by 50%.</span></span> <span data-ttu-id="62c10-206">在深夜和清晨，通行费减少 25%。</span><span class="sxs-lookup"><span data-stu-id="62c10-206">Late night and early morning, tolls are reduced by 25%.</span></span> <span data-ttu-id="62c10-207">在周末，无论什么时间，都按正常费率收费。</span><span class="sxs-lookup"><span data-stu-id="62c10-207">During the weekend, it's the normal rate, regardless of the time.</span></span>

<span data-ttu-id="62c10-208">虽然将对此功能使用模式匹配，但要将它与其他技术集成。</span><span class="sxs-lookup"><span data-stu-id="62c10-208">You'll use pattern matching for this feature, but you'll integrate it with other techniques.</span></span> <span data-ttu-id="62c10-209">可以生成一个模式匹配表达式，将方向、周几和时间所有这一切都考虑在内。</span><span class="sxs-lookup"><span data-stu-id="62c10-209">You could build a single pattern match expression that would account for all the combinations of direction, day of the week, and time.</span></span> <span data-ttu-id="62c10-210">生成的结果是一个复杂的表达式。</span><span class="sxs-lookup"><span data-stu-id="62c10-210">The result would be a complicated expression.</span></span> <span data-ttu-id="62c10-211">它既难读取，也难理解。</span><span class="sxs-lookup"><span data-stu-id="62c10-211">It would be hard to read and difficult to understand.</span></span> <span data-ttu-id="62c10-212">这就加大了确保正确性的难度。</span><span class="sxs-lookup"><span data-stu-id="62c10-212">That makes it hard to ensure correctness.</span></span> <span data-ttu-id="62c10-213">请改为将这些方法合并为生成值元组，用于简要描述所有这些状态。</span><span class="sxs-lookup"><span data-stu-id="62c10-213">Instead, combine those methods to build a tuple of values that concisely describes all those states.</span></span> <span data-ttu-id="62c10-214">然后，使用模式匹配来计算通行费乘数。</span><span class="sxs-lookup"><span data-stu-id="62c10-214">Then use pattern matching to calculate a multiplier for the toll.</span></span> <span data-ttu-id="62c10-215">元组包含以下三个离散条件：</span><span class="sxs-lookup"><span data-stu-id="62c10-215">The tuple contains three discrete conditions:</span></span>

- <span data-ttu-id="62c10-216">是工作日，还是周末。</span><span class="sxs-lookup"><span data-stu-id="62c10-216">The day is either a weekday or a weekend.</span></span>
- <span data-ttu-id="62c10-217">收取通行费时所处的时间带区。</span><span class="sxs-lookup"><span data-stu-id="62c10-217">The band of time when the toll is collected.</span></span>
- <span data-ttu-id="62c10-218">方向是入城，还是出城</span><span class="sxs-lookup"><span data-stu-id="62c10-218">The direction is into the city or out of the city</span></span>

<span data-ttu-id="62c10-219">下表展示了输入值和高峰时段定价乘数的组合：</span><span class="sxs-lookup"><span data-stu-id="62c10-219">The following table shows the combinations of input values and the peak pricing multiplier:</span></span>

| <span data-ttu-id="62c10-220">天</span><span class="sxs-lookup"><span data-stu-id="62c10-220">Day</span></span>        | <span data-ttu-id="62c10-221">时间</span><span class="sxs-lookup"><span data-stu-id="62c10-221">Time</span></span>         | <span data-ttu-id="62c10-222">方向</span><span class="sxs-lookup"><span data-stu-id="62c10-222">Direction</span></span> | <span data-ttu-id="62c10-223">附加费</span><span class="sxs-lookup"><span data-stu-id="62c10-223">Premium</span></span> |
| ---------- | ------------ | --------- |--------:|
| <span data-ttu-id="62c10-224">工作日</span><span class="sxs-lookup"><span data-stu-id="62c10-224">Weekday</span></span>    | <span data-ttu-id="62c10-225">早高峰</span><span class="sxs-lookup"><span data-stu-id="62c10-225">morning rush</span></span> | <span data-ttu-id="62c10-226">入城</span><span class="sxs-lookup"><span data-stu-id="62c10-226">inbound</span></span>   | <span data-ttu-id="62c10-227">x 2.00</span><span class="sxs-lookup"><span data-stu-id="62c10-227">x 2.00</span></span>  |
| <span data-ttu-id="62c10-228">工作日</span><span class="sxs-lookup"><span data-stu-id="62c10-228">Weekday</span></span>    | <span data-ttu-id="62c10-229">早高峰</span><span class="sxs-lookup"><span data-stu-id="62c10-229">morning rush</span></span> | <span data-ttu-id="62c10-230">出城</span><span class="sxs-lookup"><span data-stu-id="62c10-230">outbound</span></span>  | <span data-ttu-id="62c10-231">x 1.00</span><span class="sxs-lookup"><span data-stu-id="62c10-231">x 1.00</span></span>  |
| <span data-ttu-id="62c10-232">工作日</span><span class="sxs-lookup"><span data-stu-id="62c10-232">Weekday</span></span>    | <span data-ttu-id="62c10-233">日间</span><span class="sxs-lookup"><span data-stu-id="62c10-233">daytime</span></span>      | <span data-ttu-id="62c10-234">入城</span><span class="sxs-lookup"><span data-stu-id="62c10-234">inbound</span></span>   | <span data-ttu-id="62c10-235">x 1.50</span><span class="sxs-lookup"><span data-stu-id="62c10-235">x 1.50</span></span>  |
| <span data-ttu-id="62c10-236">工作日</span><span class="sxs-lookup"><span data-stu-id="62c10-236">Weekday</span></span>    | <span data-ttu-id="62c10-237">日间</span><span class="sxs-lookup"><span data-stu-id="62c10-237">daytime</span></span>      | <span data-ttu-id="62c10-238">出城</span><span class="sxs-lookup"><span data-stu-id="62c10-238">outbound</span></span>  | <span data-ttu-id="62c10-239">x 1.50</span><span class="sxs-lookup"><span data-stu-id="62c10-239">x 1.50</span></span>  |
| <span data-ttu-id="62c10-240">工作日</span><span class="sxs-lookup"><span data-stu-id="62c10-240">Weekday</span></span>    | <span data-ttu-id="62c10-241">晚高峰</span><span class="sxs-lookup"><span data-stu-id="62c10-241">evening rush</span></span> | <span data-ttu-id="62c10-242">入城</span><span class="sxs-lookup"><span data-stu-id="62c10-242">inbound</span></span>   | <span data-ttu-id="62c10-243">x 1.00</span><span class="sxs-lookup"><span data-stu-id="62c10-243">x 1.00</span></span>  |
| <span data-ttu-id="62c10-244">工作日</span><span class="sxs-lookup"><span data-stu-id="62c10-244">Weekday</span></span>    | <span data-ttu-id="62c10-245">晚高峰</span><span class="sxs-lookup"><span data-stu-id="62c10-245">evening rush</span></span> | <span data-ttu-id="62c10-246">出城</span><span class="sxs-lookup"><span data-stu-id="62c10-246">outbound</span></span>  | <span data-ttu-id="62c10-247">x 2.00</span><span class="sxs-lookup"><span data-stu-id="62c10-247">x 2.00</span></span>  |
| <span data-ttu-id="62c10-248">工作日</span><span class="sxs-lookup"><span data-stu-id="62c10-248">Weekday</span></span>    | <span data-ttu-id="62c10-249">夜间</span><span class="sxs-lookup"><span data-stu-id="62c10-249">overnight</span></span>    | <span data-ttu-id="62c10-250">入城</span><span class="sxs-lookup"><span data-stu-id="62c10-250">inbound</span></span>   | <span data-ttu-id="62c10-251">x 0.75</span><span class="sxs-lookup"><span data-stu-id="62c10-251">x 0.75</span></span>  |
| <span data-ttu-id="62c10-252">工作日</span><span class="sxs-lookup"><span data-stu-id="62c10-252">Weekday</span></span>    | <span data-ttu-id="62c10-253">夜间</span><span class="sxs-lookup"><span data-stu-id="62c10-253">overnight</span></span>    | <span data-ttu-id="62c10-254">出城</span><span class="sxs-lookup"><span data-stu-id="62c10-254">outbound</span></span>  | <span data-ttu-id="62c10-255">x 0.75</span><span class="sxs-lookup"><span data-stu-id="62c10-255">x 0.75</span></span>  |
| <span data-ttu-id="62c10-256">周末</span><span class="sxs-lookup"><span data-stu-id="62c10-256">Weekend</span></span>    | <span data-ttu-id="62c10-257">早高峰</span><span class="sxs-lookup"><span data-stu-id="62c10-257">morning rush</span></span> | <span data-ttu-id="62c10-258">入城</span><span class="sxs-lookup"><span data-stu-id="62c10-258">inbound</span></span>   | <span data-ttu-id="62c10-259">x 1.00</span><span class="sxs-lookup"><span data-stu-id="62c10-259">x 1.00</span></span>  |
| <span data-ttu-id="62c10-260">周末</span><span class="sxs-lookup"><span data-stu-id="62c10-260">Weekend</span></span>    | <span data-ttu-id="62c10-261">早高峰</span><span class="sxs-lookup"><span data-stu-id="62c10-261">morning rush</span></span> | <span data-ttu-id="62c10-262">出城</span><span class="sxs-lookup"><span data-stu-id="62c10-262">outbound</span></span>  | <span data-ttu-id="62c10-263">x 1.00</span><span class="sxs-lookup"><span data-stu-id="62c10-263">x 1.00</span></span>  |
| <span data-ttu-id="62c10-264">周末</span><span class="sxs-lookup"><span data-stu-id="62c10-264">Weekend</span></span>    | <span data-ttu-id="62c10-265">日间</span><span class="sxs-lookup"><span data-stu-id="62c10-265">daytime</span></span>      | <span data-ttu-id="62c10-266">入城</span><span class="sxs-lookup"><span data-stu-id="62c10-266">inbound</span></span>   | <span data-ttu-id="62c10-267">x 1.00</span><span class="sxs-lookup"><span data-stu-id="62c10-267">x 1.00</span></span>  |
| <span data-ttu-id="62c10-268">周末</span><span class="sxs-lookup"><span data-stu-id="62c10-268">Weekend</span></span>    | <span data-ttu-id="62c10-269">日间</span><span class="sxs-lookup"><span data-stu-id="62c10-269">daytime</span></span>      | <span data-ttu-id="62c10-270">出城</span><span class="sxs-lookup"><span data-stu-id="62c10-270">outbound</span></span>  | <span data-ttu-id="62c10-271">x 1.00</span><span class="sxs-lookup"><span data-stu-id="62c10-271">x 1.00</span></span>  |
| <span data-ttu-id="62c10-272">周末</span><span class="sxs-lookup"><span data-stu-id="62c10-272">Weekend</span></span>    | <span data-ttu-id="62c10-273">晚高峰</span><span class="sxs-lookup"><span data-stu-id="62c10-273">evening rush</span></span> | <span data-ttu-id="62c10-274">入城</span><span class="sxs-lookup"><span data-stu-id="62c10-274">inbound</span></span>   | <span data-ttu-id="62c10-275">x 1.00</span><span class="sxs-lookup"><span data-stu-id="62c10-275">x 1.00</span></span>  |
| <span data-ttu-id="62c10-276">周末</span><span class="sxs-lookup"><span data-stu-id="62c10-276">Weekend</span></span>    | <span data-ttu-id="62c10-277">晚高峰</span><span class="sxs-lookup"><span data-stu-id="62c10-277">evening rush</span></span> | <span data-ttu-id="62c10-278">出城</span><span class="sxs-lookup"><span data-stu-id="62c10-278">outbound</span></span>  | <span data-ttu-id="62c10-279">x 1.00</span><span class="sxs-lookup"><span data-stu-id="62c10-279">x 1.00</span></span>  |
| <span data-ttu-id="62c10-280">周末</span><span class="sxs-lookup"><span data-stu-id="62c10-280">Weekend</span></span>    | <span data-ttu-id="62c10-281">夜间</span><span class="sxs-lookup"><span data-stu-id="62c10-281">overnight</span></span>    | <span data-ttu-id="62c10-282">入城</span><span class="sxs-lookup"><span data-stu-id="62c10-282">inbound</span></span>   | <span data-ttu-id="62c10-283">x 1.00</span><span class="sxs-lookup"><span data-stu-id="62c10-283">x 1.00</span></span>  |
| <span data-ttu-id="62c10-284">周末</span><span class="sxs-lookup"><span data-stu-id="62c10-284">Weekend</span></span>    | <span data-ttu-id="62c10-285">夜间</span><span class="sxs-lookup"><span data-stu-id="62c10-285">overnight</span></span>    | <span data-ttu-id="62c10-286">出城</span><span class="sxs-lookup"><span data-stu-id="62c10-286">outbound</span></span>  | <span data-ttu-id="62c10-287">x 1.00</span><span class="sxs-lookup"><span data-stu-id="62c10-287">x 1.00</span></span>  |

<span data-ttu-id="62c10-288">三个变量有 16 种不同的组合。</span><span class="sxs-lookup"><span data-stu-id="62c10-288">There are 16 different combinations of the three variables.</span></span> <span data-ttu-id="62c10-289">通过结合某些条件，将能简化最终的 switch 表达式。</span><span class="sxs-lookup"><span data-stu-id="62c10-289">By combining some of the conditions, you'll simplify the final switch expression.</span></span>

<span data-ttu-id="62c10-290">通行费收取系统在收取通行费时对时间使用 <xref:System.DateTime> 结构。</span><span class="sxs-lookup"><span data-stu-id="62c10-290">The system that collects the tolls uses a <xref:System.DateTime> structure for the time when the toll was collected.</span></span> <span data-ttu-id="62c10-291">生成根据上表创建变量的成员方法。</span><span class="sxs-lookup"><span data-stu-id="62c10-291">Build member methods that create the variables from the preceding table.</span></span> <span data-ttu-id="62c10-292">以下函数用作模式匹配 switch 表达式，以表示 <xref:System.DateTime> 是表示周末，还是表示工作日：</span><span class="sxs-lookup"><span data-stu-id="62c10-292">The following function uses a pattern matching switch expression to express whether a <xref:System.DateTime> represents a weekend or a weekday:</span></span>

```csharp
private static bool IsWeekDay(DateTime timeOfToll) =>
    timeOfToll.DayOfWeek switch
    {
        DayOfWeek.Monday    => true,
        DayOfWeek.Tuesday   => true,
        DayOfWeek.Wednesday => true,
        DayOfWeek.Thursday  => true,
        DayOfWeek.Friday    => true,
        DayOfWeek.Saturday  => false,
        DayOfWeek.Sunday    => false
    };
```

<span data-ttu-id="62c10-293">此方法虽起作用，但是重复的。</span><span class="sxs-lookup"><span data-stu-id="62c10-293">That method works, but it's repetitious.</span></span> <span data-ttu-id="62c10-294">可以简化它，如下面的代码所示：</span><span class="sxs-lookup"><span data-stu-id="62c10-294">You can simplify it, as shown in the following code:</span></span>

[!code-csharp[IsWeekDay](~/samples/csharp/tutorials/patterns/finished/toll-calculator/TollCalculator.cs#IsWeekDay)]

<span data-ttu-id="62c10-295">接下来，添加将时间分类为块的类似函数：</span><span class="sxs-lookup"><span data-stu-id="62c10-295">Next, add a similar function to categorize the time into the blocks:</span></span>

[!code-csharp[GetTimeBand](~/samples/csharp/tutorials/patterns/finished/toll-calculator/TollCalculator.cs#GetTimeBand)]

<span data-ttu-id="62c10-296">上面的方法不使用模式匹配。</span><span class="sxs-lookup"><span data-stu-id="62c10-296">The previous method doesn't use pattern matching.</span></span> <span data-ttu-id="62c10-297">使用熟悉的 `if` 语句级联将更为清楚。</span><span class="sxs-lookup"><span data-stu-id="62c10-297">It's clearer using a familiar cascade of `if` statements.</span></span> <span data-ttu-id="62c10-298">你确实添加将每个时间范围转换为离散值的专用 `enum`。</span><span class="sxs-lookup"><span data-stu-id="62c10-298">You do add a private `enum` to convert each range of time to a discrete value.</span></span>

<span data-ttu-id="62c10-299">创建这些方法后，可以结合使用另一个 `switch` 表达式和元组模式  ，以计算定价附加费。</span><span class="sxs-lookup"><span data-stu-id="62c10-299">After you create those methods, you can use another `switch` expression with the **tuple pattern** to calculate the pricing premium.</span></span> <span data-ttu-id="62c10-300">可以生成包含所有 16 个臂的 `switch` 表达式：</span><span class="sxs-lookup"><span data-stu-id="62c10-300">You could build a `switch` expression with all 16 arms:</span></span>

[!code-csharp[FullTuplePattern](~/samples/csharp/tutorials/patterns/finished/toll-calculator/TollCalculator.cs#TuplePatternOne)]

<span data-ttu-id="62c10-301">上面的代码虽起作用，但可以进行简化。</span><span class="sxs-lookup"><span data-stu-id="62c10-301">The above code works, but it can be simplified.</span></span> <span data-ttu-id="62c10-302">周末对应的所有八个组合的通行费都相同。</span><span class="sxs-lookup"><span data-stu-id="62c10-302">All eight combinations for the weekend have the same toll.</span></span> <span data-ttu-id="62c10-303">可以将所有八个组合都替换为下面的代码：</span><span class="sxs-lookup"><span data-stu-id="62c10-303">You can replace all eight with the following line:</span></span>

```csharp
(false, _, _) => 1.0m,
```

<span data-ttu-id="62c10-304">入城和出城交通乘数在工作日日间和夜间时段都相同。</span><span class="sxs-lookup"><span data-stu-id="62c10-304">Both inbound and outbound traffic have the same multiplier during the weekday daytime and overnight hours.</span></span> <span data-ttu-id="62c10-305">可以将四个 switch 臂替换为以下两行代码：</span><span class="sxs-lookup"><span data-stu-id="62c10-305">Those four switch arms can be replaced with the following two lines:</span></span>

```csharp
(true, TimeBand.Overnight, _) => 0.75m,
(true, TimeBand.Daytime, _)   => 1.5m,
```

<span data-ttu-id="62c10-306">执行这两项更改后，代码应如下所示：</span><span class="sxs-lookup"><span data-stu-id="62c10-306">The code should look like the following code after those two changes:</span></span>

```csharp
public decimal PeakTimePremium(DateTime timeOfToll, bool inbound) =>
    (IsWeekDay(timeOfToll), GetTimeBand(timeOfToll), inbound) switch
    {
        (true, TimeBand.MorningRush, true)  => 2.00m,
        (true, TimeBand.MorningRush, false) => 1.00m,
        (true, TimeBand.Daytime,     _)     => 1.50m,
        (true, TimeBand.EveningRush, true)  => 1.00m,
        (true, TimeBand.EveningRush, false) => 2.00m,
        (true, TimeBand.Overnight,   _)     => 0.75m,
        (false, _,                   _)     => 1.00m,
    };
```

<span data-ttu-id="62c10-307">最后，可以删除通行费正常的两个高峰时段。</span><span class="sxs-lookup"><span data-stu-id="62c10-307">Finally, you can remove the two rush hour times that pay the regular price.</span></span> <span data-ttu-id="62c10-308">删除这些臂后，可以在最后的 switch 臂中将 `false` 替换为弃元 (`_`)。</span><span class="sxs-lookup"><span data-stu-id="62c10-308">Once you remove those arms, you can replace the `false` with a discard (`_`) in the final switch arm.</span></span> <span data-ttu-id="62c10-309">完成的方法如下所示：</span><span class="sxs-lookup"><span data-stu-id="62c10-309">You'll have the following finished method:</span></span>

[!code-csharp[SimplifiedTuplePattern](../../../samples/csharp/tutorials/patterns/finished/toll-calculator/TollCalculator.cs#FinalTuplePattern)]

<span data-ttu-id="62c10-310">此示例突出了模式匹配的一个优点：模式分支是依序计算的。</span><span class="sxs-lookup"><span data-stu-id="62c10-310">This example highlights one of the advantages of pattern matching: the pattern branches are evaluated in order.</span></span> <span data-ttu-id="62c10-311">如果将它们重排为更早的分支处理后续事例之一，编译器便会提示你无法访问的代码。</span><span class="sxs-lookup"><span data-stu-id="62c10-311">If you rearrange them so that an earlier branch handles one of your later cases, the compiler warns you about the unreachable code.</span></span> <span data-ttu-id="62c10-312">借助这些语言规则，可以更轻松地执行前面的简化，同时确信代码未更改。</span><span class="sxs-lookup"><span data-stu-id="62c10-312">Those language rules made it easier to do the preceding simplifications with confidence that the code didn't change.</span></span>

<span data-ttu-id="62c10-313">模式匹配使某些类型的代码更具可读性，并且当你无法向类添加代码时，它会提供面向对象技术的替代方法。</span><span class="sxs-lookup"><span data-stu-id="62c10-313">Pattern matching makes some types of code more readable and offers an alternative to object-oriented techniques when you can't add code to your classes.</span></span> <span data-ttu-id="62c10-314">云会导致数据和功能分离。</span><span class="sxs-lookup"><span data-stu-id="62c10-314">The cloud is causing data and functionality to live apart.</span></span> <span data-ttu-id="62c10-315">数据形状  和对相应数据执行的操作  不一定在一起进行描述。</span><span class="sxs-lookup"><span data-stu-id="62c10-315">The *shape* of the data and the *operations* on it aren't necessarily described together.</span></span> <span data-ttu-id="62c10-316">在本教程中，你通过与原始功能完全不同的方法使用了现有数据。</span><span class="sxs-lookup"><span data-stu-id="62c10-316">In this tutorial, you consumed existing data in entirely different ways from its original function.</span></span> <span data-ttu-id="62c10-317">使用模式匹配，可以覆盖这些类型编写功能，即使无法扩展类型，也不例外。</span><span class="sxs-lookup"><span data-stu-id="62c10-317">Pattern matching gave you the ability to write functionality that overrode those types, even though you couldn't extend them.</span></span>

## <a name="next-steps"></a><span data-ttu-id="62c10-318">后续步骤</span><span class="sxs-lookup"><span data-stu-id="62c10-318">Next steps</span></span>

<span data-ttu-id="62c10-319">若要下载完成后的代码，可以访问 [dotnet/samples](https://github.com/dotnet/samples/tree/master/csharp/tutorials/patterns/finished) GitHub 存储库。</span><span class="sxs-lookup"><span data-stu-id="62c10-319">You can download the finished code from the [dotnet/samples](https://github.com/dotnet/samples/tree/master/csharp/tutorials/patterns/finished) GitHub repository.</span></span> <span data-ttu-id="62c10-320">请自行探索模式，并将此技术纳入你的常规编码活动。</span><span class="sxs-lookup"><span data-stu-id="62c10-320">Explore patterns on your own and add this technique into your regular coding activities.</span></span> <span data-ttu-id="62c10-321">学些这些技术，你可以通过其他方式来处理问题和新建功能。</span><span class="sxs-lookup"><span data-stu-id="62c10-321">Learning these techniques gives you another way to approach problems and create new functionality.</span></span>
