---
title: Pick 活动
ms.date: 03/30/2017
ms.assetid: b3e49b7f-0285-4720-8c09-11ae18f0d53e
ms.openlocfilehash: b9ee6c06377760d27bc54d39c1d1f3ecf67ea0d8
ms.sourcegitcommit: 3630c2515809e6f4b7dbb697a3354efec105a5cd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2019
ms.locfileid: "58409986"
---
# <a name="pick-activity"></a><span data-ttu-id="0290c-102">Pick 活动</span><span class="sxs-lookup"><span data-stu-id="0290c-102">Pick Activity</span></span>
<span data-ttu-id="0290c-103"><xref:System.Activities.Statements.Pick> 活动简化了对一组事件触发器（后跟其相应的处理程序）的建模。</span><span class="sxs-lookup"><span data-stu-id="0290c-103">The <xref:System.Activities.Statements.Pick> activity simplifies the modeling of a set of event triggers followed by their corresponding handlers.</span></span>  <span data-ttu-id="0290c-104">
  <xref:System.Activities.Statements.Pick> 活动包含 <xref:System.Activities.Statements.PickBranch> 活动的集合，其中每个 <xref:System.Activities.Statements.PickBranch> 都是一个 <xref:System.Activities.Statements.PickBranch.Trigger%2A> 活动与一个 <xref:System.Activities.Statements.PickBranch.Action%2A> 活动之间的配对。</span><span class="sxs-lookup"><span data-stu-id="0290c-104">A <xref:System.Activities.Statements.Pick> activity contains a collection of <xref:System.Activities.Statements.PickBranch> activities, where each <xref:System.Activities.Statements.PickBranch> is a pairing between a <xref:System.Activities.Statements.PickBranch.Trigger%2A> activity and an <xref:System.Activities.Statements.PickBranch.Action%2A> activity.</span></span>  <span data-ttu-id="0290c-105">执行时，并行执行所有分支的触发器。</span><span class="sxs-lookup"><span data-stu-id="0290c-105">At execution time, the triggers for all branches are executed in parallel.</span></span>  <span data-ttu-id="0290c-106">在一个触发器完成之后，将执行其相应的操作，并且取消所有其他触发器。</span><span class="sxs-lookup"><span data-stu-id="0290c-106">When one trigger completes, then its corresponding action is executed, and all other triggers are canceled.</span></span>  <span data-ttu-id="0290c-107">[!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)]<xref:System.Activities.Statements.Pick> 活动的行为与 [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)]<xref:System.Workflow.Activities.ListenActivity> 活动类似。</span><span class="sxs-lookup"><span data-stu-id="0290c-107">The behavior of the [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)]<xref:System.Activities.Statements.Pick> activity is similar to the [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)]<xref:System.Workflow.Activities.ListenActivity> activity.</span></span>  
  
 <span data-ttu-id="0290c-108">来自[使用 Pick 活动](./samples/using-the-pick-activity.md) SDK 示例的以下屏幕快照显示了具有两个分支的 Pick 活动。</span><span class="sxs-lookup"><span data-stu-id="0290c-108">The following screenshot from the [Using the Pick Activity](./samples/using-the-pick-activity.md) SDK sample shows a Pick activity with two branches.</span></span>  <span data-ttu-id="0290c-109">一个分支具有一个名为 **Read input** 的触发器，它是从命令行读取输入的自定义活动。</span><span class="sxs-lookup"><span data-stu-id="0290c-109">One branch has a trigger called **Read input**, a custom activity that reads input from the command line.</span></span> <span data-ttu-id="0290c-110">另一个分支具有一个 <xref:System.Activities.Statements.Delay> 活动触发器。</span><span class="sxs-lookup"><span data-stu-id="0290c-110">The second branch has a <xref:System.Activities.Statements.Delay> activity trigger.</span></span> <span data-ttu-id="0290c-111">如果**Read input**活动收到数据之前<xref:System.Activities.Statements.Delay>活动完成<xref:System.Activities.Statements.Delay>延迟将被取消，并且将向控制台写入一条问候信息。</span><span class="sxs-lookup"><span data-stu-id="0290c-111">If the **Read input** activity receives data before the <xref:System.Activities.Statements.Delay> activity finishes, <xref:System.Activities.Statements.Delay> Delay will be canceled and a greeting will be written to the console.</span></span>  <span data-ttu-id="0290c-112">否则，如果 **Read input** 活动未在分配的时间内收到数据，则将取消该活动并向控制台写入一条超时消息。</span><span class="sxs-lookup"><span data-stu-id="0290c-112">Otherwise, if the **Read input** activity does not receive data in the allotted time, then it will be canceled and a timeout message will be written to the console.</span></span>  <span data-ttu-id="0290c-113">这是用来向任何操作添加超时的通用模式。</span><span class="sxs-lookup"><span data-stu-id="0290c-113">This is a common pattern used to add a timeout to any action.</span></span>  
  
 ![Pick 活动](./media/pick-activity/pick-activity-two-branches.jpg)  
  
