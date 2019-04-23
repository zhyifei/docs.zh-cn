---
title: 文档审批过程
ms.date: 03/30/2017
ms.assetid: 9b240937-76a7-45cd-8823-7f82c34d03bd
ms.openlocfilehash: dfc2e0a12d053733823427ac50066b1e4a0f97aa
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59770394"
---
# <a name="document-approval-process"></a><span data-ttu-id="ce3dd-102">文档审批过程</span><span class="sxs-lookup"><span data-stu-id="ce3dd-102">Document Approval Process</span></span>
<span data-ttu-id="ce3dd-103">此示例演示在一起的多个 Windows Workflow Foundation (WF) 和 Windows Communication Foundation (WCF) 功能的使用。</span><span class="sxs-lookup"><span data-stu-id="ce3dd-103">This sample demonstrates the use of many Windows Workflow Foundation (WF) and Windows Communication Foundation (WCF) features together.</span></span> <span data-ttu-id="ce3dd-104">这些功能一起使用实现一个文档审批过程方案。</span><span class="sxs-lookup"><span data-stu-id="ce3dd-104">Together they implement a document approval process scenario.</span></span> <span data-ttu-id="ce3dd-105">客户端应用程序既可提交等待审批的文档，也可批准文档。</span><span class="sxs-lookup"><span data-stu-id="ce3dd-105">A client application can submit documents for approval and approve documents.</span></span> <span data-ttu-id="ce3dd-106">有一个审批管理器应用程序，可用于促进客户端之间的通信和强制执行审批过程的规则。</span><span class="sxs-lookup"><span data-stu-id="ce3dd-106">An approval manager application exists to facilitate communications between clients and to enforce the rules of the approval process.</span></span> <span data-ttu-id="ce3dd-107">审批过程是一个可执行多种类型的审批的工作流。</span><span class="sxs-lookup"><span data-stu-id="ce3dd-107">The approval process is a workflow that can execute several types of approval.</span></span> <span data-ttu-id="ce3dd-108">存在多个活动来获取个人审批过程、团体审批过程（一定百分比的审批者）和复合审批过程（由团体审批和个人审批按顺序组成）。</span><span class="sxs-lookup"><span data-stu-id="ce3dd-108">Activities exist to get a single approval, a quorum approval (a percentage of set of approvers), and a complex approval process that consists of a quorum and single approval in a sequence.</span></span>

