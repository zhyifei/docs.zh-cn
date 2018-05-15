---
title: '&lt;清除&gt;connectionManagement （网络设置） 的元素'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/connectionManagement/clear
- http://schemas.microsoft.com/.NetConfiguration/v2.0#clear
helpviewer_keywords:
- <clear> element, connectionManagement
- connectionManagement, clear element
- clear element, connectionManagement
- <connectionManagement>, clear element
ms.assetid: fb259282-84c4-4dc4-a226-78d904a6edc3
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 5bcd17cfe1f3bd7531453b62552a4907df5b96bc
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="ltcleargt-element-for-connectionmanagement-network-settings"></a><span data-ttu-id="cf482-102">&lt;清除&gt;connectionManagement （网络设置） 的元素</span><span class="sxs-lookup"><span data-stu-id="cf482-102">&lt;clear&gt; Element for connectionManagement (Network Settings)</span></span>
<span data-ttu-id="cf482-103">清除连接管理列表。</span><span class="sxs-lookup"><span data-stu-id="cf482-103">Clears the connection management list.</span></span>  
  
 <span data-ttu-id="cf482-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="cf482-104">\<configuration></span></span>  
<span data-ttu-id="cf482-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="cf482-105">\<system.net></span></span>  
<span data-ttu-id="cf482-106">\<connectionManagement ></span><span class="sxs-lookup"><span data-stu-id="cf482-106">\<connectionManagement></span></span>  
<span data-ttu-id="cf482-107">\<清除 ></span><span class="sxs-lookup"><span data-stu-id="cf482-107">\<clear></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf482-108">语法</span><span class="sxs-lookup"><span data-stu-id="cf482-108">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cf482-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="cf482-109">Attributes and Elements</span></span>  
 <span data-ttu-id="cf482-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="cf482-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cf482-111">特性</span><span class="sxs-lookup"><span data-stu-id="cf482-111">Attributes</span></span>  
 <span data-ttu-id="cf482-112">无。</span><span class="sxs-lookup"><span data-stu-id="cf482-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="cf482-113">子元素</span><span class="sxs-lookup"><span data-stu-id="cf482-113">Child Elements</span></span>  
 <span data-ttu-id="cf482-114">无。</span><span class="sxs-lookup"><span data-stu-id="cf482-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="cf482-115">父元素</span><span class="sxs-lookup"><span data-stu-id="cf482-115">Parent Elements</span></span>  
  
|<span data-ttu-id="cf482-116">**元素**</span><span class="sxs-lookup"><span data-stu-id="cf482-116">**Element**</span></span>|<span data-ttu-id="cf482-117">**说明**</span><span class="sxs-lookup"><span data-stu-id="cf482-117">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="cf482-118">connectionManagement</span><span class="sxs-lookup"><span data-stu-id="cf482-118">connectionManagement</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/connectionmanagement-element-network-settings.md)|<span data-ttu-id="cf482-119">指定到网络主机的最大连接数。</span><span class="sxs-lookup"><span data-stu-id="cf482-119">Specifies the maximum number of connections to a network host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cf482-120">备注</span><span class="sxs-lookup"><span data-stu-id="cf482-120">Remarks</span></span>  
 <span data-ttu-id="cf482-121">`clear`元素清除连接管理列表中的所有条目。</span><span class="sxs-lookup"><span data-stu-id="cf482-121">The `clear` element clears all entries from the connection management list.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="cf482-122">配置文件</span><span class="sxs-lookup"><span data-stu-id="cf482-122">Configuration Files</span></span>  
 <span data-ttu-id="cf482-123">此元素可在应用程序配置文件或计算机配置文件 (Machine.config) 中使用。</span><span class="sxs-lookup"><span data-stu-id="cf482-123">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="cf482-124">示例</span><span class="sxs-lookup"><span data-stu-id="cf482-124">Example</span></span>  
 <span data-ttu-id="cf482-125">下面的示例清除连接管理列表，然后添加新服务器 www.contoso.com 和所有其他网络主机的连接管理条目。</span><span class="sxs-lookup"><span data-stu-id="cf482-125">The following example clears the connection management list and then adds new connection management entries for the server www.contoso.com and all other network hosts.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="cf482-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="cf482-126">See Also</span></span>  
 <xref:System.Net.ServicePoint>  
 <xref:System.Net.ServicePointManager>  
 [<span data-ttu-id="cf482-127">网络设置架构</span><span class="sxs-lookup"><span data-stu-id="cf482-127">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
