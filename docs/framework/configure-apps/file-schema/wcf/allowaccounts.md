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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 8e1cf4c4428814361a56b5fd06dcce9e1512c836
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="ltallowaccountsgt"></a><span data-ttu-id="33470-102">&lt;allowAccounts&gt;</span><span class="sxs-lookup"><span data-stu-id="33470-102">&lt;allowAccounts&gt;</span></span>
<span data-ttu-id="33470-103">包含一个配置元素集合，这些元素指定进程的用户帐户，这些进程承载 [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] 服务并被授予了对该共享服务的连接访问权限。</span><span class="sxs-lookup"><span data-stu-id="33470-103">Contains a collection of configuration elements that specify user accounts for processes that host [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] services, and are granted connection access to the sharing service.</span></span>  
  
 <span data-ttu-id="33470-104">\<system.serviceModel.activation ></span><span class="sxs-lookup"><span data-stu-id="33470-104">\<system.serviceModel.activation></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33470-105">语法</span><span class="sxs-lookup"><span data-stu-id="33470-105">Syntax</span></span>  
  
```xml  
<allowAccounts>  
   <add securityIdentifier="String"/>  
</allowAccounts>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="33470-106">特性和元素</span><span class="sxs-lookup"><span data-stu-id="33470-106">Attributes and Elements</span></span>  
 <span data-ttu-id="33470-107">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="33470-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="33470-108">特性</span><span class="sxs-lookup"><span data-stu-id="33470-108">Attributes</span></span>  
 <span data-ttu-id="33470-109">无。</span><span class="sxs-lookup"><span data-stu-id="33470-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="33470-110">子元素</span><span class="sxs-lookup"><span data-stu-id="33470-110">Child Elements</span></span>  
  
|<span data-ttu-id="33470-111">特性</span><span class="sxs-lookup"><span data-stu-id="33470-111">Attribute</span></span>|<span data-ttu-id="33470-112">描述</span><span class="sxs-lookup"><span data-stu-id="33470-112">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="33470-113">\<add></span><span class="sxs-lookup"><span data-stu-id="33470-113">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-allowaccounts.md)|<span data-ttu-id="33470-114">添加进程的用户帐户，这些进程承载 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 服务并被授予了对该共享服务的连接访问权限。</span><span class="sxs-lookup"><span data-stu-id="33470-114">Adds a user account for processes that host [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] services, and are granted connection access to the sharing service</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="33470-115">父元素</span><span class="sxs-lookup"><span data-stu-id="33470-115">Parent Elements</span></span>  
  
|<span data-ttu-id="33470-116">元素</span><span class="sxs-lookup"><span data-stu-id="33470-116">Element</span></span>|<span data-ttu-id="33470-117">描述</span><span class="sxs-lookup"><span data-stu-id="33470-117">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="33470-118">[\<net.pipe >](../../../../../docs/framework/configure-apps/file-schema/wcf/net-pipe.md)或[ \<net.tcp >](../../../../../docs/framework/configure-apps/file-schema/wcf/net-tcp.md)</span><span class="sxs-lookup"><span data-stu-id="33470-118">[\<net.pipe>](../../../../../docs/framework/configure-apps/file-schema/wcf/net-pipe.md) or [\<net.tcp>](../../../../../docs/framework/configure-apps/file-schema/wcf/net-tcp.md)</span></span>|<span data-ttu-id="33470-119">指定 Net Pipe 或 TCP 共享服务的配置设置。</span><span class="sxs-lookup"><span data-stu-id="33470-119">Specifies configuration settings for the Net Pipe or TCP sharing services.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="33470-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="33470-120">See Also</span></span>  
 <xref:System.ServiceModel.Activation.Configuration.NetTcpSection.AllowAccounts%2A>  
 <xref:System.ServiceModel.Activation.Configuration.NetPipeSection.AllowAccounts%2A>  
 <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElementCollection>  
 <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElement>
