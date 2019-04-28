---
title: 工作流执行属性
ms.date: 03/30/2017
ms.assetid: a50e088e-3a45-4267-bd51-1a3e6c2d246d
ms.openlocfilehash: 0f87e58a034cbc11565fc74347e6b4362952093c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61669376"
---
# <a name="workflow-execution-properties"></a><span data-ttu-id="0aa76-102">工作流执行属性</span><span class="sxs-lookup"><span data-stu-id="0aa76-102">Workflow Execution Properties</span></span>
<span data-ttu-id="0aa76-103">通过线程本地存储区 (TLS)，CLR 可为每个线程维护一个执行上下文。</span><span class="sxs-lookup"><span data-stu-id="0aa76-103">Through thread local storage (TLS), the CLR maintains an execution context for each thread.</span></span> <span data-ttu-id="0aa76-104">此执行上下文管理已知的线程属性，例如，线程标识、环境事务、当前权限集以及用户定义的线程属性（如已命名的槽）。</span><span class="sxs-lookup"><span data-stu-id="0aa76-104">This execution context governs well-known thread properties such as the thread identity, the ambient transaction, and the current permission set in addition to user-defined thread properties like named slots.</span></span>  
  
 <span data-ttu-id="0aa76-105">与直接以 CLR 为目标的程序不同，工作流程序是在线程不可知的环境中执行的以分层形式确定范围的活动树。</span><span class="sxs-lookup"><span data-stu-id="0aa76-105">Unlike programs directly targeting the CLR, workflow programs are hierarchically scoped trees of activities that execute in a thread-agnostic environment.</span></span> <span data-ttu-id="0aa76-106">这意味着标准的 TLS 机制无法直接用于确定给定工作项范围所在的上下文。</span><span class="sxs-lookup"><span data-stu-id="0aa76-106">This implies that the standard TLS mechanisms cannot directly be used to determine what context is in scope for a given work item.</span></span> <span data-ttu-id="0aa76-107">例如，两个并行的执行分支可能使用不同的事务，但计划程序可能会在同一 CLR 线程上交错执行这两个分支。</span><span class="sxs-lookup"><span data-stu-id="0aa76-107">For example, two parallel branches of execution might use different transactions, yet the scheduler might interleave their execution on the same CLR thread.</span></span>  
  
 <span data-ttu-id="0aa76-108">工作流执行属性提供向活动环境添加上下文特定属性的机制。</span><span class="sxs-lookup"><span data-stu-id="0aa76-108">Workflow execution properties provide a mechanism to add context specific properties to an activity’s environment.</span></span> <span data-ttu-id="0aa76-109">这将允许活动声明哪些属性在其子树范围内，并且还提供了用于设置和关闭 TLS 以与 CLR 对象正确交互的挂钩。</span><span class="sxs-lookup"><span data-stu-id="0aa76-109">This allows an activity to declare which properties are in scope for its sub-tree and also provides hooks for setting up and tearing down TLS to properly interoperate with CLR objects.</span></span>  
  
## <a name="creating-and-using-workflow-execution-properties"></a><span data-ttu-id="0aa76-110">创建和使用工作流执行属性</span><span class="sxs-lookup"><span data-stu-id="0aa76-110">Creating and Using Workflow Execution Properties</span></span>  
 <span data-ttu-id="0aa76-111">工作流执行属性通常实现 <xref:System.Activities.IExecutionProperty> 接口，尽管着重于消息传递的属性可能会实现 <xref:System.ServiceModel.Activities.ISendMessageCallback> 和 <xref:System.ServiceModel.Activities.IReceiveMessageCallback>。</span><span class="sxs-lookup"><span data-stu-id="0aa76-111">Workflow execution properties usually implement the <xref:System.Activities.IExecutionProperty> interface, though properties focused on messaging may implement <xref:System.ServiceModel.Activities.ISendMessageCallback> and <xref:System.ServiceModel.Activities.IReceiveMessageCallback> instead.</span></span> <span data-ttu-id="0aa76-112">若要创建工作流执行属性，请创建一个实现 <xref:System.Activities.IExecutionProperty> 接口并实现成员 <xref:System.Activities.IExecutionProperty.SetupWorkflowThread%2A> 和 <xref:System.Activities.IExecutionProperty.CleanupWorkflowThread%2A> 的类。</span><span class="sxs-lookup"><span data-stu-id="0aa76-112">To create a workflow execution property, create a class that implements the <xref:System.Activities.IExecutionProperty> interface and implement the members <xref:System.Activities.IExecutionProperty.SetupWorkflowThread%2A> and <xref:System.Activities.IExecutionProperty.CleanupWorkflowThread%2A>.</span></span> <span data-ttu-id="0aa76-113">通过这些成员，该执行属性可在包含该属性的活动（包括任何子活动）的每个工作脉冲期间正确设置和关闭线程本地存储区。</span><span class="sxs-lookup"><span data-stu-id="0aa76-113">These members provide the execution property with an opportunity to properly set up and tear down the thread local storage during each pulse of work of the activity that contains the property, including any child activities.</span></span> <span data-ttu-id="0aa76-114">在本示例中，创建了设置 `ConsoleColorProperty` 的 `Console.ForegroundColor`。</span><span class="sxs-lookup"><span data-stu-id="0aa76-114">In this example, a `ConsoleColorProperty` is created that sets the `Console.ForegroundColor`.</span></span>  
  
