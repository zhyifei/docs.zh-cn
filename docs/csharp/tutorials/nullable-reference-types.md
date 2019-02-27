---
title: 使用可为空引用类型进行设计
description: 本高级教程介绍了可为空引用类型。 你将学习在引用值可能为 NULL 时表达你的设计意图，并在引用值不能为 NULL 时让编译器强制执行。
ms.date: 02/19/2019
ms.custom: mvc
ms.openlocfilehash: 1c0df9b129e9c434eb3b5e6e50144013c2c0462e
ms.sourcegitcommit: acd8ed14fe94e9d4e3a7fb685fe83d05e941073c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/20/2019
ms.locfileid: "56442095"
---
# <a name="tutorial-express-your-design-intent-more-clearly-with-nullable-and-non-nullable-reference-types"></a><span data-ttu-id="e974d-104">教程：使用可为空和不可为空引用类型更清晰地表达设计意图</span><span class="sxs-lookup"><span data-stu-id="e974d-104">Tutorial: Express your design intent more clearly with nullable and non-nullable reference types</span></span>

<span data-ttu-id="e974d-105">C# 8 引入了可为空引用类型，它们以与可为空值类型补充值类型相同的方式补充引用类型。</span><span class="sxs-lookup"><span data-stu-id="e974d-105">C# 8 introduces **nullable reference types**, which complement reference types the same way nullable value types complement value types.</span></span> <span data-ttu-id="e974d-106">通过将 `?` 追加到此类型，你可以将变量声明为可为空引用类型。</span><span class="sxs-lookup"><span data-stu-id="e974d-106">You declare a variable to be a **nullable reference type** by appending a `?` to the type.</span></span> <span data-ttu-id="e974d-107">例如，`string?` 表示可为空的 `string`。</span><span class="sxs-lookup"><span data-stu-id="e974d-107">For example, `string?` represents a nullable `string`.</span></span> <span data-ttu-id="e974d-108">可以使用这些新类型更清楚地表达你的设计意图：某些变量必须始终具有值，其他变量可以缺少值。</span><span class="sxs-lookup"><span data-stu-id="e974d-108">You can use these new types to more clearly express your design intent: some variables *must always have a value*, others *may be missing a value*.</span></span>

<span data-ttu-id="e974d-109">在本教程中，你将了解：</span><span class="sxs-lookup"><span data-stu-id="e974d-109">In this tutorial, you'll learn how to:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="e974d-110">将可为空和不可为空引用类型合并到你的设计中</span><span class="sxs-lookup"><span data-stu-id="e974d-110">Incorporate nullable and non-nullable reference types into your designs</span></span>
> * <span data-ttu-id="e974d-111">在整个代码中启用可为空引用类型检查。</span><span class="sxs-lookup"><span data-stu-id="e974d-111">Enable nullable reference type checks throughout your code.</span></span>
> * <span data-ttu-id="e974d-112">编写编译器强制执行这些设计决策的代码。</span><span class="sxs-lookup"><span data-stu-id="e974d-112">Write code where the compiler enforces those design decisions.</span></span>
> * <span data-ttu-id="e974d-113">在自己的设计中使用可为空引用功能</span><span class="sxs-lookup"><span data-stu-id="e974d-113">Use the nullable reference feature in your own designs</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e974d-114">系统必备</span><span class="sxs-lookup"><span data-stu-id="e974d-114">Prerequisites</span></span>

<span data-ttu-id="e974d-115">需要将计算机设置为运行 .NET Core，包括 C# 8.0 beta 编译器。</span><span class="sxs-lookup"><span data-stu-id="e974d-115">You'll need to set up your machine to run .NET Core, including the C# 8.0 beta compiler.</span></span> <span data-ttu-id="e974d-116">C# 8 beta 编译器可用于 [Visual Studio 2019 预览版 2](https://visualstudio.microsoft.com/vs/preview/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019+preview) 或 [.NET Core 3.0 预览版 2](https://dotnet.microsoft.com/download/dotnet-core/3.0)。</span><span class="sxs-lookup"><span data-stu-id="e974d-116">The C# 8 beta compiler is available with [Visual Studio 2019 preview 2](https://visualstudio.microsoft.com/vs/preview/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019+preview), or [.NET Core 3.0 preview 2](https://dotnet.microsoft.com/download/dotnet-core/3.0).</span></span>

<span data-ttu-id="e974d-117">本教程假设你熟悉 C# 和 .NET，包括 Visual Studio 或 .NET Core CLI。</span><span class="sxs-lookup"><span data-stu-id="e974d-117">This tutorial assumes you're familiar with C# and .NET, including either Visual Studio or the .NET Core CLI.</span></span>

