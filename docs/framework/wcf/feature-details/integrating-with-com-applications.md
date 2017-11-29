---
title: "与 COM 应用程序集成"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Communication Foundation, COM integration
- COM [WCF], Windows Communication Foundation integration
- WCF, reusing code
- Windows Communication Foundation, reusing code
- COM [WCF]
- WCF, COM integration
ms.assetid: c98bda3e-6779-419e-8e6d-9aa94053026d
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: a0e625beaf20f6445099d8fb15cb175d3d71a860
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="integrating-with-com-applications"></a><span data-ttu-id="bf4be-102">与 COM 应用程序集成</span><span class="sxs-lookup"><span data-stu-id="bf4be-102">Integrating with COM Applications</span></span>
<span data-ttu-id="bf4be-103">通过使用 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 服务标记，[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 服务可直接集成到现有代码中。</span><span class="sxs-lookup"><span data-stu-id="bf4be-103">[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] services can be integrated directly into your existing code by using the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service moniker.</span></span> <span data-ttu-id="bf4be-104">服务标记可以在众多基于 COM 的开发环境（如 Office VBA、Visual Basic 6.0 或 Visual C++ 6.0）中使用。</span><span class="sxs-lookup"><span data-stu-id="bf4be-104">The service moniker can be used from a wide range of COM-based development environments, such as Office VBA, Visual Basic 6.0, or Visual C++ 6.0.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="bf4be-105">本节内容</span><span class="sxs-lookup"><span data-stu-id="bf4be-105">In This Section</span></span>  
 [<span data-ttu-id="bf4be-106">将与 COM 应用程序概述集成</span><span class="sxs-lookup"><span data-stu-id="bf4be-106">Integrating with COM Applications Overview</span></span>](../../../../docs/framework/wcf/feature-details/integrating-with-com-applications-overview.md)  
 <span data-ttu-id="bf4be-107">对集成过程的主要部分进行概述。</span><span class="sxs-lookup"><span data-stu-id="bf4be-107">Gives an overview of the major parts of the integration process.</span></span>  
  
 [<span data-ttu-id="bf4be-108">如何： 注册并配置服务标记</span><span class="sxs-lookup"><span data-stu-id="bf4be-108">How to: Register and Configure a Service Moniker</span></span>](../../../../docs/framework/wcf/feature-details/how-to-register-and-configure-a-service-moniker.md)  
 <span data-ttu-id="bf4be-109">若要在 COM 应用程序中使用 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 服务标记，请向 COM 注册所需属性化类型，并以所需绑定配置对 COM 应用程序和标记进行配置。</span><span class="sxs-lookup"><span data-stu-id="bf4be-109">To use the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service moniker within a COM application, register the required attributed types with COM, and configure the COM application and the moniker with the required binding configuration.</span></span>  
  
 [<span data-ttu-id="bf4be-110">如何： 使用 Windows Communication Foundation 服务标记，而无需注册</span><span class="sxs-lookup"><span data-stu-id="bf4be-110">How to: Use the Windows Communication Foundation Service Moniker without Registration</span></span>](../../../../docs/framework/wcf/feature-details/use-the-wcf-service-moniker-without-registration.md)  
 <span data-ttu-id="bf4be-111">说明如何以 Web 服务定义语言 (WSDL) 文档的形式或者从 WS-MetadataExchange 终结点获取协定的定义。</span><span class="sxs-lookup"><span data-stu-id="bf4be-111">Explains how to obtain the definition of the contract in the form of a Web Services Definition Language (WSDL) document or from a WS-MetadataExchange endpoint.</span></span>  
  
 [<span data-ttu-id="bf4be-112">如何： 使用服务标记用于 WSDL 协定</span><span class="sxs-lookup"><span data-stu-id="bf4be-112">How to: Use a Service Moniker with WSDL Contracts</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-a-service-moniker-with-wsdl-contracts.md)  
 <span data-ttu-id="bf4be-113">说明如何使用 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] WSDL 标记调用一个 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 示例。</span><span class="sxs-lookup"><span data-stu-id="bf4be-113">Describes how to call a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] sample using a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] WSDL moniker.</span></span>  
  
 [<span data-ttu-id="bf4be-114">如何： 使用元数据交换协定使用服务标记</span><span class="sxs-lookup"><span data-stu-id="bf4be-114">How to: Use a Service Moniker with Metadata Exchange Contracts</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-a-service-moniker-with-metadata-exchange-contracts.md)  
 <span data-ttu-id="bf4be-115">说明如何使用指定 Mex 终结点的 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 标记调用一个 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 示例。</span><span class="sxs-lookup"><span data-stu-id="bf4be-115">Describes how to call a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] sample using a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] moniker that specifies a Mex endpoint.</span></span>  
  
 [<span data-ttu-id="bf4be-116">如何： 指定通道安全凭据</span><span class="sxs-lookup"><span data-stu-id="bf4be-116">How to: Specify Channel Security Credentials</span></span>](../../../../docs/framework/wcf/feature-details/how-to-specify-channel-security-credentials.md)  
 <span data-ttu-id="bf4be-117">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 服务标记支持 `IChannelCredentials` 接口，该接口允许使用一系列替换方法来指定通道凭据。</span><span class="sxs-lookup"><span data-stu-id="bf4be-117">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service moniker supports the `IChannelCredentials` interface that allows a range of alternate methods for specifying channel credentials.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="bf4be-118">参考</span><span class="sxs-lookup"><span data-stu-id="bf4be-118">Reference</span></span>  
 <xref:System.ServiceModel>  
  
## <a name="see-also"></a><span data-ttu-id="bf4be-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bf4be-119">See Also</span></span>  
 [<span data-ttu-id="bf4be-120">与 COM + 应用程序集成</span><span class="sxs-lookup"><span data-stu-id="bf4be-120">Integrating with COM+ Applications</span></span>](../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications.md)
