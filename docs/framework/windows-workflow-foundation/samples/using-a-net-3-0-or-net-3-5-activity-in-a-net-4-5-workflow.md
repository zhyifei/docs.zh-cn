---
title: "在.NET Framework 4.5 工作流中使用.NET Framework 3.0 或.NET Framework 3.5 活动"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6c53fd4c-5dd0-4fb4-ab6b-111302629548
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 05660c3dc91d9d7cdba506670f62711752d7d100
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="using-a-net-framework-30-or-net-framework-35-activity-in-a-net-framework-45-workflow"></a><span data-ttu-id="5fb4d-102">在.NET Framework 4.5 工作流中使用.NET Framework 3.0 或.NET Framework 3.5 活动</span><span class="sxs-lookup"><span data-stu-id="5fb4d-102">Using a .NET Framework 3.0 or .NET Framework 3.5 Activity in a .NET Framework 4.5 Workflow</span></span>
<span data-ttu-id="5fb4d-103"><xref:System.Activities.Statements.Interop> 活动允许您在 [!INCLUDE[wf](../../../../includes/wf-md.md)] 工作流中运行 .NET Framework 3.0 [!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)] 活动。</span><span class="sxs-lookup"><span data-stu-id="5fb4d-103">The <xref:System.Activities.Statements.Interop> activity allows you to run a .NET Framework 3.0 [!INCLUDE[wf](../../../../includes/wf-md.md)] activity within a [!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)] workflow.</span></span> <span data-ttu-id="5fb4d-104">此示例演示如何使用 <xref:System.Activities.Statements.Interop> 活动来将字符串作为参数传递到自定义 [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)] 活动。</span><span class="sxs-lookup"><span data-stu-id="5fb4d-104">This sample demonstrates how to use the <xref:System.Activities.Statements.Interop> activity to pass a string as an argument to a custom [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)] activity.</span></span>  
  
## <a name="to-use-this-sample"></a><span data-ttu-id="5fb4d-105">使用此示例</span><span class="sxs-lookup"><span data-stu-id="5fb4d-105">To use this sample</span></span>  
  
1.  <span data-ttu-id="5fb4d-106">使用 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] 打开 SimpleInterop.sln 解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="5fb4d-106">Using [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], open the SimpleInterop.sln solution file.</span></span>  
  
2.  <span data-ttu-id="5fb4d-107">要生成解决方案，按 Ctrl+Shift+B。</span><span class="sxs-lookup"><span data-stu-id="5fb4d-107">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="5fb4d-108">若要运行解决方案，请按 Ctrl+F5。</span><span class="sxs-lookup"><span data-stu-id="5fb4d-108">To run the solution, press CTRL+F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="5fb4d-109">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="5fb4d-109">The samples may already be installed on your machine.</span></span> <span data-ttu-id="5fb4d-110">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="5fb4d-110">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="5fb4d-111">如果此目录不存在，请访问 [针对 .NET Framework 4 的 Windows Communication Foundation (WCF) 和 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780) 以下载所有 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 示例。</span><span class="sxs-lookup"><span data-stu-id="5fb4d-111">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="5fb4d-112">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="5fb4d-112">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Migration\SimpleInterop`  
  
## <a name="see-also"></a><span data-ttu-id="5fb4d-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="5fb4d-113">See Also</span></span>
