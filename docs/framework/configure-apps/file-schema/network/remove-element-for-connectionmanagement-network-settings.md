---
title: '&lt;删除&gt;connectionManagement （网络设置） 的元素'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/connectionManagement/remove
- http://schemas.microsoft.com/.NetConfiguration/v2.0#remove
helpviewer_keywords:
- connectionManagement, remove element
- <remove> element, connectionManagement
- <connectionManagement>, remove element
- remove element, connectionManagement
ms.assetid: 94b81775-5a22-4975-8c47-8620c40c3f35
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 8d503e06139fc6ce14f4d2c50c46e4bcfeb1b860
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
ms.locfileid: "32754475"
---
# <a name="ltremovegt-element-for-connectionmanagement-network-settings"></a><span data-ttu-id="9fb13-102">&lt;删除&gt;connectionManagement （网络设置） 的元素</span><span class="sxs-lookup"><span data-stu-id="9fb13-102">&lt;remove&gt; Element for connectionManagement (Network Settings)</span></span>
<span data-ttu-id="9fb13-103">从连接管理列表中删除 IP 地址或 DNS 名称。</span><span class="sxs-lookup"><span data-stu-id="9fb13-103">Removes an IP address or DNS name from the connection management list.</span></span>  
  
 <span data-ttu-id="9fb13-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="9fb13-104">\<configuration></span></span>  
<span data-ttu-id="9fb13-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="9fb13-105">\<system.net></span></span>  
<span data-ttu-id="9fb13-106">\<connectionManagement ></span><span class="sxs-lookup"><span data-stu-id="9fb13-106">\<connectionManagement></span></span>  
<span data-ttu-id="9fb13-107">\<remove></span><span class="sxs-lookup"><span data-stu-id="9fb13-107">\<remove></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9fb13-108">语法</span><span class="sxs-lookup"><span data-stu-id="9fb13-108">Syntax</span></span>  
  
```xml  
<remove   
  address="server name or IP address"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9fb13-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="9fb13-109">Attributes and Elements</span></span>  
 <span data-ttu-id="9fb13-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="9fb13-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9fb13-111">特性</span><span class="sxs-lookup"><span data-stu-id="9fb13-111">Attributes</span></span>  
  
|<span data-ttu-id="9fb13-112">**特性**</span><span class="sxs-lookup"><span data-stu-id="9fb13-112">**Attribute**</span></span>|<span data-ttu-id="9fb13-113">**说明**</span><span class="sxs-lookup"><span data-stu-id="9fb13-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`address`|<span data-ttu-id="9fb13-114">IP 地址或 DNS 名称。</span><span class="sxs-lookup"><span data-stu-id="9fb13-114">An IP address or DNS name.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9fb13-115">子元素</span><span class="sxs-lookup"><span data-stu-id="9fb13-115">Child Elements</span></span>  
 <span data-ttu-id="9fb13-116">无。</span><span class="sxs-lookup"><span data-stu-id="9fb13-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9fb13-117">父元素</span><span class="sxs-lookup"><span data-stu-id="9fb13-117">Parent Elements</span></span>  
  
|<span data-ttu-id="9fb13-118">**元素**</span><span class="sxs-lookup"><span data-stu-id="9fb13-118">**Element**</span></span>|<span data-ttu-id="9fb13-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="9fb13-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="9fb13-120">connectionManagement</span><span class="sxs-lookup"><span data-stu-id="9fb13-120">connectionManagement</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/connectionmanagement-element-network-settings.md)|<span data-ttu-id="9fb13-121">指定到网络主机的最大连接数。</span><span class="sxs-lookup"><span data-stu-id="9fb13-121">Specifies the maximum number of connections to a network host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9fb13-122">备注</span><span class="sxs-lookup"><span data-stu-id="9fb13-122">Remarks</span></span>  
 <span data-ttu-id="9fb13-123">`remove`元素中移除指定的服务器的连接管理列表项。</span><span class="sxs-lookup"><span data-stu-id="9fb13-123">The `remove` element removes the connection management list entry for the specified server.</span></span>  
  
 <span data-ttu-id="9fb13-124">值`address`属性应为有效的 IP 地址或主机名。</span><span class="sxs-lookup"><span data-stu-id="9fb13-124">The value of the `address` attribute should be a valid IP address or host name.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="9fb13-125">配置文件</span><span class="sxs-lookup"><span data-stu-id="9fb13-125">Configuration Files</span></span>  
 <span data-ttu-id="9fb13-126">此元素可在应用程序配置文件或计算机配置文件 (Machine.config) 中使用。</span><span class="sxs-lookup"><span data-stu-id="9fb13-126">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="9fb13-127">示例</span><span class="sxs-lookup"><span data-stu-id="9fb13-127">Example</span></span>  
 <span data-ttu-id="9fb13-128">下面的示例中移除服务器 www.adventure-works.com 所有连接管理列表条目，然后配置应用程序使用 4 个到 www.contoso.com 和两个连接到所有其他服务器。</span><span class="sxs-lookup"><span data-stu-id="9fb13-128">The following example removes any connection management list entries for the server www.adventure-works.com and then configures an application to use four connections to the server www.contoso.com and two connections to all other servers.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <connectionManagement>  
      <remove address="http://www.adventure-works.com" />  
      <add address="http://www.contoso.com" maxconnection="4" />  
      <add address="*" maxconnection="2" />  
    </connectionManagement>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="9fb13-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="9fb13-129">See Also</span></span>  
 <xref:System.Net.ServicePoint>  
 <xref:System.Net.ServicePointManager>  
 [<span data-ttu-id="9fb13-130">网络设置架构</span><span class="sxs-lookup"><span data-stu-id="9fb13-130">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
