---
title: "如何：使用消息传递活动创建工作流服务"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 53d094e2-6901-4aa1-88b8-024b27ccf78b
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b57139fdf2a07f2d37bc337a041704eee174328e
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-create-a-workflow-service-with-messaging-activities"></a><span data-ttu-id="51b3e-102">如何：使用消息传递活动创建工作流服务</span><span class="sxs-lookup"><span data-stu-id="51b3e-102">How to: Create a Workflow Service with Messaging Activities</span></span>
<span data-ttu-id="51b3e-103">此主题说明如何使用消息传递活动创建简单工作流服务，</span><span class="sxs-lookup"><span data-stu-id="51b3e-103">This topic describes how to create a simple workflow service using messaging activities.</span></span> <span data-ttu-id="51b3e-104">本主题着重介绍工作流服务的创建机制，其中的服务仅包含消息传递活动。</span><span class="sxs-lookup"><span data-stu-id="51b3e-104">This topic focuses on the mechanics of creating a workflow service where the service consists solely of messaging activities.</span></span> <span data-ttu-id="51b3e-105">在实际服务中，工作流包含其他许多活动。</span><span class="sxs-lookup"><span data-stu-id="51b3e-105">In a real-world service, the workflow contains many other activities.</span></span> <span data-ttu-id="51b3e-106">该服务实现一个名为 Echo 的操作，来获取一个字符串并将该字符串返回到调用方。</span><span class="sxs-lookup"><span data-stu-id="51b3e-106">The service implements one operation called Echo, which takes a string and returns the string to the caller.</span></span> <span data-ttu-id="51b3e-107">本主题是一系列主题（包含两个主题）中的第一个。</span><span class="sxs-lookup"><span data-stu-id="51b3e-107">This topic is the first in a series of two topics.</span></span> <span data-ttu-id="51b3e-108">下一主题[How To: 服务从工作流应用程序访问](../../../../docs/framework/wcf/feature-details/how-to-access-a-service-from-a-workflow-application.md)讨论如何创建工作流应用程序可以调用在本主题中创建服务。</span><span class="sxs-lookup"><span data-stu-id="51b3e-108">The next topic [How To: Access a Service From a Workflow Application](../../../../docs/framework/wcf/feature-details/how-to-access-a-service-from-a-workflow-application.md) discusses how to create a workflow application that can call the service created in this topic.</span></span>  
  
### <a name="to-create-a-workflow-service-project"></a><span data-ttu-id="51b3e-109">创建工作流服务项目</span><span class="sxs-lookup"><span data-stu-id="51b3e-109">To create a workflow service project</span></span>  
  
1.  <span data-ttu-id="51b3e-110">启动 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="51b3e-110">Start [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].</span></span>  
  
2.  <span data-ttu-id="51b3e-111">单击**文件**菜单上，选择**新建**，，然后**项目**以显示**新建项目对话框**。</span><span class="sxs-lookup"><span data-stu-id="51b3e-111">Click the **File** menu, select **New**, and then **Project** to display the **New Project Dialog**.</span></span> <span data-ttu-id="51b3e-112">选择**工作流**从已安装模板列表和**WCF 工作流服务应用程序**从项目类型列表。</span><span class="sxs-lookup"><span data-stu-id="51b3e-112">Select **Workflow** from the list of installed templates and **WCF Workflow Service Application** from the list of project types.</span></span> <span data-ttu-id="51b3e-113">将项目`MyWFService`，并且使用默认位置，如下面的插图中所示。</span><span class="sxs-lookup"><span data-stu-id="51b3e-113">Name the project `MyWFService` and use the default location as shown in the following illustration.</span></span>  
  
     <span data-ttu-id="51b3e-114">单击**确定**按钮以关闭**新建项目对话框**。</span><span class="sxs-lookup"><span data-stu-id="51b3e-114">Click the **OK** button to dismiss the **New Project Dialog**.</span></span>  
  