## <a name="incorporate-nullable-reference-types-into-your-designs"></a><span data-ttu-id="e974d-118">将可为空引用类型合并到你的设计中</span><span class="sxs-lookup"><span data-stu-id="e974d-118">Incorporate nullable reference types into your designs</span></span>

<span data-ttu-id="e974d-119">在本教程中，你将构建一个模拟运行调查的库。</span><span class="sxs-lookup"><span data-stu-id="e974d-119">In this tutorial, you'll build a library that models running a survey.</span></span> <span data-ttu-id="e974d-120">该代码使用可为空引用类型和不可为可空引用类型来表示实际概念。</span><span class="sxs-lookup"><span data-stu-id="e974d-120">The code uses both nullable reference types and non-nullable reference types to represent the real-world concepts.</span></span> <span data-ttu-id="e974d-121">调查问题决不会为 NULL。</span><span class="sxs-lookup"><span data-stu-id="e974d-121">The survey questions can never be null.</span></span> <span data-ttu-id="e974d-122">回应者可能不愿回答某个问题。</span><span class="sxs-lookup"><span data-stu-id="e974d-122">A respondent might prefer not to answer a question.</span></span> <span data-ttu-id="e974d-123">在这种情况下响应可能为 NULL。</span><span class="sxs-lookup"><span data-stu-id="e974d-123">The responses might be null in this case.</span></span>

<span data-ttu-id="e974d-124">你为此示例编写的代码表示该意向，并且编译器强制执行该意向。</span><span class="sxs-lookup"><span data-stu-id="e974d-124">The code you'll write for this sample expresses that intent, and the compiler enforces that intent.</span></span>

## <a name="create-the-application-and-enable-nullable-reference-types"></a><span data-ttu-id="e974d-125">创建应用程序并启用可为空引用类型</span><span class="sxs-lookup"><span data-stu-id="e974d-125">Create the application and enable nullable reference types</span></span>

<span data-ttu-id="e974d-126">在 Visual Studio 中或使用 `dotnet new console` 从命令行创建新的控制台应用程序。</span><span class="sxs-lookup"><span data-stu-id="e974d-126">Create a new console application either in Visual Studio or from the command line using `dotnet new console`.</span></span> <span data-ttu-id="e974d-127">命名应用程序 `NullableIntroduction`。</span><span class="sxs-lookup"><span data-stu-id="e974d-127">Name the application `NullableIntroduction`.</span></span> <span data-ttu-id="e974d-128">创建应用程序后，你需要启用 C# 8 beta 功能。</span><span class="sxs-lookup"><span data-stu-id="e974d-128">Once you've created the application, you'll need to enable C# 8 beta features.</span></span> <span data-ttu-id="e974d-129">打开 `csproj` 文件，并向 `PropertyGroup` 元素添加 `LangVersion` 元素。</span><span class="sxs-lookup"><span data-stu-id="e974d-129">Open the `csproj` file and add a `LangVersion` element to the `PropertyGroup` element.</span></span> <span data-ttu-id="e974d-130">必须选择“可为空引用类型”功能，即使在 C# 8 项目中也是如此。</span><span class="sxs-lookup"><span data-stu-id="e974d-130">You must opt into the **nullable reference types** feature, even in C# 8 projects.</span></span> <span data-ttu-id="e974d-131">这是因为，一旦启用该功能，现有的引用变量声明将成为不可为空引用类型。</span><span class="sxs-lookup"><span data-stu-id="e974d-131">That's because once the feature is turned on, existing reference variable declarations become **non-nullable reference types**.</span></span> <span data-ttu-id="e974d-132">虽然该决定将有助于发现现有代码可能不具有适当的 NULL 检查的问题，但它可能无法准确反映你的原始设计意图。</span><span class="sxs-lookup"><span data-stu-id="e974d-132">While that decision will help find issues where existing code may not have proper null-checks, it may not accurately reflect your original design intent.</span></span> <span data-ttu-id="e974d-133">可以通过将 `NullableContextOptions` 元素设置为 `enable` 来启用该功能：</span><span class="sxs-lookup"><span data-stu-id="e974d-133">You turn on the feature by setting the `NullableContextOptions` element to `enable`:</span></span>

```xml
<LangVersion>8.0</LangVersion>
<NullableContextOptions>enable</NullableContextOptions>
```

