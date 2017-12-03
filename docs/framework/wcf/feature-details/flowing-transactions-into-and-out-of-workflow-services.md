---
title: "使事务流入和流出工作流服务"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 03ced70e-b540-4dd9-86c8-87f7bd61f609
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d097068720bb937911316fdb29a83ba0e8e67713
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="flowing-transactions-into-and-out-of-workflow-services"></a><span data-ttu-id="10768-102">使事务流入和流出工作流服务</span><span class="sxs-lookup"><span data-stu-id="10768-102">Flowing Transactions into and out of Workflow Services</span></span>
<span data-ttu-id="10768-103">工作流服务和客户端可以参与事务。</span><span class="sxs-lookup"><span data-stu-id="10768-103">Workflow services and clients can participate in transactions.</span></span>  <span data-ttu-id="10768-104">对于将成为环境事务一部分的服务操作，将 <xref:System.ServiceModel.Activities.Receive> 活动放到 <xref:System.ServiceModel.Activities.TransactedReceiveScope> 活动内。</span><span class="sxs-lookup"><span data-stu-id="10768-104">For a service operation to become part of an ambient transaction, place a <xref:System.ServiceModel.Activities.Receive> activity within a <xref:System.ServiceModel.Activities.TransactedReceiveScope> activity.</span></span> <span data-ttu-id="10768-105">由 <xref:System.ServiceModel.Activities.Send> 内的 <xref:System.ServiceModel.Activities.SendReply> 或 <xref:System.ServiceModel.Activities.TransactedReceiveScope> 活动所做的任何调用也将在环境事务中进行。</span><span class="sxs-lookup"><span data-stu-id="10768-105">Any calls made by a <xref:System.ServiceModel.Activities.Send> or a <xref:System.ServiceModel.Activities.SendReply> activity within the <xref:System.ServiceModel.Activities.TransactedReceiveScope> will also be made within the ambient transaction.</span></span> <span data-ttu-id="10768-106">工作流客户端应用程序可以通过使用 <xref:System.Activities.Statements.TransactionScope> 活动来创建环境事务，并通过使用该环境事务来调用服务操作。</span><span class="sxs-lookup"><span data-stu-id="10768-106">A workflow client application can create an ambient transaction by using the <xref:System.Activities.Statements.TransactionScope> activity and call service operations using the ambient transaction.</span></span> <span data-ttu-id="10768-107">本主题将指导您创建参与事务的工作流服务和工作流客户端。</span><span class="sxs-lookup"><span data-stu-id="10768-107">This topic walks you through creating a workflow service and workflow client that participate in transactions.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="10768-108">如果某个工作流服务实例在事务中加载且该工作流包含 <xref:System.Activities.Statements.Persist> 活动，则该工作流实例会挂起，直到事务超时。</span><span class="sxs-lookup"><span data-stu-id="10768-108">If a workflow service instance is loaded within a transaction and the workflow contains a <xref:System.Activities.Statements.Persist> activity, the workflow instance will hang until the transaction times out.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="10768-109">无论何时使用 <xref:System.ServiceModel.Activities.TransactedReceiveScope>，都建议将所有接收都置于工作流内的 <xref:System.ServiceModel.Activities.TransactedReceiveScope> 活动中。</span><span class="sxs-lookup"><span data-stu-id="10768-109">Whenever you use a <xref:System.ServiceModel.Activities.TransactedReceiveScope> it is recommended to place all Receives in the workflow within <xref:System.ServiceModel.Activities.TransactedReceiveScope> activities.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="10768-110">如果 <xref:System.ServiceModel.Activities.TransactedReceiveScope> 且消息按错误顺序到达，则在尝试提交第一个不按顺序的消息时，工作流会中止。</span><span class="sxs-lookup"><span data-stu-id="10768-110">When using <xref:System.ServiceModel.Activities.TransactedReceiveScope> and messages arrive in the incorrect order, the workflow will be aborted when trying to deliver the first out of order message.</span></span> <span data-ttu-id="10768-111">必须确保工作流在空闲时始终处于一致的停止点。</span><span class="sxs-lookup"><span data-stu-id="10768-111">You must make sure your workflow is always at a consistent stopping point when the workflow idles.</span></span> <span data-ttu-id="10768-112">这会使您可以在工作流中止时，从以前的持久点重新启动工作流。</span><span class="sxs-lookup"><span data-stu-id="10768-112">This will allow you to restart the workflow from a previous persistence point should the workflow be aborted.</span></span>  
  
### <a name="create-a-shared-library"></a><span data-ttu-id="10768-113">创建共享库</span><span class="sxs-lookup"><span data-stu-id="10768-113">Create a shared library</span></span>  
  
1.  <span data-ttu-id="10768-114">创建新的空 Visual Studio 解决方案。</span><span class="sxs-lookup"><span data-stu-id="10768-114">Create a new empty Visual Studio Solution.</span></span>  
  
2.  <span data-ttu-id="10768-115">添加一个名为 `Common` 的新类库项目。</span><span class="sxs-lookup"><span data-stu-id="10768-115">Add a new class library project called `Common`.</span></span> <span data-ttu-id="10768-116">添加对下列程序集的引用：</span><span class="sxs-lookup"><span data-stu-id="10768-116">Add references to the following assemblies:</span></span>  
  
    -   <span data-ttu-id="10768-117">System.Activities.dll</span><span class="sxs-lookup"><span data-stu-id="10768-117">System.Activities.dll</span></span>  
  
    -   <span data-ttu-id="10768-118">System.ServiceModel.dll</span><span class="sxs-lookup"><span data-stu-id="10768-118">System.ServiceModel.dll</span></span>  
  
    -   <span data-ttu-id="10768-119">System.ServiceModel.Activities.dll</span><span class="sxs-lookup"><span data-stu-id="10768-119">System.ServiceModel.Activities.dll</span></span>  
  
    -   <span data-ttu-id="10768-120">System.Transactions.dll</span><span class="sxs-lookup"><span data-stu-id="10768-120">System.Transactions.dll</span></span>  
  
