---
title: "使用 DynamicActivity 在运行时创建活动"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1af85cc6-912d-449e-90c5-c5db3eca5ace
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d40fe3601cb8ad7c4f77cf50825da1deace5644e
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="creating-an-activity-at-runtime-with-dynamicactivity"></a><span data-ttu-id="6341e-102">使用 DynamicActivity 在运行时创建活动</span><span class="sxs-lookup"><span data-stu-id="6341e-102">Creating an Activity at Runtime with DynamicActivity</span></span>
<span data-ttu-id="6341e-103"><xref:System.Activities.DynamicActivity> 是一个带有公共构造函数的具体的密封类。</span><span class="sxs-lookup"><span data-stu-id="6341e-103"><xref:System.Activities.DynamicActivity> is a concrete, sealed class with a public constructor.</span></span> <span data-ttu-id="6341e-104">通过使用活动 DOM，<xref:System.Activities.DynamicActivity> 可用于在运行时组合活动功能。</span><span class="sxs-lookup"><span data-stu-id="6341e-104"><xref:System.Activities.DynamicActivity> can be used to assemble activity functionality at runtime using an activity DOM.</span></span>  
  
## <a name="dynamicactivity-features"></a><span data-ttu-id="6341e-105">DynamicActivity 功能</span><span class="sxs-lookup"><span data-stu-id="6341e-105">DynamicActivity Features</span></span>  
 <span data-ttu-id="6341e-106"><xref:System.Activities.DynamicActivity> 有权访问执行属性、参数和变量，但无权访问运行时服务（例如安排子活动或跟踪）。</span><span class="sxs-lookup"><span data-stu-id="6341e-106"><xref:System.Activities.DynamicActivity> has access to execution properties, arguments and variables, but no access to run-time services such as scheduling child activities or tracking.</span></span>  
  
 <span data-ttu-id="6341e-107">使用工作流 <xref:System.Activities.Argument> 对象可以设置顶级属性。</span><span class="sxs-lookup"><span data-stu-id="6341e-107">Top-level properties can be set using workflow <xref:System.Activities.Argument> objects.</span></span> <span data-ttu-id="6341e-108">在命令性代码中，使用新类型的 CLR 属性创建这些参数。</span><span class="sxs-lookup"><span data-stu-id="6341e-108">In imperative code, these arguments are created using CLR properties on a new type.</span></span> <span data-ttu-id="6341e-109">在 XAML 中，使用 `x:Class` 和 `x:Member` 标记声明这些参数。</span><span class="sxs-lookup"><span data-stu-id="6341e-109">In XAML, they are declared using `x:Class` and `x:Member` tags.</span></span>  
  
 <span data-ttu-id="6341e-110">使用 <xref:System.Activities.DynamicActivity> 构造的活动使用 <xref:System.ComponentModel.ICustomTypeDescriptor> 与设计器交互。</span><span class="sxs-lookup"><span data-stu-id="6341e-110">Activities constructed using <xref:System.Activities.DynamicActivity> interface with the designer using <xref:System.ComponentModel.ICustomTypeDescriptor>.</span></span> <span data-ttu-id="6341e-111">可以使用 <xref:System.Activities.XamlIntegration.ActivityXamlServices.Load%2A> 动态加载在设计器中创建的活动，如下面的过程所示。</span><span class="sxs-lookup"><span data-stu-id="6341e-111">Activities created in the designer can be loaded dynamically using <xref:System.Activities.XamlIntegration.ActivityXamlServices.Load%2A>, as demonstrated in the following procedure.</span></span>  
  
#### <a name="to-create-an-activity-at-runtime-using-imperative-code"></a><span data-ttu-id="6341e-112">使用命令性代码在运行时创建活动</span><span class="sxs-lookup"><span data-stu-id="6341e-112">To create an activity at runtime using imperative code</span></span>  
  
