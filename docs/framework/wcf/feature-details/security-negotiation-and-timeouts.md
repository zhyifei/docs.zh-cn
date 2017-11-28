---
title: "安全协商和超时"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 02a428f1-84e5-4d28-a11f-53ce31d63196
caps.latest.revision: "8"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: b4d0b2953a91040c37afe88d9499fd4be1970f31
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="security-negotiation-and-timeouts"></a><span data-ttu-id="5522f-102">安全协商和超时</span><span class="sxs-lookup"><span data-stu-id="5522f-102">Security Negotiation and Timeouts</span></span>
<span data-ttu-id="5522f-103">在客户端和服务进行身份验证时，[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 支持将服务凭据作为身份验证的一部分。</span><span class="sxs-lookup"><span data-stu-id="5522f-103">When clients and services authenticate, [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] supports a mode where the service credential is negotiated as part of authentication.</span></span> <span data-ttu-id="5522f-104">在这种情况下，客户端和服务之间将进行潜在多路交换，以便将服务凭据传播到客户端。</span><span class="sxs-lookup"><span data-stu-id="5522f-104">In such scenarios, a potentially multi-leg exchange occurs between the client and the service to propagate the service credential to the client.</span></span> <span data-ttu-id="5522f-105"><xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.NegotiationTimeout%2A> 属性控制多路交换需要多长时间才能完成。</span><span class="sxs-lookup"><span data-stu-id="5522f-105">The <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.NegotiationTimeout%2A> property controls how long the multi-leg exchange can take to complete.</span></span> <span data-ttu-id="5522f-106">但此超时仅在交换实际经过的时间超过单个请求响应的时间时才适用。</span><span class="sxs-lookup"><span data-stu-id="5522f-106">However, this timeout only applies if the exchange actually takes more that a single request-response.</span></span> <span data-ttu-id="5522f-107">如果协商在一次往返中完成，则该超时不适用。</span><span class="sxs-lookup"><span data-stu-id="5522f-107">In cases where the negotiation completes in a single round trip, the timeout does not apply.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5522f-108">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5522f-108">See Also</span></span>  
 <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings>  
 [<span data-ttu-id="5522f-109">如何： 设置最大时钟偏差</span><span class="sxs-lookup"><span data-stu-id="5522f-109">How to: Set a Max Clock Skew</span></span>](../../../../docs/framework/wcf/feature-details/how-to-set-a-max-clock-skew.md)
