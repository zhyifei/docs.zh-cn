---
title: '&lt;allowAccounts&gt;'
ms.date: 03/30/2017
ms.assetid: 166923a9-a8ac-478f-92f9-529d9667f3a6
ms.openlocfilehash: bbfe0d5d531cf61c01f95d0e82ce0f894031d6f3
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="ltallowaccountsgt"></a><span data-ttu-id="35c37-102">&lt;allowAccounts&gt;</span><span class="sxs-lookup"><span data-stu-id="35c37-102">&lt;allowAccounts&gt;</span></span>
<span data-ttu-id="35c37-103">包含的指定用户帐户，进程承载 Windows Communication Foundation (WCF) 服务并被授予了对该共享服务的连接访问权限的配置元素的集合。</span><span class="sxs-lookup"><span data-stu-id="35c37-103">Contains a collection of configuration elements that specify user accounts for processes that host Windows Communication Foundation (WCF) services, and are granted connection access to the sharing service.</span></span>  
  
 <span data-ttu-id="35c37-104">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="35c37-104">\<system.serviceModel.activation></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35c37-105">语法</span><span class="sxs-lookup"><span data-stu-id="35c37-105">Syntax</span></span>  
  
```xml  
<allowAccounts>  
   <add securityIdentifier="String"/>  
</allowAccounts>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="35c37-106">特性和元素</span><span class="sxs-lookup"><span data-stu-id="35c37-106">Attributes and Elements</span></span>  
 <span data-ttu-id="35c37-107">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="35c37-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="35c37-108">特性</span><span class="sxs-lookup"><span data-stu-id="35c37-108">Attributes</span></span>  
 <span data-ttu-id="35c37-109">无。</span><span class="sxs-lookup"><span data-stu-id="35c37-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="35c37-110">子元素</span><span class="sxs-lookup"><span data-stu-id="35c37-110">Child Elements</span></span>  
  
|<span data-ttu-id="35c37-111">特性</span><span class="sxs-lookup"><span data-stu-id="35c37-111">Attribute</span></span>|<span data-ttu-id="35c37-112">描述</span><span class="sxs-lookup"><span data-stu-id="35c37-112">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="35c37-113">\<add></span><span class="sxs-lookup"><span data-stu-id="35c37-113">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-allowaccounts.md)|<span data-ttu-id="35c37-114">添加进程的用户帐户，这些进程承载 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 服务并被授予了对该共享服务的连接访问权限。</span><span class="sxs-lookup"><span data-stu-id="35c37-114">Adds a user account for processes that host [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] services, and are granted connection access to the sharing service</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="35c37-115">父元素</span><span class="sxs-lookup"><span data-stu-id="35c37-115">Parent Elements</span></span>  
  
|<span data-ttu-id="35c37-116">元素</span><span class="sxs-lookup"><span data-stu-id="35c37-116">Element</span></span>|<span data-ttu-id="35c37-117">描述</span><span class="sxs-lookup"><span data-stu-id="35c37-117">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="35c37-118">[\<net.pipe >](../../../../../docs/framework/configure-apps/file-schema/wcf/net-pipe.md)或[ \<net.tcp >](../../../../../docs/framework/configure-apps/file-schema/wcf/net-tcp.md)</span><span class="sxs-lookup"><span data-stu-id="35c37-118">[\<net.pipe>](../../../../../docs/framework/configure-apps/file-schema/wcf/net-pipe.md) or [\<net.tcp>](../../../../../docs/framework/configure-apps/file-schema/wcf/net-tcp.md)</span></span>|<span data-ttu-id="35c37-119">指定 Net Pipe 或 TCP 共享服务的配置设置。</span><span class="sxs-lookup"><span data-stu-id="35c37-119">Specifies configuration settings for the Net Pipe or TCP sharing services.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="35c37-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="35c37-120">See Also</span></span>  
 <xref:System.ServiceModel.Activation.Configuration.NetTcpSection.AllowAccounts%2A>  
 <xref:System.ServiceModel.Activation.Configuration.NetPipeSection.AllowAccounts%2A>  
 <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElementCollection>  
 <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElement>
