---
title: 将工作流和活动序列化为 XAML 和从 XAML 序列化工作流和活动
ms.date: 03/30/2017
ms.assetid: 37685b32-24e3-4d72-88d8-45d5fcc49ec2
ms.openlocfilehash: f448d96de742b2d81adf7e3c95865a2dd0cb9fd0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33520248"
---
# <a name="serializing-workflows-and-activities-to-and-from-xaml"></a><span data-ttu-id="e48e6-102">将工作流和活动序列化为 XAML 和从 XAML 序列化工作流和活动</span><span class="sxs-lookup"><span data-stu-id="e48e6-102">Serializing Workflows and Activities to and from XAML</span></span>
<span data-ttu-id="e48e6-103">除了可将工作流定义编译为程序集中包含的类型之外，还可将工作流定义序列化为 XAML。</span><span class="sxs-lookup"><span data-stu-id="e48e6-103">In addition to being compiled into types that are contained in assemblies, workflow definitions can also be serialized to XAML.</span></span> <span data-ttu-id="e48e6-104">这些已序列化的定义可以重新加载以供编辑或检测，可以传递给生成系统以供编译，也可以加载并调用。</span><span class="sxs-lookup"><span data-stu-id="e48e6-104">These serialized definitions can be reloaded for editing or inspection, passed to a build system for compilation, or loaded and invoked.</span></span> <span data-ttu-id="e48e6-105">本主题概述如何序列化工作流定义以及如何使用 XAML 工作流定义。</span><span class="sxs-lookup"><span data-stu-id="e48e6-105">This topic provides an overview of serializing workflow definitions and working with XAML workflow definitions.</span></span>  
  
