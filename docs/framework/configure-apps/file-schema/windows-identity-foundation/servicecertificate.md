---
title: <serviceCertificate>
ms.date: 03/30/2017
ms.assetid: 42c7f291-2ec3-43c5-8872-35897ff3c660
author: BrucePerlerMS
ms.openlocfilehash: 653dd9cfadbfd33f5371b77172199b946321bc8c
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251858"
---
# <a name="servicecertificate"></a><span data-ttu-id="088c8-101">\<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="088c8-101">\<serviceCertificate></span></span>
<span data-ttu-id="088c8-102">配置用于加密和解密令牌的 x.509 证书。</span><span class="sxs-lookup"><span data-stu-id="088c8-102">Configures the X.509 certificate that is used to encrypt and decrypt tokens.</span></span>  
  
<span data-ttu-id="088c8-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="088c8-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="088c8-104">&nbsp;&nbsp;[ **\<System.identitymodel >** ](system-identitymodel-services.md)</span><span class="sxs-lookup"><span data-stu-id="088c8-104">&nbsp;&nbsp;[**\<system.identityModel.services>**](system-identitymodel-services.md)</span></span>\
<span data-ttu-id="088c8-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<federationConfiguration >** ](federationconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="088c8-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<federationConfiguration>**](federationconfiguration.md)</span></span>\
<span data-ttu-id="088c8-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<serviceCertificate >**</span><span class="sxs-lookup"><span data-stu-id="088c8-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceCertificate>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="088c8-107">语法</span><span class="sxs-lookup"><span data-stu-id="088c8-107">Syntax</span></span>  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration>  
    <serviceCertificate>  
    </serviceCertificate>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="088c8-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="088c8-108">Attributes and Elements</span></span>  
 <span data-ttu-id="088c8-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="088c8-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="088c8-110">特性</span><span class="sxs-lookup"><span data-stu-id="088c8-110">Attributes</span></span>  
 <span data-ttu-id="088c8-111">无</span><span class="sxs-lookup"><span data-stu-id="088c8-111">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="088c8-112">子元素</span><span class="sxs-lookup"><span data-stu-id="088c8-112">Child Elements</span></span>  
  
|<span data-ttu-id="088c8-113">元素</span><span class="sxs-lookup"><span data-stu-id="088c8-113">Element</span></span>|<span data-ttu-id="088c8-114">描述</span><span class="sxs-lookup"><span data-stu-id="088c8-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="088c8-115">\<certificateReference></span><span class="sxs-lookup"><span data-stu-id="088c8-115">\<certificateReference></span></span>](certificatereference.md)|<span data-ttu-id="088c8-116">指定用于在证书存储中查找和验证 x.509 证书的设置。</span><span class="sxs-lookup"><span data-stu-id="088c8-116">Specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="088c8-117">父元素</span><span class="sxs-lookup"><span data-stu-id="088c8-117">Parent Elements</span></span>  
  
|<span data-ttu-id="088c8-118">元素</span><span class="sxs-lookup"><span data-stu-id="088c8-118">Element</span></span>|<span data-ttu-id="088c8-119">描述</span><span class="sxs-lookup"><span data-stu-id="088c8-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="088c8-120">\<federationConfiguration></span><span class="sxs-lookup"><span data-stu-id="088c8-120">\<federationConfiguration></span></span>](federationconfiguration.md)|<span data-ttu-id="088c8-121">包含配置<xref:System.IdentityModel.Services.WSFederationAuthenticationModule> （WSFAM） <xref:System.IdentityModel.Services.SessionAuthenticationModule>和（SAM）的设置。</span><span class="sxs-lookup"><span data-stu-id="088c8-121">Contains the settings that configure the <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) and the <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM).</span></span>|  
  
## <a name="example"></a><span data-ttu-id="088c8-122">示例</span><span class="sxs-lookup"><span data-stu-id="088c8-122">Example</span></span>  
 <span data-ttu-id="088c8-123">下面的 XML 演示了如何使用\<serviceCertificate > 元素。</span><span class="sxs-lookup"><span data-stu-id="088c8-123">The following XML shows the use of the \<serviceCertificate> element.</span></span> <span data-ttu-id="088c8-124">XML 是从`CustomToken`示例获取的。</span><span class="sxs-lookup"><span data-stu-id="088c8-124">The XML is taken from the `CustomToken` sample.</span></span>  
  
```xml  
<serviceCertificate>  
  <certificateReference x509FindType="FindBySubjectName" findValue="localhost" storeLocation="LocalMachine" storeName="My"/>  
</serviceCertificate>  
```
