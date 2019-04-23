---
title: 委托的常见模式
description: 了解在代码中使用委托避免组件间强耦合的常见模式。
ms.date: 06/20/2016
ms.assetid: 0ff8fdfd-6a11-4327-b061-0f2526f35b43
ms.openlocfilehash: ea0e0b7af361b76c4b46b0a180e07b44c1fa07e1
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59095693"
---
# <a name="common-patterns-for-delegates"></a><span data-ttu-id="186b5-103">委托的常见模式</span><span class="sxs-lookup"><span data-stu-id="186b5-103">Common Patterns for Delegates</span></span>

[<span data-ttu-id="186b5-104">上一部分</span><span class="sxs-lookup"><span data-stu-id="186b5-104">Previous</span></span>](delegates-strongly-typed.md)

<span data-ttu-id="186b5-105">委托提供了一种机制，可实现涉及组件间最小耦合度的软件设计。</span><span class="sxs-lookup"><span data-stu-id="186b5-105">Delegates provide a mechanism that enables software designs involving minimal coupling between components.</span></span>

<span data-ttu-id="186b5-106">此类设计的出色示例为 LINQ。</span><span class="sxs-lookup"><span data-stu-id="186b5-106">One excellent example for this kind of design is LINQ.</span></span> <span data-ttu-id="186b5-107">LINQ 查询表达式模式依赖于其所有功能的委托。</span><span class="sxs-lookup"><span data-stu-id="186b5-107">The LINQ Query Expression Pattern relies on delegates for all of its features.</span></span> <span data-ttu-id="186b5-108">请考虑此简单示例：</span><span class="sxs-lookup"><span data-stu-id="186b5-108">Consider this simple example:</span></span>

```csharp
var smallNumbers = numbers.Where(n => n < 10);
```

<span data-ttu-id="186b5-109">这会将数字序列筛选为仅小于值 10 的数字序列。</span><span class="sxs-lookup"><span data-stu-id="186b5-109">This filters the sequence of numbers to only those less than the value 10.</span></span>
<span data-ttu-id="186b5-110">`Where` 方法使用委托来确定序列的哪些元素可通过筛选器。</span><span class="sxs-lookup"><span data-stu-id="186b5-110">The `Where` method uses a delegate that determines which elements of a sequence pass the filter.</span></span> <span data-ttu-id="186b5-111">创建 LINQ 查询时，为此特定目的提供委托的实现。</span><span class="sxs-lookup"><span data-stu-id="186b5-111">When you create a LINQ query, you supply the implementation of the delegate for this specific purpose.</span></span>

<span data-ttu-id="186b5-112">Where 方法的原型是：</span><span class="sxs-lookup"><span data-stu-id="186b5-112">The prototype for the Where method is:</span></span>

```csharp
public static IEnumerable<TSource> Where<TSource> (this IEnumerable<TSource> source, Func<TSource, bool> predicate);
```

<span data-ttu-id="186b5-113">此示例重复使用所有方法，这些方法都为 LINQ 的一部分。</span><span class="sxs-lookup"><span data-stu-id="186b5-113">This example is repeated with all the methods that are part of LINQ.</span></span> <span data-ttu-id="186b5-114">它们都依赖于管理特定查询的代码委托。</span><span class="sxs-lookup"><span data-stu-id="186b5-114">They all rely on delegates for the code that manages the specific query.</span></span> <span data-ttu-id="186b5-115">此 API 设计模式功能强大，需要学习和理解。</span><span class="sxs-lookup"><span data-stu-id="186b5-115">This API design pattern is a very powerful one to learn and understand.</span></span>

<span data-ttu-id="186b5-116">此简单示例说明了委托在组件之间仅需要极少耦合度的原因。</span><span class="sxs-lookup"><span data-stu-id="186b5-116">This simple example illustrates how delegates require very little coupling between components.</span></span> <span data-ttu-id="186b5-117">不需要创建从特定基类派生的类。</span><span class="sxs-lookup"><span data-stu-id="186b5-117">You don't need to create a class that derives from a particular base class.</span></span> <span data-ttu-id="186b5-118">不需要实现特定接口。</span><span class="sxs-lookup"><span data-stu-id="186b5-118">You don't need to implement a specific interface.</span></span>
<span data-ttu-id="186b5-119">唯一的要求是提供对当前任务至关重要的方法实现。</span><span class="sxs-lookup"><span data-stu-id="186b5-119">The only requirement is to provide the implementation of one method that is fundamental to the task at hand.</span></span>

