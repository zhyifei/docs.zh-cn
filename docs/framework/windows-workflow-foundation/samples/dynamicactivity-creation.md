---
title: DynamicActivity 创建
ms.date: 03/30/2017
ms.assetid: d8ebe82f-98c8-4452-aed7-2c60a512b097
ms.openlocfilehash: 270066fafd5c71b2a720ca305433159c172872aa
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/01/2018
ms.locfileid: "43385256"
---
# <a name="dynamicactivity-creation"></a><span data-ttu-id="42323-102">DynamicActivity 创建</span><span class="sxs-lookup"><span data-stu-id="42323-102">DynamicActivity Creation</span></span>
<span data-ttu-id="42323-103">此示例演示在运行时使用 <xref:System.Activities.DynamicActivity> 活动来创建活动的两种不同方式。</span><span class="sxs-lookup"><span data-stu-id="42323-103">This sample demonstrates two different ways to create an activity at runtime using the <xref:System.Activities.DynamicActivity> activity.</span></span>  
  
 <span data-ttu-id="42323-104">在此示例中，在运行时使用包含 <xref:System.Activities.Statements.Sequence> 活动（该活动包含 <xref:System.Activities.Statements.ForEach%601> 和 <xref:System.Activities.Statements.Assign%601> 活动）的主体创建一个活动。</span><span class="sxs-lookup"><span data-stu-id="42323-104">In this sample, an activity is created at runtime with a body that contains a <xref:System.Activities.Statements.Sequence> activity that contains <xref:System.Activities.Statements.ForEach%601> and <xref:System.Activities.Statements.Assign%601> activities.</span></span> <span data-ttu-id="42323-105">将一个整数输入列表传递到该活动中，并将其设置为一个属性。</span><span class="sxs-lookup"><span data-stu-id="42323-105">An input list of integers is passed into the activity and set as a property.</span></span> <span data-ttu-id="42323-106">然后 <xref:System.Activities.Statements.ForEach%601> 活动循环访问值列表并累积值。</span><span class="sxs-lookup"><span data-stu-id="42323-106">The <xref:System.Activities.Statements.ForEach%601> activity then iterates over the list of values and accumulates it.</span></span> <span data-ttu-id="42323-107">在 <xref:System.Activities.Statements.Assign%601> 活动中，通过将累积值除以列表中的元素数量来计算平均值，并将此值赋给平均值变量。</span><span class="sxs-lookup"><span data-stu-id="42323-107">In the <xref:System.Activities.Statements.Assign%601> activity, the average value is calculated by dividing the accumulator by the number of elements in the list and assign it to the average.</span></span>  
  
 <span data-ttu-id="42323-108">此示例演示如何使用 <xref:System.Activities.DynamicActivity> 活动，该活动流入变量作为输入参数，并流入返回值作为输出参数。</span><span class="sxs-lookup"><span data-stu-id="42323-108">The sample demonstrates the usage of a <xref:System.Activities.DynamicActivity> activity that flows in variables as input arguments and returning values as output arguments.</span></span> <span data-ttu-id="42323-109">该活动具有一个名为 `Numbers` 的输入参数，该参数是一个整数列表。</span><span class="sxs-lookup"><span data-stu-id="42323-109">The activity has one input argument named `Numbers` that is a list of integers.</span></span> <span data-ttu-id="42323-110"><xref:System.Activities.Statements.ForEach%601> 活动循环访问值列表并累积值。</span><span class="sxs-lookup"><span data-stu-id="42323-110">The <xref:System.Activities.Statements.ForEach%601> activity iterates over the list of values and accumulates it.</span></span> <span data-ttu-id="42323-111">在 <xref:System.Activities.Statements.Assign%601> 活动中，通过累积值除以列表中的元素数量来计算平均值，并将此值赋给平均值变量。</span><span class="sxs-lookup"><span data-stu-id="42323-111">In the <xref:System.Activities.Statements.Assign%601> activity, the average value is calculated by dividing the accumulator by the number of elements in the list and assigning it to the average.</span></span> <span data-ttu-id="42323-112">平均值作为一个名为 `Average` 的输出参数返回。</span><span class="sxs-lookup"><span data-stu-id="42323-112">The average is returned as an output argument named `Average`.</span></span>  
  
 <span data-ttu-id="42323-113">通过编程方式创建动态活动时，按下面的代码示例中所示声明输入和输出。</span><span class="sxs-lookup"><span data-stu-id="42323-113">When the dynamic activity is created programmatically, the input and output are declared as shown in the following code example.</span></span>  
  