## <a name="best-practices"></a><span data-ttu-id="0290c-115">最佳实践</span><span class="sxs-lookup"><span data-stu-id="0290c-115">Best practices</span></span>  
 <span data-ttu-id="0290c-116">使用 Pick 时，执行的分支是首先完成其触发器的分支。</span><span class="sxs-lookup"><span data-stu-id="0290c-116">When using Pick, the branch that executes is the branch whose trigger completes first.</span></span>  <span data-ttu-id="0290c-117">从概念上讲，所有触发器都并行执行，并且一个触发器会在由于另一个触发器完成而被取消之前执行它的大部分逻辑。</span><span class="sxs-lookup"><span data-stu-id="0290c-117">Conceptually, all triggers execute in parallel, and one trigger may have executed the majority of its logic before it is canceled by the completion of another trigger.</span></span>  <span data-ttu-id="0290c-118">记住这一点，使用 Pick 活动时要遵循的一般规则是将触发器视为表示一个事件，并且在该事件中放置尽可能少的逻辑。</span><span class="sxs-lookup"><span data-stu-id="0290c-118">With this in mind, a general guideline to follow when using the Pick activity is to treat the trigger as representing a single event, and to put as little logic as possible into it.</span></span>  <span data-ttu-id="0290c-119">理想情况下，触发器应只包含足够的逻辑来接收某个事件，并且该事件的所有处理都应属于分支的操作。</span><span class="sxs-lookup"><span data-stu-id="0290c-119">Ideally, the trigger should contain just enough logic to receive an event, and all the processing of that event should go into the action of the branch.</span></span>  <span data-ttu-id="0290c-120">此方法最大程度地减少了执行触发器之间的重叠量。</span><span class="sxs-lookup"><span data-stu-id="0290c-120">This method minimizes the amount of overlap between the execution of the triggers.</span></span>  <span data-ttu-id="0290c-121">例如，假设有一个具有两个触发器的 <xref:System.Activities.Statements.Pick>，其中每个触发器包含一个后跟附加逻辑的 <xref:System.ServiceModel.Activities.Receive> 活动。</span><span class="sxs-lookup"><span data-stu-id="0290c-121">For example, consider a <xref:System.Activities.Statements.Pick> with two triggers, where each trigger contains a <xref:System.ServiceModel.Activities.Receive> activity followed by additional logic.</span></span>  <span data-ttu-id="0290c-122">如果附加逻辑引入一个空闲点，则这两个 <xref:System.ServiceModel.Activities.Receive> 活动可能都会成功完成。</span><span class="sxs-lookup"><span data-stu-id="0290c-122">If the additional logic introduces an idle point, then there is the possibility of both <xref:System.ServiceModel.Activities.Receive> activities completing successfully.</span></span>  <span data-ttu-id="0290c-123">一个触发器将完成全部，而另一个触发器将完成一部分。</span><span class="sxs-lookup"><span data-stu-id="0290c-123">One trigger will fully complete, while another will partially complete.</span></span>  <span data-ttu-id="0290c-124">在某些情况下，接受消息，然后完成其一部分处理是不可接受的。</span><span class="sxs-lookup"><span data-stu-id="0290c-124">In some scenarios, accepting a message, and then partially completing the processing of it is unacceptable.</span></span>  <span data-ttu-id="0290c-125">因此，使用 WF 内置的消息传递活动（如 <xref:System.ServiceModel.Activities.Receive> 和 <xref:System.ServiceModel.Activities.SendReply>）时，尽管通常在触发器中使用 <xref:System.ServiceModel.Activities.Receive>，但如有可能应将 <xref:System.ServiceModel.Activities.SendReply> 和其他逻辑放入操作中。</span><span class="sxs-lookup"><span data-stu-id="0290c-125">Therefore, when using WF built-in messaging activities such as <xref:System.ServiceModel.Activities.Receive> and <xref:System.ServiceModel.Activities.SendReply>, while <xref:System.ServiceModel.Activities.Receive> is commonly used in the trigger, <xref:System.ServiceModel.Activities.SendReply> and other logic should be put in the action whenever possible.</span></span>  
  