> [!NOTE]
> <span data-ttu-id="e974d-134">当 C# 8 发布时（不处于预览模式），新项目模板将添加 `NullableContextOptions` 元素。</span><span class="sxs-lookup"><span data-stu-id="e974d-134">When C# 8 is released (not in preview mode), the `NullableContextOptions` element will be added by new project templates.</span></span> <span data-ttu-id="e974d-135">在此之前，需要手动添加它。</span><span class="sxs-lookup"><span data-stu-id="e974d-135">Until then, you'll need to add it manually.</span></span>


### <a name="design-the-types-for-the-application"></a><span data-ttu-id="e974d-136">设计应用程序的类型</span><span class="sxs-lookup"><span data-stu-id="e974d-136">Design the types for the application</span></span>

<span data-ttu-id="e974d-137">此调查应用程序需要创建许多类：</span><span class="sxs-lookup"><span data-stu-id="e974d-137">This survey application requires creating a number of classes:</span></span>

- <span data-ttu-id="e974d-138">建模问题列表的类。</span><span class="sxs-lookup"><span data-stu-id="e974d-138">A class that models the list of questions.</span></span>
- <span data-ttu-id="e974d-139">建模为调查所联系的人员列表的类。</span><span class="sxs-lookup"><span data-stu-id="e974d-139">A class that models a list of people contacted for the survey.</span></span>
- <span data-ttu-id="e974d-140">建模来自参加调查人员的答案的类。</span><span class="sxs-lookup"><span data-stu-id="e974d-140">A class that models the answers from a person that took the survey.</span></span>

<span data-ttu-id="e974d-141">这些类型将使用可为空和不可为空引用类型来表示哪些成员是必需的，哪些成员是可选的。</span><span class="sxs-lookup"><span data-stu-id="e974d-141">These types will make use of both nullable and non-nullable reference types to express which members are required and which members are optional.</span></span> <span data-ttu-id="e974d-142">可为空引用类型清楚地传达了设计意图：</span><span class="sxs-lookup"><span data-stu-id="e974d-142">Nullable reference types communicate that design intent clearly:</span></span>

- <span data-ttu-id="e974d-143">调查中的问题不可为 null：提出空问题没有任何意义。</span><span class="sxs-lookup"><span data-stu-id="e974d-143">The questions that are part of the survey can never be null: It makes no sense to ask an empty question.</span></span>
- <span data-ttu-id="e974d-144">回应者永远不能为 NULL。</span><span class="sxs-lookup"><span data-stu-id="e974d-144">The respondents can never be null.</span></span> <span data-ttu-id="e974d-145">你需要跟踪所联系的人员，即便回应者拒绝参与也是如此。</span><span class="sxs-lookup"><span data-stu-id="e974d-145">You'll want to track people you contacted, even respondents that declined to participate.</span></span>
- <span data-ttu-id="e974d-146">对某个问题的任何响应都可能为 NULL。</span><span class="sxs-lookup"><span data-stu-id="e974d-146">Any response to a question may be null.</span></span> <span data-ttu-id="e974d-147">回应者可拒绝回答部分或全部问题。</span><span class="sxs-lookup"><span data-stu-id="e974d-147">Respondents can decline to answer some or all questions.</span></span>

<span data-ttu-id="e974d-148">如果你使用 C# 编程，则可能已经习惯于允许 NULL 值的引用类型，但你可能错过了其他声明不可为空实例的机会：</span><span class="sxs-lookup"><span data-stu-id="e974d-148">If you've programmed in C#, you may be so accustomed to reference types that allow null values that you may have missed other opportunities to declare non-nullable instances:</span></span>

- <span data-ttu-id="e974d-149">问题集合应不可为空。</span><span class="sxs-lookup"><span data-stu-id="e974d-149">The collection of questions should be non-nullable.</span></span>
- <span data-ttu-id="e974d-150">回应者集合应不可为空。</span><span class="sxs-lookup"><span data-stu-id="e974d-150">The collection of respondents should be non-nullable.</span></span>

<span data-ttu-id="e974d-151">在编写代码时，你将看到不可为空引用类型作为引用的默认值，可避免可能导致空引用异常的常见错误。</span><span class="sxs-lookup"><span data-stu-id="e974d-151">As you write the code, you'll see that a non-nullable reference type as the default for references avoids common mistakes that could lead to null reference exceptions.</span></span> <span data-ttu-id="e974d-152">从本教程得出的一个经验就是，你应决定哪些变量可为 NULL 或不可为 NULL。</span><span class="sxs-lookup"><span data-stu-id="e974d-152">One lesson from this tutorial is that you made decisions about which variables could or could not be null.</span></span> <span data-ttu-id="e974d-153">该语言未提供表达这些决定的语法。</span><span class="sxs-lookup"><span data-stu-id="e974d-153">The language didn't provide syntax to express those decisions.</span></span> <span data-ttu-id="e974d-154">现在它可提供此项功能。</span><span class="sxs-lookup"><span data-stu-id="e974d-154">Now it does.</span></span>

