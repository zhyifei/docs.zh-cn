---
title: "LINQ to Objects 活动"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 403c82e8-7f2b-42f6-93cd-95c35bc76ead
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 811ffe44a65dea13482d600a09989ce42f6580dd
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="linq-to-objects-activity"></a><span data-ttu-id="5b088-102">LINQ to Objects 活动</span><span class="sxs-lookup"><span data-stu-id="5b088-102">LINQ to Objects Activity</span></span>
<span data-ttu-id="5b088-103">此示例演示如何创建活动以使用 LINQ to Objects 查询集合中的元素。</span><span class="sxs-lookup"><span data-stu-id="5b088-103">This sample demonstrates how to create an activity to use LINQ to Objects to query elements in a collection.</span></span>  
  
## <a name="activity-details-for-findincollection"></a><span data-ttu-id="5b088-104">FindInCollection 的活动详细信息</span><span class="sxs-lookup"><span data-stu-id="5b088-104">Activity Details for FindInCollection</span></span>  
 <span data-ttu-id="5b088-105">此活动允许用户使用 LINQ to Objects 查询内存中集合的元素。</span><span class="sxs-lookup"><span data-stu-id="5b088-105">This activity allows users to query elements from collections in memory using LINQ to Objects.</span></span> <span data-ttu-id="5b088-106">您必须提供 lambda 表达式形式的 LINQ 谓词以筛选结果。</span><span class="sxs-lookup"><span data-stu-id="5b088-106">You must provide a LINQ predicate in the form of a lambda expression to filter the results.</span></span> <span data-ttu-id="5b088-107">可将此活动与 <xref:System.Activities.Statements.AddToCollection%601> 活动一起使用。</span><span class="sxs-lookup"><span data-stu-id="5b088-107">This activity can be used in conjunction with <xref:System.Activities.Statements.AddToCollection%601> activities.</span></span>  
  
 <span data-ttu-id="5b088-108">下表详述了此活动的属性和返回值。</span><span class="sxs-lookup"><span data-stu-id="5b088-108">The following table details the property and return values for the activity.</span></span>  
  
|<span data-ttu-id="5b088-109">属性或返回值</span><span class="sxs-lookup"><span data-stu-id="5b088-109">Property or Return Value</span></span>|<span data-ttu-id="5b088-110">描述</span><span class="sxs-lookup"><span data-stu-id="5b088-110">Description</span></span>|  
|------------------------------|-----------------|  
|<span data-ttu-id="5b088-111">`Collection` 属性</span><span class="sxs-lookup"><span data-stu-id="5b088-111">`Collection` property</span></span>|<span data-ttu-id="5b088-112">必需属性，用于指定源集合。</span><span class="sxs-lookup"><span data-stu-id="5b088-112">A required property that specifies the source collection.</span></span>|  
|<span data-ttu-id="5b088-113">`Predicate` 属性</span><span class="sxs-lookup"><span data-stu-id="5b088-113">`Predicate` property</span></span>|<span data-ttu-id="5b088-114">必需属性，用于指定 lambda 表达式形式的集合筛选器。</span><span class="sxs-lookup"><span data-stu-id="5b088-114">A required property that specifies the filter for the collection in the form of a lambda expression.</span></span>|  
|<span data-ttu-id="5b088-115">返回值</span><span class="sxs-lookup"><span data-stu-id="5b088-115">Return Value</span></span>|<span data-ttu-id="5b088-116">经过筛选的集合。</span><span class="sxs-lookup"><span data-stu-id="5b088-116">The filtered collection.</span></span>|  
  
## <a name="code-sample-that-uses-the-custom-activity"></a><span data-ttu-id="5b088-117">使用自定义活动的代码示例</span><span class="sxs-lookup"><span data-stu-id="5b088-117">Code Sample that uses the Custom Activity</span></span>  
 <span data-ttu-id="5b088-118">下面的代码示例使用 `FindInCollection` 自定义活动查找员工集合中的所有行，这些员工的 `Role` 属性设置为 `Manager`，`Location` 属性设置为 `Redmond`。</span><span class="sxs-lookup"><span data-stu-id="5b088-118">The following code example uses the `FindInCollection` custom activity to find all rows in a collection of employees that have a `Role` property set to `Manager` and the `Location` property set to `Redmond`.</span></span>  
  