3.  <span data-ttu-id="10768-121">将一个名为 `PrintTransactionInfo` 的新类添加到 `Common` 项目。</span><span class="sxs-lookup"><span data-stu-id="10768-121">Add a new class called `PrintTransactionInfo` to the `Common` project.</span></span> <span data-ttu-id="10768-122">此类派生自 <xref:System.Activities.NativeActivity>，并重载 <xref:System.Activities.NativeActivity.Execute%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="10768-122">This class is derived from <xref:System.Activities.NativeActivity> and overloads the <xref:System.Activities.NativeActivity.Execute%2A> method.</span></span>  
  
    ```  
    using System;  
    using System;  
    using System.Activities;  
    using System.Transactions;  
  
    namespace Common  
    {  
        public class PrintTransactionInfo : NativeActivity  
        {  
            protected override void Execute(NativeActivityContext context)  
            {  
                RuntimeTransactionHandle rth = context.Properties.Find(typeof(RuntimeTransactionHandle).FullName) as RuntimeTransactionHandle;  
  
                if (rth == null)  
                {  
                    Console.WriteLine("There is no ambient RuntimeTransactionHandle");  
                }  
  
                Transaction t = rth.GetCurrentTransaction(context);  
  
                if (t == null)  
                {  
                    Console.WriteLine("There is no ambient transaction");  
                }  
                else  
                {  
                    Console.WriteLine("Transaction: {0} is {1}", t.TransactionInformation.DistributedIdentifier, t.TransactionInformation.Status);  
                }  
            }  
        }  
  
    }  
    ```  
  
     <span data-ttu-id="10768-123">这是一个本机活动，用于显示有关环境事务的信息，它将在本主题中使用的服务工作流和客户端工作流中使用。</span><span class="sxs-lookup"><span data-stu-id="10768-123">This is a native activity that displays information about the ambient transaction and is used in both the service and client workflows used in this topic.</span></span> <span data-ttu-id="10768-124">生成解决方案以使此活动可的**常见**部分**工具箱**。</span><span class="sxs-lookup"><span data-stu-id="10768-124">Build the solution to make this activity available in the **Common** section of the **Toolbox**.</span></span>  
  
### <a name="implement-the-workflow-service"></a><span data-ttu-id="10768-125">实现工作流服务</span><span class="sxs-lookup"><span data-stu-id="10768-125">Implement the workflow service</span></span>  
  