3.  <span data-ttu-id="51b3e-115">创建项目之后，将在设计器中打开 Service1.xamlx 文件，如以下插图所示。</span><span class="sxs-lookup"><span data-stu-id="51b3e-115">When the project is created, the Service1.xamlx file is opened in the designer as shown in the following illustration.</span></span>  
  
     <span data-ttu-id="51b3e-116">![设计器中显示的默认工作流](../../../../docs/framework/wcf/feature-details/media/defaultworkflowservice.JPG "DefaultWorkflowService")</span><span class="sxs-lookup"><span data-stu-id="51b3e-116">![The default workflow displayed in the designer](../../../../docs/framework/wcf/feature-details/media/defaultworkflowservice.JPG "DefaultWorkflowService")</span></span>  
  
     <span data-ttu-id="51b3e-117">右键单击标记为活动**顺序服务**和选择**删除**。</span><span class="sxs-lookup"><span data-stu-id="51b3e-117">Right-click the activity labeled **Sequential Service** and select **Delete**.</span></span>  
  
### <a name="to-implement-the-workflow-service"></a><span data-ttu-id="51b3e-118">实现工作流服务</span><span class="sxs-lookup"><span data-stu-id="51b3e-118">To implement the workflow service</span></span>  
  
1.  <span data-ttu-id="51b3e-119">选择**工具箱**屏幕显示工具箱，然后单击图钉保持窗口打开左侧的选项卡。</span><span class="sxs-lookup"><span data-stu-id="51b3e-119">Select the **Toolbox** tab on the left side of the screen to display the toolbox and click the pushpin to keep the window open.</span></span> <span data-ttu-id="51b3e-120">展开**消息**部分的工具箱以显示消息传递活动和消息传递活动模板，如在下图中所示。</span><span class="sxs-lookup"><span data-stu-id="51b3e-120">Expand the **Messaging** section of the toolbox to display the messaging activities and the messaging activity templates as shown in the following illustration.</span></span>  
  
     <span data-ttu-id="51b3e-121">![扩展了消息传送选项卡的工具箱](../../../../docs/framework/wcf/feature-details/media/wfdesignertoolbox.JPG "WFDesignerToolbox")</span><span class="sxs-lookup"><span data-stu-id="51b3e-121">![The toolbox with messaging tab expanded](../../../../docs/framework/wcf/feature-details/media/wfdesignertoolbox.JPG "WFDesignerToolbox")</span></span>  
  
2.  <span data-ttu-id="51b3e-122">拖放式**ReceiveAndSendReply**到工作流设计器的模板。</span><span class="sxs-lookup"><span data-stu-id="51b3e-122">Drag and drop a **ReceiveAndSendReply** template to the workflow designer.</span></span> <span data-ttu-id="51b3e-123">这将创建<!--zz <xref:System.ServiceModel.Activities.Sequence>-->`System.ServiceModel.Activities.Sequence`活动**接收**活动跟<xref:System.ServiceModel.Activities.SendReply>活动下图中所示。</span><span class="sxs-lookup"><span data-stu-id="51b3e-123">This creates a <!--zz <xref:System.ServiceModel.Activities.Sequence>--> `System.ServiceModel.Activities.Sequence` activity with a **Receive** activity followed by a <xref:System.ServiceModel.Activities.SendReply> activity as shown in the following illustration.</span></span>  
  
     <span data-ttu-id="51b3e-124">![在设计器中的 ReceiveAndSendReply 模板](../../../../docs/framework/wcf/feature-details/media/receiveandsendreply.JPG "ReceiveAndSendReply")</span><span class="sxs-lookup"><span data-stu-id="51b3e-124">![ReceiveAndSendReply template in designer](../../../../docs/framework/wcf/feature-details/media/receiveandsendreply.JPG "ReceiveAndSendReply")</span></span>  
  
     <span data-ttu-id="51b3e-125">请注意，已将 <xref:System.ServiceModel.Activities.SendReply> 活动的<xref:System.ServiceModel.Activities.SendReply.Request%2A> 属性设置为 `Receive`，即<xref:System.ServiceModel.Activities.Receive> 活动要答复的<xref:System.ServiceModel.Activities.SendReply> 活动的名称。</span><span class="sxs-lookup"><span data-stu-id="51b3e-125">Notice that the <xref:System.ServiceModel.Activities.SendReply> activity’s <xref:System.ServiceModel.Activities.SendReply.Request%2A> property is set to `Receive`, the name of the <xref:System.ServiceModel.Activities.Receive> activity to which the <xref:System.ServiceModel.Activities.SendReply> activity is replying.</span></span>  
  
