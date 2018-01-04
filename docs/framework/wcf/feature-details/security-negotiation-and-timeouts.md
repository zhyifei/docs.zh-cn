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
ms.workload: dotnet
ms.openlocfilehash: 6fbee18d31cb1774300c14587b0f7d973a4996ed
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="security-negotiation-and-timeouts"></a>安全协商和超时
在客户端和服务进行身份验证时，[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 支持将服务凭据作为身份验证的一部分。 在这种情况下，客户端和服务之间将进行潜在多路交换，以便将服务凭据传播到客户端。 <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.NegotiationTimeout%2A> 属性控制多路交换需要多长时间才能完成。 但此超时仅在交换实际经过的时间超过单个请求响应的时间时才适用。 如果协商在一次往返中完成，则该超时不适用。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings>  
 [如何：设置最大时钟偏差](../../../../docs/framework/wcf/feature-details/how-to-set-a-max-clock-skew.md)