```csharp  
class ConsoleColorProperty : IExecutionProperty  
{  
    public const string Name = "ConsoleColorProperty";  
  
    ConsoleColor original;  
    ConsoleColor color;  
  
    public ConsoleColorProperty(ConsoleColor color)  
    {  
        this.color = color;  
    }  
  
    void IExecutionProperty.SetupWorkflowThread()  
    {  
        original = Console.ForegroundColor;  
        Console.ForegroundColor = color;  
    }  
  
    void IExecutionProperty.CleanupWorkflowThread()  
    {  
        Console.ForegroundColor = original;  
    }  
}  
```  
  
 <span data-ttu-id="0aa76-115">活动创作者可通过在该活动的执行重写中注册此属性来使用它。</span><span class="sxs-lookup"><span data-stu-id="0aa76-115">Activity authors can use this property by registering it in the activity’s execute override.</span></span> <span data-ttu-id="0aa76-116">在本示例中，定义了一个 `ConsoleColorScope` 活动，该活动通过将 `ConsoleColorProperty` 添加到当前 <xref:System.Activities.NativeActivityContext.Properties%2A> 的 <xref:System.Activities.NativeActivityContext> 集合来注册该属性。</span><span class="sxs-lookup"><span data-stu-id="0aa76-116">In this example, a `ConsoleColorScope` activity is defined that registers the `ConsoleColorProperty` by adding it to the <xref:System.Activities.NativeActivityContext.Properties%2A> collection of the current <xref:System.Activities.NativeActivityContext>.</span></span>  
  
```csharp  
public sealed class ConsoleColorScope : NativeActivity  
{  
    public ConsoleColorScope()  
        : base()  
    {  
    }  
  
    public ConsoleColor Color { get; set; }  
    public Activity Body { get; set; }  
  
    protected override void Execute(NativeActivityContext context)  
    {  
        context.Properties.Add(ConsoleColorProperty.Name, new ConsoleColorProperty(this.Color));  
  
        if (this.Body != null)  
        {  
            context.ScheduleActivity(this.Body);  
        }  
    }  
}  
```  
  
 <span data-ttu-id="0aa76-117">当活动的主体开始一个工作脉冲时，会调用该属性的 <xref:System.Activities.IExecutionProperty.SetupWorkflowThread%2A> 方法，并且在完成该工作脉冲之后，调用 <xref:System.Activities.IExecutionProperty.CleanupWorkflowThread%2A>。</span><span class="sxs-lookup"><span data-stu-id="0aa76-117">When the activity’s body starts a pulse of work, the <xref:System.Activities.IExecutionProperty.SetupWorkflowThread%2A> method of the property is called, and when the pulse of work is complete, the <xref:System.Activities.IExecutionProperty.CleanupWorkflowThread%2A> is called.</span></span> <span data-ttu-id="0aa76-118">在本示例中，创建了一个工作流，该工作流使用具有三个分支的 <xref:System.Activities.Statements.Parallel> 活动。</span><span class="sxs-lookup"><span data-stu-id="0aa76-118">In this example, a workflow is created that uses a <xref:System.Activities.Statements.Parallel> activity with three branches.</span></span> <span data-ttu-id="0aa76-119">前两个分支使用 `ConsoleColorScope` 活动，第三个分支不使用该活动。</span><span class="sxs-lookup"><span data-stu-id="0aa76-119">The first two branches use the `ConsoleColorScope` activity and the third branch does not.</span></span> <span data-ttu-id="0aa76-120">所有这三个分支都包含两个 <xref:System.Activities.Statements.WriteLine> 活动和一个 <xref:System.Activities.Statements.Delay> 活动。</span><span class="sxs-lookup"><span data-stu-id="0aa76-120">All three branches contain two <xref:System.Activities.Statements.WriteLine> activities and a <xref:System.Activities.Statements.Delay> activity.</span></span> <span data-ttu-id="0aa76-121">当执行 <xref:System.Activities.Statements.Parallel> 活动时，分支中包含的活动采用交错的方式执行，但是执行每个子活动时，会通过 `ConsoleColorProperty` 应用正确的控制台颜色。</span><span class="sxs-lookup"><span data-stu-id="0aa76-121">When the <xref:System.Activities.Statements.Parallel> activity executes, the activities that are contained in the branches execute in an interleaved manner, but as each child activity executes the correct console color is applied by the `ConsoleColorProperty`.</span></span>  
  