## <a name="building-your-own-components-with-delegates"></a><span data-ttu-id="186b5-120">通过委托生成自己的组件</span><span class="sxs-lookup"><span data-stu-id="186b5-120">Building Your Own Components with Delegates</span></span>

<span data-ttu-id="186b5-121">基于此示例，通过使用依赖于委托的设计来创建组件，从而进行生成。</span><span class="sxs-lookup"><span data-stu-id="186b5-121">Let's build on that example by creating a component using a design that relies on delegates.</span></span>

<span data-ttu-id="186b5-122">定义一个可用于大型系统中日志消息的组件。</span><span class="sxs-lookup"><span data-stu-id="186b5-122">Let's define a component that could be used for log messages in a large system.</span></span> <span data-ttu-id="186b5-123">库组件可以在多种不同的环境中和多个不同的平台上使用。</span><span class="sxs-lookup"><span data-stu-id="186b5-123">The library components could be used in many different environments, on multiple different platforms.</span></span> <span data-ttu-id="186b5-124">管理日志的组件中有很多常用功能。</span><span class="sxs-lookup"><span data-stu-id="186b5-124">There are a lot of common features in the component that manages the logs.</span></span> <span data-ttu-id="186b5-125">它需要接受来自系统中任何组件的消息。</span><span class="sxs-lookup"><span data-stu-id="186b5-125">It will need to accept messages from any component in the system.</span></span> <span data-ttu-id="186b5-126">这些消息将具有不同的优先级（核心组件可进行管理）。</span><span class="sxs-lookup"><span data-stu-id="186b5-126">Those messages will have different priorities, which the core component can manage.</span></span> <span data-ttu-id="186b5-127">消息应当具有其最终存档形式的时间戳。</span><span class="sxs-lookup"><span data-stu-id="186b5-127">The messages should have timestamps in their final archived form.</span></span> <span data-ttu-id="186b5-128">对于更高级的方案，你可以按源组件筛选消息。</span><span class="sxs-lookup"><span data-stu-id="186b5-128">For more advanced scenarios, you could filter messages by the source component.</span></span>

<span data-ttu-id="186b5-129">此功能有一个方面会经常发生变化：写入消息的位置。</span><span class="sxs-lookup"><span data-stu-id="186b5-129">There is one aspect of the feature that will change often: where messages are written.</span></span> <span data-ttu-id="186b5-130">在某些环境中，它们可能会写入到错误控制台。</span><span class="sxs-lookup"><span data-stu-id="186b5-130">In some environments, they may be written to the error console.</span></span> <span data-ttu-id="186b5-131">在其他环境中，可能会写入一个文件。</span><span class="sxs-lookup"><span data-stu-id="186b5-131">In others, a file.</span></span> <span data-ttu-id="186b5-132">其他可能性包括数据库存储、操作系统事件日志或其他文档存储。</span><span class="sxs-lookup"><span data-stu-id="186b5-132">Other possibilities include database storage, OS event logs, or other document storage.</span></span>

<span data-ttu-id="186b5-133">还有可能用于不同方案的输出组合。</span><span class="sxs-lookup"><span data-stu-id="186b5-133">There are also combinations of output that might be used in different scenarios.</span></span> <span data-ttu-id="186b5-134">建议你将消息写入控制台和文件。</span><span class="sxs-lookup"><span data-stu-id="186b5-134">You may want to write messages to the console and to a file.</span></span>

<span data-ttu-id="186b5-135">基于委托的设计将提供极大的灵活性，从而轻松支持可能在以后添加的存储机制。</span><span class="sxs-lookup"><span data-stu-id="186b5-135">A design based on delegates will provide a great deal of flexibility, and make it easy to support storage mechanisms that may be added in the future.</span></span>

