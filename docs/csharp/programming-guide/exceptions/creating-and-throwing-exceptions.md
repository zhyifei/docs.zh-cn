---
title: 创建和抛出异常 - C# 编程指南
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- catching exceptions [C#]
- throwing exceptions [C#]
- exceptions [C#], creating
- exceptions [C#], throwing
ms.assetid: 6bbba495-a115-4c6d-90cc-1f4d7b5f39e2
ms.openlocfilehash: c7775de75ddbf274f3a1555c9f0daaf63bbee713
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2018
ms.locfileid: "53235340"
---
# <a name="creating-and-throwing-exceptions-c-programming-guide"></a><span data-ttu-id="0561c-102">创建和引发异常（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="0561c-102">Creating and Throwing Exceptions (C# Programming Guide)</span></span>
<span data-ttu-id="0561c-103">异常用于指示在运行程序时发生了错误。</span><span class="sxs-lookup"><span data-stu-id="0561c-103">Exceptions are used to indicate that an error has occurred while running the program.</span></span> <span data-ttu-id="0561c-104">此时将创建一个描述错误的异常对象，然后使用 [throw](../../../csharp/language-reference/keywords/throw.md) 关键字引发。</span><span class="sxs-lookup"><span data-stu-id="0561c-104">Exception objects that describe an error are created and then *thrown* with the [throw](../../../csharp/language-reference/keywords/throw.md) keyword.</span></span> <span data-ttu-id="0561c-105">然后，运行时搜索最兼容的异常处理程序。</span><span class="sxs-lookup"><span data-stu-id="0561c-105">The runtime then searches for the most compatible exception handler.</span></span>  
  
 <span data-ttu-id="0561c-106">当存在下列一种或多种情况时，程序员应引发异常：</span><span class="sxs-lookup"><span data-stu-id="0561c-106">Programmers should throw exceptions when one or more of the following conditions are true:</span></span>  
  
-   <span data-ttu-id="0561c-107">方法无法完成其定义的功能。</span><span class="sxs-lookup"><span data-stu-id="0561c-107">The method cannot complete its defined functionality.</span></span>  
  
     <span data-ttu-id="0561c-108">例如，如果一种方法的参数具有无效的值：</span><span class="sxs-lookup"><span data-stu-id="0561c-108">For example, if a parameter to a method has an invalid value:</span></span>  
  
     [!code-csharp[csProgGuideExceptions#12](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/creating-and-throwing-exceptions_1.cs)]  
  
-   <span data-ttu-id="0561c-109">根据对象的状态，对某个对象进行不适当的调用。</span><span class="sxs-lookup"><span data-stu-id="0561c-109">An inappropriate call to an object is made, based on the object state.</span></span>  
  
     <span data-ttu-id="0561c-110">一个示例可能是尝试写入只读文件。</span><span class="sxs-lookup"><span data-stu-id="0561c-110">One example might be trying to write to a read-only file.</span></span> <span data-ttu-id="0561c-111">在对象状态不允许操作的情况下，引发 <xref:System.InvalidOperationException> 的实例或基于此类的派生的对象。</span><span class="sxs-lookup"><span data-stu-id="0561c-111">In cases where an object state does not allow an operation, throw an instance of <xref:System.InvalidOperationException> or an object based on a derivation of this class.</span></span> <span data-ttu-id="0561c-112">这是引发 <xref:System.InvalidOperationException> 对象的方法示例：</span><span class="sxs-lookup"><span data-stu-id="0561c-112">This is an example of a method that throws an <xref:System.InvalidOperationException> object:</span></span>  
  
     [!code-csharp[csProgGuideExceptions#13](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/creating-and-throwing-exceptions_2.cs)]  
  
-   <span data-ttu-id="0561c-113">方法的参数引发了异常。</span><span class="sxs-lookup"><span data-stu-id="0561c-113">When an argument to a method causes an exception.</span></span>  
  
     <span data-ttu-id="0561c-114">在这种情况下，应捕获原始异常，并创建 <xref:System.ArgumentException> 实例。</span><span class="sxs-lookup"><span data-stu-id="0561c-114">In this case, the original exception should be caught and an <xref:System.ArgumentException> instance should be created.</span></span> <span data-ttu-id="0561c-115">应将原始异常作为 <xref:System.Exception.InnerException%2A> 参数传递给 <xref:System.ArgumentException> 的构造函数：</span><span class="sxs-lookup"><span data-stu-id="0561c-115">The original exception should be passed to the constructor of the <xref:System.ArgumentException> as the <xref:System.Exception.InnerException%2A> parameter:</span></span>  
  
     [!code-csharp[csProgGuideExceptions#14](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/creating-and-throwing-exceptions_3.cs)]  
  
 <span data-ttu-id="0561c-116">异常包含一个名为 <xref:System.Exception.StackTrace%2A> 的属性。</span><span class="sxs-lookup"><span data-stu-id="0561c-116">Exceptions contain a property named <xref:System.Exception.StackTrace%2A>.</span></span> <span data-ttu-id="0561c-117">此字符串包含当前调用堆栈上的方法的名称，以及为每个方法引发异常的位置（文件名和行号）。</span><span class="sxs-lookup"><span data-stu-id="0561c-117">This string contains the name of the methods on the current call stack, together with the file name and line number where the exception was thrown for each method.</span></span> <span data-ttu-id="0561c-118"><xref:System.Exception.StackTrace%2A> 对象由公共语言运行时 (CLR) 从 `throw` 语句的位置点自动创建，因此必须从堆栈跟踪的开始点引发异常。</span><span class="sxs-lookup"><span data-stu-id="0561c-118">A <xref:System.Exception.StackTrace%2A> object is created automatically by the common language runtime (CLR) from the point of the `throw` statement, so that exceptions must be thrown from the point where the stack trace should begin.</span></span>  
  
 <span data-ttu-id="0561c-119">所有异常都包含一个名为 <xref:System.Exception.Message%2A> 的属性。</span><span class="sxs-lookup"><span data-stu-id="0561c-119">All exceptions contain a property named <xref:System.Exception.Message%2A>.</span></span> <span data-ttu-id="0561c-120">应设置此字符串来解释发生异常的原因。</span><span class="sxs-lookup"><span data-stu-id="0561c-120">This string should be set to explain the reason for the exception.</span></span> <span data-ttu-id="0561c-121">请注意，不应将安全敏感的信息放在消息文本中。</span><span class="sxs-lookup"><span data-stu-id="0561c-121">Note that information that is sensitive to security should not be put in the message text.</span></span> <span data-ttu-id="0561c-122">除 <xref:System.Exception.Message%2A> 以外，<xref:System.ArgumentException> 也包含一个名为 <xref:System.ArgumentException.ParamName%2A> 的属性，应将该属性设置为导致引发异常的参数的名称。</span><span class="sxs-lookup"><span data-stu-id="0561c-122">In addition to <xref:System.Exception.Message%2A>, <xref:System.ArgumentException> contains a property named <xref:System.ArgumentException.ParamName%2A> that should be set to the name of the argument that caused the exception to be thrown.</span></span> <span data-ttu-id="0561c-123">对于属性资源库，<xref:System.ArgumentException.ParamName%2A> 应设置为 `value`。</span><span class="sxs-lookup"><span data-stu-id="0561c-123">In the case of a property setter, <xref:System.ArgumentException.ParamName%2A> should be set to `value`.</span></span>  
  
 <span data-ttu-id="0561c-124">公共的受保护方法在无法完成其预期功能时应引发异常。</span><span class="sxs-lookup"><span data-stu-id="0561c-124">Public and protected methods should throw exceptions whenever they cannot complete their intended functions.</span></span> <span data-ttu-id="0561c-125">引发的异常类应是符合错误条件的最具体的可用异常。</span><span class="sxs-lookup"><span data-stu-id="0561c-125">The exception class that is thrown should be the most specific exception available that fits the error conditions.</span></span> <span data-ttu-id="0561c-126">这些异常应编写为类功能的一部分，并且原始类的派生类或更新应保留相同的行为以实现后向兼容性。</span><span class="sxs-lookup"><span data-stu-id="0561c-126">These exceptions should be documented as part of the class functionality, and derived classes or updates to the original class should retain the same behavior for backward compatibility.</span></span>  
  
## <a name="things-to-avoid-when-throwing-exceptions"></a><span data-ttu-id="0561c-127">引发异常时应避免的情况</span><span class="sxs-lookup"><span data-stu-id="0561c-127">Things to Avoid When Throwing Exceptions</span></span>  
 <span data-ttu-id="0561c-128">以下列表标识了引发异常时要避免的做法：</span><span class="sxs-lookup"><span data-stu-id="0561c-128">The following list identifies practices to avoid when throwing exceptions:</span></span>  
  
-   <span data-ttu-id="0561c-129">异常不能用于在正常执行过程中更改程序的流程。</span><span class="sxs-lookup"><span data-stu-id="0561c-129">Exceptions should not be used to change the flow of a program as part of ordinary execution.</span></span> <span data-ttu-id="0561c-130">异常只能用于报告和处理错误条件。</span><span class="sxs-lookup"><span data-stu-id="0561c-130">Exceptions should only be used to report and handle error conditions.</span></span>  
  
-   <span data-ttu-id="0561c-131">只能引发异常，而不能作为返回值或参数返回异常。</span><span class="sxs-lookup"><span data-stu-id="0561c-131">Exceptions should not be returned as a return value or parameter instead of being thrown.</span></span>  
  
-   <span data-ttu-id="0561c-132">请勿有意从自己的源代码中引发 <xref:System.Exception?displayProperty=nameWithType>、<xref:System.SystemException?displayProperty=nameWithType>、<xref:System.NullReferenceException?displayProperty=nameWithType> 或 <xref:System.IndexOutOfRangeException?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="0561c-132">Do not throw <xref:System.Exception?displayProperty=nameWithType>, <xref:System.SystemException?displayProperty=nameWithType>, <xref:System.NullReferenceException?displayProperty=nameWithType>, or <xref:System.IndexOutOfRangeException?displayProperty=nameWithType> intentionally from your own source code.</span></span>  
  
-   <span data-ttu-id="0561c-133">不要创建可在调试模式下引发，但不会在发布模式下引发的异常。</span><span class="sxs-lookup"><span data-stu-id="0561c-133">Do not create exceptions that can be thrown in debug mode but not release mode.</span></span> <span data-ttu-id="0561c-134">若要在开发阶段确定运行时错误，请改用调试断言。</span><span class="sxs-lookup"><span data-stu-id="0561c-134">To identify run-time errors during the development phase, use Debug Assert instead.</span></span>  
  
## <a name="defining-exception-classes"></a><span data-ttu-id="0561c-135">定义异常类</span><span class="sxs-lookup"><span data-stu-id="0561c-135">Defining Exception Classes</span></span>  
 <span data-ttu-id="0561c-136">程序可以引发 <xref:System> 命名空间中的预定义异常类（前面提到的情况除外），或通过从 <xref:System.Exception> 派生来创建其自己的异常类。</span><span class="sxs-lookup"><span data-stu-id="0561c-136">Programs can throw a predefined exception class in the <xref:System> namespace (except where previously noted), or create their own exception classes by deriving from <xref:System.Exception>.</span></span> <span data-ttu-id="0561c-137">派生类应至少定义四个构造函数：一个默认构造函数、一个用于设置消息属性的构造函数，以及一个用于设置 <xref:System.Exception.Message%2A> 和 <xref:System.Exception.InnerException%2A> 属性的构造函数。</span><span class="sxs-lookup"><span data-stu-id="0561c-137">The derived classes should define at least four constructors: one default constructor, one that sets the message property, and one that sets both the <xref:System.Exception.Message%2A> and <xref:System.Exception.InnerException%2A> properties.</span></span> <span data-ttu-id="0561c-138">第四个构造函数用于序列化异常。</span><span class="sxs-lookup"><span data-stu-id="0561c-138">The fourth constructor is used to serialize the exception.</span></span> <span data-ttu-id="0561c-139">新的异常类应可序列化。</span><span class="sxs-lookup"><span data-stu-id="0561c-139">New exception classes should be serializable.</span></span> <span data-ttu-id="0561c-140">例如:</span><span class="sxs-lookup"><span data-stu-id="0561c-140">For example:</span></span>  
  
 [!code-csharp[csProgGuideExceptions#15](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/creating-and-throwing-exceptions_4.cs)]  
  
 <span data-ttu-id="0561c-141">只有当新属性提供的数据有助于解决异常时，才应将其添加到异常类中。</span><span class="sxs-lookup"><span data-stu-id="0561c-141">New properties should only be added to the exception class when the data they provide is useful to resolving the exception.</span></span> <span data-ttu-id="0561c-142">如果将新属性添加到派生异常类中，则应替代 `ToString()` 以返回添加的信息。</span><span class="sxs-lookup"><span data-stu-id="0561c-142">If new properties are added to the derived exception class, `ToString()` should be overridden to return the added information.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="0561c-143">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="0561c-143">C# Language Specification</span></span>  

<span data-ttu-id="0561c-144">有关详细信息，请参阅 [C# 语言规范](../../language-reference/language-specification/index.md)中的[异常](~/_csharplang/spec/exceptions.md)和 [throw 语句](~/_csharplang/spec/statements.md#the-throw-statement)。</span><span class="sxs-lookup"><span data-stu-id="0561c-144">For more information, see [Exceptions](~/_csharplang/spec/exceptions.md) and [The throw statement](~/_csharplang/spec/statements.md#the-throw-statement) in the [C# Language Specification](../../language-reference/language-specification/index.md).</span></span> <span data-ttu-id="0561c-145">该语言规范是 C# 语法和用法的权威资料。</span><span class="sxs-lookup"><span data-stu-id="0561c-145">The language specification is the definitive source for C# syntax and usage.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="0561c-146">请参阅</span><span class="sxs-lookup"><span data-stu-id="0561c-146">See Also</span></span>

- [<span data-ttu-id="0561c-147">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="0561c-147">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="0561c-148">异常和异常处理</span><span class="sxs-lookup"><span data-stu-id="0561c-148">Exceptions and Exception Handling</span></span>](../../../csharp/programming-guide/exceptions/index.md)  
- [<span data-ttu-id="0561c-149">异常层次结构</span><span class="sxs-lookup"><span data-stu-id="0561c-149">Exception Hierarchy</span></span>](../../../standard/exceptions/index.md)  
- [<span data-ttu-id="0561c-150">异常处理</span><span class="sxs-lookup"><span data-stu-id="0561c-150">Exception Handling</span></span>](../../../csharp/programming-guide/exceptions/exception-handling.md)