```csharp  
Activity wf = new Parallel  
{  
    Branches =   
    {  
        new ConsoleColorScope  
        {  
            Color = ConsoleColor.Blue,  
            Body = new Sequence  
            {  
                Activities =   
                {  
                    new WriteLine  
                    {  
                        Text = "Start blue text."  
                    },  
                    new Delay  
                    {  
                        Duration = TimeSpan.FromSeconds(1)  
                    },  
                    new WriteLine  
                    {  
                        Text = "End blue text."  
                    }  
                }  
            }  
        },  
        new ConsoleColorScope  
        {  
            Color = ConsoleColor.Red,  
            Body = new Sequence  
            {  
                Activities =   
                {  
                    new WriteLine  
                    {  
                        Text = "Start red text."  
                    },  
                    new Delay  
                    {  
                        Duration = TimeSpan.FromSeconds(1)  
                    },  
                    new WriteLine  
                    {  
                        Text = "End red text."  
                    }  
                }  
            }  
        },  
        new Sequence  
        {  
            Activities =   
            {  
                new WriteLine  
                {  
                    Text = "Start default text."  
                },  
                new Delay  
                {  
                    Duration = TimeSpan.FromSeconds(1)  
                },  
                new WriteLine  
                {  
                    Text = "End default text."  
                }  
            }  
        }  
    }  
};  
  
WorkflowInvoker.Invoke(wf);  
```  
  
 <span data-ttu-id="0aa76-122">调用该工作流时，会将以下输出写入控制台窗口。</span><span class="sxs-lookup"><span data-stu-id="0aa76-122">When the workflow is invoked, the following output is written to the console window.</span></span>  
  
```  
Start blue text.  
Start red text.  
Start default text.  
End blue text.  
End red text.  
End default text.  
```  
  
> [!NOTE]
>  <span data-ttu-id="0aa76-123">尽管没有显示在前面的输出中，但是会在控制台窗口中以指定颜色显示每个文本行。</span><span class="sxs-lookup"><span data-stu-id="0aa76-123">Although it is not shown in the previous output, each line of text in the console window is displayed in the indicated color.</span></span>  
  
 <span data-ttu-id="0aa76-124">工作流执行属性可由自定义活动创作者使用，并且这些属性还提供用于处理活动（如 <xref:System.ServiceModel.Activities.CorrelationScope> 和 <xref:System.Activities.Statements.TransactionScope> 活动）的管理的机制。</span><span class="sxs-lookup"><span data-stu-id="0aa76-124">Workflow execution properties can be used by custom activity authors, and they also provide the mechanism for handle management for activities such as the <xref:System.ServiceModel.Activities.CorrelationScope> and <xref:System.Activities.Statements.TransactionScope> activities.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0aa76-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="0aa76-125">See also</span></span>

- <xref:System.Activities.IExecutionProperty>
- <xref:System.Activities.IPropertyRegistrationCallback>
- <xref:System.Activities.RegistrationContext>
