---
title: 在活动示例中使用 AsyncOperationContext
ms.date: 03/30/2017
ms.assetid: 0888a0bd-d227-4c00-ad6a-b654a01740e8
ms.openlocfilehash: 4358a364a3f7ec69b7c1c548fcf82fe494f37505
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/16/2018
ms.locfileid: "45666546"
---
# <a name="using-asyncoperationcontext-in-an-activity-sample"></a><span data-ttu-id="d2f22-102">在活动示例中使用 AsyncOperationContext</span><span class="sxs-lookup"><span data-stu-id="d2f22-102">Using AsyncOperationContext in an Activity Sample</span></span>
<span data-ttu-id="d2f22-103">此示例演示如何开发一个自定义 <xref:System.Activities.CodeActivity>，该活动使用 <xref:System.Activities.AsyncCodeActivityContext> 在工作流外部异步执行工作。</span><span class="sxs-lookup"><span data-stu-id="d2f22-103">This sample demonstrates how to develop a custom <xref:System.Activities.CodeActivity> that uses <xref:System.Activities.AsyncCodeActivityContext> to perform work asynchronously outside of the workflow.</span></span>  
  
## <a name="sample-details"></a><span data-ttu-id="d2f22-104">示例详细信息</span><span class="sxs-lookup"><span data-stu-id="d2f22-104">Sample Details</span></span>  
 <span data-ttu-id="d2f22-105">该示例活动使用 <xref:System.IO.FileStream.BeginWrite%2A> 类上的 <xref:System.IO.FileStream.EndWrite%2A> 和 <xref:System.IO.FileStream> 方法以异步方式将数据写入文件。</span><span class="sxs-lookup"><span data-stu-id="d2f22-105">The sample activity uses the <xref:System.IO.FileStream.BeginWrite%2A> and <xref:System.IO.FileStream.EndWrite%2A> methods on the <xref:System.IO.FileStream> class to asynchronously write data to a file.</span></span> <span data-ttu-id="d2f22-106">此处介绍的模式适合于与其他异步方法一起使用。</span><span class="sxs-lookup"><span data-stu-id="d2f22-106">The pattern introduced here can be adapted for use with other asynchronous methods.</span></span> <span data-ttu-id="d2f22-107">在执行异步操作时，可以执行工作流中的其他活动，但无法持久化工作流。</span><span class="sxs-lookup"><span data-stu-id="d2f22-107">While the asynchronous operation is executing, other activities in the workflow can execute, but the workflow cannot be persisted.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="d2f22-108">设置、生成和运行示例</span><span class="sxs-lookup"><span data-stu-id="d2f22-108">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="d2f22-109">在 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 中打开 Async.sln 示例解决方案。</span><span class="sxs-lookup"><span data-stu-id="d2f22-109">Open the Async.sln sample solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="d2f22-110">生成和运行解决方案。</span><span class="sxs-lookup"><span data-stu-id="d2f22-110">Build and run the solution.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="d2f22-111">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="d2f22-111">The samples may already be installed on your machine.</span></span> <span data-ttu-id="d2f22-112">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="d2f22-112">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="d2f22-113">如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](https://go.microsoft.com/fwlink/?LinkId=150780)若要下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。</span><span class="sxs-lookup"><span data-stu-id="d2f22-113">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="d2f22-114">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="d2f22-114">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\Code-Bodied\Async`