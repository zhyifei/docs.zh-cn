---
title: "工作流发现示例"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 82cc43f1-3c8f-4771-ac19-a75ac936e2c3
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: f778fead0e09be36ca2a829dde9cf906f4fcaa9f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="workflow-discovery-sample"></a><span data-ttu-id="caf5f-102">工作流发现示例</span><span class="sxs-lookup"><span data-stu-id="caf5f-102">Workflow Discovery Sample</span></span>
<span data-ttu-id="caf5f-103">此示例演示如何使工作流服务可发现，以及如何编写搜索特定服务的自定义代码活动。</span><span class="sxs-lookup"><span data-stu-id="caf5f-103">This sample demonstrates how to make a workflow service discoverable and how to author a custom code activity that searches for a particular service.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="caf5f-104">演示</span><span class="sxs-lookup"><span data-stu-id="caf5f-104">Demonstrates</span></span>  
 <span data-ttu-id="caf5f-105">发现查找活动和工作流使用情况</span><span class="sxs-lookup"><span data-stu-id="caf5f-105">Discovery Find Activity and Workflow Usage</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="caf5f-106">讨论</span><span class="sxs-lookup"><span data-stu-id="caf5f-106">Discussion</span></span>  
 <span data-ttu-id="caf5f-107">在示例的第一部分中，使用配置使工作流服务可发现。</span><span class="sxs-lookup"><span data-stu-id="caf5f-107">In the first part of the sample, a workflow service is made discoverable using configuration.</span></span> <span data-ttu-id="caf5f-108">使用配置还可以正确地通过自定义元数据（如范围）应用服务。</span><span class="sxs-lookup"><span data-stu-id="caf5f-108">Configuration can also be used to apply the service appropriately with custom metadata (such as scopes).</span></span> <span data-ttu-id="caf5f-109">在客户端中，该示例使用了一个自定义代码活动，该活动使用发现来搜索与特定协定匹配的服务。</span><span class="sxs-lookup"><span data-stu-id="caf5f-109">On the client, the sample uses a custom code activity, which uses Discovery to search for a service matching a particular contract.</span></span> <span data-ttu-id="caf5f-110">该代码活动输出供发送活动在以后使用的 URI。</span><span class="sxs-lookup"><span data-stu-id="caf5f-110">The code activity outputs a URI, which is later used by a send activity.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="caf5f-111">设置、生成和运行示例</span><span class="sxs-lookup"><span data-stu-id="caf5f-111">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="caf5f-112">此示例使用 HTTP 终结点，其必须具有正确的 URL Acl 运行 (请参阅[配置 HTTP 和 HTTPS](http://go.microsoft.com/fwlink/?LinkId=70353)有关详细信息)。</span><span class="sxs-lookup"><span data-stu-id="caf5f-112">This sample uses HTTP endpoints, which must have proper URL ACLs to run (see [Configuring HTTP and HTTPS](http://go.microsoft.com/fwlink/?LinkId=70353) for details).</span></span> <span data-ttu-id="caf5f-113">在具有提升权限的命令提示符下执行下面的命令应添加相应的 ACL。</span><span class="sxs-lookup"><span data-stu-id="caf5f-113">Executing the following command at an elevated command prompt should add the appropriate ACLs.</span></span> <span data-ttu-id="caf5f-114">如果 shell 无法理解变量格式，请使用你的域和用户名替换以下自变量。</span><span class="sxs-lookup"><span data-stu-id="caf5f-114">Substitute your Domain and Username for the following arguments if your shell does not understand the variable format.</span></span>  
  
     <span data-ttu-id="caf5f-115">**netsh http 添加 urlacl url = http: / / +: 8000 / 用户 = %域 %\\%username%**</span><span class="sxs-lookup"><span data-stu-id="caf5f-115">**netsh http add urlacl url=http://+:8000/ user=%DOMAIN%\\%UserName%**</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="caf5f-116">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="caf5f-116">The samples may already be installed on your machine.</span></span> <span data-ttu-id="caf5f-117">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="caf5f-117">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="caf5f-118">如果此目录不存在，请访问 [针对 .NET Framework 4 的 Windows Communication Foundation (WCF) 和 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780) 以下载所有 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 示例。</span><span class="sxs-lookup"><span data-stu-id="caf5f-118">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="caf5f-119">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="caf5f-119">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Discovery\WorkflowDiscovery`
