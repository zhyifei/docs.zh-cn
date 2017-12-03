---
title: "Internet Explorer 完成的与 WCF 完成的服务证书验证之间的差异"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- service certificate validation [WCF]
- certificates [WCF], service certificate validation
ms.assetid: 9dffcab2-70a9-40f0-99fd-d3a0b296028f
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b74886f05ca6dc38c724e02cd091c6dd212c554f
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="differences-between-service-certificate-validation-done-by-internet-explorer-and-wcf"></a><span data-ttu-id="1527f-102">Internet Explorer 完成的与 WCF 完成的服务证书验证之间的差异</span><span class="sxs-lookup"><span data-stu-id="1527f-102">Differences Between Service Certificate Validation Done by Internet Explorer and WCF</span></span>
<span data-ttu-id="1527f-103">因为在使用 HTTPS 时，Internet Explorer 与 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 验证服务证书的方式不同，所以有可能 Internet Explorer 将无法访问帮助页或服务的 Web 服务描述语言 (WSDL)，即使 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 客户端可以向服务终结点成功发送消息时也将如此。</span><span class="sxs-lookup"><span data-stu-id="1527f-103">Because of difference between the way Internet Explorer and [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] validate service certificates when HTTPS is used, it is possible that Internet Explorer will not be able to access the Help page or Web Services Description Language (WSDL) of a service even though a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client is able to successfully send messages to the service endpoints.</span></span> <span data-ttu-id="1527f-104">这是因为 Internet Explorer 会检查服务证书的增强使用标志中是否具有 `ServerAuthentication` 对象标识符 (OID)，而 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 则不施加此类约束。</span><span class="sxs-lookup"><span data-stu-id="1527f-104">This is because Internet Explorer checks whether the service certificate has the `ServerAuthentication` object identifiers (OID) in the enhanced usage flags, whereas [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] does not enforce such a constraint.</span></span> <span data-ttu-id="1527f-105">如果 Internet 资源管理器无法访问服务帮助页或服务的 WSDL，请使用[ServiceModel 元数据实用工具 (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)访问服务元数据。</span><span class="sxs-lookup"><span data-stu-id="1527f-105">If Internet Explorer is unable to access the service Help page or the WSDL for the service, use the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) to access the service metadata.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1527f-106">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1527f-106">See Also</span></span>  
 [<span data-ttu-id="1527f-107">HTTPS、 SSL over TCP 和 SOAP 安全之间的证书验证差异</span><span class="sxs-lookup"><span data-stu-id="1527f-107">Certificate Validation Differences Between HTTPS, SSL over TCP, and SOAP Security</span></span>](../../../../docs/framework/wcf/feature-details/cert-val-diff-https-ssl-over-tcp-and-soap.md)  
 [<span data-ttu-id="1527f-108">如何： 检索元数据和实现兼容服务</span><span class="sxs-lookup"><span data-stu-id="1527f-108">How to: Retrieve Metadata and Implement a Compliant Service</span></span>](../../../../docs/framework/wcf/feature-details/how-to-retrieve-metadata-and-implement-a-compliant-service.md)
