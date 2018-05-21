---
title: 异常的最佳做法
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- exceptions, best practices
ms.assetid: f06da765-235b-427a-bfb6-47cd219af539
author: mairaw
ms.author: mairaw
ms.openlocfilehash: dd38b59e39f938d6347457100243f09935444d88
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="best-practices-for-exceptions"></a><span data-ttu-id="3c925-102">异常的最佳做法</span><span class="sxs-lookup"><span data-stu-id="3c925-102">Best practices for exceptions</span></span>

<span data-ttu-id="3c925-103">设计良好的应用处理异常和错误以防止应用崩溃。</span><span class="sxs-lookup"><span data-stu-id="3c925-103">A well-designed app handles exceptions and errors to prevent app crashes.</span></span> <span data-ttu-id="3c925-104">本部分介绍了处理和创建异常的最佳做法。</span><span class="sxs-lookup"><span data-stu-id="3c925-104">This section describes best practices for handling and creating exceptions.</span></span>

## <a name="use-trycatchfinally-blocks"></a><span data-ttu-id="3c925-105">使用 try/catch/finally 块</span><span class="sxs-lookup"><span data-stu-id="3c925-105">Use try/catch/finally blocks</span></span>

<span data-ttu-id="3c925-106">在可能产生异常的代码周围使用 `try`/`catch`/`finally` 块。</span><span class="sxs-lookup"><span data-stu-id="3c925-106">Use `try`/`catch`/`finally` blocks around code that can potentially generate an exception.</span></span> 

<span data-ttu-id="3c925-107">在 `catch` 块中，始终按从最特定到最不特定的顺序对异常排序。</span><span class="sxs-lookup"><span data-stu-id="3c925-107">In `catch` blocks, always order exceptions from the most specific to the least specific.</span></span>

<span data-ttu-id="3c925-108">无论是否可进行恢复，使用 `finally` 块清理资源。</span><span class="sxs-lookup"><span data-stu-id="3c925-108">Use a `finally` block to clean up resources, whether you can recover or not.</span></span>

## <a name="handle-common-conditions-without-throwing-exceptions"></a><span data-ttu-id="3c925-109">在不引发异常的前提下，处理常见情况</span><span class="sxs-lookup"><span data-stu-id="3c925-109">Handle common conditions without throwing exceptions</span></span>

<span data-ttu-id="3c925-110">对于易于发生但可能会触发异常的情况，请考虑使用能避免引发异常的方法进行处理。</span><span class="sxs-lookup"><span data-stu-id="3c925-110">For conditions that are likely to occur but might trigger an exception, consider handling them in a way that will avoid the exception.</span></span> <span data-ttu-id="3c925-111">例如，如果尝试关闭已关闭的连接，则会获得 `InvalidOperationException`。</span><span class="sxs-lookup"><span data-stu-id="3c925-111">For example, if you try to close a connection that is already closed, you'll get an `InvalidOperationException`.</span></span> <span data-ttu-id="3c925-112">尝试关闭前，可通过使用 `if` 语句检查连接状态，避免该情况。</span><span class="sxs-lookup"><span data-stu-id="3c925-112">You can avoid that by using an `if` statement to check the connection state before trying to close it.</span></span>

