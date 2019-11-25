---
title: <servicePointManager> 元素（网络设置）
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#servicePointManager
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/servicePointManager
helpviewer_keywords:
- servicePointManager element
- <servicePointManager> element
ms.assetid: 6e5def51-3646-4ef6-a7bd-c69151321bec
ms.openlocfilehash: b7333016fea2d46285d3c98181c0ca4904c376f8
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/14/2019
ms.locfileid: "74089129"
---
# <a name="servicepointmanager-element-network-settings"></a><span data-ttu-id="97dd1-102">\<servicePointManager > 元素（网络设置）</span><span class="sxs-lookup"><span data-stu-id="97dd1-102">\<servicePointManager> Element (Network Settings)</span></span>
<span data-ttu-id="97dd1-103">配置与网络资源的连接。</span><span class="sxs-lookup"><span data-stu-id="97dd1-103">Configures connections to network resources.</span></span>  

<span data-ttu-id="97dd1-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="97dd1-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="97dd1-105">\<&nbsp;&nbsp;[ **> 的**](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="97dd1-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="97dd1-106">&nbsp;&nbsp;&nbsp;&nbsp;\<[**设置 >** ](settings-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="97dd1-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<settings>**](settings-element-network-settings.md)</span></span>\
<span data-ttu-id="97dd1-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<servicePointManager >**</span><span class="sxs-lookup"><span data-stu-id="97dd1-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<servicePointManager>**</span></span>

## <a name="syntax"></a><span data-ttu-id="97dd1-108">语法</span><span class="sxs-lookup"><span data-stu-id="97dd1-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="97dd1-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="97dd1-109">Attributes and Elements</span></span>  
 <span data-ttu-id="97dd1-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="97dd1-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="97dd1-111">特性</span><span class="sxs-lookup"><span data-stu-id="97dd1-111">Attributes</span></span>  
  
