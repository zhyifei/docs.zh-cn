---
title: "如何：创建可调用其他工作流服务的工作流服务"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 99b3ee3e-aeb7-4e6f-8321-60fe6140eb67
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 54c1ffcef9946d2be174f92545cdba3181b0d8ee
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-create-a-workflow-service-that-calls-another-workflow-service"></a><span data-ttu-id="9ad39-102">如何：创建可调用其他工作流服务的工作流服务</span><span class="sxs-lookup"><span data-stu-id="9ad39-102">How to: Create a Workflow Service That Calls Another Workflow Service</span></span>
<span data-ttu-id="9ad39-103">有时，一个工作流服务必须从另一个工作流服务中获取信息。</span><span class="sxs-lookup"><span data-stu-id="9ad39-103">It is sometimes necessary for a workflow service to obtain information from another workflow service.</span></span>  <span data-ttu-id="9ad39-104">本主题演示如何从一个工作流服务调用另一个工作流服务。</span><span class="sxs-lookup"><span data-stu-id="9ad39-104">This topic demonstrates how to call one workflow service from another.</span></span> <span data-ttu-id="9ad39-105">本主题中，我们将创建两个工作流服务：一个服务具有可反转输入字符串的方法，另一个服务在反转使用第一个服务的字符串后，将输入字符串转换为大写。</span><span class="sxs-lookup"><span data-stu-id="9ad39-105">In this topic, we’ll create two workflow services; one that has a method that reverses the input string, and another that converts the input string to uppercase after reversing the string that uses the first service.</span></span>  
  
### <a name="to-create-the-reverser-workflow-service"></a><span data-ttu-id="9ad39-106">创建 Reverser 工作流服务</span><span class="sxs-lookup"><span data-stu-id="9ad39-106">To create the Reverser workflow service</span></span>  
  
1.  <span data-ttu-id="9ad39-107">以管理员身份运行 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="9ad39-107">Run [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] as an administrator.</span></span>  
  
2.  <span data-ttu-id="9ad39-108">选择**文件**，**新项目**。</span><span class="sxs-lookup"><span data-stu-id="9ad39-108">Select **File**, **New Project**.</span></span> <span data-ttu-id="9ad39-109">下**工作流**中的节点**已安装的模板**窗格中，选择**WCF 工作流服务应用程序**。</span><span class="sxs-lookup"><span data-stu-id="9ad39-109">Under the **Workflow** node in the **Installed Templates** pane, select **WCF Workflow Service Application**.</span></span> <span data-ttu-id="9ad39-110">将解决方案命名`NestedServices`，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="9ad39-110">Name the solution `NestedServices` and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="9ad39-111">下**服务器**，请确保**使用本地 IIS Web 服务器**选择。</span><span class="sxs-lookup"><span data-stu-id="9ad39-111">Under **Servers**, make sure that **Use Local IIS Web Server** is selected.</span></span> <span data-ttu-id="9ad39-112">单击**创建虚拟目录**。</span><span class="sxs-lookup"><span data-stu-id="9ad39-112">Click **Create Virtual Directory**.</span></span> <span data-ttu-id="9ad39-113">单击**确定**对话框，其内容已成功创建虚拟目录中。</span><span class="sxs-lookup"><span data-stu-id="9ad39-113">Click **OK** in the dialog box stating that the virtual directory was successfully created.</span></span>  
  
4.  <span data-ttu-id="9ad39-114">在解决方案资源管理器，将 Service1.xamlx 重命名为`StringReverserService.xamlx`。</span><span class="sxs-lookup"><span data-stu-id="9ad39-114">In Solution Explorer, rename Service1.xamlx to `StringReverserService.xamlx`.</span></span>  
  
5.  <span data-ttu-id="9ad39-115">上**项目属性**新项目页上，单击**Web**选项卡。设置**启动操作**到**特定页**，然后选择 StringReverserService.xamlx 作为启动页。</span><span class="sxs-lookup"><span data-stu-id="9ad39-115">On the **Project Properties** page for the new project, click the **Web** tab. Set the **Start Action** to **Specific Page**, and select StringReverserService.xamlx as the page to start.</span></span>  
  