1.  <span data-ttu-id="10768-126">添加新[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]称为工作流服务`WorkflowService`到`Common`项目。</span><span class="sxs-lookup"><span data-stu-id="10768-126">Add a new [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Workflow Service, called `WorkflowService` to the `Common` project.</span></span> <span data-ttu-id="10768-127">为此，右击`Common`项目，依次选择**添加**，**新建项...**，选择**工作流**下**已安装的模板**和选择**WCF 工作流服务**。</span><span class="sxs-lookup"><span data-stu-id="10768-127">To do this right click the `Common` project, select **Add**, **New Item ...**, Select **Workflow** under **Installed Templates** and select **WCF Workflow Service**.</span></span>  
  
     <span data-ttu-id="10768-128">![添加工作流服务](../../../../docs/framework/wcf/feature-details/media/addwfservice.JPG "AddWFService")</span><span class="sxs-lookup"><span data-stu-id="10768-128">![Adding a Workflow Service](../../../../docs/framework/wcf/feature-details/media/addwfservice.JPG "AddWFService")</span></span>  
  
2.  <span data-ttu-id="10768-129">删除默认的 `ReceiveRequest` 和 `SendResponse` 活动。</span><span class="sxs-lookup"><span data-stu-id="10768-129">Delete the default `ReceiveRequest` and `SendResponse` activities.</span></span>  
  
3.  <span data-ttu-id="10768-130">将 <xref:System.Activities.Statements.WriteLine> 活动拖放到 `Sequential Service` 活动中。</span><span class="sxs-lookup"><span data-stu-id="10768-130">Drag and drop a <xref:System.Activities.Statements.WriteLine> activity into the `Sequential Service` activity.</span></span> <span data-ttu-id="10768-131">将文本属性设置为 `"Workflow Service starting ..."`，如下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="10768-131">Set the text property to `"Workflow Service starting ..."` as shown in the following example.</span></span>  
  
     <span data-ttu-id="10768-132">![添加 WriteLine 活动](../../../../docs/framework/wcf/feature-details/media/addwriteline.JPG "AddWriteLine")</span><span class="sxs-lookup"><span data-stu-id="10768-132">![Adding a WriteLine activity](../../../../docs/framework/wcf/feature-details/media/addwriteline.JPG "AddWriteLine")</span></span>  
  
4.  <span data-ttu-id="10768-133">将 <xref:System.ServiceModel.Activities.TransactedReceiveScope> 拖放到 <xref:System.Activities.Statements.WriteLine> 活动后面。</span><span class="sxs-lookup"><span data-stu-id="10768-133">Drag and drop a <xref:System.ServiceModel.Activities.TransactedReceiveScope> after the <xref:System.Activities.Statements.WriteLine> activity.</span></span> <span data-ttu-id="10768-134"><xref:System.ServiceModel.Activities.TransactedReceiveScope>在找不到活动**消息**部分**工具箱**。</span><span class="sxs-lookup"><span data-stu-id="10768-134">The <xref:System.ServiceModel.Activities.TransactedReceiveScope> activity can be found in the **Messaging** section of the **Toolbox**.</span></span> <span data-ttu-id="10768-135"><xref:System.ServiceModel.Activities.TransactedReceiveScope>活动组成两个部分**请求**和**正文**。</span><span class="sxs-lookup"><span data-stu-id="10768-135">The <xref:System.ServiceModel.Activities.TransactedReceiveScope> activity is composed of two sections **Request** and **Body**.</span></span> <span data-ttu-id="10768-136">**请求**部分包含<xref:System.ServiceModel.Activities.Receive>活动。</span><span class="sxs-lookup"><span data-stu-id="10768-136">The **Request** section contains the <xref:System.ServiceModel.Activities.Receive> activity.</span></span> <span data-ttu-id="10768-137">**正文**部分包含收到消息后将在事务中执行的活动。</span><span class="sxs-lookup"><span data-stu-id="10768-137">The **Body** section contains the activities to execute within a transaction after a message has been received.</span></span>  
  
     <span data-ttu-id="10768-138">![添加 TransactedReceiveScope 活动](../../../../docs/framework/wcf/feature-details/media/trs.JPG "TRS")</span><span class="sxs-lookup"><span data-stu-id="10768-138">![Adding a TransactedReceiveScope activity](../../../../docs/framework/wcf/feature-details/media/trs.JPG "TRS")</span></span>  
  
5.  <span data-ttu-id="10768-139">选择<xref:System.ServiceModel.Activities.TransactedReceiveScope>活动，然后单击**变量**按钮。</span><span class="sxs-lookup"><span data-stu-id="10768-139">Select the <xref:System.ServiceModel.Activities.TransactedReceiveScope> activity and click the **Variables** button.</span></span> <span data-ttu-id="10768-140">添加以下变量。</span><span class="sxs-lookup"><span data-stu-id="10768-140">Add the following variables.</span></span>  
  
     <span data-ttu-id="10768-141">![向 TransactedReceiveScope 添加变量](../../../../docs/framework/wcf/feature-details/media/trsvariables.JPG "TRSVariables")</span><span class="sxs-lookup"><span data-stu-id="10768-141">![Adding Variables to the TransactedReceiveScope](../../../../docs/framework/wcf/feature-details/media/trsvariables.JPG "TRSVariables")</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="10768-142">可以删除默认情况下在该处的数据变量。</span><span class="sxs-lookup"><span data-stu-id="10768-142">You can delete the data variable that is there by default.</span></span> <span data-ttu-id="10768-143">还可以使用现有句柄变量。</span><span class="sxs-lookup"><span data-stu-id="10768-143">You can also use the existing handle variable.</span></span>  
  
6.  <span data-ttu-id="10768-144">拖放式<xref:System.ServiceModel.Activities.Receive>中的活动**请求**部分<xref:System.ServiceModel.Activities.TransactedReceiveScope>活动。</span><span class="sxs-lookup"><span data-stu-id="10768-144">Drag and drop a <xref:System.ServiceModel.Activities.Receive> activity within the **Request** section of the <xref:System.ServiceModel.Activities.TransactedReceiveScope> activity.</span></span> <span data-ttu-id="10768-145">设置以下属性：</span><span class="sxs-lookup"><span data-stu-id="10768-145">Set the following properties:</span></span>  
  
    |<span data-ttu-id="10768-146">属性</span><span class="sxs-lookup"><span data-stu-id="10768-146">Property</span></span>|<span data-ttu-id="10768-147">值</span><span class="sxs-lookup"><span data-stu-id="10768-147">Value</span></span>|  
    |--------------|-----------|  
    |<span data-ttu-id="10768-148">CanCreateInstance</span><span class="sxs-lookup"><span data-stu-id="10768-148">CanCreateInstance</span></span>|<span data-ttu-id="10768-149">True（选中复选框）</span><span class="sxs-lookup"><span data-stu-id="10768-149">True (check the checkbox)</span></span>|  
    |<span data-ttu-id="10768-150">OperationName</span><span class="sxs-lookup"><span data-stu-id="10768-150">OperationName</span></span>|<span data-ttu-id="10768-151">StartSample</span><span class="sxs-lookup"><span data-stu-id="10768-151">StartSample</span></span>|  
    |<span data-ttu-id="10768-152">ServiceContractName</span><span class="sxs-lookup"><span data-stu-id="10768-152">ServiceContractName</span></span>|<span data-ttu-id="10768-153">ITransactionSample</span><span class="sxs-lookup"><span data-stu-id="10768-153">ITransactionSample</span></span>|  
  
     <span data-ttu-id="10768-154">该工作流应如下所示：</span><span class="sxs-lookup"><span data-stu-id="10768-154">The workflow should look like this:</span></span>  
  
     <span data-ttu-id="10768-155">![添加 Receive 活动](../../../../docs/framework/wcf/feature-details/media/serviceaddreceive.JPG "ServiceAddReceive")</span><span class="sxs-lookup"><span data-stu-id="10768-155">![Adding a Receive activity](../../../../docs/framework/wcf/feature-details/media/serviceaddreceive.JPG "ServiceAddReceive")</span></span>  
  
7.  <span data-ttu-id="10768-156">单击**定义...**中链接<xref:System.ServiceModel.Activities.Receive>活动，然后进行以下设置：</span><span class="sxs-lookup"><span data-stu-id="10768-156">Click the **Define...** link in the <xref:System.ServiceModel.Activities.Receive> activity and make the following settings:</span></span>  
  
     <span data-ttu-id="10768-157">![设置 Recieve 活动的消息设置](../../../../docs/framework/wcf/feature-details/media/receivemessagesettings.JPG "ReceiveMessageSettings")</span><span class="sxs-lookup"><span data-stu-id="10768-157">![Setting message settings for the Recieve activity](../../../../docs/framework/wcf/feature-details/media/receivemessagesettings.JPG "ReceiveMessageSettings")</span></span>  
  
8.  <span data-ttu-id="10768-158">将 <xref:System.Activities.Statements.Sequence> 活动拖放到 <xref:System.ServiceModel.Activities.TransactedReceiveScope> 的“正文”部分内。</span><span class="sxs-lookup"><span data-stu-id="10768-158">Drag and drop a <xref:System.Activities.Statements.Sequence> activity into the Body section of the <xref:System.ServiceModel.Activities.TransactedReceiveScope>.</span></span> <span data-ttu-id="10768-159">在 <xref:System.Activities.Statements.Sequence> 活动内，拖放两个 <xref:System.Activities.Statements.WriteLine> 活动并设置 <xref:System.Activities.Statements.WriteLine.Text%2A> 属性，如下表所示。</span><span class="sxs-lookup"><span data-stu-id="10768-159">Within the <xref:System.Activities.Statements.Sequence> activity drag and drop two <xref:System.Activities.Statements.WriteLine> activities and set the <xref:System.Activities.Statements.WriteLine.Text%2A> properties as shown in the following table.</span></span>  
  
    |<span data-ttu-id="10768-160">Activity</span><span class="sxs-lookup"><span data-stu-id="10768-160">Activity</span></span>|<span data-ttu-id="10768-161">值</span><span class="sxs-lookup"><span data-stu-id="10768-161">Value</span></span>|  
    |--------------|-----------|  
    |<span data-ttu-id="10768-162">第一个 WriteLine</span><span class="sxs-lookup"><span data-stu-id="10768-162">1st WriteLine</span></span>|<span data-ttu-id="10768-163">"服务： 接收已完成"</span><span class="sxs-lookup"><span data-stu-id="10768-163">"Service: Receive Completed"</span></span>|  
    |<span data-ttu-id="10768-164">第二个 WriteLine</span><span class="sxs-lookup"><span data-stu-id="10768-164">2nd WriteLine</span></span>|<span data-ttu-id="10768-165">"Service: Received = " + requestMessage</span><span class="sxs-lookup"><span data-stu-id="10768-165">"Service: Received = " + requestMessage</span></span>|  
  
     <span data-ttu-id="10768-166">现在，该工作流应如下所示：</span><span class="sxs-lookup"><span data-stu-id="10768-166">The workflow should now look like this:</span></span>  
  
     <span data-ttu-id="10768-167">![添加 WriteLine 活动](../../../../docs/framework/wcf/feature-details/media/afteraddingwritelines.JPG "AfterAddingWriteLines")</span><span class="sxs-lookup"><span data-stu-id="10768-167">![Adding WriteLine activities](../../../../docs/framework/wcf/feature-details/media/afteraddingwritelines.JPG "AfterAddingWriteLines")</span></span>  
  
9. <span data-ttu-id="10768-168">拖放式`PrintTransactionInfo`后第二个活动<xref:System.Activities.Statements.WriteLine>中的活动**正文**中<xref:System.ServiceModel.Activities.TransactedReceiveScope>活动。</span><span class="sxs-lookup"><span data-stu-id="10768-168">Drag and drop the `PrintTransactionInfo` activity after the second <xref:System.Activities.Statements.WriteLine> activity in the **Body** in the <xref:System.ServiceModel.Activities.TransactedReceiveScope> activity.</span></span>  
  
     <span data-ttu-id="10768-169">![添加 PrintTransactionInfo 后](../../../../docs/framework/wcf/feature-details/media/afteraddingprinttransactioninfo.JPG "AfterAddingPrintTransactionInfo")</span><span class="sxs-lookup"><span data-stu-id="10768-169">![After adding PrintTransactionInfo](../../../../docs/framework/wcf/feature-details/media/afteraddingprinttransactioninfo.JPG "AfterAddingPrintTransactionInfo")</span></span>  
  
10. <span data-ttu-id="10768-170">将 <xref:System.Activities.Statements.Assign> 活动拖放到 `PrintTransactionInfo` 活动后面，然后根据下表设置其属性。</span><span class="sxs-lookup"><span data-stu-id="10768-170">Drag and drop an <xref:System.Activities.Statements.Assign> activity after the `PrintTransactionInfo` activity and set its properties according to the following table.</span></span>  
  
    |<span data-ttu-id="10768-171">属性</span><span class="sxs-lookup"><span data-stu-id="10768-171">Property</span></span>|<span data-ttu-id="10768-172">值</span><span class="sxs-lookup"><span data-stu-id="10768-172">Value</span></span>|  
    |--------------|-----------|  
    |<span data-ttu-id="10768-173">到</span><span class="sxs-lookup"><span data-stu-id="10768-173">To</span></span>|<span data-ttu-id="10768-174">replyMessage</span><span class="sxs-lookup"><span data-stu-id="10768-174">replyMessage</span></span>|  
    |<span data-ttu-id="10768-175">值</span><span class="sxs-lookup"><span data-stu-id="10768-175">Value</span></span>|<span data-ttu-id="10768-176">"Service: Sending reply."</span><span class="sxs-lookup"><span data-stu-id="10768-176">"Service: Sending reply."</span></span>|  
  
11. <span data-ttu-id="10768-177">将 <xref:System.Activities.Statements.WriteLine> 活动拖放到 <xref:System.Activities.Statements.Assign> 活动后面，然后将它的 <xref:System.Activities.Statements.WriteLine.Text%2A> 属性设置为 "Service: Begin reply."</span><span class="sxs-lookup"><span data-stu-id="10768-177">Drag and drop a <xref:System.Activities.Statements.WriteLine> activity after the <xref:System.Activities.Statements.Assign> activity and set its <xref:System.Activities.Statements.WriteLine.Text%2A> property to "Service: Begin reply."</span></span>  
  
     <span data-ttu-id="10768-178">现在，该工作流应如下所示：</span><span class="sxs-lookup"><span data-stu-id="10768-178">The workflow should now look like this:</span></span>  
  
     <span data-ttu-id="10768-179">![添加 Assign 和 WriteLine 后](../../../../docs/framework/wcf/feature-details/media/afteraddingsbrwriteline.JPG "AfterAddingSBRWriteLine")</span><span class="sxs-lookup"><span data-stu-id="10768-179">![After adding Assign and WriteLine](../../../../docs/framework/wcf/feature-details/media/afteraddingsbrwriteline.JPG "AfterAddingSBRWriteLine")</span></span>  
  
12. <span data-ttu-id="10768-180">右键单击<xref:System.ServiceModel.Activities.Receive>活动，并选择**创建 SendReply**并将其粘贴上次<xref:System.Activities.Statements.WriteLine>活动。</span><span class="sxs-lookup"><span data-stu-id="10768-180">Right click the <xref:System.ServiceModel.Activities.Receive> activity and select **Create SendReply** and paste it after the last <xref:System.Activities.Statements.WriteLine> activity.</span></span> <span data-ttu-id="10768-181">单击**定义...**中链接`SendReplyToReceive`活动，然后进行以下设置。</span><span class="sxs-lookup"><span data-stu-id="10768-181">Click the **Define...** link in the `SendReplyToReceive` activity and make the following settings.</span></span>  
  
     <span data-ttu-id="10768-182">![回复消息设置](../../../../docs/framework/wcf/feature-details/media/replymessagesettings.JPG "ReplyMessageSettings")</span><span class="sxs-lookup"><span data-stu-id="10768-182">![Reply message settings](../../../../docs/framework/wcf/feature-details/media/replymessagesettings.JPG "ReplyMessageSettings")</span></span>  
  
13. <span data-ttu-id="10768-183">拖放式<xref:System.Activities.Statements.WriteLine>活动后的`SendReplyToReceive`活动，并设置它具有<xref:System.Activities.Statements.WriteLine.Text%2A>属性设置为"服务： Reply sent。"</span><span class="sxs-lookup"><span data-stu-id="10768-183">Drag and drop a <xref:System.Activities.Statements.WriteLine> activity after the `SendReplyToReceive` activity and set it’s <xref:System.Activities.Statements.WriteLine.Text%2A> property to "Service: Reply sent."</span></span>  
  
14. <span data-ttu-id="10768-184">将 <xref:System.Activities.Statements.WriteLine> 活动拖放到工作流底部，然后将它的 <xref:System.Activities.Statements.WriteLine.Text%2A> 属性设置为 "Service: Workflow ends, press ENTER to exit."</span><span class="sxs-lookup"><span data-stu-id="10768-184">Drag and drop a <xref:System.Activities.Statements.WriteLine> activity at the bottom of the workflow and set its <xref:System.Activities.Statements.WriteLine.Text%2A> property to "Service: Workflow ends, press ENTER to exit."</span></span>  
  
     <span data-ttu-id="10768-185">完成的服务工作流应如下所示：</span><span class="sxs-lookup"><span data-stu-id="10768-185">The completed service workflow should look like this:</span></span>  
  
     <span data-ttu-id="10768-186">![完成服务工作流](../../../../docs/framework/wcf/feature-details/media/servicecomplete.jpg "ServiceComplete")</span><span class="sxs-lookup"><span data-stu-id="10768-186">![Complete Service Workflow](../../../../docs/framework/wcf/feature-details/media/servicecomplete.jpg "ServiceComplete")</span></span>  
  
### <a name="implement-the-workflow-client"></a><span data-ttu-id="10768-187">实现工作流客户端</span><span class="sxs-lookup"><span data-stu-id="10768-187">Implement the workflow client</span></span>  
  
1.  <span data-ttu-id="10768-188">将一个名为 `WorkflowClient` 的新 WCF 工作流应用程序添加到 `Common` 项目。</span><span class="sxs-lookup"><span data-stu-id="10768-188">Add a new WCF Workflow application, called `WorkflowClient` to the `Common` project.</span></span> <span data-ttu-id="10768-189">为此，右击`Common`项目，依次选择**添加**，**新建项...**，选择**工作流**下**已安装的模板**和选择**活动**。</span><span class="sxs-lookup"><span data-stu-id="10768-189">To do this right click the `Common` project, select **Add**, **New Item ...**, Select **Workflow** under **Installed Templates** and select **Activity**.</span></span>  
  
     <span data-ttu-id="10768-190">![添加的活动项目](../../../../docs/framework/wcf/feature-details/media/addactivity.JPG "AddActivity")</span><span class="sxs-lookup"><span data-stu-id="10768-190">![Add an Activity project](../../../../docs/framework/wcf/feature-details/media/addactivity.JPG "AddActivity")</span></span>  
  
2.  <span data-ttu-id="10768-191">将 <xref:System.Activities.Statements.Sequence> 活动拖放到设计图面上。</span><span class="sxs-lookup"><span data-stu-id="10768-191">Drag and drop a <xref:System.Activities.Statements.Sequence> activity onto the design surface.</span></span>  
  
3.  <span data-ttu-id="10768-192">在 <xref:System.Activities.Statements.Sequence> 活动内拖放一个 <xref:System.Activities.Statements.WriteLine> 活动，然后将它的 <xref:System.Activities.Statements.WriteLine.Text%2A> 属性设置为 `"Client: Workflow starting"`。</span><span class="sxs-lookup"><span data-stu-id="10768-192">Within the <xref:System.Activities.Statements.Sequence> activity drag and drop a <xref:System.Activities.Statements.WriteLine> activity and set its <xref:System.Activities.Statements.WriteLine.Text%2A> property to `"Client: Workflow starting"`.</span></span> <span data-ttu-id="10768-193">现在，该工作流应如下所示：</span><span class="sxs-lookup"><span data-stu-id="10768-193">The workflow should now look like this:</span></span>  
  
     <span data-ttu-id="10768-194">![添加 WriteLine 活动](../../../../docs/framework/wcf/feature-details/media/clientaddwriteline.JPG "ClientAddWriteLine")</span><span class="sxs-lookup"><span data-stu-id="10768-194">![Add a WriteLine activity](../../../../docs/framework/wcf/feature-details/media/clientaddwriteline.JPG "ClientAddWriteLine")</span></span>  
  
4.  <span data-ttu-id="10768-195">将 <xref:System.Activities.Statements.TransactionScope> 活动拖放到 <xref:System.Activities.Statements.WriteLine> 活动后面。</span><span class="sxs-lookup"><span data-stu-id="10768-195">Drag and drop a <xref:System.Activities.Statements.TransactionScope> activity after the <xref:System.Activities.Statements.WriteLine> activity.</span></span>  <span data-ttu-id="10768-196">选择 <xref:System.Activities.Statements.TransactionScope> 活动，单击“变量”按钮，然后添加以下变量。</span><span class="sxs-lookup"><span data-stu-id="10768-196">Select the <xref:System.Activities.Statements.TransactionScope> activity, click the Variables button and add the following variables.</span></span>  
  
     <span data-ttu-id="10768-197">![向 TransactionScope 添加变量](../../../../docs/framework/wcf/feature-details/media/tsvariables.JPG "TSVariables")</span><span class="sxs-lookup"><span data-stu-id="10768-197">![Add variables to the TransactionScope](../../../../docs/framework/wcf/feature-details/media/tsvariables.JPG "TSVariables")</span></span>  
  
5.  <span data-ttu-id="10768-198">将 <xref:System.Activities.Statements.Sequence> 活动拖放到 <xref:System.Activities.Statements.TransactionScope> 活动的正文内。</span><span class="sxs-lookup"><span data-stu-id="10768-198">Drag and drop a <xref:System.Activities.Statements.Sequence> activity into the body of the <xref:System.Activities.Statements.TransactionScope> activity.</span></span>  
  
6.  <span data-ttu-id="10768-199">在 `PrintTransactionInfo` 内拖放 <xref:System.Activities.Statements.Sequence> 活动</span><span class="sxs-lookup"><span data-stu-id="10768-199">Drag and drop a `PrintTransactionInfo` activity within the <xref:System.Activities.Statements.Sequence></span></span>  
  
7.  <span data-ttu-id="10768-200">拖放式<xref:System.Activities.Statements.WriteLine>活动后的`PrintTransactionInfo`活动，并设置其<xref:System.Activities.Statements.WriteLine.Text%2A>属性设置为"Client: Beginning Send"。</span><span class="sxs-lookup"><span data-stu-id="10768-200">Drag and drop a <xref:System.Activities.Statements.WriteLine> activity after the `PrintTransactionInfo` activity and set its <xref:System.Activities.Statements.WriteLine.Text%2A> property to "Client: Beginning Send".</span></span> <span data-ttu-id="10768-201">现在，该工作流应如下所示：</span><span class="sxs-lookup"><span data-stu-id="10768-201">The workflow should now look like this:</span></span>  
  
     <span data-ttu-id="10768-202">![将活动添加](../../../../docs/framework/wcf/feature-details/media/clientaddcbswriteline.JPG "ClientAddCBSWriteLine")</span><span class="sxs-lookup"><span data-stu-id="10768-202">![Adding activities](../../../../docs/framework/wcf/feature-details/media/clientaddcbswriteline.JPG "ClientAddCBSWriteLine")</span></span>  
  
8.  <span data-ttu-id="10768-203">将 <xref:System.ServiceModel.Activities.Send> 活动拖放到 <xref:System.Activities.Statements.Assign> 活动后面，并设置以下属性：</span><span class="sxs-lookup"><span data-stu-id="10768-203">Drag and drop a <xref:System.ServiceModel.Activities.Send> activity after the <xref:System.Activities.Statements.Assign> activity and set the following properties:</span></span>  
  
    |<span data-ttu-id="10768-204">属性</span><span class="sxs-lookup"><span data-stu-id="10768-204">Property</span></span>|<span data-ttu-id="10768-205">值</span><span class="sxs-lookup"><span data-stu-id="10768-205">Value</span></span>|  
    |--------------|-----------|  
    |<span data-ttu-id="10768-206">EndpointConfigurationName</span><span class="sxs-lookup"><span data-stu-id="10768-206">EndpointConfigurationName</span></span>|<span data-ttu-id="10768-207">workflowServiceEndpoint</span><span class="sxs-lookup"><span data-stu-id="10768-207">workflowServiceEndpoint</span></span>|  
    |<span data-ttu-id="10768-208">OperationName</span><span class="sxs-lookup"><span data-stu-id="10768-208">OperationName</span></span>|<span data-ttu-id="10768-209">StartSample</span><span class="sxs-lookup"><span data-stu-id="10768-209">StartSample</span></span>|  
    |<span data-ttu-id="10768-210">ServiceContractName</span><span class="sxs-lookup"><span data-stu-id="10768-210">ServiceContractName</span></span>|<span data-ttu-id="10768-211">ITransactionSample</span><span class="sxs-lookup"><span data-stu-id="10768-211">ITransactionSample</span></span>|  
  
     <span data-ttu-id="10768-212">现在，该工作流应如下所示：</span><span class="sxs-lookup"><span data-stu-id="10768-212">The workflow should now look like this:</span></span>  
  
     <span data-ttu-id="10768-213">![设置 Send 活动属性](../../../../docs/framework/wcf/feature-details/media/clientsendsettings.JPG "ClientSendSettings")</span><span class="sxs-lookup"><span data-stu-id="10768-213">![Setting the Send activity properties](../../../../docs/framework/wcf/feature-details/media/clientsendsettings.JPG "ClientSendSettings")</span></span>  
  
9. <span data-ttu-id="10768-214">单击**定义...**链接，然后进行以下设置：</span><span class="sxs-lookup"><span data-stu-id="10768-214">Click the **Define...** link and make the following settings:</span></span>  
  
     <span data-ttu-id="10768-215">![发送消息设置的活动](../../../../docs/framework/wcf/feature-details/media/sendmessagesettings.JPG "SendMessageSettings")</span><span class="sxs-lookup"><span data-stu-id="10768-215">![Send activity message settings](../../../../docs/framework/wcf/feature-details/media/sendmessagesettings.JPG "SendMessageSettings")</span></span>  
  
10. <span data-ttu-id="10768-216">右键单击<xref:System.ServiceModel.Activities.Send>活动，并选择**创建 ReceiveReply**。</span><span class="sxs-lookup"><span data-stu-id="10768-216">Right click the <xref:System.ServiceModel.Activities.Send> activity and select **Create ReceiveReply**.</span></span> <span data-ttu-id="10768-217"><xref:System.ServiceModel.Activities.ReceiveReply> 活动将自动放在 <xref:System.ServiceModel.Activities.Send> 活动后面。</span><span class="sxs-lookup"><span data-stu-id="10768-217">The <xref:System.ServiceModel.Activities.ReceiveReply> activity will be automatically placed after the <xref:System.ServiceModel.Activities.Send> activity.</span></span>  
  
11. <span data-ttu-id="10768-218">单击 ReceiveReplyForSend 活动上的“定义...”链接，然后进行以下设置：</span><span class="sxs-lookup"><span data-stu-id="10768-218">Click the Define... link on the ReceiveReplyForSend activity and make the following settings:</span></span>  
  
     <span data-ttu-id="10768-219">![设置 ReceiveForSend 消息的设置](../../../../docs/framework/wcf/feature-details/media/clientreplymessagesettings.JPG "ClientReplyMessageSettings")</span><span class="sxs-lookup"><span data-stu-id="10768-219">![Setting the ReceiveForSend message settings](../../../../docs/framework/wcf/feature-details/media/clientreplymessagesettings.JPG "ClientReplyMessageSettings")</span></span>  
  
12. <span data-ttu-id="10768-220">将 <xref:System.Activities.Statements.WriteLine> 活动拖放到 <xref:System.ServiceModel.Activities.Send> 和 <xref:System.ServiceModel.Activities.ReceiveReply> 活动之间，然后将它的 <xref:System.Activities.Statements.WriteLine.Text%2A> 属性设置为 "Client: Send complete."</span><span class="sxs-lookup"><span data-stu-id="10768-220">Drag and drop a <xref:System.Activities.Statements.WriteLine> activity between the <xref:System.ServiceModel.Activities.Send> and <xref:System.ServiceModel.Activities.ReceiveReply> activities and set its <xref:System.Activities.Statements.WriteLine.Text%2A> property to "Client: Send complete."</span></span>  
  
13. <span data-ttu-id="10768-221">将 <xref:System.Activities.Statements.WriteLine> 活动拖放到 <xref:System.ServiceModel.Activities.ReceiveReply> 活动后面，然后将它的 <xref:System.Activities.Statements.WriteLine.Text%2A> 属性设置为 "Client side: Reply received = " + replyMessage</span><span class="sxs-lookup"><span data-stu-id="10768-221">Drag and drop a <xref:System.Activities.Statements.WriteLine> activity after the <xref:System.ServiceModel.Activities.ReceiveReply> activity and set its <xref:System.Activities.Statements.WriteLine.Text%2A> property to "Client side: Reply received = " + replyMessage</span></span>  
  
14. <span data-ttu-id="10768-222">将 `PrintTransactionInfo` 活动拖放到 <xref:System.Activities.Statements.WriteLine> 活动后面。</span><span class="sxs-lookup"><span data-stu-id="10768-222">Drag and drop a `PrintTransactionInfo` activity after the <xref:System.Activities.Statements.WriteLine> activity.</span></span>  
  
15. <span data-ttu-id="10768-223">将 <xref:System.Activities.Statements.WriteLine> 活动拖放到工作流末尾，然后将它的 <xref:System.Activities.Statements.WriteLine.Text%2A> 属性设置为 "Client workflow ends."</span><span class="sxs-lookup"><span data-stu-id="10768-223">Drag and drop a <xref:System.Activities.Statements.WriteLine> activity at the end of the workflow and set its <xref:System.Activities.Statements.WriteLine.Text%2A> property to "Client workflow ends."</span></span> <span data-ttu-id="10768-224">完成的客户端工作流应如下图所示。</span><span class="sxs-lookup"><span data-stu-id="10768-224">The completed client workflow should look like the following diagram.</span></span>  
  
     <span data-ttu-id="10768-225">![已完成客户端工作流](../../../../docs/framework/wcf/feature-details/media/clientcompleteworkflow.jpg "ClientCompleteWorkflow")</span><span class="sxs-lookup"><span data-stu-id="10768-225">![The completed client workfliow](../../../../docs/framework/wcf/feature-details/media/clientcompleteworkflow.jpg "ClientCompleteWorkflow")</span></span>  
  
16. <span data-ttu-id="10768-226">生成解决方案。</span><span class="sxs-lookup"><span data-stu-id="10768-226">Build the solution.</span></span>  
  
### <a name="create-the-service-application"></a><span data-ttu-id="10768-227">创建服务应用程序</span><span class="sxs-lookup"><span data-stu-id="10768-227">Create the Service application</span></span>  
  
1.  <span data-ttu-id="10768-228">将一个名为 `Service` 的新控制台应用程序项目添加到该解决方案。</span><span class="sxs-lookup"><span data-stu-id="10768-228">Add a new Console Application project called `Service` to the solution.</span></span> <span data-ttu-id="10768-229">添加对下列程序集的引用：</span><span class="sxs-lookup"><span data-stu-id="10768-229">Add references to the following assemblies:</span></span>  
  
    1.  <span data-ttu-id="10768-230">System.Activities.dll</span><span class="sxs-lookup"><span data-stu-id="10768-230">System.Activities.dll</span></span>  
  
    2.  <span data-ttu-id="10768-231">System.ServiceModel.dll</span><span class="sxs-lookup"><span data-stu-id="10768-231">System.ServiceModel.dll</span></span>  
  
    3.  <span data-ttu-id="10768-232">System.ServiceModel.Activities.dll</span><span class="sxs-lookup"><span data-stu-id="10768-232">System.ServiceModel.Activities.dll</span></span>  
  
2.  <span data-ttu-id="10768-233">打开生成的 Program.cs 文件并添加以下代码：</span><span class="sxs-lookup"><span data-stu-id="10768-233">Open the generated Program.cs file and the following code:</span></span>  
  
    ```  
    static void Main()  
          {  
              Console.WriteLine("Building the server.");  
              using (WorkflowServiceHost host = new WorkflowServiceHost(new DeclarativeServiceWorkflow(), new Uri("net.tcp://localhost:8000/TransactedReceiveService/Declarative")))  
              {                
                  //Start the server  
                  host.Open();  
                  Console.WriteLine("Service started.");  
  
                  Console.WriteLine();  
                  Console.ReadLine();  
                  //Shutdown  
                  host.Close();  
              };         
          }  
    ```  
  
3.  <span data-ttu-id="10768-234">将以下 app.config 文件添加到项目。</span><span class="sxs-lookup"><span data-stu-id="10768-234">Add the following app.config file to the project.</span></span>  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8" ?>  
    <!-- Copyright © Microsoft Corporation.  All rights reserved. -->  
    <configuration>  
        <system.serviceModel>  
            <bindings>  
                <netTcpBinding>  
                    <binding transactionFlow="true" />  
                </netTcpBinding>  
            </bindings>  
        </system.serviceModel>  
    </configuration>  
    ```  
  
### <a name="create-the-client-application"></a><span data-ttu-id="10768-235">创建客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="10768-235">Create the client application</span></span>  
  
1.  <span data-ttu-id="10768-236">将一个名为 `Client` 的新控制台应用程序项目添加到该解决方案。</span><span class="sxs-lookup"><span data-stu-id="10768-236">Add a new Console Application project called `Client` to the solution.</span></span> <span data-ttu-id="10768-237">添加对 System.Activities.dll 的引用。</span><span class="sxs-lookup"><span data-stu-id="10768-237">Add a reference to System.Activities.dll.</span></span>  
  
2.  <span data-ttu-id="10768-238">打开 program.cs 文件并添加以下代码。</span><span class="sxs-lookup"><span data-stu-id="10768-238">Open the program.cs file and add the following code.</span></span>  
  
    ```  
    class Program  
        {  
  
            private static AutoResetEvent syncEvent = new AutoResetEvent(false);  
  
            static void Main(string[] args)  
            {  
                //Build client  
                Console.WriteLine("Building the client.");  
                WorkflowApplication client = new WorkflowApplication(new DeclarativeClientWorkflow());  
                client.Completed = Program.Completed;  
                client.Aborted = Program.Aborted;  
                client.OnUnhandledException = Program.OnUnhandledException;  
  
                //Wait for service to start  
                Console.WriteLine("Press ENTER once service is started.");  
                Console.ReadLine();  
  
                //Start the client              
                Console.WriteLine("Starting the client.");  
                client.Run();  
                syncEvent.WaitOne();  
  
                //Sample complete  
                Console.WriteLine();  
                Console.WriteLine("Client complete. Press ENTER to exit.");  
                Console.ReadLine();  
            }  
  
            private static void Completed(WorkflowApplicationCompletedEventArgs e)  
            {  
                Program.syncEvent.Set();  
            }  
  
            private static void Aborted(WorkflowApplicationAbortedEventArgs e)  
            {  
                Console.WriteLine("Client Aborted: {0}", e.Reason);  
                Program.syncEvent.Set();  
            }  
  
            private static UnhandledExceptionAction OnUnhandledException(WorkflowApplicationUnhandledExceptionEventArgs e)  
            {  
                Console.WriteLine("Client had an unhandled exception: {0}", e.UnhandledException);  
                return UnhandledExceptionAction.Cancel;  
            }  
        }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="10768-239">另请参阅</span><span class="sxs-lookup"><span data-stu-id="10768-239">See Also</span></span>  
 [<span data-ttu-id="10768-240">工作流服务</span><span class="sxs-lookup"><span data-stu-id="10768-240">Workflow Services</span></span>](../../../../docs/framework/wcf/feature-details/workflow-services.md)  
 [<span data-ttu-id="10768-241">Windows Communication Foundation 事务概述</span><span class="sxs-lookup"><span data-stu-id="10768-241">Windows Communication Foundation Transactions Overview</span></span>](../../../../docs/framework/wcf/feature-details/transactions-overview.md)  
 [<span data-ttu-id="10768-242">使用 TransactedReceiveScope</span><span class="sxs-lookup"><span data-stu-id="10768-242">Use of TransactedReceiveScope</span></span>](../../../../docs/framework/windows-workflow-foundation/samples/use-of-transactedreceivescope.md)
