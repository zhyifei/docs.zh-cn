---
title: <serviceCertificate>
ms.date: 03/30/2017
ms.assetid: 42c7f291-2ec3-43c5-8872-35897ff3c660
author: BrucePerlerMS
ms.openlocfilehash: a3aba5618855f7225dc8a427516eaa72b45f6e8b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69942415"
---
# <a name="servicecertificate"></a><span data-ttu-id="88801-101">\<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="88801-101">\<serviceCertificate></span></span>
<span data-ttu-id="88801-102">配置用于加密和解密令牌的 x.509 证书。</span><span class="sxs-lookup"><span data-stu-id="88801-102">Configures the X.509 certificate that is used to encrypt and decrypt tokens.</span></span>  
  
 <span data-ttu-id="88801-103">\<system.identityModel.services></span><span class="sxs-lookup"><span data-stu-id="88801-103">\<system.identityModel.services></span></span>  
<span data-ttu-id="88801-104">\<federationConfiguration></span><span class="sxs-lookup"><span data-stu-id="88801-104">\<federationConfiguration></span></span>  
<span data-ttu-id="88801-105">\<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="88801-105">\<serviceCertificate></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="88801-106">语法</span><span class="sxs-lookup"><span data-stu-id="88801-106">Syntax</span></span>  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration>  
    <serviceCertificate>  
    </serviceCertificate>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="88801-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="88801-107">Attributes and Elements</span></span>  
 <span data-ttu-id="88801-108">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="88801-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="88801-109">特性</span><span class="sxs-lookup"><span data-stu-id="88801-109">Attributes</span></span>  
 <span data-ttu-id="88801-110">无</span><span class="sxs-lookup"><span data-stu-id="88801-110">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="88801-111">子元素</span><span class="sxs-lookup"><span data-stu-id="88801-111">Child Elements</span></span>  
  
|<span data-ttu-id="88801-112">元素</span><span class="sxs-lookup"><span data-stu-id="88801-112">Element</span></span>|<span data-ttu-id="88801-113">描述</span><span class="sxs-lookup"><span data-stu-id="88801-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="88801-114">\<certificateReference></span><span class="sxs-lookup"><span data-stu-id="88801-114">\<certificateReference></span></span>](certificatereference.md)|<span data-ttu-id="88801-115">指定用于在证书存储中查找和验证 x.509 证书的设置。</span><span class="sxs-lookup"><span data-stu-id="88801-115">Specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="88801-116">父元素</span><span class="sxs-lookup"><span data-stu-id="88801-116">Parent Elements</span></span>  
  
|<span data-ttu-id="88801-117">元素</span><span class="sxs-lookup"><span data-stu-id="88801-117">Element</span></span>|<span data-ttu-id="88801-118">描述</span><span class="sxs-lookup"><span data-stu-id="88801-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="88801-119">\<federationConfiguration></span><span class="sxs-lookup"><span data-stu-id="88801-119">\<federationConfiguration></span></span>](federationconfiguration.md)|<span data-ttu-id="88801-120">包含配置<xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) <xref:System.IdentityModel.Services.SessionAuthenticationModule>和 (SAM) 的设置。</span><span class="sxs-lookup"><span data-stu-id="88801-120">Contains the settings that configure the <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) and the <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM).</span></span>|  
  
## <a name="example"></a><span data-ttu-id="88801-121">示例</span><span class="sxs-lookup"><span data-stu-id="88801-121">Example</span></span>  
 <span data-ttu-id="88801-122">下面的 XML 演示了如何使用\<serviceCertificate > 元素。</span><span class="sxs-lookup"><span data-stu-id="88801-122">The following XML shows the use of the \<serviceCertificate> element.</span></span> <span data-ttu-id="88801-123">XML 是从`CustomToken`示例获取的。</span><span class="sxs-lookup"><span data-stu-id="88801-123">The XML is taken from the `CustomToken` sample.</span></span>  
  
```xml  
<serviceCertificate>  
  <certificateReference x509FindType="FindBySubjectName" findValue="localhost" storeLocation="LocalMachine" storeName="My"/>  
</serviceCertificate>  
```