3.  <span data-ttu-id="51b3e-126">在<xref:System.ServiceModel.Activities.Receive>活动类型`Echo`标记为文本框**OperationName**。</span><span class="sxs-lookup"><span data-stu-id="51b3e-126">In the <xref:System.ServiceModel.Activities.Receive> activity type `Echo` into the textbox labeled **OperationName**.</span></span> <span data-ttu-id="51b3e-127">此步骤定义服务所实现操作的名称。</span><span class="sxs-lookup"><span data-stu-id="51b3e-127">This defines the name of the operation the service implements.</span></span>  
  
     <span data-ttu-id="51b3e-128">![指定操作名称](../../../../docs/framework/wcf/feature-details/media/defineoperation.JPG "DefineOperation")</span><span class="sxs-lookup"><span data-stu-id="51b3e-128">![Specify the operation name](../../../../docs/framework/wcf/feature-details/media/defineoperation.JPG "DefineOperation")</span></span>  
  
4.  <span data-ttu-id="51b3e-129">与<xref:System.ServiceModel.Activities.Receive>活动选择，打开属性窗口如果不是通过单击已打开**视图**菜单并选择**属性窗口**。</span><span class="sxs-lookup"><span data-stu-id="51b3e-129">With the <xref:System.ServiceModel.Activities.Receive> activity selected, open the properties window if not already open by clicking the **View** menu and selecting **Properties Window**.</span></span> <span data-ttu-id="51b3e-130">在**属性窗口**向下滚动，直到你看到**CanCreateInstance**单击复选框，如在下图中所示。</span><span class="sxs-lookup"><span data-stu-id="51b3e-130">In the **Properties Window** scroll down until you see **CanCreateInstance** and click the checkbox as shown in the following illustration.</span></span> <span data-ttu-id="51b3e-131">此设置使工作流服务主机可以在接收消息时创建服务的新实例（如果需要）。</span><span class="sxs-lookup"><span data-stu-id="51b3e-131">This setting enables the workflow service host to create a new instance of the service (if needed) when a message is received.</span></span>  
  
     <span data-ttu-id="51b3e-132">![CanCreateInstance 属性](../../../../docs/framework/wcf/feature-details/media/cancreateinstance.JPG "CanCreateInstance")</span><span class="sxs-lookup"><span data-stu-id="51b3e-132">![CanCreateInstance property](../../../../docs/framework/wcf/feature-details/media/cancreateinstance.JPG "CanCreateInstance")</span></span>  
  
