---
title: 如何：以一致的方式引用 X.509 证书
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- certificates [WCF], referencing X.509 certificates
ms.assetid: a6de1c63-e450-4640-ad08-ad7302dbfbfc
ms.openlocfilehash: bd911b1586f7f4a4816efa32480ef99ca12404f4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59176197"
---
# <a name="how-to-consistently-reference-x509-certificates"></a><span data-ttu-id="4d9f4-102">如何：以一致的方式引用 X.509 证书</span><span class="sxs-lookup"><span data-stu-id="4d9f4-102">How to: Consistently Reference X.509 Certificates</span></span>
<span data-ttu-id="4d9f4-103">可以采用下列多种方式来标识证书：证书哈希、颁发者和序列号或者使用者密钥标识符 (SKI)。</span><span class="sxs-lookup"><span data-stu-id="4d9f4-103">You can identify a certificate in several ways: by the hash of the certificate, by the issuer and serial number, or by the subject key identifier (SKI).</span></span> <span data-ttu-id="4d9f4-104">SKI 为证书的使用者公钥提供唯一标识，通常用于处理 XML 数字签名。</span><span class="sxs-lookup"><span data-stu-id="4d9f4-104">The SKI provides a unique identification for the certificate's subject public key and is often used when working with XML digital signing.</span></span> <span data-ttu-id="4d9f4-105">SKI 值通常为形式的 X.509 证书的一部分*X.509 证书扩展*。</span><span class="sxs-lookup"><span data-stu-id="4d9f4-105">The SKI value is usually part of the X.509 certificate as an *X.509 certificate extension*.</span></span> <span data-ttu-id="4d9f4-106">Windows Communication Foundation (WCF) 具有一个默认*引用样式*如果证书中缺少 SKI 扩展，则使用颁发者和序列号。</span><span class="sxs-lookup"><span data-stu-id="4d9f4-106">Windows Communication Foundation (WCF) has a default *referencing style* that uses the issuer and serial number if the SKI extension is missing from the certificate.</span></span> <span data-ttu-id="4d9f4-107">如果证书中包含 SKI 扩展，该默认引用样式将使用 SKI 来指向证书。</span><span class="sxs-lookup"><span data-stu-id="4d9f4-107">If the certificate contains the SKI extension, the default referencing style uses the SKI to point to the certificate.</span></span> <span data-ttu-id="4d9f4-108">如果在应用程序开发，使用的证书不使用使用 SKI 扩展的证书的 SKI 扩展的交换机中，使用 WCF 生成消息中的引用样式也会更改。</span><span class="sxs-lookup"><span data-stu-id="4d9f4-108">If mid-way through development of an application, you switch from using certificates that do not use the SKI extension to certificates that use the SKI extension, the referencing style used in WCF-generated messages also changes.</span></span>  
  
 <span data-ttu-id="4d9f4-109">如果无论是否存在 SKI 扩展，都需要使用一致的引用样式，则可以配置所需的引用样式，如下面的代码中所示。</span><span class="sxs-lookup"><span data-stu-id="4d9f4-109">If a consistent referencing style is required regardless of SKI extension presence, it is possible to configure the desired referencing style as shown in the following code.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4d9f4-110">示例</span><span class="sxs-lookup"><span data-stu-id="4d9f4-110">Example</span></span>  
 <span data-ttu-id="4d9f4-111">下面的示例创建一个自定义安全绑定元素，该元素使用一致的引用样式：颁发者名称和序列号。</span><span class="sxs-lookup"><span data-stu-id="4d9f4-111">The following example creates a custom security binding element that uses a single consistent referencing style, the issuer name and serial number.</span></span>  
  
 [!code-csharp[c_ReferencingCertificatesConsistently#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_referencingcertificatesconsistently/cs/source.cs#1)]
 [!code-vb[c_ReferencingCertificatesConsistently#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_referencingcertificatesconsistently/vb/source.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="4d9f4-112">编译代码</span><span class="sxs-lookup"><span data-stu-id="4d9f4-112">Compiling the Code</span></span>  
 <span data-ttu-id="4d9f4-113">编译该代码需要以下命名空间：</span><span class="sxs-lookup"><span data-stu-id="4d9f4-113">The following namespaces are required to compile the code:</span></span>  
  
-   <xref:System>  
  
-   <xref:System.ServiceModel>  
  
-   <xref:System.ServiceModel.Channels>  
  
-   <xref:System.ServiceModel.Security.Tokens>  
  
## <a name="see-also"></a><span data-ttu-id="4d9f4-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="4d9f4-114">See also</span></span>

- [<span data-ttu-id="4d9f4-115">使用证书</span><span class="sxs-lookup"><span data-stu-id="4d9f4-115">Working with Certificates</span></span>](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
