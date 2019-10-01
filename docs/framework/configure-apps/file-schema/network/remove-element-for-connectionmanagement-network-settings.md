---
title: connectionManagement 的 <remove> 元素（网络设置）
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
ms.openlocfilehash: cbafd29be6855cbb95d17388791ba152230295cc
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2019
ms.locfileid: "71697845"
---
# <a name="remove-element-for-connectionmanagement-network-settings"></a><span data-ttu-id="28f85-102">用于 connectionManagement 的 0remove > 元素（网络设置） @no__t</span><span class="sxs-lookup"><span data-stu-id="28f85-102">\<remove> Element for connectionManagement (Network Settings)</span></span>
<span data-ttu-id="28f85-103">从连接管理列表中删除 IP 地址或 DNS 名称。</span><span class="sxs-lookup"><span data-stu-id="28f85-103">Removes an IP address or DNS name from the connection management list.</span></span>  
  
[<span data-ttu-id="28f85-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="28f85-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="28f85-105">&nbsp; @ no__t[ **\<system >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="28f85-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>  
<span data-ttu-id="28f85-106">&nbsp; @ no__t-1 @ no__t-2 @ no__t[ **\<connectionManagement >** ](connectionmanagement-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="28f85-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<connectionManagement>**](connectionmanagement-element-network-settings.md)</span></span>  
<span data-ttu-id="28f85-107">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 **\<remove >**</span><span class="sxs-lookup"><span data-stu-id="28f85-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="28f85-108">语法</span><span class="sxs-lookup"><span data-stu-id="28f85-108">Syntax</span></span>  
  
```xml  
<remove   
  address="server name or IP address"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="28f85-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="28f85-109">Attributes and Elements</span></span>  
 <span data-ttu-id="28f85-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="28f85-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="28f85-111">特性</span><span class="sxs-lookup"><span data-stu-id="28f85-111">Attributes</span></span>  
  
|<span data-ttu-id="28f85-112">**特性**</span><span class="sxs-lookup"><span data-stu-id="28f85-112">**Attribute**</span></span>|<span data-ttu-id="28f85-113">**说明**</span><span class="sxs-lookup"><span data-stu-id="28f85-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`address`|<span data-ttu-id="28f85-114">IP 地址或 DNS 名称。</span><span class="sxs-lookup"><span data-stu-id="28f85-114">An IP address or DNS name.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="28f85-115">子元素</span><span class="sxs-lookup"><span data-stu-id="28f85-115">Child Elements</span></span>  
 <span data-ttu-id="28f85-116">无。</span><span class="sxs-lookup"><span data-stu-id="28f85-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="28f85-117">父元素</span><span class="sxs-lookup"><span data-stu-id="28f85-117">Parent Elements</span></span>  
  
|<span data-ttu-id="28f85-118">**元素**</span><span class="sxs-lookup"><span data-stu-id="28f85-118">**Element**</span></span>|<span data-ttu-id="28f85-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="28f85-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="28f85-120">connectionManagement</span><span class="sxs-lookup"><span data-stu-id="28f85-120">connectionManagement</span></span>](connectionmanagement-element-network-settings.md)|<span data-ttu-id="28f85-121">指定到网络主机的最大连接数。</span><span class="sxs-lookup"><span data-stu-id="28f85-121">Specifies the maximum number of connections to a network host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="28f85-122">备注</span><span class="sxs-lookup"><span data-stu-id="28f85-122">Remarks</span></span>  
 <span data-ttu-id="28f85-123">@No__t-0 元素删除指定服务器的连接管理列表项。</span><span class="sxs-lookup"><span data-stu-id="28f85-123">The `remove` element removes the connection management list entry for the specified server.</span></span>  
  
 <span data-ttu-id="28f85-124">@No__t-0 属性的值应为有效的 IP 地址或主机名。</span><span class="sxs-lookup"><span data-stu-id="28f85-124">The value of the `address` attribute should be a valid IP address or host name.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="28f85-125">配置文件</span><span class="sxs-lookup"><span data-stu-id="28f85-125">Configuration Files</span></span>  
 <span data-ttu-id="28f85-126">此元素可在应用程序配置文件或计算机配置文件 (Machine.config) 中使用。</span><span class="sxs-lookup"><span data-stu-id="28f85-126">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="28f85-127">示例</span><span class="sxs-lookup"><span data-stu-id="28f85-127">Example</span></span>  
 <span data-ttu-id="28f85-128">下面的示例将删除服务器的任何连接管理列表项 `www.adventure-works.com`，然后将应用程序配置为使用四个到服务器的连接，`www.contoso.com` 和两个与所有其他服务器的连接。</span><span class="sxs-lookup"><span data-stu-id="28f85-128">The following example removes any connection management list entries for the server `www.adventure-works.com` and then configures an application to use four connections to the server `www.contoso.com` and two connections to all other servers.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="28f85-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="28f85-129">See also</span></span>

- <xref:System.Net.ServicePoint>
- <xref:System.Net.ServicePointManager>
- [<span data-ttu-id="28f85-130">网络设置架构</span><span class="sxs-lookup"><span data-stu-id="28f85-130">Network Settings Schema</span></span>](index.md)
