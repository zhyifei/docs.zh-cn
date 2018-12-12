---
title: 编写单元测试的最佳做法
description: 了解有关编写可提高代码质量和弹性的单元测试的最佳做法
author: jpreese
ms.author: wiwagn
ms.date: 07/28/2018
ms.openlocfilehash: 00a0b999c9a08b04cb33bcb3a332513292beb363
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2018
ms.locfileid: "53143401"
---
# <a name="unit-testing-best-practices"></a><span data-ttu-id="6a2bd-103">单元测试最佳做法</span><span class="sxs-lookup"><span data-stu-id="6a2bd-103">Unit testing best practices</span></span>

<span data-ttu-id="6a2bd-104">作者是 [John Reese](http://reesespieces.io) 且特别感谢 [Roy Osherove](http://osherove.com/)</span><span class="sxs-lookup"><span data-stu-id="6a2bd-104">By [John Reese](http://reesespieces.io) with special thanks to [Roy Osherove](http://osherove.com/)</span></span>

<span data-ttu-id="6a2bd-105">编写单元测试有许多好处；它们有助于回归、提供文档和促进良好的设计。</span><span class="sxs-lookup"><span data-stu-id="6a2bd-105">There are numerous benefits to writing unit tests; they help with regression, provide documentation, and facilitate good design.</span></span> <span data-ttu-id="6a2bd-106">然而，难懂且脆弱的单元测试会对代码库造成严重破坏。</span><span class="sxs-lookup"><span data-stu-id="6a2bd-106">However, hard to read and brittle unit tests can wreak havoc on your code base.</span></span>

<span data-ttu-id="6a2bd-107">本指南将介绍一些在编写单元测试时的最佳做法，使测试具有弹性且易于理解。</span><span class="sxs-lookup"><span data-stu-id="6a2bd-107">In this guide, you'll learn some best practices when writing unit tests to keep your tests resilient and easy to understand.</span></span>

## <a name="why-unit-test"></a><span data-ttu-id="6a2bd-108">为什么要执行单元测试？</span><span class="sxs-lookup"><span data-stu-id="6a2bd-108">Why unit test?</span></span>

### <a name="less-time-performing-functional-tests"></a><span data-ttu-id="6a2bd-109">比执行功能测试节省时间</span><span class="sxs-lookup"><span data-stu-id="6a2bd-109">Less time performing functional tests</span></span>
<span data-ttu-id="6a2bd-110">功能测试费用高。</span><span class="sxs-lookup"><span data-stu-id="6a2bd-110">Functional tests are expensive.</span></span> <span data-ttu-id="6a2bd-111">它们通常涉及打开应用程序并执行一系列你（或其他人）必须遵循的步骤，以验证预期的行为。</span><span class="sxs-lookup"><span data-stu-id="6a2bd-111">They typically involve opening up the application and performing a series of steps that you (or someone else), must follow in order to validate the expected behavior.</span></span> <span data-ttu-id="6a2bd-112">测试人员可能并不总是了解这些步骤，这意味着为了执行测试，他们必须联系更熟悉该领域的人。</span><span class="sxs-lookup"><span data-stu-id="6a2bd-112">These steps may not always be known to the tester, which means they will have to reach out to someone more knowledgeable in the area in order to carry out the test.</span></span> <span data-ttu-id="6a2bd-113">对于细微更改，测试本身可能需要几秒钟，对于较大更改，可能需要几分钟。</span><span class="sxs-lookup"><span data-stu-id="6a2bd-113">Testing itself could take seconds for trivial changes, or minutes for larger changes.</span></span> <span data-ttu-id="6a2bd-114">最后，在系统中所做的每项更改都必须重复此过程。</span><span class="sxs-lookup"><span data-stu-id="6a2bd-114">Lastly, this process must be repeated for every change that you make in the system.</span></span>

<span data-ttu-id="6a2bd-115">而单元测试只需按一下按钮即可运行，只需要几毫秒时间，且无需测试人员了解整个系统。</span><span class="sxs-lookup"><span data-stu-id="6a2bd-115">Unit tests, on the other hand, take milliseconds, can be run at the press of a button and do not necessarily require any knowledge of the system at large.</span></span> <span data-ttu-id="6a2bd-116">测试通过与否取决于测试运行程序，而非测试人员。</span><span class="sxs-lookup"><span data-stu-id="6a2bd-116">Whether or not the test passes or fails is up to the test runner, not the individual.</span></span>

### <a name="protection-against-regression"></a><span data-ttu-id="6a2bd-117">防止回归</span><span class="sxs-lookup"><span data-stu-id="6a2bd-117">Protection against regression</span></span>
<span data-ttu-id="6a2bd-118">回归缺陷是在对应用程序进行更改时引入的缺陷。</span><span class="sxs-lookup"><span data-stu-id="6a2bd-118">Regression defects are defects that are introduced when a change is made to the application.</span></span> <span data-ttu-id="6a2bd-119">测试人员通常不仅测试新功能，还要测试预先存在的功能，以验证先前实现的功能是否仍按预期运行。</span><span class="sxs-lookup"><span data-stu-id="6a2bd-119">It is common for testers to not only test their new feature but also features that existed beforehand in order to verify that previously implemented features still function as expected.</span></span>

<span data-ttu-id="6a2bd-120">使用单元测试，可在每次生成后，甚至在更改一行代码后重新运行整套测试。</span><span class="sxs-lookup"><span data-stu-id="6a2bd-120">With unit testing, it's possible to rerun your entire suite of tests after every build or even after you change a line of code.</span></span> <span data-ttu-id="6a2bd-121">让你确信新代码不会破坏现有功能。</span><span class="sxs-lookup"><span data-stu-id="6a2bd-121">Giving you confidence that your new code does not break existing functionality.</span></span>

### <a name="executable-documentation"></a><span data-ttu-id="6a2bd-122">可执行文档</span><span class="sxs-lookup"><span data-stu-id="6a2bd-122">Executable documentation</span></span>
<span data-ttu-id="6a2bd-123">在给定某个输入的情况下，特定方法的作用或行为可能并不总是很明显。</span><span class="sxs-lookup"><span data-stu-id="6a2bd-123">It may not always be obvious what a particular method does or how it behaves given a certain input.</span></span> <span data-ttu-id="6a2bd-124">你可能会问自己：如果我将空白字符串传递给它，此方法会有怎样的行为？</span><span class="sxs-lookup"><span data-stu-id="6a2bd-124">You may ask yourself: How does this method behave if I pass it a blank string?</span></span> <span data-ttu-id="6a2bd-125">Null?</span><span class="sxs-lookup"><span data-stu-id="6a2bd-125">Null?</span></span>

<span data-ttu-id="6a2bd-126">如果你有一套命名正确的单元测试，每个测试应能够清楚地解释给定输入的预期输出。</span><span class="sxs-lookup"><span data-stu-id="6a2bd-126">When you have a suite of well-named unit tests, each test should be able to clearly explain the expected output for a given input.</span></span> <span data-ttu-id="6a2bd-127">此外，它应该能够验证其确实有效。</span><span class="sxs-lookup"><span data-stu-id="6a2bd-127">In addition, it should be able to verify that it actually works.</span></span>

### <a name="less-coupled-code"></a><span data-ttu-id="6a2bd-128">减少耦合代码</span><span class="sxs-lookup"><span data-stu-id="6a2bd-128">Less coupled code</span></span>
<span data-ttu-id="6a2bd-129">当代码紧密耦合时，可能难以进行单元测试。</span><span class="sxs-lookup"><span data-stu-id="6a2bd-129">When code is tightly coupled, it can be difficult to unit test.</span></span> <span data-ttu-id="6a2bd-130">如果不为编写的代码创建单元测试，则耦合可能不太明显。</span><span class="sxs-lookup"><span data-stu-id="6a2bd-130">Without creating unit tests for the code that you're writing, coupling may be less apparent.</span></span>

<span data-ttu-id="6a2bd-131">为代码编写测试会自然地解耦代码，因为采用其他方法测试会更困难。</span><span class="sxs-lookup"><span data-stu-id="6a2bd-131">Writing tests for your code will naturally decouple your code, because it would be more difficult to test otherwise.</span></span>

## <a name="characteristics-of-a-good-unit-test"></a><span data-ttu-id="6a2bd-132">优质单元测试的特征</span><span class="sxs-lookup"><span data-stu-id="6a2bd-132">Characteristics of a good unit test</span></span>
- <span data-ttu-id="6a2bd-133">快速。</span><span class="sxs-lookup"><span data-stu-id="6a2bd-133">**Fast**.</span></span> <span data-ttu-id="6a2bd-134">对成熟项目进行数千次单元测试，这很常见。</span><span class="sxs-lookup"><span data-stu-id="6a2bd-134">It is not uncommon for mature projects to have thousands of unit tests.</span></span> <span data-ttu-id="6a2bd-135">应花非常少的时间来运行单元测试。</span><span class="sxs-lookup"><span data-stu-id="6a2bd-135">Unit tests should take very little time to run.</span></span> <span data-ttu-id="6a2bd-136">几毫秒。</span><span class="sxs-lookup"><span data-stu-id="6a2bd-136">Milliseconds.</span></span>
- <span data-ttu-id="6a2bd-137">独立。</span><span class="sxs-lookup"><span data-stu-id="6a2bd-137">**Isolated**.</span></span> <span data-ttu-id="6a2bd-138">单元测试是独立的，可以单独运行，并且不依赖文件系统或数据库等任何外部因素。</span><span class="sxs-lookup"><span data-stu-id="6a2bd-138">Unit tests are standalone, can be run in isolation, and have no dependencies on any outside factors such as a file system or database.</span></span>
- <span data-ttu-id="6a2bd-139">可重复。</span><span class="sxs-lookup"><span data-stu-id="6a2bd-139">**Repeatable**.</span></span> <span data-ttu-id="6a2bd-140">运行单元测试的结果应该保持一致，也就是说，如果在运行期间不更改任何内容，总是返回相同的结果。</span><span class="sxs-lookup"><span data-stu-id="6a2bd-140">Running a unit test should be consistent with its results, that is, it always returns the same result if you do not change anything in between runs.</span></span>
- <span data-ttu-id="6a2bd-141">自检查。</span><span class="sxs-lookup"><span data-stu-id="6a2bd-141">**Self-Checking**.</span></span> <span data-ttu-id="6a2bd-142">测试应该能够在没有任何人工交互的情况下，自动检测测试是否通过。</span><span class="sxs-lookup"><span data-stu-id="6a2bd-142">The test should be able to automatically detect if it passed or failed without any human interaction.</span></span>
- <span data-ttu-id="6a2bd-143">及时。</span><span class="sxs-lookup"><span data-stu-id="6a2bd-143">**Timely**.</span></span> <span data-ttu-id="6a2bd-144">与要测试的代码相比，单元测试不应花费不成比例的时间来编写。</span><span class="sxs-lookup"><span data-stu-id="6a2bd-144">A unit test should not take a disproportionally long time to write compared to the code being tested.</span></span> <span data-ttu-id="6a2bd-145">如果发现测试代码与编写代码相比需要花费大量的时间，请考虑一种更易测试的设计。</span><span class="sxs-lookup"><span data-stu-id="6a2bd-145">If you find testing the code taking a large amount of time compared to writing the code, consider a design that is more testable.</span></span>

## <a name="lets-speak-the-same-language"></a><span data-ttu-id="6a2bd-146">让我们使用相同的术语</span><span class="sxs-lookup"><span data-stu-id="6a2bd-146">Let's speak the same language</span></span>
<span data-ttu-id="6a2bd-147">遗憾的是，当谈到测试时，术语“mock”的滥用情况很严重。</span><span class="sxs-lookup"><span data-stu-id="6a2bd-147">The term *mock* is unfortunately very misused when talking about testing.</span></span> <span data-ttu-id="6a2bd-148">以下定义了编写单元测试时最常见的 fake 类型：</span><span class="sxs-lookup"><span data-stu-id="6a2bd-148">The following defines the most common types of *fakes* when writing unit tests:</span></span>

<span data-ttu-id="6a2bd-149">Fake - Fake 是一个通用术语，可用于描述 stub 或 mock 对象。</span><span class="sxs-lookup"><span data-stu-id="6a2bd-149">*Fake* - A fake is a generic term which can be used to describe either a stub or a mock object.</span></span> <span data-ttu-id="6a2bd-150">它是 stub 还是 mock 取决于使用它的上下文。</span><span class="sxs-lookup"><span data-stu-id="6a2bd-150">Whether it is a stub or a mock depends on the context in which it's used.</span></span> <span data-ttu-id="6a2bd-151">也就是说，Fake 可以是 stub 或 mock。</span><span class="sxs-lookup"><span data-stu-id="6a2bd-151">So in other words, a fake can be a stub or a mock.</span></span>

<span data-ttu-id="6a2bd-152">Mock - Mock 对象是系统中的 fake 对象，用于确定单元测试是否通过。</span><span class="sxs-lookup"><span data-stu-id="6a2bd-152">*Mock* - A mock object is a fake object in the system that decides whether or not a unit test has passed or failed.</span></span> <span data-ttu-id="6a2bd-153">Mock 起初为 Fake，直到对其断言。</span><span class="sxs-lookup"><span data-stu-id="6a2bd-153">A mock starts out as a Fake until it is asserted against.</span></span>

<span data-ttu-id="6a2bd-154">Stub - Stub 是系统中现有依赖项（或协作者）的可控制替代项。</span><span class="sxs-lookup"><span data-stu-id="6a2bd-154">*Stub* - A stub is a controllable replacement for an existing dependency (or collaborator) in the system.</span></span> <span data-ttu-id="6a2bd-155">通过使用 Stub，可以在无需使用依赖项的情况下直接测试代码。</span><span class="sxs-lookup"><span data-stu-id="6a2bd-155">By using a stub, you can test your code without dealing with the dependency directly.</span></span> <span data-ttu-id="6a2bd-156">默认情况下，fake 起初为 Stub。</span><span class="sxs-lookup"><span data-stu-id="6a2bd-156">By default, a fake starts out as a stub.</span></span>

<span data-ttu-id="6a2bd-157">请思考以下代码片段：</span><span class="sxs-lookup"><span data-stu-id="6a2bd-157">Consider the following code snippet:</span></span>

```csharp
var mockOrder = new MockOrder();
var purchase = new Purchase(mockOrder);

purchase.ValidateOrders();

Assert.True(purchase.CanBeShipped);
```

<span data-ttu-id="6a2bd-158">这是 Stub 被引用为 mock 的一个示例。</span><span class="sxs-lookup"><span data-stu-id="6a2bd-158">This would be an example of stub being referred to as a mock.</span></span> <span data-ttu-id="6a2bd-159">在本例中，它是 Stub。</span><span class="sxs-lookup"><span data-stu-id="6a2bd-159">In this case, it is a stub.</span></span> <span data-ttu-id="6a2bd-160">只是将 Order 作为实例化 `Purchase`（被测系统）的一种方法传递。</span><span class="sxs-lookup"><span data-stu-id="6a2bd-160">You're just passing in the Order as a means to be able to instantiate `Purchase` (the system under test).</span></span> <span data-ttu-id="6a2bd-161">名称 `MockOrder` 也非常具有误导性，因为同样地 order 不是 mock。</span><span class="sxs-lookup"><span data-stu-id="6a2bd-161">The name `MockOrder` is also very misleading because again, the order is not a mock.</span></span>

<span data-ttu-id="6a2bd-162">更好的方法是</span><span class="sxs-lookup"><span data-stu-id="6a2bd-162">A better approach would be</span></span>

```csharp
var stubOrder = new FakeOrder();
var purchase = new Purchase(stubOrder);

purchase.ValidateOrders();

Assert.True(purchase.CanBeShipped);
```

<span data-ttu-id="6a2bd-163">通过将类重命名为 `FakeOrder`，使类更通用，类可以用作 mock 或 stub。</span><span class="sxs-lookup"><span data-stu-id="6a2bd-163">By renaming the class to `FakeOrder`, you've made the class a lot more generic, the class can be used as a mock or a stub.</span></span> <span data-ttu-id="6a2bd-164">以更适合测试用例者为准。</span><span class="sxs-lookup"><span data-stu-id="6a2bd-164">Whichever is better for the test case.</span></span> <span data-ttu-id="6a2bd-165">在上述示例中，`FakeOrder` 用作 stub。</span><span class="sxs-lookup"><span data-stu-id="6a2bd-165">In the above example, `FakeOrder` is used as a stub.</span></span> <span data-ttu-id="6a2bd-166">在断言期间，没有以任何形状或形式使用 `FakeOrder`。</span><span class="sxs-lookup"><span data-stu-id="6a2bd-166">You're not using the `FakeOrder` in any shape or form during the assert.</span></span> <span data-ttu-id="6a2bd-167">`FakeOrder` 只传递到 `Purchase` 类，以满足构造函数的要求。</span><span class="sxs-lookup"><span data-stu-id="6a2bd-167">`FakeOrder` was just passed into the `Purchase` class to satisfy the requirements of the constructor.</span></span>

<span data-ttu-id="6a2bd-168">要将其用作 Mock，可执行如下操作</span><span class="sxs-lookup"><span data-stu-id="6a2bd-168">To use it as a Mock, you could do something like this</span></span>

```csharp
var mockOrder = new FakeOrder();
var purchase = new Purchase(mockOrder);

purchase.ValidateOrders();

Assert.True(mockOrder.Validated);
```

<span data-ttu-id="6a2bd-169">在这种情况下，检查 Fake 上的属性（对其进行断言），因此在以上代码片段中，`mockOrder` 是 Mock。</span><span class="sxs-lookup"><span data-stu-id="6a2bd-169">In this case, you are checking a property on the Fake (asserting against it), so in the above code snippet, the `mockOrder` is a Mock.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6a2bd-170">正确理解此术语至关重要。</span><span class="sxs-lookup"><span data-stu-id="6a2bd-170">It's important to get this terminology correct.</span></span> <span data-ttu-id="6a2bd-171">如果将 stub 称为 mock，其他开发人员会对你的意图做出错误的判断。</span><span class="sxs-lookup"><span data-stu-id="6a2bd-171">If you call your stubs "mocks", other developers are going to make false assumptions about your intent.</span></span>

<span data-ttu-id="6a2bd-172">关于 mock 与 stub 需要注意的一个重点是，mock 与 stub 很像，但可以针对 mock 对象进行断言，而不针对 stub 进行断言。</span><span class="sxs-lookup"><span data-stu-id="6a2bd-172">The main thing to remember about mocks versus stubs is that mocks are just like stubs, but you assert against the mock object, whereas you do not assert against a stub.</span></span>

## <a name="best-practices"></a><span data-ttu-id="6a2bd-173">最佳实践</span><span class="sxs-lookup"><span data-stu-id="6a2bd-173">Best practices</span></span>

### <a name="naming-your-tests"></a><span data-ttu-id="6a2bd-174">为测试命名</span><span class="sxs-lookup"><span data-stu-id="6a2bd-174">Naming your tests</span></span>
<span data-ttu-id="6a2bd-175">测试的名称应包括三个部分：</span><span class="sxs-lookup"><span data-stu-id="6a2bd-175">The name of your test should consist of three parts:</span></span>
- <span data-ttu-id="6a2bd-176">要测试的方法的名称。</span><span class="sxs-lookup"><span data-stu-id="6a2bd-176">The name of the method being tested.</span></span>
- <span data-ttu-id="6a2bd-177">测试的方案。</span><span class="sxs-lookup"><span data-stu-id="6a2bd-177">The scenario under which it's being tested.</span></span>
- <span data-ttu-id="6a2bd-178">调用方案时的预期行为。</span><span class="sxs-lookup"><span data-stu-id="6a2bd-178">The expected behavior when the scenario is invoked.</span></span>

#### <a name="why"></a><span data-ttu-id="6a2bd-179">为什么？</span><span class="sxs-lookup"><span data-stu-id="6a2bd-179">Why?</span></span>
- <span data-ttu-id="6a2bd-180">命名标准非常重要，因为它们明确地表达了测试的意图。</span><span class="sxs-lookup"><span data-stu-id="6a2bd-180">Naming standards are important because they explicitly express the intent of the test.</span></span>

<span data-ttu-id="6a2bd-181">测试不仅能确保代码有效，还能提供文档。</span><span class="sxs-lookup"><span data-stu-id="6a2bd-181">Tests are more than just making sure your code works, they also provide documentation.</span></span> <span data-ttu-id="6a2bd-182">只需查看单元测试套件，就可以在不查看代码本身的情况下推断代码的行为。</span><span class="sxs-lookup"><span data-stu-id="6a2bd-182">Just by looking at the suite of unit tests, you should be able to infer the behavior of your code without even looking at the code itself.</span></span> <span data-ttu-id="6a2bd-183">此外，测试失败时，可以确切地看到哪些方案不符合预期。</span><span class="sxs-lookup"><span data-stu-id="6a2bd-183">Additionally, when tests fail, you can see exactly which scenarios do not meet your expectations.</span></span>

#### <a name="bad"></a><span data-ttu-id="6a2bd-184">不佳：</span><span class="sxs-lookup"><span data-stu-id="6a2bd-184">Bad:</span></span>
[!code-csharp[BeforeNaming](../../../samples/csharp/unit-testing-best-practices/before/StringCalculatorTests.cs#BeforeNaming)]

#### <a name="better"></a><span data-ttu-id="6a2bd-185">良好：</span><span class="sxs-lookup"><span data-stu-id="6a2bd-185">Better:</span></span>
[!code-csharp[AfterNamingAndMinimallyPassing](../../../samples/csharp/unit-testing-best-practices/after/StringCalculatorTests.cs#AfterNamingAndMinimallyPassing)]

### <a name="arranging-your-tests"></a><span data-ttu-id="6a2bd-186">安排测试</span><span class="sxs-lookup"><span data-stu-id="6a2bd-186">Arranging your tests</span></span>
<span data-ttu-id="6a2bd-187">“Arrange、Act、Assert”是单元测试时的常见模式。</span><span class="sxs-lookup"><span data-stu-id="6a2bd-187">**Arrange, Act, Assert** is a common pattern when unit testing.</span></span> <span data-ttu-id="6a2bd-188">顾名思义，它包含三个主要操作：</span><span class="sxs-lookup"><span data-stu-id="6a2bd-188">As the name implies, it consists of three main actions:</span></span>
- <span data-ttu-id="6a2bd-189">安排对象，根据需要对其进行创建和设置。</span><span class="sxs-lookup"><span data-stu-id="6a2bd-189">*Arrange* your objects, creating and setting them up as necessary.</span></span>
- <span data-ttu-id="6a2bd-190">作用于对象。</span><span class="sxs-lookup"><span data-stu-id="6a2bd-190">*Act* on an object.</span></span>
- <span data-ttu-id="6a2bd-191">断言某些项按预期进行。</span><span class="sxs-lookup"><span data-stu-id="6a2bd-191">*Assert* that something is as expected.</span></span>

#### <a name="why"></a><span data-ttu-id="6a2bd-192">为什么？</span><span class="sxs-lookup"><span data-stu-id="6a2bd-192">Why?</span></span>
- <span data-ttu-id="6a2bd-193">明确地将要测试的内容从“arrange”和“assert”步骤分开。</span><span class="sxs-lookup"><span data-stu-id="6a2bd-193">Clearly separates what is being tested from the *arrange* and *assert* steps.</span></span>
- <span data-ttu-id="6a2bd-194">降低将断言与“Act”代码混杂的可能性。</span><span class="sxs-lookup"><span data-stu-id="6a2bd-194">Less chance to intermix assertions with "Act" code.</span></span>

<span data-ttu-id="6a2bd-195">可读性是编写测试时最重要的方面之一。</span><span class="sxs-lookup"><span data-stu-id="6a2bd-195">Readability is one of the most important aspects when writing a test.</span></span> <span data-ttu-id="6a2bd-196">在测试中分离这些操作会明确地突出显示调用代码所需的依赖项、调用代码的方式以及尝试断言的内容。</span><span class="sxs-lookup"><span data-stu-id="6a2bd-196">Separating each of these actions within the test clearly highlight the dependencies required to call your code, how your code is being called, and what you are trying to assert.</span></span> <span data-ttu-id="6a2bd-197">虽然可以组合一些步骤并减小测试的大小，但主要目标是使测试尽可能可读。</span><span class="sxs-lookup"><span data-stu-id="6a2bd-197">While it may be possible to combine some steps and reduce the size of your test, the primary goal is to make the test as readable as possible.</span></span>

#### <a name="bad"></a><span data-ttu-id="6a2bd-198">不佳：</span><span class="sxs-lookup"><span data-stu-id="6a2bd-198">Bad:</span></span>
[!code-csharp[BeforeArranging](../../../samples/csharp/unit-testing-best-practices/before/StringCalculatorTests.cs#BeforeArranging)]

#### <a name="better"></a><span data-ttu-id="6a2bd-199">良好：</span><span class="sxs-lookup"><span data-stu-id="6a2bd-199">Better:</span></span>
[!code-csharp[AfterArranging](../../../samples/csharp/unit-testing-best-practices/after/StringCalculatorTests.cs#AfterArranging)]

### <a name="write-minimally-passing-tests"></a><span data-ttu-id="6a2bd-200">以最精简方式编写通过测试</span><span class="sxs-lookup"><span data-stu-id="6a2bd-200">Write minimally passing tests</span></span>
<span data-ttu-id="6a2bd-201">单元测试中使用的输入应为最简单的输入，以便验证当前正在测试的行为。</span><span class="sxs-lookup"><span data-stu-id="6a2bd-201">The input to be used in a unit test should be the simplest possible in order to verify the behavior that you are currently testing.</span></span>

#### <a name="why"></a><span data-ttu-id="6a2bd-202">为什么？</span><span class="sxs-lookup"><span data-stu-id="6a2bd-202">Why?</span></span>
- <span data-ttu-id="6a2bd-203">测试对代码库的未来更改更具弹性。</span><span class="sxs-lookup"><span data-stu-id="6a2bd-203">Tests become more resilient to future changes in the codebase.</span></span>
- <span data-ttu-id="6a2bd-204">更接近于测试行为而非实现。</span><span class="sxs-lookup"><span data-stu-id="6a2bd-204">Closer to testing behavior over implementation.</span></span>

<span data-ttu-id="6a2bd-205">包含比通过测试所需信息更多信息的测试更可能将错误引入测试，并且可能使测试的意图变得不太明确。</span><span class="sxs-lookup"><span data-stu-id="6a2bd-205">Tests that include more information than required to pass the test have a higher chance of introducing errors into the test and can make the intent of the test less clear.</span></span> <span data-ttu-id="6a2bd-206">编写测试时需要将重点放在行为上。</span><span class="sxs-lookup"><span data-stu-id="6a2bd-206">When writing tests you want to focus on the behavior.</span></span> <span data-ttu-id="6a2bd-207">在模型上设置额外的属性或在不需要时使用非零值，只会偏离所要证明的内容。</span><span class="sxs-lookup"><span data-stu-id="6a2bd-207">Setting extra properties on models or using non-zero values when not required, only detracts from what you are trying to prove.</span></span>

#### <a name="bad"></a><span data-ttu-id="6a2bd-208">不佳：</span><span class="sxs-lookup"><span data-stu-id="6a2bd-208">Bad:</span></span>
[!code-csharp[BeforeMinimallyPassing](../../../samples/csharp/unit-testing-best-practices/before/StringCalculatorTests.cs#BeforeMinimallyPassing)]

#### <a name="better"></a><span data-ttu-id="6a2bd-209">良好：</span><span class="sxs-lookup"><span data-stu-id="6a2bd-209">Better:</span></span>
[!code-csharp[AfterNamingAndMinimallyPassing](../../../samples/csharp/unit-testing-best-practices/after/StringCalculatorTests.cs#AfterNamingAndMinimallyPassing)]

### <a name="avoid-magic-strings"></a><span data-ttu-id="6a2bd-210">避免魔幻字符串</span><span class="sxs-lookup"><span data-stu-id="6a2bd-210">Avoid magic strings</span></span>
<span data-ttu-id="6a2bd-211">单元测试中的命名变量和生产代码中的命名变量同样重要。</span><span class="sxs-lookup"><span data-stu-id="6a2bd-211">Naming variables in unit tests is as important, if not more important, than naming variables in production code.</span></span> <span data-ttu-id="6a2bd-212">单元测试不应包含魔幻字符串。</span><span class="sxs-lookup"><span data-stu-id="6a2bd-212">Unit tests should not contain magic strings.</span></span>

#### <a name="why"></a><span data-ttu-id="6a2bd-213">为什么？</span><span class="sxs-lookup"><span data-stu-id="6a2bd-213">Why?</span></span>
- <span data-ttu-id="6a2bd-214">测试读者无需检查生产代码即可了解值的特殊之处。</span><span class="sxs-lookup"><span data-stu-id="6a2bd-214">Prevents the need for the reader of the test to inspect the production code in order to figure out what makes the value special.</span></span>
- <span data-ttu-id="6a2bd-215">明确地显示所要证明的内容，而不是显示要完成的内容。</span><span class="sxs-lookup"><span data-stu-id="6a2bd-215">Explicitly shows what you're trying to *prove* rather than trying to *accomplish*.</span></span>

<span data-ttu-id="6a2bd-216">魔幻字符串可能会让测试读者感到困惑。</span><span class="sxs-lookup"><span data-stu-id="6a2bd-216">Magic strings can cause confusion to the reader of your tests.</span></span> <span data-ttu-id="6a2bd-217">如果字符串看起来不寻常，他们可能想知道为什么为某个参数或返回值选择了某个值。</span><span class="sxs-lookup"><span data-stu-id="6a2bd-217">If a string looks out of the ordinary, they may wonder why a certain value was chosen for a parameter or return value.</span></span> <span data-ttu-id="6a2bd-218">这可能会使他们仔细查看实现细节，而不是专注于测试。</span><span class="sxs-lookup"><span data-stu-id="6a2bd-218">This may lead them to take a closer look at the implementation details, rather than focus on the test.</span></span>

> [!TIP] 
> <span data-ttu-id="6a2bd-219">编写测试时，应力求表达尽可能多的意图。</span><span class="sxs-lookup"><span data-stu-id="6a2bd-219">When writing tests, you should aim to express as much intent as possible.</span></span> <span data-ttu-id="6a2bd-220">对于魔幻字符串，一种很好的方法是将这些值赋给常量。</span><span class="sxs-lookup"><span data-stu-id="6a2bd-220">In the case of magic strings, a good approach is to assign these values to constants.</span></span>

#### <a name="bad"></a><span data-ttu-id="6a2bd-221">不佳：</span><span class="sxs-lookup"><span data-stu-id="6a2bd-221">Bad:</span></span>
[!code-csharp[BeforeMagicString](../../../samples/csharp/unit-testing-best-practices/before/StringCalculatorTests.cs#BeforeMagicString)]

#### <a name="better"></a><span data-ttu-id="6a2bd-222">良好：</span><span class="sxs-lookup"><span data-stu-id="6a2bd-222">Better:</span></span>
[!code-csharp[AfterMagicString](../../../samples/csharp/unit-testing-best-practices/after/StringCalculatorTests.cs#AfterMagicString)]

### <a name="avoid-logic-in-tests"></a><span data-ttu-id="6a2bd-223">在测试中应避免逻辑</span><span class="sxs-lookup"><span data-stu-id="6a2bd-223">Avoid logic in tests</span></span>
<span data-ttu-id="6a2bd-224">编写单元测试时，请避免手动字符串串联和逻辑条件，例如 `if`、`while``for` 和 `switch` 等等。</span><span class="sxs-lookup"><span data-stu-id="6a2bd-224">When writing your unit tests avoid manual string concatenation and logical conditions such as `if`, `while`, `for`, `switch`, etc.</span></span>

#### <a name="why"></a><span data-ttu-id="6a2bd-225">为什么？</span><span class="sxs-lookup"><span data-stu-id="6a2bd-225">Why?</span></span>
- <span data-ttu-id="6a2bd-226">降低在测试中引入 bug 的可能性。</span><span class="sxs-lookup"><span data-stu-id="6a2bd-226">Less chance to introduce a bug inside of your tests.</span></span>
- <span data-ttu-id="6a2bd-227">专注于最终结果，而不是实现细节。</span><span class="sxs-lookup"><span data-stu-id="6a2bd-227">Focus on the end result, rather than implementation details.</span></span>

<span data-ttu-id="6a2bd-228">将逻辑引入测试套件中时，引入 bug 的可能性大幅度增加。</span><span class="sxs-lookup"><span data-stu-id="6a2bd-228">When you introduce logic into your test suite, the chance of introducing a bug into it increases dramatically.</span></span> <span data-ttu-id="6a2bd-229">你最不希望测试套件中出现 bug。</span><span class="sxs-lookup"><span data-stu-id="6a2bd-229">The last place that you want to find a bug is within your test suite.</span></span> <span data-ttu-id="6a2bd-230">你应该对测试工作充满高度的自信，否则你将不会信任它们。</span><span class="sxs-lookup"><span data-stu-id="6a2bd-230">You should have a high level of confidence that your tests work, otherwise, you will not trust them.</span></span> <span data-ttu-id="6a2bd-231">你不信任的测试不会带来任何价值。</span><span class="sxs-lookup"><span data-stu-id="6a2bd-231">Tests that you do not trust, do not provide any value.</span></span> <span data-ttu-id="6a2bd-232">当测试失败时，你希望意识到代码存在问题且无法忽略该问题。</span><span class="sxs-lookup"><span data-stu-id="6a2bd-232">When a test fails, you want to have a sense that something is actually wrong with your code and that it cannot be ignored.</span></span>

> [!TIP]
> <span data-ttu-id="6a2bd-233">如果不可避免地要在测试中使用逻辑，请考虑将测试分成两个或多个不同的测试。</span><span class="sxs-lookup"><span data-stu-id="6a2bd-233">If logic in your test seems unavoidable, consider splitting the test up into two or more different tests.</span></span>

#### <a name="bad"></a><span data-ttu-id="6a2bd-234">不佳：</span><span class="sxs-lookup"><span data-stu-id="6a2bd-234">Bad:</span></span>
[!code-csharp[LogicInTests](../../../samples/csharp/unit-testing-best-practices/before/StringCalculatorTests.cs#LogicInTests)]

#### <a name="better"></a><span data-ttu-id="6a2bd-235">良好：</span><span class="sxs-lookup"><span data-stu-id="6a2bd-235">Better:</span></span>
[!code-csharp[AfterTestLogic](../../../samples/csharp/unit-testing-best-practices/after/StringCalculatorTests.cs#AfterTestLogic)]

### <a name="prefer-helper-methods-to-setup-and-teardown"></a><span data-ttu-id="6a2bd-236">更偏好 helper 方法而非 setup 和 teardown</span><span class="sxs-lookup"><span data-stu-id="6a2bd-236">Prefer helper methods to setup and teardown</span></span>
<span data-ttu-id="6a2bd-237">如果测试需要类似的对象或状态，那么比起使用 Setup 和 Teardown 属性（如果存在），更偏好使用 helper 方法。</span><span class="sxs-lookup"><span data-stu-id="6a2bd-237">If you require a similar object or state for your tests, prefer a helper method than leveraging Setup and Teardown attributes if they exist.</span></span>

#### <a name="why"></a><span data-ttu-id="6a2bd-238">为什么？</span><span class="sxs-lookup"><span data-stu-id="6a2bd-238">Why?</span></span>
- <span data-ttu-id="6a2bd-239">读者阅读测试时产生的困惑减少，因为每个测试中都可以看到所有代码。</span><span class="sxs-lookup"><span data-stu-id="6a2bd-239">Less confusion when reading the tests since all of the code is visible from within each test.</span></span>
- <span data-ttu-id="6a2bd-240">给定测试的设置过多或过少的可能性降低。</span><span class="sxs-lookup"><span data-stu-id="6a2bd-240">Less chance of setting up too much or too little for the given test.</span></span>
- <span data-ttu-id="6a2bd-241">在测试之间共享状态（这会在测试之间创建不需要的依赖项）的可能性降低。</span><span class="sxs-lookup"><span data-stu-id="6a2bd-241">Less chance of sharing state between tests which creates unwanted dependencies between them.</span></span>

<span data-ttu-id="6a2bd-242">在单元测试框架中，在测试套件的每个单元测试之前调用 `Setup`。</span><span class="sxs-lookup"><span data-stu-id="6a2bd-242">In unit testing frameworks, `Setup` is called before each and every unit test within your test suite.</span></span> <span data-ttu-id="6a2bd-243">虽然有些人可能会将其视为有用的工具，但它通常最终导致庞大且难懂的测试。</span><span class="sxs-lookup"><span data-stu-id="6a2bd-243">While some may see this as a useful tool, it generally ends up leading to bloated and hard to read tests.</span></span> <span data-ttu-id="6a2bd-244">每个测试通常有不同的要求，以使测试启动并运行。</span><span class="sxs-lookup"><span data-stu-id="6a2bd-244">Each test will generally have different requirements in order to get the test up and running.</span></span> <span data-ttu-id="6a2bd-245">遗憾的是，`Setup` 迫使你对每个测试使用完全相同的要求。</span><span class="sxs-lookup"><span data-stu-id="6a2bd-245">Unfortunately, `Setup` forces you to use the exact same requirements for each test.</span></span>

> [!NOTE] 
> <span data-ttu-id="6a2bd-246">自版本 2.x 起，xUnit 已删除 SetUp 和 TearDown</span><span class="sxs-lookup"><span data-stu-id="6a2bd-246">xUnit has removed both SetUp and TearDown as of version 2.x</span></span>

#### <a name="bad"></a><span data-ttu-id="6a2bd-247">不佳：</span><span class="sxs-lookup"><span data-stu-id="6a2bd-247">Bad:</span></span>
[!code-csharp[BeforeSetup](../../../samples/csharp/unit-testing-best-practices/before/StringCalculatorTests.cs#BeforeSetup)]

```csharp
// more tests...
```

[!code-csharp[BeforeHelperMethod](../../../samples/csharp/unit-testing-best-practices/before/StringCalculatorTests.cs#BeforeHelperMethod)]

#### <a name="better"></a><span data-ttu-id="6a2bd-248">良好：</span><span class="sxs-lookup"><span data-stu-id="6a2bd-248">Better:</span></span>
[!code-csharp[AfterHelperMethod](../../../samples/csharp/unit-testing-best-practices/after/StringCalculatorTests.cs#AfterHelperMethod)]

```csharp
// more tests...
```

[!code-csharp[AfterSetup](../../../samples/csharp/unit-testing-best-practices/after/StringCalculatorTests.cs#AfterSetup)]

### <a name="avoid-multiple-asserts"></a><span data-ttu-id="6a2bd-249">避免多个断言</span><span class="sxs-lookup"><span data-stu-id="6a2bd-249">Avoid multiple asserts</span></span>
<span data-ttu-id="6a2bd-250">在编写测试时，请尝试每次测试只包含一个 Assert。</span><span class="sxs-lookup"><span data-stu-id="6a2bd-250">When writing your tests, try to only include one Assert per test.</span></span> <span data-ttu-id="6a2bd-251">仅使用一个 assert 的常用方法包括：</span><span class="sxs-lookup"><span data-stu-id="6a2bd-251">Common approaches to using only one assert include:</span></span>
- <span data-ttu-id="6a2bd-252">为每个 assert 创建单独的测试。</span><span class="sxs-lookup"><span data-stu-id="6a2bd-252">Create a separate test for each assert.</span></span>
- <span data-ttu-id="6a2bd-253">使用参数化测试。</span><span class="sxs-lookup"><span data-stu-id="6a2bd-253">Use parameterized tests.</span></span>

#### <a name="why"></a><span data-ttu-id="6a2bd-254">为什么？</span><span class="sxs-lookup"><span data-stu-id="6a2bd-254">Why?</span></span>
- <span data-ttu-id="6a2bd-255">如果一个 Assert 失败，将不计算后续 Assert。</span><span class="sxs-lookup"><span data-stu-id="6a2bd-255">If one Assert fails, the subsequent Asserts will not be evaluated.</span></span>
- <span data-ttu-id="6a2bd-256">确保在测试中没有断言多个事例。</span><span class="sxs-lookup"><span data-stu-id="6a2bd-256">Ensures you are not asserting multiple cases in your tests.</span></span>
- <span data-ttu-id="6a2bd-257">让你从整体上了解测试失败原因。</span><span class="sxs-lookup"><span data-stu-id="6a2bd-257">Gives you the entire picture as to why your tests are failing.</span></span> 

<span data-ttu-id="6a2bd-258">将多个断言引入测试用例时，不能保证所有断言都会执行。</span><span class="sxs-lookup"><span data-stu-id="6a2bd-258">When introducing multiple asserts into a test case, it is not guaranteed that all of the asserts will be executed.</span></span> <span data-ttu-id="6a2bd-259">在大多数单元测试框架中，一旦断言在单元测试中失败，则进行中的测试会自动被视为失败。</span><span class="sxs-lookup"><span data-stu-id="6a2bd-259">In most unit testing frameworks, once an assertion fails in a unit test, the proceeding tests are automatically considered to be failing.</span></span> <span data-ttu-id="6a2bd-260">这可能会令人困惑，因为正在运行的功能将显示为失败。</span><span class="sxs-lookup"><span data-stu-id="6a2bd-260">This can be confusing as functionality that is actually working, will be shown as failing.</span></span>

> [!NOTE]
> <span data-ttu-id="6a2bd-261">此规则的一个常见例外是对对象进行断言。</span><span class="sxs-lookup"><span data-stu-id="6a2bd-261">A common exception to this rule is when asserting against an object.</span></span> <span data-ttu-id="6a2bd-262">在这种情况下，通常可以对每个属性进行多次断言，以确保对象处于所预期的状态。</span><span class="sxs-lookup"><span data-stu-id="6a2bd-262">In this case, it is generally acceptable to have multiple asserts against each property to ensure the object is in the state that you expect it to be in.</span></span>

#### <a name="bad"></a><span data-ttu-id="6a2bd-263">不佳：</span><span class="sxs-lookup"><span data-stu-id="6a2bd-263">Bad:</span></span>
[!code-csharp[BeforeMultipleAsserts](../../../samples/csharp/unit-testing-best-practices/before/StringCalculatorTests.cs#BeforeMultipleAsserts)]

#### <a name="better"></a><span data-ttu-id="6a2bd-264">良好：</span><span class="sxs-lookup"><span data-stu-id="6a2bd-264">Better:</span></span>
[!code-csharp[AfterMultipleAsserts](../../../samples/csharp/unit-testing-best-practices/after/StringCalculatorTests.cs#AfterMultipleAsserts)]

### <a name="validate-private-methods-by-unit-testing-public-methods"></a><span data-ttu-id="6a2bd-265">通过单元测试公共方法验证专有方法</span><span class="sxs-lookup"><span data-stu-id="6a2bd-265">Validate private methods by unit testing public methods</span></span>
<span data-ttu-id="6a2bd-266">在大多数情况下，不需要测试专用方法。</span><span class="sxs-lookup"><span data-stu-id="6a2bd-266">In most cases, there should not be a need to test a private method.</span></span> <span data-ttu-id="6a2bd-267">专用方法是实现细节。</span><span class="sxs-lookup"><span data-stu-id="6a2bd-267">Private methods are an implementation detail.</span></span> <span data-ttu-id="6a2bd-268">可以这样认为：专用方法永远不会孤立存在。</span><span class="sxs-lookup"><span data-stu-id="6a2bd-268">You can think of it this way: private methods never exist in isolation.</span></span> <span data-ttu-id="6a2bd-269">在某些时候，存在调用专用方法作为其实现的一部分的面向公共的方法。</span><span class="sxs-lookup"><span data-stu-id="6a2bd-269">At some point, there is going to be a public facing method that calls the private method as part of its implementation.</span></span> <span data-ttu-id="6a2bd-270">你应关心的是调用到专用方法的公共方法的最终结果。</span><span class="sxs-lookup"><span data-stu-id="6a2bd-270">What you should care about is the end result of the public method that calls into the private one.</span></span> 

<span data-ttu-id="6a2bd-271">请考虑下列情形</span><span class="sxs-lookup"><span data-stu-id="6a2bd-271">Consider the following case</span></span>

```csharp
public string ParseLogLine(string input)
{
    var sanitizedInput = trimInput(input);
    return sanitizedInput;
}

private string trimInput(string input)
{
    return input.Trim();
}
```

<span data-ttu-id="6a2bd-272">你的第一反应可能是开始为 `trimInput` 编写测试，因为想要确保该方法按预期工作。</span><span class="sxs-lookup"><span data-stu-id="6a2bd-272">Your first reaction may be to start writing a test for `trimInput` because you want to make sure that the method is working as expected.</span></span> <span data-ttu-id="6a2bd-273">但是，`ParseLogLine` 完全有可能以一种你所不期望的方式操纵 `sanitizedInput`，使得对 `trimInput` 的测试变得毫无用处。</span><span class="sxs-lookup"><span data-stu-id="6a2bd-273">However, it is entirely possible that `ParseLogLine` manipulates `sanitizedInput` in such a way that you do not expect, rendering a test against `trimInput` useless.</span></span> 

<span data-ttu-id="6a2bd-274">真正的测试应该针对面向公共的方法 `ParseLogLine` 进行，因为这是你最终应该关心的。</span><span class="sxs-lookup"><span data-stu-id="6a2bd-274">The real test should be done against the public facing method `ParseLogLine` because that is what you should ultimately care about.</span></span> 

```csharp
public void ParseLogLine_ByDefault_ReturnsTrimmedResult()
{
    var parser = new Parser();

    var result = parser.ParseLogLine(" a ");

    Assert.Equals("a", result);
}
```

<span data-ttu-id="6a2bd-275">由此，如果看到一个专用方法，可以找到公共方法并针对该方法编写测试。</span><span class="sxs-lookup"><span data-stu-id="6a2bd-275">With this viewpoint, if you see a private method, find the public method and write your tests against that method.</span></span> <span data-ttu-id="6a2bd-276">不能仅仅因为专用方法返回预期结果就认为最终调用专用方法的系统正确地使用结果。</span><span class="sxs-lookup"><span data-stu-id="6a2bd-276">Just because a private method returns the expected result, does not mean the system that eventually calls the private method uses the result correctly.</span></span>

### <a name="stub-static-references"></a><span data-ttu-id="6a2bd-277">Stub 静态引用</span><span class="sxs-lookup"><span data-stu-id="6a2bd-277">Stub static references</span></span>
<span data-ttu-id="6a2bd-278">单元测试的原则之一是其必须完全控制被测试的系统。</span><span class="sxs-lookup"><span data-stu-id="6a2bd-278">One of the principles of a unit test is that it must have full control of the system under test.</span></span> <span data-ttu-id="6a2bd-279">当生产代码包含对静态引用（例如 `DateTime.Now`）的调用时，这可能会存在问题。</span><span class="sxs-lookup"><span data-stu-id="6a2bd-279">This can be problematic when production code includes calls to static references (e.g. `DateTime.Now`).</span></span> <span data-ttu-id="6a2bd-280">考虑下列代码</span><span class="sxs-lookup"><span data-stu-id="6a2bd-280">Consider the following code</span></span>

```csharp
public int GetDiscountedPrice(int price)
{
    if(DateTime.Now == DayOfWeek.Tuesday) 
    {
        return price / 2;
    }
    else 
    {
        return price;
    }
}
```

<span data-ttu-id="6a2bd-281">如何对此代码进行单元测试？</span><span class="sxs-lookup"><span data-stu-id="6a2bd-281">How can this code possibly be unit tested?</span></span> <span data-ttu-id="6a2bd-282">可以尝试一种方法，例如</span><span class="sxs-lookup"><span data-stu-id="6a2bd-282">You may try an approach such as</span></span>

```csharp
public void GetDiscountedPrice_ByDefault_ReturnsFullPrice()
{
    var priceCalculator = new PriceCalculator();

    var actual = priceCalculator.GetDiscountedPrice(2);

    Assert.Equals(2, actual)
}

public void GetDiscountedPrice_OnTuesday_ReturnsHalfPrice()
{
    var priceCalculator = new PriceCalculator();

    var actual = priceCalculator.GetDiscountedPrice(2);

    Assert.Equals(1, actual);
}
```

<span data-ttu-id="6a2bd-283">遗憾的是，你会很快意识到你的测试存在一些问题。</span><span class="sxs-lookup"><span data-stu-id="6a2bd-283">Unfortunately, you will quickly realize that there are a couple problems with your tests.</span></span> 

- <span data-ttu-id="6a2bd-284">如果在星期二运行测试套件，则第二个测试将通过，但第一个测试将失败。</span><span class="sxs-lookup"><span data-stu-id="6a2bd-284">If the test suite is run on a Tuesday, the second test will pass, but the first test will fail.</span></span>
- <span data-ttu-id="6a2bd-285">如果在任何其他日期运行测试套件，则第一个测试将通过，但第二个测试将失败。</span><span class="sxs-lookup"><span data-stu-id="6a2bd-285">If the test suite is run on any other day, the first test will pass, but the second test will fail.</span></span>

<span data-ttu-id="6a2bd-286">要解决这些问题，需要将“seam”引入生产代码中。</span><span class="sxs-lookup"><span data-stu-id="6a2bd-286">To solve these problems, you'll need to introduce a *seam* into your production code.</span></span> <span data-ttu-id="6a2bd-287">一种方法是在接口中包装需要控制的代码，并使生产代码依赖于该接口。</span><span class="sxs-lookup"><span data-stu-id="6a2bd-287">One approach is to wrap the code that you need to control in an interface and have the production code depend on that interface.</span></span>

```csharp
public interface IDateTimeProvider
{
    DayOfWeek DayOfWeek();
}

public int GetDiscountedPrice(int price, IDateTimeProvider dateTimeProvider)
{
    if(dateTimeProvider.DayOfWeek() == DayOfWeek.Tuesday) 
    {
        return price / 2;
    }
    else 
    {
        return price;
    }
}
```

<span data-ttu-id="6a2bd-288">你的测试套件现在变得</span><span class="sxs-lookup"><span data-stu-id="6a2bd-288">Your test suite now becomes</span></span>

```csharp
public void GetDiscountedPrice_ByDefault_ReturnsFullPrice()
{
    var priceCalculator = new PriceCalculator();
    var dateTimeProviderStub = new Mock<IDateTimeProvider>();
    dateTimeProviderStub.Setup(dtp => dtp.DayOfWeek()).Returns(DayOfWeek.Monday);

    var actual = priceCalculator.GetDiscountedPrice(2, dateTimeProviderStub);

    Assert.Equals(2, actual);
}

public void GetDiscountedPrice_OnTuesday_ReturnsHalfPrice()
{
    var priceCalculator = new PriceCalculator();
    var dateTimeProviderStub = new Mock<IDateTimeProvider>();
    dateTimeProviderStub.Setup(dtp => dtp.DayOfWeek()).Returns(DayOfWeek.Tuesday);

    var actual = priceCalculator.GetDiscountedPrice(2, dateTimeProviderStub);

    Assert.Equals(1, actual);
}
```

<span data-ttu-id="6a2bd-289">现在，测试套件可以完全控制 `DateTime.Now`，并且在调用方法时可以存根任何值。</span><span class="sxs-lookup"><span data-stu-id="6a2bd-289">Now the test suite has full control over `DateTime.Now` and can stub any value when calling into the method.</span></span>
