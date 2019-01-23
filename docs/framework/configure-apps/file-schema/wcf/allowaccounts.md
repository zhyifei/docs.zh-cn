---
title: '&lt;allowAccounts&gt;'
ms.date: 03/30/2017
ms.assetid: 166923a9-a8ac-478f-92f9-529d9667f3a6
ms.openlocfilehash: c1c4630e6191dbbe02688a4e4a9db9e18b8d36d2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54508406"
---
# <a name="ltallowaccountsgt"></a><span data-ttu-id="ee04d-102">&lt;allowAccounts&gt;</span><span class="sxs-lookup"><span data-stu-id="ee04d-102">&lt;allowAccounts&gt;</span></span>
<span data-ttu-id="ee04d-103">包含指定用户帐户对进程承载 Windows Communication Foundation (WCF) 服务并被授予了对该共享服务的连接访问的配置元素的集合。</span><span class="sxs-lookup"><span data-stu-id="ee04d-103">Contains a collection of configuration elements that specify user accounts for processes that host Windows Communication Foundation (WCF) services, and are granted connection access to the sharing service.</span></span>  
  
 <span data-ttu-id="ee04d-104">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="ee04d-104">\<system.serviceModel.activation></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ee04d-105">语法</span><span class="sxs-lookup"><span data-stu-id="ee04d-105">Syntax</span></span>  
  
```xml  
<allowAccounts>
  <add securityIdentifier="String" />
</allowAccounts>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ee04d-106">特性和元素</span><span class="sxs-lookup"><span data-stu-id="ee04d-106">Attributes and Elements</span></span>  
 <span data-ttu-id="ee04d-107">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="ee04d-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ee04d-108">特性</span><span class="sxs-lookup"><span data-stu-id="ee04d-108">Attributes</span></span>  
 <span data-ttu-id="ee04d-109">无。</span><span class="sxs-lookup"><span data-stu-id="ee04d-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="ee04d-110">子元素</span><span class="sxs-lookup"><span data-stu-id="ee04d-110">Child Elements</span></span>  
  
|<span data-ttu-id="ee04d-111">特性</span><span class="sxs-lookup"><span data-stu-id="ee04d-111">Attribute</span></span>|<span data-ttu-id="ee04d-112">描述</span><span class="sxs-lookup"><span data-stu-id="ee04d-112">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="ee04d-113">\<add></span><span class="sxs-lookup"><span data-stu-id="ee04d-113">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-allowaccounts.md)|<span data-ttu-id="ee04d-114">添加进程的承载 WCF 服务并被授予对共享服务的连接访问权限的用户的帐户</span><span class="sxs-lookup"><span data-stu-id="ee04d-114">Adds a user account for processes that host WCF services, and are granted connection access to the sharing service</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ee04d-115">父元素</span><span class="sxs-lookup"><span data-stu-id="ee04d-115">Parent Elements</span></span>  
  
|<span data-ttu-id="ee04d-116">元素</span><span class="sxs-lookup"><span data-stu-id="ee04d-116">Element</span></span>|<span data-ttu-id="ee04d-117">描述</span><span class="sxs-lookup"><span data-stu-id="ee04d-117">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ee04d-118">[\<net.pipe>](../../../../../docs/framework/configure-apps/file-schema/wcf/net-pipe.md) or [\<net.tcp>](../../../../../docs/framework/configure-apps/file-schema/wcf/net-tcp.md)</span><span class="sxs-lookup"><span data-stu-id="ee04d-118">[\<net.pipe>](../../../../../docs/framework/configure-apps/file-schema/wcf/net-pipe.md) or [\<net.tcp>](../../../../../docs/framework/configure-apps/file-schema/wcf/net-tcp.md)</span></span>|<span data-ttu-id="ee04d-119">指定 Net Pipe 或 TCP 共享服务的配置设置。</span><span class="sxs-lookup"><span data-stu-id="ee04d-119">Specifies configuration settings for the Net Pipe or TCP sharing services.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ee04d-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="ee04d-120">See also</span></span>
- <xref:System.ServiceModel.Activation.Configuration.NetTcpSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.NetPipeSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElementCollection>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElement>