```csharp  
DynamicActivity act = new DynamicActivity()  
{  
    DisplayName = "Find average",  
    Properties =   
    {  
        // Input argument  
        new DynamicActivityProperty  
        {  
            Name = "Numbers",  
            Type = typeof(InArgument<List<int>>),  
            Value = numbers  
        },  
        // Output argument  
        new DynamicActivityProperty  
        {  
            Name = "Average",  
            Type = typeof(OutArgument<double>),  
            Value = average  
        }  
    },  
};  
```  
  
 <span data-ttu-id="42323-114">下面的代码示例演示用于计算列表中值的平均值的 `DynamicActivity` 的完整定义。</span><span class="sxs-lookup"><span data-stu-id="42323-114">The following code example shows the complete definition of the `DynamicActivity` that computes the average of the values in a list.</span></span>  
  
```  
DynamicActivity act = new DynamicActivity()  
{  
    DisplayName = "Find average",  
    Properties =   
    {  
        // Input argument  
        new DynamicActivityProperty  
        {  
            Name = "Numbers",  
            Type = typeof(InArgument<List<int>>),  
            Value = numbers  
        },  
        // Output argument  
        new DynamicActivityProperty  
        {  
            Name = "Average",  
            Type = typeof(OutArgument<double>),  
            Value = average  
        }  
    },  
    Implementation = () =>  
        new Sequence  
        {  
            Variables = { result, accumulator },  
            Activities =  
            {  
                new ForEach<int>  
                {  
                    Values =  new ArgumentValue<IEnumerable<int>> { ArgumentName = "Numbers" },                                  
                    Body = new ActivityAction<int>  
                    {  
                        Argument = iterationVariable,  
                        Handler = new Assign<int>  
                        {  
                            To = accumulator,  
                            Value = new InArgument<int>(env => iterationVariable.Get(env) +  accumulator.Get(env))  
                        }  
                    }  
                },  
  
                // Calculate the average and assign to the output argument.  
                new Assign<double>  
                {  
                    To = new ArgumentReference<double> { ArgumentName = "Average" },  
                    Value = new InArgument<double>(env => accumulator.Get(env) / numbers.Get(env).Count<int>())  
                },  
            }  
        }  
};  
```  
  
 <span data-ttu-id="42323-115">通过 XAML 创建动态活动时，按下面的代码示例中所示声明输入和输出。</span><span class="sxs-lookup"><span data-stu-id="42323-115">When created in XAML, the input and output are declared as shown in the following example.</span></span>  
  
```xml  
<Activity x:Class="Microsoft.Samples.DynamicActivityCreation.FindAverage"  
          xmlns="http://schemas.microsoft.com/netfx/2009/xaml/activities"  
          xmlns:scg="clr-namespace:System.Collections.Generic;assembly=mscorlib"  
          xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml">  
  <x:Members>  
    <x:Property Name="Numbers" Type="InArgument(scg:List(x:Int32))" />  
    <x:Property Name="Average" Type="OutArgument(x:Double)" />  
  </x:Members>  
    ...  
    ...  
</Activity>  
```  
  
 <span data-ttu-id="42323-116">可使用 [!INCLUDE[wfd1](../../../../includes/wfd1-md.md)] 以可视化方式创建 XAML。</span><span class="sxs-lookup"><span data-stu-id="42323-116">The XAML can be created visually using the [!INCLUDE[wfd1](../../../../includes/wfd1-md.md)].</span></span> <span data-ttu-id="42323-117">如果它包含 Visual Studio 项目中，请务必设置其"生成操作"为"None"以防止它正在编译。</span><span class="sxs-lookup"><span data-stu-id="42323-117">If it is included in a Visual Studio project, be sure to set its "Build Action" to "None" to prevent it from being compiled.</span></span> <span data-ttu-id="42323-118">然后可以使用以下调用动态加载 XAML。</span><span class="sxs-lookup"><span data-stu-id="42323-118">The XAML can then be loaded dynamically using the following call.</span></span>  
  