6.  <span data-ttu-id="9ad39-116">在设计器中打开 StringReverserService.xamlx，删除现有的 `ReceiveRequest` 和 `SendReply` 活动，然后将 `ReceiveAndSendReply` 活动拖到现有的序列活动中。</span><span class="sxs-lookup"><span data-stu-id="9ad39-116">Open StringReverserService.xamlx in the designer and delete the existing `ReceiveRequest` and `SendReply` activities, and then drag a `ReceiveAndSendReply` activity into the existing sequence activity.</span></span>  
  
    1.  <span data-ttu-id="9ad39-117">设置**OperationName**为 ReverseString。</span><span class="sxs-lookup"><span data-stu-id="9ad39-117">Set the **OperationName** to ReverseString.</span></span>  
  
    2.  <span data-ttu-id="9ad39-118">设置**ServiceContractName**设置为 IReverseString。</span><span class="sxs-lookup"><span data-stu-id="9ad39-118">Set the **ServiceContractName** to IReverseString.</span></span>  
  
    3.  <span data-ttu-id="9ad39-119">选择**CanCreateInstance**复选框。</span><span class="sxs-lookup"><span data-stu-id="9ad39-119">Select the **CanCreateInstance** check box.</span></span>  
  
7.  <span data-ttu-id="9ad39-120">选择**SequentialService**活动，然后再单击**变量**设计器底部的选项卡。</span><span class="sxs-lookup"><span data-stu-id="9ad39-120">Select the **SequentialService** activity, and then click the **Variables** tab at the bottom of the designer.</span></span> <span data-ttu-id="9ad39-121">创建两个分别名为 StringToReverse 和 ReversedStringToReturn 的 String 类型的新变量。</span><span class="sxs-lookup"><span data-stu-id="9ad39-121">Create two new variables named StringToReverse and ReversedStringToReturn of type String.</span></span>  
  
8.  <span data-ttu-id="9ad39-122">单击**定义**中链接**接收**活动。</span><span class="sxs-lookup"><span data-stu-id="9ad39-122">Click the **Define** link in the **Receive** activity.</span></span> <span data-ttu-id="9ad39-123">单击**参数**，并创建一个名为 InputString 的类型分配给 StringToReverse 的字符串参数。</span><span class="sxs-lookup"><span data-stu-id="9ad39-123">Click the  **Parameters**, and create a parameter named InputString of type String that assigns to StringToReverse.</span></span>  
  
9. <span data-ttu-id="9ad39-124">单击**定义**中链接**SendReplyToReceive**活动。</span><span class="sxs-lookup"><span data-stu-id="9ad39-124">Click the **Define** link in the **SendReplyToReceive** activity.</span></span> <span data-ttu-id="9ad39-125">单击**参数**，并创建一个名为 ReversedString 的分配给 ReversedStringToReturn 的 String 的类型参数。</span><span class="sxs-lookup"><span data-stu-id="9ad39-125">Click the **Parameters**, and create a parameter named ReversedString of type String, assigned to ReversedStringToReturn.</span></span>  
  
10. <span data-ttu-id="9ad39-126">若要实现服务的逻辑，请在名为 StringLibrary 的项目中创建一个新类。</span><span class="sxs-lookup"><span data-stu-id="9ad39-126">To implement the logic for the service, create a new class in the project called StringLibrary.</span></span>  <span data-ttu-id="9ad39-127">将类定义替换为以下代码。</span><span class="sxs-lookup"><span data-stu-id="9ad39-127">Replace the class definition with the following code.</span></span>  
  
    ```  
    public class StringLibrary  
        {  
            public static String ReverseString(string StringToReverse)  
            {  
                char[] charArray = StringToReverse.ToCharArray();  
                Array.Reverse(charArray);  
                return new String(charArray);  
            }  
        }  
    ```  
  
11. <span data-ttu-id="9ad39-128">若要对输入调用 ReverseString 方法，拖动**InvokeMethod**活动从工具箱到之间的空间**接收**和**SendReply**活动。</span><span class="sxs-lookup"><span data-stu-id="9ad39-128">To call the ReverseString method on the input, drag an **InvokeMethod** activity from the toolbox to the space between the **Receive** and **SendReply** activities.</span></span> <span data-ttu-id="9ad39-129">按如下方式设置活动的属性：</span><span class="sxs-lookup"><span data-stu-id="9ad39-129">Set the properties of the activity as follows:</span></span>  
  
    1.  <span data-ttu-id="9ad39-130">**MethodName**: ReverseString</span><span class="sxs-lookup"><span data-stu-id="9ad39-130">**MethodName**: ReverseString</span></span>  
  
    2.  <span data-ttu-id="9ad39-131">**结果**: ReversedStringToReturn</span><span class="sxs-lookup"><span data-stu-id="9ad39-131">**Result**: ReversedStringToReturn</span></span>  
  
    3.  <span data-ttu-id="9ad39-132">**参数**： 创建一个新的参数与**方向**为 In、**类型**的字符串，和一个**值**为 StringToReverse。</span><span class="sxs-lookup"><span data-stu-id="9ad39-132">**Parameters**: Create a new parameter with a **Direction** of In, a **Type** of String, and a **Value** of StringToReverse.</span></span>  
  
    4.  <span data-ttu-id="9ad39-133">**TargetType**: NestedServices.StringLibrary</span><span class="sxs-lookup"><span data-stu-id="9ad39-133">**TargetType**: NestedServices.StringLibrary</span></span>  
  
