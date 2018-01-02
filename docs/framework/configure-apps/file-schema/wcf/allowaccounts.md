---
title: '&lt;allowAccounts&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 166923a9-a8ac-478f-92f9-529d9667f3a6
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a1716aa77808b2a9f8f3ca903dabf81b21b8f709
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ltallowaccountsgt"></a><span data-ttu-id="39fa0-102">&lt;allowAccounts&gt;</span><span class="sxs-lookup"><span data-stu-id="39fa0-102">&lt;allowAccounts&gt;</span></span>
<span data-ttu-id="39fa0-103">包含一个配置元素集合，这些元素指定进程的用户帐户，这些进程承载 [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] 服务并被授予了对该共享服务的连接访问权限。</span><span class="sxs-lookup"><span data-stu-id="39fa0-103">Contains a collection of configuration elements that specify user accounts for processes that host [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] services, and are granted connection access to the sharing service.</span></span>  
  
 <span data-ttu-id="39fa0-104">\<system.serviceModel.activation ></span><span class="sxs-lookup"><span data-stu-id="39fa0-104">\<system.serviceModel.activation></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39fa0-105">语法</span><span class="sxs-lookup"><span data-stu-id="39fa0-105">Syntax</span></span>  
  
```xml  
<allowAccounts>  
   <add securityIdentifier="String"/>  
</allowAccounts>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="39fa0-106">特性和元素</span><span class="sxs-lookup"><span data-stu-id="39fa0-106">Attributes and Elements</span></span>  
 <span data-ttu-id="39fa0-107">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="39fa0-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="39fa0-108">特性</span><span class="sxs-lookup"><span data-stu-id="39fa0-108">Attributes</span></span>  
 <span data-ttu-id="39fa0-109">无。</span><span class="sxs-lookup"><span data-stu-id="39fa0-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="39fa0-110">子元素</span><span class="sxs-lookup"><span data-stu-id="39fa0-110">Child Elements</span></span>  
  
|<span data-ttu-id="39fa0-111">特性</span><span class="sxs-lookup"><span data-stu-id="39fa0-111">Attribute</span></span>|<span data-ttu-id="39fa0-112">描述</span><span class="sxs-lookup"><span data-stu-id="39fa0-112">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="39fa0-113">\<add></span><span class="sxs-lookup"><span data-stu-id="39fa0-113">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-allowaccounts.md)|<span data-ttu-id="39fa0-114">添加进程的用户帐户，这些进程承载 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 服务并被授予了对该共享服务的连接访问权限。</span><span class="sxs-lookup"><span data-stu-id="39fa0-114">Adds a user account for processes that host [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] services, and are granted connection access to the sharing service</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="39fa0-115">父元素</span><span class="sxs-lookup"><span data-stu-id="39fa0-115">Parent Elements</span></span>  
  
|<span data-ttu-id="39fa0-116">元素</span><span class="sxs-lookup"><span data-stu-id="39fa0-116">Element</span></span>|<span data-ttu-id="39fa0-117">描述</span><span class="sxs-lookup"><span data-stu-id="39fa0-117">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="39fa0-118">[\<net.pipe >](../../../../../docs/framework/configure-apps/file-schema/wcf/net-pipe.md)或[ \<net.tcp >](../../../../../docs/framework/configure-apps/file-schema/wcf/net-tcp.md)</span><span class="sxs-lookup"><span data-stu-id="39fa0-118">[\<net.pipe>](../../../../../docs/framework/configure-apps/file-schema/wcf/net-pipe.md) or [\<net.tcp>](../../../../../docs/framework/configure-apps/file-schema/wcf/net-tcp.md)</span></span>|<span data-ttu-id="39fa0-119">指定 Net Pipe 或 TCP 共享服务的配置设置。</span><span class="sxs-lookup"><span data-stu-id="39fa0-119">Specifies configuration settings for the Net Pipe or TCP sharing services.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="39fa0-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="39fa0-120">See Also</span></span>  
 <xref:System.ServiceModel.Activation.Configuration.NetTcpSection.AllowAccounts%2A>  
 <xref:System.ServiceModel.Activation.Configuration.NetPipeSection.AllowAccounts%2A>  
 <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElementCollection>  
 <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElement>