```  
Activity act2 = ActivityXamlServices.Load(@"FindAverage.xaml");  
```  
  
 <span data-ttu-id="42323-119">可按照下面的代码示例中所示，可以使用通过编程方式或通过加载 XAML 工作流创建的 <xref:System.Activities.DynamicActivity> 实例。</span><span class="sxs-lookup"><span data-stu-id="42323-119">The <xref:System.Activities.DynamicActivity> instance created programmatically or through loading a XAML workflow can be used as shown in the following code example.</span></span> <span data-ttu-id="42323-120">请注意，传递到`WorkflowInvoker.Invoke`是一种"操作"<xref:System.Activities.Activity>第一个代码示例中定义。</span><span class="sxs-lookup"><span data-stu-id="42323-120">Please note that "act" passed to the `WorkflowInvoker.Invoke` is the "act" <xref:System.Activities.Activity> defined in the first code example.</span></span>  
  
```  
IDictionary<string, object> results = WorkflowInvoker.Invoke(act, new Dictionary<string, object> { { "Numbers", numbers } });  
  
Console.WriteLine("The average calculated using the code activity is = " + results["Average"]);  
```  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="42323-121">使用此示例</span><span class="sxs-lookup"><span data-stu-id="42323-121">To use this sample</span></span>  
  
1.  <span data-ttu-id="42323-122">使用 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 打开 DynamicActivityCreation.sln 解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="42323-122">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the DynamicActivityCreation.sln solution file.</span></span>  
  
2.  <span data-ttu-id="42323-123">要生成解决方案，按 Ctrl+Shift+B。</span><span class="sxs-lookup"><span data-stu-id="42323-123">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="42323-124">若要运行解决方案，请按 Ctrl+F5。</span><span class="sxs-lookup"><span data-stu-id="42323-124">To run the solution, press CTRL+F5.</span></span>  
  
## <a name="command-line-arguments"></a><span data-ttu-id="42323-125">命令行参数</span><span class="sxs-lookup"><span data-stu-id="42323-125">Command line arguments</span></span>  
 <span data-ttu-id="42323-126">此示例接受命令行参数。</span><span class="sxs-lookup"><span data-stu-id="42323-126">This sample accepts command line arguments.</span></span> <span data-ttu-id="42323-127">用户可以为活动提供一个数字列表来计算其平均值。</span><span class="sxs-lookup"><span data-stu-id="42323-127">Users can provide a list of numbers for the activity to calculate their average.</span></span> <span data-ttu-id="42323-128">要使用的数字列表以由空格分隔的数字列表的形式进行传递。</span><span class="sxs-lookup"><span data-stu-id="42323-128">The list of numbers to be used is passed as a list of numbers separated by a space.</span></span> <span data-ttu-id="42323-129">例如，若要计算 5、10 和 32 的平均值，请使用下面的命令行调用此示例。</span><span class="sxs-lookup"><span data-stu-id="42323-129">For example, to calculate the average of 5, 10, and 32 invoke the sample using the following command line.</span></span>  
  
 <span data-ttu-id="42323-130">**DynamicActivityCreation 5 10 32**</span><span class="sxs-lookup"><span data-stu-id="42323-130">**DynamicActivityCreation 5 10 32**</span></span>  
> [!IMPORTANT]
>  <span data-ttu-id="42323-131">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="42323-131">The samples may already be installed on your machine.</span></span> <span data-ttu-id="42323-132">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="42323-132">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="42323-133">如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](https://go.microsoft.com/fwlink/?LinkId=150780)若要下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。</span><span class="sxs-lookup"><span data-stu-id="42323-133">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="42323-134">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="42323-134">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\DynamicActivity\DynamicActivityCreation`