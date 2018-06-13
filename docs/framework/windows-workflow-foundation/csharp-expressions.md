---
title: C# 表达式
ms.date: 03/30/2017
ms.assetid: 29110be7-f4e3-407e-8dbe-78102eb21115
ms.openlocfilehash: fa6ffd3b1828db03fd6850d4904aee2339df7f31
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33520050"
---
# <a name="c-expressions"></a><span data-ttu-id="84e59-102">C# 表达式</span><span class="sxs-lookup"><span data-stu-id="84e59-102">C# Expressions</span></span>
<span data-ttu-id="84e59-103">从开始[!INCLUDE[net_v45](../../../includes/net-v45-md.md)]，在 Windows Workflow Foundation (WF) 支持 C# 表达式。</span><span class="sxs-lookup"><span data-stu-id="84e59-103">Starting with [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], C# expressions are supported in Windows Workflow Foundation (WF).</span></span> <span data-ttu-id="84e59-104">在 [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] 中面向 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 新建的 C# 工作流项目使用 C# 表达式，而 Visual Basic 工作流项目则使用 Visual Basic 表达式。</span><span class="sxs-lookup"><span data-stu-id="84e59-104">New C# workflow projects created in [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] that target [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] use C# expressions, and Visual Basic workflow projects use Visual Basic expressions.</span></span> <span data-ttu-id="84e59-105">现有使用 Visual Basic 表达式的 [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)] 工作流项目可以不受项目语言限制而迁移到 [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)]，并得到支持。</span><span class="sxs-lookup"><span data-stu-id="84e59-105">Existing [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)] workflow projects that use Visual Basic expressions can be migrated to [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] regardless of the project language and are supported.</span></span> <span data-ttu-id="84e59-106">本主题概述了 [!INCLUDE[wf1](../../../includes/wf1-md.md)] 中的 C# 表达式。</span><span class="sxs-lookup"><span data-stu-id="84e59-106">This topic provides an overview of C# expressions in [!INCLUDE[wf1](../../../includes/wf1-md.md)].</span></span>  
  
## <a name="using-c-expressions-in-workflows"></a><span data-ttu-id="84e59-107">在工作流中使用 C# 表达式</span><span class="sxs-lookup"><span data-stu-id="84e59-107">Using C# expressions in workflows</span></span>  
  
