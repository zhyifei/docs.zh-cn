---
title: System.ServiceModel.Channels.HttpsClientCertificateNotPresent
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b13ef1b6-e340-401d-93ca-2710c3842205
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 3a9eb867826fbf1e4028f57e5118ff18d4329b23
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="systemservicemodelchannelshttpsclientcertificatenotpresent"></a><span data-ttu-id="73362-102">System.ServiceModel.Channels.HttpsClientCertificateNotPresent</span><span class="sxs-lookup"><span data-stu-id="73362-102">System.ServiceModel.Channels.HttpsClientCertificateNotPresent</span></span>
<span data-ttu-id="73362-103">需要客户端证书。</span><span class="sxs-lookup"><span data-stu-id="73362-103">Client certificate is required.</span></span> <span data-ttu-id="73362-104">在请求中未找到任何证书。</span><span class="sxs-lookup"><span data-stu-id="73362-104">No certificate was found in the request.</span></span>  
  
## <a name="description"></a><span data-ttu-id="73362-105">描述</span><span class="sxs-lookup"><span data-stu-id="73362-105">Description</span></span>  
 <span data-ttu-id="73362-106">此跟踪指示 HTTPS 侦听器收到与客户端证书无关的 HTTPS 请求。</span><span class="sxs-lookup"><span data-stu-id="73362-106">This trace indicates that the HTTPS listener received an HTTPS request that was not associated with a client certificate.</span></span> <span data-ttu-id="73362-107">因为侦听器被配置为对所有 HTTPS 请求都要求提供客户端证书，所以侦听器未能验证该客户端的真实性。</span><span class="sxs-lookup"><span data-stu-id="73362-107">Since the listener was configured to require client certificates on all HTTPS requests, the listener failed to validate the client’s authenticity.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73362-108">另请参阅</span><span class="sxs-lookup"><span data-stu-id="73362-108">See Also</span></span>  
 [<span data-ttu-id="73362-109">跟踪</span><span class="sxs-lookup"><span data-stu-id="73362-109">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="73362-110">使用跟踪来排查你的应用程序</span><span class="sxs-lookup"><span data-stu-id="73362-110">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="73362-111">管理和诊断</span><span class="sxs-lookup"><span data-stu-id="73362-111">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
