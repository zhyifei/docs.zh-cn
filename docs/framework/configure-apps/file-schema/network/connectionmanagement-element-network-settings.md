---
title: '&lt;connectionManagement&gt;元素 （网络设置）'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/connectionManagement
- http://schemas.microsoft.com/.NetConfiguration/v2.0#connectionManagement
helpviewer_keywords:
- <connectionManagement> element
- connectionManagement element
ms.assetid: bedccaab-12a2-4511-8f67-e961f249aec6
ms.openlocfilehash: 28864de79e809968f7efa6f3b052cfd599961854
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54685021"
---
# <a name="ltconnectionmanagementgt-element-network-settings"></a><span data-ttu-id="ae513-102">&lt;connectionManagement&gt;元素 （网络设置）</span><span class="sxs-lookup"><span data-stu-id="ae513-102">&lt;connectionManagement&gt; Element (Network Settings)</span></span>
<span data-ttu-id="ae513-103">指定到网络主机的最大连接数。</span><span class="sxs-lookup"><span data-stu-id="ae513-103">Specifies the maximum number of connections to a network host.</span></span>  
  
 <span data-ttu-id="ae513-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="ae513-104">\<configuration></span></span>  
<span data-ttu-id="ae513-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="ae513-105">\<system.net></span></span>  
<span data-ttu-id="ae513-106">\<connectionManagement></span><span class="sxs-lookup"><span data-stu-id="ae513-106">\<connectionManagement></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae513-107">语法</span><span class="sxs-lookup"><span data-stu-id="ae513-107">Syntax</span></span>  
  
```xml  
<connectionManagement>   
</connectionManagement>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ae513-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="ae513-108">Attributes and Elements</span></span>  
 <span data-ttu-id="ae513-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="ae513-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ae513-110">特性</span><span class="sxs-lookup"><span data-stu-id="ae513-110">Attributes</span></span>  
 <span data-ttu-id="ae513-111">无。</span><span class="sxs-lookup"><span data-stu-id="ae513-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="ae513-112">子元素</span><span class="sxs-lookup"><span data-stu-id="ae513-112">Child Elements</span></span>  
  
|<span data-ttu-id="ae513-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="ae513-113">**Element**</span></span>|<span data-ttu-id="ae513-114">**说明**</span><span class="sxs-lookup"><span data-stu-id="ae513-114">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="ae513-115">add</span><span class="sxs-lookup"><span data-stu-id="ae513-115">add</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/add-element-for-connectionmanagement-network-settings.md)|<span data-ttu-id="ae513-116">将 IP 地址或 DNS 名称添加到连接管理列表。</span><span class="sxs-lookup"><span data-stu-id="ae513-116">Adds an IP address or DNS name to the connection management list.</span></span>|  
|[<span data-ttu-id="ae513-117">clear</span><span class="sxs-lookup"><span data-stu-id="ae513-117">clear</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/clear-element-for-connectionmanagement-network-settings.md)|<span data-ttu-id="ae513-118">清除连接管理列表。</span><span class="sxs-lookup"><span data-stu-id="ae513-118">Clears the connection management list.</span></span>|  
|[<span data-ttu-id="ae513-119">remove</span><span class="sxs-lookup"><span data-stu-id="ae513-119">remove</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/remove-element-for-connectionmanagement-network-settings.md)|<span data-ttu-id="ae513-120">从连接管理列表中删除 IP 地址或 DNS 名称。</span><span class="sxs-lookup"><span data-stu-id="ae513-120">Removes an IP address or DNS name from the connection management list.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ae513-121">父元素</span><span class="sxs-lookup"><span data-stu-id="ae513-121">Parent Elements</span></span>  
  
|<span data-ttu-id="ae513-122">**元素**</span><span class="sxs-lookup"><span data-stu-id="ae513-122">**Element**</span></span>|<span data-ttu-id="ae513-123">**说明**</span><span class="sxs-lookup"><span data-stu-id="ae513-123">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="ae513-124">system.net</span><span class="sxs-lookup"><span data-stu-id="ae513-124">system.net</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)|<span data-ttu-id="ae513-125">包含指定 .NET Framework 如何连接到网络的设置。</span><span class="sxs-lookup"><span data-stu-id="ae513-125">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ae513-126">备注</span><span class="sxs-lookup"><span data-stu-id="ae513-126">Remarks</span></span>  
 <span data-ttu-id="ae513-127">`connectionManagement`元素到服务器或服务器组中定义的最大连接数。</span><span class="sxs-lookup"><span data-stu-id="ae513-127">The `connectionManagement` element defines the maximum number of connections to a server or group of servers.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="ae513-128">配置文件</span><span class="sxs-lookup"><span data-stu-id="ae513-128">Configuration Files</span></span>  
 <span data-ttu-id="ae513-129">此元素可在应用程序配置文件或计算机配置文件 (Machine.config) 中使用。</span><span class="sxs-lookup"><span data-stu-id="ae513-129">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ae513-130">示例</span><span class="sxs-lookup"><span data-stu-id="ae513-130">Example</span></span>  
 <span data-ttu-id="ae513-131">下面的示例配置应用程序使用与服务器的四个连接`www.contoso.com`和两个连接到所有其他服务器。</span><span class="sxs-lookup"><span data-stu-id="ae513-131">The following example configures an application to use four connections to the server `www.contoso.com` and two connections to all other servers.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <connectionManagement>  
      <add address = "http://www.contoso.com" maxconnection = "4" />  
      <add address = "*" maxconnection = "2" />  
    </connectionManagement>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ae513-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="ae513-132">See also</span></span>
- <xref:System.Net.ServicePoint>
- <xref:System.Net.ServicePointManager>
- [<span data-ttu-id="ae513-133">网络设置架构</span><span class="sxs-lookup"><span data-stu-id="ae513-133">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