<span data-ttu-id="186b5-136">基于此设计，主日志组件可以是非虚拟，甚至是密封的类。</span><span class="sxs-lookup"><span data-stu-id="186b5-136">Under this design, the primary log component can be a non-virtual, even sealed class.</span></span> <span data-ttu-id="186b5-137">你可以插入任何委托集，将消息写入不同的存储介质。</span><span class="sxs-lookup"><span data-stu-id="186b5-137">You can plug in any set of delegates to write the messages to different storage media.</span></span> <span data-ttu-id="186b5-138">对多播委托的内置支持有助于支持必须将消息写入多个位置（文件和控制台）的情况。</span><span class="sxs-lookup"><span data-stu-id="186b5-138">The built in support for multicast delegates makes it easy to support scenarios where messages must be written to multiple locations (a file, and a console).</span></span>

## <a name="a-first-implementation"></a><span data-ttu-id="186b5-139">首次实现</span><span class="sxs-lookup"><span data-stu-id="186b5-139">A First Implementation</span></span>

<span data-ttu-id="186b5-140">我们从小处着手：初始实现会接受新消息并使用任意附加委托编写它们。</span><span class="sxs-lookup"><span data-stu-id="186b5-140">Let's start small: the initial implementation will accept new messages, and write them using any attached delegate.</span></span> <span data-ttu-id="186b5-141">你可以从一个将消息写入控制台的委托开始。</span><span class="sxs-lookup"><span data-stu-id="186b5-141">You can start with one delegate that writes messages to the console.</span></span>