|<span data-ttu-id="97dd1-112">**特性**</span><span class="sxs-lookup"><span data-stu-id="97dd1-112">**Attribute**</span></span>|<span data-ttu-id="97dd1-113">**描述**</span><span class="sxs-lookup"><span data-stu-id="97dd1-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`checkCertificateName`|<span data-ttu-id="97dd1-114">指定在使用证书之前，系统是否应验证证书上的名称是否与服务器主机名匹配。</span><span class="sxs-lookup"><span data-stu-id="97dd1-114">Specifies whether the system should verify that the name on the certificate matches the server host name before using the certificate.</span></span> <span data-ttu-id="97dd1-115">默认值为 `true`。</span><span class="sxs-lookup"><span data-stu-id="97dd1-115">The default value is `true`.</span></span>|  
|`checkCertificateRevocationList`|<span data-ttu-id="97dd1-116">指定在使用证书之前系统是否应检查证书是否已吊销。</span><span class="sxs-lookup"><span data-stu-id="97dd1-116">Specifies whether the system should check whether the certificate has been revoked before using the certificate.</span></span> <span data-ttu-id="97dd1-117">默认值为 `false`。</span><span class="sxs-lookup"><span data-stu-id="97dd1-117">The default value is `false`.</span></span>|  
|`dnsRefreshTimeout`|<span data-ttu-id="97dd1-118">指定域名服务（DNS）解析与 DNS 轮循机制选项一起缓存的时间长度（以毫秒为单位）。</span><span class="sxs-lookup"><span data-stu-id="97dd1-118">Specifies how long Domain Name Service (DNS) resolutions are cached in conjunction with the DNS Round Robin option, in milliseconds.</span></span> <span data-ttu-id="97dd1-119">默认值是 120,000 毫秒（2 分钟）。</span><span class="sxs-lookup"><span data-stu-id="97dd1-119">The default value is 120,000 milliseconds (two minutes).</span></span>|  
|`enableDnsRoundRobin`|<span data-ttu-id="97dd1-120">指定具有多个 Internet 协议（IP）地址的主机名的 DNS 解析是返回所有地址，还是只返回第一个地址。</span><span class="sxs-lookup"><span data-stu-id="97dd1-120">Specifies whether DNS resolutions of host names with multiple Internet Protocol (IP) addresses return all the addresses, or just the first one.</span></span> <span data-ttu-id="97dd1-121">默认值为 `false`。</span><span class="sxs-lookup"><span data-stu-id="97dd1-121">The default value is `false`.</span></span>|  
|`encryptionPolicy`|<span data-ttu-id="97dd1-122">指定应用于 <xref:System.Net.ServicePointManager> 实例上的 SSL/TLS 会话的加密策略。</span><span class="sxs-lookup"><span data-stu-id="97dd1-122">Specifies the encryption policy applied to an SSL/TLS session on a <xref:System.Net.ServicePointManager> instance.</span></span> <span data-ttu-id="97dd1-123">可能的值与 <xref:System.Net.Security.EncryptionPolicy> 枚举的值等效。</span><span class="sxs-lookup"><span data-stu-id="97dd1-123">The possible values are equivalent to the values for the <xref:System.Net.Security.EncryptionPolicy> enumeration.</span></span> <span data-ttu-id="97dd1-124">当加密策略设置为 `NoEncryption`时，需要使用 <xref:System.Security.Authentication.CipherAlgorithmType.Null>。</span><span class="sxs-lookup"><span data-stu-id="97dd1-124">The use of <xref:System.Security.Authentication.CipherAlgorithmType.Null> is required when the encryption policy is set to `NoEncryption`.</span></span> <span data-ttu-id="97dd1-125">默认值为 `RequireEncryption`。</span><span class="sxs-lookup"><span data-stu-id="97dd1-125">The default value is `RequireEncryption`.</span></span>|  
|`expect100Continue`|<span data-ttu-id="97dd1-126">指定 POST 方法是否应该接收来自服务器的 `100-continue` 响应。</span><span class="sxs-lookup"><span data-stu-id="97dd1-126">Specifies whether POST methods should expect to receive a `100-continue` response from the server.</span></span> <span data-ttu-id="97dd1-127">默认值为 `true`。</span><span class="sxs-lookup"><span data-stu-id="97dd1-127">The default value is `true`.</span></span>|  
|`useNagleAlgorithm`|<span data-ttu-id="97dd1-128">指定由服务点管理器控制的连接是否使用 Nagle 算法。</span><span class="sxs-lookup"><span data-stu-id="97dd1-128">Specifies whether connections controlled by the service point manager use the Nagle algorithm.</span></span> <span data-ttu-id="97dd1-129">默认值为 `true`。</span><span class="sxs-lookup"><span data-stu-id="97dd1-129">The default value is `true`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="97dd1-130">子元素</span><span class="sxs-lookup"><span data-stu-id="97dd1-130">Child Elements</span></span>  
 <span data-ttu-id="97dd1-131">无。</span><span class="sxs-lookup"><span data-stu-id="97dd1-131">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="97dd1-132">父元素</span><span class="sxs-lookup"><span data-stu-id="97dd1-132">Parent Elements</span></span>  
  
|<span data-ttu-id="97dd1-133">**元素**</span><span class="sxs-lookup"><span data-stu-id="97dd1-133">**Element**</span></span>|<span data-ttu-id="97dd1-134">**描述**</span><span class="sxs-lookup"><span data-stu-id="97dd1-134">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="97dd1-135">设置</span><span class="sxs-lookup"><span data-stu-id="97dd1-135">Settings</span></span>](settings-element-network-settings.md)|<span data-ttu-id="97dd1-136">配置 <xref:System.Net> 命名空间的基本网络选项。</span><span class="sxs-lookup"><span data-stu-id="97dd1-136">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="97dd1-137">备注</span><span class="sxs-lookup"><span data-stu-id="97dd1-137">Remarks</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="97dd1-138">配置文件</span><span class="sxs-lookup"><span data-stu-id="97dd1-138">Configuration Files</span></span>  
 <span data-ttu-id="97dd1-139">此元素可在应用程序配置文件或计算机配置文件 (Machine.config) 中使用。</span><span class="sxs-lookup"><span data-stu-id="97dd1-139">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97dd1-140">请参阅</span><span class="sxs-lookup"><span data-stu-id="97dd1-140">See also</span></span>

- <xref:System.Net.ServicePointManager>
- <xref:System.Net.Security.EncryptionPolicy>
- [<span data-ttu-id="97dd1-141">网络设置架构</span><span class="sxs-lookup"><span data-stu-id="97dd1-141">Network Settings Schema</span></span>](index.md)