5.  <span data-ttu-id="51b3e-133">选择<!--zz <xref:System.ServiceModel.Activities.Sequence>-->`System.ServiceModel.Activities.Sequence`活动，然后单击**变量**中的设计器左下角的按钮。</span><span class="sxs-lookup"><span data-stu-id="51b3e-133">Select the <!--zz <xref:System.ServiceModel.Activities.Sequence>--> `System.ServiceModel.Activities.Sequence` activity and click the **Variables** button in the lower left corner of the designer.</span></span> <span data-ttu-id="51b3e-134">这样将显示变量编辑器。</span><span class="sxs-lookup"><span data-stu-id="51b3e-134">This displays the variables editor.</span></span> <span data-ttu-id="51b3e-135">单击**创建变量**链接添加变量来存储发送到操作的字符串。</span><span class="sxs-lookup"><span data-stu-id="51b3e-135">Click the **Create Variable** link to add a variable to store the string sent to the operation.</span></span> <span data-ttu-id="51b3e-136">将变量命名`msg`并设置其**变量**类型到字符串，如下面的插图中所示。</span><span class="sxs-lookup"><span data-stu-id="51b3e-136">Name the variable `msg` and set its **Variable** type to String as shown in the following illustration.</span></span>  
  
     <span data-ttu-id="51b3e-137">![添加变量](../../../../docs/framework/wcf/feature-details/media/addvariable.JPG "AddVariable")</span><span class="sxs-lookup"><span data-stu-id="51b3e-137">![Add a variable](../../../../docs/framework/wcf/feature-details/media/addvariable.JPG "AddVariable")</span></span>  
  
     <span data-ttu-id="51b3e-138">单击**变量**按钮以关闭变量编辑器。</span><span class="sxs-lookup"><span data-stu-id="51b3e-138">Click the **Variables** button again to close the variables editor.</span></span>  
  
6.  <span data-ttu-id="51b3e-139">单击**定义...**</span><span class="sxs-lookup"><span data-stu-id="51b3e-139">Click the **Define..**</span></span> <span data-ttu-id="51b3e-140">在链接**内容**文本框中<xref:System.ServiceModel.Activities.Receive>活动来显示**内容定义**对话框。</span><span class="sxs-lookup"><span data-stu-id="51b3e-140">link in the **Content** text box in the <xref:System.ServiceModel.Activities.Receive> activity to display the **Content Definition** dialog.</span></span> <span data-ttu-id="51b3e-141">选择**参数**单选按钮，单击**添加新参数**链接，键入`inMsg`中**名称**文本框中，选择**字符串**中**类型**下拉列表框中，并键入`msg`中**分配到**文本框中，如下面的插图中所示。</span><span class="sxs-lookup"><span data-stu-id="51b3e-141">Select the **Parameters** radio button, click the **Add new Parameter** link, type `inMsg` in the **name** text box, select **String** in the **Type** drop down list box, and type `msg` in the **Assign To** text box as shown in the following illustration.</span></span>  
  
     <span data-ttu-id="51b3e-142">![添加参数内容](../../../../docs/framework/wcf/feature-details/media/parameterscontent.jpg "ParametersContent")</span><span class="sxs-lookup"><span data-stu-id="51b3e-142">![Adding Parameters Content](../../../../docs/framework/wcf/feature-details/media/parameterscontent.jpg "ParametersContent")</span></span>  
  
     <span data-ttu-id="51b3e-143">此步骤指定由 Receive 活动接收字符串参数，并且将该数据绑定到 `msg` 变量。</span><span class="sxs-lookup"><span data-stu-id="51b3e-143">This specifies that the Receive activity receives string parameter and that data is bound to the `msg` variable.</span></span> <span data-ttu-id="51b3e-144">单击**确定**关闭**内容定义**对话框。</span><span class="sxs-lookup"><span data-stu-id="51b3e-144">Click **OK** to close the **Content Definition** dialog.</span></span>  
  
