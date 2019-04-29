---
title: <serviceCertificate>
ms.date: 03/30/2017
ms.assetid: 42c7f291-2ec3-43c5-8872-35897ff3c660
author: BrucePerlerMS
ms.openlocfilehash: 328d074f9edc5ddf871308a7e3d694bf94adea78
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61793817"
---
# <a name="servicecertificate"></a><span data-ttu-id="e19e3-101">\<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="e19e3-101">\<serviceCertificate></span></span>
<span data-ttu-id="e19e3-102">配置用于加密和解密令牌的 X.509 证书。</span><span class="sxs-lookup"><span data-stu-id="e19e3-102">Configures the X.509 certificate that is used to encrypt and decrypt tokens.</span></span>  
  
 <span data-ttu-id="e19e3-103">\<system.identityModel.services></span><span class="sxs-lookup"><span data-stu-id="e19e3-103">\<system.identityModel.services></span></span>  
<span data-ttu-id="e19e3-104">\<federationConfiguration></span><span class="sxs-lookup"><span data-stu-id="e19e3-104">\<federationConfiguration></span></span>  
<span data-ttu-id="e19e3-105">\<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="e19e3-105">\<serviceCertificate></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e19e3-106">语法</span><span class="sxs-lookup"><span data-stu-id="e19e3-106">Syntax</span></span>  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration>  
    <serviceCertificate>  
    </serviceCertificate>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e19e3-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="e19e3-107">Attributes and Elements</span></span>  
 <span data-ttu-id="e19e3-108">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="e19e3-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e19e3-109">特性</span><span class="sxs-lookup"><span data-stu-id="e19e3-109">Attributes</span></span>  
 <span data-ttu-id="e19e3-110">None</span><span class="sxs-lookup"><span data-stu-id="e19e3-110">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e19e3-111">子元素</span><span class="sxs-lookup"><span data-stu-id="e19e3-111">Child Elements</span></span>  
  
|<span data-ttu-id="e19e3-112">元素</span><span class="sxs-lookup"><span data-stu-id="e19e3-112">Element</span></span>|<span data-ttu-id="e19e3-113">描述</span><span class="sxs-lookup"><span data-stu-id="e19e3-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e19e3-114">\<certificateReference></span><span class="sxs-lookup"><span data-stu-id="e19e3-114">\<certificateReference></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatereference.md)|<span data-ttu-id="e19e3-115">指定用于查找和验证的证书存储区中的 X.509 证书的设置。</span><span class="sxs-lookup"><span data-stu-id="e19e3-115">Specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e19e3-116">父元素</span><span class="sxs-lookup"><span data-stu-id="e19e3-116">Parent Elements</span></span>  
  
|<span data-ttu-id="e19e3-117">元素</span><span class="sxs-lookup"><span data-stu-id="e19e3-117">Element</span></span>|<span data-ttu-id="e19e3-118">描述</span><span class="sxs-lookup"><span data-stu-id="e19e3-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e19e3-119">\<federationConfiguration></span><span class="sxs-lookup"><span data-stu-id="e19e3-119">\<federationConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md)|<span data-ttu-id="e19e3-120">包含配置的设置<xref:System.IdentityModel.Services.WSFederationAuthenticationModule>(WSFAM) 和<xref:System.IdentityModel.Services.SessionAuthenticationModule>(SAM)。</span><span class="sxs-lookup"><span data-stu-id="e19e3-120">Contains the settings that configure the <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) and the <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM).</span></span>|  
  
## <a name="example"></a><span data-ttu-id="e19e3-121">示例</span><span class="sxs-lookup"><span data-stu-id="e19e3-121">Example</span></span>  
 <span data-ttu-id="e19e3-122">下面的 XML 演示如何使用\<serviceCertificate > 元素。</span><span class="sxs-lookup"><span data-stu-id="e19e3-122">The following XML shows the use of the \<serviceCertificate> element.</span></span> <span data-ttu-id="e19e3-123">XML 来自`CustomToken`示例。</span><span class="sxs-lookup"><span data-stu-id="e19e3-123">The XML is taken from the `CustomToken` sample.</span></span>  
  
```xml  
<serviceCertificate>  
  <certificateReference x509FindType="FindBySubjectName" findValue="localhost" storeLocation="LocalMachine" storeName="My"/>  
</serviceCertificate>  
```