[!code-cpp[Conceptual.Exception.Handling#2](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.exception.handling/cpp/source.cpp#2)]
[!code-csharp[Conceptual.Exception.Handling#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.exception.handling/cs/source.cs#2)]
[!code-vb[Conceptual.Exception.Handling#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.exception.handling/vb/source.vb#2)]  

<span data-ttu-id="3c925-113">如果关闭前未检查连接状态，则可能捕获 `InvalidOperationException` 异常。</span><span class="sxs-lookup"><span data-stu-id="3c925-113">If you don't check connection state before closing, you can catch the `InvalidOperationException` exception.</span></span>

[!code-cpp[Conceptual.Exception.Handling#3](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.exception.handling/cpp/source.cpp#3)]
[!code-csharp[Conceptual.Exception.Handling#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.exception.handling/cs/source.cs#3)]
[!code-vb[Conceptual.Exception.Handling#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.exception.handling/vb/source.vb#3)]  

<span data-ttu-id="3c925-114">选择的方法取决于希望时间发生的频率。</span><span class="sxs-lookup"><span data-stu-id="3c925-114">The method to choose depends on how often you expect the event to occur.</span></span>

- <span data-ttu-id="3c925-115">如果此事件未经常发生（也就是说，如果此事件确实为异常并指示错误（如意外的文件尾）），则使用异常处理。</span><span class="sxs-lookup"><span data-stu-id="3c925-115">Use exception handling if the event doesn't occur very often, that is, if the event is truly exceptional and indicates an error (such as an unexpected end-of-file).</span></span> <span data-ttu-id="3c925-116">如果使用异常处理，将在正常条件下执行较少代码。</span><span class="sxs-lookup"><span data-stu-id="3c925-116">When you use exception handling, less code is executed in normal conditions.</span></span>

- <span data-ttu-id="3c925-117">如果事件例行发生，且被视为正常性执行的一部分，请检查代码中是否存在错误情况。</span><span class="sxs-lookup"><span data-stu-id="3c925-117">Check for error conditions in code if the event happens routinely and could be considered part of normal execution.</span></span> <span data-ttu-id="3c925-118">检查常见错误情况时，为了避免异常，执行较少的代码。</span><span class="sxs-lookup"><span data-stu-id="3c925-118">When you check for common error conditions, less code is executed because you avoid exceptions.</span></span>

## <a name="design-classes-so-that-exceptions-can-be-avoided"></a><span data-ttu-id="3c925-119">设计类，以避免异常</span><span class="sxs-lookup"><span data-stu-id="3c925-119">Design classes so that exceptions can be avoided</span></span>

<span data-ttu-id="3c925-120">类可提供一些方法或属性来确保避免生成会引发异常的调用。</span><span class="sxs-lookup"><span data-stu-id="3c925-120">A class can provide methods or properties that enable you to avoid making a call that would trigger an exception.</span></span> <span data-ttu-id="3c925-121">例如，<xref:System.IO.FileStream> 类提供可帮助确实是否已到达文件末尾的方法。</span><span class="sxs-lookup"><span data-stu-id="3c925-121">For example, a <xref:System.IO.FileStream> class provides methods that help determine whether the end of the file has been reached.</span></span> <span data-ttu-id="3c925-122">它可用于避免在读取超过文件末尾时引发的异常。</span><span class="sxs-lookup"><span data-stu-id="3c925-122">These can be used to avoid the exception that is thrown if you read past the end of the file.</span></span> <span data-ttu-id="3c925-123">下方示例显示如何读取文件末尾而不会引发异常。</span><span class="sxs-lookup"><span data-stu-id="3c925-123">The following example shows how to read to the end of a file without triggering an exception.</span></span>

[!code-cpp[Conceptual.Exception.Handling#5](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.exception.handling/cpp/source.cpp#5)]
[!code-csharp[Conceptual.Exception.Handling#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.exception.handling/cs/source.cs#5)]
[!code-vb[Conceptual.Exception.Handling#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.exception.handling/vb/source.vb#5)]  

<span data-ttu-id="3c925-124">避免异常的另一方法是，对极为常见的错误案例返回 NULL，而不是引发异常。</span><span class="sxs-lookup"><span data-stu-id="3c925-124">Another way to avoid exceptions is to return null for extremely common error cases instead of throwing an exception.</span></span> <span data-ttu-id="3c925-125">极其常见的错误案例可被视为常规控制流。</span><span class="sxs-lookup"><span data-stu-id="3c925-125">An extremely common error case can be considered normal flow of control.</span></span> <span data-ttu-id="3c925-126">通过在这些情况下返回 null，可最大程度地减小对应用的性能产生的影响。</span><span class="sxs-lookup"><span data-stu-id="3c925-126">By returning null in these cases, you minimize the performance impact to an app.</span></span>

## <a name="throw-exceptions-instead-of-returning-an-error-code"></a><span data-ttu-id="3c925-127">引发异常而不是返回错误代码</span><span class="sxs-lookup"><span data-stu-id="3c925-127">Throw exceptions instead of returning an error code</span></span>

<span data-ttu-id="3c925-128">异常可确保故障不被忽略，因为调用代码不会检查返回代码。</span><span class="sxs-lookup"><span data-stu-id="3c925-128">Exceptions ensure that failures do not go unnoticed because calling code didn't check a return code.</span></span> 

## <a name="use-the-predefined-net-exception-types"></a><span data-ttu-id="3c925-129">使用预定义的 .NET 异常类型</span><span class="sxs-lookup"><span data-stu-id="3c925-129">Use the predefined .NET exception types</span></span>

<span data-ttu-id="3c925-130">仅当预定义的异常类不适用时，引入新异常类。</span><span class="sxs-lookup"><span data-stu-id="3c925-130">Introduce a new exception class only when a predefined one doesn't apply.</span></span> <span data-ttu-id="3c925-131">例如:</span><span class="sxs-lookup"><span data-stu-id="3c925-131">For example:</span></span>

- <span data-ttu-id="3c925-132">如果根据对象的当前状态，属性集或方法调用不适当，则会引发 <xref:System.InvalidOperationException> 异常。</span><span class="sxs-lookup"><span data-stu-id="3c925-132">Throw an <xref:System.InvalidOperationException> exception if a property set or method call is not appropriate given the object's current state.</span></span>

- <span data-ttu-id="3c925-133">如果传送了无效的参数，则引发 <xref:System.ArgumentException> 异常或从 <xref:System.ArgumentException> 派生的一个预定义类。</span><span class="sxs-lookup"><span data-stu-id="3c925-133">Throw an <xref:System.ArgumentException> exception or one of the predefined classes that derive from <xref:System.ArgumentException> if invalid parameters are passed.</span></span>

## <a name="end-exception-class-names-with-the-word-exception"></a><span data-ttu-id="3c925-134">异常类名称的结尾为 `Exception`</span><span class="sxs-lookup"><span data-stu-id="3c925-134">End exception class names with the word `Exception`</span></span>

<span data-ttu-id="3c925-135">需要自定义异常时，对其正确命名并从 <xref:System.Exception> 类进行派生。</span><span class="sxs-lookup"><span data-stu-id="3c925-135">When a custom exception is necessary, name it appropriately and derive it from the <xref:System.Exception> class.</span></span> <span data-ttu-id="3c925-136">例如:</span><span class="sxs-lookup"><span data-stu-id="3c925-136">For example:</span></span>

[!code-cpp[Conceptual.Exception.Handling#4](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.exception.handling/cpp/source.cpp#4)]
[!code-csharp[Conceptual.Exception.Handling#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.exception.handling/cs/source.cs#4)]
[!code-vb[Conceptual.Exception.Handling#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.exception.handling/vb/source.vb#4)]  

## <a name="include-three-constructors-in-custom-exception-classes"></a><span data-ttu-id="3c925-137">在自定义异常类中包括三种构造函数</span><span class="sxs-lookup"><span data-stu-id="3c925-137">Include three constructors in custom exception classes</span></span>

<span data-ttu-id="3c925-138">创建自己的异常类别时至少使用三种公共构造函数：默认构造函数、采用字符串消息的构造函数和采用字符串消息和内部异常的构造函数。</span><span class="sxs-lookup"><span data-stu-id="3c925-138">Use at least the three common constructors when creating your own exception classes: the default constructor, a constructor that takes a string message, and a constructor that takes a string message and an inner exception.</span></span>

* <span data-ttu-id="3c925-139"><xref:System.Exception.%23ctor>（使用默认值）。</span><span class="sxs-lookup"><span data-stu-id="3c925-139"><xref:System.Exception.%23ctor>, which uses default values.</span></span>
  
* <span data-ttu-id="3c925-140"><xref:System.Exception.%23ctor%28System.String%29>，它接受字符串消息。</span><span class="sxs-lookup"><span data-stu-id="3c925-140"><xref:System.Exception.%23ctor%28System.String%29>, which accepts a string message.</span></span>  
  
* <span data-ttu-id="3c925-141"><xref:System.Exception.%23ctor%28System.String%2CSystem.Exception%29>，它接受字符串消息和内部异常。</span><span class="sxs-lookup"><span data-stu-id="3c925-141"><xref:System.Exception.%23ctor%28System.String%2CSystem.Exception%29>, which accepts a string message and an inner exception.</span></span>  
  
<span data-ttu-id="3c925-142">有关示例，请参阅[如何：创建用户定义的异常](how-to-create-user-defined-exceptions.md)。</span><span class="sxs-lookup"><span data-stu-id="3c925-142">For an example, see [How to: Create User-Defined Exceptions](how-to-create-user-defined-exceptions.md).</span></span>

## <a name="ensure-that-exception-data-is-available-when-code-executes-remotely"></a><span data-ttu-id="3c925-143">确保代码远程执行时异常数据可用</span><span class="sxs-lookup"><span data-stu-id="3c925-143">Ensure that exception data is available when code executes remotely</span></span>

<span data-ttu-id="3c925-144">创建用户定义的异常时，请确保异常的元数据对远程执行的代码可用。</span><span class="sxs-lookup"><span data-stu-id="3c925-144">When you create user-defined exceptions, ensure that the metadata for the exceptions is available to code that is executing remotely.</span></span> 

<span data-ttu-id="3c925-145">例如，在支持应用域的 .NET 实现中，异常可能会跨应用域抛出。</span><span class="sxs-lookup"><span data-stu-id="3c925-145">For example, on .NET implementations that support App Domains, exceptions may occur across App domains.</span></span> <span data-ttu-id="3c925-146">假设应用域 A 创建应用域 B，后者执行引发异常的代码。</span><span class="sxs-lookup"><span data-stu-id="3c925-146">Suppose App Domain A creates App Domain B, which executes code that throws an exception.</span></span> <span data-ttu-id="3c925-147">应用域 A 若想正确捕获和处理异常，它必须能够找到包含应用域 B 所引发的异常的程序集。如果应用域 B 在其应用程序基下（但未在应用域 A 的应用程序基下）引发了一个包含在程序集内的异常，那么应用域 A 将无法找到异常，且公共语言运行时将引发 <xref:System.IO.FileNotFoundException> 异常。</span><span class="sxs-lookup"><span data-stu-id="3c925-147">For App Domain A to properly catch and handle the exception, it must be able to find the assembly that contains the exception thrown by App Domain B. If App Domain B throws an exception that is contained in an assembly under its application base, but not under App Domain A's application base, App Domain A will not be able to find the exception, and the common language runtime will throw a <xref:System.IO.FileNotFoundException> exception.</span></span> <span data-ttu-id="3c925-148">为避免此情况，可以两种方式部署包含异常信息的程序集：</span><span class="sxs-lookup"><span data-stu-id="3c925-148">To avoid this situation, you can deploy the assembly that contains the exception information in two ways:</span></span>

- <span data-ttu-id="3c925-149">将程序集放在两个应用域共享的公共应用程序基中。</span><span class="sxs-lookup"><span data-stu-id="3c925-149">Put the assembly into a common application base shared by both app domains.</span></span>

    <span data-ttu-id="3c925-150">\- 或 -</span><span class="sxs-lookup"><span data-stu-id="3c925-150">\- or -</span></span>

- <span data-ttu-id="3c925-151">如果两个应用域不共享一个公共应用程序基，则用强名称为包含异常信息的程序集签名并将其部署到全局程序集缓存中。</span><span class="sxs-lookup"><span data-stu-id="3c925-151">If the domains do not share a common application base, sign the assembly that contains the exception information with a strong name and deploy the assembly into the global assembly cache.</span></span>

## <a name="include-a-localized-description-string-in-every-exception"></a><span data-ttu-id="3c925-152">在每个异常中都包含一个本地化描述字符串</span><span class="sxs-lookup"><span data-stu-id="3c925-152">Include a localized description string in every exception</span></span>

<span data-ttu-id="3c925-153">用户看到的错误消息派生自引发的异常的描述字符串，而不是派生自异常类的名称。</span><span class="sxs-lookup"><span data-stu-id="3c925-153">The error message that the user sees is derived from the description string of the exception that was thrown, and not from the name of the exception class.</span></span>

## <a name="use-grammatically-correct-error-messages"></a><span data-ttu-id="3c925-154">使用语法正确的错误消息</span><span class="sxs-lookup"><span data-stu-id="3c925-154">Use grammatically correct error messages</span></span>

<span data-ttu-id="3c925-155">编写清晰的句子，包括结束标点。</span><span class="sxs-lookup"><span data-stu-id="3c925-155">Write clear sentences and include ending punctuation.</span></span> <span data-ttu-id="3c925-156">在异常的描述字符串中，每个句子都应以句号结尾。</span><span class="sxs-lookup"><span data-stu-id="3c925-156">Each sentence in a description string of an exception should end in a period.</span></span> <span data-ttu-id="3c925-157">例如，“日志表已溢出”。</span><span class="sxs-lookup"><span data-stu-id="3c925-157">For example, "The log table has overflowed."</span></span> <span data-ttu-id="3c925-158">就是一个正确的描述字符串。</span><span class="sxs-lookup"><span data-stu-id="3c925-158">would be an appropriate description string.</span></span>

## <a name="in-custom-exceptions-provide-additional-properties-as-needed"></a><span data-ttu-id="3c925-159">在自定义异常中，按需提供其他属性</span><span class="sxs-lookup"><span data-stu-id="3c925-159">In custom exceptions, provide additional properties as needed</span></span>

<span data-ttu-id="3c925-160">仅当存在附加信息有用的编程方案时，才在异常中提供附加属性（不包括描述字符串）。</span><span class="sxs-lookup"><span data-stu-id="3c925-160">Provide additional properties for an exception (in addition to the description string) only when there's a programmatic scenario where the additional information is useful.</span></span> <span data-ttu-id="3c925-161">例如，<xref:System.IO.FileNotFoundException> 提供 <xref:System.IO.FileNotFoundException.FileName> 属性。</span><span class="sxs-lookup"><span data-stu-id="3c925-161">For example, the <xref:System.IO.FileNotFoundException> provides the <xref:System.IO.FileNotFoundException.FileName> property.</span></span>

## <a name="place-throw-statements-so-that-the-stack-trace-will-be-helpful"></a><span data-ttu-id="3c925-162">放置引发语句，使得堆栈跟踪有所帮助</span><span class="sxs-lookup"><span data-stu-id="3c925-162">Place throw statements so that the stack trace will be helpful</span></span>

<span data-ttu-id="3c925-163">堆栈跟踪从引发异常的语句开始，到捕获异常的 `catch` 语句结束。</span><span class="sxs-lookup"><span data-stu-id="3c925-163">The stack trace begins at the statement where the exception is thrown and ends at the `catch` statement that catches the exception.</span></span>

## <a name="use-exception-builder-methods"></a><span data-ttu-id="3c925-164">使用异常生成器方法</span><span class="sxs-lookup"><span data-stu-id="3c925-164">Use exception builder methods</span></span>

<span data-ttu-id="3c925-165">类从其实现中的不同位置引发同一异常是常见的情况。</span><span class="sxs-lookup"><span data-stu-id="3c925-165">It is common for a class to throw the same exception from different places in its implementation.</span></span> <span data-ttu-id="3c925-166">为避免过多的代码，应使用帮助器方法创建异常并将其返回。</span><span class="sxs-lookup"><span data-stu-id="3c925-166">To avoid excessive code, use helper methods that create the exception and return it.</span></span> <span data-ttu-id="3c925-167">例如:</span><span class="sxs-lookup"><span data-stu-id="3c925-167">For example:</span></span>

[!code-cpp[Conceptual.Exception.Handling#6](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.exception.handling/cpp/source.cpp#6)]
[!code-csharp[Conceptual.Exception.Handling#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.exception.handling/cs/source.cs#6)]
[!code-vb[Conceptual.Exception.Handling#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.exception.handling/vb/source.vb#6)]  
  
<span data-ttu-id="3c925-168">在某些情况下，更适合使用异常的构造函数生成异常。</span><span class="sxs-lookup"><span data-stu-id="3c925-168">In some cases, it's more appropriate to use the exception's constructor to build the exception.</span></span> <span data-ttu-id="3c925-169">例如，<xref:System.ArgumentException> 等全局异常类。</span><span class="sxs-lookup"><span data-stu-id="3c925-169">An example is a global exception class such as <xref:System.ArgumentException>.</span></span>

## <a name="clean-up-intermediate-results-when-throwing-an-exception"></a><span data-ttu-id="3c925-170">引发异常时清理中间结果</span><span class="sxs-lookup"><span data-stu-id="3c925-170">Clean up intermediate results when throwing an exception</span></span>

<span data-ttu-id="3c925-171">当异常从方法引发时，调用方应能够假定没有副作用。</span><span class="sxs-lookup"><span data-stu-id="3c925-171">Callers should be able to assume that there are no side effects when an exception is thrown from a method.</span></span> <span data-ttu-id="3c925-172">例如，如果你的代码可以通过从一个帐户取钱并存入另一个帐户来转移资金，而在存款时引发了异常，你不希望取款仍然有效。</span><span class="sxs-lookup"><span data-stu-id="3c925-172">For example, if you have code that transfers money by withdrawing from one account and depositing in another account, and an exception is thrown while executing the deposit, you don't want the withdrawal to remain in effect.</span></span>

```csharp
public void TransferFunds(Account from, Account to, decimal amount)
{
    from.Withdrawal(amount);
    // If the deposit fails, the withdrawal shouldn't remain in effect. 
    to.Deposit(amount);
}
```

<span data-ttu-id="3c925-173">解决这一情况的一种方法是，捕获由存款交易引发的异常，然后回滚取款。</span><span class="sxs-lookup"><span data-stu-id="3c925-173">One way to handle this situation is to catch any exceptions thrown by the deposit transaction and roll back the withdrawal.</span></span>

```csharp
private static void TransferFunds(Account from, Account to, decimal amount)
{
    string withdrawalTrxID = from.Withdrawal(amount);
    try
    {
        to.Deposit(amount);
    }
    catch
    {
        from.RollbackTransaction(withdrawalTrxID);
        throw;
    }
}
```

<span data-ttu-id="3c925-174">此示例介绍如何使用 `throw` 重新引发原始异常，让调用方更轻松地发现问题的真正原因，而无需检查 <xref:System.Exception.InnerException> 属性。</span><span class="sxs-lookup"><span data-stu-id="3c925-174">This example illustrates the use of `throw` to re-throw the original exception, which can make it easier for callers to see the real cause of the problem without having to examine the <xref:System.Exception.InnerException> property.</span></span> <span data-ttu-id="3c925-175">另一种方法是，引发一个新的异常并将原始异常包括在其中作为内部异常：</span><span class="sxs-lookup"><span data-stu-id="3c925-175">An alternative is to throw a new exception and include the original exception as the inner exception:</span></span>

```csharp
catch (Exception ex)
{
    from.RollbackTransaction(withdrawalTrxID);
    throw new Exception("Withdrawal failed", ex);
}
```

## <a name="see-also"></a><span data-ttu-id="3c925-176">请参阅</span><span class="sxs-lookup"><span data-stu-id="3c925-176">See Also</span></span>  
[<span data-ttu-id="3c925-177">异常</span><span class="sxs-lookup"><span data-stu-id="3c925-177">Exceptions</span></span>](index.md)