12. <span data-ttu-id="9ad39-134">按 F5 测试服务。</span><span class="sxs-lookup"><span data-stu-id="9ad39-134">Test the service by pressing F5.</span></span> <span data-ttu-id="9ad39-135">在随即出现的“WCF 测试客户端”中，双击 ReverseString() 方法。</span><span class="sxs-lookup"><span data-stu-id="9ad39-135">In the WCF Test Client that appears, double-click the ReverseString() method.</span></span> <span data-ttu-id="9ad39-136">在请求窗格中，输入`Sample`为 InputString 参数的值。</span><span class="sxs-lookup"><span data-stu-id="9ad39-136">In the Request pane, enter `Sample` for the Value of the InputString parameter.</span></span> <span data-ttu-id="9ad39-137">单击**调用**。</span><span class="sxs-lookup"><span data-stu-id="9ad39-137">Click **Invoke**.</span></span> <span data-ttu-id="9ad39-138">服务应返回“elpmaS”。</span><span class="sxs-lookup"><span data-stu-id="9ad39-138">The service should return "elpmaS".</span></span>  
  
### <a name="to-create-the-uppercaser-workflow-service"></a><span data-ttu-id="9ad39-139">创建 UpperCaser 工作流服务</span><span class="sxs-lookup"><span data-stu-id="9ad39-139">To create the UpperCaser workflow service</span></span>  
  
1.  <span data-ttu-id="9ad39-140">右键单击 NestedServices 项目并选择**添加**，**新项**。</span><span class="sxs-lookup"><span data-stu-id="9ad39-140">Right-click the NestedServices project and select **Add**, **New Item**.</span></span> <span data-ttu-id="9ad39-141">在**工作流**节点中，选择**WCF 工作流服务**，并命名为新服务`UpperCaserService`。</span><span class="sxs-lookup"><span data-stu-id="9ad39-141">In the **Workflow** node, select **WCF Workflow Service**, and name the new service `UpperCaserService`.</span></span> <span data-ttu-id="9ad39-142">单击 **“添加”**。</span><span class="sxs-lookup"><span data-stu-id="9ad39-142">Click **Add**.</span></span> <span data-ttu-id="9ad39-143">此操作应将名为 UpperCaserService.xamlx 的新工作流服务添加到项目中。</span><span class="sxs-lookup"><span data-stu-id="9ad39-143">This should add a new workflow service called UpperCaserService.xamlx to the project.</span></span>  
  
2.  <span data-ttu-id="9ad39-144">在设计器中打开 UpperCaserService.xamlx，删除现有**ReceiveRequest**和`SendReply`活动，然后拖动`ReceiveAndSendReply`到现有的序列活动的活动。</span><span class="sxs-lookup"><span data-stu-id="9ad39-144">Open UpperCaserService.xamlx in the designer and delete the existing **ReceiveRequest** and `SendReply` activities, and drag a `ReceiveAndSendReply` activity into the existing sequence activity.</span></span>  
  
    1.  <span data-ttu-id="9ad39-145">设置**OperationName**为 UpperCaseString。</span><span class="sxs-lookup"><span data-stu-id="9ad39-145">Set the **OperationName** to UpperCaseString.</span></span>  
  
    2.  <span data-ttu-id="9ad39-146">设置**ServiceContractName**设置为 IUpperCaseString。</span><span class="sxs-lookup"><span data-stu-id="9ad39-146">Set the **ServiceContractName** to IUpperCaseString.</span></span>  
  
    3.  <span data-ttu-id="9ad39-147">选择**CanCreateInstance**复选框。</span><span class="sxs-lookup"><span data-stu-id="9ad39-147">Select the **CanCreateInstance** check box.</span></span>  
  