<span data-ttu-id="e974d-155">你构建的应用程序将执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="e974d-155">The app you'll build will do the following steps:</span></span>

1. <span data-ttu-id="e974d-156">创建调查并向其添加问题。</span><span class="sxs-lookup"><span data-stu-id="e974d-156">Create a survey and add questions to it.</span></span>
1. <span data-ttu-id="e974d-157">为调查创建一组伪随机回应者。</span><span class="sxs-lookup"><span data-stu-id="e974d-157">Create a pseudo-random set of respondents for the survey.</span></span>
1. <span data-ttu-id="e974d-158">联系回应者，直到已完成的调查规模达到目标数量。</span><span class="sxs-lookup"><span data-stu-id="e974d-158">Contact respondents until the completed survey size reaches the goal number.</span></span>
1. <span data-ttu-id="e974d-159">写出有关调查响应的重要统计数据。</span><span class="sxs-lookup"><span data-stu-id="e974d-159">Write out important statistics on the survey responses.</span></span>

## <a name="build-the-survey-with-nullable-and-non-nullable-types"></a><span data-ttu-id="e974d-160">使用可为空和不可为空类型构建调查</span><span class="sxs-lookup"><span data-stu-id="e974d-160">Build the survey with nullable and non-nullable types</span></span>

<span data-ttu-id="e974d-161">你将编写的第一个代码创建调查。</span><span class="sxs-lookup"><span data-stu-id="e974d-161">The first code you'll write creates the survey.</span></span> <span data-ttu-id="e974d-162">你将编写类来为调查问题和调查运行建模。</span><span class="sxs-lookup"><span data-stu-id="e974d-162">You'll write classes to model a survey question and a survey run.</span></span> <span data-ttu-id="e974d-163">调查有三种类型的问题，通过答案格式进行区分：答案为“是”/“否”、答案为数字以及答案为文本。</span><span class="sxs-lookup"><span data-stu-id="e974d-163">Your survey has three types of questions, distinguished by the format of the answer: Yes/No answers, number answers, and text answers.</span></span> <span data-ttu-id="e974d-164">创建 `public` `SurveyQuestion` 类：</span><span class="sxs-lookup"><span data-stu-id="e974d-164">Create a `public` `SurveyQuestion` class:</span></span>

```csharp
namespace NullableIntroduction
{
    public class SurveyQuestion
    {
    }
}
```

<span data-ttu-id="e974d-165">编译器将启用可为空的上下文中的代码的每个引用类型变量声明解释为不可为空引用类型。</span><span class="sxs-lookup"><span data-stu-id="e974d-165">The compiler interprets every reference type variable declaration as a **non-nullable** reference type for code in a nullable enabled context.</span></span> <span data-ttu-id="e974d-166">你可以通过添加问题文本的属性和问题类型来查看第一个警告，如以下代码所示：</span><span class="sxs-lookup"><span data-stu-id="e974d-166">You can see your first warning by adding properties for the question text and the type of question, as shown in the following code:</span></span>

```csharp
namespace NullableIntroduction
{
    public enum QuestionType
    {
        YesNo,
        Number,
        Text
    }

    public class SurveyQuestion
    {
        public string QuestionText { get; }
        public QuestionType TypeOfQuestion { get; }
    }
}
```

<span data-ttu-id="e974d-167">因为尚未初始化 `QuestionText`，所以编译器会发出警告，指出尚未初始化不可为空属性。</span><span class="sxs-lookup"><span data-stu-id="e974d-167">Because you haven't initialized `QuestionText`, the compiler issues a warning that a non-nullable property hasn't been initialized.</span></span> <span data-ttu-id="e974d-168">设计要求问题文本为非空，因此需要添加构造函数来初始化它以及 `QuestionType` 值。</span><span class="sxs-lookup"><span data-stu-id="e974d-168">Your design requires the question text to be non-null, so you add a constructor to initialize it and the `QuestionType` value as well.</span></span> <span data-ttu-id="e974d-169">已完成类定义类似于以下代码：</span><span class="sxs-lookup"><span data-stu-id="e974d-169">The finished class definition looks like the following code:</span></span>

[!code-csharp[DefineQuestion](../../../samples/csharp/NullableIntroduction/NullableIntroduction/SurveyQuestion.cs)]