## <a name="working-with-xaml-workflow-definitions"></a><span data-ttu-id="e48e6-106">使用 XAML 工作流定义</span><span class="sxs-lookup"><span data-stu-id="e48e6-106">Working with XAML Workflow Definitions</span></span>  
 <span data-ttu-id="e48e6-107">若要创建工作流定义以进行序列化，请使用 <xref:System.Activities.ActivityBuilder> 类。</span><span class="sxs-lookup"><span data-stu-id="e48e6-107">To create a workflow definition for serialization, the <xref:System.Activities.ActivityBuilder> class is used.</span></span> <span data-ttu-id="e48e6-108"><xref:System.Activities.ActivityBuilder> 的创建方式与 <xref:System.Activities.DynamicActivity> 的创建方式极其类似。</span><span class="sxs-lookup"><span data-stu-id="e48e6-108">Creating an <xref:System.Activities.ActivityBuilder> is very similar to creating a <xref:System.Activities.DynamicActivity>.</span></span> <span data-ttu-id="e48e6-109">指定任何所需的参数，并配置构成行为的活动。</span><span class="sxs-lookup"><span data-stu-id="e48e6-109">Any desired arguments are specified, and the activities that constitute the behavior are configured.</span></span> <span data-ttu-id="e48e6-110">在下面的示例中，将要创建 `Add` 活动，此活动使用两个输入参数并将它们相加，然后返回结果。</span><span class="sxs-lookup"><span data-stu-id="e48e6-110">In the following example, an `Add` activity is created that takes two input arguments, adds them together, and returns the result.</span></span> <span data-ttu-id="e48e6-111">由于此活动返回一个结果，因此将使用泛型 <xref:System.Activities.ActivityBuilder%601> 类。</span><span class="sxs-lookup"><span data-stu-id="e48e6-111">Because this activity returns a result, the generic <xref:System.Activities.ActivityBuilder%601> class is used.</span></span>  
  
 [!code-csharp[CFX_WorkflowApplicationExample#41](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#41)]  
  
 <span data-ttu-id="e48e6-112">每个 <xref:System.Activities.DynamicActivityProperty> 实例均表示工作流的一个输入参数，并且 <xref:System.Activities.ActivityBuilder.Implementation%2A> 包含构成工作流逻辑的活动。</span><span class="sxs-lookup"><span data-stu-id="e48e6-112">Each of the <xref:System.Activities.DynamicActivityProperty> instances represents one of the input arguments to the workflow, and the <xref:System.Activities.ActivityBuilder.Implementation%2A> contains the activities that make up the logic of the workflow.</span></span> <span data-ttu-id="e48e6-113">请注意，此示例中的右值表达式是 Visual Basic 表达式。</span><span class="sxs-lookup"><span data-stu-id="e48e6-113">Note that the r-value expressions in this example are Visual Basic expressions.</span></span> <span data-ttu-id="e48e6-114">Lambda 表达式不可序列化为 XAML，除非使用 <xref:System.Activities.Expressions.ExpressionServices.Convert%2A>。</span><span class="sxs-lookup"><span data-stu-id="e48e6-114">Lambda expressions are not serializable to XAML unless <xref:System.Activities.Expressions.ExpressionServices.Convert%2A> is used.</span></span> <span data-ttu-id="e48e6-115">如果序列化的工作流要在工作流设计器中打开或进行编辑，则应使用 Visual Basic 表达式。</span><span class="sxs-lookup"><span data-stu-id="e48e6-115">If the serialized workflows are intended to be opened or edited in the workflow designer then Visual Basic expressions should be used.</span></span> <span data-ttu-id="e48e6-116">有关详细信息，请参阅[创作工作流、 活动和表达式使用命令性代码](../../../docs/framework/windows-workflow-foundation/authoring-workflows-activities-and-expressions-using-imperative-code.md)。</span><span class="sxs-lookup"><span data-stu-id="e48e6-116">For more information, see [Authoring Workflows, Activities, and Expressions Using Imperative Code](../../../docs/framework/windows-workflow-foundation/authoring-workflows-activities-and-expressions-using-imperative-code.md).</span></span>  
  
 <span data-ttu-id="e48e6-117">若要将由 <xref:System.Activities.ActivityBuilder> 实例表示的工作流定义序列化为 XAML，应使用 <xref:System.Activities.XamlIntegration.ActivityXamlServices> 创建 <xref:System.Xaml.XamlWriter>，然后通过 <xref:System.Xaml.XamlServices>，使用 <xref:System.Xaml.XamlWriter> 对工作流定义进行序列化。</span><span class="sxs-lookup"><span data-stu-id="e48e6-117">To serialize the workflow definition represented by the <xref:System.Activities.ActivityBuilder> instance to XAML, use <xref:System.Activities.XamlIntegration.ActivityXamlServices> to create a <xref:System.Xaml.XamlWriter>, and then use <xref:System.Xaml.XamlServices> to serialize the workflow definition by using the <xref:System.Xaml.XamlWriter>.</span></span> <span data-ttu-id="e48e6-118"><xref:System.Activities.XamlIntegration.ActivityXamlServices> 提供一些方法，可以在 <xref:System.Activities.ActivityBuilder> 实例和 XAML 之间进行映射，并可加载 XAML 工作流以及返回可调用的 <xref:System.Activities.DynamicActivity>。</span><span class="sxs-lookup"><span data-stu-id="e48e6-118"><xref:System.Activities.XamlIntegration.ActivityXamlServices> has methods to map <xref:System.Activities.ActivityBuilder> instances to and from XAML, and to load XAML workflows and return a <xref:System.Activities.DynamicActivity> that can be invoked.</span></span> <span data-ttu-id="e48e6-119">在下面的示例中，将上一示例中的 <xref:System.Activities.ActivityBuilder> 实例序列化为一个字符串，并将其保存到一个文件中。</span><span class="sxs-lookup"><span data-stu-id="e48e6-119">In the following example, the <xref:System.Activities.ActivityBuilder> instance from the previous example is serialized to a string, and also saved to a file.</span></span>  
  
```csharp  
// Serialize the workflow to XAML and store it in a string.  
StringBuilder sb = new StringBuilder();  
StringWriter tw = new StringWriter(sb);  
XamlWriter xw = ActivityXamlServices.CreateBuilderWriter(new XamlXmlWriter(tw, new XamlSchemaContext()));  
XamlServices.Save(xw , ab);  
string serializedAB = sb.ToString();  
  
// Display the XAML to the console.  
Console.WriteLine(serializedAB);  
  
// Serialize the workflow to XAML and save it to a file.  
StreamWriter sw = File.CreateText(@"C:\Workflows\add.xaml");  
XamlWriter xw2 = ActivityXamlServices.CreateBuilderWriter(new XamlXmlWriter(sw, new XamlSchemaContext()));  
XamlServices.Save(xw2, ab);  
sw.Close();  
```  
  
 <span data-ttu-id="e48e6-120">下面的示例表示序列化的工作流。</span><span class="sxs-lookup"><span data-stu-id="e48e6-120">The following example represents the serialized workflow.</span></span>  
  
```xaml  
<Activity   
  x:TypeArguments="x:Int32"   
  x:Class="Add"   
  xmlns="http://schemas.microsoft.com/netfx/2009/xaml/activities"   
  xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml">  
  <x:Members>  
    <x:Property Name="Operand1" Type="InArgument(x:Int32)" />  
    <x:Property Name="Operand2" Type="InArgument(x:Int32)" />  
  </x:Members>  
  <Sequence>  
    <WriteLine Text="[Operand1.ToString() + " + " + Operand2.ToString()]" />  
    <Assign x:TypeArguments="x:Int32" Value="[Operand1 + Operand2]">  
      <Assign.To>  
        <OutArgument x:TypeArguments="x:Int32">  
          <ArgumentReference x:TypeArguments="x:Int32" ArgumentName="Result" />  
          </OutArgument>  
      </Assign.To>  
    </Assign>  
  </Sequence>  
</Activity>  
```  
  
 <span data-ttu-id="e48e6-121">若要加载的序列化的工作流， <xref:System.Activities.XamlIntegration.ActivityXamlServices> <xref:System.Activities.XamlIntegration.ActivityXamlServices.Load%2A>使用方法。</span><span class="sxs-lookup"><span data-stu-id="e48e6-121">To load a serialized workflow, the <xref:System.Activities.XamlIntegration.ActivityXamlServices> <xref:System.Activities.XamlIntegration.ActivityXamlServices.Load%2A> method is used.</span></span> <span data-ttu-id="e48e6-122">这将使用序列化的工作流定义，并返回一个表示该工作流定义的 <xref:System.Activities.DynamicActivity>。</span><span class="sxs-lookup"><span data-stu-id="e48e6-122">This takes the serialized workflow definition and returns a <xref:System.Activities.DynamicActivity> that represents the workflow definition.</span></span> <span data-ttu-id="e48e6-123">请注意，在验证过程中对 <xref:System.Activities.Activity.CacheMetadata%2A> 的正文调用 <xref:System.Activities.DynamicActivity> 之前，不对 XAML 进行反序列化。</span><span class="sxs-lookup"><span data-stu-id="e48e6-123">Note that the XAML is not deserialized until <xref:System.Activities.Activity.CacheMetadata%2A> is called on the body of the <xref:System.Activities.DynamicActivity> during the validation process.</span></span> <span data-ttu-id="e48e6-124">如果未显式调用验证，则在调用工作流时执行验证。</span><span class="sxs-lookup"><span data-stu-id="e48e6-124">If validation is not explicitly called then it is performed when the workflow is invoked.</span></span> <span data-ttu-id="e48e6-125">如果 XAML 工作流定义无效，则会引发 <xref:System.ArgumentException> 异常。</span><span class="sxs-lookup"><span data-stu-id="e48e6-125">If the XAML workflow definition is invalid, then an <xref:System.ArgumentException> exception is thrown.</span></span> <span data-ttu-id="e48e6-126">从 <xref:System.Activities.Activity.CacheMetadata%2A> 引发的所有异常均不会导致调用 <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A>，必须由调用方进行处理。</span><span class="sxs-lookup"><span data-stu-id="e48e6-126">Any exceptions thrown from <xref:System.Activities.Activity.CacheMetadata%2A> escape from the call to <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> and must be handled by the caller.</span></span> <span data-ttu-id="e48e6-127">在下面的示例中，将使用 <xref:System.Activities.WorkflowInvoker> 加载并调用上一示例中的序列化的工作流。</span><span class="sxs-lookup"><span data-stu-id="e48e6-127">In the following example, the serialized workflow from the previous example is loaded and invoked by using <xref:System.Activities.WorkflowInvoker>.</span></span>  
  
 [!code-csharp[CFX_WorkflowApplicationExample#43](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#43)]  
  
 <span data-ttu-id="e48e6-128">调用该工作流时，会将以下输出显示到控制台。</span><span class="sxs-lookup"><span data-stu-id="e48e6-128">When this workflow is invoked, the following output is displayed to the console.</span></span>  
  
 <span data-ttu-id="e48e6-129">**25 + 15**</span><span class="sxs-lookup"><span data-stu-id="e48e6-129">**25 + 15**</span></span>  
<span data-ttu-id="e48e6-130">**40**</span><span class="sxs-lookup"><span data-stu-id="e48e6-130">**40**</span></span>    
> [!NOTE]
>  <span data-ttu-id="e48e6-131">有关调用工作流使用输入和输出自变量的详细信息，请参阅[使用 WorkflowInvoker 和 WorkflowApplication](../../../docs/framework/windows-workflow-foundation/using-workflowinvoker-and-workflowapplication.md)和<xref:System.Activities.WorkflowInvoker.Invoke%2A>。</span><span class="sxs-lookup"><span data-stu-id="e48e6-131">For more information about invoking workflows with input and output arguments, see [Using WorkflowInvoker and WorkflowApplication](../../../docs/framework/windows-workflow-foundation/using-workflowinvoker-and-workflowapplication.md) and <xref:System.Activities.WorkflowInvoker.Invoke%2A>.</span></span>  
  
 <span data-ttu-id="e48e6-132">如果序列化的工作流包含 C# 表达式，则<xref:System.Activities.XamlIntegration.ActivityXamlServicesSettings>实例与其<xref:System.Activities.XamlIntegration.ActivityXamlServicesSettings.CompileExpressions%2A>属性设置为`true`必须作为参数传递给传递<xref:System.Activities.XamlIntegration.ActivityXamlServices.Load%2A?displayProperty=nameWithType>，否则为<xref:System.NotSupportedException>将引发类似于的消息以下： `Expression Activity type 'CSharpValue`1 需要编译才能运行。</span><span class="sxs-lookup"><span data-stu-id="e48e6-132">If the serialized workflow contains C# expressions, then an <xref:System.Activities.XamlIntegration.ActivityXamlServicesSettings> instance with its <xref:System.Activities.XamlIntegration.ActivityXamlServicesSettings.CompileExpressions%2A> property set to `true` must be passed as a parameter to <xref:System.Activities.XamlIntegration.ActivityXamlServices.Load%2A?displayProperty=nameWithType>, otherwise a <xref:System.NotSupportedException> will be thrown with a message similar to the following: `Expression Activity type 'CSharpValue`1' requires compilation in order to run.</span></span>  <span data-ttu-id="e48e6-133">请确保已编译工作流。</span><span class="sxs-lookup"><span data-stu-id="e48e6-133">Please ensure that the workflow has been compiled.\`</span></span>  
  
```csharp  
ActivityXamlServicesSettings settings = new ActivityXamlServicesSettings  
{  
    CompileExpressions = true  
};  
  
DynamicActivity<int> wf = ActivityXamlServices.Load(new StringReader(serializedAB), settings) as DynamicActivity<int>;  
```  
  
 <span data-ttu-id="e48e6-134">有关详细信息，请参阅[C# 表达式](../../../docs/framework/windows-workflow-foundation/csharp-expressions.md)。</span><span class="sxs-lookup"><span data-stu-id="e48e6-134">For more information, see [C# Expressions](../../../docs/framework/windows-workflow-foundation/csharp-expressions.md).</span></span>  
  
 <span data-ttu-id="e48e6-135">序列化的工作流定义也可以加载到<xref:System.Activities.ActivityBuilder>实例使用<xref:System.Activities.XamlIntegration.ActivityXamlServices><xref:System.Activities.XamlIntegration.ActivityXamlServices.CreateBuilderReader%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="e48e6-135">A serialized workflow definition can also be loaded into an <xref:System.Activities.ActivityBuilder> instance by using the <xref:System.Activities.XamlIntegration.ActivityXamlServices> <xref:System.Activities.XamlIntegration.ActivityXamlServices.CreateBuilderReader%2A> method.</span></span> <span data-ttu-id="e48e6-136">在将序列化的工作流加载到 <xref:System.Activities.ActivityBuilder> 实例中后，可以对其进行检查和修改。</span><span class="sxs-lookup"><span data-stu-id="e48e6-136">After a serialized workflow is loaded into an <xref:System.Activities.ActivityBuilder> instance it can be inspected and modified.</span></span> <span data-ttu-id="e48e6-137">这对自定义工作流设计器作者很有用，并将提供用于在设计过程中保存和重新加载工作流定义的机制。</span><span class="sxs-lookup"><span data-stu-id="e48e6-137">This is useful for custom workflow designer authors and provides a mechanism for saving and reloading workflow definitions during the design process.</span></span> <span data-ttu-id="e48e6-138">在下面的示例中，将加载上一示例中的序列化的工作流定义并检查其属性。</span><span class="sxs-lookup"><span data-stu-id="e48e6-138">In the following example, the serialized workflow definition from the previous example is loaded and its properties are inspected.</span></span>  
  
 [!code-csharp[CFX_WorkflowApplicationExample#44](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#44)]
