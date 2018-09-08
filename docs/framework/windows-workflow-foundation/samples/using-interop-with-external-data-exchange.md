---
title: 与外部数据交换结合使用互操作
ms.date: 03/30/2017
ms.assetid: 96f6fe26-5305-494f-9119-7748e0c4b3fa
ms.openlocfilehash: 534321e5b5568e0dd0988333dc98ccc18ff33df8
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/08/2018
ms.locfileid: "44183439"
---
# <a name="using-interop-with-external-data-exchange"></a><span data-ttu-id="79c6c-102">与外部数据交换结合使用互操作</span><span class="sxs-lookup"><span data-stu-id="79c6c-102">Using Interop with External Data Exchange</span></span>
<span data-ttu-id="79c6c-103"><xref:System.Activities.Statements.Interop>活动可用于执行 Windows Workflow Foundation (WF) 中的活动[!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)]并[!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)](WF3) 和工作流中的 Windows Workflow Foundation 中[!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)](WF4)。</span><span class="sxs-lookup"><span data-stu-id="79c6c-103">The <xref:System.Activities.Statements.Interop> activity can be used to execute activities from Windows Workflow Foundation (WF) in [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)] and [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] (WF3), and workflows within Windows Workflow Foundation in [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] (WF4).</span></span> <span data-ttu-id="79c6c-104">此示例演示如何通过使用 WF4 工作流服务中的 <xref:System.Workflow.Activities.ExternalDataExchangeService> 活动配置和运行 WF3 工作流，该工作流使用 <xref:System.Activities.Statements.Interop> 及对应的自定义活动进行方法调用和事件处理。</span><span class="sxs-lookup"><span data-stu-id="79c6c-104">This sample shows how to configure and run a WF3 workflow that uses <xref:System.Workflow.Activities.ExternalDataExchangeService> (and corresponding custom activities for calling methods and handling events) by using the <xref:System.Activities.Statements.Interop> activity in a WF4 workflow service.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="79c6c-105">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="79c6c-105">The samples may already be installed on your machine.</span></span> <span data-ttu-id="79c6c-106">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="79c6c-106">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="79c6c-107">如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](https://go.microsoft.com/fwlink/?LinkId=150780)若要下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。</span><span class="sxs-lookup"><span data-stu-id="79c6c-107">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="79c6c-108">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="79c6c-108">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Migration\ExternalDataExchange`  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="79c6c-109">使用此示例</span><span class="sxs-lookup"><span data-stu-id="79c6c-109">To use this sample</span></span>  
  
1.  <span data-ttu-id="79c6c-110">在 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 中打开 ExternalDataExchange.sln 文件。</span><span class="sxs-lookup"><span data-stu-id="79c6c-110">Open the ExternalDataExchange.sln file in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="79c6c-111">要生成此示例，按 Ctrl+Shift+B。</span><span class="sxs-lookup"><span data-stu-id="79c6c-111">To build the sample, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="79c6c-112">要运行此示例，按 F5。</span><span class="sxs-lookup"><span data-stu-id="79c6c-112">To run the sample, press F5.</span></span>
