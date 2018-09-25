---
title: '&lt;servicePointManager&gt;元素 （网络设置）'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#servicePointManager
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/servicePointManager
helpviewer_keywords:
- servicePointManager element
- <servicePointManager> element
ms.assetid: 6e5def51-3646-4ef6-a7bd-c69151321bec
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 2aaf590975d9fd3f5d78cb64d8d2b1c38c0e8dc7
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/25/2018
ms.locfileid: "47113064"
---
# <a name="ltservicepointmanagergt-element-network-settings"></a><span data-ttu-id="b7cf7-102">&lt;servicePointManager&gt;元素 （网络设置）</span><span class="sxs-lookup"><span data-stu-id="b7cf7-102">&lt;servicePointManager&gt; Element (Network Settings)</span></span>
<span data-ttu-id="b7cf7-103">配置连接到网络资源。</span><span class="sxs-lookup"><span data-stu-id="b7cf7-103">Configures connections to network resources.</span></span>  
  
 <span data-ttu-id="b7cf7-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="b7cf7-104">\<configuration></span></span>  
<span data-ttu-id="b7cf7-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="b7cf7-105">\<system.net></span></span>  
<span data-ttu-id="b7cf7-106">\<设置 ></span><span class="sxs-lookup"><span data-stu-id="b7cf7-106">\<settings></span></span>  
<span data-ttu-id="b7cf7-107">\<servicePointManager ></span><span class="sxs-lookup"><span data-stu-id="b7cf7-107">\<servicePointManager></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b7cf7-108">语法</span><span class="sxs-lookup"><span data-stu-id="b7cf7-108">Syntax</span></span>  
  