<span data-ttu-id="e974d-170">添加构造函数会删除警告。</span><span class="sxs-lookup"><span data-stu-id="e974d-170">Adding the constructor removes the warning.</span></span> <span data-ttu-id="e974d-171">构造函数参数也是不可为空引用类型，因此编译器不会发出任何警告。</span><span class="sxs-lookup"><span data-stu-id="e974d-171">The constructor argument is also a non-nullable reference type, so the compiler doesn't issue any warnings.</span></span>

<span data-ttu-id="e974d-172">接下来，创建一个名为 `SurveyRun` 的 `public` 类。</span><span class="sxs-lookup"><span data-stu-id="e974d-172">Next, create a `public` class named `SurveyRun`.</span></span> <span data-ttu-id="e974d-173">此类包含 `SurveyQuestion` 对象的列表以及向调查添加问题的方法，如以下代码所示：</span><span class="sxs-lookup"><span data-stu-id="e974d-173">This class contains a list of `SurveyQuestion` objects and methods to add questions to the survey, as shown in the following code:</span></span>

```csharp
using System.Collections.Generic;

namespace NullableIntroduction
{
    public class SurveyRun
    {
        private List<SurveyQuestion> surveyQuestions = new List<SurveyQuestion>();

        public void AddQuestion(QuestionType type, string question) =>
            AddQuestion(new SurveyQuestion(type, question));
        public void AddQuestion(SurveyQuestion surveyQuestion) => surveyQuestions.Add(surveyQuestion);
    }
}
```

<span data-ttu-id="e974d-174">和以前一样，你必须将列表对象初始化为非空值，否则编译器会发出警告。</span><span class="sxs-lookup"><span data-stu-id="e974d-174">As before, you must initialize the list object to a non-null value or the compiler issues a warning.</span></span> <span data-ttu-id="e974d-175">在 `AddQuestion` 的第二次重载中没有 NULL 检查，因为不需要进行二次检查：已声明该变量不可为空。</span><span class="sxs-lookup"><span data-stu-id="e974d-175">There are no null checks in the second overload of `AddQuestion` because they aren't needed: You've declared that variable to be non-nullable.</span></span> <span data-ttu-id="e974d-176">其值不可为 `null`。</span><span class="sxs-lookup"><span data-stu-id="e974d-176">Its value can't be `null`.</span></span>

<span data-ttu-id="e974d-177">切换到编辑器中的 `Program.cs`，并使用以下代码行替换 `Main` 的内容：</span><span class="sxs-lookup"><span data-stu-id="e974d-177">Switch to `Program.cs` in your editor and replace the contents of `Main` with the following lines of code:</span></span>

