---
title: 与 COM 应用程序集成
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Communication Foundation, COM integration
- COM [WCF], Windows Communication Foundation integration
- WCF, reusing code
- Windows Communication Foundation, reusing code
- COM [WCF]
- WCF, COM integration
ms.assetid: c98bda3e-6779-419e-8e6d-9aa94053026d
ms.openlocfilehash: 51626da6e97e346f43cfe606a5164024580a2ac7
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59155319"
---
# <a name="integrating-with-com-applications"></a><span data-ttu-id="6c195-102">与 COM 应用程序集成</span><span class="sxs-lookup"><span data-stu-id="6c195-102">Integrating with COM Applications</span></span>
<span data-ttu-id="6c195-103">Windows Communication Foundation (WCF) 服务可以直接集成到现有的代码使用 WCF 服务名字对象。</span><span class="sxs-lookup"><span data-stu-id="6c195-103">Windows Communication Foundation (WCF) services can be integrated directly into your existing code by using the WCF service moniker.</span></span> <span data-ttu-id="6c195-104">服务标记可以在众多基于 COM 的开发环境（如 Office VBA、Visual Basic 6.0 或 Visual C++ 6.0）中使用。</span><span class="sxs-lookup"><span data-stu-id="6c195-104">The service moniker can be used from a wide range of COM-based development environments, such as Office VBA, Visual Basic 6.0, or Visual C++ 6.0.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6c195-105">本节内容</span><span class="sxs-lookup"><span data-stu-id="6c195-105">In This Section</span></span>  
 [<span data-ttu-id="6c195-106">COM 应用程序集成概述</span><span class="sxs-lookup"><span data-stu-id="6c195-106">Integrating with COM Applications Overview</span></span>](../../../../docs/framework/wcf/feature-details/integrating-with-com-applications-overview.md)  
 <span data-ttu-id="6c195-107">对集成过程的主要部分进行概述。</span><span class="sxs-lookup"><span data-stu-id="6c195-107">Gives an overview of the major parts of the integration process.</span></span>  
  
 [<span data-ttu-id="6c195-108">如何：注册和配置服务名字对象</span><span class="sxs-lookup"><span data-stu-id="6c195-108">How to: Register and Configure a Service Moniker</span></span>](../../../../docs/framework/wcf/feature-details/how-to-register-and-configure-a-service-moniker.md)  
 <span data-ttu-id="6c195-109">若要使用 COM 应用程序中的 WCF 服务名字对象，所需的特性化的类型向 COM 注册，并使用所需的绑定配置来配置 COM 应用程序和标记。</span><span class="sxs-lookup"><span data-stu-id="6c195-109">To use the WCF service moniker within a COM application, register the required attributed types with COM, and configure the COM application and the moniker with the required binding configuration.</span></span>  
  
 [<span data-ttu-id="6c195-110">如何：使用未注册的 Windows Communication Foundation 服务名字对象</span><span class="sxs-lookup"><span data-stu-id="6c195-110">How to: Use the Windows Communication Foundation Service Moniker without Registration</span></span>](../../../../docs/framework/wcf/feature-details/use-the-wcf-service-moniker-without-registration.md)  
 <span data-ttu-id="6c195-111">说明如何以 Web 服务定义语言 (WSDL) 文档的形式或者从 WS-MetadataExchange 终结点获取协定的定义。</span><span class="sxs-lookup"><span data-stu-id="6c195-111">Explains how to obtain the definition of the contract in the form of a Web Services Definition Language (WSDL) document or from a WS-MetadataExchange endpoint.</span></span>  
  
 [<span data-ttu-id="6c195-112">如何：将服务名字对象用于 WSDL 协定</span><span class="sxs-lookup"><span data-stu-id="6c195-112">How to: Use a Service Moniker with WSDL Contracts</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-a-service-moniker-with-wsdl-contracts.md)  
 <span data-ttu-id="6c195-113">介绍如何调用使用 WCF WSDL 标记的 WCF 示例。</span><span class="sxs-lookup"><span data-stu-id="6c195-113">Describes how to call a WCF sample using a WCF WSDL moniker.</span></span>  
  
 [<span data-ttu-id="6c195-114">如何：将服务名字对象与元数据交换协定一起使用</span><span class="sxs-lookup"><span data-stu-id="6c195-114">How to: Use a Service Moniker with Metadata Exchange Contracts</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-a-service-moniker-with-metadata-exchange-contracts.md)  
 <span data-ttu-id="6c195-115">介绍如何调用使用指定 Mex 终结点的 WCF 名字对象的 WCF 示例。</span><span class="sxs-lookup"><span data-stu-id="6c195-115">Describes how to call a WCF sample using a WCF moniker that specifies a Mex endpoint.</span></span>  
  
 [<span data-ttu-id="6c195-116">如何：指定通道安全凭据</span><span class="sxs-lookup"><span data-stu-id="6c195-116">How to: Specify Channel Security Credentials</span></span>](../../../../docs/framework/wcf/feature-details/how-to-specify-channel-security-credentials.md)  
 <span data-ttu-id="6c195-117">WCF 服务标记支持`IChannelCredentials`允许范围内的替换方法来指定通道凭据的接口。</span><span class="sxs-lookup"><span data-stu-id="6c195-117">The WCF service moniker supports the `IChannelCredentials` interface that allows a range of alternate methods for specifying channel credentials.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="6c195-118">参考</span><span class="sxs-lookup"><span data-stu-id="6c195-118">Reference</span></span>  
 <xref:System.ServiceModel>  
  
## <a name="see-also"></a><span data-ttu-id="6c195-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="6c195-119">See also</span></span>

- [<span data-ttu-id="6c195-120">与 COM+ 应用程序集成</span><span class="sxs-lookup"><span data-stu-id="6c195-120">Integrating with COM+ Applications</span></span>](../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications.md)
