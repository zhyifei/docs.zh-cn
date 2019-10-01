---
title: connectionManagement 的 <clear> 元素（网络设置）
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
ms.openlocfilehash: 17b380b12977423669fd413132d69a3082daca41
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2019
ms.locfileid: "71698363"
---
# <a name="clear-element-for-connectionmanagement-network-settings"></a><span data-ttu-id="91dac-102">用于 connectionManagement 的 0clear > 元素（网络设置） @no__t</span><span class="sxs-lookup"><span data-stu-id="91dac-102">\<clear> Element for connectionManagement (Network Settings)</span></span>
<span data-ttu-id="91dac-103">清除连接管理列表。</span><span class="sxs-lookup"><span data-stu-id="91dac-103">Clears the connection management list.</span></span>  
  
[<span data-ttu-id="91dac-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="91dac-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="91dac-105">&nbsp; @ no__t[ **\<system >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="91dac-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>  
<span data-ttu-id="91dac-106">&nbsp; @ no__t-1 @ no__t-2 @ no__t[ **\<connectionManagement >** ](connectionmanagement-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="91dac-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<connectionManagement>**](connectionmanagement-element-network-settings.md)</span></span>  
<span data-ttu-id="91dac-107">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 **\<clear >**</span><span class="sxs-lookup"><span data-stu-id="91dac-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91dac-108">语法</span><span class="sxs-lookup"><span data-stu-id="91dac-108">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="91dac-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="91dac-109">Attributes and Elements</span></span>  
 <span data-ttu-id="91dac-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="91dac-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="91dac-111">特性</span><span class="sxs-lookup"><span data-stu-id="91dac-111">Attributes</span></span>  
 <span data-ttu-id="91dac-112">无。</span><span class="sxs-lookup"><span data-stu-id="91dac-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="91dac-113">子元素</span><span class="sxs-lookup"><span data-stu-id="91dac-113">Child Elements</span></span>  
 <span data-ttu-id="91dac-114">无。</span><span class="sxs-lookup"><span data-stu-id="91dac-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="91dac-115">父元素</span><span class="sxs-lookup"><span data-stu-id="91dac-115">Parent Elements</span></span>  
  
|<span data-ttu-id="91dac-116">**元素**</span><span class="sxs-lookup"><span data-stu-id="91dac-116">**Element**</span></span>|<span data-ttu-id="91dac-117">**说明**</span><span class="sxs-lookup"><span data-stu-id="91dac-117">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="91dac-118">connectionManagement</span><span class="sxs-lookup"><span data-stu-id="91dac-118">connectionManagement</span></span>](connectionmanagement-element-network-settings.md)|<span data-ttu-id="91dac-119">指定到网络主机的最大连接数。</span><span class="sxs-lookup"><span data-stu-id="91dac-119">Specifies the maximum number of connections to a network host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="91dac-120">备注</span><span class="sxs-lookup"><span data-stu-id="91dac-120">Remarks</span></span>  
 <span data-ttu-id="91dac-121">@No__t 0 元素会清除连接管理列表中的所有条目。</span><span class="sxs-lookup"><span data-stu-id="91dac-121">The `clear` element clears all entries from the connection management list.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="91dac-122">配置文件</span><span class="sxs-lookup"><span data-stu-id="91dac-122">Configuration Files</span></span>  
 <span data-ttu-id="91dac-123">此元素可在应用程序配置文件或计算机配置文件 (Machine.config) 中使用。</span><span class="sxs-lookup"><span data-stu-id="91dac-123">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="91dac-124">示例</span><span class="sxs-lookup"><span data-stu-id="91dac-124">Example</span></span>  
 <span data-ttu-id="91dac-125">下面的示例将清除 "连接管理" 列表，然后为服务器 `www.contoso.com` 和所有其他网络主机添加新的连接管理条目。</span><span class="sxs-lookup"><span data-stu-id="91dac-125">The following example clears the connection management list and then adds new connection management entries for the server `www.contoso.com` and all other network hosts.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="91dac-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="91dac-126">See also</span></span>

- <xref:System.Net.ServicePoint>
- <xref:System.Net.ServicePointManager>
- [<span data-ttu-id="91dac-127">网络设置架构</span><span class="sxs-lookup"><span data-stu-id="91dac-127">Network Settings Schema</span></span>](index.md)
