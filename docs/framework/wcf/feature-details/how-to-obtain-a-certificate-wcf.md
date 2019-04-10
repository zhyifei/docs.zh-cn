---
title: 如何：获取证书 (WCF)
ms.date: 03/30/2017
helpviewer_keywords:
- certificates [WCF], obtaining
ms.assetid: d53762fd-15ea-42dc-b0ea-6a6597aa23f7
ms.openlocfilehash: 21e9e0609ed63c4398f2df7ba718f8af17464b0a
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2019
ms.locfileid: "59332477"
---
# <a name="how-to-obtain-a-certificate-wcf"></a><span data-ttu-id="3c353-102">如何：获取证书 (WCF)</span><span class="sxs-lookup"><span data-stu-id="3c353-102">How to: Obtain a Certificate (WCF)</span></span>
<span data-ttu-id="3c353-103">若要使用任何 Windows Communication Foundation (WCF) 的功能，使用 X.509 证书，必须先获取证书。</span><span class="sxs-lookup"><span data-stu-id="3c353-103">To use any of the Windows Communication Foundation (WCF) features of that use X.509 certificates, you just first obtain certificates.</span></span>  
  
### <a name="to-obtain-an-x509-certificate"></a><span data-ttu-id="3c353-104">获取 X.509 证书</span><span class="sxs-lookup"><span data-stu-id="3c353-104">To obtain an X.509 certificate</span></span>  
  
1. <span data-ttu-id="3c353-105">选择以下选项之一：</span><span class="sxs-lookup"><span data-stu-id="3c353-105">Choose one of the following:</span></span>  
  
    -   <span data-ttu-id="3c353-106">从证书颁发机构（如 VeriSign Inc）购买证书。</span><span class="sxs-lookup"><span data-stu-id="3c353-106">Purchase a certificate from a certification authority, such as VeriSign, Inc.</span></span>  
  
    -   <span data-ttu-id="3c353-107">设置自己的证书服务，并让证书颁发机构为证书签名。</span><span class="sxs-lookup"><span data-stu-id="3c353-107">Set up your own certificate service and have a certification authority sign the certificates.</span></span> [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)]<span data-ttu-id="3c353-108">Windows 2000 Server、 Windows 2000 Server Datacenter 和 Windows 2000 Datacenter Server 所有包括支持公钥基础结构 (PKI) 证书服务。</span><span class="sxs-lookup"><span data-stu-id="3c353-108">, Windows 2000 Server, Windows 2000 Server Datacenter, and Windows 2000 Datacenter Server all include certificate services that support public key infrastructure (PKI).</span></span> <span data-ttu-id="3c353-109">在 Windows Server 2008 中，使用[Active Directory 证书服务](https://go.microsoft.com/fwlink/?LinkID=153483)角色来管理证书颁发机构。</span><span class="sxs-lookup"><span data-stu-id="3c353-109">In Windows Server 2008, use the [Active Directory Certificate Services](https://go.microsoft.com/fwlink/?LinkID=153483) role to manage a certification authority.</span></span>  
  
    -   <span data-ttu-id="3c353-110">设置自己的证书服务，但不对证书进行签名。</span><span class="sxs-lookup"><span data-stu-id="3c353-110">Set up your own certificate service and do not have the certificates signed.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3c353-111">无论采取哪种方法，包含 X.509 证书的 SOAP 请求的接收方都必须信任 X.509 证书。</span><span class="sxs-lookup"><span data-stu-id="3c353-111">Whichever approach you take, the recipient of the SOAP request that contains the X.509 certificate must trust the X.509 certificate.</span></span> <span data-ttu-id="3c353-112">这意味着证书链中的 X.509 证书或颁发者位于“受信任的人”证书存储区中，并且 X.509 证书不在“不受信任的证书”存储区中。</span><span class="sxs-lookup"><span data-stu-id="3c353-112">This means that the X.509 certificate or an issuer in the certificate chain is in the Trusted People certificate store and that the X.509 certificate is not in the Untrusted Certificates store.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c353-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="3c353-113">See also</span></span>

- [<span data-ttu-id="3c353-114">使用证书</span><span class="sxs-lookup"><span data-stu-id="3c353-114">Working with Certificates</span></span>](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="3c353-115">如何：创建开发期间使用的临时证书</span><span class="sxs-lookup"><span data-stu-id="3c353-115">How to: Create Temporary Certificates for Use During Development</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-temporary-certificates-for-use-during-development.md)