7.  <span data-ttu-id="51b3e-145">单击**定义...**中链接**内容**框中<xref:System.ServiceModel.Activities.SendReply>活动来显示**内容定义**对话框。</span><span class="sxs-lookup"><span data-stu-id="51b3e-145">Click the **Define...** link in the **Content** box in the <xref:System.ServiceModel.Activities.SendReply> activity to display the **Content Definition** dialog.</span></span> <span data-ttu-id="51b3e-146">选择**参数**单选按钮，单击**添加新参数**链接，键入`outMsg`中**名称**文本框中，选择**字符串**中**类型**下拉列表框中，和`msg`中**值**文本框中，如下面的插图中所示。</span><span class="sxs-lookup"><span data-stu-id="51b3e-146">Select the **Parameters** radio button, click the **Add new Parameter** link, type `outMsg` in the **name** textbox, select **String** in the **Type** dropdown list box, and `msg` in the **Value** text box as shown in the following illustration.</span></span>  
  
     <span data-ttu-id="51b3e-147">![添加参数内容](../../../../docs/framework/wcf/feature-details/media/parameterscontent2.jpg "ParametersContent2")</span><span class="sxs-lookup"><span data-stu-id="51b3e-147">![Adding Parameters Content](../../../../docs/framework/wcf/feature-details/media/parameterscontent2.jpg "ParametersContent2")</span></span>  
  
     <span data-ttu-id="51b3e-148">此步骤指定由 <xref:System.ServiceModel.Activities.SendReply> 活动发送消息或消息协定类型，并且将该数据绑定到 `msg` 变量。</span><span class="sxs-lookup"><span data-stu-id="51b3e-148">This specifies that the <xref:System.ServiceModel.Activities.SendReply> activity sends a message or message contract type and that data is bound to the `msg` variable.</span></span> <span data-ttu-id="51b3e-149">由于此活动是 <xref:System.ServiceModel.Activities.SendReply> 活动，因此这意味着 `msg` 中的数据用于填充活动发送回客户端的消息。</span><span class="sxs-lookup"><span data-stu-id="51b3e-149">Because this is a <xref:System.ServiceModel.Activities.SendReply> activity, this means the data in `msg` is used to populate the message the activity sends back to the client.</span></span> <span data-ttu-id="51b3e-150">单击**确定**关闭**内容定义**对话框。</span><span class="sxs-lookup"><span data-stu-id="51b3e-150">Click **OK** to close the **Content Definition** dialog.</span></span>  
  
8.  <span data-ttu-id="51b3e-151">保存并生成解决方案，通过单击**生成**菜单并选择**生成解决方案**。</span><span class="sxs-lookup"><span data-stu-id="51b3e-151">Save and build the solution by clicking the **Build** menu and selecting **Build Solution**.</span></span>  
  
## <a name="configure-the-workflow-service-project"></a><span data-ttu-id="51b3e-152">配置工作流服务项目</span><span class="sxs-lookup"><span data-stu-id="51b3e-152">Configure the Workflow Service Project</span></span>  
 <span data-ttu-id="51b3e-153">现在工作流服务是完整的。</span><span class="sxs-lookup"><span data-stu-id="51b3e-153">The workflow service is complete.</span></span> <span data-ttu-id="51b3e-154">本节介绍如何配置工作流服务解决方案以易于承载和运行。</span><span class="sxs-lookup"><span data-stu-id="51b3e-154">This section explains how to configure the workflow service solution to make it easy to host and run.</span></span> <span data-ttu-id="51b3e-155">此解决方案使用 ASP.NET Development Server 承载服务。</span><span class="sxs-lookup"><span data-stu-id="51b3e-155">This solution uses the ASP.NET Development Server to host the service.</span></span>  
  
#### <a name="to-set-project-start-up-options"></a><span data-ttu-id="51b3e-156">设置项目启动选项</span><span class="sxs-lookup"><span data-stu-id="51b3e-156">To set project start up options</span></span>  
  
1.  <span data-ttu-id="51b3e-157">在**解决方案资源管理器**，右键单击**MyWFService**和选择**属性**以显示**项目属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="51b3e-157">In the **Solution Explorer**, right-click **MyWFService** and select **Properties** to display the **Project Properties** dialog.</span></span>  
  