-   [<span data-ttu-id="84e59-108">在工作流设计器中使用 C# 表达式</span><span class="sxs-lookup"><span data-stu-id="84e59-108">Using C# expressions in the Workflow Designer</span></span>](../../../docs/framework/windows-workflow-foundation/csharp-expressions.md#WFDesigner)  
  
    -   [<span data-ttu-id="84e59-109">向后兼容性</span><span class="sxs-lookup"><span data-stu-id="84e59-109">Backwards compatibility</span></span>](../../../docs/framework/windows-workflow-foundation/csharp-expressions.md#BackwardCompat)  
  
-   [<span data-ttu-id="84e59-110">在代码工作流中使用 C# 表达式</span><span class="sxs-lookup"><span data-stu-id="84e59-110">Using C# expressions in code workflows</span></span>](../../../docs/framework/windows-workflow-foundation/csharp-expressions.md#CodeWorkflows)  
  
-   [<span data-ttu-id="84e59-111">在 XAML 工作流中使用 C# 表达式</span><span class="sxs-lookup"><span data-stu-id="84e59-111">Using C# expressions in XAML workflows</span></span>](../../../docs/framework/windows-workflow-foundation/csharp-expressions.md#XamlWorkflows)  
  
    -   [<span data-ttu-id="84e59-112">编译型的 Xaml</span><span class="sxs-lookup"><span data-stu-id="84e59-112">Compiled Xaml</span></span>](../../../docs/framework/windows-workflow-foundation/csharp-expressions.md#CompiledXaml)  
  
    -   [<span data-ttu-id="84e59-113">宽松型 Xaml</span><span class="sxs-lookup"><span data-stu-id="84e59-113">Loose Xaml</span></span>](../../../docs/framework/windows-workflow-foundation/csharp-expressions.md#LooseXaml)  
  
-   [<span data-ttu-id="84e59-114">在 XAMLX 工作流服务中使用 C# 表达式</span><span class="sxs-lookup"><span data-stu-id="84e59-114">Using C# expressions in XAMLX workflow services</span></span>](../../../docs/framework/windows-workflow-foundation/csharp-expressions.md#WFServices)  
  
###  <a name="WFDesigner"></a> <span data-ttu-id="84e59-115">在工作流设计器中使用 C# 表达式</span><span class="sxs-lookup"><span data-stu-id="84e59-115">Using C# expressions in the Workflow Designer</span></span>  
 <span data-ttu-id="84e59-116">从开始[!INCLUDE[net_v45](../../../includes/net-v45-md.md)]，在 Windows Workflow Foundation (WF) 支持 C# 表达式。</span><span class="sxs-lookup"><span data-stu-id="84e59-116">Starting with [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], C# expressions are supported in Windows Workflow Foundation (WF).</span></span> <span data-ttu-id="84e59-117">在 [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] 中面向 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 创建的 C# 工作流项目使用 C# 表达式，而 Visual Basic 工作流项目则使用 Visual Basic 表达式。</span><span class="sxs-lookup"><span data-stu-id="84e59-117">C# workflow projects created in [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] that target [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] use C# expressions, while Visual Basic workflow projects use Visual Basic expressions.</span></span> <span data-ttu-id="84e59-118">若要指定所需的 C# 表达式，它在框中键入标记为**输入 C# 表达式**。</span><span class="sxs-lookup"><span data-stu-id="84e59-118">To specify the desired C# expression, type it into the box labeled **Enter a C# expression**.</span></span> <span data-ttu-id="84e59-119">该标签显示在属性窗口中（当在设计器中选中活动时），或显示在工作流设计器的活动上。</span><span class="sxs-lookup"><span data-stu-id="84e59-119">This label is displayed in the properties window when the activity is selected in the designer, or on the activity in the workflow designer.</span></span> <span data-ttu-id="84e59-120">下例中，在 `WriteLine` 范围内，一个 `Sequence` 中包含了两个 `NoPersistScope` 活动。</span><span class="sxs-lookup"><span data-stu-id="84e59-120">In the following example, two `WriteLine` activities are contained within a `Sequence` inside a `NoPersistScope`.</span></span>  
  
 <span data-ttu-id="84e59-121">![自动创建的序列活动](../../../docs/framework/windows-workflow-foundation/media/autosurround2.png "AutoSurround2")</span><span class="sxs-lookup"><span data-stu-id="84e59-121">![Automatically created sequence activity](../../../docs/framework/windows-workflow-foundation/media/autosurround2.png "AutoSurround2")</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="84e59-122">C# 表达式仅在 Visual Studio 中支持和不支持在重新承载的工作流设计器中。</span><span class="sxs-lookup"><span data-stu-id="84e59-122">C# expressions are supported only in Visual Studio, and are not supported in the re-hosted workflow designer.</span></span> <span data-ttu-id="84e59-123">有关在重新承载的设计器中受支持的新 WF45 功能的详细信息，请参阅[重新承载工作流设计器中新 Workflow Foundation 4.5 功能的支持](../../../docs/framework/windows-workflow-foundation/wf-features-in-the-rehosted-workflow-designer.md)。</span><span class="sxs-lookup"><span data-stu-id="84e59-123">For more information about new WF45 features supported in the re-hosted designer, see [Support for New Workflow Foundation 4.5 Features in the Rehosted Workflow Designer](../../../docs/framework/windows-workflow-foundation/wf-features-in-the-rehosted-workflow-designer.md).</span></span>  
  
####  <a name="BackwardCompat"></a> <span data-ttu-id="84e59-124">向后兼容性</span><span class="sxs-lookup"><span data-stu-id="84e59-124">Backwards compatibility</span></span>  
 <span data-ttu-id="84e59-125">在现有已迁移到 [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)] 的 [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] C# 工作流项目中使用的 Visual Basic 表达式是得到支持的。</span><span class="sxs-lookup"><span data-stu-id="84e59-125">Visual Basic expressions in existing [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)] C# workflow projects that have been migrated to [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] are supported.</span></span> <span data-ttu-id="84e59-126">当在工作流设计器中查看 Visual Basic 表达式时，现有的 Visual Basic 表达式的文本替换**值在 XAML 中设置**，除非 Visual Basic 表达式是有效的 C# 语法。</span><span class="sxs-lookup"><span data-stu-id="84e59-126">When the Visual Basic expressions are viewed in the workflow designer, the text of the existing Visual Basic expression is replaced with **Value was set in XAML**, unless the Visual Basic expression is valid C# syntax.</span></span> <span data-ttu-id="84e59-127">如果 Visual Basic 表达式符合 C# 语法则予以显示。</span><span class="sxs-lookup"><span data-stu-id="84e59-127">If the Visual Basic expression is valid C# syntax, then the expression is displayed.</span></span> <span data-ttu-id="84e59-128">若要将 Visual Basic 表达式更新为 C#，可在工作流设计器中编辑这些表达式，指定等效的 C# 表达式。</span><span class="sxs-lookup"><span data-stu-id="84e59-128">To update the Visual Basic expressions to C#, you can edit them in the workflow designer and specify the equivalent C# expression.</span></span> <span data-ttu-id="84e59-129">将 Visual Basic 表达式更新为 C# 不是必须的，但一旦在工作流设计器中进行更新，这些表达式即转换成 C# 并不可重新转换为 Visual Basic。</span><span class="sxs-lookup"><span data-stu-id="84e59-129">It is not required to update the Visual Basic expressions to C#, but once the expressions are updated in the workflow designer they are converted to C# and may not be reverted to Visual Basic.</span></span>  
  
###  <a name="CodeWorkflows"></a> <span data-ttu-id="84e59-130">在代码工作流中使用 C# 表达式</span><span class="sxs-lookup"><span data-stu-id="84e59-130">Using C# expressions in code workflows</span></span>  
 <span data-ttu-id="84e59-131">基于 [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] 代码的工作流支持 C# 表达式，但 C# 表达式须用 <xref:System.Activities.XamlIntegration.TextExpressionCompiler.Compile%2A?displayProperty=nameWithType> 进行编译，然后才能调用工作流。</span><span class="sxs-lookup"><span data-stu-id="84e59-131">C# expressions are supported in [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] code based workflows, but before the workflow can be invoked the C# expressions must be compiled using <xref:System.Activities.XamlIntegration.TextExpressionCompiler.Compile%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="84e59-132">工作流作者可以用 `CSharpValue` 表示表达式的右值，用 `CSharpReference` 表示表达式的左值。</span><span class="sxs-lookup"><span data-stu-id="84e59-132">Workflow authors can use `CSharpValue` to represent the r-value of an expression, and `CSharpReference` to represent the l-value of an expression.</span></span> <span data-ttu-id="84e59-133">在下例中，用一个 `Assign` 活动以及 `WriteLine` 活动中所包含的 `Sequence` 活动创建了一个工作流。</span><span class="sxs-lookup"><span data-stu-id="84e59-133">In the following example, a workflow is created with an `Assign` activity and a `WriteLine` activity contained in a `Sequence` activity.</span></span> <span data-ttu-id="84e59-134">为 `CSharpReference` 的 `To` 参数指定了一个 `Assign`，用来表示表达式的左值。</span><span class="sxs-lookup"><span data-stu-id="84e59-134">A `CSharpReference` is specified for the `To` argument of the `Assign`, and represents the l-value of the expression.</span></span> <span data-ttu-id="84e59-135">为 `CSharpValue` 的 `Value` 参数和 `Assign` 的 `Text` 参数指定了一个 `WriteLine`，用于表示这两个表达式的右值。</span><span class="sxs-lookup"><span data-stu-id="84e59-135">A `CSharpValue` is specified for the `Value` argument of the `Assign`, and for the `Text` argument of the `WriteLine`, and represents the r-value for those two expressions.</span></span>  
  
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
  
 <span data-ttu-id="84e59-136">工作流构造完毕后，通过调用 `CompileExpressions` 帮助器方法编译了 C# 表达式，随后调用工作流。</span><span class="sxs-lookup"><span data-stu-id="84e59-136">After the workflow is constructed, the C# expressions are compiled by calling the `CompileExpressions` helper method and then the workflow is invoked.</span></span> <span data-ttu-id="84e59-137">下面的示例为 `CompileExpressions` 方法。</span><span class="sxs-lookup"><span data-stu-id="84e59-137">The following example is the `CompileExpressions` method.</span></span>  
  
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
>  <span data-ttu-id="84e59-138">如果 C# 表达式尚未编译，<xref:System.NotSupportedException>使用类似于以下的消息调用工作流时，将引发： `Expression Activity type 'CSharpValue`1 需要编译才能运行。</span><span class="sxs-lookup"><span data-stu-id="84e59-138">If the C# expressions are not compiled, a <xref:System.NotSupportedException> is thrown when the workflow is invoked with a message similar to the following: `Expression Activity type 'CSharpValue`1' requires compilation in order to run.</span></span>  <span data-ttu-id="84e59-139">请确保已编译工作流。</span><span class="sxs-lookup"><span data-stu-id="84e59-139">Please ensure that the workflow has been compiled.\`</span></span>  
  
 <span data-ttu-id="84e59-140">如果基于自定义代码的工作流使用 `DynamicActivity`，则需要对 `CompileExpressions` 方法作一些修改，如下列代码示例所示。</span><span class="sxs-lookup"><span data-stu-id="84e59-140">If your custom code based workflow uses `DynamicActivity`, then some changes to the `CompileExpressions` method are required, as demonstrated in the following code example.</span></span>  
  
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
  
 <span data-ttu-id="84e59-141">在动态活动中编译 C# 表达式的 `CompileExpressions` 重载中有几处不同。</span><span class="sxs-lookup"><span data-stu-id="84e59-141">There are several differences in the `CompileExpressions` overload that compiles the C# expressions in a dynamic activity.</span></span>  
  
-   <span data-ttu-id="84e59-142">`CompileExpressions` 的参数是一个 `DynamicActivity`。</span><span class="sxs-lookup"><span data-stu-id="84e59-142">The parameter to `CompileExpressions` is a `DynamicActivity`.</span></span>  
  
-   <span data-ttu-id="84e59-143">通过使用 `DynamicActivity.Name` 属性检索类型名称和命名空间。</span><span class="sxs-lookup"><span data-stu-id="84e59-143">The type name and namespace are retrieved using the `DynamicActivity.Name` property.</span></span>  
  
-   <span data-ttu-id="84e59-144">将 `TextExpressionCompilerSettings.ForImplementation` 设置为 `true`。</span><span class="sxs-lookup"><span data-stu-id="84e59-144">`TextExpressionCompilerSettings.ForImplementation` is set to `true`.</span></span>  
  
-   <span data-ttu-id="84e59-145">调用 `CompiledExpressionInvoker.SetCompiledExpressionRootForImplementation` 而非 `CompiledExpressionInvoker.SetCompiledExpressionRoot`。</span><span class="sxs-lookup"><span data-stu-id="84e59-145">`CompiledExpressionInvoker.SetCompiledExpressionRootForImplementation` is called instead of `CompiledExpressionInvoker.SetCompiledExpressionRoot`.</span></span>  
  
 <span data-ttu-id="84e59-146">有关使用代码中的表达式的详细信息，请参阅[创作工作流、 活动和表达式使用命令性代码](../../../docs/framework/windows-workflow-foundation/authoring-workflows-activities-and-expressions-using-imperative-code.md)。</span><span class="sxs-lookup"><span data-stu-id="84e59-146">For more information about working with expressions in code, see [Authoring Workflows, Activities, and Expressions Using Imperative Code](../../../docs/framework/windows-workflow-foundation/authoring-workflows-activities-and-expressions-using-imperative-code.md).</span></span>  
  
###  <a name="XamlWorkflows"></a> <span data-ttu-id="84e59-147">在 XAML 工作流中使用 C# 表达式</span><span class="sxs-lookup"><span data-stu-id="84e59-147">Using C# expressions in XAML workflows</span></span>  
 <span data-ttu-id="84e59-148">XAML 工作流支持 C# 表达式。</span><span class="sxs-lookup"><span data-stu-id="84e59-148">C# expressions are supported in XAML workflows.</span></span> <span data-ttu-id="84e59-149">编译型 XAML 工作流被编译到类型中，而宽松型 XAML 工作流由运行时加载，并在工作流执行时编译到活动树中。</span><span class="sxs-lookup"><span data-stu-id="84e59-149">Compiled XAML workflows are compiled into a type, and loose XAML workflows are loaded by the runtime and compiled into an activity tree when the workflow is executed.</span></span>  
  
-   [<span data-ttu-id="84e59-150">编译型的 Xaml</span><span class="sxs-lookup"><span data-stu-id="84e59-150">Compiled Xaml</span></span>](../../../docs/framework/windows-workflow-foundation/csharp-expressions.md#CompiledXaml)  
  
-   [<span data-ttu-id="84e59-151">宽松型 Xaml</span><span class="sxs-lookup"><span data-stu-id="84e59-151">Loose Xaml</span></span>](../../../docs/framework/windows-workflow-foundation/csharp-expressions.md#LooseXaml)  
  
####  <a name="CompiledXaml"></a> <span data-ttu-id="84e59-152">编译型的 Xaml</span><span class="sxs-lookup"><span data-stu-id="84e59-152">Compiled Xaml</span></span>  
 <span data-ttu-id="84e59-153">编译型 XAML 工作流支持 C# 表达式，此种工作流编译成类型，作为面向 [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] 的 C# 工作流项目的组成部分。</span><span class="sxs-lookup"><span data-stu-id="84e59-153">C# expressions are supported in compiled XAML workflows that are compiled to a type as part of a C# workflow project that targets [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)].</span></span> <span data-ttu-id="84e59-154">编译型的 XAML 是 Visual Studio 中的工作流创作的默认类型和 C# 工作流项目中创建 Visual Studio 面向[!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)]使用 C# 表达式。</span><span class="sxs-lookup"><span data-stu-id="84e59-154">Compiled XAML is the default type of workflow authoring in Visual Studio, and C# workflow projects created in Visual Studio that target [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] use C# expressions.</span></span>  
  
####  <a name="LooseXaml"></a> <span data-ttu-id="84e59-155">宽松型 Xaml</span><span class="sxs-lookup"><span data-stu-id="84e59-155">Loose Xaml</span></span>  
 <span data-ttu-id="84e59-156">宽松型 XAML 工作流支持 C# 表达式。</span><span class="sxs-lookup"><span data-stu-id="84e59-156">C# expressions are supported in loose XAML workflows.</span></span> <span data-ttu-id="84e59-157">加载并调用宽松型 XAML 工作流的工作流宿主程序必须面向 [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)]，而<xref:System.Activities.XamlIntegration.ActivityXamlServicesSettings.CompileExpressions%2A> 必须设为 `true`（默认值为 `false`）。</span><span class="sxs-lookup"><span data-stu-id="84e59-157">The workflow host program that loads and invokes the loose XAML workflow must target [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)], and <xref:System.Activities.XamlIntegration.ActivityXamlServicesSettings.CompileExpressions%2A> must be set to `true` (the default is `false`).</span></span> <span data-ttu-id="84e59-158">要将 <xref:System.Activities.XamlIntegration.ActivityXamlServicesSettings.CompileExpressions%2A> 设置为 `true`，请创建一个 <xref:System.Activities.XamlIntegration.ActivityXamlServicesSettings> 实例，创建时将其 <xref:System.Activities.XamlIntegration.ActivityXamlServicesSettings.CompileExpressions%2A> 属性设为 `true`，并作为参数传递给 <xref:System.Activities.XamlIntegration.ActivityXamlServices.Load%2A?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="84e59-158">To set <xref:System.Activities.XamlIntegration.ActivityXamlServicesSettings.CompileExpressions%2A> to `true`, create an <xref:System.Activities.XamlIntegration.ActivityXamlServicesSettings> instance with its <xref:System.Activities.XamlIntegration.ActivityXamlServicesSettings.CompileExpressions%2A> property set to `true`, and pass it as a parameter to <xref:System.Activities.XamlIntegration.ActivityXamlServices.Load%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="84e59-159">如果`CompileExpressions`未设置为`true`、<xref:System.NotSupportedException>将引发类似于以下的消息： `Expression Activity type 'CSharpValue`1 需要编译才能运行。</span><span class="sxs-lookup"><span data-stu-id="84e59-159">If `CompileExpressions` Is not set to `true`, a <xref:System.NotSupportedException> will be thrown with a message similar to the following: `Expression Activity type 'CSharpValue`1' requires compilation in order to run.</span></span>  <span data-ttu-id="84e59-160">请确保已编译工作流。</span><span class="sxs-lookup"><span data-stu-id="84e59-160">Please ensure that the workflow has been compiled.\`</span></span>  
  
```csharp  
ActivityXamlServicesSettings settings = new ActivityXamlServicesSettings  
{  
    CompileExpressions = true  
};  
  
DynamicActivity<int> wf = ActivityXamlServices.Load(new StringReader(serializedAB), settings) as DynamicActivity<int>;  
```  
  
 <span data-ttu-id="84e59-161">有关使用 XAML 工作流的详细信息，请参阅[序列化工作流和活动和从 XAML](../../../docs/framework/windows-workflow-foundation/serializing-workflows-and-activities-to-and-from-xaml.md)。</span><span class="sxs-lookup"><span data-stu-id="84e59-161">For more information about working with XAML workflows, see [Serializing Workflows and Activities to and from XAML](../../../docs/framework/windows-workflow-foundation/serializing-workflows-and-activities-to-and-from-xaml.md).</span></span>  
  
###  <a name="WFServices"></a> <span data-ttu-id="84e59-162">在 XAMLX 工作流服务中使用 C# 表达式</span><span class="sxs-lookup"><span data-stu-id="84e59-162">Using C# expressions in XAMLX workflow services</span></span>  
 <span data-ttu-id="84e59-163">XAMLX 工作流服务支持 C# 表达式。</span><span class="sxs-lookup"><span data-stu-id="84e59-163">C# expressions are supported in XAMLX workflow services.</span></span> <span data-ttu-id="84e59-164">当工作流服务承载于 IIS 或 WAS 中时，无须执行任何额外步骤，但如果 XAML 工作流服务是自承载的，则 C# 表达式必须经过编译。</span><span class="sxs-lookup"><span data-stu-id="84e59-164">When a workflow service is hosted in IIS or WAS then no additional steps are required, but if the XAML workflow service is self-hosted, then the C# expressions must be compiled.</span></span> <span data-ttu-id="84e59-165">若要编译中自承载的 XAMLX 工作流服务的 C# 表达式，首先将 XAMLX 文件加载到`WorkflowService`，然后将传递`Body`的`WorkflowService`到`CompileExpressions`中前面所述的方法[使用 C#在代码工作流中的表达式](../../../docs/framework/windows-workflow-foundation/csharp-expressions.md#CodeWorkflows)部分。</span><span class="sxs-lookup"><span data-stu-id="84e59-165">To compile the C# expressions in a self-hosted XAMLX workflow service, first load the XAMLX file into a `WorkflowService`, and then pass the `Body` of the `WorkflowService` to the `CompileExpressions` method described in the previous [Using C# expressions in code workflows](../../../docs/framework/windows-workflow-foundation/csharp-expressions.md#CodeWorkflows) section.</span></span> <span data-ttu-id="84e59-166">下例加载一个 XAMLX 工作流服务，编译 C# 表达式，随后打开该工作流服务并等待请求。</span><span class="sxs-lookup"><span data-stu-id="84e59-166">In the following example, a XAMLX workflow service is loaded, the C# expressions are compiled, and then the workflow service is opened and waits for requests.</span></span>  
  
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
  
 <span data-ttu-id="84e59-167">如果 C# 表达式未编译，那么，虽然 `Open` 操作会成功执行，但工作流在调用时将失败。</span><span class="sxs-lookup"><span data-stu-id="84e59-167">If the C# expressions are not compiled, the `Open` operation succeeds but the workflow will fail when it is invoked.</span></span> <span data-ttu-id="84e59-168">以下`CompileExpressions`方法是从以前的方法相同[代码工作流中的使用 C# 表达式](../../../docs/framework/windows-workflow-foundation/csharp-expressions.md#CodeWorkflows)部分。</span><span class="sxs-lookup"><span data-stu-id="84e59-168">The following `CompileExpressions` method is the same as the method from the previous [Using C# expressions in code workflows](../../../docs/framework/windows-workflow-foundation/csharp-expressions.md#CodeWorkflows) section.</span></span>  
  
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