## <a name="using-the-pick-activity-in-the-designer"></a><span data-ttu-id="0290c-126">在设计器中使用 Pick 活动</span><span class="sxs-lookup"><span data-stu-id="0290c-126">Using the Pick activity in the designer</span></span>  
 <span data-ttu-id="0290c-127">若要在设计器中使用 Pick，请在工具箱中找到 **Pick** 和 **PickBranch**。</span><span class="sxs-lookup"><span data-stu-id="0290c-127">To use Pick in the designer, find **Pick** and **PickBranch** in the toolbox.</span></span>  <span data-ttu-id="0290c-128">将 **Pick** 拖放到画布上。</span><span class="sxs-lookup"><span data-stu-id="0290c-128">Drag and drop **Pick** onto the canvas.</span></span>  <span data-ttu-id="0290c-129">默认情况下，设计器中新的 **Pick** 活动将包含两个分支。</span><span class="sxs-lookup"><span data-stu-id="0290c-129">By default, a new **Pick** Activity in the designer will contain two branches.</span></span>  <span data-ttu-id="0290c-130">若要添加其他分支，请拖动 **PickBranch** 活动并将其放置到现有分支旁。</span><span class="sxs-lookup"><span data-stu-id="0290c-130">To add additional branches, drag the **PickBranch** activity and drop it next to existing branches.</span></span> <span data-ttu-id="0290c-131">可将活动拖放到 **Pick** 活动上任何 **PickBranch** 的“触发器”区域或“操作”区域中。</span><span class="sxs-lookup"><span data-stu-id="0290c-131">Activities can be dropped onto the **Pick** Activity into either the **Trigger** area or the **Action** area of any **PickBranch**.</span></span>  
  
## <a name="using-the-pick-activity-in-code"></a><span data-ttu-id="0290c-132">在代码中使用 Pick 活动</span><span class="sxs-lookup"><span data-stu-id="0290c-132">Using the Pick Activity in code</span></span>  
 <span data-ttu-id="0290c-133">使用 <xref:System.Activities.Statements.Pick> 活动的方法是用 <xref:System.Activities.Statements.Pick.Branches%2A> 活动填充它的 <xref:System.Activities.Statements.PickBranch> 集合。</span><span class="sxs-lookup"><span data-stu-id="0290c-133">The <xref:System.Activities.Statements.Pick> activity is used by populating its <xref:System.Activities.Statements.Pick.Branches%2A> collection with <xref:System.Activities.Statements.PickBranch> activities.</span></span> <span data-ttu-id="0290c-134">每个 <xref:System.Activities.Statements.PickBranch> 活动都有一个类型为 <xref:System.Activities.Statements.PickBranch.Trigger%2A> 的 <xref:System.Activities.Activity> 属性。</span><span class="sxs-lookup"><span data-stu-id="0290c-134">The <xref:System.Activities.Statements.PickBranch> activities each have a <xref:System.Activities.Statements.PickBranch.Trigger%2A> property of type <xref:System.Activities.Activity>.</span></span> <span data-ttu-id="0290c-135">当指定的活动完成执行后，将执行 <xref:System.Activities.Statements.PickBranch.Action%2A>。</span><span class="sxs-lookup"><span data-stu-id="0290c-135">When the specified activity completes execution, the <xref:System.Activities.Statements.PickBranch.Action%2A> executes.</span></span>  
  
 <span data-ttu-id="0290c-136">下面的代码示例演示如何使用 <xref:System.Activities.Statements.Pick> 活动为从控制台读取一行的某个活动实现超时。</span><span class="sxs-lookup"><span data-stu-id="0290c-136">The following code example demonstrates how to use a <xref:System.Activities.Statements.Pick> activity to implement a timeout for an activity that reads a line from the console.</span></span>  
  
```csharp  
Sequence body = new Sequence()  
{  
    Variables = { name },  
    Activities =   
   {  
       new System.Activities.Statements.Pick  
        {  
           Branches =   
           {  
               new PickBranch  
               {  
                   Trigger = new ReadLine  
                   {  
                      Result = name,  
                      BookmarkName = "name"  
                   },  
                   Action = new WriteLine   
                   {   
                       Text = ExpressionServices.Convert<string>(ctx => "Hello " +   
                           name.Get(ctx))   
                   }  
               },  
               new PickBranch  
               {  
                   Trigger = new Delay  
                   {  
                      Duration = new TimeSpan(0, 0, 5)  
                   },  
                   Action = new WriteLine  
                   {  
                      Text = "Time is up."  
                   }  
               }  
           }  
       }  
   }  
};  
```  
  
```xaml  
<Sequence xmlns="http://schemas.microsoft.com/netfx/2009/xaml/activities" xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml">  
  <Sequence.Variables>  
    <Variable x:TypeArguments="x:String" Name="username" />  
  </Sequence.Variables>  
  <Pick>  
    <PickBranch>  
      <PickBranch.Trigger>  
        <ReadLine BookmarkName="name" Result="username" />  
      </PickBranch.Trigger>  
      <WriteLine>[String.Concat("Hello ", username)]</WriteLine>  
    </PickBranch>  
    <PickBranch>  
      <PickBranch.Trigger>  
        <Delay>00:00:05</Delay>  
      </PickBranch.Trigger>  
      <WriteLine>Time is up.</WriteLine>  
    </PickBranch>  
  </Pick>  
</Sequence>  
```