3.  <span data-ttu-id="9ad39-148">选择 SequentialService 活动，然后单击**变量**设计器底部的选项卡。</span><span class="sxs-lookup"><span data-stu-id="9ad39-148">Select the SequentialService activity, and then click the **Variables** tab at the bottom of the designer.</span></span> <span data-ttu-id="9ad39-149">创建三个分别名为 StringToUpper、StringToReverse 和 StringToReturn 的 String 类型的新变量。</span><span class="sxs-lookup"><span data-stu-id="9ad39-149">Create three new variables named StringToUpper, StringToReverse, and StringToReturn of type String.</span></span>  
  
4.  <span data-ttu-id="9ad39-150">单击**定义**中链接**接收**活动。</span><span class="sxs-lookup"><span data-stu-id="9ad39-150">Click the **Define** link in the **Receive** activity.</span></span> <span data-ttu-id="9ad39-151">单击**参数**，并创建一个名为 InputString 的类型分配给 StringToUpper 的字符串参数。</span><span class="sxs-lookup"><span data-stu-id="9ad39-151">Click the **Parameters**, and create a parameter named InputString of type String that assigns to StringToUpper.</span></span>  
  
5.  <span data-ttu-id="9ad39-152">单击**定义**中链接**SendReplyToReceive**活动。</span><span class="sxs-lookup"><span data-stu-id="9ad39-152">Click the **Define** link in the **SendReplyToReceive** activity.</span></span> <span data-ttu-id="9ad39-153">单击**参数**，并创建一个名为 ModifiedString 的分配给 StringToReturn 的 String 的类型参数。</span><span class="sxs-lookup"><span data-stu-id="9ad39-153">Click the **Parameters**, and create a parameter named ModifiedString of type String, assigned to StringToReturn.</span></span>  
  
6.  <span data-ttu-id="9ad39-154">若要实现服务的逻辑，请使用下面的代码在 StringLibrary 类中创建一个新方法。</span><span class="sxs-lookup"><span data-stu-id="9ad39-154">To implement the logic for the service, create a new method in the StringLibrary class using the following code.</span></span>  
  
    ```  
    public static String UpperCaseString(string StringToUpperCase)  
    {  
         return StringToUpperCase.ToUpper();  
  
    }  
    ```  
  
7.  <span data-ttu-id="9ad39-155">若要对输入调用 UpperCaseString 方法，拖动**InvokeMethod**活动从工具箱到之间的空间**接收**和**SendReply**活动。</span><span class="sxs-lookup"><span data-stu-id="9ad39-155">To call the UpperCaseString method on the input, drag an **InvokeMethod** activity from the toolbox to the space between the **Receive** and **SendReply** activities.</span></span> <span data-ttu-id="9ad39-156">按如下方式设置活动的属性：</span><span class="sxs-lookup"><span data-stu-id="9ad39-156">Set the properties of the activity as follows:</span></span>  
  
    1.  <span data-ttu-id="9ad39-157">**MethodName**: UpperCaseString</span><span class="sxs-lookup"><span data-stu-id="9ad39-157">**MethodName**: UpperCaseString</span></span>  
  
    2.  <span data-ttu-id="9ad39-158">**结果**: StringToReverse</span><span class="sxs-lookup"><span data-stu-id="9ad39-158">**Result**: StringToReverse</span></span>  
  
    3.  <span data-ttu-id="9ad39-159">**参数**： 创建一个新的参数与**方向**为 In、**类型**的字符串，和一个**值**为 StringToUpper。</span><span class="sxs-lookup"><span data-stu-id="9ad39-159">**Parameters**: Create a new parameter with a **Direction** of In, a **Type** of String, and a **Value** of StringToUpper.</span></span>  
  
    4.  <span data-ttu-id="9ad39-160">**TargetType**: NestedServices.StringLibrary</span><span class="sxs-lookup"><span data-stu-id="9ad39-160">**TargetType**: NestedServices.StringLibrary</span></span>  
  
8.  <span data-ttu-id="9ad39-161">现在将对已修改的字符串调用第一个服务。</span><span class="sxs-lookup"><span data-stu-id="9ad39-161">We’ll now call the first service on the modified string.</span></span> <span data-ttu-id="9ad39-162">右键单击项目并选择**添加服务引用**。</span><span class="sxs-lookup"><span data-stu-id="9ad39-162">Right-click the project and select **Add Service Reference**.</span></span> <span data-ttu-id="9ad39-163">添加对 http://localhost/NestedServices/StringReverserService.xamlx 上的服务的服务引用，并生成项目以创建自定义活动来访问第一个 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="9ad39-163">Add a service reference to the service at http://localhost/NestedServices/StringReverserService.xamlx and build the project to create a custom activity to access the first Web service.</span></span>  
  