```csharp  
// Find all program managers in Redmond in the employees collection.  
  
Activity wf = new FindInCollection<Employee>  
{  
    Collections = new LambdaValue<IEnumerable<Employee>>(c => employees),                
    Predicate = new LambdaValue<Func<Employee, bool>>(c => new Func<Employee, bool>(e => e.Role.Equals("Manager") && e.Location.Equals("Redmond")))  
};  
```  
  
 <span data-ttu-id="5b088-119">下面的代码演示如何创建一个工作流程序，此程序使用自定义 FindInCollection 活动、<xref:System.Activities.Statements.AddToCollection%601> 和 <xref:System.Activities.Statements.ForEach%601> 活动，在集合中填入员工，查找 Redmond 市角色为开发人员的所有员工，然后循环访问结果列表。</span><span class="sxs-lookup"><span data-stu-id="5b088-119">The following code shows how to create a workflow program that uses the custom FindInCollection activity, <xref:System.Activities.Statements.AddToCollection%601>, and <xref:System.Activities.Statements.ForEach%601> activities to populate a collection with employees, find all the employees that have developer roles and are located in Redmond, and then iterate through the resulting list.</span></span>  
  
```csharp  
// Create the Linq predicate for the find expression  
  
Func<Employee, bool> predicate = e => e.Role == "DEV" && e.Location.Equals("Redmond");  
  
// Create workflow program  
Activity sampleWorkflow = new Sequence  
{  
    Variables = { employees, devsFromRedmond },  
    Activities =  
    {  
        new Assign<IList<Employee>>  
        {  
            To = employees,  
            Value = new LambdaValue<IList<Employee>>(c => new List<Employee>())  
        },  
        new AddToCollection<Employee>  
        {  
            Collection = new InArgument<ICollection<Employee>>(employees),  
            Item =  new LambdaValue<Employee>(c => new Employee(1, "Employee 1", "DEV", "Redmond"))  
        },  
        new AddToCollection<Employee>  
        {  
            Collection = new InArgument<ICollection<Employee>>(employees),  
            Item =  new LambdaValue<Employee>(c => new Employee(2, "Employee 2", "DEV", "Redmond"))  
        },  
        new AddToCollection<Employee>  
        {  
            Collection = new InArgument<ICollection<Employee>>(employees),  
            Item =  new LambdaValue<Employee>(c => new Employee(3, "Employee 3", "PM", "Redmond"))  
        },  
        new AddToCollection<Employee>  
        {  
            Collection = new InArgument<ICollection<Employee>>(employees),  
            Item =  new LambdaValue<Employee>(c => new Employee(4, "Employee 4", "PM", "China"))  
        },  
        new FindInCollection<Employee>  
        {  
            Collections = new InArgument<IEnumerable<Employee>>(employees),  
            Predicate = new LambdaValue<Func<Employee, bool>>(c => predicate),  
            Result = new OutArgument<IList<Employee>>(devsFromRedmond)  
        },  
        new ForEach<Employee>  
        {  
            Values = new InArgument<IEnumerable<Employee>>(devsFromRedmond),  
            Body = new ActivityAction<Employee>  
            {  
                Argument = iterationVariable,  
                Handler = new WriteLine  
                {  
                    Text = new InArgument<string>(env => iterationVariable.Get(env).ToString())  
                }  
            }  
        }  
    }  
};  
```  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="5b088-120">使用此示例</span><span class="sxs-lookup"><span data-stu-id="5b088-120">To use this sample</span></span>  
  
1.  <span data-ttu-id="5b088-121">使用 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 打开 LinqToObjects.sln 解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="5b088-121">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the LinqToObjects.sln solution file.</span></span>  
  
2.  <span data-ttu-id="5b088-122">要生成解决方案，按 Ctrl+Shift+B。</span><span class="sxs-lookup"><span data-stu-id="5b088-122">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="5b088-123">若要运行解决方案，请按 F5。</span><span class="sxs-lookup"><span data-stu-id="5b088-123">To run the solution, press F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="5b088-124">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="5b088-124">The samples may already be installed on your machine.</span></span> <span data-ttu-id="5b088-125">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="5b088-125">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="5b088-126">如果此目录不存在，请访问 [针对 .NET Framework 4 的 Windows Communication Foundation (WCF) 和 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780) 以下载所有 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 示例。</span><span class="sxs-lookup"><span data-stu-id="5b088-126">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="5b088-127">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="5b088-127">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\Linq\LinqToObjects`  
  
## <a name="see-also"></a><span data-ttu-id="5b088-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5b088-128">See Also</span></span>  
 [<span data-ttu-id="5b088-129">Lambda 表达式 （C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="5b088-129">Lambda Expressions (C# Programming Guide)</span></span>](http://go.microsoft.com/fwlink/?LinkId=150381)  
 [<span data-ttu-id="5b088-130">LINQ to Objects</span><span class="sxs-lookup"><span data-stu-id="5b088-130">LINQ to Objects</span></span>](http://go.microsoft.com/fwlink/?LinkID=150380)
