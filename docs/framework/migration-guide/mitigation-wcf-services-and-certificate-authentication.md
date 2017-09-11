---
title: "缓解：WCF 服务和证书身份验证"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ef19c91a-b9df-4bf0-a28e-eb1e99c4bc95
caps.latest.revision: 3
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 1d6f78d24fc6411fca81fbbb8eb886d6d0a7fe9c
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="mitigation-wcf-services-and-certificate-authentication"></a><span data-ttu-id="e070f-102">缓解：WCF 服务和证书身份验证</span><span class="sxs-lookup"><span data-stu-id="e070f-102">Mitigation: WCF Services and Certificate Authentication</span></span>
<span data-ttu-id="e070f-103">.NET Framework 4.6 向 WCF SSL 协议默认列表添加了 TLS 1.1 和 TLS 1.2。</span><span class="sxs-lookup"><span data-stu-id="e070f-103">The .NET Framework 4.6 adds TLS 1.1 and TLS 1.2 to the WCF SSL protocol default list.</span></span> <span data-ttu-id="e070f-104">客户端和服务器计算机都安装了 .NET Framework 4.6 或更高版本时，TLS 1.2 用于协商。</span><span class="sxs-lookup"><span data-stu-id="e070f-104">When both client and server machines have  the .NET Framework 4.6 or later installed, TLS 1.2 is used for negotiation.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="e070f-105">影响</span><span class="sxs-lookup"><span data-stu-id="e070f-105">Impact</span></span>  
 <span data-ttu-id="e070f-106">TLS 1.2 不支持 MD5 证书身份验证。</span><span class="sxs-lookup"><span data-stu-id="e070f-106">TLS 1.2 does not support MD5 certificate authentication.</span></span> <span data-ttu-id="e070f-107">因此，如果客户使用的 SSL 证书对哈希算法使用 MD5，WCF 客户端就无法连接 WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="e070f-107">As a result, if a customer uses an SSL  certificate which uses MD5 for the hash algorithm, the WCF client fails to connect to the WCF service.</span></span> <span data-ttu-id="e070f-108">有关详细信息，请参阅[缓解：WCF 服务和证书身份验证](../../../docs/framework/migration-guide/mitigation-wcf-services-and-certificate-authentication.md)。</span><span class="sxs-lookup"><span data-stu-id="e070f-108">For more information, see [Mitigation: WCF Services and Certificate Authentication](../../../docs/framework/migration-guide/mitigation-wcf-services-and-certificate-authentication.md).</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="e070f-109">缓解操作</span><span class="sxs-lookup"><span data-stu-id="e070f-109">Mitigation</span></span>  
 <span data-ttu-id="e070f-110">可以通过执行下列任一操作来解决此问题，以便 WCF 客户端可以连接 WCF 服务器：</span><span class="sxs-lookup"><span data-stu-id="e070f-110">You can work around this issue so that a WCF client can connect to a WCF server by doing any of the following:</span></span>  
  
-   <span data-ttu-id="e070f-111">将证书更新为不使用 MD5 算法。</span><span class="sxs-lookup"><span data-stu-id="e070f-111">Update the certificate to not use the MD5 algorithm.</span></span> <span data-ttu-id="e070f-112">建议采用此解决方案。</span><span class="sxs-lookup"><span data-stu-id="e070f-112">This is the recommended solution.</span></span>  
  
-   <span data-ttu-id="e070f-113">如果未在源代码中动态配置绑定，将应用程序的配置文件更新为使用 TLS 1.1 或更低版本的协议。</span><span class="sxs-lookup"><span data-stu-id="e070f-113">If the binding is not dynamically configured in source code, update the application's configuration file to use TLS 1.1 or an earlier version of the protocol.</span></span> <span data-ttu-id="e070f-114">这样便可以继续将证书和 MD5 哈希算法结合使用。</span><span class="sxs-lookup"><span data-stu-id="e070f-114">This allows you to continue to use a certificate with the MD5 hash algorithm.</span></span>  
  
    > [!CAUTION]
    >  <span data-ttu-id="e070f-115">不建议采用此解决方法，因为使用 MD5 哈希算法的证书被视为不安全。</span><span class="sxs-lookup"><span data-stu-id="e070f-115">This workaround is not recommended, since a certificate with the MD5 hash algorithm is considered insecure.</span></span>  
  
     <span data-ttu-id="e070f-116">下面的配置文件就采用了此解决方法：</span><span class="sxs-lookup"><span data-stu-id="e070f-116">The following configuration file does this:</span></span>  
  
    ```xml  
    <configuration>  
        <system.serviceModel>  
            <bindings>  
                <netTcpBinding>  
                    <binding>  
                        <security mode= "None|Transport|Message|TransportWithMessageCredential" >  
                            <transport clientCredentialType="None|Windows|Certificate"  
                                                protectionLevel="None|Sign|EncryptAndSign"  
                                                sslProtocols="Ssl3|Tls1|Tls11">  
                            </transport>  
                        </security>  
                    </binding>  
                </netTcpBinding>  
            </bindings>  
        </system.ServiceModel>  
    </configuration>  
    ```  
  
-   <span data-ttu-id="e070f-117">如果在源代码中动态配置了绑定，将 <xref:System.ServiceModel.TcpTransportSecurity.SslProtocols%2A?displayProperty=fullName> 属性更新为使用 TLS 1.1 (<xref:System.Security.Authentication.SslProtocols.Tls11?displayProperty=fullName>) 或源代码中的早期版本协议。</span><span class="sxs-lookup"><span data-stu-id="e070f-117">If the binding is dynamically configured in source code, update the <xref:System.ServiceModel.TcpTransportSecurity.SslProtocols%2A?displayProperty=fullName> property to use TLS 1.1 (<xref:System.Security.Authentication.SslProtocols.Tls11?displayProperty=fullName>) or an  earlier version of the protocol in the source code.</span></span>  
  
    > [!CAUTION]
    >  <span data-ttu-id="e070f-118">不建议采用此解决方法，因为使用 MD5 哈希算法的证书被视为不安全。</span><span class="sxs-lookup"><span data-stu-id="e070f-118">This workaround is not recommended, since a certificate with the MD5 hash algorithm is considered insecure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e070f-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e070f-119">See Also</span></span>  
 [<span data-ttu-id="e070f-120">运行时更改</span><span class="sxs-lookup"><span data-stu-id="e070f-120">Runtime Changes</span></span>](../../../docs/framework/migration-guide/runtime-changes-in-the-net-framework-4-6.md)