9. <span data-ttu-id="9ad39-164">将新活动的实例之间拖到工作流， **InvokeMethod**活动和**SendReplyToReceive**活动。</span><span class="sxs-lookup"><span data-stu-id="9ad39-164">Drag an instance of the new activity onto the workflow, between the **InvokeMethod** activity and the **SendReplyToReceive** activities.</span></span> <span data-ttu-id="9ad39-165">将 StringToReverse 变量分配给新活动的 InputString 属性，并将 StringToReturn 变量分配给 StringToReturn 属性。</span><span class="sxs-lookup"><span data-stu-id="9ad39-165">Assign the variable StringToReverse to the InputString property of the new activity, and the variable StringToReturn to the StringToReturn property.</span></span>  
  
10. <span data-ttu-id="9ad39-166">打开 NestedServices 项目的属性页并更改**特定页**中**Web**为 UpperCaserService.xamlx 的选项卡。</span><span class="sxs-lookup"><span data-stu-id="9ad39-166">Open the Properties page for the NestedServices project, and change the **Specific Page** in the **Web** tab to UpperCaserService.xamlx.</span></span>  
  
11. <span data-ttu-id="9ad39-167">按 F5 测试服务。</span><span class="sxs-lookup"><span data-stu-id="9ad39-167">Test the service by pressing F5.</span></span> <span data-ttu-id="9ad39-168">在随即出现的“WCF 测试客户端”中，双击 ReverseString() 方法。</span><span class="sxs-lookup"><span data-stu-id="9ad39-168">In the WCF Test Client that appears, double-click the ReverseString() method.</span></span> <span data-ttu-id="9ad39-169">在请求窗格中，输入`Sample`为 InputString 参数的值。</span><span class="sxs-lookup"><span data-stu-id="9ad39-169">In the Request pane, enter `Sample` for the Value of the InputString parameter.</span></span> <span data-ttu-id="9ad39-170">单击**调用**。</span><span class="sxs-lookup"><span data-stu-id="9ad39-170">Click **Invoke**.</span></span> <span data-ttu-id="9ad39-171">服务应返回“ELPMAS”。</span><span class="sxs-lookup"><span data-stu-id="9ad39-171">The service should return "ELPMAS".</span></span>  
  
### <a name="to-create-a-client-to-call-the-services"></a><span data-ttu-id="9ad39-172">创建要调用服务的客户端</span><span class="sxs-lookup"><span data-stu-id="9ad39-172">To create a client to call the services</span></span>  
  
1.  <span data-ttu-id="9ad39-173">将一个名为 Client 的新控制台应用程序项目添加到解决方案。</span><span class="sxs-lookup"><span data-stu-id="9ad39-173">Add a new Console application project called Client to the solution.</span></span>  
  
2.  <span data-ttu-id="9ad39-174">右键单击客户端项目并选择**添加服务引用**。</span><span class="sxs-lookup"><span data-stu-id="9ad39-174">Right-click the Client project and select **Add Service Reference**.</span></span> <span data-ttu-id="9ad39-175">在出现的窗口中，单击**发现**。</span><span class="sxs-lookup"><span data-stu-id="9ad39-175">In the window that appears, click **Discover**.</span></span> <span data-ttu-id="9ad39-176">选择 StringReverserService.xamlx，并输入 ReverseService 作为命名空间。</span><span class="sxs-lookup"><span data-stu-id="9ad39-176">Select StringReverserService.xamlx, and enter ReverseService as the namespace.</span></span>  <span data-ttu-id="9ad39-177">单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="9ad39-177">Click **OK**.</span></span>  
  
3.  <span data-ttu-id="9ad39-178">将 Program.cs 中 Main 方法替换为以下代码。</span><span class="sxs-lookup"><span data-stu-id="9ad39-178">Replace the Main method in Program.cs with the following code.</span></span>  
  
    ```  
    static void Main(string[] args)  
    {  
        Console.Write("Input string to process:");  
        String input = Console.ReadLine();  
        var service = new ReverseService.ReverseStringClient();  
        Console.WriteLine("Output from service: {0}", service.ReverseString(input));  
        Console.ReadKey();  
    }  
    ```