2.  <span data-ttu-id="51b3e-158">选择**Web**选项卡并选择**特定页**下**启动操作**和类型`Service1.xamlx`在文本框中，如下面的插图中所示。</span><span class="sxs-lookup"><span data-stu-id="51b3e-158">Select the **Web** tab and select **Specific Page** under **Start Action** and type `Service1.xamlx` in the text box as shown in the following illustration.</span></span>  
  
     <span data-ttu-id="51b3e-159">![项目属性对话框](../../../../docs/framework/wcf/feature-details/media/projectpropertiesdlg.JPG "ProjectPropertiesDlg")</span><span class="sxs-lookup"><span data-stu-id="51b3e-159">![The project properties dialog](../../../../docs/framework/wcf/feature-details/media/projectpropertiesdlg.JPG "ProjectPropertiesDlg")</span></span>  
  
     <span data-ttu-id="51b3e-160">此步骤在 ASP.NET Development Server 中承载 Service1.xamlx 中定义的服务。</span><span class="sxs-lookup"><span data-stu-id="51b3e-160">This hosts the service defined in Service1.xamlx in the ASP.NET Development Server.</span></span>  
  
3.  <span data-ttu-id="51b3e-161">按 Ctrl + F5 启动服务。</span><span class="sxs-lookup"><span data-stu-id="51b3e-161">Press Ctrl + F5 to launch the service.</span></span> <span data-ttu-id="51b3e-162">ASP.NET Development Server 图标显示在桌面的右下角，如以下图像所示。</span><span class="sxs-lookup"><span data-stu-id="51b3e-162">The ASP.NET Development Server icon is displayed in the lower right side of the desktop as shown in the following image.</span></span>  
  
     <span data-ttu-id="51b3e-163">![ASP.NET 开发服务器图标](../../../../docs/framework/wcf/feature-details/media/aspnetdevservericon.JPG "ASPNETDEVServerIcon")</span><span class="sxs-lookup"><span data-stu-id="51b3e-163">![The ASP.NET Developer Server Icon](../../../../docs/framework/wcf/feature-details/media/aspnetdevservericon.JPG "ASPNETDEVServerIcon")</span></span>  
  
     <span data-ttu-id="51b3e-164">此外，Internet Explorer 显示服务的 WCF 服务帮助页。</span><span class="sxs-lookup"><span data-stu-id="51b3e-164">In addition, Internet Explorer displays the WCF Service Help Page for the service.</span></span>  
  
     <span data-ttu-id="51b3e-165">![WCF 帮助页](../../../../docs/framework/wcf/feature-details/media/wcfhelppate.JPG "WCFHelpPate")</span><span class="sxs-lookup"><span data-stu-id="51b3e-165">![WCF Help Page](../../../../docs/framework/wcf/feature-details/media/wcfhelppate.JPG "WCFHelpPate")</span></span>  
  
4.  <span data-ttu-id="51b3e-166">继续[How To: 服务从工作流应用程序访问](../../../../docs/framework/wcf/feature-details/how-to-access-a-service-from-a-workflow-application.md)主题，以创建调用此服务的工作流客户端。</span><span class="sxs-lookup"><span data-stu-id="51b3e-166">Continue on to the [How To: Access a Service From a Workflow Application](../../../../docs/framework/wcf/feature-details/how-to-access-a-service-from-a-workflow-application.md) topic to create a workflow client that calls this service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51b3e-167">另请参阅</span><span class="sxs-lookup"><span data-stu-id="51b3e-167">See Also</span></span>  
 [<span data-ttu-id="51b3e-168">工作流服务</span><span class="sxs-lookup"><span data-stu-id="51b3e-168">Workflow Services</span></span>](../../../../docs/framework/wcf/feature-details/workflow-services.md)  
 [<span data-ttu-id="51b3e-169">承载工作流服务概述</span><span class="sxs-lookup"><span data-stu-id="51b3e-169">Hosting Workflow Services Overview</span></span>](../../../../docs/framework/wcf/feature-details/hosting-workflow-services-overview.md)  
 [<span data-ttu-id="51b3e-170">消息传递活动</span><span class="sxs-lookup"><span data-stu-id="51b3e-170">Messaging Activities</span></span>](../../../../docs/framework/wcf/feature-details/messaging-activities.md)
