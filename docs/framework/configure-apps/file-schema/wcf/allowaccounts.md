---
title: '&lt;allowAccounts&gt;'
ms.date: 03/30/2017
ms.assetid: 166923a9-a8ac-478f-92f9-529d9667f3a6
ms.openlocfilehash: 61310d530cfec2862fb64155777cd0e88132f748
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/09/2019
ms.locfileid: "54145934"
---
# <a name="ltallowaccountsgt"></a><span data-ttu-id="841ef-102">&lt;allowAccounts&gt;</span><span class="sxs-lookup"><span data-stu-id="841ef-102">&lt;allowAccounts&gt;</span></span>
<span data-ttu-id="841ef-103">包含指定用户帐户对进程承载 Windows Communication Foundation (WCF) 服务并被授予了对该共享服务的连接访问的配置元素的集合。</span><span class="sxs-lookup"><span data-stu-id="841ef-103">Contains a collection of configuration elements that specify user accounts for processes that host Windows Communication Foundation (WCF) services, and are granted connection access to the sharing service.</span></span>  
  
 <span data-ttu-id="841ef-104">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="841ef-104">\<system.serviceModel.activation></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="841ef-105">语法</span><span class="sxs-lookup"><span data-stu-id="841ef-105">Syntax</span></span>  
  
```xml  
<allowAccounts>
  <add securityIdentifier="String" />
</allowAccounts>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="841ef-106">特性和元素</span><span class="sxs-lookup"><span data-stu-id="841ef-106">Attributes and Elements</span></span>  
 <span data-ttu-id="841ef-107">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="841ef-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="841ef-108">特性</span><span class="sxs-lookup"><span data-stu-id="841ef-108">Attributes</span></span>  
 <span data-ttu-id="841ef-109">无。</span><span class="sxs-lookup"><span data-stu-id="841ef-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="841ef-110">子元素</span><span class="sxs-lookup"><span data-stu-id="841ef-110">Child Elements</span></span>  
  
|<span data-ttu-id="841ef-111">特性</span><span class="sxs-lookup"><span data-stu-id="841ef-111">Attribute</span></span>|<span data-ttu-id="841ef-112">描述</span><span class="sxs-lookup"><span data-stu-id="841ef-112">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="841ef-113">\<add></span><span class="sxs-lookup"><span data-stu-id="841ef-113">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-allowaccounts.md)|<span data-ttu-id="841ef-114">添加进程的承载 WCF 服务并被授予对共享服务的连接访问权限的用户的帐户</span><span class="sxs-lookup"><span data-stu-id="841ef-114">Adds a user account for processes that host WCF services, and are granted connection access to the sharing service</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="841ef-115">父元素</span><span class="sxs-lookup"><span data-stu-id="841ef-115">Parent Elements</span></span>  
  
|<span data-ttu-id="841ef-116">元素</span><span class="sxs-lookup"><span data-stu-id="841ef-116">Element</span></span>|<span data-ttu-id="841ef-117">描述</span><span class="sxs-lookup"><span data-stu-id="841ef-117">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="841ef-118">[\<net.pipe >](../../../../../docs/framework/configure-apps/file-schema/wcf/net-pipe.md)或[ \<net.tcp >](../../../../../docs/framework/configure-apps/file-schema/wcf/net-tcp.md)</span><span class="sxs-lookup"><span data-stu-id="841ef-118">[\<net.pipe>](../../../../../docs/framework/configure-apps/file-schema/wcf/net-pipe.md) or [\<net.tcp>](../../../../../docs/framework/configure-apps/file-schema/wcf/net-tcp.md)</span></span>|<span data-ttu-id="841ef-119">指定 Net Pipe 或 TCP 共享服务的配置设置。</span><span class="sxs-lookup"><span data-stu-id="841ef-119">Specifies configuration settings for the Net Pipe or TCP sharing services.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="841ef-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="841ef-120">See Also</span></span>  
 <xref:System.ServiceModel.Activation.Configuration.NetTcpSection.AllowAccounts%2A>  
 <xref:System.ServiceModel.Activation.Configuration.NetPipeSection.AllowAccounts%2A>  
 <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElementCollection>  
 <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElement>
