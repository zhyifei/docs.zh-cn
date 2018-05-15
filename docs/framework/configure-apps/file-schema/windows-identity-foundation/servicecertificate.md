---
title: '&lt;serviceCertificate&gt;'
ms.date: 03/30/2017
ms.assetid: 42c7f291-2ec3-43c5-8872-35897ff3c660
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: af59562dbf6c13970526f1665a9ba2c57c4f32ee
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="ltservicecertificategt"></a><span data-ttu-id="cf8a1-102">&lt;serviceCertificate&gt;</span><span class="sxs-lookup"><span data-stu-id="cf8a1-102">&lt;serviceCertificate&gt;</span></span>
<span data-ttu-id="cf8a1-103">配置用于加密和解密令牌的 X.509 证书。</span><span class="sxs-lookup"><span data-stu-id="cf8a1-103">Configures the X.509 certificate that is used to encrypt and decrypt tokens.</span></span>  
  
 <span data-ttu-id="cf8a1-104">\<system.identityModel.services ></span><span class="sxs-lookup"><span data-stu-id="cf8a1-104">\<system.identityModel.services></span></span>  
<span data-ttu-id="cf8a1-105">\<federationConfiguration ></span><span class="sxs-lookup"><span data-stu-id="cf8a1-105">\<federationConfiguration></span></span>  
<span data-ttu-id="cf8a1-106">\<serviceCertificate ></span><span class="sxs-lookup"><span data-stu-id="cf8a1-106">\<serviceCertificate></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf8a1-107">语法</span><span class="sxs-lookup"><span data-stu-id="cf8a1-107">Syntax</span></span>  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration>  
    <serviceCertificate>  
    </serviceCertificate>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cf8a1-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="cf8a1-108">Attributes and Elements</span></span>  
 <span data-ttu-id="cf8a1-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="cf8a1-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cf8a1-110">特性</span><span class="sxs-lookup"><span data-stu-id="cf8a1-110">Attributes</span></span>  
 <span data-ttu-id="cf8a1-111">无</span><span class="sxs-lookup"><span data-stu-id="cf8a1-111">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="cf8a1-112">子元素</span><span class="sxs-lookup"><span data-stu-id="cf8a1-112">Child Elements</span></span>  
  
|<span data-ttu-id="cf8a1-113">元素</span><span class="sxs-lookup"><span data-stu-id="cf8a1-113">Element</span></span>|<span data-ttu-id="cf8a1-114">描述</span><span class="sxs-lookup"><span data-stu-id="cf8a1-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cf8a1-115">\<certificateReference ></span><span class="sxs-lookup"><span data-stu-id="cf8a1-115">\<certificateReference></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatereference.md)|<span data-ttu-id="cf8a1-116">指定用于查找和验证的证书存储区中的 X.509 证书的设置。</span><span class="sxs-lookup"><span data-stu-id="cf8a1-116">Specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="cf8a1-117">父元素</span><span class="sxs-lookup"><span data-stu-id="cf8a1-117">Parent Elements</span></span>  
  
|<span data-ttu-id="cf8a1-118">元素</span><span class="sxs-lookup"><span data-stu-id="cf8a1-118">Element</span></span>|<span data-ttu-id="cf8a1-119">描述</span><span class="sxs-lookup"><span data-stu-id="cf8a1-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cf8a1-120">\<federationConfiguration></span><span class="sxs-lookup"><span data-stu-id="cf8a1-120">\<federationConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md)|<span data-ttu-id="cf8a1-121">包含配置的设置<xref:System.IdentityModel.Services.WSFederationAuthenticationModule>(WSFAM) 和<xref:System.IdentityModel.Services.SessionAuthenticationModule>(SAM)。</span><span class="sxs-lookup"><span data-stu-id="cf8a1-121">Contains the settings that configure the <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) and the <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM).</span></span>|  
  
## <a name="example"></a><span data-ttu-id="cf8a1-122">示例</span><span class="sxs-lookup"><span data-stu-id="cf8a1-122">Example</span></span>  
 <span data-ttu-id="cf8a1-123">下面的 XML 演示如何使用\<serviceCertificate > 元素。</span><span class="sxs-lookup"><span data-stu-id="cf8a1-123">The following XML shows the use of the \<serviceCertificate> element.</span></span> <span data-ttu-id="cf8a1-124">XML 取自`CustomToken`示例。</span><span class="sxs-lookup"><span data-stu-id="cf8a1-124">The XML is taken from the `CustomToken` sample.</span></span>  
  
```xml  
<serviceCertificate>  
  <certificateReference x509FindType="FindBySubjectName" findValue="localhost" storeLocation="LocalMachine" storeName="My"/>  
</serviceCertificate>  
```
