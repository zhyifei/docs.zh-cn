---
title: WCF 安全中的加密灵活性
ms.date: 03/30/2017
ms.assetid: c2c549e5-ac19-40c5-b686-8f67f52b6dbf
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: b9864fb38959cebfac21ed0f47dfd5bcb06a4dbd
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43519787"
---
# <a name="cryptographic-agility-in-wcf-security"></a><span data-ttu-id="65969-102">WCF 安全中的加密灵活性</span><span class="sxs-lookup"><span data-stu-id="65969-102">Cryptographic Agility in WCF Security</span></span>
<span data-ttu-id="65969-103">此示例演示如何在要提供加密的敏捷实现 Windows Communication Foundation (WCF) 客户端和服务中的标准/自定义算法中指定。</span><span class="sxs-lookup"><span data-stu-id="65969-103">This sample shows how to specify in a standard/custom algorithm to provide a cryptographic agile implementation in a Windows Communication Foundation (WCF) client and service.</span></span> <span data-ttu-id="65969-104">该示例由下列项目组成：</span><span class="sxs-lookup"><span data-stu-id="65969-104">The sample is composed of the following projects:</span></span>  
  
 <span data-ttu-id="65969-105">服务</span><span class="sxs-lookup"><span data-stu-id="65969-105">Service</span></span>  
 <span data-ttu-id="65969-106">这是自承载的 WCF 服务，实现`ICalculator`接口，并保护终结点使用 <<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`> 使用安全会话和可靠会话被禁用。</span><span class="sxs-lookup"><span data-stu-id="65969-106">This is a self-hosted WCF service that implements the `ICalculator` interface and secures the endpoint using the <<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`> with secure session and reliable session disabled.</span></span> <span data-ttu-id="65969-107">该服务定义一个自定义 `SecurityAlgorithmSuite` 类，以指定要用于消息安全的加密算法。</span><span class="sxs-lookup"><span data-stu-id="65969-107">The service defines a custom `SecurityAlgorithmSuite` class to specify the cryptographic algorithms to be used for message security.</span></span>  
  
 <span data-ttu-id="65969-108">客户端</span><span class="sxs-lookup"><span data-stu-id="65969-108">Client</span></span>  
 <span data-ttu-id="65969-109">这是身份验证成功后访问该服务 WCFclient。</span><span class="sxs-lookup"><span data-stu-id="65969-109">This is a WCFclient that accesses the service after successful authentication.</span></span> <span data-ttu-id="65969-110">该客户端调用由 `ICalculator` 接口公开并由服务实现的操作。</span><span class="sxs-lookup"><span data-stu-id="65969-110">It invokes the operations exposed by the `ICalculator` interface and implemented by the service.</span></span> <span data-ttu-id="65969-111">该客户端也定义相同的自定义 `SecurityAlgorithmSuite` 类，以指定要用于消息安全的加密算法。</span><span class="sxs-lookup"><span data-stu-id="65969-111">The client also defines the same custom `SecurityAlgorithmSuite` class to specify the cryptographic algorithms to be used for message security.</span></span>  
  
### <a name="to-use-this-sample"></a><span data-ttu-id="65969-112">使用此示例</span><span class="sxs-lookup"><span data-stu-id="65969-112">To use this sample</span></span>  
  
1.  <span data-ttu-id="65969-113">在 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] 中打开 CryptoAgility.sln 解决方案。</span><span class="sxs-lookup"><span data-stu-id="65969-113">Open the CryptoAgility.sln solution in [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].</span></span>  
  
2.  <span data-ttu-id="65969-114">按 Ctrl+Shift+B 生成解决方案。</span><span class="sxs-lookup"><span data-stu-id="65969-114">Press CTRL+SHIFT+B to build the solution.</span></span>  
  
3.  <span data-ttu-id="65969-115">打开[!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)]并导航到 \WCF\Basic\Security\CryptoAgility\Service\bin 目录，并使用管理员特权运行 service.exe 文件，通过右击 service.exe 并选择**以管理员身份运行**。</span><span class="sxs-lookup"><span data-stu-id="65969-115">Open [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)] and navigate to the \WCF\Basic\Security\CryptoAgility\Service\bin directory and run the service.exe file with administrator privileges by right-clicking service.exe and selecting **Run as administrator**.</span></span>  
  
4.  <span data-ttu-id="65969-116">导航到 \WCF\Basic\Security\CryptoAgility\Client\bin 目录并正常运行 client.exe 文件。</span><span class="sxs-lookup"><span data-stu-id="65969-116">Navigate to \WCF\Basic\Security\CryptoAgility\Client\bin directory and run the client.exe file normally.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="65969-117">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="65969-117">The samples may already be installed on your machine.</span></span> <span data-ttu-id="65969-118">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="65969-118">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="65969-119">如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](https://go.microsoft.com/fwlink/?LinkId=150780)若要下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。</span><span class="sxs-lookup"><span data-stu-id="65969-119">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="65969-120">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="65969-120">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Security\CryptoAgility`  
  
## <a name="see-also"></a><span data-ttu-id="65969-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="65969-121">See Also</span></span>  
 [<span data-ttu-id="65969-122">安全性</span><span class="sxs-lookup"><span data-stu-id="65969-122">Security</span></span>](../../../../docs/framework/wcf/feature-details/security.md)
