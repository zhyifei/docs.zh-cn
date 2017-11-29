---
title: "&lt;清除&gt;connectionManagement （网络设置） 的元素"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/connectionManagement/clear
- http://schemas.microsoft.com/.NetConfiguration/v2.0#clear
helpviewer_keywords:
- <clear> element, connectionManagement
- connectionManagement, clear element
- clear element, connectionManagement
- <connectionManagement>, clear element
ms.assetid: fb259282-84c4-4dc4-a226-78d904a6edc3
caps.latest.revision: "13"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 0fe32b20b9b0a0217ecef36f65ae1ee4084e92ad
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="ltcleargt-element-for-connectionmanagement-network-settings"></a><span data-ttu-id="98e76-102">&lt;清除&gt;connectionManagement （网络设置） 的元素</span><span class="sxs-lookup"><span data-stu-id="98e76-102">&lt;clear&gt; Element for connectionManagement (Network Settings)</span></span>
<span data-ttu-id="98e76-103">清除连接管理列表。</span><span class="sxs-lookup"><span data-stu-id="98e76-103">Clears the connection management list.</span></span>  
  
 <span data-ttu-id="98e76-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="98e76-104">\<configuration></span></span>  
<span data-ttu-id="98e76-105">\<system.net ></span><span class="sxs-lookup"><span data-stu-id="98e76-105">\<system.net></span></span>  
<span data-ttu-id="98e76-106">\<connectionManagement ></span><span class="sxs-lookup"><span data-stu-id="98e76-106">\<connectionManagement></span></span>  
<span data-ttu-id="98e76-107">\<清除 ></span><span class="sxs-lookup"><span data-stu-id="98e76-107">\<clear></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="98e76-108">语法</span><span class="sxs-lookup"><span data-stu-id="98e76-108">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="98e76-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="98e76-109">Attributes and Elements</span></span>  
 <span data-ttu-id="98e76-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="98e76-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="98e76-111">特性</span><span class="sxs-lookup"><span data-stu-id="98e76-111">Attributes</span></span>  
 <span data-ttu-id="98e76-112">无。</span><span class="sxs-lookup"><span data-stu-id="98e76-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="98e76-113">子元素</span><span class="sxs-lookup"><span data-stu-id="98e76-113">Child Elements</span></span>  
 <span data-ttu-id="98e76-114">无。</span><span class="sxs-lookup"><span data-stu-id="98e76-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="98e76-115">父元素</span><span class="sxs-lookup"><span data-stu-id="98e76-115">Parent Elements</span></span>  
  
|<span data-ttu-id="98e76-116">**元素**</span><span class="sxs-lookup"><span data-stu-id="98e76-116">**Element**</span></span>|<span data-ttu-id="98e76-117">**描述**</span><span class="sxs-lookup"><span data-stu-id="98e76-117">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="98e76-118">connectionManagement</span><span class="sxs-lookup"><span data-stu-id="98e76-118">connectionManagement</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/connectionmanagement-element-network-settings.md)|<span data-ttu-id="98e76-119">指定到网络主机的最大连接数。</span><span class="sxs-lookup"><span data-stu-id="98e76-119">Specifies the maximum number of connections to a network host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="98e76-120">备注</span><span class="sxs-lookup"><span data-stu-id="98e76-120">Remarks</span></span>  
 <span data-ttu-id="98e76-121">`clear`元素清除连接管理列表中的所有条目。</span><span class="sxs-lookup"><span data-stu-id="98e76-121">The `clear` element clears all entries from the connection management list.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="98e76-122">配置文件</span><span class="sxs-lookup"><span data-stu-id="98e76-122">Configuration Files</span></span>  
 <span data-ttu-id="98e76-123">此元素可在应用程序配置文件或计算机配置文件 (Machine.config) 中使用。</span><span class="sxs-lookup"><span data-stu-id="98e76-123">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="98e76-124">示例</span><span class="sxs-lookup"><span data-stu-id="98e76-124">Example</span></span>  
 <span data-ttu-id="98e76-125">下面的示例清除连接管理列表，然后添加新服务器 www.contoso.com 和所有其他网络主机的连接管理条目。</span><span class="sxs-lookup"><span data-stu-id="98e76-125">The following example clears the connection management list and then adds new connection management entries for the server www.contoso.com and all other network hosts.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <connectionManagement>  
      <clear/>  
      <add address = "http://www.contoso.com" maxconnection = "4" />  
      <add address = "*" maxconnection = "2" />  
    </connectionManagement>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="98e76-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="98e76-126">See Also</span></span>  
 <xref:System.Net.ServicePoint>  
 <xref:System.Net.ServicePointManager>  
 [<span data-ttu-id="98e76-127">网络设置架构</span><span class="sxs-lookup"><span data-stu-id="98e76-127">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
