---
title: C# 表达式
ms.date: 03/30/2017
ms.assetid: 29110be7-f4e3-407e-8dbe-78102eb21115
ms.openlocfilehash: d1728758a4f1af76c2d08695a83c0f9acc3dde3e
ms.sourcegitcommit: fbb8a593a511ce667992502a3ce6d8f65c594edf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/16/2019
ms.locfileid: "74140095"
---
# <a name="c-expressions"></a><span data-ttu-id="84d99-102">C# 表达式</span><span class="sxs-lookup"><span data-stu-id="84d99-102">C# Expressions</span></span>
<span data-ttu-id="84d99-103">从 .NET Framework 4.5 开始， C# WINDOWS WORKFLOW FOUNDATION （WF）中支持表达式。</span><span class="sxs-lookup"><span data-stu-id="84d99-103">Starting with .NET Framework 4.5, C# expressions are supported in Windows Workflow Foundation (WF).</span></span> <span data-ttu-id="84d99-104">在C# Visual Studio 2012 中创建的新工作流项目以 .NET Framework C# 4.5 使用表达式，Visual Basic 工作流项目使用 Visual Basic 表达式。</span><span class="sxs-lookup"><span data-stu-id="84d99-104">New C# workflow projects created in Visual Studio 2012 that target .NET Framework 4.5 use C# expressions, and Visual Basic workflow projects use Visual Basic expressions.</span></span> <span data-ttu-id="84d99-105">使用 Visual Basic 表达式的现有 .NET Framework 4 工作流项目可迁移到 [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)]，而不考虑项目语言和受支持。</span><span class="sxs-lookup"><span data-stu-id="84d99-105">Existing .NET Framework 4 workflow projects that use Visual Basic expressions can be migrated to [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] regardless of the project language and are supported.</span></span> <span data-ttu-id="84d99-106">本主题概述了 [!INCLUDE[wf1](../../../includes/wf1-md.md)] 中的 C# 表达式。</span><span class="sxs-lookup"><span data-stu-id="84d99-106">This topic provides an overview of C# expressions in [!INCLUDE[wf1](../../../includes/wf1-md.md)].</span></span>

## <a name="using-c-expressions-in-workflows"></a><span data-ttu-id="84d99-107">在工作流中使用 C# 表达式</span><span class="sxs-lookup"><span data-stu-id="84d99-107">Using C# expressions in workflows</span></span>

