---
title: "HTTPS、通过 TCP 的 SSL 与 SOAP 安全之间的证书验证差异"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: certificates [WCF], validation differences
ms.assetid: 953a219f-4745-4019-9894-c70704f352e6
caps.latest.revision: "14"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 34be2fbc5b8148d7bfdeb5e5d07e5b73ac89a97e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="certificate-validation-differences-between-https-ssl-over-tcp-and-soap-security"></a><span data-ttu-id="6031c-102">HTTPS、通过 TCP 的 SSL 与 SOAP 安全之间的证书验证差异</span><span class="sxs-lookup"><span data-stu-id="6031c-102">Certificate Validation Differences Between HTTPS, SSL over TCP, and SOAP Security</span></span>
<span data-ttu-id="6031c-103">除了通过 HTTP (HTTPS) 或 TCP 的传输层安全 (TLS) 之外，您还可以在 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 中使用具有消息层 (SOAP) 安全的证书。</span><span class="sxs-lookup"><span data-stu-id="6031c-103">You can use certificates in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] with message-layer (SOAP) security in addition to transport-layer security (TLS) over HTTP (HTTPS) or TCP.</span></span> <span data-ttu-id="6031c-104">本主题介绍此类证书的验证方式的差异。</span><span class="sxs-lookup"><span data-stu-id="6031c-104">This topic describes differences in the way such certificates are validated.</span></span>  
  
## <a name="validation-of-https-client-certificates"></a><span data-ttu-id="6031c-105">验证 HTTPS 客户端证书</span><span class="sxs-lookup"><span data-stu-id="6031c-105">Validation of HTTPS Client Certificates</span></span>  
 <span data-ttu-id="6031c-106">当使用 HTTPS 在客户端和服务间通信时，客户端用于向服务进行身份验证的证书必须支持链信任。</span><span class="sxs-lookup"><span data-stu-id="6031c-106">When using HTTPS to communicate between a client and a service, the certificate that the client uses to authenticate to the service must support chain trust.</span></span> <span data-ttu-id="6031c-107">也就是说，它必须链至受信任的根证书颁发机构。</span><span class="sxs-lookup"><span data-stu-id="6031c-107">That is, it must chain to a trusted root certificate authority.</span></span> <span data-ttu-id="6031c-108">否则，HTTP 层将引发<xref:System.Net.WebException>，并显示消息“远程服务器返回错误: (403) 禁止。”</span><span class="sxs-lookup"><span data-stu-id="6031c-108">If not, the HTTP layer raises a <xref:System.Net.WebException> with the message "The remote server returned an error: (403) Forbidden."</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="6031c-109"> 将此异常包装为 <xref:System.ServiceModel.Security.MessageSecurityException>。</span><span class="sxs-lookup"><span data-stu-id="6031c-109"> surfaces this exception as a <xref:System.ServiceModel.Security.MessageSecurityException>.</span></span>  
  
