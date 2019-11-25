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
ms.openlocfilehash: 287e36dce65be7a002499d2cd22481018a1f4742
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/14/2019
ms.locfileid: "74089170"
---
# <a name="remove-element-for-connectionmanagement-network-settings"></a><span data-ttu-id="39696-102">\<删除 connectionManagement 的 > 元素（网络设置）</span><span class="sxs-lookup"><span data-stu-id="39696-102">\<remove> Element for connectionManagement (Network Settings)</span></span>
<span data-ttu-id="39696-103">从连接管理列表中删除 IP 地址或 DNS 名称。</span><span class="sxs-lookup"><span data-stu-id="39696-103">Removes an IP address or DNS name from the connection management list.</span></span>  

<span data-ttu-id="39696-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="39696-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="39696-105">\<&nbsp;&nbsp;[ **> 的**](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="39696-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="39696-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<connectionManagement >** ](connectionmanagement-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="39696-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<connectionManagement>**](connectionmanagement-element-network-settings.md)</span></span>\
<span data-ttu-id="39696-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<删除 >**</span><span class="sxs-lookup"><span data-stu-id="39696-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>

## <a name="syntax"></a><span data-ttu-id="39696-108">语法</span><span class="sxs-lookup"><span data-stu-id="39696-108">Syntax</span></span>  
  
```xml  
<remove   
  address="server name or IP address"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="39696-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="39696-109">Attributes and Elements</span></span>  
 <span data-ttu-id="39696-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="39696-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="39696-111">特性</span><span class="sxs-lookup"><span data-stu-id="39696-111">Attributes</span></span>  
  
|<span data-ttu-id="39696-112">**特性**</span><span class="sxs-lookup"><span data-stu-id="39696-112">**Attribute**</span></span>|<span data-ttu-id="39696-113">**描述**</span><span class="sxs-lookup"><span data-stu-id="39696-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`address`|<span data-ttu-id="39696-114">IP 地址或 DNS 名称。</span><span class="sxs-lookup"><span data-stu-id="39696-114">An IP address or DNS name.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="39696-115">子元素</span><span class="sxs-lookup"><span data-stu-id="39696-115">Child Elements</span></span>  
 <span data-ttu-id="39696-116">无。</span><span class="sxs-lookup"><span data-stu-id="39696-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="39696-117">父元素</span><span class="sxs-lookup"><span data-stu-id="39696-117">Parent Elements</span></span>  
  
|<span data-ttu-id="39696-118">**元素**</span><span class="sxs-lookup"><span data-stu-id="39696-118">**Element**</span></span>|<span data-ttu-id="39696-119">**描述**</span><span class="sxs-lookup"><span data-stu-id="39696-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="39696-120">connectionManagement</span><span class="sxs-lookup"><span data-stu-id="39696-120">connectionManagement</span></span>](connectionmanagement-element-network-settings.md)|<span data-ttu-id="39696-121">指定到网络主机的最大连接数。</span><span class="sxs-lookup"><span data-stu-id="39696-121">Specifies the maximum number of connections to a network host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="39696-122">备注</span><span class="sxs-lookup"><span data-stu-id="39696-122">Remarks</span></span>  
 <span data-ttu-id="39696-123">`remove` 元素将删除指定服务器的连接管理列表项。</span><span class="sxs-lookup"><span data-stu-id="39696-123">The `remove` element removes the connection management list entry for the specified server.</span></span>  
  
 <span data-ttu-id="39696-124">`address` 属性的值应为有效的 IP 地址或主机名。</span><span class="sxs-lookup"><span data-stu-id="39696-124">The value of the `address` attribute should be a valid IP address or host name.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="39696-125">配置文件</span><span class="sxs-lookup"><span data-stu-id="39696-125">Configuration Files</span></span>  
 <span data-ttu-id="39696-126">此元素可在应用程序配置文件或计算机配置文件 (Machine.config) 中使用。</span><span class="sxs-lookup"><span data-stu-id="39696-126">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="39696-127">示例</span><span class="sxs-lookup"><span data-stu-id="39696-127">Example</span></span>  
 <span data-ttu-id="39696-128">下面的示例将删除服务器 `www.adventure-works.com` 的任何连接管理列表项，然后将应用程序配置为使用四个到服务器的连接 `www.contoso.com` 以及两个与其他服务器的连接。</span><span class="sxs-lookup"><span data-stu-id="39696-128">The following example removes any connection management list entries for the server `www.adventure-works.com` and then configures an application to use four connections to the server `www.contoso.com` and two connections to all other servers.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="39696-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="39696-129">See also</span></span>

- <xref:System.Net.ServicePoint>
- <xref:System.Net.ServicePointManager>
- [<span data-ttu-id="39696-130">网络设置架构</span><span class="sxs-lookup"><span data-stu-id="39696-130">Network Settings Schema</span></span>](index.md)