[!code-csharp[AddQuestions](../../../samples/csharp/NullableIntroduction/NullableIntroduction/Program.cs#AddQuestions)]

<span data-ttu-id="e974d-178">由于整个项目处于启用可为空的上下文中，因此将 `null` 传递给任何应为不可为空引用类型的方法时，将收到警告。</span><span class="sxs-lookup"><span data-stu-id="e974d-178">Because the entire project is in a nullable enabled context, you'll get warnings when you pass `null` to any method expecting a non-nullable reference type.</span></span> <span data-ttu-id="e974d-179">通过将以下行添加到 `Main` 进行尝试：</span><span class="sxs-lookup"><span data-stu-id="e974d-179">Try it by adding the following line to `Main`:</span></span>

```csharp
surveyRun.AddQuestion(QuestionType.Text, default);
```

## <a name="create-respondents-and-get-answers-to-the-survey"></a><span data-ttu-id="e974d-180">创建回应者并获取调查答案</span><span class="sxs-lookup"><span data-stu-id="e974d-180">Create respondents and get answers to the survey</span></span>

<span data-ttu-id="e974d-181">接下来，编写生成调查答案的代码。</span><span class="sxs-lookup"><span data-stu-id="e974d-181">Next, write the code that generates answers to the survey.</span></span> <span data-ttu-id="e974d-182">此过程涉及到多个小型任务：</span><span class="sxs-lookup"><span data-stu-id="e974d-182">This process involves several small tasks:</span></span>

1. <span data-ttu-id="e974d-183">构建一个生成回应者对象的方法。</span><span class="sxs-lookup"><span data-stu-id="e974d-183">Build a method that generates respondent objects.</span></span> <span data-ttu-id="e974d-184">这些对象表示要求填写调查的人员。</span><span class="sxs-lookup"><span data-stu-id="e974d-184">These represent people asked to fill out the survey.</span></span>
1. <span data-ttu-id="e974d-185">生成逻辑以模拟向回应者询问问题并收集答案，或者注意到回应者没有回答。</span><span class="sxs-lookup"><span data-stu-id="e974d-185">Build logic to simulate asking the questions to a respondent and collecting answers or noting that a respondent didn't answer.</span></span>
1. <span data-ttu-id="e974d-186">重复以上过程，直到有足够的回应者回答此调查。</span><span class="sxs-lookup"><span data-stu-id="e974d-186">Repeat until enough respondents have answered the survey.</span></span>

<span data-ttu-id="e974d-187">你需要一个表示调查响应的类，所以现在就添加它。</span><span class="sxs-lookup"><span data-stu-id="e974d-187">You'll need a class to represent a survey response, so add that now.</span></span> <span data-ttu-id="e974d-188">启用可为空支持。</span><span class="sxs-lookup"><span data-stu-id="e974d-188">Enable nullable support.</span></span> <span data-ttu-id="e974d-189">添加初始化它的 `Id` 属性和构造函数，如以下代码所示：</span><span class="sxs-lookup"><span data-stu-id="e974d-189">Add an `Id` property and a constructor that initializes it, as shown in the following code:</span></span>

```csharp
namespace NullableIntroduction
{
    public class SurveyResponse
    {
        public int Id { get; }

        public SurveyResponse(int id) => Id = id;
    }
}
```

<span data-ttu-id="e974d-190">接下来，通过生成随机 ID 添加 `static` 方法来创建新参与者：</span><span class="sxs-lookup"><span data-stu-id="e974d-190">Next, add a `static` method to create new participants by generating a random ID:</span></span>

[!code-csharp[GenerateRespondents](../../../samples/csharp/NullableIntroduction/NullableIntroduction/SurveyResponse.cs#Random)]

<span data-ttu-id="e974d-191">该类的主要职责是为调查中问题的参与者生成问题答案。</span><span class="sxs-lookup"><span data-stu-id="e974d-191">The main responsibility of this class is to generate the responses for a participant to the questions in the survey.</span></span> <span data-ttu-id="e974d-192">实现此职责有几个步骤：</span><span class="sxs-lookup"><span data-stu-id="e974d-192">This responsibility has a few steps:</span></span>

1. <span data-ttu-id="e974d-193">要求参加这项调查。</span><span class="sxs-lookup"><span data-stu-id="e974d-193">Ask for participation in the survey.</span></span> <span data-ttu-id="e974d-194">如果此人不同意，则返回缺失（或 NULL）响应。</span><span class="sxs-lookup"><span data-stu-id="e974d-194">If the person doesn't consent, return a missing (or null) response.</span></span>
1. <span data-ttu-id="e974d-195">询问每个问题并记录答案。</span><span class="sxs-lookup"><span data-stu-id="e974d-195">Ask each question and record the answer.</span></span> <span data-ttu-id="e974d-196">每个答案也可能会缺失（或 NULL）。</span><span class="sxs-lookup"><span data-stu-id="e974d-196">Each answer may also be missing (or null).</span></span>

<span data-ttu-id="e974d-197">将以下代码添加到 `SurveyResponse` 类：</span><span class="sxs-lookup"><span data-stu-id="e974d-197">Add the following code to your `SurveyResponse` class:</span></span>

[!code-csharp[AnswerSurvey](../../../samples/csharp/NullableIntroduction/NullableIntroduction/SurveyResponse.cs#AnswerSurvey)]

<span data-ttu-id="e974d-198">调查答案的存储空间为 `Dictionary<int, string>?`，表示它可能为 NULL。</span><span class="sxs-lookup"><span data-stu-id="e974d-198">The storage for the survey answers is a `Dictionary<int, string>?`, indicating that it may be null.</span></span> <span data-ttu-id="e974d-199">你正在使用新的语言功能向编译器和稍后阅读你的代码的任何人声明你的设计意图。</span><span class="sxs-lookup"><span data-stu-id="e974d-199">You're using the new language feature to declare your design intent, both to the compiler and to anyone reading your code later.</span></span> <span data-ttu-id="e974d-200">如果在首先不检查是否为 NULL 值的情况下取消引用 `surveyResponses`，则会收到编译器警告。</span><span class="sxs-lookup"><span data-stu-id="e974d-200">If you ever dereference `surveyResponses` without checking for the null value first, you'll get a compiler warning.</span></span> <span data-ttu-id="e974d-201">你没有在 `AnswerSurvey` 方法中收到警告，因为编译器可以确定 `surveyResponses` 变量已设置为上述非空值。</span><span class="sxs-lookup"><span data-stu-id="e974d-201">You don't get a warning in the `AnswerSurvey` method because the compiler can determine the `surveyResponses` variable was set to a non-null value above.</span></span>

<span data-ttu-id="e974d-202">对缺少的答案使用 `null` 强调了处理可为空引用类型的一个关键点：目标不是从程序中删除所有 `null` 值。</span><span class="sxs-lookup"><span data-stu-id="e974d-202">Using `null` for missing answers highlights a key point for working with nullable reference types: your goal isn't to remove all `null` values from your program.</span></span> <span data-ttu-id="e974d-203">而是确保编写的代码表达设计意图。</span><span class="sxs-lookup"><span data-stu-id="e974d-203">Rather, your goal is to ensure that the code you write expresses the intent of your design.</span></span> <span data-ttu-id="e974d-204">缺失值是在代码中进行表达的一个必需概念。</span><span class="sxs-lookup"><span data-stu-id="e974d-204">Missing values are a necessary concept to express in your code.</span></span> <span data-ttu-id="e974d-205">`null` 值是表示这些缺失值的一种明确方法。</span><span class="sxs-lookup"><span data-stu-id="e974d-205">The `null` value is a clear way to express those missing values.</span></span> <span data-ttu-id="e974d-206">尝试删除所有 `null` 值只会导致定义一些其他方法来在没有 `null` 的情况下表示缺失值。</span><span class="sxs-lookup"><span data-stu-id="e974d-206">Trying to remove all `null` values only leads to defining some other way to express those missing values without `null`.</span></span>

<span data-ttu-id="e974d-207">接下来，你需要在 `SurveyRun` 类中编写 `PerformSurvey` 方法。</span><span class="sxs-lookup"><span data-stu-id="e974d-207">Next, you need to write the `PerformSurvey` method in the `SurveyRun` class.</span></span> <span data-ttu-id="e974d-208">将下面的代码添加到 `SurveyRun` 类中：</span><span class="sxs-lookup"><span data-stu-id="e974d-208">Add the following code in the `SurveyRun` class:</span></span>

[!code-csharp[PerformSurvey](../../../samples/csharp/NullableIntroduction/NullableIntroduction/SurveyRun.cs#PerformSurvey)]

<span data-ttu-id="e974d-209">同样，你选择的可为空 `List<SurveyResponse>?` 指示响应可能为 NULL。</span><span class="sxs-lookup"><span data-stu-id="e974d-209">Here again, your choice of a nullable `List<SurveyResponse>?` indicates the response may be null.</span></span> <span data-ttu-id="e974d-210">这表明尚未向任何回应者提供调查。</span><span class="sxs-lookup"><span data-stu-id="e974d-210">That indicates the survey hasn't been given to any respondents yet.</span></span> <span data-ttu-id="e974d-211">请注意，在同意参与调查的回应者未达到足够数量之前，不会添加回应者。</span><span class="sxs-lookup"><span data-stu-id="e974d-211">Notice that respondents are added until enough have consented.</span></span>

<span data-ttu-id="e974d-212">运行调查的最后一步是添加一个调用，从而可在 `Main` 方法结束时执行此调查：</span><span class="sxs-lookup"><span data-stu-id="e974d-212">The last step to run the survey is to add a call to perform the survey at the end of the `Main` method:</span></span>

[!code-csharp[RunSurvey](../../../samples/csharp/NullableIntroduction/NullableIntroduction/Program.cs#RunSurvey)]

## <a name="examine-survey-responses"></a><span data-ttu-id="e974d-213">检查调查响应</span><span class="sxs-lookup"><span data-stu-id="e974d-213">Examine survey responses</span></span>

<span data-ttu-id="e974d-214">最后一步是显示调查结果。</span><span class="sxs-lookup"><span data-stu-id="e974d-214">The last step is to display survey results.</span></span> <span data-ttu-id="e974d-215">将代码添加到你所编写的诸多类。</span><span class="sxs-lookup"><span data-stu-id="e974d-215">You'll add code to many of the classes you've written.</span></span> <span data-ttu-id="e974d-216">此代码演示了区分可为空和不可为空引用类型的值。</span><span class="sxs-lookup"><span data-stu-id="e974d-216">This code demonstrates the value of distinguishing nullable and non-nullable reference types.</span></span> <span data-ttu-id="e974d-217">首先将以下两个表达式形式成员添加到 `SurveyResponse` 类：</span><span class="sxs-lookup"><span data-stu-id="e974d-217">Start by adding the following two expression-bodied members to the `SurveyResponse` class:</span></span>

[!code-csharp[ReportResponses](../../../samples/csharp/NullableIntroduction/NullableIntroduction/SurveyResponse.cs#SurveyStatus)]

<span data-ttu-id="e974d-218">因为 `surveyResponses` 是一个不可为空引用，所以在取消引用之前不需要输入任何检查。</span><span class="sxs-lookup"><span data-stu-id="e974d-218">Because `surveyResponses` is a non-nullable reference type, no checks are necessary before de-referencing it.</span></span> <span data-ttu-id="e974d-219">`Answer` 方法返回一个不可为空字符串，因此选择 `GetValueOrDefault` 的重载，它采用默认值的第二个参数。</span><span class="sxs-lookup"><span data-stu-id="e974d-219">The `Answer` method returns a non-nullable string, so choose the overload of `GetValueOrDefault` that takes a second argument for the default value.</span></span>

<span data-ttu-id="e974d-220">接下来，将这三个表达式形式成员添加到 `SurveyRun` 类：</span><span class="sxs-lookup"><span data-stu-id="e974d-220">Next, add these three expression-bodied members to the `SurveyRun` class:</span></span>

[!code-csharp[ReportResults](../../../samples/csharp/NullableIntroduction/NullableIntroduction/SurveyRun.cs#RunReport)]

<span data-ttu-id="e974d-221">`AllParticipants` 成员必须考虑 `respondents` 变量可能为 NULL 但返回值不能为 NULL 的情况。</span><span class="sxs-lookup"><span data-stu-id="e974d-221">The `AllParticipants` member must take into account that the `respondents` variable might be null, but the return value can't be null.</span></span> <span data-ttu-id="e974d-222">如果通过删除后面的 `??` 和空序列来更改该表达式，则编译器会警告你方法可能返回 `null` 并且其返回签名返回不可为空类型。</span><span class="sxs-lookup"><span data-stu-id="e974d-222">If you change that expression by removing the `??` and the empty sequence that follows, the compiler warns you the method might return `null` and its return signature returns a non-nullable type.</span></span>

<span data-ttu-id="e974d-223">最后，在 `Main` 方法的底部添加以下循环：</span><span class="sxs-lookup"><span data-stu-id="e974d-223">Finally, add the following loop at the bottom of the `Main` method:</span></span>

[!code-csharp[DisplaySurveyResults](../../../samples/csharp/NullableIntroduction/NullableIntroduction/Program.cs#WriteAnswers)]

<span data-ttu-id="e974d-224">你不需要在此代码中执行任何 `null` 检查，因为你已设计了基础接口，这样它们均返回不可为空引用类型。</span><span class="sxs-lookup"><span data-stu-id="e974d-224">You don't need any `null` checks in this code because you've designed the underlying interfaces so that they all return non-nullable reference types.</span></span>

## <a name="get-the-code"></a><span data-ttu-id="e974d-225">获取代码</span><span class="sxs-lookup"><span data-stu-id="e974d-225">Get the code</span></span>

<span data-ttu-id="e974d-226">你可以从 [csharp/NullableIntroduction](https://github.com/dotnet/samples/tree/master/csharp/NullableIntroduction) 文件夹中的[示例](https://github.com/dotnet/samples)存储库获取已完成教程的代码。</span><span class="sxs-lookup"><span data-stu-id="e974d-226">You can get the code for the finished tutorial from our [samples](https://github.com/dotnet/samples) repository in the [csharp/NullableIntroduction](https://github.com/dotnet/samples/tree/master/csharp/NullableIntroduction) folder.</span></span>

<span data-ttu-id="e974d-227">通过更改可为空和不可为空引用类型之间的类型声明进行试验。</span><span class="sxs-lookup"><span data-stu-id="e974d-227">Experiment by changing the type declarations between nullable and non-nullable reference types.</span></span> <span data-ttu-id="e974d-228">了解如何生成不同的警告以确保不会意外取消引用 `null`。</span><span class="sxs-lookup"><span data-stu-id="e974d-228">See how that generates different warnings to ensure you don't accidentally dereference a `null`.</span></span>

## <a name="next-steps"></a><span data-ttu-id="e974d-229">后续步骤</span><span class="sxs-lookup"><span data-stu-id="e974d-229">Next steps</span></span>

<span data-ttu-id="e974d-230">要了解更多信息，请迁移现有应用程序以使用可为空引用类型：</span><span class="sxs-lookup"><span data-stu-id="e974d-230">Learn more by migrating an existing application to use nullable reference types:</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="e974d-231">升级应用程序以使用可为空引用类型</span><span class="sxs-lookup"><span data-stu-id="e974d-231">Upgrade an application to use nullable reference types</span></span>](upgrade-to-nullable-references.md)
