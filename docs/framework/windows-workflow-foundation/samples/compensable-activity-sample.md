---
title: 可补偿活动示例
ms.date: 03/30/2017
ms.assetid: 58f4898c-b2b8-44a4-9a73-3bef4da6d5ba
ms.openlocfilehash: 8008eaaca062723cab1efabfb1b25018353c73b5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33513999"
---
# <a name="compensable-activity-sample"></a><span data-ttu-id="a0a7e-102">可补偿活动示例</span><span class="sxs-lookup"><span data-stu-id="a0a7e-102">Compensable Activity Sample</span></span>
<span data-ttu-id="a0a7e-103">此示例演示如何使用 `CompensableActivity` 活动来定义在正常执行过程中要为某个给定操作完成的工作，以及为补偿该操作而需完成的工作（如果稍后需要这样做）。</span><span class="sxs-lookup"><span data-stu-id="a0a7e-103">This sample demonstrates how to use the `CompensableActivity` activity to define the work to be done for a given action during normal execution and the work that is necessary to be done to compensate that action, if necessary at a later time.</span></span>  <span data-ttu-id="a0a7e-104">此示例的第一部分演示如何补偿工作的单元可以定义为在 Windows Workflow Foundation (WF) 使用`CompensableActivity`活动和，它们如何执行中成功运行。</span><span class="sxs-lookup"><span data-stu-id="a0a7e-104">The first part of the sample shows how units of compensable work can be defined in Windows Workflow Foundation (WF) using a `CompensableActivity` activity and how they are executed in a successful run.</span></span>  <span data-ttu-id="a0a7e-105">此示例的第二部分演示在遇到意外事件和取消工作流实例时，相同单元数量的可补偿工作如何自动负责补偿。</span><span class="sxs-lookup"><span data-stu-id="a0a7e-105">The second part of the sample shows how the same units of compensable work automatically take care of compensation when an unexpected event is hit and the workflow instance is canceled.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="a0a7e-106">设置、生成和运行示例</span><span class="sxs-lookup"><span data-stu-id="a0a7e-106">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="a0a7e-107">使用 Visual Studio 2010 打开 CompensableActivity.sln。</span><span class="sxs-lookup"><span data-stu-id="a0a7e-107">Using Visual Studio 2010, open the CompensableActivity.sln.</span></span>  
  
2.  <span data-ttu-id="a0a7e-108">按 Ctrl+Shift+B 生成解决方案。</span><span class="sxs-lookup"><span data-stu-id="a0a7e-108">Build the solution by pressing CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="a0a7e-109">按 F5 运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="a0a7e-109">Run the application by pressing F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="a0a7e-110">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="a0a7e-110">The samples may already be installed on your machine.</span></span> <span data-ttu-id="a0a7e-111">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="a0a7e-111">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="a0a7e-112">如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和针对.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780)下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。</span><span class="sxs-lookup"><span data-stu-id="a0a7e-112">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="a0a7e-113">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="a0a7e-113">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Compensation\BasicCompensableActivity`