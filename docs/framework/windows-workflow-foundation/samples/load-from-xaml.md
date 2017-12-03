---
title: "从 XAML 加载"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1f103ef6-7bed-4f16-ae52-9e665c5a43d7
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 54acfb1a130c8a790411a05958518665ef790e53
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="load-from-xaml"></a><span data-ttu-id="412e5-102">从 XAML 加载</span><span class="sxs-lookup"><span data-stu-id="412e5-102">Load From XAML</span></span>
<span data-ttu-id="412e5-103">此示例演示如何在不运行 XamlBuildTask 工具的情况下动态加载 XAML 工作流。</span><span class="sxs-lookup"><span data-stu-id="412e5-103">This sample demonstrates how to dynamically load a XAML workflow without having to run the XamlBuildTask tool.</span></span> <span data-ttu-id="412e5-104">此示例改为调用 <xref:System.Activities.XamlIntegration.ActivityXamlServices.Load%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="412e5-104">Instead, the sample calls the <xref:System.Activities.XamlIntegration.ActivityXamlServices.Load%2A> method.</span></span> <span data-ttu-id="412e5-105">此示例是一个 [!INCLUDE[avalon1](../../../../includes/avalon1-md.md)] 客户端应用程序，它使用 <xref:System.Activities.XamlIntegration.ActivityXamlServices> 类加载 XAML 工作流，然后执行这些工作流。</span><span class="sxs-lookup"><span data-stu-id="412e5-105">The sample is a [!INCLUDE[avalon1](../../../../includes/avalon1-md.md)] client application that loads XAML workflows using the <xref:System.Activities.XamlIntegration.ActivityXamlServices> class and executes them.</span></span> <span data-ttu-id="412e5-106">在使用 <xref:System.Activities.XamlIntegration.ActivityXamlServices> 类加载完这些工作流后，将返回一个可执行的 <xref:System.Activities.DynamicActivity%601>。</span><span class="sxs-lookup"><span data-stu-id="412e5-106">After they have been loaded using the <xref:System.Activities.XamlIntegration.ActivityXamlServices> class, a <xref:System.Activities.DynamicActivity%601> is returned that can be executed.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="412e5-107">使用此示例</span><span class="sxs-lookup"><span data-stu-id="412e5-107">To use this sample</span></span>  
  
1.  <span data-ttu-id="412e5-108">使用 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 打开 LoadFromXAML.sln 解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="412e5-108">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the LoadFromXAML.sln solution file.</span></span>  
  
2.  <span data-ttu-id="412e5-109">要生成解决方案，按 Ctrl+Shift+B。</span><span class="sxs-lookup"><span data-stu-id="412e5-109">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="412e5-110">若要运行解决方案，请按 Ctrl+F5。</span><span class="sxs-lookup"><span data-stu-id="412e5-110">To run the solution, press CTRL+F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="412e5-111">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="412e5-111">The samples may already be installed on your machine.</span></span> <span data-ttu-id="412e5-112">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="412e5-112">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="412e5-113">如果此目录不存在，请访问 [针对 .NET Framework 4 的 Windows Communication Foundation (WCF) 和 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780) 以下载所有 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 示例。</span><span class="sxs-lookup"><span data-stu-id="412e5-113">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="412e5-114">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="412e5-114">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\DynamicActivity\LoadFromXAML`