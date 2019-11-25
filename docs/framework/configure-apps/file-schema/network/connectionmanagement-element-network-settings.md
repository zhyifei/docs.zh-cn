---
title: <connectionManagement> 元素（网络设置）
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/connectionManagement
- http://schemas.microsoft.com/.NetConfiguration/v2.0#connectionManagement
helpviewer_keywords:
- <connectionManagement> element
- connectionManagement element
ms.assetid: bedccaab-12a2-4511-8f67-e961f249aec6
ms.openlocfilehash: b769dd8d3ed0c617d0d8f908e7ef516615da09a7
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088457"
---
# <a name="connectionmanagement-element-network-settings"></a><span data-ttu-id="69791-102">\<connectionManagement > 元素（网络设置）</span><span class="sxs-lookup"><span data-stu-id="69791-102">\<connectionManagement> Element (Network Settings)</span></span>
<span data-ttu-id="69791-103">指定到网络主机的最大连接数。</span><span class="sxs-lookup"><span data-stu-id="69791-103">Specifies the maximum number of connections to a network host.</span></span>  

<span data-ttu-id="69791-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="69791-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="69791-105">\<&nbsp;&nbsp;[ **> 的**](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="69791-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="69791-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<connectionManagement >**</span><span class="sxs-lookup"><span data-stu-id="69791-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<connectionManagement>**</span></span>

## <a name="syntax"></a><span data-ttu-id="69791-107">语法</span><span class="sxs-lookup"><span data-stu-id="69791-107">Syntax</span></span>  
  
```xml  
<connectionManagement>   
</connectionManagement>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="69791-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="69791-108">Attributes and Elements</span></span>  
 <span data-ttu-id="69791-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="69791-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="69791-110">特性</span><span class="sxs-lookup"><span data-stu-id="69791-110">Attributes</span></span>  
 <span data-ttu-id="69791-111">无。</span><span class="sxs-lookup"><span data-stu-id="69791-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="69791-112">子元素</span><span class="sxs-lookup"><span data-stu-id="69791-112">Child Elements</span></span>  
  
|<span data-ttu-id="69791-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="69791-113">**Element**</span></span>|<span data-ttu-id="69791-114">**描述**</span><span class="sxs-lookup"><span data-stu-id="69791-114">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="69791-115">add</span><span class="sxs-lookup"><span data-stu-id="69791-115">add</span></span>](add-element-for-connectionmanagement-network-settings.md)|<span data-ttu-id="69791-116">将 IP 地址或 DNS 名称添加到连接管理列表。</span><span class="sxs-lookup"><span data-stu-id="69791-116">Adds an IP address or DNS name to the connection management list.</span></span>|  
|[<span data-ttu-id="69791-117">clear</span><span class="sxs-lookup"><span data-stu-id="69791-117">clear</span></span>](clear-element-for-connectionmanagement-network-settings.md)|<span data-ttu-id="69791-118">清除连接管理列表。</span><span class="sxs-lookup"><span data-stu-id="69791-118">Clears the connection management list.</span></span>|  
|[<span data-ttu-id="69791-119">remove</span><span class="sxs-lookup"><span data-stu-id="69791-119">remove</span></span>](remove-element-for-connectionmanagement-network-settings.md)|<span data-ttu-id="69791-120">从连接管理列表中删除 IP 地址或 DNS 名称。</span><span class="sxs-lookup"><span data-stu-id="69791-120">Removes an IP address or DNS name from the connection management list.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="69791-121">父元素</span><span class="sxs-lookup"><span data-stu-id="69791-121">Parent Elements</span></span>  
  
|<span data-ttu-id="69791-122">**元素**</span><span class="sxs-lookup"><span data-stu-id="69791-122">**Element**</span></span>|<span data-ttu-id="69791-123">**描述**</span><span class="sxs-lookup"><span data-stu-id="69791-123">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="69791-124">system.net</span><span class="sxs-lookup"><span data-stu-id="69791-124">system.net</span></span>](system-net-element-network-settings.md)|<span data-ttu-id="69791-125">包含指定 .NET Framework 如何连接到网络的设置。</span><span class="sxs-lookup"><span data-stu-id="69791-125">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="69791-126">备注</span><span class="sxs-lookup"><span data-stu-id="69791-126">Remarks</span></span>  
 <span data-ttu-id="69791-127">`connectionManagement` 元素定义与服务器或服务器组的最大连接数。</span><span class="sxs-lookup"><span data-stu-id="69791-127">The `connectionManagement` element defines the maximum number of connections to a server or group of servers.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="69791-128">配置文件</span><span class="sxs-lookup"><span data-stu-id="69791-128">Configuration Files</span></span>  
 <span data-ttu-id="69791-129">此元素可在应用程序配置文件或计算机配置文件 (Machine.config) 中使用。</span><span class="sxs-lookup"><span data-stu-id="69791-129">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="69791-130">示例</span><span class="sxs-lookup"><span data-stu-id="69791-130">Example</span></span>  
 <span data-ttu-id="69791-131">下面的示例将应用程序配置为使用服务器 `www.contoso.com` 的四个连接，并将两个连接连接到所有其他服务器。</span><span class="sxs-lookup"><span data-stu-id="69791-131">The following example configures an application to use four connections to the server `www.contoso.com` and two connections to all other servers.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="69791-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="69791-132">See also</span></span>

- <xref:System.Net.ServicePoint>
- <xref:System.Net.ServicePointManager>
- [<span data-ttu-id="69791-133">网络设置架构</span><span class="sxs-lookup"><span data-stu-id="69791-133">Network Settings Schema</span></span>](index.md)
