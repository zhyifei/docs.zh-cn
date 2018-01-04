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
ms.workload: dotnet
ms.openlocfilehash: cd70b4154a388ecb30518f03773d2a296258d7b0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="systemservicemodelchannelshttpsclientcertificatenotpresent"></a><span data-ttu-id="8d521-102">System.ServiceModel.Channels.HttpsClientCertificateNotPresent</span><span class="sxs-lookup"><span data-stu-id="8d521-102">System.ServiceModel.Channels.HttpsClientCertificateNotPresent</span></span>
<span data-ttu-id="8d521-103">需要客户端证书。</span><span class="sxs-lookup"><span data-stu-id="8d521-103">Client certificate is required.</span></span> <span data-ttu-id="8d521-104">在请求中未找到任何证书。</span><span class="sxs-lookup"><span data-stu-id="8d521-104">No certificate was found in the request.</span></span>  
  
## <a name="description"></a><span data-ttu-id="8d521-105">描述</span><span class="sxs-lookup"><span data-stu-id="8d521-105">Description</span></span>  
 <span data-ttu-id="8d521-106">此跟踪指示 HTTPS 侦听器收到与客户端证书无关的 HTTPS 请求。</span><span class="sxs-lookup"><span data-stu-id="8d521-106">This trace indicates that the HTTPS listener received an HTTPS request that was not associated with a client certificate.</span></span> <span data-ttu-id="8d521-107">因为侦听器被配置为对所有 HTTPS 请求都要求提供客户端证书，所以侦听器未能验证该客户端的真实性。</span><span class="sxs-lookup"><span data-stu-id="8d521-107">Since the listener was configured to require client certificates on all HTTPS requests, the listener failed to validate the client’s authenticity.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d521-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="8d521-108">See Also</span></span>  
 [<span data-ttu-id="8d521-109">跟踪</span><span class="sxs-lookup"><span data-stu-id="8d521-109">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="8d521-110">使用跟踪来排除应用程序故障</span><span class="sxs-lookup"><span data-stu-id="8d521-110">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="8d521-111">管理和诊断</span><span class="sxs-lookup"><span data-stu-id="8d521-111">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