- [<span data-ttu-id="84d99-108">在C#工作流设计器中使用表达式</span><span class="sxs-lookup"><span data-stu-id="84d99-108">Using C# expressions in the Workflow Designer</span></span>](csharp-expressions.md#WFDesigner)

  - [<span data-ttu-id="84d99-109">向后兼容性</span><span class="sxs-lookup"><span data-stu-id="84d99-109">Backwards compatibility</span></span>](csharp-expressions.md#BackwardCompat)

- [<span data-ttu-id="84d99-110">在C#代码工作流中使用表达式</span><span class="sxs-lookup"><span data-stu-id="84d99-110">Using C# expressions in code workflows</span></span>](csharp-expressions.md#CodeWorkflows)

- [<span data-ttu-id="84d99-111">在C# XAML 工作流中使用表达式</span><span class="sxs-lookup"><span data-stu-id="84d99-111">Using C# expressions in XAML workflows</span></span>](csharp-expressions.md#XamlWorkflows)

  - [<span data-ttu-id="84d99-112">已编译 Xaml</span><span class="sxs-lookup"><span data-stu-id="84d99-112">Compiled Xaml</span></span>](csharp-expressions.md#CompiledXaml)

  - [<span data-ttu-id="84d99-113">松散 Xaml</span><span class="sxs-lookup"><span data-stu-id="84d99-113">Loose Xaml</span></span>](csharp-expressions.md#LooseXaml)

- [<span data-ttu-id="84d99-114">在C# .xamlx 工作流服务中使用表达式</span><span class="sxs-lookup"><span data-stu-id="84d99-114">Using C# expressions in XAMLX workflow services</span></span>](csharp-expressions.md#WFServices)

### <a name="WFDesigner"></a><span data-ttu-id="84d99-115">在C#工作流设计器中使用表达式</span><span class="sxs-lookup"><span data-stu-id="84d99-115">Using C# expressions in the Workflow Designer</span></span>

<span data-ttu-id="84d99-116">从 .NET Framework 4.5 开始， C# WINDOWS WORKFLOW FOUNDATION （WF）中支持表达式。</span><span class="sxs-lookup"><span data-stu-id="84d99-116">Starting with .NET Framework 4.5, C# expressions are supported in Windows Workflow Foundation (WF).</span></span> <span data-ttu-id="84d99-117">C#在 Visual Studio 2012 中创建的、以 .NET Framework 4.5 为C#目标的工作流项目使用表达式，而 Visual Basic 工作流项目使用 Visual Basic 表达式。</span><span class="sxs-lookup"><span data-stu-id="84d99-117">C# workflow projects created in Visual Studio 2012 that target .NET Framework 4.5 use C# expressions, while Visual Basic workflow projects use Visual Basic expressions.</span></span> <span data-ttu-id="84d99-118">若要指定所C#需的表达式，请在标有 "**输入C#表达式**" 的框中键入。</span><span class="sxs-lookup"><span data-stu-id="84d99-118">To specify the desired C# expression, type it into the box labeled **Enter a C# expression**.</span></span> <span data-ttu-id="84d99-119">该标签显示在属性窗口中（当在设计器中选中活动时），或显示在工作流设计器的活动上。</span><span class="sxs-lookup"><span data-stu-id="84d99-119">This label is displayed in the properties window when the activity is selected in the designer, or on the activity in the workflow designer.</span></span> <span data-ttu-id="84d99-120">下例中，在 `WriteLine` 范围内，一个 `Sequence` 中包含了两个 `NoPersistScope` 活动。</span><span class="sxs-lookup"><span data-stu-id="84d99-120">In the following example, two `WriteLine` activities are contained within a `Sequence` inside a `NoPersistScope`.</span></span>

![显示自动创建的序列活动的屏幕截图。](./media/csharp-expressions/auto-surround-sequence-activity.png)

> [!NOTE]
> <span data-ttu-id="84d99-122">C#表达式仅在 Visual Studio 中受支持，并且在重新托管的工作流设计器中不受支持。</span><span class="sxs-lookup"><span data-stu-id="84d99-122">C# expressions are supported only in Visual Studio, and are not supported in the re-hosted workflow designer.</span></span> <span data-ttu-id="84d99-123">有关重新托管的设计器中支持的新 WF45 功能的详细信息，请参阅[重新承载工作流设计器中对新 Workflow Foundation 4.5 功能的支持](wf-features-in-the-rehosted-workflow-designer.md)。</span><span class="sxs-lookup"><span data-stu-id="84d99-123">For more information about new WF45 features supported in the re-hosted designer, see [Support for New Workflow Foundation 4.5 Features in the Rehosted Workflow Designer](wf-features-in-the-rehosted-workflow-designer.md).</span></span>

#### <a name="BackwardCompat"></a><span data-ttu-id="84d99-124">向后兼容性</span><span class="sxs-lookup"><span data-stu-id="84d99-124">Backwards compatibility</span></span>

<span data-ttu-id="84d99-125">支持已迁移到 [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] Visual Basic C#现有 .NET Framework 4 工作流项目中的表达式。</span><span class="sxs-lookup"><span data-stu-id="84d99-125">Visual Basic expressions in existing .NET Framework 4 C# workflow projects that have been migrated to [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] are supported.</span></span> <span data-ttu-id="84d99-126">当在工作流设计器中查看 Visual Basic 表达式时，除非 Visual Basic 表达式是有效C#的语法，否则现有 Visual Basic 表达式的文本将替换为**在 XAML 中设置的值**。</span><span class="sxs-lookup"><span data-stu-id="84d99-126">When the Visual Basic expressions are viewed in the workflow designer, the text of the existing Visual Basic expression is replaced with **Value was set in XAML**, unless the Visual Basic expression is valid C# syntax.</span></span> <span data-ttu-id="84d99-127">如果 Visual Basic 表达式符合 C# 语法则予以显示。</span><span class="sxs-lookup"><span data-stu-id="84d99-127">If the Visual Basic expression is valid C# syntax, then the expression is displayed.</span></span> <span data-ttu-id="84d99-128">若要将 Visual Basic 表达式更新为 C#，可在工作流设计器中编辑这些表达式，指定等效的 C# 表达式。</span><span class="sxs-lookup"><span data-stu-id="84d99-128">To update the Visual Basic expressions to C#, you can edit them in the workflow designer and specify the equivalent C# expression.</span></span> <span data-ttu-id="84d99-129">将 Visual Basic 表达式更新为 C# 不是必须的，但一旦在工作流设计器中进行更新，这些表达式即转换成 C# 并不可重新转换为 Visual Basic。</span><span class="sxs-lookup"><span data-stu-id="84d99-129">It is not required to update the Visual Basic expressions to C#, but once the expressions are updated in the workflow designer they are converted to C# and may not be reverted to Visual Basic.</span></span>

### <a name="CodeWorkflows"></a><span data-ttu-id="84d99-130">在C#代码工作流中使用表达式</span><span class="sxs-lookup"><span data-stu-id="84d99-130">Using C# expressions in code workflows</span></span>

<span data-ttu-id="84d99-131">基于 [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] 代码的工作流支持 C# 表达式，但 C# 表达式须用 <xref:System.Activities.XamlIntegration.TextExpressionCompiler.Compile%2A?displayProperty=nameWithType> 进行编译，然后才能调用工作流。</span><span class="sxs-lookup"><span data-stu-id="84d99-131">C# expressions are supported in [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] code based workflows, but before the workflow can be invoked the C# expressions must be compiled using <xref:System.Activities.XamlIntegration.TextExpressionCompiler.Compile%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="84d99-132">工作流作者可以用 `CSharpValue` 表示表达式的右值，用 `CSharpReference` 表示表达式的左值。</span><span class="sxs-lookup"><span data-stu-id="84d99-132">Workflow authors can use `CSharpValue` to represent the r-value of an expression, and `CSharpReference` to represent the l-value of an expression.</span></span> <span data-ttu-id="84d99-133">在下例中，用一个 `Assign` 活动以及 `WriteLine` 活动中所包含的 `Sequence` 活动创建了一个工作流。</span><span class="sxs-lookup"><span data-stu-id="84d99-133">In the following example, a workflow is created with an `Assign` activity and a `WriteLine` activity contained in a `Sequence` activity.</span></span> <span data-ttu-id="84d99-134">为 `CSharpReference` 的 `To` 自变量指定了一个 `Assign`，用来表示表达式的左值。</span><span class="sxs-lookup"><span data-stu-id="84d99-134">A `CSharpReference` is specified for the `To` argument of the `Assign`, and represents the l-value of the expression.</span></span> <span data-ttu-id="84d99-135">为 `CSharpValue` 的 `Value` 自变量和 `Assign` 的 `Text` 自变量指定了一个 `WriteLine`，用于表示这两个表达式的右值。</span><span class="sxs-lookup"><span data-stu-id="84d99-135">A `CSharpValue` is specified for the `Value` argument of the `Assign`, and for the `Text` argument of the `WriteLine`, and represents the r-value for those two expressions.</span></span>

```csharp
Variable<int> n = new Variable<int>
{
    Name = "n"
};

Activity wf = new Sequence
{
    Variables = { n },
    Activities =
    {
        new Assign<int>
        {
            To = new CSharpReference<int>("n"),
            Value = new CSharpValue<int>("new Random().Next(1, 101)")
        },
        new WriteLine
        {
            Text = new CSharpValue<string>("\"The number is \" + n")
        }
    }
};

CompileExpressions(wf);

WorkflowInvoker.Invoke(wf);
```

<span data-ttu-id="84d99-136">工作流构造完毕后，通过调用 `CompileExpressions` 帮助器方法编译了 C# 表达式，随后调用工作流。</span><span class="sxs-lookup"><span data-stu-id="84d99-136">After the workflow is constructed, the C# expressions are compiled by calling the `CompileExpressions` helper method and then the workflow is invoked.</span></span> <span data-ttu-id="84d99-137">下面的示例为 `CompileExpressions` 方法。</span><span class="sxs-lookup"><span data-stu-id="84d99-137">The following example is the `CompileExpressions` method.</span></span>

```csharp
static void CompileExpressions(Activity activity)
{
    // activityName is the Namespace.Type of the activity that contains the
    // C# expressions.
    string activityName = activity.GetType().ToString();

    // Split activityName into Namespace and Type.Append _CompiledExpressionRoot to the type name
    // to represent the new type that represents the compiled expressions.
    // Take everything after the last . for the type name.
    string activityType = activityName.Split('.').Last() + "_CompiledExpressionRoot";
    // Take everything before the last . for the namespace.
    string activityNamespace = string.Join(".", activityName.Split('.').Reverse().Skip(1).Reverse());

    // Create a TextExpressionCompilerSettings.
    TextExpressionCompilerSettings settings = new TextExpressionCompilerSettings
    {
        Activity = activity,
        Language = "C#",
        ActivityName = activityType,
        ActivityNamespace = activityNamespace,
        RootNamespace = null,
        GenerateAsPartialClass = false,
        AlwaysGenerateSource = true,
        ForImplementation = false
    };

    // Compile the C# expression.
    TextExpressionCompilerResults results =
        new TextExpressionCompiler(settings).Compile();

    // Any compilation errors are contained in the CompilerMessages.
    if (results.HasErrors)
    {
        throw new Exception("Compilation failed.");
    }

    // Create an instance of the new compiled expression type.
    ICompiledExpressionRoot compiledExpressionRoot =
        Activator.CreateInstance(results.ResultType,
            new object[] { activity }) as ICompiledExpressionRoot;

    // Attach it to the activity.
    CompiledExpressionInvoker.SetCompiledExpressionRoot(
        activity, compiledExpressionRoot);
}
```

> [!NOTE]
> <span data-ttu-id="84d99-138">如果C#表达式未编译，则在使用类似于以下内容的消息调用工作流时，将引发 <xref:System.NotSupportedException>： `Expression Activity type 'CSharpValue`1 "需要编译才能运行。</span><span class="sxs-lookup"><span data-stu-id="84d99-138">If the C# expressions are not compiled, a <xref:System.NotSupportedException> is thrown when the workflow is invoked with a message similar to the following: `Expression Activity type 'CSharpValue`1' requires compilation in order to run.</span></span>  <span data-ttu-id="84d99-139">请确保已编译工作流。 "</span><span class="sxs-lookup"><span data-stu-id="84d99-139">Please ensure that the workflow has been compiled.\`</span></span>

<span data-ttu-id="84d99-140">如果基于自定义代码的工作流使用 `DynamicActivity`，则需要对 `CompileExpressions` 方法作一些修改，如下列代码示例所示。</span><span class="sxs-lookup"><span data-stu-id="84d99-140">If your custom code based workflow uses `DynamicActivity`, then some changes to the `CompileExpressions` method are required, as demonstrated in the following code example.</span></span>

```csharp
static void CompileExpressions(DynamicActivity dynamicActivity)
{
    // activityName is the Namespace.Type of the activity that contains the
    // C# expressions. For Dynamic Activities this can be retrieved using the
    // name property , which must be in the form Namespace.Type.
    string activityName = dynamicActivity.Name;

    // Split activityName into Namespace and Type.Append _CompiledExpressionRoot to the type name
    // to represent the new type that represents the compiled expressions.
    // Take everything after the last . for the type name.
    string activityType = activityName.Split('.').Last() + "_CompiledExpressionRoot";
    // Take everything before the last . for the namespace.
    string activityNamespace = string.Join(".", activityName.Split('.').Reverse().Skip(1).Reverse());

    // Create a TextExpressionCompilerSettings.
    TextExpressionCompilerSettings settings = new TextExpressionCompilerSettings
    {
        Activity = dynamicActivity,
        Language = "C#",
        ActivityName = activityType,
        ActivityNamespace = activityNamespace,
        RootNamespace = null,
        GenerateAsPartialClass = false,
        AlwaysGenerateSource = true,
        ForImplementation = true
    };

    // Compile the C# expression.
    TextExpressionCompilerResults results =
        new TextExpressionCompiler(settings).Compile();

    // Any compilation errors are contained in the CompilerMessages.
    if (results.HasErrors)
    {
        throw new Exception("Compilation failed.");
    }

    // Create an instance of the new compiled expression type.
    ICompiledExpressionRoot compiledExpressionRoot =
        Activator.CreateInstance(results.ResultType,
            new object[] { dynamicActivity }) as ICompiledExpressionRoot;

    // Attach it to the activity.
    CompiledExpressionInvoker.SetCompiledExpressionRootForImplementation(
        dynamicActivity, compiledExpressionRoot);
}
```

<span data-ttu-id="84d99-141">在动态活动中编译 C# 表达式的 `CompileExpressions` 重载中有几处不同。</span><span class="sxs-lookup"><span data-stu-id="84d99-141">There are several differences in the `CompileExpressions` overload that compiles the C# expressions in a dynamic activity.</span></span>

- <span data-ttu-id="84d99-142">`CompileExpressions` 的参数是一个 `DynamicActivity`。</span><span class="sxs-lookup"><span data-stu-id="84d99-142">The parameter to `CompileExpressions` is a `DynamicActivity`.</span></span>

- <span data-ttu-id="84d99-143">通过使用 `DynamicActivity.Name` 属性检索类型名称和命名空间。</span><span class="sxs-lookup"><span data-stu-id="84d99-143">The type name and namespace are retrieved using the `DynamicActivity.Name` property.</span></span>

- <span data-ttu-id="84d99-144">将 `TextExpressionCompilerSettings.ForImplementation` 设置为 `true`。</span><span class="sxs-lookup"><span data-stu-id="84d99-144">`TextExpressionCompilerSettings.ForImplementation` is set to `true`.</span></span>

- <span data-ttu-id="84d99-145">调用 `CompiledExpressionInvoker.SetCompiledExpressionRootForImplementation` 而非 `CompiledExpressionInvoker.SetCompiledExpressionRoot`。</span><span class="sxs-lookup"><span data-stu-id="84d99-145">`CompiledExpressionInvoker.SetCompiledExpressionRootForImplementation` is called instead of `CompiledExpressionInvoker.SetCompiledExpressionRoot`.</span></span>

<span data-ttu-id="84d99-146">有关在代码中使用表达式的详细信息，请参阅[使用命令性代码创作工作流、活动和表达式](authoring-workflows-activities-and-expressions-using-imperative-code.md)。</span><span class="sxs-lookup"><span data-stu-id="84d99-146">For more information about working with expressions in code, see [Authoring Workflows, Activities, and Expressions Using Imperative Code](authoring-workflows-activities-and-expressions-using-imperative-code.md).</span></span>

### <a name="XamlWorkflows"></a><span data-ttu-id="84d99-147">在C# XAML 工作流中使用表达式</span><span class="sxs-lookup"><span data-stu-id="84d99-147">Using C# expressions in XAML workflows</span></span>

<span data-ttu-id="84d99-148">XAML 工作流支持 C# 表达式。</span><span class="sxs-lookup"><span data-stu-id="84d99-148">C# expressions are supported in XAML workflows.</span></span> <span data-ttu-id="84d99-149">编译型 XAML 工作流被编译到类型中，而宽松型 XAML 工作流由运行时加载，并在工作流执行时编译到活动树中。</span><span class="sxs-lookup"><span data-stu-id="84d99-149">Compiled XAML workflows are compiled into a type, and loose XAML workflows are loaded by the runtime and compiled into an activity tree when the workflow is executed.</span></span>

- [<span data-ttu-id="84d99-150">已编译 Xaml</span><span class="sxs-lookup"><span data-stu-id="84d99-150">Compiled Xaml</span></span>](csharp-expressions.md#CompiledXaml)

- [<span data-ttu-id="84d99-151">松散 Xaml</span><span class="sxs-lookup"><span data-stu-id="84d99-151">Loose Xaml</span></span>](csharp-expressions.md#LooseXaml)

#### <a name="CompiledXaml"></a><span data-ttu-id="84d99-152">已编译 Xaml</span><span class="sxs-lookup"><span data-stu-id="84d99-152">Compiled Xaml</span></span>

<span data-ttu-id="84d99-153">编译型 XAML 工作流支持 C# 表达式，此种工作流编译成类型，作为面向 [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] 的 C# 工作流项目的组成部分。</span><span class="sxs-lookup"><span data-stu-id="84d99-153">C# expressions are supported in compiled XAML workflows that are compiled to a type as part of a C# workflow project that targets [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)].</span></span> <span data-ttu-id="84d99-154">在 Visual Studio 中，编译的 XAML 是工作流创作的默认C#类型，在 visual studio 中创建的工作流C#项目以 [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] 使用表达式。</span><span class="sxs-lookup"><span data-stu-id="84d99-154">Compiled XAML is the default type of workflow authoring in Visual Studio, and C# workflow projects created in Visual Studio that target [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] use C# expressions.</span></span>

#### <a name="LooseXaml"></a><span data-ttu-id="84d99-155">松散 Xaml</span><span class="sxs-lookup"><span data-stu-id="84d99-155">Loose Xaml</span></span>

<span data-ttu-id="84d99-156">宽松型 XAML 工作流支持 C# 表达式。</span><span class="sxs-lookup"><span data-stu-id="84d99-156">C# expressions are supported in loose XAML workflows.</span></span> <span data-ttu-id="84d99-157">加载并调用宽松型 XAML 工作流的工作流宿主程序必须面向 [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)]，而<xref:System.Activities.XamlIntegration.ActivityXamlServicesSettings.CompileExpressions%2A> 必须设为 `true`（默认值为 `false`）。</span><span class="sxs-lookup"><span data-stu-id="84d99-157">The workflow host program that loads and invokes the loose XAML workflow must target [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)], and <xref:System.Activities.XamlIntegration.ActivityXamlServicesSettings.CompileExpressions%2A> must be set to `true` (the default is `false`).</span></span> <span data-ttu-id="84d99-158">要将 <xref:System.Activities.XamlIntegration.ActivityXamlServicesSettings.CompileExpressions%2A> 设置为 `true`，请创建一个 <xref:System.Activities.XamlIntegration.ActivityXamlServicesSettings> 实例，创建时将其 <xref:System.Activities.XamlIntegration.ActivityXamlServicesSettings.CompileExpressions%2A> 属性设为 `true`，并作为参数传递给 <xref:System.Activities.XamlIntegration.ActivityXamlServices.Load%2A?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="84d99-158">To set <xref:System.Activities.XamlIntegration.ActivityXamlServicesSettings.CompileExpressions%2A> to `true`, create an <xref:System.Activities.XamlIntegration.ActivityXamlServicesSettings> instance with its <xref:System.Activities.XamlIntegration.ActivityXamlServicesSettings.CompileExpressions%2A> property set to `true`, and pass it as a parameter to <xref:System.Activities.XamlIntegration.ActivityXamlServices.Load%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="84d99-159">如果 `CompileExpressions` 未设置为 `true`，则将引发一个 <xref:System.NotSupportedException>，其中包含类似于以下内容的消息： `Expression Activity type 'CSharpValue`1 "需要编译才能运行。</span><span class="sxs-lookup"><span data-stu-id="84d99-159">If `CompileExpressions` Is not set to `true`, a <xref:System.NotSupportedException> will be thrown with a message similar to the following: `Expression Activity type 'CSharpValue`1' requires compilation in order to run.</span></span>  <span data-ttu-id="84d99-160">请确保已编译工作流。 "</span><span class="sxs-lookup"><span data-stu-id="84d99-160">Please ensure that the workflow has been compiled.\`</span></span>

```csharp
ActivityXamlServicesSettings settings = new ActivityXamlServicesSettings
{
    CompileExpressions = true
};

DynamicActivity<int> wf = ActivityXamlServices.Load(new StringReader(serializedAB), settings) as DynamicActivity<int>;
```

<span data-ttu-id="84d99-161">有关使用 XAML 工作流的详细信息，请参阅[在 xaml 中序列化工作流和活动](serializing-workflows-and-activities-to-and-from-xaml.md)。</span><span class="sxs-lookup"><span data-stu-id="84d99-161">For more information about working with XAML workflows, see [Serializing Workflows and Activities to and from XAML](serializing-workflows-and-activities-to-and-from-xaml.md).</span></span>

### <a name="WFServices"></a><span data-ttu-id="84d99-162">在C# .xamlx 工作流服务中使用表达式</span><span class="sxs-lookup"><span data-stu-id="84d99-162">Using C# expressions in XAMLX workflow services</span></span>

<span data-ttu-id="84d99-163">XAMLX 工作流服务支持 C# 表达式。</span><span class="sxs-lookup"><span data-stu-id="84d99-163">C# expressions are supported in XAMLX workflow services.</span></span> <span data-ttu-id="84d99-164">当工作流服务承载于 IIS 或 WAS 中时，无须执行任何额外步骤，但如果 XAML 工作流服务是自承载的，则 C# 表达式必须经过编译。</span><span class="sxs-lookup"><span data-stu-id="84d99-164">When a workflow service is hosted in IIS or WAS then no additional steps are required, but if the XAML workflow service is self-hosted, then the C# expressions must be compiled.</span></span> <span data-ttu-id="84d99-165">若要在C#自承载的 .xamlx 工作流服务中编译表达式，请首先将 .xamlx 文件加载到 `WorkflowService`中，然后将 `WorkflowService` 的 `Body` 传递到 "[代码工作流C# ](csharp-expressions.md#CodeWorkflows) " 部分中前面的 "使用表达式" 部分所述的 `CompileExpressions` 方法。</span><span class="sxs-lookup"><span data-stu-id="84d99-165">To compile the C# expressions in a self-hosted XAMLX workflow service, first load the XAMLX file into a `WorkflowService`, and then pass the `Body` of the `WorkflowService` to the `CompileExpressions` method described in the previous [Using C# expressions in code workflows](csharp-expressions.md#CodeWorkflows) section.</span></span> <span data-ttu-id="84d99-166">下例加载一个 XAMLX 工作流服务，编译 C# 表达式，随后打开该工作流服务并等待请求。</span><span class="sxs-lookup"><span data-stu-id="84d99-166">In the following example, a XAMLX workflow service is loaded, the C# expressions are compiled, and then the workflow service is opened and waits for requests.</span></span>

```csharp
// Load the XAMLX workflow service.
WorkflowService workflow1 =
    (WorkflowService)XamlServices.Load(xamlxPath);

// Compile the C# expressions in the workflow by passing the Body to CompileExpressions.
CompileExpressions(workflow1.Body);

// Initialize the WorkflowServiceHost.
var host = new WorkflowServiceHost(workflow1, new Uri("http://localhost:8293/Service1.xamlx"));

// Enable Metadata publishing/
ServiceMetadataBehavior smb = new ServiceMetadataBehavior();
smb.HttpGetEnabled = true;
smb.MetadataExporter.PolicyVersion = PolicyVersion.Policy15;
host.Description.Behaviors.Add(smb);

// Open the WorkflowServiceHost and wait for requests.
host.Open();
Console.WriteLine("Press enter to quit");
Console.ReadLine();
```

<span data-ttu-id="84d99-167">如果 C# 表达式未编译，那么，虽然 `Open` 操作会成功执行，但工作流在调用时将失败。</span><span class="sxs-lookup"><span data-stu-id="84d99-167">If the C# expressions are not compiled, the `Open` operation succeeds but the workflow will fail when it is invoked.</span></span> <span data-ttu-id="84d99-168">以下 `CompileExpressions` 方法与 "[代码工作流C# ](csharp-expressions.md#CodeWorkflows) " 部分中前面的 "使用表达式" 一节中的方法相同。</span><span class="sxs-lookup"><span data-stu-id="84d99-168">The following `CompileExpressions` method is the same as the method from the previous [Using C# expressions in code workflows](csharp-expressions.md#CodeWorkflows) section.</span></span>

```csharp
static void CompileExpressions(Activity activity)
{
    // activityName is the Namespace.Type of the activity that contains the
    // C# expressions.
    string activityName = activity.GetType().ToString();

    // Split activityName into Namespace and Type.Append _CompiledExpressionRoot to the type name
    // to represent the new type that represents the compiled expressions.
    // Take everything after the last . for the type name.
    string activityType = activityName.Split('.').Last() + "_CompiledExpressionRoot";
    // Take everything before the last . for the namespace.
    string activityNamespace = string.Join(".", activityName.Split('.').Reverse().Skip(1).Reverse());

    // Create a TextExpressionCompilerSettings.
    TextExpressionCompilerSettings settings = new TextExpressionCompilerSettings
    {
        Activity = activity,
        Language = "C#",
        ActivityName = activityType,
        ActivityNamespace = activityNamespace,
        RootNamespace = null,
        GenerateAsPartialClass = false,
        AlwaysGenerateSource = true,
        ForImplementation = false
    };

    // Compile the C# expression.
    TextExpressionCompilerResults results =
        new TextExpressionCompiler(settings).Compile();

    // Any compilation errors are contained in the CompilerMessages.
    if (results.HasErrors)
    {
        throw new Exception("Compilation failed.");
    }

    // Create an instance of the new compiled expression type.
    ICompiledExpressionRoot compiledExpressionRoot =
        Activator.CreateInstance(results.ResultType,
            new object[] { activity }) as ICompiledExpressionRoot;

    // Attach it to the activity.
    CompiledExpressionInvoker.SetCompiledExpressionRoot(
        activity, compiledExpressionRoot);
}
```
