---
title: 在工作流服务中设置消息格式
ms.date: 03/30/2017
ms.assetid: 6d15d44b-20f8-4cb7-bd4f-598c32781ebc
ms.openlocfilehash: eb9a6b3a83a28154dc968bd4c1c41d34028bdd41
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/14/2018
ms.locfileid: "45590190"
---
# <a name="formatting-messages-in-workflow-services"></a><span data-ttu-id="47a06-102">在工作流服务中设置消息格式</span><span class="sxs-lookup"><span data-stu-id="47a06-102">Formatting messages in Workflow Services</span></span>
<span data-ttu-id="47a06-103">此示例演示如何在消息传递活动（WF 服务）中使用不同的用户类型。</span><span class="sxs-lookup"><span data-stu-id="47a06-103">This sample shows how different user types can be used in messaging activities (WF services).</span></span> <span data-ttu-id="47a06-104">此示例服务是一个简单的费用审批服务，并公开三个操作。</span><span class="sxs-lookup"><span data-stu-id="47a06-104">The sample service is a simple expense approval service and exposes three operations.</span></span> <span data-ttu-id="47a06-105">`ApproveExpense` 接受一个数据协定，并演示如何使用已知类型。</span><span class="sxs-lookup"><span data-stu-id="47a06-105">`ApproveExpense` takes a data contract type and shows how to use known types.</span></span> <span data-ttu-id="47a06-106">该操作根据费用金额返回 `true` 或 `false`。</span><span class="sxs-lookup"><span data-stu-id="47a06-106">The operation returns `true` or `false` based on the expense amount.</span></span> <span data-ttu-id="47a06-107">`ApprovePO` 接受一个 XmlSerializer 类型，并返回`true`或`false`根据费用金额。`ApprovedVendor`</span><span class="sxs-lookup"><span data-stu-id="47a06-107">`ApprovePO` takes an XmlSerializer type and returns `true` or `false` based on the expense amount.`ApprovedVendor`</span></span> <span data-ttu-id="47a06-108">接受一个消息协定类型，并返回`true`或`false`供应商的情况中的已批准的供应商列表，或请求来自财务部门 （财务部门可以使用任何供应商）。</span><span class="sxs-lookup"><span data-stu-id="47a06-108">takes a message contract type and returns `true` or `false` if the vendor is in the list of approved vendors or if the request came from the finance department (the finance department can use any vendor).</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="47a06-109">使用此示例</span><span class="sxs-lookup"><span data-stu-id="47a06-109">To use this sample</span></span>  
  
1.  <span data-ttu-id="47a06-110">在 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 中加载项目解决方案，然后生成项目。</span><span class="sxs-lookup"><span data-stu-id="47a06-110">Load the project solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] and build the project.</span></span>  
  
2.  <span data-ttu-id="47a06-111">首先运行 [解决方案基目录]\FormatterService\bin\debug\ 中生成的服务</span><span class="sxs-lookup"><span data-stu-id="47a06-111">First run the service, generated in [solution base directory]\FormatterService\bin\debug\\</span></span>  
  
3.  <span data-ttu-id="47a06-112">然后运行 [解决方案基目录]\FormatterClient\bin\debug 中生成的客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="47a06-112">Second, run the Client application generated in [solution base directory]\FormatterClient\bin\debug.</span></span>  
  
4.  <span data-ttu-id="47a06-113">客户端对服务调用三个操作，并输出结果。</span><span class="sxs-lookup"><span data-stu-id="47a06-113">The client calls three operations on the service and prints the results.</span></span> <span data-ttu-id="47a06-114">完成后，请按 Enter 退出客户端，然后退出服务。</span><span class="sxs-lookup"><span data-stu-id="47a06-114">When complete, press ENTER to exit the client and then the service.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="47a06-115">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="47a06-115">The samples may already be installed on your machine.</span></span> <span data-ttu-id="47a06-116">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="47a06-116">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="47a06-117">如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](https://go.microsoft.com/fwlink/?LinkId=150780)若要下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。</span><span class="sxs-lookup"><span data-stu-id="47a06-117">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="47a06-118">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="47a06-118">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\Formatter`