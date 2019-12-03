---
title: LINQ 消息查询相关性
ms.date: 03/30/2017
ms.assetid: b746872e-57b1-4514-b337-53398a0e0deb
ms.openlocfilehash: a4b0ed058cfe8d3d487342c9feefdf1b1efe07c8
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/03/2019
ms.locfileid: "74715586"
---
# <a name="linq-message-query-correlation"></a><span data-ttu-id="67001-102">LINQ 消息查询相关性</span><span class="sxs-lookup"><span data-stu-id="67001-102">LINQ Message Query Correlation</span></span>
<span data-ttu-id="67001-103">此示例演示如何使用一个与系统提供的 <xref:System.ServiceModel.Dispatcher.MessageQuery> 相对的自定义 <xref:System.ServiceModel.XPathMessageQuery> 实现，执行基于内容的相关性。</span><span class="sxs-lookup"><span data-stu-id="67001-103">This sample demonstrates how to do content-based correlation using a custom <xref:System.ServiceModel.Dispatcher.MessageQuery> implementation as opposed to the system-provided <xref:System.ServiceModel.XPathMessageQuery>.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="67001-104">演示文本</span><span class="sxs-lookup"><span data-stu-id="67001-104">Demonstrates</span></span>  
 <span data-ttu-id="67001-105">自定义 <xref:System.ServiceModel.Dispatcher.MessageQuery>，基于内容的相关性。</span><span class="sxs-lookup"><span data-stu-id="67001-105">Custom <xref:System.ServiceModel.Dispatcher.MessageQuery>, Content-Based Correlation.</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="67001-106">讨论</span><span class="sxs-lookup"><span data-stu-id="67001-106">Discussion</span></span>  
 <span data-ttu-id="67001-107">此示例演示如何出于相关性的目的从 <xref:System.ServiceModel.Dispatcher.MessageQuery> 基类进行扩展。</span><span class="sxs-lookup"><span data-stu-id="67001-107">This sample shows how to extend from the <xref:System.ServiceModel.Dispatcher.MessageQuery> base class for the purposes of correlation.</span></span> <span data-ttu-id="67001-108">自定义实现 `LinqMessageQuery` 允许用户提供一个 XName 以使用 XLinq 在消息中查找。</span><span class="sxs-lookup"><span data-stu-id="67001-108">The custom implementation, `LinqMessageQuery`, allows users to provide an XName to find within the message using XLinq.</span></span> <span data-ttu-id="67001-109">此查询检索的数据用于构成相关性键，以将消息调度到相应的工作流实例。</span><span class="sxs-lookup"><span data-stu-id="67001-109">The data retrieved by the query is used to form the correlation key to dispatch messages to the appropriate workflow instance.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="67001-110">设置、生成和运行示例</span><span class="sxs-lookup"><span data-stu-id="67001-110">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="67001-111">此示例使用 HTTP 终结点公开一个工作流服务。</span><span class="sxs-lookup"><span data-stu-id="67001-111">This sample exposes a workflow service using HTTP endpoints.</span></span> <span data-ttu-id="67001-112">若要运行此示例，必须添加正确的 URL Acl （有关详细信息，请参阅[配置 HTTP 和 HTTPS](https://go.microsoft.com/fwlink/?LinkId=70353) ），方法是以管理员身份运行 Visual Studio，或在提升的提示符下执行以下命令来添加相应的 acl。</span><span class="sxs-lookup"><span data-stu-id="67001-112">To run this sample, proper URL ACLs must be added (see [Configuring HTTP and HTTPS](https://go.microsoft.com/fwlink/?LinkId=70353) for details), either by running Visual Studio as Administrator or by executing the following command at an elevated prompt to add the appropriate ACLs.</span></span> <span data-ttu-id="67001-113">确保替换了域和用户名。</span><span class="sxs-lookup"><span data-stu-id="67001-113">Ensure that your Domain and Username are substituted.</span></span>  
  
    ```console  
    netsh http add urlacl url=http://+:8000/ user=%DOMAIN%\%UserName%  
    ```  
  
2. <span data-ttu-id="67001-114">在添加 URL ACL 后，请使用下列步骤。</span><span class="sxs-lookup"><span data-stu-id="67001-114">Once the URL ACLs are added, use the following steps.</span></span>  
  
    1. <span data-ttu-id="67001-115">生成解决方案。</span><span class="sxs-lookup"><span data-stu-id="67001-115">Build the solution.</span></span>  
  
    2. <span data-ttu-id="67001-116">通过右键单击解决方案并选择 "**设置启动项目**" 来设置多个启动项目。</span><span class="sxs-lookup"><span data-stu-id="67001-116">Set multiple start-up projects by right-clicking the solution and selecting **Set Startup Projects**.</span></span> <span data-ttu-id="67001-117">将**服务**和**客户端**（按此顺序）添加为多个启动项目。</span><span class="sxs-lookup"><span data-stu-id="67001-117">Add **Service** and **Client** (in that order) as multiple start-up projects.</span></span>  
  
    3. <span data-ttu-id="67001-118">运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="67001-118">Run the application.</span></span> <span data-ttu-id="67001-119">客户端控制台演示工作流如何发送订单、接收订购单 ID 以及随后确认订单。</span><span class="sxs-lookup"><span data-stu-id="67001-119">The client console shows a workflow  sending an order and receiving the purchase order id and then subsequently confirming the order.</span></span> <span data-ttu-id="67001-120">服务窗口将显示正在处理的请求。</span><span class="sxs-lookup"><span data-stu-id="67001-120">The Service window will show the requests being processed.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="67001-121">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="67001-121">The samples may already be installed on your machine.</span></span> <span data-ttu-id="67001-122">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="67001-122">Check for the following (default) directory before continuing.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> <span data-ttu-id="67001-123">如果此目录不存在，请参阅[.NET Framework 4 的 Windows Communication Foundation （wcf）和 Windows Workflow Foundation （WF）示例](https://www.microsoft.com/download/details.aspx?id=21459)以下载所有 WINDOWS COMMUNICATION FOUNDATION （wcf）和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 示例。</span><span class="sxs-lookup"><span data-stu-id="67001-123">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="67001-124">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="67001-124">This sample is located in the following directory.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Services\LinqMessageQueryCorrelation`