```xml  
<servicePointManager  
  checkCertificateName="true|false"  
  checkCertificateRevocationList="true|false"  
  encryptionPolicy="AllowNoEncryption|NoEncryption|RequireEncryption"  
  expect100Continue="true|false"  
  useNagleAlgorithm="true|false"  
  enableDnsRoundRobin="true|false"  
  dnsRefreshTimeout="time"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b7cf7-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="b7cf7-109">Attributes and Elements</span></span>  
 <span data-ttu-id="b7cf7-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="b7cf7-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b7cf7-111">特性</span><span class="sxs-lookup"><span data-stu-id="b7cf7-111">Attributes</span></span>  
  
|<span data-ttu-id="b7cf7-112">**特性**</span><span class="sxs-lookup"><span data-stu-id="b7cf7-112">**Attribute**</span></span>|<span data-ttu-id="b7cf7-113">**说明**</span><span class="sxs-lookup"><span data-stu-id="b7cf7-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`checkCertificateName`|<span data-ttu-id="b7cf7-114">指定系统是否应验证对证书的名称与之前使用的证书匹配服务器主机名。</span><span class="sxs-lookup"><span data-stu-id="b7cf7-114">Specifies whether the system should verify that the name on the certificate matches the server host name before using the certificate.</span></span> <span data-ttu-id="b7cf7-115">默认值为 `true`。</span><span class="sxs-lookup"><span data-stu-id="b7cf7-115">The default value is `true`.</span></span>|  
|`checkCertificateRevocationList`|<span data-ttu-id="b7cf7-116">指定是否应检查系统，然后再使用该证书是否已吊销证书。</span><span class="sxs-lookup"><span data-stu-id="b7cf7-116">Specifies whether the system should check whether the certificate has been revoked before using the certificate.</span></span> <span data-ttu-id="b7cf7-117">默认值为 `false`。</span><span class="sxs-lookup"><span data-stu-id="b7cf7-117">The default value is `false`.</span></span>|  
|`dnsRefreshTimeout`|<span data-ttu-id="b7cf7-118">结合使用 DNS 轮循机制选项，以毫秒为单位指定时间长度域名服务 (DNS) 解析的缓存。</span><span class="sxs-lookup"><span data-stu-id="b7cf7-118">Specifies how long Domain Name Service (DNS) resolutions are cached in conjunction with the DNS Round Robin option, in milliseconds.</span></span> <span data-ttu-id="b7cf7-119">默认值是 120,000 毫秒（2 分钟）。</span><span class="sxs-lookup"><span data-stu-id="b7cf7-119">The default value is 120,000 milliseconds (two minutes).</span></span>|  
|`enableDnsRoundRobin`|<span data-ttu-id="b7cf7-120">指定是否具有多个 Internet 协议 (IP) 地址返回命名的主机的 DNS 解析所有地址或只是第一个。</span><span class="sxs-lookup"><span data-stu-id="b7cf7-120">Specifies whether DNS resolutions of host names with multiple Internet Protocol (IP) addresses return all the addresses, or just the first one.</span></span> <span data-ttu-id="b7cf7-121">默认值为 `false`。</span><span class="sxs-lookup"><span data-stu-id="b7cf7-121">The default value is `false`.</span></span>|  
|`encryptionPolicy`|<span data-ttu-id="b7cf7-122">指定应用于 SSL/TLS 会话上的加密策略<xref:System.Net.ServicePointManager>实例。</span><span class="sxs-lookup"><span data-stu-id="b7cf7-122">Specifies the encryption policy applied to an SSL/TLS session on a <xref:System.Net.ServicePointManager> instance.</span></span> <span data-ttu-id="b7cf7-123">可能的值为等效的值为<xref:System.Net.Security.EncryptionPolicy>枚举。</span><span class="sxs-lookup"><span data-stu-id="b7cf7-123">The possible values are equivalent to the values for the <xref:System.Net.Security.EncryptionPolicy> enumeration.</span></span> <span data-ttu-id="b7cf7-124">利用<xref:System.Security.Authentication.CipherAlgorithmType.Null>时，必须提供的加密策略设置为`NoEncryption`。</span><span class="sxs-lookup"><span data-stu-id="b7cf7-124">The use of <xref:System.Security.Authentication.CipherAlgorithmType.Null> is required when the encryption policy is set to `NoEncryption`.</span></span> <span data-ttu-id="b7cf7-125">默认值为 `RequireEncryption`。</span><span class="sxs-lookup"><span data-stu-id="b7cf7-125">The default value is `RequireEncryption`.</span></span>|  
|`expect100Continue`|<span data-ttu-id="b7cf7-126">指定是否应该会 POST 方法收到`100-continue`来自服务器的响应。</span><span class="sxs-lookup"><span data-stu-id="b7cf7-126">Specifies whether POST methods should expect to receive a `100-continue` response from the server.</span></span> <span data-ttu-id="b7cf7-127">默认值为 `true`。</span><span class="sxs-lookup"><span data-stu-id="b7cf7-127">The default value is `true`.</span></span>|  
|`useNagleAlgorithm`|<span data-ttu-id="b7cf7-128">指定由服务点管理器控制的连接是否使用 Nagle 算法。</span><span class="sxs-lookup"><span data-stu-id="b7cf7-128">Specifies whether connections controlled by the service point manager use the Nagle algorithm.</span></span> <span data-ttu-id="b7cf7-129">默认值为 `true`。</span><span class="sxs-lookup"><span data-stu-id="b7cf7-129">The default value is `true`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b7cf7-130">子元素</span><span class="sxs-lookup"><span data-stu-id="b7cf7-130">Child Elements</span></span>  
 <span data-ttu-id="b7cf7-131">无。</span><span class="sxs-lookup"><span data-stu-id="b7cf7-131">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b7cf7-132">父元素</span><span class="sxs-lookup"><span data-stu-id="b7cf7-132">Parent Elements</span></span>  
  
|<span data-ttu-id="b7cf7-133">**元素**</span><span class="sxs-lookup"><span data-stu-id="b7cf7-133">**Element**</span></span>|<span data-ttu-id="b7cf7-134">**说明**</span><span class="sxs-lookup"><span data-stu-id="b7cf7-134">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="b7cf7-135">设置</span><span class="sxs-lookup"><span data-stu-id="b7cf7-135">Settings</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|<span data-ttu-id="b7cf7-136">配置 <xref:System.Net> 命名空间的基本网络选项。</span><span class="sxs-lookup"><span data-stu-id="b7cf7-136">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b7cf7-137">备注</span><span class="sxs-lookup"><span data-stu-id="b7cf7-137">Remarks</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="b7cf7-138">配置文件</span><span class="sxs-lookup"><span data-stu-id="b7cf7-138">Configuration Files</span></span>  
 <span data-ttu-id="b7cf7-139">此元素可在应用程序配置文件或计算机配置文件 (Machine.config) 中使用。</span><span class="sxs-lookup"><span data-stu-id="b7cf7-139">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7cf7-140">请参阅</span><span class="sxs-lookup"><span data-stu-id="b7cf7-140">See Also</span></span>  
 <xref:System.Net.ServicePointManager>  
 <xref:System.Net.Security.EncryptionPolicy>  
 [<span data-ttu-id="b7cf7-141">网络设置架构</span><span class="sxs-lookup"><span data-stu-id="b7cf7-141">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
