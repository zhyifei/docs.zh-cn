---
title: Internet Explorer 完成的与 WCF 完成的服务证书验证之间的差异
ms.date: 03/30/2017
helpviewer_keywords:
- service certificate validation [WCF]
- certificates [WCF], service certificate validation
ms.assetid: 9dffcab2-70a9-40f0-99fd-d3a0b296028f
ms.openlocfilehash: 0bced548cdc9423d1907de09e8b52ebe078d7c19
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59225907"
---
# <a name="differences-between-service-certificate-validation-done-by-internet-explorer-and-wcf"></a><span data-ttu-id="d5f17-102">Internet Explorer 完成的与 WCF 完成的服务证书验证之间的差异</span><span class="sxs-lookup"><span data-stu-id="d5f17-102">Differences Between Service Certificate Validation Done by Internet Explorer and WCF</span></span>
<span data-ttu-id="d5f17-103">由于 Internet Explorer 和 Windows Communication Foundation (WCF) 验证服务证书时使用 HTTPS 的方式不同，很可能 Internet Explorer 将无法再访问帮助页或 Web 服务描述语言(WSDL) 服务的即使 WCF 客户端仍能够成功将消息发送到服务终结点。</span><span class="sxs-lookup"><span data-stu-id="d5f17-103">Because of difference between the way Internet Explorer and Windows Communication Foundation (WCF) validate service certificates when HTTPS is used, it is possible that Internet Explorer will not be able to access the Help page or Web Services Description Language (WSDL) of a service even though a WCF client is able to successfully send messages to the service endpoints.</span></span> <span data-ttu-id="d5f17-104">这是因为 Internet Explorer 会检查是否有服务证书`ServerAuthentication`中的增强的使用标志，对象标识符 (OID)，而 WCF 不强制实施此类约束。</span><span class="sxs-lookup"><span data-stu-id="d5f17-104">This is because Internet Explorer checks whether the service certificate has the `ServerAuthentication` object identifiers (OID) in the enhanced usage flags, whereas WCF does not enforce such a constraint.</span></span> <span data-ttu-id="d5f17-105">如果 Internet Explorer 无法访问服务帮助页或服务的 WSDL，请使用[ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)访问服务元数据。</span><span class="sxs-lookup"><span data-stu-id="d5f17-105">If Internet Explorer is unable to access the service Help page or the WSDL for the service, use the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) to access the service metadata.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5f17-106">请参阅</span><span class="sxs-lookup"><span data-stu-id="d5f17-106">See also</span></span>

- [<span data-ttu-id="d5f17-107">HTTPS、通过 TCP 的 SSL 与 SOAP 安全之间的证书验证差异</span><span class="sxs-lookup"><span data-stu-id="d5f17-107">Certificate Validation Differences Between HTTPS, SSL over TCP, and SOAP Security</span></span>](../../../../docs/framework/wcf/feature-details/cert-val-diff-https-ssl-over-tcp-and-soap.md)
- [<span data-ttu-id="d5f17-108">如何：检索元数据并实现兼容服务</span><span class="sxs-lookup"><span data-stu-id="d5f17-108">How to: Retrieve Metadata and Implement a Compliant Service</span></span>](../../../../docs/framework/wcf/feature-details/how-to-retrieve-metadata-and-implement-a-compliant-service.md)