1.  <span data-ttu-id="6341e-113">打开 [!INCLUDE[vs2010](../../../includes/vs2010-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="6341e-113">Open[!INCLUDE[vs2010](../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="6341e-114">选择**文件**，**新**，**项目**。</span><span class="sxs-lookup"><span data-stu-id="6341e-114">Select **File**, **New**, **Project**.</span></span> <span data-ttu-id="6341e-115">选择**Workflow 4.0**下**Visual C#**中**项目类型**窗口中，然后选择**v2010**节点。</span><span class="sxs-lookup"><span data-stu-id="6341e-115">Select **Workflow 4.0** under **Visual C#** in the **Project Types** window, and select the **v2010** node.</span></span> <span data-ttu-id="6341e-116">选择**顺序工作流控制台应用程序**中**模板**窗口。</span><span class="sxs-lookup"><span data-stu-id="6341e-116">Select **Sequential Workflow Console Application** in the **Templates** window.</span></span> <span data-ttu-id="6341e-117">将新项目命名为 DynamicActivitySample。</span><span class="sxs-lookup"><span data-stu-id="6341e-117">Name the new project DynamicActivitySample.</span></span>  
  
3.  <span data-ttu-id="6341e-118">右击 HelloActivity 项目中的 Workflow1.xaml，然后选择**删除**。</span><span class="sxs-lookup"><span data-stu-id="6341e-118">Right-click Workflow1.xaml in the HelloActivity project and select **Delete**.</span></span>  
  
4.  <span data-ttu-id="6341e-119">打开 Program.cs。</span><span class="sxs-lookup"><span data-stu-id="6341e-119">Open Program.cs.</span></span> <span data-ttu-id="6341e-120">将下面的指令添加到文件的顶部。</span><span class="sxs-lookup"><span data-stu-id="6341e-120">Add the following directive to the top of the file.</span></span>  
  
    ```  
    using System.Collections.Generic;  
    ```  
  
5.  <span data-ttu-id="6341e-121">将 `Main` 方法的内容替换为以下代码，这会创建一个包含单个 <xref:System.Activities.Statements.Sequence> 活动的 <xref:System.Activities.Statements.WriteLine> 活动，并将后者赋给新动态活动的 <xref:System.Activities.DynamicActivity.Implementation%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="6341e-121">Replace the contents of the `Main` method with the following code, which creates a <xref:System.Activities.Statements.Sequence> activity that contains a single <xref:System.Activities.Statements.WriteLine> activity and assigns it to the <xref:System.Activities.DynamicActivity.Implementation%2A> property of a new dynamic activity.</span></span>  
  
    ```csharp  
    //Define the input argument for the activity  
    var textOut = new InArgument<string>();  
    //Create the activity, property, and implementation  
                Activity dynamicWorkflow = new DynamicActivity()  
                {  
                    Properties =   
                    {  
                        new DynamicActivityProperty  
                        {  
                            Name = "Text",  
                            Type = typeof(InArgument<String>),  
                            Value = textOut  
                        }  
                    },  
                    Implementation = () => new Sequence()  
                    {  
                        Activities =   
                        {  
                            new WriteLine()  
                            {  
                                Text = new InArgument<string>(env => textOut.Get(env))  
                            }  
                        }  
                    }  
                };  
    //Execute the activity with a parameter dictionary  
                WorkflowInvoker.Invoke(dynamicWorkflow, new Dictionary<string, object> { { "Text", "Hello World!" } });  
                Console.ReadLine();  
    ```  
  
6.  <span data-ttu-id="6341e-122">执行应用程序。</span><span class="sxs-lookup"><span data-stu-id="6341e-122">Execute the application.</span></span> <span data-ttu-id="6341e-123">具有文本"Hello World ！"的控制台窗口</span><span class="sxs-lookup"><span data-stu-id="6341e-123">A console window with the text "Hello World!"</span></span> <span data-ttu-id="6341e-124">显示。</span><span class="sxs-lookup"><span data-stu-id="6341e-124">displays.</span></span>  
  
#### <a name="to-create-an-activity-at-runtime-using-xaml"></a><span data-ttu-id="6341e-125">使用 XAML 在运行时创建活动</span><span class="sxs-lookup"><span data-stu-id="6341e-125">To create an activity at runtime using XAML</span></span>  
  
1.  <span data-ttu-id="6341e-126">打开 [!INCLUDE[vs2010](../../../includes/vs2010-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="6341e-126">Open [!INCLUDE[vs2010](../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="6341e-127">选择**文件**，**新**，**项目**。</span><span class="sxs-lookup"><span data-stu-id="6341e-127">Select **File**, **New**, **Project**.</span></span> <span data-ttu-id="6341e-128">选择**Workflow 4.0**下**Visual C#**中**项目类型**窗口中，然后选择**v2010**节点。</span><span class="sxs-lookup"><span data-stu-id="6341e-128">Select **Workflow 4.0** under **Visual C#** in the **Project Types** window, and select the **v2010** node.</span></span> <span data-ttu-id="6341e-129">选择**工作流控制台应用程序**中**模板**窗口。</span><span class="sxs-lookup"><span data-stu-id="6341e-129">Select  **Workflow Console Application** in the **Templates** window.</span></span> <span data-ttu-id="6341e-130">将新项目命名为 DynamicActivitySample。</span><span class="sxs-lookup"><span data-stu-id="6341e-130">Name the new project DynamicActivitySample.</span></span>  
  
3.  <span data-ttu-id="6341e-131">在 HelloActivity 项目中打开 Workflow1.xaml。</span><span class="sxs-lookup"><span data-stu-id="6341e-131">Open Workflow1.xaml in the HelloActivity project.</span></span> <span data-ttu-id="6341e-132">单击**参数**设计器底部的选项。</span><span class="sxs-lookup"><span data-stu-id="6341e-132">Click the **Arguments** option at the bottom of the designer.</span></span> <span data-ttu-id="6341e-133">创建一个 `In` 类型的新 `TextToWrite` 参数，并将其命名为 `String`。</span><span class="sxs-lookup"><span data-stu-id="6341e-133">Create a new `In` argument called `TextToWrite` of type `String`.</span></span>  
  
4.  <span data-ttu-id="6341e-134">拖动**WriteLine**活动从**基元**一部分工具箱中拖动到设计器图面。</span><span class="sxs-lookup"><span data-stu-id="6341e-134">Drag a **WriteLine** activity from the **Primitives** section of the toolbox onto the designer surface.</span></span> <span data-ttu-id="6341e-135">将值分配`TextToWrite`到**文本**的活动的属性。</span><span class="sxs-lookup"><span data-stu-id="6341e-135">Assign the value `TextToWrite` to the **Text** property of the activity.</span></span>  
  
5.  <span data-ttu-id="6341e-136">打开 Program.cs。</span><span class="sxs-lookup"><span data-stu-id="6341e-136">Open Program.cs.</span></span> <span data-ttu-id="6341e-137">将下面的指令添加到文件的顶部。</span><span class="sxs-lookup"><span data-stu-id="6341e-137">Add the following directive to the top of the file.</span></span>  
  
    ```  
    using System.Activities.XamlIntegration;  
    ```  
  
6.  <span data-ttu-id="6341e-138">将 `Main` 方法的内容替换为以下代码。</span><span class="sxs-lookup"><span data-stu-id="6341e-138">Replace the contents of the `Main` method with the following code.</span></span>  
  
    ```  
    Activity act2 = ActivityXamlServices.Load(@"Workflow1.xaml");  
                    results = WorkflowInvoker.Invoke(act2, new Dictionary<string, object> { { "TextToWrite", "HelloWorld!" } });  
    Console.ReadLine();  
    ```  
  
7.  <span data-ttu-id="6341e-139">执行应用程序。</span><span class="sxs-lookup"><span data-stu-id="6341e-139">Execute the application.</span></span> <span data-ttu-id="6341e-140">具有文本"Hello World ！"的控制台窗口</span><span class="sxs-lookup"><span data-stu-id="6341e-140">A console window with the text "Hello World!"</span></span> <span data-ttu-id="6341e-141">将出现。</span><span class="sxs-lookup"><span data-stu-id="6341e-141">appears.</span></span>  
  
8.  <span data-ttu-id="6341e-142">右击 Workflow1.xaml 文件中的**解决方案资源管理器**和选择**查看代码**。</span><span class="sxs-lookup"><span data-stu-id="6341e-142">Right-click the Workflow1.xaml file in the **Solution Explorer** and select **View Code**.</span></span> <span data-ttu-id="6341e-143">请注意，活动类使用 `x:Class` 创建，属性使用 `x:Property` 创建。</span><span class="sxs-lookup"><span data-stu-id="6341e-143">Note that the activity class is created with `x:Class` and the property is created with `x:Property`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6341e-144">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6341e-144">See Also</span></span>  
 [<span data-ttu-id="6341e-145">使用强制性代码创建工作流、活动和表达式</span><span class="sxs-lookup"><span data-stu-id="6341e-145">Authoring Workflows, Activities, and Expressions Using Imperative Code</span></span>](../../../docs/framework/windows-workflow-foundation/authoring-workflows-activities-and-expressions-using-imperative-code.md)  
 [<span data-ttu-id="6341e-146">DynamicActivity 创建</span><span class="sxs-lookup"><span data-stu-id="6341e-146">DynamicActivity Creation</span></span>](../../../docs/framework/windows-workflow-foundation/samples/dynamicactivity-creation.md)
