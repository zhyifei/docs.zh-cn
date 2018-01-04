---
title: "WCF 安全中的加密灵活性"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c2c549e5-ac19-40c5-b686-8f67f52b6dbf
caps.latest.revision: "9"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 7d99ada67255d0ced8bbabc2ab6fc645e6ba9e35
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="cryptographic-agility-in-wcf-security"></a><span data-ttu-id="dc5d7-102">WCF 安全中的加密灵活性</span><span class="sxs-lookup"><span data-stu-id="dc5d7-102">Cryptographic Agility in WCF Security</span></span>
<span data-ttu-id="dc5d7-103">本示例演示如何在标准/自定义算法中进行指定，以便在 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 客户端和服务中提供加密的敏捷实现。</span><span class="sxs-lookup"><span data-stu-id="dc5d7-103">This sample shows how to specify in a standard/custom algorithm to provide a cryptographic agile implementation in a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] client and service.</span></span> <span data-ttu-id="dc5d7-104">该示例由下列项目组成：</span><span class="sxs-lookup"><span data-stu-id="dc5d7-104">The sample is composed of the following projects:</span></span>  
  
 <span data-ttu-id="dc5d7-105">服务</span><span class="sxs-lookup"><span data-stu-id="dc5d7-105">Service</span></span>  
 <span data-ttu-id="dc5d7-106">这是自承载[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]实现的服务`ICalculator`接口，并保护终结点使用 <<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`> 通过安全会话和可靠会话禁用。</span><span class="sxs-lookup"><span data-stu-id="dc5d7-106">This is a self-hosted [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service that implements the `ICalculator` interface and secures the endpoint using the <<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`> with secure session and reliable session disabled.</span></span> <span data-ttu-id="dc5d7-107">该服务定义一个自定义 `SecurityAlgorithmSuite` 类，以指定要用于消息安全的加密算法。</span><span class="sxs-lookup"><span data-stu-id="dc5d7-107">The service defines a custom `SecurityAlgorithmSuite` class to specify the cryptographic algorithms to be used for message security.</span></span>  
  
 <span data-ttu-id="dc5d7-108">客户端</span><span class="sxs-lookup"><span data-stu-id="dc5d7-108">Client</span></span>  
 <span data-ttu-id="dc5d7-109">这是在身份验证成功后访问服务的 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 客户端。</span><span class="sxs-lookup"><span data-stu-id="dc5d7-109">This is a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]client that accesses the service after successful authentication.</span></span> <span data-ttu-id="dc5d7-110">该客户端调用由 `ICalculator` 接口公开并由服务实现的操作。</span><span class="sxs-lookup"><span data-stu-id="dc5d7-110">It invokes the operations exposed by the `ICalculator` interface and implemented by the service.</span></span> <span data-ttu-id="dc5d7-111">该客户端也定义相同的自定义 `SecurityAlgorithmSuite` 类，以指定要用于消息安全的加密算法。</span><span class="sxs-lookup"><span data-stu-id="dc5d7-111">The client also defines the same custom `SecurityAlgorithmSuite` class to specify the cryptographic algorithms to be used for message security.</span></span>  
  
### <a name="to-use-this-sample"></a><span data-ttu-id="dc5d7-112">使用此示例</span><span class="sxs-lookup"><span data-stu-id="dc5d7-112">To use this sample</span></span>  
  
1.  <span data-ttu-id="dc5d7-113">在 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] 中打开 CryptoAgility.sln 解决方案。</span><span class="sxs-lookup"><span data-stu-id="dc5d7-113">Open the CryptoAgility.sln solution in [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].</span></span>  
  
2.  <span data-ttu-id="dc5d7-114">按 Ctrl+Shift+B 生成解决方案。</span><span class="sxs-lookup"><span data-stu-id="dc5d7-114">Press CTRL+SHIFT+B to build the solution.</span></span>  
  
3.  <span data-ttu-id="dc5d7-115">打开[!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)]并导航到 \WCF\Basic\Security\CryptoAgility\Service\bin 目录，然后右击 service.exe 并选择使用管理员特权运行 service.exe 文件**以管理员身份运行**。</span><span class="sxs-lookup"><span data-stu-id="dc5d7-115">Open [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)] and navigate to the \WCF\Basic\Security\CryptoAgility\Service\bin directory and run the service.exe file with administrator privileges by right-clicking service.exe and selecting **Run as administrator**.</span></span>  
  
4.  <span data-ttu-id="dc5d7-116">导航到 \WCF\Basic\Security\CryptoAgility\Client\bin 目录并正常运行 client.exe 文件。</span><span class="sxs-lookup"><span data-stu-id="dc5d7-116">Navigate to \WCF\Basic\Security\CryptoAgility\Client\bin directory and run the client.exe file normally.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="dc5d7-117">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="dc5d7-117">The samples may already be installed on your machine.</span></span> <span data-ttu-id="dc5d7-118">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="dc5d7-118">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="dc5d7-119">如果此目录不存在，请访问 [针对 .NET Framework 4 的 Windows Communication Foundation (WCF) 和 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780) 以下载所有 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 示例。</span><span class="sxs-lookup"><span data-stu-id="dc5d7-119">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="dc5d7-120">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="dc5d7-120">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Security\CryptoAgility`  
  
## <a name="see-also"></a><span data-ttu-id="dc5d7-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="dc5d7-121">See Also</span></span>  
 [<span data-ttu-id="dc5d7-122">安全性</span><span class="sxs-lookup"><span data-stu-id="dc5d7-122">Security</span></span>](../../../../docs/framework/wcf/feature-details/security.md)