[!code-csharp[LoggerImplementation](../../samples/csharp/delegates-and-events/Logger.cs#FirstImplementation "A first Logger implementation.")]

<span data-ttu-id="186b5-142">上面的静态类是可以发挥作用的最简单的类。</span><span class="sxs-lookup"><span data-stu-id="186b5-142">The static class above is the simplest thing that can work.</span></span> <span data-ttu-id="186b5-143">我们需要编写将消息写入控制台的方法的单个实现：</span><span class="sxs-lookup"><span data-stu-id="186b5-143">We need to write the single implementation for the method that writes messages to the console:</span></span> 

[!code-csharp[LogToConsole](../../samples/csharp/delegates-and-events/Program.cs#LogToConsole "A Console logger.")]

<span data-ttu-id="186b5-144">最后，你需要通过将委托附加到记录器中声明的 WriteMessage 委托来进行挂钩：</span><span class="sxs-lookup"><span data-stu-id="186b5-144">Finally, you need to hook up the delegate by attaching it to the WriteMessage delegate declared in the logger:</span></span>

[!code-csharp[ConnectDelegate](../../samples/csharp/delegates-and-events/Program.cs#ConnectDelegate "Connect to the delegate")]

## <a name="practices"></a><span data-ttu-id="186b5-145">实践</span><span class="sxs-lookup"><span data-stu-id="186b5-145">Practices</span></span>

<span data-ttu-id="186b5-146">到目前为止，我们的示例都相当简单，但仍演示了一些关于委托设计的重要指南。</span><span class="sxs-lookup"><span data-stu-id="186b5-146">Our sample so far is fairly simple, but it still demonstrates some of the important guidelines for designs involving delegates.</span></span>

<span data-ttu-id="186b5-147">使用在核心框架中定义的委托类型，用户可更轻松地使用委托。</span><span class="sxs-lookup"><span data-stu-id="186b5-147">Using the delegate types defined in the Core Framework makes it easier for users to work with the delegates.</span></span> <span data-ttu-id="186b5-148">无需定义新类型，而且使用你库的开发者不需要学习新的专用委托类型。</span><span class="sxs-lookup"><span data-stu-id="186b5-148">You don't need to define new types, and developers using your library do not need to learn new, specialized delegate types.</span></span>

<span data-ttu-id="186b5-149">使用尽可能少的灵活接口：若要新建输出记录器，必须创建一种方法。</span><span class="sxs-lookup"><span data-stu-id="186b5-149">The interfaces used are as minimal and as flexible as possible: To create a new output logger, you must create one method.</span></span> <span data-ttu-id="186b5-150">该方法可以是静态方法或实例方法。</span><span class="sxs-lookup"><span data-stu-id="186b5-150">That method may be a static method, or an instance method.</span></span> <span data-ttu-id="186b5-151">它可能具有任何访问权限。</span><span class="sxs-lookup"><span data-stu-id="186b5-151">It may have any access.</span></span>

## <a name="formatting-output"></a><span data-ttu-id="186b5-152">设置输出格式</span><span class="sxs-lookup"><span data-stu-id="186b5-152">Formatting Output</span></span>

<span data-ttu-id="186b5-153">让第一个版本更加可靠，然后开始创建其他日志记录机制。</span><span class="sxs-lookup"><span data-stu-id="186b5-153">Let's make this first version a bit more robust, and then start creating other logging mechanisms.</span></span>

<span data-ttu-id="186b5-154">然后，向 `LogMessage()` 方法添加一些参数，以便日志类创建更多结构化消息：</span><span class="sxs-lookup"><span data-stu-id="186b5-154">Next, let's add a few arguments to the `LogMessage()` method so that your log class creates more structured messages:</span></span>

[!code-csharp[Severity](../../samples/csharp/delegates-and-events/Logger.cs#Severity "Define severities")]
[!code-csharp[NextLogger](../../samples/csharp/delegates-and-events/Logger.cs#LoggerTwo "Refine the Logger")]

<span data-ttu-id="186b5-155">接下来，使用 `Severity` 参数来筛选发送到日志输出的消息。</span><span class="sxs-lookup"><span data-stu-id="186b5-155">Next, let's make use of that `Severity` argument to filter the messages that are sent to the log's output.</span></span> 

[!code-csharp[FinalLogger](../../samples/csharp/delegates-and-events/Logger.cs#LoggerFinal "Finish the Logger")]

## <a name="practices"></a><span data-ttu-id="186b5-156">实践</span><span class="sxs-lookup"><span data-stu-id="186b5-156">Practices</span></span>

<span data-ttu-id="186b5-157">已向日志记录基础结构添加了新功能。</span><span class="sxs-lookup"><span data-stu-id="186b5-157">You've added new features to the logging infrastructure.</span></span> <span data-ttu-id="186b5-158">由于记录器组件极其松散地耦合到输出机制，因此可在不影响代码实现记录器托管的情况下添加新功能。</span><span class="sxs-lookup"><span data-stu-id="186b5-158">Because the logger component is very loosely coupled to any output mechanism, these new features can be added with no impact on any of the code implementing the logger delegate.</span></span>

<span data-ttu-id="186b5-159">继续构建，你会看到更多的示例，其中显示这种松散的耦合度在更新站点部件方面实现了很高的灵活性，而不会对其他位置做出更改。</span><span class="sxs-lookup"><span data-stu-id="186b5-159">As you keep building this, you'll see more examples of how this loose coupling enables greater flexibility in updating parts of the site without any changes to other locations.</span></span> <span data-ttu-id="186b5-160">实际上，在更大的应用程序中，记录器输出类可能位于不同的程序集中，甚至不需要重新生成。</span><span class="sxs-lookup"><span data-stu-id="186b5-160">In fact, in a larger application, the logger output classes might be in a different assembly, and not even need to be rebuilt.</span></span>

## <a name="building-a-second-output-engine"></a><span data-ttu-id="186b5-161">生成第二个输出引擎</span><span class="sxs-lookup"><span data-stu-id="186b5-161">Building a Second Output Engine</span></span>

<span data-ttu-id="186b5-162">还将附带日志组件。</span><span class="sxs-lookup"><span data-stu-id="186b5-162">The Log component is coming along well.</span></span> <span data-ttu-id="186b5-163">我们再添加一个将消息记录到文件的输出引擎。</span><span class="sxs-lookup"><span data-stu-id="186b5-163">Let's add one more output engine that logs messages to a file.</span></span> <span data-ttu-id="186b5-164">这将是一个更为普及的输出引擎。</span><span class="sxs-lookup"><span data-stu-id="186b5-164">This will be a slightly more involved output engine.</span></span> <span data-ttu-id="186b5-165">它将是一个封装文件操作的类，并确保文件在每次写入后始终处于关闭状态。</span><span class="sxs-lookup"><span data-stu-id="186b5-165">It will be a class that encapsulates the file operations, and ensures that the file is always closed after each write.</span></span> <span data-ttu-id="186b5-166">这可以确保生成每条消息后将所有数据刷新到磁盘。</span><span class="sxs-lookup"><span data-stu-id="186b5-166">That ensures that all the data is flushed to disk after each message is generated.</span></span>

<span data-ttu-id="186b5-167">下面是基于文件的记录器：</span><span class="sxs-lookup"><span data-stu-id="186b5-167">Here is that file based logger:</span></span>

[!code-csharp[FileLogger](../../samples/csharp/delegates-and-events/FileLogger.cs#FileLogger "Log to files")]

<span data-ttu-id="186b5-168">创建此类后，可将它进行实例化，然后它会将 LogMessage 方法附加到记录器组件中：</span><span class="sxs-lookup"><span data-stu-id="186b5-168">Once you've created this class, you can instantiate it and it attaches its LogMessage method to the Logger component:</span></span>

[!code-csharp[FileLogger](../../samples/csharp/delegates-and-events/Program.cs#FileLogger "Log to files")]

<span data-ttu-id="186b5-169">这两项并不互相排斥。</span><span class="sxs-lookup"><span data-stu-id="186b5-169">These two are not mutually exclusive.</span></span> <span data-ttu-id="186b5-170">你可以附加这两种日志方法并生成要发送到控制台和文件的消息：</span><span class="sxs-lookup"><span data-stu-id="186b5-170">You could attach both log methods and generate messages to the console and a file:</span></span>

```csharp
var fileOutput = new FileLogger("log.txt");
Logger.WriteMessage += LogToConsole;
```

<span data-ttu-id="186b5-171">以后，即使在同一个应用程序中，也可在不对系统产生任何其他问题的情况下删除其中一个委托：</span><span class="sxs-lookup"><span data-stu-id="186b5-171">Later, even in the same application, you can remove one of the delegates without any other issues to the system:</span></span>

```csharp
Logger.WriteMessage -= LogToConsole;
```

## <a name="practices"></a><span data-ttu-id="186b5-172">实践</span><span class="sxs-lookup"><span data-stu-id="186b5-172">Practices</span></span>

<span data-ttu-id="186b5-173">现在，你已添加日志记录子系统的第二个输出处理程序。</span><span class="sxs-lookup"><span data-stu-id="186b5-173">Now, you've added a second output handler for the logging sub-system.</span></span>
<span data-ttu-id="186b5-174">这需要更多的基础结构来正确支持文件系统。</span><span class="sxs-lookup"><span data-stu-id="186b5-174">This one needs a bit more infrastructure to correctly support the file system.</span></span> <span data-ttu-id="186b5-175">此委托为实例方法。</span><span class="sxs-lookup"><span data-stu-id="186b5-175">The delegate is an instance method.</span></span> <span data-ttu-id="186b5-176">其为私有方法。</span><span class="sxs-lookup"><span data-stu-id="186b5-176">It's also a private method.</span></span>
<span data-ttu-id="186b5-177">由于委托基础结构可以连接委托，因此不需要太高的可访问性。</span><span class="sxs-lookup"><span data-stu-id="186b5-177">There's no need for greater accessibility because the delegate infrastructure can connect the delegates.</span></span>

<span data-ttu-id="186b5-178">其次，基于委托的设计可实现多种输出方法，且无需额外的代码。</span><span class="sxs-lookup"><span data-stu-id="186b5-178">Second, the delegate-based design enables multiple output methods without any extra code.</span></span> <span data-ttu-id="186b5-179">无需生成任何其他基础结构来支持多种输出方法。</span><span class="sxs-lookup"><span data-stu-id="186b5-179">You don't need to build any additional infrastructure to support multiple output methods.</span></span> <span data-ttu-id="186b5-180">它们将变为调用列表上的另一种方法。</span><span class="sxs-lookup"><span data-stu-id="186b5-180">They simply become another method on the invocation list.</span></span>

<span data-ttu-id="186b5-181">需要特别注意文件日志记录输出方法中的代码。</span><span class="sxs-lookup"><span data-stu-id="186b5-181">Pay special attention to the code in the file logging output method.</span></span> <span data-ttu-id="186b5-182">对其进行编码以确保不引发任何异常。</span><span class="sxs-lookup"><span data-stu-id="186b5-182">It is coded to ensure that it does not throw any exceptions.</span></span> <span data-ttu-id="186b5-183">虽然不是绝对必要，但这通常是很好的做法。</span><span class="sxs-lookup"><span data-stu-id="186b5-183">While this isn't always strictly necessary, it's often a good practice.</span></span> <span data-ttu-id="186b5-184">如果任意一种委托方法引发异常，将不会调用该调用中剩余的其他委托。</span><span class="sxs-lookup"><span data-stu-id="186b5-184">If either of the delegate methods throws an exception, the remaining delegates that are on the invocation won't be invoked.</span></span>

<span data-ttu-id="186b5-185">最后请注意，文件记录器必须通过打开和关闭每条日志消息上的文件来管理其资源。</span><span class="sxs-lookup"><span data-stu-id="186b5-185">As a last note, the file logger must manage its resources by opening and closing the file on each log message.</span></span> <span data-ttu-id="186b5-186">可以选择让文件保持打开状态，并在完成后执行 IDisposable 以关闭文件。</span><span class="sxs-lookup"><span data-stu-id="186b5-186">You could choose to keep the file open and implement IDisposable to close the file when you are completed.</span></span>
<span data-ttu-id="186b5-187">这两种方法各有利弊。</span><span class="sxs-lookup"><span data-stu-id="186b5-187">Either method has its advantages and disadvantages.</span></span> <span data-ttu-id="186b5-188">两者都在类之间创建了更高的耦合度。</span><span class="sxs-lookup"><span data-stu-id="186b5-188">Both do create a bit more coupling between the classes.</span></span>

<span data-ttu-id="186b5-189">为了支持这两种方案，记录器类中的代码都不需要更新。</span><span class="sxs-lookup"><span data-stu-id="186b5-189">None of the code in the Logger class would need to be updated in order to support either scenario.</span></span>

## <a name="handling-null-delegates"></a><span data-ttu-id="186b5-190">处理 Null 委托</span><span class="sxs-lookup"><span data-stu-id="186b5-190">Handling Null Delegates</span></span>

<span data-ttu-id="186b5-191">最后，更新 LogMessage 方法，从而在没有选择输出机制的情况下更加可靠。</span><span class="sxs-lookup"><span data-stu-id="186b5-191">Finally, let's update the LogMessage method so that it is robust for those cases when no output mechanism is selected.</span></span> <span data-ttu-id="186b5-192">`WriteMessage` 委托没有附加调用列表时，当前实现将引发 `NullReferenceException`。</span><span class="sxs-lookup"><span data-stu-id="186b5-192">The current implementation will throw a `NullReferenceException` when the `WriteMessage` delegate does not have an invocation list attached.</span></span>
<span data-ttu-id="186b5-193">你可能更需要在没有附加方法时自行继续的设计。</span><span class="sxs-lookup"><span data-stu-id="186b5-193">You may prefer a design that silently continues when no methods have been attached.</span></span> <span data-ttu-id="186b5-194">将 null 条件运算符与 `Delegate.Invoke()` 方法结合使用时，很容易实现该目标：</span><span class="sxs-lookup"><span data-stu-id="186b5-194">This is easy using the null conditional operator, combined with the `Delegate.Invoke()` method:</span></span>

```csharp
public static void LogMessage(string msg)
{
    WriteMessage?.Invoke(msg);
}
```

<span data-ttu-id="186b5-195">当左操作数（本例中为 `WriteMessage`）为 null 时，null 条件运算符（`?.`）会短路，这意味着不会尝试记录消息。</span><span class="sxs-lookup"><span data-stu-id="186b5-195">The null conditional operator (`?.`) short-circuits when the left operand (`WriteMessage` in this case) is null, which means no attempt is made to log a message.</span></span>

<span data-ttu-id="186b5-196">不会在 `System.Delegate` 或 `System.MulticastDelegate` 的文档中列出 `Invoke()` 方法。</span><span class="sxs-lookup"><span data-stu-id="186b5-196">You won't find the `Invoke()` method listed in the documentation for `System.Delegate` or `System.MulticastDelegate`.</span></span> <span data-ttu-id="186b5-197">编译器将为声明的所有委托类型生成类型安全的 `Invoke` 方法。</span><span class="sxs-lookup"><span data-stu-id="186b5-197">The compiler generates a type safe `Invoke` method for any delegate type declared.</span></span> <span data-ttu-id="186b5-198">在此示例中，这意味着 `Invoke` 只需要一个 `string` 参数，并且有一个无效返回类型。</span><span class="sxs-lookup"><span data-stu-id="186b5-198">In this example, that means `Invoke` takes a single `string` argument, and has a void return type.</span></span>

## <a name="summary-of-practices"></a><span data-ttu-id="186b5-199">实践摘要</span><span class="sxs-lookup"><span data-stu-id="186b5-199">Summary of Practices</span></span>

<span data-ttu-id="186b5-200">你已了解日志组件的起始部分，可以使用其他编写器和其他功能进行扩展。</span><span class="sxs-lookup"><span data-stu-id="186b5-200">You've seen the beginnings of a log component that could be expanded with other writers, and other features.</span></span> <span data-ttu-id="186b5-201">通过在设计中使用委托，这些不同的组件非常松散地耦合在一起。</span><span class="sxs-lookup"><span data-stu-id="186b5-201">By using delegates in the design these different components are very loosely coupled.</span></span> <span data-ttu-id="186b5-202">这样可提供多种优势。</span><span class="sxs-lookup"><span data-stu-id="186b5-202">This provides several advantages.</span></span> <span data-ttu-id="186b5-203">可轻松创建新的输出机制并将它们附加到系统中。</span><span class="sxs-lookup"><span data-stu-id="186b5-203">It's very easy to create new output mechanisms and attach them to the system.</span></span> <span data-ttu-id="186b5-204">这些机制只需要一种方法：编写日志消息的方法。</span><span class="sxs-lookup"><span data-stu-id="186b5-204">These other mechanisms only need one method: the method that writes the log message.</span></span> <span data-ttu-id="186b5-205">这种设计在添加新功能时有非常强的复原能力。</span><span class="sxs-lookup"><span data-stu-id="186b5-205">It's a design that is very resilient when new features are added.</span></span> <span data-ttu-id="186b5-206">所有编写器所需的协定都是为了实现一种方法。</span><span class="sxs-lookup"><span data-stu-id="186b5-206">The contract required for any writer is to implement one method.</span></span> <span data-ttu-id="186b5-207">该方法可以是静态方法或实例方法。</span><span class="sxs-lookup"><span data-stu-id="186b5-207">That method could be a static or instance method.</span></span> <span data-ttu-id="186b5-208">它可以是公用、专用或任何其他合法访问。</span><span class="sxs-lookup"><span data-stu-id="186b5-208">It could be public, private, or any other legal access.</span></span>

<span data-ttu-id="186b5-209">记录器类可在不引入重大更改的情况下进行任何数量的增强或更改。</span><span class="sxs-lookup"><span data-stu-id="186b5-209">The Logger class can make any number of enhancements or changes without introducing breaking changes.</span></span> <span data-ttu-id="186b5-210">与类相似，无法在没有重大更改的风险下修改公共 API。</span><span class="sxs-lookup"><span data-stu-id="186b5-210">Like any class, you cannot modify the public API without the risk of breaking changes.</span></span> <span data-ttu-id="186b5-211">但是，因为仅通过委托进行记录器和输出引擎之间的耦合，因此不涉及其他类型（如接口或基类）。</span><span class="sxs-lookup"><span data-stu-id="186b5-211">But, because the coupling between the logger and any output engines is only through the delegate, no other types (like interfaces or base classes) are involved.</span></span> <span data-ttu-id="186b5-212">耦合度越小越好。</span><span class="sxs-lookup"><span data-stu-id="186b5-212">The coupling is as small as possible.</span></span>

[<span data-ttu-id="186b5-213">下一页</span><span class="sxs-lookup"><span data-stu-id="186b5-213">Next</span></span>](events-overview.md)
