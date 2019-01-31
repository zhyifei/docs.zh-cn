---
title: connectionManagement -> <clear> 元素（网络设置）
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
ms.openlocfilehash: b90bdacc962eba1cd449f347f958f04cd72225d4
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2019
ms.locfileid: "55273918"
---
# <a name="clear-element-for-connectionmanagement-network-settings"></a><span data-ttu-id="758ba-102">\<清除 > connectionManagement （网络设置） 的元素</span><span class="sxs-lookup"><span data-stu-id="758ba-102">\<clear> Element for connectionManagement (Network Settings)</span></span>
<span data-ttu-id="758ba-103">清除连接管理列表。</span><span class="sxs-lookup"><span data-stu-id="758ba-103">Clears the connection management list.</span></span>  
  
 <span data-ttu-id="758ba-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="758ba-104">\<configuration></span></span>  
<span data-ttu-id="758ba-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="758ba-105">\<system.net></span></span>  
<span data-ttu-id="758ba-106">\<connectionManagement></span><span class="sxs-lookup"><span data-stu-id="758ba-106">\<connectionManagement></span></span>  
<span data-ttu-id="758ba-107">\<clear></span><span class="sxs-lookup"><span data-stu-id="758ba-107">\<clear></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="758ba-108">语法</span><span class="sxs-lookup"><span data-stu-id="758ba-108">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="758ba-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="758ba-109">Attributes and Elements</span></span>  
 <span data-ttu-id="758ba-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="758ba-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="758ba-111">特性</span><span class="sxs-lookup"><span data-stu-id="758ba-111">Attributes</span></span>  
 <span data-ttu-id="758ba-112">无。</span><span class="sxs-lookup"><span data-stu-id="758ba-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="758ba-113">子元素</span><span class="sxs-lookup"><span data-stu-id="758ba-113">Child Elements</span></span>  
 <span data-ttu-id="758ba-114">无。</span><span class="sxs-lookup"><span data-stu-id="758ba-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="758ba-115">父元素</span><span class="sxs-lookup"><span data-stu-id="758ba-115">Parent Elements</span></span>  
  
|<span data-ttu-id="758ba-116">**元素**</span><span class="sxs-lookup"><span data-stu-id="758ba-116">**Element**</span></span>|<span data-ttu-id="758ba-117">**说明**</span><span class="sxs-lookup"><span data-stu-id="758ba-117">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="758ba-118">connectionManagement</span><span class="sxs-lookup"><span data-stu-id="758ba-118">connectionManagement</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/connectionmanagement-element-network-settings.md)|<span data-ttu-id="758ba-119">指定到网络主机的最大连接数。</span><span class="sxs-lookup"><span data-stu-id="758ba-119">Specifies the maximum number of connections to a network host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="758ba-120">备注</span><span class="sxs-lookup"><span data-stu-id="758ba-120">Remarks</span></span>  
 <span data-ttu-id="758ba-121">`clear`元素清除连接管理列表中的所有条目。</span><span class="sxs-lookup"><span data-stu-id="758ba-121">The `clear` element clears all entries from the connection management list.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="758ba-122">配置文件</span><span class="sxs-lookup"><span data-stu-id="758ba-122">Configuration Files</span></span>  
 <span data-ttu-id="758ba-123">此元素可在应用程序配置文件或计算机配置文件 (Machine.config) 中使用。</span><span class="sxs-lookup"><span data-stu-id="758ba-123">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="758ba-124">示例</span><span class="sxs-lookup"><span data-stu-id="758ba-124">Example</span></span>  
 <span data-ttu-id="758ba-125">以下示例清除连接管理列表中，然后添加新的服务器的连接管理条目`www.contoso.com`和所有其他网络主机。</span><span class="sxs-lookup"><span data-stu-id="758ba-125">The following example clears the connection management list and then adds new connection management entries for the server `www.contoso.com` and all other network hosts.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="758ba-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="758ba-126">See also</span></span>
- <xref:System.Net.ServicePoint>
- <xref:System.Net.ServicePointManager>
- [<span data-ttu-id="758ba-127">网络设置架构</span><span class="sxs-lookup"><span data-stu-id="758ba-127">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
