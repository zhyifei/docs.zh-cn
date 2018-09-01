---
title: Bookmarks2
ms.date: 03/30/2017
ms.assetid: 035fadb2-49fa-4ac7-b398-daf138f66e87
ms.openlocfilehash: 6bcc4e27566b9c8553e0792558c281a6b1f1caf4
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/01/2018
ms.locfileid: "43387384"
---
# <a name="bookmarks"></a><span data-ttu-id="65179-102">书签</span><span class="sxs-lookup"><span data-stu-id="65179-102">Bookmarks</span></span>
<span data-ttu-id="65179-103">此示例演示如何编写一个自定义活动，该活动创建一个书签以接收外部输入。</span><span class="sxs-lookup"><span data-stu-id="65179-103">This sample demonstrates how to write a custom activity that creates a bookmark to receive external input.</span></span> <span data-ttu-id="65179-104">此示例还包含一个基本控制台应用程序，该应用程序使用工作流中的自定义活动，并演示如何发现和恢复与正在运行的工作流实例关联的书签。</span><span class="sxs-lookup"><span data-stu-id="65179-104">The sample also includes a basic console application that uses the custom activity in a workflow and shows how to discover and resume bookmarks associated with a running workflow instance.</span></span> <span data-ttu-id="65179-105">有关书签的详细信息，请参阅[书签](../../../../docs/framework/windows-workflow-foundation/bookmarks.md)。</span><span class="sxs-lookup"><span data-stu-id="65179-105">For more information about bookmarks, see [Bookmarks](../../../../docs/framework/windows-workflow-foundation/bookmarks.md).</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="65179-106">设置、生成和运行示例</span><span class="sxs-lookup"><span data-stu-id="65179-106">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="65179-107">在 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 中打开 Bookmarks.sln 示例解决方案。</span><span class="sxs-lookup"><span data-stu-id="65179-107">Open the Bookmarks.sln sample solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="65179-108">要生成解决方案，按 Ctrl+Shift+B。</span><span class="sxs-lookup"><span data-stu-id="65179-108">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="65179-109">若要运行示例，请按 Ctrl+F5。</span><span class="sxs-lookup"><span data-stu-id="65179-109">To run the sample, press CTRLl + F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="65179-110">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="65179-110">The samples may already be installed on your machine.</span></span> <span data-ttu-id="65179-111">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="65179-111">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="65179-112">如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](https://go.microsoft.com/fwlink/?LinkId=150780)若要下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。</span><span class="sxs-lookup"><span data-stu-id="65179-112">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="65179-113">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="65179-113">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\CodeBodied\Bookmarks`