---
title: 启用了 ReceiveContext 的 WCF 通道
ms.date: 03/30/2017
ms.assetid: d990d119-7321-4b8c-852b-10256f59f9b0
ms.openlocfilehash: d7f80d0874606129876fbf7dfa30c0327680b922
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/01/2018
ms.locfileid: "43442741"
---
# <a name="receivecontext-enabled-wcf-channels"></a><span data-ttu-id="6033b-102">启用了 ReceiveContext 的 WCF 通道</span><span class="sxs-lookup"><span data-stu-id="6033b-102">ReceiveContext-Enabled WCF Channels</span></span>
<span data-ttu-id="6033b-103">本示例演示启用了 <xref:System.ServiceModel.Channels.ReceiveContext> 的 WCF 通道的用处。</span><span class="sxs-lookup"><span data-stu-id="6033b-103">This sample demonstrates the usefulness of <xref:System.ServiceModel.Channels.ReceiveContext>-enabled WCF channels.</span></span> <span data-ttu-id="6033b-104">本示例实现一个服务，以使用 NetMSMQ 通道查找两个数字的乘积。</span><span class="sxs-lookup"><span data-stu-id="6033b-104">The sample implements a service to find the product of two numbers using a NetMSMQ channel.</span></span>  
  
 <span data-ttu-id="6033b-105">应用程序使用 <xref:System.ServiceModel.Channels.ReceiveContext> 类可以决定是访问消息还是将其留在队列中供将来进行处理，即便是在已检查了消息内容后也可如此。</span><span class="sxs-lookup"><span data-stu-id="6033b-105">The <xref:System.ServiceModel.Channels.ReceiveContext> class enables an application to decide whether to access the message or leave it in the queue for further processing, even after the contents of the message have been inspected.</span></span> <span data-ttu-id="6033b-106">在本示例中，客户端向事务性队列发送随机整数。</span><span class="sxs-lookup"><span data-stu-id="6033b-106">In this sample, a client sends random integers to a transactional queue.</span></span> <span data-ttu-id="6033b-107">`ProductCalculator` 服务接收消息，检查消息内容（为整数）以确定是否可以计算乘积。</span><span class="sxs-lookup"><span data-stu-id="6033b-107">The `ProductCalculator` service receives the messages and inspects the message contents, which are integers, to determine whether the product can be computed.</span></span> <span data-ttu-id="6033b-108">如果服务操作不计算乘积，则消息会放回队列，可由侦听队列的服务再次接收。</span><span class="sxs-lookup"><span data-stu-id="6033b-108">If the service operation does not compute the product, the message is put back into the queue and can be received again by the service listening on the queue.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="6033b-109">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="6033b-109">The samples may already be installed on your computer.</span></span> <span data-ttu-id="6033b-110">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="6033b-110">Check for the following (default) directory before continuing:</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="6033b-111">如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](https://go.microsoft.com/fwlink/?LinkId=150780)若要下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。</span><span class="sxs-lookup"><span data-stu-id="6033b-111">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="6033b-112">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="6033b-112">This sample is located in the following directory:</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\Net\MSMQ\ReceiveContextProductGenerator`  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="6033b-113">使用此示例</span><span class="sxs-lookup"><span data-stu-id="6033b-113">To use this sample</span></span>  
  
1.  <span data-ttu-id="6033b-114">确保安装了 Microsoft 消息队列 (MSMQ)。</span><span class="sxs-lookup"><span data-stu-id="6033b-114">Ensure that Microsoft Message Queuing (MSMQ) is installed.</span></span>  
  
    1.  <span data-ttu-id="6033b-115">在 [!INCLUDE[lserver](../../../../includes/lserver-md.md)] 上安装 MSMQ：</span><span class="sxs-lookup"><span data-stu-id="6033b-115">To install MSMQ on [!INCLUDE[lserver](../../../../includes/lserver-md.md)]:</span></span>  
  
        1.  <span data-ttu-id="6033b-116">在中**服务器管理器**，单击**功能**。</span><span class="sxs-lookup"><span data-stu-id="6033b-116">In **Server Manager**, click **Features**.</span></span>  
  
        2.  <span data-ttu-id="6033b-117">在下的右窗格**功能摘要**，单击**添加功能**。</span><span class="sxs-lookup"><span data-stu-id="6033b-117">In the right pane under **Features Summary**, click **Add Features**.</span></span>  
  
        3.  <span data-ttu-id="6033b-118">在生成的窗口中，展开**消息队列**。</span><span class="sxs-lookup"><span data-stu-id="6033b-118">In the resulting window, expand **Message Queuing**.</span></span>  
  
        4.  <span data-ttu-id="6033b-119">展开**消息队列服务**。</span><span class="sxs-lookup"><span data-stu-id="6033b-119">Expand **Message Queuing Services**.</span></span>  
  
        5.  <span data-ttu-id="6033b-120">单击**目录服务集成**（用于计算机加入到域的），然后单击**HTTP 支持**。</span><span class="sxs-lookup"><span data-stu-id="6033b-120">Click **Directory Services Integration** (for computers joined to a domain), and then click **HTTP Support**.</span></span>  
  
        6.  <span data-ttu-id="6033b-121">单击**下一步**，然后单击**安装**。</span><span class="sxs-lookup"><span data-stu-id="6033b-121">Click **Next**, and then click **Install**.</span></span>  
  
    2.  <span data-ttu-id="6033b-122">在 [!INCLUDE[wv](../../../../includes/wv-md.md)] 上安装 MSMQ：</span><span class="sxs-lookup"><span data-stu-id="6033b-122">To install MSMQ on [!INCLUDE[wv](../../../../includes/wv-md.md)]:</span></span>  
  
        1.  <span data-ttu-id="6033b-123">打开“控制面板” 。</span><span class="sxs-lookup"><span data-stu-id="6033b-123">Open **Control Panel**.</span></span>  
  
        2.  <span data-ttu-id="6033b-124">单击**程序**，然后在**程序和功能**，单击**打开或关闭 Windows 功能**。</span><span class="sxs-lookup"><span data-stu-id="6033b-124">Click **Programs** and then, under **Programs and Features**, click **Turn Windows Features on and off**.</span></span>  
  
        3.  <span data-ttu-id="6033b-125">展开**Microsoft 消息队列 (MSMQ) 服务器**，展开**Microsoft 消息队列 (MSMQ) 服务器核心**，然后选择以下的消息队列功能，以安装对应的复选框：</span><span class="sxs-lookup"><span data-stu-id="6033b-125">Expand **Microsoft Message Queue (MSMQ) Server**, expand **Microsoft Message Queue (MSMQ) Server Core**, and then select the check boxes for the following Message Queuing features to install:</span></span>  
  
            -   <span data-ttu-id="6033b-126">消息队列服务器</span><span class="sxs-lookup"><span data-stu-id="6033b-126">Message Queuing Server</span></span>  
  
            -   <span data-ttu-id="6033b-127">MSMQ Active Directory 域服务集成（用于加入域的计算机）</span><span class="sxs-lookup"><span data-stu-id="6033b-127">MSMQ Active Directory Domain Services Integration (for computers joined to a domain)</span></span>  
  
            -   <span data-ttu-id="6033b-128">MSMQ HTTP 支持</span><span class="sxs-lookup"><span data-stu-id="6033b-128">MSMQ HTTP Support</span></span>  
  
        4.  <span data-ttu-id="6033b-129">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="6033b-129">Click **OK**.</span></span>  
  
        5.  <span data-ttu-id="6033b-130">如果系统提示您重新启动计算机时，请单击**确定**以完成安装。</span><span class="sxs-lookup"><span data-stu-id="6033b-130">If you are prompted to restart the computer, click **OK** to complete the installation.</span></span>  
  
2.  <span data-ttu-id="6033b-131">确保计算机上安装了 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="6033b-131">Ensure that [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] is installed on the computer.</span></span>  
  
3.  <span data-ttu-id="6033b-132">使用 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] 打开 ReceiveContextProductGenerator.sln 解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="6033b-132">Using [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], open the ReceiveContextProductGenerator.sln solution file.</span></span>  
  
4.  <span data-ttu-id="6033b-133">要生成解决方案，按 Ctrl+Shift+B。</span><span class="sxs-lookup"><span data-stu-id="6033b-133">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
5.  <span data-ttu-id="6033b-134">若要运行解决方案，请按 Ctrl+F5。</span><span class="sxs-lookup"><span data-stu-id="6033b-134">To run the solution, press CTRL+F5.</span></span>
