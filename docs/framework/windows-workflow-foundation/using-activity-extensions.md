---
title: 使用活动扩展
ms.date: 03/30/2017
ms.assetid: 500eb96a-c009-4247-b6b5-b36faffdf715
ms.openlocfilehash: 32c465ae42a1f0238fab7bba5ea795486db3b562
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33517220"
---
# <a name="using-activity-extensions"></a><span data-ttu-id="a3560-102">使用活动扩展</span><span class="sxs-lookup"><span data-stu-id="a3560-102">Using Activity Extensions</span></span>
<span data-ttu-id="a3560-103">活动可与工作流应用程序扩展进行交互，这些扩展允许主机提供未在工作流中显式建模的其他功能。</span><span class="sxs-lookup"><span data-stu-id="a3560-103">Activities can interact with workflow application extensions that allow the host to provide additional functionality that is not explicitly modeled in the workflow.</span></span>  <span data-ttu-id="a3560-104">本主题描述如何创建和使用扩展以计算活动的执行次数。</span><span class="sxs-lookup"><span data-stu-id="a3560-104">This topic describes how to create and use an extension to count the number of times the activity executes.</span></span>  
  
### <a name="to-use-an-activity-extension-to-count-executions"></a><span data-ttu-id="a3560-105">使用活动扩展来计算执行次数</span><span class="sxs-lookup"><span data-stu-id="a3560-105">To use an activity extension to count executions</span></span>  
  
1.  <span data-ttu-id="a3560-106">打开 [!INCLUDE[vs2010](../../../includes/vs2010-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="a3560-106">Open [!INCLUDE[vs2010](../../../includes/vs2010-md.md)].</span></span> <span data-ttu-id="a3560-107">选择**新**，**项目**。</span><span class="sxs-lookup"><span data-stu-id="a3560-107">Select **New**, **Project**.</span></span> <span data-ttu-id="a3560-108">下**Visual C#** 节点中，选择**工作流**。</span><span class="sxs-lookup"><span data-stu-id="a3560-108">Under the **Visual C#** node, select **Workflow**.</span></span>  <span data-ttu-id="a3560-109">选择**工作流控制台应用程序**从模板列表中。</span><span class="sxs-lookup"><span data-stu-id="a3560-109">Select **Workflow Console Application** from the list of templates.</span></span> <span data-ttu-id="a3560-110">将项目命名为 `Extensions`。</span><span class="sxs-lookup"><span data-stu-id="a3560-110">Name the project `Extensions`.</span></span> <span data-ttu-id="a3560-111">单击“确定”，创建项目。</span><span class="sxs-lookup"><span data-stu-id="a3560-111">Click **OK** to create the project.</span></span>  
  
2.  <span data-ttu-id="a3560-112">添加`using`的 Program.cs 文件中的语句**System.Collections.Generic**命名空间。</span><span class="sxs-lookup"><span data-stu-id="a3560-112">Add a `using` statement in the Program.cs file for the **System.Collections.Generic** namespace.</span></span>  
  
    ```  
    using System.Collections.Generic;  
    ```  
  
3.  <span data-ttu-id="a3560-113">在 Program.cs 文件中，创建一个名为的新类**ExecutionCountExtension**。</span><span class="sxs-lookup"><span data-stu-id="a3560-113">In the Program.cs file, create a new class named **ExecutionCountExtension**.</span></span> <span data-ttu-id="a3560-114">下面的代码创建跟踪实例 Id 的工作流扩展时其**注册**调用方法。</span><span class="sxs-lookup"><span data-stu-id="a3560-114">The following code creates a workflow extension that tracks instance IDs when its **Register** method is called.</span></span>  
  
    ```  
    // This extension collects a list of workflow Ids  
    public class ExecutionCountExtension  
    {  
        IList<Guid> instances = new List<Guid>();  
  
        public int ExecutionCount  
        {  
            get  
            {  
                return this.instances.Count;  
            }  
        }  
  
        public IEnumerable<Guid> InstanceIds  
        {  
            get  
            {  
                return this.instances;  
            }  
        }  
  
        public void Register(Guid activityInstanceId)  
        {  
            if (!this.instances.Contains<Guid>(activityInstanceId))  
            {  
                instances.Add(activityInstanceId);  
            }  
        }  
    }  
    ```  
  
4.  <span data-ttu-id="a3560-115">创建使用活动**ExecutionCountExtension**。</span><span class="sxs-lookup"><span data-stu-id="a3560-115">Create an activity that consumes the **ExecutionCountExtension**.</span></span> <span data-ttu-id="a3560-116">下面的代码定义一个活动，检索**ExecutionCountExtension**对象的运行时和调用其**注册**方法执行活动时。</span><span class="sxs-lookup"><span data-stu-id="a3560-116">The following code defines an activity that retrieves the **ExecutionCountExtension** object from the runtime and calls its **Register** method when the activity executes.</span></span>  
  
    ```  
    // Activity that consumes an extension provided by the host. If the extension is available  
    // in the context, it will invoke (in this case, registers the Id of the executing workflow)  
    public class MyActivity: CodeActivity  
    {  
        protected override void Execute(CodeActivityContext context)  
        {  
            ExecutionCountExtension ext = context.GetExtension<ExecutionCountExtension>();  
            if (ext != null)  
            {  
                ext.Register(context.WorkflowInstanceId);                         
            }  
  
        }  
    }  
    ```  
  
5.  <span data-ttu-id="a3560-117">中实现该活动**Main** program.cs 文件的方法。</span><span class="sxs-lookup"><span data-stu-id="a3560-117">Implement the activity in the **Main** method of the program.cs file.</span></span> <span data-ttu-id="a3560-118">以下代码包含用于生成两个不同的工作流、将每个工作流执行多次以及显示扩展中包含的结果数据的方法。</span><span class="sxs-lookup"><span data-stu-id="a3560-118">The following code contains methods to generate two different workflows, execute each workflow several times, and display the resulting data that is contained in the extension.</span></span>  
  
    ```  
    class Program  
    {  
        // Creates a workflow that uses the activity that consumes the extension  
        static Activity CreateWorkflow1()  
        {  
            return new Sequence  
            {  
                Activities =  
                {  
                    new MyActivity()  
                }  
            };  
        }  
  
        // Creates a workflow that uses two instances of the activity that consumes the extension  
        static Activity CreateWorkflow2()  
        {  
            return new Sequence  
            {  
                Activities =  
                {  
                    new MyActivity(),  
                    new MyActivity()  
                }  
            };  
        }  
  
        static void Main(string[] args)  
        {  
            // create the extension   
            ExecutionCountExtension executionCountExt = new ExecutionCountExtension();  
  
            // configure the first invoker and execute 3 times  
            WorkflowInvoker invoker = new WorkflowInvoker(CreateWorkflow1());  
            invoker.Extensions.Add(executionCountExt);                          
            invoker.Invoke();  
            invoker.Invoke();  
            invoker.Invoke();  
  
            // configure the second invoker and execute 2 times  
            WorkflowInvoker invoker2 = new WorkflowInvoker(CreateWorkflow2());  
            invoker2.Extensions.Add(executionCountExt);  
            invoker2.Invoke();  
            invoker2.Invoke();  
  
            // show the data in the extension  
            Console.WriteLine("Executed {0} times", executionCountExt.ExecutionCount);  
            executionCountExt.InstanceIds.ToList().ForEach(i => Console.WriteLine("...{0}", i));  
        }  
    }  
    ```
