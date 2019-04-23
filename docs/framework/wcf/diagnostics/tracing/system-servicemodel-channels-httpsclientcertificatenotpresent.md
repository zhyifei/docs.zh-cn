---
title: System.ServiceModel.Channels.HttpsClientCertificateNotPresent
ms.date: 03/30/2017
ms.assetid: b13ef1b6-e340-401d-93ca-2710c3842205
ms.openlocfilehash: 15ae13563cfcfb3765559cafb2d31bd6482df7b2
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59201177"
---
# <a name="systemservicemodelchannelshttpsclientcertificatenotpresent"></a><span data-ttu-id="17aae-102">System.ServiceModel.Channels.HttpsClientCertificateNotPresent</span><span class="sxs-lookup"><span data-stu-id="17aae-102">System.ServiceModel.Channels.HttpsClientCertificateNotPresent</span></span>
<span data-ttu-id="17aae-103">需要客户端证书。</span><span class="sxs-lookup"><span data-stu-id="17aae-103">Client certificate is required.</span></span> <span data-ttu-id="17aae-104">在请求中未找到任何证书。</span><span class="sxs-lookup"><span data-stu-id="17aae-104">No certificate was found in the request.</span></span>  
  
## <a name="description"></a><span data-ttu-id="17aae-105">描述</span><span class="sxs-lookup"><span data-stu-id="17aae-105">Description</span></span>  
 <span data-ttu-id="17aae-106">此跟踪指示 HTTPS 侦听器收到与客户端证书无关的 HTTPS 请求。</span><span class="sxs-lookup"><span data-stu-id="17aae-106">This trace indicates that the HTTPS listener received an HTTPS request that was not associated with a client certificate.</span></span> <span data-ttu-id="17aae-107">因为侦听器被配置为对所有 HTTPS 请求都要求提供客户端证书，所以侦听器未能验证该客户端的真实性。</span><span class="sxs-lookup"><span data-stu-id="17aae-107">Since the listener was configured to require client certificates on all HTTPS requests, the listener failed to validate the client’s authenticity.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17aae-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="17aae-108">See also</span></span>

- [<span data-ttu-id="17aae-109">跟踪</span><span class="sxs-lookup"><span data-stu-id="17aae-109">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="17aae-110">使用跟踪来排除应用程序故障</span><span class="sxs-lookup"><span data-stu-id="17aae-110">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="17aae-111">管理和诊断</span><span class="sxs-lookup"><span data-stu-id="17aae-111">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
