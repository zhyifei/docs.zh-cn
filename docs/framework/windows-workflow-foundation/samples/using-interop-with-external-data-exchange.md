---
title: "与外部数据交换结合使用互操作"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 96f6fe26-5305-494f-9119-7748e0c4b3fa
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f62d5a468e3730ec4f636d57cb9d0c6c3973a8d3
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="using-interop-with-external-data-exchange"></a><span data-ttu-id="7653f-102">与外部数据交换结合使用互操作</span><span class="sxs-lookup"><span data-stu-id="7653f-102">Using Interop with External Data Exchange</span></span>
<span data-ttu-id="7653f-103">可使用 <xref:System.Activities.Statements.Interop> 活动从 [!INCLUDE[wf](../../../../includes/wf-md.md)] 和 [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)] (WF3) 中的 [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] 执行活动以及在 [!INCLUDE[wf2](../../../../includes/wf2-md.md)] (WF4) 中的 [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] 内执行工作流。</span><span class="sxs-lookup"><span data-stu-id="7653f-103">The <xref:System.Activities.Statements.Interop> activity can be used to execute activities from [!INCLUDE[wf](../../../../includes/wf-md.md)] in [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)] and [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] (WF3), and workflows within [!INCLUDE[wf2](../../../../includes/wf2-md.md)] in [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] (WF4).</span></span> <span data-ttu-id="7653f-104">此示例演示如何通过使用 WF4 工作流服务中的 <xref:System.Workflow.Activities.ExternalDataExchangeService> 活动配置和运行 WF3 工作流，该工作流使用 <xref:System.Activities.Statements.Interop> 及对应的自定义活动进行方法调用和事件处理。</span><span class="sxs-lookup"><span data-stu-id="7653f-104">This sample shows how to configure and run a WF3 workflow that uses <xref:System.Workflow.Activities.ExternalDataExchangeService> (and corresponding custom activities for calling methods and handling events) by using the <xref:System.Activities.Statements.Interop> activity in a WF4 workflow service.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="7653f-105">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="7653f-105">The samples may already be installed on your machine.</span></span> <span data-ttu-id="7653f-106">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="7653f-106">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="7653f-107">如果此目录不存在，请访问 [针对 .NET Framework 4 的 Windows Communication Foundation (WCF) 和 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780) 以下载所有 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 示例。</span><span class="sxs-lookup"><span data-stu-id="7653f-107">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="7653f-108">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="7653f-108">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Migration\ExternalDataExchange`  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="7653f-109">使用此示例</span><span class="sxs-lookup"><span data-stu-id="7653f-109">To use this sample</span></span>  
  
1.  <span data-ttu-id="7653f-110">在 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 中打开 ExternalDataExchange.sln 文件。</span><span class="sxs-lookup"><span data-stu-id="7653f-110">Open the ExternalDataExchange.sln file in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="7653f-111">要生成此示例，按 Ctrl+Shift+B。</span><span class="sxs-lookup"><span data-stu-id="7653f-111">To build the sample, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="7653f-112">要运行此示例，按 F5。</span><span class="sxs-lookup"><span data-stu-id="7653f-112">To run the sample, press F5.</span></span>
