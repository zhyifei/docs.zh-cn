---
title: 在.NET Framework 4.5 工作流中使用.NET Framework 3.0 或.NET Framework 3.5 活动
ms.date: 03/30/2017
ms.assetid: 6c53fd4c-5dd0-4fb4-ab6b-111302629548
ms.openlocfilehash: ec44e56a99660ba422c73bbbf00bf5ef6b7b61ff
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/03/2018
ms.locfileid: "43486126"
---
# <a name="using-a-net-framework-30-or-net-framework-35-activity-in-a-net-framework-45-workflow"></a><span data-ttu-id="92510-102">在.NET Framework 4.5 工作流中使用.NET Framework 3.0 或.NET Framework 3.5 活动</span><span class="sxs-lookup"><span data-stu-id="92510-102">Using a .NET Framework 3.0 or .NET Framework 3.5 Activity in a .NET Framework 4.5 Workflow</span></span>
<span data-ttu-id="92510-103"><xref:System.Activities.Statements.Interop>活动，可运行中的某个.NET Framework 3.0 Windows Workflow Foundation (WF) 活动[!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)]工作流。</span><span class="sxs-lookup"><span data-stu-id="92510-103">The <xref:System.Activities.Statements.Interop> activity allows you to run a .NET Framework 3.0 Windows Workflow Foundation (WF) activity within a [!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)] workflow.</span></span> <span data-ttu-id="92510-104">此示例演示如何使用 <xref:System.Activities.Statements.Interop> 活动来将字符串作为参数传递到自定义 [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)] 活动。</span><span class="sxs-lookup"><span data-stu-id="92510-104">This sample demonstrates how to use the <xref:System.Activities.Statements.Interop> activity to pass a string as an argument to a custom [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)] activity.</span></span>  
  
## <a name="to-use-this-sample"></a><span data-ttu-id="92510-105">使用此示例</span><span class="sxs-lookup"><span data-stu-id="92510-105">To use this sample</span></span>  
  
1.  <span data-ttu-id="92510-106">使用 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] 打开 SimpleInterop.sln 解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="92510-106">Using [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], open the SimpleInterop.sln solution file.</span></span>  
  
2.  <span data-ttu-id="92510-107">要生成解决方案，按 Ctrl+Shift+B。</span><span class="sxs-lookup"><span data-stu-id="92510-107">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="92510-108">若要运行解决方案，请按 Ctrl+F5。</span><span class="sxs-lookup"><span data-stu-id="92510-108">To run the solution, press CTRL+F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="92510-109">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="92510-109">The samples may already be installed on your machine.</span></span> <span data-ttu-id="92510-110">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="92510-110">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="92510-111">如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](https://go.microsoft.com/fwlink/?LinkId=150780)若要下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。</span><span class="sxs-lookup"><span data-stu-id="92510-111">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="92510-112">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="92510-112">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Migration\SimpleInterop`  
  
## <a name="see-also"></a><span data-ttu-id="92510-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="92510-113">See Also</span></span>
