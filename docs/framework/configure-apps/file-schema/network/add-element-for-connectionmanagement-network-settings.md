---
title: connectionManagement 的 <add> 元素（网络设置）
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#add
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/connectionManagement/add
helpviewer_keywords:
- <add> element, connectionManagement
- <connectionManagement>, add element
- add element, connectionManagement
- connectionManagement, add element
ms.assetid: 856bf57d-1c63-46c7-a178-03d97b0a4149
ms.openlocfilehash: 608c591b910252dd60950bf2aa7565d6df04d5fc
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/21/2019
ms.locfileid: "69664232"
---
# <a name="add-element-for-connectionmanagement-network-settings"></a><span data-ttu-id="08763-102">\<为 connectionManagement 添加 > 元素 (网络设置)</span><span class="sxs-lookup"><span data-stu-id="08763-102">\<add> Element for connectionManagement (Network Settings)</span></span>
<span data-ttu-id="08763-103">将 IP 地址或 DNS 名称添加到连接管理列表。</span><span class="sxs-lookup"><span data-stu-id="08763-103">Adds an IP address or DNS name to the connection management list.</span></span>  
  
 <span data-ttu-id="08763-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="08763-104">\<configuration></span></span>  
<span data-ttu-id="08763-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="08763-105">\<system.net></span></span>  
<span data-ttu-id="08763-106">\<connectionManagement></span><span class="sxs-lookup"><span data-stu-id="08763-106">\<connectionManagement></span></span>  
<span data-ttu-id="08763-107">\<add></span><span class="sxs-lookup"><span data-stu-id="08763-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="08763-108">语法</span><span class="sxs-lookup"><span data-stu-id="08763-108">Syntax</span></span>  
  
```xml  
<add   
  address="address expression"   
  maxconnection="integer"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="08763-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="08763-109">Attributes and Elements</span></span>  
 <span data-ttu-id="08763-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="08763-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="08763-111">特性</span><span class="sxs-lookup"><span data-stu-id="08763-111">Attributes</span></span>  
  
|<span data-ttu-id="08763-112">**特性**</span><span class="sxs-lookup"><span data-stu-id="08763-112">**Attribute**</span></span>|<span data-ttu-id="08763-113">**说明**</span><span class="sxs-lookup"><span data-stu-id="08763-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`address`|<span data-ttu-id="08763-114">描述 IP 地址或 DNS 名称的字符串。</span><span class="sxs-lookup"><span data-stu-id="08763-114">A string describing an IP address or DNS name.</span></span>|  
|`maxconnection`|<span data-ttu-id="08763-115">允许连接至服务器的最大连接数。</span><span class="sxs-lookup"><span data-stu-id="08763-115">The maximum number of connections allowed to a server.</span></span> <span data-ttu-id="08763-116">如果未提供，则默认为 2。</span><span class="sxs-lookup"><span data-stu-id="08763-116">If not supplied, the default is 2.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="08763-117">子元素</span><span class="sxs-lookup"><span data-stu-id="08763-117">Child Elements</span></span>  
 <span data-ttu-id="08763-118">无。</span><span class="sxs-lookup"><span data-stu-id="08763-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="08763-119">父元素</span><span class="sxs-lookup"><span data-stu-id="08763-119">Parent Elements</span></span>  
  
|<span data-ttu-id="08763-120">**元素**</span><span class="sxs-lookup"><span data-stu-id="08763-120">**Element**</span></span>|<span data-ttu-id="08763-121">**说明**</span><span class="sxs-lookup"><span data-stu-id="08763-121">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="08763-122">connectionManagement</span><span class="sxs-lookup"><span data-stu-id="08763-122">connectionManagement</span></span>](connectionmanagement-element-network-settings.md)|<span data-ttu-id="08763-123">指定到网络主机的最大连接数。</span><span class="sxs-lookup"><span data-stu-id="08763-123">Specifies the maximum number of connections to a network host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="08763-124">备注</span><span class="sxs-lookup"><span data-stu-id="08763-124">Remarks</span></span>  
 <span data-ttu-id="08763-125">`address` 特性的值应该是一个星号以指示所有连接，或为 `<schema>://<idn_hostname>[:<port>]` 格式的字符串。</span><span class="sxs-lookup"><span data-stu-id="08763-125">The value of the `address` attribute should be either an asterisk to indicate all connections, or a string of the form `<schema>://<idn_hostname>[:<port>]`.</span></span>  
  
 <span data-ttu-id="08763-126">如果传递到任何 HTTP API 的 URI 包含 Unicode，那么将使用 <xref:System.Uri.DnsSafeHost%2A> 内部转换名称，这可能会返回一个 punicode 字符串（行为取决于当前 IDN 配置）。</span><span class="sxs-lookup"><span data-stu-id="08763-126">If the URI passed to any HTTP APIs contains Unicode, the name will be converted internally using <xref:System.Uri.DnsSafeHost%2A> which might return a punicode string (behavior dependent on the current IDN configuration).</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="08763-127">配置文件</span><span class="sxs-lookup"><span data-stu-id="08763-127">Configuration Files</span></span>  
 <span data-ttu-id="08763-128">此元素可在应用程序配置文件或计算机配置文件 (Machine.config) 中使用。</span><span class="sxs-lookup"><span data-stu-id="08763-128">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="08763-129">示例</span><span class="sxs-lookup"><span data-stu-id="08763-129">Example</span></span>  
 <span data-ttu-id="08763-130">下面的示例将应用程序配置为使用四个到服务器`www.contoso.com`的连接, 以及两个与其他服务器的连接。</span><span class="sxs-lookup"><span data-stu-id="08763-130">The following example configures an application to use four connections to the server `www.contoso.com` and two connections to all other servers.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <connectionManagement>  
      <add address="http://www.contoso.com" maxconnection="4" />  
      <add address="*" maxconnection="2" />  
    </connectionManagement>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="08763-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="08763-131">See also</span></span>

- <xref:System.Net.ServicePoint>
- <xref:System.Net.ServicePointManager>
- [<span data-ttu-id="08763-132">网络设置架构</span><span class="sxs-lookup"><span data-stu-id="08763-132">Network Settings Schema</span></span>](index.md)