> [!IMPORTANT]
>  <span data-ttu-id="ce3dd-109">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="ce3dd-109">The samples may already be installed on your machine.</span></span> <span data-ttu-id="ce3dd-110">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="ce3dd-110">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="ce3dd-111">如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](https://go.microsoft.com/fwlink/?LinkId=150780)若要下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。</span><span class="sxs-lookup"><span data-stu-id="ce3dd-111">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="ce3dd-112">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="ce3dd-112">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Application\DocumentApprovalProcess`  
  
## <a name="sample-details"></a><span data-ttu-id="ce3dd-113">示例详细信息</span><span class="sxs-lookup"><span data-stu-id="ce3dd-113">Sample Details</span></span>  
 <span data-ttu-id="ce3dd-114">下图演示文档审批过程工作流：</span><span class="sxs-lookup"><span data-stu-id="ce3dd-114">The following graphic demonstrates the document approval process workflow:</span></span>  
  
 ![文档审批进程工作流](./media/document-approval-process/document-approval-process.jpg)  
  
 <span data-ttu-id="ce3dd-116">从客户端的角度来看，审批过程的工作方式如下：</span><span class="sxs-lookup"><span data-stu-id="ce3dd-116">From the client's perspective, the approval process functions as follows:</span></span>  
  
1. <span data-ttu-id="ce3dd-117">客户端申请成为审批过程系统中的用户。</span><span class="sxs-lookup"><span data-stu-id="ce3dd-117">A client subscribes to be a user in the approval process system.</span></span>  
  
2. <span data-ttu-id="ce3dd-118">WCF 客户端将发送到审批管理器应用程序承载的 WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="ce3dd-118">A WCF client sends to a WCF service hosted by the approval manager application.</span></span>  
  
3. <span data-ttu-id="ce3dd-119">将唯一的用户 ID 返回到客户端。</span><span class="sxs-lookup"><span data-stu-id="ce3dd-119">A unique user ID is returned to the client.</span></span> <span data-ttu-id="ce3dd-120">此时，客户端可参与审批过程。</span><span class="sxs-lookup"><span data-stu-id="ce3dd-120">The client can now participate in approval processes.</span></span>  
  
4. <span data-ttu-id="ce3dd-121">客户端在加入后可发送文档以通过个人审批过程、团体审批过程或复合审批过程进行审批。</span><span class="sxs-lookup"><span data-stu-id="ce3dd-121">Once joined, a client can send a document for approval using single, quorum or complex approval processes.</span></span>  
  
5. <span data-ttu-id="ce3dd-122">单击客户端界面中的按钮，在客户端工作流服务主机中启动工作流实例。</span><span class="sxs-lookup"><span data-stu-id="ce3dd-122">A button in the client’s interface is clicked, starting a workflow instance in a client Workflow Service Host.</span></span>  
  
6. <span data-ttu-id="ce3dd-123">工作流将审批请求发送到审批管理器应用程序。</span><span class="sxs-lookup"><span data-stu-id="ce3dd-123">The workflow sends an approval request to the approval manager application.</span></span>  
  
7. <span data-ttu-id="ce3dd-124">工作流管理器启动其自身的工作流以表示审批过程。</span><span class="sxs-lookup"><span data-stu-id="ce3dd-124">The workflow manager starts a workflow on its own side to represent an approval process.</span></span>  
  
8. <span data-ttu-id="ce3dd-125">一旦执行管理器审批工作流，就会将结果发送回客户端。</span><span class="sxs-lookup"><span data-stu-id="ce3dd-125">Once the manager approval workflow executes, the results are sent back to the client.</span></span>  
  
9. <span data-ttu-id="ce3dd-126">客户端显示结果。</span><span class="sxs-lookup"><span data-stu-id="ce3dd-126">The client displays the results.</span></span>  
  
10. <span data-ttu-id="ce3dd-127">客户端可以随时接收审批请求并对其做出响应。</span><span class="sxs-lookup"><span data-stu-id="ce3dd-127">A client may receive an approval request and respond to the request at any point in time.</span></span>  
  
11. <span data-ttu-id="ce3dd-128">在客户端上承载的 WCF 服务可以从审批管理器应用程序接收审批请求。</span><span class="sxs-lookup"><span data-stu-id="ce3dd-128">A WCF service hosted on the client can receive an approval request from the approval manager application.</span></span>  
  
12. <span data-ttu-id="ce3dd-129">客户端上将呈现文档信息以供审阅。</span><span class="sxs-lookup"><span data-stu-id="ce3dd-129">The document information is presented on the client for review.</span></span>  
  
13. <span data-ttu-id="ce3dd-130">用户可以批准或拒绝文档。</span><span class="sxs-lookup"><span data-stu-id="ce3dd-130">The user can approve or reject the document.</span></span>  
  
14. <span data-ttu-id="ce3dd-131">WCF 客户端用于发送回审批管理器应用程序审批响应。</span><span class="sxs-lookup"><span data-stu-id="ce3dd-131">A WCF client is used to send an approval response back to the approval manager application.</span></span>  
  
 <span data-ttu-id="ce3dd-132">从审批管理器应用程序的角度来看，审批过程的工作方式如下：</span><span class="sxs-lookup"><span data-stu-id="ce3dd-132">From the approval manager application’s point of view, the approval process functions as follows:</span></span>  
  
1. <span data-ttu-id="ce3dd-133">客户端请求加入审批过程系统。</span><span class="sxs-lookup"><span data-stu-id="ce3dd-133">A client requests to participate to the approval process system.</span></span>  
  
2. <span data-ttu-id="ce3dd-134">审批管理器上的 WCF 服务接收的请求成为审批过程系统的一部分。</span><span class="sxs-lookup"><span data-stu-id="ce3dd-134">A WCF service on the approval manager receives a request to be part of the approval process system.</span></span>  
  
3. <span data-ttu-id="ce3dd-135">为客户端生成唯一的 ID。</span><span class="sxs-lookup"><span data-stu-id="ce3dd-135">A unique ID is generated for the client.</span></span> <span data-ttu-id="ce3dd-136">将用户信息存储在数据库中。</span><span class="sxs-lookup"><span data-stu-id="ce3dd-136">The user information is stored in a database.</span></span>  
  
4. <span data-ttu-id="ce3dd-137">将唯一的 ID 发送回用户。</span><span class="sxs-lookup"><span data-stu-id="ce3dd-137">The unique ID is sent back to the user.</span></span>  
  
5. <span data-ttu-id="ce3dd-138">接收审批请求。</span><span class="sxs-lookup"><span data-stu-id="ce3dd-138">An approval request is receive.</span></span> <span data-ttu-id="ce3dd-139">审批管理器执行审批过程。</span><span class="sxs-lookup"><span data-stu-id="ce3dd-139">The approval manager executes an approval process.</span></span>  
  
6. <span data-ttu-id="ce3dd-140">审批管理器接收审批请求，启动新的工作流。</span><span class="sxs-lookup"><span data-stu-id="ce3dd-140">An approval request is received by the approval manager, starting a new workflow.</span></span>  
  
7. <span data-ttu-id="ce3dd-141">根据请求的类型（个人、团体或复合）来执行不同的活动。</span><span class="sxs-lookup"><span data-stu-id="ce3dd-141">Depending on the type of request (simple, quorum, or complex) a different activity is executed.</span></span>  
  
8. <span data-ttu-id="ce3dd-142">发送和接收相关的活动，这些活动用于向客户端发送供审阅的审批请求和从客户端接收响应。</span><span class="sxs-lookup"><span data-stu-id="ce3dd-142">Send and Receive activities with correlation are used to send the approval request to the client for review and receive the response.</span></span>  
  
9. <span data-ttu-id="ce3dd-143">将审批过程工作流的结果发送到客户端。</span><span class="sxs-lookup"><span data-stu-id="ce3dd-143">The result of the approval process workflow is sent to the client.</span></span>  
  
## <a name="using-the-sample"></a><span data-ttu-id="ce3dd-144">使用示例</span><span class="sxs-lookup"><span data-stu-id="ce3dd-144">Using the Sample</span></span>  
  
##### <a name="to-set-up-the-database"></a><span data-ttu-id="ce3dd-145">安装数据库</span><span class="sxs-lookup"><span data-stu-id="ce3dd-145">To set up the database</span></span>  
  
1. <span data-ttu-id="ce3dd-146">使用管理员特权打开 Visual Studio 2010 命令提示符下，导航到此 DocumentApprovalProcess 文件夹并运行 Setup.cmd。</span><span class="sxs-lookup"><span data-stu-id="ce3dd-146">From a Visual Studio 2010 command prompt opened with Administrator privileges, navigate to this DocumentApprovalProcess folder and run Setup.cmd.</span></span>  
  
##### <a name="to-set-up-the-application"></a><span data-ttu-id="ce3dd-147">设置应用程序</span><span class="sxs-lookup"><span data-stu-id="ce3dd-147">To set up the application</span></span>  
  
1. <span data-ttu-id="ce3dd-148">使用 Visual Studio 2010 打开 DocumentApprovalProcess.sln 解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="ce3dd-148">Using Visual Studio 2010, open the DocumentApprovalProcess.sln solution file.</span></span>  
  
2. <span data-ttu-id="ce3dd-149">要生成解决方案，按 Ctrl+Shift+B。</span><span class="sxs-lookup"><span data-stu-id="ce3dd-149">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3. <span data-ttu-id="ce3dd-150">若要运行解决方案，通过右键单击中的 ApprovalManager 项目启动审批管理器应用程序**解决方案资源管理器**，然后单击**调试**->**开始**从右键单击菜单中的新实例。</span><span class="sxs-lookup"><span data-stu-id="ce3dd-150">To run the solution, launch the Approval Manager Application by right-clicking the ApprovalManager project in the **Solution Explorer** and clicking **Debug**->**Start** new instance from the right-click menu.</span></span>  
  
     <span data-ttu-id="ce3dd-151">等待管理器的输出指示已做好准备工作。</span><span class="sxs-lookup"><span data-stu-id="ce3dd-151">Wait for the manager’s output to let you know that it is ready.</span></span>  
  
##### <a name="to-run-the-single-approval-scenario"></a><span data-ttu-id="ce3dd-152">运行个人审批方案</span><span class="sxs-lookup"><span data-stu-id="ce3dd-152">To run the single approval scenario</span></span>  
  
1. <span data-ttu-id="ce3dd-153">使用管理员权限打开命令提示符。</span><span class="sxs-lookup"><span data-stu-id="ce3dd-153">Open a command prompt with administrator permission.</span></span>  
  
2. <span data-ttu-id="ce3dd-154">导航到包含解决方案的目录。</span><span class="sxs-lookup"><span data-stu-id="ce3dd-154">Navigate to the directory that contains the solution.</span></span>  
  
3. <span data-ttu-id="ce3dd-155">导航到 ApprovalClient\Bin\Debug 文件夹并执行两个 ApprovalClient.exe 实例。</span><span class="sxs-lookup"><span data-stu-id="ce3dd-155">Navigate to the ApprovalClient\Bin\Debug folder and execute two instances of ApprovalClient.exe.</span></span>  
  
4. <span data-ttu-id="ce3dd-156">单击**发现**，等待，直到**订阅**按钮处于启用状态。</span><span class="sxs-lookup"><span data-stu-id="ce3dd-156">Click **discover**, wait until the **subscribe** button is enabled.</span></span>  
  
5. <span data-ttu-id="ce3dd-157">键入任何用户名，然后单击**订阅**。</span><span class="sxs-lookup"><span data-stu-id="ce3dd-157">Type any user name and click **subscribe**.</span></span> <span data-ttu-id="ce3dd-158">对于一个客户端，使用 `UserType1` 和其他类型 `UserType2`。</span><span class="sxs-lookup"><span data-stu-id="ce3dd-158">For one client, use `UserType1` and the other type `UserType2`.</span></span>  
  
6. <span data-ttu-id="ce3dd-159">在 `UserType1` 客户端中，从下拉菜单中选择个人审批类型，然后键入文档名称和内容。</span><span class="sxs-lookup"><span data-stu-id="ce3dd-159">In the `UserType1` client, select the single approval type from the drop down menu and type a document name and content.</span></span> <span data-ttu-id="ce3dd-160">单击**请求批准**。</span><span class="sxs-lookup"><span data-stu-id="ce3dd-160">Click **Request Approval**.</span></span>  
  
7. <span data-ttu-id="ce3dd-161">在 `UserType2` 客户端中，将显示等待审批的文档。</span><span class="sxs-lookup"><span data-stu-id="ce3dd-161">In the `UserType2` client, a document awaiting approval appears.</span></span> <span data-ttu-id="ce3dd-162">选择它，然后按**批准**或**拒绝**。</span><span class="sxs-lookup"><span data-stu-id="ce3dd-162">Select it and press **approve** or **reject**.</span></span> <span data-ttu-id="ce3dd-163">结果将显示在 `UserType1` 客户端中。</span><span class="sxs-lookup"><span data-stu-id="ce3dd-163">The results should show in the `UserType1` client.</span></span>  
  
##### <a name="to-run-the-quorum-approval-scenario"></a><span data-ttu-id="ce3dd-164">运行团体审批方案</span><span class="sxs-lookup"><span data-stu-id="ce3dd-164">To run the quorum approval scenario</span></span>  
  
1. <span data-ttu-id="ce3dd-165">使用管理员权限打开命令提示符。</span><span class="sxs-lookup"><span data-stu-id="ce3dd-165">Open a command prompt with administrator permission.</span></span>  
  
2. <span data-ttu-id="ce3dd-166">导航到包含解决方案的目录。</span><span class="sxs-lookup"><span data-stu-id="ce3dd-166">Navigate to the directory that contains the solution.</span></span>  
  
3. <span data-ttu-id="ce3dd-167">导航到 ApprovalClient\Bin\Debug 文件夹并执行三个 ApprovalClient.exe 实例。</span><span class="sxs-lookup"><span data-stu-id="ce3dd-167">Navigate to the ApprovalClient\Bin\Debug folder and execute three instances of ApprovalClient.exe.</span></span>  
  
4. <span data-ttu-id="ce3dd-168">单击**发现**，等待，直到**订阅**按钮处于启用状态。</span><span class="sxs-lookup"><span data-stu-id="ce3dd-168">Click **discover**, wait until the **subscribe** button is enabled.</span></span>  
  
5. <span data-ttu-id="ce3dd-169">键入任何用户名，然后单击**订阅**。</span><span class="sxs-lookup"><span data-stu-id="ce3dd-169">Type any user name and click **subscribe**.</span></span> <span data-ttu-id="ce3dd-170">对于一个客户端，使用 `UserType1` 和其他两个类型 `UserType2`。</span><span class="sxs-lookup"><span data-stu-id="ce3dd-170">For one client use `UserType1` and the other two type `UserType2`.</span></span>  
  
6. <span data-ttu-id="ce3dd-171">在 `UserType1` 客户端中，从下拉菜单中选择团体审批类型，然后键入文档名称和内容。</span><span class="sxs-lookup"><span data-stu-id="ce3dd-171">In the `UserType1` client, select the quorum approval type from the drop down menu and type a document name and content.</span></span> <span data-ttu-id="ce3dd-172">单击**请求批准**。</span><span class="sxs-lookup"><span data-stu-id="ce3dd-172">Click **Request Approval**.</span></span> <span data-ttu-id="ce3dd-173">这将请求两个 `UserType2` 客户端批准或拒绝该文档。</span><span class="sxs-lookup"><span data-stu-id="ce3dd-173">This requests that the two `UserType2` clients approve or reject the document.</span></span> <span data-ttu-id="ce3dd-174">虽然两个 `UserType2` 客户端都必须做出响应，但只需一个客户端批准文档即可使文档获得审批。</span><span class="sxs-lookup"><span data-stu-id="ce3dd-174">While both `UserType2` clients must respond, only one client must approve the document for it to be approved.</span></span>  
  
7. <span data-ttu-id="ce3dd-175">在 `UserType2` 客户端中，将显示等待审批的文档。</span><span class="sxs-lookup"><span data-stu-id="ce3dd-175">In the `UserType2` clients, a document awaiting approval appears.</span></span> <span data-ttu-id="ce3dd-176">选择它，然后按**批准**或**拒绝**。</span><span class="sxs-lookup"><span data-stu-id="ce3dd-176">Select it and press **approve** or **reject**.</span></span> <span data-ttu-id="ce3dd-177">结果将显示在 `UserType1` 客户端中。</span><span class="sxs-lookup"><span data-stu-id="ce3dd-177">The results should show in the `UserType1` client.</span></span>  
  
##### <a name="to-run-the-complex-approval-scenario"></a><span data-ttu-id="ce3dd-178">运行复合审批方案</span><span class="sxs-lookup"><span data-stu-id="ce3dd-178">To run the complex approval scenario</span></span>  
  
1. <span data-ttu-id="ce3dd-179">使用管理员权限打开命令提示符。</span><span class="sxs-lookup"><span data-stu-id="ce3dd-179">Open a command prompt with administrator permission.</span></span>  
  
2. <span data-ttu-id="ce3dd-180">导航到包含解决方案的目录。</span><span class="sxs-lookup"><span data-stu-id="ce3dd-180">Navigate to the directory that contains the solution.</span></span>  
  
3. <span data-ttu-id="ce3dd-181">导航到 ApprovalClient\Bin\Debug 文件夹并执行四个 ApprovalClient.exe 实例。</span><span class="sxs-lookup"><span data-stu-id="ce3dd-181">Navigate to the ApprovalClient\Bin\Debug folder and execute four instances of ApprovalClient.exe.</span></span>  
  
4. <span data-ttu-id="ce3dd-182">单击**发现**，等待，直到**订阅**按钮处于启用状态。</span><span class="sxs-lookup"><span data-stu-id="ce3dd-182">Click **discover**, wait until the **subscribe** button is enabled.</span></span>  
  
5. <span data-ttu-id="ce3dd-183">键入任何用户名，然后单击**订阅**。</span><span class="sxs-lookup"><span data-stu-id="ce3dd-183">Type any user name and click **subscribe**.</span></span> <span data-ttu-id="ce3dd-184">为第一个客户端使用 `UserType1`，为第二个客户端使用 `UserType2`，为最后一个客户端使用 `UserType3`。</span><span class="sxs-lookup"><span data-stu-id="ce3dd-184">For one client use `UserType1`, in two uses type `UserType2`, and in the last use `UserType3`.</span></span>  
  
6. <span data-ttu-id="ce3dd-185">在 `UserType1` 客户端中，从下拉菜单中选择个人审批类型，然后键入文档名称和内容。</span><span class="sxs-lookup"><span data-stu-id="ce3dd-185">In the `UserType1` client, select the single approval type from the drop down menu and type a document name and content.</span></span> <span data-ttu-id="ce3dd-186">单击**请求批准**。</span><span class="sxs-lookup"><span data-stu-id="ce3dd-186">Click **Request Approval**.</span></span>  
  
7. <span data-ttu-id="ce3dd-187">在 `UserType2` 客户端中，将显示等待审批的文档。</span><span class="sxs-lookup"><span data-stu-id="ce3dd-187">In the `UserType2` clients, a document awaiting approval appears.</span></span> <span data-ttu-id="ce3dd-188">选择它，然后按**批准**，该文档传递到`UserType3`客户端。</span><span class="sxs-lookup"><span data-stu-id="ce3dd-188">Select it and press **approve**, the document is passed to the `UserType3` client.</span></span>  
  
     <span data-ttu-id="ce3dd-189">如果第一个 `UserType2` 团体批准该文档，则该文档将传递到 `UserType3` 客户端。</span><span class="sxs-lookup"><span data-stu-id="ce3dd-189">If the document is approved by the first `UserType2` quorum, the document is passed to the `UserType3` client.</span></span>  
  
8. <span data-ttu-id="ce3dd-190">批准或拒绝来自 `UserType3` 客户端的文档。</span><span class="sxs-lookup"><span data-stu-id="ce3dd-190">Approve or reject the document from the `UserType3` client.</span></span> <span data-ttu-id="ce3dd-191">结果将显示在 `UserType1` 客户端中。</span><span class="sxs-lookup"><span data-stu-id="ce3dd-191">The results should show in the `UserType1` client.</span></span>  
  
##### <a name="to-clean-up"></a><span data-ttu-id="ce3dd-192">清理</span><span class="sxs-lookup"><span data-stu-id="ce3dd-192">To clean up</span></span>  
  
1. <span data-ttu-id="ce3dd-193">从 Visual Studio 2010 命令提示符，导航到 DocumentApprovalProcess 文件夹并运行 Cleanup.cmd。</span><span class="sxs-lookup"><span data-stu-id="ce3dd-193">From a Visual Studio 2010 command prompt, navigate to the DocumentApprovalProcess folder and run Cleanup.cmd.</span></span>