## <a name="validation-of-https-service-certificates"></a><span data-ttu-id="6031c-110">验证 HTTPS 服务证书</span><span class="sxs-lookup"><span data-stu-id="6031c-110">Validation of HTTPS Service Certificates</span></span>  
 <span data-ttu-id="6031c-111">当使用 HTTPS 在客户端和服务间通信时，服务器身份验证使用的证书默认情况下必须支持链信任。</span><span class="sxs-lookup"><span data-stu-id="6031c-111">When using HTTPS to communicate between a client and a service, the certificate that the server authenticates with must support chain trust by default.</span></span> <span data-ttu-id="6031c-112">也就是说，它必须链至受信任的根证书颁发机构。</span><span class="sxs-lookup"><span data-stu-id="6031c-112">That is, it must chain to a trusted root certificate authority.</span></span> <span data-ttu-id="6031c-113">不会执行任何在线检查来查看证书是否已吊销。</span><span class="sxs-lookup"><span data-stu-id="6031c-113">No online check is performed to see whether the certificate has been revoked.</span></span> <span data-ttu-id="6031c-114">可以通过注册 <xref:System.Net.Security.RemoteCertificateValidationCallback> 回调来重写此行为，如以下代码所示。</span><span class="sxs-lookup"><span data-stu-id="6031c-114">You can override this behavior by registering a <xref:System.Net.Security.RemoteCertificateValidationCallback> callback, as shown in the following code.</span></span>  
  
 [!code-csharp[c_CertificateValidationDifferences#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_certificatevalidationdifferences/cs/source.cs#1)] 
 [!code-vb[c_CertificateValidationDifferences#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_certificatevalidationdifferences/vb/source.vb#1)]  
  
 <span data-ttu-id="6031c-115">其中，`ValidateServerCertificate` 的签名如下：</span><span class="sxs-lookup"><span data-stu-id="6031c-115">where the signature for `ValidateServerCertificate` is as follows:</span></span>  
  
 [!code-csharp[c_CertificateValidationDifferences#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_certificatevalidationdifferences/cs/source.cs#2)]
 [!code-vb[c_CertificateValidationDifferences#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_certificatevalidationdifferences/vb/source.vb#2)]  
  
 <span data-ttu-id="6031c-116">实现 `ValidateServerCertificate` 可以执行客户端应用程序开发人员认为在验证服务证书时有必要进行的任何检查。</span><span class="sxs-lookup"><span data-stu-id="6031c-116">Implementing `ValidateServerCertificate` can perform any checks that the client application developer deems necessary to validate the service certificate.</span></span>  
  
## <a name="validation-of-client-certificates-in-ssl-over-tcp-or-soap-security"></a><span data-ttu-id="6031c-117">验证通过 TCP 的 SSL 或 SOAP 安全中的客户端证书</span><span class="sxs-lookup"><span data-stu-id="6031c-117">Validation of Client Certificates in SSL over TCP or SOAP Security</span></span>  
 <span data-ttu-id="6031c-118">使用通过 TCP 的安全套接字层 (SSL) 或消息 (SOAP) 安全时，根据 <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication.CertificateValidationMode%2A> 类的 <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication> 属性值验证客户端证书。</span><span class="sxs-lookup"><span data-stu-id="6031c-118">When using Secure Sockets Layer (SSL) over TCP or message (SOAP) security, client certificates are validated according to the <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication.CertificateValidationMode%2A> property value of the <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication> class.</span></span> <span data-ttu-id="6031c-119">该属性设置为 <xref:System.ServiceModel.Security.X509CertificateValidationMode> 值之一。</span><span class="sxs-lookup"><span data-stu-id="6031c-119">The property is set to one of the <xref:System.ServiceModel.Security.X509CertificateValidationMode> values.</span></span> <span data-ttu-id="6031c-120">根据 <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication.RevocationMode%2A> 类的 <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication> 属性值的值来执行吊销检查。</span><span class="sxs-lookup"><span data-stu-id="6031c-120">Revocation checking is performed according to the values of the <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication.RevocationMode%2A> property value of the <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication> class.</span></span> <span data-ttu-id="6031c-121">该属性设置为 <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> 值之一。</span><span class="sxs-lookup"><span data-stu-id="6031c-121">The property is set to one of the <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> values.</span></span>  
  
 [!code-csharp[c_CertificateValidationDifferences#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_certificatevalidationdifferences/cs/source.cs#3)]
 [!code-vb[c_CertificateValidationDifferences#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_certificatevalidationdifferences/vb/source.vb#3)]  
  
## <a name="validation-of-service-certificate-in-ssl-over-tcp-and-soap-security"></a><span data-ttu-id="6031c-122">验证通过 TCP 的 SSL 和 SOAP 安全中的服务证书</span><span class="sxs-lookup"><span data-stu-id="6031c-122">Validation of Service Certificate in SSL over TCP and SOAP Security</span></span>  
 <span data-ttu-id="6031c-123">使用通过 TCP 的 SSL 或 (SOAP) 消息安全时，根据 <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication.CertificateValidationMode%2A> 类的 <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication> 属性值来验证服务证书。</span><span class="sxs-lookup"><span data-stu-id="6031c-123">When using SSL over TCP or (SOAP) message security, service certificates are validated according to the <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication.CertificateValidationMode%2A> property value of the <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication> class.</span></span> <span data-ttu-id="6031c-124">该属性设置为 <xref:System.ServiceModel.Security.X509CertificateValidationMode> 值之一。</span><span class="sxs-lookup"><span data-stu-id="6031c-124">The property is set to one of the <xref:System.ServiceModel.Security.X509CertificateValidationMode> values.</span></span>  
  
 <span data-ttu-id="6031c-125">根据 <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication.RevocationMode%2A> 类的 <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication> 属性值的值来执行吊销检查。</span><span class="sxs-lookup"><span data-stu-id="6031c-125">Revocation checking is performed according to the values of the <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication.RevocationMode%2A> property value of the <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication> class.</span></span> <span data-ttu-id="6031c-126">该属性设置为 <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> 值之一。</span><span class="sxs-lookup"><span data-stu-id="6031c-126">The property is set to one of the <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> values.</span></span>  
  
 [!code-csharp[c_CertificateValidationDifferences#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_certificatevalidationdifferences/cs/source.cs#4)]
 [!code-vb[c_CertificateValidationDifferences#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_certificatevalidationdifferences/vb/source.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="6031c-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="6031c-127">See Also</span></span>  
 <xref:System.Net.Security.RemoteCertificateValidationCallback>  
 [<span data-ttu-id="6031c-128">使用证书</span><span class="sxs-lookup"><span data-stu-id="6031c-128">Working with Certificates</span></span>](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
